---
jira_key: RH-16639
jira_url: "https://rtahotline.etas.com/jira/browse/RH-16639"
server: rtahotline
kind: hotline
type: Support
status: Waiting for Level 3
priority: Medium
project: RH
assignee: "[[Jens_Jung|Jens Jung]]"
reporter: "[[LIU_Dong_(ETAS-ECMXSF-CN)|Dong LIU]]"
tags: [jira/comp/communication-timeservices]
fix-versions: []
epic: null
parent: null
created: "2026-07-14T12:47:31.000+0200"
updated: "2026-09-11T09:30:14.000+0200"
synced-at: "2026-09-11T07:48:00.574Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Hi, 

The customer encountered some issues while using the Ethernet Time Synchronization module. They are using RTA-CAR 12.11.0VCTCESR1pr1. 

Issue Description: 

The PPS pulse transmitted by the customer's Ethernet master node has an offset of approximately  **2.5 µs** compared with the pulse transmitted by the switch. 

The master node generates a PPS pulse with a rising edge every second. The timing starts from the hardware timer initialized during  **Eth_Init**. The switch also generates a PPS pulse with a rising edge every second. Its timing starts when the  **Global Time** is initialized to  **0**. 

The customer suspects that there is a time gap between the execution of  **Eth_Init**,  **StbM_Init**, and  **StbM_SetGlobalTime()**. This delay causes a time offset between the Ethernet hardware timer on the master node and the Global Time, resulting in an approximately  **20 µs** offset between the master node's PPS pulse and the switch's pulse.  

After optimization, the customer modified the implementation so that  **StbM_Init()** is called immediately before  **StbM_SetGlobalTime()** to reset the Ethernet hardware timer. However, there is still an offset of approximately  **2.5 µs**. 

The customer believes that this remaining offset is caused by the time elapsed from the moment the  **globalTimeRx** parameter is passed into  **StbM_SetGlobalTime()** until it is assigned to  **StbM_GlobalTimeTupleArray_ast&#91;timeBaseIndex&#93;**:  StbM_GlobalTimeTupleArray_ast&#91;timeBaseIndex&#93; = *globalTimeRx; 

The virtual local time is compensated through the following function call: StbM_Rb_VltWriteElapsedReadCurrentTimeSync(timeBaseIndex, lTvSync_st, &lCurrentVlt_st); and then stored by: StbM_VirtualLocalTimeTupleArray_ast&#91;timeBaseIndex&#93; = lCurrentVlt_st。However, no similar compensation is applied before the following assignment:  StbM_GlobalTimeTupleArray_ast&#91;timeBaseIndex&#93; = **globalTimeRx;  According to the customer's analysis, the elapsed time before this assignment is more than  *1 µs**, which contributes to the remaining synchronization offset. 

 ![[RH-16639-image001.png]] 

 The variable highlighted in the red box above represents the Virtual Local Time, which is synchronized with the Ethernet hardware timer. 

 ![[RH-16639-image002.png]] 

 The variable highlighted in the red box above represents the Global Time. 

Customer Expectation:  

The customer would like to optimize away this delay of more than 1 µs. Could you please provide a solution or recommendation? Thank you! 

Best regards,

 

  **Dong LIU** 

 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China (ETAS-ECM/XSF-CN)

 Bosch (China) Investment Ltd. | 333 Fuquan (N.) Road | Shanghai 200335 |  P.R. CHINA 

 [Dong.LIU5@etas.com!mail_small.gif!](mailto:Dong.LIU5@etas.com)

## 评论

> [!note]+ 2026-09-11 09:30 · [[Sara_Pereira|Sara Pereira]]
> [[Pereira_Joao_(XCEVO-XPC-Brg1)|Joao Pereira]] is on leave. Team is analyzing and will get back to you as soon as possible. Sorry for the delayed response.

-------

> [!note]+ 2026-08-27 12:03 · [[LIU_Dong_(ETAS-ECMXSF-CN)|Dong LIU]]
> hi, [[Pereira_Joao_(XCEVO-XPC-Brg1)|Joao Pereira]] [[Phan_Huynh_Dang_Khoa_(MSETA-Hub-CN)|Khoa Phan Huynh Dang]] 
>
> Since Eth_SetPhcTime is not supported in StbM_SetGlobalTime, the customer is currently calling Eth_SetPhcTime manually. The call is shown in the screenshot below. When the Switch receives the Ethernet time synchronization message, it synchronizes the global clock. Based on the current PPS test results, the customer found that there is still a 2 μs time difference between the MCU and the Switch. The customer would like to reduce this time difference to less than 1 μs. Do you have any recommendations on how to reduce this time difference?
>
> ![[RH-16639-image-2026-08-27-18-03-29-462.png]]

-------

> [!note]+ 2026-08-17 15:07 · [[Pereira_Joao_(XCEVO-XPC-Brg1)|Joao Pereira]]
> Also, since we are not setting the time directly on PHC with current implementation, the global time is store in StbM global variables.  If the measurement is done with PPS counter of the corresponding phc, your measuring the difference of the free running counters not the global time.

-------

> [!note]+ 2026-08-11 11:18 · [[Phan_Huynh_Dang_Khoa_(MSETA-Hub-CN)|Khoa Phan Huynh Dang]]
> Hi [[LIU_Dong_(ETAS-ECMXSF-CN)|Dong LIU]] , do we have any new information from the customer 😅 ?

-------

> [!note]+ 2026-07-31 15:52 · [[Pereira_Joao_(XCEVO-XPC-Brg1)|Joao Pereira]]
> Hello [[Phan_Huynh_Dang_Khoa_(MSETA-Hub-CN)|Khoa Phan Huynh Dang]] ,
>
> Regarding the question:
>
> **"Why is the Global Time not compensated for elapsed time in the same way as the Virtual Local Time?"**
>
> The tuple \{TGsync, TVsync} forms a consistent reference pair, when time is read later, the formula TGsync + (TV - TVsync) correctly computes the current time regardless of any constant offset between the two stored values.
>
> The interval between the aquisition of global time and the call of **StbM_SetGlobalTime** can degrade the quality of the time. But that would be an integration problem not a problem in the StbM code.

-------

> [!note]+ 2026-07-31 09:45 · [[JSM_Service_Bot|JSM Service Bot]]
> Note: Khoa Phan Huynh Dang added as watcher to the issue. Internal support agents cannot be added as Request Participants, so they have been automatically joined as Watchers instead.

-------

> [!note]+ 2026-07-31 09:45 · [[LIU_Dong_(ETAS-ECMXSF-CN)|Dong LIU]]
> [[Phan_Huynh_Dang_Khoa_(MSETA-Hub-CN)|Khoa Phan Huynh Dang]] I'll need to check this with the customer.

-------

> [!note]+ 2026-07-31 06:36 · [[JSM_Service_Bot|JSM Service Bot]]
> Note: Joao Pereira added as watcher to the issue. Internal support agents cannot be added as Request Participants, so they have been automatically joined as Watchers instead.

-------

> [!note]+ 2026-07-31 06:36 · [[Phan_Huynh_Dang_Khoa_(MSETA-Hub-CN)|Khoa Phan Huynh Dang]]
> Hi [[LIU_Dong_(ETAS-ECMXSF-CN)|Dong LIU]] ,
>
>
> After discussing this with [[Pereira_Joao_(XCEVO-XPC-Brg1)|Joao Pereira]], we have one concern and would like the customer to provide additional information:
>
> Why is PPS being used for this measurement? In this scenario, the PPS-based measurement method may not be suitable and could introduce an offset in the observed value.
>
> Regarding the customer's concern, "Why is the Global Time not compensated for elapsed time in the same way as the Virtual Local Time?", [[Pereira_Joao_(XCEVO-XPC-Brg1)|Joao Pereira]] , could you please help provide a more detailed explanation to the customer?

-------

> [!note]+ 2026-07-29 03:43 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Phuong Nguyen Le]]
> [[Pereira_Joao_(XCEVO-XPC-Brg1)|Joao Pereira]] , [[LIU_Dong_(ETAS-ECMXSF-CN)|Dong LIU]] : Can you collaborate to understand the issue and provide solution as this is critical issue?

-------

> [!note]+ 2026-07-28 13:17 · [[Pereira_Joao_(XCEVO-XPC-Brg1)|Joao Pereira]]
> Hello [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Phuong Nguyen Le]],
>
> I'm still unsure about what is the setup of the project and the measurements.
> What is the PPS pulse that we are measuring? What is feading the PPS EthHw?
> StbM holds the time values in global time arrays. The local clock is used to calculate the enlapsed time to add to local time. Therefore I'm not sure what exactly are you measuring.

-------

> [!note]+ 2026-07-28 12:57 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Phuong Nguyen Le]]
> [[Pereira_Joao_(XCEVO-XPC-Brg1)|Joao Pereira]] , Do we have any update for this issue? 

-------

> [!note]+ 2026-07-21 15:59 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi [[Fadia_Nefati|Fadia Nefati]], this Communication-TimeServices ticket requires an assignee. As the component lead for Communication-TimeServices, please ensure that the 'Level 3 Assignee' field is set to the appropriate person that can handle this issue.

-------

> [!note]+ 2026-07-21 12:04 · [[LIU_Dong_(ETAS-ECMXSF-CN)|Dong LIU]]
> [[Shaker_Abdolrahman_Saleh|Shaker Abdolrahman Saleh]] 

-------

> [!note]+ 2026-07-21 12:03 · [[LIU_Dong_(ETAS-ECMXSF-CN)|Dong LIU]]
> [^Isolar.zip]

-------

> [!note]+ 2026-07-15 16:11 · [[Shaker_Abdolrahman_Saleh|Shaker Abdolrahman Saleh]]
> Hi [[LIU_Dong_(ETAS-ECMXSF-CN)|Dong LIU]],
>
> can you provide please the RTA-CAR Project
> with generated code so that we can analyze the observed issue with the customers project.
>
> Also can you tell us please how the time measurement was done for the observed time synchronization issue.
>
> Best
> Shaker

-------

> [!note]+ 2026-07-15 16:06 · [[Shaker_Abdolrahman_Saleh|Shaker Abdolrahman Saleh]]
> Hi [[Jens_Jung|Jens Jung]] and [[Fadia_Nefati|Fadia Nefati]],
>
> as described above the customer observes ~2.5 us time offset between their Ethernet master node's PPS pulse and the switch's PPS pulse.
>
> Accepted is a delay by approximately 1 us.
>
> Could not identify a parameter for changing this behavior.
> Do you have a recommendation or is this time offset, or is this a BSW code related issue that needs to be fixed?
>
> Customer would like to know:
> if its a configuration issue or a bug. In case its a bug if we can provide a timeline for providing a fix and in which form(e.g. updated RTA-CAR version or code patch).
>
>
>
> Best regards,
> Shaker

-------

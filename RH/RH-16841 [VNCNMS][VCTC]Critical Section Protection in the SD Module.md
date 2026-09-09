---
jira_key: RH-16841
jira_url: "https://rtahotline.etas.com/jira/browse/RH-16841"
server: rtahotline
kind: hotline
type: Support
status: Waiting for Level 3
priority: Critical
project: RH
assignee: shweta.ganeshdixit@in.bosch.com
reporter: dong.liu5@etas.com
tags: [VNCNMS]
components: [Communication-Eth]
fix-versions: []
epic: null
parent: null
created: "2026-08-04T20:07:35.000+0200"
updated: "2026-09-09T15:44:58.000+0200"
synced-at: "2026-09-09T13:45:59.638Z"
jira-orphaned: false
profile: Cariad
---

# RH-16841 [VNCNMS][VCTC]Critical Section Protection in the SD Module

> [!jira] Waiting for Level 3 · Critical · [[Shweta_Ganesh_Dixit|Shweta Ganesh Dixit]] · 更新于 2026-09-09T15:44:58.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-16841)

> 标签：#jira/comp/communication-eth #jira/label/vncnms

## 描述

Hi, 

The customer has a few questions regarding the SD module. They are currently using  **RTA-CAR 12.11.0VCTCESR1pr1**. Could you please help clarify them? Thank you! 

Issue Description: 

When the customer sends an  **SD OfferService** message, they occasionally observe an abnormal number of* 

 ***OfferService entries**.  

Under normal conditions, the OfferService entries are as shown in the figure below. 

![[RH-16841-image001.jpg]] 

The number of OfferService entries under abnormal conditions is shown in the figure below. 

![[RH-16841-image002.jpg]] 

The customer investigated the code and found that variables such as  **Sd_SrvrEntryTable_ast** and  **Sd_CnseEveGrAdminTable_ast** are accessed (read and written) in both  **Sd_MainFunction** and  **Sd_RxIndication**. However, there is no corresponding critical section protection implemented. 

Since  **Sd_RxIndication** is called in the receive interrupt context, the customer suspects that when  **Sd_MainFunction** is operating on these variables, it could be interrupted by  **Sd_RxIndication**, which may modify these variables and cause data inconsistency. 

 **Customer requests:** 

1. The customer would like to confirm whether there is any risk that variables such as  **Sd_SrvrEntryTable_ast** and  **Sd_CnseEveGrAdminTable_ast** could be modified unexpectedly when there is no critical section protection.
2. Regarding the issue of an abnormal number of  **OfferService entries**, the customer would like to know whether there are any other possible analysis directions.

Best regards,

 

  **Dong LIU** 

 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China (ETAS-ECM/XSF-CN)

 Bosch (China) Investment Ltd. | 333 Fuquan (N.) Road | Shanghai 200335 |  P.R. CHINA 

 [Dong.LIU5@etas.com!mail_small.gif!](mailto:Dong.LIU5@etas.com)

## 关联

- mentions: [[RH-16791 SoAd ifTransmissionOnGoing_b guard in SoAd_IfTransmit entry check]]

## 评论

> [!note]+ 2026-09-04 10:38 · [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]]
> Hello, [[Rajendran_Jothivel|Rajendran Jothivel]] 
>
> Did you have chance to look into the project I shared?
>
> Do we have any plan for this improvement?

-------

> [!note]+ 2026-08-31 09:48 · [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]]
> Hello, [[Rajendran_Jothivel|Rajendran Jothivel]] [[Nandita_Prasad_(MSEMS-ETAS)|Prasad Nandita]] 
>
> Please refer to customer demo project configuration in link below: [Cariad_Issue](https://bosch-my.sharepoint.com/:f:/p/aiu2sgh/IgBC3Z_HHOe1QKgPklef1T07AYtTJ_MWzQKsPyNC_s1-yvc?e=OMp8b6)

-------

> [!note]+ 2026-08-27 13:49 · [[Rajendran_Jothivel|Rajendran Jothivel]]
> Hello Dong,
>
> Please see my feedback below,
>  # Yes, you are correct. If different TxPduIds are mapped to the different Socket Connections, then there won't be any issue.
>  # Unfotunately, both TcpIp_UdpTransmit and TcpIp_TcpTransmit APIs are not supported for re-entrant use cases completely. 

-------

> [!note]+ 2026-08-27 13:04 · [[LIU_Dong_(ETAS-ECMXSF-CN)|Dong LIU]]
> hi [[Phan_Huynh_Dang_Khoa_(MSETA-Hub-CN)|Khoa Phan Huynh Dang]] [[Rajendran_Jothivel|Rajendran Jothivel]] 
>
> The customer’s current calls to `SoAd_IfTransmit()` are shown in the figure below. The customer will add other call paths in the future.
>
> ![[RH-16841-image-2026-08-27-19-00-00-375.png]]

-------

> [!note]+ 2026-08-27 04:30 · [[LIU_Dong_(ETAS-ECMXSF-CN)|Dong LIU]]
> Hello, [[Rajendran_Jothivel|Rajendran Jothivel]] [[Phan_Huynh_Dang_Khoa_(MSETA-Hub-CN)|Khoa Phan Huynh Dang]] 
>
> the customer has two more questions:
>
> 1. Different TxPduIds may be mapped to the same Socket Connection or to different Socket Connections. If they are mapped to different Socket Connections, is preemption still not allowed? My understanding is that if they use different Socket Connections, we should not need to worry about data conflicts in SoAd_DyncSocConfig_ast, right?
> 2. The customer is also using DDS. DDS does not call SoAd_IfTransmit; instead, it directly calls TcpIp_UdpTransmit or TcpIp_TcpTransmit. Do these two interfaces support preemption? And can these two interfaces and TcpIp_MainFunction preempt each other?
>
> thank you!

-------

> [!note]+ 2026-08-25 09:29 · [[Rajendran_Jothivel|Rajendran Jothivel]]
> Hello Dong LIU,
>
> Please see my feedback below,
>  * If SoAd_IfTransmit API is invoked second time before completing the execution for the first SoAd_IfTransmit API with the {+}same Tx PDU{+}, then second request will be rejected by returning E_NOT_OK. It clearly indicates that SoAd_IfTransmit API is not reentrant for the same Tx PDU which is also in-line with AUTOSAR specification.
>  * If SoAd_IfTransmit API is invoked second time before completing the execution for the first SoAd_IfTransmit API with the {+}different Tx PDU{+}, then there are some variables which needs to be handled yet in the software. For example: ifTransmissionOnGoing_b won't be sufficient to handle the reentrant use case, instead counter should be implemented to make sure that SoAd_IfTransmit API supports the reentrant feature.
>
> Typically, all members of SoAd_DyncSocConfig_ast should be protected against corruption due to reentrant access. This requirement has already been identified as part of the multicore support improvements.
>
> Likewise, appropriate protection should be added for SoAd_DyncSocConfig_ast when SoAd_MainFunction() and SoAd_IfTransmit() can preempt each other, to avoid data corruption caused by concurrent access.
>
> As already mentioned, the interface APIs were designed to be non-reentrant to improve performance. However, there are plans to enhance this capability in upcoming releases.
> Please feel free to reach out to me if you need any further clarification. Thanks!

-------

> [!note]+ 2026-08-25 05:25 · [[LIU_Dong_(ETAS-ECMXSF-CN)|Dong LIU]]
> [[Rajendran_Jothivel|Rajendran Jothivel]] hello,could you please help take a look at this question?

-------

> [!note]+ 2026-08-20 12:42 · [[Phan_Huynh_Dang_Khoa_(MSETA-Hub-CN)|Khoa Phan Huynh Dang]]
> Hello [[LIU_Dong_(ETAS-ECMXSF-CN)|Dong LIU]] ,
>  * {color:#FF0000}The customer may call `SoAd_IfTransmit()` or `SoAd_TpTransmit()` from different upper-layer applications. If one upper-layer application is calling `SoAd_IfTransmit()` and another higher-priority upper-layer application preempts it and also calls {{{}SoAd_IfTransmit(){}}}, could this cause any issues?{color}
>
> I found some requirement in AUTOSAR, and **our tool limitation** related to concerns of customer as below:
>
> ![[RH-16841-image-2026-08-20-14-17-29-161.png]]
>
> ![[RH-16841-image-2026-08-20-14-20-04-115.png]]
>
> Regarding this question, two different upper-layer applications invoke {{{}SoAd_IfTransmit(){}}}, and the second call preempts the first one. This may cause the counter to be overwritten, resulting in a race condition. Consequently, the counter value may become incorrect, {*}affecting TxConfirmation processing{*}. Hello [[Rajendran_Jothivel|Rajendran Jothivel]] , 
> I believe this limitation could be extended to support this use case. Could you please review it and provide your feedback?
> Additionally, if your 2 SoAd_IfTransmit() are invoked during one socket, it also causes a lost data.  As the requirement [{*}SWS_SoAd_00653{*}], SoAd will reject request and return E_NOT_OK
>  * {color:#FF0000}If the protocol stack is currently executing {{{}SoAd_MainFunction(){}}}, and an upper-layer application calls `SoAd_IfTransmit()` and preempts {{{}SoAd_MainFunction(){}}}, could this cause any issues?{color}
>
> Currently, I found a ticket related to a potential TX data corruption issue (reported in RH-16791). [[Rajendran_Jothivel|Rajendran Jothivel]] , do you have any info about this question?

-------

> [!note]+ 2026-08-19 03:54 · [[LIU_Dong_(ETAS-ECMXSF-CN)|Dong LIU]]
> hello, [[Phan_Huynh_Dang_Khoa_(MSETA-Hub-CN)|Khoa Phan Huynh Dang]] [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Phuong Nguyen Le]] [[Rajendran_Jothivel|Rajendran Jothivel]] 
>
> The customer has two additional questions:
>  # The customer may call `SoAd_IfTransmit()` or `SoAd_TpTransmit()` from different upper-layer applications. If one upper-layer application is calling `SoAd_IfTransmit()` and another higher-priority upper-layer application preempts it and also calls {{{}SoAd_IfTransmit(){}}}, could this cause any issues?
>  # If the protocol stack is currently executing {{{}SoAd_MainFunction(){}}}, and an upper-layer application calls `SoAd_IfTransmit()` and preempts {{{}SoAd_MainFunction(){}}}, could this cause any issues?

-------

> [!note]+ 2026-08-17 06:38 · [[Shweta_Ganesh_Dixit|Shweta Ganesh Dixit]]
> ETAS recommendation: A deterministic polling mechanism can provide sufficient responsiveness while keeping CPU utilization and execution behavior predictable.
>
> A meeting explaining the rationale for desiging RTA-ETH in polling & also the anlaysis of the configuration of Cariad was explained in the meeting to [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Sathish Kumar Madanmohan]] , [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]] , [[LIU_Dong_(ETAS-ECMXSF-CN)|Dong LIU]] . 
>
> Next action: ETAS CN hub would discuss with cariad and then get back if any technical meeting is required with the customer
>
>
> [^RE_ VCTC escalation - Alignment and sync-1.msg]

-------

> [!note]+ 2026-08-11 11:55 · [[LIU_Dong_(ETAS-ECMXSF-CN)|Dong LIU]]
> [[Phan_Huynh_Dang_Khoa_(MSETA-Hub-CN)|Khoa Phan Huynh Dang]] [[Phan_Huynh_Dang_Khoa_(MSETA-Hub-CN)|Khoa Phan Huynh Dang]] 工程放在附件中了
> [^Eth_Interrupt.zip]

-------

> [!note]+ 2026-08-11 08:22 · [[Phan_Huynh_Dang_Khoa_(MSETA-Hub-CN)|Khoa Phan Huynh Dang]]
> Hi [[LIU_Dong_(ETAS-ECMXSF-CN)|Dong LIU]] ,
> Additionally, could you please re-share the project used for your testing? At the moment, I cannot see the BSW source files in the project you shared with us.

-------

> [!note]+ 2026-08-11 04:18 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Phuong Nguyen Le]]
> [[Rajendran_Jothivel|Rajendran Jothivel]] : as ETH RX interrupt isn't supported without XCoreCDD, can we add some check in code generation to report error in this case then User will aware and update this configuration.
>
>
>
> [[LIU_Dong_(ETAS-ECMXSF-CN)|Dong LIU]] :
>
> 1, 2) As [[Rajendran_Jothivel|Rajendran Jothivel]] mentions, the ETH RX interrupt is supported with condition is XCoreCDD is configured
>
> 3) Doip: [[Rajendran_Jothivel|Rajendran Jothivel]] : About DoIP issue, Is this issue same as SD and need XCoreCDD for ETH ISR too?

-------

> [!note]+ 2026-08-07 08:52 · [[LIU_Dong_(ETAS-ECMXSF-CN)|Dong LIU]]
> Hi, [[Rajendran_Jothivel|Rajendran Jothivel]]
>
> **I have two questions.** 
>
> 1. Ethernet receive interrupt mode is a commonly used feature. The customer would like to understand why our product does not support this functionality and what the original design rationale was.
>
> 2. According to this statement in the document, TCP/IP does not support interrupt mode. In this case, how is TCP/IP expected to work with XCoreCDD?
>
> ![[RH-16841-image-2026-08-05-14-44-52-206.png]]
>
> During our actual stress testing, we also observed that DoIP was reset through different paths. These paths are all unexpected, as shown in the figure below:
>
> ![[RH-16841-image-2026-08-07-14-51-20-642.png]]
>
> ![[RH-16841-image-2026-08-07-14-51-53-342.png]]

-------

> [!note]+ 2026-08-07 06:43 · [[Rajendran_Jothivel|Rajendran Jothivel]]
> Hello [[LIU_Dong_(ETAS-ECMXSF-CN)|Dong LIU]],
>
> As I mentioned previously, Ethernet Rx Interrupt is supported only when the XCoreCDD module is enabled. It is not supported without enabling this module.
>
> Since Sd_RxIndication is not reentrant, the XCoreCDD module was introduced to ensure that the received packets are stored in a pipe and processed synchronously. This prevents concurrent execution of Sd_RxIndication and avoids data corruption.
>
> Regarding the TcpIp issue, I would appreciate it if you could provide more details. Specifically:
>  * Is the issue observed in the Rx path or the Tx path?
>  * Under what scenario or conditions do you observe the unexpected behavior?
>
> This information will help us analyze the issue more effectively.

-------

> [!note]+ 2026-08-07 05:36 · [[LIU_Dong_(ETAS-ECMXSF-CN)|Dong LIU]]
> [[Phan_Huynh_Dang_Khoa_(MSETA-Hub-CN)|Khoa Phan Huynh Dang]] [[Rajendran_Jothivel|Rajendran Jothivel]] During stress testing, the current TCP/IP stack has also occasionally exhibited some unexpected behavior. The customer suspects that these issues may also be related to the Ethernet receive interrupt mechanism.

-------

> [!note]+ 2026-08-07 05:29 · [[LIU_Dong_(ETAS-ECMXSF-CN)|Dong LIU]]
> [[Phan_Huynh_Dang_Khoa_(MSETA-Hub-CN)|Khoa Phan Huynh Dang]] [[Rajendran_Jothivel|Rajendran Jothivel]]  In addition, the TCP/IP stack also does not support Ethernet receive interrupts. In that case, how does the TCP/IP stack work with XCoreCDD?

-------

> [!note]+ 2026-08-07 04:34 · [[LIU_Dong_(ETAS-ECMXSF-CN)|Dong LIU]]
> [[Phan_Huynh_Dang_Khoa_(MSETA-Hub-CN)|Khoa Phan Huynh Dang]] [[Rajendran_Jothivel|Rajendran Jothivel]]  Ethernet receive interrupts are generally considered a commonly used feature. Why doesn't our product support this functionality? What were the design considerations behind this decision?

-------

> [!note]+ 2026-08-06 15:15 · [[Rajendran_Jothivel|Rajendran Jothivel]]
> Hello [[Phan_Huynh_Dang_Khoa_(MSETA-Hub-CN)|Khoa Phan Huynh Dang]],
>
> Thank you for sharing your analysis results.
>
> Yes, your understanding is correct. Data corruption can occur in both **Sd_SrvrEntryTable_ast** and **Sd_CnseEveGrAdminTable_ast** if Sd_RxIndication preempts Sd_MainFunction while it is being executed.
>
> Additionally, I would like to point out that Sd_RxIndication from the Eth Rx Interrupt context is not supported. If the project intends to use the Eth Rx Interrupt, the rba_XcoreCdd module should be enabled between the SD and SoAd modules through PduR.
>
> If my understanding is correct, rba_XcoreCdd is not enabled in the project, which is why this data corruption has been observed by the customer.
>
> As a workaround for this issue, the project can either:
>  * Disable the Eth Rx Interrupt, or
>  * Enable the rba_XcoreCdd module in the project.
>
> Kindly let me know if any additional clarification is required. Thanks!

-------

> [!note]+ 2026-08-06 12:37 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi [[Shweta_Ganesh_Dixit|Shweta Ganesh Dixit]], this Communication-Eth ticket requires an assignee. As the component lead for Communication-Eth, please ensure that the 'Level 3 Assignee' field is set to the appropriate person that can handle this issue.

-------

> [!note]+ 2026-08-06 12:37 · [[Phan_Huynh_Dang_Khoa_(MSETA-Hub-CN)|Khoa Phan Huynh Dang]]
> Hello [[Rajendran_Jothivel|Rajendran Jothivel]] ,
>
> Regarding the issue of customer, I think it come from their project is using TCPIP as the upper layer + EthStack is using interrupt mode.
>
> As i understand, **Sd_RxIndication()** is invoked from the ISR, whereas **Sd_MainFunction()** executes in the task cyclic, and they also access to same input such as **Sd_SrvrEntryTable_ast** and {*}Sd_CnseEveGrAdminTable_ast{*}.
>
> Additionally, TcpIp/SoAd/SD are not reentrant,
>
> ![[RH-16841-image-2026-08-06-17-29-30-224.png]]
>
> and SD does not implement any Exclusive Area to protect its internal data structures
>
> ![[RH-16841-image-2026-08-06-17-32-12-228.png]]
>
> --> It will inevitably lead to potential data corruption in SD module structures
>
> ==> Then, I request them to change **CtrlEnableRxInterrupt** to **FALSE** and some related configurations of it to disable interrupt mode.
>
> Could you help me confirm:
>  # Is my understanding correct?
>  # Could you explain the root cause and the underlying design considerations in more detail?
>  # 
> Do we have any workaround for this limitation? If not, could we consider a design enhancement or bug-fix plan to support this use case in future releases?
>
> cc: [[Shweta_Ganesh_Dixit|Shweta Ganesh Dixit]] 
>
> ===================
>
> [[LIU_Dong_(ETAS-ECMXSF-CN)|Dong LIU]] , **EthifEnableRxInterruptis** has been replaced by **EthEnableRxInterrupt** as mentioned in [https://rtahotline.etas.com/jira/browse/RH-16841?focusedCommentId=713542&page=com.atlassian.jira.plugin.system.issuetabpanels:comment-tabpanel#comment-713542]

-------

> [!note]+ 2026-08-06 09:22 · [[LIU_Dong_(ETAS-ECMXSF-CN)|Dong LIU]]
> [[Phan_Huynh_Dang_Khoa_(MSETA-Hub-CN)|Khoa Phan Huynh Dang]] I found the `EthEnableRxInterrupt` configuration option in the Eth module, but I couldn't find the `EthIfEnableRxInterrupt` configuration option in the EthIf module.

-------

> [!note]+ 2026-08-06 09:02 · [[LIU_Dong_(ETAS-ECMXSF-CN)|Dong LIU]]
> [[Phan_Huynh_Dang_Khoa_(MSETA-Hub-CN)|Khoa Phan Huynh Dang]] The customer has been using the interrupt-based reception mechanism throughout the project. Since the project is now approaching mass production, making such a change at this stage would have a significant impact on the project. The customer would like to understand why interrupt mode cannot be used.

-------

> [!note]+ 2026-08-05 10:56 · [[Phan_Huynh_Dang_Khoa_(MSETA-Hub-CN)|Khoa Phan Huynh Dang]]
> Hi [[LIU_Dong_(ETAS-ECMXSF-CN)|Dong LIU]] ,
>
> With your confirmation, **interrupt mode** is found to be the reason for similar concurrency issues in the SD module as I mentioned in [https://rtahotline.etas.com/jira/browse/RH-16841?focusedCommentId=713542&page=com.atlassian.jira.plugin.system.issuetabpanels:comment-tabpanel#comment-713542] , and transitioning to **polling mode** helped solve it.
>
> ![[RH-16841-image-2026-08-05-15-54-25-360.png]]
>
> If your project still encounters this issue, please re-open this ticket. Thank you!

-------

> [!note]+ 2026-08-05 10:17 · [[JSM_Service_Bot|JSM Service Bot]]
> Note: Khoa Phan Huynh Dang added as watcher to the issue. Internal support agents cannot be added as Request Participants, so they have been automatically joined as Watchers instead.

-------

> [!note]+ 2026-08-05 10:16 · [[LIU_Dong_(ETAS-ECMXSF-CN)|Dong LIU]]
> [[Phan_Huynh_Dang_Khoa_(MSETA-Hub-CN)|Khoa Phan Huynh Dang]] The project is configured with the TcpIp feature, and the project link is attached.
> [^Isolar.zip]

-------

> [!note]+ 2026-08-05 09:57 · [[JSM_Service_Bot|JSM Service Bot]]
> Note: Jiaqi JI added as watcher to the issue. Internal support agents cannot be added as Request Participants, so they have been automatically joined as Watchers instead.

-------

> [!note]+ 2026-08-05 09:57 · [[Phan_Huynh_Dang_Khoa_(MSETA-Hub-CN)|Khoa Phan Huynh Dang]]
> Hi [[LIU_Dong_(ETAS-ECMXSF-CN)|Dong LIU]] , [[JI_Jiaqi_(ETAS-ECMXSF-CN)|Jiaqi JI]] ,
>
> Firstly, can you let us know your project have TCP/IP feature? If yes, this issue can come from the limitation of **EthIf** design as below in **Section 2.4.1** of the {*}RTA-Eth Stack Reference Guide{*}:
>
> ![[RH-16841-image-2026-08-05-14-44-52-206.png]]  
>
> If your Ethernet stack is configured to use {*}interrupt mode{*}, there is a risk of system instability under high-bandwidth operation. This could lead to race conditions or data corruption in **SD module** structures
>
> ![[RH-16841-image-2026-08-05-14-53-44-408.png]]
>
> You can try to change this **EthCtrlEnableRxInterrupt** to FALSE and some related configurations of it to disable interrupt mode.
>
> --------------
>
> If not, could you send us your project for analysis? 

-------

> [!note]+ 2026-08-05 04:23 · [[JSM_Service_Bot|JSM Service Bot]]
> Note: JSM Service Bot added as watcher to the issue. Internal support agents cannot be added as Request Participants, so they have been automatically joined as Watchers instead.

-------

> [!note]+ 2026-08-05 04:23 · [[LIU_Dong_(ETAS-ECMXSF-CN)|Dong LIU]]
> [[JSM_Service_Bot|JSM Service Bot]] This issue is very urgent for the customer, so please keep its priority as Critical.

-------

> [!note]+ 2026-08-05 04:13 · [[JI_Jiaqi_(ETAS-ECMXSF-CN)|Jiaqi JI]]
> Hi [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Phuong Nguyen Le]] ,
>
> We raised one new critical issue, could you assign one colleague to help us investigate?
>
> Big thanks!!!

-------

> [!note]+ 2026-08-05 04:12 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Dong LIU, please note that this issue was made with VNCNMS in the summary and has been sent to the relevant queue by adding the VNCNMS label.

-------

> [!note]+ 2026-08-04 20:10 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Dong LIU. Your issue is set to "Critical" priority.
> Please ensure that there is a reasonable justification for this listed in the issue description, otherwise the priority may be reviewed and adjusted during triage.
> Kind regards

-------

> [!note]+ 2026-08-04 20:07 · [[JSM_Service_Bot|JSM Service Bot]]
> Note: Jiaqi JI, JSM Service Bot, Zhou ZHOU, Jie LIU added as watcher to the issue. Internal support agents cannot be added as Request Participants, so they have been automatically joined as Watchers instead.

-------

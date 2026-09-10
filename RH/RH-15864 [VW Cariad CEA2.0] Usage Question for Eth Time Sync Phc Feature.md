---
jira_key: RH-15864
jira_url: "https://rtahotline.etas.com/jira/browse/RH-15864"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Critical
project: RH
assignee: Jie LIU
reporter: Jie LIU
tags: [jira/comp/communication-timeservices, jira/label/vncnms]
fix-versions: []
epic: null
parent: null
created: "2026-04-24T05:45:57.000+0200"
updated: "2026-08-28T14:28:06.000+0200"
synced-at: "2026-09-10T08:07:25.599Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Hello, Hotline 

Here is the question about Phc usage for Eth Time Sync on Running Project VW Cariad CEA2.0: 

When customer enables hardware clock in EthIf, the following API are generated: 

![[RH-15864-image002.png]] 

However, these interfaces have no user in upper level. 

 **Question1: How to enable this feature from BSW stack point of view?** 

Customer found some related configuration in AUTOSAR specification but seems not supported by our tool. 

![[RH-15864-image003.png]]![[RH-15864-image001.png]] 

 **Question 2: When configuring StbMIsSystemWideGlobalTimeMaster as false, if StbMTimeCorrection container is added, RTA-CAR BswGen will report error, what’s the reason?** 

![[RH-15864-image004.png]] 

 **Question 3: Can ETAS provide some demo configuration when enabling Phc feature?** 

 ** Jie LIU** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 M +86 138 16227585 

 [Jie.LIU8@etas.com!mail_small.gif!](mailto:Jie.LIU8@etas.com) 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

 [www.etas.cn](https://www.etas.cn)  

  ** ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2026-08-28 14:28 · JSM Service Bot
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2026-07-28 13:20 · Joao Pereira
> Hi Jie LIU .
> Since both time domains are available in the ECU now you can just compare the current time between both. Of course this consideres the complete round trip delay.

-------

> [!note]+ 2026-07-07 08:28 · Dang Ho Anh
> Hi a.Su Nguyen Quoc ,
>
> The Time Base cloning feature is a proposed method to cover the requirement "measure the diff between calculated global time in slave node and the real global time in master, to get precision of time sync".
>
> Hi Joao Pereira,
> As I understand your point, you are referring to the “Time Gateway” use case of StbM.
> ![[RH-15864-image-2026-07-07-12-43-16-099.png]]
>
> I have performed testing for this case using the setup below:
> ![[RH-15864-image-2026-07-07-12-46-33-929.png]]
>
> The Time Gateway is configured in the slave ECU: both the EthTSynSynchronizedTimeBaseRef of the time master port and the time slave port refer to the same StbMSynchronizedTimeBase.
>
> The video on testing: the left side shows the T32 window from the Master ECU, where the timestamps of the master and time slave are obtained via StbM_GetCurrentTime(). The right side shows the T32 window from the Slave ECU, where its timestamp is obtained via StbM_GetCurrentTime().
> [^StbM_TimeGateway_Test.mp4]
>
> From my testing, I can see that the feature works, and the master can receive the time sent by the slave node. I have not investigated deeply enough to check how precise the time is.
>
> Does what I described match your intent?
> Regarding the precision of the timestamp that the master receives from the slave based on this feature, do you have any idea how to check it?
>
> Hi Jie LIU ,
> Please add your comments.

-------

> [!note]+ 2026-07-03 14:24 · Su Nguyen Quoc
> Hi Jie LIU and Dang Ho Anh,
>  * Is Time Base Cloning {*}a hard customer requirement{*}, or only one proposed method to measure time deviation?
>  * **Can the customer accept L3’s proposed approach** of linking `MasterDomain` and `SlaveDomain` to the same StbM timebase instead of using cloning?
>
>
> **Status:** Yellow - technical direction proposed, validation pending.
> **Main risk:** unclear product expectation and ambiguous use case definition.
> **COEM L2/** ETA Hub{*}:{*} reproduced and deep-dived the issue at configuration/code level; identified the failing timing condition; aligned with L3 for an alternative architecture direction.
> **Support needed** from CN Hub{*}:{*} clarify the expected product behavior and acceptance criteria with customer before asking ETA Hub/L3 to continue deeper testing.

-------

> [!note]+ 2026-07-03 11:57 · Dang Ho Anh
> Joao Pereira , Let me retest the case today.

-------

> [!note]+ 2026-06-26 13:23 · Joao Pereira
> Hello Dang Ho Anh.
>
> I don't think clone is required. You can just link the 2 Tsyn timedomains to the same Stbm timebase 
> MasterDomain and SlaveDomain -> Same StbmTimebase.
>
> Adding clone should not be required.

-------

> [!note]+ 2026-06-19 18:50 · JSM Service Bot
> This issue has not received any response for 2 weeks and will now be automatically moved to Solution Proposed.

-------

> [!note]+ 2026-06-05 07:48 · Dang Ho Anh
> Hi Joao Pereira ,
>
> As I have discussed with Jie LIU , the purpose of using time base cloning is to "{*}measure{*} {*}the diff between calculated global time in slave node and the real global time in master, to get precision of time sync{*}".
>
> The time base cloning feature will be configured in the slave node. This node will clone the time it receives from the master node and send it back. The master node will then receive it and compare the value with its global time.
>
> I have tried to configure it and tested it with the below setup:
>
> ![[RH-15864-image-2026-06-05-12-44-55-053.png]]
>
> But an error occurs after cloning in slave node. The error happens in the function {{{}EthTSyn_GetHwTime(){}}}, which is called by `EthTSyn_TxConfirmation()` for the SYN message sent by the master port.
>
> ![[RH-15864-image-2026-06-05-12-45-18-362.png]]
>
> The if condition and while (1) loop are my test code.
>
> As you can see, the failure occurs because `lVirtualLocalTime_u64` (T2vlt) is smaller than `lSyncVirtualLocalTime_u64` (T0vlt), which results in the upcoming calculation being invalid:
>
> lCurrentTimeStamp_u64 = lVirtualLocalTime_u64 - lSyncVirtualLocalTime_u64;
>
> As I debugged the issue, the problem could come from the wrong calculation of lSyncVirtualLocalTime_u64. This variable is calculated as: 
> _lSyncVirtualLocalTime_u64 = EthTSyn_Master_ast[0].SyncVirtualLocalTime_u64 = StbM_VirtualLocalTimeTupleArray_ast[1] + (Eth_17_GEthMacV2_GetCurrentTime() - StbM_Eth_VirtualLocalTimeArray_ast[1])_
>
> in EthTSyn_Transmit() of SYN message. 
>
> StbM_VirtualLocalTimeTupleArray_ast[1] is updated when clone api is called.
>
> StbM_Eth_VirtualLocalTimeArray_ast[1] is updated every 3 seconds by StbM_MainFunction(), rather than during global time synchronization.
>
> Could you help to check if the use case is feasible?
>
> Thank you.

-------

> [!note]+ 2026-06-03 11:32 · Joao Pereira
> Hello Liu.
> Yes it looks fine. The only thing I don't fully understand is the Time Base Cloning. 
> Are you intending to use time cloning configuration or is it just a reference to the slave timebase that shall have the same time has Master?
>
> Regarding RTE. You probably need to complete the StbM rte configuration

-------

> [!note]+ 2026-05-29 10:00 · Jie LIU
> Hi, Joao Pereira 
>
> Could you have to check the following method is the way of "Reverse Sync" which can be achieved by StbM both in master node and slave node:
>
> Here is the sequence diagram with an English explanation, focusing on how the Master node calculates the Slave’s time deviation during Reverse Sync.
>
> ![[RH-15864-image-2026-05-29-16-04-13-096.png]]
>
> Step-by-step explanation
>
> 1. {*}`*`Role reversal`*`{*}  
>    In the dedicated gPTP domain used for Reverse Sync, the regular Slave node is configured as the {*}`*`Grandmaster`*`{*} and actively sends synchronization messages. The Master node assumes the {*}`*`Slave`*`{*} role in this domain.
>
> 2. {*}`*`Message exchange`*`{*}  
>    - The Slave sends a `Sync` message. The Master’s hardware captures the exact arrival time {*}`*`t2`*`{*}.  
>    - A subsequent `Follow_Up` message carries the precise origin timestamp {*}`*`t1`*`{*} of that `Sync` message.
>
> 3. {*}`*`Offset computation`*`{*}  
>    Inside the Master, the StbM applies the same formula as in standard forward synchronization to calculate the clock offset in this reverse domain:  
>    `Offset_reverse = (t1 + link_delay) - t2`  
>    This offset directly reveals how far the Slave’s synchronized global time deviates from the Master’s true global time.
>
> 4. {*}`*`Filtering and cloning`*`{*}  
>    After filtering (e.g., Kalman or linear regression), the Master obtains a stable Reverse Global Time. This value is then copied into a dedicated monitoring time base using {*}`*`Time Base Cloning`*`{*}.
>
> 5. {*}`*`Observation`*`{*}  
>    The Master’s application layer can now simply compare the primary Master Time Base with the cloned time base to read the Slave’s real-time synchronization accuracy, without dealing with low-level protocol details.

-------

> [!note]+ 2026-05-28 04:04 · Dang Ho Anh
> Joao Pereira , yes I'm using this project [^BasicSoftware_ReverseSync_1290.zip]

-------

> [!note]+ 2026-05-27 17:25 · Joao Pereira
> Hi Dang Ho Anh ,
>
> I if your using RTE your right not to configure STBM_ECUC_RB_RTE_IN_USE -> STD_OFF.
> The 2 variables should be generate in RTE Rte_StbM_Type.h. 
> Is the project the one attached to the ticket?

-------

> [!note]+ 2026-05-27 13:22 · Dang Ho Anh
>  Hi Jie LIU ,
>
> Please check the example configuration for Reverve Sync feature in this attachment [^BasicSoftware_ReverseSync_1290.zip], this configuration is based on BIP RTA-CAR 12.9.0.
>
> Hi Joao Pereira , I encountered an issue while configuring the project. The definitions for _STBM_SYSTEM_WIDE_MASTER_DISABLED_ and _STBM_SYSTEM_WIDE_MASTER_ENABLED_ cannot be found, as shown in the image below:
>
> ![[RH-15864-image-2026-05-27-18-09-53-312.png]]
>
> I worked around the issue by defining those in Rte_UserCfg.h
>
> I do not want to change STBM_ECUC_RB_RTE_IN_USE to STD_OFF by modifying EcuCRbRteInUse from true to false, as it will result in significant changes.
>
> Is there any way to make this work without altering EcuCRbRteInUse?

-------

> [!note]+ 2026-05-27 13:02 · Dang Ho Anh
> [^BasicSoftware_ReverseSync_1290.zip]

-------

> [!note]+ 2026-05-21 11:04 · Phuong Nguyen Le
> Dang Ho Anh : Please check this issue! 

-------

> [!note]+ 2026-05-21 10:55 · Joao Pereira
> Hello Phuong Nguyen Le.
> Is L3 support still needed for this topic?

-------

> [!note]+ 2026-05-20 02:52 · Jie LIU
> Phuong Nguyen Le  Could you help to check the extension of configuration for Reverse Sync?

-------

> [!note]+ 2026-05-19 10:20 · Joao Pereira
> This can be achieved with some extension of the configuration. No we don't have any demo configuration.

-------

> [!note]+ 2026-05-19 10:12 · Jie LIU
> Joao Pereira Thanks for the feedback. Is Reverse Sync supported by our RTA-CAR? Do we have the demo configuration for it?

-------

> [!note]+ 2026-05-18 10:30 · Joao Pereira
> Regarding precision testing this is usually done in the product itself since it depends on the hardware used and configuration of the project. Currently we do not have any test environment which calculate precision. I observed the usage of reverse Sync in projects (Both ends send sync to the bus and time difference between them is measured). But like I said this is tipically performed at project lvl. 

-------

> [!note]+ 2026-05-15 10:16 · Jie LIU
> Dear expert, 
>
> Could you please give some suggestion on below qeustion?
>  - Customer still wants to know with Software Clock, are we able to test time sync accuracy? They mentioned normally PPS out is used to test it.

-------

> [!note]+ 2026-05-14 18:35 · Joao Pereira
> No... The implementation of DisciplinedHWClock is done on top of TimeTuple update which is not present in that specific version. The TimeTuple change impacts other components therefore there is no simple porting of the feature to 12.9.0. 

-------

> [!note]+ 2026-05-14 18:27 · Phong Tang Dieu
> Hi Joao Pereira
> They are using **RTA-CAR_12.11.0VCTCESR1pr1** which is a specific version based on RTA-CAR 12.9.0 for fixing some issues of Sec stack. It's not related to the main branch of RTA-CAR 12.11.0. 
> Anyway, the official RTA-CAR 12.11.0 has not been released yet. (will take some months)
> Therefore, do you think that we can have any workaround solution for this feature first based on RTA-CAR 12.9.0?
>
> Thanks,

-------

> [!note]+ 2026-05-14 17:56 · Joao Pereira
> Hello Phong Tang Dieu can you confirm which version are they using?
> We have DisciplinedHWClock implemented has prototype in RTA-CAR 12.11.

-------

> [!note]+ 2026-05-13 11:08 · Phong Tang Dieu
> Hi Fadia Nefati
> Could you please support to answer customer question?
> - Our EthIf is already supporting hardware clock interface, is there any workaround for current RTA-CAR to support HW clock with the feature lack of StbM?
> - Customer still wants to know with Software Clock, are we able to test time sync accuracy? They mentioned normally PPS out is used to test it.
>
> Thanks

-------

> [!note]+ 2026-05-13 11:05 · JSM Service Bot
> Hi Fadia Nefati, this Communication-TimeServices ticket requires an assignee. As the component lead for Communication-TimeServices, please ensure the 'Level 3 Assignee' field is set the appropriate person that an handle this issue.

-------

> [!note]+ 2026-05-13 11:04 · Phong Tang Dieu
> Hi Jie LIU
> I will involve an TSync expert then. 

-------

> [!note]+ 2026-05-13 11:00 · Jie LIU
> Phong Tang Dieu  About question 1, customer still wants to know with Software Clock, are we able to test time sync accuracy? They mentioned normally PPS out is used to test it. Due to the urgent timeline from customer side, could you please quickly give response or upgrade the level of this issue?

-------

> [!note]+ 2026-05-06 14:46 · Phong Tang Dieu
> Hi Jie LIU
> As our alignment from chat, customer could resolve the problem of question 2 by themselves. So that, please find answers for remaining questions as below
> - For question 1: the feature needs an implementation in StbM module which includes changes in codegen/configuration and c/h source code, therefore, from my point of view, there is no workaround solution for now. 
> - For question 3:  [^Test_EthTSynMaster.zip]   [^Test_EthTSynSlave.zip] , here are 2 test projects for master and slave cases using software clock that I got from RTA-CAR testing team. essentially the configuration as below:
> -- StbMSynchronizedTimeBase/StbMIsSystemWideGlobalTimeMaster: set to true for Master, false for Slave.
> -- StbMSynchronizedTimeBase/StbMLocalTimeClock/StbMLocalTimeHardware references to an RTE software counter
> -- EthTSynGlobalTimeDomain/EthTSynPortRole: configure EthTSynGlobalTimeMaster for Master, EthTSynGlobalTimeSlave for Slave.
>
> Cheers,

-------

> [!note]+ 2026-05-06 14:21 · Phong Tang Dieu
> [^Test_EthTSynMaster.zip] [^Test_EthTSynSlave.zip]

-------

> [!note]+ 2026-05-06 10:23 · Jie LIU
> For question 1: our EthIf is already supporting hardware clock interface, is there any workaround for current RTA-CAR to support HW clock with the feature lack of StbM

-------

> [!note]+ 2026-05-06 10:19 · Jie LIU
> For question 3: could you please provide the demo configuration for time master and slave using software clock ?

-------

> [!note]+ 2026-05-06 07:35 · Jie LIU
> For question 2: the error log is as below:
>
> ![[RH-15864-image-2026-05-06-13-35-11-173.png]]

-------

> [!note]+ 2026-04-27 12:33 · Phong Tang Dieu
> Jie LIU That is just a note of how the PHC feature will be implemented. The pulse per second itself is not a feature of StbM, at least I couldn't find any relevant information from StbM spec. 

-------

> [!note]+ 2026-04-27 12:10 · Jie LIU
> ![[RH-15864-image-2026-04-27-18-10-12-751.png]]

-------

> [!note]+ 2026-04-27 11:53 · Phong Tang Dieu
> Jie LIU  Could you please tell me what does PPS feature mean? 
>
> According to your shared screenshot about StbMDisciplinedClock, I could only say Hardware clock adjustment (PHC) is not supported. And StbMDisciplinedClock is not supported as well. 
>
> Thanks,

-------

> [!note]+ 2026-04-27 11:37 · Jie LIU
> Phong Tang Dieu for question one, do you mean PPS feature is not possible without support of Phc?

-------

> [!note]+ 2026-04-27 11:23 · Phong Tang Dieu
> Hi Jie LIU
>
> Please find my answers as below:
> **For question 1:** This feature hasn't been supported yet. It is planned for RTA-CAR 12.13.0. Relevant ticket: [ARC-14273](https://jira.etas-dev.com/browse/ARC-14273)
>
> **For question 2:** could you please share more details of the error and the configuration? Because there are a lot of validation check related to stbMIsSystemWideGlobalTimeMaster in the StbM source code.
>
> **For question 3:** because the feature is not supported, we don't have a demo configuration for it.
>
> BRs,

-------

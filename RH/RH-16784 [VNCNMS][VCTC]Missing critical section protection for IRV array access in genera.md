---
jira_key: RH-16784
jira_url: "https://rtahotline.etas.com/jira/browse/RH-16784"
server: rtahotline
kind: hotline
type: Support
status: Solution Proposed
priority: Critical
project: RH
assignee: sisi.tao@bosch.com
reporter: sisi.tao@bosch.com
tags: [VNCNMS]
components: [RTA-RTE]
fix-versions: []
epic: null
parent: null
created: "2026-07-28T12:13:13.000+0200"
updated: "2026-09-09T09:43:01.000+0200"
synced-at: "2026-09-09T13:45:59.638Z"
jira-orphaned: false
profile: Cariad
---

# RH-16784 [VNCNMS][VCTC]Missing critical section protection for IRV array access in generated RTE code

> [!jira] Solution Proposed · Critical · [[TAO_Sisi_(ETAS-ECMXSF-CN)|Sisi TAO]] · 更新于 2026-09-09T09:43:01.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-16784)

> 标签：#jira/comp/rta-rte #jira/label/vncnms

## 描述

Hi Team,

The issue is on RTA-RTE 12.9.0:

I would like to consult you about a possible issue in generated RTE code related to IRV access protection. I have reproduced the behavior with a small use case and will send the project to you separately for reference.

The use case is as follows:

1. In INP_SWC, I added one explicit inter-runnable variable named Irv_InpSwcValue.
2. Its type is an array type, currently modeled as uint8&#91;8&#93;, defined in &#91;INP_SWC.arxml|vscode-file://vscode-app/c:/Program%20Files/Microsoft%20VS%20Code/93cfdd489c/resources/app/out/vs/code/electron-browser/workbench/workbench.html&#93;.
3. I added two runnables:
  RE_INP_SWC_WriteIrv, which writes the IRV.
  RE_INP_SWC_ReadIrv, which reads the IRV.
4. RE_INP_SWC_WriteIrv is triggered by TE_INP_SWC_HighPrio_10ms, mapped to OsTask_Core2_BSW_1ms.
5. RE_INP_SWC_ReadIrv was originally triggered by OIE_INP_SWC_NotifyIrv.
6. Following two kinds of configuration generate different RTE Code:
  1. **OIE_INP_SWC_NotifyIrv is not mapped to Task** : For the attached project, I commented out the RteEventToTaskMapping of OIE_INP_SWC_NotifyIrv in RTA_Rte_EcucValues.arxml.

After generating RTE code, I observed that the generated IRV access APIs in Rte_Partition_Partition_Core2.c:1052 do not contain any critical section protection:

The generated implementation is essentially:

![[RH-16784-image001.png]]

                2. **OIE_INP_SWC_NotifyIrv is mapped to a lower priority Task**: You can open the comment and generate RTE again. RTE_ATOMIC will be generated to Rte_IrvRead:

FUNC(void, RTE_CODE)

Rte_IrvRead_INP_SWC_RE_INP_SWC_ReadIrv_Irv_InpSwcValue(P2VAR(Irv_InpSwcValue_ElementType, AUTOMATIC, RTE_APPL_DATA) data) /* 1 */

{*

**{**}RTE_ATOMIC{*}(Rte_memcpy(data, &Rte_Irv_INP_SWC_Irv_InpSwcValue, sizeof(Irv_InpSwcValue_Array8)));

}

FUNC(void, RTE_CODE)

Rte_IrvWrite_INP_SWC_RE_INP_SWC_WriteIrv_Irv_InpSwcValue(P2CONST(Irv_InpSwcValue_ElementType, AUTOMATIC, RTE_APPL_DATA) data) /* 1 */

{ Rte_memcpy(&Rte_Irv_INP_SWC_Irv_InpSwcValue, data, sizeof(Irv_InpSwcValue_Array8)); }

Customer’s concern is that for an IRV with array type, the generated read/write access is implemented as a plain memcpy without any critical section protection. If the read side and write side can run in different scheduling contexts with different priority, this seems to introduce a potential concurrent access risk, because the array copy is not atomic.

Could you please help confirm the following:

1. Is this generated behavior expected by the product?
2. Does the RTE generator intentionally avoid generating critical section protection for this kind of IRV array access?
3. Could the fact that I commented out the RteEventToTaskMapping for OIE_INP_SWC_NotifyIrv affect the generator’s decision regarding IRV protection?
4. If critical section protection is expected for this scenario, is there any additional modeling rule or configuration that must be applied?

 **Sisi TAO** 

Cross Functional Regional Solution Field Management - Regional Solution Field Manager China

M +86 133 81555197 

[Sisi.TAO@bosch.com!mail_small.gif!](mailto:Sisi.TAO@bosch.com)

ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

[www.etas.cn](https://www.etas.cn/)

 **ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2026-09-09 09:43 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Phuong Nguyen Le]]
> [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]] : Do you have any update for this issue? Cariad is asking us to deliver the solution on 25th/Sep.

-------

> [!note]+ 2026-08-20 11:56 · [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]]
> Hi [[JI_Jiaqi_(ETAS-ECMXSF-CN)|Jiaqi JI]] , I was assuming customer is using workaround proposed before, sorry for the delay. I confirm the RTE current behavior explained in above comment [https://rtahotline.etas.com/jira/browse/RH-16784?focusedCommentId=712565&page=com.atlassian.jira.plugin.system.issuetabpanels:comment-tabpanel#comment-712565] . I will create internal ticket to address this and link here.

-------

> [!note]+ 2026-08-20 04:21 · [[JI_Jiaqi_(ETAS-ECMXSF-CN)|Jiaqi JI]]
> Hi [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]] ,
>
> Could you help us investigate this issue that we are waiting for more than 1 week without feedback from Level 3? Thanks a lot!

-------

> [!note]+ 2026-08-20 04:20 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Sisi TAO. Your issue is set to "Critical" priority.
> Please ensure that there is a reasonable justification for this listed in the issue description, otherwise the priority may be reviewed and adjusted during triage.
> Kind regards

-------

> [!note]+ 2026-08-12 05:34 · [[TAO_Sisi_(ETAS-ECMXSF-CN)|Sisi TAO]]
> Hi [[Ho_Anh_Dang_(MSETA-Hub-CN)|Dang Ho Anh]] 
>
> I understand your workaround, thank you for showing this in such detail. 
> Technically it can work. But for customer, their SWC was all generated by scripts from excel files. That means, they don't need to open ISOLAR to configure SWC at all. And there is a lot of such IRVs in their project.
> If we use this workaround, we need to change excel sheet schema and write new script for customer.
> Let's wait for L3 support.

-------

> [!note]+ 2026-08-11 11:39 · [[Ho_Anh_Dang_(MSETA-Hub-CN)|Dang Ho Anh]]
> Hi [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]] ,
> Do we have any update on this issue?

-------

> [!note]+ 2026-08-03 16:34 · [[JSM_Service_Bot|JSM Service Bot]]
> Note: Vamsi Kiran Koduri added as watcher to the issue. Internal support agents cannot be added as Request Participants, so they have been automatically joined as Watchers instead.

-------

> [!note]+ 2026-08-03 16:34 · [[Ho_Anh_Dang_(MSETA-Hub-CN)|Dang Ho Anh]]
> Hi [[TAO_Sisi_(ETAS-ECMXSF-CN)|Sisi TAO]] ,
>
> Please refer to my recommended solution to handle the mentioned use case while [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]] analyzes the case.
>
> Thank you,

-------

> [!note]+ 2026-08-03 13:28 · [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]]
> [[Ho_Anh_Dang_(MSETA-Hub-CN)|Dang Ho Anh]] I will analyze RTE behavior in this case. Your proposal configuring exclusive area is also right approach and can be proposed to customer.

-------

> [!note]+ 2026-08-03 11:08 · [[Ho_Anh_Dang_(MSETA-Hub-CN)|Dang Ho Anh]]
> [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]] Yes, and the below is the trace for sequence of write and read of the array  when OIE_INP_SWC_NotifyIrv is mapped to OsTask_Core2_ASW_10ms().
>
> ![[RH-16784-image-2026-08-03-16-08-05-155.png]]

-------

> [!note]+ 2026-08-03 10:59 · [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]]
> [[Ho_Anh_Dang_(MSETA-Hub-CN)|Dang Ho Anh]] So you mean, 
> When OIE is mapped to task OsTask_Core2_ASW_10ms() -> RTE generates protection using RTE_ATOMIC
> When the OIE is not mapped, but the client runnable is running in same task OsTask_Core2_ASW_10ms() ->RTE doesn't generate any protection mechanism
> Is that correct?

-------

> [!note]+ 2026-08-03 10:40 · [[Ho_Anh_Dang_(MSETA-Hub-CN)|Dang Ho Anh]]
> Hi [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]] ,
>
> The below is my trace for the sequence of Write and Read array when OIE_INP_SWC_NotifyIrv is not mapped to OsTask_Core2_ASW_10ms().
> ![[RH-16784-image-2026-08-03-15-35-17-906.png]]
> The runnable {{{}RE_OUTP_SWC{}}}, which is related to our RPort, is mapped to {{{}OsTask_Core2_ASW_10ms{}}}.

-------

> [!note]+ 2026-08-03 10:19 · [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]]
> Hi [[Ho_Anh_Dang_(MSETA-Hub-CN)|Dang Ho Anh]], as i said before when OIE is not mapped rte considers context of the client runnable. can you please check the task mapped to the client runnable? That can give more explanation to why RTE doesn't generate any data consistency mechanism in Read API. Once that's clear we can think about proposing exclusive area approach.

-------

> [!note]+ 2026-08-03 09:43 · [[Ho_Anh_Dang_(MSETA-Hub-CN)|Dang Ho Anh]]
> Thanks [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]] ,
>
> I have just recommended one method to [[TAO_Sisi_(ETAS-ECMXSF-CN)|Sisi TAO]] to protect the variable.
>
> From your point of view, is my recommended method sufficient, or is there another method that is more specific to this use case?
>
> From Sisi's question:
> "RTE shall be aware of the context of the variable read and write accesses even when no OIE to Task mapping exist. Is it possible?"

-------

> [!note]+ 2026-08-03 09:39 · [[Ho_Anh_Dang_(MSETA-Hub-CN)|Dang Ho Anh]]
> [[TAO_Sisi_(ETAS-ECMXSF-CN)|Sisi TAO]] ,
>
> For the mentioned use case, from the SWC perspective, I think we can configure one exclusive area for the SWC. Then, for each runnable that accesses the variable, we can map the corresponding `CanEnterExclusiveArea` to this exclusive area .
>
> With this configuration, the RTE can generate the corresponding {{{}Rte_Enter_{*}{{*}{}}}} **and `Rte_Exit_`** APIs. The runnables that access the array can then call these APIs to protect the access.
>
> ![[RH-16784-image-2026-08-03-14-36-50-217.png]]
>
> ![[RH-16784-image-2026-08-03-14-37-18-372.png]]
>
> ![[RH-16784-image-2026-08-03-14-37-49-645.png]]
>
> Of course, the corresponding OS configuration for this resource (exclusive area) also needs to be configured properly.

-------

> [!note]+ 2026-08-03 09:32 · [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]]
> Hi [[Ho_Anh_Dang_(MSETA-Hub-CN)|Dang Ho Anh]], When OIE is not mapped to a task, then RTE considers the context of the task to which the corresponding client (connected to the PPort of OIE event) runnable is mapped.

-------

> [!note]+ 2026-08-03 04:06 · [[JSM_Service_Bot|JSM Service Bot]]
> Note: Dang Ho Anh added as watcher to the issue. Internal support agents cannot be added as Request Participants, so they have been automatically joined as Watchers instead.

-------

> [!note]+ 2026-08-03 04:06 · [[TAO_Sisi_(ETAS-ECMXSF-CN)|Sisi TAO]]
> Hi [[Ho_Anh_Dang_(MSETA-Hub-CN)|Dang Ho Anh]],
>
> Thank you for your analysis. Your observation is identical with mine.
> Since in Cariad project, they don't want to do the OIE to task mapping, they need the question 3 to be supported.
> That is to say, RTE shall be aware of the context of the variable read and write accesses even when no OIE to Task mapping exist. Is it possible? Let's wait for L3 expert support. Thank you.

-------

> [!note]+ 2026-07-31 16:43 · [[JSM_Service_Bot|JSM Service Bot]]
> Reminder for tickets requiring L3 RTE attention:
>
> - Have you attached the configuration?
> - Have you stated which version of RTA-CAR is being used (or, RTA-RTE)?
> - Have you tried the configuration with the latest version of RTA-CAR (or, RTA-RTE)?
> - Have you provided the exact command-line options and exact set of input files fed in to RTA-RTE (this could be the ISOLAR RTE LOG file)?
> - Have you stated the name of the customer?
> - Have you stated the priority / deadline?
> - Have you checked the history of hotline tickets for any relevant keywords?
>
> Not providing this information could delay the solution to the problem.

-------

> [!note]+ 2026-07-31 16:43 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]], this RTA-RTE ticket requires an assignee. As the component lead for RTA-RTE, please ensure that the 'Level 3 Assignee' field is set to the appropriate person that can handle this issue.

-------

> [!note]+ 2026-07-31 16:43 · [[Ho_Anh_Dang_(MSETA-Hub-CN)|Dang Ho Anh]]
> Hi [Koduri Vamsi Kiran (ETAS-ECM/XPC-Abt1),](https://confluence.etas-dev.com/display/~kod4abt)
>
> This ticket is related to the protection mechanism for IRV array accesses.
>
> Could you please help check questions 3 and 4?
>
> Regarding questions 1 and 2, could you also review them and provide your comments if I am missing anything?
>
> Thank you.

-------

> [!note]+ 2026-07-31 16:16 · [[Ho_Anh_Dang_(MSETA-Hub-CN)|Dang Ho Anh]]
> Hi [[TAO_Sisi_(ETAS-ECMXSF-CN)|Sisi TAO]] ,
>
> {*}Use case 1{*}: For the project where the `OIE_INP_SWC_NotifyIrv` sections are commented out in the RTE configuration, I think the RTE cannot determine the context of the variable read and write accesses. Therefore, it cannot generate the required protection code for them.
>
> {*}Use case 2{*}: For the project where these sections are uncommented, the RTE can generate the protection code accordingly. In this case, the array write action is called by `OsTask_Core2_BSW_1ms` with priority 27, and the array read action is called by `OsTask_Core2_ASW_10ms` with priority 10.
>
> Since the priority of the task calling the write action is higher than the priority of the task calling the read action, the protection code is applied only to the read action, for example by using `RTE_ATOMIC` or `Rte_SuspendOSInterrupts()` / {{{}Rte_ResumeOSInterrupts(){}}}.
>
> {*}Use case 3{*}: You can try configuring the priority of the task calling the read action to be higher than the priority of the task calling the write action. In that case, the protection code will be applied to the write action, as shown below:
>
> ![[RH-16784-image-2026-07-31-21-17-27-320.png]]
>
> So for the questions:
>  # Is this generated behavior expected by the product?
> It is expected behavior of RTE.
>  # Does the RTE generator intentionally avoid generating critical section protection for this kind of IRV array access?
> This variable is accessed by the same core, so I think the Suspend and Resume Interrupts is enough for the protection. In case of the variable is accessed by different cores, the IOC channel will be generated instead, you can try this use case by moving RE_INP_SWC_WriteIrv to another core.
>  # Could the fact that I commented out the RteEventToTaskMapping for OIE_INP_SWC_NotifyIrv affect the generator’s decision regarding IRV protection?
> I will check with L3 expert.
>  # If critical section protection is expected for this scenario, is there any additional modeling rule or configuration that must be applied? I think using `SuspendInterrupts` and `ResumeInterrupts` is sufficient. However, if We can use another method, such as an OS resource, we can avoid the overhead caused by suspending all interrupts. I need to check with L3 expert for the solution.

-------

> [!note]+ 2026-07-31 09:26 · [[Phan_Huynh_Dang_Khoa_(MSETA-Hub-CN)|Khoa Phan Huynh Dang]]
> Hi [[TAO_Sisi_(ETAS-ECMXSF-CN)|Sisi TAO]] 
> Sorry for keeping you waiting for so long. We are still analyzing the issue and will provide an update as soon as possible.

-------

> [!note]+ 2026-07-29 04:24 · [[JI_Jiaqi_(ETAS-ECMXSF-CN)|Jiaqi JI]]
> Hi [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Phuong Nguyen Le]] ,
>
> Could you assign one engineer for this ticket? Thanks a lot!

-------

> [!note]+ 2026-07-28 12:22 · [[TAO_Sisi_(ETAS-ECMXSF-CN)|Sisi TAO]]
> [^BasicSoftware_IRV_Protect.zip]

-------

> [!note]+ 2026-07-28 12:13 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Sisi TAO, please note that this issue was made with VNCNMS in the summary and has been sent to the relevant queue by adding the VNCNMS label.

-------

> [!note]+ 2026-07-28 12:13 · [[JSM_Service_Bot|JSM Service Bot]]
> Note: Jiaqi JI, Jie LIU added as watcher to the issue. Internal support agents cannot be added as Request Participants, so they have been automatically joined as Watchers instead.

-------

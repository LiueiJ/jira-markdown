---
jira_key: RH-16761
jira_url: "https://rtahotline.etas.com/jira/browse/RH-16761"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: High
project: RH
assignee: junsheng.zhang@bosch.com
reporter: junsheng.zhang@bosch.com
tags: [VNCNMS]
components: []
fix-versions: []
epic: null
parent: null
created: "2026-07-25T12:56:58.000+0200"
updated: "2026-08-12T14:26:29.000+0200"
synced-at: "2026-09-06T06:58:38.472Z"
jira-orphaned: false
---

# RH-16761 [VNCNMS][VCTC]Priority issue in DCM

> [!jira] Closed · High · [[Junsheng_ZHANG|Junsheng ZHANG]] · 更新于 2026-08-12T14:26:29.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-16761)

> 标签：#jira/label/vncnms

## 描述

Hi Hotline, 

 The customer has some questions about the priority between different protocols(DoCAN and DoIP) in the DCM. Could you please reply to their inquiries? 

1. If multiple protocols (DoCAN and DoIP) use the same ServiceTable, are their sessions shared? For example, after a DoCAN request switches to the default session, then a DoIP request switches to the extended session—would that be considered a shared session?
2. When two different priority protocols (DoCAN priority 1and DoIP priority 2) are involved and the high-priority one is executed, what happens if a low-priority protocol preempts the high-priority protocol? Will an NRC be returned, and will the current task still be executed?
3. When two different priority protocols (DoCAN priority 1and DoIP priority 2) are involved and the low-priority protocol is executing, what happens if the high-priority protocol preempts the low-priority one? Will an NRC be returned, and will the current task continue to execute?
4. When DoIP (protocol = 2) is executing a diagnostic service and DoCAN (protocol = 1) receives 3E 80, what will happen? Can the S3 timer be updated?Alternatively, when DoIP (protocol = 1) is executing a diagnostic service and DoCAN (protocol = 2) receives 3E 80, what will happen?

 ** Junsheng ZHANG** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 

 M +86 155 32928056 

 [Junsheng.ZHANG@bosch.com!mail_small.gif!](mailto:Junsheng.ZHANG@bosch.com) 

 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

 [www.etas.cn](https://www.etas.cn)   ** 

 

 ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2026-08-12 14:26 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2026-07-29 14:00 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> {color:#de350b}When DoIP (protocol = 2) is executing a diagnostic service and DoCAN (protocol = 1) receives 3E 80, what will happen? Can the S3 timer be updated?Alternatively, when DoIP (protocol = 1) is executing a diagnostic service and DoCAN (protocol = 2) receives 3E 80, what will happen?{color}
>
>
> **Case1: A DoIP request (lower priority) is being processed when a TesterPresent (0x3E 0x80) request is received via DoCAN (higher priority)**
>
> → {*}According to question 3{*}, the TesterPresent request received on DoCAN (the higher-priority protocol) preempts the ongoing task on DoIP and causes it to be canceled. No response is sent for the interrupted DoIP request.
>
> {*}The TesterPresent request on DoCAN is then processed normally{*}. Since the SPRMIB (Suppress Positive Response Message Indication Bit) is set, no positive response is transmitted. However, the **S3 timer is restarted** because the request is valid and has actually been processed by the DCM.
> ----
> **Case2: A DoIP request (higher priority) is being processed when a TesterPresent (0x3E 0x80) request is received via DoCAN (lower priority)**
>
> → {*}According to question 2{*}, the DoCAN request is rejected with {*}NRC 0x21 (BusyRepeatRequest){*}.
>
> An important point is that the NRC is always sent, even when SPRMIB is set. According to ISO 14229-1, the suppress-positive-response bit applies only to {*}positive responses{*}, not to {*}negative responses{*}. S3 timer is not updated 
>
> ![[RH-16761-image-2026-07-29-19-00-21-196.png]]

-------

> [!note]+ 2026-07-29 11:54 · [[JSM_Service_Bot|JSM Service Bot]]
> Note: Jiaqi JI added as watcher to the issue. Internal support agents cannot be added as Request Participants, so they have been automatically joined as Watchers instead.

-------

> [!note]+ 2026-07-29 11:54 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hello [[Junsheng_ZHANG|Junsheng ZHANG]] , [[Jiaqi_JI|Jiaqi JI]] 
>  * {color:#de350b}If multiple protocols (DoCAN and DoIP) use the same ServiceTable, are their sessions shared? For example, after a DoCAN request switches to the default session, then a DoIP request switches to the extended session—would that be considered a shared session?{color}
>
> Yes, module DCM only use one session state for all protocols and your example is correct. As you can see, DCM only maintain 1 variable "Dcm_SesCtrlType" for ECU and ignore protocol type (as the input) in the definition.
>
> ![[RH-16761-image-2026-07-29-16-06-54-955.png]]
>  * {color:#de350b}When two different priority protocols (DoCAN priority 1and DoIP priority 2) are involved and the high-priority one is executed, what happens if a low-priority protocol preempts the high-priority protocol? Will an NRC be returned, and will the current task still be executed?{color}
>
> {color:#172b4d}You can refer "{*}7.4.4.14.3 Preemption of protocol{*}" in "{*}AUTOSAR_SWS_DiagnosticCommunicationManager.pdf{*}" for this concern and the next question. Then, {color}
> + If a new request arrives on a lower-priority protocol while a higher-priority protocol is already processing a request --> the lower-priority request will be rejected.
>
> + If **DcmDslDiagRespOnSecondDeclinedRequest** is configured {*}TRUE{*}, NRC 0x21 (BusyRepeatRequest) will be returned on the lower-priority protocol itself.
>
> + The task running on the higher-priority protocol will continue to execute normally and will not be interrupted.
>
> {color:#172b4d}![[RH-16761-image-2026-07-29-16-32-12-863.png]]{color}
>  * {color:#de350b}When two different priority protocols (DoCAN priority 1and DoIP priority 2) are involved and the low-priority protocol is executing, what happens if the high-priority protocol preempts the low-priority one? Will an NRC be returned, and will the current task continue to execute?{color}
>
> If a new request is received via a higher-priority protocol while a request on a lower-priority protocol is being processed, **DCM immediately aborts the ongoing task on the lower-priority protocol.** No response (neither a negative nor a positive response) is transmitted for the aborted DoIP request, as it is terminated before completion. {*}DCM then proceeds with processing the newly received request on the higher-priority protocol{*}.
> ![[RH-16761-image-2026-07-29-16-48-42-953.png]]

-------

> [!note]+ 2026-07-28 11:44 · [[Jiaqi_JI|Jiaqi JI]]
> Hi [[Phuong_Nguyen_Le|Phuong Nguyen Le]] ，
>
> Please support for assign one engineer on this issue.
>
> Noted with thanks!

-------

> [!note]+ 2026-07-28 11:44 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Junsheng ZHANG, please note that this issue was made with VNCNMS in the summary and has been sent to the relevant queue by adding the VNCNMS label.

-------

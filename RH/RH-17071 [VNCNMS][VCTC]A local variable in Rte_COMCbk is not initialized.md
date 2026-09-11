---
jira_key: RH-17071
jira_url: "https://rtahotline.etas.com/jira/browse/RH-17071"
server: rtahotline
kind: hotline
type: Support
status: Solution Proposed
priority: High
project: RH
assignee: "[[Junsheng_ZHANG|Junsheng ZHANG]]"
reporter: "[[Junsheng_ZHANG|Junsheng ZHANG]]"
tags: [jira/comp/rta-rte, jira/label/vncnms]
fix-versions: []
epic: null
parent: null
created: "2026-08-30T08:52:16.000+0200"
updated: "2026-09-10T05:35:48.000+0200"
synced-at: "2026-09-11T01:36:25.139Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Hi hotline, 

 In the Rte_COMCbk function, composite is not initialized. Under normal circumstances, this is not a problem. However, if composite.status is abnormal, the uninitialized data value may be passed directly to the SWC, which could cause errors in the customer’s code. 

 So the customer believes that, at minimum, we should modify it to Rte_Rx_000847_Composite_Type composite = 

{0}
; so that the structure gets an initial value at least. 

![[RH-17071-image001.png]] 

 ** Junsheng ZHANG** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 

 M +86 155 32928056 

 [Junsheng.ZHANG@bosch.com!mail_small.gif!](mailto:Junsheng.ZHANG@bosch.com) 

 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

 [www.etas.cn](https://www.etas.cn)   ** 

 

 ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2026-09-04 10:34 · [[Dang_Ho_Anh|Dang Ho Anh]]
> Hi [[Junsheng_ZHANG|Junsheng ZHANG]] ,
>
> I see two possible options here:
>  # Use the proper RTE function to retrieve the data. This option does not require an RTE update.
>  # If the customer still wants to apply the fix from RTE v12.12.0 to the Cariad version of RTA-CAR 12.11.x, [[Jiaqi_JI|Jiaqi JI]] needs to raise a request to the RTE team for the upgrade.
>
> Could you please check this?
>
> Thank you.

-------

> [!note]+ 2026-09-04 09:18 · [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]]
> Hi [[Dang_Ho_Anh|Dang Ho Anh]] , I am not in a position to answer this. This has to be discussed in Planning/Release meetings related to Cariad customer.

-------

> [!note]+ 2026-09-04 09:09 · [[Dang_Ho_Anh|Dang Ho Anh]]
> Hi [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]],
> Can the fix from RTE v12.12.0 be applied to the Cariad customer’s RTA-CAR 12.11.x version?

-------

> [!note]+ 2026-09-03 14:30 · [[JSM_Service_Bot|JSM Service Bot]]
> [[Junsheng_ZHANG|Junsheng ZHANG]], the comment you've just made is internal. Please note that internal comments do not transition an issue to 'Waiting for Level 2'.

-------

> [!note]+ 2026-09-03 14:30 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> Hi [[Dang_Ho_Anh|Dang Ho Anh]] ,
>
> Yes,Rte_Rx_xxx;
>
> I saw earlier comments saying it has already been fixed—could it be integrated into the version that our customer is currently using?

-------

> [!note]+ 2026-09-03 11:20 · [[Dang_Ho_Anh|Dang Ho Anh]]
> [[Junsheng_ZHANG|Junsheng ZHANG]] , Which variable customer use to directly read the data? {_}Rte_Rx{_}_* ?

-------

> [!note]+ 2026-09-03 11:06 · [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]]
> Is fixed in RTE v12.12.0 using https://jira.etas-dev.com/browse/RTE-22065

-------

> [!note]+ 2026-09-03 10:54 · [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]]
> Hi [[Junsheng_ZHANG|Junsheng ZHANG]]  May i know RTE version used here?

-------

> [!note]+ 2026-09-03 10:19 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> Hi [[Dang_Ho_Anh|Dang Ho Anh]] ,
>
>     You’re right. However, some of the customer’s modules directly read the values without checking the status. Although this is not very reasonable, we should still not upload/propagate incorrect data.

-------

> [!note]+ 2026-09-03 10:16 · [[JSM_Service_Bot|JSM Service Bot]]
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

> [!note]+ 2026-09-03 10:16 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]], this RTA-RTE ticket requires an assignee. As the component lead for RTA-RTE, please ensure that the 'Level 3 Assignee' field is set to the appropriate person that can handle this issue.

-------

> [!note]+ 2026-09-03 10:15 · [[Dang_Ho_Anh|Dang Ho Anh]]
> Hi [[Junsheng_ZHANG|Junsheng ZHANG]] ,
> In the `Rte_COMCbk()` function, when `Com_ReceiveSignalGroupArray()` returns {{{}COM_SERVICE_NOT_AVAILABLE{}}}, this leads to {{{}composite.status = COM_SERVICE_NOT_AVAILABLE{}}}. In this case, `composite.transformerError` and `composite.data` have unspecified values, as you mentioned.
>
> When `Rte_Read()` is called to get the data, this function returns {{{}RTE_E_COM_STOPPED{}}}.
>
> ![[RH-17071-image-2026-09-03-14-33-05-130.png]]
>
>
> From the SWC point of view, the SWC can use the return value of `Rte_Read()` to determine whether the data is valid or not. Therefore, the unspecified values of `composite.transformerError` and `composite.data` are no longer important here.
>
> Hi [Koduri Vamsi Kiran (ETAS-ECM/XPC-Abt1)](https://confluence.etas-dev.com/display/~kod4abt),
>
> From my understanding, this is not an issue. Please let me know if you have a different viewpoint.

-------

> [!note]+ 2026-09-03 04:33 · [[Dang_Ho_Anh|Dang Ho Anh]]
> Hi [[Jiaqi_JI|Jiaqi JI]] We have just returned from national holiday, and I will check this ticket.

-------

> [!note]+ 2026-09-01 04:51 · [[Jiaqi_JI|Jiaqi JI]]
> Hi [[Phuong_Nguyen_Le|Phuong Nguyen Le]] ,
>
> Could you help assign one engineer for the issue investigation?
>
> Noted with thanks for your kindly support!

-------

> [!note]+ 2026-09-01 04:51 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Junsheng ZHANG, please note that this issue was made with VNCNMS in the summary and has been sent to the relevant queue by adding the VNCNMS label.

-------

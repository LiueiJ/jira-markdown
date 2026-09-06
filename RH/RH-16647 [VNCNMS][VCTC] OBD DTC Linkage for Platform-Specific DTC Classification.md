---
jira_key: RH-16647
jira_url: "https://rtahotline.etas.com/jira/browse/RH-16647"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Critical
project: RH
assignee: jiaqi.ji@etas.com
reporter: jiaqi.ji@etas.com
tags: [VNCNMS]
components: [Diagnostic-EventStateMgmt]
fix-versions: []
epic: null
parent: null
created: "2026-07-15T07:27:35.000+0200"
updated: "2026-08-03T13:42:30.000+0200"
synced-at: "2026-09-06T06:58:38.472Z"
jira-orphaned: false
---

# RH-16647 [VNCNMS][VCTC] OBD DTC Linkage for Platform-Specific DTC Classification

> [!jira] Closed · Critical · [[Jiaqi_JI|Jiaqi JI]] · 更新于 2026-08-03T13:42:30.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-16647)

> 标签：#jira/comp/diagnostic-eventstatemgmt #jira/label/vncnms

## 描述

Hi Team, 

A DTC is OBDDTC on one platform and NoneOBDDTC on another platform. I configure the DTC to be linked to OBDDTC. Can the OBDDTC be linked or unlinked through a calibration variable? 

Noted with thanks for support! 

![[RH-16647-image001.png]] 

Best Regards, 

 ** Jiaqi JI** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 [Jiaqi.JI@etas.com!mail_small.gif!](mailto:Jiaqi.JI@etas.com) 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

 [www.etas.cn](https://www.etas.cn)  

  ** ETAS – Empowering Tomorrow’s Automotive Software**

## 关联

- is mentioned in: [[RH-16810 [VNCNMS][VCTC] OBD Cross-Core Implementation and NoOBD Configuration]]

## 评论

> [!note]+ 2026-07-31 14:24 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2026-07-17 06:38 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hi [[Sagar_Subbaramaiah|Sagar Subbaramaiah]] , anh [[Dang_Ho_Anh|Dang Ho Anh]] 
>
> Thank you so much for your response.
>
> Hi [[Jiaqi_JI|Jiaqi JI]] ,
> As confirmed by your side, the customer Cariad will use **RTA-CAR 12.11.0** as their latest version (not RTA-CAR 12.11.0VCTCESR). In this case, they can use PBS for **DemDTC.DemDtcOBDRelevance** to handle their feature. 
> ![[RH-16647-image-2026-07-17-11-26-51-968.png]]
> {+}Additionally{+}, you can also refer to PBS for switching between OBD and non-OBD protocols.
> ![[RH-16647-image-2026-07-17-11-36-20-690.png]]

-------

> [!note]+ 2026-07-16 08:48 · [[Sagar_Subbaramaiah|Sagar Subbaramaiah]]
> Hi [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]],
>
> you are absolutely right. There is no support for changing the OBD relevance of a monitor by calibration in our product. PostBuildSelectable is the right choice here, which is supported from RTA-CAR 12.10.0 onwards.
>
> BTW, the Tool Version is mentioned as RTA-CAR 12.11.0VCTCESRpr1, so I assume that it is newer than RTA-CAR 12.10.0. However, the attached screenshot seems to be from a different RTA-CAR version, as it does not show the parameter `DemDTC.DemDtcOBDRelevance`. Anyway, from RTA-CAR 12.10.0 onwards, the OBD relevance of a DTC is not depending on whether it has DemOBDDtc configured or not. Instead, it depends on whether the parameter `DemDTC.DemDtcOBDRelevance` is enabled or not.
>
> P.S: BTW, it looks like the customers outside ETAS are added to this ticket. If I am not wrong, tickets assigned to L3 should not have any non-ETAS persons. So, I am confused why someone from Cariad is added to the ticket.

-------

> [!note]+ 2026-07-16 05:10 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi [[Gunjan_Pradip_Mantala|Gunjan Pradip Mantala]], this Diagnostic-EventStateMgmt ticket requires an assignee. As the component lead for Diagnostic-EventStateMgmt, please ensure that the 'Level 3 Assignee' field is set to the appropriate person that can handle this issue.

-------

> [!note]+ 2026-07-16 05:10 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hello [[Gunjan_Pradip_Mantala|Gunjan Pradip Mantala]] ,
>
> ![[RH-16647-image-2026-07-16-10-07-35-342.png]]
> Regarding the customer's concerns, the background and feature are explained below:
> ![[RH-16647-image-2026-07-16-10-01-57-872.png]]
>  # 
> Do we have any useful configuration options for this case?
>  # 
> If not, we are currently proposing the use of **PostBuildSelectable** and **MIC handling** as a solution.
> We would appreciate it if you could suggest a better approach for us to consider. ☺️

-------

> [!note]+ 2026-07-15 12:57 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> **1. Can the OBDDTC be linked or unlinked through a calibration variable?**
>
> No, {color:#de350b}`DemObdDTCRef` {color}(the reference linking {color:#de350b}`DemDTC`{color} to {color:#de350b}`DemObdDTC`{color}) is not a calibration parameter and c{*}annot be switched on or off{*} through calibration tools such as INCA or CANape at {*}runtime{*}. It is a statically configured structural reference that is resolved during {*}the build process{*}, not a runtime-tunable characteristic. In this case, you can refer the PostBuild Selectable to create variants for handling.
> [Variant Handling - Configure Post Build Selectable project - RTA Hotline Confluence](https://rtahotline.etas.com/confluence/display/RH/Variant+Handling+-+Configure+Post+Build+Selectable+project)

-------

> [!note]+ 2026-07-15 09:24 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hi [[Jiaqi_JI|Jiaqi JI]] ,
> I have changed the priority of this topic to **_Critical_** because it is {+}currently blocking the customer's progress due to the error discussed in yesterday's meeting{+}. We will prioritize this topic and keep you informed of the solution as soon as possible.

-------

> [!note]+ 2026-07-15 07:27 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Jiaqi.JI@bosch.com, please note that this issue was made with VNCNMS in the summary and has been sent to the relevant queue by adding the VNCNMS label.

-------

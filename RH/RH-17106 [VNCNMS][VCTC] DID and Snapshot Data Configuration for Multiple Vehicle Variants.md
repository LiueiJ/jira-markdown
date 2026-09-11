---
jira_key: RH-17106
jira_url: "https://rtahotline.etas.com/jira/browse/RH-17106"
server: rtahotline
kind: hotline
type: Support
status: Solution Proposed
priority: Low
project: RH
assignee: "[[Jiaqi_JI|Jiaqi JI]]"
reporter: "[[Jiaqi_JI|Jiaqi JI]]"
tags: [jira/label/vncnms]
fix-versions: []
epic: null
parent: null
created: "2026-09-02T10:21:32.000+0200"
updated: "2026-09-07T14:49:27.000+0200"
synced-at: "2026-09-11T01:36:25.139Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Hi Team,

Cariad encountered issues as: The current software version needs to support multiple vehicle variants, such as **ICE and BEV**. However, different vehicle variants support different DIDs, and these DIDs are also used as **snapshot data** for DTCs.

For example:

- **ICE vehicle** supports **DID1, DID2, and DID3**. For **DTC1**, the snapshot data should contain*
  **{**}DID1, DID2, and DID3{*}.
- **BEV vehicle** supports only **DID1 and DID2**. For the same **DTC1**, the snapshot data should contain only **DID1 and DID2**.

Currently, all DIDs ( **DID1, DID2, and DID3**) are configured in the same software version. This creates a configuration challenge because the supported DIDs and the snapshot data requirements are different for each vehicle variant.

**Question1:**

How can we configure the software so that:

1. The same software version can support **different DID sets for different vehicle variants**.
2. The same DTC can have **different snapshot data configurations depending on the vehicle variant**.
3. Unsupported DIDs are not exposed or accessed on vehicle variants where they are not applicable.
4. The solution can be managed through configuration rather than requiring separate software branches or extensive variant-specific code changes.

### Question2: Variant-Specific DID Configuration for F400

In C7, **F400 indicates which DIDs from F401–F420 are supported**. When the supported DIDs are configured in the ETAS tool, the response value of F400 is generated automatically based on the configuration.

However, different vehicle variants support different DIDs. For example:

- **ICE variant:** supports F401 only
- **BEV variant:** supports F401 and F402

Currently, our software configuration includes both F401 and F402. We would like to use **one software baseline** for different vehicle variants while configuring different supported DIDs for each variant.

**Question2:**

How can we configure different supported DIDs for different vehicle variants within a single software baseline, while ensuring that the automatically generated **F400 response value matches the DIDs supported by each vehicle variant**?

Noted with thanks for your support!

BR,

 **Jiaqi JI** 

Cross Functional Regional Solution Field Management - Regional Solution Field Manager China

[Jiaqi.JI@etas.com!mail_small.gif!](mailto:Jiaqi.JI@etas.com)

ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

[www.etas.cn](https://www.etas.cn/)

 **ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2026-09-07 14:49 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> [^PBS for BIP.pdf]

-------

> [!note]+ 2026-09-04 09:35 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> After today's meeting, the customer confirmed that they would like to support multiple variants with a single software implementation. Post-Build Selectable (PBS) was identified as the most suitable approach for this use case, and it was introduced during the meeting.
>
> The customer has requested a sample configuration for this approach on RTA-CAR 12.11.0. I will prepare it and provide it to them.

-------

> [!note]+ 2026-09-03 12:05 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> [Variant Handling - Configure Post Build Selectable project](https://rtahotline.etas.com/jira/servicedesk/customer/kb/view/94699521?applicationId=863fe0e2-7493-3f1a-91dc-81934cdeb430&spaceKey=RH&portalId=1&title=Variant+Handling+-+Configure+Post+Build+Selectable+project&requestKey=RH-17106)
>
> Users can use MIC or PBS to handle variants on their side, and this approach shall support their use case. I will guide them through the process during tomorrow's meeting.

-------

> [!note]+ 2026-09-03 08:59 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Start analyzing this ticket today.

-------

> [!note]+ 2026-09-02 10:21 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Jiaqi JI, please note that this issue was made with VNCNMS in the summary and has been sent to the relevant queue by adding the VNCNMS label.

-------

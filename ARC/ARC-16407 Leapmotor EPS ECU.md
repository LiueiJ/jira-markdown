---
jira_key: ARC-16407
jira_url: "https://jira.etas-dev.com/browse/ARC-16407"
server: etas
kind: motivation
type: Motivation
status: New
priority: ""
project: ARC
assignee: "[[Karthi_Krishna_Shekaar_(MSEMT-ETAS)|Karthi Krishna Shekaar (MS/EMT-ETAS)]]"
reporter: "[[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]]"
tags: []
fix-versions: []
epic: null
parent: null
created: "2026-05-28T13:39:42.000+0000"
updated: "2026-09-03T10:42:58.000+0000"
synced-at: "2026-09-11T02:40:23.945Z"
jira-orphaned: false
profile: CN Motivation
---

## 描述

Here is requirement from OEM - Leapmotor,

MCC(multicore consistency check)

Locomo(Local core memory optimization)

The customer, who is currently developing an EPS(electronic power steering) controller at Leapmotor and previously worked at UAES,

has learned that CUBAS and BBM use the above tools.

He is inquiring whether ETAS’s RTA-CAR offers a similar solution.

If not, please share an implementation plan.

if the updated version could support the feature, ETCN could push customer purchase M&S and sale more RTA-CAR development license in Leapmotor.

## 评论

> [!note]+ 2026-09-03 06:54 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]] can you fil in some more project details int he description please. I assume EPS means "electronic power steering" but it could be something else. Please also add the TNS we can expect - thanks!

-------

> [!note]+ 2026-06-16 05:29 · [[Karthi_Krishna_Shekaar_(MSEMT-ETAS)|Karthi Krishna Shekaar (MS/EMT-ETAS)]]
> Hello [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]],
>  * MCC: As mentioned in previous comment, the checked done specifically for PS-SC requirement. So it would be better if we know the expectation of customer.
>  * For Exclusive area lock analysis & Call graph view, detailed documentation are available in RTA-CAR user guide (refer section 6.2.4 & 6.3) & ISOLAR-A_Help_Reference Manual (section 3.12 & 2.9)
>  * Overview of Plat4mc feature set is available in the page [MTP - Multicore Tooling Platform - MTP - Multicore Tooling Platform - Docupedia](https://inside-docupedia.bosch.com/confluence/spaces/PCMTP/pages/435520027/MTP+-+Multicore+Tooling+Platform)

-------

> [!note]+ 2026-06-15 09:16 · [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]]
> [[Karthi_Krishna_Shekaar_(MSEMT-ETAS)|Karthi Krishna Shekaar (MS/EMT-ETAS)]] 
>
> Thank you for your reply,
>
> 1, Customer expects the feature of MCC.
>
> 2," Features already available in RTA-CAR:
>  * 
>  ** Exclusive area lock analysis
>  ** Call Graph view "
>
> Could you show more detail about those features? 
>
> 3, about Plat4mc, could you share any information about this Topic?

-------

> [!note]+ 2026-06-15 09:02 · [[Karthi_Krishna_Shekaar_(MSEMT-ETAS)|Karthi Krishna Shekaar (MS/EMT-ETAS)]]
> [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] 
>
> At present, these two features (MCC & Locomo) are not part of RTA-CAR and available for BOSCH only.
>
> Just to confirm, whether Leapmotor mentioned about MCC or DCC (Data Consistency check)?
>  * MCC:
>  ** This feature has the checks that are implemented based on specification from PS-SC
>  ** Whether customer expect the check as its available for PS-SC? 
>  * Locomo:
>  ** The analysis is ongoing to bring certain parts of Locomo in RTA-CAR
>  ** The current plan is to have prototype version available tentatively by beginning of next year
>  * Features already available in RTA-CAR:
>  ** Exclusive area lock analysis
>  ** Call Graph view
>
> In case customer is looking for specific features of Plat4mc, we can work on possibilities to provide required feature set as an engineering service.

-------

> [!note]+ 2026-06-12 02:55 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[Karthi_Krishna_Shekaar_(MSEMT-ETAS)|Karthi Krishna Shekaar (MS/EMT-ETAS)]]  [[Raza_Syed_Aoun_(ETAS-ECMXPC-Fe1)|Raza Syed Aoun (ETAS-ECM/XPC-Fe1)]] 
>
> LeapMotor wants to know if the below tools from Bosch is supported within our RTA-CAR ?
>  * MCC(multicore consistency check)
>  * Locomo(Local core memory optimization)
>
> I believe these are very old tools.  would like to know:
>  * Are there are any related tooling support already available within RTA-CAR ?
>  * What other related tooling features from Plat4MC available in our RTA-CAR ?
>  * What features are currently in planning ? 
>
> Could you please share this information before Next Monday (June-14)? We have a customer visit on Tuesday, and we are expected to communicate our advanced Tooling features related to Multicore & Plat4MC available in our product. 
>
> much appreciate your support.  Many Thanks. 
>
> [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]] [[Karthik_M_S_(MSEMT-ETAS)|Karthik M S (MS/EMT-ETAS)]] [Gobbilla Gopi Krishna (MS/EMT2-ETAS)](https://confluence.etas-dev.com/display/~gob1kor) fyi

-------

> [!note]+ 2026-06-07 08:36 · [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]]
> [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] Hi Sathish, could you support to assign expert to feedback this question?

-------

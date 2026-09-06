---
jira_key: ARC-13540
jira_url: "https://jira.etas-dev.com/browse/ARC-13540"
server: etas
kind: motivation
type: Motivation
status: Accepted
priority: ""
project: ARC
assignee: tan9sgh
reporter: but9fe
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2025-10-31T14:38:20.000+0000"
updated: "2026-06-19T09:00:11.000+0000"
synced-at: "2026-09-06T06:58:54.667Z"
jira-orphaned: false
---

# ARC-13540 Nissan ZCU_L, ZCU_R and ZCU_T propjects

> [!jira] Accepted ·  · [[TAN_Yang_(ETAS-ECMXSF-CN)|TAN Yang (ETAS-ECM/XSF-CN)]] · 更新于 2026-06-19T09:00:11.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-13540)

## 描述

There appears to be a project at DongFeng/Nissan for a zone control platform (3x ECUs). NXP are especially interested in a vendor that can offer S32K5 support.

Tier1 will likely be their internal Tier1 Lianyou

## 关联

- relates to: [[ARC-14650 S32K5/M7 Support ]]
- relates to: [[ARC-14654 AVB Support]]

## 评论

> [!note]+ 2026-03-25 23:51 · [[TAN_Yang_(ETAS-ECMXSF-CN)|TAN Yang (ETAS-ECM/XSF-CN)]]
> Hi [[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]] 
>
> <<<Does this mean DF-Nissan project had the budget for the entire project cut by the DF-Nissan management? >>> For autosar purchase, yes it it at the moment.

-------

> [!note]+ 2026-03-25 13:23 · [[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]]
> [[TAN_Yang_(ETAS-ECMXSF-CN)|TAN Yang (ETAS-ECM/XSF-CN)]] I'm not sure I fully understand this line 
> {quote}However the order will also not be secured due to NXP customer DF-Nissan cut this budget completely resulting the ongoing purchase order to ETAS be suspended.
> {quote}
> Does this mean DF-Nissan project had the budget for the entire project cut by the DF-Nissan management? 

-------

> [!note]+ 2026-03-25 00:03 · [[TAN_Yang_(ETAS-ECMXSF-CN)|TAN Yang (ETAS-ECM/XSF-CN)]]
> [[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]] ,
>
> <<<If you re-sent the quotation without the porting fee, do you think they'd be enticed to purchase from ETAS?>>>
>  * this could enable DF-Nissan to consider ETAS solution at almost the only supplier
>  * However the order will also not be secured due to NXP customer DF-Nissan cut this budget completely resulting the ongoing purchase order to ETAS be suspended.

-------

> [!note]+ 2026-03-19 21:14 · [[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]]
> Hi [[TAN_Yang_(ETAS-ECMXSF-CN)|TAN Yang (ETAS-ECM/XSF-CN)]]. To entice DF-Nissan to purchase the solution from ETAS, let's waive the porting fee.
>
> If you re-sent the quotation without the porting fee, do you think they'd be enticed to purchase from ETAS?
>
> CC [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]] 

-------

> [!note]+ 2026-02-10 16:12 · [[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]]
> Hi all,
>
> DF-Nissan are pushing NXP to pay the 350k RMB porting fee, citing issues with paying a "migration fee". Looks like they don't like being the first to use it and therefore have to pay.
>
> This is the communication we received from NXP in China:
> {quote}Hi Tom,
>
> Could you help to ask the China local team provide quotation without “migration fee item”(if other name is acceptable like “integration fee” or “testing & debugging fee” ), “migration fee” gave customer an excuse to argue with NXP, it is new chip and Nissan/LANYOU thought the migration fee should be allocated to all of the customers who will use S32K5 and NXP should pay for that, which should not charge to them (they believe they are the first customer to use K5, that’s the reason they are charged with migration fee). They are pushing NXP to accept to pay for 350kRMB, which made everything stuck here（we don’t  have the budget for this project）.
>
> Thanks a lot for your great help!
> {quote}
> Is this change in the quotation something that could be done? And if so, would even help?

-------

> [!note]+ 2026-01-23 17:01 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> The NXP tyeam are being asked by DOngFeng for some "AVB things". It is unclear exactly what - I am trying to find out - but it is quite possibly the same ask they are making as the TSN PoC stuff they have asked us about. [[TAN_Yang_(ETAS-ECMXSF-CN)|TAN Yang (ETAS-ECM/XSF-CN)]] /[[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]  - has there been any progress on the PoC request for deriving the BSW TSN requirements and, if yes, then what exactly are we doing, for who and on which timeline? Thanks.

-------

> [!note]+ 2025-11-26 11:00 · [[TAN_Yang_(ETAS-ECMXSF-CN)|TAN Yang (ETAS-ECM/XSF-CN)]]
> DF Nissan is a existing RTA-CAR 9 customer.
>
> For the upcoming new architecture ZCU on NXP S32K5, DF Nissan will need ETAS support for
>
> 1) OS porting to support S32K5/GHS for M7 core: current opportunity with budget applied
>  * CN/CCE feedback DF Nissan initially OS porting takes 3-4 months from PO without receive any complain from DF Nissan
>  * considering needs/request from NXP for early porting, CNHub could support providing an alpha porting in Jan which is happy for NXP. [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] 
>
> 2) M&S upgrading to RTA-CAR 12.x (latest) in year 2026 with budget to be applying from 2026Q1
>
> 3) TSN:
>  * a new topic where no concrete requirement now.
>  * DF/Nissan is discussing with CNHub CCE for a PoC to validate and derive BSW level TSN requirement during about 2026Q2

-------

> [!note]+ 2025-11-26 10:31 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> Here is the mail from NXP:
> {quote}HI Darren,
>
> as just discussed per phone: our common friends in China are fretting about having RTA on K5 very soon (end of January).
>
> (Actually a very good news, right?)
>
> This was one of the reasons we internally pushed to have someone flying into Stuttgart to help accelerating the partage.
>
> George feedback (this morning) is that things are going smoothly, so we don’t need to fly in nobody.
>
> Great news 😊
>
> This means that you will have RTA on the K5 *{*}very{*}* soon, right?
>
> Till when?
>
> Additionally I wonder: your China colleagues seems very relaxed about the DF-Nissan request, while our colleagues are under pressure (they asked Carlos, Jahanzeb and myself to support you to accelerate the portage).
>
> But it sounds awkward that DF-Nissan is putting more stress on us to have RTA on the K5, then on ETAS… are there things we are possibly not aware of?
>
> Please let us know your opinion, once you have sync’d with your colleagues.
>
> After our call this morning, I am positive that ETAS will be able to deliver RTA on the K5 to Nissan in a (Chinese) “timely manner”, but I will leave you to comment.
>
> Thanks & cheers
>
> **Jonathan Siegel**
>
> He / Him / His
>
> Software Product Manager
>
> Business Line Automotive Embedded Systems
>
> NXP Semiconductors Germany GmbH
>
> Schatzbogen 7
>
> 81829 München, Germany
>
> Phone: +49(0)171-6933421
>
> Email: [Jonathan.siegel@nxp.com](mailto:Jonathan.siegel@nxp.com)
> {quote}

-------

> [!note]+ 2025-11-26 10:21 · [[TAN_Yang_(ETAS-ECMXSF-CN)|TAN Yang (ETAS-ECM/XSF-CN)]]
> Hi [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] , ongoing clarifying the background.

-------

> [!note]+ 2025-11-26 09:31 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> [[TAN_Yang_(ETAS-ECMXSF-CN)|TAN Yang (ETAS-ECM/XSF-CN)]] / [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] - NXP have just called and this seem like it is real business for them and they are also pushing ETAS forward as their preferred  AUTOSAR stack supplier on the S32K5. Can you update this ticket with the status as we see that please? 
>
> Apparently someone in China have told DongFeng that the port will be 3 months and the really need something "January". Assuming they can live with GHS then we could actually get them a first alpha this week.

-------

> [!note]+ 2025-10-31 14:58 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> [[TAN_Yang_(ETAS-ECMXSF-CN)|TAN Yang (ETAS-ECM/XSF-CN)]] - can you have a sniff about and see if there is busienss for us here pelase? It was a lead from the NXP team in the EU. [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]  pinging you FYI in case you've heard anything here

-------

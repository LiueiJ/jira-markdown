---
jira_key: RH-12443
jira_url: "https://rtahotline.etas.com/jira/browse/RH-12443"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Medium
project: RH
assignee: marc.kaiser2@etas.com
reporter: sisi.tao@bosch.com
tags: []
components: [Generic-Importers]
fix-versions: []
epic: null
parent: null
created: "2025-02-27T04:33:27.000+0100"
updated: "2026-03-08T08:36:38.000+0100"
synced-at: "2026-09-08T01:46:06.261Z"
jira-orphaned: false
profile: Cariad
---

# RH-12443 [Cariad][ConfGen] CanIfRxPduDataLength is not generated for UserDefinedIPdu

> [!jira] Closed · Medium · [[Marc_Kaiser|Marc Kaiser]] · 更新于 2026-03-08T08:36:38.000+0100
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-12443)

> 标签：#jira/comp/generic-importers

## 描述

Dear hotline colleague, 

I’m using  **RTA-CAR 12.6.0pr1** BSW Confgen to generate  **UserDefinedIPdu** for ComStack  **CDD** module. 

As you can see in following screenshot,  **CanIfRxPduDataLength** is not generated for this pdu, even though it’s described in system extract. Other configuration like CDD module, PduRRoutingPath can all be generated. 

Could you help me? Thank you very much. 

![[RH-12443-image001.png]] 

 

  **Sisi TAO** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 

 M +86 133 81555197

 [Sisi.TAO@bosch.com!mail_small.gif!](mailto:Sisi.TAO@bosch.com) 

 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN

 333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

 &#91;www.etas.com|www.etas.com&#93;   ** 

 

 ETAS – Empowering Tomorrow’s Automotive Software**

## 关联

- mentions: [[RH-12489 [CONFGEN] Analysis on CanIfRxPduDataLength]]
- is mentioned in: [[RH-13043 [CNMS][ECARX] CanIfRxPduDataLength is not generated for the UserDefinedPdu]]

## 评论

> [!note]+ 2025-03-06 08:07 · [[Marc_Kaiser|Marc Kaiser]]
> User finding by [[Sisi_TAO|Sisi TAO]]  is correct. GI is buggy by not importing PduLength for UserDefinedPdu.
>
> Further handling is tracked by https://rtahotline.etas.com/jira/browse/RH-12489

-------

> [!note]+ 2025-02-27 10:08 · [[Huw_Christianson|Huw Christianson]]
> Hi [[Marc_Kaiser|Marc Kaiser]],
>
> Thanks for looking into this. let me know if you need any support from L2 and I will be happy to help.
>
> Huw

-------

> [!note]+ 2025-02-27 09:40 · [[Marc_Kaiser|Marc Kaiser]]
> Look what I found in the code:
>
> ![[RH-12443-image-2025-02-27-09-39-36-124.png]]
>
> This is why it will not import it for UserDefinedPdus. I must do more research if the argument in the comment makes sense:
>
>           /*
>            * For UserDefined-Pdus or UserDefined-I-Pdus the CanIfTxPduDlc cannot be set
>            * per definition, as it cannot be decided here if Pdu is of type TP
>            * (CanIfTxPduDlc = 0) or of type IF (CanIfTxPduDlc = frameLength) Please don't
>            * remove that line, as it is then handled in else part which is wrong
>            */
>
> It would be very easy to change ithe code so that it would import that parameter for UserDefinedPdus aswell. But the comment makes it seem its not done on purpose. I must verify if the logic is correct.

-------

> [!note]+ 2025-02-27 09:22 · [[Sisi_TAO|Sisi TAO]]
> Attached TWO arxmls are System Extract to reproduce the issue
> [^SOMEIP_Config.arxml] [^DBC_SysDesc.arxml]

-------

> [!note]+ 2025-02-27 08:41 · [[Huw_Christianson|Huw Christianson]]
> hi [[Sisi_TAO|Sisi TAO]],
>
> Could you attach the project so I can take a look?
> Also, did this start when you changed to 12.6.0PR1 or have you noticed it previously?
>
> Thanks,
> Huw

-------

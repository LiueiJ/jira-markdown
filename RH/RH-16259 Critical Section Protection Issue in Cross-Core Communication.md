---
jira_key: RH-16259
jira_url: "https://rtahotline.etas.com/jira/browse/RH-16259"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Critical
project: RH
assignee: "[[Dong_LIU|Dong LIU]]"
reporter: "[[Dong_LIU|Dong LIU]]"
tags: [jira/comp/communication-comservices]
fix-versions: []
epic: null
parent: null
created: "2026-06-04T10:18:43.000+0200"
updated: "2026-07-04T11:39:18.000+0200"
synced-at: "2026-09-10T03:48:22.681Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Hi, 

Regarding cross-core communication, Cariad has some issues with critical section protection, using RTACAR version RTA-CAR 12.11.0VCTCESR1pr1. 

Problem description:  

The customer’s project uses CAN, LIN, and Ethernet communication. CAN communication runs on core0, LIN communication runs on core1, and Ethernet communication runs on core2. Taking CAN and LIN communication as an example, the customer has CAN communication routing (CanIf->PduR->CanIf), as well as routing between CAN and LIN (CanIf->PduR->LinIf). The internal CAN routing is intra-core, while CAN-to-LIN routing is cross-core. For intra-core routing, the customer wants to use interrupt protection, and for cross-core routing, the customer wants to use a spinlock.  

Note: The customer does not want to use the XcoreCdd feature, as they think XcoreCdd introduces a 1 ms periodic task and increases project complexity. 

In the PduR routing function shown below, there is only one critical section protection function, so it is not possible to simultaneously implement intra-core interrupt protection and spinlock. 

![[RH-16259-image001.png]] 

Customer requirements:  

1. In this routing function, how can both interrupt protection and spinlock be implemented?  

2. Or are there any other solutions that can meet the customer’s requirements? 

Thank you ! 

Best regards,

 

  **Dong LIU** 

 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China (ETAS-ECM/XSF-CN)

 Bosch (China) Investment Ltd. | 333 Fuquan (N.) Road | Shanghai 200335 |  P.R. CHINA 

 [Dong.LIU5@etas.com!mail_small.gif!](mailto:Dong.LIU5@etas.com)

## 评论

> [!note]+ 2026-07-04 11:39 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2026-06-19 18:50 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically moved to Solution Proposed.

-------

> [!note]+ 2026-06-05 13:05 · [[Rushali_Parate|Rushali Parate]]
> It seems there are two different routing paths where the source PDU reference differs. In this case, the PDU IDs will also be different.
>
> If the project is not using RTE-generated SchM locks, the ID can be passed as a parameter to the lock function, changing:
>
> `SchM_Enter_PduR_LockIFGatewayTx();`
>
> to:
>
> `SchM_Enter_PduR_LockIFGatewayTx(id);`
>
> This way, spinlock or interrupt protection can be implemented selectively based on the specific ID.

-------

> [!note]+ 2026-06-05 11:05 · [[Dong_LIU|Dong LIU]]
> Currently, we have two solutions in mind.
>
> solutions 1:
>
> Using XcoreCdd, for same-core communication, it goes CanIf -> PduR -> CanIf with interrupt protection; for cross-core communication, it goes CanIf -> PduR -> LinIf via XcoreCdd.
>
> ![[RH-16259-image-2026-06-05-16-59-47-333.png]]![[RH-16259-image-2026-06-05-17-00-19-085.png]]
>
> solutions 2:
>
> Using User-defined Cdd Module, for same-core communication, it goes CanIf -> PduR -> CanIf with interrupt protection; for cross-core communication, it goes CanIf -> PduR -> LinIf via User-defined User-defined Cdd Module.
>
> ![[RH-16259-image-2026-06-05-17-02-39-138.png]]![[RH-16259-image-2026-06-05-17-03-28-825.png]]
>
> Please help us evaluate the feasibility of these two solutions. Since the customer does not want to use XcoreCdd, do you have any better solutions?
>
> thank you!

-------

> [!note]+ 2026-06-05 06:34 · [[Dong_LIU|Dong LIU]]
> [[Mohammed_Sameer_Gundloor|Mohammed Sameer Gundloor]] [[Phong_Tang_Dieu|Phong Tang Dieu]] just analyze it specifically for this use case. 
> Both the same-core routing path CanIf -> PduR -> CanIf and the cross-core routing path CanIf -> PduR -> LinIf exist simultaneously, and both of them use PduR_GF_DDIF_FIFO_Transmit_Func for routing. thank you!

-------

> [!note]+ 2026-06-04 15:55 · [[Phong_Tang_Dieu|Phong Tang Dieu]]
> Hi [[Dong_LIU|Dong LIU]]
> Could you please clarify more details of customer's requirements based on the questions from Sameer?
>
> Thanks,

-------

> [!note]+ 2026-06-04 15:55 · [[Oliver_Taylor|Oliver Taylor]]
> note:
>
> {quote}
>  introduces a 1 ms periodic task and increases project complexity
> {quote}
>
> - "introduces a 1 ms periodic task" not if you use interrupt mode
> - "increases project complexity" yes absolutely, but this is unavoidable in multicore

-------

> [!note]+ 2026-06-04 15:44 · [[Mohammed_Sameer_Gundloor|Mohammed Sameer Gundloor]]
> Hello [[Phong_Tang_Dieu|Phong Tang Dieu]] 
>
> Just to clarify this particular function is called in the context of a Gateway and if the project is using a queue.
>
> Do you want us to analyze it specifically for this use case or is it in general sense covering other modules as well (i.e: COM, IPDUM)?
>
> I will check if we can enable interrupt protection (disable interrupts) and spinlock protection for this exclusive area.

-------

> [!note]+ 2026-06-04 14:55 · [[Phong_Tang_Dieu|Phong Tang Dieu]]
> Hi [[Mohammed_Sameer_Gundloor|Mohammed Sameer Gundloor]]
>
> Cariad want to apply multicores communication as in description but they don't want to use XcoreCdd. 
> Is there any possible solution for this requirement?
>
> Thanks, 

-------

> [!note]+ 2026-06-04 14:53 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi [[Mohammed_Sameer_Gundloor|Mohammed Sameer Gundloor]], this Communication-ComServices ticket requires an assignee. As the component lead for Communication-ComServices, please ensure that the 'Level 3 Assignee' field is set to the appropriate person that can handle this issue.

-------

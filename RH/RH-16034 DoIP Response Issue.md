---
jira_key: RH-16034
jira_url: "https://rtahotline.etas.com/jira/browse/RH-16034"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Critical
project: RH
assignee: Dong LIU
reporter: Dong LIU
tags: [jira/comp/communication-eth]
fix-versions: []
epic: null
parent: null
created: "2026-05-13T11:37:10.000+0200"
updated: "2026-05-26T08:17:01.000+0200"
synced-at: "2026-09-10T08:07:25.599Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Hi, 

Issue Background: 

The customer is using the pre-release version of RTA-CAR 12.11.0VCTCESR1pr1. During DoIP testing, they found that the ECU response was inconsistent with their expectation and would like the product team to confirm whether this is a bug. 

Issue Description: 

 The customer sent a DoIP message with the Payload Type parameter set to 1 and the Payload Length parameter set to 0, while the actual payload length was 1 byte, as shown in the figure below. 

![[RH-16034-image001.png]] 

The ECU replied with a positive response, and the extra payload byte was ignored, as shown in the figure. 

The customer expects the ECU to respond with a NACK and the NACK code should be 0x03. 

The customer would like to understand why the RTACAR logic returns a positive response in this scenario. Thank you! 

Best regards,

 

  **Dong LIU** 

 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China (ETAS-ECM/XSF-CN)

 Bosch (China) Investment Ltd. | 333 Fuquan (N.) Road | Shanghai 200335 |  P.R. CHINA 

 [Dong.LIU5@etas.com!mail_small.gif!](mailto:Dong.LIU5@etas.com)

## 评论

> [!note]+ 2026-05-26 08:06 · Dong LIU
> Sri Viswatej Raja Venkatesh ok, thank you

-------

> [!note]+ 2026-05-21 14:20 · Sri Viswatej Raja Venkatesh
> Hello Dong LIU,
> We have investigated the behavior observed in RTA-CAR 12.11.0VCTCESR1pr1. Please find our feedback as follows.
> The current behavior is fully compliant with the following AUTOSAR specification requirement:
> \[SWS_DoIP_00310]: If a UDP message contains more than one DoIP request, DoIP shall process and respond to the first DoIP request and discard the remaining requests.
> In the described scenario, the declared Payload Length in the generic header is 0. Therefore, the first complete DoIP message consists of exactly 8 bytes (the generic header alone, with zero payload bytes) — which is a valid and complete Vehicle Identification Request (Payload Type 0x0001 mandates a payload length of 0 per ISO 13400-2).
> The 1 extra byte present in the UDP datagram beyond the declared message boundary falls outside the scope of the first DoIP request. As per \[SWS_DoIP_00310], DoIP treats this residual data as a subsequent request — which is incomplete and therefore discarded. The ECU correctly responds to the first valid request with a Vehicle Identification Response.
>
> Regarding the Behavior of RTA-CAR 9.1.0
> The Software supports multiple DoIP requests in a single UDP message prior to the introduction of requirement SWS_DoIP_00310 (which in introduced in Diagnostic over IP AUTOSAR CP R21-11). The correction introduced in subsequent releases aligns the implementation with the AUTOSAR specification. The current behavior in RTA-CAR 12.11.0VCTCESR1pr1 represents the standards-correct behavior.
> The RTA-CAR 12.11.0VCTCESR1pr1 ECU response is correct and compliant. No product defect exists for this reported scenario. 
> Please do not hesitate to reach out if you require any further clarification.
> Best regards,
> Viswa

-------

> [!note]+ 2026-05-18 07:53 · Sobin Peter
> Joshua Cantwell could you please update the L3 assignee as well. the Automatic assignment isn't working somehow

-------

> [!note]+ 2026-05-13 18:08 · Sobin Peter
> Joshua Cantwell Dcm cannot check the validity of the DOIP message. This needs to be performed by DoIP module itself i believe. We need a DoIp team member to explain us what data will be reaching to Dcm (if it is supposed to be reaching Dcm). 

-------

> [!note]+ 2026-05-13 17:09 · JSM Service Bot
> Hi Raghuram Telagamsetti, this Diagnostic-Communication ticket requires an assignee. As the component lead for Diagnostic-Communication, please ensure the 'Level 3 Assignee' field is set the appropriate person that an handle this issue.

-------

> [!note]+ 2026-05-13 17:08 · Joshua Cantwell
> Good analysis by the customer, im moving to L3 to investigate and confirm the issue.

-------

---
jira_key: ARC-9667
jira_url: "https://jira.etas-dev.com/browse/ARC-9667"
server: etas
kind: motivation
type: Motivation
status: New
priority: ""
project: ARC
assignee: mas1yok
reporter: mas1yok
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2025-03-20T05:23:42.000+0000"
updated: "2026-07-02T13:04:15.000+0000"
synced-at: "2026-09-08T02:03:07.632Z"
jira-orphaned: true
profile: CN Motivation
---

# ARC-9667 HESAI Customized RTA-CAR for Xiaomi Spec

> [!jira] New ·  · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] · 更新于 2026-07-02T13:04:15.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-9667)

## 描述

**Scope of work as follows :** 

**DoIP Change Request :** 

1. DOIP as TCP Client shall support configurable periodically(e.g. 5ms periodic) to establish connection until connection succeed. E.g., after sent SYN, incase ECU not receive response or receive RST, DoIP shall still sending SYN with 5ms interval until connection established.
2. configurable periodically for retransmit is not TcpIpRetransmissionTimeout, but a separate retransmit parameter (multiple of Tcp_MF).
  a) this extended timer for retransmit for SYNC is only applicable for the Tcp socket for DoIP.
  b) this extended timer for retransmit for SYNC is mutual-exclusive with existing Tcp segment timers.

**EthTSyn Change Request**

- EthTSyn shall support GlobalTimeDomain to be configured with parameter EthTSynGlobalTimeDomainId from 0 – 31, without functional/feature change requests.
- ![[ARC-9667-image-2025-03-20-13-28-12-975.png]]

**Tcp Change Request**

DoIPLite: (background info: this is used in DoIP bootloader)

• ParameterDef/EcucValues:

▪ Tcp support a vendor specific timing parameter T_ConnectTcp

▪ timing parameter T_ConnectTcp can be pre-compile configured TRUE or FALSE

▪ an configurable timeout notification with notification type

1. callout function

2. C/S interface Functional：

▪ When to start the timer T_ConnectTcp: an software start (ECU code start/warm start) will automatically start the timer &#91;Hesai-2&#93;: agreed to take the alternative proposal that ETAS Recommendation: the timer T_ConnectTcp will be start automatically during Doip_OpenConneection between DoIP and Tcp, without providing an external interface that user has to take

Page 6 of 12

care during integration e.g. at an software start (ECU code start/warm start).

▪ Timer suspend/reload: no require

▪ Timer stop: stop timer T_ConnectTcp on successful Tcp connection

▪ Timer notification:

1. timeout: an timer timeout will call the callout function or C/S interface

2. successful Tcp connection: a successful Tcp Connection will call an callout function or C/S interface Functional (Dcm):

▪ S3Server: Provide an standardized interface API to start/stop S3Server

• For variable type/range of timer values for global timer

▪ min value: per MainFunction period

▪ max value: uint32

## 关联

- relates to: [[ARC-6914 Code generation customization over-ride support]]
- relates to: [[INSYNC-50 HESAI Customized RTA-CAR for Xiaomi Spec]]

## 评论

> [!note]+ 2025-04-08 06:36 · [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]
> Hello [[FENG_Tom_(ETAS-ECMXSF-CN)|FENG Tom (ETAS-ECM/XSF-CN)]] 
>
> To summarize:
>
> ARC-9669 --> shall be available in RTA-CAR 12.3.3 (is also available from RTA-CAR 12.7.0 on-wards)
>
> ARC-9668 --> we have missed the opportunity to bring it into 12.3.3 and 12.7.0.
>
> At this point it can only be planned to be incorporated into forward path (i.e. next RTA-CAR version 12.8.0)
>
>
>
> Please check the option indicated by [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] in comment #3, for Hesai.

-------

> [!note]+ 2025-04-08 05:57 · [[FENG_Tom_(ETAS-ECMXSF-CN)|FENG Tom (ETAS-ECM/XSF-CN)]]
> [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]] Thanks for your comments, I'll contact customer and set up meeting inside. Before we have an alignment please don't close any ticket. Customer is very resist to accept more versions in short time. Also these needs comes from one project. It is not proper to implement [EthTSyn] in 12.7.0 while [Doip SoAD TCP] in 12.8.0

-------

> [!note]+ 2025-04-08 05:40 · [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]
> Hello [[FENG_Tom_(ETAS-ECMXSF-CN)|FENG Tom (ETAS-ECM/XSF-CN)]] 
>
> ARC-9668 --> Both DOIP and TCP changes seem to be an valuable extension in product and will be introduced.
>
> Capabilities are now available and linked to the need, tentatively planned for RTA-CAR 12.8.0 (will be confirmed post PIP next week)

-------

> [!note]+ 2025-04-01 05:29 · [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]
> Hello [[FENG_Tom_(ETAS-ECMXSF-CN)|FENG Tom (ETAS-ECM/XSF-CN)]] 
>
> The EthTSyn change is already available and hence should flow into RTA-CAR 12.3.3. [ALM-673451](https://rb-alm-28-p.de.bosch.com/ccm/web/projects/BSW%20Platform#action=com.ibm.team.workitem.viewWorkItem&id=673451)
>
> "[DoIP SoAd TCP] DoIP server as TCP client feature extension" --> we are currently evaluating this.
>
> But i guess we are too late to bring this into 12.3.3.
>
> [[Patil_Mahesh_(MSPJ-ETH-BSW)|Patil Mahesh (MS/PJ-ETH-BSW)]] when is the code freeze for RTA-CAR12.3.3 - could not find it in Docupedia [here](https://confluence.etas-dev.com/display/RTAC/RTA-CAR+12.3.x)

-------

> [!note]+ 2025-04-01 02:45 · [[FENG_Tom_(ETAS-ECMXSF-CN)|FENG Tom (ETAS-ECM/XSF-CN)]]
> Thanks Nandita, 
>
> how about "[DoIP SoAd TCP] DoIP server as TCP client feature extension" ?
>
> The motivation of this ticket is customer require to implement these  into RTA-12.3.3 ,  need overview to search for the feasibility to do this.

-------

> [!note]+ 2025-03-31 12:17 · [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]
> {color:#172b4d}The EthTSyn Change Request --> was an improvement we already considered in our product, will be available with RTA-CAR 12.7.0
> {color}
>  * ARC-6896 [TimeServices][EthTSyn][AR45 Mainpath] Pdelay calculation in lowest time domain id and pdelay response in all time domains, when configured
>
> {color:#172b4d}The DoIPLite Change Request --> also seems a relevant use-case and supporting it would add value (we have seen a similar requirement in the Volvo specs for DOIPLITE use-case)
> {color}
>  * {color:#172b4d}We are evaluating this to provide a product relevant solution.{color}

-------

> [!note]+ 2025-03-21 09:35 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> OK - so I interpret from [#4] that the functionality described in ARC-9668 and ARC-9669 itself is **not** in any product or planned to be in any product. We have a plan for making the interfacing nicer (via ARC-6914) but the current delivery for 12.3.3 sounds like it is going to be "SEF delivers the service field content as a custom plugin that has an engineering service QA3 release".

-------

> [!note]+ 2025-03-21 06:40 · [[Fargus_Alex_(MSETA)|Fargus Alex (MS/ETA)]]
> ARC-6914 is linked showing the override capability that will be available from RTA-CAR 12.8.0.

-------

> [!note]+ 2025-03-20 09:07 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> Customization on a product version that is already released is normally done by the engineering service release (i.e. the customer solution is RTA-CAR + the engineering service delivery). 
>
> It sounds like the customization already exists.
>
> To do "{_}Provide customized versions of RTA-CAR V12.3.2 tools package based on the requirements submitted by customers and keep updated and maintain in future."{_} then the I think the only thing that needs to be done is for whoever did the service engineering work (I think this was led by [[Vishak_Nikesh_(ETAS-ECMECP-PJM)|Vishak Nikesh (ETAS-ECM/ECP-PJM)]] ) to ensure that work is is QA'd for series. And then you'd just need to ship that extension.
>
> [[Fargus_Alex_(MSETA)|Fargus Alex (MS/ETA)]] you mentioned that in the forward path some of this has already been incorporated. Can you link the tickets covering that work here please?

-------

> [!note]+ 2025-03-20 08:10 · [[FENG_Tom_(ETAS-ECMXSF-CN)|FENG Tom (ETAS-ECM/XSF-CN)]]
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] Yes,here is the abstract from the SOW "Provide customized versions of RTA-CAR V12.3.2 tools package based on the requirements submitted by customers and keep updated and maintain in future."     "Early CodeDrop is not promised for production, but will be available for the release version incorporated into RTA-CAR release12.3.2."
>
> Based on the SOW, customized function into RTA CAR is customer's initial request.  For second issue, as I checked with Liujie, Yes！Domain control slave node  of Xiaomi will have this requirement. 

-------

> [!note]+ 2025-03-20 07:32 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> This looks like we have provided an engineering service solution to customize the product for Hesai. And the request seems to be "can we take this custom engineering and integrate that into a the next RTA-CAR 12.3.x patch version (which would currently be 12.3.3).
> [[FENG_Tom_(ETAS-ECMXSF-CN)|FENG Tom (ETAS-ECM/XSF-CN)]] - can you explain why the engineering service that has already been provided cannot be use by Hesai please? Do you know if this will be a common need for all Tier1s building supplying an ECU for Xiaomi? Thanks!
> [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]] - can you have a quick look at this and decide if this is something that could sensibly be taken in the product or whether this would violate anything standard in the product. Thanks!

-------

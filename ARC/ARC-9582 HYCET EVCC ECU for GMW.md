---
jira_key: ARC-9582
jira_url: "https://jira.etas-dev.com/browse/ARC-9582"
server: etas
kind: motivation
type: Motivation
status: New
priority: ""
project: ARC
assignee: ""
reporter: mas1yok
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2025-03-17T09:14:10.000+0000"
updated: "2025-09-04T00:09:13.000+0000"
synced-at: "2026-09-06T06:58:54.667Z"
jira-orphaned: false
---

# ARC-9582 HYCET EVCC ECU for GMW

> [!jira] New ·  ·  · 更新于 2025-09-04T00:09:13.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-9582)

## 描述

**Customer Project and SOP timeline** 

    For EVCC project, the major milestone from OEM (GWM)as below:

- ET:    Sep. 2025         --> the all functions shall be ready to test by OEM.
- PT:    Dec. 2025
- **SOP:  April, 2026**

**Customer Expectation :** 

Customer requires the below feature support in the product.  In discussion with [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]  we have understood the status of these feature support in RTA-CAR.  Customer wants to know the roadmap plans for the unsupported / partially supported feature set.

**S.NO.**
**Features**
**Status in RTA-CAR**

1
Support Ethernet IPV6, the path MTU discovery should be implemented in accordance with IETF RFC 1981, and should be implemented in accordance with IETF RFC 5722Supports the processing of overlapping IP fragments
Not Supported

2
Support Ethernet DHCPV6
Only DHCP client supported

3
Support the neighbor discovery protocol ND, should perform the neighbor discovery defined in IETF RFC 4861, should comply with the provisions of IETF RFC 4429, and allow assignment before completing duplicate address detectionIP address è Neighbor handling is fully supported. Router handing -> [Status in RTA-CAR: basic supported. Router based advanced feature not fully supported like Redirection , more than one prefix not supported
Supported

All the features which are required for Automotive use cases has been covered in the RTA CAR already.|

4
Support for  ICMPV6 and ICMPv6 specified in IETF RFC 4443 should be implemented
Basic functionality is supported

5
To support SLAAC, the configuration of the link-local IPv6 unicast address specified in IETF RFC 4291 and the interface ID of the link-local address of the entity should be supportedIPv6 as described in IETF RFC 4862 should be generated from its IEEE 48-bit MAC identifier as defined in IETF RFC 4291Automatic configuration of addresses.
Only IP defend is supported for MAC generated interface ID

6
Support IPV6 TCP and UDP transmission protocols
Fully supported

7
Support for TLS – Support for TLS_ECDH_ECDSA_WITH_AES_128_CBC_SHA256 and TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256.
TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256 - alone supported.

## 评论

> [!note]+ 2025-09-04 00:09 · [[Schran_Sven_(ETAS-ECMXPC-Fe3)|Schran Sven (ETAS-ECM/XPC-Fe3)]]
> [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] is there a spelling mistake in the issue Summary (G{*}{color:#de350b}MW{color}{*} instead of G{*}{color:#00875a}WM{color}{*})?

-------

> [!note]+ 2025-09-03 10:08 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> Customer Timeline is not feasible for implementing the features. This has been communicated to the customer. Since then there is no response from the customer. 
> From discussions with [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]'s it is feature worth incorporating into product later. No timeline committed. 
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] to decide on the status on the ticket. 

-------

> [!note]+ 2025-07-18 06:18 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> There is no committed business behind this motivation yet. And the customer is not really engaging.

-------

> [!note]+ 2025-06-06 08:39 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]  i have created the needs tickets as requested.  assigned the topic support for TLS_ECDH_ECDSA_WITH_AES_128_CBC_SHA256 to Sven . 

-------

> [!note]+ 2025-05-30 08:54 · [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]
> Hello [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]]
>
> Following your request, the Com-Stack experts conducted a quick analysis, and prepared a high-level T-shirt size estimate for the identified gaps.
>  * Support Ethernet IPV6, the path MTU discovery should be implemented in accordance with IETF RFC 1981, and should be implemented in accordance with IETF RFC 5722Supports the processing of overlapping IP fragments  {color:#ff8b00}Initial estimate (T-shirt size) : Large ( > 1 PI ){color}
>  * To support SLAAC, the configuration of the link-local IPv6 unicast address specified in IETF RFC 4291 and the interface ID of the link-local address of the entity should be supportedIPv6 as described in IETF RFC 4862 should be generated from its IEEE 48-bit MAC identifier as defined in IETF RFC 4291Automatic configuration of addresses. {color:#ff8b00}Initial estimate (T-shirt size) : Large ( > 1 PI ){color}
>  * Support for TLS – Support for TLS_ECDH_ECDSA_WITH_AES_128_CBC_SHA256 and TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256. {color:#ff8b00}Initial estimate (T-shirt size) : Medium ( < 1 PI ){color}
>
> As evident from above the gaps require considerable effort.
>
> Given our current commitments for PI02.2025 it would be challenging to take up these activities immediately without impacting our existing customer priorities.
>
> Unless there is a clear directive to re-prioritize, including alignment from the PFHs, it would be best to consider these activities for PI03.2025. Even in that case, achieving full series qualification by September remains highly ambitious.
>
> That said, we remain committed to supporting this project and ensuring customer satisfaction.
>
> To move forward meaningfully, I would propose an incremental delivery approach.
>
> If the initiative is confirmed, it would be helpful to organize deep-dive technical discussions with the customer to better understand the use cases and prioritize the gaps. Based on that, we can define a phased roadmap aligned with realistic timelines.
>
> We await your confirmation and direction to initiate detailed evaluation and planning.

-------

> [!note]+ 2025-05-27 07:02 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]]  could you please clarify few things to help progress this topic.
>  # When you say, ‘{_}customer require all feature are ready before September,2025{_}’.
>  # What is this timeline referring to ? Is this an SOP timeline ?  or a timeline to start their Project development ?
>  # We can support all the unsupported / partially supported features related to IPV6DHCP needed for their ECU project if we understand the scope and timeline clearly. It will be difficult if we say, ‘We must have all features ready only then we can get the project’.
>  # What is the business value – in terms of revenue ? ( roughly )
>  # Are we in the acquisition phase for this customer project ?  or just trying to sell RTA-CAR licenses based on the feature support ?
>  # If we are in acquisition,
>  ## Is this a Single ECU project ?
>  ## What is the target Hardware for this Customer project ?
>
> [@Nandita Prasad (MS/EBD-ETAS)](mailto:Nandita.Prasad@etas.com) : Is it possible to estimate how many of the unsupported / partially supported features can be completed by September 2025 ? ( Even if it is in preview status ) .

-------

> [!note]+ 2025-05-26 10:28 · [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]
> 1. Support Ethernet IPV6, the path MTU discovery should be implemented in accordance with IETF RFC 1981, and should be implemented in accordance with IETF RFC 5722Supports the processing of overlapping IP fragments -{*}-> Not Supported{*}
>  # Support Ethernet DHCPV6 **--> Only DHCP client supported**
>  # Support the neighbor discovery protocol ND, should perform the neighbor discovery defined in IETF RFC 4861, should comply with the provisions of IETF RFC 4429, and allow assignment before completing duplicate address detectionIP address è Neighbor handling is fully supported. Router handing **-> basic feature supported. Router based advanced feature not fully supported like Redirection , more than one prefix not supported. I would say 60 % supported.**
>  # Support for  ICMPV6 and ICMPv6 specified in IETF RFC 4443 should be implemented. **--> Basic functionality is supported.**
>  # To support SLAAC, the configuration of the link-local IPv6 unicast address specified in IETF RFC 4291 and the interface ID of the link-local address of the entity should be supportedIPv6 as described in IETF RFC 4862 should be generated from its IEEE 48-bit MAC identifier as defined in IETF RFC 4291Automatic configuration of addresses. **--> only IP defend is supported for MAC generated interface ID.**
>  # Support IPV6 TCP and UDP transmission protocols. **--> Supported**
>  # Support for TLS – Support for TLS_ECDH_ECDSA_WITH_AES_128_CBC_SHA256 and TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256. **--> TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256 alone supported.**
>
>
>
> **From a technical feasibility perspective, we can certainly incorporate the missing features into our product , however, our first step should be to thoroughly understand the customer’s use case.**
>
> **While we can adopt an incremental delivery approach, a concrete plan can only be defined once we have clear priorities and confirmation from the customer.**
> **Additionally, our product roadmap already includes pre-planned activities, so re-prioritizing these features will require further alignment.**

-------

> [!note]+ 2025-03-18 06:38 · [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]]
> customer feedback, according project timeline,
>
> customer requrie all feature are ready before September,2025.

-------

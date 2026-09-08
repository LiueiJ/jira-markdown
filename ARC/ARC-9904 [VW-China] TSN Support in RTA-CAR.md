---
jira_key: ARC-9904
jira_url: "https://jira.etas-dev.com/browse/ARC-9904"
server: etas
kind: motivation
type: Need (Subtask)
status: Analyzed
priority: Medium
project: ARC
assignee: npr5kor
reporter: mas1yok
tags: [CEA2.0, COM, NETCOM]
components: []
fix-versions: []
epic: null
parent: "[[ARC-9902 VCTC : VW CEA2.0 (CDCU,LDCU,RDCU & RearDCU)]]"
created: "2025-03-28T05:27:33.000+0000"
updated: "2026-01-21T04:56:53.000+0000"
synced-at: "2026-09-08T01:46:40.034Z"
jira-orphaned: false
profile: CEA2.0 Needs
---

# ARC-9904 [VW-China] TSN Support in RTA-CAR

> [!jira] Analyzed · Medium · [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]] · 更新于 2026-01-21T04:56:53.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-9904)

> 标签：#jira/label/cea20 #jira/label/com #jira/label/netcom

## 描述

VW CEA 2.0 Requires the following TSN standards to be supported in RTA-CAR 

- **TSN**: Support for the following
- 
  
  
  **Std 802.1Qav**
  IEEE Standard for Local and Metropolitan Area Networks — Virtual Bridged Local Area Networks – Amendment 12: Forwarding and Queueing Enhancements for Time-Sensitive Streams, which specifies the Credit Based Shaper. *(It is part of IEEE Std 802.1Q-2018.)*
  
  
  

**Std 802.1AS-2020**
Timing and Synchronization for Time-Sensitive Applications
yes
 

- 802.1p VLAN TAG Priority

## 关联

- relates to: [[ARC-10588 IEEE1722-TP extension for time synchronous communication]]
- relates to: [[ARC-7882 [COM] Evaluate Time Sensitive Networking]]
- is refined by: [[ARCANA-718 Analysis of CONC_710: Deterministic Communication with TSN]]
- satisfies: [[ARC-9902 VCTC : VW CEA2.0 (CDCU,LDCU,RDCU & RearDCU)]]
- is satisfied by: [[ARC-8704 IEEE1722 Audio Streaming with presentation time]]
- is satisfied by: [[ARC-13578 IEEE1722 distribution of a generated clock rate of media clock]]
- is satisfied by: [[ARC-13579 [COM][IEEE1722] Video Streaming with presentation time]]
- is satisfied by: [[ARC-13580 [COM][TSN] Fallback virtual local time according to IEEE802.1AS 2020]]
- is satisfied by: [[ARC-13581 [COM][TSN] Neigbor rate ratio according to IEEE802.1AS 2020]]
- is satisfied by: [[ARC-13576 IEEE 802.1AS-2020 Configuration Alignment in TimeServices]]
- is satisfied by: [[ARC-2449 Hardware clock support for Precision Time Protocol (PTP) ]]

## 评论

> [!note]+ 2025-05-13 08:25 · [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]
> VW TSN POC requirement [^RFQ_General Purchasing_TSN_DDS_update0213(1)(1).pdf]

-------

> [!note]+ 2025-04-14 05:06 · [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]
> Additionally ,
> We have conducted a preliminary gap analysis of the BSW stack in relation to various IEEE standards within the TSN context.
>
> [^TSN_IEEEStd_Support_overview.xlsx]
>
> Given the breadth of the TSN and IEEE specifications, achieving complete standard coverage within our product may not be feasible in one shot.
>
> Therefore, our gap coverage will be guided primarily by known customer use cases.
>
> Next steps at COM-RT:
>
> As an initial step, we have highlighted standards and use cases already requested by customers such as Xiaomi and VW China.
>
> Our approach will be to first assess the gaps in coverage where we have received specific customer interest. (Marked in Green in the excel)
>
> This includes evaluating the relevance and T-Shirt size effort required for implementation. Addressed with - ARC-7882
>
> Based on this assessment, we will prioritize the top gaps and consider their inclusion in the upcoming product roadmap.

-------

> [!note]+ 2025-04-08 09:10 · [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]
> Updated [^Next EEA BSW Modules Required for Ring network - Updated .xlsx] based on current capabilities in RTA-BSW EthStack

-------

> [!note]+ 2025-04-08 09:10 · [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]
> Based on the feedback from [[Scindia_Subash_(ETAS-ECMBUD)|Scindia Subash (ETAS-ECM/BUD)]] (voice of customer - Xiaomi) captured here
>
> [^Next EEA BSW Modules Required for Ring network.xlsx]

-------

> [!note]+ 2025-04-07 08:29 · [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]
> Hello [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] 
>
> As discussed could you please check with the customer on specific use cases to be supported.
>
> The standards are quite vast and we may not be able to support them 100%. \Having a clear understanding of the customer use case would help to narrow down scope and work on it on priority.
>
>
>
> Currently:
>
> Std 802.1AS --> Supported.
>
> Std 802.1Qav --> Partly supported - HW dependent feature, in BSW we support Rx queues in EthStack.
>
> Std 802.1p VLAN TAG Priority -->Ethstack ULs supports VLAN Tag and prioritization, Eth Driver needs to also support it.

-------

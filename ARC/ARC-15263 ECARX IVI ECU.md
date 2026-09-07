---
jira_key: ARC-15263
jira_url: "https://jira.etas-dev.com/browse/ARC-15263"
server: etas
kind: motivation
type: Motivation
status: New
priority: ""
project: ARC
assignee: but9fe
reporter: tan9sgh
tags: [os_port_required]
components: []
fix-versions: []
epic: null
parent: null
created: "2026-03-11T08:37:33.000+0000"
updated: "2026-09-03T15:59:14.000+0000"
synced-at: "2026-09-06T06:58:54.667Z"
jira-orphaned: true
---

# ARC-15263 ECARX IVI ECU

> [!jira] New ·  · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] · 更新于 2026-09-03T15:59:14.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-15263)

> 标签：#jira/label/os_port_required

## 描述

## **SOP timeline : 09.2026**

**Expected Feature complete : 09.2026**

Business **Scope** :  ETAS shall provide a RTA-CAR with DoIP Client solution fit for EcarX IVI ECU.

Customer : EcarX

ECU: IVI ECU as Edge node

- Mcu: SemiDrive E36xx with GHS

**Status of SoW**: finalizing after bidding.

**Price**: bidding discounted from 240 kEUR to 137 kEUR from bidding with Elektrobit (waiting for LOI)

**Motivations**

- Realizing the DoIP Client+DoIP Server solution will enable RTA-CAR for Xiaomi / Geely CGW ECUs where edge ndoe has sub-network Ethernet nodes.
- (add during bidding) Integrate EthSwt Realtek RTL9071CP

**Needs for RTA-CAR by SOP (2026.09) for Hongqi project:** 

1) DoIP shall support both DoIP Server and DoIP Client in same ECU configuration with DoIP Client to be able to initiate Routing Activation with activation line control on sub-network ECUs.

![[ARC-15263-image-2026-03-11-16-37-26-097.png]]

**Needs for RTA-CAR by Q4/2026 while Hongqi project do not need EthSwt:** 

2) Integrate EthSwt Realtek RTL9071CP into RTA-CAR

---
jira_key: ARC-13421
jira_url: "https://jira.etas-dev.com/browse/ARC-13421"
server: etas
kind: motivation
type: Motivation
status: New
priority: ""
project: ARC
assignee: mas1yok
reporter: but9fe
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2025-10-17T09:11:13.000+0000"
updated: "2026-06-19T09:33:15.000+0000"
synced-at: "2026-09-08T02:03:07.632Z"
jira-orphaned: true
profile: CN Motivation
---

# ARC-13421 DHU Central Gateway

> [!jira] New ·  · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] · 更新于 2026-06-19T09:33:15.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-13421)

## 描述

**ECU Description**

Tier1 Name
DHU

OEM Name (if different)
-

Purpose
Central Gateway

Gateway routes (known to date) ETH-CAN, ETH-LIN, TpGateway, OTA

**EE Architecture Reference**

TBD

**Network Connectivity**

Bus
Required
Notes

CAN
Yes
-

LIN
Yes
-

Ethernet
Yes
-

FlexRay
No
-

**Safety** 

Unknown

**Security**

HSM support required

**Timeline**

Project Stage
Date

RfQ
Unknown

SoD
Unknown

B-sample
Unknown

C-sample
Unknown

SoP
Unknown

**Production**

Production Volume (Total over lifecycle): unknown

**3rd party SW**

Compiler Vendor
-

Compiler Version
-

Debugger
-

MCAL
-

OEM Specific ASWr/BSW
-

**Customer Stakeholders**

Name
Role

-
-

## 评论

> [!note]+ 2025-10-17 09:38 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> Via [[Weigl_Sandra_(ETAS-ECMXPC-Fe3)|Weigl Sandra (ETAS-ECM/XPC-Fe3)]]:
> {quote}I learned that we have another "RFQ" from ECARX for a SemiDrive Chip. With expected full function delivery in January. Can this be supported directly by RTA-CAR, or do we also need to negotiated here regard to the timeline?
> Background: we have a first POC on this Semidrive chip (or the version of this chip from a year ago). for CycurHSM SDK. But this is one year old. And some important features that are requested by ECARX are not supported. And we will not be able to reach the January timeline.
> {quote}

-------

> [!note]+ 2025-10-17 09:22 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> As this is a Geely project the OEM Platform might be either:
>  * GEE2.5 - see previous analysis is in ARCANA-1082 that's in the context of the Ampere project (ARC-12903)
>  * GEEA3.0 - which was investigated for the Geely ARC-5439

-------

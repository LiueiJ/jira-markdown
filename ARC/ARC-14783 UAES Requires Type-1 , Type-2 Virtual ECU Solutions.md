---
jira_key: ARC-14783
jira_url: "https://jira.etas-dev.com/browse/ARC-14783"
server: etas
kind: motivation
type: Motivation
status: New
priority: ""
project: ARC
assignee: "[[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]"
reporter: "[[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]"
tags: []
fix-versions: []
epic: null
parent: null
created: "2026-02-03T08:04:29.000+0000"
updated: "2026-06-16T14:21:16.000+0000"
synced-at: "2026-09-11T02:40:23.945Z"
jira-orphaned: false
profile: CN Motivation
---

## 描述

**UAES Mandatory requirements** :

1. Type-1 , Type-2 Virtual ECU solution to develop their Atomic services used in many Zone controller projects. 

2. Type-3 VECU is nice to have not mandatory .

Atomic Services -> is primarily in the ASW layer.

Most of the cases want to test ONLY Atomic services ( above RTE ) . No BSW need to be integrated. If there is BSW that can be integrated ( Type-3 VECU) - it will be useful for UAES.

Currently proposed Virtualization solutions :

1. VECU Builder 

2. VRTA inside RTA-CAR

Customer wants to try VRTA solutions inside RTA-CAR .

**Virtualization Solution** : We need to align on the strategy

**Migration Support :** 

**Note : Customer is currently using Vector Davinci** . If they like our solutions, then their projects need migration support.

[[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] we need some document / guide to aid customers migrate from competitor's tools to ETAS RTA-CAR. We need someone looking into it.

**Ideal** : We want our tool to support Vector & EB projects migration to RTA-CAR 

**Min**: A user guide to o aid customers migrate from competitor's tools to ETAS RTA-CAR

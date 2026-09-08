---
jira_key: ARC-14814
jira_url: "https://jira.etas-dev.com/browse/ARC-14814"
server: etas
kind: motivation
type: Motivation
status: New
priority: ""
project: ARC
assignee: but9fe
reporter: mas1yok
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2026-02-05T05:38:27.000+0000"
updated: "2026-06-19T08:20:56.000+0000"
synced-at: "2026-09-08T02:03:07.632Z"
jira-orphaned: true
profile: CN Motivation
---

# ARC-14814 HCT Mitsubishi ADAS ECU requiring DIAG Services

> [!jira] New ·  · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] · 更新于 2026-06-19T08:20:56.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-14814)

## 描述

Requested BIP from ETCN team . 

**Primary focus is** : Diagnostics - Incl. KWP200 protocol. , CanTp

**Customer expectation:**

1. Configure **CanTp**, **Dcm**, and **Dem** for KWP2000 compatibility.
2. Implement session management, reset handling, and fault handling per Mitsubishi specifications.
3. Define LID-based data/IO services and ensure seamless routing.
4. Configure security access logic and bus communication controls.

## 关联

- relates to: [[ARC-15183 KWP2000: Mitsubishi Motor (MMC) DIAG Specs]]

## 评论

> [!note]+ 2026-02-11 13:35 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> Since we dont support the KWP in RTA-CAR and there are no plans to support it in the product, I have requested KWP2000 protocol support as an Engineering service from Service Field team [[Feschenko_Stanislaw_(ETAS-ECMXPC-Fe5)|Feschenko Stanislaw (ETAS-ECM/XPC-Fe5)]] . 
>
> [[Jain_Vihitha_(MSEMS-ETAS)|Jain Vihitha (MS/EMS-ETAS)]] [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]  [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] fyi. 

-------

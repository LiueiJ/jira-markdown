---
jira_key: RTAXIP-3377
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-3377"
server: etas
kind: motivation
type: Change Request
status: Blocked
priority: Medium
project: RTAXIP
assignee: "[[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]"
reporter: "[[ZHANG_Cong_(ETAS-ECMXSF-CN)|ZHANG Cong (ETAS-ECM/XSF-CN)]]"
tags: [jira/label/rta-bip-uc]
fix-versions: [RTA-BIP-cdes-tc397tk-1211]
epic: null
parent: null
created: "2026-03-25T07:25:14.000+0000"
updated: "2026-08-10T06:36:11.000+0000"
synced-at: "2026-09-11T01:13:18.603Z"
jira-orphaned: false
profile: CNN
---

## 描述

## Summary

Improve BIP Exclusive Area implementation according to RTA-CAR recommendation

## Description

#RTA-BIP-UC

This need is a use case improvement for the current BIP project implementation.

The current implementation still contains obsolete usage of `rba_SchMAnalyzer` for Exclusive Area handling. This obsolete approach shall be removed and replaced with the recommended RTA-CAR method.

The objective is to clean up the current design, reduce legacy usage, and align the project implementation with the recommended RTA-CAR solution.

Expected outcome:

- Remove obsolete `rba_SchMAnalyzer` usage from the project.
- Rework the current Exclusive Area implementation to follow the recommended RTA-CAR approach.
- Keep the implementation maintainable and consistent with the current product direction.

Current status screenshots:

!761767_Pasted+image+20260325114158.png!

!761768_Pasted+image+20260325114233.png!

## 关联

- is satisfied by: [[RTAXIP-3950 [RTA-BIP-Improvement] Improve BIP Exclusive Area implementation according to RTA-CAR recommendation]]

## 评论

> [!note]+ 2026-05-07 08:20 · [[ZHANG_Cong_(ETAS-ECMXSF-CN)|ZHANG Cong (ETAS-ECM/XSF-CN)]]
> Hi [[Le_Hong_Nhung_(MSPJ-ETA-HN_MSETA-Hub-CN)|Le Hong Nhung (MS/PJ-ETA-HN MS/ETA-Hub-CN)]] , I didn't read it. So I didn't follow any approach, I tried by my experience :D

-------

> [!note]+ 2026-05-07 08:08 · [[Le_Hong_Nhung_(MSPJ-ETA-HN_MSETA-Hub-CN)|Le Hong Nhung (MS/PJ-ETA-HN MS/ETA-Hub-CN)]]
> Hi [[ZHANG_Cong_(ETAS-ECMXSF-CN)|ZHANG Cong (ETAS-ECM/XSF-CN)]]  I have a question related to this ticket that need you confirm. Do we follow **RTA-CAR approach** which mentions in **RTA-CAR Release Notes_12.9.0.pdf**  document , part 3.2.3.2 Exclusive Area Editor - Implementation Mechanism Assignment Analysis Qualification and 3.2.3.3 Exclusive Area Editor - Failure to Set OsSpinlockAccessingApplication to replace current approach.. Thank you
>
> ![[RTAXIP-3377-image-2026-05-07-15-06-00-527.png]]

-------

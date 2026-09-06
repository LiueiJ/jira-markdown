---
jira_key: RTAXIP-3880
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-3880"
server: etas
kind: motivation
type: Bug
status: Closed
priority: High
project: RTAXIP
assignee: dyn9hc
reporter: puy1hc
tags: [RTA-BIP-UC]
components: []
fix-versions: [RTA-BIP-cdes-tc397tk-1211, RTA-BIP-cdes-tc397tk-1290-r2.0]
epic: null
parent: null
created: "2026-07-13T02:29:13.000+0000"
updated: "2026-08-10T06:38:02.000+0000"
synced-at: "2026-09-06T06:57:27.567Z"
jira-orphaned: false
---

# RTAXIP-3880 [Internal Detect] Update CsSafety configuration for solve reported issue RH-15878

> [!jira] Closed · High · [[Nguyen_Hoang_Danh_(MSETA-Hub-CN)|Nguyen Hoang Danh (MS/ETA-Hub-CN)]] · 更新于 2026-08-10T06:38:02.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/RTAXIP-3880)

> 标签：#jira/label/rta-bip-uc

## 描述

**Context / Reference:**

- During integration and testing BIP, [[ZHANG_Cong_(ETAS-ECMXSF-CN)|ZHANG Cong (ETAS-ECM/XSF-CN)]]  and [[Nguyen_Minh_Tuan_(MSETA-Hub-CN)|Nguyen Minh Tuan (MS/ETA-Hub-CN)]] detected the issue with CsSafety and Spinlock (report in hotline [RH-15878](https://rtahotline.etas.com/jira/browse/RH-15878))
- This bug will cause random errorhook so that this error doesn't always happen in sometime/some projects
  **Description:**
- Root Cause: GetSpinlock is called by CsSafety context in Interrupt when Os is in idle state And OS doesn't allow this context
- Proposed Fix: Change CsSafety configuration which will call GetSpinlock in OsTask rather than Interrupt (contact [[Nguyen_Minh_Tuan_(MSETA-Hub-CN)|Nguyen Minh Tuan (MS/ETA-Hub-CN)]] for the solution which he applied for Ecarx project)
  **Verification Plan (How to prove it's fixed):**
- Let Discuss more due to it's not easy to reproduce
- Share Design change for review the solution
  **Acceptance Criteria:**
- The issue described in RH-15878 is no longer reproducible.
- No new regressions introduced

## 关联

- is informed by: [[RTAXIP-3872 [SemiDrive][E3620] Investigate and fix memory exception for Rips CSSafety]]
- is satisfied by: [[RTAXIP-3890 [Internal Detect] Update CsSafety configuration for solve reported issue RH-15878]]

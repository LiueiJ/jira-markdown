---
jira_key: RTAXIP-3992
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-3992"
server: etas
kind: motivation
type: Task
status: Open
priority: Medium
project: RTAXIP
assignee: ""
reporter: pka3hc
tags: [RTA-BIP-RH]
components: []
fix-versions: []
epic: null
parent: null
created: "2026-08-06T04:33:01.000+0000"
updated: "2026-08-06T04:33:01.000+0000"
synced-at: "2026-09-06T06:57:27.567Z"
jira-orphaned: false
---

# RTAXIP-3992 [RTA-BIP-RH] Check the resolution of RH-16680 -Intermittent failure to generate RIPS Cssafety source files in RTA-CAR 12.11.0

> [!jira] Open · Medium ·  · 更新于 2026-08-06T04:33:01.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/RTAXIP-3992)

> 标签：#jira/label/rta-bip-rh

## 描述

**Issue**: 

ECUExtract option to enable CSSafety RIPS doesn't work if generated on a fresh ECUExtract.

**How to test:**

1. Import the project.
2. Make sure no ECUExtract files exist. If exists, delete the files.
3. Generate EcuExtract

**Expected Behavior:**

1. FlatInstanceDescriptor "BswMSwcGenericRequest" should have RtePluginsProps generated which shall refer to CSSafety RIPS plugin.

**Current Behavior:**

1. FlatInstanceDescriptor "BswMSwcGenericRequest" is generated **without** RtePluginsProps.

 

**Solution**: This issue has been fixed in RTA-CAR 12.12.0, for workarounds in RTA-CAR 12.11.0, user can follow one of below:

- Explicitly invoke the **"Enable RIPS"** option, OR
- Re-run ECUExtract while retaining the existing ECUExtract files. The configuration will be generated as expected, OR
- Execute ECUExtract through ConfGen. Basically, running ECUExtract through CongGen fixes this issue.

## 关联

- is tracked by: [[RTAXIP-2678 [RTA-BIP] RTA-CAR Hotline issue list and tracking]]

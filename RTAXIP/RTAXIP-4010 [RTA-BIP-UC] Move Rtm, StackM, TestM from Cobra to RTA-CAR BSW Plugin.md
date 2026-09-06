---
jira_key: RTAXIP-4010
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-4010"
server: etas
kind: motivation
type: Story
status: Open
priority: Medium
project: RTAXIP
assignee: ""
reporter: aiu2sgh
tags: [RTA-BIP-UC]
components: []
fix-versions: []
epic: null
parent: null
created: "2026-08-09T08:18:04.000+0000"
updated: "2026-08-24T07:59:36.000+0000"
synced-at: "2026-09-06T06:57:27.567Z"
jira-orphaned: false
---

# RTAXIP-4010 [RTA-BIP-UC] Move Rtm, StackM, TestM from Cobra to RTA-CAR BSW Plugin

> [!jira] Open · Medium ·  · 更新于 2026-08-24T07:59:36.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/RTAXIP-4010)

> 标签：#jira/label/rta-bip-uc

## 描述

### **Description**

Currently, **RTM**, **StackM**, and **TstM** are maintained under the **Cobra** environment. To align with the RTA-CAR product architecture and simplify maintenance, these modules shall be migrated to the **RTA-CAR BSW convergence Plugin (from RTA-CAR 12.11)** framework.

The migration should ensure functional equivalence with the current implementation while enabling future development and maintenance within the RTA-CAR ecosystem.

### **Background**

- RTM, StackM, and TestM are currently integrated and maintained in Cobra.
- RTA-CAR BSW Plugin is the strategic platform for BSW-related extensions and integration.
- Maintaining the modules in Cobra increases maintenance effort and limits alignment with the current RTA-CAR architecture.

### **Scope**

- Analyze existing RTM, StackM, and TstM implementations in Cobra.
- Design the migration approach for RTA-CAR BSW Plugin.
- Port source code, configuration, and build integration.
- Validate compatibility with supported RTA-CAR versions.
- Update relevant documentation and integration guidelines.

### **Acceptance Criteria**

- Analyze the feasible with RTA-CAR convergence
- Document HOW to create CDD module with RTA-CAR
- Define steps and create follow-up tickets for migrating RTM, StackM, and TstM.

### **Benefits**

- Improved alignment with RTA-CAR architecture.
- Reduced maintenance effort across platforms.
- Easier integration for customer projects.
- Better supportability and future extensibility.

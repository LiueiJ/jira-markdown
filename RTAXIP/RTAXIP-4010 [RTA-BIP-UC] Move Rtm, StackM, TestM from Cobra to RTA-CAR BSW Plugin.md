---
jira_key: RTAXIP-4010
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-4010"
server: etas
kind: motivation
type: Story
status: In Progress
priority: Medium
project: RTAXIP
assignee: tuo8hc
reporter: aiu2sgh
tags: [RTA-BIP-UC]
components: []
fix-versions: []
epic: null
parent: null
created: "2026-08-09T08:18:04.000+0000"
updated: "2026-09-08T02:39:55.000+0000"
synced-at: "2026-09-08T05:48:25.775Z"
jira-orphaned: false
profile: CNN
---

# RTAXIP-4010 [RTA-BIP-UC] Move Rtm, StackM, TestM from Cobra to RTA-CAR BSW Plugin

> [!jira] In Progress · Medium · [[Truong_Duc_Thang_(MSETA-Hub-CN)|Truong Duc Thang (MS/ETA-Hub-CN)]] · 更新于 2026-09-08T02:39:55.000+0000
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

## 评论

> [!note]+ 2026-09-07 10:00 · [[Nguyen_Le_Thanh_Tu_(MSETA-Hub-CN)|Nguyen Le Thanh Tu (MS/ETA-Hub-CN)]]
> [[Truong_Duc_Thang_(MSETA-Hub-CN)|Truong Duc Thang (MS/ETA-Hub-CN)]]  Please support to take up the ticket. Thank you

-------

> [!note]+ 2026-09-07 09:56 · [[Nguyen_Le_Thanh_Tu_(MSETA-Hub-CN)|Nguyen Le Thanh Tu (MS/ETA-Hub-CN)]]
> At first approach, we should check the possibility of the strategy of building a new plugins.
>
>
>  # Install the environment
>  # Follow step 2.1 in [How to install RTA-CAR and using conan to migrate BSW module - lotusVN Team (Public) - Confluence (etas-dev.com)](https://confluence.etas-dev.com/spaces/RBVHSOFIA/pages/693534864/How+to+install+RTA-CAR+and+using+conan+to+migrate+BSW+module)
>  # Install path should be C:\ETAS
>  # For isolar_ab, install path should be as below
>
> ![[RTAXIP-4010-image-2026-09-07-16-57-59-714.png]]
>
>
>  # 
>  ## 
>  ### Gcc should be install as below:
>
>
>
> ![[RTAXIP-4010-image-2026-09-07-16-58-21-118.png]]
>
>
>  # 
>  ## Create token in [https://artifactory.etas-dev.com/ui/repos/tree/General/rtabsw-generic-main-local/Development/] and put the info in C:\Users\USER ID\.m2
>
> ![[RTAXIP-4010-image-2026-09-07-16-58-37-101.png]]
>  # 
>  ## Get the repo of rta-bsw: release/12.11.0.VCTCESR1pr6
>  ## Folow [How to build convergence plugin using python script - lotusVN Team (Public) - Confluence (etas-dev.com)](https://confluence.etas-dev.com/spaces/RBVHSOFIA/pages/731021783/How+to+build+convergence+plugin+using+python+script) to build the worked plugin of crypto
>
>  # After build environment is set, create the new plugin:
>  # Create a test plugin folder
>
> ![[RTAXIP-4010-image-2026-09-07-16-58-59-518.png]]
>  # 
>  ## Register the generate module
>
> ![[RTAXIP-4010-image-2026-09-07-16-59-05-229.png]]
>
>                    c. Trigger the build
>  # 
>  ## 
>  ### If the module is not recognized, build tool will notify that the tool cannot recognize the registered module
>  ### If the module has no action, build tool will notify process error
>
> ![[RTAXIP-4010-image-2026-09-07-16-59-44-173.png]]

-------

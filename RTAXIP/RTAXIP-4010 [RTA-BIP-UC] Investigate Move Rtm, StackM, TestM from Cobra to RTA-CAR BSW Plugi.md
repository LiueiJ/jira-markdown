---
jira_key: RTAXIP-4010
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-4010"
server: etas
kind: motivation
type: Story
status: In Progress
priority: Medium
project: RTAXIP
assignee: "[[Truong_Duc_Thang_(MSETA-Hub-CN)|Truong Duc Thang (MS/ETA-Hub-CN)]]"
reporter: "[[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]]"
tags: [jira/label/rta-bip-uc]
fix-versions: []
epic: null
parent: null
created: "2026-08-09T08:18:04.000+0000"
updated: "2026-09-10T09:36:14.000+0000"
synced-at: "2026-09-11T02:40:28.533Z"
jira-orphaned: false
profile: CNN
---

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

## 关联

- Is parent of:: [[RTAXIP-4144 [BIP] Create and implement Rtm convergence plugin]]
- Is parent of:: [[RTAXIP-4145 [BIP] Create and implement StackM convergence plugin]]
- Is parent of:: [[RTAXIP-4146 [BIP] Create and implement TstM convergence plugin]]

## 评论

> [!note]+ 2026-09-10 09:34 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]
> Thanks for your doc. I reviewed and no finding for now. Let start to migrate them

-------

> [!note]+ 2026-09-10 08:34 · [[Truong_Duc_Thang_(MSETA-Hub-CN)|Truong Duc Thang (MS/ETA-Hub-CN)]]
> Hi anh [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]] and [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]] 
>
> Please find the document for this ticket and kindly provide your feedback:
> [https://confluence.etas-dev.com/spaces/RBVHSOFIA/pages/758678807/Use+case+How+to+create+customized+BSW+package+as+a+convergence+plugin]
>
>
>
> As this is a PoC to evaluate the feasibility of using the Convergence feature for customized-BSW modules, the Java source code and templates in this PoC are intentionally kept minimal and simple.
>
> To make this solution suitable for official use in the BIP project, additional work will be required, including:
>  * Migrating the full logic from the existing Cobra Python implementation to Java.
>  * Verifying that the generated output
>  * Identifying and addressing potential issues (if have)
>
> These activities are planned to be addressed in the follow-up tickets listed below.
> https://jira.etas-dev.com/browse/RTAXIP-4144
>
> https://jira.etas-dev.com/browse/RTAXIP-4145
>
> https://jira.etas-dev.com/browse/RTAXIP-4146
>
> Thank you for your review!

-------

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

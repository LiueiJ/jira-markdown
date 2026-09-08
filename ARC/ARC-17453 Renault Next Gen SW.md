---
jira_key: ARC-17453
jira_url: "https://jira.etas-dev.com/browse/ARC-17453"
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
created: "2026-08-31T06:41:44.000+0000"
updated: "2026-09-03T16:12:35.000+0000"
synced-at: "2026-09-08T02:03:07.632Z"
jira-orphaned: false
profile: CN Motivation
---

# ARC-17453 Renault Next Gen SW

> [!jira] New ·  · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] · 更新于 2026-09-03T16:12:35.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-17453)

## 描述

**Renault China RFI:** Next-Generation Software Architecture

----**1. Background & Objectives**

In AUTOSAR multi-core software development, the primary objective is to achieve high software development flexibility and clear allocation of responsibilities across multiple vendors.

- **ECU Consolidation:** Reduce the overall number of physical ECUs by fully utilizing MCU computing capabilities.

- **Heterogeneous OS Support:** Allow different software partitions or Virtual Machines (VMs) to run different operating systems (*AUTOSAR Classic + non-AUTOSAR*).

- **Robust Isolation:** Ensure secure spatial and temporal isolation between different software partitions/VMs.

- **Lifecycle Independence:** Enable independent boot, power-down, fault management, and update capabilities per partition/VM.

- **Decoupled Development:** Enable independent development, integration, validation, and prototyping of features or legacy ECU scopes decoupled from the rest of the software stack.

### **2. Potential Technical Solutions**

Based on initial investigations, the following mechanisms are to be explored:

#### **2.1 CPFlex / Software Cluster**

- **Concept:** Distribute software clusters across different [teams/suppliers](https://teams.googleplex.com/suppliers):

- - *Host Cluster:* Developed and maintained by the AUTOSAR platform / BSW supplier.

- - *Application Clusters:* Distributed across functional application suppliers (e.g., VCU, Inverter, BMS, OBC).

- **Supplier Evaluation Scope:** Feasibility, limitations, required infrastructure, toolchain, integration mechanism, and production ECU impact.

#### **2.2 Hypervisor / Virtualization**

- **Concept:** Provide strong hardware-level virtualization/isolation between environments (supporting both AUTOSAR and non-AUTOSAR stacks).

- **Key Capabilities:**

- - Independent software environments & dedicated resource budgeting.

- - Independent reset and fault-handling behavior.

- - Enhanced security & functional safety (ASIL) isolation.

- **Supplier Evaluation Scope:** Feasibility, performance overhead/complexity, benefits, limitations, and automotive production readiness.

#### **2.3 Other Solutions & Hardware Recommendations**

- Supplier-proposed alternative architectures.

- Recommended target automotive MCU / SoC hardware platforms.

### **3. Research Expectations & Deliverables**

Deliverable Scope
Details & Focus Areas

**Solution Proposal & Comparison**
Propose preferred solution; compare CPFlex / Software Cluster vs. Hypervisor / Virtualization vs. alternative solutions.

**Architecture & Partitioning**
Define core/VM/cluster allocation, AUTOSAR BSW/RTE/ASW boundaries, IPC (inter-core/inter-cluster communication), resource budgeting, fault isolation/recovery, tracing/debugging, and configuration workflows.

**Proof of Concept (PoC)**
Demonstrate proposed concepts via a representative multi-core automotive ECU use case.

**SDLC Impact Analysis**
Assess end-to-end impact on development workflow, integration, validation, debugging, configuration management, release management, and OEM–Tier-1–Supplier collaboration.

## 评论

> [!note]+ 2026-09-03 10:25 · [[Baldini_Luca_(ETAS-ECMXPC-Yok2)|Baldini Luca (ETAS-ECM/XPC-Yok2)]]
> [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] To help you prepare the response, here is the context on our ongoing discussions and past architectural decisions with Renault/Ampere in Europe:
>
> **1. Current Commercial RFI (EU)**
>  * We have an ongoing RFI with Renault (started in January) primarily focused on commercial terms and supplier consolidation.
>
>  * There are at least four Chinese BSW suppliers participating in that RFI as well.
>
>  * While that RFI is commercial, your technical PoC RFI reflects the same underlying goal: consolidating multiple ECUs into fewer, more powerful controllers.
>
> **2. Past Discussions on Core RFI Topics**
>  * **Hypervisor / Virtualization:** Discussed during earlier RFIs, but we discouraged it due to overhead and complexity. They did not move forward with it at the time.
>
>  * **CPFlex / Clusterization:** Evaluated to enable parallel integration across teams. It was ultimately dropped because their engineering service partner (E2CAD) lacked the experience required to work with this approach.
>
>  * **Multiple Stacks vs. Single Large Multicore Stack:** We had extensive discussions on this trade-off. A single multicore stack was selected because:
>
>  ## *Integration complexity:* Running multiple independent stacks requires custom data synchronization and inter-stack communication strategies not defined in the standard AUTOSAR specification.
>
>  ## *Licensing costs:* Deploying multiple stack instances on the same ECU triggers additional production license fees (counted as separate projects).
>
>  * **Lessons Learned from Existing Projects**
>
>  ** **Architecture gaps:** Renault often tries to consolidate by "copy-pasting" existing SWCs rather than refactoring the software architecture, which quickly runs into integration bottlenecks.
>
>  ** **Resource consumption:** They frequently hit resource limits; for instance, on the PDC+ project, they had to consider upgrading to a larger microcontroller due to memory and CPU load.
>
> Let me know if you want to walk through any of these points in detail or align on the response strategy. We can set up a quick call.

-------

> [!note]+ 2026-08-31 06:55 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] [[Burn_Alexander_(ETAS-ECMXPC-Yok1)|Burn Alexander (ETAS-ECM/XPC-Yok1)]]  Renault China has shared their RFI .  We probably will pay a visit to Renault ( not decided on date yet ) to explore further on the POC. Renault's plans is evaluate the suppliers that can offer them the better and viable solution.
>
> we need to align on it. attached [^Renault next gen SW POC RFI.xlsx] document contains customers Q List
>
> [[Baldini_Luca_(ETAS-ECMXPC-Yok2)|Baldini Luca (ETAS-ECM/XPC-Yok2)]]  fyi. 

-------

---
jira_key: RH-16775
jira_url: "https://rtahotline.etas.com/jira/browse/RH-16775"
server: rtahotline
kind: hotline
type: Support
status: Waiting for Level 3
priority: High
project: RH
assignee: "[[Vo_Quang_Gia_Vinh_(MSETA-ARC-PF2)|Vinh Vo Quang Gia]]"
reporter: "[[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Phuong Nguyen Le]]"
tags: [jira/comp/aaa-analysis, jira/comp/fsqp, jira/label/makw, jira/label/vncnms]
fix-versions: []
epic: null
parent: null
created: "2026-07-28T05:30:12.000+0200"
updated: "2026-09-10T10:57:39.000+0200"
synced-at: "2026-09-11T01:13:17.157Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Hi [@Kust Oliver (ETAS-ECM/ESY3)!mail_small.gif!](mailto:Oliver.Kust@etas.com) 

As this issue is cross cutting concept and happening in every component, I’m reaching you to request the solution for this issue. 

 **Description:**

 We would like to suggest avoiding the use of  **static variables declared inside functions**. 

 **Problem:** 

I reviewed and list here some examples, I can’t share all finding but I think that many components have same issue. Can you help to check and align same practices for all component teams. 

- CANTP

![[RH-16775-image001.png]] 

- KeyM

![[RH-16775-image002.png]] 

![[RH-16775-image003.png]] 

- CRC:

![[RH-16775-image004.png]] 

- DCM

![[RH-16775-image005.png]] 

![[RH-16775-image006.png]] 

… 

- NVM:

![[RH-16775-image007.png]] 

 **Reason:** 

- Function-local static variables are typically allocated by the linker into default data sections.
- They cannot be easily assigned to dedicated memory sections using  **MemMap** mechanisms.
- As a result, their placement in a specific RAM region cannot be controlled as required by the project.
- This limitation makes it difficult to leverage  **MPU (Memory Protection Unit)** features, where memory objects must be located in predefined protected memory regions.
- Global/static variables can be mapped through MemMap sections and allocated to the intended memory area, providing better control for memory protection and safety concepts.

 **Recommendation:** Use global/static variables with appropriate MemMap sections instead of function-local static variables whenever memory placement control or MPU protection is required. 

 **Impact:** Improves memory allocation control, MPU compatibility, and overall compliance with safety/security-oriented memory architecture. 

 **How do you think? Let me know if you agree or not!** 

 **If you agree, please help to fix this big issue for RTA-CAR.** 

Trân trọng / Best regards,

 

  **Phuong Nguyen Le** 

 

 Engineering Services (RBVH/ETA12)

 Bosch Global Software Technologies Company Limited | 364 Cong Hoa Street | Tan Binh Ward | Ho Chi Minh City | VIETNAM | [www.bosch.com.vn](https://www.bosch.com.vn) 

 Fax +84 8 38128001 | [Phuong.NguyenLe@vn.bosch.com!mail_small.gif!](mailto:Phuong.NguyenLe@vn.bosch.com) 

 

 Managing Directors: Sawaiker Girish Vinayak (BGSV/GM)

## 关联

- mentions: [[RH-16708 [VNCNMS] BSWGen issue with missing memory map keywords in Diag Stack]]
- mentions: [[RH-16705 [VNCNMS] BSWGen issue with missing memory map keywords in Com Stack]]
- mentions: [[RH-16706 [VNCNMS] BSWGen issue with missing memory map keywords in Crypto Stack]]
- is mentioned in: [[RH-11220 [CNMS] RTE generated varaibles Section mapping]]
- is mentioned in: [[RH-16706 [VNCNMS] BSWGen issue with missing memory map keywords in Crypto Stack]]

## 评论

> [!note]+ 2026-08-13 10:08 · [[Fargus_Alex_(MSETA)|Alex Fargus]]
> [[Vo_Quang_Gia_Vinh_(MSETA-ARC-PF2)|Vinh Vo Quang Gia]] please move this to "Solution Proposed" once that analysis ticket is complete.

-------

> [!note]+ 2026-08-13 07:53 · [[Oliver_Kust|Oliver Kust]]
> This ticket should be assigned to somebody driving the implementation. Is it you, [[Fargus_Alex_(MSETA)|Alex Fargus]] ,[[Vo_Quang_Gia_Vinh_(MSETA-ARC-PF2)|Vinh Vo Quang Gia]] ?

-------

> [!note]+ 2026-08-03 09:32 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Phuong Nguyen Le]]
> [[JI_Jiaqi_(ETAS-ECMXSF-CN)|Jiaqi JI]] , [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]] : This is planned in 26.4 so that we can't provide comprehensive solution for Cariad in Aug. Is it OK for you?

-------

> [!note]+ 2026-07-30 09:36 · [[Vo_Quang_Gia_Vinh_(MSETA-ARC-PF2)|Vinh Vo Quang Gia]]
> linked the Analysis ticket and plan accordingly

-------

> [!note]+ 2026-07-30 07:51 · [[Fargus_Alex_(MSETA)|Alex Fargus]]
> [[Chandran_Girish_(ETAS-ECMXPC-Yok1)|Girish Chandran]] [[Pianta_Nicola_(ETAS-ECMXPC-Yok2)|Nicola Pianta]] [[Vo_Quang_Gia_Vinh_(MSETA-ARC-PF2)|Vinh Vo Quang Gia]]  Per Alex's comment below, please can you analyse the issue and prepare a Capability for planning in PI 26.4. Please link the analysis ticket when it is available.

-------

> [!note]+ 2026-07-29 15:52 · [[Burn_Alexander_(ETAS-ECMXPC-Yok1)|Alexander Burn]]
> [[Fargus_Alex_(MSETA)|Alex Fargus]] I would like to see this planned in 26.4.

-------

> [!note]+ 2026-07-29 13:39 · [[Fargus_Alex_(MSETA)|Alex Fargus]]
> [[Lay_Nick_(ETAS-ECMXPC-Yok1)|Nick Lay]] [[Burn_Alexander_(ETAS-ECMXPC-Yok1)|Alexander Burn]] Can you take a look and comment about the priority of this topic? We need a decision about whether to analyse and derive a Capability to address this issue.
>
> [[Pianta_Nicola_(ETAS-ECMXPC-Yok2)|Nicola Pianta]] FYI.

-------

> [!note]+ 2026-07-29 08:21 · [[Oliver_Kust|Oliver Kust]]
> On behalf of Volker Kairies:
>
> I agree that function-static elements cannot be covered by the memory mapping concept. It is not possible to use the Memory Allocation Keywords (START/STOP-#defines) inside a function or to include the MemMap header inside a function. However, static elements get into memory areas that would have to be protected by the memory mapping concept. To make this possible, global or file-static elements shall be used instead of function-static elements. The memory mapping concept can then be applied to those global or file-static elements.
>
> There is also a description in the BSW Coding Guideline that addresses this point ([https://www.docs.etas-dev.com/rtacar/develop/mainline/process.workinstructions.main/40_Guidelines/80_BSWCodingGuideline/Chap2_RuleSet_CCoding.html#Abstr_MemMap_003]):
>
> [Abstr_MemMap_003](https://www.docs.etas-dev.com/rtacar/develop/mainline/process.workinstructions.main/40_Guidelines/80_BSWCodingGuideline/Chap2_RuleSet_CCoding.html#Abstr_MemMap_003)
>
> Coding Rule:{*}Exception of Memory Mapping Concept: Function Local Variables{*}
>
> **Memory Mapping Concept shall not be applied for function local variables. It is generally not allowed that MemMap Header files are included inside the body of a function.**
>
> Function local variables are out of scope of the Memory Mapping Concept. By default, they are usually located to registers of the CPU or located to the stack. An assignment to a specific memory section is not required. Therefore, the Memory Mapping Concept is not applied and MemMap Header files must not be included inside the body of a function.
>
> Another case is the location of function local **static** variables. They are located to real memory which could be relevant for the Memory Mapping Concept. But it is still the case that inside a function the Memory Mapping Concept shall not be applied. To force a special mapping for static variables they shall be defined with a **file static** scope, then the Memory Mapping Concept can be used.

-------

> [!note]+ 2026-07-29 04:28 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Phuong Nguyen Le]]
> I received response from [[Volker_Kairies|Volker Kairies]] as [^WG VNCNMS Avoid Using Static Variables Inside Functions.msg]
>
> ^[[Volker_Kairies|Volker Kairies]] , [[Oliver_Kust|Oliver Kust]] : May I understand that we have rule for "static variables shall be defined with a **file static** scope" but this rule isn't followed strictly?^
>
> ^Do you agree that this "local static variables shall be defined with a **file static** scope" rule is MUST? If not, can you share why?^
>
> ^If yes, please help to coordinate with all Components team to update their code! Thanks^

-------

> [!note]+ 2026-07-28 10:22 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Phuong Nguyen Le]]
> [[Oliver_Kust|Oliver Kust]] , [[Erich_Merz|Erich Merz]] : Can you not only check static variable issue, but also check all memmap implementation and provide solution for them?

-------

> [!note]+ 2026-07-28 05:55 · [[JSM_Service_Bot|JSM Service Bot]]
> Note: Oliver Kust, Erich Merz added as watcher to the issue. Internal support agents cannot be added as Request Participants, so they have been automatically joined as Watchers instead.

-------

> [!note]+ 2026-07-28 05:55 · [[Phan_Huynh_Dang_Khoa_(MSETA-Hub-CN)|Khoa Phan Huynh Dang]]
> Hello [[Oliver_Kust|Oliver Kust]] , [[Erich_Merz|Erich Merz]] ,
> There are several limitations when using local static variables in our software. The customer has identified these limitations and requested improvements. Could you please review and evaluate the solution proposed by the customer?

-------

> [!note]+ 2026-07-28 05:39 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Phuong Nguyen Le]], this issue does not have a component set and cannot be transistioned to 'Waiting for Level 3'

-------

> [!note]+ 2026-07-28 05:39 · [[JSM_Service_Bot|JSM Service Bot]]
> [[Erich_Merz|Erich Merz]], [[Oliver_Kust|Oliver Kust]], this issue requires your attention.

-------

> [!note]+ 2026-07-28 05:37 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Phuong Nguyen Le]]
> Set to High Priority as this is big issue and impact to functional safety. 
>
> The memmap issues are reporting by Cariad/VCTC in RH-16706, RH-16705, RH-16708

-------

> [!note]+ 2026-07-28 05:30 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Phuong Nguyen Le, please note that this issue was made with VNCNMS in the summary and has been sent to the relevant queue by adding the VNCNMS label.

-------

> [!note]+ 2026-07-28 05:30 · [[JSM_Service_Bot|JSM Service Bot]]
> Note: Cong ZHANG, Truong Huynh Quang, Oliver Kust, Jie LIU, Yang TAN, Tien Vo Quoc added as watcher to the issue. Internal support agents cannot be added as Request Participants, so they have been automatically joined as Watchers instead.

-------

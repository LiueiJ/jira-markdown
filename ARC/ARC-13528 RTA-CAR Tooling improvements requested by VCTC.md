---
jira_key: ARC-13528
jira_url: "https://jira.etas-dev.com/browse/ARC-13528"
server: etas
kind: motivation
type: Need (Subtask)
status: New
priority: High
project: ARC
assignee: "[[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]]"
reporter: "[[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]"
tags: [jira/label/cea20]
fix-versions: []
epic: null
parent: "[[ARC-9902 VCTC : VW CEA2.0 (CDCU,LDCU,RDCU & RearDCU)]]"
created: "2025-10-30T08:37:24.000+0000"
updated: "2026-06-01T08:55:17.000+0000"
synced-at: "2026-09-10T08:07:27.706Z"
jira-orphaned: false
profile: CEA2.0 Needs
---

## 描述

1. Import the project into tooling  is very slow.  ( LIU Jie , Sisi ) - we waste 30% extra days' time because of the tool. We have to work late because of this… It is not acceptable.
2. 1000 CAN singnals
3. 1000 RTE interfaces
4. The tool can be very slow.
5. In BSW / OS  editor ,
6. Editor is slow.
7. Multiple reference selection is not possible
8. One by one is painful

1. If the reference is changed in one part, The tool does not change in all the places . But Vector & EB is  not like that.
2. Sometimes Shortname is changed, Memmap.
3. Results in long engineering time for customer.

1. IoCNeeds.arxml, OsNeeds.arxml.
2. Everytime we don’t need to select the files in code generators - Why do we need to do that ?
3. Customer : Why do we need to know which file is output and acts as an input to the next component. We don’t need to know.
4. Tao Sisi:
5. Just want to add a comment: Os, Rte, Memmap all have issues for refreshing File lists.
6. Os File list will miss OsNeeds/IocNeeds if Rte Gen once failed.
7. If new ARXML added or removed, Rte File list shall be refreshed right before RTE Gen, instead of opening the widget manually.
8. For Memmap file list, it will be always reverted to default checks without remembering last excluded files. Customer need to uncheck and check files every time before Memmap gen. This shall be improved.

 

1. OS configurations are partially done. When there is BSW code gen is done, why is the tooling reports errors.
2. BSW module generates error - why ? I don’t need to finish os and why does BSW

1. Problem logs are not efficient
2. Not very clear for developer.
3. Which error -which file ?
4. We want easy to find the tool. This mainly for RTE, BSW configurations.
5. All the Possible errors to be displayed as much as possible in the log with clear file name

1. OS editor
2. Build only &

1. Licenses :
2. Only 1 License
3. Lots of licenses -  for many users - many files - this is too much for us to maintain to know.

## 关联

- is contained in: [[RTAXIP-3209 [ETCN Customer PI Planning] Dec 2025]]
- is satisfied by: [[ARC-9226 UI Performance Optimizations]]
- is satisfied by: [[ARC-14186 Improve RIPS Enabler workflow in RTA-CAR]]
- is satisfied by: [[ARC-14523 Enhancements to Live Validation and unified code generator]]
- is satisfied by: [[ARC-15963 Improve iterative ECUExtract use case for RIPS use case]]

## 评论

> [!note]+ 2026-06-01 08:55 · [[Karthi_Krishna_Shekaar_(MSEMT-ETAS)|Karthi Krishna Shekaar (MS/EMT-ETAS)]]
> Capability ARC-15963, is not requested by Cariad. so this is not mandatory for them,.
>
> ARC-15963 will improve the RIPS workflow for Iterative usecase in RTA-CAR

-------

> [!note]+ 2026-04-22 13:31 · [[Lay_Nick_(ETAS-ECMXPC-Yok1)|Lay Nick (ETAS-ECM/XPC-Yok1)]]
> Setting assignee to [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]] who was previously set as the owner.
>
> This is because for need tickets, Assignee now represents the owner of the need.

-------

> [!note]+ 2026-02-26 04:33 · [[Allen_Jacob_(ETAS-ECMXPC-Yok2)|Allen Jacob (ETAS-ECM/XPC-Yok2)]]
> [CarAut_2]
>
>  ARC-14346 which was linked to this Capability has been removed while this ticket was in Detailed or later state. 
>
> This removal was triggered by Karthi Krishna Shekaar (MS/EMT-ETAS).
>
> [[Karthi_Krishna_Shekaar_(MSEMT-ETAS)|Karthi Krishna Shekaar (MS/EMT-ETAS)]]

-------

> [!note]+ 2026-02-26 04:32 · [[Allen_Jacob_(ETAS-ECMXPC-Yok2)|Allen Jacob (ETAS-ECM/XPC-Yok2)]]
> [CarAut_3]
>
>  ARC-14346 has been linked to this Capability while this ticket was in Detailed or later state.
>
> This addition was triggered by Karthi Krishna Shekaar (MS/EMT-ETAS).
>
> [[Karthi_Krishna_Shekaar_(MSEMT-ETAS)|Karthi Krishna Shekaar (MS/EMT-ETAS)]]

-------

> [!note]+ 2026-01-14 06:23 · [[Karthi_Krishna_Shekaar_(MSEMT-ETAS)|Karthi Krishna Shekaar (MS/EMT-ETAS)]]
> {*}`*`Performance Issues:`*`{*}
>
> 1. **(low)** Import the project into tooling  is very slow (Confgen).  ( LIU Jie , Sisi ) - we waste 30% extra days' time because of the tool. We have to work late because of this… It is not acceptable.
> 2. **(high)** The tool can be very slow(BSW codegen) => **Incremental Code Generation in V12.10.0 will reduce codegen time for second & subsequent execution. For further improvement parallelization of codegen is planned in ticket ARC-9214**
> 3. **(medium)** Confgen enhancer is slow (e.g: comsignal)
>     - 1000 CAN signals
>     - 1000 RTE interfaces(Connections & DataMappings)
> 4. **(high)** In BSW Editor (including OS configuration): => ** **ARC-14346**
>     - e.g shortname of a element is changed, then editor is not responsive.
>     - Opening table based editor (e.g:comsignals), editor is slow (additional remark, if the project is not reloaded then tool becomes slower every time)
>     - Creating new container, makes the editor to freeze for sometime
>     - Opening a reference dialog for a element which has many elements, is very slow (reference dialog pops up)
>
> {*}`*`Usability Improvements:`*`{*}
>
> 1. **(low)** In BSW Editor: Multiple reference selection is not simple
>     - For multi reference elements, in reference dialog, it is not very clear what are the elements already configured and also not notifying warning or error for duplicate selection
> 2. **(medium)** If the reference is changed in one part, The tool does not change in all the places . But Vector & EB is  not like that. (Expectation: Tool should identify the dependencies and execute necessary actions and notify user on what all generations to be executed only)
>     - When a specific element is changed, user wanted to know what other configuration changes and steps to be done
>         - (e.g: on changing OS task name, user should be notified that RTE , OS & MemMap to be generated)
>         - (e.g: when new connections added, then Ecu Extract, RTE to be executed)
> 3. **(high)** Customer, Why do we need to know which file is output and acts as an input to the next component. We don’t need to know.
>     - In this specific case, IoCNeeds.arxml, OsNeeds.arxml files were selected by customer, but after failure of RTE regeneration, the file selection was lost for OS generation (expectation: let RTEgen do not clear the folder)  **=>** **Addressed in V12.10.0 as part of convergence**
>     - List of files that are mandatory which is generated from other tool should be automatically considered (e.g: file generated by RTE to be fed as input to OS generator)
>     - If new ARXML added or removed, Rte File list shall be refreshed right before RTE Gen, instead of opening the widget manually.
>     - If customer add new Swc.arxml file or removes file, then RTE generation should consider the available files automatically(GUI & CLI), so every time customer don’t need to select the files in code generators ?)
>     - For Memmap file list, it will be always reverted to default checks without remembering last excluded files. Customer need to uncheck and check files every time before Memmap gen. This shall be improved. => **ARC-13741**
>     - MemMap generator also should remember all unselected file lists (VALUE_UNSELECTED_PREVIOUS_CATEGORY) similar to RTE) ) **=> Addressed in V12.10.0 as part of convergence**
> 4. **(high)** OS configurations are partially done. When there is BSW code gen is done, why is the tooling reports errors. 
>     - Multiplicity check on OS configuration was not done part of BSW codegen validations in previous RTA-CAR versions and its new in V12.6 (expectation is not to have this check)
> 5. **(medium)** Problem logs are not efficient for RTE & BSW codegeneration errors
>     - Error messages are not very clear for developer.
>     - Which error -which file. All the Possible errors to be displayed as much as possible in the log with clear file name
> 6. **(high)** Before RTE Gen, ECUExtract and enable RIPS to be done manually is painful **=> ARC-14427 (Short term)** and **ARC-14186 (Long Term)**

-------

> [!note]+ 2026-01-08 09:01 · [[Karthi_Krishna_Shekaar_(MSEMT-ETAS)|Karthi Krishna Shekaar (MS/EMT-ETAS)]]
> For the points on ISOLAR tooling, I will create necessary capabilities and consider possible high priority topics for the upcoming PI
>
> [[Patil_Mahesh_(MSPJ-ETH-BSW)|Patil Mahesh (MS/PJ-ETH-BSW)]] Below points on performance issues are related to confgen
>
> **Performance Issues:**
>
> 1. **(low)** Import the project into tooling  is very slow (Confgen), (LIU Jie , Sisi) - we waste 30% extra days' time because of the tool. We have to work late because of this… It is not acceptable.
>
> 3. **(medium)** Confgen enhancer is slow (e.g: comsignal)
>     - 1000 CAN signals
>     - 1000 RTE interfaces(Connections & DataMappings)

-------

> [!note]+ 2025-12-25 06:56 · [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]]
> From [[TAO_Sisi_(ETAS-ECMXSF-CN)|TAO Sisi (ETAS-ECM/XSF-CN)]] :
>
> Hi [@Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)](mailto:Sathish.Madanmohan@etas.com) and [@JI Jiaqi (ETAS-ECM/XSF-CN)](mailto:Jiaqi.JI@etas.com)
>
> I tried RTA-CAR 12.11.0VCTCESR1pr1 and find that incremental BSW code gen is not available in this version. This feature will be very helpful for faster code gen. I’m suffering from generating Cariad CZCU project, only a tiny fix of configuration can cause one hour code generation. And then I have another config error…
>
> Karthi tells me this feature will be officially released in 12.10.
>
> [@Karthi Krishna Shekaar (MS/EMT-ETAS)](mailto:Karthi.Krishna@etas.com) wants to know: *If I any PR is planned based on V12.10, then it should have the feature, who can provide details on the PR timeline and which version of RTA-CAR will be used for that? whether Lan knows?*
>
>  __ 
>
> Do you guys know about that? If there will be PR based on 12.10, then I can try this feature later.

-------

> [!note]+ 2025-12-16 03:34 · [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]]
> [[Karthi_Krishna_Shekaar_(MSEMT-ETAS)|Karthi Krishna Shekaar (MS/EMT-ETAS)]] We've marked priority as below, please check:
>
> **Performance Issues:**
>
> 1. **(low)** Import the project into tooling  is very slow (Confgen).  ( LIU Jie , Sisi ) - we waste 30% extra days' time because of the tool. We have to work late because of this… It is not acceptable.
> 2. **(high)** The tool can be very slow(BSW codegen)
> 3. **(medium)** Confgen enhancer is slow (e.g: comsignal)
>     - 1000 CAN signals
>     - 1000 RTE interfaces(Connections & DataMappings)
> 4. **(high)** In BSW Editor (including OS configuration):
>     - e.g shortname of a element is changed, then editor is not responsive.
>     - Opening table based editor (e.g:comsignals), editor is slow (additional remark, if the project is not reloaded then tool becomes slower every time)
>     - Creating new container, makes the editor to freeze for sometime
>     - Opening a reference dialog for a element which has many elements, is very slow (reference dialog pops up)
>
> **Usability Improvements:**
>
> 1. **(low)** In BSW Editor: Multiple reference selection is not simple
>     - For multi reference elements, in reference dialog, it is not very clear what are the elements already configured and also not notifying warning or error for duplicate selection
> 2. **(medium)** If the reference is changed in one part, The tool does not change in all the places . But Vector & EB is  not like that. (Expectation: Tool should identify the dependencies and execute necessary actions and notify user on what all generations to be executed only)
>     - When a specific element is changed, user wanted to know what other configuration changes and steps to be done
>         - (e.g: on changing OS task name, user should be notified that RTE , OS & MemMap to be generated)
>         - (e.g: when new connections added, then Ecu Extract, RTE to be executed)
> 3. **(high)** Customer, Why do we need to know which file is output and acts as an input to the next component. We don’t need to know.
>     - In this specific case, IoCNeeds.arxml, OsNeeds.arxml files were selected by customer, but after failure of RTE regeneration, the file selection was lost for OS generation (expectation: let RTEgen do not clear the folder)
>     - List of files that are mandatory which is generated from other tool should be automatically considered (e.g: file generated by RTE to be fed as input to OS generator)
>     - If new ARXML added or removed, Rte File list shall be refreshed right before RTE Gen, instead of opening the widget manually.(
>     - If customer add new Swc.arxml file or removes file, then RTE generation should consider the available files automatically(GUI & CLI), so every time customer don’t need to select the files in code generators ?)
>     - For Memmap file list, it will be always reverted to default checks without remembering last excluded files. Customer need to uncheck and check files every time before Memmap gen. This shall be improved.(
>     - MemMap generator also should remember all unselected file lists (VALUE_UNSELECTED_PREVIOUS_CATEGORY) similar to RTE)
> 4. **(high)** OS configurations are partially done. When there is BSW code gen is done, why is the tooling reports errors. 
>     - Multiplicity check on OS configuration was not done part of BSW codegen validations in previous RTA-CAR versions and its new in V12.6 (expectation is not to have this check)
> 5. **(medium)** Problem logs are not efficient for RTE & BSW codegeneration errors
>     - Error messages are not very clear for developer.
>     - Which error -which file. All the Possible errors to be displayed as much as possible in the log with clear file name
> 6. **(high)** Before RTE Gen, ECUExtract and enable RIPS to be done manually is painful

-------

> [!note]+ 2025-12-15 08:10 · [[Karthi_Krishna_Shekaar_(MSEMT-ETAS)|Karthi Krishna Shekaar (MS/EMT-ETAS)]]
> [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]] [[TAO_Sisi_(ETAS-ECMXSF-CN)|TAO Sisi (ETAS-ECM/XSF-CN)]] As discussed, please cross check the list and confirm all points are covered. Also based on the project demand, please categorize on the high, medium & low priority, as that would help me to prioritize the topics for next PI

-------

> [!note]+ 2025-12-02 07:04 · [[Karthi_Krishna_Shekaar_(MSEMT-ETAS)|Karthi Krishna Shekaar (MS/EMT-ETAS)]]
> Notes from discussion[02/12/2025]: (LIU JIE, TAO Sisi, Karthi Krishna Shekaar)
>
> **Performance Issues:**
>  # Import the project into tooling  is very slow (Confgen).  ( LIU Jie , Sisi ) - we waste 30% extra days' time because of the tool. We have to work late because of this… It is not acceptable.
>  # The tool can be very slow(BSW codegen)
>  # Confgen enhancer is slow (e.g: comsignal)
>  ** 1000 CAN signals
>  ** 1000 RTE interfaces(Connections & DataMappings)
>  # In BSW Editor (including OS configuration):
>  ** e.g shortname of a element is changed, then editor is not responsive.
>  ** Opening table based editor (e.g:comsignals), editor is slow (additional remark, if the project is not reloaded then tool becomes slower every time)
>  ** Creating new container, makes the editor to freeze for sometime
>  ** Opening a reference dialog for a element which has many elements, is very slow (reference dialog pops up)
>
> **Usability Improvements:**
>  # In BSW Editor: Multiple reference selection is not simple
>  ** For multi reference elements, in reference dialog, it is not very clear what are the elements already configured and also not notifying warning or error for duplicate selection
>  # If the reference is changed in one part, The tool does not change in all the places . But Vector & EB is  not like that. (Expectation: Tool should identify the dependencies and execute necessary actions and notify user on what all generations to be executed only)
>  ** When a specific element is changed, user wanted to know what other configuration changes and steps to be done
>  *** (e.g: on changing OS task name, user should be notified that RTE , OS & MemMap to be generated)
>  *** (e.g: when new connections added, then Ecu Extract, RTE to be executed)
>  # Customer, Why do we need to know which file is output and acts as an input to the next component. We don’t need to know.
>  ** In this specific case, IoCNeeds.arxml, OsNeeds.arxml files were selected by customer, but after failure of RTE regeneration, the file selection was lost for OS generation (expectation: let RTEgen do not clear the folder)
>  ** List of files that are mandatory which is generated from other tool should be automatically considered (e.g: file generated by RTE to be fed as input to OS generator)
>  ** If new ARXML added or removed, Rte File list shall be refreshed right before RTE Gen, instead of opening the widget manually.(
>  ** If customer add new Swc.arxml file or removes file, then RTE generation should consider the available files automatically(GUI & CLI), so every time customer don’t need to select the files in code generators ?)
>  ** For Memmap file list, it will be always reverted to default checks without remembering last excluded files. Customer need to uncheck and check files every time before Memmap gen. This shall be improved.(
>  ** MemMap generator also should remember all unselected file lists (VALUE_UNSELECTED_PREVIOUS_CATEGORY) similar to RTE)
>  # OS configurations are partially done. When there is BSW code gen is done, why is the tooling reports errors. 
>  ** Multiplicity check on OS configuration was not done part of BSW codegen validations in previous RTA-CAR versions and its new in V12.6 (expectation is not to have this check)
>  # Problem logs are not efficient for RTE & BSW codegeneration errors
>  ** Error messages are not very clear for developer.
>  ** Which error -which file. All the Possible errors to be displayed as much as possible in the log with clear file name
>  # Before RTE Gen, ECUExtract and enable RIPS to be done manually is painful

-------

> [!note]+ 2025-10-30 08:39 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]]  I have added all the notes I wrote down in the meeting. could you please elaborate / describe it appropriately. 
>
> Please coordinate with [[TAO_Sisi_(ETAS-ECMXSF-CN)|TAO Sisi (ETAS-ECM/XSF-CN)]] and [[Karthi_Krishna_Shekaar_(MSEMT-ETAS)|Karthi Krishna Shekaar (MS/EMT-ETAS)]] for completeness. 

-------

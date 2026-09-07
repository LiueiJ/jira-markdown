---
jira_key: ARC-16245
jira_url: "https://jira.etas-dev.com/browse/ARC-16245"
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
created: "2026-05-14T07:08:10.000+0000"
updated: "2026-08-17T07:53:44.000+0000"
synced-at: "2026-09-06T06:58:54.667Z"
jira-orphaned: true
---

# ARC-16245 UAES - ZCU - RTA-CAR Requirements

> [!jira] New ·  · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] · 更新于 2026-08-17T07:53:44.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-16245)

## 描述

UAES is evaluating **RTA-CAR** for their next-generation Zone Controller platform. After an initial assessment, we identified that **30% of their required functions** are currently unsupported or only partially supported.

please review the attached list (Column B) and provide the following for Column E:

- **Roadmap Status:** Are these functions currently planned?

- **Release Timeline:** What are the confirmed or forecasted release dates?

Since UAES is transitioning from Vector tools, our timely feedback is critical to their platform decision. 

**The current assessment of feature completeness was done against RTA-CAR 12.9.0 by the ECM-China team.** 

UAES Original deadline is May 15th (and we come to know only on May14th !sad.png!)  but asap response is appreciated.

## 评论

> [!note]+ 2026-08-17 07:53 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] [[Burn_Alexander_(ETAS-ECMXPC-Yok1)|Burn Alexander (ETAS-ECM/XPC-Yok1)]] 
>
> Based on the 2 options given to UAES :
> Option 1 : Business driven ( committed PoC Joint development for 3-6 months that involves UAES investment . Time critical )
> Option 2 : R&D driven ( UAES to work on the CP flex topic, with limited support from ETAS . Non-time critical )
>
> UAES, has chosen the {*}Option 2 : R&D driven{*}.  This means they will try to develop a PoC using our CPFlex artifacts in their own timeline. They may need support from our experts from time to time on the technical front ( here the customer expectation is zero-cost )
> I have already communicated to UAES that we cannot commit to full-time support or on-demand support. maybe a bi-weekly sync / support (1-2 hours max) should suffice. Also, I have mentioned that our experts are working on Business-critical projects and this might also impact our support sometimes. The bi-weekly (or some regular alignment) could benefit us (ETAS) in understanding the direction and what UAES is trying to build. 
>
> Now, UAES would like to know how to proceed forward. UAES want to know from ETAS,   
>  # What **CPFlex artefacts** currently exist and can be reused ? 
>  # What kind of Initial **training support** be offered to UAES 
>  # Available **consulting/alignment support** (e.g., regular Q&A sessions, periodic alignment meetings)
>
> In summary, Customer want to know how ETAS can support UAES under the Option 2 approach.  With clear time timeline for training & support  ( point 2 & 3 ) 
> **UAES have requested for an alignment meeting this week to discuss the next steps.** 
> [[Tchouante_Auges_(ETAS-ECMXPC-Abt1)|Tchouante Auges (ETAS-ECM/XPC-Abt1)]] [[Kristoferitsch_Jakob_(RBOSPJ-GM)|Kristoferitsch Jakob (RBOS/PJ-GM)]] [[Chandran_Girish_(ETAS-ECMXPC-Yok1)|Chandran Girish (ETAS-ECM/XPC-Yok1)]] fyi

-------

> [!note]+ 2026-06-15 08:19 · [[Jain_Vihitha_(MSEMS-ETAS)|Jain Vihitha (MS/EMS-ETAS)]]
> [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]] [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] : The following list of values for the DEM internal data elements has been provided below for your reference:
>
> Please check if this helps.
> | **Supported values under DemInternalDataElementClass** | **Description** |
> | DEM_AGINGCTR_UPCNT | Aging counter, counting from 0 upwards with each aging cycle |
> | DEM_AGINGCTR_DOWNCNT | Aging counter, counts fom AgingThreshold downwards with each aging cycle |
> | DEM_OCCCTR | Occurrence counter value |
> | DEM_OVFLIND | Overflow indicator |
> | DEM_SIGNIFICANCE | Value of the configuration parameter DemDTCSignificance |
> | DEM_DTC_PRIORITY | Value of the configuration parameter DemDTCPriority |
> | DEM_MONITOR_DATA_0 | Value reported as the argument monitorData0 when Dem_SetEventStatusWithMonitorData() was called |
> | DEM_MONITOR_DATA_1 | Value reported as the argument monitorData1 when Dem_SetEventStatusWithMonitorData() was called |
> | DEM_CURRENT_FDC | Current value of fault detection counter (FDC) |
> | DEM_MAX_FDC_DURING_CURRENT_CYCLE | Max. value reached by FDC in current operation cycle |
> | DEM_MAX_FDC_SINCE_LAST_CLEAR | Max. value reached by FDC since last diagnostic clear |
> | DEM_CYCLES_SINCE_FIRST_FAILED | The number of operation cycles since the FDC first reached its maximum value of +127 |
> | DEM_CYCLES_SINCE_LAST_FAILED | The number of operation cycles since the FDC last reached its maximum value of +127 |
> | DEM_FAILED_CYCLES | The number of operation cycles during which FDC reached its maximum value of +127 |
> | DEM_EVENT_ASSOCIATED_IDENTIFICATION | Value of the configuration parameter DemEventAssociatedIdentification |
> | DEM_MIL_DIST | Value of PID $21 at the time Extended data was stored |
> | DEM_WARM_UPS | Value of PID $30 at the time Extended data was stored |
> | DEM_CLR_DIST | Value of PID $31 at the time Extended data was stored |
> | DEM_MIL_TIME | Value of PID $4D at the time Extended data was stored |
> | DEM_CLR_TIME | Value of PID $4E at the time Extended data was stored |
> | DEM_DTR | Corresponds to Extended data record number $92 as defined by SAE J1979-DA |
> | DEM_IUMPR | Corresponds to Extended data record number $91 as defined by SAE J1979-DA |
> | DEM_MONITOR_ACTIVITY_DATA | Corresponds to Extended data record number $93 as defined by SAE J1979-DA |
> | **DEM_RB_B1_COUNTER** | B1 counter as defined by WWH-OBD regulations |
> | **DEM_EVENT_ID** | The ID assigned for the DemEvent (corresponds to the config parameter DemEventId) |
> | **DEM_CYCLES_SINCE_LAST_FAILED_EXCLUDING_TNC** | Similar to the AR defined DEM_CYCLES_SINCE_LAST_FAILED, but does not count the TestNotCompleted" cycles. The parameter DemRbDataElementLastFailedSinceLastFailedExcludingTNCIncludesFailedCycle controls whether the failed cycle itself is included or not for the counting. |
> | **DEM_EVENT_STATUS_BYTE** | The UDS status byte corresponding to the DemEvent |
> | **DEM_PRJ_SPECIFIC_DATA_ON_RETRIEVE** | Allows to define project specific contents via callback (live data, at the time of query by tester) |
> | **DEM_PRJ_SPECIFIC_DATA_ON_REPORT** | Allows to define project specific contents via callback (captured data when the extended data was stored) |
>
> The bold ones at the end are RTA-CAR extensions. Rest are defined in AR

-------

> [!note]+ 2026-06-12 07:26 · [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]]
> Hello, [[Jain_Vihitha_(MSEMS-ETAS)|Jain Vihitha (MS/EMS-ETAS)]] [[Pandey_Ashutosh_(ETAS-ECMXPC-Abt1)|Pandey Ashutosh (ETAS-ECM/XPC-Abt1)]]  
>
> UAES has masked some of the requirements as middle risk for their coming projects and raised some questions in the [平台开发对于AUTOSAR基础软件包的需求.xlsx](https://bosch.sharepoint.com/:x:/r/sites/msteams_9477696/Shared%20Documents/ECM/Customer/Acquisitions/2026/Acquisition%20Project%20Docs/UAES/%E5%B9%B3%E5%8F%B0%E5%BC%80%E5%8F%91%E5%AF%B9%E4%BA%8EAUTOSAR%E5%9F%BA%E7%A1%80%E8%BD%AF%E4%BB%B6%E5%8C%85%E7%9A%84%E9%9C%80%E6%B1%82.xlsx?d=wed747a70c8344139b3ed368813004c5f&csf=1&web=1&e=4YTXyK) sheet.
>
> Could you please help to check and answer the DIAG related needs?
>
> It would be appreciated to get your response by 26/06/15.
>
> cc. [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] 

-------

> [!note]+ 2026-06-12 07:24 · [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]]
> Hello, [[Karthi_Krishna_Shekaar_(MSEMT-ETAS)|Karthi Krishna Shekaar (MS/EMT-ETAS)]] 
>
> UAES has masked some of the requirements as middle risk for their coming projects and raised some questions in the [平台开发对于AUTOSAR基础软件包的需求.xlsx](https://bosch.sharepoint.com/:x:/r/sites/msteams_9477696/Shared%20Documents/ECM/Customer/Acquisitions/2026/Acquisition%20Project%20Docs/UAES/%E5%B9%B3%E5%8F%B0%E5%BC%80%E5%8F%91%E5%AF%B9%E4%BA%8EAUTOSAR%E5%9F%BA%E7%A1%80%E8%BD%AF%E4%BB%B6%E5%8C%85%E7%9A%84%E9%9C%80%E6%B1%82.xlsx?d=wed747a70c8344139b3ed368813004c5f&csf=1&web=1&e=4YTXyK) sheet.
>
> Could you please help to check and answer the Tool related needs?
>
> It would be appreciated to get your response by 26/06/15.
>
> cc. [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] 

-------

> [!note]+ 2026-06-12 07:17 · [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]]
> Hello, [[Bauer_Benedikt_(ETAS-ECMXPC-Fe1)|Bauer Benedikt (ETAS-ECM/XPC-Fe1)]]  [[Tchouante_Auges_(ETAS-ECMXPC-Abt1)|Tchouante Auges (ETAS-ECM/XPC-Abt1)]] 
>
> UAES has masked some of the requirements as middle risk for their coming projects and raised some questions in the [平台开发对于AUTOSAR基础软件包的需求.xlsx](https://bosch.sharepoint.com/:x:/r/sites/msteams_9477696/Shared%20Documents/ECM/Customer/Acquisitions/2026/Acquisition%20Project%20Docs/UAES/%E5%B9%B3%E5%8F%B0%E5%BC%80%E5%8F%91%E5%AF%B9%E4%BA%8EAUTOSAR%E5%9F%BA%E7%A1%80%E8%BD%AF%E4%BB%B6%E5%8C%85%E7%9A%84%E9%9C%80%E6%B1%82.xlsx?d=wed747a70c8344139b3ed368813004c5f&csf=1&web=1&e=4YTXyK) sheet.
>
> Could you please help to check and answer the RTE related needs?
>
> It would be appreciated to get your response by 26/06/15.
>
> cc. [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] 

-------

> [!note]+ 2026-06-04 10:58 · [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]
> [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]] I have updated the feedback for Upper Tester module -  that can be offered as an Eng.Service by the hub.
> The comment is internal and needs to be assessed by the hub before sharing with customer.

-------

> [!note]+ 2026-06-04 10:18 · [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]]
> Dear [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]] [[Jain_Vihitha_(MSEMS-ETAS)|Jain Vihitha (MS/EMS-ETAS)]]  [[Burn_Alexander_(ETAS-ECMXPC-Yok1)|Burn Alexander (ETAS-ECM/XPC-Yok1)]] [[Karthi_Krishna_Shekaar_(MSEMT-ETAS)|Karthi Krishna Shekaar (MS/EMT-ETAS)]] 
>
> UAES has masked some of the requirements as middle risk for their coming projects and raised some questions in the [平台开发对于AUTOSAR基础软件包的需求.xlsx](https://bosch.sharepoint.com/:x:/r/sites/msteams_9477696/Shared%20Documents/ECM/Customer/Acquisitions/2026/Acquisition%20Project%20Docs/UAES/%E5%B9%B3%E5%8F%B0%E5%BC%80%E5%8F%91%E5%AF%B9%E4%BA%8EAUTOSAR%E5%9F%BA%E7%A1%80%E8%BD%AF%E4%BB%B6%E5%8C%85%E7%9A%84%E9%9C%80%E6%B1%82.xlsx?d=wed747a70c8344139b3ed368813004c5f&csf=1&web=1&e=4YTXyK) sheet.
>
> I've filtered the tickets for you.
>
> Could you please help to answer by next Monday?

-------

> [!note]+ 2026-05-21 23:50 · [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]]
> Dear all,
>
> I've update loaded the collected version of feedback in SharePoint link as below:
>
> [平台开发对于AUTOSAR基础软件包的需求.xlsx ](https://bosch.sharepoint.com/:x:/r/sites/msteams_9477696/Shared%20Documents/ECM/Customer/Acquisitions/2026/Acquisition%20Project%20Docs/UAES/%E5%B9%B3%E5%8F%B0%E5%BC%80%E5%8F%91%E5%AF%B9%E4%BA%8EAUTOSAR%E5%9F%BA%E7%A1%80%E8%BD%AF%E4%BB%B6%E5%8C%85%E7%9A%84%E9%9C%80%E6%B1%82.xlsx?d=wed747a70c8344139b3ed368813004c5f&csf=1&web=1&e=6kXPui)which is used as first round feedback.
>
> We can maintain it continuously instead of attaching it.
>
> Thanks for the support and quick feedback.

-------

> [!note]+ 2026-05-20 04:23 · [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]
> [[Weigl_Sandra_(ETAS-ECMXPC-Fe3)|Weigl Sandra (ETAS-ECM/XPC-Fe3)]] Noted, Thanks for the hint, will take of the TLS requirement in NETCOM analysis.

-------

> [!note]+ 2026-05-19 16:54 · [[Weigl_Sandra_(ETAS-ECMXPC-Fe3)|Weigl Sandra (ETAS-ECM/XPC-Fe3)]]
> Thanks [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] and [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]] . I commented the requirements.
>
> [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]] there is a TLS requirement listed under Security requirements  *: During two-way verification, TLS allows users to choose whether to send the root certificate when sending the certificate chain.*
>
> You might haven't seen it using the "COM filter"

-------

> [!note]+ 2026-05-19 01:51 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[Weigl_Sandra_(ETAS-ECMXPC-Fe3)|Weigl Sandra (ETAS-ECM/XPC-Fe3)]]  they are the same file - filter was applied wrongly. now [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]]  has corrected it. thanks 

-------

> [!note]+ 2026-05-18 09:51 · [[Weigl_Sandra_(ETAS-ECMXPC-Fe3)|Weigl Sandra (ETAS-ECM/XPC-Fe3)]]
> Hi [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] , COM and SEC requirement documents are identical. Is that intentional, or did something get mixed up?

-------

> [!note]+ 2026-05-14 08:14 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> Dear [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] 
>
> UAES ZCU team is using Vector for their main projects and also use Neusoft tooling for few other projects. This team is not familiar with RTA-CAR. They are planning to use one supplier tool for all their projects. Due to our contract and position with UAES, they currently they are evaluating RTA-CAR. They have identified some gaps. they want to know our roadmap plans for closing these gaps. we have created the Needs ticket related to different ARTs and assigned to respective PRMs. We need the plan info by end of next week latest. please support. Many Thanks
>
> [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]  [[Jain_Vihitha_(MSEMS-ETAS)|Jain Vihitha (MS/EMS-ETAS)]] [[Karthi_Krishna_Shekaar_(MSEMT-ETAS)|Karthi Krishna Shekaar (MS/EMT-ETAS)]] [[Weigl_Sandra_(ETAS-ECMXPC-Fe3)|Weigl Sandra (ETAS-ECM/XPC-Fe3)]] fyi

-------

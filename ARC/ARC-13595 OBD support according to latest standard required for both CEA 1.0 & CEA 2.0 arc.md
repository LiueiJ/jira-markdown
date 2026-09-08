---
jira_key: ARC-13595
jira_url: "https://jira.etas-dev.com/browse/ARC-13595"
server: etas
kind: motivation
type: Need (Subtask)
status: On Hold
priority: Medium
project: ARC
assignee: vih4kor
reporter: mas1yok
tags: [CEA2.0, DIAG]
components: []
fix-versions: []
epic: null
parent: "[[ARC-9902 VCTC : VW CEA2.0 (CDCU,LDCU,RDCU & RearDCU)]]"
created: "2025-11-12T05:31:59.000+0000"
updated: "2026-01-15T02:13:21.000+0000"
synced-at: "2026-09-08T01:46:40.034Z"
jira-orphaned: true
profile: CEA2.0 Needs
---

# ARC-13595 OBD support according to latest standard required for both CEA 1.0 & CEA 2.0 architecture

> [!jira] On Hold · Medium · [[Jain_Vihitha_(MSEMS-ETAS)|Jain Vihitha (MS/EMS-ETAS)]] · 更新于 2026-01-15T02:13:21.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-13595)

> 标签：#jira/label/cea20 #jira/label/diag

## 描述

**Customer Expectation:** 

current OBD related functions need to be implemented on CEA1.0 MQB and CEA2.0 projects. Depending on the mass production time, both platforms need to support the relevant regulatory standards of China VIB and China VII.

The ETAS RTA-CAR protocol stack needs to support both standards.

               The available information is as follows:

              

                                        platform
Protocol stack version
Regulatory requirements need to be supported
Refer to the regulations

CEA1.0 MQB
**RTA-CAR 9.1.0**
C6b/C7
SAE J1979, SAE J1979-2/3

CEA2.0
**RTA-CAR 12.11.0** (target version)
C6b/C7
SAE J1979, SAE J1979-2/3

According toThe AUTOSAR document states that AR4.2.2 does not support the OBDonUDS function of SAE J1979-2, which is described in the AR24-11 document.

**Need ETAS to confirm:**

1. The two versions of the protocol stack support the above regulations and related protocol documents.
2. If not, confirm the support plan and support time.

C6b refers to the China 6b OBD regulation (GB.18352.6-2016),

which mandates that the data content format must comply with the SAE J1979 standard.

C7 refers to the upcoming China 7 OBD regulation (GB.18352.7-xxxx), which has not yet been officially released.

Under C7, the data content format must comply with the SAE J1979-2 / SAE J1979-3 standards.

We would like to confirm whether the ETAS RTA-CAR protocol stack supports the following standards:

SAE J1979:      Classical OBD

SAE J1979-2:  OBDonUDS

SAE J1979-3:  ZEVonUDS

--------------------------------------------------------------------

**Business Scope :**

**The budget and timeline is under discussion with customer . Will update soon.**

## 评论

> [!note]+ 2026-01-15 02:12 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [@Jain Vihitha (MS/EBD-ETAS)](mailto:Vihitha.Jain@etas.com) could you please help analyze C7 standard ( first pass analysis ) to know if there are any deviations in the Spec to what we have already implemented ? I have attached the spec . I need some inputs before we could engage with customer for roadmaps & plans.  thanks
>
> [Fargus Alex (MS/ETA)](mailto:Alex.Fargus@vn.bosch.com) fyi

-------

> [!note]+ 2026-01-13 09:17 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> attached [^C7 draft (1).zip]shared by VW (see msg [^China 7 emission standard draft.msg]) . Customer has requested clarification on C6 & C& support . please check the  [^FW_ ETAS ISOLAR 对于OBD的支持.msg]

-------

> [!note]+ 2025-12-02 04:46 · [[Jain_Vihitha_(MSEMS-ETAS)|Jain Vihitha (MS/EMS-ETAS)]]
> Placed the Need 'On Hold' , will be followed up based on C7 release.

-------

> [!note]+ 2025-11-23 23:25 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[Jain_Vihitha_(MSEMS-ETAS)|Jain Vihitha (MS/EMS-ETAS)]]  thanks a lot for the summary and clarity. I shall communicate the information to the customer. Once C7 is released, we can further follow-up with the customer to close the gaps if any.  

-------

> [!note]+ 2025-11-21 12:25 · [[Jain_Vihitha_(MSEMS-ETAS)|Jain Vihitha (MS/EMS-ETAS)]]
> [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] : Normally, the derived legislative requirements are provided to Tier1s and Tier2s by the OEM. In this case C7 is not yet published and we do not know what is inside as yet. From other OEM discussions, the updates in C7 could be more clarity regarding Zev ECUs for ZevonUDS which we support according to SAE J1979-3.
>
> As per the comment from Girish, we do support the following standards already in RTA-CAR 12.11.0:
>
> SAE J1979: Classical OBD
> SAE J1979-2: OBDonUDS
> SAE J1979-3: ZEVonUDS
>
> Since you mention in the description, under C7 data format must comply with the above SAE standards, we already do that and hence can claim compliance to C7.
>
> RTA-CAR 9.1.0 does not support the following protocols yet:
>
> SAE J1979-2: OBDonUDS
> SAE J1979-3: ZEVonUDS
>
> This would mean we need to port the Diagstack from 12.x to 9.1.0.
>
> There is already available such a version delivered to VM-Brakes: **CUBAS_Diagnosis_AR42__9_1_X__Development**
>
> The RTA-CAR integration and testing effort has to be checked - [[Chandran_Girish_(ETAS-ECMXPC-Yok1)|Chandran Girish (ETAS-ECM/XPC-Yok1)]] : Can a T-Shirt size be estimated?
>
> +What is required?+
>
> To get into more details of C7, we request you to provide the extract/delta requirements of the C7 from the customer.
>
> There was a similar query in ARC-12745 regarding EU7, and the customer was able to share with us the requirements which were analyzed to conclude that no changes from ETAS BSW was required.

-------

> [!note]+ 2025-11-21 11:09 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[Jain_Vihitha_(MSEMS-ETAS)|Jain Vihitha (MS/EMS-ETAS)]]  We need to provide customer with some concrete information that we need to communicate to the customer by next week. 
>
> From [[Chandran_Girish_(ETAS-ECMXPC-Yok1)|Chandran Girish (ETAS-ECM/XPC-Yok1)]]  I understand the current status of the OBD support w.r.t. C6 & C7 standards. But customer is pressing for more detailed information 
> 1. I have requested  AAA team can to do a Gap analysis of the C6b & C7standards and the gap analysis for support in the FWD path 
>
> 2.  However, we still need information about the current OBD support in RTA-CAR 9 and gaps in comparison to C6B standard. 
>
> CN govt has mandated the COEMs to comply to China standards . Hence the pressure from VW top management to update their CEA 1.0 project (based on RTA-CAR 9.1.0) and CEA 2.0 (based on RTA-CAR 12.11.0 (final release) ). They need to make plans and hence they pressure us to provide detailed information
>
> Could I request your support asap. 
>
> [[TAN_Yang_(ETAS-ECMXSF-CN)|TAN Yang (ETAS-ECM/XSF-CN)]] [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] [[Patil_Mahesh_(MSPJ-ETH-BSW)|Patil Mahesh (MS/PJ-ETH-BSW)]] [[Fargus_Alex_(MSETA)|Fargus Alex (MS/ETA)]] [[Lay_Nick_(ETAS-ECMXPC-Yok1)|Lay Nick (ETAS-ECM/XPC-Yok1)]] fyi

-------

> [!note]+ 2025-11-20 16:50 · [[Chandran_Girish_(ETAS-ECMXPC-Yok1)|Chandran Girish (ETAS-ECM/XPC-Yok1)]]
> Hi [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]],
> 1. Yes, we do support 6b
> 2. 6b is not supported in 9.1.0 and AFAIK, backport effort is just too high as there is a lot of architectural changes. However, the service field colleagues did support some backport in past. So, maybe they could still help with this. 

-------

> [!note]+ 2025-11-20 09:45 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[Chandran_Girish_(ETAS-ECMXPC-Yok1)|Chandran Girish (ETAS-ECM/XPC-Yok1)]]  , Thanks for the info. Could you please confirm the following: 
>  # Can I take this in confidence that **we support 6b?**   
>  # Do we support 6b in older 9.1.0 ?  ( i.e. Classic OBD, OBDonUDS & ZEVonUDS ) 
>  # If not supported what is the effort involved to support it ? ( atleast a guestimate is required to communicate to the customer )

-------

> [!note]+ 2025-11-13 10:24 · [[Chandran_Girish_(ETAS-ECMXPC-Yok1)|Chandran Girish (ETAS-ECM/XPC-Yok1)]]
> hi [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]],
> Regarding the question in email 
> {quote}We would like to confirm whether the ETAS RTA-CAR protocol stack supports the following standards:
> SAE J1979:      Classical OBD
> SAE J1979-2:  OBDonUDS
> SAE J1979-3:  ZEVonUDS
> {quote}
>
> I can confirm that we support the specified standards. But, we do not support the regulatory requirement C7 as this is not released yet. And, we have to check if the requirement C6b is supported or not. 
>
> But, on a high level, yes we do support the Classic OBD, OBDonUDS as well as ZEVonUDS. 
>
> *EDIT*:
> Also, in the email conversation, as mentioned by CARIAD,
> {quote}Dear Sathish,
>
> China 6b --C6b: GB 18352.6-2016 
> China 7 -- C7: not published
> According to other colleagues’ experience, 
> C6b’s requirement should be similar to J1979, OBD Classic
> C7’s requirement should be similar to J1979-2 / J1979-3, OBD on UDS
> {quote}
>
> so, it seems like 6b and 7 are just related to the OBD classic and OBDonUDS and ZEVonUDS. So, then yes, this seems to be supported in our product. And please let me know if they got clear requirements at hand, which we could check together with our Diag colleagues and check if see any gaps.

-------

> [!note]+ 2025-11-13 06:50 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[Fargus_Alex_(MSETA)|Fargus Alex (MS/ETA)]] [[Chandran_Girish_(ETAS-ECMXPC-Yok1)|Chandran Girish (ETAS-ECM/XPC-Yok1)]] [[Mara_Sarath_(ETAS-ECMXPC-Yok1)|Mara Sarath (ETAS-ECM/XPC-Yok1)]]  Please find the attached document and clarification email from customer : 
>
> [^RE_ *ETAS* OBD 新标准支持问题确认.msg][^GB.18352.6-2016.pdf][^J1979-3_202310.pdf]

-------

> [!note]+ 2025-11-12 06:24 · [[Fargus_Alex_(MSETA)|Fargus Alex (MS/ETA)]]
> [[Chandran_Girish_(ETAS-ECMXPC-Yok1)|Chandran Girish (ETAS-ECM/XPC-Yok1)]][[Vo_Quang_Gia_Vinh_(MSETA-ARC-PF2)|Vo Quang Gia Vinh (MS/ETA-ARC-PF2)]] This is the need ticket for the analysis request I forwarded yesterday.
>
> Based on Sathish's point #1 please can you give me **a timeline** for determining:
>
> - Whether the RTA-CAR forward path supports the requested regulatory requirements and related SAE standards.
> - Whether the RTA-CAR 9.1.0 supports the requested regulatory requirements and related SAE standards.

-------

> [!note]+ 2025-11-12 05:36 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[Jain_Vihitha_(MSEMS-ETAS)|Jain Vihitha (MS/EMS-ETAS)]] [[Fargus_Alex_(MSETA)|Fargus Alex (MS/ETA)]] [[Chandran_Girish_(ETAS-ECMXPC-Yok1)|Chandran Girish (ETAS-ECM/XPC-Yok1)]] fyi 
>
> Could you please trigger an analysis task to understand the scope and effort for implementing the new requirements? 
>  # What are the new OBD requirements that needs to be implemented in our stack  ?
>  # What is the effort involved  for implementing in RTA-CAR 12.11.0 ?  and RTA-CAR 9.1.0 ? 
>
> Need to provide a reply to customer asap. kindly support. thanks 

-------

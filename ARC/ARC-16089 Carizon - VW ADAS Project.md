---
jira_key: ARC-16089
jira_url: "https://jira.etas-dev.com/browse/ARC-16089"
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
created: "2026-04-23T12:46:10.000+0000"
updated: "2026-09-03T15:58:37.000+0000"
synced-at: "2026-09-06T06:58:54.667Z"
jira-orphaned: true
---

# ARC-16089 Carizon - VW ADAS Project

> [!jira] New ·  · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] · 更新于 2026-09-03T15:58:37.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-16089)

## 描述

ECU : ADAS ECU 

Target : J6P 

currently under acquisition.  we have gathered some information from the customer. details in this [ECM_CN_Carizon_AUTOSAR_Classic_Requirements_V1.0_EN_From TAN.xlsx!link_attachment_7.gif!](https://jira.etas-dev.com/secure/attachment/776294/776294_ECM_CN_Carizon_AUTOSAR_Classic_Requirements_V1.0_EN_From+TAN.xlsx) \

Customer wants to know 

1. RTA-CAR BSW gap with the QLAH spec shared by VW
2. SSW integration support from ETAS. ( under negotiation )

## 评论

> [!note]+ 2026-09-03 15:58 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> I'm trying to understand how this motivation differs from ARC-6725 as both are for a Carizon ADAS ECU for VW on the same EE E3-1.2 platform. [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]  - any clue?

-------

> [!note]+ 2026-05-27 03:24 · [[Fargus_Alex_(MSETA)|Fargus Alex (MS/ETA)]]
> [[Chandran_Girish_(ETAS-ECMXPC-Yok1)|Chandran Girish (ETAS-ECM/XPC-Yok1)]]  Comment #6 is the request to analyse the IPv6 support.
>
> Despite the project being on hold, from discussions with [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]], the analysis is still needed, but with lower priority.
>
> Please can you plan a quick sweep to identify the requirements relating to Ethernet IPv6 only and if possible indicate whether we support them. If there are uncertainties then, with the breathing space while the project is on hold, we can pass the specific requirements to NETCOM for clarification.

-------

> [!note]+ 2026-05-25 07:25 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> latest updates from ETCN Sales team : 
>
> Carizon has put the project dev. **on hold** , due to change in scope and resp. more details here : [^RE_ Memo for Carizon E3_1_2 project alignment_-1.msg] 
>
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] fyi

-------

> [!note]+ 2026-05-25 01:27 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[Shukla_Siddharth_(ETAS-ECMXPC-Fe1)_X|Shukla Siddharth (ETAS-ECM/XPC-Fe1) [X]]]  thanks for the feedback. Do we have any prior integration experience in integrating CycurGATE into RTA-CAR for any customer projects? In CN hub we dont have that experience. 
>  * Any integration / test projects that we can look into and prepare in advance for this project? 
>  * We may need your team support w.r.t.  Firewall features and related to CycurGATE integ. 
>
> Thanks.

-------

> [!note]+ 2026-05-21 12:35 · [[Shukla_Siddharth_(ETAS-ECMXPC-Fe1)_X|Shukla Siddharth (ETAS-ECM/XPC-Fe1) [X]]]
> [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]  CycurGATE complies with the VW firewall requirement
> Normally this is sold separately for ethernet switches, but as we plan to integrate it into RTA-CAR for this project;  we may decide to not charge extra for this. [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]  Please decide on this

-------

> [!note]+ 2026-05-21 12:20 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[Shukla_Siddharth_(ETAS-ECMXPC-Fe1)_X|Shukla Siddharth (ETAS-ECM/XPC-Fe1) [X]]] reg. the below request from customer 
>
> {color:#0747a6}{*}ETH Firewall support{*}: MCU ETH have Firewall requirement, RTA-CAR ETH stack support Firewall configuration{color}
>  * 
>  ** do you know if this CycurGATE product is compliant to VW's Firewall requirements ?
>  ** do we sell CycurGATE license separately or included in RTA-CAR license model ?  
>
> could you please share ? thanks 

-------

> [!note]+ 2026-05-20 07:58 · [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]
> [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> While we do support IPv6, performing a proper gap analysis would require a detailed deep dive into the relevant specifications referenced here. 
> - 030_184_LAH.000.900.AE_IP-Kommunikation_DE_EN_V3.1
> - 030_191_LAH.DUM.909.M_Security_for_In-Vehicle_IP_Networking_EN_DE_V2.1
> - 030_197_LAH.DUM.909.P_IP_Network_Management_DE_EN_V1.5
>
> Given the breadth of the scope, the team would need some dedicated time for a comprehensive evaluation.
> At the moment, the team is also engaged with multiple ongoing analysis activities for other customers, including the current China escalations. 
>
> Therefore, I would like to seek support of the Analysis Team (AAA) team here. 
> [[Fargus_Alex_(MSETA)|Fargus Alex (MS/ETA)]] Could Analysis Team please take up this assessment?

-------

> [!note]+ 2026-05-20 05:51 · [[Weigl_Sandra_(ETAS-ECMXPC-Fe3)|Weigl Sandra (ETAS-ECM/XPC-Fe3)]]
>  Hi [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] 
>
> CycurGate I'm not an expert for CycurGate, it isn't part of the RT Security, [[Shukla_Siddharth_(ETAS-ECMXPC-Fe1)_X|Shukla Siddharth (ETAS-ECM/XPC-Fe1) [X]]] could you help regarding CycurGate?
>
>
>
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] , Carizon is already using CycurHSM SDK (including VKMS) on the Horizon J6

-------

> [!note]+ 2026-05-20 04:49 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> Carizon is doing the QLAH spec analysis. From our Sales team [[WU_Yanan_(ETASCCN1)|WU Yanan (ETAS/CCN1)]] , we understand that Carizon have identified the following features will be required for their VW project . 
>  # {color:#0747a6}{*}IPv6 support{*}: RTA-CAR ETH stack support IPV6 configuration {color}
>   - We support IPV6 in General. But I am not sure if there is any GAP in our RTA-CAR w.r.t. the VW QLAH spec [^030_Vernetzung.zip] [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]  do you know ?
> 1. {*}ETH Firewall support{*}: MCU ETH have Firewall requirement, RTA-CAR ETH stack support Firewall configuration
>  ** We have CycurGATE product for Firewall features. 
>  ** [[Weigl_Sandra_(ETAS-ECMXPC-Fe3)|Weigl Sandra (ETAS-ECM/XPC-Fe3)]] do you know if this CycurGATE product is compliant to VW's Firewall requirements ?
>  ** [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]  [[Weigl_Sandra_(ETAS-ECMXPC-Fe3)|Weigl Sandra (ETAS-ECM/XPC-Fe3)]]  do we sell CycurGATE license separately or included in RTA-CAR license model ?  
>  # **{color:#0747a6}Support import PDX/ODX file:{color}** RTA-CAR support seamless import PDX/ODX file
>  **  We already have ODX 2.2.0 importer support in our product. 
>  # {*}{color:#0747a6}TLT Adaptation{color}{*}: Development of a project-specific timestamp CDD and a TLT SWC interfacing with the ASW
>  ** This is an Engineering work . Need to check with SEF for support. 
>
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]  from the product pov, points 1 & 2 above carry the risk. We will try and push Carizon to share any specific gaps in advance and share with PF.  
>
> [[Burn_Alexander_(ETAS-ECMXPC-Yok1)|Burn Alexander (ETAS-ECM/XPC-Yok1)]] fyi

-------

> [!note]+ 2026-05-19 01:41 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> QLAH specs attached here [^030_Vernetzung.zip]

-------

> [!note]+ 2026-04-24 06:55 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> One thing that you need to be really careful with is VKMS. VW's security architecture  places a lot of obligations on the HSM firmware.
>
> At ETAS we have a VW-specific version of CycurHSM that includes support for VKMS features.
>
> For a fuller technical understanding here approach either [[Behl_Ashish_(ETAS-ECMXPC-Bo)|Behl Ashish (ETAS-ECM/XPC-Bo)]]  or [[Schran_Sven_(ETAS-ECMXPC-Fe3)|Schran Sven (ETAS-ECM/XPC-Fe3)]] .
>
> For the Horizon chips it will essential that the Horizon HSM supports all the VKMS features - and this is entirely the responsibility of Horizon to ensure that this is the case. If the Horizon HSM doesn't support the required features already then there will be no way to make a system work correctly.

-------

> [!note]+ 2026-04-24 06:41 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> All the projects we know that have used SSW using RTA-CAR have done this themselves. 
>
> Here is the content I provided to [[HUANG_Song_(ETASCCN1)|HUANG Song (ETAS/CCN1)]]  the last time we were asked abotu this:
>
> VW’s SSW comprises a set of modules from at least 3 different vendors (Akku, Elektrobit & Vector) and these have configuration/code generation tools that are shipped by VW as part of the SSW module bundle.
>
> Each SSW module includes AUTOSAR ParamDef files (as BSWMD files) that define the configuration parameters and can be imported into configuration tools that support ParamDef format descriptions. In the ETAS ecosystem this means importing them into ISOLAR-B. Here is what it looks like when I have imported the ParamDef file for SOK-FM and started a simple configuration task:
>
> ![[ARC-16089-SSW-in RTA-CAR.png]]
>
> This model is very similar to working with 3{^}rd{^} party MCALs where the MCAL provider ships some sort of code generator and a ParamDef file and loading the ParamDef file into ISOLAR-B allows users to configure the MCAL within our environment.
>  # **Workflow:** What is the standard workflow to configure VW SSW (specifically modules like SOK, VKMS) using ISOLAR-A/B?
>  ## Import the ParamDef files for each SSW module that you need to configure into ISOLAR-B. Use the ISOLAR-B editor to set the ECUC for the specific configuration
>  # **File Generation:** How do we generate the specific configuration headers (e.g., SokFm_Cfg.h)? Do we have a specific script/generator, or is there a manual configuration mapping process in ISOLAR?
>  ## Setup ISOLAR’s build hooks to call the relevant SSW generator. In the specific case on SOK-FM there is a CLI version of DaVinci that can be called
>  # **Reference:** Can you provide a reference case or documentation proving that we can fully integrate VW SSW independent of Vector's toolchain?
>  ## We have at least 20 current Bosch projects doing this and hundreds in the last that have integrated SSW with our stack. Garrett Motion did an AUDI project that user RTA-CAR and the SSW. And we are working with an engineering service partner called Realthinkgs who are building a reference integration platform for VW using the SSW and RTA-CAR.
>
> Note that the customer must use **generator tools** shipped with each SSW module (and because the SSW modules are built by multiple different suppliers then this means multiple tools) – see and overview here  [https://rtahotline.etas.com/confluence/pages/viewpage.action?pageId=203522152]
>
> But they can all be consistently **configured** in ISOLAR

-------

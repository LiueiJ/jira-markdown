---
jira_key: ARC-12589
jira_url: "https://jira.etas-dev.com/browse/ARC-12589"
server: etas
kind: motivation
type: Motivation
status: New
priority: ""
project: ARC
assignee: hut1yok
reporter: mas1yok
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2025-09-08T04:02:53.000+0000"
updated: "2026-06-05T02:58:30.000+0000"
synced-at: "2026-09-06T06:58:54.667Z"
jira-orphaned: false
---

# ARC-12589 HVR Solutions for Changan

> [!jira] New ·  · [[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]] · 更新于 2026-06-05T02:58:30.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-12589)

## 描述

**Changan's motivation:**

It is in the interests of multiple parties for China Changan to lead and assist OEMs in building the next-generation Domain control computing platform:

➢ For OEMs: The E/E architecture and application algorithms are the value of OEMs (Affecting driving experience and cost), while the computing platform is more of a cost than a value for OEMs (A large

amount of outsourcing is used). However, a good computing platform is of great significance for the Development of efficient controller products (a contradiction)

➢ For software suppliers and chip suppliers: The basic software application and development capabilities of OEMs are relatively weak, and there are great Challenges for software suppliers/chip suppliers

to provide support (There is a lack of connection in the middle)

2. As a leading enterprise in the industry, it is more convincing and influential for us to take the lead:

➢ On the one hand, the group has strong R&D potential and the ability to promote key technologies (There are technological challenges in the R&D of the next-generation computing platform). On the

other hand, the Group has been deeply involved in the product business of the power domain and chassis domain and has the ability to Fully verify the value of the key technologies of the domain

control computing platform.

➢ As a leading Tier 1 enterprise in China, leading the key technologies of the next-generation E/E architecture has a More exemplary role

 

For More details[CCAN-Hypervisor information.pdf!link_attachment_7.gif!](https://jira.etas-dev.com/secure/attachment/640904/640904_CCAN-Hypervisor+information.pdf)[CCAN-Hypervisor information.pdf!link_attachment_7.gif!](https://jira.etas-dev.com/secure/attachment/640904/640904_CCAN-Hypervisor+information.pdf)

**Opportunities** : 

1.  OS Porting 

2. HVR POC 

3. HVR Production Licenses.

## 评论

> [!note]+ 2026-06-05 01:56 · [[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]]
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] 
>
> In preparation for your visit to Chenzi, I'll outline what info I have in preparation for your visit.
>  * They're demo solution has (IIRC) 7 VMs on an S32E - 3 running RTA-CAR for chassis ECUs, and 4 running the NesSAR stack on body ECUs. They say the decision was made because it was cheaper and the body ECUs are only for QM/ASIL-B.
>  * They wanted another VM running a chassis ECU with an RTA-CAR stack, but there were issues with our single realtime interrupt support. We don't yet have any details but they said they'd give us some.
>  * Again, they insisted on having multiple realtime interrupts and it seems like a valid use-case. They're using brushless motors which have three currents and they need to process them in realtime via interrupts. VDEs won't work as the VMs are supposed to be black box SW from Tier 1s. It remains to be seen whether they can process all three properly in a single interrupt. This is difficult for us as multiple realtime interrupts makes it extremely difficult for safety.
>  * They explained the differences with the Vector solution. Interesting differences were
>  ** 1. Vector supports cross VM communication on the PDU level
>  ** 2. and Vector supports multiple realtime interrupts 
>  ** Other than that, they're solution sounds eerily similar to ours.
>  * The ETAS Sales Manager is pushing Chenzen to publicly demo the solution at ETAS connections, and again at a show next year (can't remember it).
>  * It seems they want to collaborate exclusively with ETAS for the Hypervisor.
>
> My (potentially naive) take on the business opportunity:
>  * Zonal controllers could run several RTA-CAR stacks on one controller. We'd also charge a fair bit for the Hypervisor platform. Open question for me is how we can push Tier 1s to use RTA-CAR in Zonal Controllers on top of our hypervisors.
>  * Chenzen is the Tier 1 for ChangAn, who are a state backed OEM already with global exports.
>  * Chenzen have invested 4-5 FTE since 2025 (so 1 year). The ETAS CN Sales Manager estimates it costs 500k RMB for one engineer per year so we can estimate their investment to be 250k€ - 320k€.
>  * The Sales Manager has quoted 90k€ for the ETAS HVR support, and ETCN will split the cost 50/50 so we should be getting 45k€ revenue, which should cover a large portion of the development cost for the realtime interrupt support.
>  * It's probably worth our team investing in our providing the required features for this demo.
>  * Additionally, it will help us come to a feature set and give us great sales and marketing material for the global product.
>
> FYI [[Bauer_Benedikt_(ETAS-ECMXPC-Fe1)|Bauer Benedikt (ETAS-ECM/XPC-Fe1)]] [[Hadley_Daniel_(ETAS-ECMXPC-Yok1)|Hadley Daniel (ETAS-ECM/XPC-Yok1)]] [[Burn_Alexander_(ETAS-ECMXPC-Yok1)|Burn Alexander (ETAS-ECM/XPC-Yok1)]] [[Alshabibi_Omar_(ETAS-ECMXPC-Wte)|Alshabibi Omar (ETAS-ECM/XPC-Wte)]] 

-------

> [!note]+ 2025-09-22 13:10 · [[Bray_George_(ETAS-ECMXPC-Yok1)_X|Bray George (ETAS-ECM/XPC-Yok1) [X]]]
> [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] do you have a figure in mind that you can entice Darren with? That will help with prioritisation.

-------

> [!note]+ 2025-09-22 12:32 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> How much additional RTA-CAR business is behind this work? It only makes sense to provide a HVR solution if we think that can be leveraged for stack sales.

-------

> [!note]+ 2025-09-19 03:04 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] [[Bray_George_(ETAS-ECMXPC-Yok1)_X|Bray George (ETAS-ECM/XPC-Yok1) [X]]]  - Chenzi Technology ( owned by Changan OEM ) has issues the Letter of Intent  [^定点通知书.pdf] . to buy our HVR solution.  [[Bray_George_(ETAS-ECMXPC-Yok1)_X|Bray George (ETAS-ECM/XPC-Yok1) [X]]]  a Visit to Changan is being planned between Oct 28 - 31 . We need to prepare for that visit & roadmap plans for the HVR solution

-------

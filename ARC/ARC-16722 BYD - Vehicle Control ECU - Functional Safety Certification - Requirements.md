---
jira_key: ARC-16722
jira_url: "https://jira.etas-dev.com/browse/ARC-16722"
server: etas
kind: motivation
type: Motivation
status: New
priority: ""
project: ARC
assignee: "[[Burn_Alexander_(ETAS-ECMXPC-Yok1)|Burn Alexander (ETAS-ECM/XPC-Yok1)]]"
reporter: "[[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]"
tags: []
fix-versions: []
epic: null
parent: null
created: "2026-06-24T02:46:06.000+0000"
updated: "2026-08-03T10:51:14.000+0000"
synced-at: "2026-09-11T01:13:09.700Z"
jira-orphaned: false
profile: CN Motivation
---

## 描述

Todo

1. Project FUSA Requirements :

BYD uses two versions of ETAS tools(CAR 9.2 and CAR 12.7) to develop VCU, and currently requires a functional safety certificate. The preliminary review by the functional safety certifier is that the OS certificate in the FSQP package is not recognized as an OS Software component package to specific compiler version + chips.

INFO: BYD has already purchased FSQP.

1. Customer expectation :

The initial information provided by the certification instructor is that the OS functional safety certificates should be consistent with those of Vector and generalization software. Specify the OS component packages for the ECU(U2B10+GHS) and compiler version.

1. Current status : ( what your plans / agreements with customer )

Validity period question: The validity period in FSQP 12.7 (ETAS release is 2026) causes confusion. Can BYD still use this certificate for functional safety certification in 2026?  ![[ARC-16722-image-2026-06-24-11-19-00-734.png]]

1. What support needed from PF :

1) Whether ETAS can provide a certification certificate for functional safety software component packages; certificates that are not TOOL concepts (OS, RTE, BSW) all display the word TOOL.

Other detailed evaluations await customer feedback.

## 评论

> [!note]+ 2026-07-30 10:37 · [[HE_Jiankang_(ETAS-ECMXSF-CN)|HE Jiankang (ETAS-ECM/XSF-CN)]]
> [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] [[Burn_Alexander_(ETAS-ECMXPC-Yok1)|Burn Alexander (ETAS-ECM/XPC-Yok1)]] 
>
> As per BYD and the third party (eg. Tuv) challenge the OS/rte/BSW not as software component according ISO26262. it was an tool qualification certification. 
>
> But till now. till today. no feedback from BYD&Tuv for this topic. So right now. there was just minor question like the certification validation data is very short. or other minor issues. so I do not update this topic. 
>
> If BYD&Tuv sign contract to do their product certificate, then it will come challenge question to us.  maybe like Changan too.

-------

> [!note]+ 2026-07-22 12:55 · [[Burn_Alexander_(ETAS-ECMXPC-Yok1)|Burn Alexander (ETAS-ECM/XPC-Yok1)]]
> [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] [[HE_Jiankang_(ETAS-ECMXSF-CN)|HE Jiankang (ETAS-ECM/XSF-CN)]] 
>
> I just stumbled across this, do you need some support?

-------

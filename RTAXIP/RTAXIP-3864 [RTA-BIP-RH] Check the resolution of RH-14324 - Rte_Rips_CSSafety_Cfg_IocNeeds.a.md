---
jira_key: RTAXIP-3864
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-3864"
server: etas
kind: motivation
type: Task
status: Closed
priority: Medium
project: RTAXIP
assignee: "[[Nguyen_Tran_Phuong_Nam_(MSETA-Hub-CN)|Nguyen Tran Phuong Nam (MS/ETA-Hub-CN)]]"
reporter: "[[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]"
tags: [jira/label/rta-bip-rh]
fix-versions: [RTA-BIP-cdes-tc397tk-1211]
epic: null
parent: null
created: "2026-07-09T04:38:40.000+0000"
updated: "2026-07-24T08:58:33.000+0000"
synced-at: "2026-09-11T02:40:28.533Z"
jira-orphaned: false
profile: CNN
---

## 描述

**Motivation**: [RH-14324](https://rtahotline.etas.com/jira/browse/RH-14324) is reported by our team and it is fixed in RTA-CAR 12.11

**TODO**:

- Need to be verified this issue again on RTA-CAR 12.11
- Update status the hotline ticket if it is fixed or not

Input:

- SW BIP base from: [RTAXIP-3886](https://jira.etas-dev.com/browse/RTAXIP-3886) &#91;RTA-BIP-12.11.0&#93;Porting to RTA-CAR 12.11.0
- feature/[RTAXIP-3886](https://jira.etas-dev.com/browse/RTAXIP-3886)-rta-bip-12110-porting-to-rta-car-12110

Output: 

- Verify if the resolution of RH ticket is yet available in RTA-CAR 12.11 and compatible to BIP

## 关联

- is satisfied by: [[RTAXIP-3893 [RTA-BIP-RH] Check the resolution of Hotline ticket planned in RTA-CAR 12.11]]
- is tracked by: [[RTAXIP-2678 [RTA-BIP] RTA-CAR Hotline issue list and tracking]]

## 评论

> [!note]+ 2026-07-23 10:19 · [[Nguyen_Tran_Phuong_Nam_(MSETA-Hub-CN)|Nguyen Tran Phuong Nam (MS/ETA-Hub-CN)]]
> **Issue Description:** RTA-BSW genertated Rte_Rips_CSSafety_Cfg_IocNeeds.arxml, missing OsIocDataProperties  is not generated for Rips_CSSafety
> Issue is solved in {*}RTA-CAR 12.11.0{*}, below error had been reported in **RH-14324** is now resolved when execute RTA-BSW gen step, no error is reported:
>
> The number of instances of element "OsIocDataProperties" in parent "/RTA_BIP/EcucModuleConfigurationValuess/Os/IocOs/Rte_Rips_CSSafety_CPT_SomeIpSDUT_CPT_BswM_BswMSwcGenericRequest_BswMSwcGenericRequest_FunctionParams" is less than the lower multiplicity of "1".
>
> ![[RTAXIP-3864-image-2026-07-23-17-15-34-013.png]]
>
> ![[RTAXIP-3864-image-2026-07-23-17-16-06-741.png]]
>
> The number of instances of element "OsIocDataProperties" in parent "/RTA_BIP/EcucModuleConfigurationValuess/Os/IocOs/Rte_Rips_CSSafety_CPT_SomeIpSDUT_CPT_BswM_BswMSwcGenericRequest_BswMSwcGenericRequest" is less than the lower multiplicity of "1".
>
> ![[RTAXIP-3864-image-2026-07-23-17-16-53-485.png]]
>
> ![[RTAXIP-3864-image-2026-07-23-17-17-25-246.png]]
>
> RTA_BSW gen log:
>
> [^rta-bsw.log]

-------

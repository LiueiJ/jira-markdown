---
jira_key: ARC-15467
jira_url: "https://jira.etas-dev.com/browse/ARC-15467"
server: etas
kind: motivation
type: Motivation
status: Canceled
priority: ""
project: ARC
assignee: hut1yok
reporter: rew1sgh
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2026-03-24T14:31:29.000+0000"
updated: "2026-09-03T15:52:00.000+0000"
synced-at: "2026-09-06T06:58:54.667Z"
jira-orphaned: true
---

# ARC-15467 VM-OSS China Local Airbag

> [!jira] Canceled ·  · [[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]] · 更新于 2026-09-03T15:52:00.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-15467)

## 描述

**Background**

Bosch VM plan to choose TMC THA6104/6102 for Local Airbag platform.

Target Chip: THA6104/ THA6102

Target Core: 

- Host Core, ARM Cortex-R52+, Compiler: greenhills comp_202314_bos_3fp_x64
- HSM Core, **ARM Cortex SC300,**  Compiler: greenhills_linux64_arm-2022.1.4

Expectation date:  2026/06/30

Task:

1. Update exist OS port:11173 RTA-OS THA6-R52-GHS V5.0.4.zip to support new variants;
2. Create new OS port to support HSM core (**ARM Cortex SC300**);

ETCN has used R52 GHS base port to develop the preview OS port which support THA6104 Host Core,

for more detail, please check with Allen's team. 

[[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]] [[Duong_Thi_Ngoc_(ETAS-ECMXPC-Yok1)|Duong Thi Ngoc (ETAS-ECM/XPC-Yok1)]]

Please support to estimate the cost and schedule.

**Products / use-cases**

Airbag

**OEMs**

COEM

**Competitors**

None

**RTA potential**

OS porting service fee,

HSM development fee,

Engineer service fee for BIP and FBL.

**ToDos**

 * !check.png! Fill out with ETCN hub.

 * !check.png! Check whether the motivation type is correct.

## 评论

> [!note]+ 2026-09-03 15:52 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> Bosch has lost the project (see comments ion linked OSS tickets)

-------

> [!note]+ 2026-04-01 13:38 · [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]]
> [[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]] 
>
> Could you support to creat sub-task ARC and OPP for HSM core？

-------

> [!note]+ 2026-04-01 07:54 · [[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]]
> [[Knarr_Michael_(ETAS-ECMXPC-Fe1)|Knarr Michael (ETAS-ECM/XPC-Fe1)]] Please could we estimate for both the host and HSM cores?

-------

> [!note]+ 2026-03-25 11:09 · [[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]]
> Estimation in progress.

-------

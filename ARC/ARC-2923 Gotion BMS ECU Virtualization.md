---
jira_key: ARC-2923
jira_url: "https://jira.etas-dev.com/browse/ARC-2923"
server: etas
kind: motivation
type: Motivation
status: Canceled
priority: ""
project: ARC
assignee: brg1yok
reporter: but9fe
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2024-02-21T16:00:43.000+0000"
updated: "2025-01-28T07:58:55.000+0000"
synced-at: "2026-09-08T02:03:07.632Z"
jira-orphaned: true
profile: CN Motivation
---

# ARC-2923 Gotion BMS ECU Virtualization

> [!jira] Canceled ·  · [[Bray_George_(ETAS-ECMXPC-Yok1)_X|Bray George (ETAS-ECM/XPC-Yok1) [X]]] · 更新于 2025-01-28T07:58:55.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-2923)

## 描述

**Background:** Gotion build a BMS and what to turn this into a VECU. Gotion use ETAS-VOS products already. The currently target TC2xx & TC3xx.

The want to move this into a FMU for SIL virtualization. They need to do ECU testing with Vector's Candela & Canoe.

**Other ETAS aspects:** ETAS-DEV are have a VECU-Builder & VNET for an acquisition  (needs otbe VNET becayse this can made to talk with CANOe in a way that doens;t yet work for BOA)

**Technical aspects:**

The MCAL parts that need to be virtualized are:

- Dio
- Port
- Pwm
- Can
- SPI
- Gpt

## 关联

- relates to: [[ARC-887 Strategic Partner - Cross ETAS SF]]

## 评论

> [!note]+ 2025-01-28 07:58 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> Actually this is old stuff - [[Rosing_Martin_(ETAS-ECMXPC-Fe4)|Rosing Martin (ETAS-ECM/XPC-Fe4)]]  was involved in the old ETAS-DEV org but we lost the opp in July. But it'd be worth a check with [[Rosing_Martin_(ETAS-ECMXPC-Fe4)|Rosing Martin (ETAS-ECM/XPC-Fe4)]] to dig into the details of what we might usefully need to support for other possible opps.

-------

> [!note]+ 2025-01-27 14:11 · [[Bray_George_(ETAS-ECMXPC-Yok1)_X|Bray George (ETAS-ECM/XPC-Yok1) [X]]]
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]], building on this, do we have a contact at Gotion? It would be good to know which version of VNET they care about.

-------

> [!note]+ 2025-01-27 10:10 · [[Bray_George_(ETAS-ECMXPC-Yok1)_X|Bray George (ETAS-ECM/XPC-Yok1) [X]]]
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]], thanks! The VNET part should be somewhat informed by ARC-4948.
>
> All the other MCALs are there already, just on an older AR version.

-------

> [!note]+ 2024-02-21 16:01 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> [[Bray_George_(ETAS-ECMXPC-Yok1)_X|Bray George (ETAS-ECM/XPC-Yok1) [X]]] - heads up!

-------

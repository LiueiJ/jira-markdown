---
jira_key: ARC-2055
jira_url: "https://jira.etas-dev.com/browse/ARC-2055"
server: etas
kind: motivation
type: Motivation
status: Canceled
priority: ""
project: ARC
assignee: but9fe
reporter: npr5kor
tags: [MCAL]
components: []
fix-versions: []
epic: null
parent: null
created: "2023-09-14T08:49:40.000+0000"
updated: "2025-07-13T19:36:46.000+0000"
synced-at: "2026-09-06T06:58:54.667Z"
jira-orphaned: false
---

# ARC-2055 MCAL for MotionSilicon

> [!jira] Canceled ·  · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] · 更新于 2025-07-13T19:36:46.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-2055)

> 标签：#jira/label/mcal

## 描述

Requestor: REN Wanwei (ETAS/SPA) <Wanwei.REN@bosch.com>

MCAL development for CN regional silicon vendor requested.

The main feature of chip is as follow:

- P/N:                      MX333
- Core:                    ARM Cortex-R52 Core
- Architecture:      1+1 DCLS mode or 2+0 Performance mode.
- FLASH:                 2MB Pflash, 512KB RAM.
- Complier:            Hightec (TBD)
- Chip FuSa:           ASIL D
- UM:                     CN version: draft version ready,Oct/23 official version and EN version: Nov/23 official version

- Debugger:           Lauterbach TRACE32 Ready
- EVB board:          Ready
- Sample code:      Ready
- MCAL AR Version：AR 4.4  (TBD)
- MCAL FuSa：     ASIL D
- MCAL Modules list：
- GPT Driver；WDG Driver；MCU Driver；Core Test(TBD)
- EEPROM Driver；Flash Driver；RAM Test(TBD)；Flash Test(TBD)
- Ethernet Driver；CAN Driver；LIN Driver；FlexRay Driver；SPI Driver
- PORT Driver、DIO Driver、ADC Driver、PWM Driver、ICU Driver、OCU Driver

Specifiction is available here [ MX333用户手册V0.3.pdf|https://bosch-my.sharepoint.com/:b:/r/personal/rew1sgh_bosch_com/Documents/99_Semi/%E6%91%A9%E8%8A%AF/MX333%E7%94%A8%E6%88%B7%E6%89%8B%E5%86%8CV0.3.pdf?csf=1&web=1&e=IUMWgM]

## 评论

> [!note]+ 2024-01-17 08:50 · [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]
> Hello [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] 
>
> Unfortunately the hub do not have much details on the business potential here.
>
> Feedback from CN hub - End Customer is still debating to deploy AutoSAR or not, request postponed.

-------

> [!note]+ 2024-01-02 15:20 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> Obviously MCALs are an engineering service rather than a product offering, but do we know how much potential AR stack business the existence of this MCAL is likely to generate? That would enable [[Kuerbitz_Michael_(ETAS-ECMPRM-SEF2)|Kuerbitz Michael (ETAS-ECM/PRM-SEF2)]] to decide if this is a business opportunity worth pursuing in preference to the other requests we have.

-------

---
jira_key: ARC-17430
jira_url: "https://jira.etas-dev.com/browse/ARC-17430"
server: etas
kind: motivation
type: Motivation
status: New
priority: ""
project: ARC
assignee: ams1wte
reporter: wny5sgh
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2026-08-26T02:04:30.000+0000"
updated: "2026-08-31T20:44:27.000+0000"
synced-at: "2026-09-08T02:03:07.632Z"
jira-orphaned: true
profile: CN Motivation
---

# ARC-17430 GAC RTA-SWITCH Requirements

> [!jira] New ·  · [[Alshabibi_Omar_(ETAS-ECMXPC-Wte)|Alshabibi Omar (ETAS-ECM/XPC-Wte)]] · 更新于 2026-08-31T20:44:27.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-17430)

## 描述

After we introduced our RTA-SWITCH solution, GAC's system architecture department expressed strong interest. Currently, under their GAC EEA 5.0 architecture, the NIDS functions are primarily deployed within the ECU. If our solution can fulfill their NIDS requirements directly on the switch, it would significantly reduce the network forwarding overhead in the ECU and greatly optimize the functional partitioning of their overall architecture.

HW: Realtek (the specific model has not been disclosed yet)

SOP: 2027

Find their specific requirements in the attached document

## 评论

> [!note]+ 2026-08-31 20:35 · [[Weber_Andreas_(ETAS-ECMXPC-Fe3)|Weber Andreas (ETAS-ECM/XPC-Fe3)]]
> Our diagnostic features are much better as described. We do not support some very easy checks (that would also be very fast to add) but we do support very detailed and complex checks for the actual services.
>
> Also we do have very good support for stateful TCP. I think the switch can achieve the requested features and more.

-------

> [!note]+ 2026-08-31 20:32 · [[Weber_Andreas_(ETAS-ECMXPC-Fe3)|Weber Andreas (ETAS-ECM/XPC-Fe3)]]
> As already shared by [[Alshabibi_Omar_(ETAS-ECMXPC-Wte)|Alshabibi Omar (ETAS-ECM/XPC-Wte)]]  in general, we do fulfill these requirements. 
>
> There is some possible things that we could improve or make some better documentation, also some feature are not supported in GUI.

-------

> [!note]+ 2026-08-31 20:28 · [[Weber_Andreas_(ETAS-ECMXPC-Fe3)|Weber Andreas (ETAS-ECM/XPC-Fe3)]]
> Detailed analysis attached. Please do not share with customer. If you want to share with customer, remove the ETAS internal column.

-------

> [!note]+ 2026-08-26 02:07 · [[WANG_Yiqiang_(ETAS-ECMXSF-CN)|WANG Yiqiang (ETAS-ECM/XSF-CN)]]
> [[Alshabibi_Omar_(ETAS-ECMXPC-Wte)|Alshabibi Omar (ETAS-ECM/XPC-Wte)]] [[Rudolph_Tobias_(ETAS-ECMXPC-Fe3)|Rudolph Tobias (ETAS-ECM/XPC-Fe3)]] 
>
> Hi Team, Could the product team help conduct a preliminary assessment to evaluate the feasibility of this approach?

-------

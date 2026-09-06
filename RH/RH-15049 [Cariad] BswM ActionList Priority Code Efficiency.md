---
jira_key: RH-15049
jira_url: "https://rtahotline.etas.com/jira/browse/RH-15049"
server: rtahotline
kind: hotline
type: Support
status: Waiting for Level 3
priority: High
project: RH
assignee: mrinal.kantisirkar@in.bosch.com
reporter: sisi.tao@bosch.com
tags: []
components: [System-InfraLib-Infrastructure]
fix-versions: []
epic: null
parent: null
created: "2026-02-04T04:40:35.000+0100"
updated: "2026-08-26T06:53:23.000+0200"
synced-at: "2026-09-06T06:58:38.472Z"
jira-orphaned: false
---

# RH-15049 [Cariad] BswM ActionList Priority Code Efficiency

> [!jira] Waiting for Level 3 · High · [[Mrinal_Kanti_Sirkar|Mrinal Kanti Sirkar]] · 更新于 2026-08-26T06:53:23.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-15049)

> 标签：#jira/comp/system-infralib-infrastructure

## 描述

Dear hotline colleague,

Our customer (using RTA-CAR 12.11.0VCTCESR1pr1) complain about **BswM_Prv_ProcessDeferredReqst** effiency.

In RTA-CAR 9.1 (last platform they used, there was no such loop).

![[RH-15049-image001.png]]

When Customer configured 64 LogicalExpressions for one rule and Action list, this loop runs 2016 times (show in following picture, customer add a counter) And it tooks more than 1ms for this loop. They complain about the efficiency and want a workaround today.

![[RH-15049-image002.png]]

 **Sisi TAO** 

Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

M +86 133 81555197 

[Sisi.TAO@bosch.com!mail_small.gif!](mailto:Sisi.TAO@bosch.com) 

ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

[www.etas.cn](http://www.etas.cn/)  **

ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2026-08-26 06:53 · [[Mrinal_Kanti_Sirkar|Mrinal Kanti Sirkar]]
> Hi [[Max_Sinclair|Max Sinclair]] ,
>
> I updated your requirement on [ARCSMIL-1956. ](https://jira.etas-dev.com/browse/ARCSMIL-1956)
>
> [[Thomas_Chippy|Thomas Chippy]]  Can you please comment on the customer's expected fixed version which is RTA-CAR 12.11

-------

> [!note]+ 2026-08-25 17:18 · [[Max_Sinclair|Max Sinclair]]
> Hi [[Mrinal_Kanti_Sirkar|Mrinal Kanti Sirkar]] ,
>
> The customer is looking for a new version of the BswM to be provided here.
>
> Can you provide an updated bswm that can be put into rta-car 12.11?
>
> Thanks,
> Max

-------

> [!note]+ 2026-08-25 12:37 · [[Jiaqi_JI|Jiaqi JI]]
> Hi [[Max_Sinclair|Max Sinclair]] ,
>
> We need the plugin on RTA-CAR 12.11.0.
>
> [[Phuong_Nguyen_Le|Phuong Nguyen Le]] Could your team take this ticket into investigation on RTA-CAR 12.11.0VCTCPR7.
>
> Thanks a lot!

-------

> [!note]+ 2026-08-25 12:33 · [[Max_Sinclair|Max Sinclair]]
> Hi [[Jiaqi_JI|Jiaqi JI]] [[Sisi_TAO|Sisi TAO]] ,
>
> I can see this ticket was reopened, is there any further help you need here etc?
>
> Thanks,
> Max

-------

> [!note]+ 2026-05-28 09:37 · [[Mrinal_Kanti_Sirkar|Mrinal Kanti Sirkar]]
> Hi [[Max_Sinclair|Max Sinclair]] ,
>
> Can you closed this ticket ?

-------

> [!note]+ 2026-04-24 14:04 · [[JSM_Service_Bot|JSM Service Bot]]
> [[Max_Sinclair|Max Sinclair]] this issue requires your attention.

-------

> [!note]+ 2026-03-13 12:54 · [[Mrinal_Kanti_Sirkar|Mrinal Kanti Sirkar]]
> Hi [[Max_Sinclair|Max Sinclair]] ,
>
> We created the Problem WI [ARCSMIL-1943](https://jira.etas-dev.com/browse/ARCSMIL-1943) on this.
>
> Regards,
>
> Mrinal

-------

> [!note]+ 2026-03-13 09:03 · [[Max_Sinclair|Max Sinclair]]
> Hi [[Mrinal_Kanti_Sirkar|Mrinal Kanti Sirkar]] ,
>
> Could you please add the ARC ticket for this feature improvement and confirm if this improvement will be put into the main bsw branch?
>
> Many thanks,
> Max

-------

> [!note]+ 2026-03-09 03:42 · [[Sisi_TAO|Sisi TAO]]
> Hi [[Mrinal_Kanti_Sirkar|Mrinal Kanti Sirkar]] 
>
> I'd like to know in which RTA-CAR release version will this code fixed? Is there any ARC ticket to follow?

-------

> [!note]+ 2026-03-05 07:34 · [[Mrinal_Kanti_Sirkar|Mrinal Kanti Sirkar]]
> Hi,
>
> Do you have any further point to discusstion?

-------

> [!note]+ 2026-02-26 08:38 · [[Mrinal_Kanti_Sirkar|Mrinal Kanti Sirkar]]
> Hi [[Sisi_TAO|Sisi TAO]] ,
>
> Please find the attached runtime-optimized code, which corresponds to the existing code from lines 230 to 244 (as illustrated in the attached image). We have also incorporated your suggestion to skip processing if all ActionLists are zero. Kindly review the runtime improvements in this code and provide your feedback.
>
>
>
> Regards,
>
> Mrinal
>
> [^RH-15049_Runtime_Optimized_Code.c]

-------

> [!note]+ 2026-02-26 08:37 · [[Mrinal_Kanti_Sirkar|Mrinal Kanti Sirkar]]
> [^RH-15049_Runtime_Optimized_Code.c]

-------

> [!note]+ 2026-02-24 10:28 · [[Max_Sinclair|Max Sinclair]]
> Hi [[Mrinal_Kanti_Sirkar|Mrinal Kanti Sirkar]] & [[S_P_Deepak|S P Deepak]] ,
>
> Any updates on this?
>
> Thanks,
> Max

-------

> [!note]+ 2026-02-10 14:26 · [[S_P_Deepak|S P Deepak]]
> Hello [[Mrinal_Kanti_Sirkar|Mrinal Kanti Sirkar]] ,
>
> Could you please check this at the earliest?
>
> Regards,
>
> Deepak S P

-------

> [!note]+ 2026-02-10 12:34 · [[Sisi_TAO|Sisi TAO]]
> Hi [[Max_Sinclair|Max Sinclair]]
>
> Is there any updates for this issue?

-------

> [!note]+ 2026-02-05 17:30 · [[Max_Sinclair|Max Sinclair]]
> Hi [[S_P_Deepak|S P Deepak]] ,
>
> Would you be able to take a look at this?
>
> Shouldn't the actionlists be already pre-sorted or similar, so in theory sorting shouldn't be required?
>
> Can you also take a look at the proposed workaround as well?
>
> Many thanks,
> Max

-------

> [!note]+ 2026-02-05 13:39 · [[Sisi_TAO|Sisi TAO]]
> We made code change as workaround for now. Need expert support and confirm. 
> [^BswM_Prv_ProcessDeferredRequest - Copy.c]
>
> The main changes are as follows:
>  # Added an array to cache the priority of all ActionLists and determine whether there is no priority configuration (0).
>  # If the priority of all ActionLists is 0, skip the bubble sort.
>  # If there is an ActionList with a priority other than 0, perform the bubble sort. However, since the sorting has been cached, there is no need to repeatedly execute `BswM_Prv_GetActionListPriority`

-------

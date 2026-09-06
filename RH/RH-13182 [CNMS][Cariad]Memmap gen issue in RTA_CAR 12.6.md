---
jira_key: RH-13182
jira_url: "https://rtahotline.etas.com/jira/browse/RH-13182"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Medium
project: RH
assignee: samuel.hutchings@etas.com
reporter: hao.tao2@etas.com
tags: []
components: [Communication-Can-Lin-Fr]
fix-versions: []
epic: null
parent: null
created: "2025-06-03T05:24:13.000+0200"
updated: "2026-03-08T08:36:37.000+0100"
synced-at: "2026-09-06T06:58:38.472Z"
jira-orphaned: false
---

# RH-13182 [CNMS][Cariad]Memmap gen issue in RTA_CAR 12.6

> [!jira] Closed · Medium · [[Sam_Hutchings|Sam Hutchings]] · 更新于 2026-03-08T08:36:37.000+0100
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-13182)

> 标签：#jira/comp/communication-can-lin-fr

## 描述

Hi, Hotline, 

I met a memmap gen issue as shown in the pics. I will share with you the project after getting JIRA ticket number, please help to check the issue, thanks. 

 ** Hao TAO** 

 ETAS-ECM/XSF-CN 

 

 M +86 199 72114034

## 评论

> [!note]+ 2025-08-19 18:02 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2025-08-05 17:26 · [[Sam_Hutchings|Sam Hutchings]]
> Hi [[Hao_TAO|Hao TAO]],
>
> I'm not sure why, but the xpt template file being passed in is not being accepted by MemMapGen. I can provide a workaround for now; using an RTAText-based template instead. I have attached the customer's converted .xpt file as well as the script I created to convert it below. The changes required are updating customerTemplate.txt to point to the new file, and change the input command for MemMapGen to:
> ```
> --armemmap_templates ./UserConfig/memmap/customerTemplate.txt
> ```
> This allows MemMapGen to generate as expected.
>
> Is this a suitable workaround for the customer, or do they require using .xpt files?
>
> Kind regards,
> Sam 
> [^memMapTranslator.py] [^CustomMemMap.rtatext]

-------

> [!note]+ 2025-08-05 15:02 · [[Sam_Hutchings|Sam Hutchings]]
> [[Marc_Kaiser|Marc Kaiser]] is this still being handled as a CNMS ticket?

-------

> [!note]+ 2025-06-26 10:28 · [[Mingye_YUAN|Mingye YUAN]]
> Hello Nikesh:
>
> Can you help to check this issue? Thanks

-------

> [!note]+ 2025-06-05 13:29 · [[Hao_TAO|Hao TAO]]
> Hi,
> Anyone can help to check this issue?

-------

> [!note]+ 2025-06-03 05:46 · [[Hao_TAO|Hao TAO]]
> Hi, Hotline,
>
> You can refer to the attached file for checking the issue reported.
>
> [^isolar_original.zip] *(105.09 MB)*

-------

> [!note]+ 2025-06-03 05:24 · [[Hao_TAO|Hao TAO]]
> ![[RH-13182-2025-06-03_10h29_09.png]]
>
> ![[RH-13182-2025-06-03_10h29_39.png]]

-------

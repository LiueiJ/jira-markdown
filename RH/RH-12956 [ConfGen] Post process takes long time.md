---
jira_key: RH-12956
jira_url: "https://rtahotline.etas.com/jira/browse/RH-12956"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Medium
project: RH
assignee: sisi.tao@bosch.com
reporter: sisi.tao@bosch.com
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2025-05-06T09:02:14.000+0200"
updated: "2026-05-21T11:09:09.000+0200"
synced-at: "2026-09-08T01:46:06.261Z"
jira-orphaned: false
profile: Cariad
---

# RH-12956 [ConfGen] Post process takes long time

> [!jira] Closed · Medium · [[Sisi_TAO|Sisi TAO]] · 更新于 2026-05-21T11:09:09.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-12956)

## 描述

Dear hotline colleague,

Tool Version: RTA-CAR 12.6.0

I’m doing ConfGen on RTA-CAR12.6.0. As you see in following screenshot, it takes 17 minutes for ConfGen to generate all files. Also Enhancer has finished. But it still stop at post process (position 90%) for more than 10 minutes. User can not do any operation during this phase. NoConfgen output files are not changed during this time at all.Only enabling rips is done during this phase, but I don’t think it shall take so long time I’d like to know is it possible to make this phase shorter. Thank you.

![[RH-12956-image001.png]]

 **Sisi TAO** 

Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

M +86 133 81555197 

[Sisi.TAO@bosch.com!mail_small.gif!](mailto:Sisi.TAO@bosch.com) 

ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

[www.etas.com](http://www.etas.com/)  **

ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2026-04-02 04:46 · [[Sisi_TAO|Sisi TAO]]
> Hi [[James_Butterfield|James Butterfield]] 
>
> Thank you very much for your detail information. Customer's project now is upgraded to RTA-CAR 12.11.0VCTCESR1pr1 now which is identical with 12.9. I believe the post processor runs faster. 

-------

> [!note]+ 2026-04-01 14:21 · [[James_Butterfield|James Butterfield]]
> Hi [[Sisi_TAO|Sisi TAO]],
>
> Apologies that this ticket has taken so long to be responded to during the CNMS / VNCNMS restructuring.
>
> I believe the reason ConfGen is taking so long to execute is due to the size of the System Description. Across all the files that go into making up the System Description, you end up with **over a million lines** of ARXML. This is a lot of configuration to process, so allowing a little extra time for ConfGen to run is likely expected here.
>
> Using the attached project, I did some testing on my machine across 3 different RTA-CAR versions:
>  * {*}12.6.0{*}: ConfGen takes around 14 minutes to complete, and an extra 5-6 minutes for the post-processor
>  * {*}12.9.0{*}: ConfGen takes around 9 minutes to complete, and an extra 1-2 minutes for the post processor (a significant improvement from 12.6.0)
>  * {*}12.10.0pr10 (pre-release){*}: ConfGen takes around 10 minutes to complete, and an extra 1-2 minutes for the post processor (around the same as 12.9.0, still significantly better than 12.6.0)
>
> Based on these results, it would appear that ConfGen has improved its efficiency since 12.6.0 (especially with the post processor time which you mentioned was causing the majority of the frustration). Therefore, I would suggest that you upgrade to a newer version of RTA-CAR to reduce the overall execution time of ConfGen.
>
> Please let me know if there is anything else I can help with!
>
> Best Regards,
> James

-------

> [!note]+ 2026-03-26 18:31 · [[Su_Nguyen_Quoc|Su Nguyen Quoc]]
> [Review queue/forward]
>
> Removed labels "VNCNMS", forward to PF/ Global team - needs to assign an assignee.

-------

> [!note]+ 2025-05-06 12:18 · [[Sisi_TAO|Sisi TAO]]
> Hi [[Hritik_Mehta|Hritik Mehta]]  Attached is the project. Thank you for your support
>
> [^Config.zip] *(30.40 MB)*

-------

> [!note]+ 2025-05-06 11:42 · [[Hritik_Mehta|Hritik Mehta]]
> Hi [[Sisi_TAO|Sisi TAO]].
>
> Please attach the RTA-CAR project so I can debug confgen and understand why it's taking such a long time.
>
> Thanks,
>
> Hritik

-------

---
jira_key: RH-12851
jira_url: "https://rtahotline.etas.com/jira/browse/RH-12851"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: High
project: RH
assignee: sisi.tao@bosch.com
reporter: sisi.tao@bosch.com
tags: [Cariad, NullPointerException]
components: [Generic-Importers]
fix-versions: [RTA-CAR 12.13.0]
epic: null
parent: null
created: "2025-04-18T08:54:06.000+0200"
updated: "2026-04-14T13:58:27.000+0200"
synced-at: "2026-09-06T06:58:38.472Z"
jira-orphaned: false
---

# RH-12851 [CONFGEN][12.6.0] CanFrameTriggering with extended CANID is not supported

> [!jira] Closed · High · [[Sisi_TAO|Sisi TAO]] · 更新于 2026-04-14T13:58:27.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-12851)

> 标签：#jira/comp/generic-importers #jira/label/cariad #jira/label/nullpointerexception

## 描述

Hi Marc,

Attached is the system extract from Cariad. 

Tool Version: RTA-CAR 12.6

When doing ConfGen on this extract, it failed when importing **the CCAN message C_Waehlhebel_06 whose CanID is 0x12dd54bf**. The error information is useless.

After I remove this frametriggering, ConfGen succeeds. You can see all frametriggerings (STANDARD and EXTEND message) share the same FramePort (same as Geely, they all use the same tool to generate System extract from Simens.) I think ConfGen doesn’t support this. Could you please analyze this issue?

By the way, they are using Renesas MCAL, for CanHardwareObject, CanIdType can be mixed.

**Sisi TAO** 

Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

M +86 133 81555197 

[Sisi.TAO@bosch.com!mail_small.gif!](mailto:Sisi.TAO@bosch.com) 

ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

[www.etas.com](http://www.etas.com/) **

ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2026-04-14 13:42 · [[Sisi_TAO|Sisi TAO]]
> Hi [[James_Butterfield|James Butterfield]] 
>
> Yeah, you can close this ticket as resolved. Thank you.

-------

> [!note]+ 2026-04-14 10:31 · [[James_Butterfield|James Butterfield]]
> Hi [[Sisi_TAO|Sisi TAO]],
>
> This feature will be supported in ConfGen from RTA-CAR 12.13.0 onwards and can be tracked by [ARC-15934](https://jira.etas-dev.com/browse/ARC-15934).
> Please let me know if there is anything you wish to add to this ticket, otherwise, let me know if you are happy for it to be marked as resolved. 
>
> Best Regards,
> James

-------

> [!note]+ 2026-04-14 03:47 · [[K_Raj_Kumar|K Raj Kumar]]
> Created change request [ARC-15934](https://jira.etas-dev.com/browse/ARC-15934) to support this feature in RTA-CAR 12.13.0 release. Best Regards, Rajkumar

-------

> [!note]+ 2026-03-26 17:19 · [[K_Raj_Kumar|K Raj Kumar]]
> [[Su_Nguyen_Quoc|Su Nguyen Quoc]] We will check this issue internally and get back you. 
>
> Best Regards, **Rajkumar**

-------

> [!note]+ 2026-03-26 16:49 · [[Su_Nguyen_Quoc|Su Nguyen Quoc]]
> [Review queue/forward]
> Is the problem solved? Is there a proposed solution?
>
> **Is it solved?** **No.**
>  * Ticket status: **Unresolved**
>
>  * Customer status: **Waiting for Support**
>
>  * **No assignee** (L2 / L3 both empty)
>
>  * Open for ~{*}48 weeks{*}
>
>  * No fix version, no delivery confirmation
>
> 👉 **Conclusion:** The problem is {*}not solved{*}.
>
> **Is there a proposed solution?** {*}Yes — two partially proposed solutions{*}, but {*}none implemented{*}.
>
> From the discussion:
>
> **1. Functional limitation confirmed**
>  * ConfGen **does not support mixed standard + extended CAN IDs in the same mailbox**
>  * This is confirmed by product engineer
>
> **2. Workaround proposed**
>  * Remove extended {{{}FrameTriggering{}}}, **or**
>  * Create another `FramePort` and assign extended frames separately
>
> **3. Product enhancement proposal**
>  * Enhance **ConfGen Mailbox algorithm from the ground up**
>  * Improve **error handling** (catch `NullPointerException` only, not all {{{}Exception{}}}s)
>  * Suggested target version: **12.7.0**
>
> ⚠️ However:
>  * No implementation committed
>  * No fix version assigned
>  * No concrete plan or timeline
>
> 👉 Conclusion{*}:{*}
> Solution direction exists, No delivered fix.
>
> {color:#0747a6}My comment (Su, L2 COEM lead):{color}
>
> I forward it to the Global FAE team and removed the **VNCNMS** label.

-------

> [!note]+ 2025-07-28 09:08 · [[Mingye_YUAN|Mingye YUAN]]
> Hello Marc,
>
> I am sorry I might confuse you with my sentences, I just want to check the progress based on your comments: "It looks like we have to enhance the ConfGen Mailbox algorithm from the ground up." since this ticket is in high priority. If there is any update, please let me know, thanks a lot.

-------

> [!note]+ 2025-07-24 13:32 · [[Marc_Kaiser|Marc Kaiser]]
> Hello [[Mingye_YUAN|Mingye YUAN]], I will be honest. We have not progressed on this yet. 
>
> But I have a good idea now.
>
> What I need is User-POV requirements for how the Can Mailbox Mapping should look like.
>
> If you are interested in contributing, could you write me a pseudo CFG where the mailbox assignments are done? Could you describe the functionality that you would like me to implement verbose, or with pseudo CFG?
>
> If you do that I could be much faster in implementing it because then its more concrete!

-------

> [!note]+ 2025-07-21 09:57 · [[Mingye_YUAN|Mingye YUAN]]
> Hello Marc:
>
> Can I know if there is any update fro ConfGen Mailbox algorithm? Thanks.

-------

> [!note]+ 2025-06-20 10:06 · [[Sathish_Kumar_Madanmohan|Sathish Kumar Madanmohan]]
> thanks [[Marc_Kaiser|Marc Kaiser]]  . much appreciate your swift response.

-------

> [!note]+ 2025-06-20 09:03 · [[Marc_Kaiser|Marc Kaiser]]
> Hello [[Sathish_Kumar_Madanmohan|Sathish Kumar Madanmohan]] and [[Sisi_TAO|Sisi TAO]],
>
> thank you for raising this to my attention again. I will now prioritze this topic and find a solution in ConfGen. It looks like we have to enhance the ConfGen Mailbox algorithm from the ground up.
>
> I will keep you up to date with updates.

-------

> [!note]+ 2025-06-19 07:44 · [[Sathish_Kumar_Madanmohan|Sathish Kumar Madanmohan]]
> [[Sam_Hutchings|Sam Hutchings]] [[Marc_Kaiser|Marc Kaiser]]  could you please provide the status update on this ticket ? has any solution / agreement reached in resolving it ?

-------

> [!note]+ 2025-04-23 14:46 · [[Kishan_Parmar|Kishan Parmar]]
> Hi [[Sam_Hutchings|Sam Hutchings]],
>
> Not much for me to add here. It is clear the error information is there but not being passed through. Going to forward on to [[M_S_Karthik|M S Karthik]] - do you what has changed in 12.6 to cause this?

-------

> [!note]+ 2025-04-22 05:14 · [[Sisi_TAO|Sisi TAO]]
> Hi [[Sam_Hutchings|Sam Hutchings]] ,
>
> Thank you very much for your researching. I highly recommend this issue could be resolved in 12.7.0 (and of course the exception issue) since I think it's a generic use case for different customers.
>
> We are now cooperating with customer EE architecture department about the compatibility of their system extract and ConfGen. In the previous platform project they were using DBC and going to switch to arxml. It would be great that these features could be improved in next version. It impacts our bidding of the next platform project.

-------

> [!note]+ 2025-04-21 15:43 · [[Sam_Hutchings|Sam Hutchings]]
> Hi [[Marc_Kaiser|Marc Kaiser]] and [[Sisi_TAO|Sisi TAO]],
>
> Yes Sisi you are right, ConfGen does not support mixed frame types in a single mailbox. The workaround here is to remove the extended {{{}FrameTriggering{}}}, or add another `FramePort` and assign the extended `FT` to that {{{}FP{}}}.
>
> ![[RH-12851-image-2025-04-21-14-01-30-058.png]]
>
> Since this is for Cariad, [[Marc_Kaiser|Marc Kaiser]] is this supposed to be modified in the general RTA-BSW code, or do Cariad get their own custom version?
>
> Regarding the error message, [[Nick_Lay|Nick Lay]] and [[Kishan_Parmar|Kishan Parmar]] I think this is the opposite of what we were aiming for with the null pointer exception fixes.
> Previously, only unhandled errors threw NPEs. When testing this in 12.6.0, I get the following, and I am concerned that we now catch *all errors* that are thrown instead of just logged, which is 168 across 83 files. This leaves the user completely in the dark, and will increase the load on the support teams.
> ![[RH-12851-image-2025-04-21-14-40-23-093.png]]
>
> I checked the source and this appeared in 12.5.0:
> ![[RH-12851-image-2025-04-21-14-41-51-434.png]]
> I think the solution here is to catch `NullPointerException`‎ s instead of all `Exception`‎ s. This should be a simple, easy win - any chance we can squeeze this into 12.7.0?
>
> Thanks, Sam

-------

> [!note]+ 2025-04-18 11:30 · [[Sam_Hutchings|Sam Hutchings]]
> Hi [[Marc_Kaiser|Marc Kaiser]],
>
> Is this a CNMS ticket?
>
> Thanks, Sam

-------

> [!note]+ 2025-04-18 08:54 · [[Sisi_TAO|Sisi TAO]]
> [^CDCU-CDCU-CDCU_2025_04_11.zip] *(1.77 MB)*

-------

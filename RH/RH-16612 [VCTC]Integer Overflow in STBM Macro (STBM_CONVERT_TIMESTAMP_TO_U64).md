---
jira_key: RH-16612
jira_url: "https://rtahotline.etas.com/jira/browse/RH-16612"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Medium
project: RH
assignee: jiaqi.ji@etas.com
reporter: jiaqi.ji@etas.com
tags: [Regional, VNCNMS]
components: [Communication-TimeServices]
fix-versions: []
epic: null
parent: null
created: "2026-07-10T10:25:14.000+0200"
updated: "2026-08-05T15:00:47.000+0200"
synced-at: "2026-09-08T01:46:06.261Z"
jira-orphaned: false
profile: Cariad
---

# RH-16612 [VCTC]Integer Overflow in STBM Macro (STBM_CONVERT_TIMESTAMP_TO_U64)

> [!jira] Closed · Medium · [[Jiaqi_JI|Jiaqi JI]] · 更新于 2026-08-05T15:00:47.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-16612)

> 标签：#jira/comp/communication-timeservices #jira/label/regional #jira/label/vncnms

## 描述

Hi Team, 

During debugging, an integer overflow issue was identified in  **STBM_CONVERT_TIMESTAMP_TO_U64**. When executing the multiplication: 

((TimeStamp).secondsHi) * STBM_S_PER_SECHI * STBM_NS_PER_SEC 

the intermediate result is evaluated as a  **u32** value. If the calculation exceeds  **0xFFFFFFFF**, the upper 32 bits of the expected  **u64** result are truncated. Consequently, the timestamp conversion result becomes significantly inaccurate, leading to a large timestamp deviation. 

![[RH-16612-image001.png]] 

![[RH-16612-image002.png]] 

The customer hopes that we can resolve this issue. Could you please help analyze it? Thank you! 

Best Regards, 

 ** Jiaqi JI** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 [Jiaqi.JI@etas.com!mail_small.gif!](mailto:Jiaqi.JI@etas.com) 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

 [www.etas.cn](https://www.etas.cn)  

  ** ETAS – Empowering Tomorrow’s Automotive Software**

## 关联

- relates to: [[RH-16818 [VNCNMS][ANY] Integer Overflow in STBM Macro (STBM_CONVERT_TIMESTAMP_TO_U32)]]

## 评论

> [!note]+ 2026-07-29 16:17 · [[Joao_Pereira|Joao Pereira]]
> Hello [[Phuong_Nguyen_Le|Phuong Nguyen Le]],
>
> Can you please create another ticket to track this topic and linked it with [https://jira.etas-dev.com/browse/RCI-171.]
> I would prefer to discuss the two topics seperatly. And we close this one. 

-------

> [!note]+ 2026-07-29 16:11 · [[Jens_Jung|Jens Jung]]
> Correction done by Defect-Fix (see links).

-------

> [!note]+ 2026-07-28 11:38 · [[Phuong_Nguyen_Le|Phuong Nguyen Le]]
> [[Joao_Pereira|Joao Pereira]] , Please help to check the finding for STBM_CONVERT_TIMESTAMP_TO_U32?

-------

> [!note]+ 2026-07-28 09:47 · [[Cuong_Phan_Manh|Cuong Phan Manh]]
> Hello [[Joao_Pereira|Joao Pereira]] ,
> I have some concern about STBM_CONVERT_TIMESTAMP_TO_U32, In fact, this macro will overflow in all cases because the result of STBM_S_PER_SECHI * STBM_NS_PER_SEC always exceeds UINT32_MAX? Is there any good solution at this time to provide customer?

-------

> [!note]+ 2026-07-22 08:36 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hi [[Jiaqi_JI|Jiaqi JI]] , [[Jie_LIU|Jie LIU]] 
> I have summarized the issue and proposed solutions for this ticket [^RH_16612.zip]. As bro [[Phuong_Nguyen_Le|Phuong Nguyen Le]] mentioned, please help us share the customer's feedback as soon as possible to add the fix into next plugin release!. 😊

-------

> [!note]+ 2026-07-21 11:19 · [[Phuong_Nguyen_Le|Phuong Nguyen Le]]
> [[Jiaqi_JI|Jiaqi JI]] , [[Jie_LIU|Jie LIU]] : We need to get feedback from customer soon if you want to add the fix into next plugin release!

-------

> [!note]+ 2026-07-20 07:00 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hi [[Prasad_Nandita|Prasad Nandita]] , [[Joao_Pereira|Joao Pereira]] 
>
> Thanks for your support. As confirmation [https://rtahotline.etas.com/jira/browse/RH-16612?focusedCommentId=705539&page=com.atlassian.jira.plugin.system.issuetabpanels:comment-tabpanel#comment-705539] from anh [[Phuong_Nguyen_Le|Phuong Nguyen Le]], our RCI team will provide the fix for customer.
>
> Hi [[Jiaqi_JI|Jiaqi JI]] , 
> As discussed, please help us provide the attached [^StbM_Priv.h] for customer and collect their test feedback/ test results. We will create the plugin and forward it to you later.

-------

> [!note]+ 2026-07-16 14:25 · [[Prasad_Nandita|Prasad Nandita]]
> [[Phuong_Nguyen_Le|Phuong Nguyen Le]]  defect fixes have been linked

-------

> [!note]+ 2026-07-15 16:41 · [[Jens_Jung|Jens Jung]]
> Correction by linked Defect-Fix.

-------

> [!note]+ 2026-07-15 09:31 · [[Phuong_Nguyen_Le|Phuong Nguyen Le]]
> [[Jiaqi_JI|Jiaqi JI]]  as we discussed [[Prasad_Nandita|Prasad Nandita]] , our RCI (RTA-CAR COEM integration) team will take this and provide the fix for you.
>
> As we delivered RTA-CAR12.11.0.VCTCESR1pr4 yesterday so that we plan to delivery this fix in RTA-CAR12.11.0.VCTCESR1pr5. 
>
> [[Jiaqi_JI|Jiaqi JI]] : Please help to check if there is any ticket need to fix and delivered together with this fix and share us! Then we will plan for RTA-CAR12.11.0.VCTCESR1pr5.
>
> [[Prasad_Nandita|Prasad Nandita]] : Can you plan and share ARC ticket to follow up as we expect you can take our solution and integrate into your develop stream?

-------

> [!note]+ 2026-07-14 10:35 · [[Jiaqi_JI|Jiaqi JI]]
> Hello [[Joao_Pereira|Joao Pereira]] ,
>
> We need the port for this change to **RTA-CAR 12.11.0** as customer will only use this version.
>
> Also, could you give us the planned date for the plugin release? Thanks a lot!
>
> cc [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]] [[Phuong_Nguyen_Le|Phuong Nguyen Le]] 

-------

> [!note]+ 2026-07-14 10:30 · [[Joao_Pereira|Joao Pereira]]
> Hello Khoa.
>
> The issue is confirmed. Since the intermediate value is not cast to uint64 the variable get's truncated.
> This applies for both secondsHi and seconds. 
>
> Can you please confirm if the port for this change to **RTA-CAR 12.11.0** is required, or if we can do the change on mainpath.

-------

> [!note]+ 2026-07-13 12:05 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hi [[Joao_Pereira|Joao Pereira]] , 
> The concern would be valid if the multiplication were evaluated using 32-bit arithmetic, since the intermediate result could overflow and {*}lose the upper bits before being converted to `uint64`{*}.
>
> ![[RH-16612-image-2026-07-13-17-00-25-852.png]]
>
> To avoid this error, I think we can convert the formula as below:
> --------------------------------------------------------------------------
> #define STBM_CONVERT_TIMESTAMP_TO_U64(TimeStamp) \
>     (((uint64)(TimeStamp).secondsHi * STBM_S_PER_SECHI * STBM_NS_PER_SEC) + \
>      ((uint64)(TimeStamp).seconds * STBM_NS_PER_SEC) + \
>      ((uint64)(TimeStamp).nanoseconds))
> --------------------------------------------------------------------------
> Could you help me check the proposed solution for this case or do you have any other solutions ?
>
> {+}*Note*{+}: The customer only uses \{*}RTA-CAR 12.11.0{*}, so we need to implement the bugfix for this version.

-------

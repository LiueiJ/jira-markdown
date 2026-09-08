---
jira_key: RTAXIP-3798
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-3798"
server: etas
kind: motivation
type: Story
status: Closed
priority: Medium
project: RTAXIP
assignee: gua6hc
reporter: tgu9hc
tags: [RTA-BIP-UC]
components: []
fix-versions: [RTA-BIP-cdes-tc397tk-1211, RTA-BIP-cdes-tc397tk-1290-r2.0]
epic: null
parent: null
created: "2026-06-25T04:11:10.000+0000"
updated: "2026-09-04T04:21:47.000+0000"
synced-at: "2026-09-08T01:46:31.431Z"
jira-orphaned: false
profile: CNN
---

# RTAXIP-3798 [BIP][12.9.0] Missing library inclusion for DoIP

> [!jira] Closed · Medium · [[Nguyen_Tran_Phuong_Nam_(MSETA-Hub-CN)|Nguyen Tran Phuong Nam (MS/ETA-Hub-CN)]] · 更新于 2026-09-04T04:21:47.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/RTAXIP-3798)

> 标签：#jira/label/rta-bip-uc

## 描述

**Context:**

RTA-BSW code generation for DoIP cannot work in BIP when using Greenhills compiler without extra manual modification. 

 

**Root cause:**

***DoIP_TCPConnection.h*** uses functions from ***DoIP_Connection.h***. 

 

**Doubt and assumption:**

Compilers like Tasking or ARM_FUSA doesn't have this error. I believe this due to compilation sequence order or optimization of these compilers, the issue may have been bypassed.

 

**Suggested fix:** Theoretically, this should be the correct, proper way to include the files:

- Add include "DoIP_Connection.h" before "DoIP_TCPConnection.h" in ***DoIP_Integration.h*** and ***DoIPUT.c***.

![[RTAXIP-3798-image-2026-06-25-14-42-56-233.png]]

 

**Remaining work:** 

Follow solution in: [RTAXIP-3883](https://jira.etas-dev.com/browse/RTAXIP-3883)

## 关联

- is satisfied by: [[RTAXIP-3883 [BIP][12.11.0] Missing library inclusion for DoIP]]

## 评论

> [!note]+ 2026-09-04 04:21 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]
> Done as this's done in RTAXIP-3883

-------

> [!note]+ 2026-06-25 09:11 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]
> Noted!!! this is IMPROVEMENT NEED for BIP but it's not impact or block BIP too much so that I set it in LOW priority

-------

> [!note]+ 2026-06-25 09:06 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]
> Please check [^RH-15628.pdf]
>
> Your suggestion is not good practice for BIP integration [[Nguyen_Minh_Tuan_(MSETA-Hub-CN)|Nguyen Minh Tuan (MS/ETA-Hub-CN)]]. 
>
> How about this solution "Using extern" for test purpose
>
> ![[RTAXIP-3798-image-2026-06-25-16-05-58-467.png]]

-------

> [!note]+ 2026-06-25 07:46 · [[Nguyen_Minh_Tuan_(MSETA-Hub-CN)|Nguyen Minh Tuan (MS/ETA-Hub-CN)]]
> Dear brother [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]] , please also have a check for this issue. Personally I think this fix is needed for BIP to avoid any future questioning.

-------

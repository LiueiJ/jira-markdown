---
jira_key: RTAXIP-3187
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-3187"
server: etas
kind: motivation
type: Story
status: Closed
priority: Medium
project: RTAXIP
assignee: "[[Phan_Huynh_Dang_Khoa_(MSETA-Hub-CN)|Phan Huynh Dang Khoa (MS/ETA-Hub-CN)]]"
reporter: "[[Phan_Huynh_Dang_Khoa_(MSETA-Hub-CN)|Phan Huynh Dang Khoa (MS/ETA-Hub-CN)]]"
tags: [jira/label/bip]
fix-versions: [RTA-BIP-cdes-tc397tk-1290-r1.0]
epic: null
parent: null
created: "2026-02-03T06:06:04.000+0000"
updated: "2026-07-07T11:48:48.000+0000"
synced-at: "2026-09-11T02:40:28.533Z"
jira-orphaned: false
profile: CNN
---

## 描述

### **Task's Objective**🎯

This ticket is created to check and resolve all ErrorHook issues after an ECU reset.

![[RTAXIP-3187-image-2026-02-03-10-52-18-242.png]]

### **Background**💡

+ Currently, when restart ECU, we found some ErrorHook as below. Following the first analysis, this issue come from change location of **the function NvM_ReadAll**

### **Inputs**

### 📂develop branch: [develop/rta-bip-cdes-tc397tk-1290](https://bitbucket.etas-dev.com/projects/RTAENG/repos/autosar_rta_xip/commits?until=refs%2Fheads%2Fdevelop%2Frta-bip-cdes-tc397tk-1290)

### **DoD**✅

- Analyze all ErrorHook after an ECU reset shall be done.
- PR is created to implement SW to resolve this issue.
- Update testcase to check this issue and upload test report
- Update requirement + user guideline (if necessary)

## 关联

- relates to: [[RTAXIP-3270 [RTA-BIP-UC] Revert NvM_ReadAll design (which reduce time for All NvM Block Read at startup phase)]]
- relates to: [[RTAXIP-3258 [RTA-BIP-UC] Revert NvM_ReadAll design (which reduce time for All NvM Block Read at startup phase)]]

## 评论

> [!note]+ 2026-03-05 03:23 · [[Phan_Huynh_Dang_Khoa_(MSETA-Hub-CN)|Phan Huynh Dang Khoa (MS/ETA-Hub-CN)]]
> The implementation PR has been approved and merged, so this task can be closed.
>
> Regarding the intend point, it will be updated in the task RTAXIP-3258 (in-progress).

-------

> [!note]+ 2026-02-23 12:29 · [[Phan_Huynh_Dang_Khoa_(MSETA-Hub-CN)|Phan Huynh Dang Khoa (MS/ETA-Hub-CN)]]
> Hello anh [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]] and anh [[Trinh_Xuan_Tao_(MSETA-Hub-CN)|Trinh Xuan Tao (MS/ETA-Hub-CN)]], could you help me review this task with the scope:
> + SW implementation
> + Test case, test report
> + User guideline
>
> Thank you so much!

-------

> [!note]+ 2026-02-05 05:02 · [[Phan_Huynh_Dang_Khoa_(MSETA-Hub-CN)|Phan Huynh Dang Khoa (MS/ETA-Hub-CN)]]
> [5/2]: Fix ErrorHook issue when calling NvM_IntegrationReadAll ==> **Re-design** the process handling of NvM_Integration_ReadAll
> Thanks to anh [[Trinh_Xuan_Tao_(MSETA-Hub-CN)|Trinh Xuan Tao (MS/ETA-Hub-CN)]] for your support. This issue is resolved.
>
> ![[RTAXIP-3187-image-2026-02-05-14-03-47-311.png]]
> ![[RTAXIP-3187-image-2026-02-05-14-05-15-094.png]]
> ![[RTAXIP-3187-image-2026-02-05-12-00-19-345.png]] 

-------

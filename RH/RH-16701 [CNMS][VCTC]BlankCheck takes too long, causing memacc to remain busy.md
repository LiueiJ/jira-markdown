---
jira_key: RH-16701
jira_url: "https://rtahotline.etas.com/jira/browse/RH-16701"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Critical
project: RH
assignee: "[[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]]"
reporter: "[[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]]"
tags: [jira/comp/memory-high-level, jira/label/vncnms]
fix-versions: []
epic: null
parent: null
created: "2026-07-19T09:02:56.000+0200"
updated: "2026-09-04T14:28:39.000+0200"
synced-at: "2026-09-10T03:48:22.681Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Hi hotline，

When the customer is using RTA-CAR 12.11.0 VCTCESR1pr1, they encounter some issues when using FEE. Please help me quickly troubleshoot.

After an unexpected error or a power loss causes a write failure, or when a BlankCheck is performed from the write-failure address to the end of the sector（128K）, the operation can take up to about 20 seconds. This makes **NvM/FEE/MemAcc** unavailable for a long time. The BlankCheck should not check from the failure position to the end of the sector; it should only check the length of the data that is going to be written.

![[RH-16701-image001.png]]

For **Question 1**, the operations are as follows:

1. In the current A-version software, the length of block ID 003 is **0x10**.
2. Write the A-version data for block 003 into the DFLASH.
3. Update the software to the B version, where the length of B-version block 003 changes to **0x100**.
4. In the B version, when writing block 003 data (length **0x100**), will it cause a write error, and thus trigger a BlankCheck?

For **Question 2**, the operations are as follows:

1. In the current A-version software, the length of block ID 003 is **0x100**.
2. Write the A-version data for block 003 into the DFLASH.
3. Update the software to the B version, where the length of B-version block 003 changes to **0x10**.
4. In the B version, when writing block 003 data (length **0x10**), will it cause a write error, and thus trigger a BlankCheck?

For **Question 3**: During the execution of **NvM_WriteAll**, if **NvM_Write/ReadBlock** and **NvM_SetRamBlockStatus** are interleaved, will this cause a lower-layer error, and thus trigger a BlankCheck?

For **Question 4**: During the execution of **NvM_WriteAll**, if **NvM_WriteAll** is called again, will this cause a lower-layer error, and thus trigger a BlankCheck?

For **Question 5**: The total DFLASH length is **1 MB**. The portion allocated to **NvM FEE** is **892 KB**, and the remaining part is customer-customized Flash. When the customer accesses the custom area, is it sufficient to only check whether **MemAcc** is in **Busy** status?

 

**Junsheng ZHANG** 

Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

M +86 155 32928056 

[Junsheng.ZHANG@bosch.com!mail_small.gif!](mailto:Junsheng.ZHANG@bosch.com) 

ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

[www.etas.cn](https://www.etas.cn/) **

ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2026-09-04 14:28 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2026-08-21 09:40 · [[Dang_Ho_Anh|Dang Ho Anh]]
> Thanks [[V_Venkatachalam|V Venkatachalam]] .
>
> Hi [[Dong_LIU|Dong LIU]] , please check the answer from Venkatachalam.

-------

> [!note]+ 2026-08-20 13:08 · [[V_Venkatachalam|V Venkatachalam]]
> Hi [[Dang_Ho_Anh|Dang Ho Anh]] ,
>
> Need to keep both MemIf_Rb_MainFunction() and NvM_MainFunction() in idle (common task) task to have synchronization which has dependency on placing the job and getting the job status.  
>
>
>
> Regards,
>
> Venki

-------

> [!note]+ 2026-08-19 05:16 · [[Dang_Ho_Anh|Dang Ho Anh]]
> [[Dong_LIU|Dong LIU]] , I just checked {{{}RTA-Mem_Stack_Reference_Guide_EN.pdf{}}}. It recommends that `MemIf_Rb_MainFunction()` and `NvM_MainFunction()` shall be mapped to the same task as below:
> ![[RH-16701-image-2026-08-19-10-12-55-321.png]]
> Hi [[Tobias_Ernst|Tobias Ernst]] , Could you please add your comments on these two questions?

-------

> [!note]+ 2026-08-19 04:57 · [[Dong_LIU|Dong LIU]]
> hello, [[Dang_Ho_Anh|Dang Ho Anh]] [[Tobias_Ernst|Tobias Ernst]] 
>
> The customer plans to place MemIf_Rb_MainFunction() in the IdleTask, but they have two questions:
>
> Do MemIf_Rb_MainFunction() and NvM_MainFunction() need to be placed together in the IdleTask, or is it sufficient to place only MemIf_Rb_MainFunction() in the IdleTask?
> If MemIf_Rb_MainFunction() is placed in the IdleTask while NvM_MainFunction() is executed every 10 ms, could this cause any synchronization issues?

-------

> [!note]+ 2026-08-12 08:40 · [[Dang_Ho_Anh|Dang Ho Anh]]
> Hi [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]] and [[JI_Jiaqi_(ETAS-ECMXSF-CN)|Jiaqi JI]] ,
>
> As [[Tobias_Ernst|Tobias Ernst]] 's comment, There will be no feature update related to this issue for Cariad, as described in the ticket [ARCMND-10987](https://jira.etas-dev.com/browse/ARCMND-10987) 
> Have you aligned this point with the customer and [Jain Vihitha (MS/EMS-ETAS) ?](mailto:Vihitha.Jain@etas.com)
> I'm not sure whether this has already been decided or concluded in another communication thread.

-------

> [!note]+ 2026-08-12 07:23 · [[Tobias_Ernst|Tobias Ernst]]
> There is no functional problem reported and a suitable corrective action was proposed (suitable scheduling).
> The priority was lowered from High to Low.

-------

> [!note]+ 2026-08-12 07:20 · [[Tobias_Ernst|Tobias Ernst]]
> Hello all,
> The statements related to NvM_WriteAll are right if there is no interrupt due to a reset.
> Of course, if there is a reset/power-down etc., then of course the execution is interrupted - that is common sense.
>
> After the reset the system does NOT continue were it was before the reset, but starts freshly - that is the intention of a reset.
>
> In general, if the block length is changed in a new SW, then the all writes of the blcok will happen with the new length.
> This is a valid situation and will not cause any error.
>
> Of course, if a block is potentially located at the end of the sector and cannot be written in a sector, then some cleanup action is needed to get some free space in a new sector. We call it doing a "reorganization". This action needs significant number of main-function-calls and thus delays the triggering write operation.
> That is the intended behavior.

-------

> [!note]+ 2026-08-12 05:25 · [[Cuong_Phan_Manh|Cuong Phan Manh]]
> Hello [[V_Venkatachalam|V Venkatachalam]] , [[Adrian_Funk|Adrian Funk]] 
>
> cc: [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]] , [[Dang_Ho_Anh|Dang Ho Anh]] 
>
> May I ask for an update on the status of this ticket? I noticed that ticket [ARCMND-10987](https://jira.etas-dev.com/browse/ARCMND-10987) has been canceled without a clear reason, and its current status is waiting for L3?

-------

> [!note]+ 2026-08-10 12:56 · [[Dang_Ho_Anh|Dang Ho Anh]]
> Hi [[V_Venkatachalam|V Venkatachalam]] ,
>
> Could you help check [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]] ’s concern?
>
> I also checked the AUTOSAR specification. When `NvM_WriteAll()` is being performed, no other job can interrupt it, except jobs for blocks configured with immediate priority ({{{}NvMBlockJobPriority = 0{}}}).
>
> ![[RH-16701-image-2026-08-10-17-55-47-471.png]]

-------

> [!note]+ 2026-08-03 12:55 · [[JSM_Service_Bot|JSM Service Bot]]
> [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]], the comment you've just made is internal. Please note that internal comments do not transition an issue to 'Waiting for Level 2'.

-------

> [!note]+ 2026-08-03 12:55 · [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]]
> Hi [[V_Venkatachalam|V Venkatachalam]] ,
>
> Our current testing and code analysis results are inconsistent with what you previously said. Once WriteAll is triggered, it will not be interrupted by the WriteBlock.
>
> From a code perspective, once WriteAll is handled, it will continue until completion, and WriteBlock can only be processed after it finishes.、
>
> ![[RH-16701-image-2026-08-03-18-56-59-876.png]]
>
> ![[RH-16701-image-2026-08-03-18-56-43-512.png]]

-------

> [!note]+ 2026-07-30 09:41 · [[Dang_Ho_Anh|Dang Ho Anh]]
> [[Dong_LIU|Dong LIU]] ,
>
> I saw [[V_Venkatachalam|V Venkatachalam]] has answered the question 4 and 5 in previous comment here, please check it:
> [https://rtahotline.etas.com/jira/browse/RH-16701?focusedCommentId=708716&page=com.atlassian.jira.plugin.system.issuetabpanels:comment-tabpanel#comment-708716] 

-------

> [!note]+ 2026-07-29 10:43 · [[JSM_Service_Bot|JSM Service Bot]]
> Note: Dang Ho Anh, V Venkatachalam added as watcher to the issue. Internal support agents cannot be added as Request Participants, so they have been automatically joined as Watchers instead.

-------

> [!note]+ 2026-07-29 10:43 · [[Dong_LIU|Dong LIU]]
> [[Dang_Ho_Anh|Dang Ho Anh]] [[V_Venkatachalam|V Venkatachalam]] The customer would like to confirm the following two questions:
>
> Question 4: During the execution of NvM_WriteAll, if NvM_WriteAll is called again, will this cause any lower-layer errors and consequently trigger a Blank Check?
>
> Question 5: The total size of the DFLASH is 1 MB, of which 892 KB is allocated to NvM Fee. The remaining space is used as customer-defined Flash. When the customer accesses the customer-defined Flash by directly calling the MemAcc interface (serialized with Fee operations), is it sufficient to only check whether MemAcc is in the Busy state? Is there any risk of write failure?

-------

> [!note]+ 2026-07-28 12:23 · [[Dang_Ho_Anh|Dang Ho Anh]]
> Hi [[V_Venkatachalam|V Venkatachalam]] and [[Raghavan_Shrivatsan|Raghavan Shrivatsan]]
>
> As the customer has tested by moving `MemIf_Rb_MainFunction()` to a background task, the  execution time has been significantly reduced from 20 seconds to 500 ms.
>
> However, I think this result was measured in an idle case, where the system did not have much workload. The above action is only a mitigation workaround at this time.
>
> We still need to address the final solution through the ticket [ARCMND-10987](https://jira.etas-dev.com/browse/ARCMND-10987) 

-------

> [!note]+ 2026-07-28 11:37 · [[JSM_Service_Bot|JSM Service Bot]]
> Note: Dang Ho Anh added as watcher to the issue. Internal support agents cannot be added as Request Participants, so they have been automatically joined as Watchers instead.

-------

> [!note]+ 2026-07-28 11:37 · [[Dong_LIU|Dong LIU]]
> [[Dang_Ho_Anh|Dang Ho Anh]] I just finished the test. Using Option 2, the execution time was reduced from 20 seconds to 500 ms.

-------

> [!note]+ 2026-07-27 11:37 · [[Dong_LIU|Dong LIU]]
> [[Dang_Ho_Anh|Dang Ho Anh]] The customer does not have the test environment available today. They will probably need to wait until tomorrow to set up the environment and start testing.

-------

> [!note]+ 2026-07-27 11:00 · [[Dang_Ho_Anh|Dang Ho Anh]]
> [[Dong_LIU|Dong LIU]]
>
> As you mentioned in your previous comment, “while `MemIf_Rb_MainFunction()` runs in a 1 ms background task.”
>
> This is not actually a background task. The function may be called every 1 ms because it is triggered by another 1 ms task. You can check in the software which task is triggering this task.
>
> The background task I mean is the one from my previous comment, the Option 2:
> [https://rtahotline.etas.com/jira/browse/RH-16701?focusedCommentId=709414&page=com.atlassian.jira.plugin.system.issuetabpanels:comment-tabpanel#comment-709414] 

-------

> [!note]+ 2026-07-27 10:47 · [[Dong_LIU|Dong LIU]]
> [[Dang_Ho_Anh|Dang Ho Anh]] `MemIf_Rb_MainFunction()` has always been configured to run in the background task. In Junsheng's previous test, it took around 20 seconds.

-------

> [!note]+ 2026-07-27 08:55 · [[Dang_Ho_Anh|Dang Ho Anh]]
> [[Dong_LIU|Dong LIU]] , Please start by testing it first with only `MemIf_Rb_MainFunction()` moved to the background task.

-------

> [!note]+ 2026-07-27 08:22 · [[V_Venkatachalam|V Venkatachalam]]
> Hi [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]] ,
>
> BlankCheck will not cause any error or any impact on NvM block data.
> `NvM_WriteAll` processes the selected NvM blocks sequentially. After each block is successfully written, it checks whether any single-block read or write request is pending.
>  * If a single-block request is pending, the corresponding single-block job will be processed first. Once completed, `NvM_WriteAll` will resume with the next block in the sequence.
>  * If no single-block request is pending, `NvM_WriteAll` will continue processing the next block directly.
>
> This behavior is expected and will not lead to any errors
>
>
>
> Regards,
>
> Venki

-------

> [!note]+ 2026-07-27 08:19 · [[Dang_Ho_Anh|Dang Ho Anh]]
> Hi [[Dong_LIU|Dong LIU]] I also do not think `NvM_MainFunction()` affects the blank check time.
> Hi [[Tobias_Ernst|Tobias Ernst]] , do you think so?

-------

> [!note]+ 2026-07-27 07:30 · [[Dong_LIU|Dong LIU]]
> [[Dang_Ho_Anh|Dang Ho Anh]] As discussed, we can move these two main functions to a background task to reduce the blank-check duration.
>
> I didn't fully understand the statement above. I don't think `NvM_MainFunction()` should affect the blank check time, should it?

-------

> [!note]+ 2026-07-27 07:28 · [[Dong_LIU|Dong LIU]]
> [[Dang_Ho_Anh|Dang Ho Anh]] NvM_MainFunction() runs in a 10 ms periodic task, while MemIf_Rb_MainFunction() runs in a 1 ms background task.

-------

> [!note]+ 2026-07-27 07:18 · [[JI_Jiaqi_(ETAS-ECMXSF-CN)|Jiaqi JI]]
> Hi [[Dong_LIU|Dong LIU]] ,
>
> As [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]]  is not available this week, please have a check on this ticket.
>
> Thanks a lot!

-------

> [!note]+ 2026-07-27 06:08 · [[Dang_Ho_Anh|Dang Ho Anh]]
> Hi [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]] ,
>
> What are the current task periods for `NvM_MainFunction()` and {{{}MemIf_Rb_MainFunction(){}}}?
>
> As discussed, we can move these two main functions to a background task to reduce the blank-check duration.
>
> Could you please test this approach on the customer side and share the results here?
> For the implementation details, we can discuss them if we encounter any blocking issues.

-------

> [!note]+ 2026-07-26 05:41 · [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]]
> Hi [[V_Venkatachalam|V Venkatachalam]] ,
>
> I have some additional questions regarding your responses to the items above.；
>
> **Answer 1 & 2:**
> It is always recommended to change the Persistent ID whenever the block length is modified.
>
> **The customer is mainly concerned about what will happen afterwards and whether blank check will occur.**
>
> **Answer 3:**
> NvM_WriteAll() can be preempted by a single block write or read request.
>
> **What happens if `NvM_WriteAll` is preempted? After being interrupted, does it stop writing altogether, or does it resume and continue `NvM_WriteAll` once the read/write request finishes?**
>
> **Also, can a `NvM_WriteAll` operation preempt a single-block write? In the scenarios described above, could it lead to any write errors or failures?**

-------

> [!note]+ 2026-07-25 15:28 · [[Tobias_Ernst|Tobias Ernst]]
> Yes Option 2 - running in the background (low-priority, but frequently scheduled) if nothing else is running.
> This of course only works if the system is not loaded by more than some 90%.
>
> But also the NvM_MainFunction should be in this task
>
> The only point which needs to be considered when switch to another OS mode during shutdown you have to ensure that this task is either continuing to be running or the end has to by snchronized with the OS mode switching
> (e.g. finish the task in the old mode  /   switch OS mode  / Start new background task again)

-------

> [!note]+ 2026-07-25 02:26 · [[Dang_Ho_Anh|Dang Ho Anh]]
> Hi [[Tobias_Ernst|Tobias Ernst]] ,
>
> When you mentioned the background task which will call {*}MemIf_Rb_MainFunction(){*}, I thought of two options to implement this type of task:
>
>     1. The task (with lowest priority) is activated by another high-frequency task, for example, a 1 ms task, using the function below to trigger the task:
>
> ![[RH-16701-image-2026-07-25-06-35-23-667.png]]
>
>     2. The task (with lowest priority) is activated once by an AutoStart task or by another function. At the end of this task, it chains to itself.
>
> ![[RH-16701-image-2026-07-25-07-12-30-420.png]]
>
> Which implementation are you referring to, or are you referring to another implementation approach?
>
> I have tested these two options with my test project: four Fee sectors, each 254 KB in size, with 8 bytes checked per blank check call.
>
> The time from the write request until the blank check is finished, after traversing the whole Fee sector, is around **42** seconds for Option 1 and around **1.3** seconds for Option 2.
>
> Option 2 seems more promising.

-------

> [!note]+ 2026-07-24 22:27 · [[Tobias_Ernst|Tobias Ernst]]
> Please change to a scheduling in the background task.
> The long latency always comes back to this issue.
> Scheduling in 10ms is never suitable.

-------

> [!note]+ 2026-07-24 08:07 · [[Dang_Ho_Anh|Dang Ho Anh]]
> Added comments from [[Raghavan_Shrivatsan|Raghavan Shrivatsan]]:
>
> "There is no cancel feature that stops ongoing operation abruptly. (also, it cannot be implemented as it would cause integrity failures)
>
> The timeout supervision feature is implemented at Fls/MemAcc layer has no impact here as the BlankCheck operation is performed in chunks and there is no limiting such operation.
>
> Thus, I don't see any existing solution for the problem. 
>
> The behavior is as per design. There are some solution possibilities ({_}like doing a binary search to see if a page is programmed rather than doing a blank check for remainder of the sector{_}) but needs to be suggested and approved by the product team.
>
> I have created a problem ticket for analysis. [ARCMND-10987](https://jira.etas-dev.com/browse/ARCMND-10987)
>
> Please sync with [@Jain Vihitha (MS/EMS-ETAS)](mailto:Vihitha.Jain@etas.com) for prioritization on product team side."

-------

> [!note]+ 2026-07-23 15:47 · [[Dang_Ho_Anh|Dang Ho Anh]]
> Hi [Shrivatsan.Raghavan@in.bosch.com](mailto:Shrivatsan.Raghavan@in.bosch.com) ,
>
> I have just been informed that [[V_Venkatachalam|V Venkatachalam]], will be on vacation until June 27.
>
> Could you please help investigate this issue in his absence?
>
> We have confirmed that a blank check is performed on a Fee sector when the corresponding header is missing from the FAT sector. This results in an excessively long blank-check duration.
>
> This issue is currently blocking the customer’s development activities, so we need to provide them solution to solve this issue.

-------

> [!note]+ 2026-07-23 15:04 · [[Phuong_Nguyen_Le|Phuong Nguyen Le]]
> [[V_Venkatachalam|V Venkatachalam]] , as Cariad's expecting our response today (23/7). Can you help to provide any solution to reduce time (20s)?

-------

> [!note]+ 2026-07-23 13:24 · [[Dang_Ho_Anh|Dang Ho Anh]]
> [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]] Please check the comment from [[V_Venkatachalam|V Venkatachalam]],
>
> Hi [[V_Venkatachalam|V Venkatachalam]] , It seems this issue is unavoidable. But it still blocking the customer’s development. 
>
> Can we plan a hotfix version for this issue and release it as an ESR version?
>
> CC: [[JI_Jiaqi_(ETAS-ECMXSF-CN)|Jiaqi JI]] , [[Phuong_Nguyen_Le|Phuong Nguyen Le]] 

-------

> [!note]+ 2026-07-23 12:10 · [[V_Venkatachalam|V Venkatachalam]]
> Hi [[Dang_Ho_Anh|Dang Ho Anh]] 
>
> FeeFs2 uses two types of sectors:
>  # FAT Sector – Contains the NvM block headers.
>  # DAT Sector – Contains the NvM block data.
>
> During power-up, th{*}e Fee_Init() fun{*}ction is executed. As part of the initialization, a BlankCheck is performed on the FAT sectors to identify the end of valid data and build the index for the NvM blocks.
>
> During Fee_Init(), the DAT sectors are not scanned using BlankCheck to determine the end of data. Instead, the BlankCheck for DAT sectors is performed during the first write operation.
>
> In the project scenario, the BlankCheck is triggered on the first write after power-up. When the first write request is issued, _rba_FeeFs2_Prv_DatWrCpyDo_Transfer()_ executes the BlankCheck-before-write sequence. Since the target pages still contain residual data from the interrupted operation, the write request fails with MEMIF_JOB_FAILED. If the issue is not caused by a wordline error, the execution enters the code section you highlighted, which then scans the sector until it reaches the end. This behavior is expected and is the reason for the observed delay in the project.
>
> **Answer 1 & 2:**
> It is always recommended to change the Persistent ID whenever the block length is modified.
>
> **Answer 3:**
> NvM_WriteAll() can be preempted by a single block write or read request.
>
> **Answer 4:**
> A new NvM_WriteAll() request will not be accepted if another NvM_WriteAll() operation is already in progress.
>
> **Answer 5:**
> Checking the MemAcc status is appropriate and recommended.
>
> Regards,
>
> Venki

-------

> [!note]+ 2026-07-22 13:46 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi [[V_Venkatachalam|V Venkatachalam]], this Memory High-Level ticket requires an assignee. As the component lead for Memory High-Level, please ensure that the 'Level 3 Assignee' field is set to the appropriate person that can handle this issue.

-------

> [!note]+ 2026-07-22 13:46 · [[Dang_Ho_Anh|Dang Ho Anh]]
> Hi [Venkatachalam V (MS/EMT5-ETAS)](https://confluence.etas-dev.com/display/~ven6cob),
>
> Below is the summary of the ticket so far:
>  * The customer is using `MemAcc` and `FeeFs2` for their project on {{{}RTA-CAR 12.11.0 VCTCESR1pr1{}}}, which is based on {{{}RTA-CAR 12.9.0{}}}.
>  * The failed case can be reproduced as follows:
>  ** Request to write an Nv block.
>  ** When the data on the DAT sector has been reprogrammed, but the info on the FAT sector has not been reprogrammed yet, perform an ECU reset.
>  * After the reset, the unexpected behavior is that the software performs a blank check for the whole Fee sector. This may take up to 20 seconds on the customer side, which means that no memory job can be requested during this time.
>
> I have reproduced the issue on my side, as it is inconvenient to debug on the customer’s side.
>
> I observed that `rba_FeeFs2_Prv_Dat_st.xWrCpy_st.state_en == RBA_FEEFS2_PRV_DAT_WRCPY_FINDEOD_E` throughout this blank check process because of the code below:
> ![[RH-16701-image-2026-07-22-18-47-46-691.png]]
>
> The customer is waiting for our official feedback before EOD on 7/23.
>
> Since I can reproduce the issue on my side, please feel free to contact me anytime if you need to debug the issue or get more information. In the meantime, I will do a deep dive into debugging.
>
> This is the record of the issue from customer's side and my side:  [^RH-16701_IssueRecord.zip]
>
> Thanks in advance.
>
>
> ![[RH-16701-image-2026-07-22-18-47-46-691.png]]

-------

> [!note]+ 2026-07-22 10:38 · [[Dang_Ho_Anh|Dang Ho Anh]]
> Dear All,
>
> The issue has recently been under discussion with Junsheng.
>
> We will provide an update on the outcome — either a solution or escalation to the L3 team — by the end of the day.
>
> Thank you for your cooperation.

-------

> [!note]+ 2026-07-20 10:10 · [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]]
> Hi [[Dang_Ho_Anh|Dang Ho Anh]] ,
>
>     TC499,MemAcc provided by the BSW

-------

> [!note]+ 2026-07-20 10:01 · [[Dang_Ho_Anh|Dang Ho Anh]]
> Hi [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]] ,
>
> Which target are you working on? TC4xx, ...?
>
> Are you using MemAcc provided by the BSW or by the MCAL?

-------

> [!note]+ 2026-07-20 09:51 · [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]]
> Hi [[Dang_Ho_Anh|Dang Ho Anh]] ,
>
>     I can’t share the client’s engineering work with you, but FS2’s project should have this issue.

-------

> [!note]+ 2026-07-20 09:42 · [[JI_Jiaqi_(ETAS-ECMXSF-CN)|Jiaqi JI]]
> Hi [[Dang_Ho_Anh|Dang Ho Anh]] ,
>
> After check with [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]] , we cannot share the project due to compliance reason~ Thanks!

-------

> [!note]+ 2026-07-20 07:36 · [[Dang_Ho_Anh|Dang Ho Anh]]
> Hi [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]] ,
> Could you share the project with us for further investigation?

-------

> [!note]+ 2026-07-19 09:06 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Junsheng ZHANG. Your issue is set to "Critical" priority.
> Please ensure that there is a reasonable justification for this listed in the issue description, otherwise the priority may be reviewed and adjusted during triage.
> Kind regards

-------

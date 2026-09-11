---
jira_key: RH-15049
jira_url: "https://rtahotline.etas.com/jira/browse/RH-15049"
server: rtahotline
kind: hotline
type: Support
status: Waiting for Level 3
priority: High
project: RH
assignee: "[[Kanti_Sirkar_Mrinal_(MSEMT4-ETAS)|Mrinal Kanti Sirkar]]"
reporter: "[[TAO_Sisi_(ETAS-ECMXSF-CN)|Sisi TAO]]"
tags: [jira/comp/system-infralib-infrastructure]
fix-versions: []
epic: null
parent: null
created: "2026-02-04T04:40:35.000+0100"
updated: "2026-09-10T10:34:28.000+0200"
synced-at: "2026-09-11T01:13:17.157Z"
jira-orphaned: false
profile: Cariad
---

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

> [!note]+ 2026-09-10 10:32 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Darren Buttle]]
> If you're going to keep the sort and do some form of patching then there is a much more efficient way to implement the sort by:
>  * realizing that after each outer loop pass the biggest value is at the end of the array -> so by induction you can shorted the search space in the inner loop each time
>  ** Pass 0 - end element =  biggest --> ignore next time
>  ** Pass 1 - end element = biggest; end -1 element = second biggest --> so ignore both next time
>  ** Pass 2 - end element = biggest; end -1 element = second biggest; end -2 element = third biggest  --> so ignore all 3 next next time
>  ** etc etc etc
>  * realizing that if you do a pass and haven't swapped anything then you can stop because its sorted.
>
> A quick google gave me this bit of examplar code:
>
> `/* An optimized version of Bubble Sort*/`
> `void bubbleSort(int arr[], int n){`
> `    int i, j;`
> `    bool swapped;`
> `    for (i = 0; i < n - 1; i++) {`
> `        swapped = false; /* variable to check if we can stop */`
> {{{}        for (j = 0; j < n - i - 1; j++) { /* Note the loop guard with "{}}}{{{}j < n - i - 1{}}}{{{}" that shortens number of times we do the inner loop */{}}}
> `            if (arr[j] > arr[j + 1]) {`
> `                swap(&arr[j], &arr[j + 1]);`
> `                swapped = true; /* we did a swap - so keep going */`
>                         }
>
>                  }
>
> `        /* If no two elements were swapped by inner loop then its now sorted so we can break */`
> `        if (swapped == false)`
> `            break;`
>     }
>
> }
>
> This will also be efficient for the case where all elements have identical priority zero since the "swapped" variable would not get set to "true" in the inner loop so the sort terminates after 1 iteration of the outer loop. So for the customer problem when they have all zero priorities this is even more optimal then their cache priorities and then don't do the loop if all are zero (because it also saves the space to store the cache and the time to fill it)

-------

> [!note]+ 2026-09-10 06:31 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Phuong Nguyen Le]]
> [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Sathish Kumar Madanmohan]] : May I understand your that: We don't need to integrate their suggestion for the PR7 but we need to share to customer these messages:
>
> 1) We can confirm their code change can work well with their use case is "allZero priority Action Lists" --> They can change the code manually by themself as workaround now.
>
> 2) We need time to give 'Proper' solution and provide the solution later.
>
> ??

-------

> [!note]+ 2026-09-10 06:16 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Sathish Kumar Madanmohan]]
> I agree to [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Darren Buttle]] 's inputs. Hence I pinned it. 
>  # We need to apply the right solution in the next release- to ensure we covered CARIAD
>  # We need to evaluate >> Ordering the list during code generation phase<< asap and document that. 
>  ## It will be very helpful if we can share the proper solution proposal with the customer - just to show we can do better & build the proper solution than what they had suggested - It will highlight that we are competent and professional org. and we take customer feedback very seriously and build a 'Proper' solution. 
>  ## We must change the mindset of the customer from being critical about everything they find -> collaborative partner and they should feel positive & confident to share feedback. 
>  ## If we simply implement what customer suggested -> We are no different to other local CP suppliers in customers eyes. Then next time customer will prefer local supplier. That is the harsh reality 

-------

> [!note]+ 2026-09-10 05:54 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Phuong Nguyen Le]]
> Thank for [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Darren Buttle]] 's sharing! It's a great idea to order the list of rule in code generation phase as we can order the list base on the referred Actionlist's priority.
>
> [[Kanti_Sirkar_Mrinal_(MSEMT4-ETAS)|Mrinal Kanti Sirkar]] : How do you think?
>
> Additionally for planning:
>  * {*}For Long-term solution{*}: We can keepto apply customer's solution for the PR7 version firstly to satisfy the Cariad's usecases (as all priority is 0). How do you think [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]] , [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Sathish Kumar Madanmohan]]
>  * {*}For Long-term solution{*}: We need to analyze and apply Darren's idea.
>  ** [[Jain_Vihitha_(MSEMS-ETAS)|Vihitha Jain]]: Can you team plan to check and apply this idea in short time?

-------

> [!note]+ 2026-09-09 14:57 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Darren Buttle]]
> So a few observations from my side:
>  * Our code
>  ** Calling a function in a loop is usually a bad code smell. Doing it twice just stinks
>  *** Two calls to BswM_Prv_GetActionListPriority() inside a doubly nested loop where each loop is controlled by a 16-bit value means in the worst case we're calling that function 65536^2 x 2 = **8+ billion times**  :-O
>  *** This is embarrassingly awful code - the customer must think we're idiots
>  ** I'm guessing we don't see BSWM_MAX_NO_OF_RULES set very high in practice (and I assume we know how big this is at code generation time) but even so this is going to be really inefficient for low numbers of rules
>  * Customer's code
>  ** Caching the priority list is a good space/time tradeoff here
>  ** I'm guessing the "allZero" guard is misleading - I'd assume this needs to be strengthened to "allIdenticalPriority" as we'd not need to sort in that case either
>  *** I'd then question what we're doing with [ARCSMIL-1956](https://jira.etas-dev.com/browse/ARCSMIL-1956) and just doing what a customer has asked us instead of thinking about the problem
>
> **But....** I'd like to understand why we cannot just generate a priority sorted list of rules at code generation time? Don't we know statically via configuration which requests are deferred processing? We could then avoid lot of runtime overhead( code, data & time).

-------

> [!note]+ 2026-09-09 14:21 · [[Jain_Vihitha_(MSEMS-ETAS)|Vihitha Jain]]
> [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Phuong Nguyen Le]] : Thanks for the proposals!
>
> **1) Short-term for VCTC Pr7 plugin:**
> COEM team will fix it as suggestion in this hotline,
>
> {color:#57d9a3}Agreed(y){color}
>
> **2) Long-Term:** for official delivery. There are 2 options
> 1) the BswM RT need to provide the official solution (conan package)
>
> 2) If BswM RT can't provide the official solution, we need you to review the code changes.
>
> The code shared was actually reviewed and adapted by [[Kanti_Sirkar_Mrinal_(MSEMT4-ETAS)|Mrinal Kanti Sirkar]] . {color:#172b4d}BswM RT shall plan the official solution in the forward path(12.14.0) which would be same or close to the already shared patch. Hence, a review of the code changes can be done for the VCTC specific delivery.{color}
>
> {color:#172b4d}Additionally, do you have some measurements to verify the improvements in runtime after the update? {color}

-------

> [!note]+ 2026-09-09 11:59 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Phuong Nguyen Le]]
> [[Jain_Vihitha_(MSEMS-ETAS)|Vihitha Jain]] , We are planning to deliver a ESR for CARIAD on Sep/25th as the preview plugin on RTA-CAR 12.11. This is my plan
>
> **1) Short-term for VCTC Pr7 plugin:**
> COEM team will fix it as suggestion in this hotline,
>
> **2) Long-Term:** for official delivery. There are 2 options
> 1) the BswM RT need to provide the official solution (conan package)
> 2) If BswM RT can't provide the official solution, we need you to review the code changes.
>
> [[Jain_Vihitha_(MSEMS-ETAS)|Vihitha Jain]] : Please share your suggestion for official delivery to Cariad

-------

> [!note]+ 2026-09-09 11:42 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Sathish Kumar Madanmohan]]
> [[Jain_Vihitha_(MSEMS-ETAS)|Vihitha Jain]] appreciate your support. But I think you misunderstand the situation. it is not the patch ETAS shared with customer. It is the code correction customer applied, and Customer shared it with ETAS. it is other way around. 
>
> so, Customer is the one asking us - How long will it take for ETAS to accept that simple change and include it in the BSW.  That is the point of contention.  
>
> also, in broader terms - planning is always done by PF . agreeing on feature implementation / roadmap is all great but backlogging defect fixes / quality issues for future roadmap - customer may not accept that all the time.  This issue - according to customer is not improvement - but a quality issue as it was affecting the ECU performance. 
>
> [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Phuong Nguyen Le]] [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]] [[JI_Jiaqi_(ETAS-ECMXSF-CN)|Jiaqi JI]]  please align with [[Jain_Vihitha_(MSEMS-ETAS)|Vihitha Jain]] on the timeline of 12.11. PR7 . 
>
> [[Lan_Tran|Lan Tran]] fyi

-------

> [!note]+ 2026-09-09 10:58 · [[Jain_Vihitha_(MSEMS-ETAS)|Vihitha Jain]]
> [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Sathish Kumar Madanmohan]] : Just looking at the comments, the request was to plan the topic in forward path! I hope you agree that this is not a defect and was not automatically planned for a specific branch. I would request that {+}before sharing any patch directly to the customer{+}, kindly ensure that the proper planning is done together with the PF team.
>
> In this case, PF is not denying to take over the change but it was never planned for RTA-CAR 12.11.0 specific release.
>
> Kindly share the planning for next RTA-CAR rel based on 12.11.0 or an ESR on RTA-CAR 12.11.0 for CARIAD to help me check for the feasibility. I figure the code changes itself is not a problem since its available.

-------

> [!note]+ 2026-09-09 09:42 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Sathish Kumar Madanmohan]]
> [[Jain_Vihitha_(MSEMS-ETAS)|Vihitha Jain]]  - Customer has already shared the code change required. They are already using the change and using in their ECU testing.  It will be very hard to convince customer why the change cannot be applied.
>
> Can you please provide a clear response like as to why the customer shared code section cannot be applied ? Any risk we see in their proposal? if so, what is that? we need to feedback customer with clear response and why it will take 12.14.0 . Customer is expecting in 12.11. itself
>
> simply citing this change as 'improvement' will not acceptable. This code has big impact on the performance as whole. So this will be challenged by CARIAD for sure.
>
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Darren Buttle]] fyi.

-------

> [!note]+ 2026-09-09 09:30 · [[Jain_Vihitha_(MSEMS-ETAS)|Vihitha Jain]]
> [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Sathish Kumar Madanmohan]] : The improvement will be planned for the forward path 12.14.0, linked the ticket [ARCSMIL-1956.](https://jira.etas-dev.com/browse/ARCSMIL-1956) 
>
> FYI [[Thomas_Chippy|Thomas Chippy]] for consideration in PI26.4

-------

> [!note]+ 2026-09-07 06:44 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Sathish Kumar Madanmohan]]
> [[Kanti_Sirkar_Mrinal_(MSEMT4-ETAS)|Mrinal Kanti Sirkar]] [[Thomas_Chippy|Thomas Chippy]]  
>
> dear both, I trust you are aware of the problem . Customer has proposed a solution for performance improvement which you can find it in [^RH-15049_Runtime_Optimized_Code.c] . customer is wondering if there is any reason why ETAS cannot implement the change in the product ? 
>
> [[Vihitha_Jain|Vihitha Jain]]  to me this change should be applied . our original code is not performant. If you take a look into the for loop you shall know it. This ticket has been ongoing for months now.  
>
> could you please check on that.  Thanks 

-------

> [!note]+ 2026-08-26 06:53 · [[Kanti_Sirkar_Mrinal_(MSEMT4-ETAS)|Mrinal Kanti Sirkar]]
> Hi [[Max_Sinclair|Max Sinclair]] ,
>
> I updated your requirement on [ARCSMIL-1956. ](https://jira.etas-dev.com/browse/ARCSMIL-1956)
>
> [[Thomas_Chippy|Thomas Chippy]]  Can you please comment on the customer's expected fixed version which is RTA-CAR 12.11

-------

> [!note]+ 2026-08-25 17:18 · [[Max_Sinclair|Max Sinclair]]
> Hi [[Kanti_Sirkar_Mrinal_(MSEMT4-ETAS)|Mrinal Kanti Sirkar]] ,
>
> The customer is looking for a new version of the BswM to be provided here.
>
> Can you provide an updated bswm that can be put into rta-car 12.11?
>
> Thanks,
> Max

-------

> [!note]+ 2026-08-25 12:37 · [[JI_Jiaqi_(ETAS-ECMXSF-CN)|Jiaqi JI]]
> Hi [[Max_Sinclair|Max Sinclair]] ,
>
> We need the plugin on RTA-CAR 12.11.0.
>
> [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Phuong Nguyen Le]] Could your team take this ticket into investigation on RTA-CAR 12.11.0VCTCPR7.
>
> Thanks a lot!

-------

> [!note]+ 2026-08-25 12:33 · [[Max_Sinclair|Max Sinclair]]
> Hi [[JI_Jiaqi_(ETAS-ECMXSF-CN)|Jiaqi JI]] [[TAO_Sisi_(ETAS-ECMXSF-CN)|Sisi TAO]] ,
>
> I can see this ticket was reopened, is there any further help you need here etc?
>
> Thanks,
> Max

-------

> [!note]+ 2026-05-28 09:37 · [[Kanti_Sirkar_Mrinal_(MSEMT4-ETAS)|Mrinal Kanti Sirkar]]
> Hi [[Max_Sinclair|Max Sinclair]] ,
>
> Can you closed this ticket ?

-------

> [!note]+ 2026-04-24 14:04 · [[JSM_Service_Bot|JSM Service Bot]]
> [[Max_Sinclair|Max Sinclair]] this issue requires your attention.

-------

> [!note]+ 2026-03-13 12:54 · [[Kanti_Sirkar_Mrinal_(MSEMT4-ETAS)|Mrinal Kanti Sirkar]]
> Hi [[Max_Sinclair|Max Sinclair]] ,
>
> We created the Problem WI [ARCSMIL-1943](https://jira.etas-dev.com/browse/ARCSMIL-1943) on this.
>
> Regards,
>
> Mrinal

-------

> [!note]+ 2026-03-13 09:03 · [[Max_Sinclair|Max Sinclair]]
> Hi [[Kanti_Sirkar_Mrinal_(MSEMT4-ETAS)|Mrinal Kanti Sirkar]] ,
>
> Could you please add the ARC ticket for this feature improvement and confirm if this improvement will be put into the main bsw branch?
>
> Many thanks,
> Max

-------

> [!note]+ 2026-03-09 03:42 · [[TAO_Sisi_(ETAS-ECMXSF-CN)|Sisi TAO]]
> Hi [[Kanti_Sirkar_Mrinal_(MSEMT4-ETAS)|Mrinal Kanti Sirkar]] 
>
> I'd like to know in which RTA-CAR release version will this code fixed? Is there any ARC ticket to follow?

-------

> [!note]+ 2026-03-05 07:34 · [[Kanti_Sirkar_Mrinal_(MSEMT4-ETAS)|Mrinal Kanti Sirkar]]
> Hi,
>
> Do you have any further point to discusstion?

-------

> [!note]+ 2026-02-26 08:38 · [[Kanti_Sirkar_Mrinal_(MSEMT4-ETAS)|Mrinal Kanti Sirkar]]
> Hi [[TAO_Sisi_(ETAS-ECMXSF-CN)|Sisi TAO]] ,
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

> [!note]+ 2026-02-26 08:37 · [[Kanti_Sirkar_Mrinal_(MSEMT4-ETAS)|Mrinal Kanti Sirkar]]
> [^RH-15049_Runtime_Optimized_Code.c]

-------

> [!note]+ 2026-02-24 10:28 · [[Max_Sinclair|Max Sinclair]]
> Hi [[Kanti_Sirkar_Mrinal_(MSEMT4-ETAS)|Mrinal Kanti Sirkar]] & [[Deepak_S_P_(MSEMT4-ETAS)|S P Deepak]] ,
>
> Any updates on this?
>
> Thanks,
> Max

-------

> [!note]+ 2026-02-10 14:26 · [[Deepak_S_P_(MSEMT4-ETAS)|S P Deepak]]
> Hello [[Kanti_Sirkar_Mrinal_(MSEMT4-ETAS)|Mrinal Kanti Sirkar]] ,
>
> Could you please check this at the earliest?
>
> Regards,
>
> Deepak S P

-------

> [!note]+ 2026-02-10 12:34 · [[TAO_Sisi_(ETAS-ECMXSF-CN)|Sisi TAO]]
> Hi [[Max_Sinclair|Max Sinclair]]
>
> Is there any updates for this issue?

-------

> [!note]+ 2026-02-05 17:30 · [[Max_Sinclair|Max Sinclair]]
> Hi [[Deepak_S_P_(MSEMT4-ETAS)|S P Deepak]] ,
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

> [!note]+ 2026-02-05 13:39 · [[TAO_Sisi_(ETAS-ECMXSF-CN)|Sisi TAO]]
> We made code change as workaround for now. Need expert support and confirm. 
> [^BswM_Prv_ProcessDeferredRequest - Copy.c]
>
> The main changes are as follows:
>  # Added an array to cache the priority of all ActionLists and determine whether there is no priority configuration (0).
>  # If the priority of all ActionLists is 0, skip the bubble sort.
>  # If there is an ActionList with a priority other than 0, perform the bubble sort. However, since the sorting has been cached, there is no need to repeatedly execute `BswM_Prv_GetActionListPriority`

-------

---
jira_key: RH-15717
jira_url: "https://rtahotline.etas.com/jira/browse/RH-15717"
server: rtahotline
kind: hotline
type: Analysis Request
status: Waiting for Level 3
priority: Medium
project: RH
assignee: "[[Chandran_Girish_(ETAS-ECMXPC-Yok1)|Girish Chandran]]"
reporter: "[[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]]"
tags: [jira/comp/communication-eth]
fix-versions: [RTA-CAR 12.13.0]
epic: null
parent: null
created: "2026-04-09T16:08:43.000+0200"
updated: "2026-09-10T10:36:49.000+0200"
synced-at: "2026-09-11T01:13:17.157Z"
jira-orphaned: false
profile: Cariad
---

## 描述

**Issue Summary**

After the production line performs multiple resets on `CDCU_MCU` by service `0x1101`, the air-conditioning function may fail intermittently. The observed SOME/IP-SD symptom is that `RDCU (172.20.1.32)` continues to send `OfferService` for service `0x2001`, but the expected `SubscribeEventgroup` from `CDCU_MCU (172.20.1.33)` is missing.

This issue has customer-visible functional impact because the air-conditioning function may remain unavailable until the system is reset again.

**Customer-Visible Symptom**

- Intermittent air-conditioning function failure after repeated `CDCU_MCU` reset on the production line.

- `RDCU (172.20.1.32)` sends `OfferService` for `0x2001`.

- The expected `CDCU_MCU (172.20.1.33) -> RDCU (172.20.1.32)` `Subscribe` for `0x2001` is not observed.

- In the same capture, `CDCU_SOC (172.20.1.45) -> CDCU_MCU (172.20.1.33)` subscription for `0x200D` is normal.

- Other SOME/IP services from `CDCU_MCU` to `LDCU` can still complete the normal `Offer -> Subscribe -> SubscribeAck` flow.

**Impact**

- The failure is intermittent and difficult to detect in advance.

- The affected service does not recover automatically in the packet-loss scenario described below.

- A reset can restore function temporarily, but this is not an acceptable recovery mechanism for production vehicles.

**Affected Nodes and Service**

- Provider: `RDCU (172.20.1.32)`

- Consumer: `CDCU_MCU (172.20.1.33)`

- Related normal reference flow: `CDCU_SOC (172.20.1.45) -> CDCU_MCU (172.20.1.33)` for service `0x200D`

- Affected service: `0x2001`

**Expected Behavior**

When `CDCU_MCU` receives the `OfferService` for `0x2001`, it should send the corresponding `SubscribeEventgroup` to `RDCU`, receive `SubscribeAck`, and recover the required function even if the ECU has just been reset.

**Actual Behavior**

During the failure scenario, `CDCU_MCU` receives the `OfferService` but the expected `SubscribeEventgroup` for `0x2001` is not successfully completed. As a result, no `SubscribeAck` is received and the dependent function remains unavailable.

**Evidence From Vehicle Test and DLT Analysis**

Based on combined vehicle testing and DLT investigation, the most likely sequence is:

1. During `CDCU_MCU` initialization, the ECU receives a service offer from the provider with a TTL of `3 s`.

2. `CDCU_MCU` attempts to send the service subscription.

3. Because the network is unstable during initialization, the subscription message may fail to reach the provider.

4. `CDCU_MCU` waits for `SubscribeAck`, but the provider does not respond because it never received the subscription.

5. The provider continues sending periodic `OfferService` messages at roughly `1 s` intervals.

This explains why the log can show repeated offers while the required subscription is still not restored.

**Technical Root Cause**

The root cause is in the subscription retry condition implemented in `Sd_MsgInterpreter.c`.

In the current logic, subscription retry is enabled only when:

- `SdSubscribeEventgroupRetryMax` is greater than zero, and

- the received `OfferService` carries `WILDCARD_TTL (0xFFFF)`

The current condition is:

```c

if ((SD_ZERO != Sd_CurrInst_pcst&#91;IdxInstance_uo&#93;.nrSubscribeRetryMax_u8) &&

(WILDCARD_TTL == lClntSrvInstAdm_pst->TTLCounter_u32))

{ lClntSrvInstAdm_pst->isRetry_b = TRUE; }

else

{ lClntSrvInstAdm_pst->isRetry_b = FALSE; }

```

Because the observed offer TTL is `3 s` instead of `0xFFFF`, the retry flag is not enabled. Therefore, if the initial subscribe message is lost during the unstable initialization window, the retry mechanism does not take effect.

**Why the Function Does Not Recover Automatically**

In this scenario, the issue is not limited to a single packet loss event. The real functional problem is that the software does not re-trigger the subscription after the first failure unless another reset occurs.

As a result:

- the provider continues sending offers,

- the consumer continues waiting for an acknowledgement that will never arrive,

- and the function remains unavailable without reset-based recovery.

**Risk Assessment**

- This is a production-relevant issue because it can affect customer-visible vehicle functions.

- The trigger depends on a timing window during initialization and is therefore intermittent.

- Once triggered, the failure can persist until another reset is performed.

**Reference to RTA-CAR 12 Behavior**

According to the available reference, the corresponding logic in `RTA-CAR 12` has already removed the condition:

```c

WILDCARD_TTL == lClntSrvInstAdm_pst->TTLCounter_u32

```

This indicates that newer code no longer restricts retry activation to wildcard-TTL offers only.

**Requested Product-Team Confirmation**

Please confirm the following points:

1. Whether applying the same retry-condition change to `RTA-CAR 9.1.0` is technically valid and safe.

2. Whether this change is the officially recommended fix direction for the customer project.

3. What official customer-facing statement should be provided regarding root cause and corrective action.

**Conclusion**

This issue is most likely caused by a subscription retry design limitation in the current `RTA-CAR 9.1.0` implementation. When the initial `SubscribeEventgroup` for service `0x2001` is lost during the unstable network window after `CDCU_MCU` reset, the retry mechanism is not activated because the received offer TTL is not `WILDCARD_TTL (0xFFFF)`. As a result, the function may remain unavailable until another reset occurs.

 

 **Jie LIU** 

Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

M +86 138 16227585 

[Jie.LIU8@etas.com!mail_small.gif!](mailto:Jie.LIU8@etas.com) 

ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

[www.etas.cn](http://www.etas.cn/)  **

ETAS – Empowering Tomorrow’s Automotive Software**

## 关联

- relates to: [[RH-16250 VM CEA1.0 Socket connection status abnormal switching]]
- is blocked by: [[RHC-674 VW CEA1.0 SOA issues on Production Line]]

## 评论

> [!note]+ 2026-09-10 10:35 · [[Shweta_Ganesh_Dixit|Shweta Ganesh Dixit]]
> [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Phuong Nguyen Le]]: You are partly correct, SD code generation generates duplicate macros with different values without any warning or error.
>
> To add this error/warning to inform the user, we need to make sure that the parameters which have *Symbolic Name = TRUE* are checked for uniqueness and this needs to be handled in the code generation tool. Let us wait for [[Chandran_Girish_(ETAS-ECMXPC-Yok1)|Girish Chandran]] to comment on this ticket. 

-------

> [!note]+ 2026-09-10 08:42 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Phuong Nguyen Le]]
> [[Nandita_Prasad_(MSEMS-ETAS)|Prasad Nandita]]: I believe the root issue is not duplicated short names themselves, as this does not violate any AUTOSAR requirement. The problem is that the SD code generation tool generates duplicate macros with different values without any warning or error. 
>
> The VCTC configuration fix only resolves the issue for that specific project. Since the tool behavior remains unchanged, the same issue can still occur in other VCTC projects and may remain hidden until later integration or runtime stage.
>
> Then from my view, we should have a patch for VCTC.
>
> [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]] : can you share your view?

-------

> [!note]+ 2026-09-10 07:03 · [[Nandita_Prasad_(MSEMS-ETAS)|Prasad Nandita]]
> To have a more centralized robust approach, we are looking at options to handle this check in the tooling, instead at individual component level.
>
> It shall be considered for the forward path.
>
> [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Phuong Nguyen Le]]  For VCTC since the config is already modified and fixed for the target project, doesn't this suffice? do you need the fix on 12.11.0? 
>
> [[Chandran_Girish_(ETAS-ECMXPC-Yok1)|Girish Chandran]] [[Shweta_Ganesh_Dixit|Shweta Ganesh Dixit]]  FYI

-------

> [!note]+ 2026-09-10 05:58 · [[Shweta_Ganesh_Dixit|Shweta Ganesh Dixit]]
> [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]] : Thanks for the feedback!
>
> Currently we are discussing this with [[Chandran_Girish_(ETAS-ECMXPC-Yok1)|Girish Chandran]] if this validation can be inbuilt in the code generation tool instead of every module implementing a validation error for the parameters which will make the code bulky and unmaintainable. 
>
> I have assigned this ticket to [[Chandran_Girish_(ETAS-ECMXPC-Yok1)|Girish Chandran]] to take this forward. 

-------

> [!note]+ 2026-09-09 15:40 · [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]]
> [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Phuong Nguyen Le]] [[Shweta_Ganesh_Dixit|Shweta Ganesh Dixit]] I've changed the priority of this issue to Medium.
>
> Although it can be regarded as misconfiguration issue, the result is no warning no error, and duplicate MACROs are generated in code with different values. If customer does not notify it, it could be a hidden issue only found during runtime.
>
> And this issue is recorded in customer open issue list which is claimed to be fixed, maybe it is not blocking point, but it should be planned for Cariad.
>
> If the fix is by adding validation in BSW Code Gen, no code change is needed, can we provide the solution as patch for Cariad in short term.
>
> And plan for other customers in long term.

-------

> [!note]+ 2026-09-09 05:07 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Phuong Nguyen Le]]
> [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]] : It's seem that this is improvement request and Project team has solution now so that I think it's not urgent topic? Do you really need this improvement now? Please share your need!

-------

> [!note]+ 2026-09-08 12:58 · [[Shweta_Ganesh_Dixit|Shweta Ganesh Dixit]]
> [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Phuong Nguyen Le]]: We are currently discussing on the strategy to solve such kinds of misconfigurations. The configuration in the project is corrected by [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]] and this issue would not occur with the correct configuration. 
>
> What we are missing here is to catch the wrong configuration by the customer and this can be taken up as an improvement in the forward path of the product. I would want to understand the need for an urgent patch request here, since the customer already has a solution by changing his configuration. 
>
> [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]] : Can you please give a background of this request now?
>
> [[Nandita_Prasad_(MSEMS-ETAS)|Prasad Nandita]] : FYI

-------

> [!note]+ 2026-09-08 12:50 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Phuong Nguyen Le]]
> [[Chandran_Girish_(ETAS-ECMXPC-Yok1)|Girish Chandran]] , [[Shweta_Ganesh_Dixit|Shweta Ganesh Dixit]] : is it possible to provide code drop in CW37-38 then our team can integrate to provide the preview plugin to customer on 25/Sep

-------

> [!note]+ 2026-09-08 11:39 · [[Shweta_Ganesh_Dixit|Shweta Ganesh Dixit]]
> [[James_Butterfield|James Butterfield]] , [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Phuong Nguyen Le]] : The timeline for this topic was mentioned **tentative** as RTA-CAR 12.13.0 in [https://rtahotline.etas.com/jira/browse/RH-15717?focusedCommentId=688303&page=com.atlassian.jira.plugin.system.issuetabpanels:comment-tabpanel#comment-688303] and no patch on RTA-CAR 12.11 was discussed. 
>
> Adding [[Chandran_Girish_(ETAS-ECMXPC-Yok1)|Girish Chandran]] here since, it was discussed that the the code generation tool shall check all parameters with *Symbolic Name = TRUE* for uniqueness instead of every module implementing a validation check for multiple parameters which makes the code bulky and unmaintainable. 
>
> [[Chandran_Girish_(ETAS-ECMXPC-Yok1)|Girish Chandran]] : Was there any progress in this topic?

-------

> [!note]+ 2026-09-08 11:22 · [[James_Butterfield|James Butterfield]]
> Hi [[Shweta_Ganesh_Dixit|Shweta Ganesh Dixit]] and [[Rajendran_Jothivel|Rajendran Jothivel]],
>
> Please could you share the status on releasing a patch to the customer for RTA-CAR 12.11.0? Is everything still going ahead as planned?
>
> Best Regards,
> James

-------

> [!note]+ 2026-09-08 10:10 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Phuong Nguyen Le]]
> [[James_Butterfield|James Butterfield]] , Customer expect to provide fix on RTA-CAR 12.11 and provide patch plugin for them on 25-Sep. 
>
> Can you share your plan?

-------

> [!note]+ 2026-09-07 10:39 · [[James_Butterfield|James Butterfield]]
> Hi [[JI_Jiaqi_(ETAS-ECMXSF-CN)|Jiaqi JI]],
>
> I see you have reopened this ticket, could you please clarify whether this was a mistake?
> If not, please outline any outstanding points you feel are preventing this ticket from being closed.
>
> Best Regards,
> James

-------

> [!note]+ 2026-06-23 11:39 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2026-05-29 08:34 · [[Shweta_Ganesh_Dixit|Shweta Ganesh Dixit]]
> [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]] : I have linked the story where this improvement for the macro for SdConsumedEventGroup will be updated in our forward path.
>
> Tentative timeline: RTA-CAR 12.13.0

-------

> [!note]+ 2026-05-15 10:09 · [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]]
> I don't see linked fix issue created for the macro issue. Please create.

-------

> [!note]+ 2026-05-14 18:48 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically moved to Solution Proposed.

-------

> [!note]+ 2026-04-30 07:32 · [[Rajendran_Jothivel|Rajendran Jothivel]]
> Hello [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]] ,
>
> Typically, with a UDP communication path, it is not feasible to reliably report certain errors in SoAd. A packet that may not be relevant from an SD perspective could still be required by other upper layers interacting with SoAd.
>
> Therefore, for this specific use case, I prefer to disable the UDP supervision timeout to better align with the expected system behavior. Thanks!

-------

> [!note]+ 2026-04-30 03:19 · [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]]
> [[Rajendran_Jothivel|Rajendran Jothivel]] It's feasible to disable the UDP supervision timeout. But if the scenario is fake, could our tool to add some error or warning for this cross-model integration use case even it is not AUTOSAR specification? 

-------

> [!note]+ 2026-04-29 16:01 · [[Rajendran_Jothivel|Rajendran Jothivel]]
> Hello [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]],
>
> One option I see is to disable the UDP supervision timeout. Do you see any scenarios where this should be enabled in the project? If not, I would prefer to disable this feature. Thanks!

-------

> [!note]+ 2026-04-29 02:53 · [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]]
> Hi, [[Rajendran_Jothivel|Rajendran Jothivel]] 
>
> I agree on the first point, we can plan to fix it;
>
> For the second point, do we have some mechanism to prevent the handling of the Event Group packets before Offer and Subscribe, especially the triggering of UDP alive monitoring?  

-------

> [!note]+ 2026-04-28 13:19 · [[Rajendran_Jothivel|Rajendran Jothivel]]
> Hello [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]] ,
>
> Do you agree with previous comments? If so, we can plan the fix for the below point alone in our delivery. Thanks!
> {quote}I rechecked the RTA-CAR 12.11.0 release and observed that duplicate macros are generated when the same short name is configured across two different consumed groups. This issue needs to be addressed.
> {quote}

-------

> [!note]+ 2026-04-16 12:49 · [[Rajendran_Jothivel|Rajendran Jothivel]]
> Hello [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]],
>
> Please find my analysis results below:
>
> I rechecked the RTA-CAR 12.11.0 release and observed that duplicate macros are generated when the same short name is configured across two different consumed groups. This issue needs to be addressed.
>
> However, restricting the mapping of the same routing group to multiple consumed groups is not feasible, as some customers may intentionally want to control different consumed groups using a single routing group. 
>
> Thank you for your feedback!

-------

> [!note]+ 2026-04-16 12:07 · [[Nandita_Prasad_(MSEMS-ETAS)|Prasad Nandita]]
> [[Rajendran_Jothivel|Rajendran Jothivel]]  could you confirm if the fix is available in RTA-CAR 12.11.0?

-------

> [!note]+ 2026-04-16 09:43 · [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]]
> Status update on customer side for issue2:
>
> By changing the **SdConsumedEventGroupUdpActivationRef** to the correct one, customer now is not able to reproduce this issue both on bench and vehicle under pressure test. They agree that the root cause is found.
>
> Customer agrees not to change anything for issue2 on RTA-CAR 9.1.0;
>
> But customer requires us to improve the robustness of our product on RTA-CAR 12.11.0 release version by providing error notification in tool when the same wrong configuration happens.

-------

> [!note]+ 2026-04-16 09:04 · [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]]
> [[Rajendran_Jothivel|Rajendran Jothivel]] Yes, you are right. The macro comes from the short name across two different consumed groups
>
> ![[RH-15717-image-2026-04-16-15-06-07-841.png]]
> ![[RH-15717-image-2026-04-16-15-06-07-841.png]]

-------

> [!note]+ 2026-04-16 06:52 · [[Rajendran_Jothivel|Rajendran Jothivel]]
> Hello [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]],
>
> Yes, I agree that this needs to be fixed.
>
> My point is that the duplicate macro was generated due to the duplicate short name, not because of the same routing group reference. 
>
> Have you tried modifying the configuration? This needs to be confirmed to accurately determine the root cause of the issue. Thanks!

-------

> [!note]+ 2026-04-16 02:35 · [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]]
> [[Rajendran_Jothivel|Rajendran Jothivel]] [[Nandita_Prasad_(MSEMS-ETAS)|Prasad Nandita]] Even so, our tool has the responsibility to avoid the same macro with different value, it's a bug no matter what wrong configuration customer has. Our tool does not give warning or error on it and generate a wrong code !
>
> Customer does not request us to fix it on 9.1.0.
>
> They just request us to check the situation on 12.9++. If it still could happen, we need to raise a bugfix to ensure the fix in the final release of 12.11.0. I think this is reasonable request.
>
> It's easier to check it through the source code of BswGen instead of trying by configuration.

-------

> [!note]+ 2026-04-15 11:44 · [[Rajendran_Jothivel|Rajendran Jothivel]]
> Hello [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]],
>
> The duplicate macro was generated because the same short name was configured across two different consumed groups, not due to the same routing group configuration.
>
> Please see the below highlighted portion in blue color and this short name also should be configured with unique string. Thanks!
>
> ![[RH-15717-image-2026-04-15-15-14-14-614.png]]

-------

> [!note]+ 2026-04-15 11:09 · [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]]
> [[Rajendran_Jothivel|Rajendran Jothivel]] As you see, SoAdRoutingGroup referenced by 2 SdClientService which leads to the issue.
>
> ![[RH-15717-image-2026-04-15-17-08-32-854.png]]

-------

> [!note]+ 2026-04-15 06:24 · [[Rajendran_Jothivel|Rajendran Jothivel]]
> Hello [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]],
>
> The highlighted duplicate entry is possible only if the same consumed event group or identical short name is configured for different consumed groups across multiple client services and instances.
>
> Could you please recheck how the configuration has been set up?

-------

> [!note]+ 2026-04-15 05:49 · [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]]
> Hello, [[Rajendran_Jothivel|Rajendran Jothivel]] , 
>
> The routing group is mapped by mistake on customer side, but customer complains our tool does not give warning or error on this for RTA-CAR 9.1.0, and even generate the same macro with different value as below.
>
> Customer requests us to check this problem in RTA-CAR 12 >= 12.9.0 to see whether the same problem exists or not. If exists, a bugfix shall be created to fix it.
>
> ![[RH-15717-image-2026-04-15-11-42-56-019.png]]

-------

> [!note]+ 2026-04-14 17:18 · [[Rajendran_Jothivel|Rajendran Jothivel]]
> Hello [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]] ,
>
> Thanks for your test result.
> {quote}Could you please help confirm whether the conclusion in my previous comment is correct?
> {quote}
> I have analyzed the code in detail for the specified use case, and it appears that this scenario is possible.
>
> I would like to understand why the same routing group is mapped to **0x4015 of NGX (IP:22)** and {*}service 0x0054 of RDCU (IP:32){*}. Ideally, these should be mapped to different routing groups to better control distinct communication paths.
>
> Additionally, could you please clarify the reason for using the same routing group for two services associated with different servers? Is this configuration intended to address a specific use case?
> {quote}Could you also please confirm whether, if the customer uses static SoAd connection configuration, this issue would not happen as well?
> {quote}
> Yes, this issue is not expected to occur in a static configuration, since the UDP supervision timeout condition will not be reached when static remote addresses are used.
>
> Furthermore, SoAd ensures that a unique socket index is assigned for each remote address via the SoAd_SetUniqueRemoteAddr API.

-------

> [!note]+ 2026-04-14 14:02 · [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]]
> Hello [[Rajendran_Jothivel|Rajendran Jothivel]],
>
> Could you please help confirm whether the conclusion in my previous comment is correct?
>
> Could you also please confirm whether, if the customer uses static SoAd connection configuration, this issue would not happen as well?

-------

> [!note]+ 2026-04-14 13:53 · [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]]
> # Issue1 Troubleshooting Conclusion
>
> When **CDCU** is reset independently and then receives a **specific sequence of SOME/IP messages** from *LDCU, RDCU, and NGX*, the subsequent SOME/IP message sent by **CDCU** may use the *wrong IP address*.
>
> ## Analysis Process
>
> The IP information of each node is as follows:
>
> - CDCU IP address: `172.20.1.33`, abbreviated as `IP:33`
> - LDCU IP address: `172.20.1.232`, abbreviated as `IP:232`
> - RDCU IP address: `172.20.1.32`, abbreviated as `IP:32`
> - NGX IP address: `172.20.1.22`, abbreviated as `IP:22`
>
> - In Figure 1, Frame 1 is an Offer message sent by `NGX (IP:22)`. According to the project configuration, this Offer message is configured only for service `0x4015`. However, service `0x4015` of `NGX (IP:22)` and service `0x0054` of `RDCU (IP:32)` are associated with the same `SoAdRoutingGroup`. After CDCU receives the Offer from NGX, it sets this `SoAdRoutingGroup` to `TRUE`.
>
> - In Figure 1, Frame 2 is an Event message sent by `RDCU (IP:32)`. After CDCU receives this message, the status of RDCU's socket in the dynamic socket table (`index: 33`) changes from `reconnect` to `online` (see Figure 2, `index366`). Because service `0x0054` is associated with a `SoAdRoutingGroup` that is `TRUE`, this frame activates the UDP Alive Timer mechanism for `RDCU (IP:32)`. The currently configured timeout value is `50 ms`.
>
> - In Figure 1, Frame 3 is an Offer message sent by `RDCU (IP:32)`. After CDCU receives this Offer, the related RDCU service registration is completed, and the corresponding RDCU socket (`index: 33`) is set to `online` again, with the IP address set to `32`. It can also be seen that the interval between Frame 2 and Frame 3 is within `50 ms`, so the RDCU Alive Timer has not yet timed out at that point. However, after the Alive Timer times out, the state of RDCU's corresponding dynamic socket table entry (`index: 33`) changes from `online` to `reconnect` (see the figure index for `367`), and the IP address is cleared to `0`.
>
> - In Figure 1, Frame 4 is an Offer message sent by `LDCU (IP:232)`. After CDCU receives this Offer, it uses the best-match algorithm to find a suitable location to store the IP address. At that time, within the same socket group, the IP address at `index: 33` has already been cleared to `0`, so the position at `index: 33` is considered free. Therefore, the IP address `232` is written into the position `index: 33` in the dynamic table (see `index1184` in Figure 3).
>
> - When CDCU sends a method to `RDCU (IP:32)`, it reads the address stored at `index: 33` from the dynamic table, and that address is `IP:232`. Therefore, the method is mis-sent to `LDCU (IP:232)`.
>
> Figure 1 shows the specific message order. Frames `1`, `2`, `3`, and `4` are the key frames, and the interval between Frames `2` and `3` must be within `50 ms`.
>
> ![[RH-15717-Pasted image 20260414193414.png]]
>
> Figure 2 describes the connection status between CDCU and the other nodes:
>
> ![[RH-15717-Pasted image 20260414193443.png]]
>
> Figure 3 shows how CDCU sets the IP information in the dynamic socket table after receiving the Offer message:
>
> ![[RH-15717-Pasted image 20260414193517.png]]

-------

> [!note]+ 2026-04-13 13:01 · [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]]
> 1. this is the observation from dlt log, maybe 33 is best match result;
>  # 
> SoAd_Config_UdpSupervisionTimeout_cau32 :UDP Alive Supervision Timeout array in milliseconds for Socket Connection Group and It is multiples of SoAd Main periods

-------

> [!note]+ 2026-04-13 12:50 · [[Rajendran_Jothivel|Rajendran Jothivel]]
> Hello [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]] ,
>
> Could you please clarify the below points. 
>  # When Event packet from RDCU (172.20.1.32) is received how socket 33 is reserved? why not 31 or 32 socket in this case?
>  # What is the timeout parameter configured with 50 ms?

-------

> [!note]+ 2026-04-13 12:38 · [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]]
> [[Rajendran_Jothivel|Rajendran Jothivel]]  One observation from customer side, please help to analyze the possiblity:
>
> After CDCU_MCU (172.20.1.33) reset, it receives Event packet from RDCU (172.20.1.32) before Offer packet because RDCU is not reset, this will also occupy socket 33 with remote address 172.20.1.32 as online. The UDP has timeout configuration as 50ms, even within 50ms Offer packet is received from 172.20.1.32, when reaching 50ms the socket will release remote address and be in reconnect state. When Offer of  LDCU (172.20.1.232) comes, socket 33 will be assigned. Sd do not notice this, it will subscribe to the wrong addr in socket 33.

-------

> [!note]+ 2026-04-13 08:58 · [[Rajendran_Jothivel|Rajendran Jothivel]]
> Hello [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]],
>
> Thanks for your call and your explanation.
>
> I would like to thoroughly debug the SoAd_SetUniqueRemoteAddr and SoAd_RemoteAddr APIs for the problematic scenarios mentioned below:
>  * At the beginning of the SoAd_SetUniqueRemoteAddr call, what are the remote IP addresses and remote ports associated with sockets 32, 33, and 34, which are mapped to the same socket connection group for service 0x0501?
> This information will help identify any potential misbehavior in the API.
>  * Is there any invocation of SoAd_SetRemoteAddr to reset the remote address (IP: 0.0.0.0, Port: 0) before calling SoAd_SetUniqueRemoteAddr?
> If yes, from which Service Discovery (SD) use case is this being triggered?
>  * Please also verify that the IPv4 endpoint options received from all servers are correct, to ensure that the remote side is not behaving unexpectedly.

-------

> [!note]+ 2026-04-13 08:08 · [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]]
> New information comes from customer: 
>
> When calling {*}Sd_ClntSetRemoteAddr -> SoAd_SetUniqueRemoteAddr -> SoAd_BestMatchAlgorithm{*}, the expected socket assignment for remote addr is
>
> IP x.x.x.22 -> SOCK32,
>
> IP x.x.x.32 -> SOCK33,
>
> IP x.x.x.232 -> SOCK34
>
> But the actual result when it goes wrong is:
>
> IP x.x.x.22 -> SOCK32,
>
> IP x.x.x.32 -> SOCK33,
>
> IP x.x.x.232 -> SOCK33 which overwrites 33 but it is not free yet (or being released by accident)
>
> The dlt log shows as below:
>
> Normal case:
>
> ![[RH-15717-image-2026-04-13-14-09-23-574.png]]
>
> Abnormal Case:
>
> ![[RH-15717-image-2026-04-13-14-09-34-480.png]]
>
>
> ![[RH-15717-image-2026-04-13-14-09-23-574.png]] ![[RH-15717-image-2026-04-13-14-09-34-480.png]]

-------

> [!note]+ 2026-04-12 10:27 · [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]]
> Customer decided to change the configuration of SoAd to avoid the socket shifting issue, they raised following two questions which needs Eth Expert from PF to clarify:
> Question 1:
>
> In SoAd, the `SoAdPduRoutes` and `SoAdSocketRoutes` related to a method are both directly associated with the `SoAdSocketConnectionGroup`.
>
> The customer wants to change the configuration so that `SoAdPduRoutes` and `SoAdSocketRoutes` are directly associated with the `SoAdSocketConnection` inside the `SoAdSocketConnectionGroup`. In addition, the remote IP address and port configured in `SoAdSocketConnection` would be changed to fixed values.
>
> The customer assumes that after this change, when the SWC sends a method-related PDU, the program logic will no longer traverse the `SoAdSocketConnectionGroup` to find a suitable `SoAdSocketConnection`. Instead, it would directly use the PDU ID to index the correct `SoAdSocketConnection`, so the method and `SoAdSocketConnection` would have a direct mapping relationship. In this way, the customer expects to avoid the issue where an error during traversal of the `SoAdSocketConnectionGroup` causes the PDU to be sent to the wrong `SoAdSocketConnection`.
>
> Could you confirm whether, after this configuration change, the program execution logic will behave as the customer expects? Can this avoid the issue of sending the PDU to the wrong IP address?
>
> Question 2:
>
> When the SD module receives an Offer message from the server, `Sd_MainFunction` writes the corresponding server remote address and port to SoAd through `Sd_ClntSetRemoteAddr`. Is the server remote address and port set every time an Offer message is received, or only the first time?
>
> The customer would like to understand under what conditions the server remote address and port are set after an Offer message is received.

-------

> [!note]+ 2026-04-11 09:52 · [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]]
> issue2 related log, code, config added

-------

> [!note]+ 2026-04-11 03:53 · [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]]
> **Issue2 raised by customer may related to issue1:**
>
> **Hello ETAS,**
>
> **We have the second issue from ETH STACK of ISOLAR 9.10** 
>
> **Details as following, Please check ETH STACK and analyze the possibility place which can trigger this issue and how to fix this issue** 
>
>
>
> **Please provide the feedback before the noon of 4.15  . Details information could discuss with [@ZHOU Zhou (ETAS-ECM/XSF-CN)](mailto:zhou.zhou2@etas.com) [@LIU Jie (ETAS-ECM/XSF-CN)](mailto:jie.liu8@etas.com)**
>
> **if need more information please ask liu jie to request it from us**
>
> The LDCU (172.20.1.232) node sent an offer message for the 0501 service as the server.
>
> Under normal circumstances, CDCU (172.20.1.33) will send a request for 0501 service to LDCU (172.20.1.232).
>
> However, CDCU (172.20.1.33) may occasionally mistakenly send 0501 service requests to RDCU (172.20.1.32). The destination IP address and port number for sending belong to RDCU (172.20.1.32).
>
> ![[RH-15717-image-2026-04-11-09-55-05-464.png]]
>
> The configuration is as follows:
>
> In the project, the CDCU (172.20.1.33) node serves as the client and has three server nodes: LDCU (172.20.1.32), RDCU (172.20.1.232), and NGX (172.20.1.22). The three client sockets share a SocketGroup, and their Remote IP addresses are all configured as ANY. The Remote Port is configured as 0.
>
> ![[RH-15717-image-2026-04-11-09-55-23-219.png]]
>
> The RduRoute and RoutingGroup Ref configurations for Service ID 0501 (Method ID 0001) of CDCU (172.20.1.33) node are as follows:
>
> ![[RH-15717-image-2026-04-11-09-55-43-468.png]]
> ![[RH-15717-2026-04-11_09h52_02.png]] ![[RH-15717-image-2026-04-11-09-55-05-464.png]] ![[RH-15717-image-2026-04-11-09-55-23-219.png]] ![[RH-15717-image-2026-04-11-09-55-43-468.png]]

-------

> [!note]+ 2026-04-10 10:28 · [[Rajendran_Jothivel|Rajendran Jothivel]]
> Hello [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]],
>
> Please see my comments below,
> {quote} # Whether applying the same retry-condition change to `RTA-CAR 9.1.0` is technically valid and safe.{quote}
> Yes, it has been modified as an improvement according to the AUTOSAR specification R19-11 as part of [Change Request 253977: [EthStack][SD] Support of the retry subscription mechanism for eventgroups in combination with cyclic offers - Change and Configuration Management|https://rb-alm-28-p.de.bosch.com/ccm/web/projects/BSW%20Platform#action=com.ibm.team.workitem.viewWorkItem&id=253977] and it is safe to update the code.
>
> ![[RH-15717-image-2026-04-10-13-50-21-798.png]]
>
> For you information it was like below in the earlier versions,
>
> ![[RH-15717-image-2026-04-10-13-51-12-818.png]]
>
> Relevant AUTOSAR ticket for more information,
>
> [[AR-3052] [Sd] Support of the retry subscription mechanism for eventgroups in combination with cyclic offers - AUTOSAR JIRA|https://jira.autosar.org/browse/AR-3052]
> {quote}2. Whether this change is the officially recommended fix direction for the customer project.
> {quote}
> Yes, I recommend this as an official fix for the customer project.
> {quote}3. What official customer-facing statement should be provided regarding root cause and corrective action.
> {quote}
> We can inform the customer that it has been modified to align with AUTOSAR version R19-11.

-------

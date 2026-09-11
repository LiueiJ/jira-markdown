---
jira_key: RH-16250
jira_url: "https://rtahotline.etas.com/jira/browse/RH-16250"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Critical
project: RH
assignee: "[[Zhou_ZHOU|Zhou ZHOU]]"
reporter: "[[Zhou_ZHOU|Zhou ZHOU]]"
tags: [jira/comp/communication-eth]
fix-versions: []
epic: null
parent: null
created: "2026-06-03T13:21:42.000+0200"
updated: "2026-07-28T14:24:22.000+0200"
synced-at: "2026-09-11T01:36:25.139Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Hello Hotline Teams:

Issue description:

The customer analyzed the DLT log and found that the socket connection status for receiving LDCU Event group quickly switched between online and reconnect, switching more than 100 times in about 1 second, as shown in Figure 1:

Figure 1:

![[RH-16250-image002.png]]

According to the printed status of the socket Routing Group, as shown in Figure 2, the ” specificRgStatus_b” of the Routing Group related to LDCU (RoutingGroupID: 7, Socket ID 34 (0X22)) is False. In the correct case, it should be Ture. But the ” specificRgStatus_b” (Socket ID 32 (0X21)) of NGX is Ture.

Figure 2:

![[RH-16250-image003.png]]

This issue occurred twice on the customer's production line, both after NGX and LDCU were awakened.

The sleep wake-up sequence is as follows:

1,From Figure 3, it can be seen that NGX and LDCU sleep simultaneously. Before sleep, the dynamic socket ID assigned to NGX is 34, and the dynamic socketID assigned to lDCU is 33.

2, NGX wakes up first and LDCU wakes up later, so the dynamic socket ID assigned to NGX after waking up is 33, and the dynamic socket ID assigned to LDCU after waking up is 34.

The customer observed that the dynamic socket IDs of NGX and LDCU were swapped after sleep and wake-up.

Figure 3:

![[RH-16250-image001.png]]

## 关联

- relates to: [[RH-15717 Intermittent SOME/IP Subscription Loss After Repeated CDCU_MCU Reset]]

## 评论

> [!note]+ 2026-07-28 14:24 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2026-07-03 18:50 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically moved to Solution Proposed.

-------

> [!note]+ 2026-06-19 10:43 · [[Melanie_Hartlieb|Melanie Hartlieb]]
> Status update: Confirmation received that the fix is working. Now alignment about Delivery ongoing. 

-------

> [!note]+ 2026-06-16 14:14 · [[Clement_Fokam|Clement Fokam]]
> Hello [[Zhou_ZHOU|Zhou ZHOU]] ,
>
> Please find attached the code drop for SoAd.
>
> The update adds the overflow protection to the close request counter lSoAdDyncSocConfig_pst->socConCloseReqCnt_u16 in SoAd_CloseSoCon()
>
> [^SoAd Update 2026.06.16-1.zip]

-------

> [!note]+ 2026-06-16 12:51 · [[Shweta_Ganesh_Dixit|Shweta Ganesh Dixit]]
> [[Zhou_ZHOU|Zhou ZHOU]] : The issue of TTL expiry in Sd is a known issue and a Defect was already published from product team in 2022. Details in [509491: [EthStack][Sd] OfferService TTL expires earlier than expected for Client Services|[https://rb-alm-28-p.de.bosch.com/ccm/resource/itemName/com.ibm.team.workitem.WorkItem/509491] ]
>
> We have now ported the code changes on the Sd version in the attached project to unblock you. 
>
> Please find the before and after changes for this attached here
>
> [^Sd_RH-16250.zip]

-------

> [!note]+ 2026-06-16 06:34 · [[Zhou_ZHOU|Zhou ZHOU]]
> Hello，
>
> The customer analyzed the three scenarios in which `lClntSrvInstAdm_pst->cntrTTLMainFutCyc_u16` is set to `SD_MAIN_FUNCTION_CYCLE`:
>
> ![[RH-16250-image-2026-06-16-12-35-31-409.png]]
>
> Scenario 1: Upon receiving the initial Offer message, the software sets `lClntSrvInstAdm_pst->ClntCurrentSt_en` to `SD_CLIENT_SERVICE_AVAILABLE`. Consequently, when a second Offer message is received, the condition at line 670 evaluates to false; therefore, the software does not set `lClntSrvInstAdm_pst->cntrTTLMainFutCyc_u16` to `SD_MAIN_FUNCTION_CYCLE`.
>
> ![[RH-16250-image-2026-06-16-12-35-45-925.png]]
>
> Scenario 2: `lClntSrvInstAdm_pst->cntrTTLMainFutCyc_u16` is reset only when its current value is 0.
>
> ![[RH-16250-image-2026-06-16-12-35-58-652.png]]
>
> Scenario 3: When Offer messages are continuously received and in the absence of events such as StopOffer, TTL expiration, or IP connection loss.`lClntSrvInstAdm_pst->ComPhase_en` remains in the `SD_COM_MAIN_PHASE` state. As a result, the condition at line 1898 evaluates to false, and the software does not set `lClntSrvInstAdm_pst->cntrTTLMainFutCyc_u16` to `SD_MAIN_FUNCTION_CYCLE`.
>
> ![[RH-16250-image-2026-06-16-12-36-05-074.png]]
>
> Therefore, the customer believes that lClntSrvInstAdm_pst->cntrTTLMainFutCyc_u16 will only be set to SD_MAIN_FUNCTION_CYCLE when the offer message is received for the first time.
>
>
>
>
> ![[RH-16250-image-2026-06-16-12-35-31-409.png]] ![[RH-16250-image-2026-06-16-12-35-45-925.png]] ![[RH-16250-image-2026-06-16-12-35-58-652.png]] ![[RH-16250-image-2026-06-16-12-36-05-074.png]]

-------

> [!note]+ 2026-06-15 18:03 · [[Clement_Fokam|Clement Fokam]]
> Hello [[Zhou_ZHOU|Zhou ZHOU]] ,
>
> Regarding the second issue, it is still not clear.
> I have analyzed possible scenarios where **lClntSrvInstAdm_pst->cntrTTLMainFutCyc_u16** is not reset for some received Offer messages. but I could not find any reason for this behavior.
>
> Would it be possible to have a debug session to identify the root cause and understand why this is happening?

-------

> [!note]+ 2026-06-15 14:04 · [[Zhou_ZHOU|Zhou ZHOU]]
> Hello，
>
> Customer Feedback:
> The software sets `lClntSrvInstAdm_pst->cntrTTLMainFutCyc_u16` to `SD_MAIN_FUNCTION_CYCLE` only when the Offer message is received for the first time.
> If a second Offer message is received, the software only resets `lClntSrvInstAdm_pst->TTLCounter_u32`; the value of `lClntSrvInstAdm_pst->cntrTTLMainFutCyc_u16` remains between 0 and 500.
>
>
> ![[RH-16250-image-2026-06-15-20-04-13-079.png]]

-------

> [!note]+ 2026-06-15 12:04 · [[Clement_Fokam|Clement Fokam]]
> Hello Zhou,
>
> Regarding the 2nd Issue
> Actually, lClntSrvInstAdm_pst->cntrTTLMainFutCyc_u16 should be reset to SD_MAIN_FUNCTION_CYCLE every time a new Offer message is received.
>
> Could you please provide us the DLT log so that we can analyze the data content?
>
> Thanks.

-------

> [!note]+ 2026-06-15 10:29 · [[Zhou_ZHOU|Zhou ZHOU]]
> Hello Clement Fokam，
>
> Okay, I will confirm whether the customer has such a use case or scenario.
>
> Could you please provide the solution for Issue 2 first? The customer wants to fix both issues and then test them.

-------

> [!note]+ 2026-06-15 08:53 · [[Clement_Fokam|Clement Fokam]]
> Hello Zhou,
>
> Does the customer have a use case or scenario where the number of close requests ({*}socConCloseReqCnt_u16{*}) becomes greater than the number of open requests ({*}socConOpenReqCnt_u16{*})?
> In theory, this should not happen. The current code update prevents counter overflows for both counters, but only in {*}SoAd_OpenSoCon(){*}. Ist is not required in **SoAd_CloseSoCon()**
>
> Could you please confirm whether such a scenario exists on the customer side?

-------

> [!note]+ 2026-06-15 06:15 · [[Zhou_ZHOU|Zhou ZHOU]]
> Hello Clement Fokam，
>
> The customer believes that `socConCloseReqCnt_u16` will overflow within `SoAd_CloseSoCon`, so overflow protection is required.
>
> ![[RH-16250-2026-06-15_12h12_44.png]]
>
>
>
>
>
>
>
>
> ![[RH-16250-2026-06-15_12h12_44.png]]

-------

> [!note]+ 2026-06-14 19:49 · [[Clement_Fokam|Clement Fokam]]
> Hello [[Zhou_ZHOU|Zhou ZHOU]],
>
> The updated code will prevent counter overflows for both **socConCloseReqCnt_u16** and {*}socConOpenReqCnt_u16{*}. 

-------

> [!note]+ 2026-06-13 09:03 · [[Zhou_ZHOU|Zhou ZHOU]]
> Hello Clement Fokam，
>
> This issue has just been reproduced on the test bench, and they have confirmed that the "socConOpenReqCnt_u16" counter overflowed.
> After receiving and analyzing the updated code, the Cariad engineers raised a question: is it also necessary to implement overflow handling for the "socConCloseReqCnt_u16" counter?

-------

> [!note]+ 2026-06-13 08:17 · [[Zhou_ZHOU|Zhou ZHOU]]
> Hello Clement Fokam，
>
> Okay, I have forwarded the updated code to cariad.
> They are also looking forward to the updated code for Issue 2（The TTL Timeout of CEA1.0 Offer Messages Randomly Falls Within 2s to 3s）.

-------

> [!note]+ 2026-06-12 14:41 · [[Clement_Fokam|Clement Fokam]]
> Hi [[Zhou_ZHOU|Zhou ZHOU]] 
> Regarding the first issue, I analyzed it and made an update in SoAd_OpenSoCon() to avoid an overflow of socConOpenReqCnt_u16 and to allow the opening of a new SoAd socket connection.
>
> Please test the updated SoAd_OpenSoCon() and provide me your feedback.
>
>
> [^SoAd Update 2026.06.12-1.zip]

-------

> [!note]+ 2026-06-12 11:21 · [[Jie_LIU|Jie LIU]]
> # CEA1.0 Socket Link Status Abnormality Analysis Result
>
> Sender: ZHOU Zhou (ETAS-ECM/XSF-CN) `<Zhou.ZHOU2@etas.com>`
>
> ## Issue 1: Analysis of the CEA1.0 Socket Link Status Abnormality
>
> 1. After analyzing three DLT logs collected from production vehicles, a common phenomenon was found: when the issue first occurs, the socket states of NGX, LDCU, and RDCU are all set to `SOAD_SOCON_OFFLINE` at the same time. This state transition is the starting point of the subsequent abnormal behaviors.
>
> ![[RH-16250-RH-16250-en-20260612-172106-1.png]]
>
> 2. As shown in the following code, the function `SoAd_TriggerAutoManualOpenSoCon` determines whether the socket state should be set to `offline` by comparing `socConCloseReqCnt_u16` and `socConOpenReqCnt_u16`. The socket state is set to `offline` only when `socConCloseReqCnt_u16` is greater than or equal to `socConOpenReqCnt_u16`.
>
> ```
> /* If the socket is already opened, then evaluate the number of close requests to know if the socket need to go OFFLINE */
> else if(( lSoAdDyncSocConfig_pst->socConCloseReqCnt_u16 > 0) &&
>         ( lSoAdDyncSocConfig_pst->socConCloseReqCnt_u16 >= lSoAdDyncSocConfig_pst->socConOpenReqCnt_u16) )
> {
>     /*set the event to offlinereq such that the actions shall be taken to close the socket in next steps */
>     lSoAdDyncSocConfig_pst->socConRequestedMode_en = SOAD_EVENT_OFFLINEREQ_UL;
>
>     /* Reset the both of the counters if close request has been accepted successfully */
>     /* (open and close requests counters are not used anymore as the socket now enter in closing procedure) */
>     /* (this step is required to ensure that further calls of Tx functions will be rejected) */
>     lSoAdDyncSocConfig_pst->socConOpenReqCnt_u16 = 0;
>     lSoAdDyncSocConfig_pst->socConCloseReqCnt_u16 = 0;
> }
> ```
>
> 3. Since the maximum value that a `u16` type can represent is `65535`, and the customer observed this issue after CDCU had been running continuously for 1 to 3 days without sleeping, the counters had enough time to overflow. During these 1 to 3 days, RDCU repeatedly enters sleep and wakes up again. After each wake-up, CDCU communicates with RDCU. During each socket establishment process, `socConOpenReqCnt_u16` is incremented. After enough increments, `socConOpenReqCnt_u16` overflows, causing the condition `socConCloseReqCnt_u16 > socConOpenReqCnt_u16` to become true.
>
> 4. By counting the sleep and wake-up cycles of RDCU, LDCU, and NGX in the DLT logs, the following behavior can be observed:
>
> 4.1 If CDCU receives a SomeIp offer message from LDCU, the code shows that CDCU calls `SoAd_OpenSoCon` to establish a connection with LDCU. Since there are 16 services related to CDCU, the `socConOpenReqCnt_u16` values for RDCU, LDCU, and NGX are each incremented by 16.
>
> ```
> /* If dynamic socket is valid
>  * usecase: SoAd_SetRemoteAddr is called before SoAd_OpenSoCon is called */
> if(lIdxDynSocket_uo < SoAd_CurrConfig_cpst->SoAd_noActiveSockets_uo)
> {
>     /* copy the global array index address to local pointer for further processing */
>     lSoAdDyncSocConfig_pst = &(SoAd_DyncSocConfig_ast[lIdxDynSocket_uo]);
>
>     /**********************************************************************************************/
>     /*********************************** [SWS_SoAd_00588] *****************************************/
>     /**********************************************************************************************/
>     /** SoAd shall store a request to open or close a socket connection when called with SoAd_OpenSoCon() and **/
>     /** SoAd_CloseSoCon() respectively, but handle the request only in the SoAd_MainFunction() respecting the **/
>     /** connection setup and shutdown policy.                                                            **/
>     /**********************************************************************************************/
>
>     /* The exclusive area SoAd_OpenCloseReq is used to avoid race condition when socket open or close is requested by UL or SoAd */
>     SchM_Enter_SoAd_OpenCloseReq();
>
>     /* Increment the socConOpenReqCnt_u16 variable by 1 and compare the socConOpenReqCnt_u16 with socConCloseReqCnt_u16 in next MainFunction */
>     /* if no.of open req is greater than close req, then set the event to onlinereq, such that open req action shall be taken place */
>     lSoAdDyncSocConfig_pst->socConOpenReqCnt_u16++;
>
>     SchM_Exit_SoAd_OpenCloseReq();
>
>     lFunctionRetVal_u8 = E_OK;
> }
>
> /* Return the value */
> return(lFunctionRetVal_u8);
> ```
>
> | ECU | Socket ID | socConOpenReqCnt_u16 | socConCloseReqCnt_u16 |
> | --- | --- | --- | --- |
> | RDCU | 32 | 16 | 0 |
> | LDCU | 33 | 16 | 0 |
> | NGX | 34 | 16 | 0 |
>
> 4.2 If CDCU receives a SomeIp offer message from RDCU, the code shows that CDCU calls `SoAd_OpenSoCon` to establish a connection with RDCU. Since there are 21 services related to RDCU, the `socConOpenReqCnt_u16` values for RDCU, LDCU, and NGX are each incremented by 21.
>
> | ECU | Socket ID | socConOpenReqCnt_u16 | socConCloseReqCnt_u16 |
> | --- | --- | --- | --- |
> | RDCU | 32 | 16+21 | 0 |
> | LDCU | 33 | 16+21 | 0 |
> | NGX | 34 | 16+21 | 0 |
>
> 4.3 RDCU subsequently enters the sleep state. If CDCU does not receive an offer message from RDCU within 3 seconds, the TTL timeout mechanism of the offer message calls `SoAd_CloseSoCon` to disconnect from RDCU. At that point, the `socConCloseReqCnt_u16` values for RDCU, LDCU, and NGX are each incremented by 21. Even if RDCU wakes up again within 3 seconds after sleeping and starts sending offer messages, this still triggers the SOME/IP reboot mechanism, which also causes `SoAd_CloseSoCon` to disconnect from RDCU. The result is the same as with the offer-message TTL timeout mechanism.
>
> | ECU | Socket ID | socConOpenReqCnt_u16 | socConCloseReqCnt_u16 |
> | --- | --- | --- | --- |
> | RDCU | 32 | 16+21 | 21 |
> | LDCU | 33 | 16+21 | 21 |
> | NGX | 34 | 16+21 | 21 |
>
> 4.4 RDCU continuously switches between sleep and wake-up states, which causes both `socConOpenReqCnt_u16` and `socConCloseReqCnt_u16` to keep increasing.
>
> | ECU | Socket ID | socConOpenReqCnt_u16 | socConCloseReqCnt_u16 |
> | --- | --- | --- | --- |
> | RDCU | 32 | 16+21+21+21... | 21+21+21... |
> | LDCU | 33 | 16+21+21+21... | 21+21+21... |
> | NGX | 34 | 16+21+21+21... | 21+21+21... |
>
> 4.5 After a sufficiently long period of time (1 to 3 days), `socConOpenReqCnt_u16` overflows first, causing the condition `socConCloseReqCnt_u16 > socConOpenReqCnt_u16` to become true.
>
> | ECU | Socket ID | socConOpenReqCnt_u16 | socConCloseReqCnt_u16 |
> | --- | --- | --- | --- |
> | RDCU | 32 | 5 | 65519 |
> | LDCU | 33 | 5 | 65519 |
> | NGX | 34 | 5 | 65519 |
>
> 5. SOAD then sets the socket states of RDCU, LDCU, and NGX to `SOAD_SOCON_OFFLINE`. Meanwhile, due to the restriction in the following SD module code, even if CDCU receives an offer message from LDCU, it will not call `SoAd_OpenSoCon` to establish a connection with LDCU. As a result, CDCU and LDCU can no longer communicate.
>
> ```
> if(( SD_CLIENT_SERVICE_DOWN == lClntSrvInstAdm_pst->ClntCurrentSt_en )
>     && ( SD_COM_MAIN_PHASE == lClntSrvInstAdm_pst->ComPhase_en ) )
> {
>     /* Change current state, inform BswM and start TTL timer */
>     lClntSrvInstAdm_pst->ClntCurrentSt_en = SD_CLIENT_SERVICE_AVAILABLE;
>     Call_BswM_Sd_ClientServiceCurrentState( lClntSrvInstCfg_pcst->ClntSrvHndlId_u16, SD_CLIENT_SERVICE_AVAILABLE );
>     lClntSrvInstAdm_pst->TTLPhase_en = SD_TTL_RUNNING;
>     lClntSrvInstAdm_pst->cntrTTLMainFutCyc_u16 = SD_MAIN_FUNCTION_CYCLE;
>     /* Open Socket Connection for Methods */
>     Sd_ClntOpenSockConn( lIdxClntMthd_u16, lClntSrvInstCfg_pcst->ClntSrvL4Ptccl_u8 );
>     /* Set remote IP of the socket */
>     Sd_ClntSetRemoteAddr( lIdxClntMthd_u16, SD_CLIENT_SUB, lClntSrvInstCfg_pcst->ClntSrvL4Ptccl_u8 );
>     /* Enable RoutingGroup */
>     Sd_ClntProcRoutingGr( lIdxClntMthd_u16, lClntSrvInstCfg_pcst->ClntSrvL4Ptccl_u8, SD_METHOD, SD_SETIP );
> }
> ```
>
> ## Issue 2: The TTL Timeout of CEA1.0 Offer Messages Randomly Falls Within 2s to 3s
>
> The customer found from the DLT logs that the timeout configuration for CDCU offer messages is 3 seconds, but the actual timeout varies randomly between 2 and 3 seconds. Code analysis shows that `lClntSrvInstAdm_pst->cntrTTLMainFutCyc_u16` is not reset to `SD_MAIN_FUNCTION_CYCLE (500)` after a new offer message is received. The customer believes that every time a new offer message is received, `lClntSrvInstAdm_pst->cntrTTLMainFutCyc_u16` should be reset to `SD_MAIN_FUNCTION_CYCLE`, so that the actual timeout is an accurate 3 seconds.

-------

> [!note]+ 2026-06-10 09:54 · [[Clement_Fokam|Clement Fokam]]
> Hi [[Zhou_ZHOU|Zhou ZHOU]] 
> The behavior of the required APIs are not visible in this log file.
> Please add the following API: SoAd_EnableSpecificRouting, SoAd_DisableSpecificRouting, SoAd_DisableRouting, SoAd_EnableRouting, SoAd_SetUniqueRemoteAddr, SoAd_SetRemoteAddr. 

-------

> [!note]+ 2026-06-09 11:59 · [[Clement_Fokam|Clement Fokam]]
> Hi [[Zhou_ZHOU|Zhou ZHOU]],
> add DLT logging for the following APIs:
> SoAd_EnableSpecificRouting, SoAd_DisableSpecificRouting, SoAd_DisableRouting, SoAd_EnableRouting, SoAd_SetUniqueRemoteAddr, SoAd_SetRemoteAddr

-------

> [!note]+ 2026-06-09 10:52 · [[Zhou_ZHOU|Zhou ZHOU]]
> Hello Clement Fokam，
>
> The customer observed a specific scenario: prior to the issue occurring (as shown in the figure below), the socket states of the NGX, LDCU, and RDCU were all set to "offline" within a short period.
>
> !2026-06-09_16h48_28.png!
>
> The corresponding DLT logs have been uploaded.
>
> [^dlt_mcu_HVWJA1ER6S1204026_2.13_20260530_050607.dlt]
>
>
> ![[RH-16250-2026-06-09_16h48_28-2.png]]

-------

> [!note]+ 2026-06-09 09:38 · [[Zhou_ZHOU|Zhou ZHOU]]
> Hello Clement Fokam，
>
> I want to be sure if the issue always happens whenever the ECU goes to sleep/ wakes up?
>      The issue also occurs occasionally in these situations.
> Are there scenarios where the ECU goes through a sleep/wake cycle and the issue doesn't occur? 
>      There are situations where issue do not occur, and it is highly probable that such problems will not occur.

-------

> [!note]+ 2026-06-09 09:28 · [[Clement_Fokam|Clement Fokam]]
> Hello [[Zhou_ZHOU|Zhou ZHOU]],
> I want to be sure if the issue always happens whenever the ECU goes to sleep/ wakes up?
> Are there scenarios where the ECU goes through a sleep/wake cycle and the issue doesn't occur? 

-------

> [!note]+ 2026-06-09 05:54 · [[Zhou_ZHOU|Zhou ZHOU]]
> Hello Clement Fokam，
>
> The uploaded code is for testing purposes, so it contains extensive logging; the uploaded DLT log file comes from a mass-production vehicle, meaning the logs related to `SoAd_SetUniqueRemoteAddr` had been removed by the customer.
> Logs for `SoAd_SetUniqueRemoteAddr` have now been re-added, but the customer will not receive the mass-production vehicle for testing until June 11th.
> Please let me know if you would like to add any other logs.

-------

> [!note]+ 2026-06-08 18:54 · [[Clement_Fokam|Clement Fokam]]
> Hello [[Zhou_ZHOU|Zhou ZHOU]] ,
>
> I cannot find any DLT log entries for **SoAd_SetUniqueRemoteAddr** in this log file.
>
> Could you please check whether the logging is enabled or if I might be looking at the wrong log file?

-------

> [!note]+ 2026-06-05 13:12 · [[Zhou_ZHOU|Zhou ZHOU]]
> Hello [[Shweta_Ganesh_Dixit|Shweta Ganesh Dixit]] ，
>
> The DLT-format log file and the XML-format log parsing file have both been uploaded.
>
> [^DLT_Log.7z]

-------

> [!note]+ 2026-06-05 12:32 · [[Shweta_Ganesh_Dixit|Shweta Ganesh Dixit]]
> [[Zhou_ZHOU|Zhou ZHOU]] : Thanks! Please also share the logs so that we can analyze

-------

> [!note]+ 2026-06-05 09:30 · [[Zhou_ZHOU|Zhou ZHOU]]
> [^issue2_stack_code-1.zip]

-------

> [!note]+ 2026-06-05 09:30 · [[Zhou_ZHOU|Zhou ZHOU]]
> Hello [[Shweta_Ganesh_Dixit|Shweta Ganesh Dixit]] ，
>
> 1，From where is this SocketId fetched(Dynamic)?
>
> As shown in the figure, the socket ID corresponding to port 55117 was initially 33, and subsequently, the socket ID assigned to port 55117 was 34.
>
> ![[RH-16250-image-2026-06-05-15-06-56-803.png]]
>
> ![[RH-16250-image-2026-06-05-15-31-41-830.png]]
> 2，Where are the debug variables added to get these values in image003.png? Share the debug code & the configuration code.
>
> I have uploaded the client's source code, which contains DLT information.
> 3，When are these debug variables read(after which message)?
>
> I have uploaded the client's source code, which contains DLT information.
>
> [^issue2_stack_code.zip]
> 4，For which event group is this issue faced or is it at the service level?
>
> This issue affects all event groups for both LDCU and NGX.
>
> 5，What kind of messages were communicated before the ECUs went to sleep and what happened just after wakeup?
>
> This issue occurs sporadically on mass-produced vehicles, and the customer did not record Ethernet communication logs.
>
> 6，The client will add DLT logging for SoAd_SetUniqueRemoteAddr.

-------

> [!note]+ 2026-06-05 07:07 · [[Shweta_Ganesh_Dixit|Shweta Ganesh Dixit]]
> +Problem:+
>  * NGX and LDCU socket Ids are getting swapped after wakeup.
>  ** Before sleep
>  *** NGX- 34
>  *** LDCU-33
>  ** After wakeup
>  *** NGX- 33
>  *** LDCU-34
>
> [[Jie_LIU|Jie LIU]] , [[Zhou_ZHOU|Zhou ZHOU]] : Since this issue is very rare and is sporadic, we need the below information as discussed in our meeting to analyze this further.
>
>
>  * +Information needed:+ 
>  ** From where is this SocketId fetched(Dynamic)?
>  ** Where are the debug variables added to get these values in image003.png? Share the debug code  & the configuration code.
>  ** When are these debug variables read(after which message)?
>  ** For which event group is this issue faced or is it at the service level?
>  ** What kind of messages were communicated before the ECUs went to sleep and what happened just after wakeup?
>  ** Add debug code in SoAd_SetUniqueRemoteAddr() to check if this returns the same socket Id which is passed as an input in this API & share the DLT log. Below information is needed from the debug code.
>  *** passed Socket ID in this API
>  *** returned Socket ID from this API
>  *** For the passed ID, if the remote IP and address is configured/not configured.

-------

> [!note]+ 2026-06-04 15:56 · [[Zhou_ZHOU|Zhou ZHOU]]
> Hello [[Shweta_Ganesh_Dixit|Shweta Ganesh Dixit]]，
>
> 1.Is some API called from application for switching the socket states?
>
> The application did not call an API to switch the socket state.
>
> 2.Is there any details on the test steps?
>
> This issue cannot be reproduced in the test environment at present.
> This issue occurs sporadically only after both the LDCU and NGX nodes have entered sleep mode and subsequently been awakened.
>
> 3.Is the issue always reproducible or is sporadic?
>
> Sporadic

-------

> [!note]+ 2026-06-04 12:55 · [[Shweta_Ganesh_Dixit|Shweta Ganesh Dixit]]
> We are not very clear with the test scenario and the problem which is reported.
>  # Is some API called from application for switching the socket states?
>  # Is there any details on the test steps?
>  # Is the issue always reproducible or is sporadic?
>
> meeting scheduled for the same topic on 05.06.2026

-------

> [!note]+ 2026-06-03 14:02 · [[Zhou_ZHOU|Zhou ZHOU]]
> The RTA-CAR version is 9.1.0, and the configuration files for SD and SoAd have been uploaded.
>
> [^Sd_SOA_Config.arxml] *(578 kB)*
>
> [^SoAd_Config.arxml] *(533 kB)*
>
> [^SoAd_SOA_Config.arxml] *(2.97 MB)*
>
> [^Sd_Config.arxml] *(37 kB)*

-------

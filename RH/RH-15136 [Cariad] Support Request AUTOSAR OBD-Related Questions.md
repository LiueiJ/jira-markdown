---
jira_key: RH-15136
jira_url: "https://rtahotline.etas.com/jira/browse/RH-15136"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Medium
project: RH
assignee: Dong LIU
reporter: Dong LIU
tags: [jira/comp/diagnostic-eventstatemgmt, jira/label/cariad, jira/label/vncnms]
fix-versions: []
epic: null
parent: null
created: "2026-02-09T06:44:12.000+0100"
updated: "2026-08-05T06:05:24.000+0200"
synced-at: "2026-09-10T08:07:25.599Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Dear Team, 

Cariad has raised several questions related to AUTOSAR OBD functionality and is requesting support. The details are listed below: 

1. Does our tool support importing OBD-related CDD files (or CDD-like files) to quickly generate configuration files? 

2. After enabling OBD functionality, in RTACAR the parameter DemGeneral → DemClearDTCLimitation can only be configured as DEM_ONLY_CLEAR_ALL_DTCS and cannot be set to other options. The customer would like to use the DemGroupDTCs clear functionality. 

3. After enabling OBD functionality, in the ETAS tool the parameter DemGeneral → DemAgingRequiresTestedCycle only supports configuration as false. The customer expects both true and false to be supported. 

4. Similar to the first question, do DPST services and DTCs (DEM/DEM) support automatic import? 

5. After enabling OBD, the customer cannot find configuration items for TripCounter, HealingCounter, and PermanentDTC. Additionally, How is the priority of extended data configured? 

6. The customer configured DebounceTimeBase, The customer configured DebounceTimeBase, but it did not take effect. After investigation, the customer found that Dem_TimeBasedDebounceMainFunction was not called. 

![[RH-15136-image001.png]].![[RH-15136-image002.png]] 

7. Does RTACAR support separate configuration of P2 and P2* timing parameters for OBD Classic? 

We would appreciate your support and clarification on the above topics. 

Best regards,

 

  **Dong LIU** 

 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China (ETAS-ECM/XSF-CN)

 Bosch (China) Investment Ltd. | 333 Fuquan (N.) Road | Shanghai 200335 |  P.R. CHINA 

 Tel. +86 21 2218-4408 | [Dong.LIU5@etas.com!mail_small.gif!](mailto:Dong.LIU5@etas.com)

## 关联

- mentions: [[RHEU-4920 Debounce Timer correctly config on Isolar but not properly working]]
- mentions: [[BBM-37192 [Honda_MY27] SessionParameterRecord (P2Server_max = 100ms)(P2*Server_max = 5000ms (0x01F4)) For Service 10]]
- is mentioned in: [[RH-16827 [VNVNMS][CARIAD]P2 / P2 Configuration for OBD Diagnostic Services (Classic OBD / OBD on UDS)]]

## 评论

> [!note]+ 2026-05-07 11:37 · JSM Service Bot
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2026-04-23 03:58 · Phuong Nguyen Le
> Dong LIU , Jiaqi JI : Can we close this ticket?

-------

> [!note]+ 2026-04-08 13:09 · Khoa Phan Huynh Dang
> {color:#de350b}1. DEM_CLR_DIST and DEM_MIL_DIST were reset when the event memory was cleared.{color}
> {color:#de350b}Refer to E19 figure: The distance traveled IUMPR must NOT be reset as a result of the event memory being cleared.{color}
> {color:#de350b}Whether distance traveled IUMPR is equal to DEM_CLR_DIST or DEM_MIL_DIST ?{color}
>
> DEM_CLR_DIST: Enable the Dem_ReadClrDist API to retrieve the distance for PID 0x31 via a buffer, provided the returned status is E_OK.
>
> DEM_MIL_DIST: Enable the Dem_ReadClrDist API to retrieve the distance for PID 0x21 via a buffer, provided the returned status is E_OK.
>
> {color:#de350b}2. Refer to E20 figure: It should have two Cycle for Ignition ( Ignition Cycle Counter, Fueled Engine Oper-ation Ignition Cycle Counter), but only one configration in RTA-CAR V9.1. How to configure two Ignition Cycle?{color}
>
> The Fueled Engine Operation Ignition Cycle Counter is assigned to ITID 0x12, which must be defined as the new ITID in your project. Our tool will generate a corresponding API, and you are responsible for implementing the logic within it.
>
> {color:#de350b}3. How to configure the "monitor activity data" in RTA-CAR V9.1?{color}
>
> "DEM_MONITOR_ACTIVITY_DATA" is related to SMAD, and it was implemented from the RTA-CAR version 12.9.0. Then, this element was not created in the RTA-CAR V9.1
>
> {color:#de350b}4. Is OBD only supported DEM_OBD_PRIMARY_ECU, unsupported DEM_OBD_MASTER_ECU and DEM_OBD_DEP_SEC_ECU in RTA-CAR V12.11? see E21 log.{color}
>
> + This is a deviation from AUTOSAR which requires Dem_DcmReadDataOfPID21 to be available if DemOBDSupport is not DEM_OBD_NO_OBD_SUPPORT. However, for compatibility with Dem_SetDataOfPID21, which is only supported for DEM_OBD_PRIMARY_ECU. It is decided to remove the scope of "{*}DEM_OBD_DEP_SEC_ECU{*}", because with this type of ECU, there is no ability to set PID21 calculation of PID21.
>
> +  Configuring to DEM_OBD_MASTER_ECU will throw an error as mentioned in the release note.
>
> ![[RH-15136-image-2026-04-08-18-08-50-153.png]]

-------

> [!note]+ 2026-04-08 09:01 · Jiaqi JI
> Hi Khoa Phan Huynh Dang Dang Ho Anh ,
>
> Add question:
> Is OBD only supported DEM_OBD_PRIMARY_ECU, unsupported DEM_OBD_MASTER_ECU and DEM_OBD_DEP_SEC_ECU in RTA-CAR V12.11? see E21 log.
>
> log:
> - rba_DemObdBasic_validator --> Error (Executed for 00:00:00:211 hh:mm:ss:ms)
> Exception: Error during oAW script execution rba_DemObdBasic_Validate.mwe: Execution of rba_DemObdBasic_Validate.mwe reported an error:DemGeneral: For now only DEM_OBD_PRIMARY_ECU is supported for Dem with OBD
>
> Thanks a lot!

-------

> [!note]+ 2026-04-02 09:41 · Jiaqi JI
> ![[RH-15136-4.2 question added 2.png]] ![[RH-15136-4.2 question added 1.png]]

-------

> [!note]+ 2026-04-02 09:40 · Jiaqi JI
> Hi Khoa Phan Huynh Dang Khoa Phan Huynh Dang ,
>
> 3 questions added as following:
>
> 1. DEM_CLR_DIST and DEM_MIL_DIST were reset when the event memory was cleared.
> Refer to E19 figure: The distance traveled IUMPR must NOT be reset as a result of the event memory being cleared.
> Whether distance traveled IUMPR is equal to DEM_CLR_DIST or DEM_MIL_DIST ?
> 2. Refer to E20 figure: It should have two Cycle for Ignition ( Ignition Cycle Counter, Fueled Engine Oper-ation Ignition Cycle Counter), but only one configration in RTA-CAR V9.1. How to configure two Ignition Cycle?
> 3. How to configure the "monitor activity data" in RTA-CAR V9.1?

-------

> [!note]+ 2026-04-01 11:17 · Jiaqi JI
> Hello Khoa Phan Huynh Dang Dang Ho Anh ,
>
> For question:
> Are there any matching configuration items in ETAS tool which are equal to variable"healing_inhibition","healing_inhibition_cnt","healing_TripCounter_cnt" referring to below healing diagram ?{}
> Cariad add that:
> The current ETAS process cannot meet the process shown in the Figure 4-27 （E-15）.
> Example： If healing_Inhibition_cnt > ConfirmationThreshold, the status of TF/TFTOC/... should be frozen. When DTC recovers, the tested result is that the status of TF/TOC/... is changed. The expetced result is that the status cannot be changed, and can only be reset through the RID.

-------

> [!note]+ 2026-03-30 08:22 · Jiaqi JI
> Hello Khoa Phan Huynh Dang Dang Ho Anh both,
>
> Customer adds questions: Please give feedback on tomorrow morning follow-up meeting. Thanks a lot!
>  # Do all IUMPR counters provide APIs for ASW to call, with ASW handling the conditional checks? Does BSW only implement auto-increment and not handle conditional checks?
> What is the IUMPR processing flow? 
> BSW provides the interface for ASW calls, and ASW implements the conditional checks. BSW does not implement the conditional checks; BSW only implements auto-increment.
>  # 
> How to configure and implement ECU post-run diagnostics?

-------

> [!note]+ 2026-03-24 04:16 · Khoa Phan Huynh Dang
> Hello Dong LIU , Jiaqi JI , could you please help input new questions from the customer? This will allow us to proceed with the ticket and seek further support if necessary.

-------

> [!note]+ 2026-03-17 12:37 · Gunjan Pradip Mantala
> Hi Khoa Phan Huynh DangKhoa
>
> Thank you for reaching out to us!
>
> *Answer to Q10 *:
> Dem supports IUMPR calculation, and the same information can be accessed via Infotype $08 or $0B depending on the engine type. The response to an Infotype request follows SAE J1979 legislation and includes the General Denominator Counter, Ignition Cycle Counter, and IUMPR numerator and denominator counters based on the IUMPR groups configured in Dem.
>
> Dem also supports monitor activity data reporting, which can be configured as part of Extended Data record 0x93.
>
> The terms “{_}Fueled Engine Operation Ignition Cycle counter{_}” and “{_}distance traveled IUMPR{_}” is new to us and would expect more details on it.
>
> **Answer to Q13 :**
> If “VTD-related data” refers to snapshot data (Freeze Frame / Extended Data) or runtime PID data such as $21, $31, $4D, $4E, etc., as described in AUTOSAR [SWS_Dem_00293], then yes, this is supported in Dem.
> If the term refers to anything other than the above, please provide more details for clarification.
> {*}Note{*}: Dem does not support the calculation of PKE or EOE values.
>
> Best Reards,
> Gunjan Mantala

-------

> [!note]+ 2026-03-17 10:08 · Sobin Peter
> Hi Khoa Phan Huynh Dang ,
>
> Answer to Q7:
>
> As per autosar, P2 and P2* timing configurations can't be done corresponding to protocols directly . 
>
> But, you may try using DcmTimStrP2ServerAdjust, which is configurable per protocol to have different timing for different protocols. Dcm calculates the P2 timer as DcmDspSessionP2ServerMax - DcmTimStrP2ServerAdjust. So,it will be like you have timings specific to a protocol.
>
>
>
> Hi Gunjan Pradip Mantala , Please have a look at the Dem queries.

-------

> [!note]+ 2026-03-16 04:26 · Khoa Phan Huynh Dang
> After **Monday's meeting** (3/16/2026), we still have some **follow-up** questions:
>
>
>
> {color:#ff0000}Q7*: Can ETAS configured the P2 and P2* timing for OBD Classic independently?{color}
>
> {color:#57d9a3}Q10*: There are a lot of data contained in IUMPR such as “IUMPR counters, General Denominator Counter, Ignition Cycle Counter, Fueled Engine Oper-ation Ignition Cycle Counter, distance traveled IUMPR, and monitor activity”， please help to confirm whether all these data are configurable or not.{color}
>
> {color:#ff8b00}Q12*: AgingCounter actually increments (++), but is expected to decrement (--); a discrepancy exists.{color}
>
> {color:#403294}Q13* Calculation of VTD-related data, for example, PKE, EOE,... Can ETAS tool support it ?{color}
>
>
>
> {color:#403294}Hello Raghuram Telagamsetti, Gunjan Pradip Mantala , could you help me support the questions *Q7, Q10 and Q13*{color}
>
>
>
> {color:#403294}Currently, the customer are using the **RTA-CAR 9.1.x (official)** and *RTA-CAR 12.11.x*{color}

-------

> [!note]+ 2026-03-12 10:21 · Jiaqi JI
> [^ETAS Configuration OPL.xlsx]

-------

> [!note]+ 2026-03-08 18:41 · Khoa Phan Huynh Dang
> *{color:#FF0000}Q12.  An error occurred when generating BSW about{color}*{color:#FF0000} OBDonUDS (base on {*}RTA-CAR 12.11.0VCTCESR1pr1{*})?{color}
>
> {color:#FF0000}    see the attach file OBDonUDS-rta-bsw.log.{color}
>
> Regarding the most recent error,
>
> ![[RH-15136-image-2026-03-09-00-08-07-366.png]]
>
> The issue arises from the following:
>
> + The project has the {*}OBD feature enabled{*}.
>
> + There is **at least one Extended Data Record** where '{*}DemDataElementClass{*}' is configured as type '{*}DEM_MONITOR_ACTIVITY_DATA{*}'."
>
> ![[RH-15136-image-2026-03-09-00-10-53-729.png]]
>
> ------------
>
> +*Note:*+
>
> + "{*}demFreezeMANWhenGeneralDenominatorInhibited{*}" is a new attribute which is first introduced in **RTA-CAR 12.9.0.** It allows pausing SMAD counters when the general denominator is inhibited. For details: 
>
> ![[RH-15136-image-2026-03-09-00-17-28-724.png]]
>
> + It seems like something is wrong in the file "{*}Dem_EcucParamDef{*}" of customer ==> **Re-check with them**

-------

> [!note]+ 2026-03-08 15:57 · Khoa Phan Huynh Dang
> The remaining questions focus on **Classic OBD** configuration in **RTA-CAR 9.1.x** as follows:
>
> {color:#de350b}Q11:Are there any matching configuration items in ETAS tool which are equal to variable"healing_inhibition","healing_inhibition_cnt","healing_TripCounter_cnt" referring to below healing diagram ?{color}
>
> {color:#6fc040}[3/6/2026]Cariad:{color}
>
> {color:#6fc040}    DEM_CFG_EVT_INDICATOR is off, so they cannot be used. How to configure to active it in the RTA-CAR 9.1? {color}
>
> {color:#172b4d}For each *EventParameter:*{color}
>
> {*}{color:#172b4d}DEM_CFG_EVT_INDICATOR_ON{color}{*}: when "{*}DemIndicatorAttribute{*}" is configured
>
> ![[RH-15136-image-2026-03-08-21-48-05-716.png]]
>
> {color:#de350b}Q9:An error occurred when generating the code with the configuration of the DemRatio?{color}
>
> {color:#6fc040}[3/6/2026]Cariad:{color}
>
> {color:#6fc040}    We had an error when we configure "Dem_Ratio". (Q9) {color}
>
> {color:#172b4d}The error logs and error snapshots were already sent in Jiaqi’s previous email.{color}
>
> --------------
>
> In this case, the customer has configured the following:
>
> + EngineType: **IGNITION_SPARK**
> + Ratio Kind: **DEM_RATIO_API**
> + DemRatio needs to be mapped to at least **FID (FunctionalDRef)** or **DiagnosticEventRef: {color:#de350b}DiagnosticEventRef{color}**
>
> {color:#172b4d}*==>* Based on the error log, the '{*}demRbSupportFailureDependency{*}' attribute {*}+was not configured+{*}. This attribute must be set to **TRUE** when '{*}demComponentClassRef{*}' is used.{color}
>
> {color:#172b4d}![[RH-15136-image-2026-03-08-21-56-06-906.png]]{color}

-------

> [!note]+ 2026-03-06 09:35 · Jiaqi JI
> Hello Dang Ho Anh Khoa Phan Huynh Dang ,
>
> Please receive customer reply as attachment email. https://rtahotline.etas.com/jira/secure/attachment/314718/Re%20CARIADOBD%20Questions%20Answering%203.7%20reply.msg

-------

> [!note]+ 2026-03-06 09:26 · Jiaqi JI
> Hello Dang Ho Anh Khoa Phan Huynh Dang ,
>
> Cariad gives their information as  zip 2 image and the log file. Please have a check. Thanks!
>
> [^OBDonUDS-rta-bsw.log]
>
> [^rta-bsw 1.log]
>
> ![[RH-15136-image1.png]]
>
> ![[RH-15136-image2.jpg]]

-------

> [!note]+ 2026-03-06 06:20 · Khoa Phan Huynh Dang
> Additionally, the below is the document that can help the customer to configure OBD feature manually
>
> [^ETAS_AR422_OBD_ISO15031_UserManual 1-1.docx]

-------

> [!note]+ 2026-03-06 05:41 · Khoa Phan Huynh Dang
> {color:#de350b}*Q7.  Does RTACAR support separate configuration of P2 and P2* timing parameters for OBD Classic?*{color}
>
> I want to correct some information:
>
> + Firstly, **P2 and P2** timers* are mandatory requirements for both **OBD Classic** and {*}OBDonUDS{*}. However, for the OBD protocol, P2 must be within the range of **0–50 ms** and P2* within {*}0–5 s{*}, as specified in **ISO 15031-5**
>
> **![[RH-15136-image-2026-03-06-11-40-48-843.png]]**
>
> + In practice, these timing parameters are adjustable through {*}UDS services{*}.
>
> + Furthermore, **AUTOSAR** does not explicitly require separate {*}P2 and P2{*}* configurations for different diagnostic protocols. Hence, **RTA-CAR does not support** **separate configuration of P2 and P2** timing parameters for OBD Classic.*
>
> **![[RH-15136-image-2026-03-06-11-41-09-042.png]]**
>
> + OBD can be used after reset ECU. Since OBD is active in the Default Session, it naturally uses the P2 and P2* timers associated with that session.
>
> => Overall, the below are all information I know:
>
> + **P2 and P2** timers* are mandatory requirements for both **OBD Classic** and **OBDonUDS.** However, you only read/change these parameters when {*}use UDS $10{*}. And **OBD classic** also **OBDonUDS** use the **P2 and P2** timers* associated with **the current session** of ECU.

-------

> [!note]+ 2026-03-06 05:39 · Khoa Phan Huynh Dang
> {*}{color:#de350b}Q11:Are there any matching configuration items in ETAS tool which are equal to variable"healing_inhibition","healing_inhibition_cnt","healing_TripCounter_cnt" referring to below healing diagram ?{color}{*}{*}`*`{color:#172b4d} {color}
>
> + I understood the mentioned diagram that describe **the healing process**
>
> **{color:#57d9a3}_healing_TripCounter_cnt_{color}** --> healingCycCtr (do not have configuration) is handle in code generation.
>
> _{color:#57d9a3}*healing_Inhibition_cnt*{color}_ --> failureCycCtr (do not have configuration) is handle in code generation.
>
> _{color:#57d9a3}*healing_Inhibition*{color}_ --> not mentioned in the **RTA-CAR 9.1.x.** However, user can define this variable with the below condition:
>
> ----------------------------------
>
> ({*}Dem_AllEventsIndicatorState{*}[Corresponding_event].{*}failureCycleCounterVal{*} == 0xFFu)
>
> *AND*
>
> ({*}Bit 7{*} of status for this DTC must be set as TRUE)
>
> -----------------------------------
>
> When an event map to 1 DTC (event set TRUE as available):
>
> + {color:#de350b}*DemEventFailureCycleThreshold*{color} of the event will be set as **{color:#ffab00}_failureCycCtrThreshold_{color}**
>
> + {color:#de350b}*DemIndicatorHealingCycleCounterThreshold*{color} of the event will be set as **{color:#ffab00}_healingCycCtrThreshold_{color}**

-------

> [!note]+ 2026-03-06 05:28 · Khoa Phan Huynh Dang
> *{color:#de350b}Q8: How to active the function DEM_CFG_OBD_IUMPR ?
>
> Q9:An error occurred when generating the code with the configuration of the DemRatio? 
>
> Q10: Is The implementation of IUMPR in BSW or ASW ? how to configure items as follows:{color}*
>
> + All above questions are related to {*}IUMPR handling{*}.
>
> + ITIDs **0x08** and **0x0B** are related to IUMPR. Depend on their engine type, customer must set "{*}DemOBDEngineType{*}" as "{*}DEM_IGNITION_COMPRESSION{*}" for **ITID 0x0B** or "{*}DEM_IGNITION_SPARK{*}" for **ITID 0x08**
>
> + To use this feature (IUMPR), user must configure "{*}Dem_Ratio",{*} 
>
> **![[RH-15136-image-2026-03-06-10-59-05-072.png]]**
>
> {+}*Note*{+}: ** this is the limitation of IUMPR handling in {color:#de350b}*RTA-CAR version 9.1.x*{color}
>
> **![[RH-15136-image-2026-03-06-11-11-07-496.png]]**

-------

> [!note]+ 2026-03-06 04:55 · Khoa Phan Huynh Dang
> {color:#172b4d}Hello {*}Jiaqi{*},{color}
>
> All below info are my knowledge about the **RTA-CAR version 9.1.x** which the customer is using:
>
> {color:#de350b}*Q1, Q4: Please provide DEXT user manual or ODX user manual which instruct how to do batch configuration*{color}
>
> + In fact, customers can use the ODX importer to generate DEXT files as output.
>
> ![[RH-15136-image-2026-03-06-10-35-10-422.png]]
>
> + To be honest, we don't have the specific document to configure OBD feature via DEXT file. However, you can import **DEXT file** and follow the “{*}AUTOSAR_TPS_DiagnosticExtractTemplate{*}” document on **AUTOSAR** to update/modify and generate your configurations.
>
> [^AUTOSAR_TPS_DiagnosticExtractTemplate.pdf]
>
> + If the customer import DEXT file to generate their OBD feature, they should aware some errors in "{*}ISOLAR-A_Help_ErrorDescription.pdf{*}"
>
> {color:#de350b}*![[RH-15136-image-2026-03-06-10-33-51-841.png]]*{color}
>
> {color:#de350b}*Q2. Does RTA-CAR support clearing all DTCs and clearing OBD group DTCs?*{color}
>
> ![[RH-15136-image-2026-03-06-10-39-51-039.png]]
>  * Due to this limitation, only clear all DTC ({*}0xFFFFFF{*}) are supported. **DEM_DTC_GROUP_EMISSION_REL_DTCS** is not supported, it has invalid value ({*}0x000000u{*}) in the file **_Dem_Types.h_**
>
> **_==>_** Hence, in this RTA-CAR version 9.1.x, {color:#de350b}*you only clear all DTC 0xFFFFFFu*{color} or {color:#de350b}*group of DTC*{color} (The following ranges are reserved by ISO 14229-1 : *+0x000000+* to *+0x0000ff+* and +_0xffff00_+ to {_}+0xffffff+{_}.) for both **OBD classic** and **OBDonUDS**
>
> ![[RH-15136-image-2026-03-06-10-45-54-633.png]]
>
> ![[RH-15136-image-2026-03-06-10-48-06-041.png]]
>
> {color:#de350b}*Q5:  Normally, the data "priority" is included in "Extended data", the priority means priority of DTC, our concern is how to configure this "priority" both in classicOBD and OBDonUDS?*{color}
>
> + Firstly, the customer can define the priority of event/DTC via “{*}DemDTCPriority{*}”, the lower value means the higher priority.
>
> ![[RH-15136-image-2026-03-06-10-50-32-244.png]]
>
> Secondly, if you want to read the priority as “a part of the extended data”:
>
> + **OBD classic** is not supported to read this data for all related DTC SIDs, **only the DTCs are read when you request.**
>
> ![[RH-15136-image-2026-03-06-10-51-47-319.png]]
>
> ![[RH-15136-image-2026-03-06-10-52-23-966.png]]
>
> ![[RH-15136-image-2026-03-06-10-52-49-324.png]]
>
> + Regarding the OBDonUDS or UDS, you can read the extended data via {*}{color:#de350b}SID 0x19 with sub-function 0x16{color}{*}. You can configure the “{*}DemExternalCSDataElement{*}” in your “{*}DemDataElementClass{*}”. Then, link it to your “internal DID” which will read the “priority” data via “{*}DemDidClass{*}” in “{*}DemGeneral{*}”
>
> ![[RH-15136-image-2026-03-06-10-53-38-275.png]]

-------

> [!note]+ 2026-03-02 06:21 · Jiaqi JI
> [^Fw CARIADOBD Questions Answering.msg]

-------

> [!note]+ 2026-03-02 06:21 · Jiaqi JI
> Hi Dang Ho Anh ,questions added as follows. Email as attachment. Thanks a lot!
>
> Q8: How to active the function DEM_CFG_OBD_IUMPR ?
>
> [2/3/2026]Cariad:
>
> **Todo: wait feedback.**
>
> {*}Q9{*}:An error occurred when generating the code with the configuration of the DemRatio? 
> Error during oAW script execution rba_DemObdBasic_Validate.mwe: Execution of rba_DemObdBasic_Validate.mwe reported an error:DemRatio(DemRatio) is configured to be locked by graph, but graph feature is disabled:
>
> [2/3/2026]Cariad: supplementary document for this issue.
>
> ​[20260302-105049 1.png](https://eur03.safelinks.protection.outlook.com/?url=https%3A%2F%2Fvolkswagengroupchina-my.sharepoint.cn%2F%3Ai%3A%2Fg%2Fpersonal%2Fextern_ping_wang3_cariad-technology_cn%2FIQAP-c2cMafCQ4OFaFvN2PnhAfHfU6hD95mBxZkt1Aza-3U&data=05%7C02%7Cjiaqi.ji%40bosch.com%7C2644cce2dbc949f72f1708de7807602c%7C0ae51e1907c84e4bbb6d648ee58410f4%7C0%7C0%7C639080170301770761%7CUnknown%7CTWFpbGZsb3d8eyJFbXB0eU1hcGkiOnRydWUsIlYiOiIwLjAuMDAwMCIsIlAiOiJXaW4zMiIsIkFOIjoiTWFpbCIsIldUIjoyfQ%3D%3D%7C0%7C%7C%7C&sdata=xLtkKJU4xtzclgAEHQgO1BDqILcv7ybU323h45I%2Bhhc%3D&reserved=0)​
>
> ​[20260302-105125 1.jpg](https://eur03.safelinks.protection.outlook.com/?url=https%3A%2F%2Fvolkswagengroupchina-my.sharepoint.cn%2F%3Ai%3A%2Fg%2Fpersonal%2Fextern_ping_wang3_cariad-technology_cn%2FIQDy7zhDSyPQTIsf1nHX60WHASilmRM7DMReQVOA4wD9zl4&data=05%7C02%7Cjiaqi.ji%40bosch.com%7C2644cce2dbc949f72f1708de7807602c%7C0ae51e1907c84e4bbb6d648ee58410f4%7C0%7C0%7C639080170301816277%7CUnknown%7CTWFpbGZsb3d8eyJFbXB0eU1hcGkiOnRydWUsIlYiOiIwLjAuMDAwMCIsIlAiOiJXaW4zMiIsIkFOIjoiTWFpbCIsIldUIjoyfQ%3D%3D%7C0%7C%7C%7C&sdata=8wgzhoCAGHO%2Bhw9LgiYlI%2B1QEIgy79RAYqewFHnnwBg%3D&reserved=0)​
>
> ​[rta-bsw 1.log](https://eur03.safelinks.protection.outlook.com/?url=https%3A%2F%2Fvolkswagengroupchina-my.sharepoint.cn%2F%3Au%3A%2Fg%2Fpersonal%2Fextern_ping_wang3_cariad-technology_cn%2FIQDtgcGZZXGKTKbsentVIkxrAceG7aMvf5WMVm-4usZWDKA&data=05%7C02%7Cjiaqi.ji%40bosch.com%7C2644cce2dbc949f72f1708de7807602c%7C0ae51e1907c84e4bbb6d648ee58410f4%7C0%7C0%7C639080170301847926%7CUnknown%7CTWFpbGZsb3d8eyJFbXB0eU1hcGkiOnRydWUsIlYiOiIwLjAuMDAwMCIsIlAiOiJXaW4zMiIsIkFOIjoiTWFpbCIsIldUIjoyfQ%3D%3D%7C0%7C%7C%7C&sdata=ZNwvyAN7oVLiDwu67%2BNj5%2B7B%2BvX8Z76%2FRYQbO1YHZ%2Fs%3D&reserved=0)​
>
> **Todo: wait feedback.**
>
> **Q10:** Is The implementation of IUMPR in BSW or ASW ? how to configure items as follows:
>
> The General Denominator Counter, 
>
> the Ignition Cycle Counter, 
>
> the Fueled Engine Operation Igni tion Cycle Counter,
>
>  the IUMPR numerators, 
>
> the IUMPR denominators 
>
> [2/3/2026]Cariad:
>
> **Todo: wait feedback.**
>
> {*}Q11:{*}Are there any matching configuration items in ETAS tool which are equal to variable"healing_inhibition","healing_inhibition_cnt","healing_TripCounter_cnt" referring to below healing diagram ?
>
> [2/3/2026]Cariad:
>
> **Todo: wait feedback.**

-------

> [!note]+ 2026-02-27 10:36 · Dang Ho Anh
> Hi Jiaqi JI,
>
> Please check the summary for all questions below:
>
> {*}Q1{*}: Does our tool support importing OBD-related CDD files (or CDD-like files) to quickly generate configuration files?
>
> A1: In case the CDD file here is CANdelaStudio diagnostic description. Currently, the latest official RTA-CAR version (12.9.0) only support to import ODX or DEXT files. 
>
> If there is a tool  you are using can export CDD file to different format, I think you can covert the CDD file to ODX and DEXT file to work with RTA-CAR.
>
> {*}Q2{*}: After enabling OBD functionality, in RTACAR the parameter DemGeneral → DemClearDTCLimitation can only be configured as DEM_ONLY_CLEAR_ALL_DTCS and cannot be set to other options. The customer would like to use the DemGroupDTCs clear functionality.
>
> A2{*}:{*} Following the release note of RTA-CAR, you cannot clear the specific group DTCs. Hence, this parameter is only configured as DEM_ONLY_CLEAR_ALL_DTCS.
>
> ![[RH-15136-image-2026-02-27-11-39-59-270.png]]
>
> **Q3:** After enabling OBD functionality, in the ETAS tool the parameter DemGeneral → DemAgingRequiresTestedCycle only supports configuration as false. The customer expects both true and false to be supported.
>
> A3: The parameter DemAgingRequiresTestedCycle is not supported in official latest version RTA-CAR 12.9.0.
>
> ![[RH-15136-image-2026-02-27-12-43-20-758.png]]
>
> To control the increase of aging counter, user can use **DemRbAgingCounterType** instead.
>
>   ![[RH-15136-image-2026-02-27-12-44-48-932.png]]
>
> **Q4:** Similar to the first question, do DPST services and DTCs (DEM/DEM) support automatic import?
>
> A4: I understood your concerns are related to DPST (Diagnostic Protocol Standard Table{*}){*} and ** DTCs{*}.{*}  As mentioned in the question 1, you can change/update/modify your configuration in DEXT file or ODX files to generate your OBD feature.
>
> {*}Q5{*}: After enabling OBD, the customer cannot find configuration items for TripCounter, HealingCounter, and PermanentDTC. Additionally, How is the priority of extended data configured?
>
> A5: 
>  * Regarding to TripCounter: This counter is defined as the Failure Counter in the Dem.
>
> ![[RH-15136-image-2026-02-25-17-38-43-095.png]]
>
> There is no explicit configuration available for this counter. However, one relevant parameter, {*}DemEventConfirmationThreshold{*}, affects the way the Trip Counter is incremented, as shown in the following image:
>
> ![[RH-15136-image-2026-02-25-17-41-11-684.png]]
>
> **Note:** One deviation I noticed during testing on RTA-CAR 12.9.0 is that the Failure Counter is not reset to 0 after the event is confirmed.
>
> May I ask What are your requirements for this counter? Please let us know for better support.
>  * Regarding to HealingCounter: Same as the “Trip Counter”, there is no explicit configuration of this parameter in Dem, and we also have one relevant parameter is **DemIndicatorHealingCycleCounterThreshold** which affect the way healing counter is handled as following image:
>  ![[RH-15136-image-2026-02-25-17-57-53-334.png]]
>
> What are your requirements for this counter?
>  * Regarding to PermanentDTC: The is one related parameter for it, it is **DemRbOBDSupportBlockingPermanentDTC.** I'm not sure about your specific requirements for PermanentDTC. Could you please let us know if this parameter meets your needs or if you have additional requirements for it?{*}{*}{*}![[RH-15136-image-2026-02-27-12-56-45-989.png]]{*}
>  * Regarding to priority of extended data: ** Extended data ** has no priority. What is your requirement with the priority of extended data?
>
> **Q6:** The customer configured DebounceTimeBase, The customer configured DebounceTimeBase, but it did not take effect. After investigation, the customer found that Dem_TimeBasedDebounceMainFunction was not called.
>
> A6: We need to set DemGeneral->DemRbGeneral->{*}DemRbDebounceTimeBasedTaskTime{*} to empty (means don't config) .
>
> Reference ticket: [RHEU-4920] Debounce Timer correctly config on Isolar but not properly working - RTA Hotline
>
> {*}Q7{*}: Does RTACAR support separate configuration of P2 and P2* timing parameters for OBD Classic?
>
> A7: These parameters are only configured via SID 0x10 of UDS (not support separate configuration of OBD Classic).
>
> Reference ticket: [BBM-37192] [Honda_MY27] SessionParameterRecord (P2Server_max = 100ms)(P2*Server_max = 5000ms (0x01F4)) For Service 10 - RTA Hotline

-------

> [!note]+ 2026-02-26 08:29 · Jiaqi JI
> Hi Su Nguyen Quoc ，which detailed expectations do you need now? 
>
> As customer request, please give feedback before 12:00pm this saturday.
>
> Thanks a lot for support!

-------

> [!note]+ 2026-02-25 12:39 · Su Nguyen Quoc
> Hi Dang, as discussed, let's keep the analysis internal for now. We also need to gather more detailed expectations from the customer in order to propose the right solution.

-------

> [!note]+ 2026-02-25 11:59 · Dang Ho Anh
> Dear All,
>
> I and @Phan Huynh Dang Khoa (MS/EPS22-SWC MS/EPC-PS) have checked for the point 5 (TripCounter and HealingCounter).
>  * {*}Trip Counter{*}: This counter is defined as the Failure Counter in the Dem.
>
> ![[RH-15136-image-2026-02-25-17-38-43-095.png]]
>
> There is no explicit configuration available for this counter. However, one relevant parameter, {*}DemEventConfirmationThreshold{*}, affects the way the Trip Counter is incremented, as shown in the following image:
>
> ![[RH-15136-image-2026-02-25-17-41-11-684.png]]
>
> **One deviation** I noticed during testing on RTA-CAR 12.9.0 is that the Failure Counter is not reset to 0 after the event is confirmed.
>  * {*}Healing Counter{*}: Also, there is no explicit configuration of this parameter in Dem, and we also have one relevant parameter is **DemIndicatorHealingCycleCounterThreshold** which affect the way healing counter is handled as following image:
>
> ![[RH-15136-image-2026-02-25-17-57-53-334.png]]

-------

> [!note]+ 2026-02-10 10:05 · Badun CAI
> 5. TripCounter /HealingCounter  {color:#ff0000}*I didn't  find related information ,need Vietnamese response*{color}
>
>     PermanentDTC refer to :{*}DemRbOBDSupportBlockingPermanentDTC{*}
>
>      **Extended data has no priority**
>
>
>
> 6. Solution: Set DemGeneral->DemRbGeneral->{*}DemRbDebounceTimeBasedTaskTime{*} to empty (means don't config) 
>
>            Refer to: [[RHEU-4920] Debounce Timer correctly config on Isolar but not properly working - RTA Hotline|https://rtahotline.etas.com/jira/browse/RHEU-4920?jql=text%20~%20%22Dem_TimeBasedDebounceMainFunction%22]
>
>
>
> 7. Don't Support  
>
>            Refer to:  [[BBM-37192] [Honda_MY27] SessionParameterRecord (P2Server_max = 100ms)(P2*Server_max = 5000ms (0x01F4)) For Service 10 - RTA Hotline|https://rtahotline.etas.com/jira/browse/BBM-37192?jql=text%20~%20%22P2%20timing%20OBD%22]

-------

> [!note]+ 2026-02-10 08:59 · Junsheng ZHANG
> 2.Not supported
>
> ![[RH-15136-image-2026-02-10-15-48-36-938.png]]
>
> 3.instead of DemRbAgingCounterType
>
> ![[RH-15136-image-2026-02-10-15-57-12-499.png]]![[RH-15136-image-2026-02-10-15-57-26-151.png]]
>
> 4.I'm not sure what DPST services are, but our diagnostic only supports ODX files and DEXT files

-------

---
jira_key: RH-17007
jira_url: "https://rtahotline.etas.com/jira/browse/RH-17007"
server: rtahotline
kind: hotline
type: Support
status: Waiting for Customer
priority: Critical
project: RH
assignee: junsheng.zhang@bosch.com
reporter: junsheng.zhang@bosch.com
tags: [VNCNMS]
components: [RTA-RTE]
fix-versions: []
epic: null
parent: null
created: "2026-08-24T05:38:46.000+0200"
updated: "2026-09-04T11:45:12.000+0200"
synced-at: "2026-09-06T06:58:38.472Z"
jira-orphaned: false
---

# RH-17007 [VNCNMS][VCTC]E2E-related Rte_COMCbk generation is confusing/messy

> [!jira] Waiting for Customer · Critical · [[Junsheng_ZHANG|Junsheng ZHANG]] · 更新于 2026-09-04T11:45:12.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-17007)

> 标签：#jira/comp/rta-rte #jira/label/vncnms

## 描述

Hi Hotline，

After generating the code, the customer found that the E2E-related Rte_COMCbk generation is messy. In a single Rte_COMCbk, two E2E SignalGroup handlers are implemented, which is clearly wrong. However, please provide some ideas on why this kind of code is generated without triggering any error.

FUNC(void, RTE_CODE)

Rte_COMCbk_SG_ISigGrp_B2_LBMS_SysSt10_E2E_Can_Network_5_Channel_CAN_Rx(void)

{

Std_ReturnType rtn = RTE_E_OK;

VAR(uint8,AUTOMATIC) Rte_Xfrm_Buf_000005&#91;8&#93; =

{ 0U }; 

VAR(uint8,AUTOMATIC) Rte_Xfrm_Buf_000006&#91;8&#93; = { 0U }

;

VAR(uint8,AUTOMATIC) Rte_Xfrm_Buf_000258&#91;8&#93; =

{ 0U }

;

VAR(uint32,AUTOMATIC) Rte_Xfrm_Buf_Len_000005 = sizeof(uint8&#91;8&#93;);

VAR(uint32,AUTOMATIC) Rte_Xfrm_Buf_Len_000006 = 0U;

VAR(uint32,AUTOMATIC) Rte_Xfrm_Buf_Len_000258 = 0U;

VAR(uint8,AUTOMATIC) Rte_Xfrm_Rtn;

Rte_Rx_000791_Composite_Type composite;

StatusType comstatus;

boolean read_ok = TRUE;

/* Box: test begin */

#if !defined(RTE_OMIT_UNINIT_CHECK)

if ( TRUE != Rte_Initialized )

{ return; }

#endif /* !defined(RTE_OMIT_UNINIT_CHECK) */

/* Box: test end */

/* Box: initialize begin */

Rte_TOut_SG_ISigGrp_B2_LBMS_SysSt10_E2E_Can_Network_5_Channel_CAN_Rx = 0;

/* Box: initialize end */

/* Box: receive begin */

comstatus = Com_ReceiveSignalGroupArray(((VAR(Com_SignalIdType, AUTOMATIC))ComConf_ComSignalGroup_SG_ISigGrp_B2_LBMS_SysSt10_E2E_Can_Network_5_Channel_CAN_Rx), &Rte_Xfrm_Buf_000005&#91;0&#93;);

if ( ((VAR(StatusType, AUTOMATIC))E_OK) != comstatus )

{ read_ok = ((VAR(boolean, AUTOMATIC))FALSE); composite.status = ((VAR(Std_ReturnType, AUTOMATIC))comstatus); composite.status = ((VAR(Std_ReturnType, AUTOMATIC))comstatus); }

/* Box: receive end */

/* Box: process begin */

if ( TRUE == read_ok )

{

composite.transformerError.errorCode = 0;

composite.transformerError.transformerClass = RTE_TRANSFORMER_UNSPECIFIED;

if ( RTE_E_HARD_TRANSFORMER_ERROR != rtn )

{

/* Box: xfrmBox for reception-side data transformation for ('ISigGrp_B2_LBMS_SysSt10_E2E' and 'E2E_Profile_02' pair) mapped to 'E2EXf_Inv_Com_SG_ISigGrp_B2_LBMS_SysSt10_E2E_Can_Network_5_Channel_CAN_Rx' begin */

Rte_Xfrm_Rtn = E2EXf_Inv_Com_SG_ISigGrp_B2_LBMS_SysSt10_E2E_Can_Network_5_Channel_CAN_Rx(&Rte_Xfrm_Buf_000006&#91;0&#93;, &Rte_Xfrm_Buf_Len_000006, &Rte_Xfrm_Buf_000005&#91;0&#93;, Rte_Xfrm_Buf_Len_000005);

if ( ((VAR(uint8, AUTOMATIC))0U) != ( Rte_Xfrm_Rtn & 0x80U ) )

{ /* Box: hardErrStructAssignment begin */ composite.transformerError.errorCode = Rte_Xfrm_Rtn; composite.transformerError.transformerClass = RTE_TRANSFORMER_SAFETY; rtn = RTE_E_HARD_TRANSFORMER_ERROR; /* Box: hardErrStructAssignment end */ }

else

{

if ( ((VAR(StatusType, AUTOMATIC))E_OK) != Rte_Xfrm_Rtn )

{

if ( rtn == RTE_E_OK )

{ /* Box: softErrStructAssignment begin */ composite.transformerError.errorCode = Rte_Xfrm_Rtn; composite.transformerError.transformerClass = RTE_TRANSFORMER_SAFETY; rtn = RTE_E_SOFT_TRANSFORMER_ERROR; /* Box: softErrStructAssignment end */ }

}

}

/* Box: xfrmBox for reception-side data transformation for ('ISigGrp_B2_LBMS_SysSt10_E2E' and 'E2E_Profile_02' pair) mapped to 'E2EXf_Inv_Com_SG_ISigGrp_B2_LBMS_SysSt10_E2E_Can_Network_5_Channel_CAN_Rx' end */

}

if ( RTE_E_HARD_TRANSFORMER_ERROR != rtn )

{

/* Box: xfrmBox for reception-side data transformation for ('ISigGrp_B2_LBMS_SysSt10_E2E' and 'ComBasedTransformer_AR_431' pair) mapped to 'ComXf_Inv_Com_SG_ISigGrp_B2_LBMS_SysSt10_E2E_Can_Network_5_Channel_CAN_Rx' begin */

Rte_Xfrm_Rtn = ComXf_Inv_Com_SG_ISigGrp_B2_LBMS_SysSt10_E2E_Can_Network_5_Channel_CAN_Rx(&Rte_Xfrm_Buf_000006&#91;0&#93;, Rte_Xfrm_Buf_Len_000006, &composite.data);

if ( ((VAR(uint8, AUTOMATIC))0U) != ( Rte_Xfrm_Rtn & 0x80U ) )

{ /* Box: hardErrStructAssignment begin */ composite.transformerError.errorCode = Rte_Xfrm_Rtn; composite.transformerError.transformerClass = RTE_TRANSFORMER_SERIALIZER; rtn = RTE_E_HARD_TRANSFORMER_ERROR; /* Box: hardErrStructAssignment end */ }

else

{

if ( ((VAR(StatusType, AUTOMATIC))E_OK) != Rte_Xfrm_Rtn )

{

if ( rtn == RTE_E_OK )

{ /* Box: softErrStructAssignment begin */ composite.transformerError.errorCode = Rte_Xfrm_Rtn; composite.transformerError.transformerClass = RTE_TRANSFORMER_SERIALIZER; rtn = RTE_E_SOFT_TRANSFORMER_ERROR; /* Box: softErrStructAssignment end */ }

}

}

/* Box: xfrmBox for reception-side data transformation for ('ISigGrp_B2_LBMS_SysSt10_E2E' and 'ComBasedTransformer_AR_431' pair) mapped to 'ComXf_Inv_Com_SG_ISigGrp_B2_LBMS_SysSt10_E2E_Can_Network_5_Channel_CAN_Rx' end */

}

composite.status = ((VAR(Std_ReturnType, AUTOMATIC))RTE_E_OK);

Rte_SuspendAllInterrupts();

Rte_Rx_000791 = composite;

Rte_ResumeAllInterrupts();

composite.transformerError.errorCode = 0;

composite.transformerError.transformerClass = RTE_TRANSFORMER_UNSPECIFIED;

if ( RTE_E_HARD_TRANSFORMER_ERROR != rtn )

{

/* Box: xfrmBox for reception-side data transformation for ('ISigGrp_B2_LBMS_SysSt10_E2E' and 'E2E_Profile_02' pair) mapped to 'E2EXf_Inv_Com_SG_ISigGrp_B2_LBMS_SysSt10_E2E_Can_Network_5_Channel_CAN_Rx' begin */

Rte_Xfrm_Rtn = E2EXf_Inv_Com_SG_ISigGrp_B2_LBMS_SysSt10_E2E_Can_Network_5_Channel_CAN_Rx(&Rte_Xfrm_Buf_000258&#91;0&#93;, &Rte_Xfrm_Buf_Len_000258, &Rte_Xfrm_Buf_000005&#91;0&#93;, Rte_Xfrm_Buf_Len_000005);

if ( ((VAR(uint8, AUTOMATIC))0U) != ( Rte_Xfrm_Rtn & 0x80U ) )

{ /* Box: hardErrStructAssignment begin */ composite.transformerError.errorCode = Rte_Xfrm_Rtn; composite.transformerError.transformerClass = RTE_TRANSFORMER_SAFETY; rtn = RTE_E_HARD_TRANSFORMER_ERROR; /* Box: hardErrStructAssignment end */ }

else

{

if ( ((VAR(StatusType, AUTOMATIC))E_OK) != Rte_Xfrm_Rtn )

{

if ( rtn == RTE_E_OK )

{ /* Box: softErrStructAssignment begin */ composite.transformerError.errorCode = Rte_Xfrm_Rtn; composite.transformerError.transformerClass = RTE_TRANSFORMER_SAFETY; rtn = RTE_E_SOFT_TRANSFORMER_ERROR; /* Box: softErrStructAssignment end */ }

}

}

/* Box: xfrmBox for reception-side data transformation for ('ISigGrp_B2_LBMS_SysSt10_E2E' and 'E2E_Profile_02' pair) mapped to 'E2EXf_Inv_Com_SG_ISigGrp_B2_LBMS_SysSt10_E2E_Can_Network_5_Channel_CAN_Rx' end */

}

if ( RTE_E_HARD_TRANSFORMER_ERROR != rtn )

{

/* Box: xfrmBox for reception-side data transformation for ('ISigGrp_B2_LBMS_SysSt10_E2E' and 'ComBasedTransformer_AR_431' pair) mapped to 'ComXf_Inv_Com_SG_ISigGrp_B2_LBMS_SysSt10_E2E_Can_Network_5_Channel_CAN_Rx' begin */

Rte_Xfrm_Rtn = ComXf_Inv_Com_SG_ISigGrp_B2_LBMS_SysSt10_E2E_Can_Network_5_Channel_CAN_Rx(&Rte_Xfrm_Buf_000258&#91;0&#93;, Rte_Xfrm_Buf_Len_000258, &composite.data);

if ( ((VAR(uint8, AUTOMATIC))0U) != ( Rte_Xfrm_Rtn & 0x80U ) )

{ /* Box: hardErrStructAssignment begin */ composite.transformerError.errorCode = Rte_Xfrm_Rtn; composite.transformerError.transformerClass = RTE_TRANSFORMER_SERIALIZER; rtn = RTE_E_HARD_TRANSFORMER_ERROR; /* Box: hardErrStructAssignment end */ }

else

{

if ( ((VAR(StatusType, AUTOMATIC))E_OK) != Rte_Xfrm_Rtn )

{

if ( rtn == RTE_E_OK )

{ /* Box: softErrStructAssignment begin */ composite.transformerError.errorCode = Rte_Xfrm_Rtn; composite.transformerError.transformerClass = RTE_TRANSFORMER_SERIALIZER; rtn = RTE_E_SOFT_TRANSFORMER_ERROR; /* Box: softErrStructAssignment end */ }

}

}

/* Box: xfrmBox for reception-side data transformation for ('ISigGrp_B2_LBMS_SysSt10_E2E' and 'ComBasedTransformer_AR_431' pair) mapped to 'ComXf_Inv_Com_SG_ISigGrp_B2_LBMS_SysSt10_E2E_Can_Network_5_Channel_CAN_Rx' end */

}

/* Removed duplicate write */

Rte_SuspendAllInterrupts();

Rte_memcpy(&Rte_Rx_000792, &composite, sizeof(Rte_Rx_000792_Composite_Type));

Rte_ResumeAllInterrupts();

}

else

{ Rte_SuspendAllInterrupts(); Rte_Rx_000791 = composite; Rte_ResumeAllInterrupts(); Rte_SuspendAllInterrupts(); Rte_memcpy(&Rte_Rx_000792, &composite, sizeof(Rte_Rx_000792_Composite_Type)); Rte_ResumeAllInterrupts(); }

/* Box: process end */

}

 **Junsheng ZHANG** 

Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

M +86 155 32928056 

[Junsheng.ZHANG@bosch.com!mail_small.gif!](mailto:Junsheng.ZHANG@bosch.com) 

ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

[www.etas.cn](https://www.etas.cn/)  **

ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2026-09-04 11:40 · [[Dang_Ho_Anh|Dang Ho Anh]]
> Hi [[Junsheng_ZHANG|Junsheng ZHANG]] ,
> Could you share the project with me so that I can check it offline? Please also provide the list of `Rte_COMCbk_*` functions that seem to be incorrect.
> The test project I used is also RTA-CAR 12.11.0.

-------

> [!note]+ 2026-09-04 11:15 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> Hi [[Dang_Ho_Anh|Dang Ho Anh]] ,
>
> The issue is not consistent because the content in the RTE_CBK of E2E is duplicated and not consistent with yours, and the customer is using RTA CAR 12.11

-------

> [!note]+ 2026-09-04 10:39 · [[Dang_Ho_Anh|Dang Ho Anh]]
> [[Junsheng_ZHANG|Junsheng ZHANG]] ,
> Please check my comment at [https://rtahotline.etas.com/jira/browse/RH-17007?focusedCommentId=724246&page=com.atlassian.jira.plugin.system.issuetabpanels:comment-tabpanel#comment-724246]
>
> If the root cause I mentioned is correct, the fix is already available in RTE v12.11.2.pr2 and therefore should also be included in the final version v12.11.2.

-------

> [!note]+ 2026-09-04 10:19 · [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]]
> [[Dang_Ho_Anh|Dang Ho Anh]] Yes, i confirm the issue is fixed in RTE v12.11.2.pr2 and therefore in final version v12.11.2.

-------

> [!note]+ 2026-09-04 10:08 · [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]]
> Hi [[Dang_Ho_Anh|Dang Ho Anh]] , may i know RTE command line options used in this project?

-------

> [!note]+ 2026-09-04 09:34 · [[Dang_Ho_Anh|Dang Ho Anh]]
> [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]] Sorry, that was my typo. It should be:  "I saw that those redundant calls of the transformer function are {color:#de350b}removed {color:#172b4d}in the code {color}{color}generated with {{{}RTA-RTE_12.11.2pr2{}}}."

-------

> [!note]+ 2026-09-04 09:22 · [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]]
> HI [[Dang_Ho_Anh|Dang Ho Anh]] I can see the redundant transformer calls are already removed in {{{}RTA-RTE_12.11.2pr2 from your attached files.So i didn't get your statement in comment "I saw that those redundant calls of the transformer function **are generated with** }}{*}{{RTA-RTE_12.11.2pr2{*}{}}}{{{}."{}}}

-------

> [!note]+ 2026-09-04 03:31 · [[JSM_Service_Bot|JSM Service Bot]]
> Reminder for tickets requiring L3 RTE attention:
>
> - Have you attached the configuration?
> - Have you stated which version of RTA-CAR is being used (or, RTA-RTE)?
> - Have you tried the configuration with the latest version of RTA-CAR (or, RTA-RTE)?
> - Have you provided the exact command-line options and exact set of input files fed in to RTA-RTE (this could be the ISOLAR RTE LOG file)?
> - Have you stated the name of the customer?
> - Have you stated the priority / deadline?
> - Have you checked the history of hotline tickets for any relevant keywords?
>
> Not providing this information could delay the solution to the problem.

-------

> [!note]+ 2026-09-04 03:31 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]], this RTA-RTE ticket requires an assignee. As the component lead for RTA-RTE, please ensure that the 'Level 3 Assignee' field is set to the appropriate person that can handle this issue.

-------

> [!note]+ 2026-09-04 03:30 · [[Dang_Ho_Anh|Dang Ho Anh]]
> Hi [[Junsheng_ZHANG|Junsheng ZHANG]] , 
>
> I changed the path, but I was not able to reproduce the issue.
>
> Instead, I found that the issue can be reproduced when one signal group is received by two different SWCs located on different partitions: one SWC is on the same partition as the `Com` module handling the signal group, while the other SWC is on a different partition.
>
> Could you please check with the customer whether the cause I mentioned is correct?
>
> I saw that those redundant calls of the transformer function are generated with {{{}RTA-RTE_12.11.2pr2{}}}.
>
> I have attached the `Rte.c` files from both RTE versions. You can check the function `Rte_COMCbk_SG_ISigGrp_P_ECM_LZCU_100_2_E2E_P_ECM_LZCU_100_2_Can_Network_3_Channel_CAN_Rx()` to see the difference.
>
> Hi [Koduri Vamsi Kiran (ETAS-ECM/XPC-Abt1),](https://confluence.etas-dev.com/display/~kod4abt)
> Could you confirm whether this is a bug and the fix is available in `RTA-RTE_12.11.2pr2` or in the upcoming official release of {{{}RTA-RTE_12.11.2{}}}?
> [^Rte_test.zip]

-------

> [!note]+ 2026-09-03 14:26 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> Hi [[Dang_Ho_Anh|Dang Ho Anh]] ，
>
> The wrong path is  RTA-CAR/1.0.0/dir_out=\{PROJECT_LOC}

-------

> [!note]+ 2026-08-30 07:56 · [[JSM_Service_Bot|JSM Service Bot]]
> [[Junsheng_ZHANG|Junsheng ZHANG]], the comment you've just made is internal. Please note that internal comments do not transition an issue to 'Waiting for Level 2'.

-------

> [!note]+ 2026-08-30 07:56 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> Hi [[Dang_Ho_Anh|Dang Ho Anh]] ,
>
>    The customer reports that the issue is caused by an incorrect RTA-CAR/1.0.0/dir_out=\{OUTPUT_LOC} attribute in buildSettings.properties. This is strange: RTE does not report any error and still generates incorrect code. They want to know why this happens and would like us to fix it—at least to provide accurate error reporting.
>
> ![[RH-17007-image-2026-08-30-13-51-58-695.png]]

-------

> [!note]+ 2026-08-24 12:14 · [[Dang_Ho_Anh|Dang Ho Anh]]
>  Hi [[Junsheng_ZHANG|Junsheng ZHANG]] ,
> As communicated, the customer has resolved the issue by themselves. Please let us know if you need any further support regarding this issue.

-------

> [!note]+ 2026-08-24 09:56 · [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]]
> [[Dang_Ho_Anh|Dang Ho Anh]] From generated code it looks like there is port fan in i.e. more than one receiver in application reading the same signal, however calling same transformer function twice looks not correct. Need input configuration for further analysis.

-------

> [!note]+ 2026-08-24 09:13 · [[Dang_Ho_Anh|Dang Ho Anh]]
> Hi [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]] ,
>
> This is an urgent ticket related to RTE and needs your attention.
>
> I will try to get the project and analyze it first. If you have any ideas, please let us know.
>
> Thanks a lot.

-------

> [!note]+ 2026-08-24 08:54 · [[Dang_Ho_Anh|Dang Ho Anh]]
> [[Junsheng_ZHANG|Junsheng ZHANG]] ,
> Could you share the project to the ticket?

-------

> [!note]+ 2026-08-24 07:50 · [[Jiaqi_JI|Jiaqi JI]]
> Hi  [[Phuong_Nguyen_Le|Phuong Nguyen Le]] Phuong,
>
> We found one critical issue which is urgent for us because customer will come to production line tomorrow.
>
> Please help us have a check. Thanks a lot!
>
> BR,
>
> Jiaqi

-------

> [!note]+ 2026-08-24 07:47 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Junsheng ZHANG, please note that this issue was made with VNCNMS in the summary and has been sent to the relevant queue by adding the VNCNMS label.

-------

> [!note]+ 2026-08-24 05:42 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> [^Rte(1).c]

-------

> [!note]+ 2026-08-24 05:41 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Junsheng ZHANG. Your issue is set to "Critical" priority.
> Please ensure that there is a reasonable justification for this listed in the issue description, otherwise the priority may be reviewed and adjusted during triage.
> Kind regards

-------

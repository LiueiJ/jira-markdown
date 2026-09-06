---
jira_key: RH-17016
jira_url: "https://rtahotline.etas.com/jira/browse/RH-17016"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Critical
project: RH
assignee: junsheng.zhang@bosch.com
reporter: junsheng.zhang@bosch.com
tags: [VNCNMS]
components: []
fix-versions: []
epic: null
parent: null
created: "2026-08-24T19:40:47.000+0200"
updated: "2026-08-25T11:00:56.000+0200"
synced-at: "2026-09-06T06:58:38.472Z"
jira-orphaned: false
---

# RH-17016 [VNCNMS][VCTC]RTE Task: Runnable Period Variable Generation Error

> [!jira] Closed · Critical · [[Junsheng_ZHANG|Junsheng ZHANG]] · 更新于 2026-08-25T11:00:56.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-17016)

> 标签：#jira/label/vncnms

## 描述

Hi hotline, 

 Customer testing found that the CAN signal period was inaccurate. After comparison, it was discovered that in OsTask_BSW_Core0_100ms, every Runnable had been additionally applied with a condition like Rte_RECount_OsTask_BSW_Core0_100ms_divby_0*. As a result, the execution time increased by a multiple. 

 Actually, the smallest-period Event should not have been executed again with an additional counter-based condition, but in the code we cannot find the smallest-period Event. In the configuration, 100 ms is set as the smallest-period Event. However, this also causes the current 100 ms Event to execute only once every 1 second. 

 Please help check why code like this was generated incorrectly. If you need to review the configuration, please contact me directly. 

TASK(OsTask_BSW_Core0_100ms) 

{ 

 /* Box: Implicit Buffer Initialization begin */ 

 /* Box: Implicit Buffer Initialization end */ 

 /* Box: Implicit Buffer Fill begin */ 

 /* Box: Implicit Buffer Fill end */ 

 /* Box: BSWImpl9_Com begin */ 

 if ( Rte_RECount_OsTask_BSW_Core0_100ms_divby10_0 == ((VAR(uint8, AUTOMATIC))0U) ) 

 { 

 /* Box: populateTask begin */ 

 Com_MainFunctionRx_ComMainFunctionRx_100ms(); 

 /* Box: populateTask end */ 

 } 

 /* Box: BSWImpl9_Com end */ 

 /* Box: CPT_CDD_ComUser begin */ 

 if ( Rte_RECount_OsTask_BSW_Core0_100ms_divby10_0 == ((VAR(uint8, AUTOMATIC))0U) ) 

 { 

 /* Box: populateTask begin */ 

 CDD_ComUser_Rx_MainFunction_100ms(); 

 /* Box: populateTask end */ 

 } 

 /* Box: CPT_CDD_ComUser end */ 

 /* Box: CPT_CDD_ComUser begin */ 

 if ( Rte_RECount_OsTask_BSW_Core0_100ms_divby20_0 == ((VAR(uint8, AUTOMATIC))0U) ) 

 { 

 /* Box: populateTask begin */ 

 CDD_ComUser_Rx_MainFunction_200ms(); 

 /* Box: populateTask end */ 

 } 

 /* Box: CPT_CDD_ComUser end */ 

 /* Box: CPT_CDD_ComUser begin */ 

 if ( Rte_RECount_OsTask_BSW_Core0_100ms_divby50_0 == ((VAR(uint8, AUTOMATIC))0U) ) 

 { 

 /* Box: populateTask begin */ 

 CDD_ComUser_Rx_MainFunction_500ms(); 

 /* Box: populateTask end */ 

 } 

 /* Box: CPT_CDD_ComUser end */ 

 /* Box: CPT_CDD_ComUser begin */ 

 if ( Rte_RECount_OsTask_BSW_Core0_100ms_divby100_0 == ((VAR(uint8, AUTOMATIC))0U) ) 

 { 

 /* Box: populateTask begin */ 

 CDD_ComUser_Rx_MainFunction_1000ms(); 

 /* Box: populateTask end */ 

 } 

 /* Box: CPT_CDD_ComUser end */ 

 /* Box: CPT_CDD_ComUser begin */ 

 if ( Rte_RECount_OsTask_BSW_Core0_100ms_divby10_0 == ((VAR(uint8, AUTOMATIC))0U) ) 

 { 

 /* Box: populateTask begin */ 

 CDD_ComUser_MainFunction_100ms(); 

 /* Box: populateTask end */ 

 } 

 /* Box: CPT_CDD_ComUser end */ 

 /* Box: CPT_CDD_ComUser begin */ 

 if ( Rte_RECount_OsTask_BSW_Core0_100ms_divby20_0 == ((VAR(uint8, AUTOMATIC))0U) ) 

 { 

 /* Box: populateTask begin */ 

 CDD_ComUser_MainFunction_200ms(); 

 /* Box: populateTask end */ 

 } 

 /* Box: CPT_CDD_ComUser end */ 

 /* Box: CPT_CDD_ComUser begin */ 

 if ( Rte_RECount_OsTask_BSW_Core0_100ms_divby50_0 == ((VAR(uint8, AUTOMATIC))0U) ) 

 { 

 /* Box: populateTask begin */ 

 CDD_ComUser_MainFunction_500ms(); 

 /* Box: populateTask end */ 

 } 

 /* Box: CPT_CDD_ComUser end */ 

 /* Box: CPT_CDD_ComUser begin */ 

 if ( Rte_RECount_OsTask_BSW_Core0_100ms_divby100_0 == ((VAR(uint8, AUTOMATIC))0U) ) 

 { 

 /* Box: populateTask begin */ 

 CDD_ComUser_MainFunction_1000ms(); 

 /* Box: populateTask end */ 

 } 

 /* Box: CPT_CDD_ComUser end */ 

 /* Box: BSWImpl9_Com begin */ 

 if ( Rte_RECount_OsTask_BSW_Core0_100ms_divby10_0 == ((VAR(uint8, AUTOMATIC))0U) ) 

 { 

 /* Box: populateTask begin */ 

 Com_MainFunctionTx_ComMainFunctionTx_100ms(); 

 /* Box: populateTask end */ 

 } 

 /* Box: BSWImpl9_Com end */ 

 /* Box: CPT_CDD_CVN_CALID begin */ 

 if ( Rte_RECount_OsTask_BSW_Core0_100ms_divby10_0 == ((VAR(uint8, AUTOMATIC))0U) ) 

 { 

 /* Box: populateTask begin */ 

 CDD_CVN_CALID_MainFunction(); 

 /* Box: populateTask end */ 

 } 

 /* Box: CPT_CDD_CVN_CALID end */ 

 /* Box: CPT_Com_User_E2E begin */ 

 if ( Rte_RECount_OsTask_BSW_Core0_100ms_divby10_0 == ((VAR(uint8, AUTOMATIC))0U) ) 

 { 

 /* Box: populateTask begin */ 

 Com_User_E2E_RX_100ms(); 

 /* Box: populateTask end */ 

 } 

 /* Box: CPT_Com_User_E2E end */ 

 /* Box: CPT_Com_User_E2E begin */ 

 if ( Rte_RECount_OsTask_BSW_Core0_100ms_divby10_0 == ((VAR(uint8, AUTOMATIC))0U) ) 

 { 

 /* Box: populateTask begin */ 

 Com_User_E2E_TX_100ms(); 

 /* Box: populateTask end */ 

 } 

 /* Box: CPT_Com_User_E2E end */ 

 /* Box: Implicit Buffer Flush begin */ 

 /* Box: Implicit Buffer Flush end */ 

 if ( Rte_RECount_OsTask_BSW_Core0_100ms_divby10_0 != ((VAR(uint8, AUTOMATIC))0U) ) 

 { 

 Rte_RECount_OsTask_BSW_Core0_100ms_divby10_0--; 

 } 

 else 

 { 

 Rte_RECount_OsTask_BSW_Core0_100ms_divby10_0 = ((VAR(uint8, AUTOMATIC))9U); 

 } 

 if ( Rte_RECount_OsTask_BSW_Core0_100ms_divby20_0 != ((VAR(uint8, AUTOMATIC))0U) ) 

 { 

 Rte_RECount_OsTask_BSW_Core0_100ms_divby20_0--; 

 } 

 else 

 { 

 Rte_RECount_OsTask_BSW_Core0_100ms_divby20_0 = ((VAR(uint8, AUTOMATIC))19U); 

 } 

 if ( Rte_RECount_OsTask_BSW_Core0_100ms_divby50_0 != ((VAR(uint8, AUTOMATIC))0U) ) 

 { 

 Rte_RECount_OsTask_BSW_Core0_100ms_divby50_0--; 

 } 

 else 

 { 

 Rte_RECount_OsTask_BSW_Core0_100ms_divby50_0 = ((VAR(uint8, AUTOMATIC))49U); 

 } 

 if ( Rte_RECount_OsTask_BSW_Core0_100ms_divby100_0 != ((VAR(uint8, AUTOMATIC))0U) ) 

 { 

 Rte_RECount_OsTask_BSW_Core0_100ms_divby100_0--; 

 } 

 else 

 { 

 Rte_RECount_OsTask_BSW_Core0_100ms_divby100_0 = ((VAR(uint8, AUTOMATIC))99U); 

 } 

 TerminateTask(); 

} /* OsTask_BSW_Core0_100ms */ 

 ** Junsheng ZHANG** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 

 M +86 155 32928056 

 [Junsheng.ZHANG@bosch.com!mail_small.gif!](mailto:Junsheng.ZHANG@bosch.com) 

 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

 [www.etas.cn](https://www.etas.cn)   ** 

 

 ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2026-08-25 10:37 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hi [[Junsheng_ZHANG|Junsheng ZHANG]] ,
>
> After reviewing your project configuration, I noticed that this parameter is not configured correctly. You can remove it and use the timer scheduled in the Scheduling (Task Mapping) configuration instead (or change to 0.1: 100ms). This should resolve your current issue. Could you please try this approach and let me know the test results?
>
> ![[RH-17016-image-2026-08-25-15-12-45-667.png]]
> Thank you for your support, bro [[Dang_Ho_Anh|Dang Ho Anh]] 😊

-------

> [!note]+ 2026-08-25 07:53 · [[Jiaqi_JI|Jiaqi JI]]
> Hi [[Phuong_Nguyen_Le|Phuong Nguyen Le]] ,
>
> Could you give us one engineer ASAP now in 10mins to help investigate with [[Junsheng_ZHANG|Junsheng ZHANG]]  together as customer will upload the mainline code in one hour.
>
> Thanks a lot

-------

> [!note]+ 2026-08-25 07:51 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Junsheng ZHANG, please note that this issue was made with VNCNMS in the summary and has been sent to the relevant queue by adding the VNCNMS label.

-------

> [!note]+ 2026-08-24 19:50 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Junsheng ZHANG. Your issue is set to "Critical" priority.
> Please ensure that there is a reasonable justification for this listed in the issue description, otherwise the priority may be reviewed and adjusted during triage.
> Kind regards

-------

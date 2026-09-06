---
moc: true
project: RH
---

# RH · 项目地图 (MOC)

```dataview
TABLE status, type, assignee
FROM "__jira/RH"
WHERE jira_key AND !moc
SORT status ASC
```

## 无 Epic

- [[RH-12551 LDF Importer is not importing LinTpConfig correctly]] — Closed
- [[RH-12574 [Cariad][Mem Stack] The problem description is not clear about Mem stack]] — Closed
- [[RH-12653 [ConfGen] no error trace with line number provided]] — Closed
- [[RH-12725 [Cariad][Rte] Support for Implicit Communication with Transformers]] — Closed
- [[RH-12756 Cariad WdgM.h recursive invoke head file]] — Closed
- [[RH-12757 Cariad Dcm_Types.h can't recognize Macro]] — Closed
- [[RH-12810 [Cariad][CSXfrm]Invocation Handler Reference is not configured for OperationInvo]] — Closed
- [[RH-12824 Cantrcv_cfg.h issue]] — Closed
- [[RH-12851 [CONFGEN][12.6.0] CanFrameTriggering with extended CANID is not supported]] — Closed
- [[RH-12907 [ConfGen][Gateway] ComIPdu without ComSignal generated for gatewayed Pdu]] — Closed
- [[RH-12910 [CNMS][Cariad]FEE NvM (RTA_CAR 12.3.2) issues with Infenion TC49xN MemAcc ------]] — Closed
- [[RH-12956 [ConfGen] Post process takes long time]] — Closed
- [[RH-12959 [ConfGen] USER_GENERATED tag randomly added or removed]] — Closed
- [[RH-12965 [ConfGen] LinIfRxPdu and LinIfTxPdu for Lin Diag messages and LinIfFrameType]] — Closed
- [[RH-13029 Feedback on data type issues in the CanIf_Init() function of RTA-CAR 12.6.0]] — Closed
- [[RH-13047 [Cariad][ConfGen] XCP Pdu CanIfRxPduCanIdType is forcedly generated to STANDARD_]] — Closed
- [[RH-13161 The buffer length is wrong in Rte_Write_ interface]] — Closed
- [[RH-13182 [CNMS][Cariad]Memmap gen issue in RTA_CAR 12.6]] — Closed
- [[RH-13248 Feedback on issues in the SD module of RTA-CAR 12.6.0]] — Closed
- [[RH-13249 Feedback on data type issues in the CANIF_RXINDICATION_FNAME() function of RTA-C]] — Closed
- [[RH-13446 [Cariad][IpduM] IpduM_InitValues CodeGen Issue]] — Closed
- [[RH-13575 [Cariad] Component Code-Frame issue]] — Closed
- [[RH-13706 [Cariad] SWC Code Frame Datatype inconsistent]] — Closed
- [[RH-14204 [Cariad]DcmDspAuthenticationRoleSize configuration parameter is undersized]] — Closed
- [[RH-14360 [CNMS][Cariad] Improvement required for WdgM M&S]] — Closed
- [[RH-14934 [CNMS][VCTC] Dcm and KeyM Module Issues]] — Closed
- [[RH-15049 [Cariad] BswM ActionList Priority Code Efficiency]] — Waiting for Level 3
- [[RH-15136 [Cariad] Support Request AUTOSAR OBD-Related Questions]] — Closed
- [[RH-15143 MemAcc Module Usage Issue in the Cariad Project]] — Closed
- [[RH-15158 An issue with the MemAcc module]] — Closed
- [[RH-15324 Issues with the CounterOffset and CrcOffset of E2Exf.]] — Closed
- [[RH-15338 [CNMS][VCTC]LinTp configuration error but no error reported]] — Closed
- [[RH-15339 Error generated after importing ecy_hsm]] — Closed
- [[RH-15399 [Cariad] BSW can't be implemented by untrusted application]] — Closed
- [[RH-15475 Question About Placing Fee Module Section in Cache Region]] — Closed
- [[RH-15517 When Mem_write returns E_NOT_OK, Memacc do not terminate current job]] — Closed
- [[RH-15554 [CNMS][VCTC] RTA-SWCL Product Certification Issues]] — Closed
- [[RH-15717 Intermittent SOME IP Subscription Loss After Repeated CDCU_MCU Reset]] — Closed
- [[RH-15727 [CARIAD] OBD Related Questions]] — Closed
- [[RH-15741 [CNMS][VCTC]Rips Issues caused by version upgrades]] — Closed
- [[RH-15864 [VW Cariad CEA2.0] Usage Question for Eth Time Sync Phc Feature]] — Closed
- [[RH-15865 [VW Cariad CEA2.0] Question on the period of FailedAliveSupervisonRefCycleTol]] — Closed
- [[RH-15866 [VW Cariad CEA2.0] Os task meter for max time will decrease sometimes and then g]] — Closed
- [[RH-15894 CANTRCV_OP_MODE_NORMAL in CanTrcv_init]] — Closed
- [[RH-15993 [CNMS][VCTC] Hwcsp Key Issue]] — Closed
- [[RH-16029 [CNMS][VCTC] KeyM causes the HSM to return an ErrorCode]] — Closed
- [[RH-16034 DoIP Response Issue]] — Closed
- [[RH-16047 [CNMS][VCTC] KeyM failed to read certificate from HSM]] — Closed
- [[RH-16053 [CNMS][VCTC] Crypto Invalidation Issue Caused by HSM Self-Update]] — Closed
- [[RH-16066 [CNMS][VCTC]RTE generates case-insensitive issues]] — Closed
- [[RH-16193 The SdBuildClientEntryBuffer function causes the software to enter a trap]] — Solution Proposed
- [[RH-16220 [CNMS][VCTC]Initialization dependency confirmation for the Crypto stack module]] — Closed
- [[RH-16250 VM CEA1.0 Socket connection status abnormal switching]] — Closed
- [[RH-16259 Critical Section Protection Issue in Cross-Core Communication]] — Closed
- [[RH-16271 [Cariad] OBD Question regarding Service 0x04]] — Closed
- [[RH-16304 RTA-CAR Version Migration to 12.11.0PR3 Support]] — Closed
- [[RH-16347 RTE code gen Error parsing input file]] — Waiting for Level 3
- [[RH-16452 AliveTimeout configuration item]] — Closed
- [[RH-16461 [CNMS][VCTC] TBT(Trusted Boot Table) update time too long]] — Closed
- [[RH-16462 [VNCNMS][VCTC] HSM and Crypto interfaces are inconsistent]] — Closed
- [[RH-16478 [VNCNMS][VCTC] E2E Signalgroup Issue]] — Solution Proposed
- [[RH-16490 [VNCNMS][VCTC] Questions on Ratio Group Configuration]] — Closed
- [[RH-16495 [VNCNMS][VCTC]Address assignment problem in ImplicitBuf of RTE]] — Closed
- [[RH-16520 [VNCNMS][VCTC] RTE Error generated by TimeOut function when E2E SignalGroup is u]] — Waiting for Level 2
- [[RH-16540 IOC is generated when no cross core happening between LdCom and SWC]] — Closed
- [[RH-16553 ConfGen error with Lintp pdu]] — Closed
- [[RH-16581 ComXf Issue with Parsing float32 Data Type]] — Waiting for Level 3
- [[RH-16586 ComXf Issue with Parsing sint16 Data Type]] — Closed
- [[RH-16612 [VCTC]Integer Overflow in STBM Macro (STBM_CONVERT_TIMESTAMP_TO_U64)]] — Closed
- [[RH-16639 Ethernet Time Synchronization Deviation Issue]] — Waiting for Level 3
- [[RH-16646 [VNCNMS][VCTC]Questions on Protocol Disable Enable Implementation Options]] — Closed
- [[RH-16647 [VNCNMS][VCTC] OBD DTC Linkage for Platform-Specific DTC Classification]] — Closed
- [[RH-16658 [CNMS][VCTC]Some host code sections for HSM are missing the memory section]] — Waiting for Level 3
- [[RH-16701 [CNMS][VCTC]BlankCheck takes too long, causing memacc to remain busy]] — Closed
- [[RH-16704 [CNMS][VCTC]Remove KeyM Background Event]] — Closed
- [[RH-16705 [VNCNMS] BSWGen issue with missing memory map keywords in Com Stack]] — Closed
- [[RH-16737 [VNCNMS]The TCP and UDP Events are configured within the same Event Group.]] — Closed
- [[RH-16738 [CNMS][VCTC]SchM code definition and references are inconsistent]] — Closed
- [[RH-16761 [VNCNMS][VCTC]Priority issue in DCM]] — Closed
- [[RH-16775 [VNCNMS][VCTC] Avoid Using Static Variables Inside Functions]] — Waiting for Level 3
- [[RH-16780 [VNCNMS][Cariad] Erase reinitialization for DEM NVM block]] — Closed
- [[RH-16784 [VNCNMS][VCTC]Missing critical section protection for IRV array access in genera]] — Solution Proposed
- [[RH-16841 [VNCNMS][VCTC]Critical Section Protection in the SD Module]] — Waiting for Level 3
- [[RH-16863 [VNCNMS][VCTC]AliveTimeout configuration is not taking effect]] — Closed
- [[RH-16903 Xcp_SetControlMode接口使用问题]] — Closed
- [[RH-16912 [VNCNMS][VCTC]Macro definition of DOIP_NACK_OUT_OF_MEMORY]] — Closed
- [[RH-16960 [VNCNMS][VCTC]Multicore issues in DEM]] — Waiting for Level 3
- [[RH-16976 [VNCNMS][VCTC] OBD Cross-Core Implementation and NoOBD Configuration Follow-Up I]] — Closed
- [[RH-16985 [VNCNMS][VCTC] OBDonUDS & OBDclassic Test Issues]] — Solution Proposed
- [[RH-17005 Issues caused by the HSM version update to 3.0.7]] — Waiting for Customer
- [[RH-17007 [VNCNMS][VCTC]E2E-related Rte_COMCbk generation is confusing messy]] — Waiting for Customer
- [[RH-17016 [VNCNMS][VCTC]RTE Task Runnable Period Variable Generation Error]] — Closed
- [[RH-17023 [VCTC] RTA-CAR 12.11 Migration RTA-CAR Toolchain Issues]] — Waiting for Level 3
- [[RH-17069 [VCTC]Crypto causes certificate reading failure.]] — Waiting for Level 3
- [[RH-17070 RTA CAR file parsing error]] — Solution Proposed
- [[RH-17071 [VNCNMS][VCTC]A local variable in Rte_COMCbk is not initialized]] — Solution Proposed
- [[RH-17072 Os generate error]] — Closed
- [[RH-17085 The RTE generated section name is incorrect.]] — Waiting for Customer
- [[RH-17094 [Cariad] CycurHSM Update Compatibility]] — Investigation Required
- [[RH-17095 [Cariad] HWCSP Function Failure After HSM Reboot]] — Investigation Required
- [[RH-17096 [Cariad] HWCSP Initialization Sequence]] — Investigation Required
- [[RH-17106 [VNCNMS][VCTC] DID and Snapshot Data Configuration for Multiple Vehicle Variants]] — Solution Proposed
- [[RH-17113 Lin’s E2E issue]] — Waiting for Customer
- [[RH-17116 [VNCNMS][VCTC]Triggering of TCP messages in the SD module]] — Waiting for Level 2

---
jira_key: RH-16540
jira_url: "https://rtahotline.etas.com/jira/browse/RH-16540"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: High
project: RH
assignee: sisi.tao@bosch.com
reporter: sisi.tao@bosch.com
tags: []
components: [RTA-RTE]
fix-versions: []
epic: null
parent: null
created: "2026-07-01T12:24:59.000+0200"
updated: "2026-07-01T15:24:04.000+0200"
synced-at: "2026-09-06T06:58:38.472Z"
jira-orphaned: false
---

# RH-16540 IOC is generated when no cross core happening between LdCom and SWC

> [!jira] Closed · High · [[Sisi_TAO|Sisi TAO]] · 更新于 2026-07-01T15:24:04.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-16540)

> 标签：#jira/comp/rta-rte

## 描述

**Dear hotline colleagues,**

**I have following RTE issue in RTA-CAR 12.11.0VCTCESR1pr1:**

**Current DataMapping:** 

SWC on **Core2** Rx Port <--{}map to signal with SomIpXf <{}-- LdCom <----SoAd….EthStack on **Core2**

But **IOC** is generated on Rte_LdComCbk and Rte_Read.

**Problem Description:**

During AUTOSAR RTE generation, an unexpected cross-core communication (IOC) generation issue has been observed. The details are as follows:

1. **Signal Chain Background**:
  - A specific LdCom IPDU signal, after passing through a **SomeIp Transformer**, is routed to an RPort of a SWC.
  - This SWC and its RPort are explicitly mapped to run on **Core2**.
2. **Callback Execution Context**:
  - The LdCom callback function LdComCbkRxIndication is triggered by the Eth Stack module.
  - All Eth Stack-related modules in the project, including their MainFunctions, are deployed and running on **Core2**.
3. **Actual RTE Generation Result**:
  - The RTE generator produces the RTE port function (Rte_Rx_000000) corresponding to this LdCom callback in the form of **cross-core communication**. Specifically:
    - In the generated code, Rte_LdComCbkRxIndication_LdComIPdu_XXXX internally calls IocWrite_Rte_Rx_000000.
    - From the code structure, this RTE function is treated as an **IOC write operation from Core0 to Core2**.
4. **Contradiction**:
  - Logically, the SWC RPort resides on Core2, and the LdCom callback is also executed within the Eth Stack context on Core2. Both should be on the same core, and the RTE should generate a same-core direct access rather than a cross-core IOC.
  - However, the actual generated result violates this deployment expectation. Additionally, the global option -inter-ecu-no-ioc cannot be used, as there are other legitimate cross-core DataMappings in the project that must be preserved.
5. **Impact** :
  1. Unwanted lock of the resources, leading to high CPU load.

 **Sisi TAO** 

Cross Functional Regional Solution Field Management - Regional Solution Field Manager China

M +86 133 81555197 

[Sisi.TAO@bosch.com!mail_small.gif!](mailto:Sisi.TAO@bosch.com)

ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

[www.etas.cn](https://www.etas.cn/)

 **ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2026-07-01 15:23 · [[JSM_Service_Bot|JSM Service Bot]]
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

> [!note]+ 2026-07-01 14:28 · [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]]
> Had discussion over call with [[Sisi_TAO|Sisi TAO]],[[Marc_Kaiser|Marc Kaiser]] and agreed to migrate to RTE v12.11.0.

-------

> [!note]+ 2026-07-01 14:15 · [[Auges_Tchouante|Auges Tchouante]]
> Hi [[Sisi_TAO|Sisi TAO]]
> In 12.11.0 we have added below feature
> Version 12.11.0pr5
> Partitions for Com/LdCom callbacks are determined as specified by AUTOSAR If a project has multiple EcucPartitions and uses Com or LdCom, then the project
> must now specify which partition will be used for Com or LdCom callbacks (e.g. Rte_COMCbk_ComSignalReceiver) using EcucPduDefaultPartitionRef,
> EcucPduDedicatedPartitionRef or (for Com only) ComMainRxPartitionRef and ComMainTxPartitionRef. See AUTOSAR [SWS_Rte_91123] and [SWS_Rte_91124] for
> more information about these parameters and the precedence order which applies to them.
>
> Previously, RTA-RTE had only partial support for these parameters and used three methods to specify which partition would be used for Com/LdCom callbacks:
> 1.With the --deviate-event-based-com-mapping option, the partition for Com receive was determined via the Event -> Task -> OsApp -> EcucPartition
> route. This only applied to Com receive and was not used for Com transmit or LdCom. This method is no longer supported.
>
> 2. For LdCom only, the EcucPduDefaultPartitionRef could be used to specify the partitions for LdCom callbacks. This is still supported.
> 3.The EcucPartitionBswModuleExecution parameter would determine the partition for Com and LdCom callbacks if nothing else was specified. This
> parameter has been removed from AUTOSAR and support is deprecated within RTA-RTE. Warning 100246 will be generated if this parameter affects
> Com/LdCom partitioning.
>
> The recommended method to specify a partition for Com or LdCom callbacks is:
> 1.In each ComIPdu/LdComIPdu, ensure that there is a ComPduIdRef/LdComPduRef referencing an EcucPdu,
> 2.reference the correct partition using EcucPduDefaultPartitionRef in that EcucPdu.
> If more specific assignments are required, then EcucPduDedicatedPartitionRef or (for Com only) ComMainRx/TxPartitionRef may also be used.
> The --deviate-bsw-any-partition option has been deprecated and has no effect.
> RTA-RTE now allows BSW modules to be mapped to any OS partition without requiring this option.
> This replaces RTE-9871 and resolves known issue RTE-6185. Errors 100243, 100244, 100245, 100248, 100252, 100253 and warnings 100246 and 100249 will be
> raised if parts of the configuration are missing or incorrect: errors 1355, 2125 and 2465 no longer apply and have been removed
>
> Can you please check if the Partition are assigned to the Pdus?

-------

> [!note]+ 2026-07-01 13:56 · [[Sisi_TAO|Sisi TAO]]
> Hi [[Matthew_Greenfield|Matthew Greenfield]] ,
>
> I'm not allowed to share customer project here. Could you please quick confirm, is this feature actually supported by RTE? Can RTE be aware that LdCom is on the partition other than BswPartition(Core0). 
>
> By the way, the RTE options are:
>
>
> --strict-unconnected-rport-check\=off -nts --os-define-osenv\=RTAOS40 --exclusive-area-optimization\=disable --os-output-param\=changed --notimestamps --use-partition-sections\=on -err\=xml --deviate-bsw-any-partition\=1 --deviate-split-swci-support\=on --deviate-prefer-no-empty-executions\=on --force-basic-tasks  --error-report\=xml --text-value-spec-policy\=symbolic-pdav-always --client-server-global-optimization\=1

-------

> [!note]+ 2026-07-01 13:35 · [[Matthew_Greenfield|Matthew Greenfield]]
> [[Sisi_TAO|Sisi TAO]],
>
> Will you provide a configuration please?

-------

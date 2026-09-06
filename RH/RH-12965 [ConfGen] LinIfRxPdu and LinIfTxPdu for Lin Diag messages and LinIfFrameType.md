---
jira_key: RH-12965
jira_url: "https://rtahotline.etas.com/jira/browse/RH-12965"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Low
project: RH
assignee: sisi.tao@bosch.com
reporter: sisi.tao@bosch.com
tags: [VNCNMS]
components: [Communication-Can-Lin-Fr]
fix-versions: []
epic: null
parent: null
created: "2025-05-07T10:05:15.000+0200"
updated: "2026-07-03T10:28:49.000+0200"
synced-at: "2026-09-06T06:58:38.472Z"
jira-orphaned: false
---

# RH-12965 [ConfGen] LinIfRxPdu and LinIfTxPdu for Lin Diag messages and LinIfFrameType

> [!jira] Closed · Low · [[Sisi_TAO|Sisi TAO]] · 更新于 2026-07-03T10:28:49.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-12965)

> 标签：#jira/comp/communication-can-lin-fr #jira/label/vncnms

## 描述

Dear hotline colleague,

1. I’m using RTA-CAR12.6 confgen to generate Lin stack. For diagnostic messages, LinIfRx/TxPdu container shall not be generated. This will cause codegen error :

The number of instances of element "LinIfUserRxIndicationUL" in parent "/ETAS_Project/EcucModuleConfigurationValuess/LinIf/LinIfGlobalConfig/LinIfChannel_LinPhysicalChannel_LIN01/SlaveResp_LIN01_LinPhysicalChannel_LIN01_IN/LinIfPduDirection/SlaveResp_LIN01" is less than the lower multiplicity of "1".

The number of instances of element "LinIfRxPduRef" in parent "/ETAS_Project/EcucModuleConfigurationValuess/LinIf/LinIfGlobalConfig/LinIfChannel_LinPhysicalChannel_LIN01/SlaveResp_LIN01_LinPhysicalChannel_LIN01_IN/LinIfPduDirection/SlaveResp_LIN01" is less than the lower multiplicity of "1".

The number of instances of element "LinIfUserTxUL" in parent "/ETAS_Project/EcucModuleConfigurationValuess/LinIf/LinIfGlobalConfig/LinIfChannel_LinPhysicalChannel_LIN01/MasterReq_LIN01_LinPhysicalChannel_LIN01_OUT/LinIfPduDirection/MasterReq_LIN01" is less than the lower multiplicity of "1".

The number of instances of element "LinIfTxPduRef" in parent "/ETAS_Project/EcucModuleConfigurationValuess/LinIf/LinIfGlobalConfig/LinIfChannel_LinPhysicalChannel_LIN01/MasterReq_LIN01_LinPhysicalChannel_LIN01_OUT/LinIfPduDirection/MasterReq_LIN01" is less than the lower multiplicity of "1".

The number of instances of element "LinIfRxPduRef" in parent "/ETAS_Project/EcucModuleConfigurationValuess/LinIf/LinIfGlobalConfig/LinIfChannel_LinPhysicalChannel_LIN02/SlaveResp_LIN02_LinPhysicalChannel_LIN02_IN/LinIfPduDirection/SlaveResp_LIN02" is less than the lower multiplicity of "1".

The number of instances of element "LinIfUserRxIndicationUL" in parent "/ETAS_Project/EcucModuleConfigurationValuess/LinIf/LinIfGlobalConfig/LinIfChannel_LinPhysicalChannel_LIN02/SlaveResp_LIN02_LinPhysicalChannel_LIN02_IN/LinIfPduDirection/SlaveResp_LIN02" is less than the lower multiplicity of "1".

The number of instances of element "LinIfTxPduRef" in parent "/ETAS_Project/EcucModuleConfigurationValuess/LinIf/LinIfGlobalConfig/LinIfChannel_LinPhysicalChannel_LIN02/MasterReq_LIN02_LinPhysicalChannel_LIN02_OUT/LinIfPduDirection/MasterReq_LIN02" is less than the lower multiplicity of "1".

The number of instances of element "LinIfUserTxUL" in parent "/ETAS_Project/EcucModuleConfigurationValuess/LinIf/LinIfGlobalConfig/LinIfChannel_LinPhysicalChannel_LIN02/MasterReq_LIN02_LinPhysicalChannel_LIN02_OUT/LinIfPduDirection/MasterReq_LIN02" is less than the lower multiplicity of "1".

The number of instances of element "LinIfRxPduRef" in parent "/ETAS_Project/EcucModuleConfigurationValuess/LinIf/LinIfGlobalConfig/LinIfChannel_LinPhysicalChannel_LIN03/SlaveResp_LIN03_LinPhysicalChannel_LIN03_IN/LinIfPduDirection/SlaveResp_LIN03" is less than the lower multiplicity of "1".

1. LinIfFrameType shall be generated to SRF and MRF. Is it possible to describe it in System Extract?

![[RH-12965-image-2025-10-29-15-35-21-621.png]]

**Sisi TAO** 

Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

M +86 133 81555197 

[Sisi.TAO@bosch.com!mail_small.gif!](mailto:Sisi.TAO@bosch.com) 

ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

[www.etas.com](http://www.etas.com/) **

ETAS – Empowering Tomorrow’s Automotive Software**

## 关联

- is mentioned in: [[RH-16553 ConfGen error with Lintp pdu]]

## 评论

> [!note]+ 2026-05-26 11:38 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2025-12-22 10:48 · [[Xiao_BAI|Xiao BAI]]
> Hello [[Marc_Kaiser|Marc Kaiser]] , I think it will be fixed in RTA-CAR 12.11.0 is acceptable.

-------

> [!note]+ 2025-12-22 10:18 · [[Marc_Kaiser|Marc Kaiser]]
> Hello [[Xiao_BAI|Xiao BAI]], you are right. This is currently still not fixed in ConfGen 12.8.0. My previous comment from 18.08 was incorrect.
>
> We will fix it now. This is the ticket for tracking: [https://jira.etas-dev.com/browse/ARCCFGEN-1998] 
>
> It will be fixed in RTA-CAR 12.11.0. I hope this is acceptable? If not we will make a ConfGen customization installer for earlier RTA-CAR versions.

-------

> [!note]+ 2025-12-22 07:51 · [[Marc_Kaiser|Marc Kaiser]]
> Hello [[Xiao_BAI|Xiao BAI]], thank you for testing this. I will recheck why it is not fixed in 12.8.0.

-------

> [!note]+ 2025-12-22 06:42 · [[Xiao_BAI|Xiao BAI]]
> Hello [[Marc_Kaiser|Marc Kaiser]] ,
>
> I tested this feature, and found it has not been fixed in 12.8.0. Can you please confirm whether this feature has been fixed in 12.8.0?

-------

> [!note]+ 2025-12-17 06:19 · [[Sisi_TAO|Sisi TAO]]
> Hi, [[Xiao_BAI|Xiao BAI]] 
>
> Can you try if this feature is fixed in RTA-CAR 12.11.0VCTCESR1pr1?

-------

> [!note]+ 2025-08-18 12:12 · [[Marc_Kaiser|Marc Kaiser]]
> ![[RH-12965-screenshot-1.png]]

-------

> [!note]+ 2025-05-09 10:54 · [[Sisi_TAO|Sisi TAO]]
> [[Marc_Kaiser|Marc Kaiser]] Hi Marc, attached is the project
> [^Config.zip]

-------

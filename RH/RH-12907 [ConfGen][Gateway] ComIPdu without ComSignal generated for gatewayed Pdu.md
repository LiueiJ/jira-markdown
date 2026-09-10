---
jira_key: RH-12907
jira_url: "https://rtahotline.etas.com/jira/browse/RH-12907"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Medium
project: RH
assignee: Sisi TAO
reporter: Sisi TAO
tags: [jira/label/cariad, jira/label/vncnms]
fix-versions: []
epic: null
parent: null
created: "2025-04-27T11:31:06.000+0200"
updated: "2026-05-18T07:08:15.000+0200"
synced-at: "2026-09-10T08:07:25.599Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Dear hotline colleague,

Tool Version: RTA-CAR 12.6

Cariad has the use case that ISignalIPdu is gatewayed but not processed by the ECU swc itself. So the expected pdur routing path should be CanIf-PduR-CanIf.

But the result is two PduRRoutingPaths are generated: CanIf-PduR-CanIf and CanIf-PduR-Com. Even I removed all signals under the pdu in System Extract, the empty ComIPdu is still generated (as shown in picture).

Please take the Pdu ‘I_RDCU_ThermalSys2’ as example. I’d like to know is the current version of RTA-BSW support this use case and how could it work. Thank you.

![[RH-12907-image001.png]]

 **Sisi TAO** 

Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

M +86 133 81555197 

[Sisi.TAO@bosch.com!mail_small.gif!](mailto:Sisi.TAO@bosch.com) 

ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

[www.etas.com](http://www.etas.com/)  **

ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2026-05-18 07:07 · Khoa Phan Huynh Dang
> As confirmation from Xiao BAI , this issue has been fixed in RTA-CAR 12.11.0VCTCESR1pr1, ticket can be closed now

-------

> [!note]+ 2026-04-30 11:37 · JSM Service Bot
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2026-04-15 18:48 · JSM Service Bot
> This issue has not received any response for 2 weeks and will now be automatically moved to Solution Proposed.

-------

> [!note]+ 2026-04-01 11:38 · Phuong Nguyen Le
> Hi Xiao BAI , Did you check this issue in RTA-CAR 12.11.0VCTCESR1pr1?
>
> Can you share some update?

-------

> [!note]+ 2025-12-18 13:49 · Marc Kaiser
> Hello Xiao BAI,
>
> yes. I am certain that this issue was fixed in RTA-CAR 12.8.0 and newer.

-------

> [!note]+ 2025-12-18 11:32 · Xiao BAI
> Hello Marc Kaiser , is this issue fixed in RTA-CAR 12.11?

-------

> [!note]+ 2025-12-17 07:20 · Sisi TAO
> Hi Xiao BAI ,
>
> Could you please check if this issue is fixed in RTA-CAR 12.11.0VCTCESR1pr1
>
> Please use [^Config.zip]to test. 
>
> Gateway Pdus without Signals shall not be generated in ComIPdu.

-------

> [!note]+ 2025-07-09 04:58 · Mingye YUAN
> Confirmed from Mr. Fargus Alex, this issue will be solved in CAR 12.8.0.

-------

> [!note]+ 2025-06-25 10:53 · Marc Kaiser
> Hello Alex Fargus. We fixed this issue with this ticket: [https://jira.etas-dev.com/browse/ARCCFGEN-1484]
>
>
>
> We fixed it with a Improvement of the Algorithm that was also simultaniously requested from MPCI.

-------

> [!note]+ 2025-06-25 05:49 · Alex Fargus
> Marc Kaiser Is there a ticket so that we can track this issue is resolved in CAR 12.8.0 (as you state in the comment below).

-------

> [!note]+ 2025-05-09 09:15 · Marc Kaiser
> You are right. My explanation with PduPort is not correct. Because if that explanation where true, actually we would have to take your Pdu to Com, since it does have IN PduPort.
> I made a mistake when explaining. It is not the PduPort that matters. It is the SignalPort that decides if it should go to Com/LdCom or not. Your ISignalIPdu must have a PduPort on this EcuInstance. It can also have ISignalToIPduMappings inside. You do not have to remove them! But the ISignals mapped to the ISignalIPduMappings can not have ISignalPorts on your EcuInstance. The ISignalPorts would mean that the Signal has to be consumed in this EcuInstance. Not having them means the Pdu must be consumed but the Signals must not be consumed. If the Signals must not be consumed it doesnt have to go to Com/LdCom. This is your use case.

-------

> [!note]+ 2025-05-08 13:15 · Marc Kaiser
> Hello Sisi,
>
> Thank you for reporting this to us. We have analyzed this topic. We found that the root cause was a bug in Generic Importer. The Pdu Gateway FanOut case was not properly handled in the PduR Importer code. The CFG you have provided was fine even before you deleted the ISignalToIPduMappings.
>
> (It is unnecessary to delete these ISignalToIPduMappings in the ISignalIPdu, as you did. This configuration is not what decides if it should go to Com or not. The CFG that decides if this Pdu should go to Com is, if the ISignalIPdu has a PduTriggering, that is referencing an PduPort, on your EcuInstance. It does not have any PduPort in your CFG. This means it shall not go to Com.)
>
> We have fixed the bug for the forward path. It should now be the correct algorithm. The bugfix will be in RTA-CAR 12.8.0 and onwards.
>
> Until then, we have created a hotfix for RTA-CAR 12.6.0. We can create the Hotfix for any RTA-CAR version that you need it in. The hotfix is attached. Please feel free to try it out once you find some time.

-------

> [!note]+ 2025-05-08 13:15 · Marc Kaiser
> [^RTA_CONF_GEN_Installer_12.6.0_CN_Hotfix_pr.zip]

-------

> [!note]+ 2025-04-28 07:57 · Marc Kaiser
> Hello Sisi TAO,
>
> I will immediatly start working on this and get back to you once I have an update. We should be able to get this to work in ConfGen, as it is a well known UseCase.

-------

> [!note]+ 2025-04-27 11:52 · Sisi TAO
> Attached is the project for you to reproduce the issue. Tool version: RTA-CAR 12.6.0
> [^Config.zip]

-------

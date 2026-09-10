---
jira_key: RH-12551
jira_url: "https://rtahotline.etas.com/jira/browse/RH-12551"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Critical
project: RH
assignee: Ramakant Achari Raviraj
reporter: Sisi TAO
tags: [jira/label/cariad, jira/label/isolar-a]
fix-versions: []
epic: null
parent: null
created: "2025-03-14T04:41:17.000+0100"
updated: "2026-07-27T04:40:43.000+0200"
synced-at: "2026-09-10T08:07:25.599Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Dear hotline colleague,

I’m importing LDF files with RTA-CAR 12.6.0pr1 with LDFImporter. And the imported LinTpConfig is not imported correctly. Attached is the project to reproduce the issue.

1.Reference to Connector is missing for LinTpNode_MasterReq. Could you please confirm is this an issue? Only if I reference the connector correctly, LinTp module can be confgened. Thank you.

![[RH-12551-image001.png]]

 

2. Wrong DcmIPdus and NPdus of Slave responses. 

**Correct behavior is**: DataPdu(NPdu) shall be common for all slave responses, LinTpNSdu (DcmIPdu) shall be different for different slave nodes. 

But the imported system extract is wrong.

Could you check with Lin expert, thank you.

 

![[RH-12551-image-2025-03-14-17-56-42-972.png]]

**Sisi TAO** 

Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

M +86 133 81555197

[Sisi.TAO@bosch.com!mail_small.gif!](mailto:Sisi.TAO@bosch.com) 

ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN

333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

&#91;www.etas.com|www.etas.com&#93;  **

ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2025-07-09 04:59 · Mingye YUAN
> Confirmed from Mr. Fargus Alex, this issue will be solved in CAR 12.8.0.

-------

> [!note]+ 2025-06-03 17:58 · JSM Service Bot
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2025-05-20 12:03 · Mingye YUAN
> Raviraj will solve this issue in 12.8.0:
>
>
>
> ![[RH-12551-image.png]]

-------

> [!note]+ 2025-04-30 12:36 · Ramakant Achari Raviraj
> Hello Sisi TAO,
>
> These improvements are planned for 12.8.0. We will provide you a test version as soon as it is available.
>
> Best regards,
>
> Raviraj

-------

> [!note]+ 2025-04-02 09:15 · Sisi TAO
> Hi Ramakant Achari Raviraj 
>
>
>
> We expect this feature can be implemented in RTA-CAR 12.7. Since Cariad is our strategic customer, in their next platform project (which we are going to win this June-July), they'll have more than hundreds of Lin nodes on the central gateway which need LinTp for programming. Automatic LinTp generation is very critical for them.

-------

> [!note]+ 2025-04-02 09:08 · Ramakant Achari Raviraj
> Hello Mingye YUAN, Sisi TAO,
>
> We have analysed this and learned that connector reference was never supported. In AUTOSAR, it is mentioned that this reference is optional in case of ECUExtract, however I see confgen expects this reference to create parameters in {color:#000000}{color:#000000}LinTpGlobalConfig.{color}{color} I have created ticket to [[ARCTOOLS-8799] LDF Importer shall configure connector and TpConnection references for the completeness - Jira (etas-dev.com)|https://jira.etas-dev.com/browse/ARCTOOLS-8799] to address both points.
>
> In which version of RTA-CAR are you expecting this to be available? What is the criticality? Do you already have a workaround available for this?
>
> Best regards,
>
> Raviraj

-------

> [!note]+ 2025-03-26 06:26 · Mingye YUAN
> Hello Mr. Marc and Ramakant:
>
> Is the analysis for importing the Connector parameter done? We are waiting for this implementation to complete our Cariad project cobra part, we need to finish it by March 31st. Otherwise, there could be risk for the process. I'd really appreciate it if you could get it done as soon as you can.
>
> Let me know if there is anything that is holding you up or if you need any further information.
>
> Thanks a lot!

-------

> [!note]+ 2025-03-19 08:47 · Marc Kaiser
> Hello Sisi TAO,
>
> I had a call with Ramakant Achari Raviraj. We found that the Connector is currently not set by LDF importer, as you say. The feature currently is not implemented, so there is nothing you can change in the LDF to make it import that parameter. We have to analyse why we do not set this parameter. Ramakant Achari Raviraj  will get back to us once analysis is complete.
>
> For the second point, it is simular. We confirm your observation is the current implemented behaviour.
>
> It looks like we must improve LDF importer on both points.

-------

> [!note]+ 2025-03-14 10:54 · Sisi TAO
> [^lintpConfGen.zip]

-------

---
jira_key: RH-15741
jira_url: "https://rtahotline.etas.com/jira/browse/RH-15741"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: High
project: RH
assignee: "[[Junsheng_ZHANG|Junsheng ZHANG]]"
reporter: "[[Junsheng_ZHANG|Junsheng ZHANG]]"
tags: [jira/comp/rta-car, jira/comp/rta-rte, jira/label/vncnms]
fix-versions: []
epic: null
parent: null
created: "2026-04-12T12:56:44.000+0200"
updated: "2026-04-20T13:08:48.000+0200"
synced-at: "2026-09-11T01:36:25.139Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Hi hotline，

I am currently working on a version upgrade, but I have reported an issue with the BSW generation as shown in the image below, which is preventing me from continuing. Can you help me resolve this;

![[RH-15741-image001.png]]

Version: RTA-CAR_12.11.0VCTCESR1pr2(I have no problem generating the RTA-CAR_12.11.0VCTCESR1pr1 project);

RteInternalLockingBehavior is a new feature, and I am not sure how to configure it

 **Junsheng ZHANG** 

Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

M +86 155 32928056 

[Junsheng.ZHANG@bosch.com!mail_small.gif!](mailto:Junsheng.ZHANG@bosch.com) 

ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

[www.etas.cn](https://www.etas.cn/)  **

ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2026-04-17 16:30 · [[Liam_Wellacott|Liam Wellacott]]
> This type of error is seen with the new architecture when output folders are modified. Have any files inside the src/bsw been manually moved/updated? If not, please clean the output folder and run again.
>
> I am unavailable for the next two weeks, subsequent issues should be forwarded to the tools team colleagues who will be best placed to help.

-------

> [!note]+ 2026-04-16 16:51 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> I have update the version by add plugin;[https://artifactory.etas-dev.com/artifactory/rtabsw-generic-main-local/Release/12.11.0.VCTCESR1pr3/…](https://artifactory.etas-dev.com/artifactory/rtabsw-generic-main-local/Release/12.11.0.VCTCESR1pr3/RC/Delivery/RTA-CAR-12.11.0.VCTCESR1pr3.zip)；
>
> There will still be errors with the rip, but the content looks different
>
> ![[RH-15741-image-2026-04-16-22-51-00-201.png]]
> - BctStart :: Success
>
> - Platform_Prepare :: Success
>
> - Rte_Rips_Generate :: Error
>
> Action-Id='Rte_Rips_Generate': Exception during execution of JavaAction.
>
> Exception during execution of JavaAction.
>
> com.bosch.dgs.bfw.extension.ActionExecutionException: org.eclipse.core.runtime.CoreException: Creation of Metadata canceled. Creation of Metadata canceled. Failed to create the Metadata Metadata: CEA2_0_LDCU_converted:Project
>
> File +src\bsw\Rte_Rips\Rte_Rips_Cfg.h+ couldn't be registered. This is probably a build configuration problem (e.g. from BAMF files). Please check if this file is created/registered multiple times during the build.
>
> com.bosch.dgs.bfw.roleprovider.exceptions.RoleProviderRuntimeException: org.eclipse.core.runtime.CoreException: Creation of Metadata canceled. Creation of Metadata canceled. Failed to create the Metadata Metadata: CEA2_0_LDCU_converted:Project
>
> File +src\bsw\Rte_Rips\Rte_Rips_Cfg.h+ couldn't be registered. This is probably a build configuration problem (e.g. from BAMF files). Please check if this file is created/registered multiple times during the build.
>
> An issue occurred in the tool during code generation, please contact the tools team for support.
>
> Complete stack trace can be found in the error log (+C:/ETAS/RTA-CAR_12.11.0VCTCESR1pr2/RTA-CAR/workspace\.metadata\.log+).

-------

> [!note]+ 2026-04-16 16:48 · [[Jacob_Allen|Jacob Allen]]
> [[Lan_Tran|Lan Tran]] this may be relevant for you to know.
>
> VCTCESR1pr2 looks to have non-matching BSW and BSW.OLDARCH which will lead to confusing customer behaviour. For all 12.10.0-based versions of RTA-CAR (and any based on the current 12.11.0 master branch) we will need ensure **2** different BSW artifacts are built with the same content and include both in the package delivered to the customer.
>
> We should also be pushing customers to move to the new project architecture to avoid issues like this one.

-------

> [!note]+ 2026-04-16 16:30 · [[Liam_Wellacott|Liam Wellacott]]
> The project is using the old architecture, I do not think that this will use project based accessors, hence the workaround did not work. It also seems that this version of CAR has BSW versions from different branches so that might be a source of confusion.
>
> The root cause is the wrong paramdef is being used, we are deploying it from the RTE executable, it should come from the RteLibs package. This should be fixed in the integration repository (this also fixes an architectural misalignment).
>
> Finally, I think we could unblock the customer by instead using the "patch" feature to replace the accessor. I believe the FAE team are familiar with this and can help colleagues to do this if appropriate. (I haven't read the full ticket context).

-------

> [!note]+ 2026-04-16 16:25 · [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]]
> Hi [[Liam_Wellacott|Liam Wellacott]], can you please update ticket based on discussion during meeting.

-------

> [!note]+ 2026-04-16 06:08 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hello [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]] ,
>
> As discussed, please update your analysis on this ticket. Additionally, if you have a workaround for this case, please share it with the customer, as this error is currently blocking their progress on this version of RTA-CAR.

-------

> [!note]+ 2026-04-14 05:53 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hi [[Junsheng_ZHANG|Junsheng ZHANG]] ,
>
> The workaround for this issue involves generating a new accessor. Please follow the steps below:
>  * Ensure your project uses "{*}Rte_EcuParamDef.arxml{*}" version AR24-11 ({*}AUTOSAR_00053{*}).
>  * "Enable Java Action" in your project settings.
>
> ![[RH-15741-image-2026-04-14-10-36-44-526.png]]  
>  * "Execute Java actions" and wait until the process is finished.
>
>   ![[RH-15741-image-2026-04-14-10-38-29-295.png]]
>
> ==> After the process finishes, check your new **'Rte.java'** accessor file; it should now include all new attributes.
>
> -------------------------------------------------------------------------------------------------------------------------------
>
> After discussing with the RTA team, we found that the workaround doesn't work because a new plugin needs to be regenerated.

-------

> [!note]+ 2026-04-13 15:36 · [[JSM_Service_Bot|JSM Service Bot]]
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

> [!note]+ 2026-04-13 15:36 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]], this RTA-RTE ticket requires an assignee. As the component lead for RTA-RTE, please ensure the 'Level 3 Assignee' field is set the appropriate person that an handle this issue.

-------

> [!note]+ 2026-04-13 15:35 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hello [[Junsheng_ZHANG|Junsheng ZHANG]] ,
>
> Thank you for your finding, I and [[Phong_Thai_Thanh|Phong Thai Thanh]] have investigated the issue and confirmed that while the release note of **RTA-CAR_12.11.0VCTCESR1pr2** supports RTE version {*}AR24-11 (AUTOSAR_00053){*}, this specific pre-release version still utilizes **"Rte_EcuParamDef.arxml"** from version {*}AR22-11 (AUTOSAR_00051){*}.
>
> {color:#de350b}==> Because your project uses the **AR24-11** parameter definition file which introduces several new attributes, a **"ClassNotFoundException"** occurs during processing.{color}
>
> ------------
>
> Hello [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]] , Could you please verify this point on your side ?

-------

> [!note]+ 2026-04-12 13:01 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> [^Isolar.zip]

-------

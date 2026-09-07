---
jira_key: RH-17023
jira_url: "https://rtahotline.etas.com/jira/browse/RH-17023"
server: rtahotline
kind: hotline
type: Support
status: Waiting for Level 3
priority: Critical
project: RH
assignee: annamalai.rajasekar@in.bosch.com
reporter: sisi.tao@bosch.com
tags: [ISOLAR-AB]
components: [Generic-Importers, ISOLAR-A/B]
fix-versions: []
epic: null
parent: null
created: "2026-08-25T11:22:50.000+0200"
updated: "2026-09-07T08:55:22.000+0200"
synced-at: "2026-09-07T07:10:44.613Z"
jira-orphaned: false
---

# RH-17023 [VCTC] RTA-CAR 12.11 Migration RTA-CAR Toolchain Issues

> [!jira] Waiting for Level 3 · Critical · [[Annamalai_Rajasekar|Annamalai Rajasekar]] · 更新于 2026-09-07T08:55:22.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-17023)

> 标签：#jira/comp/generic-importers #jira/comp/isolar-a/b #jira/label/isolar-ab

## 描述

Hi [@Karthi Krishna Shekaar (MS/EMT-ETAS)!mail_small.gif!](mailto:Karthi.Krishna@etas.com)

When we are migrating VCTC (Cariad) projects from RTA-CAR 12.11.0VCTCESR1pr1 to RTA-CAR 12.11.0, we had following issues:

1. Com Error -> Clear output files and reopen workspace can solve this issue

![[RH-17023-image001.png]]

2. LDF Import by CLI. If LDF is upper case (xxxx.LDF), report error:

- 
  ```
  C:\ETAS\RTA-CAR_12.11.0\ISOLAR-AB_12.11.0\ISOLAR-A.cmd -importldf --project="C:\Project\TZCU\TZCU\Tool\Isolar\temp" --output="LIN_SysDesc.arxml" --otheropt="C:\Project\TZCU\TZCU\Tool\Isolar\SysDesc/LDF\LDF_CLI_Input.txt" --ldffile="C:\Project\TZCU\TZCU\Tool\Isolar\SysDesc\LDF\LLIN1_rev.LDF" The "ISOLAR-A.cmd" command file is deprecated. Please use "ISOLAR-AB.cmd" as the alternate command file to execute '-importldf'. To view the list of available commands, kindly execute "ISOLAR-AB.cmd -h".SLF4J: Failed to load class "org.slf4j.impl.StaticLoggerBinder".SLF4J: Defaulting to no-operation (NOP) logger implementationSLF4J: See http://www.slf4j.org/codes.html#StaticLoggerBinder for further details.###############################################################################Copyright (c) ETAS GmbH 2026. All rights reserved.###############################################################################[-importldf, --project=C:\Project\TZCU\TZCU\Tool\Isolar\temp, --output=LIN_SysDesc.arxml, --otheropt=C:\Project\TZCU\TZCU\Tool\Isolar\SysDesc/LDF\LDF_CLI_Input.txt, --ldffile=C:\Project\TZCU\TZCU\Tool\Isolar\SysDesc\LDF\LLIN1_rev.LDF]======================================================================================================================================= ISOLAR-A Commandline LDF Import feature=======================================================================================================================================[CMD_LDF_IMPORT_INFO] Execution type: Legacy CLI[CMD_LDF_IMPORT_WARNING] The legacy commandline type is deprecated. Please use the alternate meta command to execute 'LDF Import'. Please type '<tool_name> -import -ldf -h' in the command prompt to know more details about alternate meta command.[CMD_LDF_IMPORT_INFO] Pre-validation successful. Execution of commandline LDF Import started...[CMD_LDF_IMPORT_INFO] Commandline arguments passed: [-importldf, --project=C:\Project\TZCU\TZCU\Tool\Isolar\temp, --output=LIN_SysDesc.arxml, --otheropt=C:\Project\TZCU\TZCU\Tool\Isolar\SysDesc/LDF\LDF_CLI_Input.txt, --ldffile=C:\Project\TZCU\TZCU\Tool\Isolar\SysDesc\LDF\LLIN1_rev.LDF][CMD_LDF_IMPORT_INFO] Processing the project related arguments...[CMD_LDF_IMPORT_INFO] Processing the project related arguments successful![CMD_LDF_IMPORT_INFO] Validating project related commandline arguments...[CMD_LDF_IMPORT_INFO] Validation of project related commandline arguments successful![CMD_LDF_IMPORT_INFO] AUTOSAR Project loading is in progress...[CMD_LDF_IMPORT_INFO] Autosar project loading successful![CMD_LDF_IMPORT_INFO] Time taken to load the project: 0 seconds[CMD_LDF_IMPORT_INFO] Project name: temp[CMD_LDF_IMPORT_INFO] Project location: C:\Project\TZCU\TZCU\Tool\Isolar\temp[CMD_LDF_IMPORT_INFO] Autosar project version: AR 24-11 (AUTOSAR 00053)[CMD_LDF_IMPORT_INFO] Command line option "-log/-l" not provided. Hence, the default log file path is considered[CMD_LDF_IMPORT_INFO] Default log file path: C:\Project\TZCU\TZCU\Tool\Isolar\temp_log\importldf.log[CMD_LDF_IMPORT_INFO] Configuring log file...[CMD_LDF_IMPORT_INFO] Log file path: C:\Project\TZCU\TZCU\Tool\Isolar\temp_log\importldf.log[CMD_LDF_IMPORT_INFO] Master log file path: C:\Project\TZCU\TZCU\Tool\Isolar\temp_log\master.log[CMD_LDF_IMPORT_ERROR] No LDF files found in the provided input folder: C:\Project\TZCU\TZCU\Tool\Isolar\SysDesc\LDF\LLIN1_rev.LDF[CMD_LDF_IMPORT_INFO] LDF Import is aborted. Check above errors for more details.[CMD_LDF_IMPORT_INFO] It took "9" seconds to complete the execution[CMD_LDF_IMPORT_INFO] Execution of command line feature LDF Import is failed! Please read the above error messages to know the reason for the failure[CMD_LDF_IMPORT_INFO] Exit code of the execution: 1====================================================== END OF REPORT =================================================================Generated on 2026/08/20 14:16:39Result of the application : 1###############################################################################Summary for -importldf commandExecuted on 2026/08/20 14:16:39RTA-CAR 12.11.0###############################################################################Status ERROR: org.eclipse.sphinx.emf code=0 IllegalStateException occurred when invoking code from plug-in "org.eclipse.sphinx.emf": Workspace is already closed or not ready yet. Consider tracking the org.eclipse.core.resources.IWorkspace service (using your favorite technique, e.g. Declarative Services, ServiceTracker, Blueprint, ...) instead of calling the static method here to prevent such issues!. java.lang.IllegalStateException: Workspace is already closed or not ready yet. Consider tracking the org.eclipse.core.resources.IWorkspace service (using your favorite technique, e.g. Declarative Services, ServiceTracker, Blueprint, ...) instead of calling the static method here to prevent such issues! children=[Status ERROR: org.eclipse.sphinx.emf code=0 Workspace is already closed or not ready yet. Consider tracking the org.eclipse.core.resources.IWorkspace service (using your favorite technique, e.g. Declarative Services, ServiceTracker, Blueprint, ...) instead of calling the static method here to prevent such issues! java.lang.IllegalStateException: Workspace is already closed or not ready yet. Consider tracking the org.eclipse.core.resources.IWorkspace service (using your favorite technique, e.g. Declarative Services, ServiceTracker, Blueprint, ...) instead of calling the static method here to prevent such issues!]java.lang.IllegalStateException: Workspace is already closed or not ready yet. Consider tracking the org.eclipse.core.resources.IWorkspace service (using your favorite technique, e.g. Declarative Services, ServiceTracker, Blueprint, ...) instead of calling the static method here to prevent such issues! at org.eclipse.core.resources.ResourcesPlugin.getWorkspace(ResourcesPlugin.java:518) at org.eclipse.sphinx.emf.internal.ecore.proxymanagement.blacklist.MapModelIndex.startListening(MapModelIndex.java:60) at org.eclipse.sphinx.emf.internal.ecore.proxymanagement.blacklist.MapModelIndex.<init>(MapModelIndex.java:54) at org.eclipse.sphinx.emf.internal.ecore.proxymanagement.blacklist.ModelIndex.<init>(ModelIndex.java:44) at org.eclipse.sphinx.emf.internal.ecore.proxymanagement.ProxyHelperAdapter.<init>(ProxyHelperAdapter.java:42) at org.eclipse.sphinx.emf.internal.ecore.proxymanagement.ProxyHelperAdapterFactory.createAdapter(ProxyHelperAdapterFactory.java:95) at org.eclipse.emf.common.notify.impl.AdapterFactoryImpl.createAdapter(AdapterFactoryImpl.java:127) at org.eclipse.emf.common.notify.impl.AdapterFactoryImpl.adaptNew(AdapterFactoryImpl.java:101) at org.eclipse.emf.common.notify.impl.AdapterFactoryImpl.adapt(AdapterFactoryImpl.java:87) at org.eclipse.sphinx.emf.internal.ecore.proxymanagement.ProxyHelperAdapterFactory.adapt(ProxyHelperAdapterFactory.java:84) at org.eclipse.sphinx.emf.resource.ExtendedResourceSetImpl.createProxyHelper(ExtendedResourceSetImpl.java:204) at org.eclipse.sphinx.emf.resource.ExtendedResourceSetImpl.<init>(ExtendedResourceSetImpl.java:196) at org.eclipse.sphinx.emf.resource.ScopingResourceSetImpl.<init>(ScopingResourceSetImpl.java:63) at org.artop.aal.common.resource.impl.AutosarResourceSetImpl.<init>(AutosarResourceSetImpl.java:57) at com.bosch.bfw.bamf.loader.ExternalFileBAMFLoader$2.<init>(ExternalFileBAMFLoader.java:159) at com.bosch.bfw.bamf.loader.ExternalFileBAMFLoader.processResourceToManifest(ExternalFileBAMFLoader.java:159) at com.bosch.bfw.bamf.loader.ExternalFileBAMFLoader.processARXML(ExternalFileBAMFLoader.java:148) at com.bosch.bfw.bamf.loader.ExternalFileBAMFLoader.processExternalFile(ExternalFileBAMFLoader.java:211) at com.bosch.bfw.bamf.configurator.util.ModuleDependencyProviderService.lambda$14(ModuleDependencyProviderService.java:374) at java.base/java.util.ArrayList$ArrayListSpliterator.forEachRemaining(ArrayList.java:1708) at java.base/java.util.stream.ReferencePipeline$Head.forEach(ReferencePipeline.java:762) at com.bosch.bfw.bamf.configurator.util.ModuleDependencyProviderService.collectFilesFromLocator(ModuleDependencyProviderService.java:372) at com.bosch.bfw.bamf.configurator.util.ModuleDependencyProviderService.lambda$11(ModuleDependencyProviderService.java:339) at java.base/java.lang.Iterable.forEach(Iterable.java:75) at com.bosch.bfw.bamf.configurator.util.ModuleDependencyProviderService.lambda$10(ModuleDependencyProviderService.java:337) at java.base/java.lang.Iterable.forEach(Iterable.java:75) at com.bosch.bfw.bamf.configurator.util.ModuleDependencyProviderService.collectProductBamfActions(ModuleDependencyProviderService.java:337) at com.bosch.bfw.bamf.configurator.util.ModuleDependencyProviderService.getBundleActions(ModuleDependencyProviderService.java:310) at com.bosch.bfw.bamf.configurator.util.ModuleDependencyProviderService.dependencyInit(ModuleDependencyProviderService.java:143) at com.bosch.bfw.bamf.configurator.bamfloading.ProductModuleDependencyProvider.init(ProductModuleDependencyProvider.java:44) at com.etas.wbp.module.service.job.internal.ProductDependencyCalculationRunnable.run(ProductDependencyCalculationRunnable.java:28) at com.etas.wbp.module.service.job.internal.ProductDependencyProviderJob.consumeItem(ProductDependencyProviderJob.java:44) at com.etas.wbp.module.service.job.internal.ProductDependencyProviderJob.consumeItem(ProductDependencyProviderJob.java:1) at com.bosch.blueworx.core.util.jobs.ItemProcessor.run(ItemProcessor.java:55) at com.bosch.blueworx.core.util.jobs.ConsumerWorkspaceJob.runInWorkspace(ConsumerWorkspaceJob.java:76) at org.eclipse.core.internal.resources.InternalWorkspaceJob.run(InternalWorkspaceJob.java:43) at org.eclipse.core.internal.jobs.Worker.run(Worker.java:63)Status ERROR: com.bosch.bfw.bamf.configurator code=0 Cannot load dependencies of file ResourceDescriptor [url=bundleentry://1136.fwk541488026/DoIP/scripts/DoIP_bamf.arxml, fileName=DoIP_bamf.arxml, lastModifiedTimestamp=1787206571453, resourceExists=true] Cause :java.lang.IllegalStateException: Workspace is already closed or not ready yet. Consider tracking the org.eclipse.core.resources.IWorkspace service (using your favorite technique, e.g. Declarative Services, ServiceTracker, Blueprint, ...) instead of calling the static method here to prevent such issues! java.lang.IllegalStateException: Workspace is already closed or not ready yet. Consider tracking the org.eclipse.core.resources.IWorkspace service (using your favorite technique, e.g. Declarative Services, ServiceTracker, Blueprint, ...) instead of calling the static method here to prevent such issues!java.lang.IllegalStateException: Workspace is already closed or not ready yet. Consider tracking the org.eclipse.core.resources.IWorkspace service (using your favorite technique, e.g. Declarative Services, ServiceTracker, Blueprint, ...) instead of calling the static method here to prevent such issues! at org.eclipse.core.resources.ResourcesPlugin.getWorkspace(ResourcesPlugin.java:518) at org.eclipse.emf.workspace.util.WorkspaceSynchronizer.getFile(WorkspaceSynchronizer.java:341) at org.eclipse.emf.workspace.util.WorkspaceSynchronizer.getFile(WorkspaceSynchronizer.java:350) at org.eclipse.emf.workspace.util.WorkspaceSynchronizer.getFile(WorkspaceSynchronizer.java:268) at org.eclipse.sphinx.emf.util.EcorePlatformUtil.getFile(EcorePlatformUtil.java:918) at org.eclipse.sphinx.emf.metamodel.MetaModelDescriptorRegistry.getDescriptor(MetaModelDescriptorRegistry.java:626) at org.artop.aal.converters.adapters.AbstractConverterAdapter.isLoadConverterFor(AbstractConverterAdapter.java:104) at org.artop.aal.autosar40.converters.adapters.AbstractConverter40Adapter.isLoadConverterFor(AbstractConverter40Adapter.java:60) at org.eclipse.sphinx.emf.resource.ModelConverterRegistry.getLoadConverter(ModelConverterRegistry.java:136) at org.eclipse.sphinx.emf.resource.ExtendedXMLLoadImpl.load(ExtendedXMLLoadImpl.java:101) at org.artop.aal.common.resource.impl.AutosarXMLResourceImpl.doLoad(AutosarXMLResourceImpl.java:369) at org.eclipse.emf.ecore.resource.impl.ResourceImpl.load(ResourceImpl.java:1563) at com.bosch.bfw.bamf.loader.ExternalFileBAMFLoader.processResourceToManifest(ExternalFileBAMFLoader.java:175) at com.bosch.bfw.bamf.loader.ExternalFileBAMFLoader.processARXML(ExternalFileBAMFLoader.java:148) at com.bosch.bfw.bamf.loader.ExternalFileBAMFLoader.processExternalFile(ExternalFileBAMFLoader.java:211) at com.bosch.bfw.bamf.configurator.util.ModuleDependencyProviderService.lambda$14(ModuleDependencyProviderService.java:374) at java.base/java.util.ArrayList$ArrayListSpliterator.forEachRemaining(ArrayList.java:1708) at java.base/java.util.stream.ReferencePipeline$Head.forEach(ReferencePipeline.java:762) at com.bosch.bfw.bamf.configurator.util.ModuleDependencyProviderService.collectFilesFromLocator(ModuleDependencyProviderService.java:372) at com.bosch.bfw.bamf.configurator.util.ModuleDependencyProviderService.lambda$11(ModuleDependencyProviderService.java:339) at java.base/java.lang.Iterable.forEach(Iterable.java:75) at com.bosch.bfw.bamf.configurator.util.ModuleDependencyProviderService.lambda$10(ModuleDependencyProviderService.java:337) at java.base/java.lang.Iterable.forEach(Iterable.java:75) at com.bosch.bfw.bamf.configurator.util.ModuleDependencyProviderService.collectProductBamfActions(ModuleDependencyProviderService.java:337) at com.bosch.bfw.bamf.configurator.util.ModuleDependencyProviderService.getBundleActions(ModuleDependencyProviderService.java:310) at com.bosch.bfw.bamf.configurator.util.ModuleDependencyProviderService.dependencyInit(ModuleDependencyProviderService.java:143) at com.bosch.bfw.bamf.configurator.bamfloading.ProductModuleDependencyProvider.init(ProductModuleDependencyProvider.java:44) at com.etas.wbp.module.service.job.internal.ProductDependencyCalculationRunnable.run(ProductDependencyCalculationRunnable.java:28) at com.etas.wbp.module.service.job.internal.ProductDependencyProviderJob.consumeItem(ProductDependencyProviderJob.java:44) at com.etas.wbp.module.service.job.internal.ProductDependencyProviderJob.consumeItem(ProductDependencyProviderJob.java:1) at com.bosch.blueworx.core.util.jobs.ItemProcessor.run(ItemProcessor.java:55) at com.bosch.blueworx.core.util.jobs.ConsumerWorkspaceJob.runInWorkspace(ConsumerWorkspaceJob.java:76) at org.eclipse.core.internal.resources.InternalWorkspaceJob.run(InternalWorkspaceJob.java:43) at org.eclipse.core.internal.jobs.Worker.run(Worker.java:63)
  ```
  

3. Code Gen Error -> Clear output files and reopen workspace can solve this issue

![[RH-17023-image002.png]]

4. Code Gen Error -> Clear output files and reopen workspace can solve this issue

Exception during execution of JavaAction.

 

```

com.bosch.dgs.bfw.extension.ActionExecutionException: Resource(s) could not be found
src\bsw\rba_MemLib\rba_MemLib_Check2.c
_log\rba_MemLib\rba_MemLib_Report.txt
src\bsw\rba_MemLib\rba_MemLib_Cfg.h
src\bsw\rba_MemLib\rba_MemLib_UseRte.h
```

 

Registration at BFW would fail!

5. RTE code gen Error parsing input file

[https://rtahotline.etas.com/jira/browse/RH-16347](https://rtahotline.etas.com/jira/browse/RH-16347)

6. ConfGen failed without any problems. Screenshot not available. Info like: Internal Error:Sd. Reopen RTA-CAR can fix this issue.

7.Sometimes when we open the project, it intermittently reports **BSW invalid**. The sequence is:

1. Switch the BSW from version **12.11** to **12.11 PR4/PR5**.
2. Open using a new workspace, and we still get **BSW invalid**.
3. Switch back from **12.11 PR4/PR5** to **12.11**, and the issue is resolved.

8.Sometimes the first generation fails with a BFX generator error. Switching to a different workspace and generating again resolves the issue.

**Sisi TAO** 

Cross Functional Regional Solution Field Management - Regional Solution Field Manager China

M +86 133 81555197 

[Sisi.TAO@bosch.com!mail_small.gif!](mailto:Sisi.TAO@bosch.com)

ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

[www.etas.cn](https://www.etas.cn/)

**ETAS – Empowering Tomorrow’s Automotive Software**

## 关联

- mentions: [[RH-17070 RTA CAR file parsing error]]
- mentions: [[RH-16347 RTE code gen Error parsing input file ]]

## 评论

> [!note]+ 2026-09-07 08:55 · [[Jie_LIU|Jie LIU]]
> [[M_S_Karthik|M S Karthik]] , thanks for the feedback. 
>
> Yes, it is required in CW38 to have one version for our ETAS internal testing.
>
> And in CW39, we need one version to deliver to customer as VCTC PR7 release with other bugfix as a whole.
>
> cc. [[Phuong_Nguyen_Le|Phuong Nguyen Le]]  [[Lan_Tran|Lan Tran]] 

-------

> [!note]+ 2026-09-04 13:24 · [[M_S_Karthik|M S Karthik]]
> [[Jie_LIU|Jie LIU]], Thanks for asking.
>
> This delivery from ISOLAR-A/B would be a standalone installation package which user must perform installation on top of RTA-CAR to patch it. No integration with VCTC RTA-BSW plugin necessary. Do you still see a need for it to be delivered by CW 38? If this is required in CW 38 only for our ETAS internal testing, we could provide an unofficial delivery package ({_}not QG'ed one{_}) for the same.
>
> Looking forward for your feedback on the same. Thanks. 
>
> [[Shekaar_Karthi_Krishna|Shekaar Karthi Krishna]] - FYI

-------

> [!note]+ 2026-09-04 10:31 · [[Jie_LIU|Jie LIU]]
> Hello, [[Shekaar_Karthi_Krishna|Shekaar Karthi Krishna]], is it possible to provide a patch delivery by CW 38, so that we can integrate it into VCTC PR7 plugin by CW 39?

-------

> [!note]+ 2026-09-03 14:32 · [[Duy_Pham|Duy Pham]]
> Hi all, ticket https://jira.etas-dev.com/browse/ARCCFGEN-2714 create to analysis for Confgen issue #6

-------

> [!note]+ 2026-09-03 11:04 · [[Shekaar_Karthi_Krishna|Shekaar Karthi Krishna]]
> Hello [[Jie_LIU|Jie LIU]],
>
> Team is working on the fix and plan is to provide a patch delivery by CW 39 and then we will plan for an official bug fix release later.

-------

> [!note]+ 2026-09-02 10:58 · [[Jie_LIU|Jie LIU]]
> Hello, [[Shekaar_Karthi_Krishna|Shekaar Karthi Krishna]] 
>
> Do we have the timing plan for back porting to V12.11? We needs to share it also with customer

-------

> [!note]+ 2026-09-01 06:54 · [[Shekaar_Karthi_Krishna|Shekaar Karthi Krishna]]
> **#2** 
>  * .LDF(in uppercase) is not getting imported, this is a issue in CLI 
>  * Workaround:
>  ** Rename extension as .ldf (lower case) or
>  ** Use ldf import in GUI
>  * Solution: This will be fixed as part of [ARCTOOLS-23474](https://jira.etas-dev.com/browse/ARCTOOLS-23474) in V12.12 and same would be back ported to V12.11
>
> **#5** - handled via [https://rtahotline.etas.com/jira/browse/RH-16347] 
>
> **#6:  [[K_Raj_Kumar|K Raj Kumar]]** This is confgen related issue, can you please check and create necessary ticket to take forward

-------

> [!note]+ 2026-08-31 18:03 · [[M_S_Karthik|M S Karthik]]
> Please find the latest status on above reports: 
>  * **#1**
>  ** ISOLAR team is able to reproduce the issue, however, root cause is not yet identified and Its challenging. Analysis is in progress
>  ** Workaround of clearing the output files and reopen workspace works in our environment too. Suspecting script implementation contains random behavior during Incremental build case. investigation in progress...
>  ** [ARCTOOLS-23630](https://jira.etas-dev.com/browse/ARCTOOLS-23630) created to resolve this issue
>  * **#3. & #4**
>  ** "\.buildframework" folder is not delivered to SCM (like GIT).
>  ** {*}General Instruction{*}: When user store the generated output in SCM, then it is mandatory to deliver also the "\.buildframework" folder into SCM in order to automatically clean the generated artifact during previous run or to detect the configuration changes and automatically regenerate the output to keep artifacts in sync. 
>  * **#7**
>  ** This is caused by the way how RTA-BSW VCTC ESR update site package is prepared. Looks like it is prepared as release package but not as custom package due to tool randomly detecting it as its own standalone RTA-BSW and internal validation in RTA Code Generator window throws false positive errors. 
>  ** This is the tooling issue and will be fixed as part of [ARCTOOLS-23627](https://jira.etas-dev.com/browse/ARCTOOLS-23627)
>  * **#2** - we will feedback in our next post.
>  * **#5** - handled via separate ticket
>  * **#6** - Not an issue with ISOLAR. Separate ticket must be created for Conf Gen. 

-------

> [!note]+ 2026-08-31 07:25 · [[Jie_LIU|Jie LIU]]
> Issue screenshot from customer as issue7 in discription:
>
> ![[RH-17023-image-2026-08-31-13-24-06-709.png]]

-------

> [!note]+ 2026-08-30 08:29 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> The file not recognized issue also affects the customer’s use of Git for synchronized development. After downloading the code from Git, it may fail to recognize the ARXML files in the bswmd and swcd folders, causing the RTE code generation to lack links for ports related to BSW modules. RTE code can still be generated without errors, but the actual functionality is missing.You can ref https://rtahotline.etas.com/jira/projects/RH/queues/custom/470/RH-17070；

-------

> [!note]+ 2026-08-27 12:03 · [[Jie_LIU|Jie LIU]]
> Patch used basing on RTA-CAR 12.11.0 official release
> [^RTA-CAR_12.11.0.VCTCESR1pr5_UpdateSite-SNAPSHOT.zip] [^RTA-CAR_CORE_BUNDLES_UpdateSite-12.11.0.VCTCESR1pr4-SNAPSHOT.zip]

-------

> [!note]+ 2026-08-27 11:51 · [[Jie_LIU|Jie LIU]]
> Do not know whether install plugin patch will intake this issue.

-------

> [!note]+ 2026-08-27 11:48 · [[Jie_LIU|Jie LIU]]
> It could happen when changing folder structure of ecucvalues or paramdefs, adding new modules, ECUC extract, etc.

-------

> [!note]+ 2026-08-27 07:10 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Sisi TAO. Your issue is set to "Critical" priority.
> Please ensure that there is a reasonable justification for this listed in the issue description, otherwise the priority may be reviewed and adjusted during triage.
> Kind regards

-------

> [!note]+ 2026-08-27 04:52 · [[Jie_LIU|Jie LIU]]
> Issue Reported from customer side as well:
>
>
>
> ![[RH-17023-image-2026-08-27-10-53-27-726.png]]
> ![[RH-17023-image-2026-08-27-10-53-27-726.png]]

-------

> [!note]+ 2026-08-27 04:51 · [[Jie_LIU|Jie LIU]]
> The work around is to delete all these things:
>
> ![[RH-17023-image-2026-08-27-10-52-24-135.png]]

-------

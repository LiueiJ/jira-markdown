---
jira_key: RH-16347
jira_url: "https://rtahotline.etas.com/jira/browse/RH-16347"
server: rtahotline
kind: hotline
type: Support
status: Waiting for Level 3
priority: Critical
project: RH
assignee: karthi.krishna@etas.com
reporter: dong.liu5@etas.com
tags: []
components: [RTA-CAR]
fix-versions: []
epic: null
parent: null
created: "2026-06-12T11:19:50.000+0200"
updated: "2026-09-10T04:23:34.000+0200"
synced-at: "2026-09-10T03:06:42.188Z"
jira-orphaned: false
profile: Cariad
---

# RH-16347 RTE code gen Error parsing input file

> [!jira] Waiting for Level 3 · Critical · [[Karthi_Krishna_Shekaar_(MSEMT-ETAS)|Shekaar Karthi Krishna]] · 更新于 2026-09-10T04:23:34.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-16347)

> 标签：#jira/comp/rta-car

## 描述

Hi,  

 I am currently encountering some  **"Error parsing input file"** errors during the RTE generation process. Could you please help me investigate the issue? The RTA-CAR version I am using is  **RTA-CAR 12.11.0pr3**. 

Problem Description: 

During the current RTE generation process, an "Error parsing input file" error occurs, as shown in the figure: 

 ![[RH-16347-image001.png]] 

![[RH-16347-image002.png]] 

 I have attached the project files. Thank you! 

Best regards,

 

  **Dong LIU** 

 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China (ETAS-ECM/XSF-CN)

 Bosch (China) Investment Ltd. | 333 Fuquan (N.) Road | Shanghai 200335 |  P.R. CHINA 

 [Dong.LIU5@etas.com!mail_small.gif!](mailto:Dong.LIU5@etas.com)

## 关联

- relates to: [[RH-16514 ConfGen 12.11.0 elements order for EcuC leads to RTE failure]]
- split from: [[RH-17023 [VCTC] RTA-CAR 12.11 Migration RTA-CAR Toolchain Issues]]
- mentions: [[RH-15495 [BMSGen2] RTE generation failed with message "Error parsing input file"]]
- is mentioned in: [[RH-16514 ConfGen 12.11.0 elements order for EcuC leads to RTE failure]]
- is mentioned in: [[RH-16478 [VNCNMS][VCTC] E2E Signalgroup Issue]]

## 评论

> [!note]+ 2026-09-09 18:06 · [[Karthik_M_S_(MSEMT-ETAS)|M S Karthik]]
> Just to close the conversation in previous comment, ticket "[ARC-17412](https://jira.etas-dev.com/browse/ARC-17412) Resolve impact of RTE-Preprocessor removal: force schema compliance" is linked to this ticket

-------

> [!note]+ 2026-08-24 15:42 · [[Oliver_Taylor|Oliver Taylor]]
> Hi [[Karthi_Krishna_Shekaar_(MSEMT-ETAS)|Shekaar Karthi Krishna]],
>
> We discussed this exact support ticket in a call a couple of weeks ago where we agreed that (from the perspective of a user) this is simply a regression.
> You proposed a solution whereby the 'hidden' features of the preprocessor (some of which are highlighted in this ticket) could be covered by the TOOLS team.
>
> The work items for this proposed solution have not been linked to this ticket, so there's currently no solution for this class of issues that customers are facing.
>
> Please link the work items for the solution you have already proposed.
>
> Kind regards,
> Oliver

-------

> [!note]+ 2026-08-20 13:38 · [[Karthi_Krishna_Shekaar_(MSEMT-ETAS)|Shekaar Karthi Krishna]]
> Hello [[Ryan_Dixon|Ryan Dixon]],
>
> I am not right person to comment on which component has generated invalid arxml files.  [[Oliver_Taylor|Oliver Taylor]] can you please feedback

-------

> [!note]+ 2026-08-20 13:27 · [[Ryan_Dixon|Ryan Dixon]]
> [[Karthi_Krishna_Shekaar_(MSEMT-ETAS)|Shekaar Karthi Krishna]]
> Who / What is responsible for generating non-compliant schema ARXML in the first place?

-------

> [!note]+ 2026-08-20 13:14 · [[Max_Sinclair|Max Sinclair]]
> Hi [[Karthi_Krishna_Shekaar_(MSEMT-ETAS)|Shekaar Karthi Krishna]] ,
>
> Thanks very much for the fast response, I think there has been a bit of a misunderstanding here. 
>
> My understanding here is that there is future work being planned to add some of this functionality to ISOLAR. Because for many of these files they are 10000s if not 100000s of lines long and it not feasible for a user to correct this.
>
> Or have I misunderstood something here?
>
> Many thanks,
> Max

-------

> [!note]+ 2026-08-20 12:58 · [[Karthi_Krishna_Shekaar_(MSEMT-ETAS)|Shekaar Karthi Krishna]]
> Hi [[Max_Sinclair|Max Sinclair]] ,
>
> During RTA-RTE generation through the plugin, performs a preprocessing step where ARXML files are patched and rewritten before being passed to the RTE Generator. One side effect of this, ARTOP rewrites XML tags in the correct AUTOSAR schema order. 
>
> Manual workaround: Perform any configuration changes on any elements in the invalid ARXML file and perform save.
>
> I recommend that we mention this in the knowledge base or other documentation (that would be help Customer supporting teams).

-------

> [!note]+ 2026-08-20 12:28 · [[Max_Sinclair|Max Sinclair]]
> Hi [[Karthi_Krishna_Shekaar_(MSEMT-ETAS)|Shekaar Karthi Krishna]] ,
>
> [[Oliver_Taylor|Oliver Taylor]] mentioned he had a discussion with you about partially replacing some of the old functionality from the pre-processor i.e. ordering of tags.
>
> Would you be able to update this ticket with the work that is planned?
>
> Thanks,
> Max

-------

> [!note]+ 2026-07-13 11:04 · [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]]
> Hi [[Karthik_M_S_(MSEMT-ETAS)|M S Karthik]], Please check above summary from Oliver w.r.t ordering issue we discussed.

-------

> [!note]+ 2026-06-26 13:07 · [[Oliver_Taylor|Oliver Taylor]]
> All we've done here is identify where we used to unknowingly provide value to the customer which they expect to be maintained in the product, we could make something good out of this.
>
> [[TAO_Sisi_(ETAS-ECMXSF-CN)|Sisi TAO]], these files had always been contradicting the spec, the problem had been masked by the pre-processor due to the way it handles arxml it reordered the arxml as a by product of its process. You can see the pre-processed arxml at "C:/Users/<your user name>/AppData/Local/Temp/rta/rte/..."
>
> [[Ryan_Dixon|Ryan Dixon]], I backported this to CAR 12.9.0 to see how it behaves there: [^Conf_12.9.0.zip] 
> Against CAR 12.9.0 (preprocessor then rtegen) there's no arxml parsing errors. The temp dir is like  [^After_preprocessor.zip]. (It does get other errors "E001224 Element 'Dem_Init' has a duplicate name within context.." which are unimportant for this support ticket)
>
> [[Burn_Alexander_(ETAS-ECMXPC-Yok1)|Alexander Burn]] / [[Lay_Nick_(ETAS-ECMXPC-Yok1)|Nick Lay]]. I agree, the RTEGen is technically correct in throwing an error here. It has always only accepted the correct ordering of arxml. The problem is that from the perspective of the customer this is a regression. RTA-CAR's 'Generate RTE' functionality used to have a step where it would sanitise the config and permit this, and it wasn't intentional: it simply took in the config with artop (which does permit this) when doing the preprocessor and created the temp directory which had a cleaned version, which RTEGen was run against.
> I don't think that we should force RTEGen to permit this config, but I do think that RTA-CAR should provide a solution to allow customers to use the projects that we allowed them to generate code with in older versions. If it was a single line of config we wanted them to adjust this kind of measure wouldn't be necessary, but from what I can tell this will be thousands of elements that will need to be inspected, checked against the schema, and corrected manually. I think we can do better than saying "we're *technically* right, so its not out problem".
>
> For this customer with this issue I think one of our FAE's can create a script that will fix their config and get them moving again, but long term I'd like to see a tool in CAR which would permanently resolve this specific issue with the ordering of elements in the way the preprocessor handled it.
> i.e. requirements for the solution would be:
> - Customer can easily identify that their elements are ordered incorrectly (tie into the live validation topic maybe)
> - Customer can choose to run a tool which will only re-order the elements which are incorrectly ordered. This effect would be directly changing their project, not a temporary sanitisation like the preprocessor did.  
> - The tool explains why this is required, helps the customer understand why the config was broken and why its proving an improvement to their config.
> ISOLAR should be tool for writing *good* configs taking inputs from many places, including tools which have deficiencies. I tools that help them have a place in our solution.

-------

> [!note]+ 2026-06-26 12:49 · [[Oliver_Taylor|Oliver Taylor]]
> [^After_preprocessor.zip]

-------

> [!note]+ 2026-06-26 12:47 · [[Oliver_Taylor|Oliver Taylor]]
> [^Conf_12.9.0.zip]

-------

> [!note]+ 2026-06-26 09:48 · [[Ryan_Dixon|Ryan Dixon]]
> I have added a diff file to the file that is generated by the *RTE PreProcessorPlugin* to remove the *ComXf* hackery (this involves modifying the **comxf/SysDesc/DBC_SysDesc.arxml** generated into the TMP directory). Even when re-feeding this into RTA-RTE 12.9.0 I end up with the same issue as in https://rtahotline.etas.com/jira/browse/RH-16347.
>
>
> [^RemoveTranslateComXfStuff.diff]
>
> (https://rtahotline.etas.com/jira/browse/RH-16478?focusedCommentId=698429&page=com.atlassian.jira.plugin.system.issuetabpanels:comment-tabpanel#comment-698429)

-------

> [!note]+ 2026-06-25 08:12 · [[TAO_Sisi_(ETAS-ECMXSF-CN)|Sisi TAO]]
> Hi [[Max_Sinclair|Max Sinclair]] 
>
> DBC_SysDesc.arxml is generated by our hub developed script. Other files are mostly generated by customer script.
>
> Actually we have been running these scripts for several years, but it suddenly conflict with AUTOSAR schema rule. We can edit the scripts so far. But since there are quite a lot local developed customer scripts and they are still keep developing, this rule can cause some inconvenience and need more validation.

-------

> [!note]+ 2026-06-23 19:18 · [[Max_Sinclair|Max Sinclair]]
> Hi [[LIU_Dong_(ETAS-ECMXSF-CN)|Dong LIU]] ,
>
> Issues are stemming from malformed xml in your project (tags in the wrong order). In RTA-CAR 12.11 the rte preprocessor has been removed which previously would reorder these tags for you.
>
> I'm currently patching the files for you and will hopefully have a working project soon.
>
> In the meantime would you be able to find out from the customer how the following files have been generated. What we are looking for, is this from competitors tools or has one of the ETAS tools proceeded these files e.g. dbc importer?
>  * /Conf/SysDesc/DBC_SysDesc.arxml
>  * /Conf/UserConfig/DIAG/Dcm_User.arxml
>  * /Conf/UserConfig/DIAG/Dem_Config.arxml
>  * /Conf/UserConfig/DiagR/PduR_DoLinR_Config.arxml
>  * /Conf/UserConfig/NvM/NvM_UserSwcSer.arxml
>  * /Conf/UserConfig/NvM/Nvm_UserSwc.arxml
>  * /Conf/UserConfig/SOA/swc/CDD_XSF.arxml
>  * /Conf/UserConfig/SOA/swc/CDD_XSF_C2.arxml
>  * /Conf/ecu_config/cobra/EA/CanIf_EA.arxml
>  * /Conf/ecu_config/cobra/EA/Dcm_EA.arxml
>  * /Conf/ecu_config/cobra/EA/Fee_EA.arxml
>
> Many thanks,
> Max

-------

> [!note]+ 2026-06-23 17:38 · [[Max_Sinclair|Max Sinclair]]
> The RTE maybe correct here but it doesn't help an end user. 
>
> This is a clear regression from previous versions of RTA-CAR which has implicitly supported this for all of 12.x up to this version. (I agree getting rid of the rte pre-processer was the right decision).
>
> I think its also worth mentioning one of the files (DBC_SysDesc.arxml) is likely to have come from one of the general importers (not checked this yet), so we still need to be able to handle potentially other ETAS tools making mistakes.
>
> Additionally the error message for this is not clear enough so the user doesn't know what the problem is in the first place.
>
> [[Lay_Nick_(ETAS-ECMXPC-Yok1)|Nick Lay]] 

-------

> [!note]+ 2026-06-22 11:17 · [[Lay_Nick_(ETAS-ECMXPC-Yok1)|Nick Lay]]
> The RTE is likely correct here, the input its being given is not schema conformant. ARXML is only ARXML if it conforms with an AUTOSAR schema.
>
> The fix needs to be in whatever generated that non-conformant "ARXML". If that's part of our tooling, then there's a bug we need to fix. If it's come from the customer directly then (unfortunately) they will need to fix it.
>
> The previous preprocessing masked this problem, it's not correct to reintroduce it.
>
> [[Max_Sinclair|Max Sinclair]]

-------

> [!note]+ 2026-06-17 15:48 · [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]]
> [[Oliver_Taylor|Oliver Taylor]] The behavior is always same from RTE (when executed as standalone) for such configurations (with wrong ordering of elements in arxml) however Preprocessor script used to handle this when executed RTE in RTA CAR (older versions).  As we know the script is removed in recent CAR versions.
>
> Is there some solution at CAR level to handle such configurations? Its not possible for users to fix all these manually.

-------

> [!note]+ 2026-06-16 15:22 · [[Max_Sinclair|Max Sinclair]]
> Hi [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]] ,
>
> Thanks for the info, is this ordering documented anywhere? I had a look through the rte-reference guide and found references to various fields but no ordering (is this an AR spec thing?). This is because the project has multiple of these errors for different fields.
>
> Could you also consider this a defect, the error message doesn't have enough information for the end user to discern that this is the issue.
>
> Thanks again,
> Max

-------

> [!note]+ 2026-06-15 18:53 · [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]]
> Hi [[Max_Sinclair|Max Sinclair]] issue is due to order of the elements, START-POSITION should be before TRANSFER-PROPERTY.
>
> ```
>                 <I-SIGNAL-TO-I-PDU-MAPPING>
>                   <SHORT-NAME>I_BMS_Batt_InWaterTemp</SHORT-NAME>
>                   <I-SIGNAL-REF DEST="I-SIGNAL">/SysDesc/Pkg_ISignal/I_BMS_Batt_InWaterTemp_I_BMS_CellVolt_Temp</I-SIGNAL-REF>
>                   <PACKING-BYTE-ORDER>MOST-SIGNIFICANT-BYTE-FIRST</PACKING-BYTE-ORDER>
>                   <TRANSFER-PROPERTY>TRIGGERED</TRANSFER-PROPERTY>
>                   <START-POSITION>71</START-POSITION>
>                 </I-SIGNAL-TO-I-PDU-MAPPING>
> ```

-------

> [!note]+ 2026-06-15 17:44 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]], this RTA-RTE ticket requires an assignee. As the component lead for RTA-RTE, please ensure that the 'Level 3 Assignee' field is set to the appropriate person that can handle this issue.

-------

> [!note]+ 2026-06-15 17:44 · [[Max_Sinclair|Max Sinclair]]
> Hi [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]],
>
> Could you take a look at this (Conf-3.zip), from what I can see the RTE xml parser seems to be falsely labelling config as incorrect.
>
> For example the first error:
> {quote}<TEXT>Error returned from XML parser: element 'START-POSITION' is not allowed for content model '(SHORT-NAME,SHORT-NAME-FRAGMENTS?,LONG-NAME?,DESC?,CATEGORY?,ADMIN-DATA?,INTRODUCTION?,ANNOTATIONS?,I-SIGNAL-GROUP-REF?,I-SIGNAL-REF?,PACKING-BYTE-ORDER?,START-POSITION?,TRANSFER-PROPERTY?,UPDATE-INDICATION-BIT-POSITION?,VARIATION-POINT?)'.</TEXT>
> {quote}
> So it complaints that START-POSITION isn’t allowed but then has it listed as an optional allowed parameter. The tags look well formed e.g. no orphan tags or special characters , is there an error in the allowed schema?
>
> Many thanks,
> Max

-------

> [!note]+ 2026-06-15 17:17 · [[JSM_Service_Bot|JSM Service Bot]]
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

> [!note]+ 2026-06-12 11:27 · [[LIU_Dong_(ETAS-ECMXSF-CN)|Dong LIU]]
> The project has been uploaded here.

-------

> [!note]+ 2026-06-12 11:27 · [[LIU_Dong_(ETAS-ECMXSF-CN)|Dong LIU]]
> [^Conf-3.zip]

-------

> [!note]+ 2026-06-12 11:23 · [[Joshua_Cantwell|Joshua Cantwell]]
> Perhaps this ticket might help: [https://rtahotline.etas.com/jira/browse/RH-15495]
>
> From there Phong said this:
>
> ![[RH-16347-image-2026-06-12-10-24-00-428.png]]![[RH-16347-image-2026-06-12-10-24-00-428.png]]

-------

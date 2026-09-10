---
jira_key: RH-16863
jira_url: "https://rtahotline.etas.com/jira/browse/RH-16863"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: High
project: RH
assignee: "[[Dong_LIU|Dong LIU]]"
reporter: "[[Dong_LIU|Dong LIU]]"
tags: [jira/label/vncnms]
fix-versions: []
epic: null
parent: null
created: "2026-08-05T20:06:41.000+0200"
updated: "2026-08-12T11:16:44.000+0200"
synced-at: "2026-09-10T03:48:22.681Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Hi, 

The customer has some questions regarding the usage of the  **AliveTimeout configuration parameter**. The RTA-CAR version being used is* 

 ***RTA-CAR 12.11.0VCTCESR1pr1**. Could you please help check this issue? Thank you. 

 **Issue background:**

 The customer has configured the  **AliveTimeout** parameter, as shown in the figure below. However, after the configuration, they found that the  **AliveTimeout** setting has no impact on the generated configuration files and code after running  **ConfGen** and  **CodeGen**. 

![[RH-16863-image002.png]] 

![[RH-16863-image003.png]] 

The customer would like to confirm the purpose of the  **AliveTimeout** parameter and how to make it take effect. 

Best regards,

 

  **Dong LIU** 

 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China (ETAS-ECM/XSF-CN)

 Bosch (China) Investment Ltd. | 333 Fuquan (N.) Road | Shanghai 200335 |  P.R. CHINA 

 [Dong.LIU5@etas.com!mail_small.gif!](mailto:Dong.LIU5@etas.com)

## 关联

- is duplicated by: [[RH-16452 AliveTimeout configuration item]]
- is resolved by: [[RH-14775 [VNCNMS][ANY] Issue relates to generate "ComTimeOutNotification" using conf-gen of RTA-CAR 12.9.0]]

## 评论

> [!note]+ 2026-08-12 10:24 · [[Dong_LIU|Dong LIU]]
> [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]] I have changed it at first.
>
> ![[RH-16863-image-2026-08-12-16-24-29-973.png]]

-------

> [!note]+ 2026-08-12 09:39 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hello [[Dong_LIU|Dong LIU]] ,
>
> As I said, you shall change the DataTypePolicy of **I_IBRS_VehSpd_I_IBRS_SpdInfo** to **NETWORK-REPRESENTATION-FROM-COM-SPEC,** when you use **AliveTimeout** paremeter from the ** **NonQueueReceiverComSpec** of the connected RPort{*}`*`
>
> **![[RH-16863-image-2026-08-12-14-32-20-055.png]]**
>
> ![[RH-16863-image-2026-08-12-15-12-52-708.png]]
>
> [^Isolar_M.zip]
> ![[RH-16863-image-2026-08-12-15-12-52-708.png]]

-------

> [!note]+ 2026-08-11 19:59 · [[Dong_LIU|Dong LIU]]
> [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]] Could you please help test the `I_IBRS_VehSpd` signal and the related RPORT? I tried it myself, but I couldn't get it to work.
>
> ![[RH-16863-image-2026-08-12-01-56-05-354.png]]
>
> ![[RH-16863-image-2026-08-12-01-57-15-501.png]]

-------

> [!note]+ 2026-08-06 14:14 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hi [[Dong_LIU|Dong LIU]] ,
>
> I cannot see your configuration in the capture. However, I update Isignal **I_CDCU_DiagnosticSt_I_CDCU_DiagnosticSt** as the sample data for your project --> It runs normal as expectation
>
> ![[RH-16863-image-2026-08-06-19-06-44-500.png]]
>
> ![[RH-16863-image-2026-08-06-19-09-20-790.png]]
>
>
>
> In general, you have 2 options to generate the ComTimeout for ComSignal:
>  - Using **Timeout parameter** from the corresponding **ISignalPort** when the DataTypePolicy is different from NETWORK-REPRESENTATION-FROM-COM-SPEC. ({*}in your case is LEGACY{*})
>  - Using **AliveTimeout** paremeter from the **NonQueueReceiverComSpec of the connected RPort** only when the DataTypePolicy is {*}NETWORK-REPRESENTATION-FROM-COM-SPEC{*}.
> [^Isolar_Modified.zip]

-------

> [!note]+ 2026-08-06 09:27 · [[Dong_LIU|Dong LIU]]
> [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]] I have change the DataTypePolicy of the ISignal from LEGACY to NETWORK-REPRESENTATION-FROM-COM-SPEC, but it does not work.

-------

> [!note]+ 2026-08-06 05:55 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hi [[JI_Jiaqi_(ETAS-ECMXSF-CN)|Jiaqi JI]] , [[Dong_LIU|Dong LIU]] ,
>
> I believe this ticket is duplicated with RH-16452 😅, and this is not a tool issue. Could you please refer to the guidance in RH-14775 for configuring the **AliveTimeout** parameter?

-------

> [!note]+ 2026-08-06 03:30 · [[JI_Jiaqi_(ETAS-ECMXSF-CN)|Jiaqi JI]]
> Hi [[Phuong_Nguyen_Le|Phuong Nguyen Le]] ,
>
> We raised one new ticket from cariad, could you help assign one engineer from you side to help us investigate it?
>
> Thanks a lot!!!

-------

> [!note]+ 2026-08-06 03:29 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Dong LIU, please note that this issue was made with VNCNMS in the summary and has been sent to the relevant queue by adding the VNCNMS label.

-------

> [!note]+ 2026-08-05 20:32 · [[Dong_LIU|Dong LIU]]
> **The project is attached.**
> [^Isolar.zip]

-------

---
jira_key: RH-13161
jira_url: "https://rtahotline.etas.com/jira/browse/RH-13161"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Low
project: RH
assignee: Yinchuan XU
reporter: Yinchuan XU
tags: []
fix-versions: []
epic: null
parent: null
created: "2025-05-29T08:37:32.000+0200"
updated: "2026-03-05T06:52:04.000+0100"
synced-at: "2026-09-10T08:07:25.599Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Hello Hotline: 

 I meet a rte problem in RTA CAR 12.6.0. 

 As the below picture, we have a Rte_Write*** interface, in this interface, it has a buffer with a length of 13, and this buffer will be used by function  **SomeIpXf_LdCom_LdComIPdu_SOMEIPXf_Veh_BodySts5_Powertrain** 

![[RH-13161-image001.png]] 

 In function SomeIpXf_LdCom_LdComIPdu_SOMEIPXf_Veh_BodySts5_Powertrain, this 13-byte buffer will be transferred in  **buffer**, and as you can see in below picture line 91-94, buffer&#91;7&#93; has been already filled, 

![[RH-13161-image002.png]] 

 What’s more in this function, in line 102, 107, 112, 117, these four lines are also filled buffer from buffer&#91;8&#93; to buffer&#91;21&#93;, (21=8+1+4+4+4), but the input is just a 13-byte buffer, so when cpu execute these code, it will perform memory error.  

![[RH-13161-image003.png]] 

 Above all, not only one interface have this issue, but all Rte_Write interfaces about someipxf are same, so do you know if can we config the length of this buffer, or any other solution to solve this issue. 

 The attachment is my configuration which is extract by rteet.exe 

 Best Regards 

 ** Yinchuan XU** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 [Yinchuan.XU@etas.com!mail_small.gif!](mailto:Yinchuan.XU@etas.com) 

 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 Room 2601, Baoland Plaza, No.83 Pazhou Avenue, Haizhu District, Guangzhou 510308, P.R. China 

 [www.etas.cn](http://www.etas.cn)   ** 

 

 ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2025-07-08 18:00 · JSM Service Bot
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2025-06-23 18:25 · JSM Service Bot
> This issue has not received any response for 2 weeks and will now be automatically moved to Solution Proposed.

-------

> [!note]+ 2025-05-30 10:13 · Marc Kaiser
> Hello Mingye YUAN, Yinchuan.XU@bosch.com  and Sam Hutchings ,
> I had a quick chat with Yinchuan.XU@bosch.com  about this. It looks like the root cause was that the parameter rba_syselem_headerlength was set to 0 in the ecucvalues.
>
> It looks like this parameter was imported, not by ConfGen, but some customer script. 
>
> For SomeIp the header length is always going to be 64, without exception. Setting it to 0 will produce this faulty behavior.
>
> It could be considered to validate this parameter in a someipxf bsw module and throwing an error in this case, since it is guaranteed to be incorrect. I will bring it up with SomeIpXf dev team and ask for opinions. It is always not nice if such an error only shows up at runtime and can not be detected earlier.
>
> Sam Hutchings : Thank you for processing this ticket on german holiday.

-------

> [!note]+ 2025-05-30 10:05 · Sam Hutchings
> Hi Mingye YUAN,
>
> I don't think this is an issue in RTA-CAR, I think the configuration is incorrect and have explained why. If you think the explanation is wrong, please can you state why?
>
> Kind regards,
> Sam

-------

> [!note]+ 2025-05-30 07:29 · Mingye YUAN
> Hello Sam:
>
> I see the request status has been changed to “Solution Proposed“. Can I ask in which version of RTA-CAR this issue will be fixed? Thanks.

-------

> [!note]+ 2025-05-29 18:04 · Sam Hutchings
> Hi Yinchuan XU,
>
> I have reviewed the attached project and after some discussion with my colleagues, we believe that the issue is the PDU length in the EcuC module is wrong. In the example you have shared, it is set to 21, but in the System Description and the rba_SysElem module, it is set to 13. We believe that the PDU length is incorrect, perhaps from an old project or including the header length.
>
> In this case, it is likely that the 8 bytes at the start are just padding, to make the 13 bytes fit into the specified 21 bytes.
>
> ![[RH-13161-image-2025-05-29-17-04-04-389.png]] 
>
> Correcting the PDU length should resolve these issues.
>
> Kind regards,
> Sam

-------

> [!note]+ 2025-05-29 08:37 · Yinchuan XU
> [^Cariad_RteET_20250529.zip] *(7.33 MB)*

-------

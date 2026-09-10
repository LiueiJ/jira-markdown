---
jira_key: RH-13575
jira_url: "https://rtahotline.etas.com/jira/browse/RH-13575"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Low
project: RH
assignee: Xiao BAI
reporter: Xiao BAI
tags: [jira/comp/isolar-a]
fix-versions: []
epic: null
parent: null
created: "2025-07-24T12:23:27.000+0200"
updated: "2026-03-05T06:52:02.000+0100"
synced-at: "2026-09-10T08:07:25.599Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Hello Hotline team, 

I have a Component Code-Frame issue. 

If the Interface’s access point is DataWritePoints, when I generate code-frame in RTA-CAR 12.3.1, it will be showed as bellow, and it is correct. 

![[RH-13575-image001.png]] 

But when I do the same in RTA-CAR 12.6.0, it will be showed as bellow： 

![[RH-13575-image002.png]] 

In the two pictures, you can see that in 12.6.0 there is an extra ‘&’. This can lead to errors when debugging because it is value not an address. 

Is there any solution for this issue? Thank you very much for your support. 

 **Best Regards,** 

 ** Xiao BAI** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 

 T +86 28 6520-3444 

 [Xiao.BAI@cn.bosch.com!mail_small.gif!](mailto:Xiao.BAI@cn.bosch.com) 

 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

 [www.etas.cn](http://www.etas.cn)   ** 

 

 ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2025-09-16 18:03 · JSM Service Bot
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2025-09-02 10:36 · James Butterfield
> Hi Xiao BAI and Krishnaswamy Dharani Dharan,
>
> I have moved this ticket to Solution Proposed as the original issue has been resolved with a workaround, and there is also a linked work ticket to resolve this issue in the future.
> If you require any further assistance with this issue, please feel free to re-open the ticket!
>
> Best Regards,
> James

-------

> [!note]+ 2025-09-02 08:43 · Krishnaswamy Dharani Dharan
> Hello James Butterfield, 
>
> Please find the workaround attached.
>
> You can use this template.
>
> [^template 4.zip]
>
> Thank you

-------

> [!note]+ 2025-09-02 08:43 · Krishnaswamy Dharani Dharan
> [^template 4.zip]

-------

> [!note]+ 2025-08-11 11:05 · JSM Service Bot
> Hi ISOLAR-A Support Owner. This ticket requires an assignee.

-------

> [!note]+ 2025-08-11 11:05 · James Butterfield
> Hi Xiao BAI,
>
> Thank you for supplying the project file.
>
> Hi Krishnaswamy Dharani Dharan,
>
> Please find attached the project file requested.
>
> Best Regards,
> James

-------

> [!note]+ 2025-08-11 10:57 · Xiao BAI
> Hello James Butterfield ,
>
> The customer's project file is [^autosar_rta_xip-develop-vctc-bms-bip-CD-rh850U2A8GHS-1260@820f06eeaad.zip]

-------

> [!note]+ 2025-08-08 10:09 · James Butterfield
> Hi Xiao BAI,
>
> The L3 team have been able to reproduce the original issue and would like to carry out further analysis to prevent this from happening in the future.
> Would it be possible for you to provide us with the customer's project file?
>
> Best Regards,
> James

-------

> [!note]+ 2025-08-08 07:49 · Krishnaswamy Dharani Dharan
> hello James Butterfield ,
>
> Reported issue reproducible, Can you share the project to analysis and feedback
>
> Thank you!!!

-------

> [!note]+ 2025-07-25 15:56 · James Butterfield
> Hi Vamsi Kiran Koduri, thank you we will send this to the ISOLAR developers.
>
>
>
> Hi Ramakant Achari Raviraj, 
>
> We just wanted to check whether there should be a hard-coded & on line 30 of {_}WriteSection.xpt{_}.
>
> It is my understanding that if *checkIfComplexDataType* returns an '&', then the result would be, for example, *&&iWrite1* due to the hard-coded &. Is this expected behaviour?
>
>
>
> Thanks,
>
> James

-------

> [!note]+ 2025-07-25 15:54 · JSM Service Bot
> Hi ISOLAR-A Support Owner. This ticket requires an assignee.

-------

> [!note]+ 2025-07-25 15:23 · Vamsi Kiran Koduri
> James Butterfield I have no idea about file WriteSection.xpt. This seems internal to RTA-CAR and not related to RTE.

-------

> [!note]+ 2025-07-25 12:49 · JSM Service Bot
> Hi RTA-RTE Support Owner. This ticket requires an assignee.

-------

> [!note]+ 2025-07-25 12:19 · James Butterfield
> Hi Vamsi Kiran Koduri,
>
> The problem has been solved for the customer, however we just wanted to check whether there should be a hard-coded & on line 30 of {_}WriteSection.xpt{_}.
>
> It is my understanding that if *checkIfComplexDataType* returns an '&', then the result would be, for example, *&&iWrite1* due to the hard-coded &. Is this expected behaviour?

-------

> [!note]+ 2025-07-25 12:03 · Vamsi Kiran Koduri
> Sammy Burchmore Sorry, i didn't understand your question. Reading comments I assume the problem is resolved using new template.

-------

> [!note]+ 2025-07-25 11:58 · Sammy Burchmore
> Hi Vamsi Kiran Koduri,
>
> ![[RH-13575-image-2025-07-25-10-56-43-594.png]]
>
> Should the & here be hard coded? If they use the old template their code is output with 2 &s.
>
> Thanks,
>
> Sammy

-------

> [!note]+ 2025-07-25 11:52 · JSM Service Bot
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

> [!note]+ 2025-07-25 11:51 · JSM Service Bot
> Hi RTA-RTE Support Owner. This ticket requires an assignee.

-------

> [!note]+ 2025-07-25 04:53 · JSM Service Bot
> Xiao BAI, the comment you've just made is internal. Please note that internal comments do not transition an issue to 'Waiting for Level 2'.

-------

> [!note]+ 2025-07-25 04:53 · Xiao BAI
> Hello James Butterfield and Sammy Burchmore ,
>
> Thanks for your support. The error has been resolved with the new templates.

-------

> [!note]+ 2025-07-24 18:09 · James Butterfield
> Hi Xiao BAI,
>
> There also could be an error with the Code Frame Generator templates.
>
> Please could you try using this updated templates folder: [^template.zip]
>
> ![[RH-13575-image-2025-07-24-17-06-49-634.png]]
>
> Please let us know if this resolves your problem.
>
> Best Regards,
>
> James

-------

> [!note]+ 2025-07-24 17:27 · Sammy Burchmore
> Hi Xiao BAI,
>
> Does the data type change between the 2 projects? ![[RH-13575-image-2025-07-24-16-26-11-108.png]]
>
> If the 12.6.0 project is using a complex data type, then this is expected behavior.
>
> Thanks,
>
> Sammy

-------

---
jira_key: RH-12653
jira_url: "https://rtahotline.etas.com/jira/browse/RH-12653"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Medium
project: RH
assignee: Marc Kaiser
reporter: Sisi TAO
tags: []
fix-versions: []
epic: null
parent: null
created: "2025-03-26T03:16:32.000+0100"
updated: "2026-03-05T06:52:03.000+0100"
synced-at: "2026-09-10T08:07:25.599Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Dear hotline colleague, 

Recently I’m using RTA-CAR 12.6.0pr1 ConfGen. The way how Java error reported is different from the previous versions. Previously the line number and the file where error occurred could be reported in error trace. But now these informations are replaced with a decent but not helpful way as follows. Previously the root cause can at least be found by looking into the script in our hub quickly… But it’s not possible now. Or every one in hub needs to build up the debug environment. Is it possible to print more information than this? 

 **&#91;ERROR&#93;ConfGen_002: Error occured while generating the LINTP module on creation of LinTpRxNSdu Parameter**

 **&#91;ERROR&#93;Error while executing JacoP importer** 

 **src.importer.general.GenericImporterException: ConfGen_002: Error occured while generating the LINTP module on creation of LinTpRxNSdu Parameter** 

 **&#91;INFO&#93;JacoP importer execution completed.** 

 

  **Sisi TAO** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 

 M +86 133 81555197 

 [Sisi.TAO@bosch.com!mail_small.gif!](mailto:Sisi.TAO@bosch.com) 

 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

 [www.etas.com](http://www.etas.com)  ** 

 

 ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2025-03-26 12:28 · Sisi TAO
> Hi Marc Kaiser ,
>
> Good to hear that. Since now I don't have confgen issue and the installer will not be provided in customer as product, I don't need this installer for now. Will ping you if there's a must. Thank you very much for your help.

-------

> [!note]+ 2025-03-26 11:19 · Marc Kaiser
> Hello Sisi TAO,
>
> I have good news. I have had a good discussion with Product Field (K Raj Kumar).
>
> In **RTA-CAR 12.7.0** it will work like this:
>
> If you set manprop_AlgoPropertiesDebug=true in the algo.properties, then ConfGen will output the Stack Trace, in addition to the new Error Message format.
>
> If this property is not set then StackTrace will not be printed.
>
> For **RTA-CAR 12.6.0** I can offer to create a ConfGen RTA-CAR installer that will output the Stacktrace for you always. Would that be helpful?

-------

> [!note]+ 2025-03-26 09:06 · Marc Kaiser
> Hello Sisi TAO, you are correct.
>
> the decision by Product Field to hide "ununderstandable" error messages was made intentionally. The rationale provided for this decision is that, since the end user cannot access the ConfGen code (although ETAS Hubs can, OEMs will not be able to), they would lack the ability to interpret stack traces.
>
> However, I have already communicated to Product Field that I strongly disagree with this approach.
>
> Now that this ticket has been created, I believe it provides an opportunity to revisit this decision. I will advocate vigorously to reverse this change in our ConfGen Product.
>
> It is crucial for Product Field to recognize that every piece of information can aid the end user in identifying and resolving issues more efficiently. Restricting potentially valuable error details, even if they are in a less-than-perfect format, hinders productivity.
>
> Our goal should be to make RTA-CAR a productive tool. Concealing information that could assist in troubleshooting, merely because it might not be immediately interpretable, is a counterproductive decision that must be reverted.

-------

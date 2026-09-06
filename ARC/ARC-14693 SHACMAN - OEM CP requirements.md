---
jira_key: ARC-14693
jira_url: "https://jira.etas-dev.com/browse/ARC-14693"
server: etas
kind: motivation
type: Motivation
status: New
priority: ""
project: ARC
assignee: npr5kor
reporter: mas1yok
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2026-01-30T06:01:32.000+0000"
updated: "2026-06-19T08:17:03.000+0000"
synced-at: "2026-09-06T06:58:54.667Z"
jira-orphaned: false
---

# ARC-14693 SHACMAN - OEM CP requirements

> [!jira] New ·  · [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]] · 更新于 2026-06-19T08:17:03.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-14693)

## 描述

Here is requirement from OEM (SHACMAN), does the latest RTA-Car version support the function or not?

If not support feature, how much cost will charge customer? what’s the time to support?

Please feedback before this weekend.

![[ARC-14693-image-2026-01-30-13-58-40-104.png]]

By upgrading the terminal, develop parallel upgrade functionality and Ethernet data forwarding routing functionality for the MCUA controller, which supports 8 parallel CANFD channels and 4 parallel CAN device MCU controllers. 

(MCUA is IFX TC399)

1. The upgrade terminal sends data to the SOC via Ethernet.
2. The SOC splits the Ethernet data into CANFD or CAN data.
3. The SOC sends the received data to the MCUA device via Ethernet.
4. The MCUA directly routes the received Ethernet data to the corresponding MCU devices under its subnet.
5. The subnet includes 8 channels based on CANFD networks and 4 channels based on CAN communication networks.
6. OBD upgrades the MCUA and its subordinate nodes via CAN.
7. ABC upgrades the MCUA and its subordinate nodes via CANFD.

 

**The required functionality to be supported is as follows:** 

1. The toolchain must support both J1939_CAN (4 channels) and CANFD (8 channels) transceiver functionality simultaneously.
2. Support DOIP direct routing to CANFD (8 channels) and CAN (4 channels).
3. Support multiple DOIP logical addresses.
4. Support DOIP data transfer to the DCM layer.
5. Support importing ODX files to add DOIP and DOCAN configuration parameters.
6. Provide a cdd file with templates for ODX (CAN/CANFD/LIN/DOIP).
7. Support direct transfer of DOIP data to SWC functionality.
8. Support both CANFD and CAN upgrade functionality simultaneously.
9. Support Ethernet function configuration.
10. Comply with AUTOSAR specifications.
11. Include AUTOSAR modules such as OS, NVM, DEM, and DCM.
12. The toolchain must not be bound to specific chips.
13. Support importing files such as arxml, dbc, and odx.
14. Include an information security module.
15. Include a functional safety module (including safety pack).
16. Provide convenient communication matrix modification functionality.
17. Support OSEK network management and indirect network management.
18. Support parallel upgrades for multiple CAN/CANFD channels.
19. Corresponding MCAL and AUTOSAR versions.

## 评论

> [!note]+ 2026-03-03 21:06 · [[Burn_Alexander_(ETAS-ECMXPC-Yok1)|Burn Alexander (ETAS-ECM/XPC-Yok1)]]
> [[TAN_Yang_(ETAS-ECMXSF-CN)|TAN Yang (ETAS-ECM/XSF-CN)]] Yes IFX SafeTPack is the IFX libs for safety, but this does beg the question - if they need this do they not need the FSQP too? We should check this with them so we do not find out they need it later and have issues with adoption.

-------

> [!note]+ 2026-02-26 08:19 · [[TAN_Yang_(ETAS-ECMXSF-CN)|TAN Yang (ETAS-ECM/XSF-CN)]]
> <<<
>  * 15, Include a functional safety module (including safety pack). 
>  * {color:#0747a6}Yes, [[Burn_Alexander_(ETAS-ECMXPC-Yok1)|Burn Alexander (ETAS-ECM/XPC-Yok1)]] {color}
>
> {color:#0747a6}>>>{color}
>
> {color:#0747a6}This is IFX SafeTpack, not FSQP. So sould not related to you Alex [[Burn_Alexander_(ETAS-ECMXPC-Yok1)|Burn Alexander (ETAS-ECM/XPC-Yok1)]]  ?{color}

-------

> [!note]+ 2026-02-06 12:29 · [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]
> In general, we already support J1939 communication on both Classical CAN and CAN FD.
> Currently, what is not supported is the transmission of J1939 Transport Protocol - **TP** messages over CAN FD. Supporting this use case requires an additional module, namely the J1939_CANFdTp module, which is not yet integrated into RTA-CAR.
> Whether this capability is required depends on the specific customer use case. 
> The J1939_CANFdTp module is already available on our side and is tentatively planned for integration into RTA-CAR 12.12.0.
> Please let us know if this use case is relevant for customer, we can then align accordingly.

-------

> [!note]+ 2026-02-04 08:15 · [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]]
> [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]] 
>  # The toolchain must support both J1939_CAN (4 channels) and CANFD (8 channels) transceiver functionality simultaneously.
>
>  * {color:#0747a6}J1939_CAN and CANFD supported for multiple channels, but please not we do not support J1939_CANFD yet{color}
>
> Which version will support J1939_CANFD?  and when? 

-------

> [!note]+ 2026-02-04 07:46 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]  thanks for the initial feedback.  will get back to you on the open questions. 
>
> [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]] please follow-up with the customer. it would be great if you could provide us with some updates on the follow-up questions. thanks 

-------

> [!note]+ 2026-02-02 09:40 · [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]
> Feedback already provided to [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]], documenting here:
>
> 1. The toolchain must support both J1939_CAN (4 channels) and CANFD (8 channels) transceiver functionality simultaneously. 
> - {color:#0747A6} J1939_CAN and CANFD supported for multiple channels, but please not we do not support J1939_CANFD yet{color}
> 2. Support DOIP direct routing to CANFD (8 channels) and CAN (4 channels). 
> - {color:#0747A6}Supported TP gateway (DOIP - PDUR - CANTP) {color}
> 3. Support multiple DOIP logical addresses. 
> - {color:#0747A6}Supported, Its possible to select multiple DOIP logical address using the Post Build Selectable feature {color}
> 4. Support DOIP data transfer to the DCM layer. 
> - {color:#0747A6} Supported DOIP - PduR - DCM{color}
> 5. Support importing ODX files to add DOIP and DOCAN configuration parameters. 
> - {color:#0747A6}Supported,  I understand that there is ODX importer available {color}
> 6. Provide a cdd file with templates for ODX (CAN/CANFD/LIN/DOIP). 
> - {color:#0747A6}Typically ODX files are available for Diag services in DCM . Q : What is expected in the template here?{color} 
> 7. Support direct transfer of DOIP data to SWC functionality. 
> - {color:#0747A6} Typically through PduR/RTE interfaces.{color}
> 8. Support both CANFD and CAN upgrade functionality simultaneously. 
> - {color:#0747A6}Yes supported , by using different HW object and channels (Classic CAN and CAN FD) Q: what does upgrade mean here? {color}
> 9. Support Ethernet function configuration. 
> - {color:#0747A6}Supported{color}
> 10. Comply with AUTOSAR specifications. 
> - {color:#0747A6}Yes{color}
> 11. Include AUTOSAR modules such as OS, NVM, DEM, and DCM. 
> - {color:#0747A6}Included with RTA-BSW and RTA-OS{color}
> 12. The toolchain must not be bound to specific chips. 
> - {color:#0747A6}Yes, iSOLAR is not bound to any specific MCAL{color}
>  13. Support importing files such as arxml, dbc, and odx. 
> - {color:#0747A6}Yes{color}
>  14. Include an information security module. 
> - {color:#0747A6}What is expected here?{color}
> 15, Include a functional safety module (including safety pack). 
> - {color:#0747A6}Yes, [[Burn_Alexander_(ETAS-ECMXPC-Yok1)|Burn Alexander (ETAS-ECM/XPC-Yok1)]] {color}
> 16. Provide convenient communication matrix modification functionality. 
> - {color:#0747A6}What is expected here, more details needed?{color}

-------

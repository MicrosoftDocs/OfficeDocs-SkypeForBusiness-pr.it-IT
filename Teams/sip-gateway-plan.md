---
title: Pianificare gateway SIP
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/30/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Altre informazioni sul Gateway SIP, ad esempio requisiti e vantaggi.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0a1a178c279a418c0555f100c48a63c9efe71717
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681787"
---
# <a name="plan-for-sip-gateway"></a>Pianificare il Gateway SIP

Gateway SIP consente all'organizzazione di usare qualsiasi dispositivo SIP compatibile con Microsoft Teams per conservare gli investimenti effettuati nei dispositivi SIP. Ora è possibile accedere a Teams con le credenziali aziendali ed effettuare e ricevere chiamate con un dispositivo SIP compatibile. I dispositivi compatibili possono essere Skype for Business telefoni IP con firmware SIP standard, telefoni CISCO IP con firmware SIP multipiattaforma o dispositivi SIP di fornitori come Poly, Yealink e AudioCodes. Per informazioni su come configurare i dispositivi SIP per gateway SIP, vedere [Configurare il gateway SIP](sip-gateway-configure.md).

## <a name="benefits-of-sip-gateway"></a>Vantaggi del Gateway SIP

Gateway SIP connette dispositivi SIP compatibili a Teams per consentire agli utenti di eseguire facilmente la migrazione alla telefonia Teams. Con gateway SIP, gli utenti possono eseguire tutte le operazioni seguenti:

- **Effettuare chiamate:** Gli utenti di dispositivi SIP possono effettuare chiamate alla rete PSTN (Public Switched Telephone Network), ad altri dispositivi SIP e ad Teams e Skype for Business utenti. Gli utenti di dispositivi SIP possono chiamare solo utenti con numeri di telefono.
- **Ricevere chiamate:** Gli utenti di dispositivi SIP possono ricevere una chiamata da PSTN, da Teams o Skype for Business utenti che dispongono di dispositivi SIP e da applicazioni client Teams e Skype for Business. Il dispositivo SIP funge da endpoint Teams. Anche le chiamate in ingresso verranno biformate al dispositivo SIP dell'utente.
- **Più chiamate simultanee:** Un utente del dispositivo SIP in una chiamata può mettere la chiamata in attesa per effettuare o ricevere altre chiamate. Un utente del dispositivo SIP può anche effettuare due conferenze telefoniche.
- **Non disturbare:** Un utente del dispositivo SIP può impostare non disturbare nel dispositivo in modo che il dispositivo non squilli per le chiamate in arrivo. Questo non ha alcun impatto sullo stato dell'utente su tutti gli altri endpoint Teams.
- **Tieni premuto/riprendi e disattiva/riattiva l'audio:** Un utente del dispositivo SIP può sospendere e riattivare o disattivare e riattivare l'audio di una chiamata utilizzando le funzionalità per tali azioni nel dispositivo.
- **Segreteria telefonica:** Gli utenti di dispositivi SIP possono ascoltare i messaggi vocali archiviati elettronicamente che i chiamanti lasciano per loro.
- **Indicatore messaggio in attesa:** Gli utenti di dispositivi SIP possono ricevere notifiche che li avvisano quando hanno nuovi messaggi di segreteria telefonica.
- **Accedere e disconnettersi:** Gli utenti di dispositivi SIP possono accedere e disconnettersi da Teams nel dispositivo.
- **Multifrequenza a doppio tono:** Gli utenti di dispositivi SIP possono premere i tasti numerici per fornire input durante le chiamate di risposta vocale interattive.
- **riunioni Teams:** un utente del dispositivo SIP può partecipare a una riunione Teams componendo il numero di accesso alla riunione. I partecipanti alla riunione possono aggiungere un utente del dispositivo SIP alla riunione componendo il numero di telefono dell'utente o semplicemente aggiungendo un partecipante facendo clic su "Richiedi di partecipare" avviserà anche il dispositivo SIP dell'utente. Gli utenti guest di un'altra organizzazione possono essere aggiunti a una riunione Teams da un partecipante che esegue la chiamata in uscita al numero di un utente guest per includere tale guest.
- **Trasferimenti di chiamata:** Gli utenti di dispositivi SIP possono trasferire le chiamate. Sip Gateway supporta i trasferimenti non vedenti e consultivi.
- **Inoltro di chiamata locale:** Un utente del dispositivo SIP può impostare regole di inoltro (sempre in caso di timeout e occupato) per il dispositivo. Se il dispositivo è connesso al Gateway SIP, la chiamata verrà reindirizzata all'indirizzo di destinazione in base alla regola impostata dall'utente del dispositivo. Per eseguire l'inoltro di chiamata locale, l'amministratore deve impostare l'attributo `AllowCallRedirect` in su `Set-CsTeamsCallingPolicy` `Enabled`.

## <a name="requirements-to-use-sip-gateway"></a>Requisiti per l'uso del Gateway SIP

Teams gli utenti devono avere un numero di telefono con le chiamate PSTN abilitate per l'uso di Gateway SIP.

### <a name="hardware-software-and-licenses"></a>Hardware, software e licenze

Se si dispone di un dispositivo 3PIP o SIP, è necessario disporre di:

- Una licenza per Sistema telefonico (tramite E5 o una licenza autonoma)
- Abilitazione PSTN (ad esempio un numero di telefono) tramite un piano per chiamate Microsoft Teams, routing diretto o Connessione con operatore
- Una licenza Telefono Area comune per qualsiasi dispositivo dell'area comune

## <a name="compatible-devices"></a>Dispositivi compatibili

|Fornitore    |Modello      |Versione firmware minima|Versione firmware approvata|Note|Link|
|----------|-----------|------------|-----------|------------|------------|
|**Cisco** |           |            |           |I dispositivi che eseguono firmware aziendale devono essere convertiti in firmware multipiattaforma. Leggi la guida a destra per scoprire come.|[Guida alla conversione del firmware Cisco](https://www.cisco.com/c/en/us/products/collateral/collaboration-endpoints/unified-ip-phone-7800-series/guide-c07-742786.html)|
|          |8832       |11,3,5 MPP   |11,3,5 MPP  |   |   |
|          |6821       |11.1.1MPP   |11-3-3 MPP  |   |   |
|          |7811       |11.1.1MPP   |11-3-3 MPP  |   |   |
|          |7821       |11.1.1MPP   |11-3-3 MPP  |   |   |
|          |7841       |11.1.1MPP   |11-3-3 MPP  |   |   |
|          |7861       |11.1.1MPP   |11-3-3 MPP  |   |   |
|          |8811       |11.1.1MPP   |11-3-3 MPP  |   |   |
|          |8841       |11.1.1MPP   |11-3-3 MPP  |   |   |
|          |8845       |11.1.1MPP   |11-3-3 MPP  |   |   |
|          |8851       |11.1.1MPP   |11-3-3 MPP  |   |   |
|          |8861       |11.1.1MPP   |11-3-3 MPP  |   |   |
|          |8865       |11.1.1MPP   |11-3-3 MPP  |   |   |
|**Poli**  |           |            |           |Il dispositivo verrà riavviato automaticamente e installerà il firmware selezionato.|   |
|          |CCX 500    |7.0.3.0515  |7.2.1.1826 |   |   |
|          |Trio 8500  |5.9.5.3182  |7.1.1.0997 |   |   |
|          |Trio 8800  |5.9.5.3182  |7.1.1.0997 |   |   |
|          |VVX150     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX201     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX250     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX300     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX301     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX310     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX311     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX350     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX400     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX401     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX410     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX411     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX450     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX500     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX501     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX600     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX601     |5.9.5       |6.3.1.8427 |   |   |
|**Yealink**|          |            |           |   |[Supporto yealink](https://support.yealink.com/)|
|          |T40P       |83          |54.84.0.125|   |   |
|          |T41S       |83          |66.85.0.5  |   |   |
|          |T41S       |83          |66.85.0.5  |   |   |
|          |T41S       |83          |66.85.0.5  |   |   |
|          |T42G       |83          |29.83.0.130|   |   |
|          |T42S       |83          |66.85.0.5  |   |   |
|          |T42U       |83          |108.86.0.20|   |   |
|          |T43U       |83          |108.86.0.20|   |   |
|          |T46S       |83          |66.85.0.5  |   |   |
|          |T46U       |83          |108.86.0.20|   |   |
|          |T48S       |83          |66.85.0.5  |   |   |
|          |T48G       |83          |35.83.0.130|   |   |
|          |T48U       |83          |108.86.0.20|   |   |
|          |T53        |83          |96.85.0.5  |   |   |
|          |T53W       |83          |96.85.0.5  |   |   |
|          |T54W       |83          |96.85.0.5  |   |   |
|          |T57W       |83          |96.85.0.5  |   |   |
|          |T21P       |83          |52.84.0.140|   |   |
|          |T23G       |83          |44.84.0.140|   |   |
|          |T27G       |83          |69.85.0.5  |   |   |
|          |T29G       |83          |46.83.0.130|   |   |
|          |T30        |83          |124.85.0.40|   |   |
|          |T30P       |83          |124.85.0.40|   |   |
|          |T31G       |83          |124.85.0.40|   |   |
|          |T33G       |83          |124.85.0.40|   |   |
|          |T40G       |83          |76.84.0.125|   |   |
|          |T41P       |83          |36.83.0.120|   |   |
|          |T46G       |83          |28.83.0.130|   |   |
|**AudioCodes**|       |            |           |Alcuni dispositivi SIP AudioCodes richiedono un'impostazione URL di provisioning. Scarica e installa i file di aggiornamento per i dispositivi AudioCodes interessati a destra. |[File scaricabili per i dispositivi interessati su AudioCodes](https://audiocodes.sharefile.com/share/view/sc9cdf17f9ec45d09/fo7914a2-4f3a-4000-8957-47bd6f35a3a5)|
|          |405         |2.2.8      |2.2.16.570 |   |   |
|          |405HD       |3.2.1      |2.2.16.570 |   |   |
|          |420HD       |3.2.1      |2.2.16.570 |   |   |
|          |430HD       |3.2.1      |2.2.16.570 |   |   |
|          |440HD       |3.2.1      |2.2.16.570 |   |   |
|          |450HD       |3.2.1      |3.4.6.687  |   |   |
|          |C450HD      |3.2.1      |3.4.6.687  |   |   |
|          |445HD       |3.2.1      |3.4.6.687  |   |   |
|          |RX50        |3.2.1      |3.4.6.687  |   |   |

> [!NOTE]
> Per alcuni dispositivi, la versione minima del firmware è maggiore della versione approvata del firmware. Questo perché la versione 3.X è la versione Skype for Business. Viene aggiornata la versione SIP 2.X.

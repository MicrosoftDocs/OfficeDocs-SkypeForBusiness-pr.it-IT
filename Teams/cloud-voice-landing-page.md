---
title: Cloud Voice in Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- M365-voice
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
search.appverid: MET150
description: Leggi altre informazioni sulla funzionalità cloud Voice e leggi le decisioni di distribuzione necessarie che dovrai affrontare.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 952eb7064844cf0e77e829cd2506c4303504074c
ms.sourcegitcommit: 3ed779277540589eabef745685ab6c67d8a8ff90
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "44281671"
---
# <a name="cloud-voice-in-microsoft-teams"></a>Cloud Voice in Microsoft Teams

L'[Introduzione](get-started-with-teams-quick-start.md) è stata completata. Si è implementato Teams nell'organizzazione, con [chat, team, canali e app](deploy-chat-teams-channels-microsoft-teams-landing-page.md). Forse hai distribuito [riunioni & conferenze](deploy-meetings-microsoft-teams-landing-page.md). Ora si è pronti ad aggiungere funzionalità di cloud Voice per gli utenti. 

Cloud Voice offre funzionalità PBX (Private Branch Exchange) e opzioni per la connessione alla rete PSTN (Public Switched Telephone Network).

Questo articolo consente di decidere se è necessario modificare le impostazioni vocali predefinite del cloud, in base al profilo dell'organizzazione e ai requisiti aziendali, quindi illustra ogni modifica. Le impostazioni sono suddivise in due gruppi, a partire dal set di [modifiche che è più probabile apportare](#core-deployment-decisions). Il secondo gruppo include le [impostazioni aggiuntive](#additional-deployment-decisions) che può essere utile configurare in base alle esigenze dell'organizzazione.

È consigliabile che tutte le organizzazioni funzionino tramite le decisioni principali e quindi, se l'organizzazione ha requisiti aggiuntivi, esaminare il materiale seguente.



## <a name="learn-more-about-cloud-voice"></a>Leggi altre informazioni su cloud Voice

Gli articoli seguenti includono ulteriori informazioni sulla distribuzione e l'uso delle funzionalità vocali cloud in teams:

- [Sistema telefonico di Office 365](what-is-phone-system-in-office-365.md)
- [Sistema telefonico con piani di chiamata](calling-plan-landing-page.md)
- [Instradamento diretto di Sistema telefonico](direct-routing-landing-page.md)
- [Distribuzione di cloud Voice](cloud-voice-deployment.md)
- [Soluzioni di telefonia Microsoft](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)
- Per altre informazioni sul sistema telefonico, vedere la sessione seguente: [Introduzione al sistema telefonico in Microsoft teams](https://aka.ms/teams-phone-system)


## <a name="core-deployment-decisions"></a>Decisioni chiave per la distribuzione

Di seguito sono illustrate le impostazioni che la maggior parte delle organizzazioni vorrà modificare se le impostazioni predefinite di Teams non sono adeguate.

## <a name="phone-system-office-365"></a>Sistema telefonico (Office 365)

Sistema telefonico è la tecnologia Microsoft per abilitare il controllo delle chiamate e le funzionalità del PBX (Private Branch Exchange) nel cloud di Office 365. Sistema telefonico consente di sostituire il sistema PBX (Private Branch Exchange) esistente con un set di caratteristiche direttamente recapitate da Office 365 e strettamente integrate nell'esperienza di produttività del cloud aziendale.


|Chiedersi|Azione |
|:------------|:-------|
|In quali sedi utente o uffici verrà implementato il sistema telefonico? |Per altre informazioni sul sistema telefonico, vedere [cos'è il sistema telefonico in Office 365](what-is-phone-system-in-office-365.md).</li></ul>|
|||

## <a name="connection-to-the-public-switched-telephone-network-pstn"></a>Connessione alla rete PSTN (Public Switched Telephone Network)

Per connettere il sistema telefonico alla rete PSTN (Public Switched Telephone Network) in modo che gli utenti possano effettuare telefonate in tutto il mondo, sono disponibili opzioni in base alle esigenze aziendali.  Porsi le operazioni seguenti:


|Chiedersi|Azione |
| :------------|:-------|
| Si vuole usare Microsoft Calling Plan come gestore di telefonia? | Per altre informazioni, Vedi [sistema telefonico con piani di chiamata](calling-plan-landing-page.md).|
| È necessario usare il proprio gestore di telefonia? | Per altre informazioni, Vedi [sistema telefonico con routing diretto](direct-routing-landing-page.md).
|||


## <a name="additional-deployment-decisions"></a>Ulteriori decisioni per la distribuzione

Potrebbe essere necessario modificare le impostazioni per le seguenti, in base alle esigenze e alla configurazione dell'organizzazione:

- Segreteria telefonica
- Chiamata dell'identità
- Numeri di telefono da Microsoft
- Dial plan
- Code di chiamata
- Operatori automatici

### <a name="voicemail"></a>Segreteria telefonica

Cloud voicemail, alimentato da servizi di Azure voicemail, supporta i depositi della segreteria telefonica solo alle cassette postali di Exchange e non supporta sistemi di posta elettronica di terze parti. Cloud Voicemail include la trascrizione della segreteria telefonica, che è abilitata per tutti gli utenti dell'organizzazione per impostazione predefinita. Le esigenze aziendali potrebbero richiedere la disattivazione della trascrizione della segreteria telefonica per utenti specifici o tutti nell'organizzazione.

|Chiedersi|Azione |
|:------------|:-------|
| Si vuole abilitare la segreteria telefonica cloud? | Per le procedure di configurazione della segreteria telefonica, vedere [configurare la segreteria telefonica cloud](set-up-phone-system-voicemail.md).
| Si vuole abilitare la trascrizione della segreteria telefonica per alcuni o tutti gli utenti? | Per disattivare la trascrizione della segreteria telefonica, vedere [impostazione di criteri per la segreteria telefonica nell'organizzazione](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</li></ul>|
|||

### <a name="calling-identity"></a>Chiamata dell'identità

Per impostazione predefinita, tutte le chiamate in uscita usano il numero di telefono assegnato come identità di chiamata (ID chiamante). Il destinatario della chiamata può identificare rapidamente il chiamante e decidere se accettare o rifiutare la chiamata.

|Chiedersi|Azione |
|:------------|:-------|
|Si vuole mascherare o disabilitare l'ID chiamante? | Per modificare o bloccare l'ID chiamante, vedere [impostare l'ID chiamante per un utente](set-the-caller-id-for-a-user.md). |
|||

### <a name="phone-numbers-from-microsoft"></a>Numeri di telefono da Microsoft

Microsoft ha due tipi di numeri di telefono disponibili: i numeri di *abbonato* (utente), che possono essere assegnati agli utenti dell'organizzazione e i numeri di *servizio* , disponibili come numeri di servizio a pedaggio e a numero verde, che hanno una maggiore capacità di chiamata simultanea rispetto ai numeri di abbonati e che possono essere assegnati a servizi come audioconferenza, operatori automatici o code di chiamata.

|Chiedersi|Azione |
| :------------|:-------|
| Quali posizioni utente richiedono nuovi numeri di telefono da Microsoft? | Per informazioni su come ottenere i numeri di telefono, vedere [gestire i numeri di telefono per l'organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) e [ottenere i numeri di telefono per gli utenti](getting-phone-numbers-for-your-users.md). 
| Quale tipo di numero di telefono (abbonato o servizio) è necessario? | Per selezionare il tipo di numero di telefono necessario, vedere i [diversi tipi di numeri di telefono usati per chiamare i piani](different-kinds-of-phone-numbers-used-for-calling-plans.md).
Come si trasferiscono I numeri di telefono esistenti in teams?|Per altre informazioni, vedere [trasferire i numeri di telefono in Microsoft teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).
|||

### <a name="dial-plans"></a>Dial plan

Un dial plan nella caratteristica sistema telefonico di Office 365 è un set di regole di normalizzazione che traducono i numeri di telefono composti in un formato alternativo (in genere E. 164) per l'autorizzazione alle chiamate e il routing delle chiamate.

Per altre informazioni sui dial plan, vedere [Che cosa sono i dial plan?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)

|Chiedersi|Azione |
|:------------|:-------|
| L'organizzazione ha bisogno di un dial plan personalizzato? | Per determinare se è necessario un piano di chiamata personalizzato, vedere [pianificazione per i piani di chiamata del tenant](what-are-dial-plans.md#planning-for-tenant-dial-plans)|
Quali utenti devono avere un dial plan personalizzato e quale dial plan del tenant occorre assegnare a ogni utente? | Per aggiungere utenti a un dial plan personalizzato in PowerShell, vedere [creare e gestire piani di chiamata](create-and-manage-dial-plans.md). |
|||

### <a name="call-queues"></a>Code di chiamata

Le code delle chiamate Cloud includono i messaggi di saluto usati quando qualcuno chiama un numero di telefono per l'organizzazione, la possibilità di inserire automaticamente le chiamate in attesa e la possibilità di cercare l'agente di chiamata disponibile per gestire la chiamata mentre le persone che chiamano ascoltano musica in attesa. È possibile creare code di chiamata singole o multiple per l'organizzazione. 


|Chiedersi|Azione |
|:------------|:-------|
| L'organizzazione ha bisogno delle code di chiamata? | Per altre informazioni, vedere [creare una coda di chiamata cloud](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) e [configurare il sistema telefonico](setting-up-your-phone-system.md). |

### <a name="auto-attendants"></a>Operatori automatici

Gli operatori automatici cloud possono essere usati per creare un sistema di menu per l'organizzazione che consente ai chiamanti esterni e interni di spostarsi in un sistema di menu per individuare e trasferire le chiamate agli utenti o ai reparti aziendali dell'organizzazione.

|Chiedersi|Azione |
|:------------|:-------|
| L'organizzazione ha bisogno di operatori automatici? | Per altre informazioni, vedere [cosa sono gli operatori automatici di cloud](what-are-phone-system-auto-attendants.md) e [configurare un operatore automatico cloud](create-a-phone-system-auto-attendant.md). |

### <a name="devices"></a>Dispositivi

Per altre informazioni sui dispositivi supportati, vedere quanto segue:

- [Gestire i dispositivi in Microsoft Teams](devices/device-management.md)
- [Telefoni IP](https://docs.microsoft.com/skypeforbusiness/certification/devices-ip-phones?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [Dispositivi video e audio USB](https://docs.microsoft.com/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [Comunicazioni intelligenti per i dispositivi](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)



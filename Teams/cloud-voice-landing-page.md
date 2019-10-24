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
f1keywords:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
search.appverid: MET150
description: Pagina di destinazione per la distribuzione di cloud Voice in teams
appliesto:
- Microsoft Teams
ms.openlocfilehash: f60159d2d9d65afd3837a0b48b82ac7e13b8e0df
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "37515833"
---
# <a name="cloud-voice-in-microsoft-teams"></a>Cloud Voice in Microsoft Teams

È stato completato per [iniziare](get-started-with-teams-quick-start.md). Sono stati distribuiti team con [chat, team, canali, & app](deploy-chat-teams-channels-microsoft-teams-landing-page.md) in tutta l'organizzazione. Forse hai distribuito [riunioni & conferenze](deploy-meetings-microsoft-teams-landing-page.md). Ora si è pronti ad aggiungere funzionalità di cloud Voice per gli utenti. 

Cloud Voice offre funzionalità PBX (Private Branch Exchange) e opzioni per la connessione alla rete PSTN (Public Switched Telephone Network).

Questo articolo consente di decidere se è necessario modificare le impostazioni vocali predefinite del cloud, in base al profilo dell'organizzazione e ai requisiti aziendali, quindi illustra ogni modifica. Le impostazioni sono suddivise in due gruppi, a partire dal set di [modifiche che è più probabile apportare](#core-deployment-decisions). Il secondo gruppo include le [Impostazioni aggiuntive](#additional-deployment-decisions) che è consigliabile configurare in base alle esigenze dell'organizzazione.

È consigliabile che tutte le organizzazioni funzionino tramite le decisioni principali e quindi, se l'organizzazione ha requisiti aggiuntivi, esaminare il materiale seguente.



## <a name="learn-more-about-cloud-voice"></a>Leggi altre informazioni su cloud Voice

Gli articoli seguenti includono ulteriori informazioni sulla distribuzione e l'uso delle funzionalità vocali cloud in teams:

- [Sistema telefonico di Office 365](what-is-phone-system-in-office-365.md)
- [Sistema telefonico con piani di chiamata](calling-plan-landing-page.md)
- [Routing diretto del sistema telefonico](direct-routing-landing-page.md)
- [Distribuzione di cloud Voice](cloud-voice-deployment.md)
- [Soluzioni per la telefonia Microsoft](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions)
- Per altre informazioni sul sistema telefonico, vedere la sessione seguente: [Introduzione al sistema telefonico in Microsoft teams](https://aka.ms/teams-phone-system)


## <a name="core-deployment-decisions"></a>Decisioni di distribuzione principali

Queste sono le impostazioni che la maggior parte delle organizzazioni vuole modificare (se le impostazioni predefinite di teams non funzionano per l'organizzazione).

## <a name="phone-system-office-365"></a>Sistema telefonico (Office 365)

Sistema telefonico è la tecnologia Microsoft per abilitare il controllo delle chiamate e le funzionalità del PBX (Private Branch Exchange) nel cloud di Office 365. Sistema telefonico consente di sostituire il sistema PBX (Private Branch Exchange) esistente con un set di caratteristiche direttamente recapitate da Office 365 e strettamente integrate nell'esperienza di produttività del cloud aziendale.


|Chiedi a te stesso|Azione |
|:------------|:-------|
|In quali sedi utente o uffici verrà implementato il sistema telefonico? |Per altre informazioni sul sistema telefonico, vedere [cos'è il sistema telefonico in Office 365](what-is-phone-system-in-office-365.md).</li></ul>|
|||

## <a name="connection-to-the-public-switched-telephone-network-pstn"></a>Connessione alla rete PSTN (Public Switched Telephone Network)

Per connettere il sistema telefonico alla rete PSTN (Public Switched Telephone Network) in modo che gli utenti possano effettuare telefonate in tutto il mondo, sono disponibili opzioni in base alle esigenze aziendali.  Porsi le operazioni seguenti:


|Chiedi a te stesso|Azione |
| :------------|:-------|
| Si vuole usare Microsoft Calling Plan come gestore di telefonia? | Per altre informazioni, Vedi [sistema telefonico con piani di chiamata](calling-plan-landing-page.md).|
| È necessario usare il proprio gestore di telefonia? | Per altre informazioni, Vedi [sistema telefonico con routing diretto](direct-routing-landing-page.md).
|||


## <a name="additional-deployment-decisions"></a>Altre decisioni di distribuzione

Potrebbe essere necessario modificare le impostazioni per le seguenti, in base alle esigenze e alla configurazione dell'organizzazione:

- Casella vocale
- Chiamata dell'identità
- Numeri di telefono da Microsoft
- Dial plan
- Code di chiamata
- Operatori automatici

### <a name="voicemail"></a>Casella vocale

Cloud voicemail, alimentato da servizi di Azure voicemail, supporta i depositi della segreteria telefonica solo alle cassette postali di Exchange e non supporta sistemi di posta elettronica di terze parti. Cloud Voicemail include la trascrizione della segreteria telefonica, che è abilitata per tutti gli utenti dell'organizzazione per impostazione predefinita. Le esigenze aziendali potrebbero richiedere la disattivazione della trascrizione della segreteria telefonica per utenti specifici o tutti nell'organizzazione.

|Chiedi a te stesso|Azione |
|:------------|:-------|
| Si vuole abilitare la segreteria telefonica cloud? | Per le procedure di configurazione della segreteria telefonica, vedere [configurare la segreteria telefonica cloud](set-up-phone-system-voicemail.md).
| Si vuole abilitare la trascrizione della segreteria telefonica per alcuni o tutti gli utenti? | Per disattivare la trascrizione della segreteria telefonica, vedere [impostazione di criteri per la segreteria telefonica nell'organizzazione](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</li></ul>|
|||

### <a name="calling-identity"></a>Chiamata dell'identità

Per impostazione predefinita, tutte le chiamate in uscita usano il numero di telefono assegnato come identità di chiamata (ID chiamante). Il destinatario della chiamata può identificare rapidamente il chiamante e decidere se accettare o rifiutare la chiamata.

|Chiedi a te stesso|Azione |
|:------------|:-------|
|Si vuole mascherare o disabilitare l'ID chiamante? | Per modificare o bloccare l'ID chiamante, vedere [impostare l'ID chiamante per un utente](set-the-caller-id-for-a-user.md). |
|||

### <a name="phone-numbers-from-microsoft"></a>Numeri di telefono da Microsoft

Microsoft ha due tipi di numeri di telefono disponibili: i numeri di *abbonato* (utente), che possono essere assegnati agli utenti dell'organizzazione e i numeri di *servizio* , disponibili come numeri di servizio a pedaggio e a numero verde, che hanno una chiamata simultanea più alta capacità rispetto ai numeri di abbonato e può essere assegnata a servizi come audioconferenza, operatori automatici o code di chiamata.

|Chiedi a te stesso|Azione |
| :------------|:-------|
| Quali posizioni utente richiedono nuovi numeri di telefono da Microsoft? | Per informazioni su come ottenere i numeri di telefono, vedere [gestire i numeri di telefono per l'organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) e [ottenere i numeri di telefono per gli utenti](getting-phone-numbers-for-your-users.md). 
| Quale tipo di numero di telefono (abbonato o servizio) è necessario? | Per selezionare il tipo di numero di telefono necessario, vedere i [diversi tipi di numeri di telefono usati per chiamare i piani](different-kinds-of-phone-numbers-used-for-calling-plans.md).
Come si trasferiscono I numeri di telefono esistenti in Office 365?|Per altre informazioni, vedere [trasferire i numeri di telefono in Office 365](transfer-phone-numbers-to-office-365.md).
|||

### <a name="dial-plans"></a>Dial plan

Un dial plan nella caratteristica sistema telefonico di Office 365 è un set di regole di normalizzazione che traducono i numeri di telefono composti in un formato alternativo (in genere E. 164) per l'autorizzazione alle chiamate e il routing delle chiamate.

Per altre informazioni sui dial plan, vedere [cosa sono i dial plan?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)

|Chiedi a te stesso|Azione |
|:------------|:-------|
| L'organizzazione ha bisogno di un dial plan personalizzato? | Per determinare se è necessario un piano di chiamata personalizzato, vedere [pianificazione per i piani di chiamata del tenant](what-are-dial-plans.md#planning-for-tenant-dial-plans)|
Quali utenti richiedono un dial plan personalizzato e quale piano di dial tenant deve essere assegnato a ogni utente? | Per aggiungere utenti a un dial plan personalizzato in PowerShell, vedere [creare e gestire piani di chiamata](create-and-manage-dial-plans.md). |
|||

### <a name="call-queues"></a>Code di chiamata

Le code delle chiamate Cloud includono i messaggi di saluto usati quando qualcuno chiama un numero di telefono per l'organizzazione, la possibilità di inserire automaticamente le chiamate in attesa e la possibilità di cercare il successivo agente di chiamata disponibile per gestire la chiamata mentre le persone che chiamano sono ascolto della musica in attesa. È possibile creare code di chiamata singole o multiple per l'organizzazione. 


|Chiedi a te stesso|Azione |
|:------------|:-------|
| L'organizzazione ha bisogno delle code di chiamata? | Per altre informazioni, vedere [creare una coda di chiamata cloud](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) e [configurare il sistema telefonico](setting-up-your-phone-system.md). |

### <a name="auto-attendants"></a>Operatori automatici

Gli operatori automatici cloud possono essere usati per creare un sistema di menu per l'organizzazione che consente ai chiamanti esterni e interni di spostarsi in un sistema di menu per individuare e trasferire le chiamate agli utenti o ai reparti aziendali dell'organizzazione.

|Chiedi a te stesso|Azione |
|:------------|:-------|
| L'organizzazione ha bisogno di operatori automatici? | Per altre informazioni, vedere [cosa sono gli operatori automatici di cloud](what-are-phone-system-auto-attendants.md) e [configurare un operatore automatico cloud](create-a-phone-system-auto-attendant.md). |

### <a name="devices"></a>Dispositivi

Per altre informazioni sui dispositivi supportati, vedere quanto segue:

- [Gestire i dispositivi in Microsoft Teams](device-management.md)
- [Telefoni IP](https://docs.microsoft.com/en-us/skypeforbusiness/certification/devices-ip-phones?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [Dispositivi audio e video USB](https://docs.microsoft.com/en-us/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [Comunicazioni intelligenti per i dispositivi](https://products.office.com/en-gb/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)



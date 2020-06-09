---
title: Vantaggi offerti dal Sistema telefonico
ms.reviewer: ''
author: CarolynRowe
ms.author: crowe
manager: serdars
msreviewer: jastarck, makolomi
ms.topic: conceptual
ms.assetid: bc9756d1-8a2f-42c4-98f6-afb17c29231c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: "Informazioni sulle caratteristiche, la disponibilità e su come pianificare e configurare il sistema telefonico Microsoft per l'azienda. "
ms.openlocfilehash: fa7acbd4593b44805b2f9044602f3521baacaaaf
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "44638345"
---
# <a name="heres-what-you-get-with-phone-system"></a>Vantaggi offerti dal Sistema telefonico

Questo articolo descrive le caratteristiche del sistema telefonico. Per altre informazioni sull'uso del sistema telefonico come sostituzione del PBX (Private Branch Exchange) e sulle opzioni per la connessione alla rete PSTN (Public Switched Telephone Network), vedere [cos'è il sistema telefonico](what-is-phone-system-in-office-365.md).

I client sono disponibili per PC, Mac e dispositivi mobili, che offrono funzionalità su dispositivi da tablet e telefoni cellulari a PC e telefoni IP desktop. Per altre informazioni, vedere [ottenere client per Microsoft teams](get-clients.md).

  
## <a name="phone-system-features"></a>Caratteristiche del sistema telefonico

Il sistema telefonico offre le caratteristiche seguenti. Se non diversamente specificato, le funzionalità sono disponibili sia in team che in Skype for business online.
  
|||
|:-----|:-----|
|**Funzionalità sistema telefonico** <br/> |**Descrizione** <br/> |
|[Operatori automatici cloud](what-are-phone-system-auto-attendants.md) <br/> |Consente di creare un sistema di menu che consente ai chiamanti esterni e interni di individuare e inserire o trasferire le chiamate agli utenti o ai reparti aziendali dell'organizzazione.  <br/> |
|[Code di chiamate cloud](create-a-phone-system-call-queue.md) <br/> |Consente di configurare la modalità di gestione delle code di chiamata per l'organizzazione: ad esempio, configurare i messaggi di saluto e la musica in attesa, cercare l'agente di chiamata disponibile successivo per gestire la chiamata e così via.  <br/> |
|Musica in attesa | Riproduce la musica predefinita definita dal servizio quando una chiamata esterna proveniente dalla rete PSTN (Public Switched Telephone Network) viene inserita in attesa. Questa funzionalità è compatibile con chiamate da PSTN a team da uno a uno oltre alle chiamate effettuate in una coda di chiamata. Questa caratteristica offre una parità di notifica in attesa con altre piattaforme. Questa caratteristica è configurabile dall'amministratore, ma [attualmente solo tramite PowerShell](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps). Anche la musica di blocco non è supportata nel trasferimento consultivo di una chiamata PSTN.|
|Rispondere alla chiamata/avviamento (per nome e numero)  <br/> |Consente agli utenti di rispondere alle chiamate in ingresso con un tocco e di inserire chiamate in uscita effettuando la chiamata al numero di telefono completo o facendo clic su un nome nel client.  <br/> |
|[Opzioni di inoltro di chiamata e squillo simultaneo](https://support.office.com/article/call-forwarding-call-groups-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) <br/> |Consente agli utenti di impostare regole di inoltro in modo che le chiamate possano andare ovunque o le chiamate possano essere inoltrate ai colleghi o alla segreteria telefonica.  <br/> |
|[Raccolta di chiamate di gruppo e inoltro al gruppo](call-sharing-and-group-call-pickup.md) <br/> | Consente agli utenti di condividere le chiamate in arrivo con i colleghi in modo che i colleghi possano rispondere alle chiamate che si verificano quando l'utente non è disponibile. Meno distruttivo per i destinatari rispetto ad altre forme di condivisione delle chiamate, ad esempio l'inoltro di chiamata o lo squillo simultaneo, perché gli utenti possono configurare il modo in cui vogliono ricevere una chiamata condivisa in arrivo. |
|[Trasferire una chiamata e un trasferimento consultivo](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0) <br/> |Consente agli utenti di trasferire le chiamate a un'altra persona. Oppure, se hanno bisogno di uscire dall'ufficio, ma vogliono continuare la conversazione, possono trasferire le chiamate dal PC o dal telefono IP al cellulare.  <br/> |
|[Trasferimento alla segreteria telefonica a metà chiamata](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0) <br/> | Consente agli utenti di trasferirsi alla segreteria telefonica durante una chiamata. |
|[Parcheggio di chiamata e recupero](call-park-and-retrieve.md)  <br/> | Consente agli utenti di effettuare una chiamata in attesa nel servizio Teams nel cloud. Quando una chiamata viene parcheggiata, il servizio genera un codice univoco per il recupero delle chiamate. L'utente che ha parcheggiato la chiamata o qualcun altro può quindi usare il codice e un'app o un dispositivo supportato per recuperare la chiamata. <br/> |
|Chiamare il numero di telefono dalla ricerca  <br/> | Consente agli utenti di effettuare una chiamata dalla casella di ricerca usando il comando/call e specificando un nome o un numero. <br/> |
|[ID chiamante](how-can-caller-id-be-used-in-your-organization.md)  <br/> |Le chiamate dall'interno della società visualizzano un ID chiamante dettagliato che estrae le informazioni dalla directory aziendale, mostrando l'ID immagine e il titolo del lavoro anziché solo un numero di telefono. Per le chiamate da numeri di telefono esterni, viene visualizzato l'ID chiamante fornito dal provider di servizi telefonici. Se i numeri di telefono esterni sono numeri secondari nella directory aziendale, verranno visualizzate le informazioni della directory aziendale.  <br/> |
|Commutazione di dispositivo  <br/> |Consente agli utenti di effettuare una chiamata o una riunione su un altro dispositivo HID connesso a teams; ad esempio, passando dagli altoparlanti del PC a un auricolare.   <br/> |
|Routing delle chiamate basato sulla presenza <br/> |Controlla le comunicazioni in ingresso con la presenza, consentendo all'utente di bloccare tutte le comunicazioni in arrivo eccetto quelle indicate in modo specifico.  <br/> |
|[Tastiera del telefono integrata](https://support.office.com/article/use-the-dial-pad-in-teams-27bc60b5-74c0-4e9c-808b-da4db9514d89) <br/> | Consente agli utenti di effettuare una chiamata per nome o per numero in qualsiasi punto della barra di ricerca e nella tastiera del telefono, velocizzando il processo di esecuzione delle chiamate in uscita. <br/> |
|Chiamate federate  <br/> |Consente agli utenti di connettersi, comunicare e collaborare in modo sicuro con gli utenti di tenant federati.  <br/> |
|[Effettuare e ricevere una videochiamata](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42) <br/> | Se l'account dell'utente è abilitato per le videochiamate, l'utente può effettuare chiamate video faccia a faccia con i propri contatti. Tutto ciò che serve è una fotocamera, gli altoparlanti del computer e il microfono. Gli utenti possono anche usare un auricolare se il computer in uso non ha un dispositivo audio incorporato.<br/> |
|[Segreteria telefonica cloud](set-up-phone-system-voicemail.md) <br/> | Quando un utente riceve un messaggio vocale, viene recapitato alla cassetta postale di Exchange come messaggio di posta elettronica con la segreteria telefonica come allegato. Gli utenti possono ascoltare i loro messaggi nel telefono desktop certificato e in tutti i team o le applicazioni Skype for business. Il supporto per la trascrizione segreteria telefonica è stato aggiunto a partire da marzo 2017 ed è attivato per impostazione predefinita per tutte le organizzazioni e gli utenti.   <br/> |
|[Impostazioni utente di cloud Voicemail](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US) <br/> | Consente agli utenti di configurare le impostazioni del client per i saluti della segreteria telefonica, le regole di risposta alle chiamate e la lingua di saluto, inclusi i saluti fuori sede.   |
|[Suoneria secondaria](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f) <br/> | Gli utenti che dispongono di più dispositivi altoparlante collegati al PC possono scegliere di impostare un dispositivo secondario su cui squillare oltre al relativo altoparlante predefinito. Ad esempio, un utente con un auricolare collegato al PC e agli altoparlanti da tavolo può scegliere di far squillare sia l'auricolare che gli altoparlanti da tavolo quando viene inserita una chiamata, in modo da non perdere una chiamata.  |
|[Avvisi Ring distintivi](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f) (solo Teams)<br/> |Consente agli utenti di scegliere le suonerie separate per le chiamate normali, le chiamate inoltrate e le chiamate Delegate in modo che possano distinguere il tipo di chiamata.  <br/> |
|[Modalità di linea condivisa](shared-line-appearance.md) <br/> | Consente agli utenti di condividere la propria linea telefonica in modo che un altro utente possa effettuare e ricevere chiamate per proprio conto.|
|[Occupato su occupato](teams-calling-policy.md) (solo Teams) <br/> | Un criterio di chiamata che consente di configurare il modo in cui vengono gestite le chiamate in arrivo quando un utente è già in una chiamata o una conferenza o ha una chiamata in attesa. Il chiamante sentirà un segnale di occupato quando il chiamato è già sul telefono. Il chiamato riceve una notifica di chiamata senza risposta ma non è in grado di rispondere alle chiamate in arrivo. Questa caratteristica è disabilitata per impostazione predefinita, ma può essere attivata dall'amministratore del tenant. |
|[Blocco delle chiamate](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US) <br/> | Consente agli utenti di aggiungere numeri di telefono PSTN a un elenco bloccato in modo che la chiamata successiva da tale numero venga bloccata dall'utente.|
|[Telefoni per area comune](set-up-common-area-phones.md) <br/> | Un telefono con area comune viene in genere posizionato in un'area come una sala riunioni o conferenza che la rende disponibile a più persone. I telefoni delle aree comuni sono configurati come dispositivi anziché utenti e possono accedere automaticamente a una rete.|
|[Supporto per il bypass multimediale](direct-routing-plan-media-bypass.md) (solo per i team di routing diretto) <br/> | Per migliorare le prestazioni, i contenuti multimediali vengono mantenuti tra session border controller (SBC) e il client invece di inviarlo tramite il sistema telefonico Microsoft. |


## <a name="availability-in-gcc-high-and-dod-clouds"></a>Disponibilità nelle nubi di GCC High e DoD
<a name="bkmk_setup"> </a>

Le funzionalità seguenti non sono ancora disponibili nelle nubi di GCC High e DoD. 
- [Impostazioni delle chiamate per suonerie secondarie, segreteria telefonica e delega avanzata](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)
- [Trasferimento alla segreteria telefonica a metà chiamata](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)
- Chiamare il numero di telefono dalla barra di ricerca
- Musica in attesa
- Ricerca di numeri inversa di Azure AD

## <a name="related-topics"></a>Argomenti correlati

- [Che cos'è Sistema telefonico](what-is-phone-system-in-office-365.md)
- [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md)
- [Configurare Sistema telefonico](setting-up-your-phone-system.md)
- [Qual è il piano di chiamata adatto alle proprie esigenze?](calling-plan-landing-page.md)
- [Instradamento diretto di Sistema telefonico](direct-routing-landing-page.md)
- [Monitorare e gestire la qualità delle chiamate](monitor-call-quality-qos.md)
- [Licenze per i componenti aggiuntivi di Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Tariffe del Sistema telefonico](https://products.office.com/microsoft-teams/voice-calling#requirements)
- [Team per l'infrastruttura desktop virtualizzata con le chiamate e le riunioni](teams-for-vdi.md#teams-on-vdi-with-calling-and-meetings)

  
 

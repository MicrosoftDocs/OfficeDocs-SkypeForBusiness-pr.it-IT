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
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 'Scopri le funzionalità, la disponibilità e come pianificare e configurare il Sistema telefonico Microsoft per la tua azienda. '
ms.openlocfilehash: b3a3da0a2cfd8038b3af84352c754c9014a1ad6c
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030402"
---
# <a name="heres-what-you-get-with-phone-system"></a>Vantaggi offerti dal Sistema telefonico

Questo articolo descrive le funzionalità del Sistema telefonico. Per altre informazioni sull'uso di Sistema telefonico come sostituzione PBX (Private Branch Exchange) e sulle opzioni per la connessione alla rete PSTN (Public Switched Telephone Network), vedere Che cos'è [il sistema telefonico.](what-is-phone-system-in-office-365.md)

Sono disponibili client per PC, Mac e dispositivi mobili, che forniscono funzionalità su dispositivi da tablet e cellulari a PC e telefoni IP desktop. Per altre informazioni, vedere [Ottenere i clienti per Microsoft Teams.](get-clients.md)

 > [!Note]
> Per i dettagli sui sistemi telefonici Teams su piattaforme diverse, vedi le [funzionalità di Teams per piattaforma.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)
  
## <a name="phone-system-features"></a>Funzionalità sistema telefonico

Sistema telefonico offre le seguenti funzionalità. Se non diversamente specificato, le funzionalità sono disponibili sia in Teams che in Skype for Business online.
  
|||
|:-----|:-----|
|**Funzionalità Sistema telefonico** <br/> |**Descrizione** <br/> |
|[Operatori automatici cloud](what-are-phone-system-auto-attendants.md) <br/> |Consente di creare un sistema di menu che consente ai chiamanti esterni e interni di individuare ed effettuare o trasferire chiamate a reparti o utenti aziendali dell'organizzazione.  <br/> |
|[Code di chiamata cloud](create-a-phone-system-call-queue.md) <br/> |Consente di configurare la modalità di gestione delle code di chiamata per l'organizzazione: ad esempio, impostare saluti e musica di attesa, cercare il successivo agente di chiamata disponibile per gestire la chiamata e così via.  <br/> |
|Musica blocco | Riproduce musica predefinita definita dal servizio quando una chiamata esterna dalla rete PSTN (Public Switched Telephone Network) viene messa in attesa. Questa funzione funziona per le chiamate pstn-to-teams uno-a-uno, oltre alle chiamate effettuate in una coda di chiamata. Questa funzionalità offre la parità delle notifiche di blocco con altre piattaforme. Questa caratteristica può essere configurata dall'amministratore, [ma al momento solo tramite PowerShell.](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps) La musica in attesa non è supportata anche nel trasferimento consultivo di una chiamata PSTN.|
|Risposta/avvio chiamata (per nome e numero)  <br/> |Consente agli utenti di rispondere alle chiamate in entrata con un tocco ed effettuare chiamate in uscita componendo il numero telefonico completo o facendo clic su un nome nel client.  <br/> |
|[Opzioni di inoltro di chiamata e squillo simultaneo](https://support.office.com/article/call-forwarding-call-groups-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) <br/> |Consente agli utenti di configurare regole di inoltro in modo che le chiamate possano essere effettuate ovunque o le chiamate possono essere inoltrate ai colleghi o alla segreteria telefonica.  <br/> |
|[Ritiro chiamata di gruppo e inoltro al gruppo](call-sharing-and-group-call-pickup.md) <br/> | Consente agli utenti di condividere le chiamate in arrivo con i colleghi in modo che i colleghi possano rispondere alle chiamate che si verificano quando l'utente non è disponibile. Meno disturbante per i destinatari rispetto ad altre forme di condivisione delle chiamate (come l'inoltro di chiamata o lo squillo simultaneo), perché gli utenti possono configurare la modalità di notifica di una chiamata condivisa in arrivo. |
|[Trasferire una chiamata e un trasferimento consultivo](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0) <br/> |Consente agli utenti di trasferire le chiamate a un'altra persona. Oppure, se deve lasciare l'ufficio ma vuole continuare la conversazione, può trasferire le chiamate dal PC o dal telefono IP al cellulare.  <br/> |
|[Trasferimento alla segreteria telefonica durante la chiamata](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0) <br/> | Consente agli utenti di trasferirsi alla segreteria telefonica durante una chiamata. |
|[Parcheggio di chiamata e recupero](call-park-and-retrieve.md)  <br/> | Consente agli utenti di mettere una chiamata in attesa nel servizio Teams nel cloud. Quando una chiamata è in stato di esecuzione, il servizio genera un codice univoco per il recupero delle chiamate. L'utente che ha parcheggiato la chiamata o qualcun altro potrà quindi usare quel codice e un'app o un dispositivo supportato per recuperare la chiamata. <br/> |
|Chiama il numero di telefono dalla ricerca  <br/> | Consente agli utenti di effettuare una chiamata dalla casella di ricerca utilizzando il comando /call e specificando un nome o un numero. <br/> |
|[ID chiamante](how-can-caller-id-be-used-in-your-organization.md)  <br/> |Le chiamate dall'interno della società mostrano un ID chiamante dettagliato che estrae informazioni dall'elenco aziendale, mostrando l'ID immagine e la posizione invece di un semplice numero di telefono. Per le chiamate da numeri di telefono esterni, viene visualizzato l'ID chiamante fornito dal provider di servizi telefonici. Se i numeri di telefono esterni sono numeri secondari nella directory aziendale, verranno visualizzate le informazioni della directory aziendale.  <br/> |
|Cambio di dispositivo  <br/> |Consente agli utenti di riprodurre una chiamata o una riunione in un altro dispositivo HID connesso a Teams; ad esempio il passaggio dagli altoparlanti del PC a un auricolare.   <br/> |
|Routing delle chiamate basato sulla presenza <br/> |Controlla le comunicazioni in ingresso con la presenza, consentendo all'utente di bloccare tutte le comunicazioni in arrivo tranne quelle specificamente indicate.  <br/> |
|[Tastiera integrata](https://support.office.com/article/use-the-dial-pad-in-teams-27bc60b5-74c0-4e9c-808b-da4db9514d89) <br/> | Consente agli utenti di chiamare per nome o per numero in qualsiasi punto della barra di ricerca e della tastiera del telefono, velocizzando il processo di chiamata in uscita. <br/> |
|Chiamate federate  <br/> |Consente agli utenti di connettersi, comunicare e collaborare in modo sicuro con gli utenti in tenant federati.  <br/> |
|[Effettuare e ricevere una videochiamata](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42) <br/> | Se l'account utente è abilitato per le videochiamate, l'utente può effettuare videochiamate faccia a faccia con i propri contatti. Tutto ciò di cui hanno bisogno sono una fotocamera, gli altoparlanti e il microfono del computer. Gli utenti possono usare un auricolare anche se il computer non ha un dispositivo audio incorporato.<br/> |
|[Segreteria telefonica cloud](set-up-phone-system-voicemail.md) <br/> | Quando un utente riceve un messaggio della segreteria telefonica, viene recapitato alla cassetta postale di Exchange come allegato con il messaggio della segreteria telefonica. Gli utenti possono ascoltare i messaggi sul telefono desktop certificato e su tutte le applicazioni Teams o Skype for Business. Il supporto per la trascrizione segreteria telefonica è stato aggiunto a partire da marzo 2017 ed è attivato per impostazione predefinita per tutte le organizzazioni e gli utenti.   <br/> |
|[Impostazioni utente segreteria telefonica cloud](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US) <br/> | Consente agli utenti di configurare le impostazioni client per i messaggi di saluto della segreteria telefonica, le regole di risposta alle chiamate e la lingua del saluto, inclusi i saluti fuori sede.   |
|[Suoneria secondaria](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f) <br/> | Gli utenti con più dispositivi altoparlanti collegati al PC possono scegliere di impostare uno squillo secondario in aggiunta all'altoparlante predefinito. Ad esempio, un utente con un auricolare collegato al PC e agli altoparlanti da tavolo può scegliere di avere sia l'auricolare che gli altoparlanti da tavolo squillano quando arriva una chiamata per non perdere una chiamata.  |
|[Avvisi suoneria distintivi](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f) (solo Teams)<br/> |Consente agli utenti di scegliere suonerie separate per chiamate normali, chiamate inoltrate e chiamate delegate in modo da distinguere il tipo di chiamata.  <br/> |
|[Modalità di linea condivisa](shared-line-appearance.md) <br/> | Consente agli utenti di condividere la linea telefonica in modo che un altro utente possa effettuare e ricevere chiamate per proprio conto.|
|[Occupato in Occupato](teams-calling-policy.md) (solo Teams) <br/> | Un criterio di chiamata che consente di configurare la modalità di gestione delle chiamate in arrivo quando un utente è già in conferenza o è già in attesa di una chiamata. Il chiamante sentirà un segnale di occupato quando il chiamato è già sul telefono. Il destinatario riceve una notifica di chiamata senza risposta, ma non è in grado di rispondere alle chiamate in arrivo. Questa funzionalità è disabilitata per impostazione predefinita, ma può essere attivata dall'amministratore del tenant. |
|[Blocco delle chiamate](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US) <br/> | Consente agli utenti di aggiungere numeri di telefono (PSTN) a un elenco di indirizzi bloccati in modo da bloccare lo squillo alla chiamata successiva da quel numero.|
|[Telefoni dell'area comune](set-up-common-area-phones.md) <br/> | Un telefono da area comune viene in genere inserito in un'area come una sala d'attesa o una sala riunioni, rendendolo disponibile a più persone. I telefoni dell'area comune sono impostati come dispositivi anziché come utenti e possono accedere automaticamente a una rete.|
|[Supporto del bypass multimediale](direct-routing-plan-media-bypass.md) (solo per l'instradamento diretto di Teams) <br/> | Per prestazioni migliori, gli elementi multimediali vengono mantenuti tra il controller dei confini della sessione (SBC) e il client invece di inviarli tramite il Sistema telefonico Microsoft. |


## <a name="availability-in-gcc-high-and-dod-clouds"></a>Disponibilità nei cloud GCC High e DoD
<a name="bkmk_setup"> </a>

Le funzionalità seguenti non sono ancora disponibili nei cloud GCC High e DoD. 
- [Impostazioni delle chiamate per suoneria secondaria, segreteria telefonica e delega avanzata](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)
- [Trasferimento alla segreteria telefonica durante la chiamata](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)
- Chiamare il numero di telefono dalla barra di ricerca
- Musica blocco
- Ricerca inversa dei numeri di Azure AD

## <a name="related-topics"></a>Argomenti correlati

- [Che cos'è Sistema telefonico](what-is-phone-system-in-office-365.md)
- [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md)
- [Configurare Sistema telefonico](setting-up-your-phone-system.md)
- [Qual è il piano di chiamata adatto alle proprie esigenze?](calling-plan-landing-page.md)
- [Instradamento diretto di Sistema telefonico](direct-routing-landing-page.md)
- [Monitorare e gestire la qualità delle chiamate](monitor-call-quality-qos.md)
- [Licenze per i componenti aggiuntivi di Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
- [Tariffe del Sistema telefonico](https://products.office.com/microsoft-teams/voice-calling#requirements)
- [Teams per Virtualized Desktop Infrastructure con chiamate e riunioni](teams-for-vdi.md#teams-on-vdi-with-calling-and-meetings)

  
 

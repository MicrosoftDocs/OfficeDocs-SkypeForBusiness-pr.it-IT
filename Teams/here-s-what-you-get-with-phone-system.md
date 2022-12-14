---
title: Vantaggi offerti dal Sistema telefonico
ms.reviewer: ''
author: CarolynRowe
ms.author: crowe
manager: serdars
msreviewer: jastarck, roykuntz
ms.topic: conceptual
ms.assetid: bc9756d1-8a2f-42c4-98f6-afb17c29231c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: "Informazioni su funzionalità, disponibilità e su come pianificare e configurare Sistema telefonico Microsoft per l'azienda. "
ms.openlocfilehash: 118f2d52193583149e881bf564fb1df616bf108c
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392246"
---
# <a name="heres-what-you-get-with-phone-system"></a>Vantaggi offerti dal Sistema telefonico

Questo articolo descrive le funzionalità di Sistema telefonico. Per ulteriori informazioni sull'uso di Sistema telefonico come sostituzione PBX (Private Branch Exchange) e sulle opzioni per la connessione alla rete PSTN (Public Switched Telephone Network), vedi [Che cos'è il sistema telefonico](what-is-phone-system-in-office-365.md).

I client sono disponibili per PC, Mac e dispositivi mobili, che offrono funzionalità sui dispositivi da tablet e telefoni cellulari a PC e telefoni IP desktop. Per altre informazioni, vedere [Ottenere client per Microsoft Teams](get-clients.md).

 > [!Note]
> Per informazioni dettagliate sui sistemi telefonici Teams su piattaforme diverse, vedere [Funzionalità di Teams per piattaforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

Per usare le funzionalità di Sistema telefonico, l'organizzazione deve avere una licenza Sistema telefonico. Per altre informazioni sulle licenze, vedere [Licenze per i componenti aggiuntivi di Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

Tenere presente che la maggior parte delle funzionalità richiede l'assegnazione della licenza Sistema telefonico e la garanzia che gli utenti siano "abilitati per i comandi vocali". Per assegnare la licenza, usa il [cmdlet Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment?view=teams-ps) e imposta il parametro **EnterpriseVoiceEnabled** su $true. Alcune funzionalità, come l'operatore automatico cloud, non richiedono che un utente sia abilitato alla voce. Le eccezioni sono indicate nella tabella seguente.
  
## <a name="phone-system-features"></a>Funzionalità sistema telefonico

Sistema telefonico fornisce le seguenti funzionalità.
  
|Funzionalità Sistema telefonico  |Descrizione |
|:-----|:-----|
|[Operatori automatici cloud](what-are-phone-system-auto-attendants.md)  |Consente di creare un sistema di menu che consente ai chiamanti esterni e interni di individuare ed effettuare o trasferire chiamate a utenti o reparti aziendali dell'organizzazione.  <br/> Si noti che gli utenti *non* devono essere abilitati alla voce per ricevere chiamate dall'operatore automatico chiamata per nome, chiamata per numero di ricerca directory. *Gli utenti* devono essere abilitati alla voce per ricevere chiamate dalle opzioni di menu dell'operatore automatico. |
|[Code di chiamata cloud](create-a-phone-system-call-queue.md) <br> |Consente di configurare la modalità di gestione delle code di chiamata per l'organizzazione: ad esempio, configurare i messaggi di saluto e la musica in attesa, cercare il successivo agente di chiamata disponibile per gestire la chiamata e così via.  <br/> Si noti *che gli utenti* devono essere abilitati per ricevere chiamate da una coda di chiamata.|
|[Musica in attesa](music-on-hold.md) | Riproduce musica predefinita definita dal servizio o musica personalizzata caricata dall'amministratore tenant quando viene messa in attesa una chiamata esterna dalla rete PSTN (Public Switched Telephone Network). Questa funzionalità funziona per le chiamate PSTN-to-Teams uno-a-uno oltre alle chiamate effettuate a una coda di chiamata. Questa funzionalità fornisce la parità delle notifiche di blocco con altre piattaforme. |
|Risposta/avvio chiamata (per nome e numero)   |Consente agli utenti di rispondere alle chiamate in ingresso con un tocco ed effettuare chiamate in uscita componendo il numero di telefono completo o facendo clic su un nome nel client.   |
|[Opzioni di inoltro di chiamata e squillo simultaneo](https://support.office.com/article/call-forwarding-call-groups-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)  |Consente agli utenti di configurare regole di inoltro in modo che le chiamate possano essere effettuate ovunque oppure inoltrate ai colleghi o alla segreteria telefonica.   |
|[Ritiro e inoltro di chiamata di gruppo al gruppo](call-sharing-and-group-call-pickup.md)  | Consente agli utenti di condividere le chiamate in arrivo con i colleghi in modo che possano rispondere alle chiamate che si verificano quando l'utente non è disponibile. Meno fastidiosi per i destinatari rispetto ad altri tipi di condivisione delle chiamate, ad esempio l'inoltro di chiamata o lo squillo simultaneo, perché gli utenti possono configurare la modalità di notifica di una chiamata condivisa in arrivo. |
|[Trasferire una chiamata e un trasferimento di consulenza](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)  |Consente agli utenti di trasferire le chiamate a un'altra persona. In alternativa, se deve uscire dall'ufficio ma vuole continuare la conversazione, può trasferire le chiamate dal PC o dal telefono IP al cellulare.  <br/> Si noti che gli utenti *non* devono essere abilitati ai comandi vocali per ricevere chiamate trasferite da un altro utente. |
|[Trasferimento alla segreteria telefonica durante una chiamata*](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)  | Consente agli utenti di trasferirsi alla segreteria telefonica durante una chiamata. |
|[Parcheggio di chiamata e recupero](call-park-and-retrieve.md)   | Consente agli utenti di mettere una chiamata in attesa nel servizio Teams nel cloud. Quando una chiamata è parcheggiata, il servizio genera un codice univoco per il recupero delle chiamate. L'utente che ha parcheggiato la chiamata o un altro utente può quindi usare tale codice e un'app o un dispositivo supportato per recuperare la chiamata.  |
|Chiamare il numero di telefono dalla ricerca   | Consente agli utenti di effettuare una chiamata dalla casella di ricerca utilizzando il comando /call e specificando un nome o un numero.  |
|[ID chiamante](how-can-caller-id-be-used-in-your-organization.md)   |Le chiamate interne all'azienda visualizzano un ID chiamante dettagliato che recupera informazioni dalla directory aziendale, mostrando l'ID immagine e la posizione lavorativa invece di un semplice numero di telefono. Per le chiamate da numeri di telefono esterni, viene visualizzato l'ID chiamante fornito dal provider di servizi telefonici. Se i numeri di telefono esterni sono numeri secondari nella directory aziendale, verranno visualizzate le informazioni della directory aziendale.   |
|Cambio di dispositivo   |Consente agli utenti di riprodurre una chiamata o una riunione su un altro dispositivo HID connesso a Teams; ad esempio passando dagli altoparlanti del PC a un auricolare.    |
|Routing delle chiamate basato sulla presenza  |Controlla le comunicazioni in ingresso con la presenza, consentendo all'utente di bloccare tutte le comunicazioni in arrivo tranne quelle specificamente indicate.   |
|[Tastiera integrata](https://support.office.com/article/use-the-dial-pad-in-teams-27bc60b5-74c0-4e9c-808b-da4db9514d89)  | Consente agli utenti di comporre per nome o numero in qualsiasi punto della barra di ricerca e nella tastiera del telefono, accelerando il processo di esecuzione delle chiamate in uscita.  |
|Chiamate federate   |Consente agli utenti di connettersi in modo sicuro, comunicare e collaborare con gli utenti nei tenant federati.   |
|[Effettuare e ricevere una videochiamata](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)  | Se l'account dell'utente è abilitato per le videochiamate, l'utente può effettuare videochiamate faccia a faccia con i propri contatti. Tutto ciò di cui hanno bisogno è una fotocamera, gli altoparlanti e il microfono del computer. Gli utenti possono anche usare un auricolare se il computer non dispone di un dispositivo audio incorporato. |
|[Cloud Voicemail](set-up-phone-system-voicemail.md)  | Quando un utente riceve un messaggio vocale, viene recapitato alla sua cassetta postale di Exchange come messaggio di posta elettronica con il messaggio della segreteria telefonica come allegato. Gli utenti possono ascoltare i messaggi sul telefono desktop certificato e su tutte le applicazioni Teams o Skype for Business. Il supporto per la trascrizione segreteria telefonica è stato aggiunto a partire da marzo 2017 ed è attivato per impostazione predefinita per tutte le organizzazioni e gli utenti. <br> Si noti che gli utenti *non* hanno bisogno di una licenza Sistema telefonico *, né* devono essere abilitati per l'uso delle funzionalità di Cloud Voicemail.    |
|[Cloud Voicemail impostazioni utente](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US)  | Consente agli utenti di configurare le impostazioni client per il messaggio di saluto della segreteria telefonica, le regole di risposta alle chiamate e la lingua del saluto, inclusi i messaggi di saluto fuori sede. <br> Si noti che gli utenti *non* hanno bisogno di una licenza Sistema telefonico *, né* devono essere abilitati per l'uso delle funzionalità di Cloud Voicemail.  |
|[Suoneria secondaria](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)  | Gli utenti con più dispositivi altoparlanti collegati al PC possono scegliere di impostare un dispositivo secondario in modo che squilli oltre all'altoparlante predefinito. Ad esempio, un utente con un auricolare collegato al PC e gli altoparlanti da tavolo può scegliere di far squillare sia l'auricolare che gli altoparlanti da tavolo quando arriva una chiamata in modo da non perdere una chiamata.  |
|[Avvisi di anello distintivi](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f) (solo Teams) |Consente agli utenti di scegliere suonerie separate per le chiamate normali, le chiamate inoltrate e le chiamate delegate in modo che possano distinguere il tipo di chiamata.   |
|[Modalità di linea condivisa](shared-line-appearance.md)  | Consente agli utenti di condividere la linea telefonica in modo che un altro utente possa effettuare e ricevere chiamate per suo conto.|
|[Occupato su Occupato](teams-calling-policy.md) (solo Teams)  | Un criterio di chiamata che consente di configurare la modalità di gestione delle chiamate in arrivo quando un utente è: <ul><li>in una chiamata </li><li>in conferenza</li><li>una chiamata messa in attesa. </li></ul> Il chiamante riceverà una delle risposte seguenti: <ul><li>ascoltare un segnale di occupato quando il destinatario della chiamata è sul telefono</li> <li>verrà instradata di conseguenza alle impostazioni senza risposta dell'utente. Un'opzione consente al chiamante di lasciare un messaggio vocale per l'utente che è già in una chiamata.</li></ul> Il destinatario riceve una notifica di chiamata senza risposta, ma non è in grado di rispondere alle chiamate in arrivo. Questa funzionalità è disabilitata per impostazione predefinita, ma può essere attivata dall'amministratore del tenant.|
|[Blocco delle chiamate](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US)  | Consente agli utenti di aggiungere numeri di telefono (PSTN) a un elenco bloccato, in modo che alla successiva chiamata da quel numero venga impedito di far squillare l'utente.|
|[Telefoni dell'area comune](set-up-common-area-phones.md)  | Un telefono dell'area comune viene in genere inserito in un'area come una sala d'attesa o una sala riunioni che lo rende disponibile a più persone. I telefoni ad area comune sono configurati come dispositivi anziché come utenti e possono accedere automaticamente a una rete.|
|[Supporto del bypass multimediale](direct-routing-plan-media-bypass.md) (solo per il routing diretto di Teams)  | Per migliorare le prestazioni, i supporti vengono mantenuti tra il controller dei confini della sessione (SBC) e il client invece di inviarli tramite sistema telefonico. |
|[Routing dei numeri non assegnati](routing-calls-to-unassigned-numbers.md) | Consente il routing di numeri non assegnati a utenti, operatori automatici, code di chiamata o un annuncio personalizzato. |

## <a name="availability-in-gcc-high-and-dod-clouds"></a>Disponibilità nei cloud GCC High e DoD
<a name="bkmk_setup"> </a>

Le funzionalità seguenti non sono ancora disponibili nei cloud GCC High e DoD. 

- [Impostazioni di chiamata per suoneria secondaria, segreteria telefonica e delega migliorata](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)
- [Trasferimento alla segreteria telefonica durante una chiamata](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)
- Chiamare il numero di telefono dalla barra di ricerca
- Musica in attesa
- Ricerca del numero inverso di Azure ACTIVE Directory

## <a name="related-topics"></a>Argomenti correlati

- [Che cos'è Sistema telefonico](what-is-phone-system-in-office-365.md)
- [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md)
- [Configurare Sistema telefonico](setting-up-your-phone-system.md)
- [Qual è il piano di chiamata adatto alle proprie esigenze?](calling-plan-landing-page.md)
- [Monitorare e gestire la qualità delle chiamate](monitor-call-quality-qos.md)
- [Licenze per i componenti aggiuntivi di Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Tariffe del Sistema telefonico](https://products.office.com/microsoft-teams/voice-calling#requirements)
- [Teams per virtualizzazione dell'infrastruttura desktop con chiamate e riunioni](teams-for-vdi.md#teams-on-vdi-with-calling-and-meetings)

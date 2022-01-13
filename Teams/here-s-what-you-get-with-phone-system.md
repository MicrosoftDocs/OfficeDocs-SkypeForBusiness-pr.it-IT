---
title: Ecco cosa si ottiene con Teams Telefono
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
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: "Informazioni sulle caratteristiche, la disponibilità e su come pianificare e configurare Microsoft Teams Sistema telefonico per l'azienda. "
ms.openlocfilehash: f396d8fc3dd1e26a2969b825c360054db91071fa
ms.sourcegitcommit: d2c76fe7705acf6e53f7673861671b1b018813dd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2022
ms.locfileid: "62015256"
---
# <a name="heres-what-you-get-with-teams-phone"></a>Ecco cosa si ottiene con Teams Telefono

Questo articolo descrive le Teams Telefono caratteristiche. Per altre informazioni sull'uso di Teams Telefono come sostituzione pbx (Private Branch Exchange) e sulle opzioni per la connessione alla rete PSTN (Public Switched Telephone Network), vedere Che cos'è [Teams Telefono](what-is-phone-system-in-office-365.md).

I client sono disponibili per PC, Mac e dispositivi mobili, che offre funzionalità su dispositivi da tablet e telefoni cellulari a PC e telefoni IP desktop. Per altre informazioni, vedere [Ottenere i client per Microsoft Teams](get-clients.md).

 > [!Note]
> Per informazioni dettagliate Teams sistemi telefonici su piattaforme diverse, vedere Teams [funzionalità per piattaforma.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)

Per usare Teams Telefono, l'organizzazione deve avere una Sistema telefonico licenza. Per altre informazioni sulle licenze, vedere [Licenze per i componenti aggiuntivi di Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

Tenere presente che per la maggior parte delle funzionalità è necessario assegnare la licenza Sistema telefonico e assicurarsi che gli utenti siano "abilitati per la voce". Per assegnare la licenza, usare il [cmdlet Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) e impostare il **parametro enterprisevoiceenabled** su $true. Alcune funzionalità, ad esempio l'operatore automatico cloud, non richiedono che un utente sia abilitato per la voce. Le eccezioni sono indicate nella tabella seguente.
  
## <a name="teams-phone-features"></a>Teams Telefono caratteristiche

Teams Telefono fornisce le caratteristiche seguenti.
  
|Teams Telefono funzionalità  |Descrizione |
|:-----|:-----|
|[Operatori automatici cloud](what-are-phone-system-auto-attendants.md)  |Consente di creare un sistema di menu che consente ai chiamanti esterni e interni di individuare e effettuare o trasferire chiamate a utenti o reparti aziendali dell'organizzazione.  <br/> Si noti che *gli utenti non devono* essere abilitati alla voce per ricevere chiamate dall'operatore automatico. |
|[Code di chiamata cloud](create-a-phone-system-call-queue.md) <br> |Consente di configurare la modalità di gestione delle code di chiamata per l'organizzazione, ad esempio configurare i messaggi di saluto e la musica in attesa, cercare il successivo agente di chiamata disponibile per gestire la chiamata e così via.  <br/> Si noti che *gli utenti devono* essere abilitati per la voce per ricevere chiamate da una coda di chiamata.|
|[Musica blocco](music-on-hold.md) | Riproduce la musica predefinita definita dal servizio o dalla musica personalizzata caricata dall'amministratore del tenant quando viene messa in attesa una chiamata esterna dalla rete PSTN (Public Switched Telephone Network). Questa funzionalità funziona per le chiamate PSTN-to-Teams uno-a-uno oltre alle chiamate effettuate a una coda di chiamata. Questa funzionalità offre la parità delle notifiche di blocco con altre piattaforme. |
|Risposta/avvio della chiamata (per nome e numero)   |Consente agli utenti di rispondere alle chiamate in ingresso con un tocco e di effettuare chiamate in uscita componendo il numero di telefono completo o facendo clic su un nome nel client.   |
|[Opzioni di inoltro di chiamata e squillo simultaneo](https://support.office.com/article/call-forwarding-call-groups-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)  |Consente agli utenti di configurare regole di inoltro in modo che le chiamate possano essere inoltrate ovunque o che le chiamate possano essere inoltrate ai colleghi o alla segreteria telefonica.   |
|[Ritiro della chiamata di gruppo e inoltro al gruppo](call-sharing-and-group-call-pickup.md)  | Consente agli utenti di condividere le chiamate in arrivo con i colleghi in modo che i colleghi possano rispondere alle chiamate che si verificano quando l'utente non è disponibile. Meno disturbante per i destinatari rispetto ad altre forme di condivisione delle chiamate (ad esempio inoltro di chiamata o squillo simultaneo), perché gli utenti possono configurare la modalità di notifica di una chiamata condivisa in arrivo. |
|[Trasferire una chiamata e un trasferimento consultivo](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)  |Consente agli utenti di trasferire le chiamate a un'altra persona. Oppure, se devono uscire dall'ufficio ma vogliono continuare la conversazione, possono trasferire le chiamate dal pc o dal telefono IP al cellulare.  <br/> Si noti che *gli utenti non devono* essere abilitati alla voce per ricevere chiamate trasferite da un altro utente. |
|[Trasferisci alla segreteria telefonica a metà chiamata*](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)  | Consente agli utenti di eseguire il trasferimento alla segreteria telefonica durante una chiamata. |
|[Parcheggio di chiamata e recupero](call-park-and-retrieve.md)   | Consente agli utenti di mettere una chiamata in attesa nel Teams nel cloud. Quando una chiamata è parcheggiata, il servizio genera un codice univoco per il recupero delle chiamate. L'utente che ha parcheggiato la chiamata o un altro utente può quindi usare il codice e un'app o un dispositivo supportato per recuperare la chiamata.  |
|Chiama il numero di telefono dalla ricerca   | Consente agli utenti di effettuare una chiamata dalla casella di ricerca usando il comando /call e specificando un nome o un numero.  |
|[ID chiamante](how-can-caller-id-be-used-in-your-organization.md)   |Le chiamate dall'interno dell'azienda visualizzano un ID chiamante dettagliato che estrae informazioni dall'elenco aziendale, mostrando l'ID immagine e la posizione lavorativa invece di un semplice numero di telefono. Per le chiamate da numeri di telefono esterni, viene visualizzato l'ID chiamante fornito dal provider di servizi telefonici. Se i numeri di telefono esterni sono numeri secondari nell'elenco aziendale, verranno visualizzate le informazioni dell'elenco aziendale.   |
|Cambio di dispositivo   |Consente agli utenti di riprodurre una chiamata o una riunione su un altro dispositivo HID connesso a Teams, ad esempio passando dagli altoparlanti del PC a un auricolare.    |
|Routing delle chiamate basato sulla presenza  |Controlla le comunicazioni in ingresso con presenza, consentendo all'utente di bloccare tutte le comunicazioni in arrivo tranne quelle specificamente indicate.   |
|[Tastiera del telefono integrata](https://support.office.com/article/use-the-dial-pad-in-teams-27bc60b5-74c0-4e9c-808b-da4db9514d89)  | Consente agli utenti di effettuare chiamate in base al nome o al numero in qualsiasi punto della barra di ricerca e nella tastiera del telefono, velocizzando il processo di esecuzione delle chiamate in uscita.  |
|Chiamate federate   |Consente agli utenti di connettersi, comunicare e collaborare in modo sicuro con gli utenti nei tenant federati.   |
|[Effettuare e ricevere una videochiamata](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)  | Se l'account dell'utente è abilitato per le videochiamate, l'utente può effettuare videochiamate faccia a faccia con i propri contatti. Tutto ciò di cui hanno bisogno è una fotocamera, gli altoparlanti e il microfono del computer. Gli utenti possono anche usare un auricolare se il computer non ha un dispositivo audio incorporato. |
|[Cloud Voicemail](set-up-phone-system-voicemail.md)  | Quando un utente riceve una segreteria telefonica, viene recapitata nella propria cassetta postale Exchange come messaggio di posta elettronica con il messaggio della segreteria telefonica come allegato. Gli utenti possono ascoltare i messaggi sul telefono desktop certificato e in tutte le applicazioni Teams o Skype for Business applicazioni. Il supporto per la trascrizione segreteria telefonica è stato aggiunto a partire da marzo 2017 ed è attivato per impostazione predefinita per tutte le organizzazioni e gli utenti. <br> Si noti che *gli utenti non*  hanno bisogno di una licenza Sistema telefonico, né devono essere abilitati per la voce per usare Cloud Voicemail funzionalità.    |
|[Cloud Voicemail utente](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US)  | Consente agli utenti di configurare le impostazioni del client per i messaggi di saluto della segreteria telefonica, le regole di risposta alle chiamate e la lingua di apertura, inclusi i messaggi di saluto fuori sede. <br> Si noti che *gli utenti non*  hanno bisogno di una licenza Sistema telefonico, né devono essere abilitati per la voce per usare Cloud Voicemail funzionalità.  |
|[Suoneria secondaria](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)  | Gli utenti con più dispositivi altoparlanti collegati al PC possono scegliere di impostare un dispositivo secondario in modo che squilli oltre all'altoparlante predefinito. Ad esempio, un utente con un auricolare collegato al PC e agli altoparlanti da tavolo può scegliere di fare squillare sia l'auricolare che gli altoparlanti della scrivania quando viene chiamata, in modo da non perdere una chiamata.  |
|[Avvisi squillo distintivi](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f) (solo Teams) |Consente agli utenti di scegliere suonerie separate per le normali chiamate, le chiamate inoltrate e le chiamate delegate in modo che possano distinguere il tipo di chiamata.   |
|[Modalità di linea condivisa](shared-line-appearance.md)  | Consente agli utenti di condividere la propria linea telefonica in modo che un altro utente possa effettuare e ricevere chiamate per suo conto.|
|[Occupato (solo](teams-calling-policy.md) Teams occupato)  | Criteri di chiamata che consentono di configurare la modalità di gestione delle chiamate in arrivo quando un utente è: <ul><li>in una chiamata </li><li>in una conferenza</li><li>ha una chiamata messa in attesa. </li></ul> Il chiamante riceverà una delle risposte seguenti: <ul><li>sentire un segnale di occupato quando il chiamato è sul telefono</li> <li>verrà instradato di conseguenza alle impostazioni senza risposta dell'utente. Un'opzione consente al chiamante di lasciare una segreteria telefonica per l'utente che è già in una chiamata.</li></ul> Il destinatario riceve una notifica di chiamata senza risposta, ma non è in grado di rispondere alle chiamate in arrivo. Questa caratteristica è disabilitata per impostazione predefinita, ma può essere attivata dall'amministratore del tenant.|
|[Blocco delle chiamate](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US)  | Consente agli utenti di aggiungere numeri di telefono (PSTN) a un elenco bloccato in modo che la chiamata successiva da tale numero non squilli all'utente.|
|[Telefoni dell'area comune](set-up-common-area-phones.md)  | Un telefono dell'area comune viene in genere inserito in un'area come una sala d'attesa o una sala riunioni, rendendolo disponibile per più persone. I telefoni dell'area comune sono impostati come dispositivi anziché come utenti e possono accedere automaticamente a una rete.|
|[Supporto del bypass multimediale](direct-routing-plan-media-bypass.md) (solo per Teams Direct Routing)  | Per migliorare le prestazioni, i supporti multimediali vengono mantenuti tra session border controller (SBC) e il client invece di inviarlo tramite il Teams Telefono. |
|[Instradamento dei numeri non assegnati](routing-calls-to-unassigned-numbers.md) | Consente l'instradamento di numeri non assegnati a utenti, operatori automatici, code di chiamata o un annuncio personalizzato. |

## <a name="availability-in-gcc-high-and-dod-clouds"></a>Disponibilità nei cloud GCC High e DoD
<a name="bkmk_setup"> </a>

Le funzionalità seguenti non sono ancora disponibili nelle GCC High e DoD Cloud. 

- [Impostazioni di chiamata per suoneria secondaria, segreteria telefonica e delega avanzata](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)
- [Trasferisci alla segreteria telefonica a metà chiamata](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)
- Chiama il numero di telefono dalla barra di ricerca
- Musica blocco
- Azure AD ricerca inversa dei numeri

## <a name="related-topics"></a>Argomenti correlati

- [Che cos'è Teams Telefono](what-is-phone-system-in-office-365.md)
- [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md)
- [Configurare Teams Telefono](setting-up-your-phone-system.md)
- [Qual è il piano di chiamata adatto alle proprie esigenze?](calling-plan-landing-page.md)
- [Monitorare e gestire la qualità delle chiamate](monitor-call-quality-qos.md)
- [Licenze per i componenti aggiuntivi di Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Prezzi per Teams Telefono](https://products.office.com/microsoft-teams/voice-calling#requirements)
- [Teams per l'infrastruttura desktop virtualizzata con chiamate e riunioni](teams-for-vdi.md#teams-on-vdi-with-calling-and-meetings)

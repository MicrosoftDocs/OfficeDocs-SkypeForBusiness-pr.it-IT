---
title: Riunioni, webinar ed eventi live
ms.reviewer: ''
description: Guida per amministratori su come implementare e configurare le riunioni, i webinar e gli eventi live in Microsoft Teams.
ms.topic: article
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.service: msteams
ms.subservice: meetings
ms.custom: intro-overview
audience: admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
- highpri
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: e9fbd6e9075ee5680eaae4dc88dde96c842c5a7b
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800052"
---
# <a name="meetings-webinars-and-live-events"></a>Riunioni, webinar ed eventi live

[!INCLUDE[Teams Premium](includes/teams-premium-ecm.md)]

Esistono più modi per incontrarsi in Microsoft Teams: riunioni, webinar ed eventi live.

Questo articolo, destinato agli amministratori e ai professionisti IT, descrive le differenze tra riunioni, webinar ed eventi live. Fornisce quindi collegamenti alle informazioni necessarie per implementare rapidamente questa funzionalità per gli utenti.

[Meetings](#meetings), [webinars](#webinars), and [live events](#live-events) are all types of meetings, but webinars and live events provide additional control for the organizer over the conversation and participants. Webinars provide two-way interaction while live events provide a managed Q&A experience. 

I diversi tipi di riunioni sono anche caratterizzati da diversi limiti e capacità dei partecipanti. 

La tabella seguente riepiloga i tre tipi di riunioni, il numero di partecipanti consigliati e il modo in cui i partecipanti possono interagire nella riunione. Le sezioni con altre informazioni su ogni tipo di riunione seguono la tabella. Questo articolo include anche una sezione sulle [Procedure consigliate per riunioni di grandi dimensioni](#best-practices-for-large-meetings).

| Tipo di riunione | Numero di partecipanti | Interazione | Registrazione supportata |
|----------|--------|--------|-----|
| Riunioni  | Fino a 20,000* | - I partecipanti fino a 1.000 persone hanno la possibilità di partecipare a riunioni paritarie completamente interattive. <br> - I partecipanti con più di 1.000 fino a 20.000 hanno funzionalità [di sola visualizzazione](view-only-meeting-experience.md).  | Sì, con riunioni con registrazione (webinar 1.0) |
| Webinar | - Fino a 1.000<br>- Maggiori limiti con le funzionalità [di sola visualizzazione](view-only-meeting-experience.md) presto disponibili. |- I partecipanti fino a 1.000 hanno funzionalità completamente interattive.<br> - Interazione del gruppo di destinatari configurabile.<br> - Può specificare i relatori. | Sì |
| Eventi live | Fino a 20,000** |- Trasmettere a un pubblico di grandi dimensioni. <br>- Domande e risposte moderate per l'interazione con i destinatari. <br> - Può specificare producer e relatori, inclusi i relatori esterni.<br>- Supporta funzionalità di produzione più avanzate. | No |

*I soliti 10.000 sono aumentati a 20.000 fino al 30 giugno 2023.

**I soliti 10.000 sono aumentati a 20.000 fino al 30 giugno 2023. È possibile pianificare numeri ancora maggiori con eventi live in Yammer e/o Microsoft Stream. Per altre informazioni, vedere [Eventi live in Microsoft 365](/stream/live-event-m365). Si noti che gli eventi che superano 20.000 partecipanti richiedono il [programma di assistenza per eventi live](/stream/live-events-assistance).

Note that NDI is fully supported in meetings, webinars, and live events, allowing you to produce the broadcast by using tools such as OBS and Wirecast. For more information, see [Use NDI® technology in Microsoft Teams](use-ndi-in-meetings.md).

> [!NOTE]
> Per ulteriori informazioni e per ottenere indicazioni in base al ruolo per la distribuzione di eventi online con Microsoft Teams, consulta virtual [Event Playbook](https://aka.ms/VirtualEventPlaybook). Puoi anche partecipare al [forum dell'evento virtuale](https://aka.ms/VirtualEventForum) sul Microsoft Tech Community.

> [!NOTE]
> Per informazioni dettagliate sulla configurazione rapida delle riunioni e degli eventi di Teams su diverse piattaforme, vedere [Funzionalità di Teams per piattaforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="meetings"></a>Riunioni

Le **riunioni** in Teams includono audio, video e condivisione dello schermo per un massimo di 1.000 persone e [funzionalità di sola visualizzazione](view-only-meeting-experience.md) per oltre 1.000 partecipanti. Non è necessario essere membri di un'organizzazione (né avere un account Teams) per partecipare a una riunione di Teams. È possibile partecipare direttamente dall'invito di calendario tramite il collegamento Partecipa alla riunione o chiamare tramite audio, se disponibile.  

L'amministratore configurerà le impostazioni della riunione e controllerà le funzionalità delle riunioni abilitate per l'organizzazione specificando i criteri della riunione.  

Oltre alle riunioni pianificate regolarmente, gli utenti possono creare riunioni del canale. Con le riunioni del canale, tutti i membri di un team possono vedere che è in corso una riunione, parteciparvi e usare la chat. Le riunioni del canale consentono di invitare rapidamente tutti i membri di un team a una riunione. Per altre informazioni su come gli utenti finali pianificano le riunioni, vedere [Pianificare una riunione](https://support.microsoft.com/office/schedule-a-meeting-in-teams-943507a9-8583-4c58-b5d2-8ec8265e04e5).

Per informazioni sull'esperienza di riunione di sola visualizzazione, vedere [Esperienza di sola visualizzazione nelle riunioni di Teams](view-only-meeting-experience.md).

### <a name="articles-for-administrators"></a>Articoli per amministratori

La tabella seguente evidenzia gli articoli principali da esaminare:

| Articolo | Descrizione |
|----------|--------|
| [Impostazioni riunione](meeting-settings-in-teams.md) |  Descrive come configurare le impostazioni delle riunioni per gli utenti anonimi, gli inviti alle riunioni e il traffico multimediale.  |
| [Criteri riunione](meeting-policies-overview.md)  | Descrive come creare e gestire i criteri che determinano quali funzionalità sono disponibili per i partecipanti alla riunione. | 
| [Gestire la registrazione delle riunioni di Teams nel cloud](cloud-recording.md) | Descrive come gestire le registrazioni delle riunioni. |
| [Gestire i dispositivi dell'organizzazione](device-management.md)| Descrive come gestire i dispositivi dell'organizzazione, ad esempio telefoni e Teams Rooms. |
| [Usare i dati di telemetria in tempo reale per risolvere problemi di scarsa qualità delle riunioni](use-real-time-telemetry-to-troubleshoot-poor-meeting-quality.md) | Descrive come usare Real-Time Analytics (RTA) per risolvere i problemi di qualità scarsa Microsoft Teams riunione per singoli utenti.|

### <a name="key-training-for-end-users"></a>Formazione chiave per gli utenti finali

Nella tabella seguente sono elencati i corsi di formazione disponibili per gli utenti finali dell'organizzazione:

| Formazione | Descrizione |
|----------|--------|
| [Gestire le riunioni](https://support.office.com/article/join-a-teams-meeting-078e9868-f1aa-4414-8bb9-ee88e9236ee4) | Video di formazione rapido per gli utenti che non hanno esperienza con le riunioni di Teams. |
| [Pianificare una riunione](https://support.microsoft.com/office/schedule-a-meeting-in-teams-943507a9-8583-4c58-b5d2-8ec8265e04e5) | Articolo che descrive come pianificare diversi tipi di riunioni. |
| [Organizza riunioni efficaci con Teams](https://microsoftteams.eventbuilder.com/MaximizingTeamsMeetings) | Una lezione gratuita con docente su come rendere le riunioni più coinvolgenti, produttive e significative. |
| [Modificare le impostazioni dei partecipanti per una riunione di Teams](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) | Articolo sulla gestione delle opzioni di riunione. |

## <a name="webinars"></a>Webinar

I **webinar** sono riunioni strutturate in cui relatori e partecipanti hanno ruoli chiari. Una differenza fondamentale tra webinar e riunioni di Teams è che i webinar supportano una gestione affidabile delle registrazioni, un sito di registrazione e un evento personalizzabile e opzioni di riunione predefinite orientate agli eventi.

Se l'organizzazione usa già webinar, si ha familiarità con i criteri delle riunioni di Teams e le impostazioni seguenti che consentono di supportare la registrazione delle riunioni e tenere traccia dei dati sul coinvolgimento:

- AllowMeetingRegistration (abilitato o disabilitato)
- WhoCanRegister (tutti gli utenti dell'azienda esclusi i guest o tutti)

Con il rilascio della nuova esperienza di webinar, ci saranno nuovi criteri eventi di Teams con le impostazioni seguenti:

- AllowWebinar (abilitato o disabilitato)
- EventAccessType (tutti gli utenti dell'azienda esclusi i guest o tutti)

I nuovi criteri continueranno a supportare la registrazione e il monitoraggio e forniranno funzionalità aggiuntive all'esperienza del webinar. Inizialmente, saranno disponibili i seguenti elementi:

- Domande personalizzate relative a termini e condizioni
- Bio del relatore
- Banner, logo e colore predefinito
- Funzionalità di registrazione avanzate: approvazione manuale, lista di attesa, data di registrazione e limite di tempo
- Panoramica e gestione delle registrazioni: per ogni evento, un riepilogo dello stato di registrazione con elenchi di partecipanti in diversi stati di registrazione, a seconda delle funzionalità di registrazione abilitate.

È consigliabile iniziare a usare il nuovo criterio per sfruttare le nuove funzionalità non appena diventano disponibili.

Per altre informazioni sulle funzionalità e su come configurare webinar, vedere [Configurare webinar](set-up-webinars.md).


### <a name="key-training-for-end-users"></a>Formazione chiave per gli utenti finali

Nella tabella seguente sono elencati i corsi di formazione disponibili per gli utenti finali dell'organizzazione:

| Formazione | Descrizione | 
|----------|--------|
| [Introduzione ai webinar di Teams](https://support.microsoft.com/office/get-started-with-teams-webinars-42f3f874-22dc-4289-b53f-bbc1a69013e3) | Video di formazione rapido per gli utenti che non hanno esperienza con i webinar di Teams. |
| [Guida introduttiva visiva](https://adoption.microsoft.com/files/assets/TeamsWebinarsGetStartedGuide.pdf) | Guida visiva scaricabile che descrive come iniziare a pianificare webinar. |


## <a name="live-events"></a>Eventi live

Gli **eventi live** sono riunioni strutturate che consentono all'organizzazione di pianificare e produrre eventi in streaming a un pubblico online di grandi dimension—fino a 20.000 persone. Con gli eventi live, l'interazione con il pubblico è un'esperienza di domande e risposte con moderatore.

### <a name="articles-for-administrators"></a>Articoli per amministratori

La tabella seguente evidenzia gli articoli principali da esaminare:

| Articolo | Descrizione |
|----------|--------|
| [Cosa sono gli eventi live di Teams?](teams-live-events/what-are-teams-live-events.md)  | Rapida introduzione agli eventi live. |
| [Pianificare gli eventi live di Teams](teams-live-events/plan-for-teams-live-events.md) | Cosa è necessario sapere prima di configurare gli eventi live. |
| [Configurare gli eventi live di Teams](teams-live-events/set-up-for-teams-live-events.md) | Descrive i prerequisiti, ad esempio la pianificazione della rete. |
| [Configurare gli eventi live](teams-live-events/configure-teams-live-events.md) | Passaggi per la configurazione degli eventi live.|

### <a name="key-training-for-end-users"></a>Formazione chiave per gli utenti finali

Nella tabella seguente sono elencati i corsi di formazione disponibili per gli utenti finali dell'organizzazione:

| Formazione | Descrizione |
|:----------|:--------|
| [Introduzione agli eventi live](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a) | Introduzione agli eventi live e come iniziare. |
| [Video di formazione sugli eventi live di Teams](https://support.microsoft.com/en-us/office/plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502?ui=en-US&rs=en-US&ad=US) | Video che descrive come pianificare e pianificare un evento live.  |

Per produrre eventi virtuali su larga scala, consultare la [guida agli eventi virtuali](https://adoption.microsoft.com/virtual-event-guidance/), che include indicazioni per organizzatori di eventi, produttori tecnici, professionisti IT e autori di contenuti.

## <a name="apps-for-meetings"></a>App per le riunioni

Microsoft enables you to enhance meeting experiences by integrating and using meeting apps. For example, whiteboard integration in Teams meetings is powered by the Whiteboard web app, which lets Teams meeting participants draw, sketch, and write together on a shared digital canvas.

È possibile aggiungere app per le riunioni alla distribuzione di Teams usando le app fornite con Teams, con app e modelli di terze parti certificati e creando app personalizzate.

La tabella seguente elenca gli articoli contenenti altre informazioni:

| Articolo | Descrizione |
|----------|--------|
| [Panoramica delle app Teams](deploy-apps-microsoft-teams-landing-page.md) | Introduzione alle app e come distribuire app per l'organizzazione. |
| [Suggerimenti per le riunioni di Teams](/microsoftteams/platform/apps-in-teams-meetings/teams-apps-in-meetings) | Panoramica dell'estendibilità delle app per le riunioni, dei riferimenti alle API e di come abilitare e configurare le app per le riunioni. |
| [Gestire la Lavagna in Teams](manage-whiteboard.md) | Descrive le funzionalità di Whiteboard e come abilitare e disabilitare per l'organizzazione. |

## <a name="license-requirements-for-meetings-webinars-and-live-events"></a>Requisiti di licenza per riunioni, webinar ed eventi live

Chiunque può partecipare gratuitamente a una riunione dei team, a un webinar o a un evento pubblico dal vivo, senza bisogno di alcuna licenza.

Le persone che organizzano, pianificano o conducono riunioni o eventi live devono aver acquistato una delle licenze di Microsoft 365 elencate nella [descrizione del servizio Microsoft Teams](/office365/servicedescriptions/teams-service-description). Se usi già Teams, è probabile che tu abbia la licenza necessaria per organizzare e condurre riunioni, webinar ed eventi live.

Per informazioni sulle licenze di Teams Premium, vedere [licenze di Teams Premium](teams-add-on-licensing/licensing-enhance-teams.md).

Per consentire alle persone di accedere a una riunione telefonicamente, è necessario configurare il servizio di audioconferenza. Per saperne di più sull’audioconferenza, consulta [Audioconferenza in Teams](deploy-audio-conferencing-teams-landing-page.md).

## <a name="best-practices-for-large-meetings"></a>Procedure consigliate per riunioni di grandi dimensioni

Questa sezione fornisce una guida per gli amministratori, oltre a consigli che gli amministratori possono condividere con i relatori e gli organizzatori.

Per gestire un evento di successo, seguire le procedure descritte di seguito:

- Per un'esperienza ottimale nei webinar, negli eventi live e nelle riunioni di grandi dimensioni, Microsoft consiglia di usare l'ultima versione del client desktop di Teams o dei client per dispositivi mobili di Teams.

- Assicurarsi che tutti i [principi di connettività di rete di Microsoft](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles) siano stati seguiti sia in locale che per gli utenti remoti.
- Usare [la telemetria dei dati in](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/introducing-microsoft-teams-real-time-call-quality-analytics/ba-p/2912146) tempo reale per monitorare l'evento e identificare eventuali problemi e la loro origine.
  - Designare i monitoraggi delle riunioni per [analizzare](use-real-time-telemetry-to-troubleshoot-poor-meeting-quality.md) i dati di telemetria per gli utenti che riscontrano un'esperienza di scarsa qualità causata da metriche che eccedono le soglie.
  - Impostare i monitor delle riunioni come relatori per disabilitare i flussi video non autorizzati, disattivare l'audio accidentale dei microfoni in tempo reale e rimuovere i partecipanti, se necessario.

### <a name="guidelines-for-your-end-users"></a>Linee guida per gli utenti finali

Gli organizzatori e i relatori dovranno applicare i seguenti consigli:

- Per le riunioni con più di 10 partecipanti, usare [Q&A](/MicrosoftTeams/manage-qna-for-teams) per dare ai partecipanti l'opportunità di chiedere formalmente e ricevere risposte alle domande, nonché di partecipare a discussioni strutturate.

- Per creare una riunione senza intoppi, gli organizzatori di eventi possono impostare relatori predefiniti. Dopo l'avvio di una riunione, i relatori possono promuovere anche altri partecipanti al ruolo di relatore.

- Definire un co-organizzatore tramite le opzioni della riunione (anteprima pubblica)

- Pre-configurare le impostazioni video e microfono per tenere sotto controllo le esperienze dei partecipanti.
  - Disabilitare i microfoni dei partecipanti per evitare disturbi. Se qualcuno chiede di interagire durante la riunione, permettergli di riattivare l'audio quando alza la mano.
  - Disabilitare il video dei partecipanti per evitare distrazioni visive. In momenti specifici della riunione, l’uso del video può essere consentito a tutti i partecipanti o a persone specifiche.

- Usare sondaggi e domande e risposte durante la riunione.

- Usare i controlli della sala d'attesa per tenere sotto controllo l'accesso alla riunione o i blocchi della sala d'attesa.

- Eseguire il [test di connettività di rete di Microsoft 365](https://connectivity.office.com/) per verificare l'idoneità della rete alcuni giorni prima e il giorno stesso dell'evento.

- In caso di presentazioni da casa, verificare che gli altri dispositivi non consumino un’elevata larghezza di banda (servizi di streaming, giochi online, download di grandi dimensioni).

- Presentare da un endpoint con una connessione cablata per una condivisione più affidabile di audio, video e schermo.

- Verificare che gli utenti usino l'app di Teams più recente su desktop o dispositivi mobili.

- Quando si usa un portatile, verificare che la connettività di rete sia elevata e l'alimentazione sufficiente.

- Pianificare una prova prima dell'evento per identificare eventuali problemi di dispositivo, illuminazione o rete. In questo modo, gli organizzatori/relatori acquisiranno familiarità con le funzionalità da utilizzare.
  - Pianificare ulteriori prove pratiche se sono stati rilevati problemi, per garantire il corretto completamento delle attività di correzione..
  
- Usare le funzionalità come Spotlight, PowerPoint Live, registrazione delle riunioni, didascalie e trascrizioni per promuovere l'impegno e l'efficacia.

- I relatori e i partecipanti dovrebbero usare l'app desktop di Teams per offrire un'esperienza ottimale.

- I partecipanti dovranno disattivare le notifiche chat durante le riunioni di grandi dimensioni per evitare distrazioni.

- Per altri suggerimenti su come ospitare riunioni di grandi dimensioni, vedere [Procedure consigliate per le riunioni di grandi dimensioni in Teams](https://support.microsoft.com/office/best-practices-for-a-large-teams-meeting-ce2cdb9a-0546-43a4-bb55-34ab98ab6b16).

## <a name="related-topics"></a>Argomenti correlati

[Riunioni e conferenze in Teams](deploy-meetings-microsoft-teams-landing-page.md)

[Configurare webinar in Teams](set-up-webinars.md)

[Eventi live in Teams](teams-live-events/what-are-teams-live-events.md)

[Esperienza di sola visualizzazione nelle riunioni di Teams](view-only-meeting-experience.md)

[Limiti e specifiche per Teams](limits-specifications-teams.md)


---
title: Introduzione a Teams per le organizzazioni sanitarie
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-overview
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Informazioni sulle funzionalità di assistenza sanitaria come Microsoft Teams per il telesalline, l'integrazione di EHR, l'integrazione di un sistema frontline worker e l'app Pazienti.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: a5b8ea7cddba8def74a1f5b839710cf73bafc67e
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125769"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a>Introduzione a Teams per le organizzazioni sanitarie

Microsoft Teams offre diverse funzionalità di telemedicine utili per gli ospedali e altre organizzazioni sanitarie. Le funzionalità di Teams sono in fase di sviluppo per aiutare gli ospedalieri con:

- Visite virtuali e integrazione dei record sanitari elettronici (EHR)
- Pacchetti dei criteri di Teams
- Messaggistica sicura
- Modelli di Teams
- Coordinamento e collaborazione care

Questa funzionalità fa parte di Microsoft Cloud per il settore sanitario. Scopri di più sull'uso di questa soluzione, che riunisce le funzionalità di Azure, Dynamics 365 e Microsoft 365 in [Microsoft Cloud for Healthcare.](https://docs.microsoft.com/industry/healthcare)

Guardare il video seguente per saperne di più sull'uso della raccolta sanitaria per migliorare la collaborazione del team sanitario in Microsoft Teams.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hqan]

> [!NOTE]
> Il contenuto di questa sezione presuppone che Teams sia già stato distribuito nell'organizzazione. Se Teams non è ancora stato ancora implementazione, leggere [come implementare Microsoft Teams.](../../How-to-roll-out-teams.md)

Per le organizzazioni sanitarie sono disponibili gli scenari seguenti:

| Scenario | Descrizione | Requisiti |
| -------- | -------- | -------- |
| [Visite virtuali con integrazione di Electronic Healthcare Record (EHR)](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | Pianificare, gestire e condurre visite virtuali con i pazienti. Questo scenario connette Microsoft Teams e la piattaforma Innova per supportare le visite virtuali. | Abbonamento attivo a Microsoft Cloud per il settore sanitario o abbonamento all'offerta autonoma di Microsoft Teams EHR Connector. <br> Gli utenti devono avere una licenza appropriata di Microsoft 365 o Office 365 che include riunioni di Microsoft Teams*. <br> Le organizzazioni devono avere con la versione Beta di novembre 2018 o successiva. <br>[Dettagli per i requisiti EHR](ehr-admin.md#before-you-begin) |
| [Visite virtuali con Microsoft Bookings e l'app Bookings](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | Pianificare, gestire e condurre visite virtuali con i pazienti. Questo scenario si basa su Microsoft Bookings per supportare le visite virtuali. | Microsoft Bookings deve essere attivato per l'organizzazione. <br> Tutti gli utenti dell'app Bookings e tutto il personale che partecipano alle riunioni devono avere una licenza che supporta la pianificazione delle riunioni di Teams*. <br>[Dettagli per i requisiti di Bookings](../../bookings-app-admin.md#prerequisites-for-using-the-bookings-app-in-teams)|
| [Pacchetti dei criteri di Teams](#teams-policy-packages)| Assicurarsi che gli operatori clinici, gli information worker e i dispositivi per la sala pazienti siano in grado di accedere in modo appropriato alle funzionalità di Teams.| Gli utenti devono avere una licenza appropriata*. |
| [Messaggistica sicura](#secure-messaging) | È possibile attirare più rapidamente l'attenzione dei messaggi urgenti e avere la certezza che il messaggio sia stato ricevuto e letto. | Gli utenti devono avere una licenza appropriata*.  |
| [Modelli di Teams](#teams-templates-for-healthcare-organizations) | Creare team che includano un modello predefinito di impostazioni, canali e app preinstallate per la comunicazione e la collaborazione all'interno di un dipartimento, un pod o un dipartimento oppure tra più rioni, pod e dipartimenti all'interno di un ospedale. | Gli utenti devono avere una licenza appropriata*.  |
| [Coordinamento e collaborazione care](#care-coordination-and-collaboration) | Medici e personale possono collaborare internamente su pianificazioni, documenti, attività e così via.| Gli utenti devono avere una licenza appropriata*. |

*Sono supportati Office 365 A3, A5, E3 ed E5, oltre a Microsoft 365 Business Standard, A3, A5, E3 ed E5. Per altre informazioni sulle licenze generali di Teams, vedere [Gestire l'accesso degli utenti a Teams.](../../user-access.md)

## <a name="virtual-visits-and-electronic-healthcare-record-ehr-integration"></a>Visite virtuali e integrazione dei record sanitari elettronici (EHR)

Usare la piattaforma completa per le riunioni in Microsoft Teams per pianificare, gestire e condurre visite virtuali con i pazienti.

- Se la tua organizzazione usa già Electronic Health Records, o EHR, puoi integrare Microsoft Teams per un'esperienza più fluida. Microsoft Teams Electronic Health Record (EHR) Connector consente ai medici di avviare facilmente una visita o una consulenza virtuale con un altro provider di Teams direttamente dal sistema EHR. Per altre informazioni, vedere [le visite virtuali con Teams - Integrazione in EHR.](ehr-admin.md)
- Se non si usa un EHR supportato, è possibile usare Microsoft Bookings e l'app Bookings in Teams. Per altre informazioni, vedere le [visite virtuali e l'app Bookings in Microsoft Teams.](../../bookings-app-admin.md)

![Visite virtuali con Microsoft Teams](../../media/virtual-visits-teams.png)

## <a name="teams-policy-packages"></a>Pacchetti dei criteri di Teams

Applicare i pacchetti di criteri di Teams per definire i diversi ruoli che possono eseguire in Teams. Ad esempio, specificare i criteri per:

- Operatori clinici, come infermieri specializzati, infermieri a pagamento, medici e operatori sociali, in modo che possano avere accesso completo a chat, chiamate, gestione dei turni e riunioni.
- Gli information worker dell'organizzazione sanitaria, ad esempio il personale IT, il personale informatico, il personale finanziario e i responsabili della conformità, possono avere accesso completo a chat, chiamate e riunioni.
- Sale pazienti, per controllare le impostazioni per i dispositivi della sala pazienti.

Per altre informazioni, vedi Pacchetti [di criteri di Teams per il settore sanitario.](../../policy-packages-healthcare.md)

## <a name="secure-messaging"></a>Messaggistica sicura

La messaggistica sicura supporta la collaborazione all'interno dei team sanitari, incluse diverse nuove funzionalità:

- Il mittente del messaggio può impostare una priorità speciale per il messaggio, in modo che il destinatario riceve più volte una notifica finché non legge il messaggio.
- Il mittente del messaggio può richiedere una conferma di lettura, in modo da ricevere una notifica quando un messaggio inviato è stato letto dal destinatario del messaggio.

Insieme, queste caratteristiche consentono di prestare più rapidamente attenzione ai messaggi urgenti e di avere la certezza che il messaggio sia stato ricevuto e letto. I nuovi team sanitari che usano queste funzionalità possono essere creati per ogni paziente. Queste funzionalità sono basate su criteri e possono essere assegnate a singoli utenti o a interi team.

Per altre informazioni, vedere [Introduzione ai criteri di messaggistica sicura per le organizzazioni sanitarie.](messaging-policies-hc.md)

La messaggistica sicura consente anche di avere altri tenant federati dalle organizzazioni sanitarie, consentendo una comunicazione tra tenant più ricca. (Vedere [Gestire l'accesso esterno (federazione) in Microsoft Teams).](../../manage-external-access.md)

## <a name="teams-templates-for-healthcare-organizations"></a>Modelli di Teams per le organizzazioni sanitarie

Sono stati sviluppati nuovi modelli per la creazione di Teams da applicare a un ambiente ospedaliero e altri saranno presto disponibili. In questo modo è più facile creare team che gli operatori sanitari usino per coordinare le cure dei pazienti di vari reparti o reparti. Per altre informazioni, vedere [Introduzione ai modelli di Teams per le organizzazioni sanitarie.](healthcare-templates.md) I team possono essere avviati per reparti interni come la reparto di allenamento o per i reparti di assistenza e sono in fase di sviluppo altri modelli.

## <a name="care-coordination-and-collaboration"></a>Coordinamento e collaborazione care

Riunire il team sanitario per coordinare le cure e collaborare con Microsoft Teams.

![Assistenza sanitaria: Collaborare con il team per la salute in Teams](../../media/teams-healthcare-collaborate-in-teams.png)

Microsoft Teams consente a medici, medici, infermieri e altro personale di collaborare in modo efficiente con le funzionalità di collaborazione incluse in Microsoft Teams, come:

- Configurare team e canali per i team sanitari e gli information worker. Usare i canali con le schede come modo per strutturare il proprio lavoro, con l'ulteriore aiuto delle schede in cui è possibile aggiungere origini di informazioni.
- Chattare, pubblicare messaggi e comunicare. Il team può avere conversazioni persistenti su diversi pazienti che hanno bisogno di attenzione.
- Chiamare e incontrare i membri del team sanitario. Configurare riunioni individuali o usare le riunioni del canale per gestire le riunioni quotidiane, con la potenza delle funzionalità audio, video, di condivisione dello schermo, di registrazione e trascrizione di Teams.
- Archiviare e condividere file e documenti. Il team dell'integrità fa parte di un unico team virtualizzato che lavora e collabora ai documenti di Office.

Inoltre, il team può usare le app in Teams per:

- Condividere elenchi e tenere traccia delle informazioni con l'app Elenchi
- Tenere traccia e monitorare le attività con l'app Attività
- Semplificare le approvazioni con l'app Approvazioni
- Creare, gestire e condividere pianificazioni con l'app Turni

### <a name="share-lists-and-track-information-with-the-lists-app"></a>Condividere elenchi e tenere traccia delle informazioni con l'app Elenchi

> [!NOTE]
> A partire dal 30 ottobre 2020, l'app Pazienti è stata ritirata e sostituita [dall'app Elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams. Con Elenchi, i team di assistenza all'interno dell'organizzazione sanitaria possono creare elenchi di pazienti per scenari che vanno da turni e riunioni interdisciplinari del team al monitoraggio generale dei pazienti.

L'app Elenchi in Teams consente ai team di tenere traccia delle informazioni e organizzare il lavoro. L'app è preinstallato per tutti gli utenti di Teams ed è disponibile come scheda in ogni team e canale. Gli elenchi possono essere creati da zero, da modelli predefiniti o importando dati in Excel.

I team sanitari possono usare il modello Pazienti per iniziare. Possono creare elenchi per tenere traccia delle esigenze e dello stato dei pazienti. I dati dei pazienti esistenti nei fogli di calcolo di Excel possono essere disponibili per creare un elenco in Teams. Questi elenchi possono essere usati per scenari come le arrotondamenti e il monitoraggio dei pazienti per coordinare le cure.

Ad esempio, un'infermiera con carica crea un elenco di pazienti in un team che include tutti i membri del team sanitario. Durante i turni, il team sanitario accede a Teams dai propri dispositivi mobili e aggiorna le informazioni sui pazienti nell'elenco, che tutti i membri del team possono visualizzare per rimanere sincronizzati. Durante le sessioni di arrotondamento in cui il team sanitario si riunirà per discutere e valutare metriche chiave sulle prestazioni sanitarie per assicurarsi che un paziente si trova sul percorso di glide giusto da scarichi, può condividere queste informazioni utilizzando Teams su un grande schermo. I membri del team health che non sono nel sito possono partecipare da remoto.

Ecco un elenco di esempio configurato per l'arrotondamento dei pazienti.

:::image type="content" source="../../media/lists-patients-example.png" alt-text="Screenshot dell'elenco di esempio per l'arrotondamento dei pazienti":::

Per altre informazioni, vedere [Gestire l'app Elenchi per l'organizzazione in Teams.](../../manage-lists-app.md)

### <a name="track-and-monitor-tasks-with-the-tasks-app"></a>Tenere traccia e monitorare le attività con l'app Attività

Usare [le attività](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070) in Teams per tenere traccia delle attività per l'intero team di salute. Il team dell'integrità può creare, assegnare e pianificare attività, categorizzare le attività e aggiornare lo stato in qualsiasi momento, da qualsiasi dispositivo che esegue Teams.

Per altre informazioni, vedere [Gestire l'app Attività per l'organizzazione in Microsoft Teams](../../manage-tasks-app.md)

### <a name="streamline-approvals-with-the-approvals-app"></a>Semplificare le approvazioni con l'app Approvazioni

Usare [le approvazioni](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3) per semplificare tutte le richieste e i processi con il team. Creare, gestire e condividere le approvazioni direttamente dall'hub per il lavoro in team. Avviare un flusso di approvazione dalla stessa posizione in cui si invia una chat, in una conversazione di canale o dall'app Approvazione stessa. Basta selezionare un tipo di approvazione, aggiungere dettagli, allegare file e scegliere i responsabili approvazione. Dopo l'invio, i responsabili approvazione vengono informati e possono esaminare e intervenire sulla richiesta.

È possibile consentire l'app Approvazione per l'organizzazione e aggiungerla ai team. Per altre informazioni sulla gestione delle app, vedere [Gestire le app nell'interfaccia di amministrazione di Microsoft Teams.](../../manage-apps.md)

### <a name="create-manage-and-share-schedules-with-the-shifts-app-and-frontline-worker-integration"></a>Creare, gestire e condividere pianificazioni con l'app Turni e l'integrazione di Frontline Worker

Microsoft Teams si integra con l'app Turni e l'assistente in prima linea, che può essere usato per coordinare le funzionalità del personale a turni e altro ancora. Ad esempio, in Turni, i responsabili delle infermiere possono configurare e coordinare gli orari per il personale, mentre gli infermieri possono controllare gli orari e scambiare turni. Teams include un criterio di configurazione predefinito dell'app Per i dipendenti in prima linea che è possibile assegnare agli operatori sul campo nell'organizzazione. Per impostazione predefinita, il criterio include le app Attività, Turni, Chat e Chiamate. Questo criterio controlla il comportamento di queste app, ad esempio l'aggiunta dell'app Turni alla barra dell'app in modo che il team possa accedervi rapidamente.

Per altre informazioni, vedere [Gestire l'app Turni per l'organizzazione in Microsoft Teams.](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

## <a name="help-your-clinical-and-information-workers-get-going-with-teams"></a>Aiutare gli operatori clinici e information worker a iniziare a utilizzare Teams

Sono disponibili molte risorse per aiutare tutti gli utenti dell'organizzazione a usare Teams:

- Visitare il centro per l'adozione di [Teams](https://adoption.microsoft.com/microsoft-teams/) per consigli sull'implementazione di Teams se si sta iniziando il percorso di lavoro dell'organizzazione con Teams o si sta espandendo Teams in più aree dell'organizzazione.
- È consigliabile configurare percorsi [di apprendimento personalizzati](https://adoption.microsoft.com/microsoft-365-learning-pathways/) per consentire agli utenti di coprire solo le attività che devono eseguire.
- Guida e formazione per gli utenti su come eseguire attività di base in Microsoft Teams sul sito di supporto di [Teams,](https://support.microsoft.com/teams)inclusi [video di formazione rapida.](https://support.microsoft.com/office/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7) Questo sito offre anche assistenza e formazione per le app di Teams, tra cui [Elenchi,](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) [Attività,](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070) [Approvazioni,](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3) [Prenotazioni](https://support.microsoft.com/office/overview-of-the-bookings-app-in-teams-7b8569e1-0c8a-444e-b712-d9968b05110b)e [Turni.](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821)

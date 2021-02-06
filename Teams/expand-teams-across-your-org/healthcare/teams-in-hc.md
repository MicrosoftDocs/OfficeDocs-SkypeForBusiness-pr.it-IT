---
title: Iniziare a usare team per organizzazioni sanitarie
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
description: Informazioni sulle caratteristiche di assistenza sanitaria, ad esempio Microsoft teams telehealth, integrazione di EHR, integrazione del sistema di lavoro in prima linea e l'app pazienti.
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
# <a name="get-started-with-teams-for-healthcare-organizations"></a>Iniziare a usare team per organizzazioni sanitarie

Microsoft teams offre una serie di funzionalità di telemedicina utili per ospedali e altre organizzazioni sanitarie. Le caratteristiche dei team sono in fase di sviluppo per aiutare gli ospedali:

- Visite virtuali e integrazione di EHR (Electronic Healthcare record)
- Pacchetti di criteri Teams
- Messaggistica sicura
- Modelli di Teams
- Coordinamento e collaborazione per l'assistenza

Questa funzionalità fa parte del cloud Microsoft per l'assistenza sanitaria. Altre informazioni sull'uso di questa soluzione, che riunisce le funzionalità di Azure, Dynamics 365 e Microsoft 365 su [Microsoft Cloud per l'assistenza sanitaria](https://docs.microsoft.com/industry/healthcare).

Guardare il video seguente per altre informazioni sull'uso della raccolta di servizi sanitari per migliorare la collaborazione con il team di assistenza sanitaria in Microsoft teams.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hqan]

> [!NOTE]
> Il contenuto in questa sezione presuppone che siano già stati distribuiti team nell'organizzazione. Se non sono stati ancora distribuiti team, iniziare a leggere [come implementare Microsoft teams](../../How-to-roll-out-teams.md).

Gli scenari seguenti sono disponibili per le organizzazioni sanitarie:

| Scenario | Descrizione | Requisiti |
| -------- | -------- | -------- |
| [Visite virtuali con l'integrazione di Electronic Healthcare record (EHR)](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | Pianificare, gestire e condurre visite virtuali con i pazienti. Questo scenario connette Microsoft teams e la piattaforma Epic per supportare le visite virtuali. | Abbonamento attivo a Microsoft Cloud per l'assistenza sanitaria o all'abbonamento a Microsoft teams EHR Connector standalone offer. <br> Gli utenti devono avere una licenza Microsoft 365 o Office 365 appropriata che include le riunioni di Microsoft teams *. <br> Le organizzazioni devono avere con versione epica il 2018 novembre o versioni successive. <br>[Dettagli per i requisiti di EHR](ehr-admin.md#before-you-begin) |
| [Visite virtuali con le prenotazioni Microsoft e l'app bookings](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | Pianificare, gestire e condurre visite virtuali con i pazienti. Questo scenario si basa sulle prenotazioni Microsoft per supportare le visite virtuali. | Le prenotazioni Microsoft devono essere attivate per l'organizzazione. <br> Tutti gli utenti dell'app bookings e tutti i membri del personale che partecipano alle riunioni devono avere una licenza che supporti la pianificazione della riunione di teams *. <br>[Dettagli per i requisiti di prenotazione](../../bookings-app-admin.md#prerequisites-for-using-the-bookings-app-in-teams)|
| [Pacchetti di criteri Teams](#teams-policy-packages)| Verificare che i dipendenti clinici, gli Information Worker e i dispositivi della sala paziente abbiano l'accesso appropriato alla funzionalità teams.| Gli utenti devono avere una licenza appropriata *. |
| [Messaggistica sicura](#secure-messaging) | Attirare l'attenzione più rapidamente sui messaggi urgenti e avere la certezza che il messaggio è stato ricevuto e letto. | Gli utenti devono avere una licenza appropriata *.  |
| [Modelli di Teams](#teams-templates-for-healthcare-organizations) | Creare team che includono un modello predefinito di impostazioni, canali e app preinstallate per la comunicazione e la collaborazione all'interno di un reparto, un pod o un dipartimento oppure tra più reparti, baccelli e servizi all'interno di un ospedale. | Gli utenti devono avere una licenza appropriata *.  |
| [Coordinamento e collaborazione per l'assistenza](#care-coordination-and-collaboration) | I medici e il personale possono collaborare internamente a pianificazioni, documenti, attività e così via.| Gli utenti devono avere una licenza appropriata *. |

* Sono supportati Office 365 a3, a5, E3 e E5, oltre a Microsoft 365 business standard, a3, a5, E3 e E5. Per altre informazioni sulle licenze generali per i team, vedere [gestire l'accesso degli utenti ai team](../../user-access.md).

## <a name="virtual-visits-and-electronic-healthcare-record-ehr-integration"></a>Visite virtuali e integrazione di EHR (Electronic Healthcare record)

Usare la piattaforma completa riunioni in Microsoft teams per pianificare, gestire e condurre visite virtuali con i pazienti.

- Se l'organizzazione usa già i record sanitari elettronici o EHR, è possibile integrare Microsoft teams per un'esperienza più semplice. Microsoft teams Electronic Health record (EHR) Connector rende più facile per i medici avviare una visita virtuale o una consultazione con un altro provider in teams direttamente dal sistema EHR. Per altre informazioni, Vedi [visite virtuali con Teams-Integration in EHR](ehr-admin.md).
- Se non si usa un EHR supportato, è possibile usare le prenotazioni Microsoft e l'app bookings in teams. Per altre informazioni, vedere [prenotazioni di app e visite virtuali in Microsoft teams](../../bookings-app-admin.md).

![Visite virtuali con Microsoft Teams](../../media/virtual-visits-teams.png)

## <a name="teams-policy-packages"></a>Pacchetti di criteri Teams

Applicare i pacchetti dei criteri teams per definire i diversi ruoli che possono eseguire in teams. Ad esempio, specificare i criteri per:

- I lavoratori clinici, come infermieri registrati, caricano infermieri, medici e assistenti sociali, in modo che possano avere accesso completo alla chat, alle chiamate, alla gestione del turno e alle riunioni.
- Gli Information Worker dell'organizzazione sanitaria, come il personale IT, il personale informatico, il personale finanziario e i responsabili della conformità, possono avere accesso completo alla chat, alle chiamate e alle riunioni.
- Sale paziente, per controllare le impostazioni per i dispositivi della sala paziente.

Per altre informazioni, vedere [pacchetti di criteri per team per l'assistenza sanitaria](../../policy-packages-healthcare.md).

## <a name="secure-messaging"></a>Messaggistica sicura

La messaggistica sicura supporta la collaborazione all'interno dei team di integrità, incluse diverse nuove caratteristiche:

- Un mittente del messaggio può impostare una priorità speciale per il messaggio, in modo che il destinatario venga notificato ripetutamente fino a quando non legge il messaggio.
- Un mittente del messaggio può richiedere una conferma di lettura, in modo che venga notificato quando un messaggio inviato è stato letto dal destinatario del messaggio.

Insieme, queste funzionalità permettono una maggiore attenzione ai messaggi urgenti e alla fiducia che il messaggio è stato ricevuto e letto. I nuovi team di integrità che usano queste funzionalità possono essere creati per ogni singolo paziente. Queste caratteristiche sono basate su criteri e possono essere assegnate a singoli o a Team interi.

Per altre informazioni, vedere [Introduzione ai criteri di messaggistica sicura per le organizzazioni sanitarie](messaging-policies-hc.md).

Anche correlato alla messaggistica sicura è la possibilità di avere altri tenant federati da organizzazioni sanitarie, consentendo una comunicazione intertenant più ricca. Vedere [gestire l'accesso esterno (Federazione) in Microsoft teams](../../manage-external-access.md).

## <a name="teams-templates-for-healthcare-organizations"></a>Modelli di team per organizzazioni sanitarie

I nuovi modelli per la creazione di team sono stati sviluppati per applicarsi a un ambiente ospedaliero e più presto sono attesi. In questo modo è più semplice creare team che gli operatori sanitari usano per coordinare le cure per i pazienti in diversi reparti o corsi. Per altre informazioni, vedere [Introduzione ai modelli di team per le organizzazioni sanitarie](healthcare-templates.md). I team possono essere avviati per i reparti interni, ad esempio cardiologia o per i corsi di assistenza, e altri modelli sono in sviluppo.

## <a name="care-coordination-and-collaboration"></a>Coordinamento e collaborazione per l'assistenza

Collaborare con Microsoft teams per coordinare i servizi di assistenza.

![Assistenza sanitaria: collaborare con il team di assistenza sanitaria in teams](../../media/teams-healthcare-collaborate-in-teams.png)

Microsoft teams consente a medici, clinici, infermieri e altri membri del personale di collaborare in modo efficiente con le caratteristiche di collaborazione incluse in Microsoft teams, ad esempio:

- Configurare Team e canali per i team di salute e gli Information Worker. Usare i canali con le schede per strutturare il proprio lavoro, con ulteriori informazioni sulle schede a cui possono aggiungere le origini dati.
- Chattare, pubblicare messaggi e comunicare. Il team può avere conversazioni persistenti su pazienti diversi che richiedono attenzione.
- Chiama e incontra i membri del team sanitario. Configurare singole riunioni o usare le riunioni di canale per gestire le riunioni quotidiane, sia con la potenza del team audio, video, condivisione dello schermo, registrazione e funzionalità di trascrizione.
- Archiviare e condividere file e documenti. Il team di integrità fa parte di un unico team virtualizzato che lavora e collabora ai documenti di Office.

Inoltre, il team può usare le app in teams per:

- Condividere elenchi e tenere traccia delle informazioni con l'app elenchi
- Tenere traccia e monitorare le attività con l'app attività
- Semplificare le approvazioni con l'app approvazioni
- Creare, gestire e condividere le pianificazioni con l'app turni

### <a name="share-lists-and-track-information-with-the-lists-app"></a>Condividere elenchi e tenere traccia delle informazioni con l'app elenchi

> [!NOTE]
> Efficace il 30 ottobre 2020, l'app patients è stata ritirata e sostituita dall' [app elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in teams. Con gli elenchi, i team di assistenza nell'organizzazione sanitaria possono creare elenchi di pazienti per scenari che spaziano da turni e riunioni interdisciplinari del team per il monitoraggio generale dei pazienti.

L'app elenchi in teams aiuta i team a tenere traccia delle informazioni e organizzare il lavoro. L'app è preinstallata per tutti gli utenti di teams ed è disponibile come scheda in ogni team e canale. Gli elenchi possono essere creati da zero, da modelli predefiniti o dall'importazione di dati in Excel.

i team di integrità possono usare il modello patients per iniziare. Possono creare elenchi per tenere traccia delle esigenze e dello stato dei pazienti. I dati dei pazienti esistenti nei fogli di calcolo di Excel possono essere introdotti per creare un elenco in teams. Questi elenchi possono essere usati per scenari come i turni e il monitoraggio dei pazienti per coordinare le cure.

Ad esempio, un'infermiera della carica crea un elenco di pazienti in un team che include tutti i membri del team di integrità. Durante i turni, il team di integrità accede ai team sui dispositivi mobili e aggiorna le informazioni sul paziente nell'elenco, che tutti i membri del team possono visualizzare per rimanere sincronizzati. Durante le sessioni di arrotondamento in cui il team sanitario si riunisce per discutere e valutare le metriche sulle prestazioni chiave per garantire che un paziente sia sul giusto percorso di scorrimento per il discarico, può condividere queste informazioni usando teams su uno schermo di grandi dimensioni. i membri del team di integrità che non sono presenti nel sito possono partecipare in remoto.

Ecco un elenco di esempio che è stato configurato per l'arrotondamento dei pazienti.

:::image type="content" source="../../media/lists-patients-example.png" alt-text="Screenshot dell'elenco di esempio per l'arrotondamento del paziente":::

Per altre informazioni, vedere [gestire l'app elenchi per l'organizzazione in teams](../../manage-lists-app.md).

### <a name="track-and-monitor-tasks-with-the-tasks-app"></a>Tenere traccia e monitorare le attività con l'app attività

Usare le [attività](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070) in teams per tenere traccia degli elementi per l'intero team di integrità. Il team di integrità può creare, assegnare e pianificare attività, categorizzare le attività e aggiornare lo stato in qualsiasi momento da qualsiasi dispositivo in esecuzione teams.

Per altre informazioni, vedere [gestire l'app attività per l'organizzazione in Microsoft teams](../../manage-tasks-app.md)

### <a name="streamline-approvals-with-the-approvals-app"></a>Semplificare le approvazioni con l'app approvazioni

Usare le [approvazioni](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3) per semplificare tutte le richieste e i processi con il team. Creare, gestire e condividere le approvazioni direttamente dall'hub per il lavoro di gruppo. Avviare un flusso di approvazione dalla stessa posizione in cui si invia una chat, in una conversazione di canale o dall'app approvazioni stessa. Basta selezionare un tipo di approvazione, aggiungere dettagli, allegare file e scegliere responsabili approvazione. Una volta inviati, gli approvatori vengono informati e possono rivedere e agire sulla richiesta.

Puoi consentire l'app approvazioni per l'organizzazione e aggiungerla ai tuoi team. Per ulteriori informazioni sulla gestione delle app, vedere [gestire le app nell'interfaccia di amministrazione di Microsoft teams](../../manage-apps.md).

### <a name="create-manage-and-share-schedules-with-the-shifts-app-and-frontline-worker-integration"></a>Creare, gestire e condividere le pianificazioni con l'app turni e l'integrazione dei lavoratori in prima linea

Microsoft teams si integra con l'app turni e il lavoratore in prima linea, che può essere usato per coordinare le caratteristiche di personale di spostamento e altro ancora. Ad esempio, in turni, gli infermieri responsabili possono configurare e coordinare le pianificazioni per il personale e gli infermieri possono controllare le pianificazioni e scambiare i turni. Teams include un criterio predefinito di configurazione dell'app worker in prima linea che puoi assegnare agli operatori Frontline nell'organizzazione. Per impostazione predefinita, il criterio include le app attività, turni, chat e chiamate. Questo criterio Controlla il comportamento per queste app, ad esempio aggiungendo l'app turni alla barra dell'app in modo che il team possa accedervi rapidamente.

Per altre informazioni, vedere [gestire l'app turni per l'organizzazione in Microsoft teams](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md).

## <a name="help-your-clinical-and-information-workers-get-going-with-teams"></a>Aiutare i dipendenti della clinica e delle informazioni ad andare avanti con i team

Sono disponibili molte risorse per aiutare tutti gli utenti dell'organizzazione a ottenere dimestichezza con l'uso di teams:

- Visitare il [centro adozioni](https://adoption.microsoft.com/microsoft-teams/) per i team per consigli su come stendere teams se si sta appena iniziando il viaggio dell'organizzazione con teams o si espandono team in più aree dell'organizzazione.
- Valutare la possibilità di configurare [percorsi di apprendimento](https://adoption.microsoft.com/microsoft-365-learning-pathways/) personalizzati per gli utenti, in modo da coprire solo le attività che devono svolgere.
- Ottenere assistenza e formazione per gli utenti su come eseguire attività di base in Microsoft Teams nel [sito supporto teams](https://support.microsoft.com/teams), inclusi i [video di formazione rapida](https://support.microsoft.com/office/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7). Questo sito contiene anche assistenza e formazione per le app teams, inclusi [elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db), [attività](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070), [approvazioni](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3), [prenotazioni](https://support.microsoft.com/office/overview-of-the-bookings-app-in-teams-7b8569e1-0c8a-444e-b712-d9968b05110b)e [turni](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821).

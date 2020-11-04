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
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Informazioni sulle caratteristiche di assistenza sanitaria, ad esempio Microsoft teams telehealth, EHR Integration, i FIRSTLINE Worker System Integration e l'app patients.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 7cd05039797f26cd2a6fb3fb93e9b90cc3059651
ms.sourcegitcommit: 43dc627e9fef31a2508f54acf741000551ff68b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2020
ms.locfileid: "48878710"
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

### <a name="create-manage-and-share-schedules-with-the-shifts-app-and-firstline-worker-integration"></a>Creare, gestire e condividere le pianificazioni con l'app turni e l'integrazione di I FIRSTLINE Worker

Microsoft teams si integra con l'app Turns e il lavoratore I Firstline, che può essere usato per coordinare le caratteristiche di personale Shift e altro ancora. Ad esempio, in turni, gli infermieri responsabili possono configurare e coordinare le pianificazioni per il personale e gli infermieri possono controllare le pianificazioni e scambiare i turni. Teams include un criterio predefinito di configurazione dell'app Worker I FIRSTLINE che puoi assegnare a dipendenti di I FIRSTLINE nell'organizzazione. Per impostazione predefinita, il criterio include le app attività, turni, chat e chiamate. Questo criterio Controlla il comportamento per queste app, ad esempio aggiungendo l'app turni alla barra dell'app in modo che il team possa accedervi rapidamente.

Per altre informazioni, vedere [gestire l'app turni per l'organizzazione in Microsoft teams](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md).

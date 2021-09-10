---
title: Guida introduttiva a Teams per le organizzazioni del settore sanitario
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
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-overview
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Scopri le funzionalità di assistenza sanitaria come la telemedicina di Microsoft Teams, l’integrazione CCE, l'integrazione del sistema di personale in prima linea e l'app Pazienti.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 0fa0976c4e69f205feda03a4047a6bbcb26b1183
ms.sourcegitcommit: 69a5d4994ef75b9c16efa99554fb7f2ee1ccf52a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2021
ms.locfileid: "58972904"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a>Guida introduttiva a Teams per le organizzazioni del settore sanitario

Microsoft Teams offre una serie di funzionalità di telemedicina utili per ospedali e altre organizzazioni sanitarie. Le funzionalità di Teams sono in fase di sviluppo per aiutare gli ospedali con:

- Integrazione di visite virtuali e cartelle cliniche elettroniche (CCE)
- Pacchetti di criteri per Teams
- Messaggistica protetta
- Modelli di Teams
- Coordinamento sanitario e collaborazione

Questa funzionalità fa parte di Microsoft Cloud per il Settore Sanitario. Ulteriori informazioni sull'utilizzo di questa soluzione, che riunisce le funzionalità di Azure, Dynamics 365 e Microsoft 365 su[Microsoft Cloud per il Settore Sanitario](/industry/healthcare).

Guarda il video per ulteriori informazioni sull'utilizzo dell’insieme di dati sanitari per migliorare la collaborazione del team sanitario in Microsoft Teams.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hqan]

> [!NOTE]
> Il contenuto di questa sezione presuppone che tu abbia già implementato Teams nella tua organizzazione. Qualora non lo avessi ancora fatto, inizia a leggere [Come implementare Microsoft Teams](../../deploy-overview.md).

I seguenti scenari sono disponibili per le organizzazioni sanitarie:

| Scenario | Descrizione | Requisiti |
| -------- | -------- | -------- |
| [Integrazione di visite virtuali e cartelle cliniche elettroniche (CCE)](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | Pianifica, gestisci e conduci visite virtuali con i pazienti. Questo scenario collega Microsoft Teams e la piattaforma Epic per supportare le visite virtuali. | Abbonamento attivo a Microsoft Cloud per il Settore Sanitario o abbonamento all'offerta autonoma del connettore CCE di Microsoft Teams. <br> Gli utenti devono disporre di una licenza Microsoft 365 o Office 365 appropriata che includa riunioni di Microsoft Teams *. <br> Le organizzazioni devono avere la versione Epic di novembre 2018 o successiva. <br>[Dettagli per i requisiti CCE](ehr-admin.md#before-you-begin) |
| [Visite virtuali con Microsoft Bookings e l’app Bookings](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | Pianifica, gestisci e conduci visite virtuali con i pazienti. Questo scenario si basa su Microsoft Bookings per supportare le visite virtuali. | Microsoft Bookings deve essere attivato per l'organizzazione. <br> Tutti gli utenti dell'app Bookings e tutto il personale che partecipa alle riunioni devono disporre di una licenza che supporti la pianificazione delle riunioni di Teams *. <br>[Dettagli per i requisiti di Bookings](../../bookings-app-admin.md#prerequisites-for-using-the-bookings-app-in-teams)|
| [Pacchetti di criteri di Teams](#teams-policy-packages)| Garantire che gli operatori clinici, gli operatori dell'informazione e i dispositivi delle stanze dei pazienti abbiano l'accesso appropriato alla funzionalità di Teams.| L'utente deve disporre di una licenza appropriata*. |
| [Messaggistica protetta](#secure-messaging) | Attenzione più rapida ai messaggi urgenti e sicurezza che il messaggio sia stato ricevuto e letto. | L'utente deve disporre di una licenza appropriata*.  |
| [Modelli di Teams](#teams-templates-for-healthcare-organizations) | Crea team che includano un modello predefinito di impostazioni, canali e app preinstallate per la comunicazione e la collaborazione all'interno di un reparto o tra più reparti in un ospedale. | L'utente deve disporre di una licenza appropriata*.  |
| [Coordinamento sanitario e collaborazione](#care-coordination-and-collaboration) | I medici e il personale possono collaborare internamente su programmi, documenti, attività e così via.| L'utente deve disporre di una licenza appropriata*. |

*Office 365 A3, A5, E3, E5, F1, F3, Microsoft 365 A3, A5, E3 ed E5, Business Standard sono supportati. Per altre informazioni sull'assegnazione di una licenza generale di Teams, vedere [Gestire l'accesso degli utenti a Teams](../../user-access.md).

## <a name="virtual-visits-and-electronic-healthcare-record-ehr-integration"></a>Integrazione di visite virtuali e cartelle cliniche elettroniche (CCE)

Utilizza la piattaforma completa per riunioni in Microsoft Teams per pianificare, gestire e condurre visite virtuali con i pazienti.

- Se la tua organizzazione utilizza già Cartella clinica elettronica o CCE, puoi integrare Microsoft Teams per un'esperienza più fluida. Il connettore CCE (cartella clinica elettronica) di Microsoft Teams consente al personale medico di avviare una visita o un consulto virtuale con un altro provider in Teams direttamente dal sistema CCE. Per ulteriori informazioni, [Visite virtuali con Teams - Integrazione in CCE](ehr-admin.md).
- Se non usi una cartella clinica elettronica supportata, puoi usare Microsoft Bookings e l'app Bookings in Teams. Per altre informazioni, vedere [Visite virtuali con Teams e l'app Bookings.](../bookings-virtual-visits.md)

![Visite virtuali con Microsoft Teams.](../../media/virtual-visits-teams.png)

## <a name="teams-policy-packages"></a>Pacchetti di criteri per Teams

Applicare i pacchetti di criteri di Teams per definire i compiti dei diversi ruoli in Teams. Ad esempio, specificare i criteri per:

- Operatori sanitari, ad esempio infermieri, caposala, medici e operatori sociali in modo che abbiano accesso completo alle chat, alle chiamate, alla gestione dei turni e alle riunioni.
- Operatori dell'informazione nella tua organizzazione sanitaria, ad esempio personale in ambito IT e finanziario e responsabili della conformità possono avere accesso completo alle chat, alle chiamate e alle riunioni.
- Stanze dei pazienti, per controllare le impostazioni dei dispositivi nelle stanze dei pazienti.

Per ulteriori informazioni, [Pacchetti di criteri di Teams per il settore sanitario](../../policy-packages-healthcare.md).

## <a name="secure-messaging"></a>Messaggistica protetta

La messaggistica sicura supporta la collaborazione all'interno dei team sanitari, incluse diverse nuove funzionalità:

- Il mittente di un messaggio può impostare una priorità speciale per il proprio messaggio, in modo che il destinatario riceva ripetutamente una notifica finché non legge il messaggio.
- Il mittente di un messaggio può richiedere una conferma di lettura, in modo che venga avvisato quando un messaggio che ha inviato è stato letto dal destinatario del messaggio.

Queste funzionalità forniscono attenzione più rapida ai messaggi urgenti e sicurezza che il messaggio sia stato ricevuto e letto. È possibile creare nuovi team sanitari che utilizzano queste funzionalità a seconda del paziente. Queste funzionalità sono basate su criteri e possono essere assegnate a singoli o interi team.

Per ulteriori informazioni,[Guida introduttiva a Messaggistica protetta per le organizzazioni del settore sanitario](messaging-policies-hc.md).

In relazione alla messaggistica sicura esiste la possibilità di avere altri tenant federati da organizzazioni sanitarie, consentendo una comunicazione migliore tra tenant. (Vedere [Gestire l'accesso esterno (federazione) in Microsoft Teams](../../manage-external-access.md)).

## <a name="teams-templates-for-healthcare-organizations"></a>Modelli di Teams per le organizzazioni del settore sanitario

Sono stati sviluppati nuovi modelli per Teams da applicare a un ambiente ospedaliero e ne sono previsti altri. Ciò semplifica la creazione di team che gli operatori sanitari utilizzano per coordinare l'assistenza ai pazienti in vari reparti o corsie. Per ulteriori informazioni,[Guida introduttiva ai modelli di Teams per le organizzazioni del settore sanitario](./healthcare-templates-admin-console.md). È possibile avviare Teams per reparti interni come cardiologia o reparti di assistenza, e altri modelli sono in fase di sviluppo.

## <a name="care-coordination-and-collaboration"></a>Coordinamento sanitario e collaborazione

Riunisci il tuo team sanitario per coordinare l'assistenza e collaborare con Microsoft Teams.

![Assistenza sanitaria: collaborare con il team sanitario in Teams.](../../media/teams-healthcare-collaborate-in-teams.png)

Microsoft Teams consente a medici, infermieri e altro personale di collaborare in modo efficiente con le funzionalità di collaborazione incluse in Microsoft Teams, come:

- Crea team e canali per i team sanitari e gli operatori dell'informazione. Usa i canali con le schede come metodo per strutturare il loro lavoro, con ulteriore aiuto dalle schede in cui potranno bloccare fonti di informazioni.
- Chatta, pubblica messaggi e comunica. Il tuo team può avere conversazioni permanenti su diversi pazienti bisognosi di attenzioni.
- Chiama e organizza riunioni con i membri del team sanitario. Configura le riunioni individuali o usa le riunioni del canale per gestire le riunioni quotidiane, con l'efficacia delle funzionalità audio, video, di condivisione dello schermo, registrazione e trascrizione di Teams.
- Archivia e condividi file e documenti. Il team sanitario fa parte di un unico team virtualizzato che lavora e collabora ai documenti di Office.

Inoltre, il tuo team può usare le app in Teams per:

- Condividi elenchi e traccia le informazioni con l'app Elenchi
- Tieni traccia e monitora le attività con l'app Tasks
- Semplifica le approvazioni con l'app Approvazioni
- Crea, gestisci e condividi pianificazioni con l'app Turni

### <a name="share-lists-and-track-information-with-the-lists-app"></a>Condividi elenchi e traccia le informazioni con l'app Elenchi

> [!NOTE]
> A partire dal 30 ottobre 2020, l'app Pazienti è stata ritirata e sostituita dall’app [Elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams. Con Elenchi, i team di assistenza della tua organizzazione sanitaria possono creare elenchi di pazienti per scenari che vanno da turni e riunioni di team interdisciplinari al monitoraggio generale dei pazienti.

L'app Elenchi in Teams consente ai team di tenere traccia delle informazioni e organizzare il lavoro. L’app è preinstallata per tutti gli utenti di Teams ed è disponibile come scheda in ogni team e canale. Gli elenchi possono essere creati da zero, da modelli predefiniti o importando dati in Excel.

I team sanitari possono utilizzare il modello Pazienti per iniziare. Possono creare elenchi per tenere traccia delle esigenze e dello stato dei pazienti. I dati dei pazienti esistenti su fogli di calcolo Excel possono essere importati per creare un elenco in Teams. Questi elenchi possono essere utilizzati per scenari come turni e monitoraggio del paziente per coordinare l'assistenza.

Ad esempio, un'infermiera caposala crea un elenco di pazienti in un team che include tutti i membri del team sanitario. Durante i turni, i membri del team sanitario accedono a Teams sui propri dispositivi mobili e aggiornano le informazioni sui pazienti nell'elenco che tutti i membri del team possono visualizzare per rimanere aggiornati. Durante le riunioni multidisciplinari in cui il team discute e valuta i parametri delle prestazioni sanitarie principali per assicurarsi che i pazienti proseguano lungo il percorso per la dimissione, i membri possono condividere le informazioni con Teams su uno schermo di grandi dimensioni. I membri del team sanitario che non sono presenti possono partecipare in remoto.

Di seguito è riportato un elenco di esempio impostato per il giro visite dei pazienti.

:::image type="content" source="../../media/lists-patients-example.png" alt-text="Screenshot dell'elenco di esempio per l'arrotondamento dei pazienti.":::

Ulteriori informazioni su [Gestire l'app Elenchi per l'organizzazione in Teams](../../manage-lists-app.md).

### <a name="track-and-monitor-tasks-with-the-tasks-app"></a>Tieni traccia e monitora le attività con l'app Tasks

Usare [Tasks](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070) in Teams per monitorare le cose da fare per il team sanitario. Il tuo team sanitario può creare, assegnare e pianificare attività, classificare attività e aggiornare lo stato in qualsiasi momento, da qualsiasi dispositivo che esegue Teams. I professionisti e gli amministratori IT possono anche pubblicare attività in team specifici per l'organizzazione. Ad esempio, si potrebbero pubblicare una serie di attività per i nuovi protocolli di sicurezza o un nuovo passaggio per l'assunzione da usare in ospedale.

Per ulteriori informazioni vedere [Gestire l'app Tasks per l'organizzazione in Microsoft Teams](../../manage-tasks-app.md)

### <a name="streamline-approvals-with-the-approvals-app"></a>Semplifica le approvazioni con l'app Approvazioni

Usa [Approvazioni](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3) per semplificare tutte le richieste e i processi del team. Crea, gestisci e condividi le approvazioni direttamente dal tuo hub per il lavoro di squadra. Avvia un flusso di approvazione dallo stesso punto in cui invii una chat, in una conversazione del canale o dall'app Approvazioni stessa. Basta selezionare un tipo di approvazione, aggiungere dettagli, allegare file e scegliere gli approvatori. Una volta inviata, gli approvatori ricevono una notifica e possono verificare e agire in base alla richiesta.

Puoi consentire l'app Approvazioni per la tua organizzazione e aggiungerla ai team. Per ulteriori informazioni vedere [Disponibilità dell'app Approvazioni in Teams](../../approval-admin.md).

### <a name="create-manage-and-share-schedules-with-the-shifts-app-and-frontline-worker-integration"></a>Crea, gestisci e condividi pianificazioni con l'app Turni e l’integrazione personale sul campo

Microsoft Teams si integra con l'app Turni e Personale Sul Campo, che possono essere utilizzati per coordinare le funzionalità del personale su turni e altro ancora. Ad esempio, in Turni, i caposala possono impostare e coordinare i programmi per il proprio personale e gli infermieri possono controllare i programmi e scambiare i turni. Teams include un criterio predefinito di configurazione dell’app per operatori sul campo che è possibile assegnare agli operatori sul campo dell’organizzazione. Per impostazione predefinita, il criterio include le app Attività, Turni, Chat e Chiamate. Questo criterio controlla il comportamento di queste app, ad esempio, aggiungendo l'app Turni alla barra delle app in modo che il team possa accedervi rapidamente.

Per ulteriori informazioni vedere [Gestire l'app Turni per l'organizzazione in Microsoft Teams](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md).

## <a name="help-your-clinical-and-information-workers-get-going-with-teams"></a>Aiuta i tuoi operatori clinici e delle informazioni ad usare Teams

Sono disponibili molte risorse per aiutare tutti gli utenti dell'organizzazione a familiarizzare con l'utilizzo di Team:

- Visita il [centro adozione Teams](https://adoption.microsoft.com/microsoft-teams/) per consigli sull'implementazione di Teams se stai iniziando a usare Teams con la tua organizzazione o stai espandendo Teams in più aree della tua organizzazione.
- Considera l'idea di impostare [percorsi di apprendimento personalizzati](https://adoption.microsoft.com/microsoft-365-learning-pathways/)per gli utenti per coprire solo le attività che devono svolgere.
- Ottieni assistenza e formazione per i tuoi utenti su come eseguire attività di base in Microsoft Teams su [sito di supporto Teams](https://support.microsoft.com/teams), incluso [video di formazione rapida](https://support.microsoft.com/office/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7). Questo sito offre anche assistenza e formazione per le app Teams, tra cui [Elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db), [Tasks](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070), [Approvazioni](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3), [Bookings](https://support.microsoft.com/office/overview-of-the-bookings-app-in-teams-7b8569e1-0c8a-444e-b712-d9968b05110b), e [Turni](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821).

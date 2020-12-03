---
title: Assegnazioni per Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: jastark
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.assignments.overview
- ms.teamsadmincenter.assignments.tooltip.emaildigest
- ms.teamsadmincenter.assignments.tooltip.makecode
- ms.teamsadmincenter.assignments.tooltip.turnitin
description: Informazioni su come gestire le assegnazioni nell'interfaccia di amministrazione di Microsoft teams per l'istruzione.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: e3a0bf0dd0141679dc89ed1d5ecc0cfc542854c8
ms.sourcegitcommit: 3eb5820b279fc904f34ac4259deeb419e02d832a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561052"
---
# <a name="assignments-in-teams-for-education"></a>Assegnare attività in Teams per l'istruzione

Le assegnazioni sono attività o unità di lavoro assegnate a uno studente o a un membro del team in una classe come parte dello studio. Puoi creare assegnazioni all'interno della classe teams.

Leggi [altre informazioni sulle assegnazioni](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments).

> [!Note]
> Per informazioni dettagliate sulle assegnazioni di Team su piattaforme diverse, vedere [caratteristiche dei team per piattaforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="assignments-in-the-microsoft-teams-admin-center"></a>Assegnazioni nell'interfaccia di amministrazione di Microsoft Teams

Con le impostazioni di amministratore nell'interfaccia di amministrazione di Microsoft teams, è possibile attivare o disattivare le caratteristiche seguenti per essere disponibili per studenti e docenti all'interno dell'organizzazione. Di seguito sono riportate le impostazioni relative alle assegnazioni:

<a name="#bkemaildigest"> </a>
### <a name="weekly-guardian-email-digest"></a>Digest della posta elettronica Guardian settimanale

I messaggi di posta elettronica conterranno informazioni sulle assegnazioni della settimana precedente e per la settimana successiva e verranno inviate durante il fine settimana. Le informazioni sul contenuto della posta elettronica possono essere trovate qui. I messaggi di posta elettronica devono essere configurati e aggiornati dagli amministratori usando [School Data Sync (SDS)](https://docs.microsoft.com/schooldatasync/). Questa funzionalità popola automaticamente le classi per i team con i roster degli studenti dal SIS (Student Information System) della scuola. I passaggi per abilitare questa caratteristica sono i seguenti:

1. Importare le informazioni di contatto padre tramite la sincronizzazione genitore e tutore in SDS. Per istruzioni su come abilitare la sincronizzazione genitore e tutore, vedere [Abilitazione della sincronizzazione genitore e tutore](https://docs.microsoft.com/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync).

2. Attivare l'impostazione Guardian nell'interfaccia di amministrazione di Microsoft teams, perché l'impostazione è disattivata per impostazione predefinita. Ciò consentirà agli insegnanti di inviare un digest settimanale.

   > [!NOTE]
   > Gli insegnanti possono rifiutare l'opt-out del digest deselezionando l'impostazione all'interno del proprio team di classe personale (**Impostazioni assegnazione > messaggi di posta elettronica padre/tutore**).

Per verificare che i genitori ottengano il messaggio di posta elettronica, i tre elementi seguenti devono essere veri:

 - Indirizzo di posta elettronica allegato al profilo studente in SDS e contrassegnati come _padre_ o _tutore_. Per informazioni dettagliate, vedere [formato di file di sincronizzazione padre e tutore](https://docs.microsoft.com/schooldatasync/parent-contact-sync-file-format).

 - Gli studenti appartengono ad almeno una classe in cui il messaggio di posta elettronica non viene disabilitato dall'insegnante nelle [impostazioni di assegnazione](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77).

 - I messaggi di posta elettronica conterranno informazioni sulle assegnazioni che avevano una data di scadenza nella settimana precedente o nella settimana successiva.

Questa impostazione è disinserita per impostazione predefinita.


<a name="bkmakecode"> </a>
### <a name="makecode"></a>MakeCode
Microsoft MakeCode è una piattaforma di codifica basata su blocchi che consente di portare in vita l'informatica per tutti gli studenti. 

MakeCode è un prodotto Microsoft soggetto alle [condizioni d'uso](https://go.microsoft.com/fwlink/?LinkID=206977) e ai criteri di [privacy](https://go.microsoft.com/fwlink/?LinkId=521839) di Microsoft.

Questa impostazione è disinserita per impostazione predefinita. Per abilitare le assegnazioni di MakeCode in teams, nell'interfaccia di **amministrazione di teams** passare alla sezione **assegnazioni** e attivare l'opzione toggle MakeCode **su** attivato. Fare clic su **Salva** e attendere alcune ore per rendere effettive queste impostazioni.

Per altre informazioni sul funzionamento di questa funzionalità, vedere questa [dimostrazione video](https://makecode.com/blog/teams/teams-assignments).

Leggi [altre informazioni su MakeCode](https://aka.ms/makecode).

<a name="#turnitin"> </a>
### <a name="turnitin"></a>Turnitin

Turnitin è un servizio di rilevamento del plagio. Si tratta di un prodotto o un servizio di terze parti soggetto ai propri termini e alla propria politica sulla privacy. L'utente è responsabile dell'uso di prodotti e servizi di terze parti.

Questa impostazione è disinserita per impostazione predefinita.

Per abilitare correttamente Turnitin per l'organizzazione, è necessario avere già un abbonamento a Turnitin. Sarà necessario immettere le informazioni aggiuntive seguenti, che si trovano nella console di amministrazione di Turnitin:

  * **TurnitinApiKey**: questo è un GUID di 32-character trovato nella console di amministrazione in Integrations.
  * **TurnitinApiUrl**: questo è l'URL HTTPS della console di amministrazione di Turnitin.

Ecco alcune istruzioni utili per ottenere queste informazioni.

**TurnitinApiUrl** è l'indirizzo host della console di amministrazione.
Esempio `https://your-tenant-name.turnitin.com`

La console di amministrazione è la posizione in cui è possibile creare un'integrazione e una chiave API associata all'integrazione.

Selezionare **integrazioni** dal menu laterale, quindi fare clic su **Aggiungi integrazione** e assegnare un nome all'integrazione.

![Screenshot che mostra l'aggiunta di una nuova integrazione](./educationImages/Assignments_mopo_turnitin2.png)

Il **TurnitinApiKey** verrà assegnato dopo aver seguito le istruzioni. Copiare la chiave API e incollarla nell'interfaccia di amministrazione di Microsoft teams.  Questa è l'unica volta che è possibile visualizzare la chiave.

![Schermata che mostra la copia della chiave API](./educationImages/Assignments_mopo_turnitin3.png)

Dopo aver fatto clic sul pulsante **Salva** nell'interfaccia di amministrazione per questa impostazione, attendere alcune ore per rendere effettive queste impostazioni.

Pronti per iniziare a usare l'integrazione di Turnitin in teams? Iscriversi al [programma Early Access](https://www.turnitin.com/products/feedback-studio/microsoft-teams-integration).

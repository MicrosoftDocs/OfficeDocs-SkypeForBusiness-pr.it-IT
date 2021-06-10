---
title: Attività per Teams
author: cichur
ms.author: v-cichur
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
description: Informazioni su come gestire le attività nell'Microsoft Teams di amministrazione di Teams per l'istruzione.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 410f5d32dd8af4775639a080725cd5680b6a70c2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121374"
---
# <a name="assignments-in-teams-for-education"></a>Assegnare attività in Teams per l'istruzione

Le funzionalità Attività e voti in Teams per l'istruzione consentono ai docenti di assegnare attività, lavoro o quiz agli studenti. I docenti possono gestire le sequenze temporali delle assegnazioni, le istruzioni, aggiungere risorse per l'assegnazione, classificare con le rubriche e altro ancora. Possono anche tenere traccia dello stato di avanzamento della classe e dei singoli studenti nella scheda Voti.

[Altre informazioni su Attività e voti in Teams per l'istruzione.](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)

> [!Note]
> Per informazioni dettagliate Teams attività su piattaforme diverse, vedere Teams [funzionalità per piattaforma.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a>Integrazioni di assegnazioni nell'interfaccia Microsoft Teams di amministrazione

Usando le impostazioni di amministrazione nell'Microsoft Teams di amministrazione, è possibile attivare o disattivare le funzionalità per i docenti all'interno dell'organizzazione e per i loro studenti. Di seguito sono riportate le impostazioni relative alle attività:

<a name="#bkemaildigest"> </a>
### <a name="weekly-guardian-email-digest"></a>Digest della posta elettronica del tutore settimanale


I messaggi di posta elettronica dei tutori vengono inviati ogni fine settimana a genitori o tutori. Il messaggio di posta elettronica contiene informazioni sulle attività della settimana precedente e della settimana successiva. La sincronizzazione padre e tutore può essere impostata [usando School Data Sync.](/schooldatasync/parent-contact-sync)

1. Importare le informazioni sul contatto padre tramite Parent e Guardian Sync in SDS. Per istruzioni su come abilitare la sincronizzazione padre e tutore, vedere [Abilitazione della sincronizzazione padre e tutore.](/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync)

2. Attivare l'impostazione Guardiano nell'Microsoft Teams di amministrazione, perché l'impostazione è disattivata per impostazione predefinita. In questo modo gli insegnanti potranno inviare un riepilogo settimanale.

   > [!NOTE]
   > Gli insegnanti possono rifiutare esplicitamente il digest deselezionando l'impostazione all'interno del proprio team di classe personale ( Attività Impostazioni >**e-mail genitori/tutori**).

Per verificare che genitori otterrà il messaggio di posta elettronica, i tre elementi seguenti devono essere veri:

 - Indirizzo di posta elettronica allegato al profilo dello studente in SDS e contrassegnato _come_ genitore o _tutore._ Per informazioni dettagliate, vedere [Parent and Guardian Sync File Format](/schooldatasync/parent-contact-sync-file-format).

 - Gli studenti appartengono ad almeno una classe in cui la posta elettronica non è disabilitata dal docente nelle [impostazioni dell'attività.](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)

 - I messaggi di posta elettronica conterranno informazioni sulle attività che hanno una data di scadenza nella settimana precedente o nella settimana successiva.

L'impostazione predefinita per questa funzionalità è - **Disattivato.**


<a name="bkmakecode"> </a>
### <a name="makecode"></a>MakeCode
Microsoft MakeCode è una piattaforma di codifica basata su blocchi che dà vita all'informatica per tutti gli studenti. 

MakeCode è un prodotto Microsoft soggetto alle condizioni per l'uso [e](https://go.microsoft.com/fwlink/?LinkID=206977) alle condizioni [di privacy](https://go.microsoft.com/fwlink/?LinkId=521839) Microsoft.

L'impostazione predefinita per questa funzionalità è - **Disattivato.**

Per abilitare le assegnazioni MakeCode in Teams, passare all'interfaccia di  amministrazione di **Teams**, passare alla sezione Attività e impostare l'interruttore MakeCode su **Attivato**. Fare clic su **Salva**. Consentire l'applicazione di queste impostazioni per alcune ore.

Per altre informazioni sul funzionamento di questa funzionalità, vedere questa [dimostrazione video.](https://makecode.com/blog/teams/teams-assignments)

[Altre informazioni su MakeCode](https://aka.ms/makecode).

<a name="#turnitin"> </a>
### <a name="turnitin"></a>Turnitin

[Turnitin è](https://www.turnitin.com/) un servizio di integrità accademica. Si tratta di un prodotto o servizio di terze parti soggetto alle proprie condizioni e all'informativa sulla privacy. L'utente è responsabile dell'uso di prodotti e servizi di terze parti.

L'impostazione predefinita per questa caratteristica è - **Disattivato.**

Per abilitare Turnitin per l'organizzazione, è necessario un abbonamento Turnitin. È quindi possibile immettere le informazioni seguenti, disponibili nella console di amministrazione di Turnitin:

  * **TurnitinApiKey:** GUID di 32 caratteri trovato nella console di amministrazione in Integrazioni.
  * **TurnitinApiUrl:** URL HTTPS della console di amministrazione di Turnitin.

Ecco alcune istruzioni per ottenere queste informazioni.

**TurnitinApiUrl è** l'indirizzo host della console di amministrazione.
Esempio: `https://your-tenant-name.turnitin.com`

La console di amministrazione consente di creare un'integrazione e una chiave API associata all'integrazione.

Selezionare **Integrazioni** dal menu laterale, quindi selezionare **Aggiungi** integrazione e assegnare un nome all'integrazione.

![Screenshot che mostra l'aggiunta di una nuova integrazione](./educationImages/Assignments_mopo_turnitin2.png)

**L'oggetto TurnitinApiKey** verrà assegnato dopo aver seguito le istruzioni visualizzate. Copiare la chiave API e incollarla nell'Microsoft Teams di amministrazione.  Questa è l'unica volta in cui è possibile visualizzare la chiave.

![Screenshot che mostra la copia della chiave API](./educationImages/Assignments_mopo_turnitin3.png)

Dopo aver fatto **clic sul pulsante** Salva nell'interfaccia di amministrazione per questa impostazione, consentire l'applicazione di queste impostazioni per alcune ore.
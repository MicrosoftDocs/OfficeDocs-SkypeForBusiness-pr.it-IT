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
description: Informazioni su come gestire le attività nell'interfaccia di amministrazione di Microsoft Teams in Teams for Education.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: f283a4fb2d49778f4b0e8b31f46dada46f900e6f
ms.sourcegitcommit: 07afc959fec802db583e7111280d0035fdb6e412
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616910"
---
# <a name="assignments-in-teams-for-education"></a>Assegnare attività in Teams per l'istruzione

Le funzionalità Attività e voti in Teams per l'istruzione consentono ai docenti di assegnare attività, lavoro o quiz agli studenti. I docenti possono gestire le tempistiche delle attività, le istruzioni, aggiungere risorse per la consezione, valutarlo con le rubriche e altro ancora. Possono anche tenere traccia dei progressi della classe e dei singoli studenti nella scheda Voti.

[Altre informazioni sulle attività e i voti in Teams per l'istruzione.](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)

> [!Note]
> Per i dettagli sulle attività di Teams su piattaforme diverse, vedi le [funzionalità di Teams per piattaforma.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a>Integrazioni delle assegnazioni nell'interfaccia di amministrazione di Microsoft Teams

Utilizzando le impostazioni di amministrazione nell'interfaccia di amministrazione di Microsoft Teams, è possibile attivare o disattivare le funzionalità per i docenti all'interno dell'organizzazione e dei loro studenti. Di seguito sono riportate le impostazioni relative alle attività:

<a name="#bkemaildigest"> </a>
### <a name="weekly-guardian-email-digest"></a>Riepilogo settimanale della posta elettronica per tutore


I messaggi di posta elettronica per tutori vengono inviati ogni fine settimana a genitori o tutori. Il messaggio contiene informazioni sulle assegnazioni della settimana precedente e della settimana successiva. La sincronizzazione per genitori e tutori può essere impostata [con School Data Sync.](https://docs.microsoft.com/schooldatasync/parent-contact-sync)

1. Importare le informazioni sul contatto padre tramite Sincronizzazione per genitori e tutori in SDS. Per istruzioni su come abilitare la sincronizzazione per genitori e tutori, vedere Abilitare la sincronizzazione per genitori [e tutori.](https://docs.microsoft.com/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync)

2. Attivare l'impostazione per i tutori nell'interfaccia di amministrazione di Microsoft Teams, perché l'impostazione è disattivata per impostazione predefinita. In questo modo gli insegnanti potranno inviare un riepilogo settimanale.

   > [!NOTE]
   > I docenti possono rifiutare esplicitamente il digest deselezionando l'impostazione all'interno del proprio team di classe personale ( Impostazioni attività > messaggi di posta elettronica per **genitori/tutori).**

Per verificare che Genitori otterrà l'e-mail, i tre elementi seguenti devono essere veri:

 - Indirizzo di posta elettronica allegato al profilo dello studente in SDS e contrassegnato come _genitore_ o _tutore._ Per informazioni dettagliate, vedere Il formato di file di sincronizzazione per genitori [e tutori.](https://docs.microsoft.com/schooldatasync/parent-contact-sync-file-format)

 - Gli studenti appartengono ad almeno una classe in cui la posta elettronica non viene disabilitata dall'insegnante nelle [impostazioni dell'attività.](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)

 - I messaggi di posta elettronica conterranno informazioni sulle attività che avevano una data di scadenza nella settimana precedente o nella prossima settimana.

L'impostazione predefinita per questa funzionalità è - **Disattivato.**


<a name="bkmakecode"> </a>
### <a name="makecode"></a>MakeCode
Microsoft MakeCode è una piattaforma di codifica basata su blocchi che dà vita all'informatica per tutti gli studenti. 

MakeCode è un prodotto Microsoft soggetto [](https://go.microsoft.com/fwlink/?LinkID=206977) alle condizioni per l'utilizzo e all'informativa [sulla privacy](https://go.microsoft.com/fwlink/?LinkId=521839) di Microsoft.

L'impostazione predefinita per questa funzionalità è - **Disattivato.**

Per abilitare le attività MakeCode in Teams, vai all'interfaccia di amministrazione di **Teams,** passa alla sezione Attività e attiva l'opzione  MakeCode.  Fare clic su **Salva**. Impostare alcune ore per l'applicazione di queste impostazioni.

Per altre informazioni sul funzionamento di questa funzionalità, vedere questa [dimostrazione video.](https://makecode.com/blog/teams/teams-assignments)

[Altre informazioni su MakeCode.](https://aka.ms/makecode)

<a name="#turnitin"> </a>
### <a name="turnitin"></a>Turnitin

[Turnitin è un](https://www.turnitin.com/) servizio di integrità accademica. Si tratta di un prodotto o servizio di terze parti soggetto alle proprie condizioni e all'informativa sulla privacy. L'utente è responsabile dell'uso di prodotti e servizi di terze parti.

L'impostazione predefinita per questa funzionalità è - **Disattivato**..

Per abilitare Turnitin per l'organizzazione, è necessario un abbonamento Turnitin. È quindi possibile immettere le informazioni seguenti, disponibili nella console di amministrazione Turnitin:

  * **TurnitinApiKey:** GUID di 32 caratteri trovato nella console di amministrazione in Integrazioni.
  * **TurnitinApiUrl:** URL HTTPS della console di amministrazione Turnitin.

Ecco alcune istruzioni per ottenere queste informazioni.

**TurnitinApiUrl è** l'indirizzo host della console di amministrazione.
Esempio: `https://your-tenant-name.turnitin.com`

La console di amministrazione consente di creare un'integrazione e una chiave API associata all'integrazione.

Selezionare **Integrazioni dal** menu laterale, quindi selezionare **Aggiungi** integrazione e assegnare un nome all'integrazione.

![Screenshot che mostra l'aggiunta di una nuova integrazione](./educationImages/Assignments_mopo_turnitin2.png)

La **chiave TurnitinApiKey** verrà visualizzata dopo aver seguito le istruzioni visualizzate. Copiare la chiave API e incollarla nell'interfaccia di amministrazione di Microsoft Teams.  Questa è l'unica volta che puoi visualizzare il codice.

![Screenshot che mostra la copia della chiave API](./educationImages/Assignments_mopo_turnitin3.png)

Dopo aver fatto **clic sul** pulsante Salva nell'interfaccia di amministrazione per questa impostazione, è possibile impostare l'applicazione di queste impostazioni per alcune ore.


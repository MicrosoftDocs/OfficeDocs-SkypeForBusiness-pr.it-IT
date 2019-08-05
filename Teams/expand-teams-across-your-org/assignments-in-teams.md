---
title: Assegnazioni per Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: jastark
f1keywords: ms.teamsadmincenter.assignments.overview
description: Informazioni su come gestire le assegnazioni nell'interfaccia di amministrazione di Microsoft teams per l'istruzione.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1c29f703994794d75047a260fe5d62deddb2d937
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2019
ms.locfileid: "36184297"
---
# <a name="assignments-in-teams-for-education"></a>Assegnazioni in teams per l'istruzione

Le assegnazioni sono attività o unità di lavoro assegnate a uno studente o a un membro del team in una classe come parte dello studio. Puoi creare assegnazioni all'interno della classe teams.

[Ulteriori informazioni sulle assegnazioni](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)

## <a name="assignments-in-the-microsoft-teams-admin-center"></a>Assegnazioni nell'interfaccia di amministrazione di Microsoft Teams

Con le impostazioni di amministratore nell'interfaccia di amministrazione di Microsoft teams è possibile attivare o disattivare le caratteristiche seguenti per essere disponibili per studenti e docenti all'interno dell'organizzazione. Di seguito sono riportate le impostazioni relative alle assegnazioni:

<a name="#bkemaildigest"> </a>
### <a name="weekly-guardian-email-digest"></a>Digest della posta elettronica Guardian settimanale
[!INCLUDE [preview-feature](../includes/preview-feature.md)]

I messaggi di posta elettronica Guardian sono inviati settimanalmente ai genitori o ai tutori degli studenti. I messaggi di posta elettronica conterranno informazioni sulle assegnazioni della settimana precedente e per la settimana successiva e verranno inviate durante il fine settimana. I messaggi di posta elettronica devono essere aggiornati dagli amministratori tramite la funzionalità School Data Sync.

Questa impostazione è disinserita per impostazione predefinita.

<a name="bkmakecode"> </a>
### <a name="makecode"></a>MakeCode
MakeCode è una piattaforma di codifica basata su blocchi che consente di portare in vita l'informatica per tutti gli studenti. 

Si tratta di un prodotto o un servizio di terze parti soggetto ai propri termini e alla propria politica sulla privacy. L'utente è responsabile dell'uso di prodotti e servizi di terze parti.

Questa impostazione è disinserita per impostazione predefinita.

[Leggi altre informazioni su MakeCode](https://www.microsoft.com/makecode)

<a name="#turnitin"> </a>
### <a name="turnitin"></a>Turnitin
[!INCLUDE [preview-feature](../includes/preview-feature.md)]

Turnitin è un servizio di rilevamento del plagio. Si tratta di un prodotto o un servizio di terze parti soggetto ai propri termini e alla propria politica sulla privacy. L'utente è responsabile dell'uso di prodotti e servizi di terze parti.

Questa impostazione è disinserita per impostazione predefinita.

Per abilitare correttamente Turnitin per l'organizzazione, è necessario avere già un abbonamento a Turnitin. Sarà necessario immettere le informazioni aggiuntive seguenti, che si trovano nella console di amministrazione di Turnitin:

  * _TurnitinApiKey_: questo è un GUID di 32-character trovato nella console di amministrazione in Integrations.
  * _TurnitinApiUrl_: questo è l'URL HTTPS della console di amministrazione di Turnitin.

Ecco alcune istruzioni utili per ottenere queste informazioni.

TurnitinApiUrl è l'indirizzo host della console di amministrazione.
Esempio. `https://your-tenant-name.turnitin.com`

La console di amministrazione è la posizione in cui è possibile creare un'integrazione e una chiave API associata all'integrazione.

Selezionare **integrazioni** dal menu laterale, quindi fare clic su **Aggiungi integrazione** e assegnare un nome all'integrazione.
![Screenshot che mostra l'aggiunta di una nuova integrazione](./educationImages/Assignments_mopo_turnitin2.png)

Il TurnitinApiKey verrà assegnato dopo aver seguito le istruzioni. Copiare la chiave API e incollarla nell'interfaccia di amministrazione di Microsoft teams.  Questa è l'unica volta che è possibile visualizzare la chiave.
![Screenshot che Mostra come copiare la chiave API](./educationImages/Assignments_mopo_turnitin3.png)

Quando si fa clic sul pulsante **Salva** nell'interfaccia di amministrazione per questa impostazione, consentire fino a 24 ore per rendere effettive queste impostazioni.

[Leggi altre informazioni sull'integrazione tra Turnitin e Microsoft Teams](https://www.turnitin.com/products/feedback-studio/microsoft-teams-integration)

[Leggi altre informazioni su Turnitin](https://www.turnitin.com/)

---
title: Usa i modelli di team finanziari
author: lanachin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: yinchang
ms.collection:
- M365-collaboration
ms.localizationpriority: high
search.appverid: MET150
description: Scopri come gestire e usare i modelli di team finanziari nell'interfaccia di amministrazione di Teams e con Microsoft Graph per creare rapidamente e facilmente team per la tua organizzazione di servizi finanziari.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
- chat-teams-channels-revamp
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4ea67bec0fd8750e32ebb5f65d0258fa7c172a46
ms.sourcegitcommit: 387141880842c93ecf4a936aaa26342a3f996259
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2023
ms.locfileid: "69778946"
---
# <a name="use-financial-team-templates"></a>Usa i modelli di team finanziari

I modelli di Microsoft Teams consentono di creare team in modo rapido e semplice fornendo un modello predefinito di impostazioni, canali e app preinstallate.

Per le organizzazioni di servizi finanziari, i modelli di team possono risultare particolarmente efficaci, in quanto consentono di distribuire rapidamente team omogenei all'interno dell'organizzazione. I modelli aiutano anche il personale a orientarsi nell'uso efficace di Teams.

Teams include modelli sviluppati per le organizzazioni di servizi finanziari. Usa questi modelli predefiniti per creare rapidamente team nei quali il personale può comunicare e collaborare. In questo articolo verranno presentati i modelli di Teams e i consigli su come usarli.

La gestione e l'utilizzo dei modelli di team dipendono dal fatto che si sia amministratori o sviluppatori.

|Se sei: | Allora puoi: |
| ---- | --------- |
| Un amministratore o un professionista IT |[Manage team templates in the Teams admin center](#manage-team-templates-in-the-teams-admin-center). View team templates and apply templates policies to control which templates your staff can use in Teams for creating teams. |
| Uno sviluppatore | [Usare Microsoft Graph](#use-team-templates-with-microsoft-graph) per creare team dai modelli di team. |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Gestire i modelli di team nell’interfaccia di amministrazione di Teams

Gli amministratori possono gestire i modelli di team nell'interfaccia di amministrazione di Microsoft Teams. Qui è possibile visualizzare i dettagli su ogni modello. È anche possibile [creare e assegnare criteri di modelli](templates-policies.md) al personale per controllare i modelli visualizzati in Teams per la creazione di [team](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b).

Per altre informazioni sui modelli di team in generale, vedere Introduzione ai modelli [di team nell'Teams di amministrazione.](get-started-with-teams-templates-in-the-admin-console.md)

Attualmente sono disponibili i seguenti modelli di team predefiniti per le organizzazioni di servizi finanziari. Per visualizzarli, nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Teams passare a **modelli di teams** > **Team**.

### <a name="bank-branch"></a>Bank Branch

Centralizza la collaborazione dei dipendenti della tua filiale bancaria con riunioni informali, riunioni con i clienti, processi aziendali come la collaborazione sui mutui, e comunica con loro tramite annunci e complimenti.

>[!div class="mx-tdBreakAll"]
>| Tipo di modello |TemplateId| Proprietà del modello |
>| ------------------ |--|----------------------------------------------------- |
>|Bank Branch| `com.microsoft.teams.template.CollaborateWithinABankBranch`|Canali: <ul><li>Generale<li>Annunci</li><li>Briefing</li><li>Riunioni con i clienti</li><li>Richiesta di approvazione </li><li>Coaching</li><li>Sviluppo delle competenze</li><li>Elaborazione del prestito</li><li>Reclami dei clienti</li><li>Complimenti</li><li>Cose divertenti</li><li>Conformità</li></ul>App:<ul><li>Approvazioni</li><li>Bollettini</li><li>Calendario del canale</li><li>Idee per i dipendenti</li><li>Segnalazione problemi</li><li>Complimento</li><li>Turni</li><li>Wiki</li></ul>|

## <a name="use-team-templates-with-microsoft-graph"></a>Usare i modelli di Teams con Microsoft Graph

Developers can use Microsoft Graph to create teams from pre-built team templates. To learn more about using team templates with Microsoft Graph, see [Get started with team templates using Microsoft Graph](get-started-with-teams-templates.md), [Microsoft Teams API overview](/graph/teams-concept-overview?view=graph-rest-1.0&preserve-view=true), and [teamsTemplate resource type](/graph/api/resources/teamstemplate?view=graph-rest-1.0&preserve-view=true).

### <a name="bank-branch"></a>Bank Branch

Centralizza la collaborazione dei dipendenti della tua filiale bancaria con riunioni informali, riunioni con i clienti, processi aziendali come la collaborazione sui mutui, e comunica con loro tramite annunci e complimenti.

>[!div class="mx-tdBreakAll"]
>| Tipo di modello |TemplateId| Canali del modello |
>| ------------------ |--|----------------------------------------------------- |
>|Bank Branch|`https://graph.microsoft.com/beta/teamsTemplates('CollaborateWithinABankBranch')`|Generale<br>Annunci<br>Briefing<br>Riunioni con i clienti<br>Richiesta di approvazione<br>Coaching<br>Sviluppo delle competenze<br>Elaborazione del prestito<br>Reclami dei clienti<br>Complimenti<br>Cose divertenti<br>Conformità|

> [!NOTE]
> Per altri modelli applicabili all'organizzazione di servizi finanziari, vedere [Modelli predefiniti di team in Microsoft Graph per le piccole e medie imprese.](smb-templates.md)

## <a name="related-articles"></a>Articoli correlati

- [Introduzione ai modelli di team nell'interfaccia Teams di amministrazione](get-started-with-teams-templates-in-the-admin-console.md)
- [Creare un team da un modello](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [Introduzione ai modelli di team con Microsoft Graph](get-started-with-teams-templates.md)
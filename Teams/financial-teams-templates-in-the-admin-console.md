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
appliesto:
- Microsoft Teams
ms.openlocfilehash: 51ec855bc9065bb65c0f6eae14a3e41683cfbc6f
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2021
ms.locfileid: "60046132"
---
# <a name="use-financial-team-templates"></a>Usa i modelli di team finanziari

I modelli di Microsoft Teams consentono di creare team in modo rapido e semplice fornendo un modello predefinito di impostazioni, canali e app preinstallate.

Per le organizzazioni di servizi finanziari, i modelli di team possono risultare particolarmente efficaci, in quanto consentono di distribuire rapidamente team omogenei all'interno dell'organizzazione. I modelli aiutano anche il personale a orientarsi nell'uso efficace di Teams.

Teams include modelli sviluppati per le organizzazioni di servizi finanziari. Usa questi modelli predefiniti per creare rapidamente team nei quali il personale può comunicare e collaborare. In questo articolo verranno presentati i modelli di Teams e i consigli su come usarli.

La gestione e l'utilizzo dei modelli di team dipendono dal fatto che si sia amministratori o sviluppatori.

|Se sei: | Allora puoi: |
| ---- | --------- |
| Un amministratore o un professionista IT |[Gestire i modelli di team nell’interfaccia di amministrazione di Teams](#manage-team-templates-in-the-teams-admin-center): visualizzare i modelli di team e applicare i criteri di modelli per controllare quali modelli possono essere usati in Teams dal personale per la creazione di team. |
| Uno sviluppatore | [Usare Microsoft Graph](#use-team-templates-with-microsoft-graph) per creare team dai modelli di team. |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Gestire i modelli di team nell’interfaccia di amministrazione di Teams

Gli amministratori possono gestire i modelli di team nell'interfaccia di amministrazione di Microsoft Teams. Qui è possibile visualizzare i dettagli su ogni modello. È anche possibile [creare e assegnare criteri di modelli](templates-policies.md) al personale per controllare i modelli visualizzati in Teams per la creazione di [team](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b).

Per altre informazioni sui modelli di team in generale, vedere [Introduzione ai modelli di team nell'interfaccia di amministrazione di Teams](get-started-with-teams-templates-in-the-admin-console.md).

Attualmente sono disponibili i seguenti modelli di team predefiniti per le organizzazioni di servizi finanziari. Per visualizzarli, nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Teams passare a **modelli di teams** > **Team**.

### <a name="collaborate-within-a-bank-branch"></a>Collabora all'interno di una filiale bancaria

Centralizza la collaborazione dei dipendenti della tua filiale bancaria con riunioni informali, riunioni con i clienti, processi aziendali come la collaborazione sui mutui, e comunica con loro tramite annunci e complimenti.

| Tipo di modello |TemplateId| Proprietà incluse nel modello |
| ------------------ |--|----------------------------------------------------- |
|Filiale bancaria| `CollaborateWithinABankBranch`|Canali: <ul><li>Generale<li>Annunci</li><li>Briefing</li><li>Riunioni con i clienti</li><li>Richiesta di approvazioni </li><li>Coaching</li><li>Sviluppo delle competenze</li><li>Elaborazione dei prestiti</li><li>Reclami dei clienti</li><li>Complimenti</li><li>Elementi divertenti</li><li>Conformità</li></ul>App:<ul><li>Complimento </li><li>Segnalazione dei problemi</li><li>Wiki</li><li>Calendario</li><li>Approvazioni</li><li>Bollettini</li><li>Idee</li></ul>|
||||

## <a name="use-team-templates-with-microsoft-graph"></a>Usare i modelli di Teams con Microsoft Graph

Gli sviluppatori possono usare Microsoft Graph per creare team dai modelli di team predefiniti. Per altre informazioni sull'uso dei modelli di team con Microsoft Graph, vedere [Introduzione ai modelli di team con Microsoft Graph](get-started-with-teams-templates.md), [Panoramica dell'API Microsoft Teams](/graph/teams-concept-overview?view=graph-rest-1.0) e [Tipo di risorsa teamsTemplate](/graph/api/resources/teamstemplate?view=graph-rest-1.0).

### <a name="bank-branch"></a>Filiale bancaria

Centralizza la collaborazione dei dipendenti della tua filiale bancaria con riunioni informali, riunioni con i clienti, processi aziendali come la collaborazione sui mutui, e comunica con loro tramite annunci e complimenti.

| Tipo di modello |TemplateId| Canali del modello |
| ------------------ |--|----------------------------------------------------- |
|Filiale bancaria|`https://graph.microsoft.com/beta/teamsTemplates('CollaborateWithinABankBranch')`|Generale<br>Annunci<br>Briefing<br>Riunioni con i clienti<br>Richiesta di approvazioni<br>Coaching<br>Sviluppo delle competenze<br>Elaborazione dei prestiti<br>Reclami dei clienti<br>Complimenti<br>Elementi divertenti<br>Conformità|
||||

> [!NOTE]
> Per altri modelli applicabili all'organizzazione di servizi finanziari, vedere [Modelli predefiniti di team in Microsoft Graph per le piccole e medie imprese.](smb-templates.md)

## <a name="related-articles"></a>Articoli correlati

- [Introduzione ai modelli di team nell'interfaccia Teams di amministrazione](get-started-with-teams-templates-in-the-admin-console.md)
- [Creare un team da un modello](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [Introduzione ai modelli di team con Microsoft Graph](get-started-with-teams-templates.md)
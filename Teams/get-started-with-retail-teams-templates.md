---
title: Usare i modelli di team di vendita al dettaglio
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: yinchang
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
ms.localizationpriority: high
search.appverid: MET150
description: Informazioni su come gestire e usare i modelli di team di vendita al dettaglio nell'interfaccia di amministrazione di Teams e con Microsoft Graph per creare rapidamente e facilmente team per l'organizzazione di vendita al dettaglio.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 69644ce0261d37fb6a7a5e4270a68fb2a79a7d19
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2022
ms.locfileid: "68046916"
---
# <a name="use-retail-team-templates"></a>Usare i modelli di team di vendita al dettaglio

## <a name="overview"></a>Panoramica

I modelli di Microsoft Teams consentono di creare team in modo rapido e semplice fornendo un modello predefinito di impostazioni, canali e app preinstallate.

Per i rivenditori, i modelli di team possono essere particolarmente efficaci, perché consentono di distribuire rapidamente team coerenti all'interno dell'organizzazione. I modelli aiutano anche il personale a orientarsi su come usare in modo efficace Teams.

Teams include modelli progettati appositamente per le esigenze del rivenditore. Usare questi modelli predefiniti per creare rapidamente team in cui il personale può comunicare e collaborare. In questo articolo verranno presentati i modelli di Teams e i consigli su come usarli.

La gestione e l'utilizzo dei modelli di team dipendono dal fatto che si sia amministratori o sviluppatori.

|Se sei: | Allora puoi: |
| ---- | --------- |
| Un amministratore o un professionista IT |[Manage team templates in the Teams admin center](#manage-team-templates-in-the-teams-admin-center). View team templates and apply templates policies to control which templates your staff can use in Teams for creating teams. |
| Uno sviluppatore | [Usare Microsoft Graph](#use-team-templates-with-microsoft-graph) per creare team dai modelli di team. |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Gestire i modelli di team nell’interfaccia di amministrazione di Teams

Gli amministratori possono gestire i modelli di team nell'interfaccia di amministrazione di Microsoft Teams. Qui è possibile visualizzare i dettagli su ogni modello. È anche possibile [creare e assegnare criteri di modelli](templates-policies.md) al personale per controllare i modelli visualizzati in Teams per la creazione di [team](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b).

Per altre informazioni sui modelli di team in generale, vedere Introduzione ai modelli [di team nell'Teams di amministrazione.](get-started-with-teams-templates-in-the-admin-console.md)

Attualmente sono disponibili i modelli di team di vendita al dettaglio predefiniti seguenti. Per visualizzarli, nel riquadro di spostamento sinistro dell'interfaccia Teams di amministrazione passare a modelli **Teams**  >  **team.**

> [!NOTE]
> Un asterisco (*) indica che il modello è *connesso a Microsoft 365*. Quando gli utenti creano un team usando il modello, il modello di SharePoint connesso viene applicato al sito e al team. I componenti di SharePoint, ad esempio pagine, elenchi e integrazioni Power Platform, vengono aggiunti e aggiunti automaticamente come schede al canale Generale nel team. Gli utenti possono modificare queste pagine ed elenchi direttamente da Teams.
>
> Per altre informazioni sui modelli di SharePoint, vedere [Applicare e personalizzare modelli di sito di SharePoint](https://support.microsoft.com/office/apply-and-customize-sharepoint-site-templates-39382463-0e45-4d1b-be27-0e96aeec8398#ID0EDBJ=Team_site_templates).

### <a name="manage-a-store"></a>Gestisci uno Store*

Unisci i tuoi dipendenti in un'unica esperienza centralizzata per gestire attività, condividere documenti e risolvere i problemi correlati ai clienti. Integrare applicazioni aggiuntive per semplificare i processi di inizio e fine del turno.

> [!div class="mx-tdBreakAll"]
>| Tipo di modello |TemplateId | Proprietà del modello |
>| ------------------|-- |----------------------------------------------------- |
>| Gestire uno Store| `retailStore` |Canali: <ul><li>Generale<li>Shift Handoff</li><li>Preparazione negozio</li><li>Apprendimento</li></ul> App: <ul><li>Approvazioni</li><li>Ispezione</li><li>Elenchi<ul><li>Elenco inventario</li></ul></li><li>Pagine SharePoint<ul><li>Il nostro negozio</li></ul></li><li>Turni</li><li>Attività per Planner e To Do</li><li>Wiki</li></ul>|

### <a name="retail-for-managers"></a>Vendita al dettaglio per manager*

Creare un team per un gruppo di responsabili che collabori tra punti vendita o aree geografiche. Ad esempio, se l'organizzazione ha aree geografiche, è possibile creare un team per l'area geografica della California e includere tutti i responsabili negozio in tale area geografica, insieme al responsabile regionale per tale area geografica.

> [!div class="mx-tdBreakAll"]
>| Tipo di modello| TemplateId | Proprietà del modello |
>| ------------------|- |----------------------------------------------------- |
>| Vendita al dettaglio per i manager| `retailManagerCollaboration` |Canali: <ul><li>Generale<li>Operazioni</li><li>Apprendimento</li></ul> App: <ul><li>Approvazioni</li><li>Ispezione</li><li>Pagine SharePoint<ul><li>Il nostro negozio</li></ul></li><li>Attività per Planner e To Do</li><li>Wiki</li></ul>|

## <a name="use-team-templates-with-microsoft-graph"></a>Usare i modelli di Teams con Microsoft Graph

Developers can use Microsoft Graph to create teams from pre-built team templates. To learn more about using team templates with Microsoft Graph, see [Get started with team templates using Microsoft Graph](get-started-with-teams-templates.md), [Microsoft Teams API overview](/graph/teams-concept-overview?view=graph-rest-1.0), and [teamsTemplate resource type](/graph/api/resources/teamstemplate?view=graph-rest-1.0).

Ecco i modelli predefiniti del team di vendita al dettaglio.

> [!NOTE]
> Un asterisco (*) indica che il modello è *connesso a Microsoft 365*. Quando gli utenti creano un team usando il modello, il modello di SharePoint connesso viene applicato al sito e al team. I componenti di SharePoint, ad esempio pagine, elenchi e integrazioni Power Platform, vengono aggiunti e aggiunti automaticamente come schede al canale Generale nel team. Gli utenti possono modificare queste pagine ed elenchi direttamente da Teams.
>
> Per altre informazioni sui modelli di SharePoint, vedere [Applicare e personalizzare modelli di sito di SharePoint](https://support.microsoft.com/office/apply-and-customize-sharepoint-site-templates-39382463-0e45-4d1b-be27-0e96aeec8398#ID0EDBJ=Team_site_templates).

### <a name="manage-a-store"></a>Gestisci uno Store*

Usare questo modello per creare un team per ogni punto vendita al dettaglio dell'organizzazione.

> [!div class="mx-tdBreakAll"]
>| Tipo di modello | TemplateId | Canali del modello |
>| ------------------ | -------------- | ----------------------------------------------------- |
>| Retail - <br>Store | `https://graph.microsoft.com/beta/teamsTemplates('retailStore')`| Canali <ul><li>Generale</li><li>Shift Handoff</li><li>Preparazione negozio</li><li>Apprendimento</li></ul>Proprietà del team <ul><li>Visibilità del team impostata su Public</li></ul> <br>Autorizzazioni dei membri <ul><li>Non è possibile creare, aggiornare o eliminare canali </li><li>Non è possibile aggiungere o rimuovere app </li><li>Non è possibile creare, aggiornare o rimuovere schede</li><li>Non è possibile creare, aggiornare o rimuovere connettori</li><ul>|

Modi consigliati per personalizzare il modello Store per l'organizzazione:

- Se l'organizzazione prevede reparti all'interno di ogni punto vendita, aggiungere un canale per ogni reparto. L'aggiunta di un canale favorisce la comunicazione e la collaborazione all'interno del reparto.

- Se l'organizzazione prevede siti Web interni, ad esempio un sito di SharePoint, è opportuno aggiungerli come schede nel canale del team pertinente.

### <a name="retail-for-managers"></a>Vendita al dettaglio per manager*

Usare questo modello per creare un team per un gruppo di responsabili che possono collaborare in più punti vendita o aree geografiche. Ad esempio, se l'organizzazione ha aree geografiche, è possibile creare un team per l'area geografica della California e includere tutti i responsabili negozio in tale area geografica, insieme al responsabile regionale per tale area geografica.

> [!div class="mx-tdBreakAll"]
>| Tipo di modello | TemplateId | Canali del modello |
>| ------------------ | -------------- | ----------------------------------------------------- |
>| Retail - <br>Collaborazione tra responsabili | `https://graph.microsoft.com/beta/teamsTemplates('retailManagerCollaboration')`| Canali <ul><li>Generale</li><li>Operazioni</li><li>Apprendimento</li></ul>Proprietà del team <ul><li>Visibilità del team impostata su Private</li></ul> <br>Autorizzazioni dei membri <ul><li>Può creare, aggiornare ed eliminare canali </li><li>Può aggiungere e rimuovere app </li><li>Può creare, aggiornare e rimuovere schede</li><li>Può creare, aggiornare e rimuovere connettori</li><ul>|

Modi consigliati per personalizzare il modello Manager Collaboration per l'organizzazione:

- Se l'organizzazione prevede siti Web interni, ad esempio un sito di SharePoint, che sono pertinenti per i responsabili, è opportuno aggiungerli come schede in un canale del team pertinente.

### <a name="how-to-use-team-templates-with-microsoft-graph"></a>Come usare i modelli di team con Microsoft Graph

Per usare questi modelli, modificare la proprietà "template@odata.bind" nel corpo della richiesta da "standard" ai TemplateID precedenti.  Per altre informazioni su come distribuire i modelli di team, vedere l'articolo microsoft Graph su come [creare un team.](/graph/api/team-post?view=graph-rest-beta)

> [!NOTE]
> I canali nel modello verranno creati automaticamente nella scheda **Generale** tab.

### <a name="example-store-template-extension-script"></a>Esempio: script di estensione del modello Store

``` PowerShell
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('retailStore')",
  "DisplayName": "Contoso Store",
  "Description": "Team for all staff in Contoso Store",
  "Channels": [
    {
      "displayName": "Additional store channel",
      "IsFavoriteByDefault": false
    }
  ]
}
```

> [!NOTE]
> Se si usa Microsoft Graph per creare un team da un gruppo o un team di Microsoft 365 esistente usando un modello connesso a Microsoft 365, il modello di SharePoint connesso non viene applicato automaticamente al sito o al team. Sarà necessario applicare manualmente il modello di sito di SharePoint dopo la creazione del team. In Teams, passare al team, selezionare **Altre opzioni** nell'angolo in alto a destra > **Apri in SharePoint**. Quindi scegliere **Impostazioni** > **Applica modello di sito** e selezionare il modello di sito corrispondente.

## <a name="related-articles"></a>Articoli correlati

- [Introduzione ai modelli di team nell'interfaccia Teams di amministrazione](get-started-with-teams-templates-in-the-admin-console.md)
- [Creare un team da un modello](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [Introduzione ai modelli di team con Microsoft Graph](get-started-with-teams-templates.md)
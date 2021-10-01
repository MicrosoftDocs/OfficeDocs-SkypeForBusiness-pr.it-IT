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
ms.openlocfilehash: 2c2bda6467bf819bdf9cf82713c24e8e9cd18d9d
ms.sourcegitcommit: 5eb5acd7910724f7f4a598ecc28b003e5bbe5ea5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "60007796"
---
# <a name="use-retail-team-templates"></a>Usare i modelli di team di vendita al dettaglio

I modelli di Microsoft Teams consentono di creare team in modo rapido e semplice fornendo un modello predefinito di impostazioni, canali e app preinstallate.

Per i rivenditori, i modelli di team possono essere particolarmente efficaci, perché consentono di distribuire rapidamente team coerenti all'interno dell'organizzazione. I modelli aiutano anche il personale a orientarsi su come usare in modo efficace Teams.

Teams include modelli progettati appositamente per le esigenze del rivenditore. Usare questi modelli predefiniti per creare rapidamente team in cui il personale può comunicare e collaborare. In questo articolo verranno presentati i modelli di Teams e i consigli su come usarli.

La gestione e l'utilizzo dei modelli di team dipendono dal fatto che si sia amministratori o sviluppatori.

|Se sei: | Allora puoi: |
| ---- | --------- |
| Un amministratore o un professionista IT |[Gestire i modelli di team nell'interfaccia di amministrazione di Teams](#manage-team-templates-in-the-teams-admin-center). Visualizzare i modelli di team e applicare i criteri di modelli per controllare quali modelli possono essere utilizzati in Teams dal personale per la creazione di team. |
| Uno sviluppatore | [Usare Microsoft Graph](#use-team-templates-with-microsoft-graph) per creare team dai modelli di team. |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Gestire i modelli di team nell’interfaccia di amministrazione di Teams

Gli amministratori possono gestire i modelli di team nell'interfaccia di amministrazione di Microsoft Teams. Qui è possibile visualizzare i dettagli su ogni modello. È anche possibile [creare e assegnare criteri di modelli](templates-policies.md) al personale per controllare i modelli visualizzati in Teams per la creazione di [team](https://support.microsoft.com/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c). 

Per altre informazioni sui modelli di team in generale, vedere Introduzione ai modelli [di team nell'Teams di amministrazione.](get-started-with-teams-templates-in-the-admin-console.md)

Attualmente sono disponibili i modelli di team di vendita al dettaglio predefiniti seguenti. Per visualizzarli, nel riquadro di spostamento sinistro dell'interfaccia Teams di amministrazione passare a modelli **Teams**  >  **team.**

### <a name="organize-a-store"></a>Organizzare un negozio

Unisci i tuoi dipendenti in un'unica esperienza centralizzata per gestire attività, condividere documenti e risolvere i problemi correlati ai clienti. Integra applicazioni aggiuntive per ottimizzare i processi di inizio e fine turno.

| Tipo di modello |TemplateId | Proprietà del modello |
| ------------------|-- |----------------------------------------------------- |
|Organizzare un negozio| `retailStore` |Canali: <ul><li>Generale<li>Passaggio di consegne del turno</li><li>Conformità dello Store<ul><li>Ispezione&sup1;</li></ul></li><li>Apprendimento</li></ul> App: <ul><li>Wiki</li><li>Attività</li><li>Turni</li><li>Ispezione</li></ul>|

&sup1; App aggiunta al canale come scheda

### <a name="manager-collaboration"></a>Collaborazione tra responsabili

Il modello Collaborazione tra responsabili è perfetto per creare un team formato da un gruppo di responsabili e agevolare la loro collaborazione tra negozi/aree geografiche, ecc. Ad esempio, se l'organizzazione è suddivisa in più aree geografiche, si potrebbe creare un team di Collaborazione tra responsabili per l'area californiana e includere tutti gli Store manager in quella regione, come anche gli Area manager di quello Stato.

| Tipo di modello| TemplateId | Proprietà del modello |
| ------------------|- |----------------------------------------------------- |
|Vendita al dettaglio per i responsabili|`retailManagerCollaboration` |Canali: <ul><li>Generale<li>Operazioni<ul><li>Attività (Attività operative)&sup1;</li><li>Ispezione&sup1;</li></ul></li><li>Apprendimento<ul><li>Attività (Learning)&sup1;</li></ul></li></ul> App: <ul><li>Wiki</li><li>Attività</li><li>Ispezione</li></ul>|
||||

&sup1; App aggiunta al canale come scheda

## <a name="use-team-templates-with-microsoft-graph"></a>Usare i modelli di Teams con Microsoft Graph

Gli sviluppatori possono usare Microsoft Graph per creare team da modelli predefiniti di team. Per altre informazioni sull'uso dei modelli di team con Microsoft Graph, vedere Introduzione ai modelli di team con [Microsoft Graph](get-started-with-teams-templates.md), panoramica dell'API [Microsoft Teams](/graph/teams-concept-overview?view=graph-rest-1.0)e tipo di risorsa [teamsTemplate](/graph/api/resources/teamstemplate?view=graph-rest-1.0).

Ecco i modelli predefiniti del team di vendita al dettaglio.

### <a name="store"></a>Store

Il modello Store è ideale per creare un team che rappresenta la sede di un singolo punto vendita per la vendita al dettaglio. Con il modello Store è possibile creare un team per ogni punto vendita per la vendita al dettaglio nell'organizzazione.

| Tipo di modello | TemplateId | Canali del modello |
| ------------------ | -------------- | ----------------------------------------------------- |
| Retail - <br>Store | `https://graph.microsoft.com/beta/teamsTemplates('retailStore')`| Canali <ul><li>Generale</li><li>Maiusc handoff&sup2;</li><li>Conformità dello Store</li><li>Learning&sup2;</li></ul>Proprietà del team <ul><li>Visibilità del team impostata su Public</li></ul> <br>Autorizzazioni dei membri <ul><li>Non è possibile creare, aggiornare o eliminare canali </li><li>Non è possibile aggiungere o rimuovere app </li><li>Non è possibile creare, aggiornare o rimuovere schede</li><li>Non è possibile creare, aggiornare o rimuovere connettori</li><ul>|
||||

&sup2; Canali preferiti automaticamente

Modi consigliati per personalizzare il modello Store per l'organizzazione:

- Se l'organizzazione prevede reparti all'interno di ogni punto vendita, aggiungere un canale per ogni reparto. L'aggiunta di un canale favorisce la comunicazione e la collaborazione all'interno del reparto.

- Se l'organizzazione prevede siti Web interni, ad esempio un sito di SharePoint, è opportuno aggiungerli come schede nel canale del team pertinente.

### <a name="manager-collaboration"></a>Collaborazione tra responsabili

Il modello Collaborazione tra responsabili è perfetto per creare un team formato da un gruppo di responsabili e agevolare la loro collaborazione tra negozi/aree geografiche, ecc. Ad esempio, se l'organizzazione è suddivisa in più aree geografiche, si potrebbe creare un team di Collaborazione tra responsabili per l'area californiana e includere tutti gli Store manager in quella regione, come anche gli Area manager di quello Stato.

| Tipo di modello | TemplateId | Canali del modello |
| ------------------ | -------------- | ----------------------------------------------------- |
| Retail - <br>Store | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| Canali <ul><li>Generale</li><li>Operazioni&sup2;</li><li>Learning&sup2;</li></ul>Proprietà del team <ul><li>Visibilità del team impostata su Private</li></ul> <br>Autorizzazioni dei membri <ul><li>Può creare, aggiornare ed eliminare canali </li><li>Può aggiungere e rimuovere app </li><li>Può creare, aggiornare e rimuovere schede</li><li>Può creare, aggiornare e rimuovere connettori</li><ul>|
||||

&sup2; Canali preferiti automaticamente

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

## <a name="related-articles"></a>Articoli correlati

- [Introduzione ai modelli di team nell'interfaccia Teams di amministrazione](get-started-with-teams-templates-in-the-admin-console.md)
- [Creare un team da un modello nell'app Teams](https://support.microsoft.com/en-us/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c)
- [Introduzione ai modelli di team con Microsoft Graph](get-started-with-teams-templates.md)
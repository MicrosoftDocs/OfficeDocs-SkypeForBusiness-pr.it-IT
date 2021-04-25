---
title: Introduzione ai modelli di Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: Scopri come usare i modelli di Teams per creare strutture di team studiate appositamente per le esigenze dei rivenditori al dettaglio fornendo impostazioni predefinite, canali, app preinstallate.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8d72f88bb33dca16254ec09a2ea89ac90a0e7aca
ms.sourcegitcommit: 900f28c4ac12d65ccbd996028205ba183b4afb03
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/24/2021
ms.locfileid: "51995144"
---
# <a name="create-a-team-using-teams-retail-templates"></a>Creare un team usando i modelli di vendita al dettaglio di Teams

I modelli di Microsoft Teams consentono di creare team in modo rapido e semplice fornendo un modello predefinito di impostazioni, canali e app preinstallate.

I modelli di Teams includono definizioni predefinite delle strutture dei team progettate in base alle necessità dei rivenditori. Puoi usare i modelli di Teams per creare rapidamente le tipologie di team più adatte ai rivenditori e implementarle nell'organizzazione. Puoi anche estendere i modelli di Teams per creare team personalizzati in base alle specifiche esigenze dell'organizzazione.

In questo articolo verranno presentati i modelli di Teams e verrà consigliato come usarli.

Questo articolo è destinato agli utenti responsabili della pianificazione, dell'implementazione e della gestione di più team nell'organizzazione di vendita al dettaglio. Il servizio Teams è già stato implementato nell'organizzazione. Se Teams non è ancora stato implementato, per iniziare, leggere [Come implementare Microsoft Teams](./deploy-overview.md).

Per altre informazioni sui modelli di Teams in generale, vedere [Introduzione ai modelli di Teams](get-started-with-teams-templates.md).

| Chi | Metodo da usare: |
| ---- | --------- |
| Amministratori e professionisti IT | [Usare l'interfaccia di amministrazione di Teams](#use-the-teams-templates-in-the-teams-admin-center) per creare team basati sui modelli di Teams per la vendita al dettaglio.|
| Sviluppatori e integratori di sistemi | [Usare Microsoft Graph per creare](#use-the-teams-templates-with-the-microsoft-graph) team basati sui modelli di Teams per la vendita al dettaglio. |

## <a name="use-the-teams-templates-in-the-teams-admin-center"></a>Usare i modelli di Teams nell’interfaccia di amministrazione di Teams

### <a name="organize-a-store"></a>Organizzare un negozio

Unisci i tuoi dipendenti in un'unica esperienza centralizzata per gestire attività, condividere documenti e risolvere i problemi correlati ai clienti. Integra applicazioni aggiuntive per ottimizzare i processi di inizio e fine turno.

| Tipologia di modello base |baseTemplateId | Proprietà del modello base |
| ------------------|-- |----------------------------------------------------- |
|Organizzare un negozio|`retailStore`|Canali: <ul><li>Generale<li>Passaggio di consegne del turno</li><li>Apprendimento</li></ul> App: <ul><li>Wiki</li></ul>|
||||

### <a name="manager-collaboration"></a>Collaborazione tra responsabili

Il modello Collaborazione manager è ideale per creare un team in cui un set di responsabili collabori tra negozi/aree geografiche e così via. Ad esempio, se l'organizzazione ha aree geografiche, è possibile creare un team di collaborazione per i manager per l'area geografica della California e includere tutti i responsabili dei negozi dell'area geografica, insieme al responsabile regionale dell'area geografica.

| Tipo di modello base| baseTemplateId | Proprietà del modello base |
| ------------------|- |----------------------------------------------------- |
|Vendita al dettaglio: collaborazione tra responsabili|`retailManagerCollaboration` |Canali: <ul><li>Generale<li>Operazioni</li><li>Apprendimento</li></ul> App: <ul><li>Wiki</li></ul>|
||||

## <a name="use-the-teams-templates-with-the-microsoft-graph"></a>Usare i modelli di Teams con Microsoft Graph

### <a name="store-template"></a>Modello Store

Il modello Store è ideale per creare un team che rappresenta la sede di un singolo punto vendita per la vendita al dettaglio. Con il modello Store è possibile creare un team per ogni punto vendita per la vendita al dettaglio nell'organizzazione.

| Tipo di modello base | baseTemplateId | Proprietà incluse nel modello base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Retail - <br>Store | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| Canali <ul><li>Shifts handoff\*</li><li>Learning\*</li></ul>\*Canali aggiunti automaticamente ai preferiti<br><br>Proprietà del team <ul><li>Visibilità del team impostata su Public</li></ul> <br>Autorizzazioni dei membri <ul><li>Non possono creare/aggiornare/eliminare canali </li><li>Non possono aggiungere/rimuovere app </li><li>Non possono creare/aggiornare/rimuovere schede</li><li>Non possono creare/aggiornare/rimuovere connettori</li><ul>|
||||

Modi consigliati per personalizzare il modello Store per l'organizzazione:

- Se l'organizzazione prevede reparti all'interno di ogni punto vendita, aggiungere un canale per ogni reparto. L'aggiunta di un canale favorisce la comunicazione e la collaborazione all'interno del reparto.

- Se l'organizzazione prevede siti Web interni, ad esempio un sito di SharePoint, è opportuno aggiungerli come schede nel canale del team pertinente. Per le istruzioni, vedere [Introduzione ai modelli di Teams](get-started-with-teams-templates.md).

### <a name="manager-collaboration-template"></a>Modello Manager Collaboration

Il modello Manager Collaboration è un altro dei modelli di Teams pensati per le esigenze dei rivenditori. Il modello Manager Collaboration è ideale per creare un team che consenta a un set di responsabili di collaborare in punti vendita/aree geografiche e altro ancora. Ad esempio, se l'organizzazione è suddivisa in più aree geografiche, si potrebbe creare un team Manager Collaboration per l'area californiana e includere tutti i responsabili dei punti vendita di tale regione, nonché i responsabili di area di tale area geografica.

| Tipo di modello base | baseTemplateId | Proprietà incluse nel modello base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Retail - <br>Store | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| Canali <ul><li>Operations\*</li><li>Learning\*</li></ul>\*Canali aggiunti automaticamente ai preferiti<br><br>Proprietà del team <ul><li>Visibilità del team impostata su Private</li></ul> <br>Autorizzazioni dei membri <ul><li>Possono creare/aggiornare/eliminare canali </li><li>Possono aggiungere/rimuovere app </li><li>Possono creare/aggiornare/rimuovere schede</li><li>Possono creare/aggiornare/rimuovere connettori</li><ul>|
||||

Modi consigliati per personalizzare il modello Manager Collaboration per l'organizzazione:

- Se l'organizzazione prevede siti Web interni, ad esempio un sito di SharePoint, che sono pertinenti per i responsabili, è opportuno aggiungerli come schede in un canale del team pertinente. Per le istruzioni, vedere la [documentazione relativa ai modelli di Microsoft Teams](get-started-with-teams-templates.md).

## <a name="how-to-use-first-party-templates"></a>Come usare i modelli del produttore

Per usare questi modelli, modificare la proprietà "template@odata.bind" nel corpo della richiesta da "standard" ai TemplateID precedenti.  Per altre informazioni su come implementare i modelli di Teams, vedere l'articolo di Microsoft Graph su come [creare un team](/graph/api/team-post?view=graph-rest-beta).

> [!NOTE]
> I canali nel modello verranno creati automaticamente nella scheda Generale.

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

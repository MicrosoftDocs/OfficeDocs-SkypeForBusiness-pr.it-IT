---
title: Introduzione ai modelli di Teams nella vendita al dettaglio
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
description: Informazioni su come usare i modelli di Teams per creare strutture di team progettate per le esigenze dei rivenditori, fornendo impostazioni predefinite, canali e app preinstallato.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f226b60bfc3a054166eb48596c505ccd7fa5ac9
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424636"
---
# <a name="get-started-with-teams-templates-in-retail"></a>Introduzione ai modelli di Teams nella vendita al dettaglio

I modelli di Teams consentono di creare team in modo semplice e rapido, fornendo un modello predefinito di impostazioni, canali e app preinstallato.

I modelli di Teams hanno definizioni predefinite di strutture del team progettate in base alle esigenze dei rivenditori. È possibile usare i modelli di Teams per creare rapidamente i tipi di team che funzionano bene per i rivenditori e distribuirli all'interno dell'organizzazione. È anche possibile estendere i modelli di Teams per creare team personalizzati in base alle specifiche esigenze dell'organizzazione.

In questo articolo verranno presentati tutti i modelli di Teams e verrà consigliato come usarli.

Questo articolo è utile se si è responsabili della pianificazione, della distribuzione e della gestione di più team all'interno dell'organizzazione di vendita al dettaglio. Il servizio Teams è già stato distribuito nell'organizzazione. Se Teams non è ancora stato ancora implementazione, iniziare leggendo come [implementare Microsoft Teams.](How-to-roll-out-teams.md)

Per altre informazioni sui modelli di team in generale, vedere Introduzione ai modelli [di Teams.](get-started-with-teams-templates.md)

## <a name="store-template"></a>Modello Store

Il modello Store è ideale per creare un team che rappresenti una singola sede di un negozio. Con il modello Store, è possibile creare un team per ogni punto vendita all'interno dell'organizzazione.

| Tipo di modello di base | baseTemplateId | Proprietà disponibili in questo modello di base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Vendita al dettaglio - <br>Negozio | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| Canali <ul><li>Shifts handoff\*</li><li>Apprendimento\*</li></ul>\*Canali preferiti automaticamente<br><br>Proprietà del team <ul><li>Visibilità del team impostata su Pubblico</li></ul> <br>Autorizzazioni per i membri <ul><li>Non è possibile creare/aggiornare/eliminare canali </li><li>Non è possibile aggiungere/rimuovere app </li><li>Non è possibile creare/aggiornare/rimuovere schede</li><li>Non è possibile creare/aggiornare/rimuovere connettori</li><ul>|
||||

Modi consigliati per personalizzare il modello dello Store per l'organizzazione:

- Se l'organizzazione ha reparti all'interno di ogni negozio, aggiungere un canale per ogni reparto. L'aggiunta di un canale facilita la comunicazione e la collaborazione all'interno del reparto.

- Se l'organizzazione ha siti Web interni, ad esempio un sito di SharePoint, è consigliabile bloccarli come schede nel canale del team pertinente. Per [istruzioni, vedere Introduzione ai modelli di Teams.](get-started-with-teams-templates.md)

## <a name="manager-collaboration-template"></a>Modello collaborazione manager

Il modello Collaborazione con i manager è un altro dei modelli di Teams progettati in base alle esigenze dei rivenditori. Il modello Collaborazione con i responsabili è ideale per creare un team in cui un set di responsabili può collaborare in negozi/aree geografiche e altro ancora. Ad esempio, se l'organizzazione ha aree geografiche, è possibile creare un team di collaborazione manager per l'area geografica della California e includere tutti i responsabili negozio di tale area geografica, nonché il responsabile regionale per tale area geografica.

| Tipo di modello di base | baseTemplateId | Proprietà disponibili in questo modello di base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Vendita al dettaglio - <br>Negozio | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| Canali <ul><li>Operazioni\*</li><li>Apprendimento\*</li></ul>\*Canali preferiti automaticamente<br><br>Proprietà del team <ul><li>Visibilità del team impostata su Privato</li></ul> <br>Autorizzazioni per i membri <ul><li>Può creare/aggiornare/eliminare canali </li><li>Può aggiungere/rimuovere app </li><li>Può creare/aggiornare/rimuovere schede</li><li>Può creare/aggiornare/rimuovere connettori</li><ul>|
||||

Modi consigliati per personalizzare il modello Collaborazione con i manager per l'organizzazione:

- Se l'organizzazione ha siti Web interni rilevanti per i responsabili, ad esempio un sito di SharePoint, è consigliabile bloccarli come schede in un canale del team pertinente. Per istruzioni, vedere la documentazione del modello [Microsoft Teams.](get-started-with-teams-templates.md)

## <a name="how-to-use-first-party-templates"></a>Come usare i modelli di prima parte

Per usare questi modelli, modificare la proprietà "template@odata.bind" nel corpo della richiesta da "standard" ai TemplateID riportati sopra.  Per altre informazioni su come distribuire i modelli di Teams, vedere l'articolo di Microsoft Graph su come [creare un team.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)

> [!NOTE]
> I canali nel modello verranno creati automaticamente nella scheda Generale.

### <a name="example-store-template-extension-script"></a>Esempio: Script dell'estensione del modello Store

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
## <a name="relate-topic"></a>Correla argomento

[Introduzione ai modelli di Teams nell'interfaccia di amministrazione](get-started-with-teams-templates-in-the-admin-console.md)

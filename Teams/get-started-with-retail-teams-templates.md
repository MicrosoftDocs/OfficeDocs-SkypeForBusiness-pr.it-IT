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
ms.openlocfilehash: e0fecf419f6fc3ac0ef15097fe54571d85018587
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101202"
---
# <a name="get-started-with-teams-templates-in-retail"></a>Introduzione ai modelli di Teams

I modelli di Teams consentono di creare team in modo rapido e semplice fornendo un modello predefinito di impostazioni, canali e app preinstallate.

I modelli di Teams includono definizioni predefinite delle strutture dei team progettate in base alle necessità dei rivenditori. Puoi usare i modelli di Teams per creare rapidamente le tipologie di team più adatte ai rivenditori e implementarle nell'organizzazione. Puoi anche estendere i modelli di Teams per creare team personalizzati in base alle specifiche esigenze dell'organizzazione.

In questo articolo verranno presentati i modelli di Teams e verrà consigliato come usarli.

Questo articolo è destinato agli utenti responsabili della pianificazione, dell'implementazione e della gestione di più team nell'organizzazione di vendita al dettaglio. Il servizio Teams è già stato implementato nell'organizzazione. Se Teams non è ancora stato implementato, per iniziare, leggere [Come implementare Microsoft Teams](./deploy-overview.md).

Per altre informazioni sui modelli di Teams in generale, vedere [Introduzione ai modelli di Teams](get-started-with-teams-templates.md).

## <a name="store-template"></a>Modello Store

Il modello Store è ideale per creare un team che rappresenta la sede di un singolo punto vendita per la vendita al dettaglio. Con il modello Store è possibile creare un team per ogni punto vendita per la vendita al dettaglio nell'organizzazione.

| Tipo di modello base | baseTemplateId | Proprietà incluse nel modello base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Retail - <br>Store | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| Canali <ul><li>Shifts handoff\*</li><li>Learning\*</li></ul>\*Canali aggiunti automaticamente ai preferiti<br><br>Proprietà del team <ul><li>Visibilità del team impostata su Public</li></ul> <br>Autorizzazioni dei membri <ul><li>Non possono creare/aggiornare/eliminare canali </li><li>Non possono aggiungere/rimuovere app </li><li>Non possono creare/aggiornare/rimuovere schede</li><li>Non possono creare/aggiornare/rimuovere connettori</li><ul>|
||||

Modi consigliati per personalizzare il modello Store per l'organizzazione:

- Se l'organizzazione prevede reparti all'interno di ogni punto vendita, aggiungere un canale per ogni reparto. L'aggiunta di un canale favorisce la comunicazione e la collaborazione all'interno del reparto.

- Se l'organizzazione prevede siti Web interni, ad esempio un sito di SharePoint, è opportuno aggiungerli come schede nel canale del team pertinente. Per le istruzioni, vedere [Introduzione ai modelli di Teams](get-started-with-teams-templates.md).

## <a name="manager-collaboration-template"></a>Modello Manager Collaboration

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
## <a name="relate-topic"></a>Argomento correlato

[Introduzione ai modelli di Teams nell'interfaccia di amministrazione](get-started-with-teams-templates-in-the-admin-console.md)
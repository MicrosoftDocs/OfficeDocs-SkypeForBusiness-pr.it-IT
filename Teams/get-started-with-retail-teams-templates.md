---
title: Introduzione ai modelli di teams in Retail
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare i modelli di teams per creare strutture del team progettate per le esigenze del rivenditore fornendo impostazioni predefinite, canali e app preinstallate.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4477d42cf7036ac93d79684407ee97b7b9e9b900
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904661"
---
# <a name="get-started-with-teams-templates-in-retail"></a>Introduzione ai modelli di teams in Retail 

I modelli di teams consentono di creare rapidamente e facilmente team fornendo un modello predefinito di impostazioni, canali e app preinstallate.

I modelli di teams hanno definizioni predefinite delle strutture del team progettate intorno alle esigenze del rivenditore. È possibile usare i modelli di teams per creare rapidamente i tipi di team che funzionano bene per i rivenditori e li distribuiscono in tutta l'organizzazione. Puoi anche estendere i modelli di teams per creare team personalizzati per le specifiche esigenze organizzative.

In questo articolo verranno introdotti tutti i modelli di team e il modo in cui è consigliabile usarli.

Questo articolo è per te, se sei responsabile per pianificare, distribuire e gestire più team in tutta l'organizzazione al dettaglio. Supponiamo che tu abbia già implementato il servizio teams nell'organizzazione. Se non sono stati ancora distribuiti team, iniziare leggendo la [procedura per l'implementazione di Microsoft teams](How-to-roll-out-teams.md).

Per altre informazioni sui modelli di team in generale, vedere [Introduzione ai modelli](get-started-with-teams-templates.md)di teams.

## <a name="store-template"></a>Modello di archivio

Il modello dello Store è ideale per creare un team che rappresenti una singola posizione per il punto vendita. Usando il modello Store, è possibile creare un team per ogni posizione del punto vendita all'interno dell'organizzazione.

| Tipo di modello di base | baseTemplateId | Proprietà disponibili con questo modello di base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Negozio <br>Negozio | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| Canali <ul><li>Turni di consegna\*</li><li>Apprendimento\*</li></ul>\*Canali preferiti automaticamente<br><br>Proprietà del team <ul><li>Visibilità del team impostata su pubblico</li></ul> <br>Autorizzazioni per i membri <ul><li>Non è possibile creare/aggiornare/eliminare i canali </li><li>Non è possibile aggiungere/rimuovere app </li><li>Non è possibile creare/aggiornare/rimuovere schede</li><li>Non è possibile creare/aggiornare/rimuovere connettori</li><ul>|
||||

Modi consigliati per personalizzare il modello di archivio per l'organizzazione:

- Se l'organizzazione ha reparti all'interno di ogni archivio, aggiungere un canale per ogni reparto. Ciò faciliterà la comunicazione e la collaborazione all'interno del reparto.

- Se l'organizzazione ha siti Web interni, ad esempio un sito di SharePoint, è consigliabile aggiungerli come schede nel canale del team pertinente. Per istruzioni, vedere [Introduzione ai modelli di teams](get-started-with-teams-templates.md) .

## <a name="manager-collaboration-template"></a>Modello di Collaboration Manager

Il modello di collaborazione di Manager è un altro dei modelli di Team progettati intorno alle esigenze del rivenditore. Il modello di collaborazione di Manager è ideale per creare un team per un set di Manager che collaborano tra negozi/aree geografiche e così via. Ad esempio, se l'organizzazione ha aree geografiche, è possibile creare un team di collaborazione di gestione per l'area della California e includere tutti i responsabili dello Store nell'area geografica, oltre al responsabile regionale per l'area geografica.

| Tipo di modello di base | baseTemplateId | Proprietà disponibili con questo modello di base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Negozio <br>Negozio | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| Canali <ul><li>Operazioni\*</li><li>Apprendimento\*</li></ul>\*Canali preferiti automaticamente<br><br>Proprietà del team <ul><li>Visibilità del team impostata su privato</li></ul> <br>Autorizzazioni per i membri <ul><li>Può creare/aggiornare/eliminare i canali </li><li>Può aggiungere/rimuovere app </li><li>Può creare/aggiornare/rimuovere schede</li><li>Può creare/aggiornare/rimuovere connettori</li><ul>|
||||

Modi consigliati per personalizzare il modello di collaborazione di gestione per l'organizzazione:

- Se l'organizzazione ha siti Web interni, ad esempio un sito di SharePoint, che sono rilevanti per i responsabili, è consigliabile aggiungerli come schede in un canale del team pertinente. Per istruzioni, vedere la documentazione del [modello Microsoft teams](get-started-with-teams-templates.md) .

## <a name="how-to-use-first-party-templates"></a>Come usare i modelli di First Party

Per usare questi modelli, è sufficiente modificare la proprietà "template@odata. bind" nel corpo della richiesta da "standard" a TemplateIDs sopra.  Per altre informazioni su come distribuire i modelli di Team, vedere l'articolo su Microsoft Graph su come [creare un team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).

> [!NOTE]
> I canali nel modello verranno creati automaticamente nella scheda generale.

### <a name="example-store-template-extension-script"></a>Esempio: script di estensione del modello di archiviazione

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

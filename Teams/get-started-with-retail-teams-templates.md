---
title: Introduzione ai modelli di teams in Retail
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/11/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare i modelli di teams per creare strutture del team progettate per le esigenze del rivenditore.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e463061dca0633480124bbe91fb2e8e6f9f926f6
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "36181642"
---
# <a name="get-started-with-teams-templates-in-retail"></a>Introduzione ai modelli di teams in Retail 

I modelli di teams consentono di creare rapidamente e facilmente team fornendo un modello predefinito di impostazioni, canali e app preinstallate.

I modelli di teams hanno definizioni predefinite delle strutture del team progettate intorno alle esigenze del rivenditore. È possibile usare i modelli di teams per creare rapidamente i tipi di team che funzionano bene per i rivenditori e li distribuiscono in tutta l'organizzazione. Puoi anche estendere i modelli di teams per creare team personalizzati per le specifiche esigenze organizzative.

In questo articolo verranno introdotti tutti i modelli di team e il modo in cui è consigliabile usarli.

Questo articolo è per te, se sei responsabile per pianificare, distribuire e gestire più team in tutta l'organizzazione al dettaglio.

Per altre informazioni sui modelli di team in generale, vedere [Introduzione ai modelli](get-started-with-teams-templates.md)di teams.

## <a name="store-template"></a>Modello di archivio

Il modello dello Store è ideale per creare un team che rappresenti una singola posizione per il punto vendita. Usando il modello Store, è possibile creare un team per ogni posizione del punto vendita all'interno dell'organizzazione.

| Tipo di modello di base | baseTemplateId | Proprietà disponibili con questo modello di base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Negozio <br>Negozio | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| Canali <ul><li>Turni di consegna\*</li><li>Apprendimento\*</li></ul>\*Canali preferiti automaticamente<br><br>Proprietà del team <ul><li>Visibilità del team impostata su pubblico</li></ul> <br>Autorizzazioni per i membri <ul><li>Non è possibile creare/aggiornare/eliminare i canali </li><li>Non è possibile aggiungere/rimuovere app </li><li>Non è possibile creare/aggiornare/rimuovere schede</li><li>Non è possibile creare/aggiornare/rimuovere connettori</li><ul>|
||||

Modi consigliati per personalizzare il modello di archivio per l'organizzazione:

- Se l'organizzazione ha reparti all'interno di ogni archivio, aggiungere un canale per ogni reparto. Ciò faciliterà la comunicazione e la collaborazione all'interno del reparto.

- Se l'organizzazione ha siti Web interni, ad esempio un sito di SharePoint, è consigliabile aggiungerli come schede nel canale del team pertinente. Per istruzioni, vedere [Introduzione ai modelli](get-started-with-teams-templates.md) di teams.

## <a name="manager-collaboration-template"></a>Modello di Collaboration Manager

Il modello di collaborazione di Manager è un altro dei modelli di Team progettati intorno alle esigenze del rivenditore. Il modello di collaborazione di Manager è ideale per creare un team per un set di Manager che collaborano tra negozi/aree geografiche e così via. Ad esempio, se l'organizzazione ha aree geografiche, è possibile creare un team di collaborazione di gestione per l'area della California e includere tutti i responsabili dello Store nell'area geografica, oltre al responsabile regionale per l'area geografica.

| Tipo di modello di base | baseTemplateId | Proprietà disponibili con questo modello di base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Negozio <br>Negozio | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| Canali <ul><li>Operazioni\*</li><li>Apprendimento\*</li></ul>\*Canali preferiti automaticamente<br><br>Proprietà del team <ul><li>Visibilità del team impostata su privato</li></ul> <br>Autorizzazioni per i membri <ul><li>Può creare/aggiornare/eliminare i canali </li><li>Può aggiungere/rimuovere app </li><li>Può creare/aggiornare/rimuovere schede</li><li>Può creare/aggiornare/rimuovere connettori</li><ul>|
||||

Modi consigliati per personalizzare il modello di collaborazione di gestione per l'organizzazione:

- Se l'organizzazione ha siti Web interni, ad esempio un sito di SharePoint, che sono rilevanti per i responsabili, valutare la possibilità di aggiungerli come schede in un canale del team [](get-started-with-teams-templates.md) pertinente (vedere la documentazione relativa alle istruzioni).
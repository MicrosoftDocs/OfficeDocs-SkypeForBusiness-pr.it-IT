---
title: Usare i modelli di teams retail nella console di amministrazione
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare i modelli di teams per creare strutture del team progettate per le esigenze del rivenditore fornendo impostazioni predefinite, canali e app preinstallate tramite la console di amministrazione.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: c9e0a75c558888fcd1c558eb3f87718a85e22471
ms.sourcegitcommit: 340c2f432b78af4e78b21056af56c6421627045d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294542"
---
# <a name="use-teams-retail-templates-in-the-admin-console"></a>Usare i modelli di teams retail nella console di amministrazione

I modelli di teams consentono di creare rapidamente e facilmente team fornendo un modello predefinito di impostazioni, canali e app preinstallate.

I modelli di teams hanno definizioni predefinite delle strutture del team progettate intorno alle esigenze del rivenditore. È possibile usare i modelli di teams per creare rapidamente i tipi di team che funzionano bene per i rivenditori e li distribuiscono in tutta l'organizzazione. Puoi anche estendere i modelli di teams per creare team personalizzati per le specifiche esigenze organizzative.

In questo articolo verranno introdotti tutti i modelli di team e il modo in cui è consigliabile usarli.

Questo articolo è per te, se sei responsabile per pianificare, distribuire e gestire più team in tutta l'organizzazione al dettaglio. Supponiamo che tu abbia già implementato il servizio teams nell'organizzazione. Se non sono stati ancora distribuiti team, iniziare leggendo la [procedura per l'implementazione di Microsoft teams](How-to-roll-out-teams.md).

Per altre informazioni sui modelli di team in generale, vedere [Introduzione ai modelli](get-started-with-teams-templates-in-the-admin-console.md)di teams.

## <a name="organize-a-store"></a>Organizzare uno Store

Riunire i dipendenti al dettaglio in un'unica esperienza centralizzata per gestire le attività, condividere documenti e risolvere i problemi dei clienti. Integrare altre applicazioni per semplificare l'avvio di & i processi finali.

| Tipo di modello di base |baseTemplateId | Proprietà disponibili con questo modello di base |
| ------------------|-- |----------------------------------------------------- |
|Organizzare uno Store| `retailStore`|Canali <ul><li>Generale<li>Cambio di consegna</li><li>Apprendimento</li></ul> Applicazioni <ul><li>Wiki</li></ul>|
||||

## <a name="manager-collaboration"></a>Collaborazione con i Manager

Il modello di collaborazione di Manager è ideale per creare un team per un set di Manager che collaborano tra negozi/aree geografiche e così via. Ad esempio, se l'organizzazione ha aree geografiche, è possibile creare un team di collaborazione di gestione per l'area della California e includere tutti i responsabili dello Store nell'area geografica, oltre al responsabile regionale per l'area geografica.

| Tipo di modello di base| baseTemplateId | Proprietà disponibili con questo modello di base |
| ------------------|- |----------------------------------------------------- |
|Collaborazione al dettaglio-Manager|`retailManagerCollaboration` |Canali <ul><li>Generale<li>Operazioni</li><li>Apprendimento</li></ul> Applicazioni <ul><li>Wiki</li></ul>|
||||

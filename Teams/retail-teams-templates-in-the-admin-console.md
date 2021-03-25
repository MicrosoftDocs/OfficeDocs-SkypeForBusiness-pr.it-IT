---
title: Usare i modelli retail di Teams nell'interfaccia di amministrazione
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
description: Scopri come usare i modelli di Teams per creare strutture di team studiate appositamente per le esigenze dei rivenditori al dettaglio fornendo impostazioni predefinite, canali, app preinstallate tramite l'interfaccia di amministrazione.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: a63602f07e0c248b4decbc733e41b16fdafc3911
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117614"
---
# <a name="use-teams-retail-templates-in-the-admin-center"></a>Usare i modelli retail di Teams nell'interfaccia di amministrazione

I modelli di Teams consentono di creare team in modo rapido e semplice fornendo un modello predefinito di impostazioni, canali e app preinstallate.

I modelli di Teams includono definizioni predefinite delle strutture dei team progettate in base alle necessità dei rivenditori. Puoi usare i modelli di Teams per creare rapidamente le tipologie di team più adatte ai rivenditori e implementarle nell'organizzazione. Puoi anche estendere i modelli di Teams per creare team che si adattino al meglio alle esistenze specifiche dell'organizzazione.

In questo articolo, verranno presentati i modelli di Teams e come possono essere utilizzati.

Questo articolo è per i responsabili dedicati alla pianificazione, all'implementazione e alla gestione di più team nell'organizzazione di vendita al dettaglio. Si presume che tu abbia già implementato il servizio Teams nell'organizzazione. Qualora non lo avessi ancora fatto, inizia a leggere [Come implementare Microsoft Teams](./deploy-overview.md).

Per scoprire di più sui modelli dei team in generale, fai riferimento a [Introduzione ai modelli di Teams](get-started-with-teams-templates-in-the-admin-console.md).

## <a name="organize-a-store"></a>Organizzare un negozio

Unisci i tuoi dipendenti in un'unica esperienza centralizzata per gestire attività, condividere documenti e risolvere i problemi correlati ai clienti. Integra applicazioni aggiuntive per ottimizzare i processi di inizio e fine turno.

| Tipologia di modello base |baseTemplateId | Proprietà del modello base |
| ------------------|-- |----------------------------------------------------- |
|Organizzare un negozio|`retailStore`|Canali: <ul><li>Generale<li>Passaggio di consegne del turno</li><li>Apprendimento</li></ul> App: <ul><li>Wiki</li></ul>|
||||

## <a name="manager-collaboration"></a>Collaborazione tra responsabili

Il modello Collaborazione tra responsabili è perfetto per creare un team formato da un gruppo di responsabili e agevolare la loro collaborazione tra negozi/aree geografiche, ecc. Ad esempio, se l'organizzazione è suddivisa in più aree geografiche, si potrebbe creare un team di Collaborazione tra responsabili per l'area californiana e includere tutti gli Store manager in quella regione, come anche gli Area manager di quello Stato.

| Tipologia di modello base| baseTemplateId | Proprietà del modello base |
| ------------------|- |----------------------------------------------------- |
|Vendita al dettaglio: collaborazione tra responsabili|`retailManagerCollaboration` |Canali: <ul><li>Generale<li>Operazioni</li><li>Apprendimento</li></ul> App: <ul><li>Wiki</li></ul>|
||||
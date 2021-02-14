---
title: Usare i modelli di vendita al dettaglio di Teams nell'interfaccia di amministrazione
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
description: Informazioni su come usare i modelli di Teams per creare strutture di team progettate per le esigenze dei rivenditori, fornendo impostazioni predefinite, canali e app preinstallato utilizzando l'interfaccia di amministrazione.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4b40da8fd1cc8182d0e5ad80c30f5a459f17d26f
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662641"
---
# <a name="use-teams-retail-templates-in-the-admin-center"></a>Usare i modelli di vendita al dettaglio di Teams nell'interfaccia di amministrazione

I modelli di Teams consentono di creare team in modo semplice e rapido, fornendo un modello predefinito di impostazioni, canali e app preinstallato.

I modelli di Teams hanno definizioni predefinite di strutture del team progettate in base alle esigenze dei rivenditori. È possibile usare i modelli di Teams per creare rapidamente i tipi di team che funzionano bene per i rivenditori e distribuirli all'interno dell'organizzazione. È anche possibile estendere i modelli di Teams per creare team personalizzati in base alle specifiche esigenze dell'organizzazione.

In questo articolo verranno presentati tutti i modelli di Teams e verrà spiegato come usarli.

Questo articolo è utile se si è responsabili della pianificazione, della distribuzione e della gestione di più team all'interno dell'organizzazione di vendita al dettaglio. Presuppongiamo che l'utente abbia già distribuito il servizio Teams nell'organizzazione. Se Teams non è ancora stato ancora implementazione, iniziare leggendo come [implementare Microsoft Teams.](How-to-roll-out-teams.md)

Per altre informazioni sui modelli di team in generale, vedere Introduzione ai modelli [di Teams.](get-started-with-teams-templates-in-the-admin-console.md)

## <a name="organize-a-store"></a>Organizzare uno store

Riunire i dipendenti della vendita al dettaglio in un'unica esperienza centrale per gestire le attività, condividere documenti e risolvere i problemi dei clienti. Integrare altre applicazioni per semplificare i processi di & di inizio e fine.

| Tipo di modello di base |baseTemplateId | Proprietà disponibili in questo modello di base |
| ------------------|-- |----------------------------------------------------- |
|Organizzare uno store|`retailStore`|Canali: <ul><li>Generale<li>Maiusc handoff</li><li>Apprendimento</li></ul> App: <ul><li>Wiki</li></ul>|
||||

## <a name="manager-collaboration"></a>Collaborazione con i manager

Il modello Collaborazione con i responsabili è ideale per creare un team in cui un set di responsabili può collaborare in negozi/aree geografiche e così via. Ad esempio, se l'organizzazione ha aree geografiche, è possibile creare un team di collaborazione manager per l'area geografica della California e includere tutti i responsabili negozio di tale area geografica, nonché il responsabile regionale per tale area geografica.

| Tipo di modello di base| baseTemplateId | Proprietà disponibili in questo modello di base |
| ------------------|- |----------------------------------------------------- |
|Vendita al dettaglio - collaborazione con i manager|`retailManagerCollaboration` |Canali: <ul><li>Generale<li>Operazioni</li><li>Apprendimento</li></ul> App: <ul><li>Wiki</li></ul>|
||||

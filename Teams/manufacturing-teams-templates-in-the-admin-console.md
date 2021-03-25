---
title: Introduzione ai modelli di produzione di Teams nell'interfaccia di amministrazione
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
description: Scopri come usare. Modelli di Teams per creare strutture del team progettate per le esigenze di produzione, fornendo impostazioni predefinite, canali e app preinstallato usando l'interfaccia di amministrazione.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9f5439cd8fdd053ab8444a1016eac94064638605
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120557"
---
# <a name="use-teams-manufacturing-templates-in-the-admin-center"></a>Usare i modelli di produzione di Teams nell'interfaccia di amministrazione

I modelli di Teams consentono di creare team in modo rapido e semplice fornendo un modello predefinito di impostazioni, canali e app preinstallate.

I modelli di Teams hanno definizioni predefinite delle strutture del team progettate in base alle esigenze di produzione. Puoi anche estendere i modelli di Teams per creare team personalizzati in base alle specifiche esigenze dell'organizzazione.

In questo articolo vengono presentati tutti i modelli di Teams e viene consigliato come usarli.

Questo articolo è utile se si è responsabili della pianificazione, della distribuzione e della gestione di più team all'interno dell'organizzazione di produzione. Il servizio Teams è già stato implementato nell'organizzazione. Se Teams non è ancora stato implementato, per iniziare, leggere [Come implementare Microsoft Teams](./deploy-overview.md).

Per altre informazioni sui modelli di Teams in generale, vedere [Introduzione ai modelli di Teams](get-started-with-teams-templates-in-the-admin-console.md).

## <a name="quality-and-safety"></a>Qualità e sicurezza

Centralizzare le comunicazioni, l'accesso alle risorse e le operazioni degli impianti con un team dell'impianto di produzione. Includere documenti di criteri e procedure, video di formazione, avvisi di sicurezza, processi di passaggio del turno.

| Tipo di modello base|baseTemplateId| Proprietà incluse nel modello base |
| ------------------|-- |----------------------------------------------------- |
|Qualità e sicurezza|`com.microsoft.teams.template.QualitySafety` |Canali: <ul><li>Generale<li>Annunci</li><li>Riga 1</li><li>Riga 2</li><li>Riga 3</li><li>Sicurezza</li><li>Formazione</li><li>Manutenzione</li><li>Cose divertenti</li></ul> App: <ul><li>Wiki</li><li>Programmazione</li></ul>|
||||
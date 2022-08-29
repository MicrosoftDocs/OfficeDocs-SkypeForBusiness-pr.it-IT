---
title: Monitoraggio e avvisi di Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: vapati
f1.keywords: ''
ms.localizationpriority: medium
search.appverid: ''
ms.collection:
- M365-collaboration
description: Informazioni sulle funzionalità di avvisi e notifiche di Teams disponibili nell'interfaccia di amministrazione di Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 452bcbebeffa3936b9d05270626e11923caf5cda
ms.sourcegitcommit: 72b6f7ab2a44dec395622bfe64119a48094960bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/08/2022
ms.locfileid: "67283087"
---
# <a name="microsoft-teams-monitoring-and-alerting"></a>Monitoraggio e avvisi di Microsoft Teams

Nell'interfaccia di amministrazione di Teams sono disponibili nuove funzionalità di monitoraggio e avviso per Microsoft Teams. Usare diversi set di regole disponibili nella sezione **Notifiche & avvisi** nell'interfaccia di amministrazione di Teams per monitorare le funzionalità di Teams e ricevere avvisi. Ad esempio, è possibile monitorare attivamente l'integrità dei dispositivi di Teams, ad esempio telefoni IP, barre di collaborazione e altri, se si disconnettono in modo imprevisto.  

L'organizzazione può usare il monitoraggio e gli avvisi di Teams per eseguire le operazioni seguenti:

- Gestire automaticamente le funzionalità di Teams
- Ricevere un avviso se viene visualizzato qualcosa di imprevisto.
- Eseguire azioni correttive per tenere traccia delle attività.

> [!NOTE]
> La funzionalità di avviso all'interno dell'interfaccia di amministrazione di Teams non è disponibile negli ambienti GCC/GCC-High.

## <a name="how-to-manage-monitoring-and-alerting"></a>Come gestire il monitoraggio e gli avvisi

 Per configurare le regole di avviso, è necessario essere un amministratore globale di Microsoft 365 o un amministratore del servizio Teams. Vedere [Usare i ruoli di amministratore di Teams per gestire Teams](../using-admin-roles.md) per saperne di più sui ruoli di amministratore di Teams e su quali report possono accedere ogni ruolo di amministratore.

1. Accedere all'interfaccia di amministrazione di Teams.
2. Nel riquadro di spostamento sinistro seleziona **Notifiche & avvisi**.
3. Scegliere la regola da configurare da **Regole**.

## <a name="teams-monitoring-rules-reference"></a>Riferimento alle regole di monitoraggio di Teams

Continuiamo ad aggiungere e migliorare l'esperienza di monitoraggio di Teams aggiungendo varie funzionalità di monitoraggio e funzionalità di configurazione. Ecco un elenco delle regole di monitoraggio di Teams attualmente disponibili nell'interfaccia di amministrazione di Teams.


|Regola  |Funzionalità di monitoraggio|Cosa viene monitorato? |
|---------|---------|---------|
|Invii di app  |App di Teams | Monitorare attivamente le app di Teams se vengono inviate per l'approvazione.|
|[Regola dello stato del dispositivo](device-health-status.md)  |Dispositivi di Teams | Monitora attivamente i dispositivi Teams se passano offline.|

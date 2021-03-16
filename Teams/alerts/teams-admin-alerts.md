---
title: Monitoraggio e avvisi di Microsoft Teams
author: vaibhav
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: vapati
f1.keywords: ''
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-collaboration
description: Informazioni sulle funzionalità di avvisi e notifiche di Teams disponibili nell'interfaccia di amministrazione di Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 1be3ca52d4b03cfbf82d82310148ef4c2bb7f06d
ms.sourcegitcommit: c6b630f9193d7f82f0416bd567a1de390d4b260f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819456"
---
# <a name="microsoft-teams-monitoring-and-alerting"></a>Monitoraggio e avvisi di Microsoft Teams

Nell'interfaccia di amministrazione di Teams sono disponibili nuove funzionalità di monitoraggio e avviso per Microsoft Teams. Usare diversi set di  regole disponibili nella sezione Avvisi & notifiche nell'interfaccia di amministrazione di Teams per monitorare le funzionalità di Teams e ricevere avvisi. Ad esempio, è possibile monitorare attivamente l'integrità dei dispositivi di Teams, ad esempio telefoni IP, barre di collaborazione e altri utenti, se vengono inaspettatamente offline.  

L'organizzazione può usare il monitoraggio e gli avvisi di Teams per eseguire le operazioni seguenti:

- Gestire automaticamente le funzionalità di Teams
- Essere avvisati se mostrano qualcosa di imprevisto.
- Eseguire azioni correttive per ri tenere traccia degli elementi.

## <a name="how-to-manage-monitoring-and-alerting"></a>Come gestire il monitoraggio e gli avvisi

 Per configurare le regole di avviso, è necessario essere un amministratore globale di Microsoft 365 o un amministratore del servizio Teams. Vedere [Usare i ruoli di amministratore di Teams per gestire Teams](../using-admin-roles.md) per altre informazioni sui ruoli di amministratore di Teams e sui report a cui ogni ruolo di amministratore può accedere.

1. Passare all'interfaccia di amministrazione di Teams.
2. Nel riquadro di spostamento sinistro selezionare **Notifiche & avvisi**.
3. Scegliere la regola da configurare in **Regole**.

## <a name="teams-monitoring-rules-reference"></a>Riferimento alle regole di monitoraggio di Teams

Continuiamo ad aggiungere e migliorare l'esperienza di monitoraggio di Teams aggiungendo varie funzionalità di monitoraggio e funzionalità di configurazione. Ecco un elenco delle regole di monitoraggio di Teams attualmente disponibili nell'interfaccia di amministrazione di Teams.


|Regola  |Funzionalità di monitoraggio|Cosa viene monitorato? |
|---------|---------|---------|
|[Stato di integrità del dispositivo](device-health-status.md)  |Dispositivi di Teams | Monitora attivamente i dispositivi di Teams se passano offline.|

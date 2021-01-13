---
title: Visualizzare le assegnazioni dei criteri nel registro attività nell'interfaccia di amministrazione di Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Informazioni su come visualizzare le attività di assegnazione dei criteri nel registro attività nell'interfaccia di amministrazione di Microsoft teams.
localization_priority: Normal
f1.keywords:
- CSH
- ms.teamsadmincenter.dashboard.activitylog.overview
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a8d1d49d187808b768b4a92c64c4e667ca0ea8f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821316"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a>Visualizzare le assegnazioni dei criteri nel registro attività

Quando si assegnano criteri agli utenti nell'interfaccia di amministrazione di Microsoft teams, è possibile visualizzare lo stato di tali assegnazioni dei criteri nel registro attività. Il registro attività Mostra le assegnazioni dei criteri ai batch di più di 20 utenti tramite l'interfaccia di amministrazione di Microsoft teams degli ultimi 30 giorni. Tieni presente che il log attività non Mostra le assegnazioni dei pacchetti di criteri, le assegnazioni di criteri ai batch di meno di 20 utenti tramite l'interfaccia di amministrazione di Microsoft teams o le assegnazioni di criteri tramite PowerShell.

![Screenshot della pagina del log attività](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a>Visualizzare le attività di assegnazione dei criteri nel registro attività

Per visualizzare le assegnazioni dei criteri nel registro attività:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **Dashboard** e quindi in **Registro attività** Selezionare **Visualizza dettagli**.
2. È possibile visualizzare tutte le assegnazioni dei criteri o filtrare l'elenco in base allo stato per visualizzare solo le assegnazioni **non avviate**, **in corso** o **completate**. Verranno visualizzate le informazioni seguenti su ogni assegnazione:
    - **Name**: nome dell'assegnazione di criteri. Fare clic sul collegamento per visualizzare altri dettagli. Include il numero di utenti a cui è stato assegnato il criterio e il numero di assegnazioni completate, in corso e non avviate. Vedrai anche l'elenco degli utenti nel batch e lo stato e il risultato per ogni utente. Ecco un esempio:

        ![Screenshot della](media/activity-log-policy-assignment-detail.png)

    - **Inviato**: data e ora in cui è stata inviata l'assegnazione dei criteri.
    - **Ora di completamento**: data e ora l'assegnazione dei criteri è stata completata.
    - **Impatto su**: numero di utenti nel batch.
    - **Stato complessivo**: stato dell'assegnazione dei criteri.

> [!NOTE]
> È anche possibile accedere al log attività dalla pagina **utenti** . Dopo aver fatto clic su **applica** per inviare un'assegnazione di criteri di massa, viene visualizzato un banner nella parte superiore della pagina. Fare clic sul collegamento del **log attività** nell'intestazione.

## <a name="related-topics"></a>Argomenti correlati

- [Assegnare criteri agli utenti](assign-policies.md)

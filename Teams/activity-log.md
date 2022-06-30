---
title: Visualizzare le assegnazioni dei criteri nel log attività nell'interfaccia di amministrazione di Microsoft Teams
ms.author: mabond
author: mkbond007
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Informazioni su come visualizzare le attività di assegnazione dei criteri nel log attività nell'interfaccia di amministrazione di Microsoft Teams.
ms.localizationpriority: medium
f1.keywords:
- CSH
- ms.teamsadmincenter.dashboard.activitylog.overview
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e8243d60a2aca31a8b9158b922126c7c80a486eb
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562215"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a>Visualizzare le assegnazioni dei criteri nel log attività

Quando si assegnano criteri agli utenti nell'interfaccia di amministrazione di Microsoft Teams, è possibile visualizzare lo stato di queste assegnazioni di criteri nel log attività. Il log attività mostra le assegnazioni dei criteri a batch di più di 20 utenti tramite l'interfaccia di amministrazione di Microsoft Teams degli ultimi 30 giorni. Tenere presente che il log attività non mostra le assegnazioni dei pacchetti di criteri, le assegnazioni dei criteri a batch di meno di 20 utenti tramite l'interfaccia di amministrazione di Microsoft Teams o le assegnazioni dei criteri tramite PowerShell.

![Screenshot della pagina del log attività.](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a>Visualizzare le attività di assegnazione dei criteri nel log attività

Per visualizzare le assegnazioni dei criteri nel log attività:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passare a **Home** e quindi in **Log attività** selezionare **Visualizza dettagli**.
2. È possibile visualizzare tutte le assegnazioni dei criteri o filtrare l'elenco per stato per visualizzare solo le assegnazioni **non iniziate**, **In corso** o **Completate**. Verranno visualizzate le informazioni seguenti su ogni attività:
    - **Nome**: nome dell'assegnazione dei criteri. Fare clic sul collegamento per visualizzare altri dettagli. Include il numero di utenti a cui è stato assegnato il criterio e il numero di assegnazioni completate, in corso e non iniziate. Verranno inoltre visualizzati l'elenco di utenti nel batch, lo stato e il risultato per ogni utente. Ecco un esempio:

        ![Screenshot del.](media/activity-log-policy-assignment-detail.png)

    - **Inviato**: data e ora di invio dell'assegnazione dei criteri.
    - **Ora di completamento**: data e ora in cui è stata completata l'assegnazione dei criteri.
    - **Impatto su**: numero di utenti nel batch.
    - **Stato generale**: stato dell'assegnazione dei criteri.

> [!NOTE]
> È anche possibile accedere al log attività dalla pagina **Utenti** . Dopo aver fatto clic su **Applica** per inviare un'assegnazione di criteri in blocco, nella parte superiore della pagina verrà visualizzato un banner. Fare clic sul collegamento **Log attività** nel banner.

## <a name="related-topics"></a>Argomenti correlati

- [Assegnare criteri agli utenti](policy-assignment-overview.md)

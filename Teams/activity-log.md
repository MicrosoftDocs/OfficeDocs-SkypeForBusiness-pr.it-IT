---
title: Visualizzare le assegnazioni dei criteri nel log attività nell'Microsoft Teams di amministrazione
author: SerdarSoysal
ms.author: serdars
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Informazioni su come visualizzare le attività di assegnazione dei criteri nel log attività nell'Microsoft Teams di amministrazione.
ms.localizationpriority: medium
f1.keywords:
- CSH
- ms.teamsadmincenter.dashboard.activitylog.overview
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ed7903e0018d30882fa27c63941b5d03a27fdaf3
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2022
ms.locfileid: "62393528"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a>Visualizzare le assegnazioni dei criteri nel log attività

Quando si assegnano criteri agli utenti nell'Microsoft Teams di amministrazione, è possibile visualizzare lo stato di tali assegnazioni di criteri nel log attività. Il log attività mostra le assegnazioni dei criteri a batch di più di 20 utenti tramite l'Microsoft Teams di amministrazione degli ultimi 30 giorni. Tenere presente che il log attività non mostra le assegnazioni dei pacchetti di criteri, le assegnazioni dei criteri a batch di meno di 20 utenti tramite l'interfaccia di amministrazione di Microsoft Teams o le assegnazioni dei criteri tramite PowerShell.

![Screenshot della pagina Log attività.](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a>Visualizzare le attività di assegnazione dei criteri nel log attività

Per visualizzare le assegnazioni dei criteri nel log attività:

1. Nel riquadro di spostamento sinistro dell Microsoft Teams di amministrazione passare a **Home** e quindi in Log **attività** selezionare **Visualizza dettagli**.
2. È possibile visualizzare tutte le assegnazioni dei criteri o filtrare l'elenco in base allo stato per visualizzare solo le assegnazioni non iniziate **,** **in** corso o **completate**. Verranno visualizzate le informazioni seguenti su ogni attività:
    - **Nome**: il nome dell'assegnazione dei criteri. Fare clic sul collegamento per visualizzare altri dettagli. Questo include il numero di utenti a cui è stato assegnato il criterio e il numero di assegnazioni completate, in corso e non avviate. Verranno visualizzati anche l'elenco degli utenti nel batch e lo stato e il risultato per ogni utente. Ecco un esempio:

        ![Screenshot dell'oggetto.](media/activity-log-policy-assignment-detail.png)

    - **Inviato**: data e ora di invio dell'assegnazione dei criteri.
    - **Ora di completamento**: data e ora di completamento dell'assegnazione dei criteri.
    - **Impatto su**: numero di utenti nel batch.
    - **Stato generale**: stato dell'assegnazione dei criteri.

> [!NOTE]
> È anche possibile accedere al log attività dalla **pagina** Utenti. Dopo aver fatto **clic su Applica** per inviare un'assegnazione di criteri in blocco, nella parte superiore della pagina verrà visualizzato un banner. Fare clic **sul collegamento Log** attività nel banner.

## <a name="related-topics"></a>Argomenti correlati

- [Assegnare criteri agli utenti](policy-assignment-overview.md)

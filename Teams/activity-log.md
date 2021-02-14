---
title: Visualizzare le assegnazioni dei criteri nel log attività nell'interfaccia di amministrazione di Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Informazioni su come visualizzare le attività di assegnazione dei criteri nel log attività nell'interfaccia di amministrazione di Microsoft Teams.
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
# <a name="view-your-policy-assignments-in-the-activity-log"></a>Visualizzare le assegnazioni dei criteri nel log attività

Quando si assegnano criteri agli utenti nell'interfaccia di amministrazione di Microsoft Teams, è possibile visualizzare lo stato di tali assegnazioni nel log attività. Il log attività mostra le assegnazioni dei criteri a batch di più di 20 utenti tramite l'interfaccia di amministrazione di Microsoft Teams degli ultimi 30 giorni. Tenere presente che il log attività non mostra le assegnazioni dei pacchetti dei criteri, le assegnazioni dei criteri a batch di meno di 20 utenti tramite l'interfaccia di amministrazione di Microsoft Teams o le assegnazioni dei criteri tramite PowerShell.

![Screenshot della pagina Log attività](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a>Visualizzare le attività di assegnazione dei criteri nel log attività

Per visualizzare le assegnazioni dei criteri nel log attività:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa a **Dashboard,** quindi in **Log** attività seleziona **Visualizza dettagli.**
2. È possibile visualizzare tutte le assegnazioni dei criteri o filtrare l'elenco in base allo stato per visualizzare solo le assegnazioni non **iniziate,** **in** corso o **completate.** Verranno visualizzate le informazioni seguenti su ogni attività:
    - **Nome:** nome dell'assegnazione dei criteri. Fare clic sul collegamento per visualizzare altri dettagli. Questo include il numero di utenti a cui è stato assegnato il criterio e il numero di assegnazioni completate, in corso e non iniziate. Verrà visualizzato anche l'elenco di utenti nel batch e lo stato e il risultato di ogni utente. Ecco un esempio:

        ![Screenshot della](media/activity-log-policy-assignment-detail.png)

    - **Inviato:** data e ora di invio dell'assegnazione dei criteri.
    - **Ora di completamento:** data e ora di completamento dell'assegnazione dei criteri.
    - **Impatto su:** numero di utenti nel batch.
    - **Stato generale:** stato dell'assegnazione dei criteri.

> [!NOTE]
> Puoi anche accedere al log attività dalla **pagina** Utenti. Dopo aver fatto **clic su** Applica per inviare un'assegnazione di criteri in blocco, nella parte superiore della pagina verrà visualizzato un banner. Fai clic **sul collegamento Log** attività nel banner.

## <a name="related-topics"></a>Argomenti correlati

- [Assegnare criteri agli utenti](assign-policies.md)

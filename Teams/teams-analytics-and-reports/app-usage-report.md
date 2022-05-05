---
title: Microsoft Teams report sull'utilizzo delle app
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-quhur
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Informazioni su come usare il report sull'utilizzo delle app Teams nell'interfaccia di amministrazione di Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a8ef86a0387c3966b795c323d1c28d0e1ca788e1
ms.sourcegitcommit: e102d72e67ab1c440c29ae6a048fc2cf8545fe01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2022
ms.locfileid: "65217950"
---
# <a name="microsoft-teams-app-usage-report"></a>Microsoft Teams report sull'utilizzo delle app

Il report sull'utilizzo delle app Teams nell'interfaccia di amministrazione di Microsoft Teams fornisce informazioni sulle app usate dagli utenti in Teams.  

## <a name="view-the-app-usage-report"></a>Visualizzare il report Utilizzo app

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione in <https://admin.teams.microsoft.com>fare clic su **Analytics &** **reportUsa** >  report.<br><br>![Screenshot della voce di menu Report utilizzo.](media/app-usage-report1.png "Screenshot della voce di menu Report utilizzo.")
2. Nella scheda **Visualizza report** , in **Report**, selezionare **Utilizzo app**.

3. In **Intervallo di date** selezionare un intervallo e quindi fare clic su **Esegui report**. Il report sull'utilizzo di Teams app può essere visualizzato per le tendenze degli ultimi 7, 30 o 90 giorni.<br><br>![Screenshot del report Utilizzo app.](media/app-usage-report2.png "Screenshot del report Utilizzo app.")


## <a name="interpret-the-report"></a>Interpretare il report

:::image type="content" alt-text="Screenshot del report sull'utilizzo delle app Teams nell'interfaccia di amministrazione di Teams con callout." source="media/app-usage-report5.png" lightbox="media/app-usage-report5.png":::

Ogni report ha una data in alto a sinistra che indica la data di creazione del report. I report in genere riflettono una latenza di 24 ore rispetto all'apertura di un'app.

L'asse Y nel grafico è il numero di utenti che per la data selezionata passando il puntatore del mouse sul grafico sono considerati utenti attivi perché hanno aperto un'app almeno una volta.

L'asse X del grafico corrisponde all'intervallo di date selezionato per il report.

Passa il puntatore del mouse sul punto (4) che rappresenta l'utilizzo di un'app in qualsiasi data per visualizzare il numero totale di utenti attivi dell'app in tale data.

Per selezionare altre app, nell'angolo in alto a destra fare clic sull'icona **Filtro** (5), selezionare o digitare nuovi criteri e quindi fare clic su **Applica**.

La tabella nella parte inferiore del report (6) mostra gli utenti attivi e i team in base al nome dell'app.

   - **Nome app** è il nome visualizzato dell'app usata in Teams.
   - **Utenti attivi** è il numero di utenti che hanno aperto l'app almeno una volta durante il periodo di tempo specificato.
   - **Il tipo di app** è un valore statico di "Microsoft" o "Terze parti".
   - **Team attivi** è il numero di team che hanno aperto l'app da almeno un membro del team e durante i periodi di tempo specificati.
   - **Publisher** è l'autore del software dell'app.
   - **La versione** è la versione software dell'app, dell'autore dell'app.

   > [!NOTE]
   > **Gli utenti attivi** e **i team attivi** vengono calcolati solo per le app usate nei canali.

Per aggiungere o rimuovere colonne nella tabella, nell'angolo in alto a destra fare clic sull'icona **Modifica colonne** (7), nella scheda **Modifica colonne** selezionare nuovi criteri e quindi fare clic su **Applica**.

Per esportare il report in un file CSV per l'analisi offline, nell'angolo in alto a destra selezionare l'icona **Esporta in Excel** (8), quindi nella scheda **Download** in **Stato** fare clic su **Scarica**.

   :::image type="content" alt-text="Screenshot del riquadro Download." source="media/app-usage-report7.png" lightbox="media/app-usage-report7.png":::

Quando si visualizza il report in Excel, viene visualizzata anche una colonna **Id**, che rappresenta l'ID dell'app, in genere una stringa alfanumerica. Se **l'ID** è **\n**, significa che un utente ha chiesto di eliminare le informazioni.

   ![Screenshot del report Excel scaricato.](media/app-usage-report8.png "Screenshot del report Excel scaricato.")

## <a name="related-topics"></a>Argomenti correlati

- [Analisi e creazione dei report di Teams](teams-reporting-reference.md).

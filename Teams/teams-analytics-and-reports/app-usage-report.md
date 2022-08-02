---
title: Report utilizzo app Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: Informazioni su come usare il report sull'utilizzo dell'app Teams nell'interfaccia di amministrazione di Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f9dadab5ee29a15e939a120cddcd3e889d524d88
ms.sourcegitcommit: 07761c26b53d92fc36b82cab7b3e38a6de4ff945
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2022
ms.locfileid: "67156724"
---
# <a name="microsoft-teams-app-usage-report"></a>Report utilizzo app Microsoft Teams

Il report Utilizzo app Teams nell'interfaccia di amministrazione di Microsoft Teams fornisce informazioni sulle app usate dagli utenti in Teams.  

## <a name="view-the-app-usage-report"></a>Visualizzare il report Utilizzo app

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Teams selezionare **Analisi & report** > **[utilizzo](https://admin.teams.microsoft.com/analytics/reports)**.

   :::image type="content" source="media/app-usage-report1.png" alt-text="Screenshot della voce di menu Report utilizzo.":::

1. Nella scheda **Visualizza report** , in **Report**, selezionare **Utilizzo app**.

1. In **Intervallo di date** selezionare un intervallo e quindi **selezionare Esegui report**. È possibile visualizzare il report Utilizzo app di Teams per le tendenze degli ultimi 7, 30 o 90 giorni.

   :::image type="content" source="media/app-usage-report2-trimmed.png" alt-text="Screenshot dell'interfaccia del report Utilizzo app." lightbox="media/app-usage-report2.png":::

## <a name="interpret-the-report"></a>Interpretare il report

:::image type="content" alt-text="Screenshot del report utilizzo app Teams nell'interfaccia di amministrazione di Teams con callout." source="media/app-usage-report5.png" lightbox="media/app-usage-report5.png":::

Ogni report ha una data in alto a sinistra che indica la data di creazione del report. I report in genere riflettono una latenza di 24 ore rispetto all'apertura di un'app.

L'asse Y del grafico è il numero di utenti che per la data selezionata passando il puntatore del mouse sul grafico sono considerati utenti attivi. Gli utenti che aprono un'app almeno una volta vengono considerati utenti attivi.

L'asse X del grafico corrisponde all'intervallo di date selezionato per il report.

Passa il puntatore del mouse sul punto (4) che rappresenta l'utilizzo di un'app in qualsiasi data per visualizzare il numero totale di utenti attivi dell'app in tale data.

Per selezionare altre app, nell'angolo in alto a destra seleziona l'icona **Filtro** (5), seleziona o digita nuovi criteri e quindi seleziona **Applica**.

La tabella nella parte inferiore del report (6) mostra gli utenti attivi e i team in base al nome dell'app.

   - **Nome app** è il nome visualizzato dell'app usata in Teams.
   - **Utenti attivi** è il numero di utenti che hanno aperto l'app almeno una volta durante il periodo di tempo specificato.
   - **Il tipo di app** è un valore statico di "Microsoft" o "Terze parti".
   - **Team attivi** è il numero di team che hanno aperto l'app da almeno un membro del team e durante i periodi di tempo specificati.
   - **Publisher** è lo sviluppatore del software dell'app.
   - **La versione** è la versione software dell'app, dallo sviluppatore dell'app.

   > [!NOTE]
   > **Gli utenti attivi** e **i team attivi** vengono calcolati solo per le app usate nei canali.

Per aggiungere o rimuovere colonne nella tabella, nell'angolo in alto a destra selezionare l'icona **Modifica colonne** (7), nella scheda **Modifica colonne** selezionare nuovi criteri e quindi **applica**.

Per esportare il report in un file CSV per l'analisi offline, nell'angolo in alto a destra selezionare l'icona **Esporta in Excel** (8) e quindi nella scheda **Download** in **Stato** selezionare **Scarica**.

   :::image type="content" alt-text="Screenshot del riquadro Download." source="media/app-usage-report7.png" lightbox="media/app-usage-report7.png":::

Quando si visualizza il report in Microsoft Excel, viene visualizzata anche una `Id` colonna, che rappresenta l'ID app, in genere una stringa alfanumerica. Se il valore di `Id` è **\n**, significa che un utente ha chiesto di eliminare le informazioni.

   :::image type="content" source="media/app-usage-report8.png" alt-text="Screenshot del report di Excel scaricato.":::

## <a name="related-articles"></a>Articoli correlati

- [Analisi e creazione dei report di Teams](teams-reporting-reference.md).

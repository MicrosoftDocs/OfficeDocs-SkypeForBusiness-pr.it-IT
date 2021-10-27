---
title: Microsoft Teams utilizzo delle app
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
description: Informazioni su come usare il report sull'Teams di utilizzo delle app nell'Microsoft Teams di amministrazione.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7679652f0cb93e445e72af80307803b1e3197992
ms.sourcegitcommit: b57e19e20900ff02f3196c811bf1dd1acd149c79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2021
ms.locfileid: "60596213"
---
# <a name="microsoft-teams-app-usage-report"></a>Microsoft Teams utilizzo delle app

Il report Teams sull'utilizzo delle app nell'interfaccia di amministrazione di Microsoft Teams fornisce informazioni sulle app che gli utenti usano in Teams.  

## <a name="view-the-app-usage-report"></a>Visualizzare il report Utilizzo app

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione in fare clic su Analisi & <https://admin.teams.microsoft.com> **report**  >  **utilizzo**.<br><br>![Screenshot della voce di menu Report di utilizzo.](media/app-usage-report1.png "Screenshot della voce di menu Report di utilizzo.")
2. Nella scheda **Visualizza report,** in **Report,** selezionare **Utilizzo app.**

3. In **Intervallo di date** selezionare un intervallo e quindi fare clic su Esegui **report.** Il report Teams utilizzo delle app può essere visualizzato per le tendenze degli ultimi 7, 30 o 90 giorni.<br><br>![Screenshot del report Utilizzo app.](media/app-usage-report2.png "Screenshot del report Utilizzo app.")


## <a name="interpret-the-report"></a>Interpretare il report

:::image type="content" alt-text="Screenshot del report sull Teams di utilizzo delle app nell'Teams di amministrazione con callout." source="media/app-usage-report5.png" lightbox="media/app-usage-report5.png":::

1. Ogni report ha una data in alto a sinistra che mostra quando è stato creato il report. I report in genere riflettono una latenza di 24 ore dall'apertura di un'app.

2. L'asse Y del grafico è il numero di utenti che per la data selezionata passando il puntatore del mouse sul grafico vengono considerati utenti attivi perché hanno aperto un'app almeno una volta.

3. L'asse X del grafico è l'intervallo di date selezionato per il report.

4. Posizionare il puntatore del mouse sul punto che rappresenta l'utilizzo di un'app in qualsiasi data per visualizzare il numero totale di utenti attivi dell'app in tale data.

5. Per selezionare altre app, in alto a destra fare clic **sull'icona** Filtro, selezionare o digitare nuovi criteri e quindi fare clic su **Applica.**

6. La tabella nella parte inferiore del report mostra gli utenti attivi e i team in base al nome dell'app.

   - **Il nome dell'app** è il nome visualizzato dell'app usata in Teams.
   - **Utenti attivi** è il numero di utenti che hanno aperto l'app almeno una volta durante il periodo di tempo specificato.
   - **Il tipo di** app è un valore statico di "Microsoft" o "Terze parti".
   - **Team attivi** è il numero di team che hanno aperto l'app da almeno un membro del team e durante i periodi di tempo specificati.
   - **Publisher** è l'autore del software dell'app.
   - **Versione** è la versione software dell'app, dell'autore dell'app.

   > [!NOTE]
   > **Gli utenti attivi** e **i team attivi** vengono calcolati solo per le app usate nei canali.

7. Per aggiungere o rimuovere colonne nella tabella, in  alto a destra  fare clic sull'icona Modifica colonne, nella scheda Modifica colonne selezionare nuovi criteri e quindi fare clic su **Applica.**

8. Per esportare il report in un file CSV per l'analisi offline, in alto a  destra selezionare l'icona **Esporta in Excel** e quindi nella scheda Download in **Stato** fare clic su **Scarica.**

   :::image type="content" alt-text="Screenshot del riquadro Download." source="media/app-usage-report7.png" lightbox="media/app-usage-report7.png":::

9. Quando si visualizza il report in Excel, viene visualizzata anche una colonna **Id,** che rappresenta l'ID dell'app, in genere una stringa alfanumerica. Se **l'ID** è **\n**, significa che un utente ha chiesto di eliminare le informazioni.

   ![Screenshot del report Excel download.](media/app-usage-report8.png "Screenshot del report Excel download.")

## <a name="related-topics"></a>Argomenti correlati

- [Analisi e creazione dei report di Teams](teams-reporting-reference.md).

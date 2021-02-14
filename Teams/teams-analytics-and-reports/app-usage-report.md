---
title: Report Utilizzo app Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-quhur
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Informazioni su come usare il report Utilizzo app Teams nell'interfaccia di amministrazione di Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 91af37ed9c19a1d3e8d32cdf296cf32e90818564
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583795"
---
# <a name="microsoft-teams-app-usage-report"></a>Report Utilizzo app Microsoft Teams

Il report Utilizzo app Teams nell'interfaccia di amministrazione di Microsoft Teams fornisce informazioni sulle app che gli utenti usano in Teams.  

## <a name="view-the-app-usage-report"></a>Visualizzare il report Utilizzo app

1.  Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione, fare clic su Analisi & <https://admin.teams.microsoft.com> **report** \> **sull'utilizzo.** Nella scheda **Visualizza report,** in **Report,** selezionare **Utilizzo app.**

     :::image type="content" source="media/app-usage-report1.png" alt-text="Screenshot della voce di menu Report utilizzo":::

2.  In **Intervallo di date** selezionare un intervallo e quindi fare clic su Esegui **report.**

      :::image type="content" source="media/app-usage-report2.png" alt-text="Screenshot del report Utilizzo app":::

## <a name="interpret-the-report"></a>Interpretare il report

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Il report Utilizzo app Teams può essere visualizzato per le tendenze degli ultimi 7, 30 o 90 giorni. |
|**2**   |Ogni report include la data in cui è stato generato. I report in genere riflettono una latenza di 24 ore dalla data di apertura di un'app. <br><br>![Screenshot del report Utilizzo app con intervalli di date](media/app-usage-report3.png)|
|**3**    | <ul><li>L'asse X nei grafici rappresenta l'intervallo di date selezionato per il report specifico.</li><li>L'asse Y è il numero di utenti a cui è stato fatto clic nel grafico per il giorno specificato, che hanno aperto un'app almeno una volta e in questo modo sono considerati utenti attivi e si attribinano al totale visualizzato al passaggio del mouse.</li></ul>|
|**4**   |Posizionare il puntatore del mouse sul punto che rappresenta un utilizzo delle app in una data specifica per visualizzare il numero di istanze di Total Active Users dell'app in tale data.  |
|**5**   |Verranno incluse tutte le app, ma scegliendo l'icona del filtro saranno disponibili altri filtri.  |
|**6**   |La tabella fornisce un'analisi degli utenti attivi e dei team in base al nome dell'app.<br><ul><li>**Il nome dell'app** è il nome visualizzato dell'app usata in Teams.</li><li>**Utenti attivi** è il numero di utenti che hanno aperto l'app almeno una volta durante il periodo di tempo specificato.</li><li>**Il tipo** di app è un valore statico di "Microsoft" o "Di terze parti".</li><li>**Team attivi** è il numero di team che hanno aperto l'app da almeno un membro del team e durante i periodi di tempo specificati.</li><li>**Publisher** è l'autore software dell'app.</li><li>**La versione** è la versione software dell'app, dell'autore dell'app.</li></ul><br>![Screenshot di un report Utilizzo app](media/app-usage-report4.png)  |
|**7**  |Selezionare **Modifica colonne** per aggiungere o rimuovere colonne nella tabella.<br><br>![Screenshot della pagina Modifica colonne](media/app-usage-report5.png)  |
|**8**  |È possibile esportare il report in un file CSV per l'analisi offline. Fare clic su Esporta in **Excel,** quindi nella **scheda Download** fare clic su **Scarica** per scaricare il report quando è pronto.<br>![Screenshot della pagina Download](media/app-usage-report7.png)  |
|**9**   |Quando si visualizza il report in Excel, viene visualizzata anche una colonna **ID** che rappresenta l'ID dell'app. Un ID team è in genere una stringa alfanumerica. Se la **colonna ID** viene visualizzata come **\n****, significa che un utente ha richiesto l'eliminazione delle informazioni.<br>![Screenshot del report di Excel scaricato](media/app-usage-report8.png)  |

## <a name="related-topics"></a>Argomenti correlati

- [Analisi e creazione di report di Teams](teams-reporting-reference.md)
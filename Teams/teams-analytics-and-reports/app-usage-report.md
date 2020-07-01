---
title: Report sull'utilizzo delle app di Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
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
description: Informazioni su come usare il report sull'utilizzo dell'app teams nell'interfaccia di amministrazione di Microsoft teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 565a3cb28b73a37162947859effc6ec154b59258
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938205"
---
# <a name="microsoft-teams-app-usage-report"></a>Report sull'utilizzo delle app di Microsoft Teams

Il report sull'utilizzo dell'app teams nell'interfaccia di amministrazione di Microsoft teams fornisce informazioni sulle app che gli utenti usano in teams.  

## <a name="view-the-app-usage-report"></a>Visualizzare il report sull'utilizzo dell'app

1.  Nella barra di spostamento sinistra dell'interfaccia di amministrazione <https://admin.teams.microsoft.com> fare clic su **analisi &** report \> **utilizzo**rapporti. Nella scheda **Visualizza report** , in **report**, selezionare **utilizzo app**.

     :::image type="content" source="media/app-usage-report1.png" alt-text="Screenshot della voce di menu report utilizzo":::

2.  In **intervallo di date**selezionare un intervallo e quindi fare clic su **Esegui report**.

      :::image type="content" source="media/app-usage-report2.png" alt-text="Screenshot del report sull'utilizzo delle app":::

## <a name="interpret-the-report"></a>Interpretare il report

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Il report sull'utilizzo delle app teams può essere visualizzato per le tendenze degli ultimi 7, 30 o 90 giorni. |
|**2**   |Ogni report ha una data in cui è stato generato il report. I report riflettono in genere una latenza di 24 ore dal momento in cui è stata aperta un'app. <br><br>![Screenshot del report sull'utilizzo delle app che Mostra gli intervalli di date](media/app-usage-report3.png)|
|**3**    | <ul><li>L'asse X nei grafici è l'intervallo di date selezionato per il report specifico.</li><li>L'asse Y è il numero di utenti che per il giorno indicato si aggirano nel grafico, gli utenti hanno aperto un'app almeno una volta e, in questo modo, sono considerati un utente attivo e si accumulano verso il totale visto al passaggio del mouse.</li></ul>|
|**4**   |Posizionare il puntatore del mouse sul punto che rappresenta un uso di app in una data specifica per visualizzare il numero di istanze degli utenti attivi totali di tale app in quella data specificata.  |
|**5**   |Tutte le app verranno incluse, ma scegliendo l'icona filtro sono disponibili altri filtri.  |
|**6**   |La tabella offre una ripartizione degli utenti e dei team attivi per nome dell'app.<br><ul><li>**Nome app** è il nome visualizzato dell'app usata in teams.</li><li>**Utenti attivi** è il numero di utenti che hanno aperto l'app almeno una volta durante il periodo di tempo specificato.</li><li>Il **tipo di app** è un valore statico di "Microsoft" o "Third Party".</li><li>**Team attivi** è il numero di team che hanno aperto l'app da almeno un membro del team e durante i periodi di tempo specificati.</li><li>**Publisher** è l'editore del software dell'app.</li><li>**Versione** è la versione software dell'app, dall'App Publisher.</li></ul><br>![Screenshot di un report sull'utilizzo delle app](media/app-usage-report4.png)  |
|**7**  |Selezionare **modifica colonne** per aggiungere o rimuovere colonne nella tabella.<br><br>![Screenshot della pagina Modifica colonne](media/app-usage-report5.png)  |
|**8**  |È possibile esportare il report in un file CSV per l'analisi offline. Fare clic su **Esporta in Excel**, quindi nella scheda **download** fare clic su **Scarica** per scaricare il report quando è pronto.<br>![Schermata della pagina downloads](media/app-usage-report7.png)  |
|**9**   |Quando si Visualizza il report in Excel, viene visualizzata anche una colonna **ID** , che rappresenta l'ID app. Un ID team è in genere una stringa alfanumerica. Se la colonna **ID** viene visualizzata come * * \n * * * *, significa che un utente ha richiesto le informazioni da eliminare.<br>![Screenshot del report di Excel scaricato](media/app-usage-report8.png)  |

## <a name="related-topics"></a>Argomenti correlati

- [Analisi e creazione di report in teams](teams-reporting-reference.md)
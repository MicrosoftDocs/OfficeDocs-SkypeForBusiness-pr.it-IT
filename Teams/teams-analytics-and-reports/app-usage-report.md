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
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Informazioni su come usare il report sull'Teams di utilizzo delle app nell'Microsoft Teams di amministrazione.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 592b333a8a46e90d6092445a6021341887f1b64ff8f26932f4912a6d9a8e7e56
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54308367"
---
# <a name="microsoft-teams-app-usage-report"></a>Microsoft Teams utilizzo delle app

Il report Teams utilizzo delle app nell'interfaccia Microsoft Teams di amministrazione fornisce informazioni sulle app che gli utenti usano in Teams.  

## <a name="view-the-app-usage-report"></a>Visualizzare il report Utilizzo app

1.  Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione in fare clic su Analisi & <https://admin.teams.microsoft.com> **report** \> **utilizzo**. Nella scheda **Visualizza report,** in **Report,** selezionare **Utilizzo app.**

     :::image type="content" source="media/app-usage-report1.png" alt-text="Screenshot della voce di menu Report di utilizzo":::

2.  In **Intervallo di date** selezionare un intervallo e quindi fare clic su Esegui **report.**

      :::image type="content" source="media/app-usage-report2.png" alt-text="Screenshot del report Utilizzo app":::

## <a name="interpret-the-report"></a>Interpretare il report

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Il report Teams utilizzo delle app può essere visualizzato per le tendenze degli ultimi 7, 30 o 90 giorni. |
|**2**   |Ogni report ha una data in cui è stato generato il report. I report in genere riflettono una latenza di 24 ore dall'apertura di un'app. <br><br>![Screenshot del report Utilizzo app che mostra gli intervalli di date](media/app-usage-report3.png)|
|**3**    | <ul><li>L'asse X nei grafici è l'intervallo di date selezionato per il report specifico.</li><li>L'asse Y è il numero di utenti che per il giorno specificato si sono posizionati nel grafico, gli utenti hanno aperto un'app almeno una volta e in questo modo vengono considerati utenti attivi e maturati verso il totale visualizzato al passaggio del mouse.</li></ul>|
|**4**   |Passare il puntatore del mouse sul punto che rappresenta un utilizzo delle app in una data specifica per visualizzare il numero di istanze di Total Active Users dell'app in quella data.  |
|**5**   |Tutte le app verranno incluse, ma scegliendo l'icona Filtro sono disponibili altri filtri.  |
|**6**   |La tabella fornisce una suddivisione degli utenti attivi e dei team in base al nome dell'app.<br><ul><li>**Il nome dell'app** è il nome visualizzato dell'app usata in Teams.</li><li>**Utenti attivi** è il numero di utenti che hanno aperto l'app almeno una volta durante il periodo di tempo specificato.</li><li>**Il tipo di** app è un valore statico di "Microsoft" o "Terze parti".</li><li>**Team attivi** è il numero di team che hanno aperto l'app da almeno un membro del team e durante i periodi di tempo specificati.</li><li>**Publisher** è l'autore del software dell'app.</li><li>**Versione** è la versione software dell'app, dell'autore dell'app.</li></ul><b> Nota:</b> Attualmente, "Utenti attivi" e "Team attivi" vengono calcolati solo per le app usate nei canali.     

<br>![Screenshot di un report utilizzo ](media/app-usage-report4.png)  app | |**7**  | Selezionare **Modifica colonne** per aggiungere o rimuovere colonne nella tabella.<br><br>![Screenshot della pagina Modifica colonne ](media/app-usage-report5.png)  | |**8**  | È possibile esportare il report in un file CSV per l'analisi offline. Fare **clic su Esporta in Excel** e quindi nella scheda **Download** fare clic su **Scarica** per scaricare il report quando è pronto.<br>![Screenshot della pagina ](media/app-usage-report7.png) Download | |**9** | Quando si visualizza il report in Excel, viene visualizzata anche una colonna **Id,** che rappresenta l'ID dell'app. Un ID team è in genere una stringa alfanumerica. Se la **colonna Id** viene visualizzata come **\n*****, significa che un utente ha richiesto l'eliminazione delle informazioni.<br>![Screenshot del report di Excel scaricato](media/app-usage-report8.png)  |

## <a name="related-topics"></a>Argomenti correlati

- [Analisi e creazione dei report di Teams](teams-reporting-reference.md).
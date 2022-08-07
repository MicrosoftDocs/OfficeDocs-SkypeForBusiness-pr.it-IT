---
title: Report pool di minuti PSTN di Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Come usare il report pool di minuti PSTN di Teams nell'interfaccia di amministrazione di Microsoft Teams per visualizzare i minuti consumati all'interno dell'organizzazione durante il mese corrente.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-voice
ms.openlocfilehash: d3e2b4d7d0aba44929b7094c4146f9f69db0e8eb
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267371"
---
# <a name="microsoft-teams-pstn-minute-pools-report"></a>Report pool di minuti PSTN di Microsoft Teams

Il report Pool di minuti PSTN di Teams nell'interfaccia di amministrazione di Microsoft Teams offre una panoramica delle audioconferenze e delle attività di chiamata nell'organizzazione mostrando il numero di minuti consumati durante il mese corrente. È possibile visualizzare un'analisi delle attività, inclusa la licenza usata per le chiamate, i minuti totali disponibili, i minuti usati e l'utilizzo delle licenze in base alla posizione.

## <a name="view-the-pstn-minute-pools-report"></a>Visualizzare il report pool di minuti PSTN

Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams fare clic su **Analisi & report** > **utilizzo**. Nella scheda **Visualizza report** , in **Report**, selezionare **Pool di minuti PSTN e SMS (anteprima),** quindi fare clic su **Esegui report**.

![Screenshot del report pool di minuti PSTN di Teams nell'interfaccia di amministrazione.](../media/teams-reports-pstn-minute-pools-with-callouts.png "Screenshot del report pool di minuti PSTN di Teams nell'interfaccia di amministrazione di Microsoft Teams con callout numerati")

## <a name="interpret-the-report"></a>Interpretare il report

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Ogni report ha una data per la generazione. In genere, i report presentano una latenza di 24-48 ore dal momento dell'attività. |
|**2**   |Fare clic su una funzionalità (licenza) per visualizzare le attività relative a tale funzionalità. |
|**3**   |L'asse X è il paese o l'area geografica. L'asse Y è il numero di minuti. <br>Passare il puntatore del mouse su una barra nel grafico per visualizzare l'attività relativa alla posizione di utilizzo.  |
|**4**   |È possibile filtrare gli elementi visualizzati nel grafico facendo clic su un elemento nella legenda. Ad esempio, fare clic su **Inutilizzati**, **Utenti nazionali**, **Nessun dato** o **Dati internazionali usati** per visualizzare solo le informazioni pertinenti. |
|**5**   |La tabella fornisce un'analisi dei pool di minuti per funzionalità e posizione di utilizzo. <ul><li>**Il paese o l'area geografica** è la posizione di utilizzo. </li><li>**La descrizione della funzionalità** è la descrizione della licenza usata per la chiamata.  Le descrizioni delle funzionalità che possono essere visualizzate in questo report includono: <ul><li>Piano per chiamate nazionali e internazionali (1200 minuti di chiamate nazionali)</li><li>Piano per chiamate nazionali e internazionali (3000 minuti di chiamate nazionali)</li><li>Piano per chiamate nazionali e internazionali (600 minuti di chiamate internazionali)</li></ul></li><br><li>**Il totale dei minuti** è il numero totale di minuti disponibili per il mese.</li><li>**Minuti utilizzati** è il numero di minuti utilizzati ogni mese</li> <li>**Minuti disponibili** è il numero di minuti rimanenti per il mese.</li><li>**Capacità** è la licenza usata per la chiamata. Le licenze visualizzate includono:<ul><li>**MCOPSTN1** - Piano per chiamate nazionali (piani per 3000 min USA/1200 min UE)</li><li>**MCOPSTN2** - Piano per chiamate internazionali</li><li>**MCOPSTN5** - Piano per chiamate nazionali (piano per chiamate da 120 minuti)</li><li>**MCOPSTN6** - Piano per chiamate nazionali (piano per chiamate da 240 minuti)</li><li>**MCOMEETADD** - Audioconferenza</li></ul></li> </ul> Per visualizzare le informazioni desiderate nella tabella, assicurarsi di aggiungere le colonne alla tabella.|
|**6**   |Selezionare **Modifica colonne** per aggiungere o rimuovere colonne nella tabella.|
|**7**   |Selezionare **Schermo intero** per visualizzare il report in modalità schermo intero.|

## <a name="related-topics"></a>Argomenti correlati

- [Analisi e creazione dei report di Teams](teams-reporting-reference.md).

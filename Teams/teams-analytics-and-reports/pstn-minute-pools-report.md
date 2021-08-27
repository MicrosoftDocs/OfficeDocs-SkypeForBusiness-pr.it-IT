---
title: Microsoft Teams Report pool di minuti PSTN
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
MS.collection:
- M365-voice
description: Come usare il report Teams pool di minuti PSTN nell'interfaccia di amministrazione di Microsoft Teams per visualizzare i minuti consumati all'interno dell'organizzazione durante il mese corrente.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9dc0b12a17d54d6c0e5f858db92da3fc575d086f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58577750"
---
# <a name="microsoft-teams-pstn-minute-pools-report"></a>Microsoft Teams Report pool di minuti PSTN

Il report Teams pool di minuti PSTN nell'interfaccia di amministrazione di Microsoft Teams offre una panoramica delle attività di audioconferenza e chiamate nell'organizzazione mostrando il numero di minuti consumati durante il mese corrente. È possibile visualizzare una suddivisione delle attività, tra cui la licenza usata per le chiamate, i minuti totali disponibili, i minuti usati e l'utilizzo delle licenze in base alla posizione.

## <a name="view-the-pstn-minute-pools-report"></a>Visualizzare il report pool di minuti PSTN

Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione fare clic su Analisi & **report**  >  **utilizzo**. Nella scheda **Visualizza report,** in **Report,** selezionare Pool di minuti **PSTN** e quindi fare clic su **Esegui report.**

![Screenshot del report Teams pool di minuti PSTN nell'interfaccia di amministrazione](../media/teams-reports-pstn-minute-pools-with-callouts.png "Screenshot del report Teams pool di minuti PSTN nell'interfaccia Microsoft Teams di amministrazione con callout numerati")

## <a name="interpret-the-report"></a>Interpretare il report

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Ogni report ha una data in cui è stato generato. In genere, i report presentano una latenza di 24-48 ore dal momento dell'attività. |
|**2**   |Fare clic su una funzionalità (licenza) per visualizzare le attività per tale funzionalità. |
|**3**   |L'asse X è il paese o l'area geografica. L'asse Y è il numero di minuti. <br>Posizionare il puntatore del mouse su una barra del grafico per visualizzare l'attività per la posizione di utilizzo.  |
|**4**   |È possibile filtrare gli elementi visualizzati nel grafico facendo clic su un elemento nella legenda. Ad esempio, fare **clic su Inutilizzati**  , **Utenti nazionali** **,** Nessun dato o Internazionale per visualizzare solo le informazioni correlate a ognuno di essi. |
|**5**   |La tabella fornisce una suddivisione dei pool di minuti in base alla capacità e alla posizione di utilizzo. <ul><li>**Paese o area geografica** è il luogo di utilizzo. </li><li>**Descrizione funzionalità** è la descrizione della licenza usata per la chiamata.  Le descrizioni delle funzionalità che è possibile visualizzare in questo report includono: <ul><li>Piano per chiamate nazionali e internazionali (1200 minuti nazionali)</li><li>Piano per chiamate nazionali e internazionali (3000 minuti nazionali)</li><li>Piano per chiamate nazionali e internazionali (600 minuti internazionali)</li></ul></li><br><li>**Totale minuti** è il numero totale di minuti disponibili per il mese.</li><li>**Minuti usati** è il numero di minuti usati ogni mese</li> <li>**Minuti disponibili** è il numero di minuti rimanenti per il mese.</li><li>**Capacità** è la licenza usata per la chiamata. Le licenze che potresti vedere includono:<ul><li>**MCOPSTN1** - Piano per chiamate nazionali (3000 min piani UE per gli Stati Uniti/ 1200 min)</li><li>**MCOPSTN2** - Piano per chiamate internazionali</li><li>**MCOPSTN5** - Piano per chiamate nazionali (piano per chiamate da 120 minuti)</li><li>**MCOPSTN6** - Piano per chiamate nazionali (piano per chiamate di 240 minuti)</li><li>**MCOMEETADD** - Audioconferenza</li></ul></li> </ul> Per visualizzare le informazioni desiderate nella tabella, assicurarsi di aggiungere le colonne alla tabella.|
|**6**   |Selezionare **Modifica colonne** per aggiungere o rimuovere colonne nella tabella.|
|**7**   |Selezionare **Schermo intero** per visualizzare il report in modalità a schermo intero.|

## <a name="related-topics"></a>Argomenti correlati

- [Analisi e creazione dei report di Teams](teams-reporting-reference.md).

---
title: Report pool di minuti PSTN di Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
MS.collection:
- M365-voice
description: Come usare il report pool di minuti PSTN di Teams nell'interfaccia di amministrazione di Microsoft Teams per visualizzare i minuti consumati all'interno dell'organizzazione durante il mese corrente.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8df0c1201f963a1c00742532f80089b523ca79aa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809346"
---
# <a name="microsoft-teams-pstn-minute-pools-report"></a>Report pool di minuti PSTN di Microsoft Teams

Il report pool di minuti PSTN di Teams nell'interfaccia di amministrazione di Microsoft Teams offre una panoramica delle attività di audioconferenza e chiamate nella tua organizzazione, mostrando il numero di minuti consumati durante il mese corrente. È possibile visualizzare un'analisi delle attività, tra cui la licenza usata per le chiamate, i minuti totali disponibili, i minuti utilizzati e l'utilizzo della licenza in base alla posizione.

## <a name="view-the-pstn-minute-pools-report"></a>Visualizzare il report di pool di minuti PSTN

Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, fare clic su **Analisi & report**  >  **sull'utilizzo.** Nella scheda **Visualizza report,** in **Report,** selezionare Pool di minuti **PSTN** e quindi fare clic **su Esegui report.**

![Screenshot del report pool di minuti PSTN di Teams nell'interfaccia di amministrazione](../media/teams-reports-pstn-minute-pools-with-callouts.png "Screenshot del report pool di minuti PSTN di Teams nell'interfaccia di amministrazione di Microsoft Teams con callout numerati")

## <a name="interpret-the-report"></a>Interpretare il report

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Ogni report include la data in cui è stato generato. In genere, i report presentano una latenza di 24-48 ore dal momento dell'attività. |
|**2**   |Fare clic su una funzionalità (licenza) per visualizzare le attività relative a tale funzionalità. |
|**3**   |L'asse X è il paese o l'area geografica. L'asse Y è il numero di minuti. <br>Posizionare il puntatore del mouse su una barra nel grafico per visualizzare l'attività per la località di utilizzo.  |
|**4**   |È possibile filtrare gli elementi visualizzati nel grafico facendo clic su un elemento nella legenda. Ad esempio, fare **clic su** Utenti non  **utilizzati,** Utenti **nazionali,** Nessun dato o Internazionale usato per visualizzare solo le informazioni per ognuno di essi. |
|**5**   |La tabella fornisce un'analisi dei pool di minuti in base alle capacità e alla posizione di utilizzo. <ul><li>**Il paese o l'area** geografica è la località di utilizzo. </li><li>**La descrizione della** funzionalità è la descrizione della licenza usata per la chiamata.  Le descrizioni delle funzionalità disponibili in questo report includono: <ul><li>Piano per chiamate nazionali e internazionali (1200 minuti di chiamate nazionali)</li><li>Piano per chiamate nazionali e internazionali (3000 minuti di chiamate nazionali)</li><li>Piano per chiamate nazionali e internazionali (600 minuti di chiamate internazionali)</li></ul></li><br><li>**Il totale** dei minuti è il numero totale di minuti disponibili per il mese.</li><li>**Minuti utilizzati** è il numero di minuti utilizzati ogni mese</li> <li>**Minuti disponibili** è il numero di minuti rimanenti per il mese.</li><li>**Capacità** è la licenza usata per la chiamata. Le licenze disponibili includono:<ul><li>**MCOPSTNPP** - Crediti comunicazioni</li><li>**MCOPSTN1** - Piano per chiamate nazionali (piani DA 3000 min USA /1200 min UE)</li><li>**MCOPSTN2** - Piano per chiamate internazionali</li><li>**MCOPSTN5** - Piano per chiamate nazionali (piano da 120 min)</li><li>**MCOPSTN6** - Piano per chiamate nazionali (piano per chiamate da 240 min)</li><li>**MCOMEETADD** - Audioconferenza</li><li>**MCOMEETACPEA** - Audioconferenza con pagamento al minuto</li></ul></li> </ul> Per visualizzare le informazioni desiderate nella tabella, assicurarsi di aggiungere le colonne alla tabella.|
|**6**   |Selezionare **Modifica colonne** per aggiungere o rimuovere colonne nella tabella.|
|**7**   |Selezionare **Schermo intero** per visualizzare il report in modalità a schermo intero.|

## <a name="related-topics"></a>Argomenti correlati

- [Analisi e creazione di report di Teams](teams-reporting-reference.md)
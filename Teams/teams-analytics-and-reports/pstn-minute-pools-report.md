---
title: Report pool di minuti PSTN di Microsoft Teams
author: LanaChin
ms.author: v-lanac
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
description: Informazioni su come usare il report pool di minuti PSTN in teams nell'interfaccia di amministrazione di Microsoft teams per visualizzare il numero di minuti consumati durante il mese corrente all'interno dell'organizzazione.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0fa9b8f4a676c1e937fed02eabc0e7cd4acd5325
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827324"
---
# <a name="microsoft-teams-pstn-minute-pools-report"></a>Report pool di minuti PSTN di Microsoft Teams

Il report pool di minuti PSTN di teams nell'interfaccia di amministrazione di Microsoft teams offre una panoramica dei servizi di audioconferenza e delle attività di chiamata nell'organizzazione, mostrando il numero di minuti consumati durante il mese corrente. È possibile visualizzare una ripartizione delle attività, inclusa la licenza usata per le chiamate, i minuti totali disponibili, i minuti usati e l'utilizzo della licenza in base alla posizione.

## <a name="view-the-report"></a>Visualizzare il report

Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams fare clic su **analisi &** > report**sull'utilizzo**dei rapporti. Nella scheda **Visualizza report** , in **report**, selezionare **pool di minuti PSTN**e quindi fare clic su **Esegui report**.

![Screenshot del report pool di minuti PSTN di teams nell'interfaccia di amministrazione](../media/teams-reports-pstn-minute-pools-with-callouts.png "Screenshot del report pool di minuti PSTN di teams nell'interfaccia di amministrazione di Microsoft teams con callout numerati")

## <a name="interpret-the-report"></a>Interpretare il report

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Ogni report ha una data per quando è stata generata. In genere, i report presentano una latenza di 24-48 ore dal momento dell'attività. |
|**2**   |Fare clic su una funzionalità (licenza) per visualizzare le attività per tale funzionalità. |
|**3**   |L'asse X è paese o area geografica. L'asse Y è il numero di minuti. <br>Posizionare il puntatore del mouse su una barra del grafico per visualizzare l'attività relativa alla posizione di utilizzo.  |
|**4**   |È possibile filtrare gli elementi visualizzati nel grafico facendo clic su un elemento nella legenda. Ad esempio, fai clic su **utenti domestici**non **usati**, **Nessun dato**o **internazionale usato** per visualizzare solo le informazioni relative a ognuna di esse. |
|**5**   |La tabella offre una ripartizione dei pool di minuti in base alla capacità e alla posizione di utilizzo. <ul><li>**Paese o area geografica** è la posizione di utilizzo. </li><li>**Descrizione della funzionalità** è la descrizione della licenza usata per la chiamata.  Le descrizioni delle funzionalità che potrebbero essere visualizzate in questo report includono: <ul><li>Piano per chiamate nazionali e internazionali (1200 minuti nazionali)</li><li>Piano per chiamate nazionali e internazionali (3000 minuti nazionali)</li><li>Piano per chiamate nazionali e internazionali (600 minuti internazionali)</li></ul></li><br><li>**Minuti totali** indica il numero totale di minuti disponibili per il mese.</li><li>**Minuti usati** è il numero di minuti usati ogni mese</li> <li>**Minuti disponibili** indica il numero di minuti rimanenti per il mese.</li><li>**Capacità** è la licenza usata per la chiamata. Le licenze visualizzate includono:<ul><li>**MCOPSTNPP** -Credits comunicazioni</li><li>**MCOPSTN1** -piano per chiamate nazionali (3000 min US/1200 min eu plans)</li><li>**MCOPSTN2** -piano per chiamate internazionali</li><li>**MCOPSTN5** -piano per chiamate nazionali (piano per chiamate 120 min)</li><li>**MCOPSTN6** -piano per chiamate nazionali (piano per chiamate 240 min)</li><li>**MCOMEETADD** -audioconferenza</li><li>**MCOMEETACPEA** -pay per minute audioconferenza</li></ul></li> </ul> Per visualizzare le informazioni desiderate nella tabella, assicurarsi di aggiungere le colonne alla tabella.|
|**6**   |Selezionare **modifica colonne** per aggiungere o rimuovere colonne nella tabella.|
|**7**   |Selezionare **schermo intero** per visualizzare il report in modalità schermo intero.|

## <a name="related-topics"></a>Argomenti correlati

- [Analisi e creazione di report in teams](teams-reporting-reference.md)
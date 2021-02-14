---
title: Report Utenti bloccati PSTN di Microsoft Teams
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
description: Usare il report utenti bloccati PSTN nell'interfaccia di amministrazione di Microsoft Teams per ottenere una panoramica degli utenti di Teams dell'organizzazione a cui è impedito effettuare chiamate.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ed775c3796e40a775b3be2b78f22e162a047bf78
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809336"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a>Report Utenti bloccati PSTN di Microsoft Teams

Il report Utenti bloccati PSTN nell'interfaccia di amministrazione di Microsoft Teams mostra gli utenti dell'organizzazione a cui è impedito effettuare chiamate PSTN in Teams. È possibile visualizzare altre informazioni su ogni utente bloccato, inclusi il numero di telefono assegnato e il motivo per cui gli è stato impedito di effettuare chiamate.

## <a name="view-the-pstn-blocked-users-report"></a>Visualizzare il report utenti bloccati PSTN

Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, fare clic su **Analisi & report**  >  **sull'utilizzo.** Nella scheda **Visualizza report,** in **Report,** selezionare Utenti bloccati **PSTN** e quindi fare clic **su Esegui report.**

![Screenshot del report Utenti bloccati PSTN nell'interfaccia di amministrazione](../media/teams-reports-pstn-blocked-users-with-callouts.png "Screenshot del report Utenti bloccati PSTN nell'interfaccia di amministrazione di Microsoft Teams con callout numerati")

## <a name="interpret-the-report"></a>Interpretare il report

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Ogni report include la data in cui è stato generato. In genere, i report presentano una latenza di 24-48 ore dal momento dell'attività. |
|**2**   |L'asse X rappresenta la data. L'asse Y è il numero di utenti. <br>Passare il puntatore del mouse sul punto in una data specifica per visualizzare il numero di utenti bloccati in tale data. |
|**3**   |La tabella fornisce un'analisi di tutti gli utenti a cui è impedito effettuare chiamate PSTN.  Mostra tutti gli utenti a cui è assegnato Sistema telefonico o Audioconferenza e fornisce maggiori informazioni su ogni utente. <ul><li>**Il nome** visualizzato è il nome visualizzato dell'utente. È possibile fare clic sul nome visualizzato per passare alla pagina delle impostazioni dell'utente nell'interfaccia di amministrazione di Microsoft Teams. </li> <li>**Il** numero di telefono è il numero assegnato all'utente.</li> <li>**Il motivo per** cui è bloccato l'esecuzione delle chiamate è il motivo per cui l'utente è bloccato.</li><li>**L'azione**  bloccata indica se l'utente è bloccato o sbloccato dall'esecuzione di chiamate PSTN in Teams.</li> <li>**L'ora** bloccata è la data e l'ora (UTC) in cui all'utente è stato impedito effettuare chiamate.</li></li> </ul>Per visualizzare le informazioni desiderate nella tabella, assicurarsi di aggiungere le colonne alla tabella. |
|**4**   |Selezionare **Modifica colonne** per aggiungere o rimuovere colonne nella tabella.|
|**5**   |Selezionare **Schermo intero** per visualizzare il report in modalità a schermo intero.|

## <a name="related-topics"></a>Argomenti correlati

- [Analisi e creazione di report di Teams](teams-reporting-reference.md)
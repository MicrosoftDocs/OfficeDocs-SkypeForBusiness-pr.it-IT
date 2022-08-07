---
title: Report utenti PSTN bloccati di Microsoft Teams
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
description: Usare il report Utenti pstn bloccati nell'interfaccia di amministrazione di Microsoft Teams per ottenere una panoramica degli utenti di Teams dell'organizzazione a cui è impedito effettuare chiamate PSTN.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-voice
ms.openlocfilehash: 8f723a9aca6cc57510aaf526297f60966a27bcda
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267381"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a>Report utenti PSTN bloccati di Microsoft Teams

Il report Utenti pstn bloccati nell'interfaccia di amministrazione di Microsoft Teams mostra gli utenti dell'organizzazione a cui è impedito effettuare chiamate PSTN in Teams. Puoi visualizzare altre informazioni su ogni utente bloccato, incluso il numero di telefono assegnato e il motivo per cui gli è stato impedito di effettuare chiamate.

## <a name="view-the-pstn-blocked-users-report"></a>Visualizzare il report Utenti bloccati PSTN

Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams fare clic su **Analisi & report** > **utilizzo**. Nella scheda **Visualizza report** , in **Report**, selezionare **Utenti bloccati PSTN** e quindi fare clic su **Esegui report**.

![Screenshot del report Utenti bloccati PSTN nell'interfaccia di amministrazione.](../media/teams-reports-pstn-blocked-users-with-callouts.png "Screenshot del report Utenti bloccati PSTN nell'interfaccia di amministrazione di Microsoft Teams con callout numerati")

## <a name="interpret-the-report"></a>Interpretare il report

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Ogni report ha una data per la generazione. In genere, i report presentano una latenza di 24-48 ore dal momento dell'attività. |
|**2**   |L'asse X è la data. L'asse Y è il numero di utenti. <br>Passare il puntatore del mouse sul punto in una data specificata per visualizzare il numero di utenti bloccati in tale data. |
|**3**   |La tabella fornisce un'analisi di tutti gli utenti a cui è impedito effettuare chiamate PSTN.  Mostra tutti gli utenti a cui è assegnato Sistema telefonico o Audioconferenza e fornisce ulteriori informazioni su ogni utente. <ul><li>**Nome visualizzato** è il nome visualizzato dell'utente. È possibile fare clic sul nome visualizzato per passare alla pagina delle impostazioni dell'utente nell'interfaccia di amministrazione di Microsoft Teams. </li> <li>**Telefono** è il numero assegnato all'utente.</li> <li>**Motivo bloccato** è il motivo per cui all'utente viene impedito di effettuare chiamate.</li><li>**L'azione bloccata**  indica se l'utente è bloccato o sbloccato dall'effettuare chiamate PSTN in Teams.</li> <li>**L'ora di blocco** è la data e l'ora (UTC) a cui all'utente è stato impedito di effettuare chiamate.</li></li> </ul>Per visualizzare le informazioni desiderate nella tabella, assicurarsi di aggiungere le colonne alla tabella. |
|**4**   |Selezionare **Modifica colonne** per aggiungere o rimuovere colonne nella tabella.|
|**5**   |Selezionare **Schermo intero** per visualizzare il report in modalità schermo intero.|

## <a name="related-topics"></a>Argomenti correlati

- [Analisi e creazione dei report di Teams](teams-reporting-reference.md).
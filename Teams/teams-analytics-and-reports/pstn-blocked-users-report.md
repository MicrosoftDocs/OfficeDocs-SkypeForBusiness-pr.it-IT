---
title: Report utenti bloccati PSTN di Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
localization_priority: Normal
search.appverid: MET150
MS.collection:
- M365-voice
description: Informazioni su come usare il report utenti bloccati PSTN nell'interfaccia di amministrazione di Microsoft teams per ottenere una panoramica degli utenti di Teams dell'organizzazione bloccati dall'esecuzione di chiamate PSTN.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 293d99507ae5b6b273ffb59c6d1544b4785a6c0c
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "37639521"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a>Report utenti bloccati PSTN di Microsoft Teams

Il report utenti bloccati PSTN nell'interfaccia di amministrazione di Microsoft teams Mostra gli utenti dell'organizzazione bloccati dall'esecuzione di chiamate PSTN in teams. È possibile visualizzare altre informazioni su ogni utente bloccato, incluso il numero di telefono assegnato e il motivo per cui sono stati bloccati dall'esecuzione delle chiamate.

## <a name="view-the-report"></a>Visualizzare il report

Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams fare clic su **analisi &** > report**sull'utilizzo**dei rapporti. Nella scheda **Visualizza report** , in **report**, selezionare **utenti bloccati PSTN**e quindi fare clic su **Esegui report**.

![Screenshot del report degli utenti bloccati PSTN nell'interfaccia di amministrazione](../media/teams-reports-pstn-blocked-users-with-callouts.png "Screenshot del report utenti bloccati PSTN nell'interfaccia di amministrazione di Microsoft teams con callout numerati")

## <a name="interpret-the-report"></a>Interpretare il report

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Ogni report ha una data per quando è stata generata. In genere, i report presentano una latenza di 24-48 ore dal momento dell'attività. |
|**2**   |L'asse X è la data. L'asse Y è il numero di utenti. <br>Posizionare il puntatore del mouse sul punto in una data specificata per visualizzare il numero di utenti bloccati in tale data. |
|**3**   |La tabella fornisce una ripartizione di tutti gli utenti bloccati dall'esecuzione di chiamate PSTN.  Mostra tutti gli utenti con sistema telefonico o servizi di audioconferenza assegnati e fornisce altre informazioni su ogni utente. <ul><li>**Nome visualizzato** è il nome visualizzato dell'utente. È possibile fare clic sul nome visualizzato per accedere alla pagina di impostazione dell'utente nell'interfaccia di amministrazione di Microsoft teams. </li> <li>**Telefono** è il numero assegnato all'utente.</li> <li>Il **motivo bloccato** è il motivo per cui l'utente è bloccato dall'esecuzione delle chiamate.</li><li>L' **azione bloccata** indica se l'utente è bloccato o sbloccato dall'esecuzione di chiamate PSTN in teams.</li> <li>**Ora bloccata** è la data e l'ora (UTC) in cui l'utente è stato bloccato per effettuare chiamate.</li></li> </ul>Per visualizzare le informazioni desiderate nella tabella, assicurarsi di aggiungere le colonne alla tabella. |
|**4**   |Selezionare **modifica colonne** per aggiungere o rimuovere colonne nella tabella.|
|**5**   |Selezionare **schermo intero** per visualizzare il report in modalità schermo intero.|

## <a name="related-topics"></a>Argomenti correlati

- [Analisi e creazione di report in teams](teams-reporting-reference.md)
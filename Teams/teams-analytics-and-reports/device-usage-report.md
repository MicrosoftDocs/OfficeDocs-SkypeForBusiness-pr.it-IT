---
title: Report utilizzo dispositivi Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Informazioni su come usare il report Utilizzo dispositivi di Teams nell'interfaccia di amministrazione di Microsoft Teams per vedere in che modo gli utenti dell'organizzazione si connettono a Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 292632972396f5d4300fa2526f01e69a5555ff45
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815646"
---
# <a name="microsoft-teams-device-usage-report"></a>Report utilizzo dispositivi Microsoft Teams

Il report Utilizzo di dispositivi Teams nell'interfaccia di amministrazione di Microsoft Teams fornisce informazioni su come gli utenti si connettono a Teams. È possibile usare il report per visualizzare i dispositivi usati nell'organizzazione, incluso il numero di dispositivi mobili utilizzati da Teams quando si è in viaggio.  

## <a name="view-the-device-usage-report"></a>Visualizzare il report sull'utilizzo dei dispositivi

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, fare clic su **Analisi & report**  >  **sull'utilizzo.** Nella scheda **Visualizza report,** in **Report,** selezionare Utilizzo **di dispositivi Teams.**
2. In **Intervallo di date** selezionare un intervallo e quindi fare clic su Esegui **report.**

    ![Screenshot del report Utilizzo di dispositivi Teams nell'interfaccia di amministrazione di Teams con callout](../media/teams-reports-device-usage-with-callouts.png "Screenshot del report Utilizzo di dispositivi Teams nell'interfaccia di amministrazione di Teams con callout")

## <a name="interpret-the-report"></a>Interpretare il report

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Il report Utilizzo di dispositivi di Teams può essere visualizzato per le tendenze degli ultimi 7 o 30 giorni.  |
|**2**   |Ogni report include la data in cui è stato generato. I report in genere riflettono una latenza di 24 ore dal momento dell'attività. |
|**3**   |<ul><li>L'asse X nel grafico rappresenta i diversi dispositivi **(Windows,** **Mac,** **Linux,** **iOS,** **Telefono Android,** **Web)** usati per connettersi a Teams. </li><li>L'asse Y è il numero di utenti che usano il dispositivo nel periodo di tempo selezionato.</li> </ul>Passa il puntatore sulla barra che rappresenta un dispositivo per vedere il numero di utenti che usano il dispositivo per connettersi a Teams.|
|**4**   |La tabella fornisce un'analisi dell'utilizzo dei dispositivi in base all'utente. <ul><li>**Nome** utente è il nome visualizzato dell'utente. È possibile fare clic sul nome visualizzato per passare alla pagina delle impostazioni dell'utente nell'interfaccia di amministrazione di Microsoft Teams. </li><li>**Windows** è selezionato se l'utente era attivo nel client desktop di Teams in un computer basato su Windows.</li><li>**Mac** è selezionato se l'utente era attivo nel client desktop di Teams su un computer macOS. </li> <li>**Linux** è selezionato se l'utente era attivo nel client desktop di Teams su un computer Linux. </li> <li>**iOS** è selezionato se l'utente era attivo nel client teams per dispositivi mobili iOS.</li><li>**Il telefono Android** è selezionato se l'utente era attivo nel client Teams per dispositivi mobili Android. <li><li>**Il** Web è selezionato se l'utente era attivo nel client Web di Teams. <li>**L'ultima attività** è la data (UTC) in cui l'utente ha partecipato a un'attività di Teams.</li> </ul> Si noti che se un account utente non esiste più in Azure AD, il nome utente viene visualizzato come "--" nella tabella. <br><br>Per visualizzare le informazioni desiderate nella tabella, assicurarsi di aggiungere le colonne alla tabella. |
|**5**   |Selezionare **Modifica colonne** per aggiungere o rimuovere colonne nella tabella. |
|**6**   |È possibile esportare il report in un file CSV per l'analisi offline. Fare clic su Esporta in **Excel,** quindi nella **scheda Download** fare clic su **Scarica** per scaricare il report quando è pronto.<br><br>![Screenshot della scheda Download con i report esportati](../media/teams-reports-export-to-csv.png)|

## <a name="related-topics"></a>Argomenti correlati

- [Analisi e creazione di report di Teams](teams-reporting-reference.md)

---
title: Report sull'utilizzo di dispositivi Microsoft Teams
author: LanaChin
ms.author: v-lanac
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
description: Informazioni su come usare il report utilizzo del dispositivo teams nell'interfaccia di amministrazione di Microsoft teams per vedere come gli utenti dell'organizzazione si connettono ai team.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 16abf763579a542583f3aafa30252c1423759641
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827354"
---
# <a name="microsoft-teams-device-usage-report"></a>Report sull'utilizzo di dispositivi Microsoft Teams

Il report utilizzo di dispositivi teams nell'interfaccia di amministrazione di Microsoft teams fornisce informazioni su come gli utenti si connettono ai team. Puoi usare il report per visualizzare i dispositivi usati in tutta l'organizzazione, incluso il numero di team che usano i loro dispositivi mobili quando si è in viaggio.  

## <a name="view-the-report"></a>Visualizzare il report

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams fare clic su **analisi &** > report**sull'utilizzo**dei rapporti. Nella scheda **Visualizza report** , in **report**, selezionare **utilizzo del dispositivo teams**.
2. In **intervallo di date**selezionare un intervallo e quindi fare clic su **Esegui report**.

    ![Screenshot del report utilizzo di dispositivi teams nell'interfaccia di amministrazione di teams con callout](../media/teams-reports-device-usage-with-callouts.png "Screenshot del report utilizzo di dispositivi teams nell'interfaccia di amministrazione di teams con callout")

## <a name="interpret-the-report"></a>Interpretare il report

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Il report utilizzo di dispositivi teams può essere visualizzato per le tendenze degli ultimi 7 giorni o 28 giorni.  |
|**2**   |Ogni report ha una data in cui è stato generato il report. In genere, i report presentano una latenza di 24-48 ore dal momento dell'attività. |
|**3**   |<ul><li>L'asse X nel grafico rappresenta i diversi dispositivi (**Windows**, **Mac**, **Linux**, **iOS**, **telefono Android**) usati per connettersi ai team. </li><li>L'asse Y è il numero di utenti che usano il dispositivo nel periodo di tempo selezionato.</li> </ul>Posizionare il puntatore del mouse sulla barra che rappresenta un dispositivo per visualizzare il numero di utenti che usano il dispositivo per connettersi ai team.|
|**4**   |La tabella offre una ripartizione dell'utilizzo dei dispositivi da parte dell'utente. <ul><li>**Nome visualizzato** è il nome visualizzato dell'utente. È possibile fare clic sul nome visualizzato per accedere alla pagina di impostazione dell'utente nell'interfaccia di amministrazione di Microsoft teams. </li><li>**Windows** è selezionato se l'utente era attivo nel client desktop teams in un computer basato su Windows.</li><li>**Mac** è selezionato se l'utente era attivo nel client desktop teams in un computer MacOS. </li> <li>**Linux** è selezionato se l'utente era attivo nel client desktop teams in un computer Linux. </li> <li>**iOS** è selezionato se l'utente era attivo nel client per dispositivi mobili teams per iOS.</li><li>Il **telefono Android** è selezionato se l'utente era attivo nel client per dispositivi mobili teams per Android. <li>**Ultima attività** è l'ultima data (UTC) in cui l'utente ha partecipato a un'attività di teams.</li> </ul> Tieni presente che se un account utente non esiste più in Azure AD, il nome utente viene visualizzato come "--" nella tabella. <br><br>Per visualizzare le informazioni desiderate nella tabella, assicurarsi di aggiungere le colonne alla tabella. |
|**5**   |Selezionare **modifica colonne** per aggiungere o rimuovere colonne nella tabella. |
|**6**   |È possibile esportare il report in un file CSV per l'analisi offline. Fare clic su **Esporta in Excel**, quindi nella scheda **download** fare clic su **Scarica** per scaricare il report quando è pronto.<br><br>![Screenshot della scheda download che mostra i report esportati](../media/teams-reports-export-to-csv.png)|

## <a name="related-topics"></a>Argomenti correlati

- [Analisi e creazione di report in teams](teams-reporting-reference.md)
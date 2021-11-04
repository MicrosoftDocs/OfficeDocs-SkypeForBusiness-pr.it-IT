---
title: Microsoft Teams utilizzo del dispositivo
author: cichur
ms.author: v-mahoffman
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Informazioni su come usare il report sull Teams di utilizzo dei dispositivi nell'interfaccia di amministrazione di Microsoft Teams per vedere in che modo gli utenti dell'organizzazione si connettono a Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 261a25cd998243c205424dd1a403166e03e1d921
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60749575"
---
# <a name="microsoft-teams-device-usage-report"></a>Microsoft Teams utilizzo del dispositivo

Il report Teams utilizzo dei dispositivi nell'interfaccia Microsoft Teams di amministrazione fornisce informazioni su come gli utenti si connettono a Teams. È possibile usare il report per visualizzare i dispositivi usati all'interno dell'organizzazione, incluso il numero di Teams da dispositivi mobili quando si è in viaggio.  

## <a name="view-the-device-usage-report"></a>Visualizzare il report sull'utilizzo del dispositivo

1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione fare clic su **Analisi & report**  >  **utilizzo**. Nella scheda **Visualizza report,** in **Report,** selezionare Teams **utilizzo del dispositivo.**
2. In **Intervallo di date** selezionare un intervallo e quindi fare clic su Esegui **report.**

    ![Screenshot del report sull Teams utilizzo dei dispositivi nell'Teams di amministrazione con callout.](../media/teams-reports-device-usage-with-callouts.png "Screenshot del report sull Teams utilizzo dei dispositivi nell'interfaccia Teams con callout")

## <a name="interpret-the-report"></a>Interpretare il report

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Il Teams di utilizzo dei dispositivi può essere visualizzato per le tendenze degli ultimi 7 o 30 giorni.  |
|**2**   |Ogni report ha una data in cui è stato generato il report. I report in genere riflettono una latenza di 24 ore dal momento dell'attività. |
|**3**   |<ul><li>L'asse X del grafico rappresenta i diversi dispositivi (**Windows**, **Mac**, **Linux**, **iOS**, **Android Telefono**, **Web**) usati per connettersi a Teams. </li><li>L'asse Y è il numero di utenti che usano il dispositivo nel periodo di tempo selezionato.</li> </ul>Passare il puntatore del mouse sulla barra che rappresenta un dispositivo per visualizzare il numero di utenti che usano il dispositivo per connettersi a Teams.|
|**4**   |La tabella fornisce una suddivisione dell'utilizzo del dispositivo per utente. <ul><li>**Nomeutente** è il nome visualizzato dell'utente. È possibile fare clic sul nome visualizzato per passare alla pagina delle impostazioni dell'utente nell'Microsoft Teams di amministrazione. </li><li>**Windows** selezionato se l'utente era attivo nel client desktop Teams in un computer Windows basato su Windows.</li><li>**Mac** è selezionato se l'utente era attivo nel client desktop Teams in un computer macOS. </li> <li>**Linux** è selezionato se l'utente era attivo nel client desktop Teams in un computer Linux. </li> <li>**iOS** è selezionato se l'utente era attivo nel client Teams per dispositivi mobili per iOS.</li><li>**Il telefono Android** è selezionato se l'utente era attivo nel client Teams mobile per Android. <li><li>**Web** è selezionato se l'utente era attivo nel client Teams Web. <li>**L'ultima attività** è l'ultima data (UTC) a cui l'utente ha partecipato a un'Teams attività.</li> </ul> Si noti che se un account utente non esiste più in Azure AD, il nome utente viene visualizzato come "--" nella tabella. <br><br>Per visualizzare le informazioni desiderate nella tabella, assicurarsi di aggiungere le colonne alla tabella. |
|**5**   |Selezionare **Modifica colonne** per aggiungere o rimuovere colonne nella tabella. |
|**6**   |È possibile esportare il report in un file CSV per l'analisi offline. Fare **clic su Esporta in Excel** e quindi nella scheda **Download** fare clic su **Scarica** per scaricare il report quando è pronto.<br><br>![Screenshot della scheda Download che mostra i report esportati.](../media/teams-reports-export-to-csv.png)|


## <a name="make-the-user-specific-data-anonymous"></a>Rendere anonimi i dati specifici dell'utente

Per rendere anonimi i Teams di utilizzo dei dispositivi, è necessario essere un amministratore globale. In questo modo si nasconderanno le informazioni identificabili, ad esempio il nome visualizzato, la posta elettronica e AAD ID utente nel report e la relativa esportazione.

1. In interfaccia di amministrazione di Microsoft 365 passare alla scheda  Impostazioni Org Impostazioni e nella scheda Servizi \> scegliere **Report.** 
    
2. Selezionare **Report** e quindi scegliere **Visualizza identificatori anonimi**. Questa impostazione viene applicata sia ai report di utilizzo in interfaccia di amministrazione di Microsoft 365 che all'Teams di amministrazione.
  
3. Selezionare **Salva modifiche**.

## <a name="related-topics"></a>Argomenti correlati

- [Analisi e creazione dei report di Teams](teams-reporting-reference.md).

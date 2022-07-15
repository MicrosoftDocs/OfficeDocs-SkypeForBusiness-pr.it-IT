---
title: Report utilizzo dispositivi Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: Informazioni su come usare il report utilizzo dispositivi Teams nell'interfaccia di amministrazione di Microsoft Teams per vedere come gli utenti dell'organizzazione si connettono a Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 949ad172425f5e02da2fa67078193b198cb987d1
ms.sourcegitcommit: 4c4f2f220832cae3efb3f6f3c74795300d661295
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2022
ms.locfileid: "66825510"
---
# <a name="microsoft-teams-device-usage-report"></a>Report utilizzo dispositivi Microsoft Teams

Il report Utilizzo dispositivi Teams nell'interfaccia di amministrazione di Microsoft Teams fornisce informazioni su come gli utenti si connettono a Teams. È possibile usare il report per vedere i dispositivi usati nell'intera organizzazione, incluso il numero di dispositivi mobili usati da Teams quando si è in viaggio.  

## <a name="view-the-device-usage-report"></a>Visualizzare il report sull'utilizzo del dispositivo

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams fare clic su **Analisi & report** > **utilizzo**. Nella scheda **Visualizza report** , in **Report**, selezionare **Utilizzo dispositivi Teams**.
2. In **Intervallo di date** selezionare un intervallo e quindi fare clic su **Esegui report**.

    ![Screenshot del report Utilizzo dispositivi Teams nell'interfaccia di amministrazione di Teams con callout.](../media/teams-reports-device-usage-with-callouts.png "Screenshot del report Utilizzo dispositivi Teams nell'interfaccia di amministrazione di Teams con callout")

## <a name="interpret-the-report"></a>Interpretare il report

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Il report Utilizzo dispositivi Teams può essere visualizzato per le tendenze degli ultimi 7 o 30 giorni.  |
|**2**   |Ogni report ha una data per la generazione del report. I report in genere riflettono una latenza di 24 ore dal momento dell'attività. |
|**3**   |<ul><li>L'asse X nel grafico rappresenta i diversi dispositivi (**Windows**, **Mac**, **Linux**, **iOS**, **Android Phone**, **Web**) usati per connettersi a Teams. </li><li>L'asse Y è il numero di utenti che usano il dispositivo nel periodo di tempo selezionato.</li> </ul>Passare il puntatore del mouse sulla barra che rappresenta un dispositivo per visualizzare il numero di utenti che usano il dispositivo per connettersi a Teams.|
|**4**   |La tabella fornisce un'analisi dell'utilizzo del dispositivo in base all'utente. <ul><li>**Nome utente** è il nome visualizzato dell'utente. È possibile fare clic sul nome visualizzato per passare alla pagina delle impostazioni dell'utente nell'interfaccia di amministrazione di Microsoft Teams. </li><li>**Windows** è selezionato se l'utente era attivo nel client desktop di Teams in un computer basato su Windows.</li><li>**Mac** è selezionato se l'utente era attivo nel client desktop di Teams in un computer macOS. </li> <li>**Linux** è selezionato se l'utente era attivo nel client desktop di Teams su un computer Linux. </li> <li>**iOS** è selezionato se l'utente era attivo sul client mobile di Teams per iOS.</li><li>**Il telefono Android** è selezionato se l'utente era attivo sul client mobile Teams per Android. <li><li>**Web** è selezionato se l'utente era attivo sul client Web di Teams. <li>**L'ultima attività** è l'ultima data (UTC) in cui l'utente ha partecipato a un'attività di Teams.</li> </ul> Si noti che se un account utente non esiste più in Azure AD, il nome utente viene visualizzato come "--" nella tabella. <br><br>Per visualizzare le informazioni desiderate nella tabella, assicurarsi di aggiungere le colonne alla tabella. |
|**5**   |Selezionare **Modifica colonne** per aggiungere o rimuovere colonne nella tabella. |
|**6**   |È possibile esportare il report in un file CSV per l'analisi offline. Fare clic su **Esporta in Excel** e quindi nella scheda **Download** fare clic su **Scarica** per scaricare il report quando è pronto.<br><br>![Screenshot della scheda Download che mostra i report esportati.](../media/teams-reports-export-to-csv.png)|


## <a name="make-the-user-specific-data-anonymous"></a>Rendere anonimi i dati specifici dell'utente

Per rendere anonimi i dati nei report sull'utilizzo dei dispositivi di Teams, è necessario essere un amministratore globale. Le informazioni identificabili, ad esempio il nome visualizzato, l'indirizzo di posta elettronica e l'ID AAD verranno nascoste nel report e nella loro esportazione.

1. In interfaccia di amministrazione di Microsoft 365 passare a **Impostazioni** \> **impostazioni organizzazione** e, nella scheda **Servizi**, scegliere **Report**.
    
2. Selezionare **Report** e quindi scegliere **Visualizza identificatori anonimi**. Questa impostazione viene applicata sia ai report sull'utilizzo in interfaccia di amministrazione di Microsoft 365 che all'interfaccia di amministrazione di Teams.
  
3. Selezionare **Salva modifiche**.

## <a name="related-topics"></a>Argomenti correlati

- [Analisi e creazione dei report di Teams](teams-reporting-reference.md).

---
title: Report sull'utilizzo dei dispositivi di Microsoft Teams
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
description: Informazioni su come usare il report sull'utilizzo dei dispositivi di Teams nell'interfaccia di amministrazione di Microsoft Teams per vedere come gli utenti dell'organizzazione si connettono a Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1d47888884ce86bfa56546a9df600ce958380e0d
ms.sourcegitcommit: 66e7b28ba1c0433535eb6a3e7d883851c27d9d1f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "51478356"
---
# <a name="microsoft-teams-device-usage-report"></a>Report sull'utilizzo dei dispositivi di Microsoft Teams

Il report Sull'utilizzo dei dispositivi di Teams nell'interfaccia di amministrazione di Microsoft Teams fornisce informazioni su come gli utenti si connettono a Teams. È possibile usare il report per visualizzare i dispositivi usati in tutta l'organizzazione, incluso il numero di utenti di Teams dai propri dispositivi mobili quando si è in viaggio.  

## <a name="view-the-device-usage-report"></a>Visualizzare il report sull'utilizzo del dispositivo

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams fare clic su **Analisi & report**  >  **utilizzo**. Nella scheda **Visualizza report,** in **Report,** selezionare Utilizzo **dispositivi teams.**
2. In **Intervallo di date** selezionare un intervallo e quindi fare clic su Esegui **report.**

    ![Screenshot del report sull'utilizzo dei dispositivi di Teams nell'interfaccia di amministrazione di Teams con callout](../media/teams-reports-device-usage-with-callouts.png "Screenshot del report sull'utilizzo dei dispositivi di Teams nell'interfaccia di amministrazione di Teams con callout")

## <a name="interpret-the-report"></a>Interpretare il report

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Il report sull'utilizzo dei dispositivi di Teams può essere visualizzato per le tendenze degli ultimi 7 o 30 giorni.  |
|**2**   |Ogni report ha una data in cui è stato generato il report. I report in genere riflettono una latenza di 24 ore dal momento dell'attività. |
|**3**   |<ul><li>L'asse X del grafico rappresenta i diversi dispositivi (**Windows,** **Mac**, **Linux**, **iOS**, **Android Phone**, **Web**) usati per connettersi a Teams. </li><li>L'asse Y è il numero di utenti che usano il dispositivo nel periodo di tempo selezionato.</li> </ul>Passare il puntatore del mouse sulla barra che rappresenta un dispositivo per visualizzare il numero di utenti che usano il dispositivo per connettersi a Teams.|
|**4**   |La tabella fornisce una suddivisione dell'utilizzo del dispositivo per utente. <ul><li>**Nomeutente** è il nome visualizzato dell'utente. È possibile fare clic sul nome visualizzato per passare alla pagina delle impostazioni dell'utente nell'interfaccia di amministrazione di Microsoft Teams. </li><li>**Windows** è selezionato se l'utente era attivo nel client desktop di Teams in un computer basato su Windows.</li><li>**Mac** è selezionato se l'utente era attivo nel client desktop di Teams in un computer macOS. </li> <li>**Linux** è selezionato se l'utente era attivo nel client desktop di Teams in un computer Linux. </li> <li>**iOS** è selezionato se l'utente era attivo nel client per dispositivi mobili Teams per iOS.</li><li>**Il telefono Android** è selezionato se l'utente era attivo nel client per dispositivi mobili Teams per Android. <li><li>**Web** è selezionato se l'utente era attivo nel client Web di Teams. <li>**Ultima attività** è l'ultima data (UTC) a cui l'utente ha partecipato a un'attività di Teams.</li> </ul> Si noti che se un account utente non esiste più in Azure AD, il nome utente viene visualizzato come "--" nella tabella. <br><br>Per visualizzare le informazioni desiderate nella tabella, assicurarsi di aggiungere le colonne alla tabella. |
|**5**   |Selezionare **Modifica colonne** per aggiungere o rimuovere colonne nella tabella. |
|**6**   |È possibile esportare il report in un file CSV per l'analisi offline. Fare **clic su Esporta** in Excel e quindi nella scheda **Download** fare clic su **Scarica** per scaricare il report quando è pronto.<br><br>![Screenshot della scheda Download che mostra i report esportati](../media/teams-reports-export-to-csv.png)|


## <a name="make-the-user-specific-data-anonymous"></a>Rendere anonimi i dati specifici dell'utente

Per rendere anonimi i dati nel report sull'utilizzo dei dispositivi di Teams, è necessario essere un amministratore globale. In questo modo si nasconderanno informazioni identificabili come il nome visualizzato, la posta elettronica e l'ID AAD nel report e la relativa esportazione.

1. Nell'interfaccia di amministrazione di Microsoft 365 passare a **Impostazioni** organizzazione Impostazioni e nella scheda Servizi \> scegliere **Report.** 
    
2. Selezionare **Report** e quindi scegliere **Visualizza identificatori anonimi**. Questa impostazione viene applicata sia ai report di utilizzo nell'interfaccia di amministrazione di Microsoft 365 che all'interfaccia di amministrazione di Teams.
  
3. Selezionare **Salva modifiche**.

## <a name="related-topics"></a>Argomenti correlati

- [Analisi e creazione di report di Teams](teams-reporting-reference.md)

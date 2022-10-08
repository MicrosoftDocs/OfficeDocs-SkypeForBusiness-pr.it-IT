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
ms.openlocfilehash: 11a16026bf8d844b4d533316e8680b8aa409b5b2
ms.sourcegitcommit: b2692b3f6c60d8df5ba0677c68ff9c90a75a0d72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2022
ms.locfileid: "68033804"
---
# <a name="microsoft-teams-device-usage-report"></a>Report utilizzo dispositivi Microsoft Teams

Il report Utilizzo dispositivi Teams nell'interfaccia di amministrazione di Microsoft Teams fornisce informazioni su come gli utenti si connettono a Teams. È possibile usare il report per vedere i dispositivi usati nell'intera organizzazione, incluso il numero di dispositivi mobili usati da Teams quando si è in viaggio.  

## <a name="view-the-device-usage-report"></a>Visualizzare il report sull'utilizzo del dispositivo


Per visualizzare i report nell'interfaccia di amministrazione di Teams, è necessario essere un amministratore globale, un lettore globale o un amministratore del servizio Teams. Vedere [Usare i ruoli di amministratore di Teams per gestire Teams](../using-admin-roles.md) per informazioni su come ottenere ruoli e autorizzazioni di amministratore.


1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams fare clic su **Analisi & report** > **utilizzo**. Nella scheda **Visualizza report** , in **Report**, selezionare **Utilizzo dispositivi Teams**.
2. In **Intervallo di date** selezionare un intervallo e quindi fare clic su **Esegui report**.

    ![Screenshot del report Utilizzo dispositivi Teams nell'interfaccia di amministrazione di Teams con callout.](../media/teams-reports-device-usage-with-callouts.png "Screenshot del report Utilizzo dispositivi Teams nell'interfaccia di amministrazione di Teams con callout")

## <a name="interpret-the-report"></a>Interpretare il report

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Il report Utilizzo dispositivi Teams può essere visualizzato per le tendenze degli ultimi 7, 30, 90 e 180 giorni.  |
|**2**   |Ogni report ha una data per la generazione del report. I report in genere riflettono una latenza di 24-48 ore dal momento dell'attività. |
|**3**   |<ul><li>L'asse X nel grafico rappresenta i diversi dispositivi (**Windows**, **Mac**, **Linux**, **iOS**, **Android Phone**, **Web**) usati per connettersi a Teams. </li><li>L'asse Y è il numero di utenti che usano il dispositivo nel periodo di tempo selezionato.</li> </ul>Passare il puntatore del mouse sulla barra che rappresenta un dispositivo per visualizzare il numero di utenti che usano il dispositivo per connettersi a Teams.|
|**4**   |La tabella fornisce un'analisi dell'utilizzo del dispositivo in base all'utente. <ul><li>**Nome utente** è il nome visualizzato dell'utente. È possibile fare clic sul nome visualizzato per passare alla pagina delle impostazioni dell'utente nell'interfaccia di amministrazione di Microsoft Teams. </li><li>**Windows** è selezionato se l'utente era attivo nel client desktop di Teams in un computer basato su Windows.</li><li>**Mac** è selezionato se l'utente era attivo nel client desktop di Teams in un computer macOS. </li> <li>**Linux** è selezionato se l'utente era attivo nel client desktop di Teams su un computer Linux. </li> <li>**iOS** è selezionato se l'utente era attivo sul client mobile di Teams per iOS.</li><li>**Il telefono Android** è selezionato se l'utente era attivo sul client mobile Teams per Android.</li><li>**Chrome OS** è selezionato se l'utente era attivo nel client desktop di Teams in un computer ChromeOS.</li><li>**Web** è selezionato se l'utente era attivo sul client Web di Teams. <li>**L'ultima attività** è l'ultima data (UTC) in cui l'utente ha partecipato a un'attività di Teams.</li> </ul> Si noti che se un account utente non esiste più in Azure AD, il nome utente viene visualizzato come "--" nella tabella. <br><br>Per visualizzare le informazioni desiderate nella tabella, assicurarsi di aggiungere le colonne alla tabella. |
|**5**   |Selezionare **Modifica colonne** per aggiungere o rimuovere colonne nella tabella. |
|**6**   |Esportare il report in un file CSV per l'analisi offline. Selezionare l'icona **Esporta in Excel** per scaricare il report nel browser.|
|**7** |I dati della serie temporale rappresentati nel grafico superiore mostrano metriche di utilizzo diverse aggregate per l'intero tenant|
|**8** |I dati tabulari rappresentati nella metà botton mostrano metriche di utilizzo diverse aggregate per utente|


## <a name="make-the-user-specific-data-anonymous"></a>Rendere anonimi i dati specifici dell'utente

Per rendere anonimi i dati nel report attività degli utenti di Teams, è necessario essere un amministratore globale. L'amministratore globale può nascondere le informazioni identificabili (usando gli hash MD5), ad esempio il nome visualizzato, il nome del gruppo, la posta elettronica e l'ID AAD nel report e nella relativa esportazione.

1. In interfaccia di amministrazione di Microsoft 365 passare a **Impostazioni** \> **impostazioni organizzazione** e, nella scheda **Servizi**, scegliere **Report**.
    
2. Selezionare **Report** e quindi scegliere **Visualizza nomi di utenti, gruppi e siti nascosti in tutti i report**. Questa impostazione viene applicata sia ai report sull'utilizzo in interfaccia di amministrazione di Microsoft 365 che all'interfaccia di amministrazione di Teams.
  
3. Selezionare **Salva modifiche**.

> [!NOTE]
> L'abilitazione di questa impostazione deidentificherà le informazioni sul nome di utenti, gruppi e siti nel [report Attività utente di Teams](user-activity-report.md), nel [report Sull'utilizzo dei dispositivi di Teams](device-usage-report.md) e nel [report sull'utilizzo di Teams](teams-usage-report.md). A partire dal 1° settembre 2021, questa impostazione è abilitata per impostazione predefinita per tutti gli utenti nell'ambito del nostro costante impegno per proteggere le informazioni importanti e consentire alle aziende di supportare le leggi locali sulla privacy. 
>
>Questa impostazione si applica anche ai report sull'utilizzo di Microsoft 365 in interfaccia di amministrazione di Microsoft 365, Microsoft Graph e Power BI.

## <a name="related-topics"></a>Argomenti correlati

- [Analisi e creazione dei report di Teams](teams-reporting-reference.md).

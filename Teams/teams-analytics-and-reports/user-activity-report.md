---
title: Report attività utente di Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Informazioni su come usare il report attività utente teams nell'interfaccia di amministrazione di Microsoft teams per scoprire in che modo gli utenti dell'organizzazione usano team.
appliesto:
- Microsoft Teams
ms.openlocfilehash: dd8c33bfa1ebfbeb4ba4c79827c13e4c33f9a340
ms.sourcegitcommit: f1c4255b52576c602d528c580941404eb547bc78
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "37131599"
---
# <a name="microsoft-teams-user-activity-report"></a>Report attività utente di Microsoft Teams

Il report attività utente teams offre informazioni sui tipi di attività che gli utenti dell'organizzazione eseguono in teams. Ad esempio, puoi vedere il numero di utenti che comunicano tramite le chiamate di 1:1, il numero di utenti che comunicano tramite messaggi di canale e il numero di utenti che partecipano a messaggi di chat privati.

## <a name="view-the-report"></a>Visualizzare il report

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams fare clic su **analisi &** > report**sull'utilizzo**dei rapporti. Nella scheda **Visualizza report** , in **report**, selezionare **attività utente teams**.
2. In **intervallo di date**selezionare un intervallo e quindi fare clic su **Esegui report**.

    ![Screenshot del report attività utente teams nell'interfaccia di amministrazione di teams con callout] (../media/teams-reports-user-activity-with-callouts.png "Screenshot del report attività utente teams nell'interfaccia di amministrazione di teams con callout")

## <a name="interpret-the-report"></a>Interpretare il report

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Il report attività utente teams può essere visualizzato per le tendenze degli ultimi 7 giorni o 28 giorni. |
|**2**   |Ogni report riporta la data in cui è stato generato. In genere, i report presentano una latenza di 24-48 ore dal momento dell'attività. |
|**3**   |<ul><li>L'asse X nei grafici è l'intervallo di date selezionato per il report specifico. </li><li>L'asse Y è il numero di utenti che partecipano all'attività.</li></ul>Posizionare il puntatore del mouse sul punto che rappresenta un'attività in una data specificata per visualizzare il numero di istanze di tale attività in quella data specificata. |
|**4**   |È possibile filtrare gli elementi visualizzati nel grafico facendo clic su un elemento nella legenda. Ad esempio, fare clic su **1:1 chiamate**, **canali**o **messaggi di chat** per visualizzare solo le informazioni relative a ognuna di esse. La modifica della selezione non modifica le informazioni nella tabella. |
|**5**   |La tabella offre una ripartizione dell'utilizzo da parte dell'utente.   <ul><li>**Nome visualizzato** è il nome visualizzato dell'utente. È possibile fare clic sul nome visualizzato per accedere alla pagina di impostazione dell'utente nell'interfaccia di amministrazione di Microsoft teams.</li><li>**1:1 chiamate** è il numero di chiamate 1:1 a cui l'utente ha partecipato durante il periodo di tempo specificato.</li><li>**Messaggi di canale** è il numero di messaggi univoci che l'utente ha postato in una chat del team durante il periodo di tempo specificato.</li> <li>**Messaggi di chat** è il numero di messaggi univoci che l'utente ha postato in una chat privata durante il periodo di tempo specificato.</li>  <li>**Ultima attività** è l'ultima data (UTC) in cui l'utente ha partecipato a un'attività di teams.</li> </ul>Tieni presente che se un account utente non esiste più in Azure AD, il nome utente viene visualizzato come "--" nella tabella. <br><br>Per visualizzare le informazioni desiderate nella tabella, assicurarsi di aggiungere le colonne alla tabella.
|**6**   |Selezionare **modifica colonne** per aggiungere o rimuovere colonne nella tabella. |
|**7**   |È possibile esportare il report in un file CSV per l'analisi offline. Fare clic su **Esporta in Excel**, quindi nella scheda **download** fare clic su **Scarica** per scaricare il report quando è pronto.<br><br>![Screenshot della scheda download che mostra i report esportati da scaricare](../media/teams-reports-export-to-csv.png) <br>Quando si Visualizza il report in Excel, viene visualizzata anche una colonna **ID** , che rappresenta l'ID del team. Un ID team è in genere una stringa alfanumerica. Se la colonna **ID** viene visualizzata come **\n**, significa che un utente ha richiesto le informazioni da eliminare. ||

## <a name="related-topics"></a>Argomenti correlati

- [Analisi e creazione di report in teams](teams-reporting-reference.md)
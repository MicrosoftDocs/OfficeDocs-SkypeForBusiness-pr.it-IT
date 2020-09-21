---
title: Report attività utente di Microsoft Teams
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
description: Informazioni su come usare il report attività utente teams nell'interfaccia di amministrazione di Microsoft teams per scoprire in che modo gli utenti dell'organizzazione usano team.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ccc59501260d5a63ca43f7b32aa0cc2f76e3cfd2
ms.sourcegitcommit: 140d7d71077bd396e558f19f16177ec432a8f95c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104644"
---
# <a name="microsoft-teams-user-activity-report"></a>Report attività utente di Microsoft Teams

Il report attività utente teams offre informazioni sui tipi di attività che gli utenti dell'organizzazione eseguono in teams. Ad esempio, si può vedere il numero di utenti che comunicano su base ad hoc tramite riunioni non pianificate comunemente denominate 1:1 e chiamate di gruppo, riunioni organizzate da un utente di teams e riunioni a cui ha partecipato un utente di teams. Condividiamo i dettagli relativi ai minuti dello schermo, video e audio e alle statistiche di comunicazione della chat, ad esempio il numero di utenti che rispondono ai messaggi del canale e il numero di utenti che partecipano a 1:1 o messaggi di chat di gruppo.

## <a name="view-the-user-activity-report"></a>Visualizzare il report attività utente

Per apportare queste modifiche, è necessario essere un amministratore del servizio teams. Vedere [usare i ruoli di amministratore di team per gestire i team](https://docs.microsoft.com/microsoftteams/using-admin-roles) per leggere informazioni su come ottenere ruoli di amministratore e autorizzazioni.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams fare clic su **analisi &** report  >  **sull'utilizzo**dei rapporti. Nella scheda **Visualizza report** , in **report**, selezionare **attività utente teams**.
2. In **intervallo di date**selezionare un intervallo e quindi fare clic su **Esegui report**.

    ![Screenshot del report attività utente teams nell'interfaccia di amministrazione di teams con callout](../media/teams-reports-user-activity-with-callouts.png "Screenshot del report attività utente teams nell'interfaccia di amministrazione di teams con callout")

## <a name="interpret-the-report"></a>Interpretare il report

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Il report attività utente teams può essere visualizzato per le tendenze degli ultimi 7 giorni, 30 o 90 giorni. |
|**2**   |Ogni report riporta la data in cui è stato generato. I report riflettono in genere una latenza di 24 ore dal momento dell'attività. |
|**3**   |<ul><li>L'asse X nei grafici è l'intervallo di date selezionato per il report specifico. </li><li>L'asse Y è il numero di utenti che partecipano all'attività.</li></ul>Posizionare il puntatore del mouse sul punto che rappresenta un'attività in una data specificata per visualizzare il numero di istanze di tale attività in quella data specificata. |
|**4**   |È possibile filtrare gli elementi visualizzati nel grafico facendo clic su un elemento nella legenda. Ad esempio, fare clic su **1:1 chiamate**, **canali**o **messaggi di chat** per visualizzare solo le informazioni relative a ognuna di esse. La modifica della selezione non modifica le informazioni nella tabella. |
|**5**   |La tabella offre una ripartizione dell'utilizzo da parte dell'utente.   <ul><li>**Username** è il nome visualizzato dell'utente. È possibile fare clic sul nome visualizzato per accedere alla pagina di impostazione dell'utente nell'interfaccia di amministrazione di Microsoft teams.</li><li>**Messaggi di canale** è il numero di messaggi univoci che l'utente ha postato in una chat del team durante il periodo di tempo specificato.</li><li>**Messaggi di risposta** è il numero di messaggi di risposta univoci inviati dall'utente in un canale del team durante il periodo di tempo specificato.</li> <li>**Post messages** è il numero di messaggi univoci che l'utente ha postato in un canale del team durante il periodo di tempo specificato.</li><li>**Messaggi di chat** è il numero di messaggi univoci che l'utente ha postato in una chat privata durante il periodo di tempo specificato.</li><li>**Messaggi urgenti** è il numero di messaggi urgenti inviati dall'utente in una chat durante il periodo di tempo specificato.</li><li>**Total Meetings** rappresenta il numero totale di riunioni pianificate e ad hoc a cui l'utente ha partecipato durante il periodo di tempo specificato.</li><li>**Riunioni organizzate** è il numero di riunioni pianificate e ad hoc che un utente ha organizzato durante il periodo di tempo specificato.</li><li>**Riunioni organizzate pianificate** è il numero di riunioni pianificate che un utente ha organizzato durante il periodo di tempo specificato.</li><li>**Riunioni organizzate Adhoc** è il numero di riunioni ad hoc che un utente ha organizzato durante il periodo di tempo specificato.</li><li>**Riunioni partecipate** è il numero delle riunioni pianificate e ad hoc a cui l'utente ha partecipato durante il periodo di tempo specificato.</li><li>**Riunioni in programma partecipato** è il numero delle riunioni pianificate a cui l'utente ha partecipato durante il periodo di tempo specificato.</li><li>Le **riunioni hanno partecipato ad Adhoc** è il numero di riunioni ad hoc a cui l'utente ha partecipato durante il periodo di tempo specificato.</li><li>**1:1 chiamate** è il numero di chiamate 1:1 a cui l'utente ha partecipato durante il periodo di tempo specificato.</li><li>**Ora audio** è il tempo totale audio a cui l'utente ha partecipato durante il periodo di tempo specificato.</li><li>**Ora video** è il tempo totale del video a cui l'utente ha partecipato durante il periodo di tempo specificato.</li><li>**Ora di condivisione dello schermo** è il tempo totale di condivisione dello schermo a cui l'utente ha partecipato durante il periodo di tempo specificato.</li>  <li>**Ultima attività** è l'ultima data (UTC) in cui l'utente ha partecipato a un'attività di teams.</li><li>**Altre** tracce di attività quando l'utente è considerato attivo, ma con un valore pari a zero per i messaggi di chat, le chiamate di 1:1, i messaggi del canale, le riunioni totali e le riunioni organizzate. Gli esempi di azioni si verificano quando un utente apre un post di un canale, ma non risponde o quando un utente riceve un messaggio privato e lo legge, ma non lo soddisfa.</li> </ul>Tieni presente che le **chiamate di gruppo** sono state sostituite da **riunioni organizzate ad hoc** e le **riunioni hanno partecipato ad Adhoc**, in cui la somma di questi due valori è uguale a quella misurata dalle chiamate di **gruppo**.
|**6**   |Selezionare **modifica colonne** per aggiungere o rimuovere colonne nella tabella. |
|**7**   |È possibile esportare il report in un file CSV per l'analisi offline. Fare clic su **Esporta in Excel**, quindi nella scheda **download** fare clic su **Scarica** per scaricare il report quando è pronto.<br><br>![Screenshot della scheda download che mostra i report esportati da scaricare](../media/teams-reports-export-to-csv.png) <br>Quando si Visualizza il report in Excel, viene visualizzata anche una colonna **ID** , che rappresenta l'ID del team. Un ID team è in genere una stringa alfanumerica. Se la colonna **ID** viene visualizzata come **\n**, significa che un utente ha richiesto le informazioni da eliminare. ||

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>Argomenti correlati

- [Analisi e creazione di report in teams](teams-reporting-reference.md)

---
title: Report Attività degli utenti di Microsoft Teams
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
description: Informazioni su come usare il report Attività degli utenti di Teams nell'interfaccia di amministrazione di Microsoft Teams per vedere in che modo gli utenti dell'organizzazione usano Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f02d2f8751b8059f435164158d5c97fb6766a286
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196915"
---
# <a name="microsoft-teams-user-activity-report"></a>Report Attività degli utenti di Microsoft Teams

Il report Attività degli utenti di Teams fornisce informazioni dettagliate sui tipi di attività che gli utenti dell'organizzazione e devono eseguire in Teams. È possibile vedere quanti utenti comunicano a base non pianificata attraverso riunioni non pianificate (chiamate 1:1 e di gruppo). Vedere quante riunioni ha organizzato un utente di Teams e a cui ha partecipato un utente di Teams. Vedere i dettagli su schermo, video, minuti audio e statistiche sulle comunicazioni chat, ad esempio quanti utenti rispondono ai messaggi del canale e pubblicano post e quanti utenti sono coinvolti in messaggi 1:1 o di chat di gruppo.

## <a name="view-the-user-activity-report"></a>Visualizzare il report attività utente

Per apportare queste modifiche, è necessario essere un amministratore dei servizi di Teams. Vedere [Usare i ruoli di amministratore di Teams per gestire Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) e leggere come ottenere i ruoli di amministratore e le autorizzazioni.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams selezionare **Analisi & report**  >  **sull'utilizzo.** Nella scheda **Visualizza report,** in **Report,** selezionare Attività **utente di Teams.**
2. In **Intervallo di date** selezionare un intervallo e quindi selezionare Esegui **report.**

    ![Screenshot del report Attività degli utenti di Teams nell'interfaccia di amministrazione di Teams con callout](../media/teams-reports-user-activity-with-callouts.png "Screenshot del report Attività degli utenti di Teams nell'interfaccia di amministrazione di Teams con callout")

## <a name="interpret-the-report"></a>Interpretare il report

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Il report Attività degli utenti di Teams può essere visualizzato per le tendenze degli ultimi 7, 30 o 90 giorni. |
|**2**   |Ogni report riporta la data in cui è stato generato. I report in genere riflettono una latenza di 24 ore dal momento dell'attività. |
|**3**   |I punti dati della serie temporale nel grafico mostrano diverse metriche di utilizzo aggregate al tenant. |
|**4**   |I dati tabulari rappresentavano diverse metriche di utilizzo aggregate per utente. |
|**5**   |<ul><li>L'asse X nel grafico rappresenta l'intervallo di date selezionato per il report.</li> <li> L'asse Y è il conteggio degli elementi attivi o delle attività.</li> </ul>Posizionare il puntatore del mouse sul punto che rappresenta un elemento o un'attività in una data specifica per visualizzare il numero di istanze dell'elemento o dell'attività in tale data.|
|**6**   | Ognuna delle metriche rappresentate nel grafico a livello di tenant. Filtrare gli elementi visualizzati nel grafico selezionando un elemento nella legenda. Selezionare **Messaggi del canale,** **Rispondi,**  **Messaggi in chat** o Riunioni **organizzate** per visualizzare le informazioni per ciascun canale. La modifica di questa selezione non modifica le informazioni nella tabella. |
|**7**   |La tabella fornisce un'analisi dell'utilizzo in base all'utente.   <ul><li>**Il nome** visualizzato è il nome visualizzato dell'utente. Selezionare il nome visualizzato per passare alla pagina dei dettagli utente nell'interfaccia di amministrazione di Microsoft Teams.</li><li>**Messaggi del** canale è il numero di messaggi univoci che l'utente ha pubblicato in un canale del team durante il periodo di tempo specificato.</li><li>**Messaggi di risposta** è il numero di messaggi di risposta univoci che l'utente ha pubblicato in un canale del team durante il periodo di tempo specificato.</li> <li>**Pubblica messaggi** è il numero di messaggi univoci che l'utente ha pubblicato in un canale del team durante il periodo di tempo specificato.</li><li>**I messaggi di** chat sono il numero di messaggi univoci che l'utente ha pubblicato in una chat privata durante il periodo di tempo specificato.</li><li>**Messaggi urgenti** è il numero di messaggi urgenti che l'utente ha pubblicato in una chat durante il periodo di tempo specificato.</li><li>**Il totale delle** riunioni organizzate è la somma di una riunione pianificata, ricorrente, non pianificata e <em>non</em> classificata organizzata da un utente durante il periodo di tempo specificato.</li><li>**Le riunioni organizzate una sola volta** sono il numero di riunioni pianificate una sola volta che un utente ha organizzato durante il periodo di tempo specificato.</li><li>**Riunioni organizzate ricorrenti pianificate** è il numero di riunioni ricorrenti organizzate da un utente durante il periodo di tempo specificato.</li><li>**Riunioni organizzate adhoc** è il numero di riunioni non pianificate organizzate da un utente durante il periodo di tempo specificato.</li><li>**Il totale** delle riunioni a cui ha partecipato un utente è <em></em> la somma delle riunioni pianificate, ricorrenti, non pianificate e non classificate a cui un utente ha partecipato nel periodo di tempo specificato.</li><li>**Riunioni a cui l'utente ha** partecipato una sola volta è il numero di riunioni pianificate a cui un utente ha partecipato nel periodo di tempo specificato.</li><li>**Riunioni a cui l'utente** ha partecipato ricorrentmente è il numero di riunioni ricorrenti a cui ha partecipato un utente durante il periodo di tempo specificato.</li><li>**Riunioni a cui ha partecipato un** utente è il numero di riunioni non pianificate a cui ha partecipato un utente durante il periodo di tempo specificato.</li><li>**Le chiamate 1:1** sono il numero di chiamate 1:1 a cui l'utente ha partecipato nel periodo di tempo specificato.</li><li>**Il tempo audio** è il tempo audio totale (minuti) a cui l'utente ha partecipato nel periodo di tempo specificato.</li><li>**Il tempo video** è il tempo video totale (minuti) a cui l'utente ha partecipato nel periodo di tempo specificato.</li><li>**Il tempo di condivisione dello** schermo è il tempo totale di condivisione dello schermo (minuti) a cui l'utente ha partecipato nel periodo di tempo specificato.</li>  <li>**L'ultima attività** è la data (UTC) in cui l'utente ha partecipato a un'attività di Teams.</li><li>**Altre attività** rilevano quando l'utente è considerato attivo, ma ha un valore pari a zero per i messaggi di chat, le chiamate 1:1, i messaggi del canale, il totale delle riunioni e le riunioni organizzate. Esempi di azioni sono quando un utente apre un post di un messaggio del canale ma non risponde a esso o quando un utente riceve un messaggio privato e lo legge ma non risponde.</li> <li>**Le riunioni non classificate** sono quelle che non possono essere classificate come pianificate o ricorrenti o non pianificate. Si tratta di numeri brevi che per la maggior parte non possono essere identificati a causa di informazioni di telemetria manomesso</li> </ul>**Le chiamate di** gruppo sono state sostituite da **Riunioni organizzate adhoc** e **Riunioni organizzate adhoc.** La somma di questi due valori è uguale a quella misurata dalle **chiamate di gruppo.**
|**8**   |Selezionare **Modifica colonne** per aggiungere o rimuovere colonne nella tabella. |
|**9**   |Esportare il report in un file CSV per l'analisi offline. Selezionare **Esporta in Excel,** quindi nella **scheda Download** selezionare **Scarica** per scaricare il report quando è pronto.<br><br>![Screenshot della scheda Download che mostra i report esportati da scaricare](../media/teams-reports-export-to-csv.png) <br>Quando si visualizza il report in Excel, viene visualizzata anche una colonna **ID** che rappresenta l'ID utente. Un ID utente è in genere una stringa alfanumerica. ||

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>Argomenti correlati

- [Analisi e creazione di report di Teams](teams-reporting-reference.md)

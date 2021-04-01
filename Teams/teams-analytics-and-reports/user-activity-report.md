---
title: Report attività utente di Microsoft Teams
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
description: Informazioni su come usare il report Attività utente di Teams nell'interfaccia di amministrazione di Microsoft Teams per vedere come gli utenti dell'organizzazione usano Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9122289d0765dbdded98727d2ed06912d0348f64
ms.sourcegitcommit: 66e7b28ba1c0433535eb6a3e7d883851c27d9d1f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "51478336"
---
# <a name="microsoft-teams-user-activity-report"></a>Report attività utente di Microsoft Teams

Il report Attività utente di Teams fornisce informazioni dettagliate sui tipi di attività che gli utenti dell'organizzazione ese in Teams. È possibile vedere quanti utenti comunicano in modo non pianificato tramite riunioni non pianificate (1:1 e chiamate di gruppo). Visualizzare il numero di riunioni organizzate da un utente di Teams e le riunioni a cui un utente di Teams ha partecipato. Visualizza i dettagli sui minuti dello schermo, video e audio e le statistiche sulle comunicazioni chat, ad esempio il numero di utenti che rispondono e pubblicano messaggi del canale e il numero di utenti che si impegnano in messaggi di chat 1:1 o di gruppo.

## <a name="view-the-user-activity-report"></a>Visualizzare il report attività utente

Per apportare queste modifiche, è necessario essere un amministratore del servizio Teams. Vedere [Usare i ruoli di amministratore di Teams per gestire Teams](../using-admin-roles.md) per informazioni su come ottenere ruoli e autorizzazioni di amministratore.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams selezionare Analisi **& report**  >  **utilizzo**. Nella scheda **Visualizza report,** in **Report,** selezionare **Attività utente di Teams.**
2. In **Intervallo di date** selezionare un intervallo e quindi selezionare Esegui **report.**

    ![Screenshot del report attività utente di Teams nell'interfaccia di amministrazione di Teams con callout](../media/teams-reports-user-activity-with-callouts.png "Screenshot del report attività utente di Teams nell'interfaccia di amministrazione di Teams con callout")

## <a name="interpret-the-report"></a>Interpretare il report

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Il report Attività utente di Teams può essere visualizzato per le tendenze degli ultimi 7, 30 o 90 giorni. |
|**2**   |Ogni report riporta la data in cui è stato generato. I report in genere riflettono una latenza di 24 ore dal momento dell'attività. |
|**3**   |I punti dati della serie temporale nel grafico mostrano metriche di utilizzo diverse aggregate nel tenant. |
|**4**   |I dati tabulari rappresentavano metriche di utilizzo diverse aggregate per utente. |
|**5**   |<ul><li>L'asse X del grafico è l'intervallo di date selezionato per il report.</li> <li> L'asse Y è il conteggio degli elementi attivi o delle attività.</li> </ul>Posizionare il puntatore del mouse sul punto che rappresenta un elemento o un'attività in una data specifica per visualizzare il numero di istanze dell'elemento o dell'attività in tale data.|
|**6**   | Ognuna delle metriche rappresentate nel grafico a livello di tenant. Filtrare gli elementi visualizzati nel grafico selezionando un elemento nella legenda. Selezionare **Messaggi del canale,** **Rispondi** ai messaggi,  **Messaggi chat** o Riunioni **organizzate** per visualizzare le informazioni correlate a ognuno di essi. La modifica di questa selezione non modifica le informazioni nella tabella. |
|**7**   |La tabella fornisce una suddivisione dell'utilizzo in base all'utente.   <ul><li>**Nome visualizzato** è il nome visualizzato dell'utente. Selezionare il nome visualizzato per passare alla pagina dei dettagli utente nell'interfaccia di amministrazione di Microsoft Teams.</li><li>**Messaggi del** canale è il numero di messaggi univoci che l'utente ha pubblicato in un canale del team durante il periodo di tempo specificato.</li><li>**Messaggi di risposta** è il numero di messaggi di risposta univoci che l'utente ha pubblicato in un canale del team durante il periodo di tempo specificato.</li> <li>**Pubblica messaggi** è il numero di messaggi di post univoci che l'utente ha pubblicato in un canale del team durante il periodo di tempo specificato.</li><li>**Messaggi chat** è il numero di messaggi univoci che l'utente ha pubblicato in una chat privata durante il periodo di tempo specificato.</li><li>**Messaggi urgenti** è il numero di messaggi urgenti che l'utente ha pubblicato in una chat durante il periodo di tempo specificato.</li><li>**Totale riunioni organizzate** è la somma di una riunione pianificata, ricorrente, non pianificata e <em>non</em> classificata organizzata da un utente durante il periodo di tempo specificato.</li><li>**Riunioni organizzate una sola volta** è il numero di riunioni pianificate una sola volta organizzate da un utente durante il periodo di tempo specificato.</li><li>**Riunioni organizzate ricorrenti pianificate** è il numero di riunioni ricorrenti organizzate da un utente durante il periodo di tempo specificato.</li><li>**Riunioni organizzate adhoc** è il numero di riunioni non pianificate organizzate da un utente durante il periodo di tempo specificato.</li><li>**Totale riunioni partecipate** è la somma delle riunioni programmate, ricorrenti, non pianificate e <em>non</em> classificate a cui un utente ha partecipato durante il periodo di tempo specificato.</li><li>**Riunioni partecipate programmate una sola** volta è il numero di riunioni programmate una sola volta a cui un utente ha partecipato durante il periodo di tempo specificato.</li><li>**Riunioni partecipate ricorrenti pianificate** è il numero di riunioni ricorrenti a cui un utente ha partecipato durante il periodo di tempo specificato.</li><li>**Riunioni partecipate adhoc** è il numero di riunioni non pianificate a cui un utente ha partecipato durante il periodo di tempo specificato.</li><li>**Chiamate 1:1** è il numero di chiamate 1:1 a cui l'utente ha partecipato durante il periodo di tempo specificato.</li><li>**Il tempo audio** è il tempo audio totale (minuti) a cui l'utente ha partecipato durante il periodo di tempo specificato.</li><li>**Il tempo video** è il tempo video totale (minuti) a cui l'utente ha partecipato durante il periodo di tempo specificato.</li><li>**Il tempo di condivisione dello** schermo è il tempo totale di condivisione dello schermo (minuti) a cui l'utente ha partecipato durante il periodo di tempo specificato.</li>  <li>**Ultima attività** è l'ultima data (UTC) a cui l'utente ha partecipato a un'attività di Teams.</li><li>**Altre attività** rilevano quando l'utente è considerato attivo, ma ha un valore pari a zero per i messaggi di chat, le chiamate 1:1, i messaggi del canale, il totale delle riunioni e le riunioni organizzate. Esempi di azioni sono quando un utente apre un post di messaggio del canale ma non risponde o quando un utente riceve un messaggio privato e lo legge ma non risponde.</li> <li>**Le riunioni non classificate** sono quelle che non possono essere classificate come programmate o ricorrenti o non pianificate. Si tratta di numeri brevi e per lo più non identificabili a causa di informazioni di telemetria manomissioni</li> </ul>**Le chiamate di** gruppo sono state sostituite da Riunioni **organizzate adhoc** e **Riunioni adhoc.** La somma di questi due valori è uguale a quella misurata dalle **chiamate di gruppo.**
|**8**   |Selezionare **Modifica colonne** per aggiungere o rimuovere colonne nella tabella. |
|**9**   |Esportare il report in un file CSV per l'analisi offline. Selezionare **Esporta in Excel** e quindi nella scheda **Download** selezionare **Scarica** per scaricare il report quando è pronto.<br><br>![Screenshot della scheda Download che mostra i report esportati da scaricare](../media/teams-reports-export-to-csv.png) <br>Quando si visualizza il report in Excel, viene visualizzata anche una colonna **ID** che rappresenta l'ID utente. Un ID utente è in genere una stringa alfanumerica. ||

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>Rendere anonimi i dati specifici dell'utente

Per rendere anonimi i dati nel report attività utente di Teams, è necessario essere un amministratore globale. In questo modo si nasconderanno informazioni identificabili come il nome visualizzato, la posta elettronica e l'ID AAD nel report e la relativa esportazione.

1. Nell'interfaccia di amministrazione di Microsoft 365 passare a **Impostazioni** organizzazione Impostazioni e nella scheda Servizi \> scegliere **Report.** 
    
2. Selezionare **Report** e quindi scegliere **Visualizza identificatori anonimi**. Questa impostazione viene applicata sia ai report di utilizzo nell'interfaccia di amministrazione di Microsoft 365 che all'interfaccia di amministrazione di Teams.
  
3. Selezionare **Salva modifiche**.

## <a name="related-topics"></a>Argomenti correlati

- [Analisi e creazione di report di Teams](teams-reporting-reference.md)

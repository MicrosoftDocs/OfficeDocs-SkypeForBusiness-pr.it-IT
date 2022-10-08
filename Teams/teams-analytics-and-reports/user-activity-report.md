---
title: Report attività degli utenti di Microsoft Teams
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
description: Informazioni su come usare il report attività degli utenti di Teams nell'interfaccia di amministrazione di Microsoft Teams per vedere in che modo gli utenti dell'organizzazione usano Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 78f1b58dbcddb66e2d8a045d9510a3609bfe4a05
ms.sourcegitcommit: b2692b3f6c60d8df5ba0677c68ff9c90a75a0d72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2022
ms.locfileid: "68033844"
---
# <a name="microsoft-teams-user-activity-report"></a>Report attività degli utenti di Microsoft Teams

The Teams user activity report gives insight into the types of activities that users in your organization do in Teams. È possibile vedere quanti utenti comunicano non pianificati tramite riunioni non pianificate (1:1 e chiamate di gruppo). Vedere quante riunioni ha organizzato un utente di Teams e a cui ha partecipato un utente di Teams. Visualizzare i dettagli su minuti di schermo, video e audio e statistiche sulle comunicazioni in chat, ad esempio quanti utenti rispondono ai messaggi del canale e pubblicano messaggi del canale e quanti utenti interagiscono nei messaggi in chat 1:1 o di gruppo.

> [!NOTE]
> La possibilità di pianificare un report attività utente non è al momento disponibile.

## <a name="view-the-user-activity-report"></a>Visualizzare il report attività utente

Per apportare queste modifiche, è necessario essere un amministratore del servizio Teams. Vedere [Usare i ruoli di amministratore di Teams per gestire Teams](../using-admin-roles.md) per informazioni su come ottenere ruoli e autorizzazioni di amministratore.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams selezionare **Analisi & report** > **utilizzo**. Nella scheda **Visualizza report** , in **Report**, selezionare **Attività degli utenti di Teams**.
2. In **Intervallo di date** selezionare un intervallo e quindi **selezionare Esegui report**.

    ![Screenshot del report attività degli utenti di Teams nell'interfaccia di amministrazione di Teams con callout.](../media/teams-reports-user-activity-with-callouts.png "Screenshot del report attività degli utenti di Teams nell'interfaccia di amministrazione di Teams con callout")

## <a name="interpret-the-report"></a>Interpretare il report

| Callout |Descrizione  |
|--------|-------------|
|**1**   |Il report Attività degli utenti di Teams può essere visualizzato per le tendenze degli ultimi 7, 30 o 90 giorni. |
|**2**   |Ogni report riporta la data in cui è stato generato. I report in genere riflettono una latenza di 24 ore dal momento dell'attività. |
|**3**   |I punti dati della serie temporale nel grafico mostrano metriche di utilizzo diverse aggregate nel tenant. |
|**4**   |I dati tabulari rappresentavano metriche di utilizzo diverse aggregate per utente. |
|**5**   |<ul><li>L'asse X nel grafico rappresenta l'intervallo di date selezionato per il report.</li> <li> L'asse Y è il conteggio degli elementi attivi o delle attività.</li> </ul>Passa il puntatore del mouse sul punto che rappresenta un elemento o un'attività in una data specificata per visualizzare il numero di istanze dell'elemento o dell'attività in tale data specificata.|
|**6**   | Ognuna delle metriche rappresentate nel grafico a livello di tenant. Filtrare gli elementi visualizzati nel grafico selezionando un elemento nella legenda. Selezionare **Messaggi del canale**, **Messaggi di risposta**,  **Messaggi in chat** o **Riunioni organizzate** per visualizzare le informazioni pertinenti. La modifica di questa selezione non modifica le informazioni nella tabella. |
|**7**   |La tabella fornisce un'analisi dell'utilizzo in base all'utente.   <ul><li>**Nome utente** è l'indirizzo di posta elettronica dell'utente. Vedere [la sezione seguente](#make-the-user-specific-data-anonymous) per indicazioni su come anonimizzarlo o selezionare il nome utente per passare alla pagina dei dettagli dell'utente.</li><li>**Nome tenant** è il nome di un tenant interno o esterno a cui appartiene un utente. <br> Se un utente appartiene a un tenant esterno, le metriche dei dati corrispondenti, ad esempio i messaggi di posta elettronica e i messaggi di risposta, vengono calcolate in base alle interazioni nei canali condivisi del tenant dell'amministratore. Le interazioni eseguite dall'utente nel proprio tenant (all'esterno dei canali condivisi del tenant specificato) non sono considerate per il report sull'utilizzo da parte dell'amministratore del tenant specificato.  </li><li>**Messaggi del canale** è il numero di messaggi univoci pubblicati dall'utente in un canale del team durante il periodo di tempo specificato.</li><li>**Messaggi di** risposta è il numero di messaggi di risposta univoci pubblicati dall'utente in un canale del team durante il periodo di tempo specificato.</li> <li>**Messaggi pubblicati** è il numero di messaggi post univoci pubblicati dall'utente in un canale del team durante il periodo di tempo specificato.</li><li>**Messaggi di chat** è il numero di messaggi univoci pubblicati dall'utente in una chat privata durante il periodo di tempo specificato.</li><li>**Messaggi urgenti** è il numero di messaggi urgenti pubblicati dall'utente in una chat durante il periodo di tempo specificato.</li><li>**Totale riunioni organizzate** è la somma delle riunioni pianificate, ricorrenti, non pianificate e <em>non classificate</em> organizzate da un utente durante il periodo di tempo specificato.</li><li>**Riunioni organizzate una sola volta** è il numero di riunioni pianificate una sola volta organizzate da un utente durante il periodo di tempo specificato.</li><li>**Riunioni pianificate ricorrenti** è il numero di riunioni ricorrenti organizzate da un utente durante il periodo di tempo specificato.</li><li>**Riunioni organizzate ad hoc** è il numero di riunioni non pianificate organizzate da un utente durante il periodo di tempo specificato.</li><li>**Totale riunioni a cui l'utente ha partecipato** è la somma delle riunioni pianificate, ricorrenti, non pianificate e <em>non classificate</em> a cui ha partecipato un utente durante il periodo di tempo specificato.</li><li>**Riunioni a cui ha partecipato una sola volta** è il numero delle riunioni pianificate una sola volta a cui ha partecipato un utente durante il periodo di tempo specificato.</li><li>**Riunioni a cui l'utente ha partecipato come ricorrente** è il numero delle riunioni ricorrenti a cui ha partecipato un utente durante il periodo di tempo specificato.</li><li>**Riunioni a cui ha partecipato ad hoc** è il numero di riunioni non pianificate a cui ha partecipato un utente durante il periodo di tempo specificato.</li><li>**Le chiamate 1:1** sono il numero di chiamate 1:1 a cui l'utente ha partecipato durante il periodo di tempo specificato.</li><li>**Tempo audio** è il tempo audio totale (minuti) a cui l'utente ha partecipato durante il periodo di tempo specificato.</li><li>**Tempo video** è il tempo video totale (minuti) a cui l'utente ha partecipato durante il periodo di tempo specificato.</li><li>**Il tempo di condivisione dello** schermo è il tempo totale di condivisione dello schermo (minuti) a cui l'utente ha partecipato durante il periodo di tempo specificato.</li>  <li>**L'ultima attività** è l'ultima data (UTC) in cui l'utente ha partecipato a un'attività di Teams.</li><li>**Altre attività** tengono traccia quando l'utente è considerato attivo ma ha un valore zero per i messaggi in chat, le chiamate 1:1, i messaggi del canale, il totale delle riunioni e le riunioni organizzate. Esempi di azioni sono quando un utente apre un post di un messaggio del canale ma non risponde o quando un utente riceve un messaggio privato e lo legge ma non risponde.</li> <li>**Le riunioni non classificate** sono quelle che non possono essere identificate come pianificate, ricorrenti o non pianificate. Questi sono pochi in numero e spesso non possono essere identificati a causa di informazioni di telemetria imperfette.</li> </ul>**Le chiamate di gruppo** sono state sostituite da **Riunioni organizzate ad hoc** e **Riunioni a cui hanno partecipato ad hoc**. La somma di questi due valori è uguale a quella misurata dalle **chiamate di gruppo**.
|**8**   |Selezionare **Modifica colonne** per aggiungere o rimuovere colonne nella tabella. |
|**9**   |Esportare il report in un file CSV per l'analisi offline. Selezionare **Esporta in Excel**, quindi nella scheda **Download** selezionare **Scarica** per scaricare il report quando è pronto.<br><br>![Screenshot della scheda Download che mostra i report esportati da scaricare.](../media/teams-reports-export-to-csv.png) <br>Quando si visualizza il report in Excel, viene visualizzata anche una colonna **ID** , che rappresenta l'ID utente. Un ID utente è in genere una stringa alfanumerica. |

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>Rendere anonimi i dati specifici dell'utente

Per rendere anonimi i dati nel report attività degli utenti di Teams, è necessario essere un amministratore globale. Verranno nascoste le informazioni identificabili (usando hash MD5), ad esempio il nome visualizzato, la posta elettronica e l'ID AAD nel report e nella relativa esportazione.

1. In interfaccia di amministrazione di Microsoft 365 passare a **Impostazioni** \> **impostazioni organizzazione** e, nella scheda **Servizi**, scegliere **Report**.
    
2. Selezionare **Report** e quindi scegliere **Visualizza nomi di utenti, gruppi e siti nascosti in tutti i report**. Questa impostazione viene applicata sia ai report sull'utilizzo in interfaccia di amministrazione di Microsoft 365 che all'interfaccia di amministrazione di Teams.
  
3. Selezionare **Salva modifiche**.

## <a name="related-topics"></a>Argomenti correlati

- [Analisi e creazione dei report di Teams](teams-reporting-reference.md).

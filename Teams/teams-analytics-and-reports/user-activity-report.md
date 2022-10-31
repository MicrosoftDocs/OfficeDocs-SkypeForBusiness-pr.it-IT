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
ms.openlocfilehash: d353a49dc074f721e805e3269580f13b8663b85f
ms.sourcegitcommit: 57616ad45eaa8be7f78dd0126d324c8777c5a367
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2022
ms.locfileid: "68792805"
---
# <a name="microsoft-teams-user-activity-report"></a>Report attività degli utenti di Microsoft Teams

The Teams user activity report gives insight into the types of activities that users in your organization do in Teams. È possibile vedere quanti utenti comunicano non pianificati tramite riunioni non pianificate (1:1 e chiamate di gruppo). Vedere quante riunioni ha organizzato un utente di Teams e a cui ha partecipato un utente di Teams. Visualizzare i dettagli su minuti di schermo, video e audio e statistiche sulle comunicazioni in chat, ad esempio quanti utenti rispondono ai messaggi del canale e pubblicano messaggi del canale e quanti utenti interagiscono nei messaggi in chat 1:1 o di gruppo.

Con altre informazioni aggiuntive sugli utenti interni ed esterni, è ora possibile misurare l'interazione degli utenti nei [canali condivisi](/Teams/shared-channels.md) interni ed esterni. Ad esempio, metriche come il nome tenant in cui appartiene l'utente, i nomi tenant esterni in cui l'utente sta interagendo e se l'utente è esterno al tenant aiuteranno gli amministratori a misurare l'inattività degli utenti attraverso le caratteristiche dei canali condivisi. 

> [!NOTE]
> La possibilità di pianificare un report attività utente non è al momento disponibile.

## <a name="view-the-user-activity-report"></a>Visualizzare il report attività utente

Per visualizzare il report nell'interfaccia di amministrazione di Microsoft Teams, è necessario essere un amministratore globale, un lettore globale o un amministratore del servizio Teams. Vedere [Usare i ruoli di amministratore di Teams per gestire Teams](../using-admin-roles.md) per informazioni su come ottenere ruoli e autorizzazioni di amministratore.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams selezionare **Analisi & report** > **utilizzo**. Nella scheda **Visualizza report** , in **Report**, selezionare **Attività degli utenti di Teams**.
2. In **Intervallo di date** selezionare un intervallo e quindi **selezionare Esegui report**.

    ![Screenshot del report attività degli utenti di Teams nell'interfaccia di amministrazione di Teams con callout.](../media/teams-reports-user-activity-with-callouts2.png "Screenshot del report attività degli utenti di Teams nell'interfaccia di amministrazione di Teams con callout")

## <a name="interpret-the-report"></a>Interpretare il report

| **Callout** |**Descrizione**  |
|--------|-------------|
|**1**   |Il report Attività degli utenti di Teams può essere visualizzato per le tendenze degli ultimi 7, 30, 90 o 180 giorni. |
|**2**   |Ogni report riporta la data in cui è stato generato. I report in genere riflettono una latenza di 24-48 ore dal momento dell'attività. |
|**3**   |I dati della serie temporale rappresentati nel grafico superiore mostrano metriche di utilizzo diverse aggregate per l'intero tenant. |
|**4**   |I dati tabulari rappresentati nella metà inferiore mostrano metriche di utilizzo diverse aggregate per utente. |
|**5**   |<ul><li>L'asse X nel grafico rappresenta l'intervallo di date selezionato per il report.</li> <li> L'asse Y è il conteggio degli elementi attivi o delle attività.</li> </ul>Passa il puntatore del mouse sul punto che rappresenta un elemento o un'attività in una data specificata per visualizzare il numero di istanze dell'elemento o dell'attività in tale data specificata.|
|**6**   | Ognuna delle metriche è rappresentata nel grafico a livello di tenant. Filtrare gli elementi visualizzati nel grafico selezionando un elemento nella legenda. Selezionare **Messaggi del canale**, **Messaggi di risposta**,  **Messaggi in chat** o **Riunioni organizzate** e altro ancora per visualizzare le informazioni pertinenti. La modifica di questa selezione non modifica le informazioni nella tabella. |
|**7**   |La tabella fornisce un'analisi dell'utilizzo in base all'utente.   <ul><li>**Nome utente** è l'indirizzo di posta elettronica dell'utente. Vedere [la sezione seguente](#make-the-user-specific-data-anonymous) per indicazioni su come renderla anonima.  Selezionare il nome utente per passare alla pagina dei dettagli dell'utente.</li><li>**Nome tenant** (nuovo) è il nome di un tenant interno o esterno a cui appartiene un utente. Se un utente appartiene a un tenant esterno, metriche di utilizzo diverse (ad esempio, pubblicare messaggi, messaggi di risposta e altro) vengono calcolate in base alle interazioni in uno o più canali condivisi del tenant dell'amministratore. Le interazioni eseguite da un utente esterno nel proprio tenant non vengono considerate per il report sull'utilizzo da parte dell'amministratore di un determinato tenant.  </li><li>**I nomi dei tenant di canale condivisi** (nuovi) sono i nomi dei tenant interni o esterni a cui l'utente ha partecipato come parte di un canale condiviso.</li><li>**Messaggi del canale** è il numero di messaggi univoci pubblicati dall'utente in un canale del team durante il periodo di tempo specificato.</li><li>**Risposte** è il numero di messaggi di risposta univoci pubblicati dall'utente in un canale del team durante il periodo di tempo specificato.</li> <li>**Post** è il numero di messaggi univoci pubblicati dall'utente in un canale del team durante il periodo di tempo specificato.</li><li>**Messaggi di chat** è il numero di messaggi univoci pubblicati dall'utente in una chat privata durante il periodo di tempo specificato.</li><li>**Messaggi urgenti** è il numero di messaggi urgenti pubblicati dall'utente in una chat durante il periodo di tempo specificato.</li><li>**Totale riunioni organizzate** è la somma delle riunioni pianificate, ricorrenti, non pianificate e non classificate organizzate da un utente durante il periodo di tempo specificato.</li><li>**Riunioni organizzate una tantum** è il numero di riunioni pianificate una tantum organizzate da un utente durante il periodo di tempo specificato.</li><li>**Riunioni pianificate ricorrenti** è il numero di riunioni ricorrenti organizzate da un utente durante il periodo di tempo specificato.</li><li>**Riunioni organizzate ad hoc** è il numero di riunioni non pianificate organizzate da un utente durante il periodo di tempo specificato.</li><li>**Totale riunioni a cui l'utente ha partecipato** è la somma delle riunioni pianificate, ricorrenti, non pianificate e non classificate a cui ha partecipato un utente durante il periodo di tempo specificato.</li><li>**Riunioni a cui ha partecipato una sola volta** è il numero delle riunioni pianificate una tantum a cui ha partecipato un utente durante il periodo di tempo specificato.</li><li>**Riunioni a cui ha partecipato una riunione pianificata ricorrente** è il numero di riunioni ricorrenti a cui ha partecipato un utente durante il periodo di tempo specificato.</li><li>**Riunioni a cui ha partecipato ad hoc** è il numero di riunioni non pianificate a cui ha partecipato un utente durante il periodo di tempo specificato.</li><li>**Chiamate 1:1** è il numero di chiamate 1:1 a cui l'utente ha partecipato durante il periodo di tempo specificato.</li><li>**Il tempo audio** è il tempo audio totale (in minuti) a cui l'utente ha partecipato durante il periodo di tempo specificato.</li><li>**Il tempo video** è il tempo video totale (in minuti) a cui l'utente ha partecipato durante il periodo di tempo specificato.</li><li>**Il tempo di condivisione dello** schermo è il tempo totale di condivisione dello schermo (minuti) a cui l'utente ha partecipato durante il periodo di tempo specificato.</li>  <li>**L'ultima attività** è l'ultima data (UTC) in cui l'utente ha partecipato a un'attività di Teams.</li><li>**Altre attività** tengono traccia quando l'utente è considerato attivo ma ha un valore zero per i messaggi in chat, le chiamate 1:1, i messaggi del canale, il totale delle riunioni e le riunioni organizzate. Esempi di azioni sono quando un utente modifica lo stato di Teams o il messaggio di stato di Teams, quando un utente apre un post del messaggio del canale ma non risponde o quando un utente riceve un messaggio privato e lo legge ma non risponde.</li> </ul> **Le riunioni non classificate** sono quelle che non possono essere identificate come pianificate, ricorrenti o non pianificate. Questi sono pochi in numero e spesso non possono essere identificati a causa di informazioni di telemetria imperfette.<br><br>**Le chiamate di gruppo** sono state sostituite da **Riunioni organizzate ad hoc** e **Riunioni a cui hanno partecipato ad hoc**. La somma di questi due valori è uguale a quella misurata dalle **chiamate di gruppo**. <br/><br/>Si noti che se un utente non esiste più, il nome viene visualizzato come "--" nella tabella.
|**8**   |Selezionare **Modifica colonne** per aggiungere o rimuovere colonne nella tabella. |
**9**   |Esportare il report in un file CSV per l'analisi offline. Selezionare **Esporta in Excel** per scaricare il report nel browser. <br>Quando si visualizza il report in Excel: <br>- Verrà visualizzata anche una colonna **ID utente** , che rappresenta l'ID utente. Un ID utente è in genere una stringa alfanumerica. <br>- Noterai anche che le colonne **Durata audio**, **Durata video** e **Durata condivisione schermo** sono rappresentate sia in giorni che in secondi. |


[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>Rendere anonimi i dati specifici dell'utente

Per rendere anonimi i dati nel report attività utente di Teams, è necessario essere un amministratore globale. Il amministratore globale può nascondere le informazioni identificabili (usando hash MD5), ad esempio il nome visualizzato, il nome del gruppo, la posta elettronica e l'ID AAD nei report e la loro esportazione.

1. In interfaccia di amministrazione di Microsoft 365 passare a **Impostazioni** \> **impostazioni organizzazione** e, nella scheda **Servizi**, scegliere **Report**.
    
2. Selezionare **Report** e quindi scegliere **Visualizza nomi di utenti, gruppi e siti nascosti in tutti i report**. Questa impostazione viene applicata sia ai report sull'utilizzo in interfaccia di amministrazione di Microsoft 365 che all'interfaccia di amministrazione di Teams.
  
3. Selezionare **Salva modifiche**.


> [!NOTE]
> L'abilitazione di questa impostazione deidentificherà le informazioni sul nome di utenti, gruppi e siti nel [report attività utente di Teams](user-activity-report.md), nel [report Sull'utilizzo dei dispositivi di Teams](device-usage-report.md) e nel [report sull'utilizzo di Teams](teams-usage-report.md) . A partire dal 1° settembre 2021, questa impostazione è abilitata per impostazione predefinita per tutti gli utenti nell'ambito del nostro costante impegno a proteggere le informazioni importanti e a consentire alle aziende di supportare le leggi locali sulla privacy. Questa impostazione si applica anche ai report sull'utilizzo di Microsoft 365 in interfaccia di amministrazione di Microsoft 365, Microsoft Graph e Power BI.
## <a name="related-topics"></a>Argomenti correlati

- [Analisi e creazione dei report di Teams](teams-reporting-reference.md).

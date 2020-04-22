---
title: Report dettagli della sessione.
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: e62ac09f-dfdc-4306-8e06-31349a3b27f0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
description: Il nuovo dashboard dei report di Microsoft 365 Mostra la panoramica delle attività nei prodotti Office 365 dell'organizzazione. Ti permette di approfondire le analisi fino al livello dei report dei singoli prodotti per una panoramica più dettagliata delle attività di ciascun prodotto.
ms.openlocfilehash: b10e68e46b8865579692594ded33e89558f4fdc2
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776281"
---
# <a name="session-details-report"></a>Report dettagli della sessione.

[] Il nuovo dashboard **Report** di Office 365 offre una panoramica delle attività su tutti i prodotti Office 365 nella tua organizzazione. Ti permette di approfondire le analisi fino al livello dei report dei singoli prodotti per una panoramica più dettagliata delle attività di ciascun prodotto. Ad esempio, puoi usare il report **Dettagli sessione di Skype for business** per vedere i dettagli sulle singole esperienze di chiamata dell'utente.
  
Vedere [Panoramica dei report](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) per altri report disponibili.
  
Questo report, insieme agli altri report di Skype for business, fornisce informazioni dettagliate sull'attività, inclusi i dettagli della sessione nell'organizzazione. Questi dettagli sono molto utili per l'analisi, la pianificazione e l'esecuzione di altre decisioni aziendali per l'organizzazione e per la configurazione dei crediti per le [comunicazioni](/microsoftteams/what-are-communications-credits).
  
> [!NOTE]
> È possibile visualizzare tutti i report di Skype for business quando si accede come amministratore all'interfaccia di amministrazione di Microsoft 365. 
  
## <a name="how-to-get-to-the-skype-for-business-session-details-report"></a>Come ottenere il report Dettagli sessione di Skype for business

1. Accedere all'interfaccia di amministrazione > **report**
    
2. Selezionare **report** nel menu a sinistra e quindi fare clic su **utilizzo**.
    
3. Nell'elenco in **selezionare un report**fare clic su **Dettagli sessione di Skype for business**.
    
    > [!TIP]
    > Se > **questo report non** > è visualizzato, accedere ai dettagli della**sessione**nell'interfaccia di **amministrazione di Skype for business**. 
  
    > [!IMPORTANT]
    > A seconda dell'abbonamento a Microsoft 365 o Office 365, è possibile che non vengano visualizzati tutti i prodotti e i report visualizzati qui. 
  
## <a name="interpret-the-skype-for-business-session-details-report"></a>Interpretare il report Dettagli sessione di Skype for business

È possibile visualizzare i dettagli della sessione Skype for business dell'utente esaminando ognuna delle colonne visualizzate.
  
Questo è l'aspetto del report.
  
![Dashboard dei dettagli della sessione di Skype for business per il report.](../images/3d87ab39-6eaa-46b5-b5f9-7f54dc987ae0.png)
  
***
![Numero 1](../images/sfbcallout1.png)<br/>La **ricerca di un utente tramite alias** consente di cercare un singolo utente e di visualizzare tutti i dettagli della sessione dell'utente nella tabella seguente. 
***
![Numero 2](../images/sfbcallout2.png)<br/>**Invio da data/ora** consente di inserire la data di inizio. È possibile usare il calendario per selezionare la data o immetterla manualmente. Questo campo deve essere popolato.
***
![Numero 3](../images/sfbcallout3.png)<br/>**Invio a data ora** consente di inserire la data di fine. È possibile usare il calendario per selezionare la data o immetterla manualmente. Se non viene impostata una data di fine, l'impostazione predefinita è 30 giorni dalla data di inizio.
***
![Numero 4](../images/sfbcallout4.png)<br/>La tabella mostra una ripartizione dei dettagli di tutte le sessioni per ogni utente. In questo articolo vengono visualizzati tutti gli utenti a cui sono stati assegnati Skype for business e le relative informazioni sulla sessione. È possibile aggiungere/rimuovere colonne dalla tabella. <br/><br/>La tabella contiene le colonne seguenti per ogni sessione:
*    **ID finestra di dialogo** è l'ID per l'identificatore univoco della sessione SIP.
*    **Descrizione tipi di elementi multimediali** descrive se la sessione è una conferenza telefonica o una sessione P2P e il tipo di elemento multimediale usato (audio/video/condivisione applicazioni).
*    **Ora inizio** è l'ora in cui è stata avviata la sessione.
*    **Ora di fine** è il momento in cui la sessione è terminata.
*    **From URI** è l'URI dell'utente o del servizio che ha avviato la sessione. Potrebbe essere vuoto se l'utente ha avviato la sessione da un telefono PSTN.
*    **Per URI** è l'URI dell'utente o del servizio che era la destinazione dell'avvio della sessione. Nel caso della conferenza, questo è l'URI dell'organizzatore. Potrebbe essere vuoto se la destinazione della sessione era un numero di telefono PSTN.
*    **Dalla versione client** viene indicato l'agente utente e la versione del client usata dall'utente o dal servizio che ha avviato la sessione.
*    **Per la versione client** viene indicato l'agente utente e la versione del client usata dall'utente o dal servizio che era la destinazione dell'avvio della sessione.
*    **URL conferenza** è l'URL SIP per la conferenza, se la sessione è stata una conferenza telefonica. Tutti gli utenti della stessa conferenza telefonica avranno lo stesso URL conferenza. 
*    **Da Tel num** è il numero di telefono che è stato il destinatario della sessione, se applicabile. Le ultime cifre del numero di telefono possono essere sostituite con "x" per proteggere la privacy degli utenti.
*    **Per numero Tel** si trova il numero di telefono che era il destinatario della sessione, se applicabile. Le ultime cifre del numero di telefono possono essere sostituite con "x" per proteggere la privacy degli utenti.
*    **Da ID endpoint** è un GUID univoco dell'endpoint usato dall'utente. Usato per identificare se l'utente sta comunicando più sessioni dallo stesso endpoint. Potrebbe essere vuoto se l'utente usa un telefono PSTN o se la sessione è stata avviata da un servizio.
*    **Per ID endpoint** è un GUID univoco dell'endpoint usato dall'utente. Usato per identificare se l'utente sta comunicando più sessioni dallo stesso endpoint. Potrebbe essere vuoto se l'utente usa un telefono PSTN, se la sessione è stata avviata da un servizio o se non è stata creata una sessione.
*    L' **istanza di conf** è un GUID univoco per l'istanza della conferenza usando l'URL della conferenza. Le riunioni ricorrenti avranno lo stesso URL della conferenza, ma ogni istanza della riunione avrà un'istanza di conf differenza.
*    **Per conto di URI** è l'URI del delegante per conto della quale viene stabilita la sessione. <br/> **Indicato da URI** è l'URI dell'utente che ha fatto riferimento alla creazione di una sessione.
*    Il **codice di risposta** è il codice di risposta SIP per la creazione della sessione che indica se la sessione è stata stabilita correttamente.

Per ogni sessione è disponibile una tabella secondaria con dati diversi a seconda dello scenario. Di seguito sono elencate le schede disponibili nella tabella secondaria per l'utente o i servizi da e a.
*    La scheda sessione Mostra i dati relativi ai computer e ai sistemi operativi.
*    La scheda MEDIALINES Mostra le informazioni sulla connettività di rete e le informazioni sui dispositivi.
*    La scheda AUDIOSTREAMS Mostra i dati sulle prestazioni di rete relativi ai flussi audio coinvolti nella sessione.
*    La scheda AUDIOCLIENTEVENTS Mostra i dati relativi ai problemi rilevati dal client che influiscono sull'esperienza audio.
*    AUDIOSIGNALS Tab Mostra i dati relativi all'elaborazione del segnale audio per la sessione.
*    La scheda APPSHARINGSTREAMS Mostra i dati sulle prestazioni di rete relativi alla condivisione dell'applicazione o ai flussi di condivisione desktop coinvolti nella sessione.
*    VIDEOCLIENTEVENTS Tab Mostra i dati relativi ai problemi rilevati dal client che influiscono sull'esperienza video.
*    La scheda VIDEOSTREAMS Mostra i dati sulle prestazioni di rete relativi ai flussi video coinvolti nella sessione.
*    La scheda TRACEROUTE Mostra i passaggi di rete raccolti tramite traceroute durante la sessione. Il percorso multimediale effettivo usato per la sessione può variare e questi dati sono disponibili solo quando c'è l'audio nella sessione.
*    La scheda FEEDBACKREPORTS Mostra la fine dei dati di sondaggio delle chiamate forniti dagli utenti nella sessione.
***
![Numero 5](../images/sfbcallout5.png)<br/>Fare clic per trascinare una colonna fino a **Per raggruppare per una specifica colonna, trascinare qui l'intestazione di colonna** se si desidera creare una visualizzazione che raggruppi tutti i dati in una o più colonne. 
***
![Numero 6](../images/sfbcallout6.png)<br/>È anche possibile esportare i dati del report in un file CSV di Excel toccando o facendo clic sul collegamento **Esporta in Excel**. <br/><br/> Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati.  
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Per consultare altri report di Skype for Business

- [Report attività in Skype for Business](activity-report.md) permette di vedere quanto gli utenti usano le conferenze peer-to-peer e organizzate o vi partecipano.
    
- [Skype per report di utilizzo del dispositivo Business](device-usage-report.md) permette di vedere i dispositivi, compresi i sistemi operativi e dispositivi mobili basati su Windows, in cui è installata l'app Skype for Business e che la utilizzano per messaggistica istantanea e riunioni.
    
- [Report attività organizzatore di conferenze in Skype for Business](conference-organizer-activity-report.md) permette di vedere quanto gli utenti organizzano conferenze che utilizzano messaggistica istantanea, audio/video, condivisione applicazioni, web, accesso esterno in ingresso/uscita di terze parti e accesso esterno in ingresso/uscita Microsoft.
    
- [Report attività partecipante di conferenze di Skype for business](conference-participant-activity-report.md) Puoi vedere il numero di partecipazioni a conferenze di messaggistica istantanea, audio/video, condivisione applicazioni, Web e accesso esterno in entrata/uscita.
    
- [Report attività peer-to-peer in Skype for Business](peer-to-peer-activity-report.md) - Permette di vedere quanto gli utenti usano messaggistica istantanea, audio/video, condivisione applicazioni e trasferimento di file.
    
- [Report sull'utilizzo PSTN di Skype for business](pstn-usage-report.md) È possibile visualizzare il numero di minuti di chiamate in ingresso/in uscita e il costo per queste chiamate.

- [Skype per gli utenti aziendali bloccati report](users-blocked-report.md) - Permette di consultare gli utenti dell'organizzazione a cui è impedito effettuare chiamate.

- [Report pool di minuti PSTN di Skype for business](pstn-minute-pools-report.md) è possibile visualizzare il numero di minuti consumati durante il mese corrente all'interno dell'organizzazione.
    
## <a name="related-topics"></a>Argomenti correlati
[Report attività nell'interfaccia di amministrazione](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 
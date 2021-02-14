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
description: Il dashboard Report mostra una panoramica delle attività per tutti i prodotti Microsoft 365 o Office 365 nell'organizzazione. Ti permette di approfondire le analisi fino al livello dei report dei singoli prodotti per una panoramica più dettagliata delle attività di ciascun prodotto.
ms.openlocfilehash: 951f93aabe66bdb7e6b92f9b2c6cf1627e7e1a10
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "44205507"
---
# <a name="session-details-report"></a>Report dettagli della sessione.

Il **dashboard** Report mostra una panoramica delle attività per tutti i prodotti Microsoft 365 o Office 365 nell'organizzazione. Ti permette di approfondire le analisi fino al livello dei report dei singoli prodotti per una panoramica più dettagliata delle attività di ciascun prodotto. Ad esempio, è possibile utilizzare il report dettagli **sessione di Skype for Business** per visualizzare i dettagli sulle esperienze di chiamata dei singoli utenti.
  
Per altri [report disponibili,](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) vedere panoramica dei report.
  
Questo report, insieme agli altri rapporti di Skype for Business, ti dà dettagli sull'attività, inclusi i dettagli della sessione in tutta l'organizzazione. Questi dettagli sono molto utili per indagare, pianificare e prendere altre decisioni aziendali per l'organizzazione e per la configurazione dei [Crediti comunicazioni.](/microsoftteams/what-are-communications-credits)
  
> [!NOTE]
> Puoi visualizzare tutti i rapporti di Skype for Business quando accedi come amministratore all'interfaccia di amministrazione di Microsoft 365. 
  
## <a name="how-to-get-to-the-skype-for-business-session-details-report"></a>Come ottenere il report dettagli sessione di Skype for Business

1. Passare all'interfaccia di amministrazione > **report**
    
2. Selezionare **Report dal** menu a sinistra e quindi fare clic su **Utilizzo.**
    
3. Nell'elenco selezionare **un report,** fare clic su **Dettagli sessione Skype for Business.**
    
    > [!TIP]
    > Se non vedi questo report nell'elenco, vai ai dettagli della sessione di report dell'interfaccia di amministrazione di **Skype for**  >    >  Business. 
  
    > [!IMPORTANT]
    > A seconda dell'abbonamento a Microsoft 365 o Office 365 di cui si dispone, potrebbero non essere visualizzati tutti i prodotti e i report illustrati qui. 
  
## <a name="interpret-the-skype-for-business-session-details-report"></a>Interpretare il report dettagli sessione di Skype for Business

Per avere una visione d'insieme dei dettagli della sessione Skype for Business dell'utente, è possibile visualizzare tutte le colonne visualizzate.
  
Questo è l'aspetto del report.
  
![Dashboard del report dettagli sessione di Skype for Business.](../images/3d87ab39-6eaa-46b5-b5f9-7f54dc987ae0.png)
  
***
![Numero 1](../images/sfbcallout1.png)<br/>**La ricerca utente per alias** consente di cercare un singolo utente e di visualizzare tutti i dettagli della sessione dell'utente nella tabella seguente. 
***
![Numero 2](../images/sfbcallout2.png)<br/>**Immettere la data e l'ora** in base alla data di inizio. È possibile usare il calendario per selezionare la data o immettervi manualmente. Questo campo deve essere popolato.
***
![Numero 3](../images/sfbcallout3.png)<br/>**Immettere alla data e ora** la data di fine. È possibile usare il calendario per selezionare la data o immettervi manualmente. Se non è impostata alcuna data di fine, il valore predefinito è 30 giorni dalla data di inizio.
***
![Numero 4](../images/sfbcallout4.png)<br/>La tabella mostra un'analisi di tutti i dettagli della sessione per ogni utente. Mostra tutti gli utenti a cui è assegnato Skype for Business e le informazioni sulla sessione. È possibile aggiungere/rimuovere colonne dalla tabella. <br/><br/>Per ogni sessione, la tabella contiene le colonne seguenti:
*    **L'ID** finestra di dialogo è l'ID per l'identificatore univoco della sessione SIP.
*    **La descrizione dei** tipi di elementi multimediali indica se la sessione è una conferenza telefonica o una sessione P2P e il tipo di supporto utilizzato (Condivisione audio/video/applicazione).
*    **L'ora** di inizio è l'ora di inizio della sessione.
*    **L'ora** di fine è l'ora di fine della sessione.
*    **Da URI è** l'URI dell'utente o del servizio che ha avviato la sessione. Potrebbe essere vuoto se l'utente ha avviato la sessione da un telefono PSTN.
*    **Per URI si** tratta dell'URI dell'utente o del servizio di destinazione dell'avvio della sessione. Nel caso della conferenza, si tratta dell'URI dell'organizzatore. Potrebbe essere vuoto se la destinazione della sessione è un numero di telefono PSTN.
*    **Dalla versione client** indica l'agente utente e la versione del client usati dall'utente o dal servizio che ha avviato la sessione.
*    **La versione client** indica l'agente utente e la versione del client usati dall'utente o dal servizio di destinazione dell'avvio della sessione.
*    **L'URL** conferenza è l'URL SIP della conferenza, se la sessione è stata una conferenza telefonica. Tutti gli utenti nella stessa conferenza telefonica avranno lo stesso URL conferenza. 
*    **Da Numero tel** è il numero di telefono di destinazione della sessione, se applicabile. Le ultime cifre del numero di telefono possono essere sostituite con "x" per proteggere la privacy degli utenti.
*    **A Numero Tel** è il numero di telefono di destinazione della sessione, se applicabile. Le ultime cifre del numero di telefono possono essere sostituite con "x" per proteggere la privacy degli utenti.
*    **Da ID endpoint** è un GUID univoco dell'endpoint usato dall'utente Da. Consente di identificare se l'utente comunica più sessioni dallo stesso endpoint. Può essere vuoto se l'utente usa un telefono PSTN o se la sessione è stata avviata da un servizio.
*    **L'ID endpoint** è un GUID univoco dell'endpoint usato dall'utente A. Consente di identificare se l'utente comunica più sessioni dallo stesso endpoint. Può essere vuoto se l'utente usa un telefono PSTN, se la sessione è stata avviata da un servizio o se la sessione non è stata stabilita.
*    **Istanza di** conferenza è un GUID univoco per l'istanza della conferenza che usa l'URL della conferenza. Le riunioni ricorrenti avranno lo stesso URL conferenza, ma ogni istanza della riunione avrà una differenza.
*    **Per conto dell'URI** è l'URI del delegante per conto del quale viene stabilita la sessione. <br/> **L'URI a cui fa riferimento l'URI** è l'URI dell'utente che ha definito l'origine di una sessione.
*    **Il codice di** risposta è il codice di risposta SIP per la connessione della sessione che indica se la sessione è stata stabilita correttamente.

Per ogni sessione è presente una tabella secondaria con dati diversi, a seconda dello scenario. Di seguito sono elencate le schede disponibili nella tabella secondaria per l'utente o i servizi Da e A.
*    La scheda SESSION mostra i dati relativi ai computer e ai sistemi operativi.
*    La scheda MEDIALINES mostra le informazioni sulla connettività di rete e sul dispositivo.
*    La scheda AUDIOSTREAMS mostra i dati sulle prestazioni di rete relativi ai flussi audio coinvolti nella sessione.
*    La scheda AUDIOCLIENTEVENTS mostra i dati sui problemi rilevati dal client che influiscono sull'esperienza audio.
*    La scheda AUDIOSIGNALS mostra i dati sull'elaborazione del segnale audio per la sessione.
*    La scheda APPSHARINGSTREAMS mostra i dati sulle prestazioni di rete relativi ai flussi di condivisione applicazioni o di condivisione desktop coinvolti nella sessione.
*    La scheda VIDEOCLIENTEVENTS mostra i dati sui problemi rilevati dal client che influiscono sull'esperienza video.
*    La scheda VIDEOSTREAMS mostra i dati sulle prestazioni di rete relativi ai flussi video coinvolti nella sessione.
*    La scheda TRACEROUTES mostra gli hop di rete raccolti tramite traceroute durante la sessione. Il percorso effettivo del supporto utilizzato per la sessione può variare e questi dati sono disponibili solo quando è presente l'audio nella sessione.
*    La scheda FEEDBACKREPORTS mostra i dati di fine del sondaggio forniti dagli utenti della sessione.
***
![Numero 5](../images/sfbcallout5.png)<br/>Fare clic per trascinare una colonna fino a **Per raggruppare per una specifica colonna, trascinare qui l'intestazione di colonna** se si desidera creare una visualizzazione che raggruppi tutti i dati in una o più colonne. 
***
![Numero 6](../images/sfbcallout6.png)<br/>È anche possibile esportare i dati del report in un file CSV di Excel toccando o facendo clic sul collegamento **Esporta in Excel**. <br/><br/> Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati.  
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Per consultare altri report di Skype for Business

- [Report attività in Skype for Business](activity-report.md) permette di vedere quanto gli utenti usano le conferenze peer-to-peer e organizzate o vi partecipano.
    
- [Skype per report di utilizzo del dispositivo Business](device-usage-report.md) permette di vedere i dispositivi, compresi i sistemi operativi e dispositivi mobili basati su Windows, in cui è installata l'app Skype for Business e che la utilizzano per messaggistica istantanea e riunioni.
    
- [Report attività organizzatore di conferenze in Skype for Business](conference-organizer-activity-report.md) permette di vedere quanto gli utenti organizzano conferenze che utilizzano messaggistica istantanea, audio/video, condivisione applicazioni, web, accesso esterno in ingresso/uscita di terze parti e accesso esterno in ingresso/uscita Microsoft.
    
- [Report attività partecipante di conferenze in Skype for Business](conference-participant-activity-report.md) È possibile visualizzare il numero di partecipanti a conferenze con messaggistica istantanea, audio/video, condivisione applicazioni, web e accesso esterno in ingresso/uscita.
    
- [Report attività peer-to-peer in Skype for Business](peer-to-peer-activity-report.md) - Permette di vedere quanto gli utenti usano messaggistica istantanea, audio/video, condivisione applicazioni e trasferimento di file.
    
- [Report di utilizzo PSTN di Skype for Business](pstn-usage-report.md) È possibile visualizzare il numero di minuti speso per le chiamate in entrata/in uscita e i costi per queste chiamate.

- [Skype per gli utenti aziendali bloccati report](users-blocked-report.md) - Permette di consultare gli utenti dell'organizzazione a cui è impedito effettuare chiamate.

- [I pool di minuti PSTN di Skype for Business riportano](pstn-minute-pools-report.md) il numero di minuti consumati durante il mese corrente all'interno dell'organizzazione.
    
## <a name="related-topics"></a>Argomenti correlati
[Report attività nell'interfaccia di amministrazione](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 
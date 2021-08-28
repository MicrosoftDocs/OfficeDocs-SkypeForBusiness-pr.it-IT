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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Reporting
description: Il dashboard Report mostra la panoramica delle attività in Microsoft 365 o Office 365 prodotti dell'organizzazione. Ti permette di approfondire le analisi fino al livello dei report dei singoli prodotti per una panoramica più dettagliata delle attività di ciascun prodotto.
ms.openlocfilehash: c369f93c126629673996aec44d1ce86f561c4947
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58592920"
---
# <a name="session-details-report"></a>Report dettagli della sessione.

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Il **dashboard Report** mostra la panoramica delle attività in Microsoft 365 o Office 365 prodotti dell'organizzazione. Ti permette di approfondire le analisi fino al livello dei report dei singoli prodotti per una panoramica più dettagliata delle attività di ciascun prodotto. Ad esempio, è possibile usare il report **Skype for Business dettagli della** sessione per visualizzare i dettagli sulle esperienze di chiamata dei singoli utenti.
  
Per altri [report disponibili,](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) vedere Panoramica dei report.
  
Questo report, insieme agli altri report Skype for Business report, consente di visualizzare dettagli sulle attività, inclusi i dettagli della sessione nell'intera organizzazione. Questi dettagli sono molto utili quando si analizzano, si pianificano e si prendono altre decisioni aziendali per l'organizzazione e per la configurazione dei [Crediti comunicazioni.](/microsoftteams/what-are-communications-credits)
  
> [!NOTE]
> È possibile visualizzare tutti i report Skype for Business quando si accede come amministratore al interfaccia di amministrazione di Microsoft 365. 
  
## <a name="how-to-get-to-the-skype-for-business-session-details-report"></a>Come accedere al report dettagli Skype for Business sessione

1. Passare all'interfaccia di amministrazione > **report**
    
2. Selezionare **Report** dal menu a sinistra e quindi fare clic su **Utilizzo.**
    
3. Nell'elenco in **Selezionare un report** fare clic Skype for Business dettagli della **sessione.**
    
    > [!TIP]
    > Se il report non è presente nell'elenco, passare Skype for Business dettagli della sessione **report nell'interfaccia**  >    >  **di amministrazione.** 
  
    > [!IMPORTANT]
    > A seconda dell'Microsoft 365 o Office 365 abbonamento, è possibile che non siano visualizzati tutti i prodotti e i report visualizzati. 
  
## <a name="interpret-the-skype-for-business-session-details-report"></a>Interpretare il report Skype for Business dettagli sessione

È possibile visualizzare i dettagli della sessione Skype for Business utente esaminando ognuna delle colonne visualizzate.
  
Questo è l'aspetto del report.
  
![Skype for Business Dashboard Report dettagli sessione.](../images/3d87ab39-6eaa-46b5-b5f9-7f54dc987ae0.png)
  
***
![Numero 1](../images/sfbcallout1.png)<br/>**La ricerca utente per alias** consente di cercare un singolo utente e di visualizzare tutti i dettagli della sessione dell'utente nella tabella seguente. 
***
![Numero 2](../images/sfbcallout2.png)<br/>**Immetti da data ora** consente di inserire la data di inizio. È possibile usare il calendario per selezionare la data o immettere la data manualmente. Questo campo deve essere popolato.
***
![Numero 3](../images/sfbcallout3.png)<br/>**Immettere l'ora di** data consente di inserire la data di fine. È possibile usare il calendario per selezionare la data o immettere la data manualmente. Se non è impostata alcuna data di fine, il valore predefinito è 30 giorni dalla data di inizio.
***
![Numero 4](../images/sfbcallout4.png)<br/>La tabella mostra una suddivisione di tutti i dettagli della sessione per utente. Mostra tutti gli utenti a cui sono Skype for Business e le relative informazioni sulla sessione. È possibile aggiungere/rimuovere colonne dalla tabella. <br/><br/>La tabella contiene le colonne seguenti per ogni sessione:
*    **ID finestra di** dialogo è l'ID per l'identificatore univoco della sessione SIP.
*    **La descrizione dei** tipi di elementi multimediali descrive se la sessione è una conferenza telefonica o una sessione P2P e il tipo di supporto usato (Audio/Video/Condivisione applicazioni).
*    **L'ora** di inizio è l'ora di avvio della sessione.
*    **L'ora** di fine è l'ora di fine della sessione.
*    **Da URI** è l'URI dell'utente o del servizio che ha avviato la sessione. Può essere vuoto se l'utente ha avviato la sessione da un telefono PSTN.
*    **Per URI** è l'URI dell'utente o del servizio che era la destinazione dell'avvio della sessione. Nel caso della conferenza, questo è l'URI dell'organizzatore. Può essere vuoto se l'obiettivo della sessione era un numero di telefono PSTN.
*    **Dalla versione client** indica l'Agente utente e la versione del client usata dall'utente o dal servizio che ha avviato la sessione.
*    **Alla versione client** indica l'Agente utente e la versione del client usata dall'utente o dal servizio che era la destinazione dell'avvio della sessione.
*    **URL conferenza** è l'URL SIP della conferenza, se la sessione era una conferenza telefonica. Tutti gli utenti della stessa conferenza telefonica avranno lo stesso URL conferenza. 
*    **Da Numero tel** è il numero di telefono che è stato l'obiettivo della sessione, se applicabile. Le ultime cifre del numero di telefono possono essere sostituite con "x" per proteggere la privacy degli utenti.
*    **Per Numero tel** è il numero di telefono che è stato l'obiettivo della sessione, se applicabile. Le ultime cifre del numero di telefono possono essere sostituite con "x" per proteggere la privacy degli utenti.
*    **Da ID endpoint** è un GUID univoco dell'endpoint usato dall'utente Da. Consente di identificare se l'utente sta comunicando più sessioni dallo stesso endpoint. Può essere vuoto se l'utente usa un telefono PSTN o se la sessione è stata avviata da un servizio.
*    **A ID endpoint** è un GUID univoco dell'endpoint usato dall'utente A. Consente di identificare se l'utente sta comunicando più sessioni dallo stesso endpoint. Può essere vuoto se l'utente usa un telefono PSTN, se la sessione è stata avviata da un servizio o se non è stato possibile stabilire una sessione.
*    **Istanza conf** è un GUID univoco per l'istanza della conferenza usando l'URL conferenza. Le riunioni ricorrenti avranno lo stesso URL conferenza, ma ogni istanza della riunione avrà una differenza con l'istanza conf.
*    **Per conto di URI** è l'URI del delegante per conto del quale viene stabilita la sessione. <br/> **Riferimento tramite URI è** l'URI dell'utente che ha fatto riferimento alla creazione di una sessione.
*    **Codice risposta** è il codice di risposta SIP per la creazione della sessione che indica se la sessione è stata stabilita correttamente.

Per ogni sessione è disponibile una tabella secondaria con dati diversi a seconda dello scenario. Di seguito sono elencate le schede disponibili nella tabella secondaria per l'utente o i servizi Da e A.
*    La scheda SESSION mostra i dati relativi ai computer e ai sistemi operativi.
*    La scheda MEDIALINES mostra le informazioni sulla connettività di rete e sul dispositivo.
*    La scheda AUDIOSTREAMS mostra i dati sulle prestazioni di rete relativi ai flussi audio coinvolti nella sessione.
*    La scheda AUDIOCLIENTEVENTS mostra i dati sui problemi rilevati dal client che influiscono sull'esperienza audio.
*    La scheda AUDIOSIGNALS mostra i dati sull'elaborazione del segnale audio per la sessione.
*    La scheda APPSHARINGSTREAMS mostra i dati sulle prestazioni di rete relativi ai flussi di condivisione applicazioni o desktop coinvolti nella sessione.
*    La scheda VIDEOCLIENTEVENTS mostra i dati sui problemi rilevati dal client che influiscono sull'esperienza video.
*    La scheda VIDEOSTREAMS mostra i dati sulle prestazioni di rete relativi ai flussi video coinvolti nella sessione.
*    La scheda TRACEROUTES mostra gli hop di rete raccolti tramite traceroute durante la sessione. Il percorso multimediale effettivo usato per la sessione può variare e questi dati sono disponibili solo quando nella sessione è presente l'audio.
*    La scheda FEEDBACKREPORTS mostra tutti i dati di fine del sondaggio di chiamata forniti dagli utenti nella sessione.
***
![Numero 5](../images/sfbcallout5.png)<br/>Fare clic per trascinare una colonna fino a **Per raggruppare per una specifica colonna, trascinare qui l'intestazione di colonna** se si desidera creare una visualizzazione che raggruppi tutti i dati in una o più colonne. 
***
![Numero 6](../images/sfbcallout6.png)<br/>È anche possibile esportare i dati del report in un file CSV di Excel toccando o facendo clic sul collegamento **Esporta in Excel**. <br/><br/> Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati.  
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Per consultare altri report di Skype for Business

- [Report attività in Skype for Business](activity-report.md) permette di vedere quanto gli utenti usano le conferenze peer-to-peer e organizzate o vi partecipano.
    
- [Skype per report di utilizzo del dispositivo Business](device-usage-report.md) permette di vedere i dispositivi, compresi i sistemi operativi e dispositivi mobili basati su Windows, in cui è installata l'app Skype for Business e che la utilizzano per messaggistica istantanea e riunioni.
    
- [Report attività organizzatore di conferenze in Skype for Business](conference-organizer-activity-report.md) permette di vedere quanto gli utenti organizzano conferenze che utilizzano messaggistica istantanea, audio/video, condivisione applicazioni, web, accesso esterno in ingresso/uscita di terze parti e accesso esterno in ingresso/uscita Microsoft.
    
- [Skype for Business attività dei partecipanti alla conferenza](conference-participant-activity-report.md) È possibile vedere il numero di conferenze di messaggistica istantanea, audio/video, condivisione di applicazioni, Web e conferenza telefonica con accesso esterno/esterno a cui si partecipa.
    
- [Report attività peer-to-peer in Skype for Business](peer-to-peer-activity-report.md) - Permette di vedere quanto gli utenti usano messaggistica istantanea, audio/video, condivisione applicazioni e trasferimento di file.
    
- [Skype for Business utilizzo PSTN](pstn-usage-report.md) È possibile visualizzare il numero di minuti trascorsi nelle chiamate in ingresso/in uscita e il costo per queste chiamate.

- [Skype per gli utenti aziendali bloccati report](users-blocked-report.md) - Permette di consultare gli utenti dell'organizzazione a cui è impedito effettuare chiamate.

- Skype for Business pool di minuti [PSTN](pstn-minute-pools-report.md) è possibile visualizzare il numero di minuti consumati durante il mese corrente all'interno dell'organizzazione.
    
## <a name="related-topics"></a>Argomenti correlati
[Report attività nell'interfaccia di amministrazione](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 

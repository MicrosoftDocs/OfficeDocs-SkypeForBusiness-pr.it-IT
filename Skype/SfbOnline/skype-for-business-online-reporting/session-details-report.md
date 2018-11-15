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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: '[] Il nuovo dashboard Report di Office 365 offre una panoramica delle attività su tutti i prodotti Office 365 nella propria organizzazione. Permette di approfondire le analisi fino al livello dei report dei singoli prodotti per un panorama più dettagliato delle attività di ciascun prodotto.'
ms.openlocfilehash: 33aa42ea7acd2f28ab0e27da85421071f948ca99
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2018
ms.locfileid: "26530551"
---
# <a name="session-details-report"></a>Report dettagli della sessione.

[] Il nuovo dashboard **Report** di Office 365 offre una panoramica delle attività su tutti i prodotti Office 365 nella propria organizzazione. Permette di approfondire le analisi fino al livello dei report dei singoli prodotti per un panorama più dettagliato delle attività di ciascun prodotto. Ad esempio, è possibile utilizzare report **Skype per Business dettagli** per visualizzare informazioni dettagliate sull'esperienza di chiamata dell'utente singolo.
  
Vedere [Panoramica dei report](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) per i report più disponibili.
  
La relazione, nonché altri Skype per i report di Business fornire informazioni dettagliate sull'attività all'interno dell'organizzazione, incluse informazioni dettagliate di sessione. Queste informazioni sono molto utili quando si analisi dei, pianificazione e l'esecuzione di altre business le decisioni per l'organizzazione e per la configurazione di [titoli di coda di comunicazioni](/microsoftteams/what-are-communications-credits).
  
> [!NOTE]
> È possibile visualizzare tutti i report di Skype for Business quando si accede come amministratori nell'interfaccia di amministrazione di Office 365. 
  
## <a name="how-to-get-to-the-skype-for-business-session-details-report"></a>Come ottenere Skype per rapporto Dettagli sessione Business

1. Vai al **Centro di amministrazione di Office 365** > **report**
    
2. Selezionare **report** dal menu a sinistra e quindi fare clic su **dati di utilizzo**.
    
3. Nell'elenco **Selezionare un report**, fare clic su **Skype per i dettagli di sessione Business**.
    
    > [!TIP]
    > Se non viene visualizzata in questo report elencato, andare a **Skype per Business admin center** > **report** > **Dettagli sessione**. 
  
    > [!IMPORTANT]
    > In base all'abbonamento a Office 365 di cui si dispone, alcuni dei prodotti e report illustrati in questo articolo potrebbero non essere disponibili. 
  
## <a name="interpret-the-skype-for-business-session-details-report"></a>Interpretazione Skype per rapporto Dettagli sessione Business

È possibile ottenere una visualizzazione in Skype dell'utente per i dettagli di sessione Business esaminando ognuna delle colonne visualizzate.
  
Questo è l'aspetto del report.
  
![Skype per dashboard rapporto Dettagli sessione Business.](../images/3d87ab39-6eaa-46b5-b5f9-7f54dc987ae0.png)
  
***
![Numero 1](../images/sfbcallout1.png)<br/>**Utente di ricerca da alias** consente di cercare un singolo utente e tutti i dettagli di sessione dell'utente viene visualizzato nella tabella seguente. 
***
![Numero 2](../images/sfbcallout2.png)<br/>**Invio da data ora** consente di che salvare la data di inizio. È possibile utilizzare il calendario per selezionare la data o immettere la data manualmente. In questo campo deve essere compilato.
***
![Numero 3](../images/sfbcallout3.png)<br/>**INVIO per data ora** consente di che salvare la data di fine. È possibile utilizzare il calendario per selezionare la data o immettere la data manualmente. Se non è impostata alcuna data di fine, il valore predefinito è 30 giorni dalla data di inizio.
***
![Numero 4](../images/sfbcallout4.png)<br/>La tabella mostra suddivisione di tutti i dettagli di sessioni per utente. Mostra tutti gli utenti che hanno Skype per le aziende assegnata e alle informazioni sulla sessione. È possibile aggiungere/rimuovere colonne dalla tabella. <br/><br/>La tabella include le colonne seguenti per ogni sessione:
*    **Finestra di dialogo ID** è l'ID dell'identificatore univoco della sessione SIP.
*    **Descrizione di tipi multimediali** descrive se la sessione è una conferenza telefonica o una sessione P2P e il tipo di supporto utilizzato (Audio/Video/Application Sharing).
*    **Ora di inizio** è l'ora di inizio della sessione.
*    **Ora di fine** è l'ora di fine della sessione.
*    **Dall'URI** è l'URI dell'utente o del servizio che ha avviato la sessione. Può essere vuota se l'utente ha avviato la sessione da un telefono PSTN.
*    **All'URI** è l'URI dell'utente o del servizio di destinazione dell'avvio della sessione. Nel caso di conferenza, si tratta URI dell'organizzatore. Può essere vuota se la destinazione della sessione è un numero di telefono PSTN.
*    **Dalla versione del client** viene illustrato l'agente utente e la versione del client utilizzato dall'utente o servizio che ha avviato la sessione.
*    **Versione client** viene illustrato l'agente utente e la versione del client utilizzato dall'utente o del servizio di destinazione dell'avvio della sessione.
*    **URL della conferenza** è l'URL SIP per la conferenza, se la sessione è stata una conferenza telefonica. Tutti gli utenti nella stessa conferenza telefonica avranno lo stesso URL di conferenza. 
*    **Numero da Tel** è il numero di telefono di destinazione della sessione, se applicabile. L'ultima cifre del numero di telefono possono essere sostituite con "x" per proteggere la riservatezza degli utenti.
*    **Numero di Tel** è il numero di telefono di destinazione della sessione, se applicabile. L'ultima cifre del numero di telefono possono essere sostituite con "x" per proteggere la riservatezza degli utenti.
*    **Dall'Id dell'Endpoint** è un GUID univoco dell'endpoint utilizzato dall'utente da. Consente di stabilire se l'utente comunica più sessioni da stesso endpoint. Può essere vuota se l'utente sta utilizzando un telefono PSTN o se la sessione è stata avviata da un servizio.
*    **Per Id dell'Endpoint** è un GUID univoco dell'endpoint dell'utente a. Consente di stabilire se l'utente comunica più sessioni da stesso endpoint. Può essere vuota se l'utente sta utilizzando un telefono PSTN, se la sessione è stata avviata da un servizio o una sessione non è riuscito a stabilire.
*    **Istanza conf** è un GUID univoco per l'istanza di conferenza utilizzando l'URL della conferenza. Riunioni ricorrenti avranno lo stesso URL di conferenza, ma ogni istanza della riunione avrà una differenza istanza Conf.
*    **Per conto di URI** è l'URI del delegante per conto del quale viene stabilita la sessione. <br/> **Definito dall'URI** è l'URI dell'utente che ha definito la creazione di una sessione.
*    **Codice di risposta** è il codice di risposta SIP per la determinazione della sessione che indica se la sessione è stata stabilita correttamente.

Per ogni sessione è disponibile a seconda dello scenario una tabella di sub con dati diversi. Di seguito sono elencati le schede disponibili nella tabella sub per il mittente e di utente o i servizi.
*    Scheda di sessione vengono visualizzati dati relativi al computer e i sistemi operativi.
*    Scheda MEDIALINES Mostra informazioni di connettività di rete e informazioni sul dispositivo.
*    Scheda AUDIOSTREAMS vengono illustrati dati sulle prestazioni di rete sui flussi audio per la sessione.
*    Scheda AUDIOCLIENTEVENTS Mostra dati relativi ai client rilevato incidono sulla qualità audio.
*    Scheda AUDIOSIGNALS Mostra i dati sull'elaborazione per la sessione del segnale audio.
*    Scheda APPSHARINGSTREAMS vengono illustrati dati sulle prestazioni di rete sulla condivisione di applicazioni o flussi di condivisione desktop per la sessione.
*    Scheda VIDEOCLIENTEVENTS Mostra dati relativi ai client rilevato incidono sull'esperienza video.
*    Scheda VIDEOSTREAMS vengono illustrati dati sulle prestazioni di rete sui flussi video per la sessione.
*    Scheda TRACEROUTE Mostra l'hop di rete raccolti da traceroute durante la sessione. Il percorso multimediale effettivo utilizzato per la sessione può variare e dati sono disponibili solo se è presente nella sessione audio.
*    Scheda FEEDBACKREPORTS Visualizza qualsiasi fine della chiamata i dati del sondaggio forniti dagli utenti nella sessione.
***
![Numero 5](../images/sfbcallout5.png)<br/>Fare clic per trascinare una colonna fino a **Per raggruppare per una specifica colonna, trascinare qui l'intestazione di colonna** se si desidera creare una visualizzazione che raggruppi tutti i dati in una o più colonne. 
***
![Numero 6](../images/sfbcallout6.png)<br/>È anche possibile esportare i dati del report in un file CSV di Excel toccando o facendo clic sul collegamento **Esporta in Excel**. <br/><br/> Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati.  
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Per consultare altri report di Skype for Business

- [Report attività in Skype for Business](activity-report.md) permette di vedere quanto gli utenti usano le conferenze peer-to-peer e organizzate o vi partecipano.
    
- [Skype per report di utilizzo del dispositivo Business](device-usage-report.md) permette di vedere i dispositivi, compresi i sistemi operativi e dispositivi mobili basati su Windows, in cui è installata l'app Skype for Business e che la utilizzano per messaggistica istantanea e riunioni.
    
- [Report attività organizzatore di conferenze in Skype for Business](conference-organizer-activity-report.md) permette di vedere quanto gli utenti organizzano conferenze che utilizzano messaggistica istantanea, audio/video, condivisione applicazioni, web, accesso esterno in ingresso/uscita di terze parti e accesso esterno in ingresso/uscita Microsoft.
    
- [Skype per rapporto attività partecipante di conferenza aziendali](conference-participant-activity-report.md) È possibile visualizzare il numero messaggistica immediata, audio/video, la condivisione delle applicazioni, Web e le conferenze telefoniche/esclusione conferenze sono viene ha partecipate.
    
- [Report attività peer-to-peer in Skype for Business](peer-to-peer-activity-report.md) - Permette di vedere quanto gli utenti usano messaggistica istantanea, audio/video, condivisione applicazioni e trasferimento di file.
    
- [Skype per i report di utilizzo PSTN Business](pstn-usage-report.md) È possibile visualizzare il numero di minuti, trascorso per le chiamate in ingresso/in uscita e dei costi per le chiamate.

- [Skype per gli utenti aziendali bloccati report](users-blocked-report.md) - Permette di consultare gli utenti dell'organizzazione a cui è impedito effettuare chiamate.

- [Skype per report pool minuto Business PSTN](pstn-minute-pools-report.md) è possibile visualizzare il numero di minuti utilizzati durante il mese corrente all'interno dell'organizzazione.
    
## <a name="related-topics"></a>Argomenti correlati
[Report attività nell'interfaccia di amministrazione di Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 
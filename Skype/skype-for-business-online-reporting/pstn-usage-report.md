---
title: Report di utilizzo PSTN
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 74eda791-c41f-4fd9-ae0b-913342e7ab04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Reporting
description: "Nuovo Skype per area Business Admin Center report mostra è chiamante e audio conferencing attività all'interno dell'organizzazione. Consente di penetrare nei rapporti per assegnare più granulare delle conoscenze sulle attività di ogni utente. Ad esempio, è possibile utilizzare Skype per report dettagli sull'utilizzo PSTN Business per visualizzare il numero di minuti, trascorso per le chiamate in ingresso/in uscita e dei costi per le chiamate. È possibile visualizzare i dettagli sull'utilizzo di Audio conferenza PSTN compreso il costo della chiamata in modo che è possibile acquisire familiarità con i dati di utilizzo e chiamare fatturazione dettagli per determinare l'utilizzo all'interno dell'organizzazione."
ms.openlocfilehash: 99a57109ca7e6fa1d9933174de7d5cf9209efdfc
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2017
---
# <a name="pstn-usage-report"></a>Report di utilizzo PSTN

Nuovo Skype per area Business Admin Center **report** Mostra è chiamante e audio conferencing attività all'interno dell'organizzazione. Consente di penetrare nei rapporti per assegnare più granulare delle conoscenze sulle attività di ogni utente. Ad esempio, è possibile utilizzare il rapporto **Skype per informazioni dettagliate sull'utilizzo PSTN Business** per visualizzare il numero di minuti, trascorso per le chiamate in ingresso/in uscita e dei costi per le chiamate. È possibile visualizzare i dettagli sull'utilizzo di Audio conferenza PSTN compreso il costo della chiamata in modo che è possibile acquisire familiarità con i dati di utilizzo e chiamare fatturazione dettagli per determinare l'utilizzo all'interno dell'organizzazione.
  
Consultare la [Panoramica dei report](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) per i report più disponibili.
  
La relazione, nonché altri Skype per i report di Business, offre informazioni dettagliate su attività inclusa la chiamata a utilizzo all'interno dell'organizzazione. Queste informazioni sono molto utili quando l'analisi dei, pianificazione e l'esecuzione di altre business le decisioni per l'organizzazione e per la configurazione di [comunicazioni titoli di coda](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md)
  
> [!NOTE]
> È possibile visualizzare tutti i report di Skype for Business quando si accede come amministratori nell'interfaccia di amministrazione di Office 365. 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-usage-details-report"></a>Come ottenere i report di utilizzo PSTN di Skype for Business

- Accedere **all'interfaccia di amministrazione di Office 365** > **Admin Center** > **Skype per Business admin center** > **report** > **dettagli sull'utilizzo PSTN**.
    
    > [!NOTE]
    > In base all'abbonamento a Office 365 di cui si dispone, alcuni dei prodotti e report illustrati in questo articolo potrebbero non essere disponibili. 
  
## <a name="interpret-the-skype-for-business-pstn-usage-report"></a>Interpretare il report di utilizzo PSTN di Skype for Business

È possibile consultare l'utilizzo di PSTN Skype for Business dei propri utenti leggendo le colonne visualizzate.
  
Questo è l'aspetto del report.
  
![Report di utilizzo PSTN di Skype for Business](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png)

***
![Numero 1](../images/sfbcallout1.png)<br/>La tabella illustra tutto l'utilizzo di PSTN suddiviso per utente. Mostra tutti gli utenti a cui è assegnato Skype for Business e il loro utilizzo di PSTN. È possibile aggiungere/rimuovere colonne dalla tabella.
*    **ID chiamata** è l'ID della chiamata. Si tratta di un identificativo univoco per la chiamata utilizzato quando si chiama l'assistenza Microsoft.
*    **ID utente** è il nome di accesso dell'utente.
*    **Numero di telefono** è il numero di telefono Skype for Business che ha ricevuto la chiamata (per le chiamate in entrata) o il numero chiamato (per le chiamate in uscita).
*    **Posizione utente** è il paese/area geografica in cui si trova l'utente.
*    **ID chiamante** è il numero di telefono del chiamante (ID chiamante) per le chiamate in entrata, oppure il numero o numero Skype for Business da cui è partita la chiamata per le chiamate in uscita.
*    **Tipo di chiamata** è se la chiamata è stata chiamata di una rete PSTN in uscita o in ingresso e il tipo di chiamata, ad esempio una chiamata effettuata da un utente o una conferenza telefonica. È possibile visualizzare i tipi di chiamata sono: 

     **Tipi di chiamata del Piano per chiamate** 
     *    **user_in** (l'utente ha ricevuto una chiamata PSTN in ingresso) 
     *    **user_out** (l'utente ha effettuato una chiamata PSTN in uscita) 
     *    **user_out_conf** (l'utente ha aggiunto 2 o più partecipanti PSTN alla chiamata, per esempio una conferenza a 3) 
     *    **user_out_transfer** (l'utente ha trasferito la chiamata a un numero PSTN) 
     *    **user_out_forwarding** (l'utente ha inoltrato la chiamata a un numero PSTN)

     **Tipi di chiamate Audioconferenze**
     *    **conf_in** (una chiamata in arrivo al bridge di conferenze Audio) 
     *    **conf_out** (chiamata in uscita dal bridge Audioconferenze, tipicamente per aggiungere un numero PSTN alla conferenza)

     **Applicazioni di comunicazioni unificate (UCAP)** 
     *    **ucap_in** (una chiamata in arrivo per l'applicazione di comunicazioni unificate, ad esempio coda chiamata o operatore automatico) 
     *    **ucap_out** (una chiamata in uscita dall'applicazione di comunicazioni unificate, ad esempio coda chiamata o operatore automatico)
*     
     **Nazionale/internazionale** indica se la chiamata effettuata è considerata nazionale (entro un Paese/area geografica) o internazionale (al di fuori di un Paese/area geografica) a seconda della posizione dell'utente. 
*    **Destinazione composto** è il nome della destinazione paese/area geografica composto, ad esempio Francia, Germania o degli Stati Uniti (Stati Uniti). 
*    **Tipo di numero** è il tipo di numero di telefono che ha origine dal numero di telefono dell'utente, un servizio o il numero verde.  
*    **Ora di inizio (UTC)** è l'ora in cui è stata iniziata o effettuata la chiamata. 
*    **Durata** è il tempo per cui resta connessa la chiamata.  
*    **ConfID** è l'ID conferenza dell'audioconferenza. 
*    **Addebito** è l'importo del costo della chiamata addebitato sull'account. 
*    **Valuta** è il tipo di valuta usato per calcolare il costo della chiamata. 
*    **Capacità** è la licenza usata per la chiamata. I tipi di licenza disponibili sono i seguenti. 
     *    **MCOPSTNPP** - Communications titoli di coda <br/> **MCOPSTN1** - chiamata pianificare nazionale (min 3000 US / min 1200 UE piani) 
     *    **MCOPSTN2** - piano chiamate internazionali 
     *    **MCOPSTN5** - nazionale chiamata Plan (piano chiamante min 120) 
     *    **MCOMEETADD** - audioconferenze con accesso esterno
     *    **MCOMEETACPEA** - retributive Per minuto audioconferenze con accesso esterno 
***
![Numero 2](../images/sfbcallout2.png)<br/>Fare clic per trascinare una colonna fino a **Per raggruppare per una specifica colonna, trascinare qui l'intestazione di colonna** se si desidera creare una visualizzazione che raggruppi tutti i dati in una o più colonne.
 ***
![Numero 3](../images/sfbcallout3.png)<br/>È anche possibile esportare i dati del report in un file CSV di Excel toccando o facendo clic sul collegamento **Esporta in Excel**. <br/><br/> Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati.
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Per consultare altri report di Skype for Business

- [Report attività in Skype for Business](activity-report.md) permette di vedere quanto gli utenti usano le conferenze peer-to-peer e organizzate o vi partecipano.
    
- [Skype per report di utilizzo del dispositivo Business](device-usage-report.md) permette di vedere i dispositivi, compresi i sistemi operativi e dispositivi mobili basati su Windows, in cui è installata l'app Skype for Business e che la utilizzano per messaggistica istantanea e riunioni.
    
- [Skype per rapporto attività di organizzatore della conferenza aziendali](conference-organizer-activity-report.md) È possibile visualizzare quanto gli utenti sono organizzare conferenze che utilizzano la messaggistica immediata, audio/video, condivisione di applicazioni, Web, /dial le parti - 3rd e /dial out - Microsoft.
    
- [Skype per rapporto attività partecipante di conferenza aziendali](conference-participant-activity-report.md) È possibile visualizzare il numero messaggistica immediata, audio/video, la condivisione delle applicazioni, server Web e chiamate in uscita audioconferenze sono viene ha partecipati.
    
- [Report attività peer-to-peer in Skype for Business](peer-to-peer-activity-report.md) - Permette di vedere quanto gli utenti usano messaggistica istantanea, audio/video, condivisione applicazioni e trasferimento di file.
    
- [Skype per gli utenti aziendali bloccati report](users-blocked-report.md) - Permette di consultare gli utenti dell'organizzazione a cui è impedito effettuare chiamate.

- [Skype per report pool minuto Business PSTN](pstn-minute-pools-report.md) è possibile visualizzare il numero di minuti utilizzati durante il mese corrente all'interno dell'organizzazione.

- [Skype per rapporto Dettagli sessione Business](session-details-report.md) È possibile visualizzare informazioni dettagliate sull'esperienza di chiamata dell'utente singolo.
    
## <a name="related-topics"></a>Argomenti correlati
[Report attività nell'interfaccia di amministrazione di Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  


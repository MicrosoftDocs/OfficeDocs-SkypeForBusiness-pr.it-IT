---
title: "Report di utilizzo PSTN di Skype for Business"
ms.author: tonysmit
author: tonysmit
ms.date: 11/24/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 74eda791-c41f-4fd9-ae0b-913342e7ab04
description: "Nuovo Skype per Business Admin Center report area Mostra si chiamate audio e video conferenze attività all'interno dell'organizzazione. Consente di drill-down dei report per consente di comprendere meglio relativi alle attività di ogni utente. Ad esempio, è possibile utilizzare il report di Skype per Business PSTN dettagli per visualizzare il numero di minuti trascorso in chiamate in ingresso/uscita e dei costi per le chiamate. È possibile visualizzare dettagli sull'utilizzo di Audio i servizi di conferenza PSTN inclusi il costo della chiamata, in modo da poter comprendere l'utilizzo e chiamare i dettagli di fatturazione per determinare l'utilizzo all'interno dell'organizzazione."
---

# Report di utilizzo PSTN di Skype for Business

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la dichiarazione di non responsabilità.  
  
Nuovo Skype per Business Admin Center **report** area Mostra si chiamate audio e video conferenze attività all'interno dell'organizzazione. Consente di drill-down dei report per consente di comprendere meglio relativi alle attività di ogni utente. Ad esempio, è possibile utilizzare il report di **Skype per Business PSTN dettagli** per visualizzare il numero di minuti trascorso in chiamate in ingresso/uscita e dei costi per le chiamate. È possibile visualizzare dettagli sull'utilizzo di Audio i servizi di conferenza PSTN inclusi il costo della chiamata, in modo da poter comprendere l'utilizzo e chiamare i dettagli di fatturazione per determinare l'utilizzo all'interno dell'organizzazione.
  
 Consultare[Report attività nell'interfaccia di amministrazione di Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) per scoprire quali altri report sono disponibili.
  
Questo report insieme altri Skype per i report di Business per ottenere informazioni dettagliate sull'attività, inclusa la chiamata all'uso in tutta l'organizzazione. Questi dettagli sono molto utili quando si analisi, pianificazione e la creazione di altre aziende decisioni per l'organizzazione e per configurare [Cosa sono i Crediti comunicazioni?](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md).
  
> [!NOTE]
> È possibile visualizzare tutti i report di Skype for Business quando si accede come amministratori nell'interfaccia di amministrazione di Office 365. 
  
## Come ottenere i report di utilizzo PSTN di Skype for Business

1. Passare all'interfaccia **di amministrazione di Office 365** > fare clic su **amministratore Centra** > quindi fare clic su **Skype for Business Admin Center**
    
2. Dall'interfaccia di amministrazione Skype for Business, seleziona **Report** dal menu a sinistra, poi fai clic su **Dettagli utilizzo PSTN**.
    
    > [!NOTE]
    > In base all'abbonamento a Office 365 di cui si dispone, alcuni dei prodotti e report illustrati in questo articolo potrebbero non essere disponibili. 
  
## Interpretare il report di utilizzo PSTN di Skype for Business

È possibile consultare l'utilizzo di PSTN Skype for Business dei propri utenti leggendo le colonne visualizzate.
  
Questo è l'aspetto del report.
  
![Skype for Business PSTN usage report.](../images/d3fee22a-a163-45c5-921a-45191288e0c8.png)
  
## 

|||
|:-----|:-----|
|**1** <br/> | La tabella illustra tutto l'utilizzo di PSTN suddiviso per utente. Mostra tutti gli utenti a cui è assegnato Skype for Business e il loro utilizzo di PSTN. È possibile aggiungere/rimuovere colonne dalla tabella. <br/> **ID chiamata** è l'ID della chiamata. Si tratta di un identificativo univoco per la chiamata utilizzato quando si chiama l'assistenza Microsoft. <br/> **ID utente** è il nome di accesso dell'utente. <br/> **Numero di telefono** è il numero di telefono Skype for Business che ha ricevuto la chiamata (per le chiamate in entrata) o il numero chiamato (per le chiamate in uscita). <br/> **Percorso utente** è il paese/area geografica in cui l'utente si trova. <br/> **ID chiamante** è il numero di telefono del chiamante (ID chiamante) per le chiamate in entrata, oppure il numero o numero Skype for Business da cui è partita la chiamata per le chiamate in uscita. <br/> **Tipo di chiamata** è se la chiamata è stata chiamata una PSTN in uscita o posta in arrivo e il tipo di chiamata, ad esempio una chiamata collocati da un utente o una conferenza audio. I tipi di chiamata che venga visualizzato sono: <br/> **Tipi di chiamata del Piano per chiamate** <br/> **user_in** (l'utente ha ricevuto una chiamata PSTN in ingresso) <br/> **﻿user_out** (l'utente ha effettuato una chiamata PSTN in uscita) <br/> **﻿user_out_conf** (l'utente ha aggiunto 2 o più partecipanti PSTN alla chiamata, per esempio una conferenza a 3) <br/> **﻿user_out_transfer** (l'utente ha trasferito la chiamata a un numero PSTN) <br/> **user_out_forwarding** (l'utente ha inoltrato la chiamata a un numero PSTN) <br/> **Tipi di chiamate Audioconferenze** <br/> **conf_in** (una chiamata in ingresso al bridge di conferenze Audio) <br/> **﻿conf_out** (chiamata in uscita dal bridge Audioconferenze, tipicamente per aggiungere un numero PSTN alla conferenza) <br/>  ﻿UCAP (Unified Communication Applications) <br/> **ucap_in** (una chiamata in ingresso all'applicazione di comunicazioni unificate, ad esempio coda di chiamata o all'operatore automatico) <br/> **ucap_out** (una chiamata in uscita dall'applicazione di comunicazioni unificate, ad esempio coda di chiamata o all'operatore automatico) <br/> **Nazionale/internazionale** indica se la chiamata effettuata è considerata nazionale (entro un Paese/area geografica) o internazionale (al di fuori di un Paese/area geografica) a seconda della posizione dell'utente. <br/> **Destinazione composto** è il nome della destinazione paese/area geografica da comporre, ad esempio Francia, Germania o negli Stati Uniti (Stati Uniti). <br/> **Tipo di numero** è il tipo di numero di telefono, per esempio il numero di telefono di un utente, un numero di assistenza o un numero verde. <br/> **Ora di inizio (UTC)** è l'ora in cui è stata iniziata o effettuata la chiamata. <br/> **Durata** è il tempo per cui resta connessa la chiamata. <br/> **ConfID** è l'ID conferenza dell'audioconferenza. <br/> **Addebito** è l'importo del costo della chiamata addebitato sull'account. <br/> **Valuta** è il tipo di valuta usato per calcolare il costo della chiamata. <br/> **Capacità** è la licenza usata per la chiamata. I tipi di licenza disponibili sono i seguenti. <br/> **MCOPSTNPP** - crediti comunicazioni <br/> **MCOPSTN1** - chiamate nazionali pianificare (min 3000 US / min 1200 UE plan di messaggistica unificata) <br/> **MCOPSTN2** - piano internazionali <br/> **MCOPSTN5** - nazionali chiamata piano (piano tariffario 120 min) <br/> **MCOMEETADD** - audioconferenza <br/> **MCOMEETACPEA** - per ciascun audioconferenza minuto <br/> |
|**2** <br/> |Fare clic per trascinare una colonna fino a **Per raggruppare per una specifica colonna, trascinare qui l'intestazione di colonna** se si desidera creare una visualizzazione che raggruppi tutti i dati in una o più colonne. <br/> |
|**3** <br/> |È anche possibile esportare i dati del report in un file CSV di Excel toccando o facendo clic sul collegamento **Esporta in Excel**.  <br/> Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati.  <br/> |
   
## Per consultare altri report di Skype for Business

- [Report attività in Skype for Business](skype-for-business-activity-report.md) permette di vedere quanto gli utenti usano le conferenze peer-to-peer e organizzate o vi partecipano.
    
- [Skype per report di utilizzo del dispositivo Business](skype-for-business-device-usage-report.md) permette di vedere i dispositivi, compresi i sistemi operativi e dispositivi mobili basati su Windows, in cui è installata l'app Skype for Business e che la utilizzano per messaggistica istantanea e riunioni.
    
- [Report attività organizzatore di conferenze in Skype for Business](skype-for-business-conference-organizer-activity-report.md) È possibile vedere quanto gli utenti sono organizzare conferenze che utilizzano messaggistica Istantanea, audio/video, la condivisione di applicazioni, Web, /dial le parti - 3 e /dial: Microsoft.
    
- [Report attività partecipante di conferenze in Skype for Business](skype-for-business-conference-participant-activity-report.md) È possibile vedere quante messaggistica Istantanea, audio/video, la condivisione delle applicazioni, Web e chiamate in uscita audioconferenze sono vengano partecipati.
    
- [Report attività peer-to-peer in Skype for Business](skype-for-business-peer-to-peer-activity-report.md) - Permette di vedere quanto gli utenti usano messaggistica istantanea, audio/video, condivisione applicazioni e trasferimento di file.
    
- [Skype per gli utenti aziendali bloccati report](skype-for-business-users-blocked-report.md) - Permette di consultare gli utenti dell'organizzazione a cui è impedito effettuare chiamate.
    
- [Skype per gli utenti aziendali bloccati report](skype-for-business-users-blocked-report.md) mostra i dettagli del supporto usato, della durata della sessione, del client usato e dell'URL di conferenza.
    
## Argomenti correlati

[Report attività nell'interfaccia di amministrazione di Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  


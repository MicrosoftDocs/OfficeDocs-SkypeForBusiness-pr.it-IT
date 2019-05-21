---
title: Report di utilizzo PSTN
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 74eda791-c41f-4fd9-ae0b-913342e7ab04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: La nuova area report dell'interfaccia di amministrazione di Skype for business Mostra la chiamata e l'attività di conferenza audio nell'organizzazione. Permette di approfondire le analisi fino al livello dei report per un panorama più dettagliato delle attività di ciascun utente. Ad esempio, con il report Dettagli di utilizzo PSTN Skype for Business è possibile consultare il numero di minuti delle chiamate in entrata e in uscita e i costi di quelle chiamate. È possibile visualizzare i dettagli di utilizzo PSTN dei servizi di audioconferenza, incluso il costo della chiamata, in modo da poter comprendere l'utilizzo e chiamare i dettagli di fatturazione per determinare l'utilizzo all'interno dell'organizzazione.
ms.openlocfilehash: e1753915753c110a615edb108b2ff98efe237aa6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287724"
---
# <a name="pstn-usage-report"></a>Report di utilizzo PSTN

La nuova area **report** dell'interfaccia di amministrazione di Skype for business Mostra la chiamata e l'attività di conferenza audio nell'organizzazione. Permette di approfondire le analisi fino al livello dei report per un panorama più dettagliato delle attività di ciascun utente. Ad esempio, con il report **Dettagli di utilizzo PSTN Skype for Business** è possibile consultare il numero di minuti delle chiamate in entrata e in uscita e i costi di quelle chiamate. È possibile visualizzare i dettagli di utilizzo PSTN dei servizi di audioconferenza, incluso il costo della chiamata, in modo da poter comprendere l'utilizzo e chiamare i dettagli di fatturazione per determinare l'utilizzo all'interno dell'organizzazione.
  
Vedere la [Panoramica dei report](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) per altri report disponibili.
  
Questo report, insieme agli altri report di Skype for business, fornisce informazioni dettagliate sull'attività, incluso l'uso delle chiamate nell'organizzazione. Questi dettagli sono molto utili per l'analisi, la pianificazione e l'esecuzione di altre decisioni aziendali per l'organizzazione e per la configurazione dei crediti per le [comunicazioni](/microsoftteams/what-are-communications-credits)
  
> [!NOTE]
> I report sono disponibili quando si accede a Skype for Business come amministratore dall'interfaccia di amministrazione di Office 365. 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-usage-details-report"></a>Come ottenere i report di utilizzo PSTN di Skype for Business

![SFB-logo-30x30. png](../images/sfb-logo-30x30.png) **con l'interfaccia di amministrazione di Skype for business**

- Accedere all'interfaccia di amministrazione di **Office 365** > **** > per gli amministratori dell'interfaccia di amministrazione di**Skype for business** > per i**report** > di**utilizzo PSTN**.
    
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
*    La **posizione dell'utente** è il paese/area geografica in cui si trova l'utente.
*    **ID chiamante** è il numero di telefono del chiamante (ID chiamante) per le chiamate in entrata, oppure il numero o numero Skype for Business da cui è partita la chiamata per le chiamate in uscita.
*    **Tipo di chiamata** indica se la chiamata è stata una chiamata in uscita o in arrivo PSTN e il tipo di chiamata, ad esempio una chiamata effettuata da un utente o da una conferenza audio. Questi sono i tipi di chiamata visualizzati. 

     **Tipi di chiamata del Piano per chiamate** 
     *    **user_in** (l'utente ha ricevuto una chiamata PSTN in ingresso) 
     *    **user_out** (l'utente ha effettuato una chiamata PSTN in uscita) 
     *    **user_out_conf** (l'utente ha aggiunto 2 o più partecipanti PSTN alla chiamata, per esempio una conferenza a 3) 
     *    **user_out_transfer** (l'utente ha trasferito la chiamata a un numero PSTN) 
     *    **user_out_forwarding** (l'utente ha inoltrato la chiamata a un numero PSTN)

     **Tipi di chiamate Audioconferenze**
     *    **conf_in** (una chiamata in entrata per il Bridge di audioconferenza) 
     *    **conf_out** (chiamata in uscita dal bridge Audioconferenze, tipicamente per aggiungere un numero PSTN alla conferenza)

     **UCAP (Unified Communication Applications)** 
     *    **ucap_in** (chiamata PSTN in ingresso per l'applicazione UC, ad esempio operatore automatico o coda di chiamata) 
     *    **ucap_out** (chiamata PSTN in uscita dall'applicazione UC, ad esempio operatore automatico o coda di chiamata)
     *    **Nota:** Le chiamate trasferite a un utente dall'applicazione UC, ad esempio un operatore automatico o una coda di chiamata, non verranno visualizzate nel report utilizzo PSTN, poiché questi piedini di chiamata sono chiamate audio peer-to-peer (P2P). È possibile accedere alle chiamate P2P nell'interfaccia di amministrazione di Skype for business in "strumenti > Skype for business call Analytics" e cercare in base al nome utente o all'indirizzo SIP correlando la chiamata per data/ora e/o CLID di origine (ID linea chiamante). 
*     
     **Nazionale/internazionale** indica se la chiamata effettuata è considerata nazionale (entro un Paese/area geografica) o internazionale (al di fuori di un Paese/area geografica) a seconda della posizione dell'utente. 
*    **Destinazione chiamata** è il nome della destinazione paese/area geografica chiamata, ad esempio Francia, Germania o Stati Uniti (USA). 
*    **Tipo di numero** è il tipo di numero di telefono proveniente dal numero di telefono di un utente, un servizio o un numero verde.  
*    **Ora di inizio (UTC)** è l'ora in cui è stata iniziata o effettuata la chiamata. 
*    **Durata** è il tempo per cui resta connessa la chiamata.  
*    **ConfID** è l'ID conferenza dell'audioconferenza. 
*    **Addebito** è l'importo del costo della chiamata addebitato sull'account. 
*    **Valuta** è il tipo di valuta usato per calcolare il costo della chiamata. 
*    **Capacità** è la licenza usata per la chiamata. I tipi di licenza disponibili sono i seguenti. 
     *    **MCOPSTNPP** -Credits comunicazioni <br/> **MCOPSTN1** -piano per chiamate nazionali (3000 min US/1200 min eu plans) 
     *    **MCOPSTN2** -piano per chiamate internazionali 
     *    **MCOPSTN5** -piano per chiamate nazionali (piano per chiamate 120 min) 
     *    **MCOPSTN6** -piano per chiamate nazionali (240 min Calling Plan) Nota: disponibilità limitata
     *    **MCOMEETADD** -audioconferenza
     *    **MCOMEETACPEA** -pay per minute audioconferenza
> [!NOTE]
> Se si vuole eseguire un report per includere solo le chiamate pay per minute che non sono incluse nell'abbonamento a una chiamata o a una conferenza, filtrare il report con la funzionalità "MCOPSTNPP". In questo modo verrà fornito un elemento per tutte le chiamate pay per minute.  Per i servizi di conferenza audio pay per minute, filtrare per "MCOMEETACPEA" invece di "MCOPSTNPP".  
***
> [!NOTE]
> In alcuni campi potrebbe essere visualizzato anche "Nessun dato". "Nessun dato" indica che il campo non è applicabile al tipo o alla funzionalità di chiamata. 
***
> [!NOTE]
> Se si dispone di un piano per chiamate Telstra, non verranno visualizzati record dettagli chiamata nel report utilizzo PSTN. Contattare Telstra per le esigenze di Reporting. 
***
![Numero 2](../images/sfbcallout2.png)<br/>Fare clic per trascinare una colonna fino a **Per raggruppare per una specifica colonna, trascinare qui l'intestazione di colonna** se si desidera creare una visualizzazione che raggruppi tutti i dati in una o più colonne.
 ***
![Numero 3](../images/sfbcallout3.png)<br/>È anche possibile esportare i dati del report in un file di Excel delimitato da TABULAzioni, facendo clic o toccando il pulsante **Esporta in Excel** . <br/><br/> Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. 
    > [!Note] 
    > Despite the export file named as .CSV (which implies a comma delimited export), as there may be commas in the data set, the file is actually delimited with **TABS** and not **COMMAS**.

## <a name="want-to-see-other-skype-for-business-reports"></a>Per consultare altri report di Skype for Business

- [Report attività in Skype for Business](activity-report.md) permette di vedere quanto gli utenti usano le conferenze peer-to-peer e organizzate o vi partecipano.
    
- [Skype per report di utilizzo del dispositivo Business](device-usage-report.md) permette di vedere i dispositivi, compresi i sistemi operativi e dispositivi mobili basati su Windows, in cui è installata l'app Skype for Business e che la utilizzano per messaggistica istantanea e riunioni.
    
- [Report attività organizzatore di conferenze di Skype for business](conference-organizer-activity-report.md) Puoi vedere quanto gli utenti organizzano conferenze che usano messaggistica istantanea, audio/video, condivisione applicazioni, Web,/dial out-3rd party e/dial out-Microsoft.
    
- [Report attività partecipante di conferenze di Skype for business](conference-participant-activity-report.md) È possibile vedere il numero di partecipazioni a conferenze audio, audio/video, condivisione applicazioni, Web e dial-out.
    
- [Report attività peer-to-peer in Skype for Business](peer-to-peer-activity-report.md) - Permette di vedere quanto gli utenti usano messaggistica istantanea, audio/video, condivisione applicazioni e trasferimento di file.
    
- [Skype per gli utenti aziendali bloccati report](users-blocked-report.md) - Permette di consultare gli utenti dell'organizzazione a cui è impedito effettuare chiamate.

- [Report pool di minuti PSTN di Skype for business](pstn-minute-pools-report.md) è possibile visualizzare il numero di minuti consumati durante il mese corrente all'interno dell'organizzazione.

- [Report Dettagli sessione di Skype for business](session-details-report.md) È possibile visualizzare i dettagli sulle singole esperienze delle chiamate degli utenti.
    
## <a name="related-topics"></a>Argomenti correlati
[Report attività nell'interfaccia di amministrazione di Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  
  
 

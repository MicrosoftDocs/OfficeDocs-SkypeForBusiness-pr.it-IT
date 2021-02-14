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
f1.keywords:
- NOCSH
ms.custom:
- Reporting
description: La nuova area report dell'interfaccia di amministrazione di Skype for Business mostra le attività di chiamata e audioconferenza all'interno dell'organizzazione. Permette di approfondire le analisi fino al livello dei report per un panorama più dettagliato delle attività di ciascun utente. Ad esempio, con il report Dettagli di utilizzo PSTN Skype for Business è possibile consultare il numero di minuti delle chiamate in entrata e in uscita e i costi di quelle chiamate. È possibile visualizzare i dettagli di utilizzo di PSTN per i servizi di audioconferenza, compreso il costo della chiamata, in modo da poter comprendere i dati di utilizzo e di fatturazione delle chiamate per determinare l'utilizzo all'interno dell'organizzazione.
ms.openlocfilehash: 09d372f6526d14a65e878271a1b277fc19d7d3e4
ms.sourcegitcommit: bdf6cea0face74809ad3b8b935bc14ad60b3bb35
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "45201170"
---
# <a name="pstn-usage-report"></a>Report di utilizzo PSTN

La nuova area report  dell'interfaccia di amministrazione di Skype for Business mostra le attività di chiamata e audioconferenza all'interno dell'organizzazione. Permette di approfondire le analisi fino al livello dei report per un panorama più dettagliato delle attività di ciascun utente. Ad esempio, con il report **Dettagli di utilizzo PSTN Skype for Business** è possibile consultare il numero di minuti delle chiamate in entrata e in uscita e i costi di quelle chiamate. È possibile visualizzare i dettagli di utilizzo di PSTN per i servizi di audioconferenza, compreso il costo della chiamata, in modo da poter comprendere i dati di utilizzo e di fatturazione delle chiamate per determinare l'utilizzo all'interno dell'organizzazione.
  
Per altri [report disponibili,](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) vedere la panoramica dei report.
  
Questo report, insieme agli altri rapporti di Skype for Business, offre dettagli sull'attività, compreso l'utilizzo delle chiamate in tutta l'organizzazione. Questi dettagli sono molto utili per indagare, pianificare e prendere altre decisioni aziendali per l'organizzazione e per la configurazione dei [Crediti comunicazioni.](/microsoftteams/what-are-communications-credits)
  
> [!NOTE]
> Puoi visualizzare tutti i rapporti di Skype for Business quando accedi come amministratore all'interfaccia di amministrazione di Microsoft 365. 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-usage-details-report"></a>Come ottenere i report di utilizzo PSTN di Skype for Business

![Icona che mostra il logo di Skype for Business](../images/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**

- Accedi all'interfaccia di amministrazione e > **di**  >  **amministrazione Skype for Business** segnala i  >  **dettagli di** utilizzo di  >  **PSTN.**
    
    > [!NOTE]
    > A seconda dell'abbonamento a Microsoft 365 o Office 365 di cui si dispone, potrebbero non essere visualizzati tutti i prodotti e i report illustrati qui.
  
## <a name="interpret-the-skype-for-business-pstn-usage-report"></a>Interpretare il report di utilizzo PSTN di Skype for Business

È possibile consultare l'utilizzo di PSTN Skype for Business dei propri utenti leggendo le colonne visualizzate.
  
Questo è l'aspetto del report.
  
[![Report di utilizzo PSTN di Skype for Business ](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png)](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png#lightbox)

***
![Numero 1](../images/sfbcallout1.png)<br/>La tabella illustra tutto l'utilizzo di PSTN suddiviso per utente. Mostra tutti gli utenti a cui è assegnato Skype for Business e il loro utilizzo di PSTN. È possibile aggiungere/rimuovere colonne dalla tabella.
*    **ID chiamata** è l'ID della chiamata. Si tratta di un identificatore della chiamata utilizzato quando si chiama il supporto tecnico Microsoft.
*    **ID utente** è il nome di accesso dell'utente.
*    **Numero di telefono** è il numero di telefono Skype for Business che ha ricevuto la chiamata (per le chiamate in entrata) o il numero chiamato (per le chiamate in uscita).
*    **La località dell'utente** è il paese/area geografica in cui si trova l'utente.
*    **ID chiamante** è il numero di telefono del chiamante (ID chiamante) per le chiamate in entrata, oppure il numero o numero Skype for Business da cui è partita la chiamata per le chiamate in uscita.
*    **Il tipo di** chiamata è se la chiamata PSTN era in uscita o in arrivo e il tipo di chiamata, ad esempio una chiamata effettuato da un utente o un'audioconferenza. Questi sono i tipi di chiamata visualizzati. 

     **Tipi di chiamata del Piano per chiamate** 
     *    **user_in** (l'utente ha ricevuto una chiamata PSTN in ingresso) 
     *    **user_out** (l'utente ha effettuato una chiamata PSTN in uscita) 
     *    **user_out_conf** (l'utente ha aggiunto 2 o più partecipanti PSTN alla chiamata, per esempio una conferenza a 3) 
     *    **user_out_transfer** (l'utente ha trasferito la chiamata a un numero PSTN) 
     *    **user_out_forwarding** (l'utente ha inoltrato la chiamata a un numero PSTN)

     **Tipi di chiamate Audioconferenze**
     *    **conf_in** (chiamata in ingresso al bridge audioconferenza). Per i record di questo tipo di chiamata, l'utente specificato nella colonna **ID utente** corrisponde all'organizzatore della riunione.
     *    **conf_out** (chiamata in uscita dal bridge audioconferenza, in genere per aggiungere un numero PSTN alla conferenza). Per i record di questo tipo di chiamata, l'utente specificato nella colonna **ID utente** corrisponde all'organizzatore della riunione.

     **UCAP (Unified Communication Applications)** 
     *    **ucap_in** (chiamata PSTN in ingresso all'applicazione UC, come un operatore automatico o una coda di chiamata) 
     *    **ucap_out** (una chiamata PSTN in uscita dall'applicazione UC, come un operatore automatico o una coda di chiamata)
         > [!NOTE]
         > Le chiamate trasferite a un utente dall'applicazione UC, ad esempio un operatore automatico o una coda di chiamata, non compariranno nel report di utilizzo PSTN, in quanto queste richieste di chiamata sono chiamate audio peer-to-peer (P2P). È possibile accedere alle chiamate P2P nell'interfaccia di amministrazione di Skype for Business in "Strumenti > Skype for Business Call Analytics" e cercare per nome utente o indirizzo SIP correlati alla chiamata per data/ora e/o ID riga di chiamata. 

     **Nazionale/internazionale** indica se la chiamata effettuata è considerata nazionale (entro un Paese/area geografica) o internazionale (al di fuori di un Paese/area geografica) a seconda della posizione dell'utente. 
*    **Destinazione chiamata è** il nome del paese o dell'area geografica chiamata, ad esempio Francia, Germania o Stati Uniti (USA). 
*    **Il tipo** di numero è il tipo di numero di telefono che deriva dal numero di telefono di un utente, da un numero di servizio o numero verde.  
*    **Ora di inizio (UTC)** è l'ora in cui è stata iniziata o effettuata la chiamata. 
*    **Durata** è il tempo per cui resta connessa la chiamata.  
*    **ConfID** è l'ID conferenza dell'audioconferenza. 
*    **Addebito** è l'importo del costo della chiamata addebitato sull'account. 
*    **Valuta** è il tipo di valuta usato per calcolare il costo della chiamata. 
*    **Capacità** è la licenza usata per la chiamata. I tipi di licenza disponibili sono i seguenti. 
     *    **MCOPSTNPP** - Crediti comunicazioni <br/> **MCOPSTN1** - Piano per chiamate nazionali (piani DA 3000 min USA /1200 min UE) 
     *    **MCOPSTN2** - Piano per chiamate internazionali 
     *    **MCOPSTN5** - Piano per chiamate nazionali (piano da 120 min) 
     *    **MCOPSTN6** - Piano per chiamate nazionali (piano per chiamate da 240 min) Nota: disponibilità limitata
     *    **MCOMEETADD** - Audioconferenza
     *    **MCOMEETACPEA** - Audioconferenza con pagamento al minuto
     
> [!NOTE]
> Se si desidera eseguire un report per includere solo chiamate con pagamento al minuto non incluse nell'abbonamento alle chiamate o alle conferenze, filtrare il report con la funzionalità "MCOPSTNPP". In questo modo verranno fornite informazioni su tutte le chiamate con pagamento al minuto.  Per i servizi di audioconferenza con pagamento al minuto, filtrare in base a "MCOMEETACPEA" invece che a "MCOPSTNPP".  

> [!NOTE]
> In alcuni campi potrebbe inoltre essere visualizzato il messaggio "nessun dato". "Nessun dato" indica che il campo non è applicabile al tipo o alle funzionalità di chiamata. 

> [!NOTE]
> Se si ha un piano per le chiamate Telstra o Softbank, non verranno visualizzati record dei dettagli delle chiamate nel report sull'utilizzo di PSTN. Contatta Telstra o Softbank per le tue esigenze di reporting. 
***
![Numero 2](../images/sfbcallout2.png)<br/>Fare clic per trascinare una colonna fino a **Per raggruppare per una specifica colonna, trascinare qui l'intestazione di colonna** se si desidera creare una visualizzazione che raggruppi tutti i dati in una o più colonne.
 ***

## <a name="exporting-pstn-usage-report"></a>Esportazione del report sull'utilizzo di PSTN

Facendo clic o **toccando il pulsante Esporta** in Excel è possibile scaricare il report sull'utilizzo di PSTN. È possibile esportare i dati fino a un anno dalla data corrente, a meno che le normative specifiche del paese non impedino la conservazione dei dati per 12 mesi.

Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi.

Il completamento del processo di esportazione può richiedere da pochi secondi a diversi minuti, a seconda della quantità di dati. Al termine dell'esportazione, si riceverà un file ZIP denominato **"Calls.Export.[ `identifier` ]. zip**", con l'identificatore un ID univoco per l'esportazione, che può essere usato per la risoluzione dei problemi.

Se hai piani per chiamate e instradamento diretto, il file esportato potrebbe contenere dati per entrambi i prodotti. Il file del report sull'utilizzo PSTN avrà il nome "**PSTN.calls.[ `UTC date` ]. csv**". Oltre ai file PSTN e Direct Routing, l'archivio contiene il file "**parameters.jssu**", con l'intervallo di tempo di esportazione selezionato e le eventuali funzionalità.

Il file esportato è un file con valori delimitati da virgole (CSV), conforme allo standard [RFC 4180.](https://tools.ietf.org/html/rfc4180) Il file può essere aperto in Excel o in qualsiasi altro editor conforme agli standard senza richiedere alcuna trasformazione.

La prima riga del file CSV contiene i nomi di colonna.

### <a name="fields-in-the-export"></a>Campi nell'esportazione

Il file esportato contiene altri campi non disponibili nel report online. Possono essere usati per la risoluzione dei problemi e flussi di lavoro automatizzati.

> [!div class="has-no-wrap"]  
> | #  | Nome | [Tipo di dati (SQL Server)](https://docs.microsoft.com/sql/t-sql/data-types/data-types-transact-sql) | Descrizione |
> | :-: | :-: | :-: |:------------------- |
> | 0 | UsageId | `uniqueidentifier` | Identificatore di chiamata univoco |
> | 1 | ID chiamata | `nvarchar(64)` | Identificatore della chiamata. Non garantito come univoco |
> | 2 | ID conferenza | `nvarchar(64)` | ID dell'audioconferenza |
> | 3 | Posizione utente | `nvarchar(2)` | Codice paese dell'utente, [ISO 3166-1 alfa-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | AAD ObjectId | `uniqueidentifier` | Chiamata dell'ID utente in Azure Active Directory.<br/> Queste e altre informazioni utente saranno Null/vuote per i tipi di chiamata bot (ucap_in, ucap_out) |
> | 5 | UPN | `nvarchar(128)` | UserPrincipalName (nome di accesso) in Azure Active Directory.<br/>In genere corrisponde all'indirizzo SIP dell'utente e può essere uguale all'indirizzo di posta elettronica dell'utente |
> | 6 | Nome visualizzato dell'utente | `nvarchar(128)` | Nome visualizzato dell'utente |
> | 7 | ID chiamante | `nvarchar(128)` | Numero che ha ricevuto la chiamata per le chiamate in entrata o il numero composto per le chiamate in uscita. [Formato E.164](https://en.wikipedia.org/wiki/E.164) |
> | 8 | Tipo di chiamata | `nvarchar(32)` | Se la chiamata PSTN è in uscita o in entrata e il tipo di chiamata, ad esempio una chiamata effettuato da un utente o un'audioconferenza |
> | 9 | Tipo numero | `nvarchar(16)` | Tipo di numero di telefono dell'utente, ad esempio un servizio di numero verde |
> | 10 | Nazionali/internazionali | `nvarchar(16)` | Se la chiamata è stata nazionale (all'interno di un paese o di un'area geografica) o internazionale (all'esterno di un paese o di un'area geografica) in base alla posizione dell'utente |
> | 11 | Destinazione chiamata | `nvarchar(64)` | Paese o area geografica chiamata |
> | 12 | Destination Number | `nvarchar(32)` | Numero composto nel [formato E.164](https://en.wikipedia.org/wiki/E.164) |
> | 13 | Ora inizio | `datetimeoffset` | Ora di inizio chiamata (UTC, [ISO 8601)](https://en.wikipedia.org/wiki/ISO_8601) |
> | 14 | Ora fine | `datetimeoffset` | Ora di fine chiamata (UTC, [ISO 8601)](https://en.wikipedia.org/wiki/ISO_8601) |
> | 15 | Duration Seconds | `int` | Per quanto tempo è stata connessa la chiamata |
> | 16 | Commissione di connessione | `numeric(16, 2)` | Prezzo commissione di connessione |
> | 17 | Carica | `numeric(16, 2)` | Importo della chiamata o costo addebitato sul tuo account |
> | 18 | Valuta | `nvarchar(3)` | Tipo di valuta utilizzata per calcolare il costo della chiamata[(ISO 4217)](https://en.wikipedia.org/wiki/ISO_4217) |
> | 19 | Funzionalità | `nvarchar(32)` | Licenza utilizzata per la chiamata |

    
## <a name="want-to-see-other-skype-for-business-reports"></a>Per consultare altri report di Skype for Business

- [Report attività in Skype for Business](activity-report.md) permette di vedere quanto gli utenti usano le conferenze peer-to-peer e organizzate o vi partecipano.
    
- [Skype per report di utilizzo del dispositivo Business](device-usage-report.md) permette di vedere i dispositivi, compresi i sistemi operativi e dispositivi mobili basati su Windows, in cui è installata l'app Skype for Business e che la utilizzano per messaggistica istantanea e riunioni.
    
- [Report attività organizzatore di conferenze in Skype for Business](conference-organizer-activity-report.md) È possibile vedere quanto gli utenti organizzano conferenze che usano messaggistica istantanea, audio/video, condivisione applicazioni, web, /chiamata in uscita di terze parti e /chiamata in uscita - Microsoft.
    
- [Report attività partecipante di conferenze in Skype for Business](conference-participant-activity-report.md) È possibile visualizzare il numero di partecipanti a conferenze audio, audio/video, condivisione applicazioni, web e chiamata in uscita.
    
- [Report attività peer-to-peer in Skype for Business](peer-to-peer-activity-report.md) - Permette di vedere quanto gli utenti usano messaggistica istantanea, audio/video, condivisione applicazioni e trasferimento di file.
    
- [Skype per gli utenti aziendali bloccati report](users-blocked-report.md) - Permette di consultare gli utenti dell'organizzazione a cui è impedito effettuare chiamate.

- [I pool di minuti PSTN di Skype for Business riportano](pstn-minute-pools-report.md) il numero di minuti consumati durante il mese corrente all'interno dell'organizzazione.

- [Report dei dettagli della sessione di Skype for Business](session-details-report.md) Puoi vedere i dettagli sulle esperienze di chiamata di un singolo utente.
    
## <a name="related-topics"></a>Argomenti correlati
[Report attività nell'interfaccia di amministrazione](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  
  
 

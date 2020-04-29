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
description: La nuova area report dell'interfaccia di amministrazione di Skype for business Mostra la chiamata e l'attività di conferenza audio nell'organizzazione. Permette di approfondire le analisi fino al livello dei report per un panorama più dettagliato delle attività di ciascun utente. Ad esempio, con il report Dettagli di utilizzo PSTN Skype for Business è possibile consultare il numero di minuti delle chiamate in entrata e in uscita e i costi di quelle chiamate. È possibile visualizzare i dettagli di utilizzo PSTN dei servizi di audioconferenza, incluso il costo della chiamata, in modo da poter comprendere l'utilizzo e chiamare i dettagli di fatturazione per determinare l'utilizzo all'interno dell'organizzazione.
ms.openlocfilehash: e298bc79b821a8ec8373186a879b94790bc9d151
ms.sourcegitcommit: 0835f4335ebc8ca53b8348e0b1b906828eb4e13e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2020
ms.locfileid: "43918514"
---
# <a name="pstn-usage-report"></a>Report di utilizzo PSTN

La nuova area **report** dell'interfaccia di amministrazione di Skype for business Mostra la chiamata e l'attività di conferenza audio nell'organizzazione. Permette di approfondire le analisi fino al livello dei report per un panorama più dettagliato delle attività di ciascun utente. Ad esempio, con il report **Dettagli di utilizzo PSTN Skype for Business** è possibile consultare il numero di minuti delle chiamate in entrata e in uscita e i costi di quelle chiamate. È possibile visualizzare i dettagli di utilizzo PSTN dei servizi di audioconferenza, incluso il costo della chiamata, in modo da poter comprendere l'utilizzo e chiamare i dettagli di fatturazione per determinare l'utilizzo all'interno dell'organizzazione.
  
Vedere la [Panoramica dei report](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) per altri report disponibili.
  
Questo report, insieme agli altri report di Skype for business, fornisce informazioni dettagliate sull'attività, incluso l'uso delle chiamate nell'organizzazione. Questi dettagli sono molto utili per l'analisi, la pianificazione e l'esecuzione di altre decisioni aziendali per l'organizzazione e per la configurazione dei crediti per le [comunicazioni](/microsoftteams/what-are-communications-credits).
  
> [!NOTE]
> È possibile visualizzare tutti i report di Skype for business quando si accede come amministratore all'interfaccia di amministrazione di Microsoft 365. 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-usage-details-report"></a>Come ottenere i report di utilizzo PSTN di Skype for Business

![Icona che mostra il logo di Skype for Business](../images/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**

-  > Accedere all'interfaccia di amministrazione > **interfaccia di amministrazione di****Skype for business** > per l'interfaccia di amministrazione**segnala** > **i dettagli sull'utilizzo PSTN**.
    
    > [!NOTE]
    > A seconda dell'abbonamento a Microsoft 365 o Office 365, è possibile che non vengano visualizzati tutti i prodotti e i report visualizzati qui.
  
## <a name="interpret-the-skype-for-business-pstn-usage-report"></a>Interpretare il report di utilizzo PSTN di Skype for Business

È possibile consultare l'utilizzo di PSTN Skype for Business dei propri utenti leggendo le colonne visualizzate.
  
Questo è l'aspetto del report.
  
![Report di utilizzo PSTN di Skype for Business](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png)

***
![Numero 1](../images/sfbcallout1.png)<br/>La tabella illustra tutto l'utilizzo di PSTN suddiviso per utente. Mostra tutti gli utenti a cui è assegnato Skype for Business e il loro utilizzo di PSTN. È possibile aggiungere/rimuovere colonne dalla tabella.
*    **ID chiamata** è l'ID della chiamata. Si tratta di un identificatore per la chiamata usata quando si chiama il servizio di supporto tecnico Microsoft.
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
     *    **conf_in** (una chiamata in entrata per il Bridge di audioconferenza). Per i record di questo tipo di chiamata, l'utente specificato nella colonna **ID utente** corrisponde all'organizzatore della riunione.
     *    **conf_out** (una chiamata in uscita dal Bridge di audioconferenza, in genere per aggiungere un numero PSTN alla conferenza). Per i record di questo tipo di chiamata, l'utente specificato nella colonna **ID utente** corrisponde all'organizzatore della riunione.

     **UCAP (Unified Communication Applications)** 
     *    **ucap_in** (chiamata PSTN in ingresso per l'applicazione UC, ad esempio operatore automatico o coda di chiamata) 
     *    **ucap_out** (chiamata PSTN in uscita dall'applicazione UC, ad esempio operatore automatico o coda di chiamata)
         > [!NOTE]
         > Le chiamate trasferite a un utente dall'applicazione UC, ad esempio un operatore automatico o una coda di chiamata, non verranno visualizzate nel report utilizzo PSTN, poiché questi piedini di chiamata sono chiamate audio peer-to-peer (P2P). È possibile accedere alle chiamate P2P nell'interfaccia di amministrazione di Skype for business in "strumenti > Skype for business call Analytics" e cercare in base al nome utente o all'indirizzo SIP correlando la chiamata per data/ora e/o CLID di origine (ID linea chiamante). 

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

> [!NOTE]
> In alcuni campi potrebbe essere visualizzato anche "Nessun dato". "Nessun dato" indica che il campo non è applicabile al tipo o alla funzionalità di chiamata. 

> [!NOTE]
> Se si dispone di un piano per chiamate Telstra, non verranno visualizzati record dettagli chiamata nel report utilizzo PSTN. Contattare Telstra per le esigenze di Reporting. 
***
![Numero 2](../images/sfbcallout2.png)<br/>Fare clic per trascinare una colonna fino a **Per raggruppare per una specifica colonna, trascinare qui l'intestazione di colonna** se si desidera creare una visualizzazione che raggruppi tutti i dati in una o più colonne.
 ***

## <a name="exporting-pstn-usage-report"></a>Esportazione di report sull'utilizzo PSTN

Facendo clic o toccando il pulsante **Esporta in Excel** è possibile scaricare il report sull'utilizzo PSTN. È possibile esportare i dati fino a un anno dalla data corrente, a meno che le normative specifiche per paese non vietino la conservazione dei dati per 12 mesi.

Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi.

Il processo di esportazione può richiedere da pochi secondi a diversi minuti per il completamento, a seconda della quantità di dati. Quando il server completa l'esportazione, viene visualizzato un file zip denominato "**chiamate. Export. [ ] `identifier`. zip**", con l'identificatore che rappresenta un ID univoco per l'esportazione, che può essere usato per la risoluzione dei problemi.

Se si hanno entrambi i piani per le chiamate e il routing diretto, il file esportato potrebbe contenere dati per entrambi i prodotti. Il file di report sull'utilizzo PSTN avrà il nome "**PSTN. Calls. [ ] `UTC date`. csv**". Oltre ai file di routing PSTN e Direct, l'archivio contiene il file "**Parameters. JSON**", con l'intervallo di tempo e le funzionalità di esportazione selezionati (se presenti).

File esportato è un file con valori separati da virgola (CSV), conforme allo standard [RFC 4180](https://tools.ietf.org/html/rfc4180) . Il file può essere aperto in Excel o in qualsiasi altro editor conforme agli standard senza richiedere trasformazioni.

La prima riga del file CSV contiene i nomi di colonna.

### <a name="fields-in-the-export"></a>Campi nell'esportazione

Il file esportato contiene altri campi che non sono disponibili nel report online. Questi possono essere usati per la risoluzione dei problemi e i flussi di lavoro automatici.

> [!div class="has-no-wrap"]  
> | #  | Nome | [Tipo di dati (SQL Server)](https://docs.microsoft.com/sql/t-sql/data-types/data-types-transact-sql) | Descrizione |
> | :-: | :-: | :-: |:------------------- |
> | 0 | UsageId | `uniqueidentifier` | Identificatore univoco delle chiamate |
> | 1 | ID chiamata | `nvarchar(64)` | Identificatore chiamata. Non è garantito che sia univoco |
> | 2 | ID conferenza | `nvarchar(64)` | ID della conferenza audio |
> | 3 | Posizione utente | `nvarchar(2)` | Codice paese dell'utente, [ISO 3166-1 Alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | AAD ObjectId | `uniqueidentifier` | Chiamata dell'ID utente in Azure Active Directory.<br/> Questo e altre informazioni utente saranno null/Empty per i tipi di chiamata bot (ucap_in, ucap_out) |
> | 5 | UPN | `nvarchar(128)` | UserPrincipalName (nome di accesso) in Azure Active Directory.<br/>Si tratta in genere dello stesso indirizzo SIP dell'utente e può essere uguale all'indirizzo di posta elettronica dell'utente |
> | 6 | Nome visualizzato dell'utente | `nvarchar(128)` | Nome visualizzato dell'utente |
> | 7 | ID chiamante | `nvarchar(128)` | Numero che ha ricevuto la chiamata per le chiamate in ingresso o il numero composto per le chiamate in uscita. Formato [E. 164](https://en.wikipedia.org/wiki/E.164) |
> | 8 | Tipo di chiamata | `nvarchar(32)` | Se la chiamata è una chiamata in uscita PSTN o in ingresso e il tipo di chiamata, ad esempio una chiamata effettuata da un utente o da una conferenza audio |
> | 9 | Tipo di numero | `nvarchar(16)` | Tipo di numero di telefono dell'utente, ad esempio un servizio di numero verde |
> | 10 | Nazionali/internazionali | `nvarchar(16)` | Se la chiamata è stata nazionale (all'interno di un paese o di un'area geografica) o internazionale (all'esterno di un paese o area geografica) in base alla posizione dell'utente |
> | 11 | Destinazione chiamata | `nvarchar(64)` | Paese o area geografica chiamata |
> | 12 | Numero di destinazione | `nvarchar(32)` | Numero composto in formato [E. 164](https://en.wikipedia.org/wiki/E.164) |
> | 13 | Ora di inizio | `datetimeoffset` | Ora di inizio chiamata (UTC, [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601)) |
> | 14 | Ora di fine | `datetimeoffset` | Ora di fine chiamata (UTC, [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601)) |
> | 15 | Secondi di durata | `int` | Per quanto tempo la chiamata è stata connessa |
> | 16 | Costo di connessione | `numeric(16, 2)` | Prezzo della tariffa di connessione |
> | 17 | Addebito | `numeric(16, 2)` | Importo del pagamento o del costo della chiamata addebitata al tuo account |
> | 18 | Valuta | `nvarchar(3)` | Tipo di valuta usata per calcolare il costo della chiamata ([ISO 4217](https://en.wikipedia.org/wiki/ISO_4217)) |
> | 19 | Funzionalità | `nvarchar(32)` | Licenza usata per la chiamata |

    
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
[Report attività nell'interfaccia di amministrazione](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  
  
 

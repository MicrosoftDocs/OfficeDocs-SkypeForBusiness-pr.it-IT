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
description: La nuova area Skype for Business report dell'interfaccia di amministrazione mostra le attività di chiamata e audioconferenza nell'organizzazione. Permette di approfondire le analisi fino al livello dei report per un panorama più dettagliato delle attività di ciascun utente. Ad esempio, con il report Dettagli di utilizzo PSTN Skype for Business è possibile consultare il numero di minuti delle chiamate in entrata e in uscita e i costi di quelle chiamate. È possibile visualizzare i dettagli sull'utilizzo PSTN per i servizi di audioconferenza, incluso il costo della chiamata, in modo da comprendere i dettagli di utilizzo e di fatturazione delle chiamate per determinare l'utilizzo all'interno dell'organizzazione.
ms.openlocfilehash: 2c6a0410611919662f5eaf37a03bfcca11b543be
ms.sourcegitcommit: 3704577b1424c063fd925a58a6f6d0b3ff2c8148
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2021
ms.locfileid: "53278449"
---
# <a name="pstn-usage-report"></a>Report di utilizzo PSTN

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

La nuova area Skype for Business **report** dell'interfaccia di amministrazione mostra le attività di chiamata e audioconferenza nell'organizzazione. Permette di approfondire le analisi fino al livello dei report per un panorama più dettagliato delle attività di ciascun utente. Ad esempio, con il report **Dettagli di utilizzo PSTN Skype for Business** è possibile consultare il numero di minuti delle chiamate in entrata e in uscita e i costi di quelle chiamate. È possibile visualizzare i dettagli sull'utilizzo PSTN per i servizi di audioconferenza, incluso il costo della chiamata, in modo da comprendere i dettagli di utilizzo e di fatturazione delle chiamate per determinare l'utilizzo all'interno dell'organizzazione.
  
Vedere la [panoramica dei report](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) per altri report disponibili.
  
Questo report, insieme agli altri report Skype for Business, fornisce dettagli sull'attività, incluso l'utilizzo delle chiamate all'interno dell'organizzazione. Questi dettagli sono molto utili quando si analizzano, si pianificano e si prendono altre decisioni aziendali per l'organizzazione e per la configurazione dei [Crediti comunicazioni.](/microsoftteams/what-are-communications-credits)
  
> [!NOTE]
> È possibile visualizzare tutti i report Skype for Business quando si accede come amministratore al interfaccia di amministrazione di Microsoft 365. 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-usage-details-report"></a>Come ottenere i report di utilizzo PSTN di Skype for Business

![Icona che mostra il logo di Skype for Business](../images/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**

- Passare all'interfaccia di amministrazione > **di amministrazione Skype for Business**  >  **l'interfaccia di amministrazione** Riporta  >  **i**  >  **dettagli sull'utilizzo pstn.**
    
    > [!NOTE]
    > A seconda dell'Microsoft 365 o Office 365 abbonamento, è possibile che non siano visualizzati tutti i prodotti e i report visualizzati qui.
  
## <a name="interpret-the-skype-for-business-pstn-usage-report"></a>Interpretare il report di utilizzo PSTN di Skype for Business

È possibile consultare l'utilizzo di PSTN Skype for Business dei propri utenti leggendo le colonne visualizzate.
  
Questo è l'aspetto del report.
  
[![Skype for Business utilizzo PSTN ](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png)](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png#lightbox)

***
![Numero 1](../images/sfbcallout1.png)<br/>La tabella illustra tutto l'utilizzo di PSTN suddiviso per utente. Mostra tutti gli utenti a cui è assegnato Skype for Business e il loro utilizzo di PSTN. È possibile aggiungere/rimuovere colonne dalla tabella.
*    **ID chiamata** è l'ID della chiamata. Si tratta di un identificatore per la chiamata usata quando si chiama il supporto del servizio Microsoft.
*    **ID utente** è il nome di accesso dell'utente.
*    **Numero di telefono** è il numero di telefono Skype for Business che ha ricevuto la chiamata (per le chiamate in entrata) o il numero chiamato (per le chiamate in uscita).
*    **La posizione dell'utente** è il paese/area geografica in cui si trova l'utente.
*    **ID chiamante** è il numero di telefono del chiamante (ID chiamante) per le chiamate in entrata, oppure il numero o numero Skype for Business da cui è partita la chiamata per le chiamate in uscita.
*    **Tipo di** chiamata indica se la chiamata è stata una chiamata PSTN in uscita o in arrivo e il tipo di chiamata, ad esempio una chiamata da parte di un utente o un'audioconferenza. Questi sono i tipi di chiamata visualizzati. 

     **Tipi di chiamata del Piano per chiamate** 
     *    **user_in** (l'utente ha ricevuto una chiamata PSTN in ingresso) 
     *    **user_out** (l'utente ha effettuato una chiamata PSTN in uscita) 
     *    **user_out_conf** (l'utente ha aggiunto 2 o più partecipanti PSTN alla chiamata, per esempio una conferenza a 3) 
     *    **user_out_transfer** (l'utente ha trasferito la chiamata a un numero PSTN) 
     *    **user_out_forwarding** (l'utente ha inoltrato la chiamata a un numero PSTN)

     **Tipi di chiamate Audioconferenze**
     *    **conf_in** (chiamata in ingresso al bridge di audioconferenza). Per i record di questo tipo di chiamata, l'utente specificato nella colonna **ID** utente corrisponde all'organizzatore della riunione.
     *    **conf_out** (chiamata in uscita dal bridge di audioconferenza, in genere per aggiungere un numero PSTN alla conferenza). Per i record di questo tipo di chiamata, l'utente specificato nella colonna **ID** utente corrisponde all'organizzatore della riunione.

     **UCAP (Unified Communication Applications)** 
     *    **ucap_in** (una chiamata PSTN in ingresso all'applicazione UC, ad esempio l'operatore automatico o la coda di chiamata) 
     *    **ucap_out** (una chiamata PSTN in uscita dall'applicazione UC, ad esempio l'operatore automatico o la coda di chiamata)
         > [!NOTE]
         > Le chiamate trasferite a un utente dall'applicazione UC, ad esempio un operatore automatico o una coda di chiamata, non verranno visualizzate nel report sull'utilizzo pstn, in quanto queste chiamate sono chiamate audio peer-to-peer (P2P). È possibile accedere alle chiamate P2P nell'interfaccia di amministrazione di Skype for Business in "Strumenti > Skype for Business Call Analytics" e cercare in base al nome utente o all'indirizzo SIP che correla la chiamata in base alla data/ora e/o al CLID di origine (ID linea chiamante). 

     **Nazionale/internazionale** indica se la chiamata effettuata è considerata nazionale (entro un Paese/area geografica) o internazionale (al di fuori di un Paese/area geografica) a seconda della posizione dell'utente. 
*    **Destinazione chiamata è** il nome del paese o dell'area geografica di destinazione chiamata, ad esempio Francia, Germania o Stati Uniti (Stati Uniti). 
*    **Tipo di** numero è il tipo di numero di telefono del numero di telefono di un utente, di un servizio o di un numero verde.  
*    **Ora di inizio (UTC)** è l'ora in cui è stata iniziata o effettuata la chiamata. 
*    **Durata** è il tempo per cui resta connessa la chiamata.  
*    **ConfID** è l'ID conferenza dell'audioconferenza. 
*    **Addebito** è l'importo del costo della chiamata addebitato sull'account. 
*    **Valuta** è il tipo di valuta usato per calcolare il costo della chiamata. 
*    **Capacità** è la licenza usata per la chiamata. I tipi di licenza disponibili sono i seguenti. 
     *    **MCOPSTNPP** - Crediti comunicazioni <br/> **MCOPSTN1** - Piano per chiamate nazionali (3000 min piani UE per gli Stati Uniti/ 1200 min) 
     *    **MCOPSTN2** - Piano per chiamate internazionali 
     *    **MCOPSTN5** - Piano per chiamate nazionali (piano per chiamate da 120 minuti) 
     *    **MCOPSTN6** - Piano per chiamate nazionali (piano per chiamate di 240 minuti) Nota: Disponibilità limitata
     *    **MCOMEETADD** - Audioconferenza
     *    **MCOMEETACPEA** - Audioconferenza a pagamento al minuto
     
> [!NOTE]
> Se si vuole eseguire un report per includere solo chiamate a pagamento al minuto non incluse nell'abbonamento alle chiamate o ai servizi di conferenza, filtrare il report con la funzionalità "MCOPSTNPP". In questo modo verrà fornito un elenco di tutte le chiamate a pagamento al minuto.  Per audioconferenze a pagamento al minuto, filtrare in base a "MCOMEETACPEA" invece di "MCOPSTNPP".  

> [!NOTE]
> In alcuni campi potrebbe essere visualizzato anche "nessun dato". "Nessun dato" indica che il campo non è applicabile al tipo di chiamata o alla funzionalità. 

> [!NOTE]
> Se si ha un piano per le chiamate Telstra o Softbank, nel report sull'utilizzo PSTN non verranno visualizzati i record dei dettagli delle chiamate. Contatta Telstra o Softbank per le tue esigenze di segnalazione. 
***
![Numero 2](../images/sfbcallout2.png)<br/>Fare clic per trascinare una colonna fino a **Per raggruppare per una specifica colonna, trascinare qui l'intestazione di colonna** se si desidera creare una visualizzazione che raggruppi tutti i dati in una o più colonne.
 ***

## <a name="exporting-pstn-usage-report"></a>Esportazione del report sull'utilizzo PSTN

Facendo clic o toccando il **pulsante Esporta in Excel** consente di scaricare il report sull'utilizzo PSTN. È possibile esportare dati fino a un anno dalla data corrente, a meno che le normative specifiche del paese non impedino la conservazione dei dati per 12 mesi.

Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi.

Il completamento del processo di esportazione può richiedere da alcuni secondi a diversi minuti, a seconda della quantità di dati. Quando il server completa l'esportazione, si riceverà un file ZIP denominato "**Calls.Export.[ `identifier` ] .zip**", con l'identificatore come ID univoco per l'esportazione, che può essere usato per la risoluzione dei problemi.

Se si hanno piani per chiamate e instradamento diretto, il file esportato può contenere dati per entrambi i prodotti. Il file di report sull'utilizzo PSTN avrà il nome del file "**PSTN.calls.[ `UTC date` ] .csv**". Oltre ai file PSTN e Direct Routing, l'archivio contiene il file "**parameters.jssu**", con l'intervallo di tempo di esportazione selezionato e le funzionalità (se presenti).

Il file esportato è un file CSV (Comma Separated Values), conforme allo standard [RFC 4180.](https://tools.ietf.org/html/rfc4180) Il file può essere aperto in Excel o in qualsiasi altro editor conforme agli standard senza richiedere alcuna trasformazione.

La prima riga del file CSV contiene nomi di colonna.

### <a name="fields-in-the-export"></a>Campi nell'esportazione

Il file esportato contiene altri campi non disponibili nel report online. Possono essere usati per la risoluzione dei problemi e per i flussi di lavoro automatizzati.

> [!div class="has-no-wrap"]  
> | #  | Nome | [Tipo di dati (SQL Server)](/sql/t-sql/data-types/data-types-transact-sql) | Descrizione |
> | :-: | :-: | :-: |:------------------- |
> | 0 | UsageId | `uniqueidentifier` | Identificatore univoco della chiamata |
> | 1 | ID chiamata | `nvarchar(64)` | Identificatore di chiamata. Non è garantito che sia univoco |
> | 2 | ID conferenza | `nvarchar(64)` | ID dell'audioconferenza |
> | 3 | Posizione utente | `nvarchar(2)` | Codice paese dell'utente, [ISO 3166-1 alfa-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | AAD ObjectId | `uniqueidentifier` | Id utente chiamante in Azure Active Directory.<br/> Questa e altre informazioni utente saranno Null/vuote per i tipi di chiamata bot (ucap_in, ucap_out) |
> | 5 | UPN | `nvarchar(128)` | UserPrincipalName (nome di accesso) in Azure Active Directory.<br/>In genere corrisponde all'indirizzo SIP dell'utente e può essere uguale all'indirizzo di posta elettronica dell'utente |
> | 6 | Nome visualizzato utente | `nvarchar(128)` | Nome visualizzato dell'utente |
> | 7 | ID chiamante | `nvarchar(128)` | Numero che ha ricevuto la chiamata per le chiamate in ingresso o il numero composto per le chiamate in uscita. [Formato E.164](https://en.wikipedia.org/wiki/E.164) |
> | 8 | Tipo di chiamata | `nvarchar(32)` | Se la chiamata è stata una chiamata PSTN in uscita o in ingresso e il tipo di chiamata, ad esempio una chiamata da un utente o un'audioconferenza |
> | 9 | Tipo di numero | `nvarchar(16)` | Tipo di numero di telefono dell'utente, ad esempio un servizio di numero verde |
> | 10 | Nazionale/Internazionale | `nvarchar(16)` | Se la chiamata è stata nazionale (all'interno di un paese o di un'area geografica) o internazionale (all'esterno di un paese o di un'area geografica) in base alla posizione dell'utente |
> | 11 | Destinazione chiamata | `nvarchar(64)` | Paese o area geografica chiamata |
> | 12 | Numero di destinazione | `nvarchar(32)` | Numero composto in [formato E.164](https://en.wikipedia.org/wiki/E.164) |
> | 13 | Ora inizio | `datetimeoffset` | Ora di inizio chiamata (UTC, [ISO 8601)](https://en.wikipedia.org/wiki/ISO_8601) |
> | 14 | Ora di fine | `datetimeoffset` | Ora di fine chiamata (UTC, [ISO 8601)](https://en.wikipedia.org/wiki/ISO_8601) |
> | 15 | Durata secondi | `int` | Per quanto tempo è stata connessa la chiamata |
> | 16 | Quota di connessione | `numeric(16, 2)` | Prezzo delle commissioni di connessione |
> | 17 | Addebito | `numeric(16, 2)` | Importo o costo della chiamata addebitata sul tuo account |
> | 18 | Valuta | `nvarchar(3)` | Tipo di valuta usata per calcolare il costo della chiamata ([ISO 4217](https://en.wikipedia.org/wiki/ISO_4217)) |
> | 19 | Funzionalità | `nvarchar(32)` | La licenza usata per la chiamata |

    
## <a name="want-to-see-other-skype-for-business-reports"></a>Per consultare altri report di Skype for Business

- [Report attività in Skype for Business](activity-report.md) permette di vedere quanto gli utenti usano le conferenze peer-to-peer e organizzate o vi partecipano.
    
- [Skype per report di utilizzo del dispositivo Business](device-usage-report.md) permette di vedere i dispositivi, compresi i sistemi operativi e dispositivi mobili basati su Windows, in cui è installata l'app Skype for Business e che la utilizzano per messaggistica istantanea e riunioni.
    
- [Skype for Business attività dell'organizzatore della conferenza](conference-organizer-activity-report.md) È possibile vedere quanto gli utenti organizzano conferenze che usano messaggistica istantanea, audio/video, condivisione applicazioni, Web, /dial out - terze parti e /dial out - Microsoft.
    
- [Skype for Business attività dei partecipanti alla conferenza](conference-participant-activity-report.md) È possibile vedere il numero di conferenze audio, audio/video, condivisione di applicazioni, Web e chiamate in uscita a cui si sta partecipando.
    
- [Report attività peer-to-peer in Skype for Business](peer-to-peer-activity-report.md) - Permette di vedere quanto gli utenti usano messaggistica istantanea, audio/video, condivisione applicazioni e trasferimento di file.
    
- [Skype per gli utenti aziendali bloccati report](users-blocked-report.md) - Permette di consultare gli utenti dell'organizzazione a cui è impedito effettuare chiamate.

- Skype for Business pool di minuti [PSTN](pstn-minute-pools-report.md) è possibile visualizzare il numero di minuti consumati durante il mese corrente all'interno dell'organizzazione.

- [Skype for Business dei dettagli della sessione](session-details-report.md) Puoi visualizzare i dettagli sulle esperienze di chiamata dei singoli utenti.
    
## <a name="related-topics"></a>Argomenti correlati
[Report attività nell'interfaccia di amministrazione](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  
  

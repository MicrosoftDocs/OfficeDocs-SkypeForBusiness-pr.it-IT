---
title: Report utilizzo PSTN di Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
MS.collection:
- M365-voice
description: Informazioni su come usare il report utilizzo PSTN teams nell'interfaccia di amministrazione di Microsoft teams per ottenere una panoramica dell'utilizzo delle chiamate e delle conferenze audio nell'organizzazione.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 18fce1d70308fcdc58441bb1a5cad8a446131e0e
ms.sourcegitcommit: bdf6cea0face74809ad3b8b935bc14ad60b3bb35
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "45201200"
---
# <a name="microsoft-teams-pstn-usage-report"></a>Report utilizzo PSTN di Microsoft Teams

Il report utilizzo PSTN teams nell'interfaccia di amministrazione di Microsoft teams offre una panoramica delle attività di audioconferenza e delle chiamate nell'organizzazione. È possibile visualizzare un'attività di chiamata dettagliata per i piani di chiamata se si usa Microsoft come gestore di telefonia e per il routing diretto se si usa il proprio gestore di telefonia.

La scheda **piani di chiamata** Mostra le informazioni che includono il numero di minuti che gli utenti hanno trascorso nelle chiamate PSTN in ingresso e in uscita e il costo di queste chiamate. La scheda **routing diretto** Mostra le informazioni che includono l'indirizzo SIP e l'ora di inizio e di fine delle chiamate. Usare le informazioni contenute in questo report per scoprire l'uso della rete PSTN nell'organizzazione e consentire l'analisi, pianificare e prendere decisioni aziendali.

> [!NOTE]
> Se si ha un piano di chiamata Telstra o Softbank, non verranno visualizzati record dettagli chiamata nel report utilizzo PSTN. Contattare Telstra o Softbank per le proprie esigenze di Reporting. 

## <a name="view-the-pstn-usage-report"></a>Visualizzare il report sull'utilizzo PSTN

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams fare clic su **analisi &** report  >  **sull'utilizzo**dei rapporti. Nella scheda **Visualizza report** , in **report**, selezionare **report sull'utilizzo PSTN**.
2. In **intervallo di date**selezionare un intervallo predefinito di 7 o 28 giorni oppure impostare un intervallo personalizzato e quindi selezionare **Esegui report**.

## <a name="interpret-the-report"></a>Interpretare il report

### <a name="calling-plans"></a>Piani di chiamata

[![Screenshot del report rapporto utilizzo PSTN piani di chiamata nell'interfaccia di amministrazione](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png "Screenshot del report sull'utilizzo PSTN nell'interfaccia di amministrazione di Microsoft teams con callout numerati")](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png#lightbox)

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Il report può essere visualizzato per le tendenze degli ultimi 7 giorni, 28 giorni o un intervallo di date personalizzato impostato |
|**2**   |Ogni report ha una data per quando è stata generata. In genere, i report presentano una latenza di 24-48 ore dal momento dell'attività. |
|**3**   |L'asse X è l'intervallo di date selezionato per il report specifico. L'asse Y è il numero totale di chiamate nel periodo di tempo selezionato. <br>Posizionare il puntatore del mouse sul punto in una data specificata per visualizzare le chiamate totali in tale data.  |
|**4**   |La tabella offre una ripartizione dell'utilizzo PSTN per chiamata. <ul><li>**Data/ora (UTC)** è l'ora in cui è stata avviata la chiamata.</li><li>**Nome visualizzato** è il nome visualizzato dell'utente. È possibile fare clic sul nome visualizzato per accedere alla pagina di impostazione dell'utente nell'interfaccia di amministrazione di Microsoft teams.</li><li>**Username** è il nome di accesso dell'utente.</li><li>**Numero di telefono** è il numero che ha ricevuto la chiamata per le chiamate in ingresso o il numero composto per le chiamate in uscita.</li><li>**Tipo di chiamata** indica se la chiamata è stata chiamata in uscita PSTN o in ingresso e il tipo di chiamata, ad esempio una chiamata effettuata da un utente o da una conferenza audio. I tipi di chiamate che potrebbero essere visualizzati includono:<br><br>**Tipi di chiamata utente Teams**<ul><li>**user_in** : l'utente ha ricevuto una chiamata PSTN in ingresso.</li><li>**user_out** -l'utente ha effettuato una chiamata PSTN in uscita</li><li>**user_out_conf** : l'utente ha aggiunto due o più partecipanti PSTN alla chiamata, ad esempio una conferenza telefonica a tre vie</li><li>**user_out_transfer** -l'utente ha trasferito la chiamata a un numero PSTN</li><li>**user_out_forwarding** : l'utente ha inoltrato la chiamata a un numero PSTN</li><li>**conf_in** -una chiamata in entrata per il Bridge di audioconferenza</li><li>**conf_out** -una chiamata in uscita dal Bridge di audioconferenza in genere per aggiungere un numero PSTN alla conferenza</li></ul><br>**Tipi di chiamata di bots Teams**<ul><li>**ucap_in** : chiamata PSTN in ingresso a teams bot, ad esempio operatore automatico o coda di chiamata</li><li>**ucap_out** : chiamata PSTN in uscita da un bot di Team, ad esempio operatore automatico o coda di chiamata</li></ul><br><li>**Chiamata a** è il numero composto.</li><li>**Per paese o area geografica** è il paese o l'area geografica chiamata.</li><li>Called **from** è il numero che ha posto la chiamata.</li><li>**Da paese o area geografica** è il paese o l'area geografica in cui è stata inserita la chiamata.</li><li>**Addebito** è la quantità di denaro o il costo della chiamata addebitata al tuo account. </li><li>**Valuta** è il tipo di valuta usato per calcolare il costo della chiamata. </li><li>**Durata** è il tempo per cui resta connessa la chiamata.</li><li>**Nazionale/internazionale** indica se la chiamata è stata domestica (all'interno di un paese o area geografica) o internazionale (all'esterno di un paese o area geografica) in base alla posizione dell'utente.</li><li>**ID chiamata** è l'ID della chiamata. È un identificatore per la chiamata che puoi usare per chiamare il supporto tecnico Microsoft.</li><li>**Tipo di numero** è il tipo di numero di telefono dell'utente, ad esempio un servizio di numero verde. </li><li>**Paese o area geografica** è la posizione di utilizzo. </li> <li>**ID conferenza** è l'ID conferenza della conferenza audio. </li><li>**Capacità** è la licenza usata per la chiamata. I tipi di licenza che si possono vedere includono:<ul><li>**MCOPSTNPP** -Credits comunicazioni</li><li>**MCOPSTN1** -piano per chiamate nazionali (3000 min US/1200 min eu plans)</li><li>**MCOPSTN2** -piano per chiamate internazionali</li><li>**MCOPSTN5** -piano per chiamate nazionali (piano per chiamate 120 min)</li><li>**MCOPSTN6** -piano per chiamate nazionali (piano per chiamate 240 min)</li><li>**MCOMEETADD** -audioconferenza</li><li>**MCOMEETACPEA** -pay per minute audioconferenza</li></ul></li></ul> Per visualizzare le informazioni desiderate nella tabella, assicurarsi di aggiungere le colonne alla tabella.|
|**5**   |Selezionare **modifica colonne** per aggiungere o rimuovere colonne nella tabella. |
|**6**   |Selezionare **filtro** per filtrare il report per nome utente o tipo di chiamata |
|**7**   |Selezionare **schermo intero** per visualizzare il report in modalità schermo intero. |
|**8**   |È possibile esportare il report in un file CSV per l'analisi offline. Fare clic su **Esporta in Excel**, quindi nella scheda **download** fare clic su **Scarica** per scaricare il report quando è pronto.|

### <a name="direct-routing"></a>Routing diretto

[![Screenshot del report rapporto utilizzo PSTN Direct routing nell'interfaccia di amministrazione](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png "Screenshot del report sull'uso PSTN diretto nell'interfaccia di amministrazione di Microsoft teams con callout numerati")](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png#lightbox)

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Il report può essere visualizzato per le tendenze degli ultimi 7 giorni o 28 giorni. |
|**2**   |Ogni report ha una data per quando è stata generata. In genere, i report presentano una latenza di 24-48 ore dal momento dell'attività. |
|**3**   |L'asse X è l'intervallo di date selezionato per il report specifico. L'asse Y è il numero totale di chiamate nel periodo di tempo selezionato.<br>Posizionare il puntatore del mouse sul punto in una data specificata per visualizzare le chiamate totali in tale data.  |
|**4**   |La tabella offre una ripartizione dell'utilizzo PSTN per chiamata. <ul><li>**Data/ora (UTC)** è l'ora in cui è stata avviata la chiamata.</li><li>**Nome visualizzato** è il nome visualizzato dell'utente. È possibile fare clic sul nome visualizzato per accedere alla pagina delle impostazioni dell'utente nell'interfaccia di amministrazione di Microsoft teams. Il nome può essere anche il nome di un bot, ad esempio la coda di chiamata o l'operatore automatico cloud. </li><li>L' **indirizzo SIP** è l'indirizzo SIP dell'utente o un bot che ha ricevuto o eseguito la chiamata.</li><li>**Numero chiamante** è il numero dell'utente o del bot che ha eseguito la chiamata. </li><li>**Numero di chiamata** è il numero dell'utente o del bot che ha ricevuto la chiamata. In una chiamata in ingresso a un utente di teams sarà l'utente di teams, in una chiamata in uscita da un utente di teams sarà l'utente PSTN. </li><li>**Tipo di chiamata** indica se la chiamata è stata chiamata in uscita PSTN o in ingresso e il tipo di chiamata, ad esempio una chiamata effettuata da un utente o da una conferenza audio. I tipi di chiamata che potrebbero essere visualizzati includono:<br><br>**Tipi di chiamata utente Teams**<ul><li>**dr_in** -l'utente ha ricevuto una chiamata PSTN in ingresso</li><li>**dr_out** -l'utente ha effettuato una chiamata PSTN in uscita</li><li>**dr_out_user_conf** : l'utente ha aggiunto un partecipante PSTN alla chiamata</li><li>**user_out_transfer** -l'utente ha trasferito la chiamata a un numero PSTN</li><li>**dr_out_user_forwarding** : l'utente ha inoltrato la chiamata a un numero PSTN</li><li>**dr_out_user_transfer** -l'utente ha trasferito la chiamata a un numero PSTN</li><li>**dr_emergency_out** -l'utente ha eseguito una chiamata di emergenza</li></ul><br>**Tipi di chiamata di bots Teams**<ul><li>**dr_in_ucap** : chiamata PSTN in ingresso a un bot di teams, ad esempio operatore automatico o coda di chiamata</li><li>**dr_out_ucap** : chiamata PSTN in uscita da un bot di Team, ad esempio operatore automatico o coda di chiamata</li></ul><br><li>**Chiamata a** è il numero dell'utente che ha ricevuto la chiamata.</li><li>**Ora di inizio (UTC)** è il momento in cui il proxy SIP ha ricevuto la risposta finale (messaggio SIP "200 OK") da SBC su una chiamata in uscita (teams/bot a un utente PSTN) o dopo che il proxy SIP ha inviato l'invito all'hop successivo all'interno del backend del team su una chiamata in ingresso (un utente PSTN di un team/bot). </li><li>L' **ora di invito (UTC)** è il momento in cui l'invito iniziale è stato inviato in una chiamata in uscita da un utente di teams o da una chiamata bot al SBC o ricevuto in una chiamata in ingresso a una chiamata di teams o bot dal componente proxy SIP del routing diretto da SBC.</li><li>**Ora di errore (UTC)** è il momento in cui la chiamata non è riuscita. Solo per le chiamate non riuscite. Il codice SIP finale, il sottocodice finale Microsoft e la frase SIP finale offrono i motivi per cui la chiamata non è riuscita e può aiutare la risoluzione dei problemi. </li><li>**Ora di fine (UTC)** è il momento in cui la chiamata è terminata (solo per le chiamate con successo).</li><li>**Durata** è il tempo per cui resta connessa la chiamata.</li><li>**Tipo di numero** è il tipo di numero di telefono dell'utente, ad esempio un servizio di numero verde. </li><li>Il **bypass multimediale** indica se il trunk è stato abilitato per il bypass multimediale. </li> <li>L' **FQDN di SBC** è il nome di dominio completo (FQDN) di Session Border Controller (SBC). </li><li>**Area geografica di Azure per elementi multimediali** è il centro dati usato come percorso multimediale in una chiamata non di bypass. </li><li>**Area di Azure per la segnalazione** è il centro dati usato per la segnalazione sia per le chiamate di bypass che per quelle non di bypass. </li><li>**Tipo di evento** è il tipo di evento della chiamata. Verrà visualizzato l'esito positivo per le chiamate e il tentativo di chiamate non riuscite. </li><li>Il **codice SIP finale** è il codice con cui è terminata la chiamata.</li><li>Il **sottocodice Microsoft finale** è un codice che indica azioni specifiche che si sono verificate.</li><li>La **frase finale SIP** è la descrizione del codice SIP e del sottocodice Microsoft.</li><li>**ID di correlazione** è un identificatore univoco per la chiamata che puoi usare per chiamare il supporto tecnico Microsoft.</li><li>L' **ID di correlazione condivisa** è visibile solo nel file CSV scaricabile e non esiste nel portale. L'ID di correlazione condivisa esiste in almeno due chiamate correlate. Vedere la descrizione dettagliata seguente.</li></ul> Per visualizzare le informazioni desiderate nella tabella, assicurarsi di aggiungere le colonne alla tabella.|
|**5**   |Selezionare **modifica colonne** per aggiungere o rimuovere colonne nella tabella. |
|**6**   |Selezionare **schermo intero** per visualizzare il report in modalità schermo intero. |
|**7**   |Selezionare **Esporta in Excel** per scaricare i dati in un file CSV (comma separated) per l'analisi offline o per usarlo come input per il sistema di fatturazione. |

#### <a name="callercallee-fields-considerations"></a>Considerazioni sui campi chiamante/chiamato

A seconda della direzione della chiamata, il chiamante o i nomi dei chiamanti possono contenere numeri non E164.

Questi campi possono provenire da SBC del cliente. Sono disponibili tre formati che possono essere inviati da SBC al routing diretto: numeri E. 164, numeri non E. 164 e stringhe.

- Numero di telefono e. 164 da un utente con un numero E. 164 a un utente che ha anche un numero E. 164. 
- Chiama da un numero non E. 164. Un utente di un PBX di terze parti collegato al routing diretto effettua una chiamata a un utente di teams. In questo caso, il numero chiamante potrebbe essere un numero diverso da E. 164, ad esempio + 1001. 
- Uno spammer chiama e non presenta un numero, bensì un nome, ad esempio "Internal Revenue Service". Questa stringa verrà visualizzata nei report.

#### <a name="about-shared-correlation-id"></a>Informazioni sull'ID correlazione condivisa

L'ID di correlazione condivisa esiste solo nel file di Excel esportato che si scarica e indica che sono correlate due o più chiamate. Di seguito vengono illustrati i diversi scenari e quando è presente l'ID di correlazione condivisa.

1.    Utente PSTN 1 in un endpoint PSTN denominato teams User 1 nel client teams, tipo di chiamata Dr_In, ID di correlazione 57f28917-42k5-4c0c-9433-79734873f2ac, nessun ID di correlazione condivisa.
2.    L'utente teams 1 nel client Teams ha chiamato l'utente PSTN 1 in un endpoint PSTN, chiama tipo Dr_Out 2c12b8ca-62eb-4c48-B68D-e451f518ff4, nessun ID di correlazione condivisa.
3.    Utente PSTN 1 in un endpoint PSTN denominato teams User 2 nel client teams, tipo di chiamata Dr_In f45e9a25-9f94-46e7-A457-84f5940efde9, ID di correlazione condivisa f45e9a25-9f94-46e7-A457-84f5940efde9.
4.    Chiamata esistente 3 con l'ID di correlazione "f45e9a25-9f94-46e7-A457-84f5940efde9". Utente PSTN 1 in una chiamata con teams User 2. Utenti teams 2 trasferiti (ciechi o consultivi) una chiamata a team o utenti PSTN, tipo di chiamata Dr_Out_User_Transfer 45a1da7c-9e97-481a-8a05-3fe19a9a77e0, ID di correlazione condivisa f45e9a25-9f94-46e7-A457-84f5940efde9.

## <a name="exporting-the-reports"></a>Esportare i report
Fare clic su **Esporta in Excel**, quindi nella scheda **download** fare clic su **Scarica** per scaricare il report quando è pronto. Il processo di esportazione può richiedere da pochi secondi a diversi minuti per il completamento, a seconda della quantità di dati.

Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. I file esportati contengono altri campi che non sono disponibili nel report online. Questi possono essere usati per la risoluzione dei problemi e i flussi di lavoro automatici.

 Si riceverà un file zip denominato "**calls. Export. `[identifier]` . zip**", con l'identificatore che rappresenta un ID univoco per l'esportazione che può essere usata per la risoluzione dei problemi.

Se si hanno entrambi i piani per le chiamate e il routing diretto, il file esportato potrebbe contenere dati per entrambi i prodotti. Il file di report sull'utilizzo PSTN avrà il nome "**PSTN. calls `[UTC date]` .. CSV**"e routing diretto"**DirectRouting. Calls. `[UTC date]` . CSV**".

 Oltre ai file di routing PSTN e Direct, l'archivio contiene il file "**parameters.js**attivato", con l'intervallo di tempo di esportazione e le funzionalità selezionati.

I file esportati si trovano in formato CSV (comma separated values), conforme allo standard [RFC 4180](https://tools.ietf.org/html/rfc4180) . I file possono essere aperti in Excel o in qualsiasi altro editor conforme agli standard senza richiedere trasformazioni.

La prima riga del file CSV contiene i nomi di colonna. Tutte le date sono UTC e in formato [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) .

### <a name="exported-pstn-usage-report"></a>Report sull'utilizzo PSTN esportato

 È possibile esportare i dati fino a un anno dalla data corrente, a meno che le normative specifiche per paese non vietino la conservazione dei dati per 12 mesi.

> [!div class="has-no-wrap"]  
> | # | Nome | [Tipo di dati (SQL Server)](https://docs.microsoft.com/sql/t-sql/data-types/data-types-transact-sql) | Descrizione |
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
> | 13 | Ora di inizio | `datetimeoffset` | Ora di inizio chiamata |
> | 14 | Ora di fine | `datetimeoffset` | Ora di fine chiamata |
> | 15 | Secondi di durata | `int` | Per quanto tempo la chiamata è stata connessa |
> | 16 | Costo di connessione | `numeric(16, 2)` | Prezzo della tariffa di connessione |
> | 17 | Addebito | `numeric(16, 2)` | Importo del pagamento o del costo della chiamata addebitata al tuo account |
> | 18 | Valuta | `nvarchar(3)` | Tipo di valuta usata per calcolare il costo della chiamata ([ISO 4217](https://en.wikipedia.org/wiki/ISO_4217)) |
> | 19 | Funzionalità | `nvarchar(32)` | Licenza usata per la chiamata |

### <a name="exported-direct-routing-usage-report"></a>Report sull'uso di routing diretto esportato

È possibile esportare i dati fino a un massimo di cinque mesi (150 giorni) dalla data corrente, a meno che le normative nazionali non vietino la conservazione dei dati per tale periodo.

> [!div class="has-no-wrap"]  
> | # | Nome | [Tipo di dati (SQL Server)](https://docs.microsoft.com/sql/t-sql/data-types/data-types-transact-sql) | Descrizione |
> | :-: | :-: | :-: |:------------------- |
> | 0 | CorrelationId | `uniqueidentifier` | Identificatore univoco delle chiamate |
> | 1 | Indirizzo SIP | `nvarchar(128)` | Indirizzo dell'utente o del bot che ha eseguito o ricevuto la chiamata.<br/>Si noti che si tratta in realtà di UserPrincipalName (UPN, nome di accesso) in Azure Active Directory, che in genere corrisponde all'indirizzo SIP. |
> | 2 | Nome visualizzato | `nvarchar(128)` | Nome di un utente o di un bot chiamante, ad esempio coda di chiamata o operatore automatico, impostato nell'interfaccia di amministrazione di Microsoft 365 |
> | 3 | Paese utente | `nvarchar(2)` | Codice paese dell'utente, [ISO 3166-1 Alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | Invitare il tempo | `datetimeoffset` | Quando l'invito iniziale invia in uscita dall'utente di teams o dalla chiamata bot al SBC o ricevuto in ingresso a teams o chiamata tramite bot dal componente proxy SIP del routing diretto da SBC |
> | 5 | Ora di inizio | `datetimeoffset` | Ora in cui il proxy SIP ha ricevuto la risposta finale (messaggio SIP "200 OK") da SBC in uscita (teams/bot a un utente PSTN) o dopo che il proxy SIP ha inviato l'invito all'hop successivo all'interno del backend di teams sulla chiamata in ingresso (un utente PSTN in un team/bot).<br/>Per le chiamate non riuscite e senza risposta, può essere uguale a tempo di inviti o di errore |
> | 6 | Tempo di errore | `datetimeoffset` | Esiste solo per le chiamate fallite (non completamente stabilite) |
> | 7 | Ora di fine | `datetimeoffset` | Esiste solo per le chiamate di successo (completamente stabilita). Ora di fine chiamata |
> | 8 | Durata (secondi) | `int` | Durata della chiamata |
> | 9 | Successo | `nvarchar(3)` | Sì/No. Operazione riuscita o tentativo |
> | 10 | Numero chiamante | `nvarchar(32)` | Numero dell'utente o del bot che ha eseguito la chiamata. In ingresso a una chiamata utente del team sarà un utente PSTN, in uscita dalla chiamata utente teams sarà il numero di utenti Teams |
> | 12 | Numero di chiamanti | `nvarchar(32)` | Numero dell'utente o del bot che ha ricevuto la chiamata. In ingresso a una chiamata utente del team sarà l'utente teams, in uscita dalla chiamata utente teams sarà l'utente PSTN |
> | 13 | Tipo di chiamata | `nvarchar(32)` | Tipo di chiamata e direzione |
> | 14 | Area geografica di Azure per elementi multimediali | `nvarchar(8)` | Centro dati usato per il percorso multimediale in una chiamata non di bypass |
> | 15 | Area di Azure per la segnalazione | `nvarchar(8)` | Centro dati usato per la segnalazione sia per le chiamate di bypass che per quelle non di bypass |
> | 16 | Codice SIP finale | `int` | Il codice con cui è terminata la chiamata, [RFC 3261](https://tools.ietf.org/html/rfc3261) |
> | 17 | Sottocodice Microsoft finale | `int` | Oltre ai codici SIP, Microsoft ha sottocodici personalizzati che indicano il problema specifico |
> | 18 | Frase SIP finale | `nvarchar(256)` | Descrizione del codice SIP e del sottocodice Microsoft |
> | 19 | FQDN DI SBC | `nvarchar(64)` | Nome di dominio completo del controller di bordo della sessione |
> | 20 | Bypass multimediale | `nvarchar(3)` | Sì/No. Indica se il trunk è stato abilitato per il bypass multimediale o non |
> | 21 | ID correlazione condivisa | `uniqueidentifier` | Indica che due o più chiamate sono correlate |


## <a name="related-topics"></a>Argomenti correlati

- [Analisi e creazione di report in teams](teams-reporting-reference.md)

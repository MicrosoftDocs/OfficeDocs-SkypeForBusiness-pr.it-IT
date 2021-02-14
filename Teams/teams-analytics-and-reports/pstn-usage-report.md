---
title: Report di utilizzo PSTN di Microsoft Teams
author: cichur
ms.author: v-cichur
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
description: Informazioni su come usare il report utilizzo PSTN di Teams nell'interfaccia di amministrazione di Microsoft Teams per una panoramica dell'utilizzo delle chiamate e delle audioconferenze nell'organizzazione.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cc2b1ae0b6df29e29a55152dbafb9b76ae31e973
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809296"
---
# <a name="microsoft-teams-pstn-usage-report"></a>Report di utilizzo PSTN di Microsoft Teams

Il report utilizzo PSTN di Teams nell'interfaccia di amministrazione di Microsoft Teams offre una panoramica delle attività di chiamata e audioconferenza nell'organizzazione. È possibile visualizzare un'attività di chiamata dettagliata per i piani per chiamate se si utilizza Microsoft come gestore di telefonia e per l'instradamento diretto se si usa il proprio gestore di telefonia.

La **scheda Piani** per chiamate mostra informazioni come il numero di minuti di chiamate PSTN in entrata e in uscita e il costo di queste chiamate. La **scheda Routing diretto** mostra informazioni come l'indirizzo SIP e l'ora di inizio e di fine della chiamata. Usare le informazioni contenute in questo report per ottenere informazioni approfondite sull'utilizzo di PSTN nell'organizzazione e consentire di analizzare, pianificare e prendere decisioni aziendali.

> [!NOTE]
> Se si ha un piano per le chiamate Telstra o Softbank, non verranno visualizzati record dei dettagli delle chiamate nel report sull'utilizzo di PSTN. Contatta Telstra o Softbank per le tue esigenze di reporting. 

## <a name="view-the-pstn-usage-report"></a>Visualizzare il report sull'utilizzo di PSTN

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, fare clic su **Analisi & report**  >  **sull'utilizzo.** Nella scheda **Visualizza report,** in **Report,** selezionare **Report utilizzo PSTN.**
2. In **Intervallo di date** selezionare un intervallo predefinito di 7 o 28 giorni oppure impostare un intervallo personalizzato e quindi selezionare Esegui **report.**

## <a name="interpret-the-report"></a>Interpretare il report

### <a name="calling-plans"></a>Piani di chiamata

[![Screenshot del report Utilizzo PSTN](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png "Screenshot del report Utilizzo PSTN nell'interfaccia di amministrazione di Microsoft Teams con callout numerati") di Piani per chiamate nell'interfaccia di amministrazione](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png#lightbox)

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Il report può essere visualizzato per le tendenze degli ultimi 7, 28 giorni o un intervallo di date personalizzato impostato |
|**2**   |Ogni report include la data in cui è stato generato. In genere, i report presentano una latenza di 24-48 ore dal momento dell'attività. |
|**3**   |L'asse X è l'intervallo di date selezionato per il report specifico. L'asse Y è il numero totale di chiamate nel periodo di tempo selezionato. <br>Posizionare il puntatore del mouse sul punto in una data specifica per visualizzare il totale delle chiamate effettuate in tale data.  |
|**4**   |La tabella fornisce un'analisi dell'utilizzo di PSTN per ogni chiamata. <ul><li>**L'ora (UTC)** è l'ora di inizio della chiamata.</li><li>**Il nome** visualizzato è il nome visualizzato dell'utente. È possibile fare clic sul nome visualizzato per passare alla pagina delle impostazioni dell'utente nell'interfaccia di amministrazione di Microsoft Teams.</li><li>**Nome** utente è il nome di accesso dell'utente.</li><li>**Il numero di** telefono è il numero che ha ricevuto la chiamata per le chiamate in entrata o il numero composto per le chiamate in uscita.</li><li>**Il tipo di** chiamata è se la chiamata PSTN era in uscita o in entrata e il tipo di chiamata, ad esempio una chiamata effettuato da un utente o un'audioconferenza. I tipi di chiamata visualizzati includono:<br><br>**Tipi di chiamata utente di Teams**<ul><li>**user_in:** l'utente ha ricevuto una chiamata PSTN in ingresso.</li><li>**user_out** - l'utente ha effettuato una chiamata PSTN in uscita</li><li>**user_out_conf** - l'utente ha aggiunto due o più partecipanti PSTN alla chiamata, ad esempio una conferenza telefonica a tre</li><li>**user_out_transfer** - l'utente ha trasferito la chiamata a un numero PSTN</li><li>**user_out_forwarding** - l'utente ha inoltrato la chiamata a un numero PSTN</li><li>**conf_in** - chiamata in ingresso al bridge di audioconferenza</li><li>**conf_out** - una chiamata in uscita dal bridge di audioconferenza che in genere consente di aggiungere un numero PSTN alla conferenza</li></ul><br>**Tipi di chiamate dei bot di Teams**<ul><li>**ucap_in** - una chiamata PSTN in ingresso a un bot di Teams come un operatore automatico o una coda di chiamata</li><li>**ucap_out** - una chiamata PSTN in uscita da un bot di Teams come un operatore automatico o una coda di chiamata</li></ul><br><li>**Chiamato a** è il numero composto.</li><li>**Il paese o l'area** geografica è il paese o l'area geografica chiamata.</li><li>**Chiamato da** è il numero che ha effettuato la chiamata.</li><li>**Il paese o l'area** geografica è il paese o l'area geografica da cui è stata effettuato la chiamata.</li><li>**L'addebito** è l'importo o il costo della chiamata addebitato sul tuo account. </li><li>**Valuta** è il tipo di valuta usato per calcolare il costo della chiamata. </li><li>**Durata** è il tempo per cui resta connessa la chiamata.</li><li>**Nazionali/internazionali** indica se la chiamata è stata nazionale (all'interno di un paese o area geografica) o internazionale (all'esterno di un paese o di un'area geografica) in base alla posizione dell'utente.</li><li>**ID chiamata** è l'ID della chiamata. Si tratta di un identificatore per la chiamata che puoi utilizzare quando chiami il supporto tecnico Microsoft.</li><li>**Tipo di** numero è il tipo di numero di telefono dell'utente, ad esempio un servizio di numero verde. </li><li>**Il paese o l'area** geografica è la località di utilizzo. </li> <li>**L'ID** conferenza è l'ID conferenza dell'audioconferenza. </li><li>**Capacità** è la licenza usata per la chiamata. I tipi di licenza disponibili includono:<ul><li>**MCOPSTNPP** - Crediti comunicazioni</li><li>**MCOEV o MCOEV_VIRTUALUSER** - Applicazioni vocali come Operatore automatico o Code di chiamata</li><li>**FREECALL** - In caso di problemi tecnici che impediscono il prezzo di una chiamata, la chiamata viene fornita gratuitamente e verrà visualizzata con questa funzionalità</li><li>**MCOPSTN1** - Piano per chiamate nazionali (piani DA 3000 min USA /1200 min UE)</li><li>**MCOPSTN2** - Piano per chiamate internazionali</li><li>**MCOPSTN5** - Piano per chiamate nazionali (piano da 120 min)</li><li>**MCOPSTN6** - Piano per chiamate nazionali (piano per chiamate da 240 min)</li><li>**MCOMEETADD** - Audioconferenza</li><li>**MCOMEETACPEA** - Audioconferenza con pagamento al minuto</li></ul></li></ul> Per visualizzare le informazioni desiderate nella tabella, assicurarsi di aggiungere le colonne alla tabella.|
|**5**   |Selezionare **Modifica colonne** per aggiungere o rimuovere colonne nella tabella. |
|**6**   |Selezionare **Filtro per** filtrare il report in base al nome utente o al tipo di chiamata |
|**7**   |Selezionare **Schermo intero** per visualizzare il report in modalità a schermo intero. |
|**8**   |È possibile esportare il report in un file CSV per l'analisi offline. Fare clic su Esporta in **Excel,** quindi nella **scheda Download** fare clic su **Scarica** per scaricare il report quando è pronto.|

### <a name="direct-routing"></a>Routing diretto

[![Screenshot del report Sull'utilizzo di PSTN per l'instradamento diretto nell'interfaccia di amministrazione](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png "Screenshot del report Di utilizzo PSTN per l'instradamento diretto nell'interfaccia di amministrazione di Microsoft Teams con callout numerati")](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png#lightbox)

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Il report può essere visualizzato per le tendenze degli ultimi 7 o 28 giorni. |
|**2**   |Ogni report include la data in cui è stato generato. In genere, i report presentano una latenza di 24-48 ore dal momento dell'attività. |
|**3**   |L'asse X è l'intervallo di date selezionato per il report specifico. L'asse Y è il numero totale di chiamate nel periodo di tempo selezionato.<br>Posizionare il puntatore del mouse sul punto in una data specifica per visualizzare il totale delle chiamate effettuate in tale data.  |
|**4**   |La tabella fornisce un'analisi dell'utilizzo di PSTN per ogni chiamata. <ul><li>**L'ora (UTC)** è l'ora di inizio della chiamata.</li><li>**Il nome** visualizzato è il nome visualizzato dell'utente. È possibile fare clic sul nome visualizzato per passare alla pagina delle impostazioni dell'utente nell'interfaccia di amministrazione di Microsoft Teams. Il nome può anche essere il nome di un bot, ad esempio la coda di chiamata o l'Operatore automatico. </li><li>**L'indirizzo SIP** è l'indirizzo SIP dell'utente o di un bot che ha ricevuto o effettuato la chiamata.</li><li>**Il numero chiamante** è il numero dell'utente o del bot che ha effettuato la chiamata. </li><li>**Numero del chiamato è** il numero dell'utente o del bot che ha ricevuto la chiamata. Durante una chiamata in ingresso a un utente di Teams sarà l'utente di Teams, in una chiamata in uscita da un utente di Teams sarà l'utente PSTN. </li><li>**Il tipo di** chiamata è se la chiamata PSTN era in uscita o in entrata e il tipo di chiamata, ad esempio una chiamata effettuato da un utente o un'audioconferenza. I tipi di chiamata disponibili includono:<br><br>**Tipi di chiamata utente di Teams**<ul><li>**dr_in** - l'utente ha ricevuto una chiamata PSTN in ingresso</li><li>**dr_out** - l'utente ha effettuato una chiamata PSTN in uscita</li><li>**dr_out_user_conf** - l'utente ha aggiunto un partecipante PSTN alla chiamata</li><li>**user_out_transfer** - l'utente ha trasferito la chiamata a un numero PSTN</li><li>**dr_out_user_forwarding** - l'utente ha inoltrato la chiamata a un numero PSTN</li><li>**dr_out_user_transfer** - l'utente ha trasferito la chiamata a un numero PSTN</li><li>**dr_emergency_out** - l'utente ha effettuato una chiamata di emergenza</li></ul><br>**Tipi di chiamate dei bot di Teams**<ul><li>**dr_in_ucap** - una chiamata PSTN in ingresso a un bot di Teams come un operatore automatico o una coda di chiamata</li><li>**dr_out_ucap** - una chiamata PSTN in uscita da un bot di Teams come un operatore automatico o una coda di chiamata</li></ul><br><li>**Chiamato a** è il numero dell'utente che ha ricevuto la chiamata.</li><li>L'ora di inizio **(UTC)** è l'ora in cui il proxy SIP ha ricevuto la risposta finale (messaggio SIP "200 OK") dal sistema SBC durante una chiamata in uscita (Teams/Bot a un utente PSTN) o dopo che il proxy SIP ha inviato l'invito all'hop successivo all'interno del back-end di Teams con una chiamata in ingresso (utente PSTN a teams/bot). </li><li>L'ora di invito **(UTC)** è l'ora in cui l'invito iniziale è stato inviato in una chiamata in uscita da un utente di Teams o una chiamata bot al servizio SBC o ricevuto durante una chiamata in entrata a teams o bot dal componente proxy SIP dell'instradamento diretto dal servizio SBC.</li><li>**L'ora utc (Failure Time)** è l'ora in cui la chiamata non è riuscita. Solo per le chiamate non effettuate. Il codice SIP finale, il sottocodice Microsoft finale e la frase SIP finale forniscono i motivi per cui la chiamata non è riuscita e possono essere utili per la risoluzione dei problemi. </li><li>**L'ora di fine (UTC)** è l'ora di fine della chiamata (solo per chiamate di successo).</li><li>**Durata** è il tempo per cui resta connessa la chiamata.</li><li>**Tipo di** numero è il tipo di numero di telefono dell'utente, ad esempio un servizio di numero verde. </li><li>**Il bypass multimediale** indica se il trunk è stato abilitato per il bypass multimediale. </li> <li>**L'FQDN di SBC** è il nome di dominio completo (FQDN) del controller dei confini della sessione. </li><li>**Area geografica di Azure per** i supporti multimediali è il data center usato come percorso multimediale in una chiamata senza bypass. </li><li>**L'area geografica di Azure** per il segnalazione è il centro dati utilizzato per le chiamate di bypass e non bypass. </li><li>**Il tipo di** evento è il tipo di evento della chiamata. Verranno visualizzati l'errore per le chiamate riuscite e il tentativo di chiamata non riuscita. </li><li>**Il codice SIP finale** è il codice con cui la chiamata è terminata.</li><li>**Il sottocodice Microsoft finale** è un codice che indica azioni specifiche che si sono verificati.</li><li>**La frase SIP finale** è la descrizione del codice SIP e del sottocodice Microsoft.</li><li>**L'ID** di correlazione è un identificatore univoco per la chiamata che è possibile usare quando si chiama il supporto tecnico Microsoft.</li><li>**L'ID** di correlazione condiviso è visibile solo nel file CSV scaricabile e non esiste nel portale. L'ID di correlazione condiviso è presente in almeno due chiamate correlate. Vedere la descrizione dettagliata di seguito.</li></ul> Per visualizzare le informazioni desiderate nella tabella, assicurarsi di aggiungere le colonne alla tabella.|
|**5**   |Selezionare **Modifica colonne** per aggiungere o rimuovere colonne nella tabella. |
|**6**   |Selezionare **Schermo intero** per visualizzare il report in modalità a schermo intero. |
|**7**   |Selezionare **Esporta in Excel** per scaricare i dati in un file con valori delimitati da virgole (CSV) per l'analisi offline o per usarli come input per il sistema di fatturazione. |

#### <a name="callercallee-fields-considerations"></a>Considerazioni sui campi Chiamante/Chiamato

A seconda della direzione della chiamata, i nomi dei chiamanti o dei chiamanti possono contenere numeri non E164.

Questi campi possono essere provenienti dai record SBC del cliente. Esistono tre formati che il servizio SBC può inviare al routing diretto: numeri E.164, numeri non E.164 e stringhe.

- E.164 numero di telefono di un utente che ha un numero E.164 a un utente che ha anche un numero E.164. 
- Chiama da un numero non E.164. Un utente di un PBX di terze parti connesso con l'instradamento diretto effettua una chiamata a un utente di Teams. In questo caso, il numero chiamante potrebbe essere qualsiasi numero diverso da E.164, ad esempio +1001. 
- Uno spammer chiama e non presenta un numero, ma solo un nome, ad esempio "Internal Revenue Service". Questa stringa verrà visualizzata nei report.

#### <a name="about-shared-correlation-id"></a>Informazioni sull'ID di correlazione condiviso

L'ID di correlazione condivisa esiste solo nel file esportato di Excel scaricato e indica che due o più chiamate sono correlate. Di seguito vengono illustrati i diversi scenari e la data in cui è presente l'ID di correlazione condiviso.

1.    Utente PSTN 1 su un endpoint PSTN chiamato Teams User 1 sul client Teams, tipo di chiamata Dr_In, ID di correlazione 57f28917-42k5-4c0c-9433-79734873f2ac, nessun ID di correlazione condiviso.
2.    Utente 1 di Teams sul client Teams chiamato Utente PSTN 1 su un endpoint PSTN, tipo di chiamata Dr_Out 2c12b8ca-62eb-4c48-b68d-e451f518ff4, nessun ID di correlazione condiviso.
3.    Utente PSTN 1 su un endpoint PSTN chiamato Teams User 2 sul client Teams, call type Dr_In f45e9a25-9f94-46e7-a457-84f5940efde9, shared correlation ID f45e9a25-9f94-46e7-a457-84f5940efde9.
4.    Chiamata esistente 3 con ID di correlazione "f45e9a25-9f94-46e7-a457-84f5940efde9". Utente PSTN 1 in una chiamata con l'utente 2 di Teams. Teams User 2 ha trasferito (non vedente o consultivo) una chiamata a Teams o a un Utente PSTN, call type Dr_Out_User_Transfer 45a1da7c-9e97-481a-8a05-3fe19a9a77e0, shared correlation ID f45e9a25-9f94-46e7-a457-84f5940efde9.

## <a name="exporting-the-reports"></a>Esportazione dei report
Fare clic su Esporta in **Excel,** quindi nella **scheda Download** fare clic su **Scarica** per scaricare il report quando è pronto. Il completamento del processo di esportazione può richiedere da pochi secondi a diversi minuti, a seconda della quantità di dati.

Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. I file esportati contengono campi aggiuntivi non disponibili nel report online. Possono essere usati per la risoluzione dei problemi e flussi di lavoro automatizzati.

 Si riceverà un file ZIP denominato "**Calls.Export. `[identifier]` . zip**", con l'identificatore un ID univoco per l'esportazione che può essere usato per la risoluzione dei problemi.

Se hai piani per chiamate e instradamento diretto, il file esportato potrebbe contenere dati per entrambi i prodotti. Il file del report sull'utilizzo PSTN avrà il nome "**PSTN.calls. `[UTC date]` . csv**" e Direct Routing "**DirectRouting.calls. `[UTC date]` . csv**".

 Oltre ai file PSTN e Direct Routing, l'archivio contiene il file "**parameters.js",** con l'intervallo di tempo e le funzionalità di esportazione selezionati.

I file esportati sono in formato CSV (Comma Separated Values), conforme allo standard [RFC 4180.](https://tools.ietf.org/html/rfc4180) I file possono essere aperti in Excel o in qualsiasi altro editor conforme agli standard senza richiedere alcuna trasformazione.

La prima riga del file CSV contiene i nomi di colonna. Tutte le date sono in formato UTC e [ISO 8601.](https://en.wikipedia.org/wiki/ISO_8601)

### <a name="exported-pstn-usage-report"></a>Report sull'utilizzo di PSTN esportato

 È possibile esportare i dati fino a un anno dalla data corrente, a meno che le normative specifiche del paese non impedino la conservazione dei dati per 12 mesi.

> [!div class="has-no-wrap"]  
> | # | Nome | [Tipo di dati (SQL Server)](https://docs.microsoft.com/sql/t-sql/data-types/data-types-transact-sql) | Descrizione |
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
> | 13 | Ora inizio | `datetimeoffset` | Ora di inizio chiamata |
> | 14 | Ora fine | `datetimeoffset` | Ora di fine chiamata |
> | 15 | Duration Seconds | `int` | Per quanto tempo è stata connessa la chiamata |
> | 16 | Commissione di connessione | `numeric(16, 2)` | Prezzo commissione di connessione |
> | 17 | Carica | `numeric(16, 2)` | Importo della chiamata o costo addebitato sul tuo account |
> | 18 | Valuta | `nvarchar(3)` | Tipo di valuta utilizzata per calcolare il costo della chiamata[(ISO 4217)](https://en.wikipedia.org/wiki/ISO_4217) |
> | 19 | Funzionalità | `nvarchar(32)` | Licenza utilizzata per la chiamata |

### <a name="exported-direct-routing-usage-report"></a>Report sull'utilizzo dell'instradamento diretto esportato

È possibile esportare dati fino a cinque mesi (150 giorni) dalla data corrente, a meno che le normative specifiche del paese non impedino la conservazione dei dati per tale periodo.

> [!div class="has-no-wrap"]  
> | # | Nome | [Tipo di dati (SQL Server)](https://docs.microsoft.com/sql/t-sql/data-types/data-types-transact-sql) | Descrizione |
> | :-: | :-: | :-: |:------------------- |
> | 0 | Id correlazione | `uniqueidentifier` | Identificatore di chiamata univoco |
> | 1 | Indirizzo SIP | `nvarchar(128)` | Indirizzo dell'utente o del bot che ha effettuato o ricevuto la chiamata.<br/>Si noti che si tratta in realtà di UserPrincipalName (UPN, nome di accesso) in Azure Active Directory, che in genere corrisponde all'indirizzo SIP |
> | 2 | Nome visualizzato | `nvarchar(128)` | Il nome di un utente o di un bot per le chiamate (ad esempio coda di chiamata o Operatore automatico) come impostato nell'interfaccia di amministrazione di Microsoft 365 |
> | 3 | Paese utente | `nvarchar(2)` | Codice paese dell'utente, [ISO 3166-1 alfa-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | Ora invito | `datetimeoffset` | Quando l'invito iniziale viene inviato in uscita dall'utente o dalla chiamata bot di Teams all'SBC o quando si riceve una chiamata in ingresso a Teams o bot dal componente proxy SIP dell'instradamento diretto da SBC |
> | 5 | Ora di inizio | `datetimeoffset` | Ora in cui il proxy SIP ha ricevuto la risposta finale (messaggio SIP "200 OK") dal servizio SBC in uscita (Teams/Bot a un utente PSTN) o dopo che il proxy SIP ha inviato l'invito al passaggio successivo all'interno di Teams back-end sulla chiamata in ingresso (Utente PSTN a teams/bot).<br/>Per le chiamate non riuscite e senza risposta, può essere uguale all'ora di invito o di errore |
> | 6 | Tempo di errore | `datetimeoffset` | Esiste solo per le chiamate non riuscite (non stabilite completamente) |
> | 7 | Ora di fine | `datetimeoffset` | Esiste solo per le chiamate con esito positivo (completo). Ora di fine della chiamata |
> | 8 | Durata (secondi) | `int` | Durata della chiamata |
> | 9 | Operazione riuscita | `nvarchar(3)` | Sì/No. Operazione riuscita o tentativo |
> | 10 | Numero chiamante | `nvarchar(32)` | Numero dell'utente o del bot che ha effettuato la chiamata. In entrata a una chiamata di un utente del team sarà un utente PSTN, in uscita dalla chiamata utente di Teams sarà il numero utente di Teams |
> | 12 | Numero del chiamato | `nvarchar(32)` | Numero dell'utente o del bot che ha ricevuto la chiamata. In entrata a una chiamata di un utente del team sarà l'utente di Teams, in uscita dalla chiamata dell'utente teams sarà l'utente PSTN |
> | 13 | Tipo di chiamata | `nvarchar(32)` | Tipo e direzione della chiamata |
> | 14 | Area geografica azure per elementi multimediali | `nvarchar(8)` | Data center utilizzato per il percorso del supporto in una chiamata senza bypass |
> | 15 | Area geografica Azure per il segnalazione | `nvarchar(8)` | Il centro dati utilizzato per la segnalazione sia per le chiamate di bypass che per le chiamate senza bypass |
> | 16 | Codice SIP finale | `int` | Codice con cui la chiamata è terminata, [RFC 3261](https://tools.ietf.org/html/rfc3261) |
> | 17 | Sottocodice Microsoft finale | `int` | Oltre ai codici SIP, Microsoft ha dei sottocodice che indicano il problema specifico |
> | 18 | Frase SIP finale | `nvarchar(256)` | Descrizione del codice SIP e del sottocodice Microsoft |
> | 19 | SBC FQDN | `nvarchar(64)` | Nome di dominio completo del controller dei confini della sessione |
> | 20 | Bypass multimediale | `nvarchar(3)` | Sì/No. Indica se il trunk è stato abilitato per il bypass multimediale |
> | 21 | ID di correlazione condiviso | `uniqueidentifier` | Indica che due o più chiamate sono correlate |


## <a name="related-topics"></a>Argomenti correlati

- [Analisi e creazione di report di Teams](teams-reporting-reference.md)

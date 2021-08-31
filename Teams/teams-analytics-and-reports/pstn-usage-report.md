---
title: Microsoft Teams Report sull'utilizzo PSTN
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
MS.collection:
- M365-voice
description: Informazioni su come usare il report sull'utilizzo Teams PSTN nell'interfaccia di amministrazione di Microsoft Teams per ottenere una panoramica dell'utilizzo delle chiamate e delle audioconferenze nell'organizzazione.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bf7432f33162b51199beb7783f68dac86f88d697
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731035"
---
# <a name="microsoft-teams-pstn-usage-report"></a>Microsoft Teams Report sull'utilizzo PSTN

Il report Teams utilizzo di PSTN (Public Switched Telephone Network) nell'interfaccia di amministrazione di Microsoft Teams offre una panoramica delle attività di chiamata e audioconferenza nell'organizzazione. Se si usa Microsoft come gestore di telefonia e per l'instradamento diretto, è possibile visualizzare l'attività di chiamata dettagliata per i piani di chiamata se si usa Microsoft come gestore di telefonia e per il routing diretto se si usa il proprio gestore di telefonia.

La **scheda Piani chiamate** mostra informazioni, tra cui il numero di minuti trascorsi dagli utenti nelle chiamate PSTN in ingresso e in uscita e il costo di queste chiamate. La **scheda Instradamento** diretto mostra informazioni che includono l'indirizzo SIP e l'ora di inizio e di fine della chiamata. Usare le informazioni contenute in questo report per ottenere informazioni approfondite sull'utilizzo della rete PSTN nell'organizzazione e per analizzare, pianificare e prendere decisioni aziendali.

> [!NOTE]
> Se si ha un piano per le chiamate Telstra o Softbank, nel report sull'utilizzo PSTN non verranno visualizzati i record dei dettagli delle chiamate. Contatta Telstra o Softbank per le tue esigenze di segnalazione. 

## <a name="view-the-pstn-usage-report"></a>Visualizzare il report sull'utilizzo pstn

1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione fare clic su Analisi & **report**  >  **utilizzo**. Nella scheda **Visualizza report,** in **Report,** selezionare **Report utilizzo PSTN.**
2. In **Intervallo di date** selezionare un intervallo predefinito di 7 o 28 giorni oppure impostare un intervallo personalizzato e quindi selezionare Esegui **report.**

## <a name="interpret-the-report"></a>Interpretare il report

### <a name="calling-plans"></a>Piani di chiamata

[! [Screenshot del report sull'utilizzo PSTN di Piani per chiamate nell'interfaccia di amministrazione] (.. /media/teams-reports-pstn-usage-calling-plans-with-callouts.png "Screenshot del report sull'utilizzo PSTN nell'interfaccia Microsoft Teams di amministrazione con callout numerati".](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png#lightbox)

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Il report può essere visualizzato per le tendenze degli ultimi 7, 28 giorni o per un intervallo di date personalizzato impostato |
|**2**   |Ogni report ha una data in cui è stato generato. In genere, i report presentano una latenza di 24-48 ore dal momento dell'attività. |
|**3**   |L'asse X è l'intervallo di date selezionato per il report specifico. L'asse Y è il numero totale di chiamate nel periodo di tempo selezionato. <br>Passare il puntatore del mouse sul punto in una data specifica per visualizzare il totale delle chiamate in tale data.  |
|**4**   |La tabella fornisce una descrizione dell'utilizzo PSTN per ogni chiamata. <ul><li>**Timestamp (UTC)** è l'ora di inizio della chiamata.</li><li>**Nome visualizzato** è il nome visualizzato dell'utente. È possibile fare clic sul nome visualizzato per passare alla pagina delle impostazioni dell'utente nell'Microsoft Teams di amministrazione.</li><li>**Nomeutente** è il nome di accesso dell'utente.</li><li>**Telefono numero è** il numero che ha ricevuto la chiamata per le chiamate in ingresso o il numero composto per le chiamate in uscita.</li><li>**Tipo di** chiamata indica se la chiamata è stata una chiamata PSTN in uscita o in ingresso e il tipo di chiamata, ad esempio una chiamata da parte di un utente o un'audioconferenza. I tipi di chiamate che potrebbero essere visualizzati includono:<br><br>**Teams tipi di chiamata utente**<ul><li>**user_in** : l'utente ha ricevuto una chiamata PSTN in ingresso.</li><li>**user_out** - l'utente ha effettuato una chiamata PSTN in uscita</li><li>**user_out_conf** : l'utente ha aggiunto due o più partecipanti PSTN alla chiamata, ad esempio una conferenza telefonica a tre</li><li>**user_out_transfer** - l'utente ha trasferito la chiamata a un numero PSTN</li><li>**user_out_forwarding** : l'utente ha inoltrato la chiamata a un numero PSTN</li><li>**conf_in-** una chiamata in ingresso al bridge di audioconferenza</li><li>**conf_out:** una chiamata in uscita dal bridge di audioconferenza in genere per aggiungere un numero PSTN alla conferenza</li></ul><br>**Teams di chiamata dei bot**<ul><li>**ucap_in:** una chiamata PSTN in ingresso a Teams bot, ad esempio l'operatore automatico o la coda di chiamata</li><li>**ucap_out-** una chiamata PSTN in uscita da un bot Teams, ad esempio l'operatore automatico o la coda di chiamata</li></ul><br><li>**Chiamato a** è il numero composto.</li><li>**Per paese o area geografica** è il paese o l'area geografica chiamata.</li><li>**Chiamato da** è il numero che ha effettuato la chiamata.</li><li>**Da paese o area geografica** è il paese o l'area geografica da cui è stata inserita la chiamata.</li><li>**Addebito** è l'importo o il costo della chiamata addebitato sul tuo account. </li><li>**Valuta** è il tipo di valuta usato per calcolare il costo della chiamata. </li><li>**Durata** è il tempo per cui resta connessa la chiamata.</li><li>**Nazionale/Internazionale indica** se la chiamata è stata nazionale (all'interno di un paese o di un'area geografica) o internazionale (all'esterno di un paese o di un'area geografica) in base alla posizione dell'utente.</li><li>**ID chiamata** è l'ID della chiamata. Si tratta di un identificatore per la chiamata che è possibile usare quando si chiama il supporto Tecnico Microsoft.</li><li>**Tipo di** numero è il tipo di numero di telefono dell'utente, ad esempio un servizio di numero verde. </li><li>**Paese o area geografica** è il luogo di utilizzo. </li> <li>**ID conferenza** è l'ID conferenza dell'audioconferenza. </li><li>**Capacità** è la licenza usata per la chiamata. I tipi di licenza visualizzati includono:<ul><li>**MCOEV o MCOEV_VIRTUALUSER o MCOEV_VIRTUALUSER_GOV** - Applicazioni vocali come Operatore automatico o Code di chiamata</li><li>**FREECALL** - In caso di problemi tecnici che impediscono il prezzo di una chiamata, la chiamata viene fornita gratuitamente e verrà visualizzata con questa funzionalità</li><li>**MCOPSTN1** - Piano per chiamate nazionali (3000 min piani UE per gli Stati Uniti/ 1200 min)</li><li>**MCOPSTN2** - Piano per chiamate internazionali</li><li>**MCOPSTN5** - Piano per chiamate nazionali (piano per chiamate da 120 minuti)</li><li>**MCOPSTN6** - Piano per chiamate nazionali (piano per chiamate di 240 minuti)</li><li>**MCOPSTN8** - Piano per chiamate nazionali 120 min per utente (non in pool tra gli utenti come gli altri piani di chiamata)</li><li>**MCOPSTN9** - Piano per chiamate internazionali</li><li>**MCOPSTNCAP** - Area Telefono</li><li>**MCOPSTNPP** - Crediti comunicazioni</li><li>**MCOMEETADD** - Audioconferenza</li><li>**MCOMEETADD_DIALOUT_US** - Audioconferenza dial-out per Stati Uniti e Canada</li><li>**MCOMEETADD_CN_GLOBAL** - Audioconferenze per utenti non cinesi</li><li>**MCOMEETADD_TATA** - Tata Communications Connections</li><li>**MCOMEETACPEA** - Audioconferenza pay-per-minute </li><li>**MCOMEETACPEA_GOV** - Pagamento al minuto per i servizi di audioconferenza per enti pubblici</li></ul></li></ul> Per visualizzare le informazioni desiderate nella tabella, assicurarsi di aggiungere le colonne alla tabella.|
|**5**   |Selezionare **Modifica colonne** per aggiungere o rimuovere colonne nella tabella. |
|**6**   |Selezionare **Filtro** per filtrare il report in base al nome utente o al tipo di chiamata |
|**7**   |Selezionare **Schermo intero** per visualizzare il report in modalità a schermo intero. |
|**8**   |È possibile esportare il report in un file CSV per l'analisi offline. Fare **clic su Esporta Excel** e quindi nella scheda **Download** fare clic su **Scarica** per scaricare il report quando è pronto.|

### <a name="direct-routing"></a>Routing diretto

[! [Screenshot del report sull'utilizzo PSTN di Routing diretto nell'interfaccia di amministrazione] (.. /media/teams-reports-pstn-usage-direct-routing-with-callouts.png "Screenshot del report sull'utilizzo PSTN di Routing diretto nell'interfaccia di amministrazione di Microsoft Teams con callout numerati".](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png#lightbox)

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Il report può essere visualizzato per le tendenze degli ultimi 7 o 28 giorni. |
|**2**   |Ogni report ha una data in cui è stato generato. In genere, i report presentano una latenza di 24-48 ore dal momento dell'attività. |
|**3**   |L'asse X è l'intervallo di date selezionato per il report specifico. L'asse Y è il numero totale di chiamate nel periodo di tempo selezionato.<br>Passare il puntatore del mouse sul punto in una data specifica per visualizzare il totale delle chiamate in tale data.  |
|**4**   |La tabella fornisce una descrizione dell'utilizzo PSTN per ogni chiamata. <ul><li>**Timestamp (UTC)** è l'ora di inizio della chiamata.</li><li>**Nome visualizzato** è il nome visualizzato dell'utente. È possibile fare clic sul nome visualizzato per passare alla pagina delle impostazioni dell'utente nell'Microsoft Teams di amministrazione. Il nome può anche essere il nome di un bot, ad esempio coda di chiamata o Operatore automatico. </li><li>**L'indirizzo SIP** è l'indirizzo SIP dell'utente o di un bot che ha ricevuto o effettuato la chiamata.</li><li>**Numero chiamante** è il numero dell'utente o del bot che ha effettuato la chiamata. </li><li>**Numero chiamato è** il numero dell'utente o del bot che ha ricevuto la chiamata. In una chiamata in ingresso a un Teams utente sarà l'utente Teams, in una chiamata in uscita da un utente Teams sarà l'utente PSTN. </li><li>**Tipo di** chiamata indica se la chiamata è stata una chiamata PSTN in uscita o in ingresso e il tipo di chiamata, ad esempio una chiamata da parte di un utente o un'audioconferenza. I tipi di chiamata visualizzati includono:<br><br>**Teams tipi di chiamata utente**<ul><li>**dr_in** - l'utente ha ricevuto una chiamata PSTN in ingresso</li><li>**dr_out** - l'utente ha effettuato una chiamata PSTN in uscita</li><li>**dr_out_user_conf** : l'utente ha aggiunto un partecipante PSTN alla chiamata</li><li>**user_out_transfer** - l'utente ha trasferito la chiamata a un numero PSTN</li><li>**dr_out_user_forwarding** : l'utente ha inoltrato la chiamata a un numero PSTN</li><li>**dr_out_user_transfer** - l'utente ha trasferito la chiamata a un numero PSTN</li><li>**dr_emergency_out** - l'utente ha effettuato una chiamata di emergenza</li></ul><br>**Teams di chiamata dei bot**<ul><li>**dr_in_ucap:** una chiamata PSTN in ingresso a un bot Teams, ad esempio l'operatore automatico o la coda di chiamata</li><li>**dr_out_ucap:** una chiamata PSTN in uscita da un bot Teams, ad esempio l'operatore automatico o la coda di chiamata</li></ul><br><li>**Chiamato a** è il numero dell'utente che ha ricevuto la chiamata.</li><li>Ora di inizio **(UTC)** è l'ora in cui il proxy SIP ha ricevuto la risposta finale (messaggio SIP "200 OK") da SBC in una chiamata in uscita (Teams/Bot a un utente PSTN) o dopo che il proxy SIP ha inviato l'invito all'hop successivo all'interno del backend di Teams in una chiamata in ingresso (Utente PSTN a un Teams/Bot). </li><li>Ora di invito **(UTC)** è l'ora in cui l'invito iniziale è stato inviato a una chiamata in uscita da un utente di Teams o da una chiamata bot a SBC o ricevuto in una chiamata in ingresso a un Teams o a una chiamata bot dal componente proxy SIP del routing diretto da SBC.</li><li>**Ora di errore (UTC)** è l'ora in cui la chiamata non è riuscita. Solo per le chiamate non riuscite. Il codice SIP finale, il sottocodice Microsoft finale e la frase SIP finale forniscono i motivi per cui la chiamata non è riuscita e possono essere utili per la risoluzione dei problemi. </li><li>**Ora di fine (UTC)** è l'ora di fine della chiamata (solo per le chiamate riuscite).</li><li>**Durata** è il tempo per cui resta connessa la chiamata.</li><li>**Tipo di** numero è il tipo di numero di telefono dell'utente, ad esempio un servizio di numero verde. </li><li>**Bypass multimediale** indica se il trunk è stato abilitato per il bypass multimediale. </li> <li>**FQDN SBC** è il nome di dominio completo (FQDN) del Session Border Controller (SBC). </li><li>**L'area di Azure per i** supporti multimediali è il data center usato come percorso multimediale in una chiamata non bypass. </li><li>**L'area di Azure per** la segnalazione è il data center usato per la segnalazione sia per le chiamate di bypass che per le chiamate non bypass. </li><li>**Il tipo di** evento è il tipo di evento della chiamata. Verranno visualizzati Operazione riuscita per le chiamate riuscite e Tentativo di chiamate non riuscite. </li><li>**Il codice SIP finale** è il codice con cui è terminata la chiamata.</li><li>**Il sottocodice Microsoft finale** è un codice che indica azioni specifiche che si sono verificate.</li><li>**La frase SIP finale** è la descrizione del codice SIP e del sottocodice Microsoft.</li><li>**L'ID** di correlazione è un identificatore univoco per la chiamata che è possibile usare quando si chiama il supporto tecnico Microsoft.</li><li>**L'ID di** correlazione condiviso è visibile solo nel file CSV scaricabile e non esiste nel portale. L'ID di correlazione condiviso è presente in almeno due chiamate correlate. Vedere la descrizione dettagliata più avanti.</li></ul> Per visualizzare le informazioni desiderate nella tabella, assicurarsi di aggiungere le colonne alla tabella.|
|**5**   |Selezionare **Modifica colonne** per aggiungere o rimuovere colonne nella tabella. |
|**6**   |Selezionare **Schermo intero** per visualizzare il report in modalità a schermo intero. |
|**7**   |Selezionare **Esporta in Excel** per scaricare i dati in un file con valori delimitati da virgole (CSV) per l'analisi offline o per usarli come input per il sistema di fatturazione. |

#### <a name="callercallee-fields-considerations"></a>Considerazioni sui campi Chiamante/Chiamato

A seconda della direzione della chiamata, i nomi chiamante o chiamato possono contenere numeri non E164.

Questi campi possono derivare dagli SBC del cliente. Esistono tre formati che il SBC può inviare al routing diretto: numeri E.164, numeri non E.164 e stringhe.

- Numero di telefono E.164 da un utente che ha un numero E.164 a un utente che ha anche un numero E.164. 
- Chiama da un numero diverso da E.164. Un utente di un PBX di terze parti connesso con Routing diretto effettua una chiamata a un Teams utente. In questo caso, il numero chiamante potrebbe essere qualsiasi numero diverso da E.164, ad esempio +1001. 
- Uno spammer chiama e non presenta un numero, ma solo un nome, ad esempio "Internal Revenue Service". Questa stringa verrà visualizzata nei report.

#### <a name="about-shared-correlation-id"></a>Informazioni sull'ID di correlazione condivisa

L'ID di correlazione condivisa è presente solo nel file di Excel esportato scaricato e indica che due o più chiamate sono correlate. Di seguito sono illustrati i diversi scenari e quando è presente l'ID di correlazione condivisa.

1.    Utente PSTN 1 in un endpoint PSTN denominato Teams Utente 1 nel client Teams, tipo di chiamata Dr_In, ID di correlazione 57f28917-42k5-4c0c-9433-79734873f2ac, nessun ID di correlazione condiviso.
2.    Teams Utente 1 in un client Teams denominato Utente PSTN 1 in un endpoint PSTN, tipo di chiamata Dr_Out 2c12b8ca-62eb-4c48-b68d-e451f518ff4, nessun ID di correlazione condiviso.
3.    Utente PSTN 1 in un endpoint PSTN denominato Teams utente 2 in Teams client, tipo di chiamata Dr_In f45e9a25-9f94-46e7-a457-84f5940efde9, ID di correlazione condiviso f45e9a25-9f94-46e7-a457-84f5940efde9.
4.    Chiamata esistente 3 con ID di correlazione "f45e9a25-9f94-46e7-a457-84f5940efde9". Utente PSTN 1 in una chiamata con Teams utente 2. Teams L'utente 2 ha trasferito (non vedente o consultivo) una chiamata a Teams utente PSTN, tipo di chiamata Dr_Out_User_Transfer 45a1da7c-9e97-481a-8a05-3fe19a9a77e0, ID di correlazione condiviso f45e9a25-9f94-46e7-a457-84f5940efde9.

## <a name="exporting-the-reports"></a>Esportazione dei report
Fare **clic su Esporta Excel** e quindi nella scheda **Download** fare clic su **Scarica** per scaricare il report quando è pronto. Il completamento del processo di esportazione può richiedere da alcuni secondi a diversi minuti, a seconda della quantità di dati.

Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. I file esportati contengono campi aggiuntivi non disponibili nel report online. Possono essere usati per la risoluzione dei problemi e per i flussi di lavoro automatizzati.

 Si riceverà un file ZIP denominato "**Calls.Export. `[identifier]`.zip**", con l'identificatore un ID univoco per l'esportazione che può essere usato per la risoluzione dei problemi.

Se si hanno piani per chiamate e instradamento diretto, il file esportato potrebbe contenere dati per entrambi i prodotti. Il file di report sull'utilizzo PSTN avrà il nome file "**PSTN.calls. `[UTC date]`.csv**" e Direct Routing "**DirectRouting.calls. `[UTC date]`.csv**".

 Oltre ai file PSTN e Direct Routing, l'archivio contiene il file "**parameters.js**", con l'intervallo di tempo e le funzionalità di esportazione selezionati.

I file esportati sono in formato CSV (Comma Separated Values), conforme allo standard [RFC 4180.](https://tools.ietf.org/html/rfc4180) I file possono essere aperti in Excel o in qualsiasi altro editor conforme agli standard senza richiedere alcuna trasformazione.

La prima riga del file CSV contiene nomi di colonna. Tutte le date sono UTC e in [formato ISO 8601.](https://en.wikipedia.org/wiki/ISO_8601)

### <a name="exported-pstn-usage-report"></a>Report sull'utilizzo PSTN esportato

 È possibile esportare dati fino a un anno dalla data corrente, a meno che le normative specifiche del paese non impedino la conservazione dei dati per 12 mesi.

> [!div class="has-no-wrap"]  
> | # | Nome | [Tipo di dati (SQL Server)](/sql/t-sql/data-types/data-types-transact-sql) | Descrizione |
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
> | 13 | Ora inizio | `datetimeoffset` | Ora di inizio della chiamata |
> | 14 | Ora di fine | `datetimeoffset` | Ora di fine chiamata |
> | 15 | Durata secondi | `int` | Per quanto tempo è stata connessa la chiamata |
> | 16 | Quota di connessione | `numeric(16, 2)` | Prezzo delle commissioni di connessione |
> | 17 | Addebito | `numeric(16, 2)` | Importo o costo della chiamata addebitata sul tuo account |
> | 18 | Valuta | `nvarchar(3)` | Tipo di valuta usata per calcolare il costo della chiamata ([ISO 4217](https://en.wikipedia.org/wiki/ISO_4217)) |
> | 19 | Funzionalità | `nvarchar(32)` | La licenza usata per la chiamata |

### <a name="exported-direct-routing-usage-report"></a>Report sull'utilizzo del routing diretto esportato

È possibile esportare i dati fino a cinque mesi (150 giorni) dalla data corrente, a meno che le normative specifiche del paese non proibino la conservazione dei dati per tale periodo.

> [!div class="has-no-wrap"]  
> | # | Nome | [Tipo di dati (SQL Server)](/sql/t-sql/data-types/data-types-transact-sql) | Descrizione |
> | :-: | :-: | :-: |:------------------- |
> | 0 | CorrelationId | `uniqueidentifier` | Identificatore univoco della chiamata |
> | 1 | Indirizzo SIP | `nvarchar(128)` | Indirizzo dell'utente o del bot che ha effettuato o ricevuto la chiamata.<br/>Si noti che si tratta in realtà di UserPrincipalName (UPN, nome di accesso) in Azure Active Directory, che in genere corrisponde all'indirizzo SIP |
> | 2 | Nome visualizzato | `nvarchar(128)` | Il nome di un utente o di un bot chiamante (ad esempio coda di chiamata o Operatore automatico) impostato in interfaccia di amministrazione di Microsoft 365 |
> | 3 | Paese utente | `nvarchar(2)` | Codice paese dell'utente, [ISO 3166-1 alfa-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | Ora di invito | `datetimeoffset` | Quando l'invito iniziale viene inviato Teams uscita da una chiamata utente o bot all'SBC o viene ricevuta in ingresso a Teams o una chiamata bot dal componente proxy SIP di Routing diretto da SBC |
> | 5 | Ora di inizio | `datetimeoffset` | Ora in cui il proxy SIP ha ricevuto la risposta finale (messaggio SIP "200 OK") da SBC in uscita (Teams/Bot a un utente PSTN) o dopo che il proxy SIP ha inviato l'invito all'hop successivo all'interno di un back-end Teams una chiamata in ingresso (utente PSTN a un Teams/Bot).<br/>Per le chiamate non riuscite e senza risposta, questo può essere uguale al tempo di invito o di errore |
> | 6 | Tempo di errore | `datetimeoffset` | Esiste solo per le chiamate non riuscite (non completamente stabilite) |
> | 7 | Ora di fine | `datetimeoffset` | Esiste solo per le chiamate riuscite (completamente stabilite). Ora di fine della chiamata |
> | 8 | Durata (secondi) | `int` | Durata della chiamata |
> | 9 | Operazione riuscita | `nvarchar(3)` | Sì/No. Operazione riuscita o tentativo |
> | 10 | Numero chiamante | `nvarchar(32)` | Numero dell'utente o del bot che ha effettuato la chiamata. In ingresso a una chiamata utente del team sarà un utente PSTN, in uscita da Teams chiamata utente sarà il numero Teams utente |
> | 12 | Numero del chiamato | `nvarchar(32)` | Numero dell'utente o del bot che ha ricevuto la chiamata. In ingresso a una chiamata utente del team sarà l'utente Teams, in uscita da Teams chiamata utente sarà l'utente PSTN |
> | 13 | Tipo di chiamata | `nvarchar(32)` | Tipo di chiamata e direzione |
> | 14 | Area geografica di Azure per elementi multimediali | `nvarchar(8)` | Data center usato per il percorso multimediale nelle chiamate non bypass |
> | 15 | Area geografica di Azure per la segnalazione | `nvarchar(8)` | Data center usato per la segnalazione sia per le chiamate bypass che per le chiamate non bypass |
> | 16 | Codice SIP finale | `int` | Codice con cui è terminata la chiamata, [RFC 3261](https://tools.ietf.org/html/rfc3261) |
> | 17 | Sottocodice Microsoft finale | `int` | Oltre ai codici SIP, Microsoft ha sottocodice che indicano il problema specifico |
> | 18 | Frase SIP finale | `nvarchar(256)` | Descrizione del codice SIP e del sottocodice Microsoft |
> | 19 | SBC FQDN | `nvarchar(64)` | Nome di dominio completo del controller di bordo della sessione |
> | 20 | Bypass multimediale | `nvarchar(3)` | Sì/No. Indica se il trunk è stato abilitato o meno per il bypass multimediale |
> | 21 | ID di correlazione condiviso | `uniqueidentifier` | Indica che due o più chiamate sono correlate |


## <a name="related-topics"></a>Argomenti correlati

- [Analisi e creazione dei report di Teams](teams-reporting-reference.md).
---
title: Report utilizzo PSTN di Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni su come usare il report utilizzo PSTN di Teams nell'interfaccia di amministrazione di Microsoft Teams per ottenere una panoramica dell'utilizzo di chiamate e audioconferenze nell'organizzazione.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-voice
ms.openlocfilehash: 1539f679225334f71855300a54c4fba950ddd8f8
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267631"
---
# <a name="microsoft-teams-pstn-usage-report"></a>Report utilizzo PSTN di Microsoft Teams

Il report sull'utilizzo di Teams PSTN (Public Switched Telephone Network) nell'interfaccia di amministrazione di Microsoft Teams offre una panoramica delle attività relative a chiamate e audioconferenze nell'organizzazione. È possibile visualizzare le attività di chiamata dettagliate per i Piani per chiamate se si utilizza Microsoft come gestore di telefonia e per Direct Routing se si utilizza il proprio gestore di telefonia.

La scheda **Piani per** chiamate mostra informazioni che includono il numero di minuti che gli utenti hanno trascorso in chiamate PSTN in entrata e in uscita e il costo di queste chiamate. La scheda **Routing diretto** mostra informazioni tra cui l'indirizzo SIP e l'ora di inizio e di fine della chiamata. Usare le informazioni in questo report per ottenere informazioni più approfondite sull'utilizzo di PSTN nell'organizzazione e consentire di analizzare, pianificare e prendere decisioni aziendali.

> [!NOTE]
> Se si ha un piano per chiamate Telstra o Softbank, non verranno visualizzati record dei dettagli delle chiamate nel report utilizzo PSTN. Contatta Telstra o Softbank per le tue esigenze di reporting. 

## <a name="view-the-pstn-usage-report"></a>Visualizzare il report utilizzo PSTN

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams fare clic su **Analisi & report** > **utilizzo**. Nella scheda **Visualizza report** , in **Report**, selezionare **Report utilizzo PSTN**.
2. In **Intervallo di date** selezionare un intervallo predefinito di 7 o 28 giorni oppure impostare un intervallo personalizzato e quindi selezionare **Esegui report**.

## <a name="interpret-the-report"></a>Interpretare il report

### <a name="calling-plans"></a>Piani di chiamata

   ![Screenshot del report utilizzo PSTN Piani per chiamate nell'interfaccia di amministrazione](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png)![Screenshot del report utilizzo PSTN nell'interfaccia di amministrazione di Microsoft Teams con callout numerati](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png#lightbox)

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Il report può essere visualizzato per le tendenze degli ultimi 7, 28 giorni o per un intervallo di date personalizzato impostato. |
|**2**   |Ogni report ha una data per la generazione. In genere, i report presentano una latenza di 24-48 ore dal momento dell'attività. |
|**3**   |L'asse X è l'intervallo di date selezionato per il report specifico. L'asse Y è il numero totale di chiamate nel periodo di tempo selezionato. <br>Passa il puntatore del mouse sul punto in una data specificata per visualizzare il totale delle chiamate in tale data.  |
|**4**   |La tabella fornisce un'analisi dell'utilizzo di PSTN per chiamata. <ul><li>**Il timestamp (UTC)** è l'ora di avvio della chiamata.</li><li>**Nome visualizzato** è il nome visualizzato dell'utente. È possibile fare clic sul nome visualizzato per passare alla pagina delle impostazioni dell'utente nell'interfaccia di amministrazione di Microsoft Teams.</li><li>**Nome utente** è il nome di accesso dell'utente.</li><li>**Numero di telefono** è il numero che ha ricevuto la chiamata per le chiamate in ingresso o il numero comporre per le chiamate in uscita.</li><li>**Il tipo di** chiamata indica se la chiamata era in uscita o in ingresso PSTN e il tipo di chiamata, ad esempio una chiamata effettuata da un utente o un'audioconferenza. I tipi di chiamata che possono essere visualizzati includono:<br><br>**Tipi di chiamata utente di Teams**<ul><li>**user_in** : l'utente ha ricevuto una chiamata PSTN in ingresso</li><li>**user_out** : l'utente ha effettuato una chiamata PSTN in uscita</li><li>**user_out_conf** : l'utente ha aggiunto due o più partecipanti PSTN alla chiamata, ad esempio una conferenza telefonica a tre vie</li><li>**user_out_transfer** : l'utente ha trasferito la chiamata a un numero PSTN</li><li>**user_out_forwarding** : l'utente ha inoltrato la chiamata a un numero PSTN</li><li>**conf_in** : chiamata in ingresso al bridge di audioconferenza</li><li>**conf_out** : una chiamata in uscita dal bridge di audioconferenza in genere per aggiungere un numero PSTN alla conferenza</li><li>**unassigned_in** : chiamata PSTN in entrata tramite Piano per chiamate a un numero non assegnato</li></ul><br>**Tipi di chiamata bot di Teams**<ul><li>**ucap_in** - una chiamata PSTN in ingresso al bot di Teams, ad esempio operatore automatico o coda di chiamata</li><li>**ucap_out** - una chiamata PSTN in uscita da un bot di Teams, ad esempio un operatore automatico o una coda di chiamata</li></ul><br><li>**Chiamato a** è il numero chiamato.</li><li>**Il paese o l'area geografica** è il paese o l'area geografica chiamata.</li><li>**Chiamato da** è il numero che ha effettuato la chiamata.</li><li>**Dal paese o area geografica** si trova il paese o l'area geografica da cui è stata effettuata la chiamata.</li><li>**L'addebito** è l'importo o il costo della chiamata addebitata sul tuo account. </li><li>**Valuta** è il tipo di valuta usato per calcolare il costo della chiamata. </li><li>**Durata** è il tempo per cui resta connessa la chiamata.</li><li>**Nazionale/Internazionale** indica se la chiamata è stata nazionale (all'interno di un paese o area geografica) o internazionale (al di fuori di un paese o area geografica) in base alla posizione dell'utente.</li><li>**ID chiamata** è l'ID della chiamata. Si tratta di un identificatore per la chiamata che puoi usare quando chiami supporto tecnico Microsoft.</li><li>**Tipo di numero** è il tipo di numero di telefono dell'utente, ad esempio un servizio di numero verde. </li><li>**Il paese o l'area geografica** è la posizione di utilizzo. </li> <li>**ID conferenza** è l'ID conferenza dell'audioconferenza. </li><li>**Capacità** è la licenza usata per la chiamata. I tipi di licenza che possono essere visualizzati includono:<ul><li>**MCOEV o MCOEV_VIRTUALUSER o MCOEV_VIRTUALUSER_GOV** - Applicazioni vocali come Operatore automatico o Code di chiamata</li><li>**FREECALL** - In caso di problemi tecnici che impediscono di fissare i prezzi di una chiamata, la chiamata viene fornita gratuitamente e apparirà con questa funzionalità</li><li>**MCOPSTN1** - Piano per chiamate nazionali (piani per 3000 min USA/1200 min UE)</li><li>**MCOPSTN2** - Piano per chiamate internazionali</li><li>**MCOPSTN5** - Piano per chiamate nazionali (piano per chiamate da 120 minuti)</li><li>**MCOPSTN6** - Piano per chiamate nazionali (piano per chiamate da 240 minuti)</li><li>**MCOPSTN8** - Piano per chiamate nazionali 120 min per utente (non raggruppato tra gli utenti come gli altri piani per chiamate)</li><li>**MCOPSTN9** - Piano per chiamate internazionali</li><li>**MCOPSTNCAP** - Telefono area comune</li><li>**MCOPSTNPP** - Crediti comunicazioni</li><li>**MCOMEETADD** - Audioconferenza</li><li>**MCOMEETADD_DIALOUT_US** - Piano di chiamata in uscita Stati Uniti e Canada per audioconferenze</li><li>**MCOMEETADD_CN_GLOBAL** - Audioconferenza per utenti non cinesi</li><li>**MCOMEETADD_TATA** - Tata Communications Connections</li><li>**MCOMEETACPEA** - Audioconferenza con tariffa al minuto </li><li>**MCOMEETACPEA_GOV** - Audioconferenza con tariffa al minuto per enti pubblici</li></ul></li></ul> Per visualizzare le informazioni desiderate nella tabella, assicurarsi di aggiungere le colonne alla tabella.|
|**5**   |Selezionare **Modifica colonne** per aggiungere o rimuovere colonne nella tabella. |
|**6**   |Selezionare **Filtro** per filtrare il report in base al nome utente o al tipo di chiamata. |
|**7**   |Selezionare **Schermo intero** per visualizzare il report in modalità schermo intero. |
|**8**   |È possibile esportare il report in un file CSV per l'analisi offline. Fare clic su **Esporta in Excel** e quindi nella scheda **Download** fare clic su **Scarica** per scaricare il report quando è pronto.|

### <a name="direct-routing"></a>Routing diretto

   ![Screenshot del report di utilizzo PSTN routing diretto nell'interfaccia di amministrazione](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png)![Screenshot del report di utilizzo PSTN routing diretto nell'interfaccia di amministrazione di Microsoft Teams con callout numerati](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png#lightbox)

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Il report può essere visualizzato per le tendenze degli ultimi 7 o 28 giorni. |
|**2**   |Ogni report ha una data per la generazione. In genere, i report presentano una latenza di 24-48 ore dal momento dell'attività. |
|**3**   |L'asse X è l'intervallo di date selezionato per il report specifico. L'asse Y è il numero totale di chiamate nel periodo di tempo selezionato.<br>Passa il puntatore del mouse sul punto in una data specificata per visualizzare il totale delle chiamate in tale data.  |
|**4**   |La tabella fornisce un'analisi dell'utilizzo di PSTN per chiamata. <ul><li>**Il timestamp (UTC)** è l'ora di avvio della chiamata.</li><li>**Nome visualizzato** è il nome visualizzato dell'utente. È possibile fare clic sul nome visualizzato per passare alla pagina delle impostazioni dell'utente nell'interfaccia di amministrazione di Microsoft Teams. Il nome può anche essere il nome di un bot, ad esempio coda di chiamata o Operatore automatico cloud. </li><li>**Indirizzo SIP** è l'indirizzo SIP dell'utente o di un bot che ha ricevuto o effettuato la chiamata.</li><li>**Numero chiamante** è il numero dell'utente o del bot che ha effettuato la chiamata. </li><li>**Numero chiamante** è il numero dell'utente o del bot che ha ricevuto la chiamata. In una chiamata in ingresso a un utente di Teams sarà l'utente di Teams, in una chiamata in uscita da un utente di Teams sarà l'utente PSTN. </li><li>**Il tipo di** chiamata indica se la chiamata era in uscita o in ingresso PSTN e il tipo di chiamata, ad esempio una chiamata effettuata da un utente o un'audioconferenza. I tipi di chiamata che possono essere visualizzati includono:<br><br>**Tipi di chiamata utente di Teams**<ul><li>**dr_in** : l'utente ha ricevuto una chiamata PSTN in ingresso</li><li>**dr_out** : l'utente ha effettuato una chiamata PSTN in uscita</li><li>**dr_out_user_conf** : l'utente ha aggiunto un partecipante PSTN alla chiamata</li><li>**dr_out_user_forwarding** : l'utente ha inoltrato la chiamata a un numero PSTN</li><li>**dr_out_user_transfer** : l'utente ha trasferito la chiamata a un numero PSTN</li><li>**dr_emergency_out** - l'utente ha effettuato una chiamata di emergenza</li><li>**dr_unassigned_in** : chiamata PSTN in ingresso tramite routing diretto a un numero non assegnato</li></ul><br>**Tipi di chiamata bot di Teams**<ul><li>**dr_in_bot** - una chiamata PSTN in ingresso a un bot di Teams, ad esempio un operatore automatico o una coda di chiamata</li><li>**dr_out_bot** - una chiamata PSTN in uscita da un bot di Teams, ad esempio un operatore automatico o una coda di chiamata</li></ul><br><li>**Chiamato a** è il numero dell'utente che ha ricevuto la chiamata.</li><li>**L'ora di inizio (UTC)** è l'ora in cui il proxy SIP ha ricevuto la risposta finale (messaggio SIP "200 OK") da SBC in una chiamata in uscita (Teams/Bot a un utente PSTN) o dopo che il proxy SIP ha inviato l'invito all'hop successivo all'interno del back-end di Teams in una chiamata in ingresso (Utente PSTN a Teams/Bot). </li><li>**Ora di invito (UTC)** è l'ora in cui l'invito iniziale è stato inviato in una chiamata in uscita da un utente o bot di Teams all'SBC o ricevuto in una chiamata in ingresso a una chiamata teams o bot dal componente proxy SIP del routing diretto da SBC.</li><li>**Ora errore (UTC)** è l'ora in cui la chiamata non è riuscita. Solo per le chiamate non riuscite. Il codice SIP finale, il sottocodice Microsoft finale e la frase SIP finale forniscono i motivi per cui la chiamata ha avuto esito negativo e possono essere utili per la risoluzione dei problemi. </li><li>**Ora di fine (UTC)** è l'ora di fine della chiamata (solo per le chiamate riuscite).</li><li>**La durata** è il tempo per cui la chiamata è stata connessa, dall'invito al termine della chiamata o dall'errore. Per l'inoltro di chiamata, la durata include lo squillo nella coda di chiamata.</li><li>**Tipo di numero** è il tipo di numero di telefono dell'utente, ad esempio un servizio di numero verde. </li><li>**Il bypass multimediale** indica se il trunk è stato abilitato per il bypass multimediale. </li> <li>**FQDN SBC** è il nome di dominio completo (FQDN) del controller di bordo della sessione (SBC). </li><li>**L'area geografica di Azure per elementi multimediali** è il data center usato come percorso multimediale in una chiamata non bypass. </li><li>**L'area geografica di Azure per il traffico di segnalazione** è il data center usato per la segnalazione sia per le chiamate di bypass che per le chiamate non di bypass. </li><li>**Tipo di evento** è il tipo di evento della chiamata. Vedrai l'opzione Operazione riuscita per le chiamate riuscite e Tentativo per le chiamate non riuscite. </li><li>**Il codice SIP finale** è il codice con cui è terminata la chiamata.</li><li>**Il sottocodice Microsoft finale** è un codice che indica azioni specifiche che si sono verificate.</li><li>**La frase SIP finale** è la descrizione del codice SIP e del sottocodice Microsoft.</li><li>**L'ID di correlazione** è un identificatore univoco per la chiamata che è possibile usare quando si chiama supporto tecnico Microsoft.</li><li>**L'ID di correlazione condiviso** è visibile solo nel file CSV scaricabile e non esiste nel portale. L'ID di correlazione condiviso esiste in almeno due chiamate correlate. Vedi la descrizione dettagliata di seguito.</li></ul> Per visualizzare le informazioni desiderate nella tabella, assicurarsi di aggiungere le colonne alla tabella.|
|**5**   |Selezionare **Modifica colonne** per aggiungere o rimuovere colonne nella tabella. |
|**6**   |Selezionare **Schermo intero** per visualizzare il report in modalità schermo intero. |
|**7**   |Selezionare **Esporta in Excel** per scaricare i dati in un file separato da virgola (CSV) per l'analisi offline o per usarli come input per il sistema di fatturazione. |

#### <a name="callercallee-fields-considerations"></a>Considerazioni relative ai campi chiamante/destinatario chiamata

A seconda della direzione della chiamata, i nomi del chiamante o del destinatario chiamata possono contenere numeri non E164.

Questi campi possono provenire da SBC del cliente. Esistono tre formati che SBC può inviare a Direct Routing: numeri E.164, numeri non E.164 e stringhe.

- Numero di telefono E.164 di un utente che ha un numero E.164 a un utente che ha anche un numero E.164. 
- Chiama da un numero non E.164. Un utente da un PBX di terze parti interconnesso con Direct Routing effettua una chiamata a un utente di Teams. In questo caso, il numero del chiamante potrebbe essere qualsiasi numero diverso da E.164, ad esempio +1001. 
- Uno spammer chiama e non presenta un numero, ma solo un nome, ad esempio "Internal Revenue Service". Questa stringa verrà visualizzata nei report.

#### <a name="phone-number-obfuscation"></a>Offuscamento del numero di telefono
I requisiti di privacy per paese includono l'offuscamento dei numeri di telefono esterni (non di proprietà del cliente). Le tre o quattro ultime cifre del numero di telefono vengono sostituite con asterischi (+123 456789***). 

Per le chiamate in arrivo, il numero del chiamante viene mascherato, per le chiamate in uscita il numero del destinatario della chiamata viene mascherato. Si applica ai report PSTN e Direct Routing in Tenant Amministrazione Center, all'esportazione dei dati e ai registri delle chiamate disponibili tramite Microsoft Graph.

L'offuscamento si basa sulla posizione dell'organizzazione (paese). I numeri di telefono completi vengono visualizzati per i paesi non elencati nella tabella seguente:

| Paese | Numero di cifre di offuscamento |
| :-: | :- |
|BE - Belgio | 3 |
|CH - Svizzera | 4 |
|DE - Germania | 3 |
|DK - Danimarca | 3 |
|ES - Spagna | 3 |
|FI - Finlandia | 3 |
|FR - Francia | 4 |
|IT - Italia | 3 |
|NL - Paesi Bassi | 3 |
|NO - Norvegia | 3 |
|SE - Svezia | 3 |

#### <a name="about-shared-correlation-id"></a>Informazioni sull'ID di correlazione condiviso

L'ID di correlazione condiviso esiste solo nel file di Excel esportato scaricato e indica che due o più chiamate sono correlate. Di seguito vengono illustrati i diversi scenari e quando è presente l'ID di correlazione condiviso.

1.    PSTN User 1 su un endpoint PSTN chiamato Teams User 1 su Teams client, tipo di chiamata Dr_In, ID di correlazione 57f28917-42k5-4c0c-9433-79734873f2ac, nessun ID di correlazione condiviso.
2.    Utente di Teams 1 sul client Teams denominato Utente PSTN 1 su un endpoint PSTN, tipo di chiamata Dr_Out 2c12b8ca-62eb-4c48-b68d-e451f518ff4, nessun ID di correlazione condiviso.
3.    Utente PSTN 1 in un endpoint PSTN denominato utente 2 di Teams sul client Teams, tipo di chiamata Dr_In f45e9a25-9f94-46e7-a457-84f5940efde9, ID correlazione condivisa f45e9a25-9f94-46e7-a457-84f5940efde9.
4.    Chiamata 3 esistente con ID di correlazione "f45e9a25-9f94-46e7-a457-84f5940efde9". PstN User 1 in una chiamata con Teams User 2. L'utente di Teams 2 ha trasferito (non vedente o consultata) una chiamata a Teams o utente PSTN, tipo di chiamata Dr_Out_User_Transfer 45a1da7c-9e97-481a-8a05-3fe19a9a77e0, ID di correlazione condiviso f45e9a25-9f94-46e7-a457-84f5940efde9.

## <a name="exporting-the-reports"></a>Esportazione dei report
Fare clic su **Esporta in Excel** e quindi nella scheda **Download** fare clic su **Scarica** per scaricare il report quando è pronto. Il completamento del processo di esportazione può richiedere da pochi secondi a diversi minuti, a seconda della quantità di dati.

Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. I file esportati contengono campi aggiuntivi non disponibili nel report online. Questi possono essere usati per la risoluzione dei problemi e flussi di lavoro automatizzati.

 Si riceverà un file ZIP denominato "**Calls.Export.`[identifier]`.zip**", con l'identificatore come ID univoco per l'esportazione che può essere utilizzato per la risoluzione dei problemi.

Se hai sia Piani per chiamate che Routing diretto, il file esportato potrebbe contenere dati per entrambi i prodotti. Il file del report utilizzo PSTN avrà il nome file "**PSTN.calls.`[UTC date]`.csv**" e Routing diretto "**DirectRouting.calls.`[UTC date]`.csv**".

 Oltre ai file PSTN e Direct Routing, l'archivio contiene il file "**parameters.json**", con l'intervallo di tempo e le funzionalità di esportazione selezionati.

I file esportati sono in formato CSV (Comma Separated Values), compatibile con lo standard [RFC 4180](https://tools.ietf.org/html/rfc4180) . I file possono essere aperti in Excel o in qualsiasi altro editor conforme agli standard senza richiedere trasformazioni.

La prima riga del file CSV contiene i nomi di colonna. Tutte le date sono UTC e in formato [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) .

### <a name="exported-pstn-usage-report"></a>Report sull'utilizzo pstn esportato

 È possibile esportare i dati fino a un anno dalla data corrente, a meno che le normative specifiche del paese non proibiscano la conservazione dei dati per 12 mesi.

> [!div class="has-no-wrap"]  
> | # | Nome | [Tipo di dati (SQL Server)](/sql/t-sql/data-types/data-types-transact-sql) | Descrizione |
> | :-: | :-: | :-: |:------------------- |
> | 0 | UsageId | `uniqueidentifier` | Identificatore di chiamata univoco |
> | 1 | ID chiamata | `nvarchar(64)` | Identificatore di chiamata. Non è garantito che sia univoco |
> | 2 | ID conferenza | `nvarchar(64)` | ID dell'audioconferenza |
> | 3 | Posizione utente | `nvarchar(2)` | Codice paese dell'utente, [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | AAD ObjectId | `uniqueidentifier` | Chiamata dell'ID utente in Azure Active Directory.<br/> Queste e altre informazioni utente saranno null/vuote per i tipi di chiamata bot (ucap_in, ucap_out) |
> | 5 | Upn | `nvarchar(128)` | UserPrincipalName (nome di accesso) in Azure Active Directory.<br/>In genere corrisponde all'indirizzo SIP dell'utente e può corrispondere all'indirizzo di posta elettronica dell'utente |
> | 6 | Nome visualizzato utente | `nvarchar(128)` | Nome visualizzato dell'utente |
> | 7 | ID chiamante | `nvarchar(128)` | Numero che ha ricevuto la chiamata per le chiamate in ingresso o il numero chiamato per le chiamate in uscita. [Formato E.164](https://en.wikipedia.org/wiki/E.164) |
> | 8 | Tipo di chiamata | `nvarchar(32)` | Se la chiamata era una chiamata PSTN in uscita o in ingresso e il tipo di chiamata, ad esempio una chiamata effettuata da un utente o un'audioconferenza |
> | 9 | Tipo di numero | `nvarchar(16)` | Tipo di numero di telefono dell'utente, ad esempio un servizio di numero verde |
> | 10 | Nazionali/Internazionali | `nvarchar(16)` | Se la chiamata era nazionale (all'interno di un paese o area geografica) o internazionale (al di fuori di un paese o area geografica) in base alla posizione dell'utente |
> | 11 | Destination Dialed | `nvarchar(64)` | Paese o area geografica chiamata |
> | 12 | Numero di destinazione | `nvarchar(32)` | Numero comporre in formato [E.164](https://en.wikipedia.org/wiki/E.164) |
> | 13 | Ora inizio | `datetimeoffset` | Ora di inizio chiamata |
> | 14 | Ora fine | `datetimeoffset` | Ora di fine chiamata |
> | 15 | Durata secondi | `int` | Per quanto tempo è stata connessa la chiamata |
> | 16 | Tassa di connessione | `numeric(16, 2)` | Prezzo della commissione di connessione |
> | 17 | Carica | `numeric(16, 2)` | Importo del denaro o costo della chiamata addebitato sul tuo account |
> | 18 | Valuta | `nvarchar(3)` | Tipo di valuta utilizzata per calcolare il costo della chiamata ([ISO 4217](https://en.wikipedia.org/wiki/ISO_4217)) |
> | 19 | Funzionalità | `nvarchar(32)` | Licenza usata per la chiamata |

### <a name="exported-direct-routing-usage-report"></a>Report sull'utilizzo del routing diretto esportato

È possibile esportare dati fino a cinque mesi (150 giorni) dalla data corrente, a meno che le normative specifiche del paese non vietano la conservazione dei dati per tale periodo.

> [!div class="has-no-wrap"]  
> | # | Nome | [Tipo di dati (SQL Server)](/sql/t-sql/data-types/data-types-transact-sql) | Descrizione |
> | :-: | :-: | :-: |:------------------- |
> | 0 | Correlationid | `uniqueidentifier` | Identificatore di chiamata. Più gambe della stessa chiamata possono condividere lo stesso CorrelationId |
> | 1 | AAD ObjectId | `uniqueidentifier` | Chiamata dell'ID utente in Azure Active Directory.<br/> Questa e altre informazioni utente possono essere null/vuote per i tipi di chiamata bot |
> | 2 | Upn | `nvarchar(128)` | UserPrincipalName (nome di accesso, Azure Active Directory) dell'utente o del bot che ha effettuato o ricevuto la chiamata.<br/>In genere corrisponde all'indirizzo SIP dell'utente e può corrispondere all'indirizzo di posta elettronica dell'utente |
> | 3 | Nome visualizzato | `nvarchar(128)` | Il nome di un utente o di un bot di chiamata (ad esempio, Coda di chiamata o Operatore automatico) impostato in interfaccia di amministrazione di Microsoft 365 |
> | 4 | Paese utente | `nvarchar(2)` | Codice paese dell'utente, [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 5 | Ora invito | `datetimeoffset` | Quando l'invito iniziale viene inviato in uscita dall'utente o bot di Teams all'SBC o ricevuto in ingresso a Teams o chiamata bot dal componente proxy SIP del routing diretto da SBC |
> | 6 | Ora di inizio | `datetimeoffset` | Ora in cui il proxy SIP ha ricevuto la risposta finale (messaggio SIP "200 OK") da SBC in uscita (Teams/Bot a un utente PSTN) o dopo che il proxy SIP ha inviato l'invito all'hop successivo all'interno del back-end di Teams alla chiamata in ingresso (Utente PSTN a teams/bot).<br/>Per le chiamate non riuscite e senza risposta, questo può essere uguale al tempo di invito o di errore |
> | 7 | Ora errore | `datetimeoffset` | Esiste solo per le chiamate non riuscite (non completamente definite) |
> | 8 | Ora di fine | `datetimeoffset` | Esiste solo per le chiamate di successo (definite completamente). Ora in cui è terminata la chiamata |
> | 9 | Durata (secondi) | `int` | Durata della chiamata, dall'invito al termine della chiamata o dall'errore. Per l'inoltro di chiamata, la durata include lo squillo nella coda di chiamata. |
> | 10 | Successo | `nvarchar(3)` | Sì/No. Operazione completata o tentativo |
> | 11 | Numero chiamante | `nvarchar(32)` | Numero dell'utente o bot che ha effettuato la chiamata. In ingresso a una chiamata dell'utente del team sarà un utente PSTN, in uscita dalla chiamata dell'utente di Teams sarà il numero utente di Teams |
> | 12 | Numero destinatario chiamata | `nvarchar(32)` | Numero dell'utente o del bot che ha ricevuto la chiamata. In ingresso a una chiamata dell'utente del team sarà l'utente di Teams, in uscita dalla chiamata dell'utente di Teams sarà l'utente PSTN |
> | 13 | Tipo di chiamata | `nvarchar(32)` | Tipo e direzione della chiamata |
> | 14 | Area geografica di Azure per gli elementi multimediali | `nvarchar(8)` | Data center usato per il percorso multimediale in una chiamata non bypass |
> | 15 | Area geografica di Azure per il traffico di segnalazione | `nvarchar(8)` | Data center usato per la segnalazione sia per le chiamate di bypass che per le chiamate non bypass |
> | 16 | Codice SIP finale | `int` | Il codice con cui è terminata la chiamata, [RFC 3261](https://tools.ietf.org/html/rfc3261) |
> | 17 | Sottocodice Microsoft finale | `int` | Oltre ai codici SIP, Microsoft dispone di sottocodice propri che indicano il problema specifico |
> | 18 | Frase SIP finale | `nvarchar(256)` | Descrizione del codice SIP e del sottocodice Microsoft |
> | 19 | SBC FQDN | `nvarchar(64)` | Nome di dominio completo del controller dei confini della sessione |
> | 20 | Bypass multimediale | `nvarchar(3)` | Sì/No. Indica se il trunk è stato abilitato o meno per il bypass multimediale |
> | 21 | ID di correlazione condiviso | `uniqueidentifier` | Indica che due o più chiamate sono correlate |


## <a name="related-topics"></a>Argomenti correlati

- [Analisi e creazione dei report di Teams](teams-reporting-reference.md).
- [Report chiamate PSTN in Microsoft Graph](/graph/api/callrecords-callrecord-getpstncalls?view=graph-rest-1.0&tabs=http)
- [Report di routing diretto in Microsoft Graph](/graph/api/callrecords-callrecord-getdirectroutingcalls?view=graph-rest-1.0&tabs=http)

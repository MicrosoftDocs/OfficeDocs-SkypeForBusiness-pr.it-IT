---
title: Report cronologici aggiornati relativi all'operatore automatico e alla coda di chiamata
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
description: Informazioni su come usare l'operatore automatico di Teams aggiornato & report storico sulla coda di chiamata di Power BI per visualizzare i dati cronologici di Operatore automatico e Coda di chiamata.
ms.openlocfilehash: 780d6057960c96713ac67be3e189d7982fd2fa46
ms.sourcegitcommit: e9718ad7e23317d490b238b3801267cb2e6b26e2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2022
ms.locfileid: "69176693"
---
# <a name="updated-auto-attendant-and-call-queue-historical-reports"></a>Report cronologici aggiornati relativi all'operatore automatico e alla coda di chiamata

>[!NOTE]
> I clienti GCC HIgh e DOD devono continuare a usare v1.63 di [Operatore automatico & Call Queue Historical Reports (CQD)](aa-cq-cqd-historical-reports-v163.md).

Questo modello di Power BI fornisce tre report che consentono alle organizzazioni di segnalare il numero di chiamate elaborate da operatori automatici e code di chiamata.  Fornisce anche informazioni dettagliate sulle prestazioni dell'agente.

## <a name="v304-published-on-november-18-2022"></a>V3.0.4 data di pubblicazione: 18 novembre 2022

Il modello Power BI Operatore automatico & coda di chiamata fornisce i tre report seguenti:

- Il report [Operatore automatico](media/aa-cq-historical-report-sample-aa-v304.png) mostra i dati analitici per le chiamate in arrivo negli operatori automatici.
- Il report [Coda](media/aa-cq-historical-report-sample-cq-v304.png) di chiamata mostra i dati analitici per le chiamate che arrivano nelle code di chiamata.
- Il report [Sequenza temporale agente](media/aa-cq-historical-report-sample-at-v304.png) mostra una visualizzazione sequenza temporale degli agenti attivi nelle chiamate in coda di chiamata.

Questi report usano i dati del servizio Voice Applications Analytics Collector (VAAC).

## <a name="v3xx-prerequisites"></a>Prerequisiti V3.x.x

### <a name="power-bi-desktop"></a>Power BI Desktop

Devi aver installato Power BI Desktop. Puoi installare e usare la versione gratuita da [Microsoft Windows Store](https://aka.ms/pbidesktopstore).

La versione minima compatibile è 2.85.681.0 (settembre 2020).

### <a name="permissions-to-access-the-cqd-pipeline"></a>Autorizzazioni per accedere alla pipeline di Call Quality Dashboard

Anche se questa versione dei report non usa la pipeline di dati call quality dashboard (CQD), l'account usato per visualizzare i dati cronologici richiede comunque l'accesso al dashboard qualità chiamata. Per altre informazioni, vedere [Ruolo di accesso a Call Quality Dashboard](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).

- Questo requisito verrà rimosso in una versione futura.

## <a name="v3xx-installation"></a>Installazione V3.x.x 

I passaggi seguenti presuppongono che siano già stati installati Power BI Desktop nel computer e che l'account disponga delle autorizzazioni necessarie per accedere alla pipeline di dati di Call Quality Dashboard.

Eseguire le operazioni seguenti:

1. Scarica e salva il file [V3.0.4.zipTeams Auto Attendant & i rapporti cronologici della coda di chiamata ](https://www.microsoft.com/download/details.aspx?id=104623) nel computer.

2. Aprire il file ZIP.

3. Aprire il file modello `Teams Auto Attendant & Call Queue Historical Reports V3.0.4.pbit` . Power BI Desktop dovrebbe avviarsi.

4. Verrà chiesto di selezionare **l'origine dati**.  Selezionare la `api.interfaces.records.teams.microsoft.com` voce.

  :::image type="content" source="media/aa-cq-historical-report-01-v304.png" alt-text="Screenshot che seleziona il api.interfaces.records.teams.microsoft.com Data Soure":::

5. Verrà richiesto di accedere con un account. Selezionare **Account aziendale** e quindi **selezionare Accedi**.

  :::image type="content" source="media/aa-cq-historical-report-03-v300.png" alt-text="Screenshot che mostra l'accesso per V3.0.0.":::

6. Seleziona **Connetti** per aggiornare i dati.

> [!NOTE]
> Se si stava usando v1.63 o versioni precedenti, potrebbe verificarsi un errore quando v3.x.x tenta di recuperare i dati da VAAC.  Per risolvere questo errore, è necessario cancellare eventuali credenziali precedenti da Power BI.
> 
> 1. Aprire il modello v3.x.x per cancellare l'errore. 
> 1. Selezionare Opzioni **file** > **& Impostazioni Impostazioni** > **origine dati**.
> 1. Selezionare l'elenco a discesa **Cancella autorizzazioni** e quindi **selezionare Cancella tutte le autorizzazioni**.
> 1. Chiudere il modello dopo averlo cancellato e riavviare Power BI. Ti verrà chiesto di autorizzare di nuovo. 

## <a name="data-latency-for-auto-attendant-and-call-queue-analytics"></a>Latenza dei dati per l'operatore automatico e l'analisi della coda di chiamata

I dati sono in genere disponibili entro 30 minuti dal completamento della chiamata; in alcuni casi, tuttavia, la visualizzazione dei dati può richiedere diverse ore. 

Sarà necessario aggiornare i dati per visualizzare i nuovi dati.

## <a name="customization"></a>Personalizzazione 

È possibile personalizzare alcuni aspetti della visualizzazione dei report, ad esempio l'aggiunta o la rimozione di campi da visualizzare nelle varie visualizzazioni, la modifica del tipo di grafico e altro ancora.

Il report contiene tutte le metriche dei dati attualmente disponibili.

### <a name="change-color-schema"></a>Modificare lo schema dei colori 

I passaggi seguenti presuppongono che i passaggi di installazione siano già stati completati.

Eseguire le operazioni seguenti:

1. Selezionare **la scheda Visualizza** sulla barra multifunzione.

  :::image type="content" source="media/aa-cq-historical-report-04.png" alt-text="Screenshot che seleziona la scheda Visualizza per modificare la combinazione di colori.":::

2. Selezionare lo schema colori nell'elenco a discesa.

  :::image type="content" source="media/aa-cq-historical-report-05.png" alt-text="Screenshot che mostra varie combinazioni di colori.":::
  
## <a name="dimensions-and-measurements"></a>Dimensioni e misure

### <a name="common-dimensions"></a>Dimensioni comuni

Queste dimensioni sono comuni sia per gli operatori automatici che per le code di chiamata:

|Nome (tipo)                                            |Valori possibili                |Descrizione                                                       |
|:------------------------------------------------------|:------------------------------|:-----------------------------------------------------------------|
|ConferenceId<br>(Testo)                                 |GUID                           |Identificatore di chiamata                                                   |
|Data<br>(DateTime)                                     |                               |Data della chiamata (UTC)                                                |
|DialogId<br>(Testo)                                     |GUID                           |Identificatore di chiamata                                                   |
|Id documento<br>(Testo)                                   |GUID                           |Identificatore di chiamata                                                   |
|Durata<br>(Numero intero)                             |                               |Durata della chiamata, in secondi                                      |
|Endtime<br>(DateTime)                                  |                               |Ora di fine chiamata (UTC)                                             |
|FirstIsCaller<br>(booleano)                             |                               |                                                                  |
|FirstUPN<br>(Testo)                                     |                               |                                                                  |
|Hour<br>(Testo)                                         |                               |Ora di inizio chiamata (UTC)                                           |
|Minute<br>(Testo)                                       |                               |Minute call started (UTC)                                         |
|PSTNCallDuration<br>(Numero intero)                     |                               |                                                                  |
|PSTNCallType<br>(Testo)                                 |                               |                                                                  |
|                                                       |Esterno                       |                                                                  |
|                                                       |Interno                       |                                                                  |
|PSTNConnectivityType<sup>1</sup><br>(Testo)             |                               |                                                                  |
|                                                       |Piano chiamate                    |                                                                  |
|                                                       |DirectRouting                  |                                                                  |
|Second<br>(Testo)                                       |                               |Seconda chiamata avviata (UTC)                                         |
|SecondUPN<br>(Testo)                                    |                               |                                                                  |
|TenantId<br>(Testo)                                     |                               |ID tenant                                                         |
|Timestamp<br>(DateTime)                                |                               |Il record ora è stato scritto (UTC)                                     |
|UserStartTimeUTC<br>(DateTime)                         |                               |Ora di avvio della chiamata (UTC)                                           |

- <sup>1</sup> **PSTNConnectivityType** mostrerà l'origine del leg di chiamata finale anziché l'origine iniziale del leg di chiamata. Ad esempio, se un operatore automatico riceve una chiamata esterna e trasferisce la chiamata a un altro operatore automatico o coda di chiamata, **l'origine della chiamata in arrivo** verrà segnalata come **Interna**.


### <a name="auto-attendant-dimensions"></a>Dimensioni operatore automatico

|Nome (tipo)                                            |Valori possibili                |Descrizione                                                       |
|:------------------------------------------------------|:------------------------------|:-----------------------------------------------------------------|
|AutoAttendantCallFlow<br>(Testo)                        |                               |Incapsula i diversi stati della chiamata dell'operatore automatico          |
|                                                       |abs_search                     |                                                                  |
|                                                       |Annuncio                   |                                                                  |
|                                                       |automatic_menu                 |                                                                  |
|                                                       |call_termination               |                                                                  |
|                                                       |call_transfer                  |                                                                  |
|                                                       |first_level_menu               |                                                                  |
|                                                       |main_menu                      |                                                                  |
|                                                       |speech_input_confirmation      |                                                                  |
|                                                       |user_selection                 |                                                                  |
|AutoAttendantCallResult<br>(Testo)                      |                               |Risultato finale della chiamata                                                 |
|                                                       |failed_to_establish_media      |Non è stato possibile stabilire la parte multimediale della chiamata             |
|                                                       |failover_to_operator           |Chiamata trasferita all'operatore in genere a causa di un errore di sistema      |
|                                                       |oaa_chain_too_long             |Troppe gambe nell'AA                                           |
|                                                       |oaa_session_too_long           |La sessione AA è durata troppo a lungo                                    |
|                                                       |service_declined               |AA non ha accettato la chiamata                                         |
|                                                       |service_terminated             |La configurazione AA disconnette la chiamata o la chiamata sospesa             |
|                                                       |terminated_automatic_selection |La configurazione AA disconnette le chiamate                           |
|                                                       |terminated_no_operator         |Tutti terminati a causa di errore nessun operatore definito                   |
|                                                       |terminated_transfer_failed     |Chiamata terminata come trasferimento non riuscito- in genere a numero esterno |
|                                                       |transfer_in_progress           |Trasferimento AA->AA                                                   |
|                                                       |transferred_to_operator        |La chiamata è stata trasferita all'operatore                                  |
|                                                       |transferred_to_cq              |La chiamata è stata trasferita alla coda di chiamata                                |
|                                                       |transferred_to_receptionist    |Come transferred_to_operator                                   |
|                                                       |transferred_to_self            |La chiamata è stata restituita all'inizio dell'AA                          |
|                                                       |transferred_to_shared_voicemail |La chiamata è stata trasferita alla segreteria telefonica condivisa                         |
|                                                       |transferred_to_user            |La chiamata è stata trasferita a un utente                                    |
|                                                       |Sconosciuto                        |Si è verificata una condizione sconosciuta                                 |
|                                                       |user_terminated                |Chiamante riagganciato                                                    |
|AutoAttendantCallerActionCounts<br>(Numero intero)      |                               |                                                                  |
|AutoAttendantChairDurationInSecs<br>(Numero reale)      |                               |                                                                  |
|AutoAttendantChainIndex<br>(Numero intero)              |                               |                                                                  |
|AutoAttendantChainStartTime<br>(DateTime)              |                               |                                                                  |
|AutoAttendantCount<br>(Numero intero)                   |                               |                                                                  |
|AutoAttendantDirectorySearchMethod<br>(Testo)           |                               |Metodo di ricerca della directory                                           |
|                                                       |abs_search_dtmf                |Tono tocco                                                        |
|                                                       |abs_search_voice               |Opzioni vocali                                                             |
|AutoAttendantIdentity<br>(Testo)                        |                               |Chiamata URI dell'account delle risorse arrivata                              |
|AutoAttendantTransferAction<br>(Testo)                  |                               |Tipo di destinazione trasferimento chiamata                                         |
|                                                       |Aa                             |Trasferito a un AA                                              |
|                                                       |Cq                             |Trasferito a un call quality dashboard                                               |
|                                                       |external_pstn                  |Trasferito a un numero esterno                                 |
|                                                       |segreteria telefonica condivisa               |Trasferito alla segreteria telefonica condivisa                                   |
|                                                       |Sconosciuto                        |Azione sconosciuta                                                    |
|HasAA<br>(booleano)                                     |                               |L'AA è coinvolta nella chiamata                                            |


### <a name="call-queue-dimensions"></a>Dimensioni della coda di chiamata

|Nome (tipo)                                            |Valori possibili                |Descrizione                                                       |
|:------------------------------------------------------|:------------------------------|:-----------------------------------------------------------------|
|CallQueueAgentCount<br>(Numero intero)                  |                               |Numero di agenti in coda di chiamata                                    |
|CallQueueAgentOptInCount<br>(Numero intero)             |                               |Numero di agenti a cui è stato fornito il consenso per la coda di chiamata                           |
|CallQueueCallResult<br>(Testo)                          |                               |Stato finale chiamata in coda di chiamata                                       |
|                                                       |agent_joined_conference        |Risposta alla chiamata - Call Call in modalità conferenza                                |
|                                                       |Rifiutato                       |                                                                  |
|                                                       |Disconnesso                   |                                                                  |
|                                                       |errore                          |                                                                  |
|                                                       |Fallito                         |                                                                  |
|                                                       |Non valido                        |                                                                  |
|                                                       |traboccante                      |Condizione di overflow soddisfatta                                            |
|                                                       |timed_out                      |Condizione di timeout soddisfatta                                             |
|                                                       |transferred_to_agent           |Risposta alla chiamata - Call Call in modalità di trasferimento                                  |
|CallQueueDurationSeconds<br>(Numero reale)              |                               |                                                                  |
|CallQueueFinaleStateAction<br>(Testo)                   |                               |Azione finale coda di chiamata                                           |
|                                                       |Scollegare                     |chiamate time_out                                                    |
|                                                       |disconnect_with_busy           |chiamate traboccanti                                                   |
|                                                       |failed_to_accept_call          |                                                                  |
|                                                       |Avanti                        |                                                                  |
|                                                       |shared_voicemail               |                                                                  |
|                                                       |Altro                          |                                                                  |
|                                                       |Segreteria telefonica                      |                                                                  |
|CallQueueIdentity<br>(Testo)                            |                               |Chiamata URI dell'account delle risorse arrivata                              |
|CallQueueTargetType<br>(Testo)                          |                               |Destinazione reindirizzamento chiamate                                           |
|                                                       |ApplicationEndpoint            |                                                                  |
|                                                       |Cassetta postale                        |                                                                  |
|                                                       |Other                          |                                                                  |
|                                                       |Telefono                          |                                                                  |
|                                                       |Utente                           |                                                                  |
|HasCQ<br>(booleano)                                     |                               |Call Quality Dashboard è coinvolto nella chiamata                                            |
|TransferredFromCallQueueIdentity<br>(Testo)             |                               |                                                                  |

### <a name="measurements"></a>Misure

|Nome (tipo)                                            |Valori possibili                |Descrizione                                                       |
|:------------------------------------------------------|:------------------------------|:-----------------------------------------------------------------|
|AvgAutoAttendantChainDurationSeconds<br>(Numero reale)  |                               |                                                                  |
|AvgCallDuration<br>(Numero reale)                       |                               |                                                                  |
|AvgCallQueueDurationSeconds<br>(Numero reale)           |                               |                                                                  |
|PSTNTotalMinutes<br>(Numero reale)                      |                               |                                                                  |
|TotalAudioStreamDuration<br>(Numero reale)              |                               |                                                                  |
|TotalCallCount<br>(Numero intero)                       |                               |                                                                  |

## <a name="auto-attendant-and-call-queue-historical-reports-definitions"></a>Definizioni dei report cronologici dell'operatore automatico e della coda di chiamata

### <a name="cloud-auto-attendant-analytics-report"></a>Report analisi operatore automatico cloud

#### <a name="report-description"></a>Descrizione del report

|Sezione Report                          |Descrizione                                                       |
|:---------------------------------------|:-----------------------------------------------------------------|
|Origine chiamata in arrivo                    |Distribuzione delle chiamate per origine chiamata interna/esterna            |
|Metodo di ricerca directory                 |Distribuzione delle chiamate per tipo di ricerca                              |
|Numero azioni chiamante                     |Distribuzione delle chiamate per azione numero usata durante la chiamata       |
|Media dei secondi in AA                   |Numero medio di secondi che i chiamanti trascorrono nell'AA                 |
|Media azioni chiamante                  |Numero medio di azioni eseguite dai chiamanti nell'AA               |
|Risultati chiamata                            |Distribuzione delle chiamate per stato di chiamata finale                         |
|Sezione inferiore del report                 |Suddivisione del flusso delle chiamate                                               |

#### <a name="report-visual-and-field-mapping"></a>Mapping di oggetti visivi e campi di report

|Scheda Report            |Nome tabella report     |Filtro globale                          |
|:---------------------|:---------------------|:--------------------------------------|
|Operatore automatico        |fAutoAttendant        |Nessuno                                   |

|Sezione Report                               |Campi utilizzati                                                                                    |Filtri applicati |
|:--------------------------------------------|:------------------------------------------------------------------------------------------------|:----------|
|Selettore data                                |AAStartTime                                                                                      |Nessuno       |
|Selettore Intervallo di tempo                          |AAStartHour                                                                                      |Nessuno       |
|Account di risorse operatore automatico             |Nome AA                                                                                          |Nessuno       |
|Origine chiamata in arrivo                         |Tipo di chiamata<br>Somma di TotalCallCount         |Chiamate esterne: il tipo di chiamata è esterno<br>Chiamate interne: il tipo di chiamata è interno |
|Metodo di ricerca directory                      |AADirectorySearchMethod<br>AADirectorySearchMethodLegend<br>TotalCallCount  |AADirectorySearchMethod viene abs_search_dtmf o abs_search_name    |
|Numero azioni chiamante                          |AACallerActionCount<br>TotalCallCount                                                            |Nessuno       |
|Media dei secondi in AA                        |AAChainDuration                                                                                  |Nessuno       |
|Media azioni chiamante                       |AACallerActionCount                                                                              |Nessuno       |
|Risultati chiamata                                 |AACallResult<br>AACallResultLegend<br>TotalCallCount                                             |Nessuno       |
|Sezione inferiore del report                      |MM-DD<br>Nome AA<br>AACallFlow<br>Tipo di chiamata<br>AACallResult<br>TotalCallCount<br>AAChainDuration |Nessuno       |

#### <a name="fautoattendant-field-description"></a>fAutoAttendant field description

|Nome                                    |Tipo di dati                |Descrizione                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Nome AA                                 |Testo                     |Nome dell'account della risorsa associato a Operatore automatico<br><br>Se il nome completo Account risorsa è **aa_test@microsoft.com**, il valore sarà: **aa_test** |
|AACallerActionCount                     |Numero intero             |Riepiloga: Somma<br>Numero di azioni selezionate dal chiamante in Operatore automatico durante la chiamata  |
|AACallerActionCount (misura)           |Numero intero             |Come sopra, tranne 0 se non vengono effettuate chiamate anziché vuote                              |
|AACallFlow                              |Testo                     |Vedere Dimensioni operatore automatico -> AutoAttendantCallFlow                                   |
|AACallResult                            |Testo                     |Vedere Dimensioni operatore automatico -> AutoAttendantCallResult                                 |
|AACallResultLegend                      |Testo                     |Imposta gli elementi della legenda in base a AACallResult                                               |
|AAChainDuration                         |Numero decimale           |Riepiloga: Somma<br>Durata della chiamata in Operatore automatico                                     |
|AAChainDuration (misura)               |Numero decimale           |Come sopra, tranne 0 se non vengono effettuate chiamate anziché vuote                              |
|AAChainIndex                            |Testo                     |                                                                                         |
|AAConnectivityType                      |Testo                     |                                                                                         |
|AACount                                 |Testo                     |Numero di operatori automatici coinvolti nella chiamata                                               |
|AADirectorySearchMethod                 |Testo                     |Vedere Dimensioni operatore automatico -> AutoAttendantDirectorySearchMethod                      |
|AADirectorySearchMethodLegend           |Testo                     |Imposta gli elementi della legenda in base a AADirectorySearchMethod                                    |
|AAStartHour                             |Numero decimale           |Ora di inizio chiamata Operatore automatico                                                           |
|AAStartTime                             |Data/ora                |Ora di inizio chiamata Operatore automatico                                                           |
|AATransferAction                        |Testo                     |Vedere Dimensioni operatore automatico -> AutoAttendantTransferAction                             |
|Tipo di chiamata<sup>1</sup>                   |Testo                     |Vedere Common Dimensions -> PSTNCallType                                                    |
|MM-DD                                   |Testo                     |Chiamata operatore automatico mese-giorno                                                            |
|PSTNMinutes                             |Numero intero             |Riepiloga: Somma<br>Utilizzo totale dei minuti                                                     |
|TotalCallCount                          |Numero intero             |Riepiloga: Somma<br>Sempre 1 - usato per fornire la somma di tutte le chiamate                            |
|Somma di TotalCallCount (Misura)         |Numero intero             |Come sopra, tranne 0 se non vengono effettuate chiamate anziché vuote                              |


### <a name="cloud-call-queue-analytics-report"></a>Report Analisi code di chiamata cloud

#### <a name="report-description"></a>Descrizione del report

|Sezione Report                          |Descrizione                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|Origine chiamata in arrivo                    |Distribuzione delle chiamate per origine chiamata interna/esterna             |
|Tempo medio di attesa (secondi)             |Attendere il tempo per le chiamate risposte e abbandonate                          |
|Numero di consenso esplicito per il volume delle chiamate e l'agente      |Distribuzione delle chiamate per code di chiamata / Numero massimo di richieste di consenso esplicito dell'agente  |
|Risultati chiamata                            |Distribuzione delle chiamate per risultato della chiamata                               |
|Chiamate abbandonate                         |Distribuzione di chiamate abbandonate per code di chiamata                     |
|Durata media sessione (secondi)        |Durata della chiamata in secondi raggruppati per risultato della chiamata                      |
|Destinazioni di overflow/timeout di chiamata      |Distribuzione delle chiamate in timeout o in overflow                 |


#### <a name="report-visual-and-field-mapping"></a>Mapping di oggetti visivi e campi di report

|Scheda Report            |Nome tabella report                                   |Filtro globale       |
|:---------------------|:---------------------------------------------------|:-------------------|
|Coda di chiamata            |fCallQueueAnalytics<br>fCallQueueFinalStateAction   |Nessuno                |

|Sezione Report                      |Tabella -> Campi utilizzati                |Filtri applicati       |
|:-----------------------------------|:-------------------------------------|:---------------------|
|Selettore data                       |fCallQueueAnalytics -> Date           |Nessuno                  |
|Selettore Intervallo di tempo                 |fCallQueueAnalytics -> CQHour         |Nessuno                  |
|Account delle risorse della coda di chiamata         |fCallQueueAnalytics -> call quality dashboard        |Nessuno                  |
|Origine chiamata in arrivo                |fCallQueueAnalytics -> somma del numero di chiamate (misura)  |Chiamate esterne: il tipo di chiamata è esterno<br>Chiamate interne: il tipo di chiamata è interno |
|Avg Wait Time (seconds)-Before Answered |fCallQueueFinalStateAction -> Media di durata media CQ (Misura) |Risultato chiamata in coda di chiamata è agent_joined_conference o transferred_to_agent|
|Avg Wait Time (seconds)-Before Abandoned |fCallQueueFinalStateAction -> Media della durata media della chiamata (misura) |Risultato chiamata in coda di chiamata non è agent_joined_conference, transferred_to_agent, overflow, timed_out |
|Numero Opt-In agente e volume delle chiamate   |fCallQueueAnalytics -> Numero chiamate<br>fCallQueueAnalytics -> Agente coda di chiamata Opt In Count<br>fCallQueueAnalytics -> call quality dashboard<br>fCallQueueAnalytics -> Date |Nessuno |
|Chiamate abbandonate                     |fCallQueueAnalytics -> Date<br>fCallQueueAnalytics -> TotalCallCount | La legenda dei risultati della chiamata in coda di chiamata è abbandonata |
|Durata media sessione (secondi)    |fCallQueueFinalStateAction -> durata media della coda di chiamata (sec)<br>Legenda dei risultati delle chiamate in coda di chiamata |Durata media coda di chiamata (sec) > 0 |
|Destinazioni di overflow/timeout di chiamata  |fCallQueueAnalytics -> Numero chiamate<br>fCallQueueAnalytics -> tipo di destinazione coda di chiamata<br>Legenda del tipo di destinazione fCallQueue |La legenda del tipo di destinazione della coda di chiamata non contiene elementi abbandonati e risposta dell'agente |


#### <a name="fcallqueueanalytics-field-description"></a>Descrizione del campo fCallQueueAnalytics

|Nome                                    |Tipo di dati                |Descrizione                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|Numero chiamate                              |Numero intero             |Riepiloga: Somma<br>Numero di chiamate                                          |
|Numero agente coda di chiamata                  |Numero intero             |Riepiloga: Somma<br>Numero di agenti configurati nella coda di chiamata            |
|Numero di richieste di consenso esplicito per l'agente della coda di chiamata           |Numero intero             |Riepiloga: Somma<br>Numero di agenti che hanno fornito il consenso alla coda di chiamata              |
|Risultato chiamata in coda di chiamata                  |Testo                     |Vedere Dimensioni coda di chiamata -> CallQueueCallResult                           |
|Legenda dei risultati delle chiamate in coda di chiamata           |Testo                     |Imposta gli elementi della legenda in base al risultato della coda di chiamata                            |
|Tipo di destinazione coda di chiamata                  |Testo                     |Vedere Call Queue Dimensions -> CallQueueTargetType                           |
|Legenda del tipo di destinazione coda di chiamata           |Testo                     |Configura gli elementi della legenda in base al tipo di destinazione della coda di chiamata                       |
|Tipo di chiamata                               |Testo                     |Vedere Common Dimensions -> PSTNCallType                              |
|Call Quality Dashboard                                 |Testo                     |Nome dell'account della risorsa collegato alla coda di chiamata<br><br>Se il nome completo Account risorsa è **cq_test@microsoft.com**, il valore sarà: **cq_test** |
|Call Quality Dashboard                                 |Numero intero             |Ora di inizio chiamata in coda di chiamata                                                 |
|Data                                    |Data/ora                |Data e ora di inizio chiamata in coda di chiamata (ora)                                 | 
|DateTimeCQName                          |Testo                     |Chiave univoca per filtrare in fCallQueueFinalStateAction                     |
|Tipo di connettività PSTN                  |Testo                     |Vedere Dimensioni comuni - > PSTNConnectivityType                              |
|Totale minuti PSTN                      |Numero intero             |Riepiloga: Somma<br>Numero totale di minuti di utilizzo per le chiamate PSTN                       |
|Somma del numero di chiamate (misura)             |Numero intero             |Come numero di chiamate, tuttavia, sarà 0 quando non viene effettuata alcuna chiamata                          |
|TotalCallCount (Misura)                |Numero intero             |Riepiloga: Somma<br>Numero chiamate                                               |


#### <a name="fcallqueuefinalstateaction-field-description"></a>Descrizione del campo fCallQueueFinalStateAction

|Nome                                    |Tipo di dati                |Descrizione                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|Durata media chiamata (secondi)         |Numero decimale           |Riepiloga: Somma<br>Durata media delle chiamate in secondi per le chiamate abbandonate     |
|Durata media coda di chiamata (sec)       |Numero decimale           |Riepiloga: Somma<br>Tempo medio di attesa in secondi per le chiamate a cui si è risposto       |
|Media della durata media delle chiamate (misura)  |Numero intero             |Uguale alla durata media della chiamata (secondi), tuttavia, sarà 0 quando non vengono effettuate chiamate    |
|Media della durata media di Call Quality Dashboard (misura)    |Numero intero             |Come la durata media della coda di chiamata (sec), tuttavia, sarà uguale a 0 quando non vengono effettuate chiamate  |
|Numero chiamate                              |Numero intero             |Riepiloga: Somma<br>Numero di chiamate                                          |
|Risultato chiamata in coda di chiamata                  |Testo                     |Vedere Dimensioni coda di chiamata -> CallQueueCallResult                           |
|Legenda dei risultati delle chiamate in coda di chiamata           |Testo                     |Imposta gli elementi della legenda in base al risultato della chiamata in coda di chiamata                       |
|Azione di stato finale sulla coda di chiamata           |Testo                     |Vedere Call Queue Dimensions -> CallQueueFinaleStateAction                    |
|Call Quality Dashboard                                 |Testo                     |Nome dell'account della risorsa collegato alla coda di chiamata<br><br>Se il nome completo Account risorsa è **cq_test@microsoft.com**, il valore sarà: **cq_test** |
|Call Quality Dashboard                                 |Numero                   |Ora in cui è stata effettuata la chiamata
|Data                                    |Data/ora                |Data e ora di inizio chiamata in coda di chiamata (ora)                                 |
|DateTimeCQName                          |Testo                     |Chiave univoca per filtrare in fCallQueueFinalStateAction                     |
|IsAbandoned                             |Vero/falso               |True se alla chiamata non risponde un agente                                    |


### <a name="cloud-call-queue-agent-timeline-report"></a>Report sequenza temporale agente coda di chiamata cloud

#### <a name="report-description"></a>Descrizione del report

|Sezione Report                                          |Descrizione                                                         |
|:-------------------------------------------------------|:-------------------------------------------------------------------|
|Numero di chiamate da parte dell'agente                                |Distribuzione delle chiamate per coda di chiamata e agente                       |
|Distribuzione per agente e per tutte le code                     |Distribuzione delle chiamate per agente e coda di chiamata                       |
|Tabella (in basso a sinistra)                                     |Distribuzione delle chiamate per agente con durata media e totale delle chiamate |
|Durata media chiamata (secondi) dell'agente (in basso a destra) |Durata media (secondi) della chiamata da parte dell'agente                         |

#### <a name="report-visual-field-mapping"></a>Mapping del campo visivo del report

|Scheda Report            |Nome tabella report           |Filtro globale       |
|:---------------------|:---------------------------|:-------------------|
|Sequenza temporale dell'agente        |fAgentTimelineAnalytics     |Nessuno                |


|Sezione Report                                |Campi utilizzati                         |Filtri applicati       |
|:---------------------------------------------|:-------------------------------------|:---------------------|
|Selettore data                                 |Datetime                              |Nessuno                  |
|Selettore Agent Username                       |Nome agente                            |Nessuno                  |
|Selettore account di risorsa coda di chiamata         |Call Quality Dashboard                               |Nessuno                  |
|Numero di chiamate da parte dell'agente                      |Numero chiamate<br>Nome agente<br>Data<br>Hour      |Nessuno                  |
|Distribuzione per agente e coda di chiamata          |Nome agente<br>Durata media chiamate (secondi)<br>Numero chiamate<br>Call Quality Dashboard |Nessuno                      |
|In basso a sinistra                                   |Nome agente<br>Durata media chiamata (secondi)<br>Numero chiamate<br>Durata chiamata (Minuti)<br>Call Quality Dashboard<br>Hour<br>MM-DD | Nessuno |
|Durata media chiamata (secondi) dall'agente      |Nome agente<br>Durata media chiamata (secondi) | Nessuno |

#### <a name="fagenttimelineanalytics-field-description"></a>Descrizione del campo fAgentTimelineAnalytics

|Nome                                    |Tipo di dati                |Descrizione                                         |
|:---------------------------------------|:------------------------|:---------------------------------------------------|
|Nome agente                              |Testo                     |UPN utente<br>Se il nome utente completo è **user@microsoft.com**, il valore sarà: **utente** |
|Durata media chiamata (secondi)         |Numero decimale           |Riepiloga: Somma<br>Durata media delle chiamate in coda di chiamata in secondi |
|Numero chiamate                              |Numero intero             |Riepiloga: Somma<br>Numero di chiamate a cui l'agente ha risposto     |
|Durata chiamata (minuti)                 |Numero intero             |Riepiloga: Somma<br>Durata totale delle chiamate in coda di chiamata in minuti (arrotondata per eccesso al minuto più vicino)  |
|Call Quality Dashboard                                 |Testo                     |Nome dell'account della risorsa collegato alla coda di chiamata<br><br>Se il nome completo Account risorsa è **cq_test@microsoft.com**, il valore sarà: **cq_test** |
|Data                                    |Data                     |Data della chiamata                                             |
|Datetime                                |Datetime                 |Data della chiamata                                             |
|Hour                                    |Numero intero             |Ora di chiamata                                             |
|MM-DD                                   |Testo                     |Mese e giorno di chiamata                                    |


> [!NOTE]
> Quando una chiamata arriva alla prima coda di chiamata, se il numero di chiamate già in attesa in quella coda ha raggiunto il limite di **gestione del overflow** di chiamata e se l'opzione di reindirizzamento invia nuove chiamate a una seconda coda di chiamata, gli agenti nella seconda coda di chiamata verranno visualizzati come nella prima coda di chiamata in questo report. 

## <a name="known-issues"></a>Problemi noti

- Le code di chiamata e gli operatori automatici sono mostrati dall'ID dell'account della risorsa invece che dai nomi della coda di chiamata/operatore automatico.  Per mostrare tutto il traffico per un operatore automatico o una coda di chiamata, è necessario selezionare tutti gli account delle risorse assegnati all'operatore automatico o alla coda di chiamata.

- Solo 28 giorni di cronologia sono disponibili nel dashboard in quanto i dati della coda di chiamata/dell'operatore automatico sono considerati dati personali ed è soggetto a criteri di conservazione della privacy dei dati.

- In alcuni scenari, l'agente ha risposto al numero di chiamate nel rapporto **Sequenza temporale agente coda di chiamata cloud** può essere diverso rispetto al numero di chiamate mostrate nella cronologia chiamate client di Teams. La cronologia delle chiamate del client di Teams è corretta. Il supporto è in fase di analisi, ma al momento non è disponibile alcun tempo stimato per la riparazione.

## <a name="version-3xx-history"></a>Cronologia della versione 3.x.x

Consulta: Teams Auto Attendant & call queue historical reports - Change Log.docx in the downloaded zip file for a detailed list of changes 

|Versione  |Data di pubblicazione     |Filename                                                           |Descrizione                                         |
|:--------|:------------------|:------------------------------------------------------------------|:---------------------------------------------------|
|3.0.4    |18 novembre 2022  |Teams Auto Attendant & Call Queue Historical Reports V3.0.4        |Errore corretto, classificazione delle chiamate migliorata, aggiunta della legenda |
|3.0.3    |8 novembre 2022   |Teams Auto Attendant & Call Queue Historical Reports V3.0.3        |Errore corretto, collegamento alla documentazione aggiunto, query ottimizzate |
|3.0.1    |26 ottobre 2022   |Teams Auto Attendant & Call Queue Historical Reports V3.0.1        |Rimozione dell'immissione dell'origine dati di test                   |
|3.0.0    |25 ottobre 2022   |Teams Auto Attendant & Call Queue Historical Reports V3.0.0        |Nuova origine dati back-end                             |

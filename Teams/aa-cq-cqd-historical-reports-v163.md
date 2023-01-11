---
title: Report cronologici relativi all'operatore automatico e alla coda di chiamata per GCC High e DoD
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
ROBOTS: NOINDEX, NOFOLLOW
description: Informazioni su come usare l'operatore automatico di Teams & report storico sulla coda di chiamata di Power BI per visualizzare i dati cronologici di Operatore automatico e Coda di chiamata per i clienti GCC High e DoD.
ms.openlocfilehash: cde953bfd8e9c95c60c795f6de91488506c2addf
ms.sourcegitcommit: ae687f530d5505b96df7cb7ef4da3a36bd9afd29
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/10/2023
ms.locfileid: "69763677"
---
# <a name="auto-attendant-and-call-queue-historical-reports-for-gcc-high-and-dod"></a>Report cronologici relativi all'operatore automatico e alla coda di chiamata per GCC High e DoD

> [!IMPORTANT]
> Il supporto del cloud pubblico per il modello V1.63 terminerà il 25 novembre 2022.
>
> I clienti cloud pubblici devono usare V3.x.x di [Operatore automatico & i rapporti cronologici della coda di chiamata](aa-cq-cqd-historical-reports.md)

## <a name="v163-published-on-august-24-2022"></a>V1.63 pubblicato il 24 agosto 2022

Il **modello Power BI Per l'operatore automatico di Teams & rapporto storico coda di chiamata** fornisce i tre report seguenti:

- Il report [Operatore automatico](media/aa-cq-historical-report-sample-aa-v163.png) mostra i dati analitici per le chiamate in arrivo negli operatori automatici.
- Il report [Coda](media/aa-cq-historical-report-sample-cq-v163.png) di chiamata mostra i dati analitici per le chiamate che arrivano nelle code di chiamata.
- Il report [Sequenza temporale agente](media/aa-cq-historical-report-sample-at-v163.png) mostra una visualizzazione sequenza temporale degli agenti attivi nelle chiamate in coda di chiamata.

Questi report usano i dati dell'archivio dati Call [Quality Dashboard (CQD).](CQD-Power-BI-query-templates.md) 

## <a name="v163-prerequisites"></a>Prerequisiti V1.63

### <a name="power-bi-desktop"></a>Power BI Desktop
Devi aver installato Power BI Desktop. Puoi installare e usare la versione gratuita da [Microsoft Windows Store](https://aka.ms/pbidesktopstore).

La versione minima compatibile è 2.85.681.0 (settembre 2020).

### <a name="permissions-to-access-the-cqd-pipeline"></a>Autorizzazioni per accedere alla pipeline di Call Quality Dashboard

L'account usato per visualizzare il report cronologico deve avere le autorizzazioni per accedere alla pipeline di dati di Call Quality Dashboard. Per altre informazioni, vedere [Ruolo di accesso a Call Quality Dashboard](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).

## <a name="v163-installation"></a>Installazione V1.63 

I passaggi seguenti presuppongono che siano già stati installati Power BI Desktop nel computer e che l'account disponga delle autorizzazioni necessarie per accedere alla pipeline di dati di Call Quality Dashboard.

Eseguire le operazioni seguenti:

1. Scaricare e salvare il file zip dei [modelli di query di Power BI di Call Quality Dashboard](https://www.microsoft.com/download/details.aspx?id=102291) nel computer.

2. Aprire il file ZIP.

3. Aprire il file modello `CQD Teams Auto Attendant & Call Queue Historical Report V1.63.pbit` . Power BI Desktop dovrebbe avviarsi.

4. Verrà richiesto di selezionare l'area della pipeline di dati di Call Quality Dashboard. Selezionare l'area geografica in cui si trova il tenant.

     :::image type="content" source="media/aa-cq-historical-report-01-v163.png" alt-text="Screenshot che seleziona l'area della pipeline di dati di Call Quality Dashboard.":::

    Tenant cloud pubblici

5. L'area geografica in cui si trova il tenant può essere ottenuta utilizzando il cmdlet [Get-CsTenant](/powershell/module/skype/get-cstenant) .

    ```powershell
    (Get-CsTenant).ServiceInstance

    microsoftcommunicationsonline/noam-4a-s7
    ```

    L'area geografica verrà visualizzata dopo il **/** come nell'esempio precedente in cui l'area geografica è `noam`.

    Tenant GCC High e DoD

6. Aggiornare il modello in modo da usare uno dei connettori seguenti:

   - GCCH: `https://data.cqd.gov.teams.microsoft.us/RunQuery`
   - Dod: `https://data.cqd.dod.teams.microsoft.us/RunQuery`


7. Il report verrà avviato con dati di esempio.
 
8. Per visualizzare i propri dati, selezionare **Aggiorna** nella scheda **Home** in **Query** in Power BI Desktop.

   :::image type="content" source="media/aa-cq-historical-report-02-v163.png" alt-text="Screenshot che seleziona l'opzione di aggiornamento.":::

9. Verrà richiesto di eseguire l'accesso. Selezionare **Account aziendale** e quindi **selezionare Accedi**.

   :::image type="content" source="media/aa-cq-historical-report-03-v163.png" alt-text="Screenshot che mostra l'accesso per V1.63.":::

10. Seleziona **Connetti** per aggiornare i dati.

## <a name="data-latency-for-aa-and-cq-analytics"></a>Latenza dei dati per l'analisi di AA e CQ

I dati sono in genere disponibili entro 30 minuti dal completamento della chiamata; in alcuni casi, tuttavia, la visualizzazione dei dati può richiedere diverse ore.

Sarà necessario aggiornare i dati per visualizzare i nuovi dati.

## <a name="customization"></a>Personalizzazione

È possibile personalizzare alcuni aspetti della visualizzazione dei report, ad esempio l'aggiunta o la rimozione di campi da visualizzare nelle varie visualizzazioni, la modifica del tipo di grafico e così via.

Il report contiene tutte le metriche dei dati attualmente disponibili.

### <a name="change-color-schema"></a>Modificare lo schema dei colori

I passaggi seguenti presuppongono che i passaggi di installazione siano già stati completati.

Eseguire le operazioni seguenti:

1. Selezionare **la scheda Visualizza** sulla barra multifunzione.

    :::image type="content" source="media/aa-cq-historical-report-04.png" alt-text="Screenshot che seleziona la scheda Visualizza per modificare la combinazione di colori.":::

2. Selezionare lo schema colori nell'elenco a discesa.

    :::image type="content" source="media/aa-cq-historical-report-05.png" alt-text="Screenshot che mostra varie combinazioni di colori.":::
  
## <a name="auto-attendant-and-call-queue-historical-reports-definitions"></a>Definizioni dei report cronologici dell'operatore automatico e della coda di chiamata

### <a name="cloud-auto-attendant-analytics-report"></a>Report analisi operatore automatico cloud

#### <a name="report-description"></a>Descrizione del report

|Sezione Report                          |Descrizione                                                       |
|:---------------------------------------|:-----------------------------------------------------------------|
|Origine chiamata in arrivo<sup>1</sup>        |Distribuzione delle chiamate per origine chiamata interna/esterna            |
|Metodo di ricerca directory                 |Distribuzione delle chiamate per tipo di ricerca                              |
|Numero azioni chiamante                     |Distribuzione delle chiamate per azione numero usata durante la chiamata       |
|Media dei secondi in AA                   |Numero medio di secondi che i chiamanti trascorrono nell'AA                 |
|Media azioni chiamante                  |Numero medio di azioni eseguite dai chiamanti nell'AA               |
|Risultati chiamata                            |Distribuzione delle chiamate per stato di chiamata finale                         |
|Sezione inferiore del report                 |Suddivisione del flusso delle chiamate                                               |



#### <a name="report-to-cqd-table-and-field-mapping"></a>Report sul mapping di tabelle e campi di Call Quality Dashboard

|Scheda Report            |Nome tabella report     |Nome tabella di origine            |Filtro globale                          |
|:---------------------|:---------------------|:----------------------------|:--------------------------------------|
|Operatore automatico        |fAutoAttendant        |Operatore automatico                |Nessuno                                   |

|Sezione Report                                  |Campi utilizzati                              |Filtri applicati     |
|:-----------------------------------------------|:------------------------------------------|:-------------------|
|Selettore data                                   |AAStartTime                                |Nessuno                |
|Selettore Intervallo di tempo                             |AAStartHour                                |Nessuno                |
|Operatore automatico                                  |Nome AA                                    |Nessuno                |
|Origine chiamata in arrivo<sup>1</sup>                |Tipo di chiamata<br>Somma di TotalCallCount (Misura) |Chiamate esterne: il tipo di chiamata è esterno<br>Chiamate interne: il tipo di chiamata è interno |
|Metodo di ricerca directory                         |AADirectorySearchMethod<br>TotalCallCount  |AADirectorySearchMethod viene abs_search_dtmf o abs_search_name    |
|Numero azioni chiamante                             |AACallerActionCount<br>TotalCallCount      |Nessuno                                                             |
|Media dei secondi in AA                           |AAChainDuration (misura)                  |Nessuno                                                             |
|Media azioni chiamante                          |AACallerActionCount (misura)              |Nessuno                                                             |
|Risultati chiamata                                    |AACallResult<br>AACallResultLegend<br>TotalCallCount             |Nessuno                                       |
|Sezione inferiore del report                         |Nome AA<br>AACallFlow<br>AACallResult<br>AAChainDuration<br>Tipo di chiamata<br>MM-DD<br>TotalCallCount |Nessuno       |

#### <a name="fautoattendant-cqd-fields-description"></a>fAutoAttendant CQD fields description

|Nome                                    |Tipo di dati                |Descrizione                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Nome AA                                 |Testo                     |Nome dell'account della risorsa associato a Operatore automatico<br><br>Se il nome completo Account risorsa è **aa_test@microsoft.com**, il valore sarà: **aa_test** |
|AACallerActionCount                     |Numero intero             |Riepiloga: Somma<br>Numero di azioni selezionate dal chiamante in Operatore automatico durante la chiamata  |
|AACallerActionCount (misura)          |Numero intero             |Come sopra, tranne 0 se non vengono effettuate chiamate anziché vuote                              |
|AACallFlow                              |Testo                     |Incapsula i diversi stati della chiamata operatore automatico: valori possibili:<br><br>§ abs_search<br>§ annuncio<br>§ automatic_menu<br>§ call_termination<br>§ call_transfer<br>§ first_level_menu<br>§ main_menu<br>§ speech_input_confirmation<br>§ user_selection |
|AACallResult                            |Testo                     |Risultato finale della chiamata: valori possibili:<br><br>§ failed_to_establish_media (non è stato possibile stabilire la parte multimediale della chiamata)<br>§ failover_to_operator (chiamata trasferita all'operatore in genere a causa di un errore di sistema)<br>§ oaa_chain_too_long (troppe gambe nell'AA)<br>§ oaa_session_too_long (la sessione AA è durata troppo a lungo)<br>§ service_declined (AA non ha accettato la chiamata)<br>§ service_terminated (la configurazione AA disconnette la chiamata o la chiamata riagganciata)<br>§ terminated_automatic_selection (la configurazione AA disconnette le chiamate)<br>§ terminated_no_operator (chiamata terminata per errore nessun operatore definito) <br>§ terminated_transfer_failed (chiamata terminata come trasferimento non riuscita - in genere a numero esterno)<br>§ transfer_in_progress (trasferimento AA->AA)<br>§ transferred_to_operator (la chiamata è stata trasferita all'operatore - in genere a causa di un errore dell'utente)<br>§ transferred_to_receptionist (come transferred_to_operator)<br>§ transferred_to_self (la chiamata è stata restituita all'inizio dell'AA- in genere da un'opzione di annuncio di menu)<br>§ transferred_to_shared_voicemail (la chiamata è stata trasferita alla segreteria telefonica condivisa)<br>§ transferred_to_user (la chiamata è stata trasferita a un utente - include code di chiamata)<br>§ sconosciuto (si è verificata una condizione sconosciuta)<br>§ user_terminated (chiamante riagganciato) |
|Legenda chiamata AA                          |Testo                     |Imposta gli elementi della legenda in base a AACallResult                               |
|AAChainDuration                         |Numero decimale           |Riepiloga: Somma<br>Durata della chiamata in Operatore automatico                     |
|AAChainDuration (misura)               |Numero decimale           |Come sopra, tranne 0 se non vengono effettuate chiamate anziché vuote              |
|AAChainIndex                            |Testo                     |                                                                         |
|AAConnectivityType                      |Testo                     |Tipo di chiamata: valori possibili:<br><br>§ Chiamata esterna<br>§ Chiamata interna |
|AACount                                 |Testo                     |Numero di operatori automatici coinvolti nella chiamata                               |
|AADirectorySearchMethod                 |Testo                     |Metodo di ricerca dell'ultima rubrica: valori possibili:<br><br>§ abs_search_dtmf<br>§ abs_search_extension_x<br>§ abs_search_name |
|AAStartHour                             |Numero decimale           |Ora di inizio chiamata Operatore automatico                                           |
|AAStartTime                             |Data/ora                |Ora di inizio chiamata Operatore automatico                                           |
|AATransferAction                        |Testo                     |Tipo di destinazione trasferimento chiamata: valori possibili:<br><br>§ applicazione - entità dell'applicazione vocale<br>§ external_pstn<br>§ hunt_group - Entità coda di chiamata<br>§ orgaa - Entità Operatore automatico<br>§ shared_voicemail<br>§ sconosciuto<br>§ utente |
|Tipo di chiamata<sup>1</sup>                   |Testo                     |Tipo di chiamata: valori possibili:<br><br>§ Esterno<br>§ Interno           |
|IsAAInvolved                            |Testo                     |Sempre 1                                                                 |
|MM-DD                                   |Testo                     |Chiamata operatore automatico mese-giorno                                            |
|PSTNMinutes                             |Numero intero             |Riepiloga: Somma<br>Utilizzo totale dei minuti                                     |
|TotalCallCount                          |Numero intero             |Riepiloga: Somma<br>Sempre 1 - usato per fornire la somma di tutte le chiamate            |
|Somma di TotalCallCount (Misura)         |Numero intero             |Come sopra, tranne 0 se non vengono effettuate chiamate anziché vuote              |


### <a name="cloud-call-queue-analytics-report"></a>Report Analisi code di chiamata cloud

#### <a name="report-description"></a>Descrizione del report

|Sezione Report                          |Descrizione                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|Origine chiamata in arrivo<sup>1</sup>        |Distribuzione delle chiamate per origine chiamata interna/esterna             |
|Tempo medio di attesa (secondi)             |Attendere il tempo per le chiamate risposte e abbandonate                          |
|Numero di consenso esplicito per il volume delle chiamate e l'agente      |Distribuzione delle chiamate per code di chiamata / Numero massimo di richieste di consenso esplicito dell'agente  |
|Risultati chiamata                            |Distribuzione delle chiamate per risultato della chiamata                               |
|Chiamate abbandonate                         |Distribuzione di chiamate abbandonate per code di chiamata                     |
|Durata media sessione (secondi)        |Durata della chiamata in secondi raggruppati per risultato della chiamata                      |
|Destinazioni di overflow/timeout di chiamata      |Distribuzione delle chiamate in timeout o in overflow                 |


#### <a name="report-to-cqd-table-and-field-mapping"></a>Report sul mapping di tabelle e campi di Call Quality Dashboard

|Scheda Report            |Nome tabella report                                   |Nome tabella di origine                               |Filtro globale       |
|:---------------------|:---------------------------------------------------|:-----------------------------------------------|:-------------------|
|Coda di chiamata            |fCallQueueAnalytics<br>fCallQueueFinalStateAction   |CallQueueAnalytics<br>CallQueueFinalStateAction |Nessuno                |

|Sezione Report                      |Tabella -> Campi utilizzati                |Filtri applicati       |
|:-----------------------------------|:-------------------------------------|:---------------------|
|Selettore data                       |fCallQueueAnalytics -> Date           |Nessuno                  |
|Selettore Intervallo di tempo                 |fCallQueueAnalytics -> CQHour         |Nessuno                  |
|Account delle risorse della coda di chiamata         |fCallQueueAnalytics -> call quality dashboard        |Nessuno                  |
|Origine chiamata in arrivo<sup>1</sup>    |fCallQueueAnalytics -> somma del numero di chiamate (misura)<br>fCallQueueAnalytics -> tipo di chiamata    |Chiamate esterne: il tipo di chiamata è esterno<br>Chiamate interne: il tipo di chiamata è interno |
|Avg Wait Time (seconds)-Before Answered |fCallQueueFinalStateAction -> Media di durata media CQ (Misura) |Risultato chiamata in coda di chiamata è agent_joined_conference o transferred_to_agent|
|Avg Wait Time (seconds)-Before Abandoned |fCallQueueFinalStateAction -> Media della durata media della chiamata (misura) |Risultato chiamata in coda di chiamata non è agent_joined_conference, transferred_to_agent, overflow, timed_out |
|Numero Opt-In agente e volume delle chiamate   |fCallQueueAnalytics -> Numero chiamate<br>fCallQueueAnalytics -> Agente coda di chiamata Opt In Count<br>fCallQueueAnalytics -> call quality dashboard<br>fCallQueueAnalytics -> Date |Nessuno |
|Chiamate abbandonate                     |fCallQueueAnalytics -> Date<br>fCallQueueAnalytics -> TotalCallCount | La legenda dei risultati della chiamata in coda di chiamata è abbandonata |
|Durata media sessione (secondi)    |fCallQueueFinalStateAction -> durata media della coda di chiamata (sec)<br>Legenda dei risultati delle chiamate in coda di chiamata |Durata media coda di chiamata (sec) > 0 |
|Destinazioni di overflow/timeout di chiamata  |fCallQueueAnalytics -> Numero chiamate<br>fCallQueueAnalytics -> tipo di destinazione coda di chiamata<br>Legenda del tipo di destinazione fCallQueue |La legenda del tipo di destinazione della coda di chiamata non contiene elementi abbandonati e risposta dell'agente |


#### <a name="fcallqueueanalytics-cqd-fields-description"></a>Descrizione dei campi CQD di fCallQueueAnalytics

|Nome                                    |Tipo di dati                |Descrizione                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|Numero chiamate                              |Numero intero             |Riepiloga: Somma<br>Numero di chiamate                                          |
|Numero agente coda di chiamata                  |Numero intero             |Riepiloga: Somma<br>Numero di agenti configurati nella coda di chiamata            |
|Numero di richieste di consenso esplicito per l'agente della coda di chiamata           |Numero intero             |Riepiloga: Somma<br>Numero di agenti che hanno fornito il consenso alla coda di chiamata              |
|Risultato chiamata in coda di chiamata                  |Testo                     |Stato finale chiamata in coda di chiamata: valori possibili:<br><br>§ agent_joined_conference (risposta alle chiamate in modalità conferenza)<br>§ rifiutata<br>§ disconnesso<br>§ errore<br>§ non riuscito<br>§ non valido<br>§ overflown (condizione di overflow soddisfatta)<br>§ timed_out (condizione di timeout soddisfatta)<br>§ transferred_to_agent (risposta alle chiamate in modalità di trasferimento {default}) |
|Legenda dei risultati delle chiamate in coda di chiamata           |Testo                     |Imposta gli elementi della legenda in base al risultato della coda di chiamata                             |
|Tipo di destinazione coda di chiamata                  |Testo                     |***Tipo di destinazione del reindirizzamento delle chiamate: valori possibili:***<br><br>§ ApplicationEndpoint<br>§ Cassetta postale<br>§ Altro<br>§ Utente |
|Legenda del tipo di destinazione coda di chiamata           |Testo                     |Configura gli elementi della legenda in base al tipo di destinazione della coda di chiamata                        |
|Tipo di chiamata<sup>1</sup>                   |Testo                     |Tipo di chiamata: valori possibili:<br><br>§ Esterno<br>§ Interno             |
|Call Quality Dashboard                                 |Testo                     |Nome dell'account della risorsa collegato alla coda di chiamata<br><br>Se il nome completo Account risorsa è **cq_test@microsoft.com**, il valore sarà: **cq_test** |
|Call Quality Dashboard                                 |Numero intero             |Ora di inizio chiamata in coda di chiamata                                                 |
|Data                                    |Data/ora                |Data e ora di inizio chiamata in coda di chiamata (ora)                                 | 
|DateTimeCQName                          |Testo                     |Chiave univoca per filtrare in fCallQueueFinalStateAction                     |
|Tipo di connettività PSTN                  |Testo                     |Tipo di chiamata: valori possibili:<br><br>§ Chiamata esterna<br>§ Chiamata interna     |
|Totale minuti PSTN                      |Numero intero             |Riepiloga: Somma<br>Numero totale di minuti di utilizzo per le chiamate PSTN                       |
|Somma del numero di chiamate (misura)             |Numero intero             |Come numero di chiamate, tuttavia, sarà 0 quando non viene effettuata alcuna chiamata                          |
|TotalCallCount (Misura)                |Numero intero             |Riepiloga: Somma<br>Numero chiamate                                                |


#### <a name="fcallqueuefinalstateaction-cqd-fields-description"></a>Descrizione dei campi fCallQueueFinalStateAction CQD

|Nome                                    |Tipo di dati                |Descrizione                                        |
|:---------------------------------------|:------------------------|:--------------------------------------------------|
|Durata media chiamata (secondi)         |Numero decimale           |Riepiloga: Somma<br>Durata media delle chiamate in secondi per le chiamate abbandonate    |
|Durata media coda di chiamata (sec)       |Numero decimale           |Riepiloga: Somma<br>Media di attesa in secondi per le chiamate a cui si è risposto           |
|Media della durata media delle chiamate (misura)  |Numero intero             |Uguale alla durata media della chiamata (secondi), tuttavia, sarà 0 quando non vengono effettuate chiamate   |
|Media della durata media di Call Quality Dashboard (misura)    |Numero intero             |Come la durata media della coda di chiamata (sec), tuttavia, sarà uguale a 0 quando non vengono effettuate chiamate |
|Numero chiamate                              |Numero intero             |Riepiloga: Somma<br>Numero di chiamate                                         |
|Risultato chiamata in coda di chiamata                  |Testo                     |Stato finale chiamata in coda di chiamata: valori possibili:<br><br>§ agent_joined_conference (risposta alle chiamate in modalità conferenza)<br>§ rifiutata<br>§ disconnesso<br>§ errore<br>§ non riuscito<br>§ non valido<br>§ overflown (condizione di overflow soddisfatta)<br>§ timed_out (condizione di timeout soddisfatta)<br>§ transferred_to_agent (risposta alle chiamate in modalità di trasferimento {default} |
|Legenda dei risultati delle chiamate in coda di chiamata           |Testo                     |Imposta gli elementi della legenda in base al risultato della chiamata in coda di chiamata                      |
|Azione di stato finale sulla coda di chiamata           |Testo                     |Azione finale coda di chiamata: valori possibili:<br><br>§ disconnetti (chiamate timed_out)<br>§ disconnect_with_busy (chiamate in eccesso)<br>§ failed_to_accept_call<br>§ avanti<br>§ shared_voicemail<br>§ altro<br>§ segreteria telefonica                |
|Call Quality Dashboard                                 |Testo                     |Nome dell'account della risorsa collegato alla coda di chiamata<br><br>Se il nome completo Account risorsa è **cq_test@microsoft.com**, il valore sarà: **cq_test** |
|Data                                    |Data/ora                |Data e ora di inizio chiamata in coda di chiamata (ora)                                 |
|DateTimeCQName                          |Testo                     |Chiave univoca per filtrare in fCallQueueFinalStateAction                     |
|IsAbandoned                             |Vero/falso               |True se alla chiamata non risponde un agente                                   |


### <a name="cloud-call-queue-agent-timeline-report"></a>Report sequenza temporale agente coda di chiamata cloud

#### <a name="report-description"></a>Descrizione del report

|Sezione Report                                          |Descrizione                                                  |
|:-------------------------------------------------------|:------------------------------------------------------------|
|Numero di chiamate da parte dell'agente                                |Distribuzione delle chiamate per coda di chiamata e agente                |
|Distribuzione per agente e per tutte le code                     |Distribuzione delle chiamate per agente e coda di chiamata                |
|Tabella (in basso a destra)                                    |Distribuzione delle chiamate per agente con durata media e totale delle chiamate |
|Durata media chiamata (secondi) dell'agente                |Durata media (secondi) della chiamata da parte dell'agente                  |

#### <a name="report-to-cqd-table-and-field-mapping"></a>Report sul mapping di tabelle e campi di Call Quality Dashboard

|Scheda Report            |Nome tabella report           |Nome tabella di origine         |Filtro globale       |
|:---------------------|:---------------------------|:-------------------------|:-------------------|
|Sequenza temporale dell'agente        |fAgentTimelineAnalytics     |fAgentTimelineAnalytics   |Nessuno                |


|Sezione Report                                |Campi utilizzati                         |Filtri applicati       |
|:---------------------------------------------|:-------------------------------------|:---------------------|
|Selettore data                                 |Datetime                              |Nessuno                  |
|Selettore Agent Username                       |Nome agente                            |Nessuno                  |
|Selettore account di risorsa coda di chiamata          |Call Quality Dashboard                               |Nessuno                  |
|Numero di chiamate da parte dell'agente                      |Nome agente<br>Numero chiamate<br>Hour      |Nessuno                  |
|Distribuzione per agente e coda di chiamata          |Nome agente<br>Durata media chiamate (secondi)<br>Numero chiamate<br>Call Quality Dashboard |Nessuno                      |
|In basso a sinistra                                   |Nome agente<br>Durata media chiamata (secondi)<br>Numero chiamate<br>Durata chiamata (Minuti)<br>Call Quality Dashboard<br>Hour<br>MM-DD | Nessuno |
|Durata media chiamata (secondi) dall'agente      |Nome agente<br>Durata media chiamata (secondi) | Nessuno |

#### <a name="fagenttimelineanalytics-cqd-fields-description"></a>Descrizione dei campi di fAgentTimelineAnalytics CQD

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

- La coda di chiamata e gli operatori automatici sono mostrati dall'ID dell'account della risorsa invece che dai nomi della coda di chiamata o dell'operatore automatico.  Per mostrare tutto il traffico per un operatore automatico o una coda di chiamata, è necessario selezionare tutti gli account delle risorse assegnati all'operatore automatico o alla coda di chiamata.

- Solo 28 giorni di cronologia sono disponibili nel dashboard in quanto i dati della coda di chiamata/dell'operatore automatico sono considerati dati personali ed è soggetto a criteri di conservazione della privacy dei dati.

- In alcuni scenari, l'agente ha risposto al numero di chiamate nel rapporto **Sequenza temporale agente coda di chiamata cloud** può essere diverso rispetto al numero di chiamate mostrate nella cronologia chiamate client di Teams. La cronologia delle chiamate del client di Teams è corretta. Il supporto è in fase di analisi, ma al momento non è disponibile alcun tempo stimato per la riparazione.

- <sup>1</sup> **L'origine della chiamata in arrivo** nell'operatore automatico e nei grafici della coda di chiamata mostra l'origine finale della coda di chiamata anziché l'origine iniziale della coda di chiamata. Ad esempio, se un operatore automatico riceve una chiamata esterna e trasferisce la chiamata a un altro operatore automatico o coda di chiamata, **l'origine della chiamata in arrivo** verrà segnalata come Interna.

## <a name="version-1xx-history"></a>Cronologia della versione 1.xx

Consulta: CQD Teams Auto Attendant & Call Queue Historical Reports - Change Log.docx in the downloaded zip file for a detailed list of changes                         

|Versione  |Data di pubblicazione     |Filename                                                           |Descrizione                                         |
|:--------|:------------------|:------------------------------------------------------------------|:---------------------------------------------------
|1.63     |24 agosto 2022    |CQD Teams Auto Attendant & Call Queue Historical Report V1.63.pbit |                                                    |
|1.60     |22 luglio 2022      |CQD Teams Auto Attendant & Call Queue Historical Report V1.60.pbit |                                                    |
|1.00     |5 novembre 2020   |CQ e AA combinati Analytics 20201105.pbit                         |Rilascio iniziale                                     |


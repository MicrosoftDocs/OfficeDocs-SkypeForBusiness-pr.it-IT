---
title: Report cronologico della coda di chiamata & operatore automatico
author: CarolynRowe
ms.author: crowe
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
description: Informazioni su come usare il report di Power BI di Call Quality Dashboard per visualizzare i dati cronologici di Operatore automatico e Coda di chiamata.
ms.openlocfilehash: b9bb3cf0990058cd16ed35d52d07f63be6cd90fb
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/26/2022
ms.locfileid: "67024009"
---
# <a name="auto-attendant--call-queue-historical-report"></a>Report cronologico della coda di chiamata & operatore automatico

Il modello Power BI di Power BI Operatore automatico & coda di chiamata fornisce i tre report seguenti:

- [Operatore automatico](media/cqd-teams-aa-cq-historical-report-sample-aa.png) : mostra i dati analitici per le chiamate in arrivo agli operatori automatici.
- [Coda di chiamata](media/cqd-teams-aa-cq-historical-report-sample-cq.png) , che mostra i dati analitici per le chiamate in arrivo nelle code di chiamata.
- [Sequenza temporale agente](media/cqd-teams-aa-cq-historical-report-sample-at.png) : mostra una visualizzazione sequenza temporale degli agenti attivi nelle chiamate in coda di chiamata.

Questi report usano i dati dell'archivio dati [Call Quality Dashboard](CQD-Power-BI-query-templates.md) . I report consentono alle organizzazioni di segnalare il numero di chiamate elaborate da operatori automatici e code di chiamata.  I report forniscono anche informazioni dettagliate sulle prestazioni dell'agente nelle code di chiamata.

### <a name="v160-published-on-july-22-2022"></a>V1.60 pubblicato il 22 luglio 2022

## <a name="prerequisites"></a>Prerequisiti

### <a name="power-bi-desktop"></a>Power BI Desktop
Devi aver installato Power BI Desktop. Puoi installarlo da [Microsoft Windows Store](https://aka.ms/pbidesktopstore).

È possibile usare la versione gratuita di Power BI Desktop. La versione minima compatibile è 2.85.681.0 (settembre 2020).

### <a name="permissions-to-access-the-cqd-pipeline"></a>Autorizzazioni per accedere alla pipeline di Call Quality Dashboard

L'account usato per visualizzare il report cronologico deve avere le autorizzazioni per accedere alla pipeline di dati di Call Quality Dashboard. Per altre informazioni, vedere [Ruolo di accesso a Call Quality Dashboard](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).

## <a name="installation"></a>Installazione 

I passaggi seguenti presuppongono che nel computer sia già installato Power BI Desktop e che l'account disponga delle autorizzazioni necessarie per accedere alla pipeline di dati di Call Quality Dashboard.

Eseguire le operazioni seguenti:

- Scaricare i [modelli di query di Power BI di Call Quality Dashboard](https://www.microsoft.com/download/details.aspx?id=102291) e salvare il file ZIP in una directory del computer.

- Fare doppio clic sul file ZIP per aprirlo.

- Fai doppio clic sul file modello "CQD Teams Auto Attendant & Call Queue Historical Report V1.60.pbit". Il Power BI Desktop dovrebbe avviarsi.

- Verrà richiesto di selezionare l'area della pipeline di dati di Call Quality Dashboard. Selezionare l'area geografica in cui si trova il tenant.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="Screenshot che seleziona l'area della pipeline di dati di Call Quality Dashboard.":::

- L'area geografica in cui si trova il tenant può essere ottenuta utilizzando il cmdlet [Get-CsTenant](/powershell/module/skype/get-cstenant) .

    ```PowerShell
    (Get-CsTenant).ServiceInstance


    microsoftcommunicationsonline/noam-4a-s7
    ```

    - L'area verrà visualizzata dopo il **/** come nell'esempio precedente in cui l'area è: noam

 - Il report verrà avviato con dati di esempio.
 
 - Per visualizzare i propri dati, selezionare **Aggiorna** nella scheda Home in Query in Power BI Desktop.

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="Screenshot che seleziona l'opzione di aggiornamento.":::

- Verrà richiesto di eseguire l'accesso. Seleziona **Account aziendale** e quindi **seleziona Accedi**.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="Screenshot che mostra l'accesso.":::

- Selezionare **Connetti** e osservare l'aggiornamento dei dati.

## <a name="data-latency-and-aa--cq-analytics"></a>Latenza dei dati e analisi di AA & CQ

I dati sono in genere disponibili entro 30 minuti dal completamento della chiamata; in alcuni casi, tuttavia, la visualizzazione dei dati può richiedere diverse ore. 

Sarà necessario aggiornare i dati per visualizzare i nuovi dati.

## <a name="customization"></a>Personalizzazione 

È possibile personalizzare alcuni aspetti della visualizzazione dei report, ad esempio l'aggiunta o la rimozione di campi da visualizzare nelle varie visualizzazioni, la modifica del tipo di grafico e così via.

Il report contiene tutte le metriche dei dati attualmente disponibili.

### <a name="change-color-schema"></a>Modificare lo schema dei colori 

I passaggi seguenti presuppongono che siano già stati completati i passaggi di installazione.

Eseguire le operazioni seguenti:
- Selezionare **la scheda Visualizza** sulla barra multifunzione.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="Screenshot che seleziona la scheda Visualizza per modificare la combinazione di colori.":::

- Selezionare lo schema colori nell'elenco a discesa.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="Screenshot che mostra varie combinazioni di colori.":::
  
## <a name="auto-attendant-and-call-queue-historical-reports-definitions"></a>Definizioni dei report cronologici dell'operatore automatico e della coda di chiamata

### <a name="cloud-auto-attendant-analytics"></a>Analisi operatore automatico cloud

#### <a name="report-description"></a>Descrizione del report

|Sezione Report                          |Descrizione                                                       |
|:---------------------------------------|:-----------------------------------------------------------------|
|Origine chiamata in arrivo<sup>1</sup>        |Distribuzione delle chiamate per origine chiamata interna/esterna             |
|Totali dei metodi di ricerca nella directory          |Distribuzione delle chiamate per tipo di ricerca                               |
|Azione chiamante                           |Distribuzione delle chiamate da parte del destinatario della chiamata                             |
|Risultato della chiamata                             |Distribuzione delle chiamate per stato di chiamata finale                          |
|Numero di azioni chiamante                     |Distribuzione delle chiamate per azione numero usata durante la chiamata        |


#### <a name="report-to-cqd-table-and-field-mapping"></a>Report sul mapping di tabelle e campi di Call Quality Dashboard

|Scheda Report            |Nome tabella report     |Filtro globale                          |
|:---------------------|:---------------------|:--------------------------------------|
|Operatore automatico        |fAutoAttendant        |AAStartTime è negli ultimi 28 giorni |


|Nome tabella report            |Nome tabella di origine            |Elaborazione       |
|:----------------------------|:----------------------------|:----------------|
|fAutoAttendant               |Operatore automatico                |Source = AutoAttendant, <br>#"Righe filtrate" = Table.SelectRows(Source, each true), <br>#"Operatore automatico" = Table.AddColumn(#"Righe filtrate", "Nome AA", ogni List.First(Text.Split([AAIdentity], "@"))), <br>#"Changed Type" = Table.TransformColumnTypes(#"Auto Attendant",{{"AAStartTime", type datetime}}), <br>#"Removed Columns" = Table.RemoveColumns(#"Changed Type",{"AAIdentity"}) |


|Sezione Report                                  |Campi utilizzati                              |Filtri applicati     |
|:-----------------------------------------------|:------------------------------------------|:-------------------|
|Selettore data                                   |AAStartTime                                |Nessuno                |
|Operatore automatico                                  |Nome AA                                    |Nessuno                |
|Origine chiamata in arrivo<sup>1</sup>                |Tipo di chiamata<br>TotalCallCount                |Chiamate esterne: il tipo di chiamata è esterno<br>Chiamate interne: il tipo di chiamata è interno |
|Totali dei metodi di ricerca nella directory                  |AADirectorySearchMethod<br>TotalCallCount  |AADirectorySearchMethod viene abs_search_dtmf o abs_search_name    |
|Azioni del chiamante                                  |AATransferAction<br>TotalCallCount         |Nessuno                                                             |
|Media dei secondi in AA<br>Media azioni chiamante |AAChainDuration<br>AACallerActionCount     |Nessuno                                                             |
|Risultati delle chiamate                                    |AACallResult<br>TotalCallCount             |Nessuno                                                             |
|Numero di azioni del chiamante                            |AACallerActionCount<br>TotalCallCount      |Nessuno                                                             |
|Sezione inferiore del report                         |Nome AA<br>AACallFlow<br>AACallResult<br>AAChainDuration<br>Tipo di chiamata<br>TotalCallCount |Nessuno                |

#### <a name="fautoattendant-cqd-fields-description"></a>fAutoAttendant CQD fields description

|Nome                                    |Tipo di dati                |Descrizione                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Nome AA                                 |Testo                     |Nome dell'account della risorsa associato a Operatore automatico<br><br>Se il nome completo Account risorsa è **aa_test@microsoft.com**, il valore sarà: **aa_test** |
|AACallerActionCount                     |Numero intero             |Riepiloga: Somma<br>Numero di azioni selezionate dal chiamante in Operatore automatico durante la chiamata  |
|AACallFlow                              |Testo                     |Incapsula i diversi stati della chiamata operatore automatico: valori possibili:<br><br>§ abs_search<br>§ annuncio<br>§ automatic_menu<br>§ call_termination<br>§ call_transfer<br>§ first_level_menu<br>§ main_menu<br>§ speech_input_confirmation<br>§ user_selection |
|AACallResult                            |Testo                     |Risultato finale della chiamata: valori possibili:<br><br>§ failed_to_establish_media (non è stato possibile stabilire la parte mediatica della chiamata)<br>§ failover_to_operator (chiamata trasferita all'operatore in genere a causa di un errore di sistema)<br>§ oaa_chain_too_long (troppe gambe nell'AA)<br>§ oaa_session_too_long (la sessione AA è durata troppo a lungo)<br>§ service_declined (AA non ha accettato la chiamata)<br>§ service_terminated (la configurazione AA disconnette la chiamata)<br>§ terminated_automatic_selection (la configurazione AA disconnette le chiamate)<br>§ terminated_no_operator (chiamata terminata per errore nessun operatore definito) <br>§ terminated_transfer_failed (chiamata terminata come trasferimento non riuscita - in genere al numero esapernale)<br>***§ transferred_to_operator*** (la chiamata è stata trasferita all'operatore - in genere a causa di un errore di input dell'utente)<br>§ transferred_to_receptionist (come transferred_to_operator)<br>§ transferred_to_self (la chiamata è stata restituita all'inizio dell'AA- in genere da un'opzione di annuncio di menu)<br>§ transferred_to_shared_voicemail (la chiamata è stata trasferita alla segreteria telefonica condivisa)<br>§ transferred_to_user (la chiamata è stata trasferita a un utente - include code di chiamata)<br>§ sconosciuto (si è verificato un errore sconosciuto)<br>§ user_terminated (chiamante riagganciato) |
|AAChainDuration                         |Numero decimale           |Riepiloga: Somma<br>Durata della chiamata in Operatore automatico                     |
|AAChainIndex                            |Testo                     |                                                                         |
|AAConnectivityType                      |Testo                     |Tipo di chiamata: valori possibili:<br><br>§ Chiamata esterna<br>§ Chiamata interna |
|AACount                                 |Testo                     |Numero di operatori automatici coinvolti nella chiamata                               |
|AADirectorySearchMethod                 |Testo                     |Metodo di ricerca dell'ultima rubrica: valori possibili:<br><br>§ abs_search_dtmf<br>§ abs_search_extension_x<br>§ abs_search_name |
|AAStartTime                             |Data/ora                |Ora di inizio chiamata Operatore automatico                                           |
|AATransferAction                        |Testo                     |Tipo di destinazione trasferimento chiamata: valori possibili:<br><br>***§ applicazione - entità applicazione** _<br>vocale§ external_pstn<br>_*_§ hunt_group - Entità_*_<br>_* coda di chiamata _§ orgaa - Entità Operatore automatico organizzazione_**<br>§ shared_voicemail<br>§ sconosciuto<br>§ utente |
|Tipo di chiamata<sup>1</sup>                   |Testo                     |Tipo di chiamata: valori possibili:<br><br>§ Esterno<br>§ Interno         |
|IsAAInvolved                            |Testo                     |Sempre 1                                                                 |
|PSTNMinutes                             |Numero intero             |Riepiloga: Somma<br>Utilizzo totale dei minuti                                     |
|TotalCallCount                          |Numero intero             |Riepiloga: Somma<br>Sempre 1 - usato per fornire la somma di tutte le chiamate            |


### <a name="cloud-call-queue-analytics"></a>Analisi delle code di chiamata cloud

#### <a name="report-description"></a>Descrizione del report

|Sezione Report                          |Descrizione                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|Origine chiamata in arrivo<sup>1</sup>        |Distribuzione della chiamata dall'origine della chiamata interna/esterna              |
|Volume chiamate                             |Distribuzione della chiamata per code di chiamata                                |
|Risultato del chiamante                           |Distribuzione della chiamata per risultato della chiamata                                |
|Azione totale chiamata timeout/overflow      |Distribuzione della chiamata NON inoltrata (abbandonata) in base al risultato della chiamata       |
|Trasferire/Inoltrare totali di destinazione          |Distribuzione della chiamata inoltrata dal risultato della chiamata                      |
|Rapporto chiamate abbandonate                   |Rapporto tra numero di chiamate riuscite e abbandonate                        |
|Durata media della sessione (secondi)        |Durata della chiamata in secondi raggruppata per chiamate abbandonate/riuscite       |

#### <a name="report-to-cqd-table-and-field-mapping"></a>Report sul mapping di tabelle e campi di Call Quality Dashboard

|Scheda Report         |Nomi tabella report                                                          |Filtro globale |
|:------------------|:---------------------------------------------------------------------------|:-------------|
|Coda di chiamata         |Date<br>dCQ-CQIdenity<br>fCallQueueAnalytics<br>fCallQueueFinalStateAction |Nessuno          |
 
|Nome tabella report            |Nome tabella di origine            |Elaborazione       |
|:----------------------------|:----------------------------|:----------------|
|Date                        |Date                        |Nessuno             |
|dCQ-CQIdentity               |CallQueueAnalytics           |Source = CallQueueAnalytics, <br>#"Removed Columns" = Table.RemoveColumns(Source,{"Call Count", "Call Queue Call Result", "Date", "PSTN Connectivity Type", "Call Queue Target Type", "PSTN Total Minutes"}),<br>Distinct = Table.Distinct(#"Colonne rimosse") |
|fCallQueueAnalytics          |CallQueueAnalytics           |Nessuno             |
|fCallQueueFinalStateAction   |CallQueueFinalStateAction    |Nessuno             |

|Sezione Report                      |Tabella -> Campi utilizzati                |Filtri applicati       |
|:-----------------------------------|:-------------------------------------|:---------------------|
|Selettore data                       |Dates -> DateTime                     |Nessuno                  |
|Identità coda di chiamata                 |dCQ-CQIdentity -> l'identità della coda di chiamata |Nessuno                  |
|Origine chiamata in arrivo<sup>1</sup>    |fCallQueueAnalytics -> Numero chiamate<br>fCallQueueAnalytics -> tipo di chiamata    |Chiamate esterne: il tipo di chiamata è esterno<br>Chiamate interne: il tipo di chiamata è interno |
|Avg Waiting Time                    |fCallQueueFinalStateAction -> durata media della chiamata (secondi) |Prima del trasferimento: il risultato della chiamata in coda di chiamata viene agent_joined_conference o transferred_to_agent<br>Prima della chiamata: il risultato della chiamata in coda di chiamata non è agent_joined_conference o transferred_to_agent |
|Risultato chiamata                         |fCallQueueAnalytics -> Numero chiamate<br>fCallQueueAnalytics -> risultato della chiamata in coda di chiamata | Nessuno |
|Azione totale chiamate timeout/overflow |fCallQueueFinalStateAction -> Numero chiamate<br>fCallQueueFinalStateAction -> azione di stato finale della coda di chiamata |L'azione di stato finale della coda di chiamata non è inoltrata |
|Transfer/Forard target totals       |fCallQueueAnalytics -> Numero chiamate<br>fCallQueueAnalytics -> tipo di destinazione coda di chiamata |Nessuno |
|Volumi delle chiamate                        |fCallQueueAnalytics -> Numero chiamate<br>fCallQueueAnalytics -> Identificazione coda di chiamata<br>fCallQueueAnalytics -> Date |Nessuno |
|Chiamate abbandonate                     |fCallQueueAnalytics -> %Abandoned Calls<br>fCallQueueAnalytics -> Numero chiamate<br>fCallQueueAnalytics -> Date<br>fCallQueueAnalytics -> IsAbandoned |IsAbandoned è True |
|Durata media sessione (secondi)    |fCallQueueFinalStateAction -> durata media della chiamata<br>fCallQueueFinalStateAction -> Date<br>fCallQueueFinalStateAction -> IsAbandoned |Nessuno |

#### <a name="dcq-cqidenity-cqd-fields-description"></a>dCQ-CQIdenity CQD fields description

|Nome                                    |Tipo di dati                |Descrizione                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Identità coda di chiamata                     |Testo                     |Nome dell'account della risorsa collegato alla coda di chiamata<br><br>Se il nome completo Account risorsa è **cq_test@microsoft.com**, il valore sarà: **cq_test** |

#### <a name="fcallqueueanalytics-cqd-fields-description"></a>Descrizione dei campi CQD di fCallQueueAnalytics

|Nome                                    |Tipo di dati                |Descrizione                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|Numero chiamate                              |Numero intero             |Riepiloga: Somma<br>Numero di chiamate                                          |
|Risultato chiamata in coda di chiamata                  |Testo                     |Stato finale chiamata in coda di chiamata: valori possibili:<br><br>§ agent_joined_conference (risposta alle chiamate in modalità conferenza)<br>§ rifiutata<br>§ disconnesso<br>§ errore<br>§ non riuscito<br>§ non valido<br>§ overflown (condizione di overflow soddisfatta)<br>§ timed_out (condizione di timeout soddisfatta)<br>§ transferred_to_agent (risposta alle chiamate in modalità tranfer {default}) |
|Identità coda di chiamata                     |Testo                     |Nome dell'account della risorsa collegato alla coda di chiamata<br><br>Se il nome completo Account risorsa è **cq_test@microsoft.com**, il valore sarà: **cq_test** |
|Tipo di destinazione coda di chiamata                  |Testo                     |***Tipo di destinazione del reindirizzamento delle chiamate: valori possibili:***<br><br>§ ApplicationEndpoint<br>§ Cassetta postale<br>§ Altro<br>§ Utente |
|Tipo di chiamata<sup>1</sup>                   |Testo                     |Tipo di chiamata: valori possibili:<br><br>§ Esterno<br>§ Interno           |
|Data                                    |Data/ora                |Data e ora di inizio delle chiamate in coda di chiamata (ora) (UTC)                           | 
|IsAbandoned                             |Vero/falso               |True se la chiamata non riceve risposta da un agente                                   |
|Tipo di connettività PSTN                  |Testo                     |Tipo di chiamata: valori possibili:<br><br>§ Chiamata esterna<br>§ Chiamata interna   |
|Totale minuti PSTN                      |Numero intero             |Riepiloga: Somma<br>Numero totale di minuti di utilizzo per le chiamate PSTN                       |

#### <a name="fcallqueueanalytics-measures-description"></a>Descrizione delle misure di fCallQueueAnalytics

|Nome                                    |Tipo di dati                |Descrizione                              |
|:---------------------------------------|:------------------------|:----------------------------------------|
|***% chiamate abbandonate***                 |Percentuale               |Misura: Numero di chiamate abbandonate / Chiamate totali    |
|Totale chiamate                             |Numero intero             |Misura: Sum agent ha risposto alle chiamate        |
|TotalCallCount                          |Numero intero             |Misura: Somma(Numero chiamate)                 |

#### <a name="fcallqueuefinalstateaction--cqd-fields-description"></a>Descrizione dei campi fCallQueueFinalStateAction CQD

|Nome                                    |Tipo di dati                |Descrizione                                        |
|:---------------------------------------|:------------------------|:--------------------------------------------------|
|Durata media chiamata (secondi)         |Numero decimale           |Riepiloga: Somma<br>Durata media della chiamata in secondi |
|Numero chiamate                              |Numero intero             |Riepiloga: Somma<br>Numero di chiamate                  |
|Risultato chiamata in coda di chiamata                  |Testo                     |Stato finale chiamata in coda di chiamata: valori possibili:<br><br>§ agent_joined_conference (risposta alle chiamate in modalità conferenza)<br>§ rifiutata<br>§ disconnesso<br>§ errore<br>§ non riuscito<br>§ non valido<br>§ overflown (condizione di overflow soddisfatta)<br>§ timed_out (condizione di timeout soddisfatta)<br>§ transferred_to_agent (risposta alle chiamate in modalità di trasferimento {default} |
|Azione di stato finale sulla coda di chiamata           |Testo                     |Azione finale coda di chiamata: valori possibili:<br><br>§ disconnetti (chiamate timed_out)<br>§ disconnect_with_busy (chiamate in eccesso)<br>§ failed_to_accept_call<br>§ avanti<br>§ shared_voicemail<br>§ altro<br>§ segreteria telefonica |
|Identità coda di chiamata                     |Testo                     |Nome dell'account della risorsa collegato alla coda di chiamata<br><br>Se il nome completo Account risorsa è **cq_test@microsoft.com**, il valore sarà: **cq_test** |
|Data                                    |Data/ora                |Data e ora di inizio delle chiamate in coda di chiamata (ora) (UTC)   |
|IsAbandoned                             |Vero/falso               |True se la chiamata non riceve risposta da un agente           |


### <a name="cloud-call-queue-agent-timeline"></a>Sequenza temporale agente coda di chiamata cloud

#### <a name="report-description"></a>Descrizione del report

|Sezione Report                                          |Descrizione                                                  |
|:-------------------------------------------------------|:------------------------------------------------------------|
|# chiamate da parte dell'agente                                        |Distribuzione della chiamata per coda di chiamata e agente                 |
|Durata totale della chiamata (secondi) per agente e coda di chiamata   |Durata totale (secondi) della chiamata da parte dell'agente e della coda di chiamata     |
|Durata media della chiamata (secondi) in base al nome dell'agente           |Durata media (secondi) della chiamata da parte dell'agente                  |

#### <a name="report-to-cqd-table-and-field-mapping"></a>Report sul mapping di tabelle e campi di Call Quality Dashboard

|Scheda Report         |Nomi tabella report        |Filtro globale |
|:------------------|:-------------------------|:-------------|
|Sequenza temporale dell'agente     |fAgentTimelineAnalytics   |Nessuno          |
 
|Nome tabella report            |Nome tabella di origine            |Elaborazione       |
|:----------------------------|:----------------------------|:----------------|
|fAgentTimelineAnalytics      |AgentTimelineAnalytics       |Source = AgentTimelineAnalytics, <br>#"Changed Type" = Table.TransformColumnTypes(Source,{{"Call Count", Int64.Type}, {"Call Duration (Minute)", Int64.Type}, {"Average Call Duration (Second)", type number}, {"Date", type date}})|

|Sezione Report                                |Campi utilizzati                         |Filtri applicati       |
|:---------------------------------------------|:-------------------------------------|:---------------------|
|Nome agente                                    |Nome agente                            |Nessuno                  |
|Nome coda di chiamata                               |Nome coda di chiamata                       |Nessuno                  |
|#Calls dall'agente                               |Nome agente<br>Numero chiamate<br>Data      |Nessuno                  |
|Distribuzione per agente e coda di chiamata          |Nome agente<br>Numero chiamate<br>Durata chiamata (minuti)<br>Nome coda di chiamata |Nessuno                      |
|In basso a sinistra                                   |Nome agente<br>Durata media chiamata (secondo)<br>Numero chiamate<br>Durata chiamata (Minuti)<br>Nome coda di chiamata | Nessuno |
|Durata media chiamata (secondi) in base al nome dell'agente |Nome agente<br>Durata media chiamata (secondo)<br>Numero chiamate<br>Durata chiamata (Minuti)<br>Nome coda di chiamata | Nessuno |

#### <a name="fagenttimelineanalytics-cqd-fields-description"></a>Descrizione dei campi di fAgentTimelineAnalytics CQD

|Nome                                    |Tipo di dati                |Descrizione                                         |
|:---------------------------------------|:------------------------|:---------------------------------------------------|
|Nome agente                              |Testo                     |UPN utente<br>Se il nome utente completo è **user@microsoft.com**, il valore sarà: **utente** |
|Durata media chiamata (secondo)          |Numero decimale           |Riepiloga: Somma<br>Durata media delle chiamate in coda di chiamata in secondi |
|Numero chiamate                              |Numero intero             |Riepiloga: Somma<br>Numero di chiamate presentate all'agente     |
|Durata chiamata (Minuti)                  |Numero intero             |Riepiloga: Somma<br>Durata totale delle chiamate in coda di chiamata in minuti (arrotondata per eccesso al minuto più vicino)  |
|Nome coda di chiamata                         |Testo                     |Nome dell'account della risorsa collegato alla coda di chiamata<br><br>Se il nome completo Account risorsa è **cq_test@microsoft.com**, il valore sarà: **cq_test** |
|Data                                    |Data                     |                                                    |


> [!NOTE]
> 1) Questo report mostra i conteggi delle chiamate dal punto di vista degli agenti e quindi il totale delle chiamate in questo report sarà in genere superiore al numero totale di chiamate nel report **Analisi coda di chiamata cloud** . Ogni chiamata in coda può essere presentata a uno o più agenti almeno una volta prima che risponda. Ogni chiamata in coda di chiamata presentata a un agente viene conteggiata in questo report, anche se l'agente non ha risposto. La differenza nel conteggio delle chiamate tra questi due rapporti è più pronunciata con l'opzione **routing Attendant** che squilla ogni agente per ogni chiamata. 
> 2) Quando una chiamata arriva per la prima volta alla prima coda di chiamata, se il numero di chiamate già in attesa in tale coda supera il limite di **gestione di overflow** delle chiamate e se l'opzione di reindirizzamento invia chiamate a una seconda coda di chiamata, gli agenti nella seconda coda di chiamata verranno visualizzati come nella prima coda di chiamata in questo report. 

## <a name="known-issues"></a>Problemi noti

- La coda di chiamata e gli operatori automatici sono mostrati dall'ID dell'account della risorsa invece che dai nomi della coda di chiamata o dell'operatore automatico.  Per mostrare tutto il traffico per un operatore automatico o una coda di chiamata, è necessario selezionare tutti gli account delle risorse assegnati all'operatore automatico o alla coda di chiamata.

- Solo 28 giorni di cronologia sono disponibili nel dashboard in quanto i dati della coda di chiamata/dell'operatore automatico sono considerati dati personali ed è soggetto a criteri di conservazione della privacy dei dati.

- In alcuni scenari, l'agente ha risposto al numero di chiamate nel rapporto Sequenza temporale agente coda di chiamata cloud può essere diverso rispetto al numero di chiamate mostrate nella cronologia chiamate client di Teams. La cronologia delle chiamate del client di Teams è corretta. Il supporto è in fase di analisi, ma al momento non è disponibile alcun tempo stimato per la riparazione.

- <sup>1</sup> **L'origine della chiamata in arrivo** nell'operatore automatico e nei grafici della coda di chiamata mostra l'origine finale della coda di chiamata anziché l'origine iniziale della coda di chiamata. Ad esempio, se un operatore automatico riceve una chiamata esterna e trasferisce la chiamata a un altro operatore automatico o coda di chiamata, **l'origine della chiamata in arrivo** verrà segnalata come Interna.

## <a name="version-history"></a>Cronologia versioni
|Versione  |Data di pubblicazione     |Filename                                                           |Descrizione                                         |
|:--------|:------------------|:------------------------------------------------------------------|:---------------------------------------------------|
|1.60     |22 luglio 2022      |CQD Teams Auto Attendant & Call Queue Historical Report V1.60.pbit |Fare riferimento a:<br>CQD Teams Auto Attendant & Call Queue Historical Reports - Change Log.docx in the downloaded zip file for a list of changes                                                                             |
|1.00     |5 novembre 2020   |CQ e AA combinati Analytics 20201105.pbit                         |Rilascio iniziale                                     |




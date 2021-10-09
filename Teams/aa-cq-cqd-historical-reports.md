---
title: Operatore automatico & cronologia della coda di chiamata
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
description: Informazioni su come usare il report Power BI qualità delle chiamate per visualizzare i Operatore automatico e la cronologia della coda di chiamata.
ms.openlocfilehash: 4594a673225a167e762bcfee63067f70e7fe10b4
ms.sourcegitcommit: e7f6125d348b6f14eeba28e09d5f1975ad4fde69
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2021
ms.locfileid: "60249558"
---
# <a name="auto-attendant--call-queue-historical-report"></a>Operatore automatico & cronologia della coda di chiamata

Il modello CQD Teams Operatore automatico & report cronologico coda di chiamata Power BI report fornisce i tre report seguenti:

- [Operatore automatico,](media/cqd-teams-aa-cq-historical-report-sample-aa.png) che mostra l'analisi delle chiamate in arrivo negli operatori automatici.
- [Coda di chiamata:](media/cqd-teams-aa-cq-historical-report-sample-cq.png) mostra l'analisi delle chiamate in arrivo nelle code di chiamata.
- [Sequenza temporale agente:](media/cqd-teams-aa-cq-historical-report-sample-at.png) mostra una visualizzazione sequenza temporale degli agenti attivi nelle chiamate in coda di chiamata.

Questi report usano i dati [dell'archivio dati di Call Quality Dashboard.](CQD-Power-BI-query-templates.md) Consentono alle organizzazioni di segnalare il numero di chiamate elaborate dagli operatori automatici e dalle code di chiamata.  Forniscono anche informazioni approfondite sulle prestazioni degli agenti nelle code di chiamata.

## <a name="prerequisites"></a>Prerequisiti

### <a name="power-bi-desktop"></a>Power BI Desktop
È necessario avere installato Power BI Desktop. È possibile installarlo da [Microsoft Windows Store.](https://aka.ms/pbidesktopstore)

È possibile usare la versione gratuita di Power BI Desktop. La versione minima compatibile è 2.85.681.0 (settembre 2020).

### <a name="permissions-to-access-the-cqd-pipeline"></a>Autorizzazioni per accedere alla pipeline CQD

L'account che si usa per visualizzare il report cronologico AA & CQ Analytics deve avere le autorizzazioni per accedere alla pipeline di dati CQD. Per altre informazioni, vedere [Ruolo di accesso CQD.](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)

## <a name="installation"></a>Installazione 

I passaggi seguenti presuppongono che Power BI Desktop nel computer e che l'account abbia le autorizzazioni necessarie per accedere alla pipeline di dati CQD.

Eseguire la procedura seguente:

- Scaricare i [modelli di query Power BI CQD](https://www.microsoft.com/download/details.aspx?id=102291) e salvare il file ZIP in una directory del computer.

- Fare doppio clic sul file ZIP per aprirlo.

- Fare doppio clic sul file di modello "CQ and AA combined Analytics 20201105.pbit" e Power BI Desktop dovrebbe essere avviato.

- Verrà richiesto di selezionare l'area della pipeline di dati CQD. Selezionare l'area geografica in cui si trova il tenant.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="Screenshot che seleziona l'area della pipeline di dati CQD.":::

- L'area geografica in cui si trova il tenant può essere ottenuta usando il cmdlet [Get-CsTenant.](/powershell/module/skype/get-cstenant)

    ```PowerShell
    (Get-CsTenant).ServiceInstance


    microsoftcommunicationsonline/noam-4a-s7
    ```

    - L'area verrà visualizzata dopo il come nell'esempio precedente in cui è **/** presente l'area: noam

 - Il report verrà avviato con dati di esempio.
 
 - Per visualizzare i propri dati, selezionare **Aggiorna** nella scheda Home in Query in Power BI Desktop.

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="Screenshot che seleziona l'opzione di aggiornamento.":::

- Verrà quindi richiesto di eseguire l'accesso. Selezionare **Account organizzazione** e quindi **Accedi.**

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="Screenshot che mostra l'accesso.":::

- Selezionare **Connessione** e osservare l'aggiornamento dei dati.

## <a name="data-latency-and-aa--cq-analytics"></a>Latenza dei dati e analisi AA & CQ

I dati saranno disponibili nella pipeline di dati CQD entro 30 minuti.

Sarà necessario aggiornare i dati per visualizzare i nuovi dati di analisi. 

## <a name="customization"></a>Personalizzazione 

È possibile personalizzare alcuni aspetti della visualizzazione dei report, ad esempio l'aggiunta o la rimozione di campi da visualizzare nelle varie visualizzazioni, la modifica del tipo di grafico e così via.

Non è possibile aggiungere altri campi dati al report.

### <a name="change-color-schema"></a>Modificare lo schema dei colori 

I passaggi seguenti presuppongono che la procedura di installazione sia già stata completata.

Eseguire la procedura seguente:
- Selezionare **la scheda Visualizza** sulla barra multifunzione.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="Screenshot che seleziona la scheda Visualizza per cambiare la combinazione di colori.":::

- Selezionare lo schema colori nell'elenco a discesa.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="Screenshot che mostra varie combinazioni di colori.":::
  
## <a name="auto-attendant-and-call-queue-historical-reports-definitions"></a>Operatore automatico dei report cronologici della coda di chiamata e della coda di chiamata

### <a name="cloud-auto-attendant-analytics"></a>Analisi Operatore automatico cloud

#### <a name="report-description"></a>Descrizione del report

|Sezione report                          |Descrizione                                                       |
|:---------------------------------------|:-----------------------------------------------------------------|
|Origine chiamata in arrivo<sup>1</sup>        |Distribuzione delle chiamate per fonte di chiamata interna/esterna             |
|Totali dei metodi di ricerca nella directory          |Distribuzione delle chiamate per tipo di ricerca                               |
|Azione chiamante                           |Distribuzione delle chiamate per ricevitore di chiamate                             |
|Risultato della chiamata                             |Distribuzione delle chiamate per stato di chiamata finale                          |
|Conteggio azioni chiamante                     |Distribuzione delle chiamate per azione per numero usata durante la chiamata        |


#### <a name="report-to-cqd-table-and-field-mapping"></a>Mapping tra tabelle e campi in CQD

|Scheda Report            |Nome tabella report     |Filtro globale                          |
|:---------------------|:---------------------|:--------------------------------------|
|Operatore automatico        |fAutoAttendant        |AAStartTime rientra negli ultimi 28 giorni |


|Nome tabella report            |Nome tabella di origine            |Elaborazione in corso       |
|:----------------------------|:----------------------------|:----------------|
|fAutoAttendant               |AutoAttendant                |Source = AutoAttendant, <br>#"Righe filtrate" = Table.SelectRows(Source, each true), <br>#"Operatore automatico" = Table.AddColumn(#"Filtered Rows", "AA Name", each List.First(Text.Split([AAIdentity], "@"))), <br>#"Changed Type" = Table.TransformColumnTypes(#"Operatore automatico",{{"AAStartTime", type datetime}}), <br>#"Colonne rimosse" = Table.RemoveColumns(#"Changed Type",{"AAIdentity"}) |


|Sezione report                                  |Campi usati                              |Filtri applicati     |
|:-----------------------------------------------|:------------------------------------------|:-------------------|
|Selezione data                                   |AAStartTime                                |Nessuno                |
|Operatore automatico                                  |Nome AA                                    |Nessuno                |
|Origine chiamata in arrivo<sup>1</sup>                |Tipo di chiamata<br>TotalCallCount                |Chiamate esterne: il tipo di chiamata è Esterno<br>Chiamate interne: il tipo di chiamata è interno |
|Totali dei metodi di ricerca nella directory                  |AADirectorySearchMethod<br>TotalCallCount  |AADirectorySearchMethod è abs_search_dtmf o abs_search_name    |
|Azioni chiamante                                  |AATransferAction<br>TotalCallCount         |Nessuno                                                             |
|Media dei secondi in AA<br>Media delle azioni chiamanti |AAChainDuration<br>AACallerActionCount     |Nessuno                                                             |
|Risultati della chiamata                                    |AACallResult<br>TotalCallCount             |Nessuno                                                             |
|Conteggio azioni chiamante                            |AACallerActionCount<br>TotalCallCount      |Nessuno                                                             |
|Sezione inferiore del report                         |Nome AA<br>AACallFlow<br>AACallResult<br>AAChainDuration<br>Tipo di chiamata<br>TotalCallCount |Nessuno                |

#### <a name="fautoattendant-cqd-fields-description"></a>fAutoAttendant CQD fields description

|Nome                                    |Tipo di dati                |Descrizione                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Nome AA                                 |testo                     |Nome dell'account della risorsa Operatore automatico<br><br>Se il nome completo dell'account della **risorsa aa_test@microsoft.com,** questo valore sarà: **aa_test** |
|AACallerActionCount                     |numero intero             |Riepiloga: Somma<br>Numero di azioni selezionate dal chiamante in Operatore automatico durante la chiamata  |
|AACallFlow                              |testo                     |Incapsula i diversi stati di Operatore automatico chiamata-- valori possibili:<br><br>§ abs_search<br>§ annuncio<br>§ automatic_menu<br>§ call_termination<br>§ call_transfer<br>§ first_level_menu<br>§ main_menu<br>§ speech_input_confirmation<br>§ user_selection |
|AACallResult                            |testo                     |Risultato della chiamata finale: valori possibili:<br><br>§ failed_to_establish_media<br>§ failover_to_operator<br>§ oaa_chain_too_long<br>§ oaa_session_too_long<br>§ service_declined<br>§ service_terminated<br>§ terminated_automatic_selection<br>§ terminated_no_operator<br>§ terminated_transfer_failed<br>***§ transferred_to_operator***<br>§ transferred_to_receptionist<br>§ transferred_to_self<br>§ transferred_to_shared_voicemail<br>§ transferred_to_user<br>§ sconosciuto<br>§ user_terminated |
|AAChainDuration                         |numero decimale           |Riepiloga: Somma<br>Durata della chiamata in Operatore automatico                     |
|AAChainIndex                            |testo                     |                                                                         |
|AAConnectivityType                      |testo                     |Tipo di chiamata: valori possibili:<br><br>§ ExternalCall<br>§ InternalCall |
|AACount                                 |testo                     |Numero di operatori automatici coinvolti nella chiamata                               |
|AADirectorySearchMethod                 |testo                     |Ultimo metodo di ricerca della rubrica: valori possibili:<br><br>§ abs_search_dtmf<br>§ abs_search_extension_x<br>§ abs_search_name |
|AAStartTime                             |data/ora                |Operatore automatico'ora di inizio della chiamata                                           |
|AATransferAction                        |testo                     |Tipo di destinazione trasferimento chiamata : valori possibili:<br><br>***§ application - voice application entity**§_<br> external_pstn <br>_§ hunt_group - Call Queue *_entity_* _<br>_ * _§ orgaa - Organizational Operatore automatico entity_**<br>§ shared_voicemail<br>§ sconosciuto<br>§ utente |
|Tipo di<sup>chiamata 1</sup>                   |testo                     |Tipo di chiamata: valori possibili:<br><br>§ Esterno<br>§ Interno         |
|IsAAInvolved                            |testo                     |Sempre 1                                                                 |
|PSTNMinutes                             |numero intero             |Riepiloga: Somma<br>Utilizzo totale dei minuti                                     |
|TotalCallCount                          |numero intero             |Riepiloga: Somma<br>Sempre 1 - usato per fornire la somma di tutte le chiamate            |


### <a name="cloud-call-queue-analytics"></a>Analisi delle code di chiamata cloud

#### <a name="report-description"></a>Descrizione del report

|Sezione report                          |Descrizione                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|Origine chiamata in arrivo<sup>1</sup>        |Distribuzione della chiamata da parte dell'origine chiamata interna/esterna              |
|Volume delle chiamate                             |Distribuzione delle chiamate in base alle code di chiamata                                |
|Risultato chiamante                           |Distribuzione del risultato della chiamata per chiamata                                |
|Azione totale chiamata Timeout/Overflow      |Distribuzione della chiamata NON inoltrata(abbandonata) in base al risultato della chiamata       |
|Totali destinazione trasferimento/inoltro          |Distribuzione della chiamata inoltrata dal risultato della chiamata                      |
|Rapporto chiamate abbandonate                   |Rapporto tra il numero di chiamate riuscite e il numero di chiamate abbandonate                        |
|Durata media della sessione (secondi)        |Durata delle chiamate in secondi raggruppate per chiamate abbandonate/riuscite       |

#### <a name="report-to-cqd-table-and-field-mapping"></a>Mapping tra tabelle e campi in CQD

|Scheda Report         |Nomi tabella report                                                          |Filtro globale |
|:------------------|:---------------------------------------------------------------------------|:-------------|
|Coda di chiamata         |Date<br>dCQ-CQIdenity<br>fCallQueueAnalytics<br>fCallQueueFinalStateAction |Nessuno          |
 
|Nome tabella report            |Nome tabella di origine            |Elaborazione in corso       |
|:----------------------------|:----------------------------|:----------------|
|Date                        |Date                        |Nessuno             |
|dCQ-CQIdentity               |CallQueueAnalytics           |Source = CallQueueAnalytics, <br>#"Colonne rimosse" = Table.RemoveColumns(Source,{"Call Count", "Call Queue Call Result", "Date", "PSTN Connectivity Type", "Call Queue Target Type", "PSTN Total Minutes"}),<br>Distinct = Table.Distinct(#"Colonne rimosse") |
|fCallQueueAnalytics          |CallQueueAnalytics           |Nessuno             |
|fCallQueueFinalStateAction   |CallQueueFinalStateAction    |Nessuno             |

|Sezione report                      |Tabella -> campi usati                |Filtri applicati       |
|:-----------------------------------|:-------------------------------------|:---------------------|
|Selezione data                       |Date -> DateTime                     |Nessuno                  |
|Identità coda di chiamata                 |dCQ-CQIdentity -> Call Queue Identity |Nessuno                  |
|Origine chiamata in arrivo<sup>1</sup>    |fCallQueueAnalytics -> Numero chiamate<br>fCallQueueAnalytics -> Call Type    |Chiamate esterne: il tipo di chiamata è Esterno<br>Chiamate interne: il tipo di chiamata è interno |
|Tempo di attesa medio                    |fCallQueueFinalStateAction -> durata media delle chiamate (secondi) |Prima del trasferimento: il risultato della chiamata in coda agent_joined_conference o transferred_to_agent<br>Prima del blocco: il risultato della chiamata in coda di chiamata non agent_joined_conference o transferred_to_agent |
|Risultato chiamata                         |fCallQueueAnalytics -> Numero chiamate<br>fCallQueueAnalytics -> call queue call result | Nessuno |
|Azione totale chiamate timeout/overflow |fCallQueueFinalStateAction -> Call Count<br>fCallQueueFinalStateAction -> Call Queue Final State Action |L'azione sullo stato finale della coda di chiamata non è inoltrata |
|Totali destinazione trasferimento/ford       |fCallQueueAnalytics -> Numero chiamate<br>fCallQueueAnalytics -> di destinazione della coda di chiamata |Nessuno |
|Volumi di chiamata                        |fCallQueueAnalytics -> Numero chiamate<br>fCallQueueAnalytics -> Coda di chiamata Identifica<br>fCallQueueAnalytics -> Date |Nessuno |
|Chiamate abbandonate                     |fCallQueueAnalytics -> %Abandoned Calls<br>fCallQueueAnalytics -> Numero chiamate<br>fCallQueueAnalytics -> Date<br>fCallQueueAnalytics -> IsAbandoned |IsAbandoned è True |
|Durata media sessione (secondi)    |fCallQueueFinalStateAction -> durata media delle chiamate<br>fCallQueueFinalStateAction -> Date<br>fCallQueueFinalStateAction -> IsAbandoned |Nessuno |

#### <a name="dcq-cqidenity-cqd-fields-description"></a>Descrizione dei campi CQD dCQ-CQIdenity

|Nome                                    |Tipo di dati                |Descrizione                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Identità coda di chiamata                     |testo                     |Nome dell'account della risorsa allegato alla coda di chiamata<br><br>Se il nome completo dell'account della **risorsa cq_test@microsoft.com** il valore sarà: **cq_test** |

#### <a name="fcallqueueanalytics-cqd-fields-description"></a>fCallQueueAnalytics Descrizione dei campi CQD

|Nome                                    |Tipo di dati                |Descrizione                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|Conteggio chiamate                              |numero intero             |Riepiloga: Somma<br>Numero di chiamate                                          |
|Risultato della chiamata in coda di chiamata                  |testo                     |Stato finale chiamata in coda di chiamata -- valori possibili:<br><br>§ agent_joined_conference<br>§ rifiutato<br>§ disconnesso<br>§ errore<br>§ non riuscito<br>§ non valido<br>§ overflow<br>§ timed_out<br>§ transferred_to_agent |
|Identità coda di chiamata                     |testo                     |Nome dell'account della risorsa allegato alla coda di chiamata<br><br>Se il nome completo dell'account della **risorsa cq_test@microsoft.com** il valore sarà: **cq_test** |
|Tipo di destinazione coda di chiamata                  |testo                     |***Tipo di destinazione del reindirizzamento delle chiamate: valori possibili:***<br><br>§ ApplicationEndpoint<br>§ Cassetta postale<br>§ Altro<br>§ Utente |
|Tipo di<sup>chiamata 1</sup>                   |testo                     |Tipo di chiamata: valori possibili:<br><br>§ Esterno<br>§ Interno           |
|Data                                    |data/ora                |Data e ora di inizio della chiamata in coda di chiamata (ora) (UTC)                           | 
|IsAbandoned                             |vero/falso               |True se la chiamata non viene risolta da un agente                                   |
|Tipo di connettività PSTN                  |testo                     |Tipo di chiamata: valori possibili:<br><br>§ ExternalCall<br>§ InternalCall   |
|Minuti totali PSTN                      |numero intero             |Riepiloga: Somma<br>Utilizzo totale dei minuti per le chiamate PSTN                       |

#### <a name="fcallqueueanalytics-measures-description"></a>fCallQueueAnalytics measures description

|Nome                                    |Tipo di dati                |Descrizione                              |
|:---------------------------------------|:------------------------|:----------------------------------------|
|***% chiamate abbandonate***                 |percentuale               |Misura: TotalCallCount /Total Calls<br>Rapporto tra il numero di chiamate riuscite e il numero di chiamate abbandonate    |
|Totale chiamate                             |numero intero             |Misura: l'agente sum ha risposto alle chiamate        |
|TotalCallCount                          |numero intero             |Misura: Somma(Conteggio chiamate)                 |

#### <a name="fcallqueuefinalstateaction--cqd-fields-description"></a>fCallQueueFinalStateAction Descrizione dei campi CQD

|Nome                                    |Tipo di dati                |Descrizione                                        |
|:---------------------------------------|:------------------------|:--------------------------------------------------|
|Durata media chiamata (secondi)         |numero decimale           |Riepiloga: Somma<br>Durata media delle chiamate in secondi |
|Conteggio chiamate                              |numero intero             |Riepiloga: Somma<br>Numero di chiamate                  |
|Risultato della chiamata in coda di chiamata                  |testo                     |Stato finale chiamata in coda di chiamata -- valori possibili:<br><br>§ agent_joined_conference<br>§ rifiutato<br>§ disconnesso<br>§ errore<br>§ non riuscito<br>§ non valido<br>§ overflow<br>§ timed_out<br>§ transferred_to_agent |
|Azione stato finale coda di chiamata           |testo                     |Azione finale coda di chiamata -- valori possibili:<br><br>§ Disconnetti<br>§ disconnect_with_busy<br>§ failed_to_accept_call<br>§ avanti<br>§ shared_voicemail<br>§ other<br>§ segreteria telefonica |
|Identità coda di chiamata                     |testo                     |Nome dell'account della risorsa allegato alla coda di chiamata<br><br>Se il nome completo dell'account della **risorsa cq_test@microsoft.com** il valore sarà: **cq_test** |
|Data                                    |data/ora                |Data e ora di inizio della chiamata in coda di chiamata (ora) (UTC)   |
|IsAbandoned                             |vero/falso               |True se la chiamata non viene risolta da un agente           |


### <a name="cloud-call-queue-agent-timeline"></a>Sequenza temporale dell'agente coda chiamate cloud

#### <a name="report-description"></a>Descrizione del report

|Sezione report                                          |Descrizione                                                  |
|:-------------------------------------------------------|:------------------------------------------------------------|
|# chiamate da parte dell'agente                                        |Distribuzione della chiamata in base alla coda di chiamata e all'agente                 |
|Durata totale delle chiamate (secondi) per agente e coda di chiamata   |Durata totale (secondi) della chiamata per agente e coda di chiamata     |
|Durata media delle chiamate (secondi) in base al nome dell'agente           |Durata media (secondi) della chiamata da parte dell'agente                  |

#### <a name="report-to-cqd-table-and-field-mapping"></a>Mapping tra tabelle e campi in CQD

|Scheda Report         |Nomi tabella report        |Filtro globale |
|:------------------|:-------------------------|:-------------|
|Sequenza temporale dell'agente     |fAgentTimelineAnalytics   |Nessuno          |
 
|Nome tabella report            |Nome tabella di origine            |Elaborazione in corso       |
|:----------------------------|:----------------------------|:----------------|
|fAgentTimelineAnalytics      |AgentTimelineAnalytics       |Source = AgentTimelineAnalytics, <br>#"Tipo modificato" = Table.TransformColumnTypes(Source,{{"Call Count", Int64.Type}, {"Call Duration (Minute)", Int64.Type}, {"Average Call Duration (Second)", type number}, {"Date", type date}})|

|Sezione report                                |Campi usati                         |Filtri applicati       |
|:---------------------------------------------|:-------------------------------------|:---------------------|
|Nome agente                                    |Nome agente                            |Nessuno                  |
|Nome coda di chiamata                               |Nome coda di chiamata                       |Nessuno                  |
|#Calls per agente                               |Nome agente<br>Conteggio chiamate<br>Data      |Nessuno                  |
|Distribuzione per agente e coda di chiamata          |Nome agente<br>Conteggio chiamate<br>Durata chiamata (minuti)<br>Nome coda di chiamata |Nessuno                      |
|In basso a sinistra                                   |Nome agente<br>Durata media chiamata (secondo)<br>Conteggio chiamate<br>Durata chiamata (minuti)<br>Nome coda di chiamata | Nessuno |
|Durata media delle chiamate (secondi) in base al nome dell'agente |Nome agente<br>Durata media chiamata (secondo)<br>Conteggio chiamate<br>Durata chiamata (minuti)<br>Nome coda di chiamata | Nessuno |

#### <a name="fagenttimelineanalytics-cqd-fields-description"></a>fAgentTimelineAnalytics Descrizione dei campi CQD

|Nome                                    |Tipo di dati                |Descrizione                                         |
|:---------------------------------------|:------------------------|:---------------------------------------------------|
|Nome agente                              |testo                     |UPN utente<br>Se il nome utente **completo user@microsoft.com** il valore sarà: **utente** |
|Durata media chiamata (secondo)          |numero decimale           |Riepiloga: Somma<br>Durata media delle chiamate in coda di chiamata in secondi |
|Conteggio chiamate                              |numero intero             |Riepiloga: Somma<br>Numero di chiamate gestite dall'agente                    |
|Durata chiamata (minuti)                  |numero intero             |Riepiloga: Somma<br>Durata totale delle chiamate in coda di chiamata in minuti  |
|Nome coda di chiamata                         |testo                     |Nome dell'account della risorsa allegato alla coda di chiamata<br><br>Se il nome completo dell'account della **risorsa cq_test@microsoft.com** il valore sarà: **cq_test** |
|Data                                    |data                     |                                                    |


> [!NOTE]
> 1) Questo report mostra i conteggi delle chiamate dal punto di vista degli agenti e quindi il totale del conteggio chiamate in questo report sarà in genere superiore al numero totale di chiamate nel report **Analisi** coda chiamate cloud. Ogni chiamata in coda può essere presentata a uno o più agenti almeno una volta prima di rispondere. Ogni chiamata in coda di chiamata presentata a un agente viene conteggiata in questo report, anche se l'agente non ha risposto. La differenza tra i conteggi delle chiamate tra  questi due report è più pronunciata con l'opzione di instradamento operatore che chiama ogni agente per ogni chiamata. 
> 2) Quando una chiamata arriva per la prima volta alla prima coda di chiamata, se il numero di chiamate già in attesa in quella coda supera il limite di gestione dell'overflow delle chiamate e se l'opzione di reindirizzamento invia chiamate a una seconda coda di chiamata, gli agenti nella seconda coda di chiamata verranno visualizzati nella prima coda di chiamata in questo report.  

## <a name="known-issues"></a>Problemi noti

- La coda di chiamata e gli operatori automatici vengono visualizzati in base all'ID dell'account della risorsa anziché ai nomi delle code di chiamata o degli operatori automatici.  Per visualizzare tutto il traffico per un operatore automatico o una coda di chiamata, è necessario selezionare tutti gli account delle risorse assegnati all'operatore automatico o alla coda di chiamata.

- Nel dashboard sono disponibili solo 28 giorni di cronologia, in quanto i dati relativi alla coda di chiamata o all'operatore automatico sono considerati dati personali ed è soggetto ai criteri di conservazione della privacy dei dati.

- <sup>1</sup> **L'origine della chiamata** in arrivo nei grafici dell'operatore automatico e della coda di chiamata mostra l'origine della coda di chiamata finale invece dell'origine iniziale della coda di chiamata. Ad esempio, se un operatore automatico riceve una chiamata esterna e la  trasferisce a un altro operatore automatico o coda di chiamata, l'origine della chiamata in arrivo verrà segnalata come Interna.

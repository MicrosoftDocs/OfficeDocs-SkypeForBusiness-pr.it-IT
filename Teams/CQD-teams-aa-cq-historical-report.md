---
title: Uso del report Power BI CQD per visualizzare Operatore automatico & report cronologico della coda di chiamata
ms.author: colongma
author: clyvr
manager: roykuntz
ms.reviewer: mikedav, siunies, gageames
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
- seo-marvel-apr2020
description: Informazioni su come usare il report dashboard qualità Power BI chiamata per visualizzare i Operatore automatico e la cronologia della coda di chiamata.
ms.openlocfilehash: 73ffd8e993a3dacd0412123d49e19c704df0cb8c
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731385"
---
# <a name="what-are-the-requirements"></a>Quali sono i requisiti? 
È necessario avere installato Power BI Desktop. È possibile installarlo da [Microsoft Windows Store.](https://aka.ms/pbidesktopstore)

È possibile usare la versione gratuita di Power BI Desktop. La versione minima compatibile è 2.85.681.0 (settembre 2020).

## <a name="permissions-to-access-the-cqd-pipeline"></a>Autorizzazioni per accedere alla pipeline CQD
L'account che si usa per visualizzare il report cronologico AA & CQ Analytics deve avere le autorizzazioni per accedere alla pipeline di dati CQD. Per altre informazioni, vedere il ruolo [di accesso CQD.](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)

## <a name="installation"></a>Installazione 
I passaggi seguenti presuppongono che Power BI Desktop nel computer e che l'account abbia le autorizzazioni necessarie per accedere alla pipeline di dati CQD.

Eseguire questa procedura:
- Scaricare il modello di report cronologico Teams Operatore automatico & coda di chiamata [CQD](./aa-cq-cqd-historical-reports.md) e salvarlo in una directory nel computer.

- Fare doppio clic sul modello e Power BI Desktop dovrebbe essere avviato.

- Verrà richiesto di selezionare l'area della pipeline di dati CQD. Selezionare l'area geografica in cui si trova il tenant.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="Screenshot del pulsante Dashboard qualità chiamata nell'Teams di amministrazione.":::

 - È possibile visualizzare l'area usando il cmdlet Skype for Business Online PS (Get-CsTenant). Output di ServiceInstance. 
 L'area verrà visualizzata dopo l'opzione / like in questo esempio: 
 
   microsoftcommunicationsonline/noam-4a-s7 dove l'area geografica è noam.
   
 - Il report verrà avviato con dati di esempio.
 
 - Per visualizzare i propri dati, fare clic **su** Aggiorna nella scheda Home in Query in Power BI Desktop.

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="Screenshot del pulsante Dashboard qualità chiamata nell'Teams di amministrazione.":::

- Verrà quindi richiesto di eseguire l'accesso. Selezionare **Account organizzazione** e quindi **Accedi.**

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="Screenshot del pulsante Dashboard qualità chiamata nell'Teams di amministrazione.":::

- Selezionare **Connessione** e guardare l'aggiornamento dei dati.

## <a name="data-latency-any-aa--cq-analytics"></a>Latenza dei dati Qualsiasi analisi AA & CQ
I dati saranno disponibili nella pipeline di dati CQD entro 30 minuti.

Sarà necessario aggiornare i dati per visualizzare i nuovi dati di analisi. 

## <a name="customization"></a>Personalizzazione 
È possibile personalizzare alcuni aspetti della visualizzazione dei report, ad esempio l'aggiunta o la rimozione di campi da visualizzare nelle varie visualizzazioni, la modifica del tipo di grafico e così via.

Non è possibile aggiungere altri campi dati diversi da quelli forniti nel report.

### <a name="change-color-schema"></a>Modificare lo schema dei colori 
I passaggi seguenti presuppongono che la procedura di installazione sia già stata completata.

Eseguire questa procedura:
- Selezionare **la scheda Visualizza** sulla barra multifunzione.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="Screenshot del pulsante Dashboard qualità chiamata nell'Teams di amministrazione.":::

- Selezionare lo schema colori nell'elenco a discesa.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="Screenshot del pulsante Dashboard qualità chiamata nell'Teams di amministrazione.":::


## <a name="cqd-fields-description"></a>Descrizione dei campi CQD

|Nome                                    |Tipo di dati                |Descrizione                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Operatore automatico identity                 |stringa                   |Nome dell'account della risorsa allegato a AA<br>Esempio: aa_test@microsoft.com|
|Operatore automatico inizio catena         |datetime                 |Ora di inizio della catena AA                    |
|Operatore automatico di ricerca nella directory  |stringa                   |Ultimo metodo di ricerca rubrica        |
|Operatore automatico trasferimento          |stringa                   |Tipo di destinazione trasferimento chiamata<br>Valori possibili:<br>§ sconosciuto: il tipo di entità non è stato specificato<br>§ utente - entità utente<br>§ orgaa - Entità Operatore automatico organizzativa<br>§ hunt_group - Entità Coda di chiamata<br>§ application - voice application entity<br>§ external_pstn - entità PSTN esterna<br>§ shared_voicemail - entità segreteria telefonica condivisa|
|Operatore automatico risultato della chiamata              |stringa                   |Risultato della chiamata:<br>§ sconosciuto: la chiamata non è riuscita a configurare o trasferire e il servizio non ha ricevuto alcun motivo di errore significativo <br>§ transferred_to_user - Chiamata trasferita a un utente tramite chiamata per nome/interno o opzione di menu configurata <br>§ transferred_to_operator - La chiamata è stata trasferita a un operatore configurato, ad esempio se AA è configurato con un operatore per le ore successive <br>§ failover_to_operator - Fallback all'operatore quando il trasferimento non riesce o il riconoscimento del nome non funziona dopo tre tentativi<br>§ user_terminated - Il chiamante ha terminato la chiamata <br>§ service_declined - Chiamata rifiutata dal servizio, questo problema può verificarsi se il servizio non riesce a recuperare Operatore automatico configurazione <br>§ service_terminated - Il servizio back-end ha terminato la chiamata, se un trasferimento a destinazione non è riuscito e nessun operatore è configurato come fallback <br>§ failed_to_establish_media - Media establishment failed between caller and service <br>§ terminated_no_operator - Riconoscimento del nome non riuscito dopo tre tentativi e non è configurato alcun operatore <br>§ terminated_transfer_failed - Trasferimento alla destinazione non riuscito e nessun operatore è configurato <br>§ terminated_automatic_selection - Se non è configurata alcuna azione durante o dopo l'orario, la chiamata terminerà per impostazione predefinita <br>§ transferred_to_shared_voicemail - Chiamata trasferita alla segreteria telefonica condivisa se configurata come destinazione <br>§ oaa_chain_too_long- Quando una catena di Operatore automatico supera cinque operatori automatici in successione, la chiamata termina per evitare possibili cicli di chiamata <br>§ oaa_session_too_long - La chiamata ha superato la durata massima consentita della sessione ed è scaduto |
|Operatore automatico chiamata Flow                |stringa                   |Incapsula i diversi stati di Operatore automatico Chiamata<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>§ annuncio|
|È Operatore automatico coinvolta              |Boolean                  |Indicato se AA è coinvolto nella chiamata |
|Operatore automatico numero di azioni chiamanti      |int                      |Numero di azioni usate dal chiamante         |
|Operatore automatico Durata catena secondi   |int                      |Durata della chiamata in AA                 |
|Risultato della chiamata in coda di chiamata                  |Stringa                   |Stato finale chiamata in coda di chiamata<br>valori possibili:<br>§ errore<br>§ rifiutato<br>§ overflow<br>§ non riuscito<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference|
|Azione stato finale coda di chiamata           |Stringa                   |Azione finale coda di chiamata<br>valori possibili:<br>§ avanti<br>§ Disconnetti<br>§ segreteria telefonica<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ other|
|Identità coda di chiamata                     |Stringa                   |Nome dell'account della risorsa allegato a CQ<br>Esempio: aa_test@microsoft.com|
|La coda di chiamata è in modalità conferenza           |Boolean                  |Impostare su 1 se la modalità conferenza è abilitata in CQ |
|Tipo di destinazione coda di chiamata                  |Stringa                   |Tipo di destinazione di reindirizzamento delle chiamate previsto     |
|Identità della coda di chiamata trasferita    |Boolean                  |Nome dell'account della risorsa allegato a CQ da cui è stata trasferita la chiamata<br>Esempio: aa_test@microsoft.com|
|Numero di consenso esplicito dell'agente della coda di chiamata           |int                      |Numero di agenti disponibili per questa coda al momento della chiamata |
|Conteggio agenti coda di chiamata                  |int                      |Numero di agenti assegnati a questa coda al momento della chiamata |
|È coinvolta la coda di chiamata                  |Boolean                  |Se la coda di chiamata è coinvolta in questa chiamata uguale a 1 |


### <a name="powerbi-data-model-dimensions"></a>Dimensioni del modello di dati di PowerBI

|Nome                                    |Tipo di dati                |Descrizione                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Nome AA                                   |stringa                   |Operatore automatico (ID account risorsa) |
|AACallFlow                              |stringa                   |Incapsula i diversi stati di Operatore automatico Chiamata<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>annuncio |
|AACallResult                            |stringa                   |Risultato della Operatore automatico chiamata:<br>§ sconosciuto<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined - errore di configurazione AA<br>§ service_terminated – errori AA interni<br>§ failed_to_establish_media<br> terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long          |
|AAChainDuration                         |stringa                   |Durata della Operatore automatico chiamata in secondi  |
|AACount                                 |stringa                   |# di Operatore automatico implicano nella chiamata         |
|AADirectorySearchMethod                 |stringa                   |Metodo di ricerca usato nella chiamata:<br>§ abs_search_dtmf<br>§ abs_search_extension<br>§ abs_search_name|
|AAStartTime                             |stringa                   |Ora della chiamata in UTC                            |
|AATransferAction                        |stringa                   |Destinatario della chiamata:<br>§ sconosciuto: il tipo di entità non è stato specificato<br>§ utente - entità utente<br>§ AA - Entità Operatore automatico organizzativa<br>§ CQ - Entità Coda di chiamata<br>§ application - voice application entity<br>§ external_pstn - entità PSTN esterna<br>§ shared_voicemail - entità segreteria telefonica condivisa      |
|PSTNMinutes                             |int                      |Utilizzo totale dei minuti                          |
|Risultato della chiamata in coda di chiamata                  |stringa                   |Stato finale chiamata in coda di chiamata<br>valori possibili:<br>§ errore<br>§ rifiutato<br>§ overflow<br>§ non riuscito<br> timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference    |
|Identità coda di chiamata                     |stringa                   |Nome dell'account della risorsa allegato a CQ     |
|Tipo di destinazione coda di chiamata                  |stringa                   |Tipo di destinazione previsto per il reindirizzamento delle chiamate:<br>§ Utente<br>§ Endpoint dell'applicazione<br>§ Altro     |
|Risultato della chiamata in coda di chiamata                  |stringa                   |Stato finale chiamata in coda di chiamata<br>valori possibili:<br>§ errore<br>§ rifiutato<br>§ overflow<br>§ non riuscito<br> timed_out<br>§ transferred_to_agent<br>agent_joined_conference           |
|Azione stato finale coda di chiamata           |stringa                   |Azione finale coda di chiamata<br>valori possibili:<br>§ avanti<br>§ Disconnetti<br>§ segreteria telefonica<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ other             |
|Nome agente                              |stringa                   |UPN utente               |


### <a name="measures"></a>Misure

|Nome                                      |Tipo                       |Descrizione                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AACallerActionCount                     |int                        |# di azione selezionata dall'utente in AA durante la chiamata  |
|PSTNMinutes                             |int                      |Utilizzo totale dei minuti                                  |
|TotalCallCount                          |int                      |Numero di chiamate                                          |
|Durata media chiamata( secondi)         |int                      |Durata totale delle chiamate in coda di chiamata in secondi     |


### <a name="power-bi-graph-description-auto-attendant"></a>Power BI descrizione del grafico Operatore automatico

|Nome                                      |Descrizione                            |
|:---------------------------------------|:--------------------------------------|
|Origine chiamata in arrivo                    |Distribuzione della chiamata da parte dell'origine chiamata interna/esterna      |
|Totali dei metodi di ricerca nella directory          |Distribuzione della chiamata per tipo di ricerca                         |
|Azione chiamante                           |Distribuzione della chiamata da parte del destinatario della chiamata                       |
|Risultato della chiamata                             |Distribuzione della chiamata per stato di chiamata finale                    |
|Conteggio azioni chiamante                     |Distribuzione dell'azione chiamata per numero usata durante la chiamata  |


### <a name="call-queue"></a>Coda di chiamata

|Nome                                      |Descrizione                            |
|:---------------------------------------|:--------------------------------------|
|Origine chiamata in arrivo                    |Distribuzione della chiamata da parte dell'origine chiamata interna/esterna         |
|Volume delle chiamate                             |Distribuzione delle chiamate in base alle code di chiamata                            |
|Risultato chiamante                           |Distribuzione del risultato della chiamata per chiamata                            |
|Azione totale chiamata Timeout/Overflow      |Distribuzione della chiamata NON inoltrata(abbandonata) in base al risultato della chiamata   |
|Totali destinazione trasferimento/inoltro          |Distribuzione della chiamata inoltrata dal risultato della chiamata                  |
|Rapporto chiamate abbandonate                   |Rapporto tra il numero di chiamate riuscite e il numero di chiamate abbandonate                    |
|Durata media della sessione (secondi)        |Durata delle chiamate in secondi raggruppate per chiamate abbandonate/riuscite   |



### <a name="agent-timeline"></a>Sequenza temporale dell'agente

|Nome                                                      |Descrizione                            |
|:-------------------------------------------------------|:--------------------------------------|
|# chiamate da parte dell'agente                                        |Distribuzione della chiamata in base alla coda di chiamata e all'agente                 |
|Durata totale delle chiamate (secondi) per agente e coda di chiamata   |Durata totale (secondi) della chiamata per agente e coda di chiamata     |
|Durata media delle chiamate (secondi) in base al nome dell'agente            |Durata media (secondi) della chiamata da parte dell'agente                  |



## <a name="known-issues"></a>Problemi noti
- Attualmente, Coda di chiamata e operatore automatico mostrano l'ID degli account delle risorse invece dei nomi delle code di chiamata/operatori automatici.  Per visualizzare tutto il traffico per un operatore automatico o una coda di chiamata, è necessario selezionare tutti gli account delle risorse assegnati all'operatore automatico o alla coda di chiamata.

- Attualmente, nel dashboard sono disponibili solo 28 giorni di cronologia, in quanto i dati della coda di chiamata/operatore automatico sono considerati informazioni identificabili dall'utente finale ed è soggetto ai criteri di conservazione della privacy dei dati.

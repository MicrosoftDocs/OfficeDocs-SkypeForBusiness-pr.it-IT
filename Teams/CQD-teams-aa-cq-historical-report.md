---
title: Uso del report di Power BI di CallQD per visualizzare Operatore automatico & report cronologico coda di chiamata
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Informazioni su come usare i report di Power BI di Call Quality Dashboard per visualizzare i Operatore automatico della cronologia delle chiamate e della coda di chiamata.
ms.openlocfilehash: 16f8682e8f1bc444e2694a0586ff21cf442288cd
ms.sourcegitcommit: 7966991c398cd80f6bd0bb21e57a6b2a97c09ea9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130427"
---
# <a name="what-are-the-requirements"></a>Quali sono i requisiti? 
È necessario che Power BI Desktop sia installato. Puoi installarlo da [Microsoft Windows Store.](https://aka.ms/pbidesktopstore)

È possibile usare la versione gratuita di Power BI Desktop. La versione minima compatibile è la 2.85.681.0 (settembre 2020).

## <a name="permissions-to-access-the-cqd-pipeline"></a>Autorizzazioni per accedere alla pipeline di CQD
L'account utilizzato per visualizzare il report cronologico di AA & CQ Analytics deve avere le autorizzazioni per accedere alla pipeline di dati di CQD. Per altre informazioni, vedere il ruolo di accesso [di CQD.](https://docs.microsoft.com/microsoftteams/turning-on-and-using-call-quality-dashboard#assign-roles-for-accessing-cqd)

## <a name="installation"></a>Installazione 
I passaggi seguenti presuppongono che Power BI Desktop sia già installato nel computer e che l'account abbia le autorizzazioni necessarie per accedere alla pipeline di dati di CQD.

Eseguire questa procedura:
- Scarica il modello di report cronologico della coda di [Operatore automatico & CQD Teams](https://aka.ms/TAPAACQAnalytics) e salvalo in una directory sul tuo computer.

- Fare doppio clic sul modello per avviare Power BI Desktop.

- Ti verrà richiesto di selezionare l'area della pipeline di dati di CQD. Selezionare l'area geografica in cui si trova il tenant.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="Screenshot del pulsante Dashboard qualità chiamata nell'interfaccia di amministrazione di Teams":::

 - Puoi vedere l'area geografica utilizzando il cmdlet PS di Skype for Business Online (Get-CsTenant). Output di ServiceInstance. 
 L'area geografica verrà visualizzata dopo / come in questo esempio: 
 
   microsoftcommunicationsonline/noam-4a-s7, dove l'area geografica è noam.
   
 - Il report verrà avviato con dati di esempio.
 
 - Per visualizzare i propri dati, fare clic **su** Aggiorna nella scheda Home in Query in Power BI Desktop.

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="Screenshot del pulsante Dashboard qualità chiamata nell'interfaccia di amministrazione di Teams":::

- Verrà quindi richiesto di eseguire l'accesso. Selezionare **Account organizzazione** e quindi **Accedi.**

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="Screenshot del pulsante Dashboard qualità chiamata nell'interfaccia di amministrazione di Teams":::

- Selezionare **Connetti e** osservare l'aggiornamento dei dati.

## <a name="data-latency-any-aa--cq-analytics"></a>Latenza dei dati qualsiasi analisi AA & CQ
I dati saranno disponibili nella pipeline di dati di CQD entro 30 minuti.

Sarà necessario aggiornare i dati per visualizzare i nuovi dati analitici. 

## <a name="customization"></a>Personalizzazione 
È possibile personalizzare determinati aspetti della visualizzazione dei report, ad esempio aggiungere o rimuovere campi da visualizzare nelle varie visualizzazioni, cambiare il tipo di grafico e così via.

Non è possibile aggiungere altri campi dati diversi da quelli disponibili nel report.

### <a name="change-color-schema"></a>Cambiare lo schema dei colori 
I passaggi seguenti presuppongono che la procedura di installazione sia già stata completata.

Eseguire questa procedura:
- Selezionare **la scheda Visualizza** sulla barra multifunzione.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="Screenshot del pulsante Dashboard qualità chiamata nell'interfaccia di amministrazione di Teams":::

- Selezionare lo schema colori nell'elenco a discesa.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="Screenshot del pulsante Dashboard qualità chiamata nell'interfaccia di amministrazione di Teams":::


## <a name="cqd-fields-description"></a>Descrizione dei campi di CQD

|Nome                                    |Tipo di dati                |Descrizione                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Operatore automatico identity                 |stringa                   |Nome dell'account della risorsa collegato ad AA<br>Esempio: aa_test@microsoft.com|
|Operatore automatico'ora di inizio della catena di distribuzione         |datetime                 |Ora di inizio della catena AA                    |
|Operatore automatico directory Search Method  |stringa                   |Metodo di ricerca Ultima rubrica        |
|Operatore automatico trasferimento azioni          |stringa                   |Tipo di destinazione trasferimento chiamata<br>Valori possibili:<br>§ sconosciuto. Il tipo di entità non è stato specificato<br>§ utente - entità utente<br>§ orgaa - Entità Operatore automatico organizzazione<br>§ hunt_group - Entità coda di chiamata<br>§ application - voice application entity<br>§ external_pstn - entità PSTN esterna<br>§ shared_voicemail - entità segreteria telefonica condivisa|
|Operatore automatico risultato della chiamata              |stringa                   |Risultato della chiamata:<br>§ sconosciuto<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined<br>§ service_terminated<br>§ failed_to_establish_media<br>§ terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long|
|Operatore automatico flusso delle chiamate                |stringa                   |Incapsula i diversi stati della Operatore automatico Chiamata<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>annuncio §|
|È Operatore automatico coinvolto              |Boolean                  |Indicato se AA è coinvolto nella chiamata |
|Operatore automatico'azione chiamante      |int                      |Numero di azioni usate dal chiamante         |
|Operatore automatico Durata catena secondi   |int                      |Durata della chiamata in AA                 |
|Risultato chiamata in coda di chiamata                  |Stringa                   |Stato finale chiamata in coda di chiamata<br>valori possibili:<br>Errore §<br>§ rifiutata<br>§ overflown<br>§ non riuscito<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference|
|Azione di stato finale coda di chiamata           |Stringa                   |Azione finale coda di chiamata<br>valori possibili:<br>§ avanti<br>§ Disconnetti<br>§ segreteria telefonica<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ altro|
|Identità coda di chiamata                     |Stringa                   |Nome dell'account della risorsa allegato a Domande e risposte<br>Esempio: aa_test@microsoft.com|
|La coda di chiamata è la modalità conferenza           |Boolean                  |Impostato su 1 se la modalità conferenza è abilitata su CQ |
|Tipo di destinazione coda di chiamata                  |Stringa                   |Tipo di destinazione del reindirizzamento delle chiamate previsto     |
|Trasferimento dall'identità della coda di chiamata    |Boolean                  |Nome dell'account della risorsa collegato a CallQ da cui è stata trasferita la chiamata<br>Esempio: aa_test@microsoft.com|
|Numero di consenso esplicito per l'agente della coda di chiamata           |int                      |Numero di agenti disponibili in questa coda al momento della chiamata |
|Call Queue Agent Count                  |int                      |Numero di agenti assegnati a questa coda al momento della chiamata |
|È coinvolta una coda di chiamata                  |Boolean                  |Se la coda di chiamata è coinvolta in questa chiamata uguale a 1 |


### <a name="powerbi-data-model-dimensions"></a>Dimensioni del modello di dati di PowerBI

|Nome                                    |Tipo di dati                |Descrizione                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Nome AA                                   |stringa                   |Operatore automatico risorsa (ID account risorsa) |
|AACallFlow                              |stringa                   |Incapsula i diversi stati della Operatore automatico Chiamata<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>annuncio |
|AACallResult                            |stringa                   |Risultato della Operatore automatico chiamata:<br>§ sconosciuto<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined - Errore di configurazione AA<br>§ service_terminated - Errori AA interni<br>§ failed_to_establish_media<br> terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long          |
|AAChainDuration                         |stringa                   |Durata della Operatore automatico chiamata in secondi  |
|AACount                                 |stringa                   |# di Operatore automatico implicano nella chiamata         |
|AADirectorySearchMethod                 |stringa                   |Metodo di ricerca utilizzato nella chiamata:<br>§ abs_search_dtmf<br>§ abs_search_extension<br>§ abs_search_name|
|AAStartTime                             |stringa                   |Ora della chiamata in UTC                            |
|AATransferAction                        |stringa                   |Destinatario della chiamata:<br>§ sconosciuto. Il tipo di entità non è stato specificato<br>§ utente - entità utente<br>§ AA - Entità Operatore automatico organizzazione<br>§ CQ - Entità coda di chiamata<br>§ application - voice application entity<br>§ external_pstn - entità PSTN esterna<br>§ shared_voicemail - entità segreteria telefonica condivisa      |
|PSTNMinutes                             |int                      |Utilizzo totale minuti                          |
|Risultato chiamata in coda di chiamata                  |stringa                   |Stato finale chiamata in coda di chiamata<br>valori possibili:<br>Errore §<br>§ rifiutata<br>§ overflown<br>§ non riuscito<br> timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference    |
|Identità coda di chiamata                     |stringa                   |Nome dell'account della risorsa allegato a Domande e risposte     |
|Tipo di destinazione coda di chiamata                  |stringa                   |Tipo di destinazione previsto per il reindirizzamento delle chiamate:<br>§ Utente<br>§ Endpoint applicazione<br>§ Altro     |
|Risultato chiamata in coda di chiamata                  |stringa                   |Stato finale chiamata in coda di chiamata<br>valori possibili:<br>Errore §<br>§ rifiutata<br>§ overflown<br>§ non riuscito<br> timed_out<br>§ transferred_to_agent<br>agent_joined_conference           |
|Azione di stato finale coda di chiamata           |stringa                   |Azione finale coda di chiamata<br>valori possibili:<br>§ avanti<br>§ Disconnetti<br>§ segreteria telefonica<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ altro             |
|Nome agente                              |stringa                   |UPN utente               |


### <a name="measures"></a>Misure

|Nome                                      |Tipo                       |Descrizione                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AACallerActionCount                     |int                        |# of action selected by user in AA during the call  |
|PSTNMinutes                             |int                      |Utilizzo totale minuti                                  |
|TotalCallCount                          |int                      |N. di chiamate                                          |
|Durata media chiamata( Secondi)         |int                      |Durata totale delle chiamate in coda di chiamata in secondi     |


### <a name="power-bi-graph-description-auto-attendant"></a>Descrizione di Power BI Graph Operatore automatico

|Nome                                      |Descrizione                            |
|:---------------------------------------|:--------------------------------------|
|Origine chiamata in arrivo                    |Distribuzione della chiamata da parte di un'origine di chiamata interna/esterna      |
|Totali dei metodi di ricerca nella directory          |Distribuzione della chiamata per tipo di ricerca                         |
|Azione chiamante                           |Distribuzione della chiamata tramite ricevitore di chiamata                       |
|Risultato della chiamata                             |Distribuzione della chiamata per stato di chiamata finale                    |
|Numero di azioni del chiamante                     |Distribuzione dell'azione chiamata per numero usata durante la chiamata  |


### <a name="call-queue"></a>Coda di chiamata

|Nome                                      |Descrizione                            |
|:---------------------------------------|:--------------------------------------|
|Origine chiamata in arrivo                    |Distribuzione della chiamata da parte di un'origine di chiamata interna/esterna         |
|Volume della chiamata                             |Distribuzione delle chiamate per code di chiamata                            |
|Risultato del chiamante                           |Distribuzione del risultato di chiamata per chiamata                            |
|Azione totale chiamata timeout/overflow      |Distribuzione di NOT forwarded(abandoned) call by call result   |
|Totali destinazione di trasferimento/inoltro          |Distribuzione della chiamata inoltrata dal risultato della chiamata                  |
|Rapporto chiamate abbandonate                   |Rapporto tra esito positivo e numero di chiamate abbandonato                    |
|Durata media della sessione (secondi)        |Durata della chiamata in secondi raggruppata da chiamate abbandonate/effettuate   |



### <a name="agent-timeline"></a>Sequenza temporale agente

|Nome                                                      |Descrizione                            |
|:-------------------------------------------------------|:--------------------------------------|
|# chiamate dall'agente                                        |Distribuzione della chiamata per coda di chiamata e agente                 |
|Durata totale della chiamata (secondi) per agente e coda di chiamata   |Durata totale (secondi) della chiamata da parte dell'agente e della coda di chiamata     |
|Durata media chiamata (secondi) per nome agente            |Durata media (secondi) della chiamata da parte dell'agente                  |



## <a name="known-issues"></a>Problemi noti
- Attualmente, coda di chiamata e operatore automatico mostrano l'ID dell'account delle risorse invece dei nomi delle code di chiamata o dell'operatore automatico.  Per mostrare tutto il traffico per un operatore automatico o una coda di chiamata, devi selezionare tutti gli account delle risorse assegnati all'operatore automatico o alla coda di chiamata.

- Attualmente, solo 28 giorni di cronologia sono disponibili nel dashboard perché i dati della coda di chiamata o dell'operatore automatico sono considerati informazioni identificabili dall'utente finale ed è soggetto ai criteri di conservazione della privacy dei dati.

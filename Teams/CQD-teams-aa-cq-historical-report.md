---
title: Uso del report di Power BI di Call Quality dashboard per visualizzare l'operatore automatico & report cronologico delle code di chiamata
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
description: Informazioni su come usare il report di Power BI di Call Quality dashboard per visualizzare i dati cronologici dell'operatore automatico e della coda di chiamata.
ms.openlocfilehash: 16f8682e8f1bc444e2694a0586ff21cf442288cd
ms.sourcegitcommit: 7966991c398cd80f6bd0bb21e57a6b2a97c09ea9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130427"
---
# <a name="what-are-the-requirements"></a>Quali sono i requisiti? 
È necessario avere installato desktop di Power BI. Puoi installarlo da [Microsoft Windows Store](https://aka.ms/pbidesktopstore).

È possibile usare la versione gratuita di Power BI desktop. La versione minima compatibile è 2.85.681.0 (2020 settembre).

## <a name="permissions-to-access-the-cqd-pipeline"></a>Autorizzazioni per accedere alla pipeline Call Quality dashboard
L'account usato per visualizzare il report cronologico di analisi & CQ per gli AA deve avere le autorizzazioni per accedere alla pipeline di dati di Call Quality dashboard. Per altre informazioni, fare riferimento al [ruolo di accesso di Call Quality dashboard](https://docs.microsoft.com/microsoftteams/turning-on-and-using-call-quality-dashboard#assign-roles-for-accessing-cqd) .

## <a name="installation"></a>Installazione 
I passaggi seguenti presuppongono che nel computer sia già installato Power BI desktop e che l'account disponga delle autorizzazioni necessarie per accedere alla pipeline di dati Call Quality dashboard.

Eseguire questa procedura:
- Scaricare l' [operatore automatico di Call Quality dashboard teams & modello di report cronologico della coda di chiamata](https://aka.ms/TAPAACQAnalytics) e salvarlo in una directory nel computer.

- Fare doppio clic sul modello e avviare il desktop di Power BI.

- Verrà richiesto di selezionare l'area della pipeline di dati Call Quality dashboard. Selezionare l'area geografica in cui si trova il tenant.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="Screenshot del pulsante dashboard qualità chiamata nell'interfaccia di amministrazione di Teams":::

 - Puoi visualizzare l'area geografica usando il cmdlet Skype for business online PS (Get-CsTenant). Output ServiceInstance. 
 L'area geografica verrà visualizzata dopo il/come in questo esempio: 
 
   MicrosoftCommunicationsOnline/Noam-4a-S7 dove la regione è Noam.
   
 - Il report verrà avviato con i dati di esempio.
 
 - Per visualizzare i propri dati, fare clic su **Aggiorna** nella scheda Home in query in Power bi desktop.

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="Screenshot del pulsante dashboard qualità chiamata nell'interfaccia di amministrazione di Teams":::

- Verrà richiesto di eseguire l'accesso. Selezionare **account organizzazione** e quindi fare clic **su Accedi**.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="Screenshot del pulsante dashboard qualità chiamata nell'interfaccia di amministrazione di Teams":::

- Selezionare **Connetti** e guardare l'aggiornamento dati.

## <a name="data-latency-any-aa--cq-analytics"></a>Latenza dei dati qualsiasi & di analisi CQ di AA
I dati saranno disponibili nella pipeline di dati Call Quality dashboard entro 30 minuti.

Sarà necessario aggiornare i dati per visualizzare i nuovi dati di analisi. 

## <a name="customization"></a>Personalizzazione 
È possibile personalizzare alcuni aspetti della visualizzazione dei report, ad esempio aggiungere o rimuovere campi da visualizzare nelle varie visualizzazioni, modificando il tipo di grafico e così via.

Non è possibile aggiungere campi dati aggiuntivi diversi da quelli forniti nel report.

### <a name="change-color-schema"></a>Cambiare lo schema di colore 
I passaggi seguenti presuppongono che siano già state completate le procedure di installazione.

Eseguire questa procedura:
- Selezionare la **scheda Visualizza** sulla barra multifunzione.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="Screenshot del pulsante dashboard qualità chiamata nell'interfaccia di amministrazione di Teams":::

- Selezionare lo schema colore nell'elenco a discesa.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="Screenshot del pulsante dashboard qualità chiamata nell'interfaccia di amministrazione di Teams":::


## <a name="cqd-fields-description"></a>Descrizione campi Call Quality dashboard

|Nome                                    |Tipo di dati                |Descrizione                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Identità operatore automatico                 |stringa                   |Nome dell'account delle risorse allegato a AA<br>Esempio: aa_test@microsoft.com|
|Ora di inizio della catena operatore automatico         |DateTime                 |Ora di inizio della catena AA                    |
|Metodo di ricerca della directory operatore automatico  |stringa                   |Metodo di ricerca dell'ultima rubrica        |
|Azione di trasferimento di operatore automatico          |stringa                   |Tipo di destinazione trasferimento chiamata<br>Valori possibili:<br>§ sconosciuto-il tipo di entità non è stato specificato<br>§ User-User Entity<br>§ orgaa-entità operatore automatico organizzazione<br>§ hunt_group-entità della coda di chiamata<br>§ applicazione-entità applicazione vocale<br>§ external_pstn-entità PSTN esterna<br>§ shared_voicemail-entità della segreteria telefonica condivisa|
|Risultato chiamata operatore automatico              |stringa                   |Risultato chiamata:<br>§ sconosciuto<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined<br>§ service_terminated<br>§ failed_to_establish_media<br>§ terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long|
|Flusso delle chiamate di operatore automatico                |stringa                   |Incapsula i diversi Stati della chiamata all'operatore automatico<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>annuncio §|
|Operatore automatico coinvolto              |Boolean                  |Indicato se AA implicato nella chiamata |
|Conteggio azioni del chiamante dell'operatore automatico      |int                      |Conteggio dell'azione usata dal chiamante         |
|Durata della catena operatore automatico secondi   |int                      |Durata della chiamata in AA                 |
|Risultato della chiamata alla coda di chiamata                  |Stringa                   |Stato finale chiamata coda di chiamata<br>valori possibili:<br>errore §<br>§ rifiutato<br>§ overflow<br>§ non riuscito<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference|
|Azione stato finale coda di chiamata           |Stringa                   |Azione finale della coda di chiamata<br>valori possibili:<br>§ inoltra<br>§ Disconnetti<br>§ segreteria telefonica<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ altro|
|Identità della coda di chiamata                     |Stringa                   |Nome dell'account delle risorse allegato a CQ<br>Esempio: aa_test@microsoft.com|
|La coda di chiamata è la modalità conferenza           |Boolean                  |Impostato su 1 se la modalità conferenza è abilitata in CQ |
|Tipo di destinazione della coda di chiamata                  |Stringa                   |Tipo di destinazione del reindirizzamento delle chiamate previsto     |
|Trasferimento dall'identità della coda di chiamata    |Boolean                  |Nome dell'account delle risorse allegato a CQ da cui è stata trasferita la chiamata<br>Esempio: aa_test@microsoft.com|
|Opzione chiama agente di Accodamento in conteggio           |int                      |Numero di agenti disponibili per la coda al momento della chiamata |
|Conteggio dell'agente della coda di chiamata                  |int                      |Numero di agenti assegnati alla coda al momento della chiamata |
|La coda di chiamata è coinvolta                  |Boolean                  |Se la coda di chiamata è coinvolta in una chiamata uguale a 1 |


### <a name="powerbi-data-model-dimensions"></a>Dimensioni del modello di dati PowerBI

|Nome                                    |Tipo di dati                |Descrizione                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Nome AA                                   |stringa                   |ID operatore automatico (ID account risorse) |
|AACallFlow                              |stringa                   |Incapsula i diversi Stati della chiamata all'operatore automatico<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>annuncio |
|AACallResult                            |stringa                   |Risultato della chiamata all'operatore automatico:<br>§ sconosciuto<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined – errore della configurazione AA<br>§ service_terminated-errori interni AA<br>§ failed_to_establish_media<br> terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long          |
|AAChainDuration                         |stringa                   |Durata della chiamata all'operatore automatico in secondi  |
|AACount                                 |stringa                   |# di operatore automatico coinvolgere nella chiamata         |
|AADirectorySearchMethod                 |stringa                   |Metodo di ricerca usato nella chiamata:<br>§ abs_search_dtmf<br>§ abs_search_extension<br>§ abs_search_name|
|AAStartTime                             |stringa                   |Tempo di chiamata in formato UTC                            |
|AATransferAction                        |stringa                   |Destinatario della chiamata:<br>§ sconosciuto-il tipo di entità non è stato specificato<br>§ User-User Entity<br>§ AA-entità operatore automatico dell'organizzazione<br>§ CQ-entità della coda di chiamata<br>§ applicazione-entità applicazione vocale<br>§ external_pstn-entità PSTN esterna<br>§ shared_voicemail-entità della segreteria telefonica condivisa      |
|PSTNMinutes                             |int                      |Utilizzo totale minuti                          |
|Risultato della chiamata alla coda di chiamata                  |stringa                   |Stato finale chiamata coda di chiamata<br>valori possibili:<br>errore §<br>§ rifiutato<br>§ overflow<br>§ non riuscito<br> timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference    |
|Identità della coda di chiamata                     |stringa                   |Nome dell'account delle risorse allegato a CQ     |
|Tipo di destinazione della coda di chiamata                  |stringa                   |Tipo di destinazione di reindirizzamento delle chiamate previsto:<br>§ Utente<br>§ Endpoint applicazione<br>§ Altro     |
|Risultato della chiamata alla coda di chiamata                  |stringa                   |Stato finale chiamata coda di chiamata<br>valori possibili:<br>errore §<br>§ rifiutato<br>§ overflow<br>§ non riuscito<br> timed_out<br>§ transferred_to_agent<br>agent_joined_conference           |
|Azione stato finale coda di chiamata           |stringa                   |Azione finale della coda di chiamata<br>valori possibili:<br>§ inoltra<br>§ Disconnetti<br>§ segreteria telefonica<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ altro             |
|Nome agente                              |stringa                   |UPN dell'utente               |


### <a name="measures"></a>Misure

|Nome                                      |Tipo                       |Descrizione                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AACallerActionCount                     |int                        |# of Action selezionato dall'utente in AA durante la chiamata  |
|PSTNMinutes                             |int                      |Utilizzo totale minuti                                  |
|TotalCallCount                          |int                      |# delle chiamate                                          |
|Durata media delle chiamate (secondi)         |int                      |Durata totale delle chiamate alla coda di chiamata in pochi secondi     |


### <a name="power-bi-graph-description-auto-attendant"></a>Power BI Graph Descrizione operatore automatico

|Nome                                      |Descrizione                            |
|:---------------------------------------|:--------------------------------------|
|Origine chiamata in arrivo                    |Distribuzione della chiamata da origine chiamata interna/esterna      |
|Totali del metodo di ricerca della directory          |Distribuzione della chiamata tramite il tipo di ricerca                         |
|Azione chiamante                           |Distribuzione della chiamata tramite destinatario chiamata                       |
|Risultato chiamata                             |Distribuzione della chiamata per stato di chiamata finale                    |
|Conteggio azioni chiamante                     |Distribuzione dell'azione chiamata per numero usata durante la chiamata  |


### <a name="call-queue"></a>Coda di chiamata

|Nome                                      |Descrizione                            |
|:---------------------------------------|:--------------------------------------|
|Origine chiamata in arrivo                    |Distribuzione della chiamata da origine chiamata interna/esterna         |
|Volume chiamata                             |Distribuzione della chiamata tramite le code delle chiamate                            |
|Risultato del chiamante                           |Distribuzione della chiamata tramite il risultato della chiamata                            |
|Azione totale chiamata timeout/overflow      |Distribuzione della chiamata non inoltrata (abbandonata) tramite il risultato della chiamata   |
|Trasferire/inoltrare totali di destinazione          |Distribuzione della chiamata inoltrata tramite il risultato della chiamata                  |
|Rapporto chiamate abbandonate                   |Rapporto tra il conteggio delle chiamate abbandonato e il successo                    |
|Lunghezza media della sessione (secondi)        |Lunghezza chiamata in secondi raggruppati per chiamate abbandonate/di successo   |



### <a name="agent-timeline"></a>Sequenza temporale dell'agente

|Nome                                                      |Descrizione                            |
|:-------------------------------------------------------|:--------------------------------------|
|# chiamate per agente                                        |Distribuzione della chiamata tramite coda di chiamata e agente                 |
|Durata totale delle chiamate (secondi) per agente e coda di chiamata   |Durata totale (secondi) di chiamata per agente e coda di chiamata     |
|Durata media chiamata (secondi) per nome agente            |Durata media (secondi) della chiamata per agente                  |



## <a name="known-issues"></a>Problemi noti
- Attualmente, le chiamate coda e operatore automatico mostrano l'ID degli account delle risorse anziché i nomi delle code di chiamata o degli operatori automatici.  Per visualizzare tutto il traffico per un operatore automatico o una coda di chiamata, è necessario selezionare tutti gli account delle risorse assegnati all'operatore automatico o alla coda di chiamata.

- Attualmente, solo 28 giorni di storia sono disponibili nel dashboard, poiché i dati dell'operatore automatico per la coda di chiamata vengono considerati informazioni di identificazione dell'utente finale ed è soggetto ai criteri di conservazione della privacy dei dati.

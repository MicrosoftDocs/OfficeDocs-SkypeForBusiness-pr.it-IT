---
title: Usare l'analisi delle chiamate per risolvere i problemi relativi alla scarsa qualità delle chiamate
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: Usare i dettagli di analisi delle chiamate per utente su dispositivi, reti e connettività per risolvere i problemi degli utenti Microsoft Teams chiamate e riunioni.
ms.openlocfilehash: 4732cf68624b824a452455fc779b22ae7eb32d56
ms.sourcegitcommit: ca2230a981a1e3c03437d1ecb8727d66ad6967f9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760561"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>Usare l'analisi delle chiamate per risolvere i problemi relativi alla scarsa qualità delle chiamate

Questo articolo spiega come usare l'analisi delle chiamate per risolvere i problemi di qualità scarsa Microsoft Teams chiamata o riunione per singoli utenti se si è un amministratore di Teams o un tecnico o uno specialista del supporto per le comunicazioni Teams.

## <a name="call-analytics-permissions"></a>Autorizzazioni di Call Analytics

Questo articolo presuppone che l'analisi delle chiamate sia già stata impostata. In caso contrario, vedere Configurare [l'analisi](set-up-call-analytics.md)delle chiamate per Teams .

## <a name="introduction-to-call-analytics"></a>Introduzione all'analisi delle chiamate

L'analisi delle chiamate mostra informazioni dettagliate su Teams chiamate e riunioni per ogni utente del Office 365 account. Include informazioni su dispositivi, reti, connettività e qualità delle chiamate (uno di questi fattori può essere un fattore di scarsa qualità per le chiamate o le riunioni). Se si caricano informazioni sull'edificio, il sito e il tenant, queste informazioni verranno visualizzate anche per ogni chiamata e riunione. Usare l'analisi delle chiamate per capire perché un utente ha avuto una scarsa esperienza di chiamata o riunione.

L'analisi delle chiamate mostra ogni fase di una chiamata o di una riunione, ad esempio da un partecipante a un secondo partecipante. Analizzando questi dettagli, un amministratore Teams può isolare le aree di problemi e identificare la causa radice per la scarsa qualità.

Come amministratore Teams, si ottiene l'accesso completo a tutti i dati di analisi delle chiamate per ogni utente. Inoltre, è possibile assegnare Azure Active Directory ruoli al personale di supporto. Per altre informazioni su questi ruoli, vedere [Concedere l'autorizzazione al supporto e al personale dell'helpdesk.](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff) Da non perdere [Cosa fa ogni Teams di supporto tecnico?](#what-does-each-teams-support-role-do) di seguito.

## <a name="where-to-find-per-user-call-analytics"></a>Dove trovare l'analisi delle chiamate per utente

Per visualizzare tutte le informazioni sulle chiamate e i dati per un utente, passare [all'interfaccia Teams di amministrazione.](https://admin.teams.microsoft.com) In **Utenti** selezionare un utente e quindi aprire la scheda Riunioni **& chiamate** nella pagina del profilo dell'utente. Qui troverai tutte le chiamate e le riunioni per quell'utente per gli ultimi 30 giorni.

![Screenshot di tutti i dati utente di analisi](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

Per ottenere altre informazioni su una determinata sessione, inclusi elementi multimediali dettagliati e statistiche di rete, fare clic su una sessione per visualizzare i dettagli.

![Screenshot dei dati della sessione utente di analisi delle chiamate](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)

## <a name="what-does-each-teams-support-role-do"></a>Cosa fa ogni Teams supporto tecnico?

Lo **Teams di supporto per le comunicazioni** (supporto di livello 1) gestisce i problemi di qualità delle chiamate di base. Non esaminano i problemi relativi alle riunioni. Al contrario, raccolgono informazioni correlate e quindi vengono inoltrate a un tecnico del supporto per le comunicazioni.

Il **Teams di** supporto per le comunicazioni di livello 2 visualizza informazioni nei log delle chiamate dettagliati nascosti allo specialista Teams supporto per le comunicazioni. La tabella seguente elenca le informazioni disponibili per ogni ruolo di supporto Teams comunicazione.

La tabella seguente indica quali informazioni per utente sono disponibili per ogni ruolo di supporto per le comunicazioni.

|Attività|Informazioni|Quali sono le comunicazioni<br>lo *specialista del supporto* vede|Quali sono le comunicazioni<br>il *tecnico del supporto* vede|
|---|---|---|---|
|**Chiamate**|Nome chiamante|Solo il nome dell'utente per cui l'agente ha cercato.|Nome utente.|
||Nome destinatario|Viene visualizzato come utente interno o utente esterno.|Nome del destinatario.|
||Numero di telefono del chiamante|L'intero numero di telefono, ad eccezione delle ultime tre cifre, viene offuscato con simboli asterisco. Ad esempio, 15552823 \* \* \* .|L'intero numero di telefono, ad eccezione delle ultime tre cifre, viene offuscato con simboli asterisco. Ad esempio, 15552823 \* \* \* .|
||Numero di telefono del destinatario|L'intero numero di telefono, ad eccezione delle ultime tre cifre, viene offuscato con simboli asterisco. Ad esempio, 15552823 \* \* \* .|L'intero numero di telefono, ad eccezione delle ultime tre cifre, viene offuscato con simboli asterisco. Ad esempio, 15552823 \* \* \* .|
||**Dettagli chiamata** \> **Scheda** Avanzate|Informazioni non visualizzate.|Tutti i dettagli visualizzati, ad esempio i nomi dei dispositivi, l'indirizzo IP, la mappatura della subnet e altro ancora.|
||**Dettagli chiamata** \> **Avanzate** \> **Scheda** Debug|Informazioni non visualizzate.|Tutti i dettagli visualizzati, ad esempio suffisso DNS e SSID.|
|**Riunioni**|Nomi dei partecipanti|Solo il nome dell'utente per cui l'agente ha cercato. Altri partecipanti identificati come Utente interno o Utente esterno.|Tutti i nomi visualizzati.|
||Numero di partecipanti|Numero di partecipanti.|Numero di partecipanti.|
||Dettagli della sessione|Dettagli della sessione visualizzati con eccezioni. Viene visualizzato solo il nome dell'utente per cui l'agente ha cercato. Altri partecipanti identificati come Utente interno o Utente esterno. Ultime tre cifre del numero di telefono offuscate con simboli asterisco.|Dettagli della sessione visualizzati. Nomi utente e dettagli della sessione visualizzati. Ultime tre cifre del numero di telefono offuscate con simboli asterisco.|
||||

## <a name="troubleshoot-user-call-quality-problems"></a>Risolvere i problemi di qualità delle chiamate degli utenti

1. Aprire l'Teams di amministrazione ( ) e accedere con il supporto Teams comunicazioni o Teams <https://admin.teams.microsoft.com> credenziali di amministratore.

2. Nel **dashboard,** in **Ricerca utente,** iniziare a digitare il nome o l'indirizzo  SIP dell'utente di cui si vuole risolvere i problemi di chiamata oppure selezionare Visualizza utenti per visualizzare un elenco di utenti.

3. Selezionare l'utente nell'elenco.

4. Selezionare **Cronologia chiamate** e quindi selezionare la chiamata o la riunione da risolvere.

5. Selezionare la **scheda Avanzate** e quindi cercare gli elementi gialli e rossi che indicano problemi di qualità della chiamata o di connessione di qualità scarsa.

   Nei dettagli della sessione per ogni chiamata o riunione, i problemi secondari vengono visualizzati in giallo. Se qualcosa è giallo, non rientra nell'intervallo normale e potrebbe contribuire al problema, ma è improbabile che sia la causa principale del problema. Se qualcosa è rosso, si tratta di un problema significativo ed è probabile che sia la causa principale della scarsa qualità delle chiamate per questa sessione.

In rari casi, i dati sulla qualità dell'esperienza non vengono ricevuti per le sessioni audio. Spesso questo problema è causato da una chiamata interrotta o dalla chiusura della connessione con il client. In questo caso, la valutazione della sessione non è **disponibile.**

Per le sessioni audio con dati QoE (Quality of Experience), la tabella seguente descrive i problemi principali che qualificano una sessione come **scarsa.**

|Problema|Area|Descrizione|
|---|---|---|
|Configurazione della chiamata|Sessione|Il codice di errore Ms-diag 20-29 indica che la configurazione della chiamata non è riuscita. L'utente non è riuscito a partecipare alla chiamata o alla riunione.|
|Chiamata di qualità scarsa classificata per la rete audio|Sessione|Si sono verificati problemi di qualità della rete, ad esempio perdita di pacchetti, instabilità, degradazione di NMOS, RTT o rapporto nascosto.|
|Dispositivo non funzionante|Dispositivo|Un dispositivo non funziona correttamente. I rapporti di dispositivo non funzionanti sono: <p> DeviceRenderNotFunctioningEventRatio >= 0,005 <br>  DeviceCaptureNotFunctioningEventRatio >= 0,005|
||||

## <a name="related-topics"></a>Argomenti correlati

[Configurare l'analisi delle chiamate per utente](set-up-call-analytics.md)

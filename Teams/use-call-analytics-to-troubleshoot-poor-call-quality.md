---
title: Uso di Call Analytics per risolvere problemi di bassa qualità delle chiamate
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: Usare i dettagli di Call Analytics per utente su dispositivi, reti e connettività per risolvere i problemi degli utenti Microsoft Teams chiamate e riunioni.
ms.openlocfilehash: 9f61796d83977c9d0782957fe3bafe787f60403b
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731935"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>Uso di Call Analytics per risolvere problemi di bassa qualità delle chiamate

Questo articolo spiega come usare Call Analytics per risolvere i problemi di qualità scarsa delle chiamate Microsoft Teams o delle riunioni per i singoli utenti se si ha il ruolo di amministratore di Teams, specialista del supporto per le comunicazioni Teams o tecnico del supporto per le comunicazioni Teams.

## <a name="call-analytics-permissions"></a>Autorizzazioni di Call Analytics

Questo articolo presuppone che sia già stata impostata l'analisi delle chiamate. In caso contrario, vedere Configurare [l'analisi](set-up-call-analytics.md)delle chiamate per Teams .

## <a name="introduction-to-call-analytics"></a>Introduzione all'analisi delle chiamate

Call Analytics mostra informazioni dettagliate sulle Teams e le riunioni per ogni utente nel tuo account Office 365 personale. Include informazioni su dispositivi, reti, connettività e qualità delle chiamate (uno di questi fattori può essere un fattore di scarsa qualità per le chiamate o le riunioni). Se si caricano informazioni sull'edificio, il sito e il tenant, queste informazioni verranno visualizzate anche per ogni chiamata e riunione. Usare Call Analytics per capire perché un utente ha avuto una scarsa esperienza di chiamata o riunione.

Call Analytics mostra ogni fase di una chiamata o di una riunione, ad esempio da un partecipante a un secondo partecipante. Analizzando questi dettagli, un amministratore Teams può isolare le aree di problemi e identificare la causa radice della scarsa qualità.

Come amministratore Teams, si ottiene l'accesso completo a tutti i dati di Call Analytics per ogni utente. È anche possibile assegnare ruoli Azure Active Directory al personale di supporto. Per altre informazioni su questi ruoli, vedere [Concedere l'autorizzazione al supporto e al personale dell'helpdesk.](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff) Da non perdere Cosa fa [ogni Teams di supporto tecnico?](#what-does-each-teams-support-role-do) di seguito.

## <a name="where-to-find-per-user-call-analytics"></a>Dove trovare Call Analytics per utente

Per visualizzare tutte le informazioni sulle chiamate e i dati per un utente, passare [all'interfaccia Teams di amministrazione.](https://admin.teams.microsoft.com) In **Utenti** selezionare un utente e quindi aprire la scheda Riunioni **& chiamate** nella pagina del profilo dell'utente. Qui troverai tutte le chiamate e le riunioni per quell'utente negli ultimi 30 giorni.

![Screenshot di tutti i dati utente di analisi.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

Per ottenere altre informazioni su una determinata sessione, inclusi elementi multimediali dettagliati e statistiche di rete, fare clic su una sessione per visualizzare i dettagli.

![Screenshot dei dati della sessione utente di analisi delle chiamate.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)

## <a name="what-does-each-teams-support-role-do"></a>Cosa fa ogni Teams supporto tecnico?

Lo **Teams di supporto per le comunicazioni** di livello 1 gestisce i problemi di qualità delle chiamate di base. Non esaminano i problemi relativi alle riunioni. Al contrario, raccolgono informazioni correlate e quindi vengono inoltrate a un Teams tecnico del supporto per le comunicazioni.

Il **Teams** di supporto per le comunicazioni di livello 2 visualizza informazioni nei log delle chiamate dettagliati nascosti allo specialista Teams supporto per le comunicazioni. La tabella seguente elenca le informazioni disponibili per ogni ruolo di supporto Teams comunicazione.

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

> [!NOTE]
> Le informazioni contenute nella scheda Debug contengono dati di telemetria e di diagnostica del servizio destinati a supportare i tecnici del supporto Tecnico Microsoft. Senza il contesto dei dati aggiuntivi disponibili per i tecnici di supporto, potrebbero sembrare ridondanti, imprecisi o confusi. Anche se lo rendiamo disponibile per gli utenti esperti che cercano un altro livello di dettaglio nella risoluzione dei problemi relativi alle chiamate, non è consigliabile esprimere giudizi sulla base di questi dati senza il supporto Microsoft.

## <a name="troubleshoot-user-call-quality-problems"></a>Risolvere i problemi di qualità delle chiamate degli utenti

1. Aprire l'Teams di amministrazione ( ) e accedere con il supporto Teams comunicazioni o Teams <https://admin.teams.microsoft.com> credenziali di amministratore.

2. Nel **dashboard,** in **Ricerca utente,** iniziare a digitare il nome o l'indirizzo  SIP dell'utente di cui si vuole risolvere i problemi di chiamata oppure selezionare Visualizza utenti per visualizzare un elenco di utenti.

3. Selezionare l'utente nell'elenco.

4. Selezionare **Cronologia chiamate** e quindi selezionare la chiamata o la riunione da risolvere.

5. Selezionare la **scheda Avanzate** e quindi cercare gli elementi giallo e rosso che indicano problemi di qualità della chiamata o di connessione di qualità scarsa.

   Nei dettagli della sessione per ogni chiamata o riunione, i problemi secondari vengono visualizzati in giallo. Se qualcosa è giallo, non rientra nell'intervallo normale e potrebbe contribuire al problema, ma è improbabile che sia la causa principale del problema. Se qualcosa è rosso, si tratta di un problema significativo ed è probabile che sia la causa principale della scarsa qualità delle chiamate per questa sessione.

In rari casi, i dati sulla qualità dell'esperienza non vengono ricevuti per le sessioni audio. Spesso questo problema è causato da una chiamata interrotta o dalla fine della connessione con il client. In questo caso, la valutazione della sessione non è **disponibile.**

Per le sessioni audio con dati QoE (Quality of Experience), la tabella seguente descrive i problemi principali che qualificano una sessione come **scarsa.**

|Problema|Area|Descrizione|
|---|---|---|
|Configurazione della chiamata|Sessione|Il codice di errore Ms-diag 20-29 indica che la configurazione della chiamata non è riuscita. L'utente non è riuscito a partecipare alla chiamata o alla riunione.|
|Chiamata di qualità scarsa classificata per la rete audio|Sessione|Si sono verificati problemi di qualità della rete, ad esempio perdita di pacchetti, instabilità, degradazione di NMOS, RTT o proporzioni nascoste.|
|Dispositivo non funzionante|Dispositivo|Un dispositivo non funziona correttamente. I rapporti di dispositivo non funzionanti sono: <p> DeviceRenderNotFunctioningEventRatio >= 0,005 <br>  DeviceCaptureNotFunctioningEventRatio >= 0,005|
||||

## <a name="related-topics"></a>Argomenti correlati

[Configurare l'analisi delle chiamate per utente](set-up-call-analytics.md)

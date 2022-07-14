---
title: Uso di Call Analytics per risolvere problemi di bassa qualità delle chiamate
author: CarolynRowe
ms.author: crowe
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
description: Usare i dettagli di Call Analytics per utente su dispositivi, reti e connettività per risolvere i problemi degli utenti relativi a chiamate e riunioni di Microsoft Teams.
ms.openlocfilehash: 38636d911be55648ec17628bcec7d4cee21358c5
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794314"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>Uso di Call Analytics per risolvere problemi di bassa qualità delle chiamate

Questo articolo spiega come usare Call Analytics per risolvere problemi di scarsa qualità delle chiamate o delle riunioni di Microsoft Teams per i singoli utenti se si svolge il ruolo di amministratore di Teams, specialista del supporto per le comunicazioni di Teams o ingegnere del supporto per le comunicazioni di Teams.

## <a name="call-analytics-permissions"></a>Autorizzazioni di Call Analytics

Questo articolo presuppone che Call Analytics sia già stato configurato. In caso contrario, vedere [Configurare l'analisi delle chiamate per Teams](set-up-call-analytics.md).

## <a name="introduction-to-call-analytics"></a>Introduzione a Call Analytics

Call Analytics mostra informazioni dettagliate sulle chiamate e le riunioni di Teams per ogni utente nell'account Office 365. Include informazioni su dispositivi, reti, connettività e qualità delle chiamate (uno di questi può essere un fattore di scarsa qualità delle chiamate o delle riunioni). Se si caricano informazioni su edifici, siti e tenant, queste informazioni verranno visualizzate anche per ogni chiamata e riunione. Usare Call Analytics per capire perché un utente ha avuto un'esperienza di chiamata o riunione scadente.

Call Analytics mostra ogni parte di una chiamata o riunione, ad esempio da un partecipante a un secondo partecipante. Analizzando questi dettagli, un amministratore di Teams può isolare le aree problematiche e identificare la causa principale della scarsa qualità.

L'amministratore di Teams ottiene l'accesso completo a tutti i dati di Call Analytics per ogni utente. È anche possibile assegnare ruoli di Azure Active Directory al supporto del personale. Per altre informazioni su questi ruoli, vedere [Concedere l'autorizzazione al supporto e al personale helpdesk](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff). Non perderti [cosa fa ogni ruolo di supporto di Teams?](#what-does-each-teams-support-role-do) di seguito.

## <a name="where-to-find-per-user-call-analytics"></a>Dove trovare Call Analytics per utente

Per visualizzare tutte le informazioni e i dati delle chiamate per un utente, accedere [all'interfaccia di amministrazione di Teams](https://admin.teams.microsoft.com). In **Utenti** selezionare un utente e quindi aprire la scheda **Riunioni & Chiamate** nella pagina del profilo dell'utente. Qui troverai tutte le chiamate e le riunioni per quell'utente negli ultimi 30 giorni.

![Screenshot di tutti i dati utente di analisi.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

Per ottenere informazioni aggiuntive su una determinata sessione, incluse statistiche dettagliate su elementi multimediali e di rete, fare clic su una sessione per visualizzare i dettagli.

![Screenshot dei dati della sessione utente di analisi delle chiamate.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)

## <a name="what-does-each-teams-support-role-do"></a>Cosa fa ogni ruolo di supporto di Teams?

Lo **specialista del supporto per le comunicazioni di Teams** (supporto di Livello 1) gestisce i problemi di base relativi alla qualità delle chiamate. Non esaminano i problemi relativi alle riunioni. Vengono invece raccolte informazioni correlate e quindi inoltrate a un tecnico del supporto per le comunicazioni di Teams.

Il **tecnico del supporto per le comunicazioni di Teams** (supporto di Livello 2) vede le informazioni nei registri delle chiamate dettagliati nascosti allo specialista del supporto per le comunicazioni di Teams. La tabella seguente elenca le informazioni disponibili per ogni ruolo di supporto per le comunicazioni di Teams.

La tabella seguente indica quali informazioni per utente sono disponibili per ogni ruolo di supporto per le comunicazioni.

|Attività|Informazioni|Quali sono le comunicazioni<br>addetto al supporto *tecnico* vede|Quali sono le comunicazioni<br>*il tecnico* del supporto vede|
|---|---|---|---|
|**Chiamate**|Nome chiamante|Solo il nome dell'utente cercato dall'agente.|Nome utente.|
||Nome del destinatario|Mostra come Utente interno o Utente esterno.|Nome del destinatario.|
||Numero di telefono del chiamante|Numero di telefono intero ad eccezione delle ultime tre cifre, mascherate con asterischi. Ad esempio, 15552823\*\*\*.|Numero di telefono intero ad eccezione delle ultime tre cifre, mascherate con asterischi. Ad esempio, 15552823\*\*\*.|
||Numero di telefono del destinatario|Numero di telefono intero ad eccezione delle ultime tre cifre, mascherate con asterischi. Ad esempio, 15552823\*\*\*.|Numero di telefono intero ad eccezione delle ultime tre cifre, mascherate con asterischi. Ad esempio, 15552823\*\*\*.|
||**Dettagli** \> chiamata **Scheda Avanzate**|Informazioni non visualizzate.|Vengono mostrati tutti i dettagli, ad esempio i nomi dei dispositivi, l'indirizzo IP, la mappatura subnet e altro ancora.|
||**Dettagli** \> chiamata **Avanzate** \> **Scheda Debug**|Informazioni non visualizzate.|Vengono mostrati tutti i dettagli, ad esempio suffisso DNS e SSID.|
|**Riunioni**|Nomi dei partecipanti|Solo il nome dell'utente cercato dall'agente. Altri partecipanti identificati come Utente interno o Utente esterno.|Vengono visualizzati tutti i nomi.|
||Numero partecipanti|Numero di partecipanti.|Numero di partecipanti.|
||Dettagli sessione|Dettagli della sessione mostrati con eccezioni. Viene visualizzato solo il nome dell'utente cercato dall'agente. Altri partecipanti identificati come Utente interno o Utente esterno. Le ultime tre cifre del numero di telefono sono mascherate con asterischi.|Vengono mostrati i dettagli della sessione. Vengono visualizzati i nomi utente e i dettagli della sessione. Le ultime tre cifre del numero di telefono sono mascherate con asterischi.|
||||

> [!NOTE]
> Le informazioni contenute nella sezione "Altro" della scheda Avanzate e nella scheda Debug contengono dati di telemetria e di diagnostica del servizio destinati ad assistere i tecnici del supporto tecnico Microsoft. Senza il contesto dei dati aggiuntivi disponibili per supportare i tecnici, potrebbe risultare ridondante, impreciso o confuso. Anche se lo rendono disponibile per gli utenti esperti che stanno cercando un altro livello di dettaglio per la risoluzione dei problemi di chiamata, non è consigliabile esprimere valutazioni in base a questi dati senza il supporto tecnico Microsoft.

## <a name="troubleshoot-user-call-quality-problems"></a>Risolvere i problemi di qualità delle chiamate degli utenti

1. Aprire l'interfaccia di amministrazione di Teams (<https://admin.teams.microsoft.com>) e accedere con le credenziali del supporto per le comunicazioni di Teams o dell'amministratore di Teams.

2. Nel **dashboard**, in **Ricerca utente**, iniziare a digitare il nome o l'indirizzo SIP dell'utente di cui si vogliono risolvere i problemi di chiamata oppure selezionare **Visualizza utenti** per visualizzare un elenco di utenti.

3. Selezionare l'utente dall'elenco.

4. Seleziona **Cronologia chiamate** e quindi seleziona la chiamata o la riunione di cui vuoi risolvere i problemi.

5. Seleziona la scheda **Avanzate** e quindi cerca gli elementi gialli e rossi che indicano una bassa qualità della chiamata o problemi di connessione.

   Nei dettagli della sessione per ogni chiamata o riunione, i problemi secondari vengono visualizzati in giallo. Se qualcosa è giallo, è al di fuori dell'intervallo normale e potrebbe contribuire al problema, ma è improbabile che sia la causa principale del problema. Se qualcosa è rosso, si tratta di un problema significativo ed è probabilmente la causa principale della scarsa qualità delle chiamate per questa sessione.

In rari casi, i dati relativi alla qualità dell'esperienza non sono ricevuti per le sessioni audio. Spesso ciò è causato da una chiamata interrotta o quando la connessione con il client termina. In questo caso, la valutazione della sessione **non è disponibile**.

Per le sessioni audio con dati QoE (Quality of Experience), la tabella seguente descrive i problemi principali che qualificano una sessione come **scadente**.

|Problema|Zona|Descrizione|
|---|---|---|
|Configurazione delle chiamate|Sessione|Il codice di errore Ms-diag 20-29 indica che la configurazione della chiamata non è riuscita. L'utente non ha potuto partecipare alla chiamata o alla riunione.|
|Chiamata di rete audio classificata di qualità scarsa|Sessione|Sono stati rilevati problemi di qualità della rete (ad esempio perdita di pacchetti, instabilità, degradazione NMOS, RTT o rapporto nascosto).|
|Dispositivo non funzionante|Dispositivo|Un dispositivo non funziona correttamente. I rapporti del dispositivo non funzionante sono: <p> DeviceRenderNotFunctioningEventRatio >= 0,005 <br>  DeviceCaptureNotFunctioningEventRatio >= 0,005|
||||

## <a name="related-topics"></a>Argomenti correlati

[Configurare l'analisi delle chiamate per utente](set-up-call-analytics.md)

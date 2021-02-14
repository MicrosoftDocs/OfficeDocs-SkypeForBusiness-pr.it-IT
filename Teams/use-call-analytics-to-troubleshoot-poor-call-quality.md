---
title: Usare i dati analitici delle chiamate per risolvere i problemi di bassa qualità delle chiamate
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
description: Usare i dettagli di analisi delle chiamate per utente su dispositivi, reti e connettività per risolvere i problemi degli utenti con le chiamate e le riunioni di Microsoft Teams.
ms.openlocfilehash: 8bee41e79f2610adcb9a1fed3f895c728526f5ea
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583625"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>Usare i dati analitici delle chiamate per risolvere i problemi di bassa qualità delle chiamate

Questo articolo spiega come usare l'analisi delle chiamate per risolvere problemi di bassa qualità delle chiamate o delle riunioni di Microsoft Teams per i singoli utenti, se sei un amministratore di Teams o un tecnico o un esperto di supporto per le comunicazioni di Teams.


  
## <a name="call-analytics-permissions"></a>Autorizzazioni di Call Analytics

In questo articolo si presuppone che l'analisi delle chiamate sia già stata impostata. In caso contrario, leggi [Configurare l'analisi delle chiamate per Teams.](set-up-call-analytics.md)

## <a name="introduction-to-call-analytics"></a>Introduzione all'analisi delle chiamate

Call Analytics mostra informazioni dettagliate sulle chiamate e le riunioni di Teams per ogni utente nel tuo account Office 365. Include informazioni su dispositivi, reti, connettività e qualità delle chiamate (uno di questi fattori può essere un fattore di scarsa qualità delle chiamate o delle riunioni). Se si caricano informazioni relative a edifici, siti e tenant, queste informazioni verranno visualizzate anche per ogni chiamata e riunione. Usa i dati analitici delle chiamate per capire perché un utente ha avuto un'esperienza di chiamata o riunione scadente.

L'analisi delle chiamate mostra ogni fase di una chiamata o riunione, ad esempio da un partecipante a un secondo partecipante. Analizzando questi dettagli, un amministratore di Teams può isolare le aree interessate e identificare la causa alla radice della qualità scarsa.
   
Come amministratore di Teams, si ottiene l'accesso completo a tutti i dati di analisi delle chiamate per ogni utente. Inoltre, è possibile assegnare ruoli di Azure Active Directory al personale di supporto. Per altre informazioni su questi ruoli, leggere Concedere le autorizzazioni per il personale di supporto [e supporto tecnico.](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff) Cosa fa [ogni ruolo del supporto tecnico di Teams?](#what-does-each-teams-support-role-do) Di seguito.

## <a name="where-to-find-per-user-call-analytics"></a>Dove trovare l'analisi delle chiamate per utente

Per visualizzare tutte le informazioni sulle chiamate e i dati relativi a un utente, accedi all'interfaccia [di amministrazione di Teams.](https://admin.teams.microsoft.com) In **Utenti** seleziona un utente e quindi apri la scheda **Cronologia** chiamate nella pagina del profilo dell'utente. Qui troverai tutte le chiamate e le riunioni per quell'utente per gli ultimi 30 giorni.

![Screenshot di tutti i dati utente di analisi](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

Per ottenere altre informazioni su una determinata sessione, inclusi elementi multimediali dettagliati e statistiche di rete, fare clic su una sessione per visualizzare i dettagli.

![Schermata dei dati della sessione utente di Call Analytics](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)
  
## <a name="what-does-each-teams-support-role-do"></a>Cosa fa ogni ruolo del supporto tecnico di Teams?

**L'esperto del supporto per le** comunicazioni di Teams (supporto di Livello 1) gestisce i problemi di base relativi alla qualità delle chiamate. Non esaminano i problemi relativi alle riunioni. Raccolgono invece informazioni correlate e poi inoltrarle a un tecnico del supporto per le comunicazioni. 

Il **tecnico del supporto per le** comunicazioni di Teams (supporto di Livello 2) vede informazioni in registri chiamate dettagliati che sono nascosti al tecnico del supporto per la comunicazione di Teams. La tabella seguente elenca le informazioni disponibili per ogni ruolo di supporto alla comunicazione di Teams.

La tabella seguente indica quali informazioni per utente sono disponibili per ogni ruolo di supporto per le comunicazioni.

|**Attività**|**Informazioni**|Cosa vede l'esperto del supporto **per le** comunicazioni|Cosa vede il tecnico **del supporto per le** comunicazioni|
|:-----|:-----|:-----|:-----|
|**Chiamate** <br/> |Nome chiamante  <br/> |Solo il nome dell'utente cercato dall'agente.  <br/> |Nome utente.  <br/> |
||Nome del destinatario  <br/> |Mostra come Utente interno o Utente esterno.  <br/> |Nome del destinatario.  <br/> |
||Numero di telefono del chiamante  <br/> |Numero di telefono intero eccetto le ultime tre cifre, offuscati con asterischi. Ad esempio, 15552823***.  <br/> |Numero di telefono intero eccetto le ultime tre cifre, offuscati con asterischi. Ad esempio, 15552823***.  <br/> |
||Numero di telefono del destinatario  <br/> |Numero di telefono intero eccetto le ultime tre cifre, offuscati con asterischi. Ad esempio, 15552823***.  <br/> |Numero di telefono intero eccetto le ultime tre cifre, offuscati con asterischi. Ad esempio, 15552823***.  <br/> |
||**Dettagli chiamata**  >  **Scheda** Avanzate <br/> |Informazioni non visualizzate.  <br/> |Vengono mostrati tutti i dettagli, come i nomi dei dispositivi, l'indirizzo IP, la mappatura della subnet e altro ancora.  <br/> |
||**Dettagli chiamata**  >  **Avanzate**  >  **Scheda** Debug <br/> |Informazioni non visualizzate.  <br/> |Vengono mostrati tutti i dettagli, ad esempio suffisso DNS e SSID.  <br/> |
|**Riunioni** <br/> |Nomi dei partecipanti  <br/> |Solo il nome dell'utente cercato dall'agente. Altri partecipanti identificati come Utente interno o Utente esterno.  <br/> |Vengono visualizzati tutti i nomi.  <br/> |
||Numero di partecipanti  <br/> |Numero di partecipanti.  <br/> |Numero di partecipanti.  <br/> |
||Dettagli della sessione  <br/> |Vengono mostrati i dettagli della sessione, ad eccezione delle eccezioni. Viene visualizzato solo il nome dell'utente cercato dall'agente. Altri partecipanti identificati come Utente interno o Utente esterno. Le ultime tre cifre del numero di telefono sono offuscate con asterischi.  <br/> |Vengono mostrati i dettagli della sessione. Vengono visualizzati i nomi utente e i dettagli della sessione. Le ultime tre cifre del numero di telefono sono offuscate con asterischi.  <br/> |
||||
  
## <a name="troubleshoot-user-call-quality-problems"></a>Risolvere i problemi di qualità delle chiamate degli utenti 

1. Aprire l'interfaccia di amministrazione di Teams (e accedere con le credenziali di amministratore di Teams o di supporto per le https://admin.teams.microsoft.com) comunicazioni di Teams).

2. Nel **Dashboard,** **in** Ricerca utente, inizia a digitare il nome o l'indirizzo  SIP dell'utente per cui vuoi risolvere i problemi di chiamata oppure seleziona Visualizza utenti per visualizzare un elenco di utenti.

3. Selezionare l'utente nell'elenco.

4. Seleziona **Cronologia chiamate,** quindi seleziona la chiamata o la riunione di cui vuoi risolvere i problemi.
    
5. Selezionare la **scheda Avanzate,** quindi cercare gli elementi in giallo e in rosso che indicano una bassa qualità della chiamata o problemi di connessione.
    
    Nei dettagli della sessione per ogni chiamata o riunione, i problemi secondari vengono visualizzati in giallo. Se qualcosa è giallo, non rientra nel normale intervallo e può contribuire al problema, ma è improbabile che sia la causa principale del problema. Se qualcosa è rosso, si tratta di un problema significativo che probabilmente è la causa principale della scarsa qualità delle chiamate per questa sessione. 
      
In rari casi, i dati sulla qualità dell'esperienza non vengono ricevuti per le sessioni audio. Spesso questo problema è causato da una chiamata interrotta o dalla fine della connessione con il client. In questo caso, la valutazione della sessione non è **disponibile.**
  
Per le sessioni audio con dati QoE (Quality of Experience), la tabella seguente descrive i problemi principali che qualificano una sessione come **scadente.**
  
|**Problema**|**Area**|**Descrizione**|
|:-----|:-----|:-----|
|Configurazione delle chiamate  <br/> |Sessione  <br/> |Il codice di errore Ms-diag 20-29 indica che la chiamata non è riuscita. L'utente non ha potuto partecipare alla chiamata o alla riunione.  <br/> |
|Audio network classified poor call  <br/> |Sessione  <br/> |Si sono verificati problemi di qualità della rete (come perdita di pacchetti, instabilità, degradazione NMOS, RTT o rapporto nascosto).  <br/> |
|Il dispositivo non funziona  <br/> |Dispositivo  <br/> | Un dispositivo non funziona correttamente. I rapporti del dispositivo non funzionanti sono: <br/>  DeviceRenderNotFunctioningEventRatio >= 0,005 <br/>  DeviceCaptureNotFunctioningEventRatio >= 0,005 <br/> |
   

## <a name="related-topics"></a>Argomenti correlati

[Configurare l'analisi delle chiamate per utente](set-up-call-analytics.md)



  
 

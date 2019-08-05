---
title: Report di diagnostica attività peer-to-peer in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 025e8ab4-2e64-4a6b-8f52-caf756a5cac3
description: 'Riepilogo: informazioni sul report di diagnostica attività peer-to-peer in Skype for Business Server.'
ms.openlocfilehash: 37773edc939787eff034d8dd6d001e3529c0db91
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188750"
---
# <a name="peer-to-peer-activity-diagnostic-report-in-skype-for-business-server"></a>Report di diagnostica attività peer-to-peer in Skype for Business Server
 
**Riepilogo:** Informazioni sul report di diagnostica attività peer-to-peer in Skype for Business Server.
  
Il report di diagnostica attività peer-to-peer fornisce informazioni sull'esito positivo e negativo delle sessioni di comunicazione peer-to-peer. Tieni presente che Skype for Business Server distingue i diversi tipi di errore:
  
- **Errore previsto**. Un errore previsto è in genere un errore solo in senso più tecnico. Ad esempio, supponiamo che tu chiami qualcuno, ma che sia fuori sede e che non sia in grado di rispondere al telefono. Dato che la chiamata non è stata risolta, la chiamata è tecnicamente considerata un errore. D'altra parte, si trattava di un errore previsto: Skype for Business Server non si aspetta di rispondere al telefono se non si è disponibili per rispondere al telefono. Allo stesso modo, si verificherà un errore previsto se si tenta di inviare un messaggio istantaneo a un utente offline oppure si accede solo a un telefono che non supporta la messaggistica istantanea.
    
- **Errore imprevisto**. Un errore imprevisto è esattamente quello che il nome implica: un errore che, in base alle circostanze, non si aspetterebbe che si verifichi. Ad esempio, supponiamo che tu chiami qualcuno e che la persona sia disponibile per rispondere alla chiamata; Tuttavia, quando Skype for Business Server prova a instradare la chiamata alla segreteria telefonica, la chiamata non riesce perché la connettività alla messaggistica unificata di Exchange è andata perduta. Si tratta di un errore imprevisto: ci si aspetterebbe che le chiamate vengano sempre indirizzate alla segreteria telefonica. Come regola generale, gli errori imprevisti sono errori reali: si tratta di problemi che probabilmente non possono essere risolti tramite l'istruzione degli utenti o misure simili.
    
Tieni presente che l'esito positivo, l'errore previsto e le metriche degli errori imprevisti potrebbero non essere sommati alla metrica totale delle sessioni. Nella figura precedente, ad esempio, sono presenti i valori seguenti:
  
|**Successi**|**Errori previsti**|**Errori imprevisti**|**Totale sessioni**|
|:-----|:-----|:-----|:-----|
|2024  <br/> |469  <br/> |16  <br/> |2521  <br/> |
   
Se si aggiunge 2024 + 469 + 16 si ottengono complessivamente 2.509 sessioni, ma la colonna Total Sessions Mostra un totale di 2.521 sessioni. Le sessioni "mancanti" di 12 sono sessioni che il sistema non è in grado di categorizzare in modo riuscito o fallito. A volte si tratta di un prodotto di terze parti che introduce un nuovo codice diagnostico sconosciuto a Skype for Business Server. In questo caso, le chiamate effettuate tramite tale prodotto e segnalando il codice diagnostico non possono sempre essere categorizzate come un successo, un errore previsto o un errore imprevisto.
  
## <a name="accessing-the-peer-to-peer-activity-diagnostic-report"></a>Accesso al report di diagnostica attività peer-to-peer

Il report di diagnostica peer-to-peer si accede dalla Home page dei report di monitoraggio. Per accedere al [report di distribuzione dell'errore in Skype for Business Server](failure-distribution-report.md) , fare clic su una delle metriche seguenti:
  
- Volume di errore imprevisto
    
- Volume di errore previsto
    
## <a name="making-the-best-use-of-the-peer-to-peer-activity-diagnostic-report"></a>Sfruttare al meglio il rapporto di diagnostica attività peer-to-peer

Esistono diversi modi per filtrare il report di diagnostica attività peer-to-peer ma, per impostazione predefinita, le opzioni di filtro sono nascoste dalla visualizzazione. Per visualizzare le opzioni di filtro disponibili, fare clic sul pulsante Mostra/Nascondi parametri nell'angolo in alto a destra della finestra del report. Dopo aver eseguito l'operazione, le opzioni di filtro saranno disponibili per l'uso.
  
## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Il report di diagnostica attività peer-to-peer, ad esempio, consente di filtrare in base alla modalità di sessione, ad esempio la messaggistica istantanea, il trasferimento di file o la condivisione di applicazioni. È anche possibile scegliere la modalità di raggruppamento dei dati. In questo caso, le chiamate vengono raggruppate per ora, giorno, settimana o mese.
  
Nella tabella seguente sono elencati i filtri che è possibile usare con il report di diagnostica attività peer-to-peer.
  
**Filtri di report di diagnostica attività peer-to-peer**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**Da** <br/> |Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**A** <br/> |Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**Intervallo** <br/> | Intervallo di tempo. Selezionare una delle opzioni seguenti: <br/>  Ogni ora (può essere visualizzato un massimo di 25 ore) <br/>  Giornaliera (è possibile visualizzare un massimo di 31 giorni) <br/>  Settimanale (può essere visualizzato un massimo di 12 settimane) <br/>  Mensile (può essere visualizzato un massimo di 12 mesi) <br/>  Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, viene visualizzato solo il numero massimo di valori (a partire dalla data di inizio). Se ad esempio si seleziona l'intervallo giornaliero con una data di inizio di 7/7/2015 e una data di fine 2/28/2015, i dati verranno visualizzati per i giorni 8/7/2015 12:00 da AM a 9/7/2015 12:00 AM, ovvero un totale di 31 giorni di dati. <br/> |
|**Pool** <br/> |Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale. È possibile selezionare un singolo pool o fare clic su **[tutti]** per visualizzare i dati per tutti i pool. Questo elenco a discesa viene compilato automaticamente in base ai record nel database. <br/> |
|**Modalità** <br/> | Indica il tipo di attività di comunicazione che ha avuto luogo. Selezionare una delle opzioni seguenti: <br/>  Tutti <br/>  Messaggistica istantanea <br/>  Trasferimento di file <br/>  Condivisione applicazioni <br/>  Audio <br/>  Video <br/> |
   
## <a name="metrics-per-modality"></a>Metriche (per modalità)

Nella tabella seguente sono elencate le informazioni fornite nel report di diagnostica attività peer-to-peer per ogni modalità.
  
**Metriche (per modalità)**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Volume di successo** <br/> |No  <br/> |Numero totale di sessioni peer-to-peer di successo.  <br/> |
|**Percentuale di successo** <br/> |No  <br/> |Percentuale di sessioni peer-to-peer completate da problemi significativi. Calcolata dividendo il volume di successo per il totale delle sessioni.  <br/> |
|**Volume di errore previsto** <br/> |No  <br/> |Numero totale di sessioni in cui si è verificato un "errore previsto".  <br/> Un errore previsto è un errore che dovrebbe verificarsi. Ad esempio, se un utente ha impostato il proprio stato su non disturbare, si prevede che qualsiasi chiamata non venga eseguita correttamente.  <br/> |
|**Percentuale di errore prevista** <br/> |No  <br/> |Percentuale di sessioni peer-to-peer che hanno avuto un errore previsto. Calcolata dividendo il volume di errore previsto per le sessioni totali.  <br/> |
|**Volume di errore imprevisto** <br/> |No  <br/> |Numero totale di sessioni in cui si è verificato un "errore imprevisto".  <br/> Un errore imprevisto è un errore che si verifica in quello che sembrerebbe essere un sistema altrimenti integro. Ad esempio, una chiamata non deve essere terminata se il chiamante viene posizionato in attesa. Se questo si verifica, verrebbe contrassegnato come errore imprevisto.  <br/> |
|**Percentuale di errore imprevisto** <br/> |No  <br/> |Percentuale di sessioni peer-to-peer che hanno registrato un errore imprevisto. Calcolata dividendo il volume di errore imprevisto per le sessioni totali.  <br/> |
|**Totale sessioni** <br/> |No  <br/> |Numero totale di sessioni, incluse le sessioni di successo, le sessioni non riuscite (errori previsti e gli errori imprevisti) e le sessioni Uncategorized.  <br/> |
   


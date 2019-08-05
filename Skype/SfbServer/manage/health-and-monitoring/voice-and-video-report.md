---
title: Report vocale e video peer-to-peer in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e17c36b5-5a2f-4673-9696-3b2d31c2bb2f
description: 'Riepilogo: informazioni sul report vocale e video peer-to-peer in Skype for Business Server.'
ms.openlocfilehash: 8ba665886e91371373358f98f69fa15b8d62a9dd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188621"
---
# <a name="peer-to-peer-voice-and-video-report-in-skype-for-business-server"></a>Report vocale e video peer-to-peer in Skype for Business Server
 
**Riepilogo:** Informazioni sul report vocale e video peer-to-peer in Skype for Business Server.
  
Il report vocale e video peer-to-peer fornisce un'analisi dettagliata della distribuzione delle chiamate vocali e video in un determinato periodo di tempo, ad esempio chiamate per ora o chiamate per giorno. Il report offre anche l'opzione di visualizzare tutte le chiamate vocali e video effettuate o di visualizzare solo le chiamate di successo o non riuscito. I report mostrano le informazioni sulle chiamate suddivise nei raggruppamenti seguenti:
  
- Chiamate per pool
    
- Chiamate per tipo di chiamata (ad esempio, una chiamata Skype for business a Skype for business e una chiamata Skype for business a una persona nella rete PSTN)
    
- Chiamate per tipo di accesso (gli utenti hanno effettuato l'accesso alla rete interna e agli utenti connessi alla rete esterna)
    
- Chiamate per Mediation Server
    
## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a>Per accedere al report vocale e video peer-to-peer

È possibile accedere al report vocale e video peer-to-peer solo aprendo il report di riepilogo attività peer-to-peer e quindi facendo clic su una delle metriche seguenti:
  
- Totale sessioni audio peer-to-peer
    
- Totale minuti audio peer-to-peer
    
- Totale sessioni video peer-to-peer
    
- Totale minuti di video peer-to-peer
    
## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a>Per sfruttare al meglio il rapporto voce e video peer-to-peer

È possibile filtrare il report vocale e video peer-to-peer in diversi modi. Tuttavia, le opzioni di filtro sono nascoste dalla visualizzazione per impostazione predefinita. Per visualizzare le opzioni di filtro disponibili, fare clic sul pulsante **Mostra/Nascondi parametri** nell'angolo in alto a destra della finestra del report.
  
## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati in modi diversi. Nella tabella seguente sono elencati i filtri che è possibile usare con il report vocale e video peer-to-peer.
  
**Filtri di report vocali e video peer-to-peer**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**Da** <br/> |Data e ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**A** <br/> |Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**Intervallo** <br/> | Intervallo di tempo. Selezionare una delle opzioni seguenti: <br/>  Ogni ora (può essere visualizzato un massimo di 25 ore) <br/>  Giornaliera (è possibile visualizzare un massimo di 31 giorni) <br/>  Settimanale (può essere visualizzato un massimo di 12 settimane) <br/>  Mensile (può essere visualizzato un massimo di 12 mesi) <br/>  Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, viene visualizzato solo il numero massimo di valori (a partire dalla data di inizio). Se ad esempio si seleziona l'intervallo giornaliero con una data di inizio di 7/7/2015 e una data di fine 2/28/2015, i dati verranno visualizzati per i giorni 8/7/2015 12:00 da AM a 9/7/2015 12:00 AM, ovvero un totale di 31 giorni di dati. <br/> |
|**Tipo di elemento multimediale** <br/> | Indica il tipo di elemento multimediale usato nella sessione. Selezionare una delle opzioni seguenti: <br/>  Sia <br/>  Audio <br/>  Video <br/> |
|**Disposizione chiamata** <br/> | Indica l'esito positivo o negativo della sessione. Selezionare una delle opzioni seguenti: <br/>  Tutti <br/>  Chiamate di successo <br/>  Chiamate non riuscite <br/> |
|**Report di** <br/> | Indica i valori da usare nel report. Selezionare una delle opzioni seguenti: <br/>  Conteggio sessioni <br/>  Minuti di chiamata <br/> |
   
## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a>Metriche per l'attività vocale e video peer-to-peer per pool

Nella tabella seguente sono elencate le informazioni fornite nel report vocale e video peer-to-peer per ogni pool.
  
**Metriche per l'attività vocale e video peer-to-peer per pool**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Pool** <br/> |No  <br/> |Nome del pool di registrazione o del server perimetrale usato per la chiamata.  <br/> |
|**Data/ora** <br/> |No  <br/> |Periodo di data e ora in cui la chiamata ha avuto luogo.  <br/> |
|**Totale** <br/> |No  <br/> |Numero totale di sessioni o conteggio totale dei messaggi.  <br/> |
   
## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a>Metriche per l'attività vocale e video peer-to-peer tramite il tipo di chiamata

Nella tabella seguente sono elencate le informazioni fornite nel report vocale e video peer-to-peer per ogni tipo di chiamata effettuata.
  
**Metriche per l'attività vocale e video peer-to-peer tramite il tipo di chiamata**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Tipo di chiamata** <br/> |No  <br/> | Indica il tipo di chiamata effettuata. I valori sono uno degli elementi seguenti: <br/>  UC-to-UC <br/>  UC-to-PSTN <br/>  PSTN-to-UC <br/>  PSTN-to-PSTN <br/> |
|**Data/ora** <br/> |No  <br/> |Periodo di data e ora in cui la chiamata ha avuto luogo.  <br/> |
|**Totale** <br/> |No  <br/> |Numero totale di sessioni o conteggio totale dei messaggi.  <br/> |
   
## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a>Metriche per l'attività voce e video peer-to-peer per tipo di accesso

Nella tabella seguente sono elencate le informazioni fornite nel report vocale e video peer-to-peer per ogni tipo di accesso alla rete.
  
**Metriche per l'attività voce e video peer-to-peer per tipo di accesso**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Tipo di attività** <br/> |No  <br/> | Indica se i client hanno eseguito l'accesso alla rete interna o alla rete esterna quando è stata inserita la chiamata. I valori sono in genere uno degli elementi seguenti: <br/>  Interno <br/>  Esterno <br/>  Misto <br/> |
|**Data/ora** <br/> |No  <br/> |Periodo di data e ora in cui la chiamata ha avuto luogo.  <br/> |
|**Totale** <br/> |No  <br/> |Numero totale di sessioni o conteggio totale dei messaggi.  <br/> |
   
## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a>Metriche per l'attività di voce e video peer-to-peer da Mediation Server

Nella tabella seguente sono elencate le informazioni fornite nel report vocale e video peer-to-peer per ogni Mediation Server.
  
**Metriche per l'attività di voce e video peer-to-peer da Mediation Server**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Mediation Server** <br/> |No  <br/> |Nome del Mediation Server.  <br/> |
|**Data/ora** <br/> |No  <br/> |Periodo di data e ora in cui la chiamata ha avuto luogo.  <br/> |
|**Totale** <br/> |No  <br/> |Numero totale di sessioni o conteggio totale dei messaggi.  <br/> |
   


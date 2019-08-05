---
title: Report di riepilogo attività peer-to-peer in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e829a21e-9dfa-46ba-9b5b-077c175d6586
description: 'Riepilogo: informazioni sul report di riepilogo attività peer-to-peer in Skype for Business Server.'
ms.openlocfilehash: dd11e5d998c8aef779b98cc0a74ba83a4dc70d84
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188738"
---
# <a name="peer-to-peer-activity-summary-report-in-skype-for-business-server"></a>Report di riepilogo attività peer-to-peer in Skype for Business Server
 
**Riepilogo:** Informazioni sul report di riepilogo attività peer-to-peer in Skype for Business Server.
  
Il report di riepilogo attività peer-to-peer offre una visualizzazione complessiva delle sessioni di comunicazione peer-to-peer. Una sessione peer-to-peer in genere coinvolge solo due utenti e non richiede l'uso dei servizi di conferenza di Skype for Business Server. In confronto, una conferenza in genere coinvolge più di due utenti e richiede l'uso di servizi di conferenza di Skype for Business Server. L'attività conferenza viene segnalata nel report di riepilogo conferenza.
  
Il report di riepilogo attività peer-to-peer consente di rispondere a domande come le seguenti:
  
- Quanti messaggi istantanei peer-to-peer i miei utenti inviano in un giorno tipico?
    
- I miei utenti sfruttano effettivamente le funzionalità di condivisione delle applicazioni e di trasferimento di file di Skype for Business Server?
    
- Gli utenti si lamentano che la rete sembra lenta in determinate ore del giorno. Quanti minuti sono dedicati alle sessioni audio e video peer-to-peer in questi periodi di tempo?
    
## <a name="accessing-the-peer-to-peer-activity-summary-report"></a>Accesso al report di riepilogo attività peer-to-peer

È possibile accedere al report di riepilogo attività peer-to-peer dalla Home page dei report di monitoraggio. Per aprire il [report di messaggistica istantanea peer-to-peer in Skype for Business Server](im-report.md) , fare clic su una delle metriche seguenti:
  
- Totale sessioni di messaggistica istantanea peer-to-peer
    
- Totale messaggi di messaggistica istantanea peer-to-peer
    
Analogamente, è possibile aprire il report vocale e video peer-to-peer facendo clic su una delle metriche seguenti:
  
- Totale sessioni audio peer-to-peer
    
- Totale minuti sessioni audio peer-to-peer
    
- Totale sessioni audio peer-to-peer
    
- Totale minuti sessioni audio peer-to-peer
    
## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a>Sfruttare al meglio il rapporto di riepilogo attività peer-to-peer

Nella parte inferiore del report di riepilogo attività peer-to-peer si trovano i totali per le metriche, ad esempio le sessioni di messaggistica istantanea Total peer-to-peer e i messaggi di messaggistica istantanea totali peer-to-peer. In questo modo è disponibile un breve riepilogo delle informazioni dettagliate presenti nel corpo del report.
  
## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Il report di riepilogo attività peer-to-peer, ad esempio, consente di scegliere la modalità di raggruppamento dei dati. In questo caso, attività raggruppate per ora, giorno, settimana o mese.
  
Nella tabella seguente sono elencati i filtri che è possibile usare con il report di riepilogo attività peer-to-peer.
  
**Filtri dei report di riepilogo attività peer-to-peer**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**Da** <br/> |Data e ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:  <br/> 7/17/12015 1:00 PM  <br/> Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/17/12015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/13/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**A** <br/> |Data e ora di fine per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:  <br/> 7/17/12015 1:00 PM  <br/> Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/17/12015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/13/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**Intervallo** <br/> | Intervallo di tempo. Selezionare una delle opzioni seguenti: <br/>  Ogni ora (può essere visualizzato un massimo di 25 ore) <br/>  Giornaliera (è possibile visualizzare un massimo di 31 giorni) <br/>  Settimanale (può essere visualizzato un massimo di 12 settimane) <br/>  Mensile (può essere visualizzato un massimo di 12 mesi) <br/>  Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, viene visualizzato solo il numero massimo di valori (a partire dalla data di inizio). Se ad esempio si seleziona l'intervallo giornaliero con una data di inizio di 7/17/12015 e una data di fine 2/28/2015, i dati verranno visualizzati per i giorni 8/7/12015 12:00 da AM a 9/7/12015 12:00 AM, ovvero un totale di 31 giorni di dati. <br/> |
   
## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni fornite nel report di riepilogo attività peer-to-peer.
  
**Metriche rapporto di riepilogo attività peer-to-peer**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Oraria** <br/> **Quotidiana** <br/> **Settimanale** <br/> **Mensile** <br/> |No  <br/> |Indica l'intervallo di tempo selezionato sulla barra degli strumenti filtro. Se applicabile, è possibile fare clic su un intervallo di tempo specifico per visualizzare informazioni dettagliate per l'intervallo. Se ad esempio si usa l'intervallo giornaliero e si fa clic su 7/17/12015, viene visualizzata una ripartizione oraria dell'attività di registrazione utente per tale data.  <br/> |
|**Totale sessioni peer-to-peer** <br/> |No  <br/> |Numero totale di sessioni peer-to-peer condotte, indipendentemente dal tipo di sessione.  <br/> |
|**Totale sessioni di messaggistica istantanea peer-to-peer** <br/> |No  <br/> |Numero totale di sessioni di messaggistica istantanea peer-to-peer. Quando si fa clic su questo elemento, nel report viene visualizzato il report di messaggistica istantanea peer-to-peer per il periodo di tempo selezionato.  <br/> |
|**Totale messaggi di messaggistica istantanea peer-to-peer** <br/> |No  <br/> |Numero totale di messaggi istantanei inviati nelle sessioni peer-to-peer. Quando si fa clic su questo elemento, nel report viene visualizzato il report di messaggistica istantanea peer-to-peer per il periodo di tempo selezionato.  <br/> |
|**Totale sessioni audio peer-to-peer** <br/> |No  <br/> |Numero totale di chiamate audio peer-to-peer. Quando si fa clic su questo campo, nel report viene visualizzato il report vocale e video peer-to-peer per il periodo di tempo selezionato.  <br/> |
|**Totale minuti sessioni audio peer-to-peer** <br/> |No  <br/> |Quantità totale di tempo trascorso nelle sessioni audio peer-to-peer. Quando si fa clic su questo elemento, il report Mostra il report vocale e video peer-to-peer per il periodo di tempo selezionato.  <br/> |
|**Minuti medi della sessione audio peer-to-peer** <br/> |No  <br/> |Intervallo di tempo medio trascorso nelle sessioni audio peer-to-peer. Calcolata dividendo il tempo totale della sessione audio in base al numero totale di sessioni audio.  <br/> |
|**Totale sessioni video peer-to-peer** <br/> |No  <br/> |Numero totale di chiamate video peer-to-peer. Tieni presente che le sessioni video vengono conteggiate anche come sessioni audio: ogni sessione video viene conteggiata come una sessione video e una sessione audio. Quando si fa clic su questo elemento, il report Mostra il report vocale e video peer-to-peer per il periodo di tempo selezionato.  <br/> |
|**Totale minuti sessioni video peer-to-peer** <br/> |No  <br/> |Quantità totale di tempo trascorso nelle sessioni video peer-to-peer. Quando si fa clic su questo elemento, il report Mostra il report vocale e video peer-to-peer per il periodo di tempo selezionato.  <br/> |
|**Minuti media sessione video peer-to-peer** <br/> |No  <br/> |Intervallo di tempo medio trascorso nelle sessioni video peer-to-peer. Calcolata dividendo il tempo totale della sessione video in base al numero totale di sessioni video.  <br/> |
|**Totale sessioni di trasferimento di file peer-to-peer** <br/> |No  <br/> |Numero totale di sessioni peer-to-peer che includevano i trasferimenti di file.  <br/> |
|**Totale sessioni di condivisione applicazioni peer-to-peer** <br/> |No  <br/> |Numero totale di sessioni peer-to-peer che includevano la condivisione di applicazioni.  <br/> |
   


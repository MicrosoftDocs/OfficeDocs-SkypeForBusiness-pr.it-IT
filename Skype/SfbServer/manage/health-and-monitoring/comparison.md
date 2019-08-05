---
title: Report di confronto qualità multimediale in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1d0b5a8-98ff-455a-b78b-a05a21cf066d
description: 'Riepilogo: informazioni sul report di confronto qualità multimediale in Skype for Business Server.'
ms.openlocfilehash: d665c568bcda1be6124b30f5f2907447fa585343
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191375"
---
# <a name="media-quality-comparison-report-in-skype-for-business-server"></a>Report di confronto qualità multimediale in Skype for Business Server
 
**Riepilogo:** Informazioni sul report di confronto qualità multimediale in Skype for Business Server.
  
Il report di confronto qualità multimediale consente di confrontare i valori della qualità delle chiamate per i diversi tipi di chiamate audio, ad esempio le chiamate effettuate tramite una rete wireless o le chiamate effettuate tramite una connessione cablata.
  
## <a name="accessing-the-media-quality-comparison-report"></a>Accesso al report di confronto qualità multimediale

È possibile accedere al report di confronto qualità multimediale dalla Home page dei report di monitoraggio. 
  
## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Nella tabella seguente sono elencati i filtri che è possibile usare con il report di confronto qualità multimediale.
  
**Filtri di report di confronto qualità multimediale**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**Da** <br/> |Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**A** <br/> |Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**Chiamate** <br/> | Tipo di chiamata da usare come elemento di confronto principale. I valori consentiti sono: <br/>  Tutti <br/>  Esterno <br/>  Interno <br/>  VPN <br/>  Non VPN <br/>  Cablata <br/>  Wireless <br/>  Esterna e cablata <br/>  Esterno e wireless <br/>  Esterna e VPN <br/>  Esterno e non VPN <br/>  Interni e cablati <br/>  Interni e wireless <br/> |
|**Confronto con le chiamate** <br/> | Tipo di chiamata da usare come elemento di confronto secondario. I valori consentiti sono: <br/>  Tutti <br/>  Esterno <br/>  Interno <br/>  VPN <br/>  Non VPN <br/>  Cablata <br/>  Wireless <br/>  Esterna e cablata <br/>  Esterno e wireless <br/>  Esterna e VPN <br/>  Esterno e non VPN <br/>  Interni e cablati <br/>  Interni e wireless <br/> |
|**Intervallo** <br/> | Intervallo di tempo. Selezionare una delle opzioni seguenti: <br/>  Ogni ora (può essere visualizzato un massimo di 25 ore) <br/>  Giornaliera (è possibile visualizzare un massimo di 31 giorni) <br/>  Settimanale (può essere visualizzato un massimo di 12 settimane) <br/>  Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, viene visualizzato solo il numero massimo di valori (a partire dalla data di inizio). Se ad esempio si seleziona l'intervallo giornaliero con una data di inizio di 7/7/2015 e una data di fine 2/28/2015, i dati verranno visualizzati per i giorni 8/7/2015 12:00 da AM a 9/7/2015 12:00 AM, ovvero un totale di 31 giorni di dati. <br/> |
   
## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni fornite nel report di confronto qualità multimediale.
  
**Metriche del report di confronto qualità multimediale**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Volume chiamata** <br/> |No  <br/> |Numero totale di chiamate.  <br/> |
|**Degradazione (MOS)** <br/> |No  <br/> |Importo medio della degradazione MOS (media Opinion Score) con esperienza durante una chiamata. I valori di degradazione possono variare da un minimo di 0,0 a un massimo di 5,0; un valore di 0,5 o meno rappresenta una degradazione accettabile. Storicamente, i punteggi degli opinion media sono stati calcolati avendo gli utenti valutano la qualità di una chiamata su una scala da 1 a 5. Skype for Business Server usa un set di algoritmi per prevedere in che modo gli utenti avrebbero valutato una chiamata.  <br/> I valori di degradazione elevati possono essere causati dalla congestione; mancanza di larghezza di banda; congestione o interferenza wireless oppure un server multimediale o un endpoint di overload. L'elevata degradazione genera un audio distorta o perso.  <br/> |
|**Percentuale di chiamata scadente** <br/> |No  <br/> |Numero totale di chiamate classificate come scarse. Una chiamata scadente è una chiamata che almeno una delle metriche misurate ha superato il valore consentito, ad esempio una chiamata con un eccessivo jitter.  <br/> |
|**Andata e ritorno (MS)** <br/> |No  <br/> |Importo medio (in millisecondi) richiesto per un pacchetto di protocollo di trasporto in tempo reale per spostarsi in un altro endpoint e quindi viceversa. I tempi di andata e ritorno di 200 millisecondi sono considerati di qualità accettabile.  <br/> I valori alti di andata e ritorno possono essere causati da routing delle chiamate internazionali; una configurazione errata di routing; o un server multimediale in overload. Gli alti tempi di andata e ritorno si verificano in difficoltà con le conversazioni audio in tempo reale a due vie.  <br/> |
|**Perdita di pacchetti** <br/> |No  <br/> |Tasso medio di perdita di pacchetti RTP (Real-Time Transport Protocol). La perdita di pacchetti si verifica quando i pacchetti RTP, un protocollo usato per la trasmissione di audio e video su Internet, non riescono a raggiungere la destinazione. I tassi di perdita elevati sono in genere causati dalla congestione; mancanza di larghezza di banda; congestione o interferenza wireless; o un server multimediale in overload. La perdita di pacchetti in genere genera un audio distorta o perso.  <br/> |
|**Jitter (MS)** <br/> |No  <br/> |Jitter medio rilevato tra gli arrivi del pacchetto RTP. (Jitter è una misura della "shakiness" di una chiamata). I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o perse.  <br/> |
|**Rapporto nascosto del guaritore** <br/> |No  <br/> |Rapporto media tra campioni audio nascosti e il totale al numero totale di esempi. (Un esempio di audio nascosto è una tecnica usata per attenuare la transizione brusca che in genere viene causata da pacchetti di rete eliminati). I valori elevati indicano livelli significativi di occultamento delle perdite applicati a causa di perdita di pacchetti o jitter e generano audio distorte o perse.  <br/> |
|**Rapporto allungato guaritore** <br/> |No  <br/> |Rapporto medio tra campioni audio allungati e il totale al numero totale di esempi. (L'audio allungato è l'audio che è stato espanso per mantenere la qualità delle chiamate quando è stato rilevato un pacchetto di rete scartato). I valori alti indicano livelli significativi di stretching dei campioni causati da jitter e generano audio o distorte.  <br/> |
|**Rapporto compresso del guaritore** <br/> |No  <br/> |Rapporto medio tra campioni audio compressi e il numero totale di esempi. (L'audio compresso è un audio compresso che consente di mantenere la qualità delle chiamate quando è stato rilevato un pacchetto di rete scartato). I valori alti indicano livelli significativi di compressione dei campioni causati da jitter e generano un suono accelerato o distorta.  <br/> |
   


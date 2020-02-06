---
title: Report trend qualità media del server in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8a51fd13-1487-4632-b5ec-f7ae2abe8ed4
description: 'Riepilogo: informazioni sul report sulle tendenze del supporto per la qualità del server in Skype for Business Server.'
ms.openlocfilehash: eca6aa75d7b831356da15a86692658019b3c0d54
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817715"
---
# <a name="server-media-quality-trend-report-in-skype-for-business-server"></a>Report trend qualità media del server in Skype for Business Server
 
**Riepilogo:** Informazioni sul report sulle tendenze di qualità media del server in Skype for Business Server.
  
Il report tendenze per la qualità dei contenuti multimediali consente di confrontare graficamente fino a cinque server in termini di qualità delle metriche dell'esperienza, ad esempio il volume delle chiamate, la percentuale di chiamata scadente, la perdita di pacchetti e il jitter. In questo modo, è più facile eseguire operazioni come identificare i server che eseguono in modo poco corretto, identificare i server sottoutilizzati o identificare i server che vengono sovrautilizzati.
  
## <a name="accessing-the-server-media-quality-trend-report"></a>Accesso al report trend qualità media del server

È possibile accedere al report trend qualità media del server da uno dei report seguenti:
  
- [Report sulle prestazioni del server in Skype for Business Server](server-performance.md) (facendo clic sulla metrica di tendenza)
    
- [Report dettagli chiamata in Skype for Business Server](call-detail-report.md) (facendo clic sulla metrica a/V Edge Server. Se il chiamante o il visitatore è un server, è anche possibile raggiungere il report trend media per la qualità del server facendo clic sul nome dell'endpoint.
    
## <a name="making-the-best-use-of-server-media-quality-trend-report"></a>Sfruttare al meglio il report trend di qualità media del server

Quando si fa clic sulla metrica di tendenza nel [report sulle prestazioni del server in Skype for Business Server](server-performance.md) per un server specifico, viene aperto il report trend qualità media del server. Verrà tuttavia visualizzata solo un'istanza vuota del report. il server selezionato nel report prestazioni server non verrà visualizzato sullo schermo. È invece necessario selezionare il server dall'elenco a discesa Server. Tieni presente che anche l'elenco a discesa dei server include un'opzione Seleziona tutto. Questa opzione non funziona se si hanno più di 5 Server; il report trend Quality media server può visualizzare solo i dati per un massimo di 5 server alla volta.
  
Nei grafici visualizzati dal report trend qualità media del server, i punti etichettati volume chiamata e percentuale di chiamata scadente sono hotlinks; facendo clic su un punto del grafico si aprirà un'istanza del [report elenco chiamate in Skype for Business Server](call-list-report-0.md) che mostra le chiamate totali (o chiamate scadenti) per il periodo di tempo specificato.
  
## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Nella tabella seguente sono elencati i filtri che è possibile usare con il report trend qualità media del server.
  
**Filtri per i report sulle tendenze della qualità multimediale del server**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**Da** <br/> |Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**A** <br/> |Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**Intervallo** <br/> | Intervallo di tempo. Selezionare una delle opzioni seguenti: <br/>  Ogni ora (può essere visualizzato un massimo di 25 ore) <br/>  Giornaliera (è possibile visualizzare un massimo di 31 giorni) <br/>  Settimanale (può essere visualizzato un massimo di 12 settimane) <br/>  Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, viene visualizzato solo il numero massimo di valori (a partire dalla data di inizio). Se ad esempio si seleziona l'intervallo giornaliero con una data di inizio di 8/7/2015 e una data di fine 9/28/2015, i dati verranno visualizzati per i giorni 8/7/2015 12:00 da AM a 9/7/2015 12:00 AM, ovvero un totale di 31 giorni di dati. <br/> |
|**Tipo di server** <br/> | Tipo di server coinvolto nella chiamata. I valori consentiti sono: <br/>  Mediation Server <br/>  A/V Conferencing Server <br/>  A/V Edge Server <br/>  Gateway (Mediation Server) <br/>  Gateway (bypass Mediation Server) <br/>  COME server delle conferenze <br/> |
|**Server** <br/> |Nome del server coinvolto nella sessione; Questo elenco a discesa viene compilato automaticamente in base al valore del filtro del tipo di server. Quando si compila un report, è possibile selezionare fino a 5 server diversi.  <br/> |
|**Tipo di accesso** <br/> | Indica se il partecipante ha effettuato l'accesso alla rete interna o alla rete esterna. I valori consentiti sono: <br/>  Tutti <br/>  Interno <br/>  Esterno <br/> |
|**Tipo di rete** <br/> | Indica il tipo di rete a cui il partecipante è connesso. I valori consentiti sono: <br/>  Tutti <br/>  Cablata <br/>  Wireless <br/> |
|**VPN** <br/> | Indica se un partecipante esterno usa una connessione VPN (Virtual Private Network) durante la sessione. I valori consentiti sono: <br/>  Tutti <br/>  VPN <br/>  Non VPN <br/> |
   
## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni disponibili nel report trend qualità media del server.
  
**Metriche dei report sulle tendenze della qualità multimediale del server**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Volume chiamata** <br/> |No  <br/> |Numero totale di chiamate.  <br/> |
|**Degradazione (MOS)** <br/> |No  <br/> |Valore medio della degradazione MOS (Media Option score) sperimentata durante una chiamata. I valori di degradazione possono variare da un minimo di 0,0 a un massimo di 5,0; un valore di 0,5 o meno rappresenta una degradazione accettabile. Storicamente, i punteggi delle opzioni medie sono stati calcolati avendo gli utenti valutano la qualità di una chiamata in una scala da 1 a 5. Skype for Business Server usa un set di algoritmi per prevedere in che modo gli utenti avrebbero valutato una chiamata.  <br/> I valori di degradazione elevati possono essere causati dalla congestione; mancanza di larghezza di banda; congestione o interferenza wireless oppure un server multimediale o un endpoint di overload. L'elevata degradazione genera un audio distorta o perso.  <br/> |
|**Percentuale di chiamata scadente** <br/> |No  <br/> |Numero totale di chiamate classificate come scarse. Una chiamata scadente è una chiamata che almeno una delle metriche misurate ha superato il valore consentito, ad esempio una chiamata con un eccessivo jitter.  <br/> |
|**Andata e ritorno (MS)** <br/> |No  <br/> |Intervallo di tempo medio (in millisecondi) necessario per un pacchetto di protocollo di trasporto in tempo reale per spostarsi in un punto finale e quindi viceversa. I tempi di andata e ritorno di 200 millisecondi sono considerati di qualità accettabile.  <br/> I valori alti di andata e ritorno possono essere causati da routing delle chiamate internazionali; una configurazione errata di routing; o un server multimediale in overload. Gli alti tempi di andata e ritorno si verificano in difficoltà con le conversazioni audio in tempo reale a due vie.  <br/> |
|**Perdita di pacchetti** <br/> |No  <br/> |Tasso medio di perdita di pacchetti RTP (Real-Time Transport Protocol). La perdita di pacchetti si verifica quando i pacchetti RTP, un protocollo usato per la trasmissione di audio e video su Internet, non riescono a raggiungere la destinazione. I tassi di perdita elevati sono in genere causati dalla congestione; mancanza di larghezza di banda; congestione o interferenza wireless; o un server multimediale in overload. La perdita di pacchetti in genere genera un audio distorta o perso.  <br/> |
|**Jitter (MS)** <br/> |No  <br/> |Jitter medio rilevato tra gli arrivi del pacchetto RTP. (Jitter è una misura della "shakiness" di una chiamata). I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o perse.  <br/> |
|**Rapporto nascosto del guaritore** <br/> |No  <br/> |Rapporto media tra campioni audio nascosti e il totale al numero totale di esempi. (Un esempio di audio nascosto è una tecnica usata per attenuare la transizione brusca che in genere viene causata da pacchetti di rete eliminati). I valori elevati indicano livelli significativi di occultamento delle perdite applicati a causa di perdita di pacchetti o jitter e generano audio distorte o perse.  <br/> |
|**Rapporto allungato guaritore** <br/> |No  <br/> |Rapporto medio tra campioni audio allungati e il totale al numero totale di esempi. (L'audio allungato è l'audio che è stato espanso per mantenere la qualità delle chiamate quando è stato rilevato un pacchetto di rete scartato). I valori alti indicano livelli significativi di stretching dei campioni causati da jitter e generano audio o distorte.  <br/> |
|**Rapporto compresso del guaritore** <br/> |No  <br/> |Rapporto medio tra campioni audio compressi e il numero totale di esempi. (L'audio compresso è un audio compresso che consente di mantenere la qualità delle chiamate quando è stato rilevato un pacchetto di rete scartato). I valori alti indicano livelli significativi di compressione dei campioni causati da jitter e generano un suono accelerato o distorta.  <br/> |
   


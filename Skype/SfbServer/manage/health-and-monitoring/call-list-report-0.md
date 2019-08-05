---
title: Report elenco chiamate in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9739f9f0-7a37-4844-91d5-f089d2011013
description: 'Riepilogo: informazioni sul report elenco chiamate usato in Skype for Business Server.'
ms.openlocfilehash: fcf7f0e5f34a48644c8bd3bad3f1f2267afeb63d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191402"
---
# <a name="call-list-report-in-skype-for-business-server"></a>Report elenco chiamate in Skype for Business Server
 
**Riepilogo:** Informazioni sul report elenco chiamate usato in Skype for Business Server.
  
Il report elenco chiamate offre metriche di qualità delle esperienze (QoE) per le singole chiamate effettuate e ricevute nell'organizzazione. Tieni presente che le metriche effettive segnalate dipendono dalla modalità di accesso al report elenco chiamate. Ad esempio, se si apre il report dal [report del dispositivo in Skype for Business Server](device-report.md), verranno visualizzate le metriche, come le metriche seguenti, che vengono anche segnalate nel report del dispositivo:
  
- Microfono del chiamante
    
- Altoparlante del chiamante
    
- Microfono del destinatario
    
- Altoparlante del destinatario
    
- Rapporto tra il tempo di cambio vocale 
    
Tuttavia, se si apre il report elenco chiamate dal [report posizione in Skype for Business Server](location-report.md), non verrà visualizzata alcuna di queste metriche. vedrai invece le metriche come queste:
  
- Andata e ritorno (MS)
    
- Degradazione (MOS)
    
- Perdita di pacchetti
    
- Jitter (MS)
    
Queste sono le metriche segnalate nel report posizione. Tuttavia, dal report elenco chiamate è sempre possibile fare clic sulla metrica Dettagli per specificare le informazioni QoE complete per qualsiasi chiamata.
  
## <a name="accessing-the-call-list-report"></a>Accesso al report elenco chiamate

È possibile accedere al report elenco chiamate da uno dei report seguenti:
  
- Il [report posizione in Skype for Business Server](location-report.md) (facendo clic sul volume delle chiamate o sulla metrica della percentuale di chiamata scadente)
    
- Il [report del dispositivo in Skype for Business Server](device-report.md) (facendo clic sul volume delle chiamate o sulla metrica della percentuale di chiamata scadente)
    
- [Report di riepilogo qualità multimediale in Skype for Business Server](summary.md) (facendo clic sul volume delle chiamate o sulla metrica della percentuale di chiamata scadente)
    
- [Report sulle prestazioni del server in Skype for Business Server](server-performance.md) (facendo clic sul volume delle chiamate o sulla metrica della percentuale di chiamata scadente)
    
Dall'interno del report elenco chiamate è possibile accedere al [report dettagli chiamata in Skype for Business Server](call-detail-report.md) facendo clic sulla metrica dettaglio.
  
## <a name="making-the-best-use-of-the-call-list-report"></a>Sfruttare al meglio il report elenco chiamate

Se non si ricordano le metriche del rapporto elenco chiamate (ad esempio il tempo di cambio di rapporto vocale), tenere il mouse sopra l'etichetta metrica; verrà visualizzata una descrizione comando che consente di visualizzare brevemente la metrica.
  
## <a name="filters"></a>Filtri

Nessuno. Non è possibile filtrare il report elenco chiamate.
  
## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni fornite nel report elenco chiamate per ogni chiamata.
  
**Metriche rapporto elenco chiamate**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Dettagli** <br/> |No  <br/> |Quando si fa clic su questo elemento, nel report vengono visualizzate altre informazioni sulla chiamata.  <br/> |
|**Chiamante** <br/> |Sì  <br/> |Indirizzo SIP della persona che ha avviato la chiamata.  <br/> |
|**Chiamato** <br/> |Sì  <br/> |Indirizzo SIP della persona che è stata chiamata.  <br/> |
|**Ora di inizio** <br/> |Sì  <br/> |Data e ora di inizio della chiamata.  <br/> |
|**Ora di fine** <br/> |Sì  <br/> |Data e ora di fine della chiamata.  <br/> |
|**Agente utente chiamante** <br/> |Sì  <br/> |Software usato dall'endpoint della persona che ha avviato la chiamata.  <br/> |
|**Agente utente chiamato** <br/> |Sì  <br/> |Software usato dall'endpoint della persona chiamata.  <br/> |
|**Andata e ritorno (MS)** <br/> |Sì  <br/> |Importo medio (in millisecondi) richiesto per un pacchetto RTP (Real-Time Transport Protocol) per spostarsi in un altro endpoint e quindi viceversa. I tempi di andata e ritorno di 100 millisecondi sono considerati di qualità accettabile.  <br/> I valori alti di andata e ritorno possono essere causati da routing delle chiamate internazionali, da una configurazione errata del routing o da un server multimediale di overload. Gli alti tempi di andata e ritorno si verificano in difficoltà con le conversazioni audio in tempo reale a due vie.  <br/> |
|**Degradazione (MOS)** <br/> |Sì  <br/> |Valore medio della degradazione media del Punteggio di opinione (MOS) sperimentato durante una chiamata. I valori di degradazione possono variare da un minimo di 0,0 a un massimo di 5,0. Un valore di 0,5 o meno rappresenta una degradazione accettabile. Storicamente, i punteggi delle opzioni medie sono stati calcolati avendo gli utenti valutano la qualità di una chiamata in una scala da 1 a 5. In Skype for Business Server, un set di algoritmi prevede in che modo gli utenti avrebbero valutato una chiamata.  <br/> I valori di degradazione elevati possono essere causati dalla congestione, dalla mancanza di larghezza di banda, dalla congestione wireless o dall'interferenza o da un server multimediale o un endpoint di overload. L'elevata degradazione genera un audio distorta o perso.  <br/> |
|**Perdita di pacchetti** <br/> |Sì  <br/> |Tasso medio di perdita di pacchetti RTP. La perdita di pacchetti si verifica quando i pacchetti RTP, un protocollo usato per la trasmissione di audio e video su Internet, non riescono a raggiungere la destinazione. I tassi di perdita elevati sono in genere causati dalla congestione, dalla mancanza di larghezza di banda, dalla congestione wireless o dall'interferenza o da un server multimediale sovraccaricato. La perdita di pacchetti in genere genera un audio distorta o perso.  <br/> |
|**Jitter** <br/> |Sì  <br/> |Jitter medio rilevato tra gli arrivi del pacchetto RTP. (Jitter è una misura della "shakiness" di una chiamata). I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o perse.  <br/> |
|**Rapporto nascosto del guaritore** <br/> |Sì  <br/> |Rapporto media tra campioni audio nascosti e il totale al numero totale di esempi. (Un esempio di audio nascosto è una tecnica usata per attenuare la transizione brusca che in genere viene causata da pacchetti di rete eliminati). I valori elevati indicano livelli significativi di occultamento delle perdite applicati a causa di perdita di pacchetti o jitter e generano audio distorte o perse.  <br/> |
|**Rapporto allungato guaritore** <br/> |Sì  <br/> |Rapporto medio tra campioni audio allungati e il totale al numero totale di esempi. (L'audio allungato è l'audio che è stato espanso per mantenere la qualità delle chiamate quando è stato rilevato un pacchetto di rete scartato). I valori alti indicano livelli significativi di stretching dei campioni causati da jitter e generano audio o distorte.  <br/> |
|**Rapporto compresso del guaritore** <br/> |Sì  <br/> |Rapporto medio tra campioni audio compressi e il numero totale di esempi. (L'audio compresso è un audio compresso che consente di mantenere la qualità delle chiamate quando è stato rilevato un pacchetto di rete scartato). I valori alti indicano livelli significativi di compressione dei campioni causati da jitter e generano un suono accelerato o distorta.  <br/> |
|**Connettività** <br/> |Sì  <br/> | Tipo di collegamento di comunicazione wireless. In genere, questa è una delle opzioni seguenti: <br/>  Inoltro <br/>  Diretto <br/> |
   


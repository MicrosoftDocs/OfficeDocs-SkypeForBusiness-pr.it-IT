---
title: Report sulle prestazioni del server in Skype for Business Server
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
ms.assetid: 942bb39a-1790-498e-9d99-8f6ce2d155c3
description: 'Riepilogo: informazioni sul report sulle prestazioni del server in Skype for Business Server.'
ms.openlocfilehash: fc7e3232e16bd4366ac80f75fb12eca0fb24b4dd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817695"
---
# <a name="server-performance-report-in-skype-for-business-server"></a>Report sulle prestazioni del server in Skype for Business Server
 
**Riepilogo:** Informazioni sul report sulle prestazioni del server in Skype for Business Server.
  
Il report prestazioni server include un elenco di server Skype for Business Server che hanno sperimentato la percentuale più alta di chiamate scadenti. Il report suddivide i server per tipo di server, segnalando statistiche separate per i tipi seguenti:
  
- Mediation Server
    
- A/V Conferencing Server
    
- A/V Edge Server
    
- Gateway (Mediation Server)
    
- Gateway (bypass Mediation Server)
    
- Video (incluse le metriche video per i server di servizi di conferenza A/V e i/V Edge Server)
    
- Condivisione di applicazioni (incluse le metriche di condivisione delle applicazioni per i server di servizi di conferenza A/V e i/V Edge Server)
    
È importante notare che la classificazione mostrata in questo report è come classifica relativa. Supponiamo ad esempio che il server con prestazioni peggiori abbia una chiamata scadente tra le chiamate a 1.000. È una percentuale più che accettabile di 1%. Tuttavia, se questo è il server più performante che hai (ovvero, se tutti gli altri server hanno una percentuale di chiamata scadente anche inferiore a .1%), il server continuerà a essere visualizzato nel report sulle prestazioni del server.
  
## <a name="accessing-the-server-performance-report"></a>Accesso al report sulle prestazioni del server

Il report prestazioni server è accessibile dalla Home page dei report di monitoraggio. È possibile eseguire il drill-down [nel report elenco chiamate in Skype for Business Server](call-list-report-0.md) facendo clic su una delle metriche seguenti:
  
- Volume chiamata
    
- Percentuale di chiamata scadente
    
È inoltre possibile eseguire il drill-down per il report trend qualità media del server facendo clic sulla metrica seguente:
  
- Tendenza
    
## <a name="making-the-best-use-of-the-server-performance-report"></a>Uso ottimale del report sulle prestazioni del server

Il report prestazioni server offre diversi modi per filtrare i dati. ad esempio, è possibile filtrare in base al tipo di rete (chiamate effettuate da una connessione cablata e chiamate effettuate da una connessione wireless) e il tipo di accesso (chiamate effettuate dall'interno del firewall e dalle chiamate effettuate dall'esterno del firewall). È una buona idea quando si Visualizza il report sulle prestazioni del server per usare questi filtri. Supponiamo ad esempio di avere un Mediation Server con una percentuale di chiamata scadente pari a 3,24%. Se si osservano solo le chiamate wireless, lo stesso server potrebbe avere una percentuale di chiamata scadente che si avvicina al 20%. Ciò significa che il server ha avuto difficoltà con le chiamate wireless, un problema parzialmente oscurato perché il server non aveva problemi con le chiamate cablate.
  
## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Il report sulle prestazioni del server, ad esempio, consente di eseguire operazioni come filtrare i dati restituiti per tipo di server o per tipo di rete (cablata o wireless). È anche possibile scegliere la modalità di raggruppamento dei dati. In questo caso, i dati vengono raggruppati per ora, giorno, settimana o mese.
  
Nella tabella seguente sono elencati i filtri che è possibile usare con il report prestazioni server.
  
**Filtri dei report sulle prestazioni del server**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**Da** <br/> |Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**A** <br/> |Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**Tipo di server** <br/> |Indica il tipo di server di cui devono essere segnalate le prestazioni. Selezionare una delle opzioni seguenti:  <br/> Tutti Mediation Server A/V Conferencing Server A/V Edge Server |
|**Inizio N** <br/> |Indica il numero di server (in base alla percentuale di chiamate) da visualizzare in ogni categoria. Ad esempio, se si seleziona **5** , vengono visualizzati i cinque server con prestazioni più scarse. Selezionare una delle opzioni seguenti: <br/> [Tutti] 5 10 |
|**Tipo di accesso** <br/> |Indica se il client ha effettuato l'accesso alla rete interna o alla rete esterna quando è stata inserita la chiamata. Selezionare una delle opzioni seguenti:  <br/> Tutti Interni esterni |
|**Tipo di rete** <br/> |Indica il tipo di rete a cui il client è connesso quando è stata inserita la chiamata. Selezionare una delle opzioni seguenti:  <br/> Tutti Wireless cablata |
|**VPN** <br/> |Indica se un client esterno usa una connessione VPN (Virtual Private Network) quando la chiamata è stata inserita. Selezionare una delle opzioni seguenti:  <br/> Tutti VPN non VPN |
   
## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni fornite nel report sulle prestazioni del server.
  
**Metriche del report sulle prestazioni del server: riepilogo delle chiamate audio**

|**Nome**|**Può ordinare in base a**|**Descrizione**|
|:-----|:-----|:-----|
|**Server** <br/> |No  <br/> |Nome/indirizzo IP del server.  <br/> |
|**Volume chiamata** <br/> |No  <br/> |Numero totale di chiamate effettuate.  <br/> |
|**Percentuale di chiamata scadente** <br/> |No  <br/> |Numero totale di chiamate classificate come scadenti. Una chiamata scadente è una chiamata che almeno una delle metriche misurate ha superato il valore consentito, ad esempio una chiamata con un eccessivo jitter.  <br/> |
|**Andata e ritorno (MS)** <br/> |Sì  <br/> |Importo medio (in millisecondi) richiesto per un pacchetto RTP (Real-Time Transport Protocol) per spostarsi in un altro endpoint e quindi viceversa. I tempi di andata e ritorno di 100 millisecondi sono considerati di qualità accettabile.  <br/> I valori alti di andata e ritorno possono essere causati da routing delle chiamate internazionali; una configurazione errata di routing; o un server multimediale in overload. Gli alti tempi di andata e ritorno si verificano in difficoltà con le conversazioni audio in tempo reale a due vie.  <br/> |
|**Degradazione (MOS)** <br/> |Sì  <br/> |Valore medio della degradazione media del Punteggio di opinione (MOS) sperimentato durante una chiamata. I valori di degradazione possono variare da un minimo di 0,0 a un massimo di 5,0. Un valore di 0,5 o meno rappresenta una degradazione accettabile. Storicamente, i punteggi delle opzioni medie sono stati calcolati avendo gli utenti valutano la qualità di una chiamata in una scala da 1 a 5. In Skype for Business Server, il server di monitoraggio usa un set di algoritmi per prevedere in che modo gli utenti avrebbero valutato una chiamata.  <br/> I valori di degradazione elevati possono essere causati dalla congestione, dalla mancanza di larghezza di banda, dalla congestione wireless o dall'interferenza o da un server multimediale o un endpoint di overload. L'elevata degradazione genera un audio distorta o perso.  <br/> |
|**Perdita di pacchetti** <br/> |Sì  <br/> |Tasso medio di perdita di pacchetti RTP (Real-Time Transport Protocol). La perdita di pacchetti si verifica quando i pacchetti RTP, un protocollo usato per la trasmissione di audio e video su Internet, non riescono a raggiungere la destinazione. I tassi di perdita elevati sono in genere causati dalla congestione, dalla mancanza di larghezza di banda, dalla congestione wireless o dall'interferenza o da un server multimediale sovraccaricato. La perdita di pacchetti in genere genera un audio distorta o perso.  <br/> |
|**Jitter (MS)** <br/> |Sì  <br/> |Jitter medio rilevato tra gli arrivi del pacchetto RTP. (Jitter è una misura della "shakiness" di una chiamata). I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o perse.  <br/> |
|**Rapporto nascosto del guaritore** <br/> |Sì  <br/> |Rapporto media tra campioni audio nascosti e il totale al numero totale di esempi. (Un esempio di audio nascosto è una tecnica usata per attenuare la transizione brusca che in genere viene causata da pacchetti di rete eliminati). I valori elevati indicano livelli significativi di occultamento delle perdite applicati a causa di perdita di pacchetti o jitter e generano audio distorte o perse.  <br/> |
|**Rapporto allungato guaritore** <br/> |Sì  <br/> |Rapporto medio tra campioni audio allungati e il totale al numero totale di esempi. (L'audio allungato è l'audio che è stato espanso per mantenere la qualità delle chiamate quando è stato rilevato un pacchetto di rete scartato). I valori alti indicano livelli significativi di stretching dei campioni causati da jitter e generano audio o distorte.  <br/> |
|**Rapporto compresso del guaritore** <br/> |Sì  <br/> |Rapporto medio tra campioni audio compressi e il numero totale di esempi. (L'audio compresso è un audio compresso che consente di mantenere la qualità delle chiamate quando è stato rilevato un pacchetto di rete scartato). I valori alti indicano livelli significativi di compressione dei campioni causati da jitter e generano un suono accelerato o distorta.  <br/> |
   
**Metriche dei report sulle prestazioni del server: riepilogo videochiamata**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Tipo di chiamata/tipo di endpoint** <br/> |No  <br/> | Quando si fa clic su questo elemento, nel report vengono visualizzate informazioni dettagliate sulle chiamate basate su tale tipo. I tipi di chiamata includono: <br/>  Chiamate peer-to-peer UC <br/>  Sessioni di conferenza UC <br/>  Sessioni di conferenza PSTN <br/>  Chiamate PSTN: bypass multimediale <br/>  Chiamate PSTN (non bypass): Leg UC <br/>  Chiamate PSTN (non bypass): Leg gateway <br/>  Altri tipi di chiamata <br/> |
|**Volume chiamata** <br/> |No  <br/> |Numero totale di chiamate per tipo di chiamata.  <br/> |
|**Percentuale di chiamata scadente** <br/> |No  <br/> |Numero totale di chiamate classificate come scadenti. Una chiamata scadente è una chiamata che almeno una delle metriche misurate ha superato il valore consentito, ad esempio una chiamata con un eccessivo jitter.  <br/> |
|**Volume chiamata (chiamata wireless)** <br/> |No  <br/> |Numero totale di chiamate che hanno usato una connessione wireless.  <br/> |
|**Volume chiamata (chiamata VPN)** <br/> |No  <br/> |Numero totale di chiamate che hanno usato una connessione VPN.  <br/> |
|**Volume chiamata (chiamata esterna)** <br/> |No  <br/> |Numero di chiamate che hanno usato una connessione esterna (ovvero una connessione esterna alla rete interna).  <br/> |
|**Velocità di bit AVG (kbit/s)** <br/> |No  <br/> |Velocità in bit video media (in kilobit al secondo).  <br/> |
|**Percentuale di bit bassa** <br/> |No  <br/> |Percentuale della chiamata in cui il bit rate è basso.  <br/> |
|**Perdita di pacchetti in uscita** <br/> |No  <br/> |Perdita di pacchetti RTP (Real-Time Transport Protocol) per pacchetti in uscita. La perdita di pacchetti si verifica quando i pacchetti RTP, un protocollo usato per la trasmissione di audio e video su Internet, non riescono a raggiungere la destinazione. I tassi di perdita elevati sono in genere causati dalla congestione; mancanza di larghezza di banda; congestione o interferenza wireless; o un server multimediale in overload. La perdita di pacchetti in genere genera un audio distorta o perso.  <br/> |
|**Fotogramma congelato%** <br/> |No  <br/> |Percentuale di fotogrammi "bloccati". In un fotogramma bloccato il video smette di avanzare mentre la parte audio della chiamata continua.  <br/> |
|**Frequenza fotogrammi in uscita AVG** <br/> |No  <br/> |Frequenza fotogrammi media per le trasmissioni in uscita durante la chiamata.  <br/> |
|**Frequenza fotogrammi in ingresso AVG** <br/> |No  <br/> |Frequenza fotogrammi media per le trasmissioni in arrivo durante la chiamata.  <br/> |
|**Frequenza fotogrammi ridotta in ingresso%** <br/> |No  <br/> |Percentuale della chiamata in cui la velocità in bit per il video in arrivo è bassa.  <br/> |
|**Integrità client%** <br/> ||Indica l'integrità relativa del dispositivo client durante la chiamata.  <br/> |
   
**Metriche del report sulle prestazioni del server: riepilogo delle chiamate di condivisione applicazioni**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Tipo di chiamata/tipo di endpoint** <br/> |No  <br/> | Quando si fa clic su questo elemento, nel report vengono visualizzate informazioni dettagliate sulle chiamate basate su tale tipo. I tipi di chiamata includono: <br/>  Chiamate peer-to-peer UC <br/>  Sessioni di conferenza UC <br/>  Sessioni di conferenza PSTN <br/>  Chiamate PSTN: bypass multimediale <br/>  Chiamate PSTN (non bypass): Leg UC <br/>  Chiamate PSTN (non bypass): Leg gateway <br/>  Altri tipi di chiamata <br/> |
|**Volume chiamata** <br/> |No  <br/> |Numero totale di chiamate per tipo di chiamata.  <br/> |
|**Percentuale di chiamata scadente** <br/> |No  <br/> |Numero totale di chiamate classificate come scadenti. Una chiamata scadente è una chiamata che almeno una delle metriche misurate ha superato il valore consentito, ad esempio una chiamata con un eccessivo jitter.  <br/> |
|**Volume chiamata (chiamata wireless)** <br/> |No  <br/> |Numero totale di chiamate che hanno usato una connessione wireless.  <br/> |
|**Volume chiamata (chiamata VPN)** <br/> |No  <br/> |Numero totale di chiamate che hanno usato una connessione VPN.  <br/> |
|**Volume chiamata (chiamata esterna)** <br/> |No  <br/> |Numero di chiamate che hanno usato una connessione esterna (ovvero una connessione esterna alla rete interna).  <br/> |
|**Jitter (MS)** <br/> |No  <br/> |Jitter medio rilevato tra gli arrivi del pacchetto RTP. (Jitter è una misura della "shakiness" di una chiamata). I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o perse.  <br/> |
|**AVG. un modo relativo** <br/> |No  <br/> |Ritardo unidirezionale relativo medio tra due endpoint multimediali. Si tratta di una misura di latenza single-hop.  <br/> |
|**Latenza di elaborazione del riquadro media RDP** <br/> |No  <br/> |La latenza media di elaborazione dei riquadri RDP nel server dei servizi di conferenza durante la durata della sessione di visualizzazione. Questa metrica non include la latenza della rete. Una media elevata riflette un ritardo maggiore nell'esperienza di visualizzazione. Un server di conferenza di overload può avere ritardi medi più alti.  <br/> |
|**Totale riquadro viziato%** <br/> |No  <br/> |Percentuale totale di riquadri RDP viziati.  <br/> |
   


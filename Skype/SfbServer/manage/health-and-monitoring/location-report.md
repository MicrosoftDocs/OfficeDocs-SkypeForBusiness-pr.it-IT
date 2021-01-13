---
title: Report percorso in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cb2f1551-1e21-4f13-a39d-91f5f9010ccf
description: 'Riepilogo: informazioni sul rapporto percorso in Skype for Business Server.'
ms.openlocfilehash: 4c99b958c4cdf129338b263486dc12adc3ef64a7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827896"
---
# <a name="location-report-in-skype-for-business-server"></a>Report percorso in Skype for Business Server
 
**Riepilogo:** Informazioni sul rapporto località in Skype for Business Server.
  
Nel Rapporto percorsi vengono fornite informazioni sulla metrica di qualità delle chiamate raggruppata per percorso di rete, ovvero per subnet di rete. Se si verificano problemi con le chiamate degli utenti, questo rapporto consente di determinare se i problemi sono diffusi oppure sono circoscritti a un segmento di rete specifico.
  
## <a name="accessing-the-location-report"></a>Accesso al Rapporto percorsi

Il Rapporto percorsi è accessibile dalla home page di Relazioni monitoraggio. È possibile eseguire il drill-down fino al Rapporto Elenco chiamate facendo clic su una delle metriche seguenti:
  
- Volume chiamata
    
- Percentuale chiamate di livello insufficiente
    
## <a name="filters"></a>Filtri

I filtri consentono di restituire un insieme di dati più circoscritto o di visualizzare in modi diversi i dati restituiti. Il Rapporto percorsi, ad esempio, consente di filtrare in base alla posizione dalla quale è stata originata una chiamata o a seconda che la chiamata sia stata effettuata utilizzando una connessione wireless o cablata. È inoltre possibile scegliere la modalità di raggruppamento dei dati. In questo caso, le chiamate vengono raggruppate per ora, giorno, settimana o mese.
  
Nella tabella che segue sono elencati i filtri applicabili al Rapporto percorsi.
  
**Filtri del Rapporto percorsi**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**From** <br/> |Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**To** <br/> |Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**Località chiamante** <br/> |Subnet IP dell'utente che ha effettuato la chiamata. È possibile selezionare solo l'opzione **[Tutto]** per indicare tutte le subnet.<br/> |
|**Località destinatario chiamata** <br/> |Subnet IP dell'utente che ha ricevuto la chiamata. È possibile selezionare solo l'opzione **[Tutto]** per indicare tutte le subnet.<br/> |
|**Tipo di rete** <br/> | Indica il tipo di rete alla quale era connesso il client quando è stata effettuata la chiamata. Selezionare una delle opzioni seguenti: <br/>  Tutti <br/>  Cablata <br/>  Wireless <br/> |
|**VPN** <br/> | Indica se un client esterno stava utilizzando una connessione VPN (Virtual Private Network) al momento della chiamata. Selezionare una delle opzioni seguenti: <br/>  Tutti <br/>  VPN <br/>  Non VPN <br/> |
   
## <a name="metrics"></a>Metriche

Nella tabella che segue sono elencate le informazioni fornite nel Rapporto percorsi.
  
**Metriche del Rapporto percorsi**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Subnet chiamante** <br/> |No  <br/> |Subnet IP dell'utente che ha effettuato la chiamata.  <br/> |
|**Subnet destinatario chiamata** <br/> |No  <br/> |Subnet IP dell'utente che ha ricevuto la chiamata.  <br/> |
|**Volume chiamata** <br/> |Sì  <br/> |Numero totale di chiamate effettuate.  <br/> |
|**Percentuale chiamate di livello insufficiente** <br/> |Sì  <br/> |Percentuale delle chiamate classificate come insufficienti. Una chiamata insufficiente è una chiamata per la quale almeno una delle metriche misurate ha superato il valore consentito, ad esempio una chiamata con un'instabilità eccessiva.  <br/> |
|**Roundtrip (ms)** <br/> |Sì  <br/> |Tempo medio di roundtrip (in millisecondi) richiesto per il viaggio di andata e ritorno di un pacchetto RTP (Real-Time Transport Protocol) verso e da un altro endpoint. I roundtrip che non superano i 100 millisecondi vengono considerati accettabili.  <br/> Valori di roundtrip elevati possono essere causati dal routing di chiamate internazionali, da una configurazione errata del routing o da un server di contenuti multimediali sovraccarico. Tempi di roundtrip elevati generano difficoltà nelle conversazioni audio in tempo reale bidirezionali.  <br/> |
|**Degradazione (MOS)** <br/> |Sì  <br/> |Valore medio di degradazione MOS (Mean Opinion Score) osservata durante una chiamata. I valori di degradazione possono essere compresi tra un minimo di 0 e un massimo di 5. Il valore 0,5 o inferiore rappresenta una degradazione accettabile. In passato, i valori MOS venivano calcolati chiedendo agli utenti di valutare la qualità di una chiamata su una scala da 1 a 5. In Skype for Business Server, un insieme di algoritmi prevedono come gli utenti avrebbero valutato una chiamata.  <br/> Valori di degradazione elevati possono essere causati da congestione, mancanza di larghezza di banda, interferenze o congestione della rete wireless o da un endpoint o un server di contenuti multimediali sovraccarico. Una degradazione elevata genera audio distorto o perdita di audio.  <br/> |
|**Perdita di pacchetti** <br/> |Sì  <br/> |Frequenza media di perdita di pacchetti RTP. La perdita di pacchetti si verifica quando i pacchetti RTP, ovvero un protocollo utilizzato per la trasmissione audio e video su Internet, non riescono a raggiungere la destinazione. Frequenze di perdita elevate sono in genere causate da congestione, mancanza di larghezza di banda, interferenze o congestione della rete wireless o da un server di contenuti multimediali sovraccarico. La perdita di pacchetti di solito genera audio distorto o perdita di audio.  <br/> |
|**Instabilità** <br/> |Sì  <br/> |Instabilità media rilevata tra gli arrivi di pacchetti RTP. L'instabilità è una misura dell'inattendibilità di una chiamata. Valori elevati di instabilità sono in genere causati da congestione o da un server di contenuti multimediali sovraccarico e generano audio distorto o perdita di audio.  <br/> |
|**Rapporto campioni nascosti utilità di ripristino** <br/> |Sì  <br/> |Rapporto medio tra i campioni audio nascosti e il numero totale di campioni. Un campione audio nascosto è una tecnica utilizzata per mitigare le transazioni improvvise generalmente causate dall'eliminazione di pacchetti di rete. Valori elevati indicano l'applicazione di livelli significativi di soppressione della perdita applicata dovuti a perdita di pacchetti o instabilità, con conseguente audio distorto o perdita di audio.  <br/> |
|**Rapporto campioni estesi utilità di ripristino** <br/> |Sì  <br/> |Rapporto medio tra i campioni audio estesi e il numero totale di campioni. Con audio esteso si intende l'audio che è stato espanso per garantire la qualità delle chiamate quando viene rilevato un pacchetto di rete eliminato. Valori elevati indicano livelli significativi di estensione dei campioni dovuti a instabilità, con conseguente riproduzione di audio robotico o distorto.  <br/> |
|**Rapporto campioni compressi utilità di ripristino** <br/> |Sì  <br/> |Rapporto medio tra i campioni audio compressi e il numero totale di campioni. L'audio compresso è audio che è stato compresso per mantenere la qualità della chiamata quando è stato rilevato un pacchetto di rete eliminato. Valori alti indicano livelli significativi di compressione dei campioni dovuti a instabilità con conseguente riproduzione di audio accelerato o distorto.  <br/> |
   


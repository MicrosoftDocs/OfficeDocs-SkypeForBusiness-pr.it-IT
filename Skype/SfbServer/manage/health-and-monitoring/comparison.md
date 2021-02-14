---
title: Rapporto di confronto qualità multimediale in Skype for Business Server
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
ms.assetid: c1d0b5a8-98ff-455a-b78b-a05a21cf066d
description: 'Riepilogo: informazioni sul Rapporto di confronto qualità multimediale in Skype for Business Server.'
ms.openlocfilehash: bb8a14ae9685e53ed2441201b25449bdde3f9b0c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817056"
---
# <a name="media-quality-comparison-report-in-skype-for-business-server"></a>Rapporto di confronto qualità multimediale in Skype for Business Server
 
**Riepilogo:** Informazioni sul Rapporto di confronto qualità multimediale in Skype for Business Server.
  
Il Rapporto di confronto qualità multimediale consente di confrontare i valori di qualità delle chiamate per diversi tipi di chiamate audio, ad esempio le chiamate effettuate su rete wireless rispetto alle chiamate effettuate su connessione cablata.
  
## <a name="accessing-the-media-quality-comparison-report"></a>Accesso al Rapporto di confronto qualità multimediale

È possibile accedere al Rapporto di confronto qualità multimediale dalla home page dei rapporti di monitoraggio. 
  
## <a name="filters"></a>Filtri

I filtri consentono di restituire un insieme di dati più circoscritto o di visualizzare in modi diversi i dati restituiti. Nella tabella riportata di seguito vengono elencati i filtri che è possibile utilizzare con il Rapporto di confronto qualità multimediale.
  
**Filtri del Rapporto di confronto qualità multimediale**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**From** <br/> |Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:  <br/> 07/07/2015 13.00  <br/> Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**To** <br/> |Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:  <br/> 07/07/2015 13.00  <br/> Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**Chiamate** <br/> | Tipo di chiamata da utilizzare come elemento principale del confronto. I valori consentiti sono: <br/>  [All] <br/>  Esterno <br/>  Interno <br/>  VPN <br/>  Non VPN <br/>  Cablata <br/>  Wireless <br/>  Esterne e cablate <br/>  Esterne e wireless <br/>  Esterne e VPN <br/>  Esterne e non VPN <br/>  Interne e cablate <br/>  Interne e wireless <br/> |
|**Confronto con le chiamate** <br/> | Tipo di chiamata da utilizzare come elemento secondario del confronto. I valori consentiti sono: <br/>  [All] <br/>  Esterno <br/>  Interno <br/>  VPN <br/>  Non VPN <br/>  Cablata <br/>  Wireless <br/>  Esterne e cablate <br/>  Esterne e wireless <br/>  Esterne e VPN <br/>  Esterne e non VPN <br/>  Interne e cablate <br/>  Interne e wireless <br/> |
|**Interval** <br/> | Selezionare uno dei seguenti: <br/>  Orario (è possibile visualizzare un massimo di 25 ore) <br/>  Giornaliero (è possibile visualizzare un massimo di 31 giorni) <br/>  Settimanale (è possibile visualizzare un massimo di 12 settimane) <br/>  Se per le date di inizio e di fine si immette un numero di valori superiore al massimo consentito per l'intervallo selezionato, verrà visualizzato solo il numero massimo di valori (a partire dalla data di inizio). Ad esempio, se si seleziona l'intervallo giornaliero con data di inizio 7/7/2015 e data di fine 28/02/2015, i dati verranno visualizzati per i giorni 07/08/2015 12.00 al 7/09/2015 12.00 (ovvero un totale di 31 giorni di dati). <br/> |
   
## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni disponibili nel Rapporto di confronto qualità multimediale.
  
**Metriche del Rapporto di confronto qualità multimediale**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Volume chiamata** <br/> |No  <br/> |Numero totale di chiamate  <br/> |
|**Degradazione (MOS)** <br/> |No  <br/> |Quantità media di degradazione MOS (mean opinion score) riscontrata durante una chiamata. I valori di degradazione possono variare da un valore basso di 0,0 a un valore alto di 5,0. un valore pari o inferiore a 0,5 rappresenta una degradazione accettabile. I punteggi di opinione medi sono stati calcolati in base al fatto che gli utenti valutano la qualità di una chiamata su una scala da 1 a 5. Skype for Business Server usa un set di algoritmi per prevedere come gli utenti avrebbero valutato una chiamata.  <br/> Valori di degradazione elevati possono essere causati da congestione, mancanza di larghezza di banda, interferenze o congestione della rete wireless o da un endpoint o un server di contenuti multimediali sovraccarico. Una degradazione elevata genera audio distorto o perdita di audio.  <br/> |
|**Percentuale chiamate di livello insufficiente** <br/> |No  <br/> |Numero totale di chiamate classificate come di livello insufficiente. In una chiama di livello insufficiente almeno una delle metriche misurate supera il valore consentito, ad esempio viene rilevato un livello di instabilità eccessivo.  <br/> |
|**Roundtrip (ms)** <br/> |No  <br/> |Tempo medio di roundtrip (in millisecondi) necessario a un pacchetto RTP (Real-Time Transport Protocol) per raggiungere un altro endpoint e quindi tornare indietro. I roundtrip pari o inferiori a 200 millisecondi vengono considerati accettabili.  <br/> Valori alti di tempo di roundtrip possono essere dovuti a routing delle chiamate internazionali, errata configurazione del routing o sovraccarico del server dei contenuti multimediali con conseguenti difficoltà nelle conversazioni audio bidirezionali in tempo reale.  <br/> |
|**Perdita di pacchetti** <br/> |No  <br/> |Frequenza media di perdita di pacchetti RTP (Real-Time Transport Protocol). La perdita di pacchetti si verifica quando i pacchetti RTP, un protocollo utilizzato per la trasmissione di audio e video su Internet, non raggiungono la destinazione. Valori alti di perdita sono in genere dovuti a congestione, superamento della larghezza di banda disponibile, congestione/interferenze wireless o sovraccarico del server dei contenuti multimediali con conseguente audio distorto o perdita di audio.  <br/> |
|**Instabilità (ms)** <br/> |No  <br/> |Instabilità media rilevata tra gli arrivi di pacchetti RTP. L'instabilità è una misura dell'inattendibilità di una chiamata. Valori elevati di instabilità sono in genere causati da congestione o da un server di contenuti multimediali sovraccarico e generano audio distorto o perdita di audio.  <br/> |
|**Rapporto campioni nascosti utilità di ripristino** <br/> |No  <br/> |Rapporto medio tra i campioni audio nascosti e il numero totale di campioni. Un campione audio nascosto è una tecnica utilizzata per mitigare le transazioni improvvise generalmente causate dall'eliminazione di pacchetti di rete. Valori elevati indicano l'applicazione di livelli significativi di soppressione della perdita applicata dovuti a perdita di pacchetti o instabilità, con conseguente audio distorto o perdita di audio.  <br/> |
|**Rapporto campioni estesi utilità di ripristino** <br/> |No  <br/> |Rapporto medio tra i campioni audio estesi e il numero totale di campioni. Con audio esteso si intende l'audio che è stato espanso per garantire la qualità delle chiamate quando viene rilevato un pacchetto di rete eliminato. Valori elevati indicano livelli significativi di estensione dei campioni dovuti a instabilità, con conseguente riproduzione di audio robotico o distorto.  <br/> |
|**Rapporto campioni compressi utilità di ripristino** <br/> |No  <br/> |Rapporto medio tra i campioni audio compressi e il numero totale di campioni. L'audio compresso è audio che è stato compresso per mantenere la qualità della chiamata quando è stato rilevato un pacchetto di rete eliminato. Valori alti indicano livelli significativi di compressione dei campioni dovuti a instabilità con conseguente riproduzione di audio accelerato o distorto.  <br/> |
   


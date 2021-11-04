---
title: Rapporto tendenze qualità multimediale server in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8a51fd13-1487-4632-b5ec-f7ae2abe8ed4
description: 'Riepilogo: informazioni sul Rapporto tendenze qualità multimediale server in Skype for Business Server.'
ms.openlocfilehash: d813e6d0935a24652b99beb4da9b854197ba98dd
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774796"
---
# <a name="server-media-quality-trend-report-in-skype-for-business-server"></a>Rapporto tendenze qualità multimediale server in Skype for Business Server
 
**Riepilogo:** Informazioni sul Rapporto tendenze qualità multimediale server in Skype for Business Server.
  
Il Rapporto tendenze qualità multimediale server consente di confrontare graficamente fino a cinque server nelle metriche di qualità dell'esperienza, ad esempio il volume delle chiamate, la percentuale di chiamate scarsa, la perdita di pacchetti e l'instabilità. Ciò agevola attività quali l'identificazione dei server con prestazioni insufficienti, sottoutilizzati o sovrautilizzati.
  
## <a name="accessing-the-server-media-quality-trend-report"></a>Accesso al Rapporto tendenze qualità multimediale server

Il Rapporto tendenze qualità multimediale server è accessibile da uno o l'altro dei rapporto seguenti:
  
- [Rapporto prestazioni server in Skype for Business Server](server-performance.md) (facendo clic sulla metrica Tendenza)
    
- [Call Detail Report in Skype for Business Server](call-detail-report.md) (facendo clic sulla metrica del server perimetrale A/V. Se il chiamante o il chiamato è un server, è anche possibile raggiungere il Rapporto tendenze multimediali qualità server facendo clic sul nome dell'endpoint.
    
## <a name="making-the-best-use-of-server-media-quality-trend-report"></a>Uso ottimale del Rapporto tendenze qualità multimediale server

Quando si fa clic sulla metrica Tendenza nel Rapporto prestazioni server [in Skype for Business Server](server-performance.md) per un server specifico, verrà aperto il Rapporto tendenze qualità multimediale server. Tuttavia, verrà visualizzata solo un'istanza vuota del rapporto; il server selezionato nel Rapporto prestazioni dei server non verrà visualizzato. Sarà invece necessario selezionare il server dal menu a discesa Server. Tenere presente che l'elenco a discesa Server include anche un'opzione Seleziona tutto. Questa opzione non funziona se sono presenti più di 5 server; il Rapporto tendenze qualità multimediale server è in grado di visualizzare dati per un massimo di 5 server alla volta.
  
Nei grafici visualizzati dal Rapporto tendenze qualità multimediale server, i punti contrassegnati come Volume chiamate e Percentuale chiamate scarsa sono collegamenti a caldo; Se si fa clic su un punto nel grafico, verrà aperta un'istanza del Rapporto elenco chiamate [in Skype for Business Server](call-list-report-0.md) che mostra il numero totale di chiamate (o chiamate di qualità scarsa) per il periodo di tempo specificato.
  
## <a name="filters"></a>Filtri

I filtri consentono di restituire un insieme di dati più circoscritto o di visualizzare in modi diversi i dati restituiti. Nella tabella riportata di seguito vengono elencati i filtri che è possibile utilizzare con il Rapporto tendenze qualità multimediale server.
  
**Filtri del Rapporto tendenze qualità multimediale server**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**From** <br/> |Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:  <br/> 07/07/2015 13.00  <br/> Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**To** <br/> |Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:  <br/> 07/07/2015 13.00  <br/> Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**Interval** <br/> | Selezionare uno dei seguenti: <br/>  Orario (è possibile visualizzare un massimo di 25 ore) <br/>  Giornaliero (è possibile visualizzare un massimo di 31 giorni) <br/>  Settimanale (è possibile visualizzare un massimo di 12 settimane) <br/>  Se per le date di inizio e di fine si immette un numero di valori superiore al massimo consentito per l'intervallo selezionato, verrà visualizzato solo il numero massimo di valori (a partire dalla data di inizio). Ad esempio, se si seleziona l'intervallo giornaliero con una data di inizio 07/08/2015 e una data di fine del 28/09/2015, verranno visualizzati i dati relativi ai giorni 07/08/2015 12.00 alle 07.00.00 del 9/07/2015 (ovvero un totale di 31 giorni di dati). <br/> |
|**Tipo di server** <br/> | Tipo di server coinvolto nella chiamata. Valori consentiti: <br/>  Mediation Server <br/>  A/V Conferencing Server <br/>  A/V Edge Server <br/>  Gateway (Mediation Server) <br/>  Gateway (bypass a Mediation Server) <br/>  AS Conferencing Server <br/> |
|**Server** <br/> |Nome del server coinvolto nella sessione; questo elenco a discesa viene automaticamente popolato in base al valore del filtro Tipo di server. È possibile selezionare fino a 5 diversi server per la compilazione di un rapporto.  <br/> |
|**Tipo di accesso** <br/> | Indica se il partecipante era connesso alla rete interna o dalla rete esterna. Valori consenti: <br/>  [All] <br/>  Interno <br/>  Esterno <br/> |
|**Tipo di rete** <br/> | Indica il tipo di rete a cui era connesso il partecipante. Valori consentiti: <br/>  [All] <br/>  Cablata <br/>  Wireless <br/> |
|**VPN** <br/> | Indica se un partecipante esterno utilizzava una connessione di rete privata virtuale (VPN) durante la sessione. Valori consentiti: <br/>  [All] <br/>  VPN <br/>  Non VPN <br/> |
   
## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni disponibili nel Rapporto tendenze qualità multimediale server.
  
**Metriche del Rapporto tendenze qualità multimediale server**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Volume chiamata** <br/> |No  <br/> |Numero totale di chiamate  <br/> |
|**Degradazione (MOS)** <br/> |No  <br/> |Quantità media di degradazione MOS (punteggio medio opzione) riscontrata durante una chiamata. I valori di degradazione possono variare da un valore minimo di 0,0 a un valore elevato di 5,0. un valore pari o inferiore a 0,5 rappresenta una degradazione accettabile. In passato, i valori MOS venivano calcolati chiedendo agli utenti di valutare la qualità di una chiamata su una scala da 1 a 5. Skype for Business Server utilizza un set di algoritmi per prevedere come gli utenti avrebbero valutato una chiamata.  <br/> Valori di degradazione elevati possono essere causati da congestione, mancanza di larghezza di banda, interferenze o congestione della rete wireless o da un endpoint o un server di contenuti multimediali sovraccarico. Una degradazione elevata genera audio distorto o perdita di audio.  <br/> |
|**Percentuale chiamate di livello insufficiente** <br/> |No  <br/> |Numero totale di chiamate classificate come di livello insufficiente. In una chiama di livello insufficiente almeno una delle metriche misurate supera il valore consentito, ad esempio viene rilevato un livello di instabilità eccessivo.  <br/> |
|**Roundtrip (ms)** <br/> |No  <br/> |Tempo medio (in millisecondi) richiesto per il roundtrip di un pacchetto RTP (Real-Time Transport Protocol) verso e da un altro endpoint. I roundtrip che non superano i 200 millisecondi vengono considerati accettabili.  <br/> Valori alti di tempo di roundtrip possono essere dovuti a routing delle chiamate internazionali, errata configurazione del routing o sovraccarico del server dei contenuti multimediali con conseguenti difficoltà nelle conversazioni audio bidirezionali in tempo reale.  <br/> |
|**Perdita di pacchetti** <br/> |No  <br/> |Frequenza media di perdita di pacchetti RTP (Real-Time Transport Protocol). La perdita di pacchetti si verifica quando i pacchetti RTP, un protocollo utilizzato per la trasmissione di audio e video su Internet, non raggiungono la destinazione. Valori alti di perdita sono in genere dovuti a congestione, superamento della larghezza di banda disponibile, congestione/interferenze wireless o sovraccarico del server dei contenuti multimediali con conseguente audio distorto o perdita di audio.  <br/> |
|**Instabilità (ms)** <br/> |No  <br/> |Instabilità media rilevata tra gli arrivi di pacchetti RTP. L'instabilità è una misura dell'inattendibilità di una chiamata. Valori elevati di instabilità sono in genere causati da congestione o da un server di contenuti multimediali sovraccarico e generano audio distorto o perdita di audio.  <br/> |
|**Rapporto campioni nascosti utilità di ripristino** <br/> |No  <br/> |Rapporto medio tra i campioni audio nascosti e il numero totale di campioni. Un campione audio nascosto è una tecnica utilizzata per mitigare le transazioni improvvise generalmente causate dall'eliminazione di pacchetti di rete. Valori elevati indicano l'applicazione di livelli significativi di soppressione della perdita applicata dovuti a perdita di pacchetti o instabilità, con conseguente audio distorto o perdita di audio.  <br/> |
|**Rapporto campioni estesi utilità di ripristino** <br/> |No  <br/> |Rapporto medio tra i campioni audio estesi e il numero totale di campioni. Con audio esteso si intende l'audio che è stato espanso per garantire la qualità delle chiamate quando viene rilevato un pacchetto di rete eliminato. Valori elevati indicano livelli significativi di estensione dei campioni dovuti a instabilità, con conseguente riproduzione di audio robotico o distorto.  <br/> |
|**Rapporto campioni compressi utilità di ripristino** <br/> |No  <br/> |Rapporto medio tra i campioni audio compressi e il numero totale di campioni. L'audio compresso è audio che è stato compresso per mantenere la qualità della chiamata quando è stato rilevato un pacchetto di rete eliminato. Valori alti indicano livelli significativi di compressione dei campioni dovuti a instabilità con conseguente riproduzione di audio accelerato o distorto.  <br/> |
   


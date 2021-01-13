---
title: Rapporto elenco chiamate in Skype for Business Server
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
ms.assetid: 9739f9f0-7a37-4844-91d5-f089d2011013
description: 'Riepilogo: informazioni sul rapporto elenco chiamate utilizzato in Skype for Business Server.'
ms.openlocfilehash: 8deb14cc8d2b8ff4b47701502de414d7460a81ef
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817076"
---
# <a name="call-list-report-in-skype-for-business-server"></a>Rapporto elenco chiamate in Skype for Business Server
 
**Riepilogo:** Informazioni sul rapporto elenco chiamate utilizzato in Skype for Business Server.
  
Il rapporto Elenco chiamate offre metriche QoE (Quality of Experience) per le singole chiamate effettuate e ricevute nell'organizzazione. Tenere presente che le metriche effettive riportate dipendono dalla modalità di accesso al rapporto Elenco chiamate. Ad esempio, se si apre il report del rapporto del [dispositivo in Skype for Business Server](device-report.md), vengono visualizzate le metriche, quali le metriche seguenti, che sono state segnalate anche nel rapporto dispositivo:
  
- Microfono del chiamante
    
- Altoparlante del chiamante
    
- Microfono del chiamato
    
- Altoparlante del chiamato
    
- Rapporto di tempo commutazione vocale 
    
Tuttavia, se si apre il rapporto elenco chiamate dal [rapporto percorso in Skype for Business Server](location-report.md), non verrà visualizzata alcuna di queste metriche. si vedranno invece metriche come queste:
  
- Roundtrip (ms)
    
- Degradazione (MOS)
    
- Perdita di pacchetti
    
- Instabilità (ms)
    
Si tratta delle metriche riportate nel Rapporto percorsi. Tuttavia, nel rapporto Elenco chiamate è sempre possibile fare clic sulla metrica Dettagli per ottenere informazioni di QoE complete per qualsiasi chiamata.
  
## <a name="accessing-the-call-list-report"></a>Accesso al rapporto Elenco chiamate

Il rapporto Elenco chiamate è accessibile da qualsiasi dei rapporti seguenti:
  
- Il [rapporto percorso in Skype for Business Server](location-report.md) (facendo clic sulla metrica volume chiamata o percentuale di chiamate insufficienti)
    
- Il [rapporto del dispositivo in Skype for Business Server](device-report.md) (facendo clic sulla metrica volume chiamata o percentuale di chiamate insufficienti)
    
- Il [rapporto riepilogativo sulla qualità multimediale in Skype for Business Server](summary.md) (facendo clic sulla metrica volume chiamata o percentuale chiamate insufficienti)
    
- Il [rapporto prestazioni server in Skype for Business Server](server-performance.md) (facendo clic sulla metrica volume chiamata o percentuale di chiamate insufficienti)
    
Dall'interno del rapporto elenco chiamate è possibile accedere al [rapporto dettagli chiamata in Skype for Business Server](call-detail-report.md) facendo clic sulla metrica Dettagli.
  
## <a name="making-the-best-use-of-the-call-list-report"></a>Uso ottimale del rapporto Elenco chiamate

Se non si è certi del tipo di misurazioni offerte dalle metriche del rapporto Elenco chiamate (ad esempio il rapporto di tempo di commutazione vocale), tenere il puntatore del mouse sull'etichetta per visualizzare una descrizione comandi con informazioni sintetiche sulla metrica in questione.
  
## <a name="filters"></a>Filtri

Nessuno. Non è possibile filtrare il rapporto Elenco chiamate.
  
## <a name="metrics"></a>Metriche

La tabella seguente elenca le informazioni disponibili nel rapporto Elenco chiamate per ogni chiamata.
  
**Metriche del rapporto Elenco chiamate**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Dettagli** <br/> |No  <br/> |Facendo clic su questo elemento è possibile visualizzare ulteriori informazioni sulla chiamata.  <br/> |
|**Chiamante** <br/> |Sì  <br/> |Indirizzo SIP dell'utente che ha avviato la chiamata.  <br/> |
|**Destinatario chiamata** <br/> |Sì  <br/> |Indirizzo SIP dell'utente chiamato.  <br/> |
|**Ora inizio** <br/> |Sì  <br/> |Data e ora di inizio della chiamata.  <br/> |
|**Ora fine** <br/> |Sì  <br/> |Data e ora di fine della chiamata.  <br/> |
|**Agente utente chiamante** <br/> |Sì  <br/> |Software utilizzato dall'endpoint dell'utente che ha avviato la chiamata.  <br/> |
|**Agente utente destinatario chiamata** <br/> |Sì  <br/> |Software utilizzato dall'endpoint dell'utente che è stato chiamato.  <br/> |
|**Roundtrip (ms)** <br/> |Sì  <br/> |Tempo medio di roundtrip (in millisecondi) richiesto per il viaggio di andata e ritorno di un pacchetto RTP (Real-Time Transport Protocol) verso e da un altro endpoint. I roundtrip che non superano i 100 millisecondi vengono considerati accettabili.  <br/> Valori di roundtrip elevati possono essere causati dal routing di chiamate internazionali, da una configurazione errata del routing o da un server di contenuti multimediali sovraccarico. Tempi di roundtrip elevati generano difficoltà nelle conversazioni audio in tempo reale bidirezionali.  <br/> |
|**Degradazione (MOS)** <br/> |Sì  <br/> |Valore medio di degradazione MOS (Mean Opinion Score) osservata durante una chiamata. I valori di degradazione possono essere compresi tra un minimo di 0 e un massimo di 5. Il valore 0,5 o inferiore rappresenta una degradazione accettabile. In passato, i valori MOS venivano calcolati chiedendo agli utenti di valutare la qualità di una chiamata su una scala da 1 a 5. In Skype for Business Server, un insieme di algoritmi prevedono come gli utenti avrebbero valutato una chiamata.  <br/> Valori di degradazione elevati possono essere causati da congestione, mancanza di larghezza di banda, interferenze o congestione della rete wireless o da un endpoint o un server di contenuti multimediali sovraccarico. Una degradazione elevata genera audio distorto o perdita di audio.  <br/> |
|**Perdita di pacchetti** <br/> |Sì  <br/> |Frequenza media di perdita di pacchetti RTP. La perdita di pacchetti si verifica quando i pacchetti RTP, ovvero un protocollo utilizzato per la trasmissione audio e video su Internet, non riescono a raggiungere la destinazione. Frequenze di perdita elevate sono in genere causate da congestione, mancanza di larghezza di banda, interferenze o congestione della rete wireless o da un server di contenuti multimediali sovraccarico. La perdita di pacchetti di solito genera audio distorto o perdita di audio.  <br/> |
|**Instabilità** <br/> |Sì  <br/> |Instabilità media rilevata tra gli arrivi di pacchetti RTP. L'instabilità è una misura dell'inattendibilità di una chiamata. Valori elevati di instabilità sono in genere causati da congestione o da un server di contenuti multimediali sovraccarico e generano audio distorto o perdita di audio.  <br/> |
|**Rapporto campioni nascosti utilità di ripristino** <br/> |Sì  <br/> |Rapporto medio tra i campioni audio nascosti e il numero totale di campioni. Un campione audio nascosto è una tecnica utilizzata per mitigare le transazioni improvvise generalmente causate dall'eliminazione di pacchetti di rete. Valori elevati indicano l'applicazione di livelli significativi di soppressione della perdita applicata dovuti a perdita di pacchetti o instabilità, con conseguente audio distorto o perdita di audio.  <br/> |
|**Rapporto campioni estesi utilità di ripristino** <br/> |Sì  <br/> |Rapporto medio tra i campioni audio estesi e il numero totale di campioni. Con audio esteso si intende l'audio che è stato espanso per garantire la qualità delle chiamate quando viene rilevato un pacchetto di rete eliminato. Valori elevati indicano livelli significativi di estensione dei campioni dovuti a instabilità, con conseguente riproduzione di audio robotico o distorto.  <br/> |
|**Rapporto campioni compressi utilità di ripristino** <br/> |Sì  <br/> |Rapporto medio tra i campioni audio compressi e il numero totale di campioni. I campioni audio vengono compressi per mantenere la qualità della chiamata quando è stato rilevato un pacchetto di rete eliminato. Valori alti indicano livelli significativi di compressione dei campioni dovuti a instabilità con conseguente riproduzione di audio accelerato o distorto.  <br/> |
|**Connettività** <br/> |Sì  <br/> | Tipo di collegamento di comunicazione wireless. In genere è uno dei seguenti: <br/>  Relè <br/>  Diretto <br/> |
   


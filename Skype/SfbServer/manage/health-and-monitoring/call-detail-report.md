---
title: Report dettagli chiamata in Skype for Business Server
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
ms.assetid: 38862e35-3fec-41b9-a035-0b301942d446
description: 'Riepilogo: informazioni sul report dettagli chiamata usato in Skype for Business Server.'
ms.openlocfilehash: a700bf9969c921db2d36a816579ee36ff59cb3b3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818147"
---
# <a name="call-detail-report-in-skype-for-business-server"></a>Report dettagli chiamata in Skype for Business Server
 
**Riepilogo:** Informazioni sul report dettagli chiamata usato in Skype for Business Server.
  
Il report dettagli chiamata fornisce un'occhiata dettagliata a una singola chiamata; il report include quasi tutta la qualità delle metriche delle esperienze e delle statistiche raccolte da Skype for Business Server, suddivise in sezioni di report come:
  
- Informazioni sulle chiamate 
    
- Metriche del segnale e del dispositivo chiamante
    
- Dispositivo chiamato e metriche del segnale
    
- Evento del client chiamante
    
- Evento client chiamato
    
- Flusso audio (chiamante)
    
- Flusso video (chiamante)
    
- Flusso audio (chiamato dal chiamante)
    
- Flusso video (chiamato dal chiamante)
    
Tieni presente che le categorie e le metriche visualizzate in un report specifico dipendono da due fattori: il tipo di sessione e il tipo di endpoint usati nella sessione. Ad esempio, una chiamata solo audio non riporta le metriche per i flussi video; Questo perché la chiamata non ha un flusso video. Analogamente, è possibile che sia presente un report che elenca le statistiche del chiamante ma non le statistiche chiamate. In genere perché il destinatario non usa un dispositivo conforme a SIP. Gli endpoint sono responsabili della segnalazione delle statistiche alla fine di una chiamata; Tuttavia, un cellulare (che non conosce le statistiche SIP o SIP) non è in grado di segnalare questo tipo di informazioni. Se si chiama qualcuno e si risponde al telefono cellulare, non si riceverà un report dal telefono cellulare al termine della chiamata.
  
Il report dettagli chiamata è molto utile quando si prova a determinare esattamente il motivo per cui una determinata chiamata ha riscontrato problemi di qualità multimediale.
  
## <a name="accessing-the-call-detail-report"></a>Accesso al report dettagli chiamata

È possibile accedere al report dettagli chiamata da uno dei report seguenti:
  
- Il [rapporto posizione in Skype for Business Server (location-report.md) (facendo clic sul volume delle chiamate o sulla metrica della percentuale di chiamata scadente)
    
- [Report Riepilogo qualità multimediale in Skype for Business Server (summary.md) (facendo clic sul volume delle chiamate o sulla metrica della percentuale di chiamata scadente)
    
- [Report di confronto qualità multimediale in Skype for Business Server](comparison.md) (facendo clic sul [report elenco chiamate in Skype for Business Server](call-list-report-0.md) e quindi scegliendo la metrica dettaglio).
    
- [Report sulle prestazioni del server in Skype for Business Server](server-performance.md) (facendo clic sul volume delle chiamate o sulla metrica della percentuale di chiamata scadente)
    
- [Report elenco chiamate in Skype for Business Server](call-list-report-0.md) (facendo clic sulla metrica dettaglio)
    
Dall'interno del report dettagli chiamata è possibile accedere al [report del dispositivo in Skype for Business Server](device-report.md) facendo clic su una delle metriche seguenti:
  
- Dispositivo di acquisizione
    
- Dispositivo di rendering
    
È anche possibile accedere al report trend qualità media del server facendo clic sulla metrica A/V Edge Server.
  
## <a name="making-the-best-use-of-the-call-detail-report"></a>Sfruttare al meglio il report dettagli chiamata

Il report dettagli chiamata in genere include più di 250 metriche diverse, inclusi elementi come la deriva del timestamp del microfono, l'ora bassa di SNR e la fine del tempo di Echo. Se non si riesce a ricordare ciò che tutte queste metriche effettivamente misurano, provare a tenere il mouse sopra l'etichetta metrica; spesso, viene visualizzata una descrizione comando che descrive la metrica.
  
In caso di problemi con l'individuazione di una metrica, digitare parte dell'etichetta metrica nella casella di ricerca e quindi fare clic su **trova**. Ad esempio, se non si riesce a trovare la metrica per l'ora bassa SNR, digitare SNR nella casella di ricerca e quindi fare clic su **trova**.
  
Tieni presente che il report tiene traccia solo delle informazioni su una chiamata. La chiamata stessa non viene registrata.
  
## <a name="filters"></a>Filtri

Nessuno. Non è possibile filtrare il report dettagli chiamata.
  
## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni fornite nel report dettagli chiamata per ogni chiamata.
  
**Metriche report dettagli chiamata**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Chiamante PAI** <br/> |No  <br/> |P-asserzione-identità dell'utente che ha avviato la chiamata. La P-Asserted-Identity viene usata per trasmettere l'identità comprovata di un utente all'interno di una rete attendibile.  <br/> |
|**URI chiamante** <br/> |No  <br/> |Indirizzo SIP dell'utente che ha avviato la chiamata.  <br/> |
|**Endpoint chiamante** <br/> |No  <br/> |Dispositivo usato per effettuare la chiamata.  <br/> |
|**Agente utente chiamante** <br/> |No  <br/> |Software usato nel dispositivo che ha eseguito la chiamata.  <br/> |
|**Inizio chiamata** <br/> |No  <br/> |Data e ora in cui la chiamata è stata inizialmente inserita.  <br/> |
|**Chiamata di bypass di Mediation Server** <br/> |No  <br/> |Indica se la chiamata è connessa a un gateway vocale PSTN o a un IP-PBX qualificato senza passare tramite Mediation Server.  <br/> |
|**Sistema operativo chiamante** <br/> |No  <br/> |Sistema operativo del computer del chiamante.  <br/> |
|**CPU chiamante** <br/> |No  <br/> |CPU installata nel computer dell'utente che ha avviato la chiamata.  <br/> |
|**Numero di core della CPU chiamante** <br/> |No  <br/> |Numero del processore nel computer usato dalla persona che ha avviato la chiamata.  <br/> |
|**Velocità della CPU chiamante** <br/> |No  <br/> |Velocità di clock della CPU del computer usato dalla persona che ha avviato la chiamata.  <br/> |
|**Virtualizzazione della CPU chiamante** <br/> |No  <br/> |Virtualizzazione (se presenti) usata nel computer usato dalla persona che ha avviato la chiamata.  <br/> |
|**Chiamata PAI** <br/> |No  <br/> |P-asserzione-identità dell'utente invitato a partecipare alla chiamata. La P-Asserted-Identity viene usata per trasmettere l'identità comprovata di un utente all'interno di una rete attendibile.  <br/> |
|**URI chiamato** <br/> |No  <br/> |Indirizzo SIP dell'utente che è stato chiamato.  <br/> |
|**Endpoint chiamato** <br/> |No  <br/> |Dispositivo usato per ricevere la chiamata.  <br/> |
|**Agente utente chiamato** <br/> |No  <br/> |Software usato nel dispositivo che ha ricevuto la chiamata.  <br/> |
|**Durata** <br/> |No  <br/> |Intervallo di tempo per la chiamata.  <br/> |
|**Contrassegno di avviso di bypass multimediale** <br/> |No  <br/> |Avviso emesso quando il Mediation Server è stato ignorato.  <br/> |
|**Sistema operativo chiamato** <br/> |No  <br/> |Sistema operativo del computer per l'utente che è stato chiamato.  <br/> |
|**CPU chiamato** <br/> |No  <br/> |CPU installata nel computer dell'utente che è stato chiamato.  <br/> |
|**Numero di nucleo chiamato** <br/> |No  <br/> |Numero del processore nel computer usato dalla persona che è stata chiamata.  <br/> |
|**Velocità della CPU chiamato** <br/> |No  <br/> |Velocità di clock della CPU del computer usato dalla persona che è stata chiamata.  <br/> |
|**Virtualizzazione della CPU chiamato** <br/> |No  <br/> |Virtualizzazione (se presenti) usata nel computer usato dalla persona che è stata chiamata.  <br/> |
   


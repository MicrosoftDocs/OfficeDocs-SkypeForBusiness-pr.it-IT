---
title: Rapporto dettagli chiamata in Skype for Business Server
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
ms.assetid: 38862e35-3fec-41b9-a035-0b301942d446
description: 'Riepilogo: informazioni sul Rapporto dettagli chiamata utilizzato in Skype for Business Server.'
ms.openlocfilehash: 9b02722c8dd872b5703d6b459c2cd48568e39f94
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826516"
---
# <a name="call-detail-report-in-skype-for-business-server"></a>Rapporto dettagli chiamata in Skype for Business Server
 
**Riepilogo:** Informazioni sul Rapporto dettagli chiamata utilizzato in Skype for Business Server.
  
Il Rapporto dettagli chiamata fornisce un'analisi dettagliata di una singola chiamata; il report include quasi tutte le metriche e le statistiche sulla qualità dell'esperienza raccolte da Skype for Business Server, suddivise in sezioni di report come:
  
- Informazioni chiamata 
    
- Metrica dispositivi e segnale chiamante
    
- Metrica dispositivi e segnale destinatario chiamata
    
- Evento client chiamante
    
- Evento client destinatario chiamata
    
- Flusso audio (da chiamante a destinatario chiamata)
    
- Flusso video (da chiamante a destinatario chiamata)
    
- Flusso audio (da destinatario chiamata a chiamante)
    
- Flusso video (da destinatario chiamata a chiamante)
    
Tenere presente che le categorie e le metriche incluse in un rapporto specifico dipendono da due fattori: il tipo di sessione e il tipo di endpoint usato nella sessione. Ad esempio in una chiamata solo audio non saranno presenti metriche per i flussi video, in quanto la chiamata non presenta alcun flusso video. Analogamente, si potrebbe avere un rapporto in cui sono elencate statistiche del chiamante ma non del destinatario della chiamata. Questa situazione si verifica generalmente quando il destinatario della chiamata non usa un dispositivo compatibile con SIP. Gli endpoint sono responsabili della segnalazione delle statistiche alla fine di una chiamata, ma ad esempio un telefono cellulare (che non ha nulla a che vedere con SIP o statistiche SIP) non è in grado di produrre un rapporto su questo tipo di informazioni. Se si chiama qualcuno che risponde dal telefono cellulare, non verrà prodotto alcun rapporto da quel telefono al termine della chiamata.
  
Il Rapporto dettagli chiamata risulta utile soprattutto quando si prova a stabilire in modo preciso la causa dei problemi di qualità multimediale in una chiamata.
  
## <a name="accessing-the-call-detail-report"></a>Accesso al Rapporto dettagli chiamata

Si può accedere al Rapporto dettagli chiamata da uno dei rapporti seguenti:
  
- [Rapporto località in Skype for Business Server (location-report.md) (facendo clic sulla metrica Volume chiamata o Percentuale di chiamate di livello insufficiente)
    
- Il [Rapporto riepilogativo qualità multimediale in Skype for Business Server (summary.md) (facendo clic sulla metrica Volume chiamata o Percentuale di chiamate di livello insufficiente)
    
- Rapporto [di confronto qualità multimediale in Skype for Business Server](comparison.md) (facendo clic sul Rapporto elenco chiamate in Skype for Business [Server](call-list-report-0.md) e quindi sulla metrica Dettagli).
    
- Rapporto [prestazioni server in Skype for Business Server](server-performance.md) (facendo clic sulla metrica Volume chiamata o Percentuale di chiamate di livello insufficiente)
    
- Rapporto [Elenco chiamate in Skype for Business Server](call-list-report-0.md) (facendo clic sulla metrica Dettagli)
    
Dal Rapporto dettagli chiamata è possibile accedere al Rapporto dispositivi [in Skype for Business Server](device-report.md) facendo clic su una delle metriche seguenti:
  
- Dispositivo di acquisizione
    
- Dispositivo di rendering
    
È inoltre possibile accedere al Rapporto tendenze qualità multimediale server facendo clic sulla metrica A/V Edge Server.
  
## <a name="making-the-best-use-of-the-call-detail-report"></a>Utilizzo ottimale del Rapporto dettagli chiamata

Il Rapporto dettagli chiamata include generalmente oltre 250 metriche diverse, tra cui Deviazione timestamp microfono, Tempo rapporto segnale/rumore basso e Tempo rapporto segnale near-end/eco. Se non si ricorda la misura effettiva di tutte queste metriche, provare a posizionare il mouse sull'etichetta della metrica per visualizzare un a descrizione comando della metrica.
  
In caso di problemi durante l'individuazione di una metrica, digitare parte dell'etichetta nella casella di ricerca e quindi fare clic su **Trova.** Ad esempio, se non è possibile trovare la metrica Tempo SNR basso, digitare SNR nella casella di ricerca e quindi fare clic su **Trova.**
  
Si noti che il rapporto tiene traccia solo delle informazioni relative a una chiamata. La chiamata stessa non viene registrata.
  
## <a name="filters"></a>Filtri

Nessuno. Non è possibile applicare filtri nel Rapporto dettagli chiamata.
  
## <a name="metrics"></a>Metriche

Nella tabella riportata di seguito vengono elencate le informazioni fornite nel Rapporto dettagli chiamata per ogni chiamata.
  
**Metrica del Rapporto dettagli chiamata**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**PAI chiamante** <br/> |No  <br/> |PAI (P-Asserted-Identity) dell'utente che ha avviato la chiamata. Questo valore viene utilizzato per trasmettere l'identità comprovata di un utente in una rete attendibile.  <br/> |
|**URI chiamante** <br/> |No  <br/> |Indirizzo SIP dell'utente che ha avviato la chiamata.  <br/> |
|**Endpoint chiamante** <br/> |No  <br/> |Dispositivo utilizzato per effettuare la chiamata.  <br/> |
|**Agente utente chiamante** <br/> |No  <br/> |Software utilizzato nel dispositivo con cui è stata effettuata la chiamata.  <br/> |
|**Inizio chiamata** <br/> |No  <br/> |Data e ora di inizio della chiamata.  <br/> |
|**Chiamata di bypass a Mediation Server** <br/> |No  <br/> |Indica l'eventuale connessione della chiamata a un gateway vocale PSTN o IP-PBX qualificato senza passare attraverso il Mediation Server.  <br/> |
|**Sistema operativo chiamante** <br/> |No  <br/> |Sistema operativo del computer del chiamante.  <br/> |
|**CPU chiamante** <br/> |No  <br/> |CPU installata nel computer dell'utente che ha avviato la chiamata.  <br/> |
|**Numero di core CPU chiamante** <br/> |No  <br/> |Numero di processori nel computer utilizzato dalla persona che ha avviato la chiamata.  <br/> |
|**Velocità CPU chiamante** <br/> |No  <br/> |Velocità di clock della CPU del computer utilizzato dalla persona che ha avviato la chiamata.  <br/> |
|**Virtualizzazione CPU chiamante** <br/> |No  <br/> |Eventuale virtualizzazione nel computer utilizzato dalla persona che ha avviato la chiamata.  <br/> |
|**PAI destinatario chiamata** <br/> |No  <br/> |PAI (P-Asserted-Identity) dell'utente che ha inviato l'invito a partecipare alla chiamata. Questo valore viene utilizzato per trasmettere l'identità comprovata di un utente in una rete attendibile.  <br/> |
|**URI destinatario chiamata** <br/> |No  <br/> |Indirizzo SIP dell'utente chiamato.  <br/> |
|**Endpoint destinatario chiamata** <br/> |No  <br/> |Dispositivo utilizzato per ricevere la chiamata.  <br/> |
|**Agente utente destinatario chiamata** <br/> |No  <br/> |Software utilizzato nel dispositivo con cui è stata ricevuta la chiamata.  <br/> |
|**Durata** <br/> |No  <br/> |Durata della chiamata.  <br/> |
|**Flag di avviso bypass multimediale** <br/> |No  <br/> |Avviso generato quando è stato ignorato il Mediation Server.  <br/> |
|**Sistema operativo destinatario chiamata** <br/> |No  <br/> |Sistema operativo del computer dell'utente chiamato.  <br/> |
|**CPU destinatario chiamata** <br/> |No  <br/> |CPU installata nel computer dell'utente chiamato.  <br/> |
|**Numero di core CPU destinatario chiamata** <br/> |No  <br/> |Numero di processori nel computer utilizzato dalla persona chiamata.  <br/> |
|**Velocità CPU destinatario chiamata** <br/> |No  <br/> |Velocità di clock della CPU del computer utilizzato dalla persona chiamata.  <br/> |
|**Virtualizzazione CPU destinatario chiamata** <br/> |No  <br/> |Eventuale virtualizzazione nel computer utilizzato dalla persona chiamata.  <br/> |
   


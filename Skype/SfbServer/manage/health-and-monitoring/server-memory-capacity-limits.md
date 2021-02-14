---
title: Monitorare i limiti di capacità della memoria del server in Skype for Business Server
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
ms.assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
description: 'Riepilogo: informazioni su come monitorare i limiti di capacità della memoria del server in Skype for Business Server.'
ms.openlocfilehash: f1423d840fdf690332081a8083617c3a072b373c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814296"
---
# <a name="monitor-for-server-memory-capacity-limits-in-skype-for-business-server"></a>Monitorare i limiti di capacità della memoria del server in Skype for Business Server
 
**Riepilogo:** Informazioni su come monitorare i limiti di capacità della memoria del server in Skype for Business Server.
  
> [!CAUTION]
> Le informazioni contenute in questo argomento relative alla pianificazione della capacità riguardano solo i client Lync 2010 Mobile e il servizio per dispositivi mobili (Mcx). La pianificazione della capacità per UCWA (Unified Communications Web API), utilizzata dai client Lync 2013 Mobile, è fornita dallo strumento di pianificazione di Lync Server 2013. 

> [!NOTE]
> Il supporto MCX (Mobility Service) per i client mobili legacy non è più disponibile in Skype for Business Server 2019. Tutti i client mobili Skype for Business correnti usano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che utilizzano MCX dovranno eseguire l'aggiornamento a un client corrente.
  
Due contatori delle prestazioni per dispositivi mobili consentono di determinare l'utilizzo corrente e di pianificare la capacità per il servizio Per dispositivi mobili di Skype for Business Server (Mcx), oltre a monitorare l'utilizzo della memoria per UCWA. Per UCWA, la categoria del contatore è **LS:WEB - UCWA.** Per il servizio per dispositivi mobili (Mcx), i contatori sono nella categoria **LS:WEB - Mobile Communication Service.** I contatori da monitorare sono:
  
- **Numero di** sessioni attualmente attive con sottoscrizioni di presenza attive, ovvero il numero corrente di endpoint registrati tramite UCWA o il servizio per dispositivi mobili (Mcx) con sottoscrizioni di presenza attive (numero di utenti mobili sempre connessi)
    
- **Conteggio sessioni attualmente attive,** ovvero il numero corrente di endpoint registrati tramite UCWA o il servizio per dispositivi mobili
    
Se la  differenza tra il numero di  sessioni attualmente attive con sottoscrizioni di presenza attive e il numero di sessioni attualmente attive è ridotta nel tempo, significa che la maggior parte degli utenti di dispositivi mobili dispone di un dispositivo sempre connesso, ad esempio un dispositivo mobile Android o Nokia (solo per Mcx). I dispositivi UCWA sempre connessi includono dispositivi Apple e Android che eseguono client Lync 2013 Mobile. Se  il numero di sessioni attualmente attive è molto superiore al numero di sessioni attualmente attive con sottoscrizioni di presenza **attive,** questo indica che più utenti usano un dispositivo endpoint in background, ad esempio un dispositivo Apple iOS o Windows Phone in Mcx. Windows Phone è l'unico client Lync 2013 Mobile che verrà registrato come questo.
  
È consigliabile impostare  un limite per il numero  di sessioni attualmente attive con sottoscrizioni presenza attive e contatori delle prestazioni Conteggio sessioni attualmente attive in base all'utilizzo previsto, ai risultati della pianificazione della capacità e al monitoraggio continuo del servizio per dispositivi mobili e di altri contatori del Front End Server. I limiti impostati dovrebbero consentire di valutare la capacità del server e generare avvisi quando la capacità viene superata.
  
Per determinare i limiti appropriati, è necessario innanzitutto determinare la quantità di memoria disponibile nel Front End Server per il servizio per dispositivi mobili. Monitorare i contatori per determinare quando è necessario pianificare capacità aggiuntive, in base alla formula seguente:
  
Memoria totale utilizzata dal servizio Mcx Mobility (MB) = 164 + (400 + 134) / 1024 * **Conteggio** sessioni attualmente attive con sottoscrizioni presenza attive + 400 / 1024 * **(** Conteggio sessioni attualmente attive con sottoscrizioni presenza attive  -  )
  
> [!IMPORTANT]
> Lo strumento di calcolo della capacità di Microsoft Lync Server 2010 è un foglio di calcolo prepopolato con tutte le formule che consentono a un responsabile della pianificazione di determinare quali saranno i requisiti per i server Skype for Business, inclusi CPU, memoria e unità disco rigido. È possibile [scaricare il foglio di calcolo e un documento associato.](https://go.microsoft.com/fwlink/p/?LinkID=212657) 
  
Il Front End Server necessita di memoria sufficiente per supportare il servizio per dispositivi mobili in situazioni di failover. È possibile monitorare la memoria disponibile corrente nel Front End Server utilizzando il contatore **Memoria\Mbyte** disponibili oppure l'equazione indicata in precedenza per pianificare la quantità di memoria che si prevede verrà utilizzata dal servizio per dispositivi mobili.
  
Se la quantità di memoria disponibile nel Front End Server è inferiore a 1.500 MB quando si pianifica il numero previsto di utenti per dispositivi mobili, è necessario aggiungere più hardware per supportare il servizio per dispositivi mobili. Per ulteriori dettagli, vedere [Monitor mobility for performance in Skype for Business Server](monitor-mobility-performance.md) nella documentazione relativa alle operazioni.
  
## <a name="see-also"></a>Vedere anche

[Monitorare i dispositivi mobili per le prestazioni in Skype for Business Server](monitor-mobility-performance.md)

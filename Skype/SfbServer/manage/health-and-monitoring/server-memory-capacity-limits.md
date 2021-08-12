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
ms.openlocfilehash: d62ae4a7e9eaed4fd866107de276990c3d883d946b2d44035fcac4fa47b69e61
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54314462"
---
# <a name="monitor-for-server-memory-capacity-limits-in-skype-for-business-server"></a>Monitorare i limiti di capacità della memoria del server in Skype for Business Server
 
**Riepilogo:** Informazioni su come monitorare i limiti di capacità della memoria del server in Skype for Business Server.
  
> [!CAUTION]
> Le informazioni contenute in questo argomento che fanno riferimento alla pianificazione della capacità riguardano solo i client Lync 2010 Mobile e il servizio per dispositivi mobili (Mcx). Capacity Planning for the Unified Communications Web API (UCWA), utilizzata dai client Lync 2013 Mobile, è fornita dallo Strumento di pianificazione di Lync Server 2013. 

> [!NOTE]
> Il supporto MCX (Mobility Service) per i client mobili legacy non è più disponibile Skype for Business Server 2019. Tutti i client Skype for Business mobili utilizzano già UNIFIED Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che usano MCX dovranno eseguire l'aggiornamento a un client corrente.
  
Due contatori delle prestazioni per dispositivi mobili consentono di determinare l'utilizzo corrente e di pianificare la capacità per Skype for Business Server Mobility Service (Mcx), nonché di monitorare l'utilizzo della memoria per UCWA. Per UCWA, la categoria contatore è **LS:WEB - UCWA.** Per il servizio per dispositivi mobili (Mcx), i contatori sono nella categoria **LS:WEB - Mobile Communication Service.** I contatori da monitorare sono:
  
- **Conteggio** sessioni attualmente attive con sottoscrizioni presenza attiva , ovvero il numero corrente di endpoint registrati tramite UCWA o il servizio per dispositivi mobili (Mcx) con sottoscrizioni di presenza attive (numero di utenti mobili sempre connessi)
    
- **Conteggio sessioni attualmente attive,** ovvero il numero corrente di endpoint registrati tramite UCWA o il servizio per dispositivi mobili
    
Se la  differenza tra Conteggio sessioni  attualmente attive con sottoscrizioni presenza attiva e Conteggio sessioni attualmente attive è ridotta nel tempo, significa che la maggior parte degli utenti di dispositivi mobili dispone di un dispositivo sempre connesso, ad esempio un dispositivo mobile Android o Nokia (solo per Mcx). I dispositivi ucWA sempre connessi includono dispositivi Apple e Android che eseguono client Lync 2013 Mobile). Se  il numero di sessioni attualmente attive è molto superiore al numero di sessioni attualmente attive con sottoscrizioni di presenza **attive,** questo indica che più utenti usano un dispositivo endpoint in background, ad esempio un dispositivo Apple iOS o un Windows Phone in Mcx. (Windows Phone è l'unico client Lync 2013 Mobile che verrà registrato come questo).
  
È consigliabile impostare  un limite per i contatori delle prestazioni Conteggio sessioni attualmente attive con sottoscrizioni presenza attiva e Conteggio sessioni attualmente attive in base all'utilizzo previsto, ai risultati della pianificazione della capacità e al monitoraggio continuo del servizio per dispositivi mobili e di altri contatori del Front End Server.  I limiti impostati dovrebbero consentire di valutare la capacità del server e generare avvisi quando la capacità viene superata.
  
Per determinare i limiti appropriati, è innanzitutto necessario determinare la quantità di memoria disponibile nel Front End Server per il servizio per dispositivi mobili. Monitorare i contatori per determinare quando è necessario pianificare una capacità aggiuntiva, in base alla formula seguente:
  
Memoria totale utilizzata dal servizio Per dispositivi mobili Mcx (MB) = 164 + (400 + 134) / 1024 ***** Conteggio sessioni attualmente attive con sottoscrizioni presenza attive + 400 / 1024 * **(** Conteggio sessioni attualmente attive con sottoscrizioni  -  **presenza attive**)
  
> [!IMPORTANT]
> Il calcolatore della capacità di Microsoft Lync Server 2010 è un foglio di calcolo prepopolato con tutte le formule che consentono a un pianificatore di determinare quali saranno i requisiti per i server Skype for Business, tra cui CPU, memoria e unità disco rigido. È possibile [scaricare il foglio di calcolo e un documento associato.](https://go.microsoft.com/fwlink/p/?LinkID=212657) 
  
Il Front End Server necessita di memoria disponibile sufficiente per supportare il servizio per dispositivi mobili in situazioni di failover. È possibile monitorare la memoria disponibile corrente nel Front End Server utilizzando il contatore **Memory\Available Mbytes** oppure utilizzando l'equazione citata in precedenza per pianificare la quantità di memoria che si prevede verrà utilizzata dal servizio per dispositivi mobili.
  
Se la quantità di memoria disponibile nel Front End Server è inferiore a 1.500 MB quando si pianifica il numero previsto di utenti per dispositivi mobili, è necessario aggiungere più hardware per supportare il servizio per dispositivi mobili. Per ulteriori dettagli, vedere [Monitor mobility for performance in Skype for Business Server](monitor-mobility-performance.md) nella documentazione relativa alle operazioni.
  
## <a name="see-also"></a>Vedere anche

[Monitorare la mobilità per le prestazioni in Skype for Business Server](monitor-mobility-performance.md)

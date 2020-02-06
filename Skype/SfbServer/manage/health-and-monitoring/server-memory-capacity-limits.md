---
title: Monitorare i limiti di capacità di memoria del server in Skype for Business Server
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
ms.assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
description: 'Riepilogo: informazioni su come monitorare i limiti di capacità di memoria del server in Skype for Business Server.'
ms.openlocfilehash: 4f56fec8f3ed6900f4c4f1a97286dc14b66bb7c8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817705"
---
# <a name="monitor-for-server-memory-capacity-limits-in-skype-for-business-server"></a>Monitorare i limiti di capacità di memoria del server in Skype for Business Server
 
**Riepilogo:** Informazioni su come monitorare i limiti della capacità di memoria del server in Skype for Business Server.
  
> [!CAUTION]
> Le informazioni contenute in questo argomento che fanno riferimento alla pianificazione della capacità riguardano solo i client mobili Lync 2010 e il servizio mobilità (MCX). La pianificazione della capacità per Unified Communications Web API (UCWA), usata dai client per dispositivi mobili Lync 2013, è fornita da Lync Server 2013, strumento di pianificazione. 

> [!NOTE]
> Il supporto di MCX (servizio mobilità) per i client mobili legacy non è più disponibile in Skype for Business Server 2019. Tutti i client di Skype for business mobile correnti usano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che usano MCX dovranno eseguire l'aggiornamento a un client corrente.
  
Due contatori delle prestazioni della mobilità possono aiutarti a determinare l'uso corrente e ti aiutano a pianificare la capacità per il servizio di mobilità di Skype for Business Server (MCX), nonché a monitorare l'uso della memoria per UCWA. Per UCWA, la categoria contatore è **ls: Web-UCWA**. Per il servizio mobilità (MCX), i contatori sono sotto la categoria **ls: Web-servizio di comunicazione mobile**. I contatori da monitorare sono:
  
- **Conteggio delle sessioni attualmente attivo con gli abbonamenti alla presenza attiva**, ovvero il numero corrente di endpoint registrati tramite UCWA o il servizio di mobilità (MCX) con abbonamenti alla presenza attiva (numero di utenti di dispositivi mobili sempre connessi)
    
- **Conteggio delle sessioni attualmente attivo**, ovvero il numero corrente di endpoint registrati tramite UCWA o il servizio mobilità
    
Se la differenza tra il **conteggio delle sessioni attive con gli abbonamenti alla presenza attiva** e il conteggio delle **sessioni** attive è ridotta nel tempo, significa che la maggior parte degli utenti di dispositivi mobili ha un dispositivo sempre connesso, ad esempio un dispositivo mobile Android o Nokia (solo per MCX). I dispositivi UCWA sempre connessi includono dispositivi Apple e Android con client mobili Lync 2013. Se il **conteggio delle sessioni attualmente attivo** è molto più elevato del **conteggio delle sessioni attive con gli abbonamenti alla presenza attiva**, questo indica che più utenti usano un dispositivo endpoint in background, ad esempio un dispositivo iOS di Apple o un Windows Phone in MCX. Windows Phone è l'unico client per dispositivi mobili Lync 2013 che verrà registrato come questo.
  
È necessario impostare un limite per il **conteggio delle sessioni attivo con gli abbonamenti alla presenza attiva** e i contatori delle prestazioni **attualmente attivi** , in base ai risultati previsti per l'uso, alla pianificazione della capacità e al monitoraggio continuo del servizio di mobilità e di altri contatori del server front-end. I limiti impostati devono consentire di valutare la capacità del server e generare avvisi quando viene superata la capacità.
  
Per determinare i limiti appropriati, è prima di tutto necessario determinare la quantità di memoria disponibile nel server front-end per il servizio di mobilità. Monitorare i contatori per determinare quando è necessario pianificare la capacità aggiuntiva, in base alla formula seguente:
  
Memoria totale usata dal servizio di mobilità MCX (MB) = 164 + (400 + 134)/1024 * **numero di sessioni attualmente attivo con abbonamenti alla presenza attiva** + 400/1024 *** (** - il conteggio delle sessioni attualmente attivo è attualmente attivo**con gli abbonamenti alla presenza attiva**)
  
> [!IMPORTANT]
> Il calcolatore di capacità di Microsoft Lync Server 2010 è un foglio di calcolo prepopolato con tutte le formule che consentono a un planner di determinare quali sono i requisiti per i server Skype for business, tra cui CPU, memoria e disco rigido. È possibile [scaricare il foglio di calcolo e un documento associato](https://go.microsoft.com/fwlink/p/?LinkID=212657). 
  
Il server front-end richiede abbastanza memoria disponibile per supportare il servizio di mobilità in situazioni di failover. È possibile monitorare la memoria disponibile corrente sul server front-end usando il contatore **MByte Memoria\Mbyte** o usando l'equazione menzionata in precedenza per pianificare la quantità di memoria che si prevede venga usata dal servizio di mobilità.
  
Se la quantità di memoria disponibile nel server front-end è inferiore a 1.500 MB quando si prevede il numero previsto di utenti della mobilità, è necessario aggiungere altro hardware per supportare il servizio di mobilità. Per altre informazioni, vedere [monitorare la mobilità per le prestazioni in Skype for Business Server](monitor-mobility-performance.md) nella documentazione sulle operazioni.
  
## <a name="see-also"></a>Vedere anche

[Monitorare la mobilità per le prestazioni in Skype for Business Server](monitor-mobility-performance.md)

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
> Le informazioni contenute in questo argomento che si riferiscono alla pianificazione della capacità riguardano solo i client mobili Lync 2010 e il servizio di mobilità (MCX). La pianificazione della capacità per Unified Communications Web API (UCWA), utilizzata dai client per dispositivi mobili Lync 2013, viene fornita da Lync Server 2013, strumento di pianificazione. 

> [!NOTE]
> Il supporto di MCX (Mobility Service) per i client mobili legacy non è più disponibile in Skype for Business Server 2019. Tutti i client per dispositivi mobili Skype for business corrente utilizzano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che utilizzano MCX dovranno eseguire l'aggiornamento a un client corrente.
  
Due contatori delle prestazioni per dispositivi mobili possono essere utili per determinare l'utilizzo corrente e facilitare la pianificazione della capacità per il servizio per dispositivi mobili di Skype for Business Server (MCX), nonché per monitorare l'utilizzo della memoria per UCWA. Per UCWA, la categoria del contatore è **ls: Web-UCWA**. Per il servizio per dispositivi mobili (MCX), i contatori sono sotto la categoria **ls: Web-Mobile Communication Service**. I contatori da monitorare sono:
  
- **Conteggio delle sessioni attivo con gli abbonamenti alla presenza attiva**, ovvero il numero corrente di endpoint registrati tramite UCWA o il servizio per dispositivi mobili (MCX) che dispongono di sottoscrizioni di presenza attiva (numero di utenti mobili sempre connessi)
    
- **Conteggio delle sessioni attivo**, ovvero il numero corrente di endpoint registrati tramite UCWA o il servizio per dispositivi mobili
    
Se la differenza tra il **conteggio delle sessioni attive con gli abbonamenti alla presenza attiva** e il numero di **sessioni** attivo è di dimensioni ridotte nel tempo, significa che la maggior parte degli utenti di dispositivi mobili ha un dispositivo sempre connesso, ad esempio un dispositivo mobile Android o Nokia (solo per MCX). I dispositivi sempre connessi di UCWA includono i dispositivi Apple e Android che eseguono client mobili Lync 2013). Se il **numero di sessioni attualmente** attivo è molto più alto rispetto **al numero di sessioni attivo corrente con gli abbonamenti a presenza attiva**, ciò indica che più utenti utilizzano un dispositivo endpoint in background, ad esempio un dispositivo Apple iOS o Windows Phone in MCX. (Windows Phone è l'unico client per dispositivi mobili Lync 2013 che registrerà questo tipo di registrazione).
  
È necessario impostare un limite per il **conteggio delle sessioni attivo con gli abbonamenti per la presenza attiva** e i contatori delle prestazioni del **conteggio delle sessioni** attivo in base all'utilizzo previsto, ai risultati della pianificazione della capacità e al monitoraggio continuo del servizio per dispositivi mobili e di altri contatori di front end server. I limiti impostati devono consentire di valutare la capacità del server e aumentare gli avvisi in caso di superamento della capacità.
  
Per determinare i limiti corretti, è necessario determinare in primo luogo la quantità di memoria disponibile nel front end server per il servizio per dispositivi mobili. Monitorare i contatori per determinare quando è necessario pianificare la capacità aggiuntiva, in base alla formula seguente:
  
Memoria totale utilizzata da MCX Mobility Service (MB) = 164 + (400 + 134)/1024 * **Currently Active Session Count with Active Presence Subscriptions** + 400/1024 * ( **Currently Active Session Count**  -  **Currently Active Session Count with Active Presence Subscriptions**)
  
> [!IMPORTANT]
> Microsoft Lync Server 2010 capacity Calculator è un foglio di calcolo prepopolato con tutte le formule che consentono a un pianificatore di determinare quali sono i requisiti per i server Skype for business, tra cui CPU, memoria e disco rigido. È possibile [scaricare il foglio di calcolo e un documento associato](https://go.microsoft.com/fwlink/p/?LinkID=212657). 
  
Il front end server deve disporre di memoria sufficiente per supportare il servizio per dispositivi mobili in situazioni di failover. È possibile monitorare la memoria disponibile corrente sul front end server utilizzando il contatore **Memoria\mbyte MBytes** , oppure utilizzando l'equazione citata in precedenza, per pianificare la quantità di memoria che il servizio per dispositivi mobili deve utilizzare.
  
Se la quantità di memoria disponibile nel front end server è inferiore a 1.500 MB quando si pianifica il numero previsto di utenti di dispositivi mobili, è necessario aggiungere altro hardware per supportare il servizio per dispositivi mobili. Per ulteriori informazioni, vedere [monitorare i dispositivi mobili per le prestazioni in Skype for Business Server](monitor-mobility-performance.md) nella documentazione relativa alle operazioni.
  
## <a name="see-also"></a>Vedere anche

[Monitorare i dispositivi mobili per le prestazioni in Skype for Business Server](monitor-mobility-performance.md)

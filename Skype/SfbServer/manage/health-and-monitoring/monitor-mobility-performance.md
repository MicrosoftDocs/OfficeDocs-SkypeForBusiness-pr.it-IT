---
title: Monitorare la mobilità per le prestazioni in Skype for Business Server
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
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: "Riepilogo: informazioni sul servizio per dispositivi mobili (Mcx) e sull'API Web per comunicazioni unificate (UCWA) in Skype for Business Server."
ms.openlocfilehash: 5f8adbbdc653d8cdf2e19ce3f82fc4fdb0383505
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746922"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a>Monitorare la mobilità per le prestazioni in Skype for Business Server
 
**Riepilogo:** Informazioni su Mobility Service (Mcx) e Unified Communications Web API (UCWA) in Skype for Business Server.
  
Il Skype for Business Server Mobility Service (Mcx) e UCWA (Unified Communications Web API) aumentano il carico nei Front End Server e nei pool Front End. I dispositivi mobili che mantengono una connessione al server anche quando l'applicazione mobile è ridotta al minimo, ad esempio i dispositivi Android e Nokia che eseguono Lync 2010 Mobile, nonché i dispositivi Android e Apple che eseguono Lync 2013 Mobile, impongono un carico maggiore rispetto ai dispositivi che terminano la connessione al server quando l'applicazione mobile viene ridotta a icona. Con l'aumentare dell'utilizzo della mobilità, è necessario monitorare le prestazioni dei dispositivi mobili per determinare quando è necessario aumentare la capacità.

> [!NOTE]
> Il supporto MCX (Mobility Service) per i client mobili legacy non è più disponibile Skype for Business Server 2019. Tutti i client Skype for Business mobili utilizzano già UNIFIED Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che usano MCX dovranno eseguire l'aggiornamento a un client corrente.
  
Diversi limiti influiscono sulle prestazioni di mobilità: 
  
- Memoria disponibile
    
- Limite coda richieste
    
- Connessioni simultanee
    
- Lunghezza coda IIS
    
Altri limiti sui server che possono influire sulle prestazioni dei dispositivi mobili sono un massimo di 12 accessi simultanei, autenticazioni, rinnovi di sessioni e terminazioni. Questi valori massimi non devono essere modificati per la maggior parte delle distribuzioni.
  
## <a name="in-this-section"></a>Contenuto della sezione

- [Monitorare i limiti di capacità della memoria del server in Skype for Business Server](server-memory-capacity-limits.md)
    
- [Monitorare l'utilizzo di Servizi per dispositivi mobili e UCWA in Skype for Business Server](service-and-ucwa-usage.md)
    
- [Configurare il servizio per dispositivi mobili per prestazioni elevate in Skype for Business Server](configure-service.md)
    
- [Monitoraggio dei file di registro di traccia delle richieste IIS in Skype for Business Server](iis-request-tracing-log-files.md)
    
- [Contatori delle prestazioni per dispositivi mobili in Skype for Business Server](performance-counters.md)
    


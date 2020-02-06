---
title: Monitorare la mobilità per le prestazioni in Skype for Business Server
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
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: "Riepilogo: informazioni sul servizio di mobilità (MCX) e sull'API Web Unified Communications (UCWA) in Skype for Business Server."
ms.openlocfilehash: 4d604c46704881a055385336f8b1ff32862d929a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817835"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a>Monitorare la mobilità per le prestazioni in Skype for Business Server
 
**Riepilogo:** Informazioni sul servizio di mobilità (MCX) e sull'API Unified Communications Web (UCWA) in Skype for Business Server.
  
Il servizio di mobilità di Skype for Business Server (MCX) e l'API Web Unified Communications (UCWA) aumentano il carico nei server front-end e nei pool Front-end. I dispositivi mobili che gestiscono una connessione al server anche quando l'applicazione mobile è ridotta a icona, ad esempio dispositivi Android e Nokia che utilizzano Lync 2010 mobile, oltre a dispositivi Android e Apple che utilizzano Lync 2013 mobile, impongono un carico maggiore rispetto ai dispositivi che terminare la connessione al server quando l'applicazione per dispositivi mobili viene ridotta a icona. Man mano che l'uso della mobilità aumenta, è necessario monitorare le prestazioni della mobilità per determinare quando è necessario aumentare la propria capacità.

> [!NOTE]
> Il supporto di MCX (servizio mobilità) per i client mobili legacy non è più disponibile in Skype for Business Server 2019. Tutti i client di Skype for business mobile correnti usano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che usano MCX dovranno eseguire l'aggiornamento a un client corrente.
  
Diversi limiti influenzano le prestazioni di mobilità: 
  
- Memoria disponibile
    
- Limite della coda di richiesta
    
- Connessioni simultanee
    
- Lunghezza coda di IIS
    
Altri limiti per i server che possono influenzare le prestazioni della mobilità sono un massimo di 12 accessi contemporanei, autenticazioni, rinnovi di sessioni e terminazioni. Non è necessario modificare questi massimali per la maggior parte delle distribuzioni.
  
## <a name="in-this-section"></a>In questa sezione

- [Monitorare i limiti di capacità di memoria del server in Skype for Business Server](server-memory-capacity-limits.md)
    
- [Monitorare il servizio di mobilità e l'uso di UCWA in Skype for Business Server](service-and-ucwa-usage.md)
    
- [Configurare il servizio di mobilità per prestazioni elevate in Skype for Business Server](configure-service.md)
    
- [Monitoraggio dei file di log della traccia delle richieste di IIS in Skype for Business Server](iis-request-tracing-log-files.md)
    
- [Contatori delle prestazioni di mobilità in Skype for Business Server](performance-counters.md)
    


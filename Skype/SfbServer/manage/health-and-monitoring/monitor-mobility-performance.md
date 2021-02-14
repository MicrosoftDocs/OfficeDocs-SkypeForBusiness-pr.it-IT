---
title: Monitorare i dispositivi mobili per le prestazioni in Skype for Business Server
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
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 'Riepilogo: informazioni sul servizio per dispositivi mobili (Mcx) e su Unified Communications Web API (UCWA) in Skype for Business Server.'
ms.openlocfilehash: d7473d22f2de0576bf6214ae43719c8bfc70d49a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816836"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a>Monitorare i dispositivi mobili per le prestazioni in Skype for Business Server
 
**Riepilogo:** Informazioni sul servizio per dispositivi mobili (Mcx) e su Unified Communications Web API (UCWA) in Skype for Business Server.
  
Il servizio Per dispositivi mobili di Skype for Business Server (Mcx) e UCWA (Unified Communications Web API) aumentano il carico sui Front End Server e sui pool Front End. I dispositivi mobili che mantengono una connessione al server anche quando l'applicazione mobile è ridotta a icona, ad esempio i dispositivi Android e Nokia che eseguono Lync 2010 Mobile, nonché i dispositivi Android e Apple che eseguono Lync 2013 Mobile, impongono un carico maggiore rispetto ai dispositivi che terminano la connessione al server quando l'applicazione mobile viene ridotta a icona. Con l'aumentare dell'utilizzo della mobilità, è necessario monitorare le prestazioni della mobilità per determinare quando è necessario aumentare la capacità.

> [!NOTE]
> Il supporto MCX (Mobility Service) per i client mobili legacy non è più disponibile in Skype for Business Server 2019. Tutti i client mobili Skype for Business correnti usano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che utilizzano MCX dovranno eseguire l'aggiornamento a un client corrente.
  
Diversi limiti influiscono sulle prestazioni dei dispositivi mobili: 
  
- Memoria disponibile
    
- Limite coda richieste
    
- Connessioni simultanee
    
- Lunghezza coda IIS
    
Altri limiti per i server che possono influire sulle prestazioni dei dispositivi mobili sono un massimo di 12 accessi simultanei, autenticazioni, rinnovi di sessioni e terminazioni. Questi valori massimi non devono essere modificati per la maggior parte delle distribuzioni.
  
## <a name="in-this-section"></a>Contenuto della sezione

- [Monitorare i limiti di capacità della memoria del server in Skype for Business Server](server-memory-capacity-limits.md)
    
- [Monitorare il servizio per dispositivi mobili e l'utilizzo di UCWA in Skype for Business Server](service-and-ucwa-usage.md)
    
- [Configurare il servizio per dispositivi mobili per prestazioni elevate in Skype for Business Server](configure-service.md)
    
- [Monitoraggio dei file di registro di traccia delle richieste IIS in Skype for Business Server](iis-request-tracing-log-files.md)
    
- [Contatori delle prestazioni per dispositivi mobili in Skype for Business Server](performance-counters.md)
    


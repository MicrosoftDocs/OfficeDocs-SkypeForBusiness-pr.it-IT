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
description: "Riepilogo: informazioni sul servizio per dispositivi mobili (MCX) e sull'API Unified Communications Web (UCWA) in Skype for Business Server."
ms.openlocfilehash: d7473d22f2de0576bf6214ae43719c8bfc70d49a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816836"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a>Monitorare i dispositivi mobili per le prestazioni in Skype for Business Server
 
**Riepilogo:** Informazioni su The Mobility Service (MCX) e Unified Communications Web API (UCWA) in Skype for Business Server.
  
Skype for Business Server Mobility Service (MCX) e Unified Communications Web API (UCWA) aumentano il carico nei front end server e nei pool Front end. I dispositivi mobili che gestiscono una connessione al server anche quando l'applicazione per dispositivi mobili è ridotta a icona, come Android e Nokia su cui è in esecuzione Lync 2010 mobile, così come i dispositivi Android e Apple che eseguono Lync 2013 mobile, impongono un carico maggiore rispetto ai dispositivi che terminano la connessione al server quando l'applicazione per dispositivi mobili è ridotta a icona. Quando l'utilizzo della mobilità aumenta, è necessario monitorare le prestazioni dei dispositivi mobili per determinare quando è necessario aumentare la capacità.

> [!NOTE]
> Il supporto di MCX (Mobility Service) per i client mobili legacy non è più disponibile in Skype for Business Server 2019. Tutti i client per dispositivi mobili Skype for business corrente utilizzano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che utilizzano MCX dovranno eseguire l'aggiornamento a un client corrente.
  
Diversi limiti influenzano le prestazioni della mobilità: 
  
- Memoria disponibile
    
- Limite coda richieste
    
- Connessioni simultanee
    
- Lunghezza coda IIS
    
Altri limiti nei server che possono influire sulle prestazioni della mobilità sono al massimo 12 accessi simultanei, autenticazioni, rinnovi di sessioni e terminazioni. Non è necessario modificare questi valori massimi per la maggior parte delle distribuzioni.
  
## <a name="in-this-section"></a>Contenuto della sezione

- [Monitorare i limiti di capacità della memoria del server in Skype for Business Server](server-memory-capacity-limits.md)
    
- [Monitorare il servizio per dispositivi mobili e l'utilizzo di UCWA in Skype for Business Server](service-and-ucwa-usage.md)
    
- [Configurare il servizio per dispositivi mobili per ottenere prestazioni elevate in Skype for Business Server](configure-service.md)
    
- [Monitoraggio dei file di registro di traccia delle richieste IIS in Skype for Business Server](iis-request-tracing-log-files.md)
    
- [Contatori delle prestazioni per dispositivi mobili in Skype for Business Server](performance-counters.md)
    


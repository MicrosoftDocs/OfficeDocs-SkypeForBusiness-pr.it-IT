---
title: Configurare il servizio di mobilità per prestazioni elevate in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 'Riepilogo: informazioni sul servizio mobilità in Skype for Business Server.'
ms.openlocfilehash: 35e04fa080964495ccd9abed28c0688dd7be45a9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195707"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a>Configurare il servizio di mobilità per prestazioni elevate in Skype for Business Server
 
**Riepilogo:** Informazioni sul servizio mobilità in Skype for Business Server.
  
> [!IMPORTANT]
> Questo argomento si applica solo al servizio di mobilità di Skype for Business Server (MCX) e non si applica a Unified Communications Web API (UCWA), come fornito negli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013. 
  
Quando si installa il servizio di mobilità (MCX) in Internet Information Services (IIS) 7,5, il programma di installazione del servizio di mobilità configura alcune impostazioni di prestazioni nel server front-end. È consigliabile usare IIS 7,5 per la mobilità. Le impostazioni influenzano il numero massimo di richieste utente simultanee e il numero massimo di thread consentiti per il servizio di mobilità.
  
Ecco le impostazioni delle prestazioni:
  
### <a name="settings-for-mcx-on-iis-75"></a>Impostazioni per MCX in IIS 7,5

1. **MaxConcurrentThreadsPerCPU** è impostato su zero (0).
    
2. **maxConcurrentRequestsPerCPU** è impostato su zero (0).
    
3. Il modello di processo di ASP.NET è impostato su AutoConfig (solo per IIS 7,5).
    
4. Il limite della coda HTTP. sys è impostato su 1.000 (per impostazione predefinita).
    


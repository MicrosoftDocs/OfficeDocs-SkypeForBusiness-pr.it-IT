---
title: Configurare il servizio per dispositivi mobili per ottenere prestazioni elevate in Skype for Business Server
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
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 'Riepilogo: informazioni sul servizio per dispositivi mobili in Skype for Business Server.'
ms.openlocfilehash: 83d8d6dc7a32b05a58c738deddc8c92e43bd5557
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817036"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a>Configurare il servizio per dispositivi mobili per ottenere prestazioni elevate in Skype for Business Server
 
**Riepilogo:** Informazioni sul servizio per dispositivi mobili in Skype for Business Server.
  
> [!IMPORTANT]
> Questo argomento si applica solo al servizio per dispositivi mobili di Skype for Business Server (MCX) e non si applica a Unified Communications Web API (UCWA), come recapitato negli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013. 
  
Quando si installa il servizio per dispositivi mobili (MCX) su Internet Information Services (IIS) 7,5, il programma di installazione del servizio per dispositivi mobili configura alcune impostazioni delle prestazioni nel front end server. È consigliabile utilizzare IIS 7.5 per la mobilità. Le impostazioni influiscono sul numero massimo di richieste utente simultanee e il numero massimo di thread consentiti per il servizio di mobilità.
  
Di seguito sono conformate le impostazioni delle prestazioni:
  
### <a name="settings-for-mcx-on-iis-75"></a>Impostazioni per MCX in IIS 7,5

1. Il valore **maxConcurrentThreadsPerCPU** viene impostato su zero (0).
    
2. Il valore **maxConcurrentRequestsPerCPU** viene impostato su zero (0).
    
3. Il modello di processo ASP.NET viene impostato su AutoConfig (solo per IIS 7.5).
    
4. Il limite di coda HTTP.sys viene impostato su 1.000 per impostazione predefinita.
    


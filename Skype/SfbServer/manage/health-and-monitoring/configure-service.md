---
title: Configurare il servizio per dispositivi mobili per prestazioni elevate in Skype for Business Server
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
ms.openlocfilehash: 3029877aa6f252ada9bbb38bca0148b8a96908ad5cf4deded7cf48e6451ec833
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54298136"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a>Configurare il servizio per dispositivi mobili per prestazioni elevate in Skype for Business Server
 
**Riepilogo:** Informazioni sul servizio per dispositivi mobili in Skype for Business Server.
  
> [!IMPORTANT]
> Questo argomento si applica solo al servizio per dispositivi mobili di Skype for Business Server (Mcx) e non si applica a UCWA (Unified Communications Web API), come fornito negli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013. 
  
Quando si installa il servizio per dispositivi mobili (Mcx) in Internet Information Services (IIS) 7.5, il programma di installazione del servizio per dispositivi mobili configura alcune impostazioni delle prestazioni nel Front End Server. È consigliabile utilizzare IIS 7.5 per la mobilità. Le impostazioni influiscono sul numero massimo di richieste utente simultanee e il numero massimo di thread consentiti per il servizio di mobilità.
  
Ecco le impostazioni delle prestazioni:
  
### <a name="settings-for-mcx-on-iis-75"></a>Impostazioni per Mcx in IIS 7.5

1. Il valore **maxConcurrentThreadsPerCPU** viene impostato su zero (0).
    
2. Il valore **maxConcurrentRequestsPerCPU** viene impostato su zero (0).
    
3. Il modello di processo ASP.NET viene impostato su AutoConfig (solo per IIS 7.5).
    
4. Il limite di coda HTTP.sys viene impostato su 1.000 per impostazione predefinita.
    


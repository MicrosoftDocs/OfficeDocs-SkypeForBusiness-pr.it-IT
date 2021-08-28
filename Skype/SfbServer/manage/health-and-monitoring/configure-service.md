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
ms.localizationpriority: medium
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 'Riepilogo: informazioni sul servizio per dispositivi mobili in Skype for Business Server.'
ms.openlocfilehash: da2685faae6bf44fee212132dba6a0f7e0fe2e76
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58621032"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a>Configurare il servizio per dispositivi mobili per prestazioni elevate in Skype for Business Server
 
**Riepilogo:** Informazioni sul servizio per dispositivi mobili in Skype for Business Server.
  
> [!IMPORTANT]
> Questo argomento si applica solo al servizio per dispositivi mobili di Skype for Business Server (Mcx) e non a UCWA (Unified Communications Web API), come fornito negli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013. 
  
Quando si installa il servizio per dispositivi mobili (Mcx) in Internet Information Services (IIS) 7.5, il programma di installazione del servizio per dispositivi mobili configura alcune impostazioni delle prestazioni nel Front End Server. È consigliabile utilizzare IIS 7.5 per la mobilità. Le impostazioni influiscono sul numero massimo di richieste utente simultanee e il numero massimo di thread consentiti per il servizio di mobilità.
  
Ecco le impostazioni delle prestazioni:
  
### <a name="settings-for-mcx-on-iis-75"></a>Impostazioni per Mcx in IIS 7.5

1. Il valore **maxConcurrentThreadsPerCPU** viene impostato su zero (0).
    
2. Il valore **maxConcurrentRequestsPerCPU** viene impostato su zero (0).
    
3. Il modello di processo ASP.NET viene impostato su AutoConfig (solo per IIS 7.5).
    
4. Il limite di coda HTTP.sys viene impostato su 1.000 per impostazione predefinita.
    


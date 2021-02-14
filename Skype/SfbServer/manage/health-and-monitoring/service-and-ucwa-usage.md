---
title: Monitorare il servizio per dispositivi mobili e l'utilizzo di UCWA in Skype for Business Server
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
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Riepilogo: gestire il servizio per dispositivi mobili (Mcx) e Unified Communications Web API (UCWA) in Skype for Business Server.'
ms.openlocfilehash: 76bcf8727d3abbb417595f033ce9a59ec00a39ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814246"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a>Monitorare il servizio per dispositivi mobili e l'utilizzo di UCWA in Skype for Business Server
 
**Riepilogo:** Gestire il servizio per dispositivi mobili (Mcx) e Unified Communications Web API (UCWA) in Skype for Business Server.

> [!NOTE]
> Il supporto MCX (Mobility Service) per i client mobili legacy non è più disponibile in Skype for Business Server 2019. Tutti i client mobili Skype for Business correnti usano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che utilizzano MCX dovranno eseguire l'aggiornamento a un client corrente.
  
Su base continuativa, è consigliabile monitorare la CPU e la memoria utilizzata dal servizio Per dispositivi mobili di Skype for Business Server (Mcx) e da Unified Communications Web API (UCWA). Per monitorare l'utilizzo, è possibile utilizzare quanto segue:
  
 **Per UCWA (Unified Communications Web API):**
  
- Processo **di lavoro LyncUcwa** in Gestione Internet Information Services (IIS). Nel riquadro **Processi di lavoro** analizzare le colonne **% CPU** e **Byte privati (KB)** (memoria).
    
- Contatori delle prestazioni relativi a **CPU** e **Processore**.
    
Per la maggior parte delle distribuzioni, l'utilizzo medio della CPU di UCWA deve essere inferiore al 15%. L'utilizzo della memoria deve rientrare nei limiti descritti in Monitorare i limiti di capacità della memoria del [server in Skype for Business Server.](server-memory-capacity-limits.md)
  
Oltre ai contatori di utilizzo della CPU e della memoria, è possibile utilizzare i contatori delle prestazioni seguenti per determinare quando un server è sovraccarico di richieste:
  
- **LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, che indica il numero di richieste Web in sospeso nel server. Quando questo contatore raggiunge 10.000, le richieste successive avranno esito negativo, con il messaggio di errore "503 - Servizio non disponibile".
    
- **ASP.NET\Requests Queued** (deve essere sempre zero).
    
> [!NOTE]
> Se si soddisfano o si superano questi valori, è necessario rivedere e ricalcolare la pianificazione della capacità per il dimensionamento corretto della CPU, il numero di core e la memoria per i computer che ospitano i servizi Web. 
  
 **Per il servizio per dispositivi mobili (Mcx):**
  
- I processi di lavoro **CSIntMcxAppPool** e **CSExtMcxAppPool** in Gestione Internet Information Services (IIS). Nel riquadro **Processi di lavoro** analizzare le colonne **% CPU** e **Byte privati (KB)** (memoria).
    
- Contatori delle prestazioni relativi a **CPU** e **Processore**.
    
Per la maggior parte delle distribuzioni, l'utilizzo medio della CPU del servizio per dispositivi mobili deve essere inferiore al 15%. L'utilizzo della memoria deve rientrare nei limiti descritti in Monitorare i limiti di capacità della memoria del [server in Skype for Business Server.](server-memory-capacity-limits.md)
  
Oltre ai contatori di utilizzo della CPU e della memoria, è possibile utilizzare il contatori delle prestazioni ASP.NET seguenti per determinare quando un server è sovraccarico di richieste:
  
- **ASP.NET v2.0.50727\Requests Current**, che indica il numero di richieste Web in sospeso nel server. Quando questo contatore raggiunge 5.000, le richieste successive avranno esito negativo con il messaggio di errore "503 - Servizio non disponibile".
    
- **ASP.NET\Requests Queued** (deve essere sempre zero).
    
> [!NOTE]
> Se si soddisfano o si superano questi valori, è consigliabile rivedere e ricalcolare la pianificazione della capacità per il dimensionamento corretto della CPU, del numero di core e della memoria per i computer che ospitano i servizi Web. 

> [!NOTE]
> Il supporto MCX (Mobility Service) per i client mobili legacy non è più disponibile in Skype for Business Server 2019. Tutti i client mobili Skype for Business correnti usano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che utilizzano MCX dovranno eseguire l'aggiornamento a un client corrente.
  
## <a name="see-also"></a>Vedere anche

[Monitorare i limiti di capacità della memoria del server in Skype for Business Server](server-memory-capacity-limits.md)

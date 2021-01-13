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
description: 'Sintesi: gestire il servizio per dispositivi mobili (MCX) e Unified Communications Web API (UCWA) in Skype for Business Server.'
ms.openlocfilehash: 76bcf8727d3abbb417595f033ce9a59ec00a39ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814246"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a>Monitorare il servizio per dispositivi mobili e l'utilizzo di UCWA in Skype for Business Server
 
**Riepilogo:** Gestire il servizio per dispositivi mobili (MCX) e Unified Communications Web API (UCWA) in Skype for Business Server.

> [!NOTE]
> Il supporto di MCX (Mobility Service) per i client mobili legacy non è più disponibile in Skype for Business Server 2019. Tutti i client per dispositivi mobili Skype for business corrente utilizzano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che utilizzano MCX dovranno eseguire l'aggiornamento a un client corrente.
  
Su base continuativa, è consigliabile monitorare la CPU e la memoria utilizzata da Skype for Business Server Mobility Service (MCX) e Unified Communications Web API (UCWA). Per monitorare l'utilizzo, è possibile utilizzare gli elementi seguenti:
  
 **Per Unified Communications Web API (UCWA):**
  
- Il processo di lavoro di **LyncUcwa** in Gestione Internet Information Services (IIS). Nel riquadro **Processi di lavoro** analizzare le colonne **% CPU** e **Byte privati (KB)** (memoria).
    
- Contatori delle prestazioni relativi a **CPU** e **Processore**.
    
Per la maggior parte delle distribuzioni, l'utilizzo della CPU UCWA dovrebbe essere inferiore al 15% in media. L'utilizzo della memoria deve rientrare nei limiti descritti in [Monitor per i limiti di capacità della memoria del server in Skype for Business Server](server-memory-capacity-limits.md).
  
Oltre ai contatori di utilizzo della CPU e della memoria, è possibile utilizzare i contatori delle prestazioni seguenti per determinare quando un server è sottoposto a overload con richieste:
  
- **Ls: richieste di limitazione Web e Authentication\WEB-totale nell'elaborazione**, che indica il numero di richieste Web in sospeso sul server. Quando questo contatore raggiunge 10.000, le richieste successive avranno esito negativo, con il messaggio di errore "503-servizio non disponibile".
    
- **ASP.NET\Requests Queued** (deve essere sempre zero).
    
> [!NOTE]
> Se si soddisfano o superano questi valori, è consigliabile rivisitare e ricalcolare la pianificazione della capacità per il corretto dimensionamento della CPU, il numero di core e la memoria dei computer che ospitano i servizi Web. 
  
 **Per il servizio per dispositivi mobili (MCX):**
  
- I processi di lavoro di **CSIntMcxAppPool** e **CSExtMcxAppPool** in Gestione Internet Information Services (IIS). Nel riquadro **Processi di lavoro** analizzare le colonne **% CPU** e **Byte privati (KB)** (memoria).
    
- Contatori delle prestazioni relativi a **CPU** e **Processore**.
    
Per la maggior parte delle distribuzioni, l'utilizzo della CPU del servizio per dispositivi mobili deve essere inferiore al 15%, in media. L'utilizzo della memoria deve rientrare nei limiti descritti in [Monitor per i limiti di capacità della memoria del server in Skype for Business Server](server-memory-capacity-limits.md).
  
Oltre ai contatori di utilizzo della CPU e della memoria, è possibile utilizzare il contatori delle prestazioni ASP.NET seguenti per determinare quando un server è sovraccarico di richieste:
  
- **ASP.NET v2.0.50727\Requests Current**, che indica il numero di richieste Web in sospeso nel server. Quando questo contatore raggiunge 5.000, le richieste successive avranno esito negativo con il messaggio di errore "503-servizio non disponibile".
    
- **ASP.NET\Requests Queued** (deve essere sempre zero).
    
> [!NOTE]
> Se si soddisfano o superano questi valori, è consigliabile rivisitare e ricalcolare la pianificazione della capacità per il corretto dimensionamento della CPU, del numero di core e della memoria per i computer che ospitano i servizi Web. 

> [!NOTE]
> Il supporto di MCX (Mobility Service) per i client mobili legacy non è più disponibile in Skype for Business Server 2019. Tutti i client per dispositivi mobili Skype for business corrente utilizzano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che utilizzano MCX dovranno eseguire l'aggiornamento a un client corrente.
  
## <a name="see-also"></a>Vedere anche

[Monitorare i limiti di capacità della memoria del server in Skype for Business Server](server-memory-capacity-limits.md)

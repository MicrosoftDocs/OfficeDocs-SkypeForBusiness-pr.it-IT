---
title: Monitorare l'utilizzo del servizio per dispositivi mobili e UCWA in Skype for Business Server
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
description: "Riepilogo: gestire il servizio per dispositivi mobili (Mcx) e l'API Web per comunicazioni unificate (UCWA) in Skype for Business Server."
ms.openlocfilehash: 6f97e8ec6199fe4665d3d7532f0cb03e21204fafc4764cf36c89dcbeacc4321d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54317601"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a>Monitorare l'utilizzo del servizio per dispositivi mobili e UCWA in Skype for Business Server
 
**Riepilogo:** Gestire il servizio per dispositivi mobili (Mcx) e l'API Unified Communications Web (UCWA) in Skype for Business Server.

> [!NOTE]
> Il supporto MCX (Mobility Service) per i client mobili legacy non è più disponibile Skype for Business Server 2019. Tutti i client Skype for Business mobili utilizzano già UNIFIED Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che usano MCX dovranno eseguire l'aggiornamento a un client corrente.
  
Su base continuativa, è consigliabile monitorare la CPU e la memoria utilizzata dal servizio per dispositivi mobili di Skype for Business Server (Mcx) e dall'API Web per comunicazioni unificate (UCWA). Per monitorare l'utilizzo, è possibile utilizzare quanto segue:
  
 **Per UCWA (Unified Communications Web API):**
  
- Processo **di lavoro LyncUcwa** in Gestione Internet Information Services (IIS). Nel riquadro **Processi di lavoro** analizzare le colonne **% CPU** e **Byte privati (KB)** (memoria).
    
- Contatori delle prestazioni relativi a **CPU** e **Processore**.
    
Per la maggior parte delle distribuzioni, l'utilizzo della CPU UCWA deve essere in media inferiore al 15%. L'utilizzo della memoria deve rientrare nei limiti descritti in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).
  
Oltre ai contatori di utilizzo della CPU e della memoria, è possibile utilizzare i contatori delle prestazioni seguenti per determinare quando un server è sovraccarico di richieste:
  
- **LS:WEB - Limitazione e autenticazione\WEB - Totale** richieste in elaborazione, che indica il numero di richieste Web in sospeso nel server. Quando questo contatore raggiunge 10.000, le richieste successive avranno esito negativo, con il messaggio di errore "503 - Servizio non disponibile".
    
- **ASP.NET\Requests Queued** (deve essere sempre zero).
    
> [!NOTE]
> Se si soddisfano o si superano questi valori, è consigliabile rivisitare e ricalcolare la pianificazione della capacità per il dimensionamento corretto della CPU, del numero di core e della memoria per i computer che ospitano i servizi Web. 
  
 **Per il servizio per dispositivi mobili (Mcx):**
  
- I processi di lavoro **CSIntMcxAppPool** e **CSExtMcxAppPool** in Gestione Internet Information Services (IIS). Nel riquadro **Processi di lavoro** analizzare le colonne **% CPU** e **Byte privati (KB)** (memoria).
    
- Contatori delle prestazioni relativi a **CPU** e **Processore**.
    
Per la maggior parte delle distribuzioni, l'utilizzo della CPU del servizio per dispositivi mobili deve essere in media inferiore al 15%. L'utilizzo della memoria deve rientrare nei limiti descritti in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).
  
Oltre ai contatori di utilizzo della CPU e della memoria, è possibile utilizzare il contatori delle prestazioni ASP.NET seguenti per determinare quando un server è sovraccarico di richieste:
  
- **ASP.NET v2.0.50727\Requests Current**, che indica il numero di richieste Web in sospeso nel server. Quando questo contatore raggiunge 5.000, le richieste successive avranno esito negativo con il messaggio di errore "503 - Servizio non disponibile".
    
- **ASP.NET\Requests Queued** (deve essere sempre zero).
    
> [!NOTE]
> Se si soddisfano o si superano questi valori, è consigliabile rivedere e ricalcolare la pianificazione della capacità per il ridimensionamento corretto della CPU, del numero di core e della memoria per i computer che ospitano i servizi Web. 

> [!NOTE]
> Il supporto MCX (Mobility Service) per i client mobili legacy non è più disponibile Skype for Business Server 2019. Tutti i client Skype for Business mobili utilizzano già UNIFIED Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che usano MCX dovranno eseguire l'aggiornamento a un client corrente.
  
## <a name="see-also"></a>Vedere anche

[Monitorare i limiti di capacità della memoria del server in Skype for Business Server](server-memory-capacity-limits.md)

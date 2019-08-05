---
title: Monitorare il servizio di mobilità e l'uso di UCWA in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Riepilogo: gestire il servizio di mobilità (MCX) e la Unified Communications Web API (UCWA) in Skype for Business Server.'
ms.openlocfilehash: 5447eb0ac8ffe468fd52c7011824cc1f2f2f7b55
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188681"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a>Monitorare il servizio di mobilità e l'uso di UCWA in Skype for Business Server
 
**Riepilogo:** Gestire il servizio di mobilità (MCX) e la Unified Communications Web API (UCWA) in Skype for Business Server.

> [!NOTE]
> Il supporto di MCX (servizio mobilità) per i client mobili legacy non è più disponibile in Skype for Business Server 2019. Tutti i client di Skype for business mobile correnti usano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che usano MCX dovranno eseguire l'aggiornamento a un client corrente.
  
In base alle proprie attività, è necessario monitorare la CPU e la memoria usate dal servizio di mobilità di Skype for Business Server (MCX) e da Unified Communications Web API (UCWA). Per monitorare l'uso, è possibile usare quanto segue:
  
 **Per Unified Communications Web API (UCWA):**
  
- Processo di lavoro di **LyncUcwa** in Gestione Internet Information Services (IIS). Nel riquadro **processi di lavoro** esaminare le colonne **CPU%** e **private bytes (KB)** (memoria).
    
- Contatori delle prestazioni della **CPU** e del **processore** .
    
Per la maggior parte delle distribuzioni, l'uso della CPU UCWA deve essere inferiore al 15% in media. L'utilizzo della memoria deve rientrare nei limiti descritti in [Monitor per i limiti di capacità di memoria del server in Skype for Business Server](server-memory-capacity-limits.md).
  
Oltre ai contatori di utilizzo della CPU e della memoria, è possibile usare i contatori delle prestazioni seguenti per determinare quando un server è in overload con le richieste:
  
- **Ls: limitazione del Web e Authentication\WEB-totale delle richieste di elaborazione**, che indica il numero di richieste Web in sospeso nel server. Quando questo contatore raggiunge 10.000, le richieste successive avranno esito negativo, con il messaggio di errore "503-servizio non disponibile".
    
- **ASP. NET\Richieste in coda** (deve sempre essere zero).
    
> [!NOTE]
> Se si soddisfano o superano questi valori, è necessario rivedere e ricalcolare la pianificazione della capacità per il dimensionamento corretto della CPU, il numero di core e la memoria per i computer che ospitano i servizi Web. 
  
 **Per il servizio mobilità (MCX):**
  
- Processi di lavoro di **CSIntMcxAppPool** e **CSExtMcxAppPool** in Gestione Internet Information Services (IIS). Nel riquadro **processi di lavoro** esaminare le colonne **CPU%** e **private bytes (KB)** (memoria).
    
- Contatori delle prestazioni della **CPU** e del **processore** .
    
Per la maggior parte delle distribuzioni, l'uso della CPU del servizio di mobilità deve essere inferiore al 15%, in media. L'utilizzo della memoria deve rientrare nei limiti descritti in [Monitor per i limiti di capacità di memoria del server in Skype for Business Server](server-memory-capacity-limits.md).
  
Oltre ai contatori di utilizzo della CPU e della memoria, è possibile usare i seguenti contatori delle prestazioni di ASP.NET per determinare quando un server è in overload con le richieste:
  
- **ASP.NET v 2.0.50727 \ richiede Current**, che indica il numero di richieste Web in sospeso nel server. Quando questo contatore raggiunge 5.000, le richieste successive avranno esito negativo con il messaggio di errore "503-servizio non disponibile".
    
- **ASP. NET\Richieste in coda** (deve sempre essere zero).
    
> [!NOTE]
> Se si soddisfano o superano questi valori, è necessario rivedere e ricalcolare la pianificazione della capacità per il dimensionamento corretto della CPU, del numero di core e della memoria per i computer che ospitano i servizi Web. 

> [!NOTE]
> Il supporto di MCX (servizio mobilità) per i client mobili legacy non è più disponibile in Skype for Business Server 2019. Tutti i client di Skype for business mobile correnti usano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che usano MCX dovranno eseguire l'aggiornamento a un client corrente.
  
## <a name="see-also"></a>Vedere anche

[Monitorare i limiti di capacità di memoria del server in Skype for Business Server](server-memory-capacity-limits.md)

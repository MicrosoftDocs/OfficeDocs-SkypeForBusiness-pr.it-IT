---
title: 'Lync Server 2013: monitoraggio del servizio per dispositivi mobili e utilizzo di UCWA'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring Mobility Service and UCWA usage
ms:assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690025(v=OCS.15)
ms:contentKeyID: 48184683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94a04e310e3d7c7d0954ba8a34088a41d1692df8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149285"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-service-and-ucwa-usage-in-lync-server-2013"></a>Monitoraggio del servizio per dispositivi mobili e utilizzo di UCWA in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-14_

Per una base continuativa, è consigliabile monitorare la CPU e la memoria utilizzata da Lync Server Mobility Service (MCX) e Unified Communications Web API (UCWA). Per monitorare l'utilizzo, è possibile utilizzare gli elementi seguenti:

**Per Unified Communications Web API (UCWA):**

  - Il processo di lavoro di **LyncUcwa** in Gestione Internet Information Services (IIS). Nel riquadro **Processi di lavoro** analizzare le colonne **% CPU** e **Byte privati (KB)** (memoria).

  - Contatori delle prestazioni relativi a **CPU** e **Processore**.

Per la maggior parte delle distribuzioni, l'utilizzo della CPU UCWA dovrebbe essere inferiore al 15% in media. L'utilizzo della memoria deve rientrare nei limiti descritti in [monitoraggio dei limiti di capacità della memoria del server in Lync server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).

Oltre ai contatori di utilizzo della CPU e della memoria, è possibile utilizzare i contatori delle prestazioni seguenti per determinare quando un server è sottoposto a overload con richieste:

  - **Ls: Web – limitazione e autenticazione\\Web – richieste totali nell'elaborazione**, che indica il numero di richieste Web in sospeso sul server. Quando questo contatore raggiunge 10.000, le richieste successive avranno esito negativo, con il messaggio di errore "503-servizio non disponibile".

  - **Le\\richieste di ASP.NET in coda** (devono sempre essere pari a zero).

<div>


> [!NOTE]  
> Se si soddisfano o superano questi valori, è consigliabile rivisitare e ricalcolare la pianificazione della capacità per il corretto dimensionamento della CPU, il numero di core e la memoria dei computer che ospitano i servizi Web.



</div>

**Per il servizio per dispositivi mobili (MCX):**

  - I processi di lavoro di **CSIntMcxAppPool** e **CSExtMcxAppPool** in Gestione Internet Information Services (IIS). Nel riquadro **Processi di lavoro** analizzare le colonne **% CPU** e **Byte privati (KB)** (memoria).

  - Contatori delle prestazioni relativi a **CPU** e **Processore**.

Per la maggior parte delle distribuzioni, l'utilizzo della CPU del servizio per dispositivi mobili deve essere inferiore al 15%, in media. L'utilizzo della memoria deve rientrare nei limiti descritti in [monitoraggio dei limiti di capacità della memoria del server in Lync server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).

Oltre ai contatori di utilizzo della CPU e della memoria, è possibile utilizzare il contatori delle prestazioni ASP.NET seguenti per determinare quando un server è sovraccarico di richieste:

  - **ASP.NET v 2.0.50727\\richiede la versione corrente**, che indica il numero di richieste Web in sospeso sul server. Quando questo contatore raggiunge 5.000, le richieste successive avranno esito negativo con il messaggio di errore "503-servizio non disponibile".

  - **Le\\richieste di ASP.NET in coda** (devono sempre essere pari a zero).

<div>


> [!NOTE]  
> Se si soddisfano o superano questi valori, è consigliabile rivisitare e ricalcolare la pianificazione della capacità per il corretto dimensionamento della CPU, del numero di core e della memoria per i computer che ospitano i servizi Web.



</div>

<div>

## <a name="see-also"></a>Vedere anche


[Monitoraggio dei limiti di capacità della memoria del server in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


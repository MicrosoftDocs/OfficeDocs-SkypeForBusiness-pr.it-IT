---
title: 'Lync Server 2013: monitoraggio del servizio di mobilità e uso di UCWA'
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
ms.openlocfilehash: d4968c1a3b3dc30bdab2a3c19fd8e930da6122cb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756810"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-service-and-ucwa-usage-in-lync-server-2013"></a>Monitoraggio del servizio di mobilità e uso di UCWA in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-14_

In modo continuo, dovresti monitorare la CPU e la memoria usata dal servizio di mobilità di Lync Server (MCX) e dall'API Web Unified Communications (UCWA). Per monitorare l'uso, è possibile usare quanto segue:

**Per Unified Communications Web API (UCWA):**

  - Processo di lavoro di **LyncUcwa** in Gestione Internet Information Services (IIS). Nel riquadro **processi di lavoro** esaminare le colonne **CPU%** e **private bytes (KB)** (memoria).

  - Contatori delle prestazioni della **CPU** e del **processore** .

Per la maggior parte delle distribuzioni, l'uso della CPU UCWA deve essere inferiore al 15% in media. L'utilizzo della memoria deve rientrare nei limiti descritti in [monitoraggio dei limiti della capacità di memoria del server in Lync server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).

Oltre ai contatori di utilizzo della CPU e della memoria, è possibile usare i contatori delle prestazioni seguenti per determinare quando un server è in overload con le richieste:

  - **Ls: Web-limitazione e autenticazione\\Web-totale delle richieste di elaborazione**, che indica il numero di richieste Web in sospeso nel server. Quando questo contatore raggiunge 10.000, le richieste successive avranno esito negativo, con il messaggio di errore "503-servizio non disponibile".

  - **Le\\richieste di ASP.NET in coda** (devono essere sempre pari a zero).

<div>


> [!NOTE]  
> Se si soddisfano o superano questi valori, è necessario rivedere e ricalcolare la pianificazione della capacità per il dimensionamento corretto della CPU, il numero di core e la memoria per i computer che ospitano i servizi Web.



</div>

**Per il servizio mobilità (MCX):**

  - Processi di lavoro di **CSIntMcxAppPool** e **CSExtMcxAppPool** in Gestione Internet Information Services (IIS). Nel riquadro **processi di lavoro** esaminare le colonne **CPU%** e **private bytes (KB)** (memoria).

  - Contatori delle prestazioni della **CPU** e del **processore** .

Per la maggior parte delle distribuzioni, l'uso della CPU del servizio di mobilità deve essere inferiore al 15%, in media. L'utilizzo della memoria deve rientrare nei limiti descritti in [monitoraggio dei limiti della capacità di memoria del server in Lync server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).

Oltre ai contatori di utilizzo della CPU e della memoria, è possibile usare i seguenti contatori delle prestazioni di ASP.NET per determinare quando un server è in overload con le richieste:

  - **ASP.NET v 2.0.50727\\richiede Current**, che indica il numero di richieste Web in sospeso nel server. Quando questo contatore raggiunge 5.000, le richieste successive avranno esito negativo con il messaggio di errore "503-servizio non disponibile".

  - **Le\\richieste di ASP.NET in coda** (devono essere sempre pari a zero).

<div>


> [!NOTE]  
> Se si soddisfano o superano questi valori, è necessario rivedere e ricalcolare la pianificazione della capacità per il dimensionamento corretto della CPU, del numero di core e della memoria per i computer che ospitano i servizi Web.



</div>

<div>

## <a name="see-also"></a>Vedere anche


[Monitoraggio dei limiti della capacità di memoria del server in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


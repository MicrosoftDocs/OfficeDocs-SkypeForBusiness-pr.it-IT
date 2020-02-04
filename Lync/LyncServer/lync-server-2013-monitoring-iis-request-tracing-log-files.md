---
title: 'Lync Server 2013: monitoraggio dei file di log di analisi delle richieste di IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring IIS request tracing log files
ms:assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690034(v=OCS.15)
ms:contentKeyID: 48185215
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d29082fd4f2e988d586501d4d867be0dc23a0c5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765967"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-iis-request-tracing-log-files-in-lync-server-2013"></a><span data-ttu-id="c7d1d-102">Monitoraggio dei file di log della traccia delle richieste di IIS in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7d1d-102">Monitoring IIS request tracing log files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7d1d-103">_**Argomento Ultima modifica:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="c7d1d-103">_**Topic Last Modified:** 2013-02-14_</span></span>

    This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).

<span data-ttu-id="c7d1d-104">Quando si Abilita l'analisi delle richieste di Internet Information Services (IIS) per il servizio di mobilità di Lync Server (MCX), i file di log generati possono utilizzare fino a tre gigabyte di spazio su disco al giorno.</span><span class="sxs-lookup"><span data-stu-id="c7d1d-104">When you enable Internet Information Services (IIS) request tracing for the Lync Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="c7d1d-105">La registrazione della traccia di IIS è abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c7d1d-105">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="c7d1d-106">È consigliabile monitorare i server front-end per assicurarsi che non finiscano nello spazio su disco.</span><span class="sxs-lookup"><span data-stu-id="c7d1d-106">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span>

<span data-ttu-id="c7d1d-107">Per impostazione predefinita, in IIS i file di log vengono archiviati\\in\\%\\SystemDrive% Inetpub log log.</span><span class="sxs-lookup"><span data-stu-id="c7d1d-107">By default, IIS stores the log files at %SystemDrive%\\inetpub\\logs\\LogFiles.</span></span>

<span data-ttu-id="c7d1d-108">Per disattivare la traccia delle richieste di IIS per un intero server, nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="c7d1d-108">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>

    %SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True

<span data-ttu-id="c7d1d-109">Per informazioni dettagliate sul comando **HttpLogging** , vedere [http://go.microsoft.com/fwlink/p/?linkId=234927](http://go.microsoft.com/fwlink/p/?linkid=234927).</span><span class="sxs-lookup"><span data-stu-id="c7d1d-109">For details about the **httpLogging** command, see [http://go.microsoft.com/fwlink/p/?linkId=234927](http://go.microsoft.com/fwlink/p/?linkid=234927).</span></span>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: monitoraggio dei file di registro di traccia delle richieste IIS'
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
ms.openlocfilehash: 76e8734c8cef93191c5e7186240c1b78529916fa
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531923"
---
# <a name="monitoring-iis-request-tracing-log-files-in-lync-server-2013"></a><span data-ttu-id="57f3d-102">Monitoraggio dei file di registro di traccia delle richieste IIS in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57f3d-102">Monitoring IIS request tracing log files in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57f3d-103">_**Ultimo argomento modificato:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="57f3d-103">_**Topic Last Modified:** 2013-02-14_</span></span>

    This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).

<span data-ttu-id="57f3d-104">Quando si Abilita l'analisi delle richieste di Internet Information Services (IIS) per il servizio per dispositivi mobili di Lync Server (MCX), i file di registro generati possono utilizzare fino a tre gigabyte di spazio su disco al giorno.</span><span class="sxs-lookup"><span data-stu-id="57f3d-104">When you enable Internet Information Services (IIS) request tracing for the Lync Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="57f3d-105">La registrazione della traccia IIS è abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="57f3d-105">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="57f3d-106">È necessario monitorare i Front End Server per assicurarsi che non si esaurisca lo spazio su disco.</span><span class="sxs-lookup"><span data-stu-id="57f3d-106">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span>

<span data-ttu-id="57f3d-107">Per impostazione predefinita, i file di registro vengono archiviati in% SystemDrive% \\ Inetpub \\ logs \\ .</span><span class="sxs-lookup"><span data-stu-id="57f3d-107">By default, IIS stores the log files at %SystemDrive%\\inetpub\\logs\\LogFiles.</span></span>

<span data-ttu-id="57f3d-108">Per disattivare la traccia delle richieste di IIS per un intero server, digitare il comando seguente alla riga di comando:</span><span class="sxs-lookup"><span data-stu-id="57f3d-108">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>

    %SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True

<span data-ttu-id="57f3d-109">Per informazioni dettagliate sul comando **HttpLogging** , vedere [https://go.microsoft.com/fwlink/p/?linkId=234927](https://go.microsoft.com/fwlink/p/?linkid=234927) .</span><span class="sxs-lookup"><span data-stu-id="57f3d-109">For details about the **httpLogging** command, see [https://go.microsoft.com/fwlink/p/?linkId=234927](https://go.microsoft.com/fwlink/p/?linkid=234927).</span></span>

</div>

<span> </span>

</div>

</div>

</div>


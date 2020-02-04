---
title: 'Lync Server 2013: backup di archiviazione e monitoraggio di database'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up Archiving and Monitoring databases
ms:assetid: c120db81-b02c-4a4c-90cd-8aca6cff64f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202188(v=OCS.15)
ms:contentKeyID: 51541515
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4092ddc3c86496053cc0ebbb367188490096de4f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-archiving-and-monitoring-databases-in-lync-server-2013"></a><span data-ttu-id="21d85-102">Eseguire il backup di database di archiviazione e monitoraggio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21d85-102">Backing up Archiving and Monitoring databases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21d85-103">_**Argomento Ultima modifica:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="21d85-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="21d85-104">Se è stata distribuita l'archiviazione o il monitoraggio, è necessario eseguire il backup di questi database in base ai criteri di backup di SQL Server dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="21d85-104">If you deployed Archiving or Monitoring, you need to back up these databases according to your organization's SQL Server backup policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="21d85-105">Le impostazioni per l'archiviazione e il monitoraggio vengono supportate quando si esegue il backup dell'Central Management store.</span><span class="sxs-lookup"><span data-stu-id="21d85-105">The settings for Archiving and Monitoring are backed up when you back up the Central Management store.</span></span> <span data-ttu-id="21d85-106">Per informazioni dettagliate, vedere <A href="lync-server-2013-backing-up-core-data-and-settings.md">backup dei dati di base e delle impostazioni in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="21d85-106">For details, see <A href="lync-server-2013-backing-up-core-data-and-settings.md">Backing up core data and settings in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="21d85-107">Per l'archiviazione e il monitoraggio, è possibile usare uno strumento di SQL Server, ad esempio SQL Server Management Studio, per eseguire un backup manuale oppure usare gli strumenti di gestione di SQL Server per pianificare backup automatici e regolari.</span><span class="sxs-lookup"><span data-stu-id="21d85-107">For Archiving and Monitoring, you can use a SQL Server tool such as SQL Server Management Studio to perform a manual backup, or you can use SQL Server management tools to schedule regular, automatic backups.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


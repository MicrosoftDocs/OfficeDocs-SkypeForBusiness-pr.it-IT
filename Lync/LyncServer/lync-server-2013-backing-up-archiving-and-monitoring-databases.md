---
title: 'Lync Server 2013: backup dei database di archiviazione e monitoraggio'
description: 'Lync Server 2013: backup dei database di archiviazione e di monitoraggio.'
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
ms.openlocfilehash: 49b4fa194bffa27a52f32d61a729eeaa31cc0ad3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543762"
---
# <a name="backing-up-archiving-and-monitoring-databases-in-lync-server-2013"></a><span data-ttu-id="e7062-103">Backup dei database di archiviazione e monitoraggio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7062-103">Backing up Archiving and Monitoring databases in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7062-104">_**Ultimo argomento modificato:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="e7062-104">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="e7062-105">Se sono state distribuite le funzionalità di archiviazione o monitoraggio, è necessario eseguire il backup dei database corrispondenti in base ai criteri di backup di SQL Server dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e7062-105">If you deployed Archiving or Monitoring, you need to back up these databases according to your organization's SQL Server backup policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e7062-106">Quando si esegue il backup dell'archivio di gestione centrale, vengono sottoposte a backup le impostazioni per l'archiviazione e il monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="e7062-106">The settings for Archiving and Monitoring are backed up when you back up the Central Management store.</span></span> <span data-ttu-id="e7062-107">Per ulteriori informazioni, vedere <A href="lync-server-2013-backing-up-core-data-and-settings.md">backing up core data and Settings in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e7062-107">For details, see <A href="lync-server-2013-backing-up-core-data-and-settings.md">Backing up core data and settings in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="e7062-108">Per l'archiviazione e il monitoraggio è possibile utilizzare uno strumento di SQL Server come SQL Server Management Studio per eseguire un backup manuale oppure gli strumenti di gestione di SQL Server per pianificare backup automatici regolari.</span><span class="sxs-lookup"><span data-stu-id="e7062-108">For Archiving and Monitoring, you can use a SQL Server tool such as SQL Server Management Studio to perform a manual backup, or you can use SQL Server management tools to schedule regular, automatic backups.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Supporto per l'archiviazione file di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: File storage support
ms:assetid: ed66430d-3c19-4267-938c-956a51005073
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399073(v=OCS.15)
ms:contentKeyID: 48185743
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b870aa22d9dea13e84f045af8fc6fe800fb3d55
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207262"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="file-storage-support-in-lync-server-2013"></a><span data-ttu-id="16b10-102">Supporto per l'archiviazione di file in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16b10-102">File storage support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16b10-103">_**Ultimo argomento modificato:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="16b10-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="16b10-104">Lync Server 2013 utilizza lo stesso archivio file per l'archiviazione di tutti i file.</span><span class="sxs-lookup"><span data-stu-id="16b10-104">Lync Server 2013 uses the same file store for all file storage.</span></span> <span data-ttu-id="16b10-105">Il supporto per l'archiviazione dei file include gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="16b10-105">File storage support includes the following:</span></span>

  - <span data-ttu-id="16b10-106">Condivisione di file per l'archiviazione diretta (DAS) o per una rete di archiviazione (SAN), tra cui il file System distribuito (DFS) e su una matrice ridondante di dischi indipendenti (RAID) per gli archivi di file.</span><span class="sxs-lookup"><span data-stu-id="16b10-106">A file share on either direct attached storage (DAS) or a storage area network (SAN), including Distributed File System (DFS), and on a redundant array of independent disks (RAID) for file stores.</span></span> <span data-ttu-id="16b10-107">Per informazioni dettagliate sui requisiti di archiviazione, vedere [requisiti tecnici per Front End Server, messaggistica istantanea e presenza in Lync server 2013](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) e [requisiti hardware e software per il Director in Lync Server 2013](lync-server-2013-hardware-and-software-requirements-for-the-director.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="16b10-107">For details about storage requirements, see [Technical requirements for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) and [Hardware and software requirements for the Director in Lync Server 2013](lync-server-2013-hardware-and-software-requirements-for-the-director.md) in the Planning documentation.</span></span> <span data-ttu-id="16b10-108">Per informazioni dettagliate sul sistema operativo DFS per Windows Server 2008, vedere la guida dettagliata di DFS per Windows Server 2008 all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835).</span><span class="sxs-lookup"><span data-stu-id="16b10-108">For details about DFS for Windows Server 2008 operating system, see the DFS Step-by-Step Guide for Windows Server 2008 at [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835).</span></span>

  - <span data-ttu-id="16b10-109">Un cluster condiviso per la condivisione file.</span><span class="sxs-lookup"><span data-stu-id="16b10-109">A shared cluster for the file share.</span></span> <span data-ttu-id="16b10-110">Se si utilizza un cluster condiviso, è consigliabile utilizzare i server cluster che eseguono Windows Server 2008 o Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="16b10-110">If you use a shared cluster, you should use cluster servers running Windows Server 2008 or Windows Server 2008 R2.</span></span> <span data-ttu-id="16b10-111">L'utilizzo di server di cluster che eseguono una versione precedente di Windows può causare problemi di autorizzazione che impediscono che alcune funzionalità siano disponibili.</span><span class="sxs-lookup"><span data-stu-id="16b10-111">Using cluster servers running an older version of Windows may result in permission issues that prevent some features from being available.</span></span> <span data-ttu-id="16b10-112">Utilizzare Amministrazione cluster per creare le condivisioni file.</span><span class="sxs-lookup"><span data-stu-id="16b10-112">Use the Cluster Administrator to create the file shares.</span></span> <span data-ttu-id="16b10-113">Per informazioni dettagliate sull'utilizzo dell'amministratore del cluster, vedere l'articolo 284838 della Microsoft Knowledge Base "come creare una condivisione file cluster di server con cluster. [https://go.microsoft.com/fwlink/p/?linkId=140899](https://go.microsoft.com/fwlink/p/?linkid=140899)exe" all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="16b10-113">For details about using the Cluster Administrator, see Microsoft Knowledge Base article 284838, "How to Create a Server Cluster File Share with Cluster.exe" at [https://go.microsoft.com/fwlink/p/?linkId=140899](https://go.microsoft.com/fwlink/p/?linkid=140899).</span></span>

</div>

<span> </span>

</div>

</div>

</div>


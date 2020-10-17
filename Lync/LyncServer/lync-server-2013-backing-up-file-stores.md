---
title: 'Lync Server 2013: backup degli archivi file'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up file stores
ms:assetid: 1a7f4e93-aa3d-461e-878e-2c572baa1293
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202167(v=OCS.15)
ms:contentKeyID: 51541449
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4971b5df8646f20843569ba653cd7a0c274d501
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523163"
---
# <a name="backing-up-file-stores-in-lync-server-2013"></a><span data-ttu-id="b0096-102">Backup degli archivi di file in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0096-102">Backing up file stores in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0096-103">_**Ultimo argomento modificato:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="b0096-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="b0096-104">Il backup degli archivi file di Lync Server include tutti i file e le cartelle utilizzati dai componenti di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b0096-104">Backing up the Lync Server File Stores includes all the files and folders used by Lync Server components.</span></span>

<div>

## <a name="to-back-up-file-stores"></a><span data-ttu-id="b0096-105">Per eseguire il backup degli archivi file</span><span class="sxs-lookup"><span data-stu-id="b0096-105">To back up File Stores</span></span>

1.  <span data-ttu-id="b0096-106">Per trovare le posizioni specifiche degli archivi file di Lync Server, aprire Generatore di topologie e cercare nel nodo **archivi file** .</span><span class="sxs-lookup"><span data-stu-id="b0096-106">To find the specific locations of your Lync Server File Stores, open Topology Builder and look in the **File stores** node.</span></span>

2.  <span data-ttu-id="b0096-107">Utilizzare Robocopy o un altro strumento di gestione del file System per copiare ogni archivio file in $Backup \\ filestore.</span><span class="sxs-lookup"><span data-stu-id="b0096-107">Use Robocopy or another file system management tool to copy each File Store to $Backup\\filestore.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


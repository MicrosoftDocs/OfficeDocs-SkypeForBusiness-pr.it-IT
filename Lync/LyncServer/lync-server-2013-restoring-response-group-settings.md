---
title: 'Lync Server 2013: ripristino delle impostazioni di Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring Response Group settings
ms:assetid: 4f8e1949-925d-4538-be1d-9ac7c06b2aca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202174(v=OCS.15)
ms:contentKeyID: 51541473
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bbde44ac248e59af63a34cfeab6415166994c0b8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208472"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-response-group-settings-in-lync-server-2013"></a><span data-ttu-id="8eb20-102">Ripristino delle impostazioni di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8eb20-102">Restoring Response Group settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8eb20-103">_**Ultimo argomento modificato:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="8eb20-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="8eb20-104">Se è stata distribuita l'applicazione Response Group ed è necessario ripristinare un server di back-end o uno Standard Edition, è necessario ripristinare anche le impostazioni di configurazione di Response Group.</span><span class="sxs-lookup"><span data-stu-id="8eb20-104">If you deployed the Response Group application and you need to restore a Back End Server or a Standard Edition server, you also need to restore the Response Group configuration settings.</span></span>

<div>

## <a name="to-restore-response-group-configuration-settings"></a><span data-ttu-id="8eb20-105">Per ripristinare le impostazioni di configurazione di Response Group</span><span class="sxs-lookup"><span data-stu-id="8eb20-105">To restore Response Group configuration settings</span></span>

1.  <span data-ttu-id="8eb20-106">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="8eb20-106">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<pool FQDN>" -OverwriteOwner -FileName "<path and file name of the backed up file at $Backup>"
    
    <span data-ttu-id="8eb20-107">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8eb20-107">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service: ApplicationServer:pool01.contoso.com" -OverwriteOwner -FileName "C:\RgsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>


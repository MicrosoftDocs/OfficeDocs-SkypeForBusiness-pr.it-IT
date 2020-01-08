---
title: 'Lync Server 2013: ripristino delle impostazioni di Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring Response Group settings
ms:assetid: 4f8e1949-925d-4538-be1d-9ac7c06b2aca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202174(v=OCS.15)
ms:contentKeyID: 51541473
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af4aace2739a2aee8e2f9dbba2a0cb0779f19a3d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979438"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-response-group-settings-in-lync-server-2013"></a><span data-ttu-id="fe249-102">Ripristinare le impostazioni del gruppo di risposte in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe249-102">Restoring Response Group settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe249-103">_**Argomento Ultima modifica:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="fe249-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="fe249-104">Se è stata distribuita l'applicazione Response Group ed è necessario ripristinare un server back-end o un server Standard Edition, è anche necessario ripristinare le impostazioni di configurazione del Response Group.</span><span class="sxs-lookup"><span data-stu-id="fe249-104">If you deployed the Response Group application and you need to restore a Back End Server or a Standard Edition server, you also need to restore the Response Group configuration settings.</span></span>

<div>

## <a name="to-restore-response-group-configuration-settings"></a><span data-ttu-id="fe249-105">Per ripristinare le impostazioni di configurazione di Response Group</span><span class="sxs-lookup"><span data-stu-id="fe249-105">To restore Response Group configuration settings</span></span>

1.  <span data-ttu-id="fe249-106">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="fe249-106">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<pool FQDN>" -OverwriteOwner -FileName "<path and file name of the backed up file at $Backup>"
    
    <span data-ttu-id="fe249-107">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="fe249-107">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service: ApplicationServer:pool01.contoso.com" -OverwriteOwner -FileName "C:\RgsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>


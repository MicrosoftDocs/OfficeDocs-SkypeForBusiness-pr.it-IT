---
title: Verificare le impostazioni di configurazione
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 51c2d1d9-63f7-43ab-88ca-b8913da7cede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204885(v=OCS.15)
ms:contentKeyID: 48184111
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80b84d2c11fee62b0912cc43317ed6716dd33f27
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048250"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a><span data-ttu-id="ba0f4-102">Verificare le impostazioni di configurazione</span><span class="sxs-lookup"><span data-stu-id="ba0f4-102">Verify configuration settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba0f4-103">_**Ultimo argomento modificato:** 2012-09-06_</span><span class="sxs-lookup"><span data-stu-id="ba0f4-103">_**Topic Last Modified:** 2012-09-06_</span></span>

<span data-ttu-id="ba0f4-104">È possibile convalidare la replica delle informazioni di configurazione nel server perimetrale eseguendo il cmdlet **Get-CsManagementStoreReplicationStatus** di lync Server 2013 nel computer interno in cui si trova l'archivio di gestione centrale o in qualsiasi computer aggiunto al dominio in cui è installato lync Server 2013 Core Components (OCSCore. msi).</span><span class="sxs-lookup"><span data-stu-id="ba0f4-104">You can validate the replication of configuration information to the Edge server by running the Lync Server 2013 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located, or on any domain joined computer on which Lync Server 2013 Core Components (OcsCore.msi) is installed.</span></span>

<span data-ttu-id="ba0f4-105">I risultati iniziali possono indicare lo stato "False" anziché "True" per la replica.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="ba0f4-106">In questo caso, eseguire il cmdlet **Invoke-CsManagementStoreReplication** e attendere il completamento della replica prima di eseguire di nuovo **Get-CsManagementStoreReplicationStatus**.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


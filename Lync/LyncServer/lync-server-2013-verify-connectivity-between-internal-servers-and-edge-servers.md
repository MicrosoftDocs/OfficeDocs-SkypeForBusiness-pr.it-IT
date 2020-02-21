---
title: Verificare la connettività tra server interni e server perimetrali
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify connectivity between internal servers and Edge Servers
ms:assetid: 219f706e-2b8a-46c5-b394-c384240eef50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398292(v=OCS.15)
ms:contentKeyID: 48183602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7bd749aea86f610cee2671648e4e2ce1486cfba5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-connectivity-between-internal-servers-and-edge-servers-in-lync-server-2013"></a><span data-ttu-id="db950-102">Verificare la connettività tra server interni e server perimetrali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db950-102">Verify connectivity between internal servers and Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db950-103">_**Ultimo argomento modificato:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="db950-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="db950-104">In Lync Server 2013, era disponibile una procedura guidata di convalida separata che consentiva di convalidare la connettività tra server perimetrali e server interni.</span><span class="sxs-lookup"><span data-stu-id="db950-104">In Lync Server 2013, a separate validation wizard was available to help validate connectivity between Edge Servers and internal servers.</span></span> <span data-ttu-id="db950-105">In Lync Server 2013 la convalida della connettività viene fatta automaticamente quando si installano i server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="db950-105">In Lync Server 2013 validation of connectivity is done automatically when you install your Edge Servers.</span></span>

<span data-ttu-id="db950-106">È possibile convalidare la replica delle informazioni di configurazione nel server perimetrale eseguendo il cmdlet **Get-CsManagementStoreReplicationStatus** di Windows PowerShell nel computer interno in cui si trova l'archivio di gestione centrale (o in qualsiasi computer aggiunto al dominio in cui è installato Lync Server 2013 Core Components (OCSCore. msi).</span><span class="sxs-lookup"><span data-stu-id="db950-106">You can validate the replication of configuration information to the edge by running the Windows PowerShell **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located (or any domain joined computer on which Lync Server 2013 Core Components (OcsCore.msi) is installed.</span></span> <span data-ttu-id="db950-107">I risultati iniziali possono indicare lo stato "False" anziché "True" per la replica.</span><span class="sxs-lookup"><span data-stu-id="db950-107">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="db950-108">In questo caso, eseguire il cmdlet **Invoke-CsManagementStoreReplication** e attendere il completamento della replica prima di eseguire di nuovo **Get-CsManagementStoreReplicationStatus**.</span><span class="sxs-lookup"><span data-stu-id="db950-108">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span>

<span data-ttu-id="db950-109">È possibile verificare la connettività degli utenti esterni separatamente, utilizzando tra l'altro l'analizzatore connettività remota di Office Communications Server per verificare la connettività degli utenti remoti.</span><span class="sxs-lookup"><span data-stu-id="db950-109">You can verify external user connectivity separately, including using the Office Communications Server Remote Connectivity Analyzer to verify remote user connectivity.</span></span> <span data-ttu-id="db950-110">Per ulteriori informazioni, vedere [verificare la connettività per gli utenti esterni in Lync Server 2013](lync-server-2013-verify-connectivity-for-external-users.md).</span><span class="sxs-lookup"><span data-stu-id="db950-110">For details, see [Verify connectivity for external users in Lync Server 2013](lync-server-2013-verify-connectivity-for-external-users.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>


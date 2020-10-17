---
title: 'Lync Server 2013: concessione di autorizzazioni di installazione'
description: 'Lync Server 2013: concessione di autorizzazioni di installazione.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting setup permissions
ms:assetid: 15982bfe-6844-44f6-815a-72dcaf0e4d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398225(v=OCS.15)
ms:contentKeyID: 48183491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5523494219d07907caeefc1bd139c41856effa54
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554482"
---
# <a name="granting-setup-permissions-in-lync-server-2013"></a><span data-ttu-id="d3b08-103">Concessione di autorizzazioni di installazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3b08-103">Granting setup permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3b08-104">_**Ultimo argomento modificato:** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="d3b08-104">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="d3b08-105">È possibile utilizzare il cmdlet **Grant-CsSetupPermission** per aggiungere autorizzazioni Read, Write, ReadSPN e WriteSPN al gruppo RTCUniversalServerAdmins per una determinata unità organizzativa (OU) di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d3b08-105">You can use the **Grant-CsSetupPermission** cmdlet to add Read, Write, ReadSPN, and WriteSPN permissions to the RTCUniversalServerAdmins group for a specified Active Directory organizational unit (OU).</span></span> <span data-ttu-id="d3b08-106">I membri del gruppo RTCUniversalServerAdmins nell'unità organizzativa possono quindi installare i server che eseguono Lync Server 2013 nel dominio specificato senza essere membri del gruppo Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="d3b08-106">Then members of the RTCUniversalServerAdmins group in that OU can install servers running Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="d3b08-107">Utilizzare il cmdlet **Test-CsSetupPermission** per verificare le autorizzazioni impostate mediante il cmdlet **Grant-CsSetupPermission**.</span><span class="sxs-lookup"><span data-stu-id="d3b08-107">Use the **Test-CsSetupPermission** cmdlet to verify the permissions you set up by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<span data-ttu-id="d3b08-108">È possibile utilizzare il cmdlet **Revoke-CsSetupPermission** per rimuovere le autorizzazioni concesse mediante il cmdlet **Grant-CsSetupPermission**.</span><span class="sxs-lookup"><span data-stu-id="d3b08-108">You can use the **Revoke-CsSetupPermission** cmdlet to remove permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-setup-permissions"></a><span data-ttu-id="d3b08-109">Per concedere autorizzazioni di installazione</span><span class="sxs-lookup"><span data-stu-id="d3b08-109">To grant setup permissions</span></span>

1.  <span data-ttu-id="d3b08-110">Accedere a un computer su cui è in esecuzione Lync Server 2013 nel dominio in cui si desidera concedere le autorizzazioni di installazione.</span><span class="sxs-lookup"><span data-stu-id="d3b08-110">Log on to a computer running Lync Server 2013 in the domain where you want to grant setup permissions.</span></span> <span data-ttu-id="d3b08-111">Utilizzare un account membro del gruppo Domain Admins o del gruppo Enterprise Admins se l'unità organizzativa si trova in un altro dominio figlio.</span><span class="sxs-lookup"><span data-stu-id="d3b08-111">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="d3b08-112">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d3b08-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d3b08-113">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="d3b08-113">Run:</span></span>
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="d3b08-p103">È possibile specificare il parametro ComputerOu in base al contesto dei nomi predefinito del dominio specificato, ad esempio CN=computer. In alternativa, è possibile specificare tale parametro come nome distinto (DN) completo dell'unità organizzativa (OU), ad esempio "CN=computer,DC=Contoso,DC=com". In quest'ultimo caso, è necessario specificare un nome distinto dell'unità organizzativa che sia coerente con il dominio specificato.</span><span class="sxs-lookup"><span data-stu-id="d3b08-p103">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers). Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com"). In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="d3b08-117">Se non si specifica il parametro Domain, per impostazione predefinita verrà utilizzato il dominio locale.</span><span class="sxs-lookup"><span data-stu-id="d3b08-117">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-setup-permissions"></a><span data-ttu-id="d3b08-118">Per verificare le autorizzazioni di installazione</span><span class="sxs-lookup"><span data-stu-id="d3b08-118">To verify setup permissions</span></span>

1.  <span data-ttu-id="d3b08-119">Accedere a un computer in cui è in esecuzione Lync Server 2013 nel dominio in cui si desidera verificare le autorizzazioni di installazione concesse utilizzando il cmdlet **Grant-CsSetupPermission** .</span><span class="sxs-lookup"><span data-stu-id="d3b08-119">Log on to a computer running Lync Server 2013 in the domain where you want to verify setup permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="d3b08-120">Utilizzare un account membro del gruppo Domain Admins o del gruppo Enterprise Admins se l'unità organizzativa si trova in un altro dominio figlio.</span><span class="sxs-lookup"><span data-stu-id="d3b08-120">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="d3b08-121">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d3b08-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d3b08-122">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="d3b08-122">Run:</span></span>
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="d3b08-p105">È possibile specificare il parametro ComputerOu in base al contesto dei nomi predefinito del dominio specificato, ad esempio CN=computer. In alternativa, è possibile specificare tale parametro come nome distinto (DN) completo dell'unità organizzativa (OU), ad esempio "CN=computer,DC=Contoso,DC=com". In quest'ultimo caso, è necessario specificare un nome distinto dell'unità organizzativa che sia coerente con il dominio specificato.</span><span class="sxs-lookup"><span data-stu-id="d3b08-p105">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers). Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com"). In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="d3b08-126">Se non si specifica il parametro Domain, per impostazione predefinita verrà utilizzato il dominio locale.</span><span class="sxs-lookup"><span data-stu-id="d3b08-126">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-setup-permissions"></a><span data-ttu-id="d3b08-127">Per revocare le autorizzazioni di installazione</span><span class="sxs-lookup"><span data-stu-id="d3b08-127">To revoke setup permissions</span></span>

1.  <span data-ttu-id="d3b08-128">Accedere a un computer in cui è in esecuzione Lync Server 2013 nel dominio in cui si desidera revocare le autorizzazioni di installazione concesse dal cmdlet **Grant-CsSetupPermission** .</span><span class="sxs-lookup"><span data-stu-id="d3b08-128">Log on to a computer running Lync Server 2013 in the domain where you want to revoke setup permissions that were granted by the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="d3b08-129">Utilizzare un account membro del gruppo Domain Admins o del gruppo Enterprise Admins se l'unità organizzativa si trova in un altro dominio figlio.</span><span class="sxs-lookup"><span data-stu-id="d3b08-129">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="d3b08-130">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d3b08-130">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d3b08-131">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="d3b08-131">Run:</span></span>
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="d3b08-p107">È possibile specificare il parametro ComputerOu in base al contesto dei nomi predefinito del dominio specificato, ad esempio CN=computer. In alternativa, è possibile specificare tale parametro come nome distinto (DN) completo dell'unità organizzativa (OU), ad esempio "CN=computer,DC=Contoso,DC=com". In quest'ultimo caso, è necessario specificare un nome distinto dell'unità organizzativa che sia coerente con il dominio specificato.</span><span class="sxs-lookup"><span data-stu-id="d3b08-p107">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers). Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com"). In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="d3b08-135">Se non si specifica il parametro Domain, per impostazione predefinita verrà utilizzato il dominio locale.</span><span class="sxs-lookup"><span data-stu-id="d3b08-135">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


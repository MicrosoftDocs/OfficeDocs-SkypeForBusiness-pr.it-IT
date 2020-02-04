---
title: 'Lync Server 2013: Concessione di autorizzazioni di installazione'
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
ms.openlocfilehash: 2a4642a9e0c77d9cf3aa77c146ff692a7fa7a6c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763890"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-setup-permissions-in-lync-server-2013"></a><span data-ttu-id="2c0f8-102">Concessione di autorizzazioni di installazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c0f8-102">Granting setup permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c0f8-103">_**Argomento Ultima modifica:** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="2c0f8-103">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="2c0f8-104">Puoi usare il cmdlet **Grant-CsSetupPermission** per aggiungere autorizzazioni di lettura, scrittura, ReadSPN e WriteSPN al gruppo RTCUniversalServerAdmins per un'unità organizzativa di Active Directory specificata.</span><span class="sxs-lookup"><span data-stu-id="2c0f8-104">You can use the **Grant-CsSetupPermission** cmdlet to add Read, Write, ReadSPN, and WriteSPN permissions to the RTCUniversalServerAdmins group for a specified Active Directory organizational unit (OU).</span></span> <span data-ttu-id="2c0f8-105">I membri del gruppo RTCUniversalServerAdmins dell'unità organizzativa possono quindi installare i server che utilizzano Lync Server 2013 nel dominio specificato senza essere membri del gruppo Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="2c0f8-105">Then members of the RTCUniversalServerAdmins group in that OU can install servers running Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="2c0f8-106">Utilizzare il cmdlet **Test-CsSetupPermission** per verificare le autorizzazioni configurate tramite il cmdlet **Grant-CsSetupPermission** .</span><span class="sxs-lookup"><span data-stu-id="2c0f8-106">Use the **Test-CsSetupPermission** cmdlet to verify the permissions you set up by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<span data-ttu-id="2c0f8-107">Puoi usare il cmdlet **Revoke-CsSetupPermission** per rimuovere le autorizzazioni concesse tramite il cmdlet **Grant-CsSetupPermission** .</span><span class="sxs-lookup"><span data-stu-id="2c0f8-107">You can use the **Revoke-CsSetupPermission** cmdlet to remove permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-setup-permissions"></a><span data-ttu-id="2c0f8-108">Per concedere le autorizzazioni di configurazione</span><span class="sxs-lookup"><span data-stu-id="2c0f8-108">To grant setup permissions</span></span>

1.  <span data-ttu-id="2c0f8-109">Accedere a un computer in cui è in uso Lync Server 2013 nel dominio in cui si desidera concedere le autorizzazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="2c0f8-109">Log on to a computer running Lync Server 2013 in the domain where you want to grant setup permissions.</span></span> <span data-ttu-id="2c0f8-110">Usare un account membro del gruppo Domain Admins o dell'Enterprise Admins se l'unità organizzativa si trova in un dominio figlio diverso.</span><span class="sxs-lookup"><span data-stu-id="2c0f8-110">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="2c0f8-111">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="2c0f8-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="2c0f8-112">Eseguire</span><span class="sxs-lookup"><span data-stu-id="2c0f8-112">Run:</span></span>
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="2c0f8-113">Puoi specificare il parametro ComputerOu in relazione al contesto di denominazione predefinito del dominio specificato, ad esempio CN = Computers.</span><span class="sxs-lookup"><span data-stu-id="2c0f8-113">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers).</span></span> <span data-ttu-id="2c0f8-114">In alternativa, puoi specificare questo parametro come nome distinto OU completo (DN), ad esempio "CN = Computers, DC = contoso, DC = com".</span><span class="sxs-lookup"><span data-stu-id="2c0f8-114">Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com").</span></span> <span data-ttu-id="2c0f8-115">In quest'ultimo caso, devi specificare un DN di OU coerente con il dominio specificato.</span><span class="sxs-lookup"><span data-stu-id="2c0f8-115">In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="2c0f8-116">Se non specifichi il parametro Domain, il valore predefinito è il dominio locale.</span><span class="sxs-lookup"><span data-stu-id="2c0f8-116">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-setup-permissions"></a><span data-ttu-id="2c0f8-117">Per verificare le autorizzazioni di configurazione</span><span class="sxs-lookup"><span data-stu-id="2c0f8-117">To verify setup permissions</span></span>

1.  <span data-ttu-id="2c0f8-118">Accedere a un computer che usa Lync Server 2013 nel dominio in cui si vogliono verificare le autorizzazioni di configurazione concesse tramite il cmdlet **Grant-CsSetupPermission** .</span><span class="sxs-lookup"><span data-stu-id="2c0f8-118">Log on to a computer running Lync Server 2013 in the domain where you want to verify setup permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="2c0f8-119">Usare un account membro del gruppo Domain Admins o dell'Enterprise Admins se l'unità organizzativa si trova in un dominio figlio diverso.</span><span class="sxs-lookup"><span data-stu-id="2c0f8-119">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="2c0f8-120">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="2c0f8-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="2c0f8-121">Eseguire</span><span class="sxs-lookup"><span data-stu-id="2c0f8-121">Run:</span></span>
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="2c0f8-122">Puoi specificare il parametro ComputerOu in relazione al contesto di denominazione predefinito del dominio specificato, ad esempio CN = Computers.</span><span class="sxs-lookup"><span data-stu-id="2c0f8-122">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers).</span></span> <span data-ttu-id="2c0f8-123">In alternativa, puoi specificare questo parametro come nome distinto OU completo (DN), ad esempio "CN = Computers, DC = contoso, DC = com".</span><span class="sxs-lookup"><span data-stu-id="2c0f8-123">Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com").</span></span> <span data-ttu-id="2c0f8-124">In quest'ultimo caso, devi specificare un DN di OU coerente con il dominio specificato.</span><span class="sxs-lookup"><span data-stu-id="2c0f8-124">In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="2c0f8-125">Se non specifichi il parametro Domain, il valore predefinito è il dominio locale.</span><span class="sxs-lookup"><span data-stu-id="2c0f8-125">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-setup-permissions"></a><span data-ttu-id="2c0f8-126">Per revocare le autorizzazioni di configurazione</span><span class="sxs-lookup"><span data-stu-id="2c0f8-126">To revoke setup permissions</span></span>

1.  <span data-ttu-id="2c0f8-127">Accedere a un computer in cui è in uso Lync Server 2013 nel dominio in cui si desidera revocare le autorizzazioni di configurazione concesse dal cmdlet **Grant-CsSetupPermission** .</span><span class="sxs-lookup"><span data-stu-id="2c0f8-127">Log on to a computer running Lync Server 2013 in the domain where you want to revoke setup permissions that were granted by the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="2c0f8-128">Usare un account membro del gruppo Domain Admins o dell'Enterprise Admins se l'unità organizzativa si trova in un dominio figlio diverso.</span><span class="sxs-lookup"><span data-stu-id="2c0f8-128">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="2c0f8-129">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="2c0f8-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="2c0f8-130">Eseguire</span><span class="sxs-lookup"><span data-stu-id="2c0f8-130">Run:</span></span>
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="2c0f8-131">Puoi specificare il parametro ComputerOu in relazione al contesto di denominazione predefinito del dominio specificato, ad esempio CN = Computers.</span><span class="sxs-lookup"><span data-stu-id="2c0f8-131">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers).</span></span> <span data-ttu-id="2c0f8-132">In alternativa, puoi specificare questo parametro come nome distinto OU completo (DN), ad esempio "CN = Computers, DC = contoso, DC = com".</span><span class="sxs-lookup"><span data-stu-id="2c0f8-132">Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com").</span></span> <span data-ttu-id="2c0f8-133">In quest'ultimo caso, devi specificare un DN di OU coerente con il dominio specificato.</span><span class="sxs-lookup"><span data-stu-id="2c0f8-133">In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="2c0f8-134">Se non specifichi il parametro Domain, il valore predefinito è il dominio locale.</span><span class="sxs-lookup"><span data-stu-id="2c0f8-134">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


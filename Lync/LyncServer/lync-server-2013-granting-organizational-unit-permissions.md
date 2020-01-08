---
title: 'Lync Server 2013: Concessioni di autorizzazioni per unità organizzative'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Granting organizational unit permissions
ms:assetid: 95ee5ffa-39b1-4d80-87a2-27bb364f7396
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398763(v=OCS.15)
ms:contentKeyID: 48184849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c65ff483fbb9c63d4eaca31eca47c9093d229438
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-organizational-unit-permissions-in-lync-server-2013"></a><span data-ttu-id="ccc4d-102">Concessioni di autorizzazioni per unità organizzative in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccc4d-102">Granting organizational unit permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ccc4d-103">_**Argomento Ultima modifica:** 2012-05-14_</span><span class="sxs-lookup"><span data-stu-id="ccc4d-103">_**Topic Last Modified:** 2012-05-14_</span></span>

<span data-ttu-id="ccc4d-104">Puoi usare il cmdlet **Grant-CsOUPermission** per concedere le autorizzazioni per gli oggetti in unità organizzative specificate in modo che i membri dei gruppi di RTC universale creati dalla preparazione della foresta possano accedervi senza essere membri del gruppo Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="ccc4d-104">You can use the **Grant-CsOuPermission** cmdlet to grant permissions to objects in specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access them without being members of the Domain Admins group.</span></span> <span data-ttu-id="ccc4d-105">Le autorizzazioni aggiunte all'UO specificata sono le stesse che il cmdlet **Enable-CsAdDomain** aggiunge ai contenitori computer e utenti durante la preparazione del dominio.</span><span class="sxs-lookup"><span data-stu-id="ccc4d-105">The permissions added to the specified OU are the same permissions that the **Enable-CsAdDomain** cmdlet adds to the computers and users containers during domain preparation.</span></span>

<span data-ttu-id="ccc4d-106">Utilizzare il cmdlet **Test-CsOUPermission** per verificare le autorizzazioni configurate tramite il cmdlet **Grant-CsOUPermission** .</span><span class="sxs-lookup"><span data-stu-id="ccc4d-106">Use the **Test-CsOuPermission** cmdlet to verify the permissions you set up by using the **Grant-CsOuPermission** cmdlet.</span></span>

<span data-ttu-id="ccc4d-107">Puoi usare il cmdlet **Revoke-CsOUPermission** per rimuovere le autorizzazioni concesse tramite il cmdlet **Grant-CsOUPermission** .</span><span class="sxs-lookup"><span data-stu-id="ccc4d-107">You can use the **Revoke-CsOuPermission** cmdlet to remove permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-ou-permissions"></a><span data-ttu-id="ccc4d-108">Per concedere le autorizzazioni dell'unità organizzativa</span><span class="sxs-lookup"><span data-stu-id="ccc4d-108">To grant OU permissions</span></span>

1.  <span data-ttu-id="ccc4d-109">Accedere a un computer in cui è in uso Lync Server 2013 nel dominio in cui si desidera concedere le autorizzazioni dell'unità organizzativa.</span><span class="sxs-lookup"><span data-stu-id="ccc4d-109">Log on to a computer running Lync Server 2013 in the domain where you want to grant OU permissions.</span></span> <span data-ttu-id="ccc4d-110">Usare un account membro del gruppo Domain Admins o dell'Enterprise Admins se l'unità organizzativa si trova in un dominio figlio diverso.</span><span class="sxs-lookup"><span data-stu-id="ccc4d-110">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="ccc4d-111">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="ccc4d-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ccc4d-112">Eseguire</span><span class="sxs-lookup"><span data-stu-id="ccc4d-112">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="ccc4d-113">Se non specifichi il parametro Domain, il valore predefinito è il dominio locale.</span><span class="sxs-lookup"><span data-stu-id="ccc4d-113">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-ou-permissions"></a><span data-ttu-id="ccc4d-114">Per verificare le autorizzazioni dell'unità organizzativa</span><span class="sxs-lookup"><span data-stu-id="ccc4d-114">To verify OU permissions</span></span>

1.  <span data-ttu-id="ccc4d-115">Accedere a un computer in cui è in uso Lync Server 2013 nel dominio in cui si vogliono verificare le autorizzazioni dell'unità organizzativa concesse tramite il cmdlet **Grant-CsOUPermission** .</span><span class="sxs-lookup"><span data-stu-id="ccc4d-115">Log on to a computer running Lync Server 2013 in the domain where you want to verify OU permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="ccc4d-116">Usare un account membro del gruppo Domain Admins o dell'Enterprise Admins se l'unità organizzativa si trova in un dominio figlio diverso.</span><span class="sxs-lookup"><span data-stu-id="ccc4d-116">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="ccc4d-117">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="ccc4d-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ccc4d-118">Eseguire</span><span class="sxs-lookup"><span data-stu-id="ccc4d-118">Run:</span></span>
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="ccc4d-119">Se non specifichi il parametro Domain, il valore predefinito è il dominio locale.</span><span class="sxs-lookup"><span data-stu-id="ccc4d-119">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-ou-permissions"></a><span data-ttu-id="ccc4d-120">Per revocare le autorizzazioni dell'unità organizzativa</span><span class="sxs-lookup"><span data-stu-id="ccc4d-120">To revoke OU permissions</span></span>

1.  <span data-ttu-id="ccc4d-121">Accedere a un computer in cui è in uso Lync Server 2013 nel dominio in cui si desidera revocare le autorizzazioni dell'unità organizzativa concesse dal cmdlet **Grant-CsOUPermission** .</span><span class="sxs-lookup"><span data-stu-id="ccc4d-121">Log on to a computer running Lync Server 2013 in the domain where you want to revoke OU permissions that were granted by the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="ccc4d-122">Usare un account membro del gruppo Domain Admins o dell'Enterprise Admins se l'unità organizzativa si trova in un dominio figlio diverso.</span><span class="sxs-lookup"><span data-stu-id="ccc4d-122">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="ccc4d-123">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="ccc4d-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ccc4d-124">Eseguire</span><span class="sxs-lookup"><span data-stu-id="ccc4d-124">Run:</span></span>
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="ccc4d-125">Se non specifichi il parametro Domain, il valore predefinito è il dominio locale.</span><span class="sxs-lookup"><span data-stu-id="ccc4d-125">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


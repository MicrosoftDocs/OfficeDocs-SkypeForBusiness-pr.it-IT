---
title: 'Lync Server 2013: concessione di autorizzazioni per le unità organizzative'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting organizational unit permissions
ms:assetid: 95ee5ffa-39b1-4d80-87a2-27bb364f7396
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398763(v=OCS.15)
ms:contentKeyID: 48184849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be8e2e96de97444364cb07169ce4276a7983f158
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146129"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="granting-organizational-unit-permissions-in-lync-server-2013"></a><span data-ttu-id="60267-102">Concessione di autorizzazioni per le unità organizzative in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60267-102">Granting organizational unit permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60267-103">_**Ultimo argomento modificato:** 2012-05-14_</span><span class="sxs-lookup"><span data-stu-id="60267-103">_**Topic Last Modified:** 2012-05-14_</span></span>

<span data-ttu-id="60267-104">È possibile utilizzare il cmdlet **Grant-CsOUPermission** per concedere le autorizzazioni per gli oggetti nelle unità organizzative specificate, in modo che i membri dei gruppi universali RTC creati dalla preparazione della foresta possano accedervi senza essere membri del gruppo Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="60267-104">You can use the **Grant-CsOuPermission** cmdlet to grant permissions to objects in specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access them without being members of the Domain Admins group.</span></span> <span data-ttu-id="60267-105">Le autorizzazioni aggiunte all'unità organizzativa specificata sono le stesse autorizzazioni che il cmdlet **Enable-CsAdDomain** aggiunge ai contenitori dei computer e degli utenti durante la preparazione del dominio.</span><span class="sxs-lookup"><span data-stu-id="60267-105">The permissions added to the specified OU are the same permissions that the **Enable-CsAdDomain** cmdlet adds to the computers and users containers during domain preparation.</span></span>

<span data-ttu-id="60267-106">Utilizzare il cmdlet **Test-CsOUPermission** per verificare le autorizzazioni impostate utilizzando il cmdlet **Grant-CsOUPermission** .</span><span class="sxs-lookup"><span data-stu-id="60267-106">Use the **Test-CsOuPermission** cmdlet to verify the permissions you set up by using the **Grant-CsOuPermission** cmdlet.</span></span>

<span data-ttu-id="60267-107">È possibile utilizzare il cmdlet **Revoke-CsOUPermission** per rimuovere le autorizzazioni concesse utilizzando il cmdlet **Grant-CsOUPermission** .</span><span class="sxs-lookup"><span data-stu-id="60267-107">You can use the **Revoke-CsOuPermission** cmdlet to remove permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-ou-permissions"></a><span data-ttu-id="60267-108">Per concedere le autorizzazioni per le unità organizzative</span><span class="sxs-lookup"><span data-stu-id="60267-108">To grant OU permissions</span></span>

1.  <span data-ttu-id="60267-109">Accedere a un computer in cui è in esecuzione Lync Server 2013 nel dominio in cui si desidera concedere le autorizzazioni per l'unità organizzativa.</span><span class="sxs-lookup"><span data-stu-id="60267-109">Log on to a computer running Lync Server 2013 in the domain where you want to grant OU permissions.</span></span> <span data-ttu-id="60267-110">Utilizzare un account membro del gruppo Domain Admins o del gruppo Enterprise Admins se l'unità organizzativa si trova in un altro dominio figlio.</span><span class="sxs-lookup"><span data-stu-id="60267-110">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="60267-111">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="60267-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="60267-112">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="60267-112">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="60267-113">Se non si specifica il parametro Domain, per impostazione predefinita verrà utilizzato il dominio locale.</span><span class="sxs-lookup"><span data-stu-id="60267-113">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-ou-permissions"></a><span data-ttu-id="60267-114">Per verificare le autorizzazioni dell'unità organizzativa</span><span class="sxs-lookup"><span data-stu-id="60267-114">To verify OU permissions</span></span>

1.  <span data-ttu-id="60267-115">Accedere a un computer in cui è in esecuzione Lync Server 2013 nel dominio in cui si desidera verificare le autorizzazioni dell'unità organizzativa concesse utilizzando il cmdlet **Grant-CsOUPermission** .</span><span class="sxs-lookup"><span data-stu-id="60267-115">Log on to a computer running Lync Server 2013 in the domain where you want to verify OU permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="60267-116">Utilizzare un account membro del gruppo Domain Admins o del gruppo Enterprise Admins se l'unità organizzativa si trova in un altro dominio figlio.</span><span class="sxs-lookup"><span data-stu-id="60267-116">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="60267-117">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="60267-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="60267-118">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="60267-118">Run:</span></span>
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="60267-119">Se non si specifica il parametro Domain, per impostazione predefinita verrà utilizzato il dominio locale.</span><span class="sxs-lookup"><span data-stu-id="60267-119">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-ou-permissions"></a><span data-ttu-id="60267-120">Per revocare le autorizzazioni per le unità organizzative</span><span class="sxs-lookup"><span data-stu-id="60267-120">To revoke OU permissions</span></span>

1.  <span data-ttu-id="60267-121">Accedere a un computer in cui è in esecuzione Lync Server 2013 nel dominio in cui si desidera revocare le autorizzazioni dell'unità organizzativa concesse dal cmdlet **Grant-CsOUPermission** .</span><span class="sxs-lookup"><span data-stu-id="60267-121">Log on to a computer running Lync Server 2013 in the domain where you want to revoke OU permissions that were granted by the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="60267-122">Utilizzare un account membro del gruppo Domain Admins o del gruppo Enterprise Admins se l'unità organizzativa si trova in un altro dominio figlio.</span><span class="sxs-lookup"><span data-stu-id="60267-122">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="60267-123">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="60267-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="60267-124">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="60267-124">Run:</span></span>
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="60267-125">Se non si specifica il parametro Domain, per impostazione predefinita verrà utilizzato il dominio locale.</span><span class="sxs-lookup"><span data-stu-id="60267-125">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


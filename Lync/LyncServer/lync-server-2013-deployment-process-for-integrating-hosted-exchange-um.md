---
title: "Lync Server 2013: processo di distribuzione per l'integrazione della messaggistica unificata di Exchange ospitata"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for integrating hosted Exchange UM with Lync Server
ms:assetid: dbec9c38-7f66-419d-b8c3-c61380052cac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398968(v=OCS.15)
ms:contentKeyID: 48185586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfd58efd994e7034253fd3314e66d956e3259bcb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213522"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-hosted-exchange-um-with-lync-server-2013"></a><span data-ttu-id="7d203-102">Processo di distribuzione per l'integrazione della messaggistica unificata di Exchange ospitata con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d203-102">Deployment process for integrating hosted Exchange UM with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d203-103">_**Ultimo argomento modificato:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="7d203-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="7d203-104">Per una pianificazione efficace dell'integrazione di Lync Server 2013 con messaggistica unificata di Exchange ospitata, è necessario tenere conto di quanto segue:</span><span class="sxs-lookup"><span data-stu-id="7d203-104">Effective planning for integrating Lync Server 2013 with hosted Exchange Unified Messaging (UM) requires that you take into account the following:</span></span>

  - <span data-ttu-id="7d203-105">Prerequisiti per l'integrazione di Lync Server 2013 con la messaggistica unificata di Exchange ospitata</span><span class="sxs-lookup"><span data-stu-id="7d203-105">Prerequisites for integrating Lync Server 2013 with hosted Exchange UM</span></span>

  - <span data-ttu-id="7d203-106">Passaggi necessari durante il processo di integrazione</span><span class="sxs-lookup"><span data-stu-id="7d203-106">Steps required during the integration process</span></span>

<div>

## <a name="deployment-prerequisites-for-integrating-with-hosted-exchange-um"></a><span data-ttu-id="7d203-107">Prerequisiti di distribuzione per l'integrazione con la messaggistica unificata di Exchange ospitata</span><span class="sxs-lookup"><span data-stu-id="7d203-107">Deployment Prerequisites for Integrating with Hosted Exchange UM</span></span>

<span data-ttu-id="7d203-108">Prima di iniziare il processo di integrazione, è necessario che sia già stato distribuito Lync Server 2013 (almeno un pool Front end o un server Standard Edition), un server perimetrale e client Lync 2013 o Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="7d203-108">Before you can begin the integration process, you must already have deployed Lync Server 2013 (at a minimum, a Front End pool or a Standard Edition server), an Edge Server, and Lync 2013 or Lync 2010 clients.</span></span>

</div>

<div>

## <a name="integration-process"></a><span data-ttu-id="7d203-109">Processo di integrazione</span><span class="sxs-lookup"><span data-stu-id="7d203-109">Integration Process</span></span>

<span data-ttu-id="7d203-110">Nella tabella seguente viene fornita una panoramica del processo di integrazione della messaggistica unificata di Exchange ospitata.</span><span class="sxs-lookup"><span data-stu-id="7d203-110">The following table provides an overview of the hosted Exchange UM integration process.</span></span> <span data-ttu-id="7d203-111">Per informazioni dettagliate sulla procedura di distribuzione, vedere [providing Lync Server 2013 Users Voice mail sulla messaggistica unificata di Exchange ospitata](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="7d203-111">For details about deployment steps, see [Providing Lync Server 2013 users voice mail on hosted Exchange UM](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7d203-112">Fase</span><span class="sxs-lookup"><span data-stu-id="7d203-112">Phase</span></span></th>
<th><span data-ttu-id="7d203-113">Passaggi</span><span class="sxs-lookup"><span data-stu-id="7d203-113">Steps</span></span></th>
<th><span data-ttu-id="7d203-114">Diritti e autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="7d203-114">Rights and permissions</span></span></th>
<th><span data-ttu-id="7d203-115">Documentazione relativa alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="7d203-115">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7d203-116">Configurare il server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="7d203-116">Configure the Edge Server.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="7d203-117">Configurare il server perimetrale per la federazione.</span><span class="sxs-lookup"><span data-stu-id="7d203-117">Configure the Edge Server for federation.</span></span></p></li>
<li><p><span data-ttu-id="7d203-118">Replicare manualmente i dati nel server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="7d203-118">Manually replicate data to the Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="7d203-119">Configurare il provider di hosting nel server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="7d203-119">Configure the hosting provider on the Edge Server.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="7d203-120">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="7d203-120">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="7d203-121"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Configurare il server perimetrale per l'integrazione con la messaggistica unificata di Exchange ospitata</a></span><span class="sxs-lookup"><span data-stu-id="7d203-121"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Configure the Edge Server for integration with hosted Exchange UM</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d203-122">Configurare i criteri di segreteria telefonica ospitata.</span><span class="sxs-lookup"><span data-stu-id="7d203-122">Configure hosted voice mail policy.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="7d203-123">Modificare il criterio di segreteria telefonica ospitata globale o creare un nuovo criterio di segreteria telefonica ospitata con ambito sito o per utente.</span><span class="sxs-lookup"><span data-stu-id="7d203-123">Either modify the global hosted voice mail policy or create a new hosted voice mail policy with Site or Per-User scope.</span></span></p></li>
<li><p><span data-ttu-id="7d203-124">Per i criteri con ambito per utente, assegnare il criterio agli utenti o ai gruppi.</span><span class="sxs-lookup"><span data-stu-id="7d203-124">For policies with Per-User scope, assign the policy to users or groups.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="7d203-125">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="7d203-125">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="7d203-126"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Gestire i criteri di segreteria telefonica ospitata in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7d203-126"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage hosted voice mail policies in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d203-127">Abilitare gli utenti per la segreteria telefonica ospitata.</span><span class="sxs-lookup"><span data-stu-id="7d203-127">Enable users for hosted voice mail.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7d203-128">Configurare gli account utente per gli utenti le cui cassette postali si trovano in un servizio di Exchange ospitato.</span><span class="sxs-lookup"><span data-stu-id="7d203-128">Configure user accounts for users whose mailboxes are on a hosted Exchange service.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7d203-129">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="7d203-129">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="7d203-130"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Abilitare gli utenti per la segreteria telefonica ospitata in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7d203-130"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Enable users for hosted voice mail in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d203-131">Configurare gli oggetti contatto ospitati.</span><span class="sxs-lookup"><span data-stu-id="7d203-131">Configure hosted contact objects.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="7d203-132">Creare gli oggetti contatto dell'operatore automatico per la messaggistica unificata di Exchange ospitata.</span><span class="sxs-lookup"><span data-stu-id="7d203-132">Create auto-attendant Contact objects for hosted Exchange UM.</span></span></p></li>
<li><p><span data-ttu-id="7d203-133">Creare oggetti contatto accesso sottoscrittore per la messaggistica unificata di Exchange ospitata.</span><span class="sxs-lookup"><span data-stu-id="7d203-133">Create Subscriber Access contact objects for hosted Exchange UM.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="7d203-134">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="7d203-134">RTCUniversalUserAdmins</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="7d203-135">Per creare, modificare o rimuovere oggetti contatto, l'utente che esegue il cmdlet New-CsExUmContact, Set-CsExUmContact o Remove-CsExUmContact deve disporre dell'autorizzazione corretta per l'unità organizzativa di Active Directory in cui sono archiviati i nuovi oggetti contatto.</span><span class="sxs-lookup"><span data-stu-id="7d203-135">To create, modify or remove contact objects, the user who runs the New-CsExUmContact, Set-CsExUmContact or Remove-CsExUmContact cmdlet must have the correct permission to the Active Directory organizational unit where the new contact objects are stored.</span></span> <span data-ttu-id="7d203-136">Questa autorizzazione può essere concessa eseguendo il cmdlet Grant-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="7d203-136">This permission can be granted by running the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="7d203-137">Per informazioni dettagliate, vedere la documentazione relativa a Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="7d203-137">For details, see the Lync Server Management Shell documentation.</span></span>


</div></td>
<td><p><span data-ttu-id="7d203-138"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Creare oggetti contatto per la messaggistica unificata di Exchange ospitata in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7d203-138"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Create contact objects for hosted Exchange UM in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: "Lync Server 2013: Processo di distribuzione per l'integrazione della messaggistica unificata di Exchange ospitata"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for integrating hosted Exchange UM with Lync Server
ms:assetid: dbec9c38-7f66-419d-b8c3-c61380052cac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398968(v=OCS.15)
ms:contentKeyID: 48185586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6269efd85261c702c77568fac67c96034ba01a71
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978503"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-hosted-exchange-um-with-lync-server-2013"></a><span data-ttu-id="37048-102">Processo di distribuzione per l'integrazione della messaggistica unificata di Exchange ospitata con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37048-102">Deployment process for integrating hosted Exchange UM with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37048-103">_**Argomento Ultima modifica:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="37048-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="37048-104">Una pianificazione efficace per l'integrazione di Lync Server 2013 con messaggistica unificata di Exchange ospitata richiede che si prenda in considerazione le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="37048-104">Effective planning for integrating Lync Server 2013 with hosted Exchange Unified Messaging (UM) requires that you take into account the following:</span></span>

  - <span data-ttu-id="37048-105">Prerequisiti per l'integrazione di Lync Server 2013 con UM ospitata di Exchange</span><span class="sxs-lookup"><span data-stu-id="37048-105">Prerequisites for integrating Lync Server 2013 with hosted Exchange UM</span></span>

  - <span data-ttu-id="37048-106">Passaggi necessari durante il processo di integrazione</span><span class="sxs-lookup"><span data-stu-id="37048-106">Steps required during the integration process</span></span>

<div>

## <a name="deployment-prerequisites-for-integrating-with-hosted-exchange-um"></a><span data-ttu-id="37048-107">Prerequisiti di distribuzione per l'integrazione con la messaggistica unificata di Exchange ospitata</span><span class="sxs-lookup"><span data-stu-id="37048-107">Deployment Prerequisites for Integrating with Hosted Exchange UM</span></span>

<span data-ttu-id="37048-108">Prima di iniziare il processo di integrazione, è necessario che sia già stato distribuito Lync Server 2013 (almeno un pool Front-end o un server Standard Edition), un server perimetrale e i client Lync 2013 o Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="37048-108">Before you can begin the integration process, you must already have deployed Lync Server 2013 (at a minimum, a Front End pool or a Standard Edition server), an Edge Server, and Lync 2013 or Lync 2010 clients.</span></span>

</div>

<div>

## <a name="integration-process"></a><span data-ttu-id="37048-109">Processo di integrazione</span><span class="sxs-lookup"><span data-stu-id="37048-109">Integration Process</span></span>

<span data-ttu-id="37048-110">La tabella seguente offre una panoramica del processo di integrazione della messaggistica unificata di Exchange ospitata.</span><span class="sxs-lookup"><span data-stu-id="37048-110">The following table provides an overview of the hosted Exchange UM integration process.</span></span> <span data-ttu-id="37048-111">Per informazioni dettagliate sulla procedura di distribuzione, vedere [fornire agli utenti di Lync Server 2013 la segreteria telefonica di Exchange ospitata](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="37048-111">For details about deployment steps, see [Providing Lync Server 2013 users voice mail on hosted Exchange UM](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="37048-112">Fase</span><span class="sxs-lookup"><span data-stu-id="37048-112">Phase</span></span></th>
<th><span data-ttu-id="37048-113">Passaggi</span><span class="sxs-lookup"><span data-stu-id="37048-113">Steps</span></span></th>
<th><span data-ttu-id="37048-114">Diritti e autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="37048-114">Rights and permissions</span></span></th>
<th><span data-ttu-id="37048-115">Documentazione di distribuzione</span><span class="sxs-lookup"><span data-stu-id="37048-115">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="37048-116">Configurare il server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="37048-116">Configure the Edge Server.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="37048-117">Configurare il server perimetrale per la federazione.</span><span class="sxs-lookup"><span data-stu-id="37048-117">Configure the Edge Server for federation.</span></span></p></li>
<li><p><span data-ttu-id="37048-118">Replicare manualmente i dati nel server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="37048-118">Manually replicate data to the Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="37048-119">Configurare il provider di hosting nel server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="37048-119">Configure the hosting provider on the Edge Server.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="37048-120">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="37048-120">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="37048-121"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Configurare il server perimetrale per l'integrazione con la messaggistica unificata di Exchange ospitata</a></span><span class="sxs-lookup"><span data-stu-id="37048-121"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Configure the Edge Server for integration with hosted Exchange UM</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37048-122">Configurare i criteri di segreteria telefonica ospitata.</span><span class="sxs-lookup"><span data-stu-id="37048-122">Configure hosted voice mail policy.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="37048-123">Modificare i criteri di segreteria telefonica ospitata globale o creare un nuovo criterio di segreteria telefonica ospitata con ambito sito o per utente.</span><span class="sxs-lookup"><span data-stu-id="37048-123">Either modify the global hosted voice mail policy or create a new hosted voice mail policy with Site or Per-User scope.</span></span></p></li>
<li><p><span data-ttu-id="37048-124">Per i criteri con ambito per utente, assegnare i criteri agli utenti o ai gruppi.</span><span class="sxs-lookup"><span data-stu-id="37048-124">For policies with Per-User scope, assign the policy to users or groups.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="37048-125">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="37048-125">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="37048-126"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Gestire i criteri di segreteria telefonica ospitata in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="37048-126"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage hosted voice mail policies in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37048-127">Abilitare gli utenti per la segreteria telefonica ospitata.</span><span class="sxs-lookup"><span data-stu-id="37048-127">Enable users for hosted voice mail.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="37048-128">Configurare gli account utente per gli utenti le cui cassette postali si trovano in un servizio ospitato di Exchange.</span><span class="sxs-lookup"><span data-stu-id="37048-128">Configure user accounts for users whose mailboxes are on a hosted Exchange service.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="37048-129">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="37048-129">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="37048-130"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Abilitare gli utenti per la segreteria telefonica ospitata in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="37048-130"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Enable users for hosted voice mail in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37048-131">Configurare gli oggetti contatto ospitati.</span><span class="sxs-lookup"><span data-stu-id="37048-131">Configure hosted contact objects.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="37048-132">Creare oggetti contatto di operatore automatico per la messaggistica unificata di Exchange ospitata.</span><span class="sxs-lookup"><span data-stu-id="37048-132">Create auto-attendant Contact objects for hosted Exchange UM.</span></span></p></li>
<li><p><span data-ttu-id="37048-133">Creare oggetti contatto di accesso del Sottoscrittore per UM di Exchange ospitata.</span><span class="sxs-lookup"><span data-stu-id="37048-133">Create Subscriber Access contact objects for hosted Exchange UM.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="37048-134">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="37048-134">RTCUniversalUserAdmins</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="37048-135">Per creare, modificare o rimuovere oggetti contatto, l'utente che esegue il cmdlet New-CsExUmContact, Set-CsExUmContact o Remove-CsExUmContact deve avere l'autorizzazione corretta per l'unità organizzativa di Active Directory in cui sono archiviati i nuovi oggetti contatto.</span><span class="sxs-lookup"><span data-stu-id="37048-135">To create, modify or remove contact objects, the user who runs the New-CsExUmContact, Set-CsExUmContact or Remove-CsExUmContact cmdlet must have the correct permission to the Active Directory organizational unit where the new contact objects are stored.</span></span> <span data-ttu-id="37048-136">Questa autorizzazione può essere concessa eseguendo il cmdlet Grant-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="37048-136">This permission can be granted by running the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="37048-137">Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="37048-137">For details, see the Lync Server Management Shell documentation.</span></span>


</div></td>
<td><p><span data-ttu-id="37048-138"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Creare oggetti contatto per la messaggistica unificata di Exchange ospitata in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="37048-138"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Create contact objects for hosted Exchange UM in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


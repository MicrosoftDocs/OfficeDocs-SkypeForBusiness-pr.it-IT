---
title: 'Lync Server 2013: checklist di distribuzione per il controllo di ammissione di chiamata'
description: 'Lync Server 2013: checklist di distribuzione per il controllo di ammissione di chiamata.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for call admission control
ms:assetid: 7e56a169-3e63-44ab-bf28-1fdeb52381c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398631(v=OCS.15)
ms:contentKeyID: 48184621
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea5b16d41228faf01637e7e0d78f5ce56f950a19
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557692"
---
# <a name="deployment-checklist-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="e777d-103">Checklist di distribuzione per il controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e777d-103">Deployment checklist for call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e777d-104">_**Ultimo argomento modificato:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="e777d-104">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="e777d-105">Per una pianificazione efficace del servizio Controllo di ammissione di chiamata è necessario prendere in considerazione quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e777d-105">To plan effectively for call admission control (CAC), you need to consider the following:</span></span>

  - <span data-ttu-id="e777d-106">Prerequisiti per la distribuzione del servizio Controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="e777d-106">Prerequisites for deploying CAC.</span></span>

  - <span data-ttu-id="e777d-107">Informazioni necessarie per il servizio Controllo di ammissione di chiamata e decisioni che devono essere prese prima di iniziare la distribuzione</span><span class="sxs-lookup"><span data-stu-id="e777d-107">Information required for CAC and configuration decisions that you must make in advance of deployment.</span></span>

<div>

## <a name="deployment-prerequisites-for-call-admission-control"></a><span data-ttu-id="e777d-108">Prerequisiti per la distribuzione del servizio Controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="e777d-108">Deployment Prerequisites for Call Admission Control</span></span>

<span data-ttu-id="e777d-109">Prima di distribuire il controllo di ammissione di chiamata, è necessario che siano già stati distribuiti i server interni di Lync Server 2013, tra cui un pool Front end o un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e777d-109">Before you deploy call admission control, you must already have deployed your Lync Server 2013 internal servers, including either a Front End pool or a Standard Edition server.</span></span>

</div>

<div>

## <a name="information-requirements-for-call-admission-control"></a><span data-ttu-id="e777d-110">Informazioni necessarie per il servizio Controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="e777d-110">Information Requirements for Call Admission Control</span></span>

<span data-ttu-id="e777d-111">Nella tabella seguente sono riepilogate le informazioni necessarie per la distribuzione del servizio Controllo di ammissione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="e777d-111">The following table summarizes the required information for deploying call admission control.</span></span>

### <a name="information-requirements-for-call-admission-control-deployment"></a><span data-ttu-id="e777d-112">Informazioni necessarie per la distribuzione del servizio Controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="e777d-112">Information Requirements for Call Admission Control Deployment</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e777d-113">Informazioni</span><span class="sxs-lookup"><span data-stu-id="e777d-113">Information</span></span></th>
<th><span data-ttu-id="e777d-114">Riepilogo delle informazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="e777d-114">Summary of Information Required</span></span></th>
<th><span data-ttu-id="e777d-115">Documentazione</span><span class="sxs-lookup"><span data-stu-id="e777d-115">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e777d-116">Funzionalità di Lync Server necessarie per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="e777d-116">Lync Server capabilities required by your organization</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e777d-117">Funzionalità da supportare nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="e777d-117">Capabilities to be supported by your organization</span></span></p></li>
<li><p><span data-ttu-id="e777d-118">Funzionalità da abilitare per i singoli utenti</span><span class="sxs-lookup"><span data-stu-id="e777d-118">Capabilities to be enabled for individual users</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e777d-119"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Definizione dei requisiti per il controllo di ammissione di chiamata in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e777d-119"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e777d-120">Topologie e componenti da distribuire</span><span class="sxs-lookup"><span data-stu-id="e777d-120">Topologies and components to be deployed</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e777d-121">I componenti correlati a CAC vengono installati automaticamente come parte di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e777d-121">CAC related components are automatically installed as part of Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e777d-122"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Definizione dei requisiti per il controllo di ammissione di chiamata in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e777d-122"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e777d-123">Requisiti di sistema</span><span class="sxs-lookup"><span data-stu-id="e777d-123">System requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e777d-124">Requisiti hardware</span><span class="sxs-lookup"><span data-stu-id="e777d-124">Hardware requirements</span></span></p></li>
<li><p><span data-ttu-id="e777d-125">Requisiti software</span><span class="sxs-lookup"><span data-stu-id="e777d-125">Software requirements</span></span></p></li>
<li><p><span data-ttu-id="e777d-126">Requisiti di collocazione</span><span class="sxs-lookup"><span data-stu-id="e777d-126">Collocation requirements</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e777d-127"><a href="lync-server-2013-determining-your-system-requirements.md">Determinazione dei requisiti di sistema per Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e777d-127"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e777d-128">Requisiti dell'infrastruttura</span><span class="sxs-lookup"><span data-stu-id="e777d-128">Infrastructure requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e777d-129">Per il Controllo di ammissione di chiamata non esistono requisiti dell'infrastruttura specifici</span><span class="sxs-lookup"><span data-stu-id="e777d-129">No specific infrastructure requirements are necessary for CAC</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e777d-130"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Requisiti dell'infrastruttura per il controllo di ammissione di chiamata in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e777d-130"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Infrastructure requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e777d-131">Requisiti dell'interfaccia di rete</span><span class="sxs-lookup"><span data-stu-id="e777d-131">Network interface requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e777d-132">Informazioni sull'interfaccia interna ed esterna</span><span class="sxs-lookup"><span data-stu-id="e777d-132">Internal and external interface information</span></span></p></li>
<li><p><span data-ttu-id="e777d-133">Informazioni sul routing (incluse le informazioni sul Blog di NextHop nel <a href="https://go.microsoft.com/fwlink/p/?linkid=203149">https://go.microsoft.com/fwlink/p/?LinkId=203149</a> canale di risposta dei clienti del team di Microsoft Lync Server)</span><span class="sxs-lookup"><span data-stu-id="e777d-133">Routing information (including information on the NextHop blog at <a href="https://go.microsoft.com/fwlink/p/?linkid=203149">https://go.microsoft.com/fwlink/p/?LinkId=203149</a>, Microsoft Lync Server team’s customer response channel)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e777d-134"><a href="lync-server-2013-deploying-external-user-access.md">Distribuzione dell'accesso degli utenti esterni in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e777d-134"><a href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e777d-135">Strategia di distribuzione</span><span class="sxs-lookup"><span data-stu-id="e777d-135">Deployment strategy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e777d-136">Sequenza di distribuzione</span><span class="sxs-lookup"><span data-stu-id="e777d-136">Deployment sequence</span></span></p></li>
<li><p><span data-ttu-id="e777d-137">Gruppo di lavoro o dominio</span><span class="sxs-lookup"><span data-stu-id="e777d-137">Workgroup or domain</span></span></p></li>
<li><p><span data-ttu-id="e777d-138">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="e777d-138">Security</span></span></p></li>
<li><p><span data-ttu-id="e777d-139">Monitoraggio e controllo</span><span class="sxs-lookup"><span data-stu-id="e777d-139">Monitoring and auditing</span></span></p></li>
<li><p><span data-ttu-id="e777d-140">Considerazioni sull'hardware</span><span class="sxs-lookup"><span data-stu-id="e777d-140">Hardware considerations</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e777d-141"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Procedure consigliate per il controllo di ammissione di chiamata in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e777d-141"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Best practices for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e777d-142">Processo di distribuzione</span><span class="sxs-lookup"><span data-stu-id="e777d-142">Deployment process</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e777d-143">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="e777d-143">Prerequisites</span></span></p></li>
<li><p><span data-ttu-id="e777d-144">Informazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="e777d-144">Information requirements</span></span></p></li>
<li><p><span data-ttu-id="e777d-145">Processo e procedure</span><span class="sxs-lookup"><span data-stu-id="e777d-145">Process and procedures</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e777d-146"><a href="lync-server-2013-configure-call-admission-control.md">Configurare il controllo di ammissione di chiamata in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e777d-146"><a href="lync-server-2013-configure-call-admission-control.md">Configure call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


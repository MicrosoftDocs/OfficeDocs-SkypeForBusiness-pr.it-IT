---
title: 'Lync Server 2013: checklist di distribuzione per il controllo di ammissione di chiamata'
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
ms.openlocfilehash: 13d9591ad8dfed90373fedc8adfb3a3c3c44eb57
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529143"
---
# <a name="deployment-checklist-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="6a7e9-102">Checklist di distribuzione per il controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a7e9-102">Deployment checklist for call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a7e9-103">_**Ultimo argomento modificato:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="6a7e9-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="6a7e9-104">Per una pianificazione efficace del servizio Controllo di ammissione di chiamata è necessario prendere in considerazione quanto segue:</span><span class="sxs-lookup"><span data-stu-id="6a7e9-104">To plan effectively for call admission control (CAC), you need to consider the following:</span></span>

  - <span data-ttu-id="6a7e9-105">Prerequisiti per la distribuzione del servizio Controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="6a7e9-105">Prerequisites for deploying CAC.</span></span>

  - <span data-ttu-id="6a7e9-106">Informazioni necessarie per il servizio Controllo di ammissione di chiamata e decisioni che devono essere prese prima di iniziare la distribuzione</span><span class="sxs-lookup"><span data-stu-id="6a7e9-106">Information required for CAC and configuration decisions that you must make in advance of deployment.</span></span>

<div>

## <a name="deployment-prerequisites-for-call-admission-control"></a><span data-ttu-id="6a7e9-107">Prerequisiti per la distribuzione del servizio Controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="6a7e9-107">Deployment Prerequisites for Call Admission Control</span></span>

<span data-ttu-id="6a7e9-108">Prima di distribuire il controllo di ammissione di chiamata, è necessario che siano già stati distribuiti i server interni di Lync Server 2013, tra cui un pool Front end o un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="6a7e9-108">Before you deploy call admission control, you must already have deployed your Lync Server 2013 internal servers, including either a Front End pool or a Standard Edition server.</span></span>

</div>

<div>

## <a name="information-requirements-for-call-admission-control"></a><span data-ttu-id="6a7e9-109">Informazioni necessarie per il servizio Controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="6a7e9-109">Information Requirements for Call Admission Control</span></span>

<span data-ttu-id="6a7e9-110">Nella tabella seguente sono riepilogate le informazioni necessarie per la distribuzione del servizio Controllo di ammissione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="6a7e9-110">The following table summarizes the required information for deploying call admission control.</span></span>

### <a name="information-requirements-for-call-admission-control-deployment"></a><span data-ttu-id="6a7e9-111">Informazioni necessarie per la distribuzione del servizio Controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="6a7e9-111">Information Requirements for Call Admission Control Deployment</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6a7e9-112">Informazioni</span><span class="sxs-lookup"><span data-stu-id="6a7e9-112">Information</span></span></th>
<th><span data-ttu-id="6a7e9-113">Riepilogo delle informazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="6a7e9-113">Summary of Information Required</span></span></th>
<th><span data-ttu-id="6a7e9-114">Documentazione</span><span class="sxs-lookup"><span data-stu-id="6a7e9-114">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6a7e9-115">Funzionalità di Lync Server necessarie per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="6a7e9-115">Lync Server capabilities required by your organization</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6a7e9-116">Funzionalità da supportare nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="6a7e9-116">Capabilities to be supported by your organization</span></span></p></li>
<li><p><span data-ttu-id="6a7e9-117">Funzionalità da abilitare per i singoli utenti</span><span class="sxs-lookup"><span data-stu-id="6a7e9-117">Capabilities to be enabled for individual users</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6a7e9-118"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Definizione dei requisiti per il controllo di ammissione di chiamata in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6a7e9-118"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a7e9-119">Topologie e componenti da distribuire</span><span class="sxs-lookup"><span data-stu-id="6a7e9-119">Topologies and components to be deployed</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6a7e9-120">I componenti correlati a CAC vengono installati automaticamente come parte di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a7e9-120">CAC related components are automatically installed as part of Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6a7e9-121"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Definizione dei requisiti per il controllo di ammissione di chiamata in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6a7e9-121"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a7e9-122">Requisiti di sistema</span><span class="sxs-lookup"><span data-stu-id="6a7e9-122">System requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6a7e9-123">Requisiti hardware</span><span class="sxs-lookup"><span data-stu-id="6a7e9-123">Hardware requirements</span></span></p></li>
<li><p><span data-ttu-id="6a7e9-124">Requisiti software</span><span class="sxs-lookup"><span data-stu-id="6a7e9-124">Software requirements</span></span></p></li>
<li><p><span data-ttu-id="6a7e9-125">Requisiti di collocazione</span><span class="sxs-lookup"><span data-stu-id="6a7e9-125">Collocation requirements</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6a7e9-126"><a href="lync-server-2013-determining-your-system-requirements.md">Determinazione dei requisiti di sistema per Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6a7e9-126"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a7e9-127">Requisiti dell'infrastruttura</span><span class="sxs-lookup"><span data-stu-id="6a7e9-127">Infrastructure requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6a7e9-128">Per il Controllo di ammissione di chiamata non esistono requisiti dell'infrastruttura specifici</span><span class="sxs-lookup"><span data-stu-id="6a7e9-128">No specific infrastructure requirements are necessary for CAC</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6a7e9-129"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Requisiti dell'infrastruttura per il controllo di ammissione di chiamata in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6a7e9-129"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Infrastructure requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a7e9-130">Requisiti dell'interfaccia di rete</span><span class="sxs-lookup"><span data-stu-id="6a7e9-130">Network interface requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6a7e9-131">Informazioni sull'interfaccia interna ed esterna</span><span class="sxs-lookup"><span data-stu-id="6a7e9-131">Internal and external interface information</span></span></p></li>
<li><p><span data-ttu-id="6a7e9-132">Informazioni sul routing (incluse le informazioni sul Blog di NextHop nel <a href="https://go.microsoft.com/fwlink/p/?linkid=203149">https://go.microsoft.com/fwlink/p/?LinkId=203149</a> canale di risposta dei clienti del team di Microsoft Lync Server)</span><span class="sxs-lookup"><span data-stu-id="6a7e9-132">Routing information (including information on the NextHop blog at <a href="https://go.microsoft.com/fwlink/p/?linkid=203149">https://go.microsoft.com/fwlink/p/?LinkId=203149</a>, Microsoft Lync Server team’s customer response channel)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6a7e9-133"><a href="lync-server-2013-deploying-external-user-access.md">Distribuzione dell'accesso degli utenti esterni in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6a7e9-133"><a href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a7e9-134">Strategia di distribuzione</span><span class="sxs-lookup"><span data-stu-id="6a7e9-134">Deployment strategy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6a7e9-135">Sequenza di distribuzione</span><span class="sxs-lookup"><span data-stu-id="6a7e9-135">Deployment sequence</span></span></p></li>
<li><p><span data-ttu-id="6a7e9-136">Gruppo di lavoro o dominio</span><span class="sxs-lookup"><span data-stu-id="6a7e9-136">Workgroup or domain</span></span></p></li>
<li><p><span data-ttu-id="6a7e9-137">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="6a7e9-137">Security</span></span></p></li>
<li><p><span data-ttu-id="6a7e9-138">Monitoraggio e controllo</span><span class="sxs-lookup"><span data-stu-id="6a7e9-138">Monitoring and auditing</span></span></p></li>
<li><p><span data-ttu-id="6a7e9-139">Considerazioni sull'hardware</span><span class="sxs-lookup"><span data-stu-id="6a7e9-139">Hardware considerations</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6a7e9-140"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Procedure consigliate per il controllo di ammissione di chiamata in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6a7e9-140"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Best practices for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a7e9-141">Processo di distribuzione</span><span class="sxs-lookup"><span data-stu-id="6a7e9-141">Deployment process</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6a7e9-142">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="6a7e9-142">Prerequisites</span></span></p></li>
<li><p><span data-ttu-id="6a7e9-143">Informazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="6a7e9-143">Information requirements</span></span></p></li>
<li><p><span data-ttu-id="6a7e9-144">Processo e procedure</span><span class="sxs-lookup"><span data-stu-id="6a7e9-144">Process and procedures</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6a7e9-145"><a href="lync-server-2013-configure-call-admission-control.md">Configurare il controllo di ammissione di chiamata in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6a7e9-145"><a href="lync-server-2013-configure-call-admission-control.md">Configure call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Elenco di controllo di distribuzione per il controllo di ammissione di chiamata'
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
ms.openlocfilehash: 0bf88529734530e70c4d0536d5337395ff0742d2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740746"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="e33d1-102">Elenco di controllo di distribuzione per il controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e33d1-102">Deployment checklist for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e33d1-103">_**Argomento Ultima modifica:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="e33d1-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="e33d1-104">Per pianificare efficacemente il controllo di ammissione alle chiamate (CAC), è necessario tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e33d1-104">To plan effectively for call admission control (CAC), you need to consider the following:</span></span>

  - <span data-ttu-id="e33d1-105">Prerequisiti per la distribuzione di CAC.</span><span class="sxs-lookup"><span data-stu-id="e33d1-105">Prerequisites for deploying CAC.</span></span>

  - <span data-ttu-id="e33d1-106">Informazioni necessarie per le decisioni di configurazione e CAC che è necessario apportare prima della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e33d1-106">Information required for CAC and configuration decisions that you must make in advance of deployment.</span></span>

<div>

## <a name="deployment-prerequisites-for-call-admission-control"></a><span data-ttu-id="e33d1-107">Prerequisiti di distribuzione per il controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="e33d1-107">Deployment Prerequisites for Call Admission Control</span></span>

<span data-ttu-id="e33d1-108">Prima di distribuire il controllo di ammissione di chiamata, è necessario che siano già stati distribuiti i server interni di Lync Server 2013, incluso un pool Front-end o un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e33d1-108">Before you deploy call admission control, you must already have deployed your Lync Server 2013 internal servers, including either a Front End pool or a Standard Edition server.</span></span>

</div>

<div>

## <a name="information-requirements-for-call-admission-control"></a><span data-ttu-id="e33d1-109">Requisiti di informazioni per il controllo dell'ammissione alle chiamate</span><span class="sxs-lookup"><span data-stu-id="e33d1-109">Information Requirements for Call Admission Control</span></span>

<span data-ttu-id="e33d1-110">Nella tabella seguente vengono riepilogate le informazioni necessarie per la distribuzione del controllo di ammissione alle chiamate.</span><span class="sxs-lookup"><span data-stu-id="e33d1-110">The following table summarizes the required information for deploying call admission control.</span></span>

### <a name="information-requirements-for-call-admission-control-deployment"></a><span data-ttu-id="e33d1-111">Requisiti di informazioni per la distribuzione del controllo di ammissione alle chiamate</span><span class="sxs-lookup"><span data-stu-id="e33d1-111">Information Requirements for Call Admission Control Deployment</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e33d1-112">Informazioni</span><span class="sxs-lookup"><span data-stu-id="e33d1-112">Information</span></span></th>
<th><span data-ttu-id="e33d1-113">Riepilogo delle informazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="e33d1-113">Summary of Information Required</span></span></th>
<th><span data-ttu-id="e33d1-114">Documentazione</span><span class="sxs-lookup"><span data-stu-id="e33d1-114">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e33d1-115">Funzionalità di Lync Server richieste dall'organizzazione</span><span class="sxs-lookup"><span data-stu-id="e33d1-115">Lync Server capabilities required by your organization</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e33d1-116">Funzionalità supportate dall'organizzazione</span><span class="sxs-lookup"><span data-stu-id="e33d1-116">Capabilities to be supported by your organization</span></span></p></li>
<li><p><span data-ttu-id="e33d1-117">Funzionalità da abilitare per singoli utenti</span><span class="sxs-lookup"><span data-stu-id="e33d1-117">Capabilities to be enabled for individual users</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e33d1-118"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Definizione dei requisiti dell'organizzazione per il controllo di ammissione di chiamata in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e33d1-118"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e33d1-119">Topologie e componenti da distribuire</span><span class="sxs-lookup"><span data-stu-id="e33d1-119">Topologies and components to be deployed</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e33d1-120">I componenti correlati a CAC vengono automaticamente installati come parte di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e33d1-120">CAC related components are automatically installed as part of Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e33d1-121"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Definizione dei requisiti dell'organizzazione per il controllo di ammissione di chiamata in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e33d1-121"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e33d1-122">Requisiti di sistema</span><span class="sxs-lookup"><span data-stu-id="e33d1-122">System requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e33d1-123">Requisiti hardware</span><span class="sxs-lookup"><span data-stu-id="e33d1-123">Hardware requirements</span></span></p></li>
<li><p><span data-ttu-id="e33d1-124">Requisiti software</span><span class="sxs-lookup"><span data-stu-id="e33d1-124">Software requirements</span></span></p></li>
<li><p><span data-ttu-id="e33d1-125">Requisiti di collocazione</span><span class="sxs-lookup"><span data-stu-id="e33d1-125">Collocation requirements</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e33d1-126"><a href="lync-server-2013-determining-your-system-requirements.md">Determinazione dei requisiti di sistema per Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e33d1-126"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e33d1-127">Requisiti per l'infrastruttura</span><span class="sxs-lookup"><span data-stu-id="e33d1-127">Infrastructure requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e33d1-128">Non sono necessari requisiti specifici per l'infrastruttura per CAC</span><span class="sxs-lookup"><span data-stu-id="e33d1-128">No specific infrastructure requirements are necessary for CAC</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e33d1-129"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Requisiti dell'infrastruttura per il controllo di ammissione di chiamata in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e33d1-129"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Infrastructure requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e33d1-130">Requisiti di interfaccia di rete</span><span class="sxs-lookup"><span data-stu-id="e33d1-130">Network interface requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e33d1-131">Informazioni sulle interfacce interne ed esterne</span><span class="sxs-lookup"><span data-stu-id="e33d1-131">Internal and external interface information</span></span></p></li>
<li><p><span data-ttu-id="e33d1-132">Informazioni di routing (incluse le informazioni sul Blog di <a href="http://go.microsoft.com/fwlink/p/?linkid=203149">http://go.microsoft.com/fwlink/p/?LinkId=203149</a>NextHop at, canale di risposta del cliente del team di Microsoft Lync Server)</span><span class="sxs-lookup"><span data-stu-id="e33d1-132">Routing information (including information on the NextHop blog at <a href="http://go.microsoft.com/fwlink/p/?linkid=203149">http://go.microsoft.com/fwlink/p/?LinkId=203149</a>, Microsoft Lync Server team’s customer response channel)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e33d1-133"><a href="lync-server-2013-deploying-external-user-access.md">Distribuzione dell'accesso degli utenti esterni in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e33d1-133"><a href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e33d1-134">Strategia di distribuzione</span><span class="sxs-lookup"><span data-stu-id="e33d1-134">Deployment strategy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e33d1-135">Sequenza di distribuzione</span><span class="sxs-lookup"><span data-stu-id="e33d1-135">Deployment sequence</span></span></p></li>
<li><p><span data-ttu-id="e33d1-136">Gruppo di lavoro o dominio</span><span class="sxs-lookup"><span data-stu-id="e33d1-136">Workgroup or domain</span></span></p></li>
<li><p><span data-ttu-id="e33d1-137">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="e33d1-137">Security</span></span></p></li>
<li><p><span data-ttu-id="e33d1-138">Monitoraggio e controllo</span><span class="sxs-lookup"><span data-stu-id="e33d1-138">Monitoring and auditing</span></span></p></li>
<li><p><span data-ttu-id="e33d1-139">Considerazioni sull'hardware</span><span class="sxs-lookup"><span data-stu-id="e33d1-139">Hardware considerations</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e33d1-140"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Procedure consigliate per il controllo di ammissione di chiamata in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e33d1-140"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Best practices for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e33d1-141">Processo di distribuzione</span><span class="sxs-lookup"><span data-stu-id="e33d1-141">Deployment process</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e33d1-142">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="e33d1-142">Prerequisites</span></span></p></li>
<li><p><span data-ttu-id="e33d1-143">Requisiti per le informazioni</span><span class="sxs-lookup"><span data-stu-id="e33d1-143">Information requirements</span></span></p></li>
<li><p><span data-ttu-id="e33d1-144">Processi e procedure</span><span class="sxs-lookup"><span data-stu-id="e33d1-144">Process and procedures</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e33d1-145"><a href="lync-server-2013-configure-call-admission-control.md">Configurare il controllo di ammissione di chiamata in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e33d1-145"><a href="lync-server-2013-configure-call-admission-control.md">Configure call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


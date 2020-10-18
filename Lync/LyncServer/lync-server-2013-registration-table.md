---
title: 'Lync Server 2013: tabella di registrazione'
description: 'Lync Server 2013: tabella di registrazione.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Registration table
ms:assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398114(v=OCS.15)
ms:contentKeyID: 48183298
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 806e1a4e944c9bc04ebdd167c41c80a57fde3f29
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578527"
---
# <a name="registration-table-in-lync-server-2013"></a><span data-ttu-id="6147d-103">Tabella di registrazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6147d-103">Registration table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6147d-104">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="6147d-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="6147d-105">Ogni record rappresenta un evento di registrazione utente.</span><span class="sxs-lookup"><span data-stu-id="6147d-105">Each record represents one user registration event.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6147d-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="6147d-106">Column</span></span></th>
<th><span data-ttu-id="6147d-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="6147d-107">Data Type</span></span></th>
<th><span data-ttu-id="6147d-108">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="6147d-108">Key/Index</span></span></th>
<th><span data-ttu-id="6147d-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="6147d-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6147d-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="6147d-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6147d-111">datetime</span><span class="sxs-lookup"><span data-stu-id="6147d-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="6147d-112">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="6147d-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="6147d-113">Data e ora della richiesta di sessione.</span><span class="sxs-lookup"><span data-stu-id="6147d-113">Time of session request.</span></span> <span data-ttu-id="6147d-114">Valore utilizzato insieme a <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="6147d-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="6147d-115">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6147d-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6147d-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="6147d-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="6147d-117">int</span><span class="sxs-lookup"><span data-stu-id="6147d-117">int</span></span></p></td>
<td><p><span data-ttu-id="6147d-118">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="6147d-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="6147d-119">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="6147d-119">ID number to identify the session.</span></span> <span data-ttu-id="6147d-120">Valore utilizzato insieme a <strong>SessionIdTime</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="6147d-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="6147d-121">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6147d-121">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6147d-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="6147d-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="6147d-123">int</span><span class="sxs-lookup"><span data-stu-id="6147d-123">int</span></span></p></td>
<td><p><span data-ttu-id="6147d-124">Stranieri</span><span class="sxs-lookup"><span data-stu-id="6147d-124">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6147d-125">ID utente.</span><span class="sxs-lookup"><span data-stu-id="6147d-125">The user ID.</span></span> <span data-ttu-id="6147d-126">Per ulteriori informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6147d-126">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6147d-127"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="6147d-127"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="6147d-128">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="6147d-128">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6147d-p104">GUID per identificare un endpoint di registrazione. L'evento di registrazione dallo stesso computer dello stesso utente in genere avrà lo stesso ID endpoint. Computer diversi hanno un ID endpoint diverso.</span><span class="sxs-lookup"><span data-stu-id="6147d-p104">A GUID to identify a registration endpoint. Usually the register event from the same computer of the same user will have the same endpoint ID. Different machines have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6147d-132"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="6147d-132"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="6147d-133">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="6147d-133">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6147d-134">ID utilizzato per distinguere le registrazioni che interessano lo stesso utente e lo stesso endpoint.</span><span class="sxs-lookup"><span data-stu-id="6147d-134">ID used to differentiate registrations that involve the same user and the same endpoint.</span></span></p>
<p><span data-ttu-id="6147d-135">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6147d-135">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6147d-136"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="6147d-136"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="6147d-137">int</span><span class="sxs-lookup"><span data-stu-id="6147d-137">int</span></span></p></td>
<td><p><span data-ttu-id="6147d-138">Stranieri</span><span class="sxs-lookup"><span data-stu-id="6147d-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6147d-139">Versione client dell'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="6147d-139">Client version of current user.</span></span> <span data-ttu-id="6147d-140">Per ulteriori informazioni, vedere la <a href="lync-server-2013-clientversions-table.md">Tabella ClientVersions in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6147d-140">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6147d-141"><strong>RegistrarId</strong></span><span class="sxs-lookup"><span data-stu-id="6147d-141"><strong>RegistrarId</strong></span></span></p></td>
<td><p><span data-ttu-id="6147d-142">int</span><span class="sxs-lookup"><span data-stu-id="6147d-142">int</span></span></p></td>
<td><p><span data-ttu-id="6147d-143">Stranieri</span><span class="sxs-lookup"><span data-stu-id="6147d-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6147d-144">ID del server di registrazione utilizzato per la registrazione.</span><span class="sxs-lookup"><span data-stu-id="6147d-144">ID of the Registrar Server used for registration.</span></span> <span data-ttu-id="6147d-145">Per ulteriori informazioni, vedere la <a href="lync-server-2013-servers-table.md">tabella Servers in Lync server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6147d-145">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6147d-146"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="6147d-146"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="6147d-147">int</span><span class="sxs-lookup"><span data-stu-id="6147d-147">int</span></span></p></td>
<td><p><span data-ttu-id="6147d-148">Stranieri</span><span class="sxs-lookup"><span data-stu-id="6147d-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6147d-149">ID del pool in cui è stata acquisita la sessione.</span><span class="sxs-lookup"><span data-stu-id="6147d-149">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="6147d-150">Per ulteriori informazioni, vedere la <a href="lync-server-2013-pools-table.md">Tabella Pools in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6147d-150">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6147d-151"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="6147d-151"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="6147d-152">int</span><span class="sxs-lookup"><span data-stu-id="6147d-152">int</span></span></p></td>
<td><p><span data-ttu-id="6147d-153">Stranieri</span><span class="sxs-lookup"><span data-stu-id="6147d-153">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6147d-154">Server perimetrale attraverso il quale passa la registrazione.</span><span class="sxs-lookup"><span data-stu-id="6147d-154">Edge Server the registration is going through.</span></span> <span data-ttu-id="6147d-155">Per ulteriori informazioni, vedere la <a href="lync-server-2013-edgeservers-table.md">tabella EdgeServers in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6147d-155">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6147d-156"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="6147d-156"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="6147d-157">Po'</span><span class="sxs-lookup"><span data-stu-id="6147d-157">Bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6147d-158">Se l'utente è connesso o meno dall'interno.</span><span class="sxs-lookup"><span data-stu-id="6147d-158">Whether the user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6147d-159"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="6147d-159"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="6147d-160">po'</span><span class="sxs-lookup"><span data-stu-id="6147d-160">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6147d-161">Se il servizio utente è disponibile o meno.</span><span class="sxs-lookup"><span data-stu-id="6147d-161">Whether the UserService is available or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6147d-162"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="6147d-162"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="6147d-163">po'</span><span class="sxs-lookup"><span data-stu-id="6147d-163">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6147d-164">Se registrare o meno nella funzione di registrazione principale.</span><span class="sxs-lookup"><span data-stu-id="6147d-164">Whether register to the primary Registrar or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6147d-165"><strong>IsPrimaryRegistrarCentral</strong></span><span class="sxs-lookup"><span data-stu-id="6147d-165"><strong>IsPrimaryRegistrarCentral</strong></span></span></p></td>
<td><p><span data-ttu-id="6147d-166">po'</span><span class="sxs-lookup"><span data-stu-id="6147d-166">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6147d-167">Indica se l'utente è registrato o meno con un Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="6147d-167">Indicates whether or not the user is registered with a survivable branch appliance.</span></span></p>
<p><span data-ttu-id="6147d-168">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6147d-168">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6147d-169"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="6147d-169"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6147d-170">datetime</span><span class="sxs-lookup"><span data-stu-id="6147d-170">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6147d-171">Data/ora di registrazione.</span><span class="sxs-lookup"><span data-stu-id="6147d-171">Registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6147d-172"><strong>DeRegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="6147d-172"><strong>DeRegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6147d-173">datetime</span><span class="sxs-lookup"><span data-stu-id="6147d-173">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6147d-174">Data/ora di annullamento della registrazione.</span><span class="sxs-lookup"><span data-stu-id="6147d-174">De-Registration time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6147d-175"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="6147d-175"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="6147d-176">int</span><span class="sxs-lookup"><span data-stu-id="6147d-176">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6147d-177">Codice di risposta della richiesta di registrazione.</span><span class="sxs-lookup"><span data-stu-id="6147d-177">Response code of the register request.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6147d-178"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="6147d-178"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="6147d-179">int</span><span class="sxs-lookup"><span data-stu-id="6147d-179">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6147d-p109">ID diagnostica della richiesta di registrazione. Indica il tipo di informazioni diagnostiche.</span><span class="sxs-lookup"><span data-stu-id="6147d-p109">Diagnostic ID of the register request. This indicates that diagnostic information type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6147d-182"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="6147d-182"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="6147d-183">int</span><span class="sxs-lookup"><span data-stu-id="6147d-183">int</span></span></p></td>
<td><p><span data-ttu-id="6147d-184">Stranieri</span><span class="sxs-lookup"><span data-stu-id="6147d-184">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6147d-185">Dispositivo da cui proviene la richiesta di registrazione.</span><span class="sxs-lookup"><span data-stu-id="6147d-185">The device that the register request is coming from.</span></span> <span data-ttu-id="6147d-186">Per ulteriori informazioni, vedere la <a href="lync-server-2013-devices-table.md">Tabella Devices in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6147d-186">See the <a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6147d-187"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="6147d-187"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="6147d-188">tinyint</span><span class="sxs-lookup"><span data-stu-id="6147d-188">tinyint</span></span></p></td>
<td><p><span data-ttu-id="6147d-189">Stranieri</span><span class="sxs-lookup"><span data-stu-id="6147d-189">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6147d-190">Motivo dell'annullamento della registrazione, ad esempio 'user initiated' (avviato dall'utente), 'registration expired' (registrazione scaduta), 'client fail' (problema del client) e così via.</span><span class="sxs-lookup"><span data-stu-id="6147d-190">The reason of de-register, such as ‘user initiated’, ‘registration expired’, ‘client fail’, and more.</span></span> <span data-ttu-id="6147d-191">Per ulteriori informazioni, vedere la <a href="lync-server-2013-deregistertype-table.md">Tabella DeRegisterType in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6147d-191">See the <a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6147d-192"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="6147d-192"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="6147d-193">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6147d-193">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6147d-194">Indirizzo IP dell'endpoint con cui l'utente è registrato.</span><span class="sxs-lookup"><span data-stu-id="6147d-194">IP address of the endpoint the user registered with.</span></span> <span data-ttu-id="6147d-195">Può essere un indirizzo IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="6147d-195">This can be an IPv4 address or an IPv6 address.</span></span></p>
<p><span data-ttu-id="6147d-196">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6147d-196">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


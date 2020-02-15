---
title: 'Lync Server 2013: tabella di registrazione'
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
ms.openlocfilehash: 0679915e73061e550e01c0809fd5c5b20b566ff6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050718"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-table-in-lync-server-2013"></a><span data-ttu-id="a4621-102">Tabella di registrazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4621-102">Registration table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4621-103">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="a4621-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="a4621-104">Ogni record rappresenta un evento di registrazione utente.</span><span class="sxs-lookup"><span data-stu-id="a4621-104">Each record represents one user registration event.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a4621-105">Colonna</span><span class="sxs-lookup"><span data-stu-id="a4621-105">Column</span></span></th>
<th><span data-ttu-id="a4621-106">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="a4621-106">Data Type</span></span></th>
<th><span data-ttu-id="a4621-107">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="a4621-107">Key/Index</span></span></th>
<th><span data-ttu-id="a4621-108">Dettagli</span><span class="sxs-lookup"><span data-stu-id="a4621-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a4621-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="a4621-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a4621-110">datetime</span><span class="sxs-lookup"><span data-stu-id="a4621-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="a4621-111">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="a4621-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="a4621-112">Data e ora della richiesta di sessione.</span><span class="sxs-lookup"><span data-stu-id="a4621-112">Time of session request.</span></span> <span data-ttu-id="a4621-113">Valore utilizzato insieme a <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="a4621-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="a4621-114">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a4621-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4621-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a4621-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a4621-116">int</span><span class="sxs-lookup"><span data-stu-id="a4621-116">int</span></span></p></td>
<td><p><span data-ttu-id="a4621-117">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="a4621-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="a4621-118">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="a4621-118">ID number to identify the session.</span></span> <span data-ttu-id="a4621-119">Valore utilizzato insieme a <strong>SessionIdTime</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="a4621-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="a4621-120">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a4621-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4621-121"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="a4621-121"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="a4621-122">int</span><span class="sxs-lookup"><span data-stu-id="a4621-122">int</span></span></p></td>
<td><p><span data-ttu-id="a4621-123">Stranieri</span><span class="sxs-lookup"><span data-stu-id="a4621-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a4621-124">ID utente.</span><span class="sxs-lookup"><span data-stu-id="a4621-124">The user ID.</span></span> <span data-ttu-id="a4621-125">Per ulteriori informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a4621-125">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4621-126"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="a4621-126"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="a4621-127">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="a4621-127">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4621-p104">GUID per identificare un endpoint di registrazione. L'evento di registrazione dallo stesso computer dello stesso utente in genere avrà lo stesso ID endpoint. Computer diversi hanno un ID endpoint diverso.</span><span class="sxs-lookup"><span data-stu-id="a4621-p104">A GUID to identify a registration endpoint. Usually the register event from the same computer of the same user will have the same endpoint ID. Different machines have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4621-131"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="a4621-131"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="a4621-132">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="a4621-132">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4621-133">ID utilizzato per distinguere le registrazioni che interessano lo stesso utente e lo stesso endpoint.</span><span class="sxs-lookup"><span data-stu-id="a4621-133">ID used to differentiate registrations that involve the same user and the same endpoint.</span></span></p>
<p><span data-ttu-id="a4621-134">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4621-134">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4621-135"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="a4621-135"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="a4621-136">int</span><span class="sxs-lookup"><span data-stu-id="a4621-136">int</span></span></p></td>
<td><p><span data-ttu-id="a4621-137">Stranieri</span><span class="sxs-lookup"><span data-stu-id="a4621-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a4621-138">Versione client dell'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="a4621-138">Client version of current user.</span></span> <span data-ttu-id="a4621-139">Per ulteriori informazioni, vedere la <a href="lync-server-2013-clientversions-table.md">Tabella ClientVersions in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a4621-139">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4621-140"><strong>RegistrarId</strong></span><span class="sxs-lookup"><span data-stu-id="a4621-140"><strong>RegistrarId</strong></span></span></p></td>
<td><p><span data-ttu-id="a4621-141">int</span><span class="sxs-lookup"><span data-stu-id="a4621-141">int</span></span></p></td>
<td><p><span data-ttu-id="a4621-142">Stranieri</span><span class="sxs-lookup"><span data-stu-id="a4621-142">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a4621-143">ID del server di registrazione utilizzato per la registrazione.</span><span class="sxs-lookup"><span data-stu-id="a4621-143">ID of the Registrar Server used for registration.</span></span> <span data-ttu-id="a4621-144">Per ulteriori informazioni, vedere la <a href="lync-server-2013-servers-table.md">tabella Servers in Lync server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a4621-144">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4621-145"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="a4621-145"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="a4621-146">int</span><span class="sxs-lookup"><span data-stu-id="a4621-146">int</span></span></p></td>
<td><p><span data-ttu-id="a4621-147">Stranieri</span><span class="sxs-lookup"><span data-stu-id="a4621-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a4621-148">ID del pool in cui è stata acquisita la sessione.</span><span class="sxs-lookup"><span data-stu-id="a4621-148">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="a4621-149">Per ulteriori informazioni, vedere la <a href="lync-server-2013-pools-table.md">Tabella Pools in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a4621-149">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4621-150"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="a4621-150"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="a4621-151">int</span><span class="sxs-lookup"><span data-stu-id="a4621-151">int</span></span></p></td>
<td><p><span data-ttu-id="a4621-152">Stranieri</span><span class="sxs-lookup"><span data-stu-id="a4621-152">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a4621-153">Server perimetrale attraverso il quale passa la registrazione.</span><span class="sxs-lookup"><span data-stu-id="a4621-153">Edge Server the registration is going through.</span></span> <span data-ttu-id="a4621-154">Per ulteriori informazioni, vedere la <a href="lync-server-2013-edgeservers-table.md">tabella EdgeServers in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a4621-154">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4621-155"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="a4621-155"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="a4621-156">Po'</span><span class="sxs-lookup"><span data-stu-id="a4621-156">Bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4621-157">Se l'utente è connesso o meno dall'interno.</span><span class="sxs-lookup"><span data-stu-id="a4621-157">Whether the user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4621-158"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="a4621-158"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="a4621-159">po'</span><span class="sxs-lookup"><span data-stu-id="a4621-159">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4621-160">Se il servizio utente è disponibile o meno.</span><span class="sxs-lookup"><span data-stu-id="a4621-160">Whether the UserService is available or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4621-161"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="a4621-161"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="a4621-162">po'</span><span class="sxs-lookup"><span data-stu-id="a4621-162">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4621-163">Se registrare o meno nella funzione di registrazione principale.</span><span class="sxs-lookup"><span data-stu-id="a4621-163">Whether register to the primary Registrar or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4621-164"><strong>IsPrimaryRegistrarCentral</strong></span><span class="sxs-lookup"><span data-stu-id="a4621-164"><strong>IsPrimaryRegistrarCentral</strong></span></span></p></td>
<td><p><span data-ttu-id="a4621-165">po'</span><span class="sxs-lookup"><span data-stu-id="a4621-165">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4621-166">Indica se l'utente è registrato o meno con un Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="a4621-166">Indicates whether or not the user is registered with a survivable branch appliance.</span></span></p>
<p><span data-ttu-id="a4621-167">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4621-167">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4621-168"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="a4621-168"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a4621-169">datetime</span><span class="sxs-lookup"><span data-stu-id="a4621-169">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4621-170">Data/ora di registrazione.</span><span class="sxs-lookup"><span data-stu-id="a4621-170">Registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4621-171"><strong>DeRegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="a4621-171"><strong>DeRegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a4621-172">datetime</span><span class="sxs-lookup"><span data-stu-id="a4621-172">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4621-173">Data/ora di annullamento della registrazione.</span><span class="sxs-lookup"><span data-stu-id="a4621-173">De-Registration time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4621-174"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="a4621-174"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="a4621-175">int</span><span class="sxs-lookup"><span data-stu-id="a4621-175">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4621-176">Codice di risposta della richiesta di registrazione.</span><span class="sxs-lookup"><span data-stu-id="a4621-176">Response code of the register request.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4621-177"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="a4621-177"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="a4621-178">int</span><span class="sxs-lookup"><span data-stu-id="a4621-178">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4621-p109">ID diagnostica della richiesta di registrazione. Indica il tipo di informazioni diagnostiche.</span><span class="sxs-lookup"><span data-stu-id="a4621-p109">Diagnostic ID of the register request. This indicates that diagnostic information type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4621-181"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="a4621-181"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="a4621-182">int</span><span class="sxs-lookup"><span data-stu-id="a4621-182">int</span></span></p></td>
<td><p><span data-ttu-id="a4621-183">Stranieri</span><span class="sxs-lookup"><span data-stu-id="a4621-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a4621-184">Dispositivo da cui proviene la richiesta di registrazione.</span><span class="sxs-lookup"><span data-stu-id="a4621-184">The device that the register request is coming from.</span></span> <span data-ttu-id="a4621-185">Per ulteriori informazioni, vedere la <a href="lync-server-2013-devices-table.md">Tabella Devices in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a4621-185">See the <a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4621-186"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="a4621-186"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="a4621-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="a4621-187">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a4621-188">Stranieri</span><span class="sxs-lookup"><span data-stu-id="a4621-188">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a4621-189">Motivo dell'annullamento della registrazione, ad esempio 'user initiated' (avviato dall'utente), 'registration expired' (registrazione scaduta), 'client fail' (problema del client) e così via.</span><span class="sxs-lookup"><span data-stu-id="a4621-189">The reason of de-register, such as ‘user initiated’, ‘registration expired’, ‘client fail’, and more.</span></span> <span data-ttu-id="a4621-190">Per ulteriori informazioni, vedere la <a href="lync-server-2013-deregistertype-table.md">Tabella DeRegisterType in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a4621-190">See the <a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4621-191"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="a4621-191"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="a4621-192">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a4621-192">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4621-193">Indirizzo IP dell'endpoint con cui l'utente è registrato.</span><span class="sxs-lookup"><span data-stu-id="a4621-193">IP address of the endpoint the user registered with.</span></span> <span data-ttu-id="a4621-194">Può essere un indirizzo IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="a4621-194">This can be an IPv4 address or an IPv6 address.</span></span></p>
<p><span data-ttu-id="a4621-195">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4621-195">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


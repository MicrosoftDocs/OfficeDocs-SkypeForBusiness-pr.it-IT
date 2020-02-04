---
title: 'Lync Server 2013: Tabella Registration'
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
ms.openlocfilehash: 0bc19c35893b12aae7842be5fc474f7831b7f979
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724396"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-table-in-lync-server-2013"></a><span data-ttu-id="a3837-102">Tabella Registration in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3837-102">Registration table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3837-103">_**Argomento Ultima modifica:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="a3837-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="a3837-104">Ogni record rappresenta un evento di registrazione utente.</span><span class="sxs-lookup"><span data-stu-id="a3837-104">Each record represents one user registration event.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a3837-105">Colonna</span><span class="sxs-lookup"><span data-stu-id="a3837-105">Column</span></span></th>
<th><span data-ttu-id="a3837-106">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="a3837-106">Data Type</span></span></th>
<th><span data-ttu-id="a3837-107">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="a3837-107">Key/Index</span></span></th>
<th><span data-ttu-id="a3837-108">Dettagli</span><span class="sxs-lookup"><span data-stu-id="a3837-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3837-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="a3837-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a3837-110">DateTime</span><span class="sxs-lookup"><span data-stu-id="a3837-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="a3837-111">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="a3837-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="a3837-112">Ora della richiesta della sessione.</span><span class="sxs-lookup"><span data-stu-id="a3837-112">Time of session request.</span></span> <span data-ttu-id="a3837-113">Usato in combinazione con <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="a3837-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="a3837-114">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a3837-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3837-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a3837-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a3837-116">int</span><span class="sxs-lookup"><span data-stu-id="a3837-116">int</span></span></p></td>
<td><p><span data-ttu-id="a3837-117">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="a3837-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="a3837-118">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="a3837-118">ID number to identify the session.</span></span> <span data-ttu-id="a3837-119">Usato in combinazione con <strong>SessionIdTime</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="a3837-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="a3837-120">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a3837-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3837-121"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="a3837-121"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="a3837-122">int</span><span class="sxs-lookup"><span data-stu-id="a3837-122">int</span></span></p></td>
<td><p><span data-ttu-id="a3837-123">Esterna</span><span class="sxs-lookup"><span data-stu-id="a3837-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a3837-124">ID utente.</span><span class="sxs-lookup"><span data-stu-id="a3837-124">The user ID.</span></span> <span data-ttu-id="a3837-125">Per altre informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella utenti in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a3837-125">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3837-126"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="a3837-126"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="a3837-127">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="a3837-127">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a3837-128">GUID per identificare un endpoint di registrazione.</span><span class="sxs-lookup"><span data-stu-id="a3837-128">A GUID to identify a registration endpoint.</span></span> <span data-ttu-id="a3837-129">In genere, l'evento Register dello stesso computer dello stesso utente avrà lo stesso ID endpoint.</span><span class="sxs-lookup"><span data-stu-id="a3837-129">Usually the register event from the same computer of the same user will have the same endpoint ID.</span></span> <span data-ttu-id="a3837-130">I computer diversi hanno un ID endpoint diverso.</span><span class="sxs-lookup"><span data-stu-id="a3837-130">Different machines have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3837-131"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="a3837-131"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="a3837-132">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="a3837-132">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a3837-133">ID usato per distinguere le registrazioni che coinvolgono lo stesso utente e lo stesso endpoint.</span><span class="sxs-lookup"><span data-stu-id="a3837-133">ID used to differentiate registrations that involve the same user and the same endpoint.</span></span></p>
<p><span data-ttu-id="a3837-134">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a3837-134">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3837-135"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="a3837-135"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="a3837-136">int</span><span class="sxs-lookup"><span data-stu-id="a3837-136">int</span></span></p></td>
<td><p><span data-ttu-id="a3837-137">Esterna</span><span class="sxs-lookup"><span data-stu-id="a3837-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a3837-138">Versione client dell'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="a3837-138">Client version of current user.</span></span> <span data-ttu-id="a3837-139">Per altre informazioni, vedere la <a href="lync-server-2013-clientversions-table.md">Tabella ClientVersions in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a3837-139">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3837-140"><strong>RegistrarId</strong></span><span class="sxs-lookup"><span data-stu-id="a3837-140"><strong>RegistrarId</strong></span></span></p></td>
<td><p><span data-ttu-id="a3837-141">int</span><span class="sxs-lookup"><span data-stu-id="a3837-141">int</span></span></p></td>
<td><p><span data-ttu-id="a3837-142">Esterna</span><span class="sxs-lookup"><span data-stu-id="a3837-142">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a3837-143">ID del server registrar usato per la registrazione.</span><span class="sxs-lookup"><span data-stu-id="a3837-143">ID of the Registrar Server used for registration.</span></span> <span data-ttu-id="a3837-144">Per altre informazioni, vedere la <a href="lync-server-2013-servers-table.md">tabella server in Lync server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a3837-144">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3837-145"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="a3837-145"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="a3837-146">int</span><span class="sxs-lookup"><span data-stu-id="a3837-146">int</span></span></p></td>
<td><p><span data-ttu-id="a3837-147">Esterna</span><span class="sxs-lookup"><span data-stu-id="a3837-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a3837-148">ID del pool in cui è stata acquisita la sessione.</span><span class="sxs-lookup"><span data-stu-id="a3837-148">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="a3837-149">Per altre informazioni, vedere la <a href="lync-server-2013-pools-table.md">Tabella Pools in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a3837-149">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3837-150"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="a3837-150"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="a3837-151">int</span><span class="sxs-lookup"><span data-stu-id="a3837-151">int</span></span></p></td>
<td><p><span data-ttu-id="a3837-152">Esterna</span><span class="sxs-lookup"><span data-stu-id="a3837-152">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a3837-153">Edge Server che la registrazione sta attraversando.</span><span class="sxs-lookup"><span data-stu-id="a3837-153">Edge Server the registration is going through.</span></span> <span data-ttu-id="a3837-154">Per altre informazioni, vedere la <a href="lync-server-2013-edgeservers-table.md">tabella EdgeServers in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a3837-154">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3837-155"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="a3837-155"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="a3837-156">Po'</span><span class="sxs-lookup"><span data-stu-id="a3837-156">Bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a3837-157">Se l'utente ha eseguito l'accesso da Internal o not.</span><span class="sxs-lookup"><span data-stu-id="a3837-157">Whether the user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3837-158"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="a3837-158"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="a3837-159">po'</span><span class="sxs-lookup"><span data-stu-id="a3837-159">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a3837-160">Se il UserService è disponibile o meno.</span><span class="sxs-lookup"><span data-stu-id="a3837-160">Whether the UserService is available or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3837-161"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="a3837-161"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="a3837-162">po'</span><span class="sxs-lookup"><span data-stu-id="a3837-162">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a3837-163">Se eseguire la registrazione al registrar principale o meno.</span><span class="sxs-lookup"><span data-stu-id="a3837-163">Whether register to the primary Registrar or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3837-164"><strong>IsPrimaryRegistrarCentral</strong></span><span class="sxs-lookup"><span data-stu-id="a3837-164"><strong>IsPrimaryRegistrarCentral</strong></span></span></p></td>
<td><p><span data-ttu-id="a3837-165">po'</span><span class="sxs-lookup"><span data-stu-id="a3837-165">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a3837-166">Indica se l'utente è registrato o meno con un Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="a3837-166">Indicates whether or not the user is registered with a survivable branch appliance.</span></span></p>
<p><span data-ttu-id="a3837-167">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a3837-167">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3837-168"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="a3837-168"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a3837-169">DateTime</span><span class="sxs-lookup"><span data-stu-id="a3837-169">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a3837-170">Ora di registrazione.</span><span class="sxs-lookup"><span data-stu-id="a3837-170">Registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3837-171"><strong>DeRegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="a3837-171"><strong>DeRegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a3837-172">DateTime</span><span class="sxs-lookup"><span data-stu-id="a3837-172">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a3837-173">Tempo di annullamento della registrazione.</span><span class="sxs-lookup"><span data-stu-id="a3837-173">De-Registration time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3837-174"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="a3837-174"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="a3837-175">int</span><span class="sxs-lookup"><span data-stu-id="a3837-175">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a3837-176">Codice di risposta della richiesta di registrazione.</span><span class="sxs-lookup"><span data-stu-id="a3837-176">Response code of the register request.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3837-177"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="a3837-177"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="a3837-178">int</span><span class="sxs-lookup"><span data-stu-id="a3837-178">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a3837-179">ID di diagnostica della richiesta di registrazione.</span><span class="sxs-lookup"><span data-stu-id="a3837-179">Diagnostic ID of the register request.</span></span> <span data-ttu-id="a3837-180">Indica il tipo di informazioni di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="a3837-180">This indicates that diagnostic information type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3837-181"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="a3837-181"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="a3837-182">int</span><span class="sxs-lookup"><span data-stu-id="a3837-182">int</span></span></p></td>
<td><p><span data-ttu-id="a3837-183">Esterna</span><span class="sxs-lookup"><span data-stu-id="a3837-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a3837-184">Il dispositivo da cui proviene la richiesta di registro.</span><span class="sxs-lookup"><span data-stu-id="a3837-184">The device that the register request is coming from.</span></span> <span data-ttu-id="a3837-185">Per altre informazioni, vedere la <a href="lync-server-2013-devices-table.md">tabella dispositivi in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a3837-185">See the <a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3837-186"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="a3837-186"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="a3837-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="a3837-187">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a3837-188">Esterna</span><span class="sxs-lookup"><span data-stu-id="a3837-188">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a3837-189">Il motivo dell'annullamento della registrazione, ad esempio "utente avviato", "Registrazione scaduta", "errore client" e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="a3837-189">The reason of de-register, such as ‘user initiated’, ‘registration expired’, ‘client fail’, and more.</span></span> <span data-ttu-id="a3837-190">Per altre informazioni, vedere la <a href="lync-server-2013-deregistertype-table.md">Tabella DeRegisterType in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a3837-190">See the <a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3837-191"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="a3837-191"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="a3837-192">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a3837-192">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a3837-193">Indirizzo IP dell'endpoint con cui è stato registrato l'utente.</span><span class="sxs-lookup"><span data-stu-id="a3837-193">IP address of the endpoint the user registered with.</span></span> <span data-ttu-id="a3837-194">Può trattarsi di un indirizzo IPv4 o di un indirizzo IPv6.</span><span class="sxs-lookup"><span data-stu-id="a3837-194">This can be an IPv4 address or an IPv6 address.</span></span></p>
<p><span data-ttu-id="a3837-195">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a3837-195">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


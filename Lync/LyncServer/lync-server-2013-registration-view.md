---
title: 'Lync Server 2013: visualizzazione registrazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Registration view
ms:assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688120(v=OCS.15)
ms:contentKeyID: 49733718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe1b01b748204d3d4365b6f28ae4480d3632b35a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974142"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-view-in-lync-server-2013"></a><span data-ttu-id="f3938-102">Visualizzazione di registrazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3938-102">Registration view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3938-103">_**Argomento Ultima modifica:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="f3938-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="f3938-104">La visualizzazione di registrazione archivia le informazioni sulla registrazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="f3938-104">The Registration view stores information about user registration.</span></span> <span data-ttu-id="f3938-105">Questa visualizzazione è stata introdotta in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f3938-105">This view was introduced in Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f3938-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="f3938-106">Column</span></span></th>
<th><span data-ttu-id="f3938-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="f3938-107">Data Type</span></span></th>
<th><span data-ttu-id="f3938-108">Dettagli</span><span class="sxs-lookup"><span data-stu-id="f3938-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f3938-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="f3938-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f3938-110">DateTime</span><span class="sxs-lookup"><span data-stu-id="f3938-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="f3938-111">Ora della richiesta della sessione.</span><span class="sxs-lookup"><span data-stu-id="f3938-111">Time of session request.</span></span> <span data-ttu-id="f3938-112">Usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="f3938-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="f3938-113">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f3938-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3938-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f3938-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f3938-115">int</span><span class="sxs-lookup"><span data-stu-id="f3938-115">int</span></span></p></td>
<td><p><span data-ttu-id="f3938-116">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="f3938-116">ID number to identify the session.</span></span> <span data-ttu-id="f3938-117">Usato in combinazione con SessionIdTime per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="f3938-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="f3938-118">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f3938-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3938-119"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="f3938-119"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f3938-120">DateTime</span><span class="sxs-lookup"><span data-stu-id="f3938-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="f3938-121">Ora in cui si è verificata la registrazione.</span><span class="sxs-lookup"><span data-stu-id="f3938-121">Time at which registration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3938-122"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="f3938-122"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="f3938-123">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="f3938-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="f3938-124">URI dell'utente che ha registrato.</span><span class="sxs-lookup"><span data-stu-id="f3938-124">URI of the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3938-125"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="f3938-125"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="f3938-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f3938-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f3938-127">Tipo di URI dell'utente che ha registrato.</span><span class="sxs-lookup"><span data-stu-id="f3938-127">Type of URI of the user who registered.</span></span> <span data-ttu-id="f3938-128">Per altre informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f3938-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3938-129"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="f3938-129"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="f3938-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f3938-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f3938-131">Tenant dell'utente che ha registrato.</span><span class="sxs-lookup"><span data-stu-id="f3938-131">Tenant of the user who registered.</span></span> <span data-ttu-id="f3938-132">Per altre informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f3938-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3938-133"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="f3938-133"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="f3938-134">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="f3938-134">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="f3938-135">Identificatore univoco dell'endpoint dell'utente registrato con.</span><span class="sxs-lookup"><span data-stu-id="f3938-135">Unique identifier of the endpoint of the user registered with.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3938-136"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="f3938-136"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="f3938-137">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="f3938-137">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="f3938-138">Identificatore univoco usato per distinguere le registrazioni che coinvolgono lo stesso utente e lo stesso endpoint.</span><span class="sxs-lookup"><span data-stu-id="f3938-138">Unique identifier used to differentiate registrations that involve the same user and the same endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3938-139"><strong>DeRegisterType</strong></span><span class="sxs-lookup"><span data-stu-id="f3938-139"><strong>DeRegisterType</strong></span></span></p></td>
<td><p><span data-ttu-id="f3938-140">DateTime</span><span class="sxs-lookup"><span data-stu-id="f3938-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="f3938-141">Ora in cui si è verificata l'annullamento della registrazione.</span><span class="sxs-lookup"><span data-stu-id="f3938-141">Time at which deregistration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3938-142"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="f3938-142"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="f3938-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f3938-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f3938-144">Motivo dell'annullamento della registrazione.</span><span class="sxs-lookup"><span data-stu-id="f3938-144">Reason for deregistration.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3938-145"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="f3938-145"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="f3938-146">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f3938-146">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f3938-147">Versione del client usata dall'utente che ha registrato.</span><span class="sxs-lookup"><span data-stu-id="f3938-147">Version of client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3938-148"><strong>TipoClient</strong></span><span class="sxs-lookup"><span data-stu-id="f3938-148"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="f3938-149">int</span><span class="sxs-lookup"><span data-stu-id="f3938-149">int</span></span></p></td>
<td><p><span data-ttu-id="f3938-150">Client usato dall'utente che ha registrato.</span><span class="sxs-lookup"><span data-stu-id="f3938-150">Client used by the user who registered.</span></span> <span data-ttu-id="f3938-151">Per altri dettagli, vedere la <a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f3938-151">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3938-152"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="f3938-152"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="f3938-153">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="f3938-153">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="f3938-154">Categoria del client usata dall'utente che ha registrato.</span><span class="sxs-lookup"><span data-stu-id="f3938-154">Category of the client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3938-155"><strong>IpAddress</strong></span><span class="sxs-lookup"><span data-stu-id="f3938-155"><strong>IpAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="f3938-156">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f3938-156">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f3938-157">Indirizzo IP con cui l'utente ha registrato.</span><span class="sxs-lookup"><span data-stu-id="f3938-157">IP Address the user registered with.</span></span> <span data-ttu-id="f3938-158">Può trattarsi di un indirizzo IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="f3938-158">This may be an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3938-159"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="f3938-159"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="f3938-160">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="f3938-160">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="f3938-161">ID finestra di dialogo SIP.</span><span class="sxs-lookup"><span data-stu-id="f3938-161">SIP dialog ID.</span></span> <span data-ttu-id="f3938-162">Il formato dell'is:</span><span class="sxs-lookup"><span data-stu-id="f3938-162">The format of the is:</span></span></p>
<p><span data-ttu-id="f3938-163">finestra di dialogo; da-tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="f3938-163">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3938-164"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="f3938-164"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="f3938-165">int</span><span class="sxs-lookup"><span data-stu-id="f3938-165">int</span></span></p></td>
<td><p><span data-ttu-id="f3938-166">Codice di risposta SIP per l'invito alla sessione.</span><span class="sxs-lookup"><span data-stu-id="f3938-166">SIP response code to the session invitation.</span></span> <span data-ttu-id="f3938-167">Questo campo viene in genere popolato da dati generati dal messaggio di invito iniziale nella sessione.</span><span class="sxs-lookup"><span data-stu-id="f3938-167">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="f3938-168">Se non è presente alcun messaggio di invito, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="f3938-168">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3938-169"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="f3938-169"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="f3938-170">int</span><span class="sxs-lookup"><span data-stu-id="f3938-170">int</span></span></p></td>
<td><p><span data-ttu-id="f3938-171">ID di diagnostica acquisito dall'intestazione SIP.</span><span class="sxs-lookup"><span data-stu-id="f3938-171">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3938-172"><strong>Registrar</strong></span><span class="sxs-lookup"><span data-stu-id="f3938-172"><strong>Registrar</strong></span></span></p></td>
<td><p><span data-ttu-id="f3938-173">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f3938-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f3938-174">Nome di dominio completo del registrar.</span><span class="sxs-lookup"><span data-stu-id="f3938-174">FQDN of the Registrar.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3938-175"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="f3938-175"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="f3938-176">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f3938-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f3938-177">Nome di dominio completo del pool che ha acquisito i dati per la sessione.</span><span class="sxs-lookup"><span data-stu-id="f3938-177">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3938-178"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="f3938-178"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="f3938-179">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f3938-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f3938-180">FQDN dell'Edge Server usato dall'utente che ha registrato.</span><span class="sxs-lookup"><span data-stu-id="f3938-180">FQDN of the Edge Server used by the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3938-181"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="f3938-181"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="f3938-182">po'</span><span class="sxs-lookup"><span data-stu-id="f3938-182">bit</span></span></p></td>
<td><p><span data-ttu-id="f3938-183">Indica se l'utente ha effettuato l'accesso dalla rete interna.</span><span class="sxs-lookup"><span data-stu-id="f3938-183">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3938-184"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="f3938-184"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="f3938-185">po'</span><span class="sxs-lookup"><span data-stu-id="f3938-185">bit</span></span></p></td>
<td><p><span data-ttu-id="f3938-186">Indica se il UserService è disponibile al momento della registrazione.</span><span class="sxs-lookup"><span data-stu-id="f3938-186">Indicates whether the UserService was available at registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3938-187"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="f3938-187"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="f3938-188">po'</span><span class="sxs-lookup"><span data-stu-id="f3938-188">bit</span></span></p></td>
<td><p><span data-ttu-id="f3938-189">Indica se la registrazione è stata con il registrar principale.</span><span class="sxs-lookup"><span data-stu-id="f3938-189">Indicates whether registration was with the primary Registrar.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3938-190"><strong>DeviceMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="f3938-190"><strong>DeviceMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="f3938-191">bigint</span><span class="sxs-lookup"><span data-stu-id="f3938-191">bigint</span></span></p></td>
<td><p><span data-ttu-id="f3938-192">Indirizzo MAC del dispositivo registrato.</span><span class="sxs-lookup"><span data-stu-id="f3938-192">MAC Address of device registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3938-193"><strong>DeviceManufacturer</strong></span><span class="sxs-lookup"><span data-stu-id="f3938-193"><strong>DeviceManufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="f3938-194">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f3938-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f3938-195">Produttore del dispositivo registrato.</span><span class="sxs-lookup"><span data-stu-id="f3938-195">Manufacturer of the device registered.</span></span> <span data-ttu-id="f3938-196">Per altre informazioni, vedere la <a href="lync-server-2013-manufacturers-table.md">tabella produttori in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f3938-196">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3938-197"><strong>DeviceHardwareVersion</strong></span><span class="sxs-lookup"><span data-stu-id="f3938-197"><strong>DeviceHardwareVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="f3938-198">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f3938-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f3938-199">Versione hardware del dispositivo registrato.</span><span class="sxs-lookup"><span data-stu-id="f3938-199">Hardware version of the device registered.</span></span> <span data-ttu-id="f3938-200">Per altre informazioni, vedere la <a href="lync-server-2013-hardwareversions-table.md">tabella HardwareVersions in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f3938-200">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


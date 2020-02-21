---
title: 'Lync Server 2013: visualizzazione registrazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Registration view
ms:assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688120(v=OCS.15)
ms:contentKeyID: 49733718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d3683965562d01c5aff33000450182c83e4d4c7b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215102"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="registration-view-in-lync-server-2013"></a><span data-ttu-id="68531-102">Visualizzazione registrazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68531-102">Registration view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68531-103">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="68531-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="68531-104">Nella vista Registration sono archiviate informazioni sulla registrazione degli utenti.</span><span class="sxs-lookup"><span data-stu-id="68531-104">The Registration view stores information about user registration.</span></span> <span data-ttu-id="68531-105">Questa visualizzazione è stata introdotta in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="68531-105">This view was introduced in Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="68531-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="68531-106">Column</span></span></th>
<th><span data-ttu-id="68531-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="68531-107">Data Type</span></span></th>
<th><span data-ttu-id="68531-108">Dettagli</span><span class="sxs-lookup"><span data-stu-id="68531-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="68531-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="68531-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="68531-110">datetime</span><span class="sxs-lookup"><span data-stu-id="68531-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="68531-111">Ora della richiesta di sessione.</span><span class="sxs-lookup"><span data-stu-id="68531-111">Time of session request.</span></span> <span data-ttu-id="68531-112">Valore usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="68531-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="68531-113">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="68531-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68531-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="68531-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="68531-115">int</span><span class="sxs-lookup"><span data-stu-id="68531-115">int</span></span></p></td>
<td><p><span data-ttu-id="68531-116">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="68531-116">ID number to identify the session.</span></span> <span data-ttu-id="68531-117">Valore usato in combinazione con SessionIdTime per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="68531-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="68531-118">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="68531-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68531-119"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="68531-119"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="68531-120">datetime</span><span class="sxs-lookup"><span data-stu-id="68531-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="68531-121">Ora in cui è stata eseguita la registrazione.</span><span class="sxs-lookup"><span data-stu-id="68531-121">Time at which registration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68531-122"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="68531-122"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="68531-123">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="68531-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="68531-124">URI dell'utente che ha effettuato la registrazione.</span><span class="sxs-lookup"><span data-stu-id="68531-124">URI of the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68531-125"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="68531-125"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="68531-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="68531-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="68531-127">Tipo di URI dell'utente che ha effettuato la registrazione.</span><span class="sxs-lookup"><span data-stu-id="68531-127">Type of URI of the user who registered.</span></span> <span data-ttu-id="68531-128">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="68531-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68531-129"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="68531-129"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="68531-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="68531-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="68531-131">Tenant dell'utente che ha effettuato la registrazione.</span><span class="sxs-lookup"><span data-stu-id="68531-131">Tenant of the user who registered.</span></span> <span data-ttu-id="68531-132">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="68531-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68531-133"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="68531-133"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="68531-134">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="68531-134">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="68531-135">Identificatore univoco dell'endpoint in cui l'utente ha effettuato la registrazione.</span><span class="sxs-lookup"><span data-stu-id="68531-135">Unique identifier of the endpoint of the user registered with.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68531-136"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="68531-136"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="68531-137">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="68531-137">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="68531-138">Identificatore univoco usato per differenziare le registrazioni che coinvolgono lo stesso utente e lo stesso endpoint.</span><span class="sxs-lookup"><span data-stu-id="68531-138">Unique identifier used to differentiate registrations that involve the same user and the same endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68531-139"><strong>DeRegisterType</strong></span><span class="sxs-lookup"><span data-stu-id="68531-139"><strong>DeRegisterType</strong></span></span></p></td>
<td><p><span data-ttu-id="68531-140">datetime</span><span class="sxs-lookup"><span data-stu-id="68531-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="68531-141">Ora in cui la registrazione è stata annullata.</span><span class="sxs-lookup"><span data-stu-id="68531-141">Time at which deregistration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68531-142"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="68531-142"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="68531-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="68531-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="68531-144">Motivo dell'annullamento della registrazione.</span><span class="sxs-lookup"><span data-stu-id="68531-144">Reason for deregistration.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68531-145"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="68531-145"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="68531-146">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="68531-146">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="68531-147">Versione del client utilizzata dall'utente che ha effettuato la registrazione.</span><span class="sxs-lookup"><span data-stu-id="68531-147">Version of client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68531-148"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="68531-148"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="68531-149">int</span><span class="sxs-lookup"><span data-stu-id="68531-149">int</span></span></p></td>
<td><p><span data-ttu-id="68531-150">Client utilizzato dall'utente che ha effettuato la registrazione.</span><span class="sxs-lookup"><span data-stu-id="68531-150">Client used by the user who registered.</span></span> <span data-ttu-id="68531-151">Per ulteriori informazioni, vedere la <a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="68531-151">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68531-152"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="68531-152"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="68531-153">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="68531-153">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="68531-154">Categoria del client utilizzato dall'utente che ha effettuato la registrazione.</span><span class="sxs-lookup"><span data-stu-id="68531-154">Category of the client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68531-155"><strong>IpAddress</strong></span><span class="sxs-lookup"><span data-stu-id="68531-155"><strong>IpAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="68531-156">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="68531-156">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="68531-157">Indirizzo IP con cui l'utente ha effettuato la registrazione.</span><span class="sxs-lookup"><span data-stu-id="68531-157">IP Address the user registered with.</span></span> <span data-ttu-id="68531-158">Può trattarsi di un indirizzo IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="68531-158">This may be an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68531-159"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="68531-159"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="68531-160">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="68531-160">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="68531-p108">ID finestra di dialogo SIP. Formato:</span><span class="sxs-lookup"><span data-stu-id="68531-p108">SIP dialog ID. The format of the is:</span></span></p>
<p><span data-ttu-id="68531-163">finestra di dialogo; da-tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="68531-163">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68531-164"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="68531-164"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="68531-165">int</span><span class="sxs-lookup"><span data-stu-id="68531-165">int</span></span></p></td>
<td><p><span data-ttu-id="68531-p109">Codice di risposta SIP all'invito alla sessione. Questo campo viene in genere popolato con i dati generati dal messaggio INVITE iniziale nella sessione. Se non sono presenti messaggi INVITE, il campo viene popolato con data e ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="68531-p109">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68531-169"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="68531-169"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="68531-170">int</span><span class="sxs-lookup"><span data-stu-id="68531-170">int</span></span></p></td>
<td><p><span data-ttu-id="68531-171">ID di diagnostica acquisito dall'intestazione SIP.</span><span class="sxs-lookup"><span data-stu-id="68531-171">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68531-172"><strong>Registrar</strong></span><span class="sxs-lookup"><span data-stu-id="68531-172"><strong>Registrar</strong></span></span></p></td>
<td><p><span data-ttu-id="68531-173">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="68531-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="68531-174">FQDN del registrar.</span><span class="sxs-lookup"><span data-stu-id="68531-174">FQDN of the Registrar.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68531-175"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="68531-175"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="68531-176">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="68531-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="68531-177">FQDN del pool che ha acquisito i dati per la sessione.</span><span class="sxs-lookup"><span data-stu-id="68531-177">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68531-178"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="68531-178"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="68531-179">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="68531-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="68531-180">FQDN del server perimetrale usato dall'utente che ha effettuato la registrazione.</span><span class="sxs-lookup"><span data-stu-id="68531-180">FQDN of the Edge Server used by the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68531-181"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="68531-181"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="68531-182">po'</span><span class="sxs-lookup"><span data-stu-id="68531-182">bit</span></span></p></td>
<td><p><span data-ttu-id="68531-183">Indica se l'utente ha effettuato l'accesso dalla rete interna.</span><span class="sxs-lookup"><span data-stu-id="68531-183">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68531-184"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="68531-184"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="68531-185">po'</span><span class="sxs-lookup"><span data-stu-id="68531-185">bit</span></span></p></td>
<td><p><span data-ttu-id="68531-186">Indica se UserService era disponibile al momento della registrazione.</span><span class="sxs-lookup"><span data-stu-id="68531-186">Indicates whether the UserService was available at registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68531-187"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="68531-187"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="68531-188">po'</span><span class="sxs-lookup"><span data-stu-id="68531-188">bit</span></span></p></td>
<td><p><span data-ttu-id="68531-189">Indica se la registrazione è stata effettuata con il registrar principale.</span><span class="sxs-lookup"><span data-stu-id="68531-189">Indicates whether registration was with the primary Registrar.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68531-190"><strong>DeviceMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="68531-190"><strong>DeviceMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="68531-191">bigint</span><span class="sxs-lookup"><span data-stu-id="68531-191">bigint</span></span></p></td>
<td><p><span data-ttu-id="68531-192">Indirizzo MAC del dispositivo registrato.</span><span class="sxs-lookup"><span data-stu-id="68531-192">MAC Address of device registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68531-193"><strong>DeviceManufacturer</strong></span><span class="sxs-lookup"><span data-stu-id="68531-193"><strong>DeviceManufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="68531-194">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="68531-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="68531-195">Produttore del dispositivo registrato.</span><span class="sxs-lookup"><span data-stu-id="68531-195">Manufacturer of the device registered.</span></span> <span data-ttu-id="68531-196">Per ulteriori informazioni, vedere la <a href="lync-server-2013-manufacturers-table.md">tabella Manufacturers in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="68531-196">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68531-197"><strong>DeviceHardwareVersion</strong></span><span class="sxs-lookup"><span data-stu-id="68531-197"><strong>DeviceHardwareVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="68531-198">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="68531-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="68531-199">Versione hardware del dispositivo registrato.</span><span class="sxs-lookup"><span data-stu-id="68531-199">Hardware version of the device registered.</span></span> <span data-ttu-id="68531-200">Per ulteriori informazioni, vedere la <a href="lync-server-2013-hardwareversions-table.md">tabella HardwareVersions in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="68531-200">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


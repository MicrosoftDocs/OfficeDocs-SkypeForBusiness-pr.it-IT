---
title: 'Lync Server 2013: visualizzazione registrazione'
description: 'Lync Server 2013: visualizzazione registrazione.'
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
ms.openlocfilehash: be169cafc324f89cacedda154ca49a8ff1ff39aa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578528"
---
# <a name="registration-view-in-lync-server-2013"></a><span data-ttu-id="5d406-103">Visualizzazione registrazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d406-103">Registration view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d406-104">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="5d406-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="5d406-105">Nella vista Registration sono archiviate informazioni sulla registrazione degli utenti.</span><span class="sxs-lookup"><span data-stu-id="5d406-105">The Registration view stores information about user registration.</span></span> <span data-ttu-id="5d406-106">Questa visualizzazione è stata introdotta in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5d406-106">This view was introduced in Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5d406-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="5d406-107">Column</span></span></th>
<th><span data-ttu-id="5d406-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="5d406-108">Data Type</span></span></th>
<th><span data-ttu-id="5d406-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="5d406-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5d406-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="5d406-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5d406-111">datetime</span><span class="sxs-lookup"><span data-stu-id="5d406-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="5d406-112">Ora della richiesta di sessione.</span><span class="sxs-lookup"><span data-stu-id="5d406-112">Time of session request.</span></span> <span data-ttu-id="5d406-113">Valore usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="5d406-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="5d406-114">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5d406-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d406-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5d406-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5d406-116">int</span><span class="sxs-lookup"><span data-stu-id="5d406-116">int</span></span></p></td>
<td><p><span data-ttu-id="5d406-117">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="5d406-117">ID number to identify the session.</span></span> <span data-ttu-id="5d406-118">Valore usato in combinazione con SessionIdTime per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="5d406-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="5d406-119">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5d406-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d406-120"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="5d406-120"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5d406-121">datetime</span><span class="sxs-lookup"><span data-stu-id="5d406-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="5d406-122">Ora in cui è stata eseguita la registrazione.</span><span class="sxs-lookup"><span data-stu-id="5d406-122">Time at which registration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d406-123"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="5d406-123"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5d406-124">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5d406-124">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5d406-125">URI dell'utente che ha effettuato la registrazione.</span><span class="sxs-lookup"><span data-stu-id="5d406-125">URI of the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d406-126"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="5d406-126"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5d406-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5d406-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5d406-128">Tipo di URI dell'utente che ha effettuato la registrazione.</span><span class="sxs-lookup"><span data-stu-id="5d406-128">Type of URI of the user who registered.</span></span> <span data-ttu-id="5d406-129">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5d406-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d406-130"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="5d406-130"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="5d406-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5d406-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5d406-132">Tenant dell'utente che ha effettuato la registrazione.</span><span class="sxs-lookup"><span data-stu-id="5d406-132">Tenant of the user who registered.</span></span> <span data-ttu-id="5d406-133">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5d406-133">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d406-134"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="5d406-134"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="5d406-135">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="5d406-135">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="5d406-136">Identificatore univoco dell'endpoint in cui l'utente ha effettuato la registrazione.</span><span class="sxs-lookup"><span data-stu-id="5d406-136">Unique identifier of the endpoint of the user registered with.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d406-137"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="5d406-137"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="5d406-138">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="5d406-138">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="5d406-139">Identificatore univoco usato per differenziare le registrazioni che coinvolgono lo stesso utente e lo stesso endpoint.</span><span class="sxs-lookup"><span data-stu-id="5d406-139">Unique identifier used to differentiate registrations that involve the same user and the same endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d406-140"><strong>DeRegisterType</strong></span><span class="sxs-lookup"><span data-stu-id="5d406-140"><strong>DeRegisterType</strong></span></span></p></td>
<td><p><span data-ttu-id="5d406-141">datetime</span><span class="sxs-lookup"><span data-stu-id="5d406-141">datetime</span></span></p></td>
<td><p><span data-ttu-id="5d406-142">Ora in cui la registrazione è stata annullata.</span><span class="sxs-lookup"><span data-stu-id="5d406-142">Time at which deregistration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d406-143"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="5d406-143"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="5d406-144">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5d406-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5d406-145">Motivo dell'annullamento della registrazione.</span><span class="sxs-lookup"><span data-stu-id="5d406-145">Reason for deregistration.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d406-146"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="5d406-146"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="5d406-147">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5d406-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5d406-148">Versione del client utilizzata dall'utente che ha effettuato la registrazione.</span><span class="sxs-lookup"><span data-stu-id="5d406-148">Version of client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d406-149"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="5d406-149"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="5d406-150">int</span><span class="sxs-lookup"><span data-stu-id="5d406-150">int</span></span></p></td>
<td><p><span data-ttu-id="5d406-151">Client utilizzato dall'utente che ha effettuato la registrazione.</span><span class="sxs-lookup"><span data-stu-id="5d406-151">Client used by the user who registered.</span></span> <span data-ttu-id="5d406-152">Per ulteriori informazioni, vedere la <a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5d406-152">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d406-153"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="5d406-153"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="5d406-154">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="5d406-154">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="5d406-155">Categoria del client utilizzato dall'utente che ha effettuato la registrazione.</span><span class="sxs-lookup"><span data-stu-id="5d406-155">Category of the client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d406-156"><strong>IpAddress</strong></span><span class="sxs-lookup"><span data-stu-id="5d406-156"><strong>IpAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="5d406-157">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5d406-157">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5d406-158">Indirizzo IP con cui l'utente ha effettuato la registrazione.</span><span class="sxs-lookup"><span data-stu-id="5d406-158">IP Address the user registered with.</span></span> <span data-ttu-id="5d406-159">Può trattarsi di un indirizzo IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="5d406-159">This may be an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d406-160"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="5d406-160"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="5d406-161">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="5d406-161">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="5d406-p108">ID finestra di dialogo SIP. Formato:</span><span class="sxs-lookup"><span data-stu-id="5d406-p108">SIP dialog ID. The format of the is:</span></span></p>
<p><span data-ttu-id="5d406-164">finestra di dialogo; da-tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="5d406-164">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d406-165"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="5d406-165"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="5d406-166">int</span><span class="sxs-lookup"><span data-stu-id="5d406-166">int</span></span></p></td>
<td><p><span data-ttu-id="5d406-p109">Codice di risposta SIP all'invito alla sessione. Questo campo viene in genere popolato con i dati generati dal messaggio INVITE iniziale nella sessione. Se non sono presenti messaggi INVITE, il campo viene popolato con data e ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="5d406-p109">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d406-170"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="5d406-170"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="5d406-171">int</span><span class="sxs-lookup"><span data-stu-id="5d406-171">int</span></span></p></td>
<td><p><span data-ttu-id="5d406-172">ID di diagnostica acquisito dall'intestazione SIP.</span><span class="sxs-lookup"><span data-stu-id="5d406-172">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d406-173"><strong>Registrar</strong></span><span class="sxs-lookup"><span data-stu-id="5d406-173"><strong>Registrar</strong></span></span></p></td>
<td><p><span data-ttu-id="5d406-174">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5d406-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5d406-175">FQDN del registrar.</span><span class="sxs-lookup"><span data-stu-id="5d406-175">FQDN of the Registrar.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d406-176"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="5d406-176"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="5d406-177">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5d406-177">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5d406-178">FQDN del pool che ha acquisito i dati per la sessione.</span><span class="sxs-lookup"><span data-stu-id="5d406-178">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d406-179"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="5d406-179"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="5d406-180">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5d406-180">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5d406-181">FQDN del server perimetrale usato dall'utente che ha effettuato la registrazione.</span><span class="sxs-lookup"><span data-stu-id="5d406-181">FQDN of the Edge Server used by the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d406-182"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="5d406-182"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="5d406-183">po'</span><span class="sxs-lookup"><span data-stu-id="5d406-183">bit</span></span></p></td>
<td><p><span data-ttu-id="5d406-184">Indica se l'utente ha effettuato l'accesso dalla rete interna.</span><span class="sxs-lookup"><span data-stu-id="5d406-184">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d406-185"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="5d406-185"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="5d406-186">po'</span><span class="sxs-lookup"><span data-stu-id="5d406-186">bit</span></span></p></td>
<td><p><span data-ttu-id="5d406-187">Indica se UserService era disponibile al momento della registrazione.</span><span class="sxs-lookup"><span data-stu-id="5d406-187">Indicates whether the UserService was available at registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d406-188"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="5d406-188"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="5d406-189">po'</span><span class="sxs-lookup"><span data-stu-id="5d406-189">bit</span></span></p></td>
<td><p><span data-ttu-id="5d406-190">Indica se la registrazione è stata effettuata con il registrar principale.</span><span class="sxs-lookup"><span data-stu-id="5d406-190">Indicates whether registration was with the primary Registrar.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d406-191"><strong>DeviceMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="5d406-191"><strong>DeviceMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="5d406-192">bigint</span><span class="sxs-lookup"><span data-stu-id="5d406-192">bigint</span></span></p></td>
<td><p><span data-ttu-id="5d406-193">Indirizzo MAC del dispositivo registrato.</span><span class="sxs-lookup"><span data-stu-id="5d406-193">MAC Address of device registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d406-194"><strong>DeviceManufacturer</strong></span><span class="sxs-lookup"><span data-stu-id="5d406-194"><strong>DeviceManufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="5d406-195">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5d406-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5d406-196">Produttore del dispositivo registrato.</span><span class="sxs-lookup"><span data-stu-id="5d406-196">Manufacturer of the device registered.</span></span> <span data-ttu-id="5d406-197">Per ulteriori informazioni, vedere la <a href="lync-server-2013-manufacturers-table.md">tabella Manufacturers in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5d406-197">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d406-198"><strong>DeviceHardwareVersion</strong></span><span class="sxs-lookup"><span data-stu-id="5d406-198"><strong>DeviceHardwareVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="5d406-199">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5d406-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5d406-200">Versione hardware del dispositivo registrato.</span><span class="sxs-lookup"><span data-stu-id="5d406-200">Hardware version of the device registered.</span></span> <span data-ttu-id="5d406-201">Per ulteriori informazioni, vedere la <a href="lync-server-2013-hardwareversions-table.md">tabella HardwareVersions in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5d406-201">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


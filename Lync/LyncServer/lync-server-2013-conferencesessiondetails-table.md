---
title: 'Lync Server 2013: tabella ConferenceSessionDetails'
description: 'Lync Server 2013: tabella ConferenceSessionDetails.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceSessionDetails table
ms:assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412741(v=OCS.15)
ms:contentKeyID: 48184925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d101eb1607e366ab814e60acaeee80820fe87c5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566782"
---
# <a name="conferencesessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="cd043-103">Tabella ConferenceSessionDetails in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd043-103">ConferenceSessionDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd043-104">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="cd043-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="cd043-105">Ogni record rappresenta una sessione di conferenza, che può indicare la sessione con Focus o la sessione con un server per conferenze specifico.</span><span class="sxs-lookup"><span data-stu-id="cd043-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cd043-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="cd043-106">Column</span></span></th>
<th><span data-ttu-id="cd043-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="cd043-107">Data Type</span></span></th>
<th><span data-ttu-id="cd043-108">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="cd043-108">Key/Index</span></span></th>
<th><span data-ttu-id="cd043-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="cd043-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cd043-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="cd043-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cd043-111">DateTime</span><span class="sxs-lookup"><span data-stu-id="cd043-111">Datetime</span></span></p></td>
<td><p><span data-ttu-id="cd043-112">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="cd043-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="cd043-113">Ora della richiesta di sessione; utilizzato insieme a <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione di conferenza.</span><span class="sxs-lookup"><span data-stu-id="cd043-113">Time of session request; used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="cd043-114">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cd043-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd043-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="cd043-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="cd043-116">int</span><span class="sxs-lookup"><span data-stu-id="cd043-116">int</span></span></p></td>
<td><p><span data-ttu-id="cd043-117">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="cd043-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="cd043-118">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="cd043-118">ID number to identify the session.</span></span> <span data-ttu-id="cd043-119">Utilizzato insieme a <strong>SessionIdTime</strong> per identificare in modo univoco una sessione di conferenza.</span><span class="sxs-lookup"><span data-stu-id="cd043-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="cd043-120">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cd043-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd043-121"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="cd043-121"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="cd043-122">int</span><span class="sxs-lookup"><span data-stu-id="cd043-122">int</span></span></p></td>
<td><p><span data-ttu-id="cd043-123">Stranieri</span><span class="sxs-lookup"><span data-stu-id="cd043-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cd043-124">URI di conferenza Focus associato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="cd043-124">Focus conference URI related to this session.</span></span> <span data-ttu-id="cd043-125">Per ulteriori informazioni, vedere la <a href="lync-server-2013-conferenceuris-table.md">tabella ConferenceUris in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cd043-125">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="cd043-126">Si tratta di un URI di conferenza basata su Focus.</span><span class="sxs-lookup"><span data-stu-id="cd043-126">This URI is a Focus-based conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd043-127"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="cd043-127"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="cd043-128">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="cd043-128">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cd043-129">Identificare che distingue le istanze di conferenze ricorrenti.</span><span class="sxs-lookup"><span data-stu-id="cd043-129">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="cd043-130">Ogni conferenza ricorrente presenta lo stesso valore di ConferenceURI ma un valore diverso di ConfInstance.</span><span class="sxs-lookup"><span data-stu-id="cd043-130">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p>
<p><span data-ttu-id="cd043-131">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cd043-131">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd043-132"><strong>McuConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="cd043-132"><strong>McuConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="cd043-133">int</span><span class="sxs-lookup"><span data-stu-id="cd043-133">int</span></span></p></td>
<td><p><span data-ttu-id="cd043-134">Stranieri</span><span class="sxs-lookup"><span data-stu-id="cd043-134">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cd043-135">URI di conferenza del server per conferenze associato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="cd043-135">Conferencing server conference URI related to this session.</span></span> <span data-ttu-id="cd043-136">Per ulteriori informazioni, vedere la <a href="lync-server-2013-conferenceuris-table.md">tabella ConferenceUris in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cd043-136">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="cd043-137">Si tratta di un URI di conferenza basata su server di conferenza.</span><span class="sxs-lookup"><span data-stu-id="cd043-137">This URI is the conferencing server-based conference URI.</span></span> <span data-ttu-id="cd043-138">Per le sessioni di conferenza Focus, questa colonna sarà null.</span><span class="sxs-lookup"><span data-stu-id="cd043-138">For Focus conference sessions, this column will be null.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd043-139"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="cd043-139"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="cd043-140">int</span><span class="sxs-lookup"><span data-stu-id="cd043-140">int</span></span></p></td>
<td><p><span data-ttu-id="cd043-141">Stranieri</span><span class="sxs-lookup"><span data-stu-id="cd043-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cd043-142">ID di un utente nella sessione di conferenza.</span><span class="sxs-lookup"><span data-stu-id="cd043-142">ID of one user in the conference session.</span></span> <span data-ttu-id="cd043-143">Per ulteriori informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cd043-143">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd043-144"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="cd043-144"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="cd043-145">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="cd043-145">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cd043-p107">GUID per l'identificazione dell'istanza dell'endpoint. Ad esempio, se un utente accede a due computer con lo stesso account, ogni computer disporrà di un ID endpoint diverso.</span><span class="sxs-lookup"><span data-stu-id="cd043-p107">A GUID to identify the instance of endpoint. For example, if one user logs on to different machines with the same account, then each machine will have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd043-148"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="cd043-148"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="cd043-149">int</span><span class="sxs-lookup"><span data-stu-id="cd043-149">int</span></span></p></td>
<td><p><span data-ttu-id="cd043-150">Stranieri</span><span class="sxs-lookup"><span data-stu-id="cd043-150">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cd043-151">Indica l'ID dell'utente per conto del quale il chiamante esegue la chiamata.</span><span class="sxs-lookup"><span data-stu-id="cd043-151">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="cd043-152">Per ulteriori informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cd043-152">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd043-153"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="cd043-153"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="cd043-154">int</span><span class="sxs-lookup"><span data-stu-id="cd043-154">int</span></span></p></td>
<td><p><span data-ttu-id="cd043-155">Stranieri</span><span class="sxs-lookup"><span data-stu-id="cd043-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cd043-156">ID dell'utente da quale proviene la chiamata.</span><span class="sxs-lookup"><span data-stu-id="cd043-156">ID of the user by who the call is referred.</span></span> <span data-ttu-id="cd043-157">Per ulteriori informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cd043-157">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd043-158"><strong>UserClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="cd043-158"><strong>UserClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="cd043-159">int</span><span class="sxs-lookup"><span data-stu-id="cd043-159">int</span></span></p></td>
<td><p><span data-ttu-id="cd043-160">Stranieri</span><span class="sxs-lookup"><span data-stu-id="cd043-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cd043-161">Versione del client utilizzata dall'utente della conferenza.</span><span class="sxs-lookup"><span data-stu-id="cd043-161">Client version used by the conference user.</span></span> <span data-ttu-id="cd043-162">Per ulteriori informazioni, vedere la <a href="lync-server-2013-clientversions-table.md">Tabella ClientVersions in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cd043-162">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd043-163"><strong>ConfClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="cd043-163"><strong>ConfClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="cd043-164">int</span><span class="sxs-lookup"><span data-stu-id="cd043-164">int</span></span></p></td>
<td><p><span data-ttu-id="cd043-165">Stranieri</span><span class="sxs-lookup"><span data-stu-id="cd043-165">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cd043-166">Versione del client utilizzata dal server per conferenze.</span><span class="sxs-lookup"><span data-stu-id="cd043-166">Client version used by the conference server.</span></span> <span data-ttu-id="cd043-167">Per ulteriori informazioni, vedere la <a href="lync-server-2013-clientversions-table.md">Tabella ClientVersions in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cd043-167">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd043-168"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="cd043-168"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cd043-169">datetime</span><span class="sxs-lookup"><span data-stu-id="cd043-169">datetime</span></span></p></td>
<td><p><span data-ttu-id="cd043-170">Stranieri</span><span class="sxs-lookup"><span data-stu-id="cd043-170">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cd043-171">Numero ID per l'identificazione della finestra di dialogo sostituita dalla sessione corrente.</span><span class="sxs-lookup"><span data-stu-id="cd043-171">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="cd043-172">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cd043-172">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd043-173"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="cd043-173"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="cd043-174">int</span><span class="sxs-lookup"><span data-stu-id="cd043-174">int</span></span></p></td>
<td><p><span data-ttu-id="cd043-175">Stranieri</span><span class="sxs-lookup"><span data-stu-id="cd043-175">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cd043-176">Numero ID per l'identificazione della sessione.</span><span class="sxs-lookup"><span data-stu-id="cd043-176">ID number to identify the session.</span></span> <span data-ttu-id="cd043-177">Valore utilizzato in combinazione con <strong>ReplacesDialogIdTime</strong> per identificare in modo univoco una sessione sostituita da questa sessione.</span><span class="sxs-lookup"><span data-stu-id="cd043-177">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="cd043-178">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cd043-178">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd043-179"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="cd043-179"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="cd043-180">po'</span><span class="sxs-lookup"><span data-stu-id="cd043-180">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cd043-181">Indica se la sessione è stata avviata dal server per conferenze.</span><span class="sxs-lookup"><span data-stu-id="cd043-181">Indicates if the session started by the conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd043-182"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="cd043-182"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="cd043-183">po'</span><span class="sxs-lookup"><span data-stu-id="cd043-183">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cd043-184">Indica se la sessione è stata terminata dal server per conferenze.</span><span class="sxs-lookup"><span data-stu-id="cd043-184">Indicates if the session ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd043-185"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="cd043-185"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="cd043-186">po'</span><span class="sxs-lookup"><span data-stu-id="cd043-186">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cd043-187">Indica se l'utente è connesso dall'interno o meno.</span><span class="sxs-lookup"><span data-stu-id="cd043-187">Whether user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd043-188"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="cd043-188"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="cd043-189">int</span><span class="sxs-lookup"><span data-stu-id="cd043-189">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cd043-190">Codice di risposta SIP (Session Initiation Protocol) all'invito alla sessione.</span><span class="sxs-lookup"><span data-stu-id="cd043-190">Session Initiation Protocol (SIP) response code to the session invitation.</span></span> <span data-ttu-id="cd043-191">Questo campo viene in genere popolato con i dati generati dal messaggio INVITE iniziale nella sessione.</span><span class="sxs-lookup"><span data-stu-id="cd043-191">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="cd043-192">Se non sono presenti messaggi INVITE, il campo viene popolato con data e ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="cd043-192">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd043-193"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="cd043-193"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="cd043-194">int</span><span class="sxs-lookup"><span data-stu-id="cd043-194">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cd043-195">ID di diagnostica acquisito dall'intestazione SIP.</span><span class="sxs-lookup"><span data-stu-id="cd043-195">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd043-196"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="cd043-196"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="cd043-197">int</span><span class="sxs-lookup"><span data-stu-id="cd043-197">int</span></span></p></td>
<td><p><span data-ttu-id="cd043-198">Stranieri</span><span class="sxs-lookup"><span data-stu-id="cd043-198">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cd043-199">ID del Front End Server utilizzato per questa sessione.</span><span class="sxs-lookup"><span data-stu-id="cd043-199">ID of the front-end server used for this session.</span></span> <span data-ttu-id="cd043-200">Per ulteriori informazioni, vedere la <a href="lync-server-2013-servers-table.md">tabella Servers in Lync server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cd043-200">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd043-201"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="cd043-201"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="cd043-202">int</span><span class="sxs-lookup"><span data-stu-id="cd043-202">int</span></span></p></td>
<td><p><span data-ttu-id="cd043-203">Stranieri</span><span class="sxs-lookup"><span data-stu-id="cd043-203">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cd043-204">ID del pool in cui è stata acquisita la sessione.</span><span class="sxs-lookup"><span data-stu-id="cd043-204">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="cd043-205">Per ulteriori informazioni, vedere la <a href="lync-server-2013-pools-table.md">Tabella Pools in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cd043-205">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd043-206"><strong>MediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="cd043-206"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="cd043-207">int</span><span class="sxs-lookup"><span data-stu-id="cd043-207">int</span></span></p></td>
<td><p><span data-ttu-id="cd043-208">Stranieri</span><span class="sxs-lookup"><span data-stu-id="cd043-208">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cd043-209">Mediation Server utilizzato dalla chiamata.</span><span class="sxs-lookup"><span data-stu-id="cd043-209">The Mediation Server the call is using.</span></span> <span data-ttu-id="cd043-210">Per ulteriori informazioni, vedere la <a href="lync-server-2013-mediationservers-table.md">Tabella MediationServers in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cd043-210">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd043-211"><strong>GatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="cd043-211"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="cd043-212">int</span><span class="sxs-lookup"><span data-stu-id="cd043-212">int</span></span></p></td>
<td><p><span data-ttu-id="cd043-213">Stranieri</span><span class="sxs-lookup"><span data-stu-id="cd043-213">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cd043-214">Gateway utilizzato dalla chiamata.</span><span class="sxs-lookup"><span data-stu-id="cd043-214">The gateway the call is using.</span></span> <span data-ttu-id="cd043-215">Per ulteriori informazioni, vedere la <a href="lync-server-2013-gateways-table.md">tabella gateway in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cd043-215">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd043-216"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="cd043-216"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="cd043-217">int</span><span class="sxs-lookup"><span data-stu-id="cd043-217">int</span></span></p></td>
<td><p><span data-ttu-id="cd043-218">Stranieri</span><span class="sxs-lookup"><span data-stu-id="cd043-218">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cd043-219">Server perimetrale utilizzato dalla chiamata.</span><span class="sxs-lookup"><span data-stu-id="cd043-219">The Edge Server the call is using.</span></span> <span data-ttu-id="cd043-220">Per ulteriori informazioni, vedere la <a href="lync-server-2013-edgeservers-table.md">tabella EdgeServers in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cd043-220">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd043-221"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="cd043-221"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="cd043-222">int</span><span class="sxs-lookup"><span data-stu-id="cd043-222">int</span></span></p></td>
<td><p><span data-ttu-id="cd043-223">Stranieri</span><span class="sxs-lookup"><span data-stu-id="cd043-223">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cd043-224">Tipo di contenuto utilizzato nella sessione.</span><span class="sxs-lookup"><span data-stu-id="cd043-224">Content type used in the session.</span></span> <span data-ttu-id="cd043-225">Per ulteriori informazioni, vedere la <a href="lync-server-2013-contenttypes-table.md">tabella ContentTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cd043-225">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd043-226"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="cd043-226"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cd043-227">datetime</span><span class="sxs-lookup"><span data-stu-id="cd043-227">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cd043-p121">Ora della prima richiesta INVITE. Questo campo viene in genere popolato con i dati generati dal messaggio INVITE iniziale nella sessione. Se non sono presenti messaggi INVITE, il campo viene popolato con data e ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="cd043-p121">The time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd043-231"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="cd043-231"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cd043-232">datetime</span><span class="sxs-lookup"><span data-stu-id="cd043-232">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cd043-233">Ora della prima risposta SIP.</span><span class="sxs-lookup"><span data-stu-id="cd043-233">Time of the first SIP RESPONSE.</span></span> <span data-ttu-id="cd043-234">Questo campo viene in genere popolato con i dati generati dal messaggio INVITE iniziale nella sessione.</span><span class="sxs-lookup"><span data-stu-id="cd043-234">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="cd043-235">Se non sono presenti messaggi INVITE, il campo viene popolato con data e ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="cd043-235">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd043-236"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="cd043-236"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cd043-237">datetime</span><span class="sxs-lookup"><span data-stu-id="cd043-237">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cd043-238">Ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="cd043-238">The time when the session is ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd043-239"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="cd043-239"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="cd043-240">tinyint</span><span class="sxs-lookup"><span data-stu-id="cd043-240">tinyint</span></span></p></td>
<td><p><span data-ttu-id="cd043-241">Stranieri</span><span class="sxs-lookup"><span data-stu-id="cd043-241">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cd043-242">Contiene il valore del tipo di URI MCU dalla <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="cd043-242">Contains the MCU URI type value from the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a>.</span></span> <span data-ttu-id="cd043-243">Questo campo è usato per migliorare le prestazioni di query.</span><span class="sxs-lookup"><span data-stu-id="cd043-243">This field is used for improving query performance.</span></span></p>
<p><span data-ttu-id="cd043-244">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cd043-244">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd043-245"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="cd043-245"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="cd043-246">smallint</span><span class="sxs-lookup"><span data-stu-id="cd043-246">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cd043-p124">Set di bit che indica gli attributi dell'utente. Sono incluse le definizioni di attributo seguenti:</span><span class="sxs-lookup"><span data-stu-id="cd043-p124">A bit set that indicates the user attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="cd043-249">Integrato con telefono da tavolo  - 1</span><span class="sxs-lookup"><span data-stu-id="cd043-249">Integrated with desktop phone - 1</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd043-250"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="cd043-250"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="cd043-251">smallint</span><span class="sxs-lookup"><span data-stu-id="cd043-251">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cd043-p125">Set di bit che indica gli attributi della chiamata. Sono incluse le definizioni di attributo seguenti:</span><span class="sxs-lookup"><span data-stu-id="cd043-p125">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="cd043-254">Sessione ripetuta  - 1</span><span class="sxs-lookup"><span data-stu-id="cd043-254">Retried Session - 1</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cd043-255">\* Per la maggior parte delle sessioni, SessionIdSeq avrà il valore 1.</span><span class="sxs-lookup"><span data-stu-id="cd043-255">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="cd043-256">Se più sessioni iniziano esattamente alla stessa ora, il valore SessionIdSeq per una sarà 1, per l'altra sarà 2 e così via.</span><span class="sxs-lookup"><span data-stu-id="cd043-256">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


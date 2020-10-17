---
title: 'Lync Server 2013: tabella ConferenceSessionDetails'
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
ms.openlocfilehash: 57d8e3cb0a79c8ce6a6c1c51891fbad265f045de
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529203"
---
# <a name="conferencesessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="5c3b9-102">Tabella ConferenceSessionDetails in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5c3b9-102">ConferenceSessionDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5c3b9-103">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="5c3b9-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="5c3b9-104">Ogni record rappresenta una sessione di conferenza, che può indicare la sessione con Focus o la sessione con un server per conferenze specifico.</span><span class="sxs-lookup"><span data-stu-id="5c3b9-104">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5c3b9-105">Colonna</span><span class="sxs-lookup"><span data-stu-id="5c3b9-105">Column</span></span></th>
<th><span data-ttu-id="5c3b9-106">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="5c3b9-106">Data Type</span></span></th>
<th><span data-ttu-id="5c3b9-107">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="5c3b9-107">Key/Index</span></span></th>
<th><span data-ttu-id="5c3b9-108">Dettagli</span><span class="sxs-lookup"><span data-stu-id="5c3b9-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5c3b9-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="5c3b9-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5c3b9-110">DateTime</span><span class="sxs-lookup"><span data-stu-id="5c3b9-110">Datetime</span></span></p></td>
<td><p><span data-ttu-id="5c3b9-111">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="5c3b9-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="5c3b9-112">Ora della richiesta di sessione; utilizzato insieme a <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione di conferenza.</span><span class="sxs-lookup"><span data-stu-id="5c3b9-112">Time of session request; used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="5c3b9-113">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5c3b9-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c3b9-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5c3b9-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5c3b9-115">int</span><span class="sxs-lookup"><span data-stu-id="5c3b9-115">int</span></span></p></td>
<td><p><span data-ttu-id="5c3b9-116">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="5c3b9-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="5c3b9-117">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="5c3b9-117">ID number to identify the session.</span></span> <span data-ttu-id="5c3b9-118">Utilizzato insieme a <strong>SessionIdTime</strong> per identificare in modo univoco una sessione di conferenza.</span><span class="sxs-lookup"><span data-stu-id="5c3b9-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="5c3b9-119">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5c3b9-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c3b9-120"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="5c3b9-120"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="5c3b9-121">int</span><span class="sxs-lookup"><span data-stu-id="5c3b9-121">int</span></span></p></td>
<td><p><span data-ttu-id="5c3b9-122">Stranieri</span><span class="sxs-lookup"><span data-stu-id="5c3b9-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5c3b9-123">URI di conferenza Focus associato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="5c3b9-123">Focus conference URI related to this session.</span></span> <span data-ttu-id="5c3b9-124">Per ulteriori informazioni, vedere la <a href="lync-server-2013-conferenceuris-table.md">tabella ConferenceUris in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5c3b9-124">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="5c3b9-125">Si tratta di un URI di conferenza basata su Focus.</span><span class="sxs-lookup"><span data-stu-id="5c3b9-125">This URI is a Focus-based conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c3b9-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="5c3b9-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="5c3b9-127">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="5c3b9-127">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5c3b9-128">Identificare che distingue le istanze di conferenze ricorrenti.</span><span class="sxs-lookup"><span data-stu-id="5c3b9-128">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="5c3b9-129">Ogni conferenza ricorrente presenta lo stesso valore di ConferenceURI ma un valore diverso di ConfInstance.</span><span class="sxs-lookup"><span data-stu-id="5c3b9-129">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p>
<p><span data-ttu-id="5c3b9-130">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5c3b9-130">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c3b9-131"><strong>McuConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="5c3b9-131"><strong>McuConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="5c3b9-132">int</span><span class="sxs-lookup"><span data-stu-id="5c3b9-132">int</span></span></p></td>
<td><p><span data-ttu-id="5c3b9-133">Stranieri</span><span class="sxs-lookup"><span data-stu-id="5c3b9-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5c3b9-134">URI di conferenza del server per conferenze associato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="5c3b9-134">Conferencing server conference URI related to this session.</span></span> <span data-ttu-id="5c3b9-135">Per ulteriori informazioni, vedere la <a href="lync-server-2013-conferenceuris-table.md">tabella ConferenceUris in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5c3b9-135">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="5c3b9-136">Si tratta di un URI di conferenza basata su server di conferenza.</span><span class="sxs-lookup"><span data-stu-id="5c3b9-136">This URI is the conferencing server-based conference URI.</span></span> <span data-ttu-id="5c3b9-137">Per le sessioni di conferenza Focus, questa colonna sarà null.</span><span class="sxs-lookup"><span data-stu-id="5c3b9-137">For Focus conference sessions, this column will be null.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c3b9-138"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="5c3b9-138"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="5c3b9-139">int</span><span class="sxs-lookup"><span data-stu-id="5c3b9-139">int</span></span></p></td>
<td><p><span data-ttu-id="5c3b9-140">Stranieri</span><span class="sxs-lookup"><span data-stu-id="5c3b9-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5c3b9-141">ID di un utente nella sessione di conferenza.</span><span class="sxs-lookup"><span data-stu-id="5c3b9-141">ID of one user in the conference session.</span></span> <span data-ttu-id="5c3b9-142">Per ulteriori informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5c3b9-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c3b9-143"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="5c3b9-143"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="5c3b9-144">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="5c3b9-144">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5c3b9-p107">GUID per l'identificazione dell'istanza dell'endpoint. Ad esempio, se un utente accede a due computer con lo stesso account, ogni computer disporrà di un ID endpoint diverso.</span><span class="sxs-lookup"><span data-stu-id="5c3b9-p107">A GUID to identify the instance of endpoint. For example, if one user logs on to different machines with the same account, then each machine will have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c3b9-147"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="5c3b9-147"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="5c3b9-148">int</span><span class="sxs-lookup"><span data-stu-id="5c3b9-148">int</span></span></p></td>
<td><p><span data-ttu-id="5c3b9-149">Stranieri</span><span class="sxs-lookup"><span data-stu-id="5c3b9-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5c3b9-150">Indica l'ID dell'utente per conto del quale il chiamante esegue la chiamata.</span><span class="sxs-lookup"><span data-stu-id="5c3b9-150">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="5c3b9-151">Per ulteriori informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5c3b9-151">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c3b9-152"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="5c3b9-152"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="5c3b9-153">int</span><span class="sxs-lookup"><span data-stu-id="5c3b9-153">int</span></span></p></td>
<td><p><span data-ttu-id="5c3b9-154">Stranieri</span><span class="sxs-lookup"><span data-stu-id="5c3b9-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5c3b9-155">ID dell'utente da quale proviene la chiamata.</span><span class="sxs-lookup"><span data-stu-id="5c3b9-155">ID of the user by who the call is referred.</span></span> <span data-ttu-id="5c3b9-156">Per ulteriori informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5c3b9-156">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c3b9-157"><strong>UserClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="5c3b9-157"><strong>UserClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="5c3b9-158">int</span><span class="sxs-lookup"><span data-stu-id="5c3b9-158">int</span></span></p></td>
<td><p><span data-ttu-id="5c3b9-159">Stranieri</span><span class="sxs-lookup"><span data-stu-id="5c3b9-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5c3b9-160">Versione del client utilizzata dall'utente della conferenza.</span><span class="sxs-lookup"><span data-stu-id="5c3b9-160">Client version used by the conference user.</span></span> <span data-ttu-id="5c3b9-161">Per ulteriori informazioni, vedere la <a href="lync-server-2013-clientversions-table.md">Tabella ClientVersions in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5c3b9-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c3b9-162"><strong>ConfClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="5c3b9-162"><strong>ConfClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="5c3b9-163">int</span><span class="sxs-lookup"><span data-stu-id="5c3b9-163">int</span></span></p></td>
<td><p><span data-ttu-id="5c3b9-164">Stranieri</span><span class="sxs-lookup"><span data-stu-id="5c3b9-164">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5c3b9-165">Versione del client utilizzata dal server per conferenze.</span><span class="sxs-lookup"><span data-stu-id="5c3b9-165">Client version used by the conference server.</span></span> <span data-ttu-id="5c3b9-166">Per ulteriori informazioni, vedere la <a href="lync-server-2013-clientversions-table.md">Tabella ClientVersions in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5c3b9-166">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c3b9-167"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="5c3b9-167"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5c3b9-168">datetime</span><span class="sxs-lookup"><span data-stu-id="5c3b9-168">datetime</span></span></p></td>
<td><p><span data-ttu-id="5c3b9-169">Stranieri</span><span class="sxs-lookup"><span data-stu-id="5c3b9-169">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5c3b9-170">Numero ID per l'identificazione della finestra di dialogo sostituita dalla sessione corrente.</span><span class="sxs-lookup"><span data-stu-id="5c3b9-170">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="5c3b9-171">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5c3b9-171">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c3b9-172"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5c3b9-172"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5c3b9-173">int</span><span class="sxs-lookup"><span data-stu-id="5c3b9-173">int</span></span></p></td>
<td><p><span data-ttu-id="5c3b9-174">Stranieri</span><span class="sxs-lookup"><span data-stu-id="5c3b9-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5c3b9-175">Numero ID per l'identificazione della sessione.</span><span class="sxs-lookup"><span data-stu-id="5c3b9-175">ID number to identify the session.</span></span> <span data-ttu-id="5c3b9-176">Valore utilizzato in combinazione con <strong>ReplacesDialogIdTime</strong> per identificare in modo univoco una sessione sostituita da questa sessione.</span><span class="sxs-lookup"><span data-stu-id="5c3b9-176">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="5c3b9-177">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5c3b9-177">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c3b9-178"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="5c3b9-178"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="5c3b9-179">po'</span><span class="sxs-lookup"><span data-stu-id="5c3b9-179">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5c3b9-180">Indica se la sessione è stata avviata dal server per conferenze.</span><span class="sxs-lookup"><span data-stu-id="5c3b9-180">Indicates if the session started by the conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c3b9-181"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="5c3b9-181"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="5c3b9-182">po'</span><span class="sxs-lookup"><span data-stu-id="5c3b9-182">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5c3b9-183">Indica se la sessione è stata terminata dal server per conferenze.</span><span class="sxs-lookup"><span data-stu-id="5c3b9-183">Indicates if the session ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c3b9-184"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="5c3b9-184"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="5c3b9-185">po'</span><span class="sxs-lookup"><span data-stu-id="5c3b9-185">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5c3b9-186">Indica se l'utente è connesso dall'interno o meno.</span><span class="sxs-lookup"><span data-stu-id="5c3b9-186">Whether user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c3b9-187"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="5c3b9-187"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="5c3b9-188">int</span><span class="sxs-lookup"><span data-stu-id="5c3b9-188">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5c3b9-189">Codice di risposta SIP (Session Initiation Protocol) all'invito alla sessione.</span><span class="sxs-lookup"><span data-stu-id="5c3b9-189">Session Initiation Protocol (SIP) response code to the session invitation.</span></span> <span data-ttu-id="5c3b9-190">Questo campo viene in genere popolato con i dati generati dal messaggio INVITE iniziale nella sessione.</span><span class="sxs-lookup"><span data-stu-id="5c3b9-190">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="5c3b9-191">Se non sono presenti messaggi INVITE, il campo viene popolato con data e ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="5c3b9-191">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c3b9-192"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="5c3b9-192"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="5c3b9-193">int</span><span class="sxs-lookup"><span data-stu-id="5c3b9-193">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5c3b9-194">ID di diagnostica acquisito dall'intestazione SIP.</span><span class="sxs-lookup"><span data-stu-id="5c3b9-194">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c3b9-195"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="5c3b9-195"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="5c3b9-196">int</span><span class="sxs-lookup"><span data-stu-id="5c3b9-196">int</span></span></p></td>
<td><p><span data-ttu-id="5c3b9-197">Stranieri</span><span class="sxs-lookup"><span data-stu-id="5c3b9-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5c3b9-198">ID del Front End Server utilizzato per questa sessione.</span><span class="sxs-lookup"><span data-stu-id="5c3b9-198">ID of the front-end server used for this session.</span></span> <span data-ttu-id="5c3b9-199">Per ulteriori informazioni, vedere la <a href="lync-server-2013-servers-table.md">tabella Servers in Lync server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5c3b9-199">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c3b9-200"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="5c3b9-200"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="5c3b9-201">int</span><span class="sxs-lookup"><span data-stu-id="5c3b9-201">int</span></span></p></td>
<td><p><span data-ttu-id="5c3b9-202">Stranieri</span><span class="sxs-lookup"><span data-stu-id="5c3b9-202">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5c3b9-203">ID del pool in cui è stata acquisita la sessione.</span><span class="sxs-lookup"><span data-stu-id="5c3b9-203">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="5c3b9-204">Per ulteriori informazioni, vedere la <a href="lync-server-2013-pools-table.md">Tabella Pools in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5c3b9-204">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c3b9-205"><strong>MediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="5c3b9-205"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="5c3b9-206">int</span><span class="sxs-lookup"><span data-stu-id="5c3b9-206">int</span></span></p></td>
<td><p><span data-ttu-id="5c3b9-207">Stranieri</span><span class="sxs-lookup"><span data-stu-id="5c3b9-207">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5c3b9-208">Mediation Server utilizzato dalla chiamata.</span><span class="sxs-lookup"><span data-stu-id="5c3b9-208">The Mediation Server the call is using.</span></span> <span data-ttu-id="5c3b9-209">Per ulteriori informazioni, vedere la <a href="lync-server-2013-mediationservers-table.md">Tabella MediationServers in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5c3b9-209">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c3b9-210"><strong>GatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="5c3b9-210"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="5c3b9-211">int</span><span class="sxs-lookup"><span data-stu-id="5c3b9-211">int</span></span></p></td>
<td><p><span data-ttu-id="5c3b9-212">Stranieri</span><span class="sxs-lookup"><span data-stu-id="5c3b9-212">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5c3b9-213">Gateway utilizzato dalla chiamata.</span><span class="sxs-lookup"><span data-stu-id="5c3b9-213">The gateway the call is using.</span></span> <span data-ttu-id="5c3b9-214">Per ulteriori informazioni, vedere la <a href="lync-server-2013-gateways-table.md">tabella gateway in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5c3b9-214">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c3b9-215"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="5c3b9-215"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="5c3b9-216">int</span><span class="sxs-lookup"><span data-stu-id="5c3b9-216">int</span></span></p></td>
<td><p><span data-ttu-id="5c3b9-217">Stranieri</span><span class="sxs-lookup"><span data-stu-id="5c3b9-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5c3b9-218">Server perimetrale utilizzato dalla chiamata.</span><span class="sxs-lookup"><span data-stu-id="5c3b9-218">The Edge Server the call is using.</span></span> <span data-ttu-id="5c3b9-219">Per ulteriori informazioni, vedere la <a href="lync-server-2013-edgeservers-table.md">tabella EdgeServers in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5c3b9-219">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c3b9-220"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="5c3b9-220"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="5c3b9-221">int</span><span class="sxs-lookup"><span data-stu-id="5c3b9-221">int</span></span></p></td>
<td><p><span data-ttu-id="5c3b9-222">Stranieri</span><span class="sxs-lookup"><span data-stu-id="5c3b9-222">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5c3b9-223">Tipo di contenuto utilizzato nella sessione.</span><span class="sxs-lookup"><span data-stu-id="5c3b9-223">Content type used in the session.</span></span> <span data-ttu-id="5c3b9-224">Per ulteriori informazioni, vedere la <a href="lync-server-2013-contenttypes-table.md">tabella ContentTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5c3b9-224">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c3b9-225"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="5c3b9-225"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5c3b9-226">datetime</span><span class="sxs-lookup"><span data-stu-id="5c3b9-226">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5c3b9-p121">Ora della prima richiesta INVITE. Questo campo viene in genere popolato con i dati generati dal messaggio INVITE iniziale nella sessione. Se non sono presenti messaggi INVITE, il campo viene popolato con data e ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="5c3b9-p121">The time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c3b9-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="5c3b9-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5c3b9-231">datetime</span><span class="sxs-lookup"><span data-stu-id="5c3b9-231">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5c3b9-232">Ora della prima risposta SIP.</span><span class="sxs-lookup"><span data-stu-id="5c3b9-232">Time of the first SIP RESPONSE.</span></span> <span data-ttu-id="5c3b9-233">Questo campo viene in genere popolato con i dati generati dal messaggio INVITE iniziale nella sessione.</span><span class="sxs-lookup"><span data-stu-id="5c3b9-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="5c3b9-234">Se non sono presenti messaggi INVITE, il campo viene popolato con data e ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="5c3b9-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c3b9-235"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="5c3b9-235"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5c3b9-236">datetime</span><span class="sxs-lookup"><span data-stu-id="5c3b9-236">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5c3b9-237">Ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="5c3b9-237">The time when the session is ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c3b9-238"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="5c3b9-238"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="5c3b9-239">tinyint</span><span class="sxs-lookup"><span data-stu-id="5c3b9-239">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5c3b9-240">Stranieri</span><span class="sxs-lookup"><span data-stu-id="5c3b9-240">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5c3b9-241">Contiene il valore del tipo di URI MCU dalla <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5c3b9-241">Contains the MCU URI type value from the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a>.</span></span> <span data-ttu-id="5c3b9-242">Questo campo è usato per migliorare le prestazioni di query.</span><span class="sxs-lookup"><span data-stu-id="5c3b9-242">This field is used for improving query performance.</span></span></p>
<p><span data-ttu-id="5c3b9-243">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5c3b9-243">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c3b9-244"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="5c3b9-244"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="5c3b9-245">smallint</span><span class="sxs-lookup"><span data-stu-id="5c3b9-245">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5c3b9-p124">Set di bit che indica gli attributi dell'utente. Sono incluse le definizioni di attributo seguenti:</span><span class="sxs-lookup"><span data-stu-id="5c3b9-p124">A bit set that indicates the user attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="5c3b9-248">Integrato con telefono da tavolo  - 1</span><span class="sxs-lookup"><span data-stu-id="5c3b9-248">Integrated with desktop phone - 1</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c3b9-249"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="5c3b9-249"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="5c3b9-250">smallint</span><span class="sxs-lookup"><span data-stu-id="5c3b9-250">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5c3b9-p125">Set di bit che indica gli attributi della chiamata. Sono incluse le definizioni di attributo seguenti:</span><span class="sxs-lookup"><span data-stu-id="5c3b9-p125">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="5c3b9-253">Sessione ripetuta  - 1</span><span class="sxs-lookup"><span data-stu-id="5c3b9-253">Retried Session - 1</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5c3b9-254">\* Per la maggior parte delle sessioni, SessionIdSeq avrà il valore 1.</span><span class="sxs-lookup"><span data-stu-id="5c3b9-254">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="5c3b9-255">Se più sessioni iniziano esattamente alla stessa ora, il valore SessionIdSeq per una sarà 1, per l'altra sarà 2 e così via.</span><span class="sxs-lookup"><span data-stu-id="5c3b9-255">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


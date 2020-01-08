---
title: 'Lync Server 2013: Tabella ConferenceSessionDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceSessionDetails table
ms:assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412741(v=OCS.15)
ms:contentKeyID: 48184925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c5aaa3ec022be18ad54cc8a24b8410c23faf799
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985599"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="a279d-102">Tabella ConferenceSessionDetails in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a279d-102">ConferenceSessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a279d-103">_**Argomento Ultima modifica:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="a279d-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="a279d-104">Ogni record rappresenta una sessione di conferenza, che può essere la sessione con lo stato attiva o la sessione con uno specifico server di conferenza.</span><span class="sxs-lookup"><span data-stu-id="a279d-104">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a279d-105">Colonna</span><span class="sxs-lookup"><span data-stu-id="a279d-105">Column</span></span></th>
<th><span data-ttu-id="a279d-106">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="a279d-106">Data Type</span></span></th>
<th><span data-ttu-id="a279d-107">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="a279d-107">Key/Index</span></span></th>
<th><span data-ttu-id="a279d-108">Dettagli</span><span class="sxs-lookup"><span data-stu-id="a279d-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a279d-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="a279d-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a279d-110">DateTime</span><span class="sxs-lookup"><span data-stu-id="a279d-110">Datetime</span></span></p></td>
<td><p><span data-ttu-id="a279d-111">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="a279d-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="a279d-112">Ora della richiesta di sessione; usato in combinazione con <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione di conferenza.</span><span class="sxs-lookup"><span data-stu-id="a279d-112">Time of session request; used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="a279d-113">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a279d-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a279d-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a279d-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a279d-115">int</span><span class="sxs-lookup"><span data-stu-id="a279d-115">int</span></span></p></td>
<td><p><span data-ttu-id="a279d-116">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="a279d-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="a279d-117">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="a279d-117">ID number to identify the session.</span></span> <span data-ttu-id="a279d-118">Usato in combinazione con <strong>SessionIdTime</strong> per identificare in modo univoco una sessione di conferenza.</span><span class="sxs-lookup"><span data-stu-id="a279d-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="a279d-119">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a279d-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a279d-120"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="a279d-120"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="a279d-121">int</span><span class="sxs-lookup"><span data-stu-id="a279d-121">int</span></span></p></td>
<td><p><span data-ttu-id="a279d-122">Esterna</span><span class="sxs-lookup"><span data-stu-id="a279d-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a279d-123">URI della conferenza dello stato di attivazione relativo a questa sessione.</span><span class="sxs-lookup"><span data-stu-id="a279d-123">Focus conference URI related to this session.</span></span> <span data-ttu-id="a279d-124">Per altre informazioni, vedere la <a href="lync-server-2013-conferenceuris-table.md">tabella ConferenceUris in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a279d-124">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="a279d-125">Questo URI è un URI di conferenza basato sullo stato.</span><span class="sxs-lookup"><span data-stu-id="a279d-125">This URI is a Focus-based conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a279d-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="a279d-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="a279d-127">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="a279d-127">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a279d-128">Identificatore che distingue tra le istanze delle conferenze periodiche.</span><span class="sxs-lookup"><span data-stu-id="a279d-128">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="a279d-129">Ogni istanza di conferenza ricorrente ha lo stesso ConferenceURI, ma un valore ConfInstance diverso.</span><span class="sxs-lookup"><span data-stu-id="a279d-129">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p>
<p><span data-ttu-id="a279d-130">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a279d-130">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a279d-131"><strong>McuConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="a279d-131"><strong>McuConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="a279d-132">int</span><span class="sxs-lookup"><span data-stu-id="a279d-132">int</span></span></p></td>
<td><p><span data-ttu-id="a279d-133">Esterna</span><span class="sxs-lookup"><span data-stu-id="a279d-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a279d-134">URI conferenza del server delle conferenze correlato a questa sessione.</span><span class="sxs-lookup"><span data-stu-id="a279d-134">Conferencing server conference URI related to this session.</span></span> <span data-ttu-id="a279d-135">Per altre informazioni, vedere la <a href="lync-server-2013-conferenceuris-table.md">tabella ConferenceUris in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a279d-135">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="a279d-136">Questo URI è l'URI per conferenze basato su server di conferenza.</span><span class="sxs-lookup"><span data-stu-id="a279d-136">This URI is the conferencing server-based conference URI.</span></span> <span data-ttu-id="a279d-137">Per le sessioni di conferenza dello stato di attivazione, questa colonna sarà null.</span><span class="sxs-lookup"><span data-stu-id="a279d-137">For Focus conference sessions, this column will be null.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a279d-138"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="a279d-138"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="a279d-139">int</span><span class="sxs-lookup"><span data-stu-id="a279d-139">int</span></span></p></td>
<td><p><span data-ttu-id="a279d-140">Esterna</span><span class="sxs-lookup"><span data-stu-id="a279d-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a279d-141">ID di un utente nella sessione di conferenza.</span><span class="sxs-lookup"><span data-stu-id="a279d-141">ID of one user in the conference session.</span></span> <span data-ttu-id="a279d-142">Per altre informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella utenti in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a279d-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a279d-143"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="a279d-143"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="a279d-144">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="a279d-144">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a279d-145">GUID per identificare l'istanza di endpoint.</span><span class="sxs-lookup"><span data-stu-id="a279d-145">A GUID to identify the instance of endpoint.</span></span> <span data-ttu-id="a279d-146">Ad esempio, se un utente accede a computer diversi con lo stesso account, ogni computer avrà un ID endpoint diverso.</span><span class="sxs-lookup"><span data-stu-id="a279d-146">For example, if one user logs on to different machines with the same account, then each machine will have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a279d-147"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="a279d-147"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="a279d-148">int</span><span class="sxs-lookup"><span data-stu-id="a279d-148">int</span></span></p></td>
<td><p><span data-ttu-id="a279d-149">Esterna</span><span class="sxs-lookup"><span data-stu-id="a279d-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a279d-150">Indica l'ID dell'utente di chi è il chiamante per conto.</span><span class="sxs-lookup"><span data-stu-id="a279d-150">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="a279d-151">Per altre informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella utenti in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a279d-151">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a279d-152"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="a279d-152"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="a279d-153">int</span><span class="sxs-lookup"><span data-stu-id="a279d-153">int</span></span></p></td>
<td><p><span data-ttu-id="a279d-154">Esterna</span><span class="sxs-lookup"><span data-stu-id="a279d-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a279d-155">ID dell'utente con cui si fa riferimento alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="a279d-155">ID of the user by who the call is referred.</span></span> <span data-ttu-id="a279d-156">Per altre informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella utenti in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a279d-156">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a279d-157"><strong>UserClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="a279d-157"><strong>UserClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="a279d-158">int</span><span class="sxs-lookup"><span data-stu-id="a279d-158">int</span></span></p></td>
<td><p><span data-ttu-id="a279d-159">Esterna</span><span class="sxs-lookup"><span data-stu-id="a279d-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a279d-160">Versione client usata dall'utente della conferenza.</span><span class="sxs-lookup"><span data-stu-id="a279d-160">Client version used by the conference user.</span></span> <span data-ttu-id="a279d-161">Per altre informazioni, vedere la <a href="lync-server-2013-clientversions-table.md">Tabella ClientVersions in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a279d-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a279d-162"><strong>ConfClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="a279d-162"><strong>ConfClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="a279d-163">int</span><span class="sxs-lookup"><span data-stu-id="a279d-163">int</span></span></p></td>
<td><p><span data-ttu-id="a279d-164">Esterna</span><span class="sxs-lookup"><span data-stu-id="a279d-164">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a279d-165">Versione client usata dal server conferenza.</span><span class="sxs-lookup"><span data-stu-id="a279d-165">Client version used by the conference server.</span></span> <span data-ttu-id="a279d-166">Per altre informazioni, vedere la <a href="lync-server-2013-clientversions-table.md">Tabella ClientVersions in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a279d-166">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a279d-167"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="a279d-167"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a279d-168">DateTime</span><span class="sxs-lookup"><span data-stu-id="a279d-168">datetime</span></span></p></td>
<td><p><span data-ttu-id="a279d-169">Esterna</span><span class="sxs-lookup"><span data-stu-id="a279d-169">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a279d-170">Numero ID per identificare la finestra di dialogo che è stata sostituita dalla sessione corrente.</span><span class="sxs-lookup"><span data-stu-id="a279d-170">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="a279d-171">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a279d-171">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a279d-172"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a279d-172"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a279d-173">int</span><span class="sxs-lookup"><span data-stu-id="a279d-173">int</span></span></p></td>
<td><p><span data-ttu-id="a279d-174">Esterna</span><span class="sxs-lookup"><span data-stu-id="a279d-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a279d-175">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="a279d-175">ID number to identify the session.</span></span> <span data-ttu-id="a279d-176">Usato in combinazione con <strong>ReplacesDialogIdTime</strong> per identificare in modo univoco una sessione sostituita da questa sessione.</span><span class="sxs-lookup"><span data-stu-id="a279d-176">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="a279d-177">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a279d-177">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a279d-178"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="a279d-178"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="a279d-179">po'</span><span class="sxs-lookup"><span data-stu-id="a279d-179">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a279d-180">Indica se la sessione è stata avviata dal server dei servizi di conferenza.</span><span class="sxs-lookup"><span data-stu-id="a279d-180">Indicates if the session started by the conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a279d-181"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="a279d-181"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="a279d-182">po'</span><span class="sxs-lookup"><span data-stu-id="a279d-182">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a279d-183">Indica se la sessione è terminata dal server dei servizi di conferenza.</span><span class="sxs-lookup"><span data-stu-id="a279d-183">Indicates if the session ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a279d-184"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="a279d-184"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="a279d-185">po'</span><span class="sxs-lookup"><span data-stu-id="a279d-185">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a279d-186">Se l'utente ha effettuato l'accesso da Internal o not.</span><span class="sxs-lookup"><span data-stu-id="a279d-186">Whether user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a279d-187"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="a279d-187"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="a279d-188">int</span><span class="sxs-lookup"><span data-stu-id="a279d-188">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a279d-189">Codice di risposta SIP (Session Initiation Protocol) all'invito alla sessione.</span><span class="sxs-lookup"><span data-stu-id="a279d-189">Session Initiation Protocol (SIP) response code to the session invitation.</span></span> <span data-ttu-id="a279d-190">Questo campo viene in genere popolato da dati generati dal messaggio di invito iniziale nella sessione.</span><span class="sxs-lookup"><span data-stu-id="a279d-190">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="a279d-191">Se non è presente alcun messaggio di invito, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="a279d-191">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a279d-192"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="a279d-192"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="a279d-193">int</span><span class="sxs-lookup"><span data-stu-id="a279d-193">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a279d-194">ID di diagnostica acquisito dall'intestazione SIP.</span><span class="sxs-lookup"><span data-stu-id="a279d-194">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a279d-195"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="a279d-195"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="a279d-196">int</span><span class="sxs-lookup"><span data-stu-id="a279d-196">int</span></span></p></td>
<td><p><span data-ttu-id="a279d-197">Esterna</span><span class="sxs-lookup"><span data-stu-id="a279d-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a279d-198">ID del server front-end usato per questa sessione.</span><span class="sxs-lookup"><span data-stu-id="a279d-198">ID of the front-end server used for this session.</span></span> <span data-ttu-id="a279d-199">Per altre informazioni, vedere la <a href="lync-server-2013-servers-table.md">tabella server in Lync server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a279d-199">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a279d-200"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="a279d-200"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="a279d-201">int</span><span class="sxs-lookup"><span data-stu-id="a279d-201">int</span></span></p></td>
<td><p><span data-ttu-id="a279d-202">Esterna</span><span class="sxs-lookup"><span data-stu-id="a279d-202">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a279d-203">ID del pool in cui è stata acquisita la sessione.</span><span class="sxs-lookup"><span data-stu-id="a279d-203">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="a279d-204">Per altre informazioni, vedere la <a href="lync-server-2013-pools-table.md">Tabella Pools in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a279d-204">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a279d-205"><strong>MediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="a279d-205"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="a279d-206">int</span><span class="sxs-lookup"><span data-stu-id="a279d-206">int</span></span></p></td>
<td><p><span data-ttu-id="a279d-207">Esterna</span><span class="sxs-lookup"><span data-stu-id="a279d-207">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a279d-208">Server di mediazione che la chiamata sta usando.</span><span class="sxs-lookup"><span data-stu-id="a279d-208">The Mediation Server the call is using.</span></span> <span data-ttu-id="a279d-209">Per altre informazioni, vedere la <a href="lync-server-2013-mediationservers-table.md">Tabella MediationServers in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a279d-209">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a279d-210"><strong>GatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="a279d-210"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="a279d-211">int</span><span class="sxs-lookup"><span data-stu-id="a279d-211">int</span></span></p></td>
<td><p><span data-ttu-id="a279d-212">Esterna</span><span class="sxs-lookup"><span data-stu-id="a279d-212">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a279d-213">Il gateway che la chiamata sta usando.</span><span class="sxs-lookup"><span data-stu-id="a279d-213">The gateway the call is using.</span></span> <span data-ttu-id="a279d-214">Per altre informazioni, vedere la <a href="lync-server-2013-gateways-table.md">tabella gateway in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a279d-214">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a279d-215"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="a279d-215"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="a279d-216">int</span><span class="sxs-lookup"><span data-stu-id="a279d-216">int</span></span></p></td>
<td><p><span data-ttu-id="a279d-217">Esterna</span><span class="sxs-lookup"><span data-stu-id="a279d-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a279d-218">Server perimetrale usato dalla chiamata.</span><span class="sxs-lookup"><span data-stu-id="a279d-218">The Edge Server the call is using.</span></span> <span data-ttu-id="a279d-219">Per altre informazioni, vedere la <a href="lync-server-2013-edgeservers-table.md">tabella EdgeServers in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a279d-219">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a279d-220"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="a279d-220"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="a279d-221">int</span><span class="sxs-lookup"><span data-stu-id="a279d-221">int</span></span></p></td>
<td><p><span data-ttu-id="a279d-222">Esterna</span><span class="sxs-lookup"><span data-stu-id="a279d-222">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a279d-223">Tipo di contenuto usato nella sessione.</span><span class="sxs-lookup"><span data-stu-id="a279d-223">Content type used in the session.</span></span> <span data-ttu-id="a279d-224">Per altre informazioni, vedere la <a href="lync-server-2013-contenttypes-table.md">tabella ContentTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a279d-224">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a279d-225"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="a279d-225"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a279d-226">DateTime</span><span class="sxs-lookup"><span data-stu-id="a279d-226">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a279d-227">L'ora della prima richiesta di invito.</span><span class="sxs-lookup"><span data-stu-id="a279d-227">The time of the first INVITE request.</span></span> <span data-ttu-id="a279d-228">Questo campo viene in genere popolato da dati generati dal messaggio di invito iniziale nella sessione.</span><span class="sxs-lookup"><span data-stu-id="a279d-228">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="a279d-229">Se non è presente alcun messaggio di invito, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="a279d-229">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a279d-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="a279d-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a279d-231">DateTime</span><span class="sxs-lookup"><span data-stu-id="a279d-231">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a279d-232">Ora della prima risposta SIP.</span><span class="sxs-lookup"><span data-stu-id="a279d-232">Time of the first SIP RESPONSE.</span></span> <span data-ttu-id="a279d-233">Questo campo viene in genere popolato da dati generati dal messaggio di invito iniziale nella sessione.</span><span class="sxs-lookup"><span data-stu-id="a279d-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="a279d-234">Se non è presente alcun messaggio di invito, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="a279d-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a279d-235"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="a279d-235"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a279d-236">DateTime</span><span class="sxs-lookup"><span data-stu-id="a279d-236">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a279d-237">Ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="a279d-237">The time when the session is ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a279d-238"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="a279d-238"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="a279d-239">tinyint</span><span class="sxs-lookup"><span data-stu-id="a279d-239">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a279d-240">Esterna</span><span class="sxs-lookup"><span data-stu-id="a279d-240">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a279d-241">Contiene il valore di tipo URI MCU della <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a279d-241">Contains the MCU URI type value from the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a>.</span></span> <span data-ttu-id="a279d-242">Questo campo viene usato per migliorare le prestazioni delle query.</span><span class="sxs-lookup"><span data-stu-id="a279d-242">This field is used for improving query performance.</span></span></p>
<p><span data-ttu-id="a279d-243">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a279d-243">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a279d-244"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="a279d-244"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="a279d-245">smallint</span><span class="sxs-lookup"><span data-stu-id="a279d-245">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a279d-246">Set di bit che indica gli attributi utente.</span><span class="sxs-lookup"><span data-stu-id="a279d-246">A bit set that indicates the user attributes.</span></span> <span data-ttu-id="a279d-247">Sono elencate le definizioni di attributo seguenti:</span><span class="sxs-lookup"><span data-stu-id="a279d-247">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="a279d-248">Integrazione con il telefono da tavolo-1</span><span class="sxs-lookup"><span data-stu-id="a279d-248">Integrated with desktop phone - 1</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a279d-249"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="a279d-249"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="a279d-250">smallint</span><span class="sxs-lookup"><span data-stu-id="a279d-250">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a279d-251">Set di bit che indica gli attributi di chiamata.</span><span class="sxs-lookup"><span data-stu-id="a279d-251">A bit set that indicates the call attributes.</span></span> <span data-ttu-id="a279d-252">Sono elencate le definizioni di attributo seguenti:</span><span class="sxs-lookup"><span data-stu-id="a279d-252">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="a279d-253">Riprova sessione-1</span><span class="sxs-lookup"><span data-stu-id="a279d-253">Retried Session - 1</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a279d-254">\*Per la maggior parte delle sessioni, SessionIdSeq avrà il valore 1.</span><span class="sxs-lookup"><span data-stu-id="a279d-254">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="a279d-255">Se più sessioni iniziano esattamente nello stesso momento, il SessionIdSeq per uno sarà 1, per un altro sarà 2 e così via.</span><span class="sxs-lookup"><span data-stu-id="a279d-255">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


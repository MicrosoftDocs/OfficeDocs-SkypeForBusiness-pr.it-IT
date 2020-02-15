---
title: 'Lync Server 2013: interoperabilità client in Lync 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client interoperability in Lync 2013
ms:assetid: 0f126571-91a2-45d5-855c-1e4ddb45fc04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204672(v=OCS.15)
ms:contentKeyID: 48183417
ms.date: 03/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc807d65c76a1307ccd8532e644f9f9d23ffc69e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046739"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-interoperability-in-lync-2013"></a><span data-ttu-id="ed4bf-102">Interoperabilità client in Lync 2013</span><span class="sxs-lookup"><span data-stu-id="ed4bf-102">Client interoperability in Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed4bf-103">_**Ultimo argomento modificato:** 2016-03-04_</span><span class="sxs-lookup"><span data-stu-id="ed4bf-103">_**Topic Last Modified:** 2016-03-04_</span></span>

<span data-ttu-id="ed4bf-104">In questo argomento viene illustrata la possibilità per i client Microsoft Lync Server 2013 di coesistere e interagire con client provenienti da versioni precedenti di Lync Server e Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-104">This topic discusses the ability of Microsoft Lync Server 2013 clients to coexist and interact with clients from earlier versions of Lync Server and Office Communications Server.</span></span>

<div>

## <a name="server-and-client-compatibility"></a><span data-ttu-id="ed4bf-105">Compatibilità di server e client</span><span class="sxs-lookup"><span data-stu-id="ed4bf-105">Server and Client Compatibility</span></span>

<span data-ttu-id="ed4bf-106">Nella tabella seguente sono mostrate le combinazioni supportate di versioni client e server.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-106">The following table shows the supported combinations of client versions and server versions.</span></span> <span data-ttu-id="ed4bf-107">Viene indicato se è supportato l'accesso quando il client tenta di connettersi al server indicato.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-107">This table indicates whether sign-in is supported when the client attempts to connect to the server indicated.</span></span> <span data-ttu-id="ed4bf-108">Lync Server 2013 supporta la versione client precedente.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-108">Lync Server 2013 supports the previous client version.</span></span> <span data-ttu-id="ed4bf-109">Inoltre, a differenza delle versioni precedenti, Lync Server 2010 supporta i nuovi client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-109">Also, unlike previous releases, Lync Server 2010 supports the new Lync 2013 clients.</span></span> <span data-ttu-id="ed4bf-110">In questo modo, le organizzazioni che eseguono l'aggiornamento da Lync Server 2010 possono implementare nuovi client indipendenti dagli aggiornamenti di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-110">This allows organizations who are upgrading from Lync Server 2010 to roll out new clients independent of Lync Server upgrades.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ed4bf-111">Client</span><span class="sxs-lookup"><span data-stu-id="ed4bf-111">Client</span></span></th>
<th><span data-ttu-id="ed4bf-112">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed4bf-112">Lync Server 2013</span></span></th>
<th><span data-ttu-id="ed4bf-113">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="ed4bf-113">Lync Server 2010</span></span></th>
<th><span data-ttu-id="ed4bf-114">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="ed4bf-114">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed4bf-115">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="ed4bf-115">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-116">Supportato</span><span class="sxs-lookup"><span data-stu-id="ed4bf-116">Supported</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-117">Supported5</span><span class="sxs-lookup"><span data-stu-id="ed4bf-117">Supported5</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-118">Non supportata</span><span class="sxs-lookup"><span data-stu-id="ed4bf-118">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed4bf-119">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="ed4bf-119">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-120">Supportato</span><span class="sxs-lookup"><span data-stu-id="ed4bf-120">Supported</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-121">Supportato</span><span class="sxs-lookup"><span data-stu-id="ed4bf-121">Supported</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-122">Non supportata</span><span class="sxs-lookup"><span data-stu-id="ed4bf-122">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed4bf-123">Lync Web App 2013</span><span class="sxs-lookup"><span data-stu-id="ed4bf-123">Lync Web App 2013</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-124">Supportato</span><span class="sxs-lookup"><span data-stu-id="ed4bf-124">Supported</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-125">Non supportata</span><span class="sxs-lookup"><span data-stu-id="ed4bf-125">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-126">Non supportato</span><span class="sxs-lookup"><span data-stu-id="ed4bf-126">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed4bf-127">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="ed4bf-127">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-128">Supportato</span><span class="sxs-lookup"><span data-stu-id="ed4bf-128">Supported</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-129">Supportato</span><span class="sxs-lookup"><span data-stu-id="ed4bf-129">Supported</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-130">Non supportata</span><span class="sxs-lookup"><span data-stu-id="ed4bf-130">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed4bf-131">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="ed4bf-131">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-132">Supportato</span><span class="sxs-lookup"><span data-stu-id="ed4bf-132">Supported</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-133">Supportato</span><span class="sxs-lookup"><span data-stu-id="ed4bf-133">Supported</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-134">Non supportata</span><span class="sxs-lookup"><span data-stu-id="ed4bf-134">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed4bf-135">Chat di gruppo Lync 2010</span><span class="sxs-lookup"><span data-stu-id="ed4bf-135">Lync 2010 Group Chat</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-136">Supported1</span><span class="sxs-lookup"><span data-stu-id="ed4bf-136">Supported1</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-137">Supported2</span><span class="sxs-lookup"><span data-stu-id="ed4bf-137">Supported2</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-138">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="ed4bf-138">Not Applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed4bf-139">Lync Web App 2010</span><span class="sxs-lookup"><span data-stu-id="ed4bf-139">Lync Web App 2010</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-140">Non supportato</span><span class="sxs-lookup"><span data-stu-id="ed4bf-140">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-141">Supportato</span><span class="sxs-lookup"><span data-stu-id="ed4bf-141">Supported</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-142">Non supportata</span><span class="sxs-lookup"><span data-stu-id="ed4bf-142">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed4bf-143">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="ed4bf-143">Lync 2010 Attendee</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-144">Non Supported3</span><span class="sxs-lookup"><span data-stu-id="ed4bf-144">Not Supported3</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-145">Supportato</span><span class="sxs-lookup"><span data-stu-id="ed4bf-145">Supported</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-146">Non supportata</span><span class="sxs-lookup"><span data-stu-id="ed4bf-146">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed4bf-147">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="ed4bf-147">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-148">Interoperable4</span><span class="sxs-lookup"><span data-stu-id="ed4bf-148">Interoperable4</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-149">Supportato</span><span class="sxs-lookup"><span data-stu-id="ed4bf-149">Supported</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-150">Supportato</span><span class="sxs-lookup"><span data-stu-id="ed4bf-150">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed4bf-151">Microsoft Office Communications Server 2007 R2 Attendant</span><span class="sxs-lookup"><span data-stu-id="ed4bf-151">Microsoft Office Communications Server 2007 R2 Attendant</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-152">Non supportato</span><span class="sxs-lookup"><span data-stu-id="ed4bf-152">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-153">Supportato</span><span class="sxs-lookup"><span data-stu-id="ed4bf-153">Supported</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-154">Supportato</span><span class="sxs-lookup"><span data-stu-id="ed4bf-154">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed4bf-155">Office Communicator 2007</span><span class="sxs-lookup"><span data-stu-id="ed4bf-155">Office Communicator 2007</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-156">Non supportato</span><span class="sxs-lookup"><span data-stu-id="ed4bf-156">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-157">Supportato</span><span class="sxs-lookup"><span data-stu-id="ed4bf-157">Supported</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-158">Supportato</span><span class="sxs-lookup"><span data-stu-id="ed4bf-158">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed4bf-159">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="ed4bf-159">Office Live Meeting 2007</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-160">Non supportato</span><span class="sxs-lookup"><span data-stu-id="ed4bf-160">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-161">Supportato</span><span class="sxs-lookup"><span data-stu-id="ed4bf-161">Supported</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-162">Supportato</span><span class="sxs-lookup"><span data-stu-id="ed4bf-162">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed4bf-163">App Lync Windows Store</span><span class="sxs-lookup"><span data-stu-id="ed4bf-163">Lync Windows Store app</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-164">Supportato</span><span class="sxs-lookup"><span data-stu-id="ed4bf-164">Supported</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-165">Supportato</span><span class="sxs-lookup"><span data-stu-id="ed4bf-165">Supported</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-166">Non supportata</span><span class="sxs-lookup"><span data-stu-id="ed4bf-166">Not Supported</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ed4bf-167">per informazioni dettagliate su 1per, vedere [Migration from Lync server 2010, Group Chat o Office Communications Server 2007 R2 Group Chat to Lync server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="ed4bf-167">1For details, see [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="ed4bf-168">2In Microsoft Lync Server 2010, la funzionalità Group Chat era disponibile con Group Chat Server, un'applicazione attendibile di terze parti per Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-168">2In Microsoft Lync Server 2010, group chat functionality was available with Group Chat Server, a third-party trusted application for Lync Server 2010.</span></span> <span data-ttu-id="ed4bf-169">I client Lync 2013 non sono compatibili con Lync Server 2010, Group Chat.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-169">Lync 2013 clients are not compatible with Lync Server 2010, Group Chat.</span></span>

<span data-ttu-id="ed4bf-170">3Lync Web App 2013 ora offre un'esperienza di riunione completa, tra cui audio e video del computer, ed è considerata la sostituzione di Lync 2010 Attendee.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-170">3Lync Web App 2013 now provides a full in-meeting experience, including computer audio and video, and is considered the replacement for Lync 2010 Attendee.</span></span> <span data-ttu-id="ed4bf-171">Lync 2010 Attendee si connetterà a Lync Server 2013 solo quando si utilizza un browser non supportato (Internet Explorer 6 o Internet Explorer 7) e Windows XP.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-171">Lync 2010 Attendee will connect to Lync Server 2013 only when you are using an unsupported browser (Internet Explorer 6 or Internet Explorer 7) and Windows XP.</span></span>

<span data-ttu-id="ed4bf-172">le funzionalità di presenza e messaggistica istantanea di 4Il in Office Communicator 2007 R2 sono compatibili con Lync Server 2013, ma non le funzionalità di conferenza.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-172">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="ed4bf-173">Durante la migrazione da Office Communications Server 2007 R2, Office Communicator 2007 R2 è idoneo per l'interoperabilità della messaggistica istantanea e della presenza, ma gli utenti devono utilizzare Lync Web App 2013 per partecipare alle riunioni di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-173">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

<span data-ttu-id="ed4bf-174">5 per le limitazioni, vedere "supporto delle funzionalità di conferenza per i client di Lync 2013 nelle riunioni di Lync Server 2010" più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-174">5 For limitations, see "Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings" later in this topic.</span></span>

</div>

<div>

## <a name="interoperability-among-clients"></a><span data-ttu-id="ed4bf-175">Interoperabilità tra client</span><span class="sxs-lookup"><span data-stu-id="ed4bf-175">Interoperability among Clients</span></span>

<span data-ttu-id="ed4bf-176">Con la versione Lync Server 2013, diverse versioni client possono interagire senza problemi in entrambi gli scenari peer-to-peer e di conferenza.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-176">With the Lync Server 2013 release, various client versions can interact seamlessly in both peer-to-peer and conferencing scenarios.</span></span> <span data-ttu-id="ed4bf-177">In questa sezione vengono illustrate le funzionalità disponibili quando gli utenti interagiscono con altri utenti che utilizzano versioni diverse dei client e server.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-177">This section discusses feature availability when users interact with other users who are using different versions of clients and servers.</span></span>

<div>

## <a name="peer-to-peer-feature-support"></a><span data-ttu-id="ed4bf-178">Supporto della funzionalità peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="ed4bf-178">Peer-to-Peer Feature Support</span></span>

<span data-ttu-id="ed4bf-p106">Le funzionalità peer-to-peer sono supportate per gli utenti ospitati su diverse versioni del server e che utilizzano diverse versioni client. L'esperienza dell'utente finale e le caratteristiche disponibili sono in linea con le funzionalità del client dell'utente e con la versione del server a cui l'utente ha eseguito l'accesso. In altri termini:</span><span class="sxs-lookup"><span data-stu-id="ed4bf-p106">Peer-to-peer features are supported for users who are homed on different versions of the server and who are using different client versions. The end-user experience and available features are consistent with the capabilities of the user’s client and the version of the server the user is signed in to. In other words:</span></span>

  - <span data-ttu-id="ed4bf-182">Se un utente ha eseguito l'accesso a Lync Server 2013 con un client precedente, l'utente avrà la stessa esperienza a cui viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-182">If a user is signed in to Lync Server 2013 with an older client, the user will have the same experience he or she is used to.</span></span> <span data-ttu-id="ed4bf-183">Nessuna delle nuove funzionalità introdotte in Lync Server 2013 sarà disponibile finché il client dell'utente non viene aggiornato.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-183">None of the new features introduced in Lync Server 2013 will be available until the user’s client is upgraded.</span></span> <span data-ttu-id="ed4bf-184">Gli esempi includono la visualizzazione raccolta video, video HD, la condivisione di PowerPoint aggiornata e l'opzione per disattivare l'audio e il video di tutti i partecipanti dopo la voce di riunione.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-184">Examples include video gallery view, HD video, updated PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="ed4bf-185">Le nuove funzionalità sono descritte in [nuove funzionalità di conferenza in Lync server 2013](lync-server-2013-new-conferencing-features.md) e [novità per i client in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="ed4bf-185">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

  - <span data-ttu-id="ed4bf-186">Se un utente ha eseguito l'accesso a Lync Server 2010 con un client Lync 2013, tutte le nuove funzionalità non supportate da Lync Server 2010 non saranno disponibili fino a quando l'utente non verrà spostato in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-186">If a user is signed in to Lync Server 2010 with a Lync 2013 client, any new features not supported by Lync Server 2010 will be unavailable until the user is moved to Lync Server 2013.</span></span>

<span data-ttu-id="ed4bf-187">Nella tabella seguente vengono confrontate le funzionalità disponibili nelle sessioni peer-to-peer in cui il client ha eseguito l'accesso a Lync Server 2013 o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-187">The following table compares feature availability in peer-to-peer sessions where the client is signed in to either Lync Server 2013 or Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ed4bf-188">Lync Web App e Lync 2010 Attendee sono client solo per riunioni e non sono inclusi in questa tabella.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-188">Lync Web App and Lync 2010 Attendee are meeting-only clients and aren’t included in this table.</span></span>



</div>


<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ed4bf-189">Client</span><span class="sxs-lookup"><span data-stu-id="ed4bf-189">Client</span></span></th>
<th><span data-ttu-id="ed4bf-190">Messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="ed4bf-190">Instant Messaging</span></span></th>
<th><span data-ttu-id="ed4bf-191">Presenza</span><span class="sxs-lookup"><span data-stu-id="ed4bf-191">Presence</span></span></th>
<th><span data-ttu-id="ed4bf-192">Voce</span><span class="sxs-lookup"><span data-stu-id="ed4bf-192">Voice</span></span></th>
<th><span data-ttu-id="ed4bf-193">Video</span><span class="sxs-lookup"><span data-stu-id="ed4bf-193">Video</span></span></th>
<th><span data-ttu-id="ed4bf-194">Condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="ed4bf-194">Application Sharing</span></span></th>
<th><span data-ttu-id="ed4bf-195">Trasferimento di file</span><span class="sxs-lookup"><span data-stu-id="ed4bf-195">File Transfer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed4bf-196">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="ed4bf-196">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-197">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-197">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-198">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-199">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-199">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-200">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-200">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-201">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-201">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-202">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-202">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed4bf-203">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="ed4bf-203">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-204">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-204">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-205">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-205">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-206">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-207">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-208">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-209">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-209">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed4bf-210">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="ed4bf-210">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-211">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-211">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-212">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-213">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-214">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-215">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-216">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-216">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed4bf-217">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="ed4bf-217">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-218">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-218">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-219">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-220">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-220">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed4bf-221">Lync 2010 Mobile</span><span class="sxs-lookup"><span data-stu-id="ed4bf-221">Lync 2010 Mobile</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-222">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-223">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-223">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed4bf-224">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="ed4bf-224">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-225">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-225">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-226">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-227">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-227">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed4bf-228">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="ed4bf-228">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-229">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-229">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-230">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-230">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-231">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-231">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-232">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-233">Yes1</span><span class="sxs-lookup"><span data-stu-id="ed4bf-233">Yes1</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-234">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-234">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed4bf-235">Messaggistica istantanea pubblica (AOL, Yahoo!)</span><span class="sxs-lookup"><span data-stu-id="ed4bf-235">Public IM (AOL, Yahoo!)</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-236">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-236">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-237">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-237">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed4bf-238">Messaggistica istantanea pubblica (MSN, Windows Live Messenger)</span><span class="sxs-lookup"><span data-stu-id="ed4bf-238">Public IM (MSN, Windows Live Messenger)</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-239">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-239">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-240">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-240">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-241">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-241">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-242">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-242">Yes</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="ed4bf-243">Al 1 ° settembre 2012, la licenza di sottoscrizione a Microsoft Lync Public IM Connectivity (PIC USL) non è più disponibile per l'acquisto dei contratti nuovi o rinnovati.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-243">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="ed4bf-244">I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="ed4bf-244">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="ed4bf-245">Messenger fino alla data di arresto del servizio.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-245">Messenger until the service shutdown date.</span></span> <span data-ttu-id="ed4bf-246">Una data di fine vita del 2014 giugno per AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="ed4bf-246">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="ed4bf-247">sono stati annunciati.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-247">has been announced.</span></span> <span data-ttu-id="ed4bf-248">Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>..</span><span class="sxs-lookup"><span data-stu-id="ed4bf-248">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>..</span></span></P>
> <LI>
> <P><span data-ttu-id="ed4bf-249">Il PIC USL è una licenza di sottoscrizione per utente, per mese, necessaria per la Federazione di Lync Server o Office Communications Server con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="ed4bf-249">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="ed4bf-250">Messaggero.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-250">Messenger.</span></span> <span data-ttu-id="ed4bf-251">La capacità di Microsoft di fornire questo servizio è stata subordinata al supporto da Yahoo!, ovvero il contratto sottostante per il quale non verrà rinnovato.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-251">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="ed4bf-252">Più che mai, Lync è uno strumento potente per la connessione tra le organizzazioni e gli utenti di tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-252">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="ed4bf-253">La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-253">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="ed4bf-254">La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone attraverso la messaggistica istantanea e la voce.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-254">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="ed4bf-255">1 in Office Communicator 2007 R2, è disponibile solo la condivisione del desktop (e non la condivisione dei programmi).</span><span class="sxs-lookup"><span data-stu-id="ed4bf-255">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ed4bf-256">La condivisione desktop tra Office Communicator 2007 R2 e Skype for business 2015 non può essere avviata dal client più recente quando viene applicata l'interfaccia utente del client Skype for business 2015.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-256">Desktop sharing between Office Communicator 2007 R2 and Skype for Business 2015 cannot be initiated from the newer client when the Skype for Business 2015 client user interface is enforced.</span></span>



</div>

</div>

<div>

## <a name="conferencing-feature-support-for-lync-2013-clients-in-lync-server-2010-meetings"></a><span data-ttu-id="ed4bf-257">Supporto delle funzionalità di conferenza per i client di Lync 2013 nelle riunioni di Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="ed4bf-257">Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings</span></span>

<span data-ttu-id="ed4bf-258">Quando gli utenti accedono alle riunioni di Lync Server 2010 con un client Lync 2013, possono accedere alle funzionalità client di Lync 2013 con le eccezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ed4bf-258">When users join Lync Server 2010 meetings with a Lync 2013 client, they have access to Lync 2013 client features with the following exceptions:</span></span>

  - <span data-ttu-id="ed4bf-259">Nelle opzioni di gestione dei **partecipanti** , che sono accessibili facendo riferimento all'icona persone nella finestra riunione, l'opzione **Nessuna riunione di messaggistica istantanea** non funziona.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-259">In the **Participants** management options, which are accessible by pointing to the people icon in the meeting window, the **No Meeting IM** option does not function.</span></span>

  - <span data-ttu-id="ed4bf-260">La visualizzazione raccolta non funziona nelle conferenze video.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-260">Gallery View does not function in video conferences.</span></span> <span data-ttu-id="ed4bf-261">L'utente visualizza solo l'altoparlante attivo invece di tutti gli altoparlanti.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-261">The user sees only the active speaker instead of all speakers.</span></span> <span data-ttu-id="ed4bf-262">Nell'elenco delle opzioni **Seleziona un layout** , la **visualizzazione raccolta** non è disponibile</span><span class="sxs-lookup"><span data-stu-id="ed4bf-262">In the list of **Pick a Layout** options, **Gallery View** is unavailable</span></span>

  - <span data-ttu-id="ed4bf-263">L'elenco dei partecipanti viene visualizzato per impostazione predefinita nelle conferenze video.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-263">The participant list displays by default in video conferences.</span></span>

  - <span data-ttu-id="ed4bf-264">Quando si fa clic con il pulsante destro del mouse su un utente nell'elenco partecipanti, le opzioni di gestione del **blocco video e del** **pin per la raccolta** non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-264">When right-clicking a user in the participants list, the **Lock the Video Spotlight** and **Pin to Gallery** participant management options are unavailable.</span></span>

</div>

<div>

## <a name="conferencing-feature-support-in-lync-server-2013-meetings"></a><span data-ttu-id="ed4bf-265">Supporto delle funzionalità di conferenza nelle riunioni di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed4bf-265">Conferencing Feature Support in Lync Server 2013 Meetings</span></span>

<span data-ttu-id="ed4bf-266">Lync Server 2013 fornisce nuove funzionalità di conferenza che diventano disponibili per gli utenti dopo lo spostamento degli account in Lync Server 2013 ed eseguono l'accesso con il client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-266">Lync Server 2013 provides new conferencing features that become available to users after their accounts are moved to Lync Server 2013 and they sign in with the Lync 2013 client.</span></span> <span data-ttu-id="ed4bf-267">Gli esempi includono la visualizzazione della raccolta video, il video HD, la condivisione di PowerPoint e l'opzione per disattivare l'audio e il video dei partecipanti dopo la voce di riunione.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-267">Examples include video gallery view, HD video, PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="ed4bf-268">Le nuove funzionalità sono descritte in [nuove funzionalità di conferenza in Lync server 2013](lync-server-2013-new-conferencing-features.md) e [novità per i client in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="ed4bf-268">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="ed4bf-269">Nelle riunioni di Lync Server 2013, alcune funzionalità di conferenza sono supportate per gli utenti che si trovano in diverse versioni del server e che utilizzano client e versioni client diversi.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-269">In Lync Server 2013 meetings, certain conferencing features are supported for users who are homed on different versions of the server and who are using different clients and client versions.</span></span> <span data-ttu-id="ed4bf-270">Quando i client partecipano a una riunione di Lync Server 2013, gli utenti possono accedere alle caratteristiche e alle funzionalità illustrate in questa tabella.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-270">When clients join a Lync Server 2013 meeting, users have access to the features and capabilities shown in this table.</span></span>


<table style="width:100%;">
<colgroup>
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ed4bf-271">Client</span><span class="sxs-lookup"><span data-stu-id="ed4bf-271">Client</span></span></th>
<th><span data-ttu-id="ed4bf-272">Messaggistica istantanea peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="ed4bf-272">Peer-to-peer IM</span></span></th>
<th><span data-ttu-id="ed4bf-273">Voce</span><span class="sxs-lookup"><span data-stu-id="ed4bf-273">Voice</span></span></th>
<th><span data-ttu-id="ed4bf-274">Video</span><span class="sxs-lookup"><span data-stu-id="ed4bf-274">Video</span></span></th>
<th><span data-ttu-id="ed4bf-275">Condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="ed4bf-275">Application Sharing</span></span></th>
<th><span data-ttu-id="ed4bf-276">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="ed4bf-276">PowerPoint</span></span></th>
<th><span data-ttu-id="ed4bf-277">Trasferimento di file</span><span class="sxs-lookup"><span data-stu-id="ed4bf-277">File Transfer</span></span></th>
<th><span data-ttu-id="ed4bf-278">Whiteboard</span><span class="sxs-lookup"><span data-stu-id="ed4bf-278">Whiteboard</span></span></th>
<th><span data-ttu-id="ed4bf-279">Polling</span><span class="sxs-lookup"><span data-stu-id="ed4bf-279">Polling</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed4bf-280">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="ed4bf-280">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-281">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-281">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-282">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-282">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-283">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-283">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-284">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-284">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-285">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-285">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-286">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-286">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-287">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-287">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-288">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-288">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed4bf-289">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="ed4bf-289">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-290">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-290">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-291">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-291">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-292">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-292">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-293">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-293">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-294">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-294">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-295">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-295">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-296">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-296">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-297">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-297">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed4bf-298">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="ed4bf-298">Lync Web App</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-299">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-299">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-300">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-300">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-301">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-301">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-302">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-302">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-303">Sì2</span><span class="sxs-lookup"><span data-stu-id="ed4bf-303">Yes2</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-304">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-304">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-305">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-305">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-306">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-306">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed4bf-307">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="ed4bf-307">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-308">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-308">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-309">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-309">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-310">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-310">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-311">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-311">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-312">Yes3</span><span class="sxs-lookup"><span data-stu-id="ed4bf-312">Yes3</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-313">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-313">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-314">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-314">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-315">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-315">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed4bf-316">Office Communicator 2007 R2 4</span><span class="sxs-lookup"><span data-stu-id="ed4bf-316">Office Communicator 2007 R2 4</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-317">Sì</span><span class="sxs-lookup"><span data-stu-id="ed4bf-317">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ed4bf-318">1 in Office Communicator 2007 R2, è disponibile solo la condivisione del desktop (e non la condivisione dei programmi).</span><span class="sxs-lookup"><span data-stu-id="ed4bf-318">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<span data-ttu-id="ed4bf-319">2 Lync Server 2013 utilizza un meccanismo aggiornato per il caricamento dei file di PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-319">2 Lync Server 2013 uses an updated mechanism for uploading PowerPoint files.</span></span> <span data-ttu-id="ed4bf-320">Gli utenti di Lync Web App che partecipano a una riunione originariamente pianificata su Lync Server 2010 possono visualizzare e esplorare le presentazioni di PowerPoint, ma non possono caricare i file di PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-320">Lync Web App users who join a meeting that was originally scheduled on Lync Server 2010 can view and navigate PowerPoint presentations, but cannot upload PowerPoint files.</span></span>

<span data-ttu-id="ed4bf-321">3 Se la riunione è stata pianificata su Lync Server 2013 e le diapositive di PowerPoint sono state caricate da un client Lync 2013, gli utenti di Lync 2010 dispongono dell'accesso in sola visualizzazione alle diapositive.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-321">3 If the meeting was scheduled on Lync Server 2013 and PowerPoint slides were uploaded by a Lync 2013 client, Lync 2010 users have view-only access to the slides.</span></span> <span data-ttu-id="ed4bf-322">Viceversa, se le diapositive di PowerPoint sono state caricate da un utente Lync 2010, gli utenti di Lync Server 2013 saranno in grado di visualizzare e diapositive e, se il server Office Web Apps è configurato, accedere a nuove funzionalità come la visualizzazione a risoluzione più elevata, le animazioni, le transizioni di diapositive e video incorporato.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-322">Conversely, if the PowerPoint slides were uploaded by a Lync 2010 user, Lync Server 2013 users will be able to view and slides and, if Office Web Apps Server is configured, access new capabilities such as higher resolution display, animations, slide transitions, and embedded video.</span></span> <span data-ttu-id="ed4bf-323">Per ulteriori informazioni, vedere [configurazione dell'integrazione con Office Web Apps Server e Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="ed4bf-323">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="ed4bf-324">le funzionalità di presenza e messaggistica istantanea di 4Il in Office Communicator 2007 R2 sono compatibili con Lync Server 2013, ma non le funzionalità di conferenza.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-324">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="ed4bf-325">Durante la migrazione da Office Communications Server 2007 R2, Office Communicator 2007 R2 è idoneo per l'interoperabilità della messaggistica istantanea e della presenza, ma gli utenti devono utilizzare Lync Web App 2013 per partecipare alle riunioni di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-325">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

</div>

</div>

<div>

## <a name="scheduling-add-in-support"></a><span data-ttu-id="ed4bf-326">Supporto dei componenti aggiuntivi di pianificazione</span><span class="sxs-lookup"><span data-stu-id="ed4bf-326">Scheduling Add-in Support</span></span>

<span data-ttu-id="ed4bf-327">Il supporto server per i vari componenti aggiuntivi di pianificazione è coerente con la compatibilità tra le versioni server e client.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-327">Server support for the various scheduling add-ins is consistent with server and client version compatibility.</span></span> <span data-ttu-id="ed4bf-328">In generale, i componenti aggiuntivi di pianificazione seguenti sono supportati in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-328">In general, the following scheduling add-ins are supported on Lync Server 2013.</span></span> <span data-ttu-id="ed4bf-329">Tuttavia, le versioni precedenti dei componenti aggiuntivi non forniscono nuove funzionalità del componente aggiuntivo Lync 2013, ad esempio l'opzione per disattivare l'audio e il video dei partecipanti dopo la voce di riunione.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-329">However, previous versions of add-ins do not provide new Lync 2013 add-in features, such as the option to mute all attendee audio and video upon meeting entry.</span></span>

  - <span data-ttu-id="ed4bf-330">**Il componente aggiuntivo per riunioni online per Lync 2013**   fornisce le stesse caratteristiche del componente aggiuntivo per riunioni online per Lync 2010, con l'aggiunta di controlli di silenziamento dei partecipanti, che consentono agli organizzatori di riunioni di pianificare le conferenze in cui l'audio e il video dei partecipanti sono disattivati per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-330">**Online Meeting Add-in for Lync 2013**   Provides the same features as the Online Meeting Add-in for Lync 2010, with the addition of attendee mute controls, which allow meeting organizers to schedule conferences that have attendee audio and video muted by default.</span></span> <span data-ttu-id="ed4bf-331">Gli amministratori possono anche personalizzare gli inviti alle riunioni dell'organizzazione aggiungendo un logo personalizzato, un URL di supporto, un URL di dichiarazione di non responsabilità legale o un testo del piè di pagina personalizzato.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-331">Administrators can also customize the organization’s meeting invitations by adding a custom logo, a support URL, a legal disclaimer URL, or custom footer text.</span></span>

  - <span data-ttu-id="ed4bf-332">**Il componente aggiuntivo per riunioni online per Lync 2010**   fornisce la pianificazione per le riunioni di Lync e rimuove la possibilità di pianificare le conferenze di Office Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-332">**Online Meeting Add-in for Lync 2010**   Provides scheduling for Lync meetings and removes the capability to schedule Office Live Meeting conferences.</span></span>

  - <span data-ttu-id="ed4bf-333">**Il componente aggiuntivo per conferenze di Office Communicator 2007 R2**   fornisce la pianificazione per le conferenze di Office Live Meeting e Office Communicator 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-333">**Office Communicator 2007 R2 Conferencing Add-in**   Provides scheduling for both Office Live Meeting conferences and Office Communicator 2007 R2 conferences.</span></span> 

<div>


> [!NOTE]  
> <span data-ttu-id="ed4bf-334">Le conferenze di Live Meeting non possono essere pianificate su Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-334">Live Meeting conferences cannot be scheduled on Lync Server 2013.</span></span>



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ed4bf-335">Client di pianificazione</span><span class="sxs-lookup"><span data-stu-id="ed4bf-335">Scheduling Client</span></span></th>
<th><span data-ttu-id="ed4bf-336">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed4bf-336">Lync Server 2013</span></span></th>
<th><span data-ttu-id="ed4bf-337">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="ed4bf-337">Lync Server 2010</span></span></th>
<th><span data-ttu-id="ed4bf-338">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="ed4bf-338">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed4bf-339">Componente aggiuntivo per riunioni online per Lync 2013 (può essere utilizzato con Office 2013, Outlook 2010 e Outlook 2007)</span><span class="sxs-lookup"><span data-stu-id="ed4bf-339">Online Meeting Add-in for Lync 2013 (can be used with Office 2013, Outlook 2010, and Outlook 2007)</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-340">Supportato</span><span class="sxs-lookup"><span data-stu-id="ed4bf-340">Supported</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-341">Supportato (nuove caratteristiche dei componenti aggiuntivi non disponibili)</span><span class="sxs-lookup"><span data-stu-id="ed4bf-341">Supported (new add-in features not available)</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-342">Non supportato</span><span class="sxs-lookup"><span data-stu-id="ed4bf-342">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed4bf-343">Utilità di pianificazione Web di Lync 2013</span><span class="sxs-lookup"><span data-stu-id="ed4bf-343">Lync 2013 Web Scheduler</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-344">Supportato</span><span class="sxs-lookup"><span data-stu-id="ed4bf-344">Supported</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-345">Non supportata</span><span class="sxs-lookup"><span data-stu-id="ed4bf-345">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-346">Non supportata</span><span class="sxs-lookup"><span data-stu-id="ed4bf-346">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed4bf-347">Online Meeting Add-in per Lync 2010</span><span class="sxs-lookup"><span data-stu-id="ed4bf-347">Online Meeting Add-in for Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-348">Supportato</span><span class="sxs-lookup"><span data-stu-id="ed4bf-348">Supported</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-349">Supportato</span><span class="sxs-lookup"><span data-stu-id="ed4bf-349">Supported</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-350">Non supportato</span><span class="sxs-lookup"><span data-stu-id="ed4bf-350">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed4bf-351">Componente aggiuntivo per conferenze per Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="ed4bf-351">Office Communicator 2007 R2 Conferencing Add-in</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-352">Non supportata</span><span class="sxs-lookup"><span data-stu-id="ed4bf-352">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-353">Supportato</span><span class="sxs-lookup"><span data-stu-id="ed4bf-353">Supported</span></span></p></td>
<td><p><span data-ttu-id="ed4bf-354">Supportato</span><span class="sxs-lookup"><span data-stu-id="ed4bf-354">Supported</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="support-for-joining-meetings"></a><span data-ttu-id="ed4bf-355">Supporto della partecipazione a riunioni</span><span class="sxs-lookup"><span data-stu-id="ed4bf-355">Support for Joining Meetings</span></span>

<span data-ttu-id="ed4bf-356">Tutti i client supportati da Lync Server 2013 sono autorizzati a partecipare alle riunioni di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-356">All of the clients that Lync Server 2013 supports are allowed to join Lync 2013 meetings.</span></span> <span data-ttu-id="ed4bf-357">Poiché Lync Web App è un componente Web del server, nei casi in cui viene utilizzata Lync Web App per partecipare a una riunione di Lync Server 2013, viene sempre utilizzata la versione più recente di Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-357">Because Lync Web App is a web component of the server, in cases where Lync Web App is used to join a Lync Server 2013 meeting, the newer version of Lync Web App is always used.</span></span>

<span data-ttu-id="ed4bf-358">I client Lync 2013 possono partecipare alle riunioni ospitate in Lync 2010 e Office Communications Server 2007 R2 con funzionalità con scalabilità orizzontale.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-358">Lync 2013 clients can join meetings hosted on Lync 2010 and Office Communications Server 2007 R2 with scaled-down functionality.</span></span> <span data-ttu-id="ed4bf-359">Le funzionalità per le riunioni sono limitate dalla versione del server in cui è ospitata la riunione.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-359">In-meeting features are limited by the version of the server on which the meeting is hosted.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ed4bf-360">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed4bf-360">See Also</span></span>


[<span data-ttu-id="ed4bf-361">Requisiti delle app di Windows Store di Lync per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed4bf-361">Lync Windows Store app requirements for Lync Server 2013</span></span>](lync-server-2013-lync-windows-store-app-requirements.md)  
[<span data-ttu-id="ed4bf-362">Nuove funzionalità di conferenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed4bf-362">New conferencing features in Lync Server 2013</span></span>](lync-server-2013-new-conferencing-features.md)  
[<span data-ttu-id="ed4bf-363">Novità per i client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed4bf-363">What's new for clients in Lync Server 2013</span></span>](lync-server-2013-what-s-new-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


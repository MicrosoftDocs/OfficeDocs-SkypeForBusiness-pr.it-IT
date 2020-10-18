---
title: 'Lync Server 2013: installazione e configurazione di nodi Watcher'
description: 'Lync Server 2013: installazione e configurazione di nodi Watcher.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing and configuring watcher nodes
ms:assetid: 61f6deea-e3ef-4468-9be8-a65705815ebb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204943(v=OCS.15)
ms:contentKeyID: 48184284
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87bf43e1651fabfa0137d09234d663cc905e947b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574002"
---
# <a name="installing-and-configuring-watcher-nodes-in-lync-server-2013"></a><span data-ttu-id="945b9-103">Installazione e configurazione di nodi Watcher in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="945b9-103">Installing and configuring watcher nodes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="945b9-104">_**Ultimo argomento modificato:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="945b9-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="945b9-105">I *nodi Watcher* sono computer che eseguono periodicamente transazioni sintetiche di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="945b9-105">*Watcher nodes* are computers that periodically run Lync Server synthetic transactions.</span></span> <span data-ttu-id="945b9-106">*Le transazioni sintetiche* sono cmdlet di Windows PowerShell che verificano che gli scenari fondamentali degli utenti finali, ad esempio la possibilità di accedere al sistema o la possibilità di scambiare messaggi istantanei, funzionino come previsto.</span><span class="sxs-lookup"><span data-stu-id="945b9-106">*Synthetic transactions* are Windows PowerShell cmdlets that verify that key end user scenarios—such as the ability to sign in to the system, or the ability to exchange instant messages—are working as expected.</span></span> <span data-ttu-id="945b9-107">Per Lync Server 2013, System Center Operations Manager è in grado di eseguire le transazioni sintetiche illustrate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="945b9-107">For Lync Server 2013, System Center Operations Manager can run the synthetic transactions shown in the following table.</span></span> <span data-ttu-id="945b9-108">Esistono tre tipi diversi di transazioni sintetiche:</span><span class="sxs-lookup"><span data-stu-id="945b9-108">There are three different synthetic transaction types shown in the table:</span></span>

  - <span data-ttu-id="945b9-109">**Valore predefinito**.</span><span class="sxs-lookup"><span data-stu-id="945b9-109">**Default**.</span></span> <span data-ttu-id="945b9-110">Queste sono le transazioni sintetiche eseguite per impostazione predefinita da un nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="945b9-110">These are the synthetic transactions that a watcher node will run by default.</span></span> <span data-ttu-id="945b9-111">Quando si crea un nuovo nodo Watcher esiste la possibilità di specificare quali transazioni sintetiche verranno eseguite dal nodo.</span><span class="sxs-lookup"><span data-stu-id="945b9-111">When you create a new watcher node, you have the option of specifying which synthetic transactions that node will run.</span></span> <span data-ttu-id="945b9-112">(Questo è lo scopo del parametro tests utilizzato dal cmdlet **New-CsWatcherNodeConfiguration** ). Se non si utilizza il parametro tests quando viene creato il nodo Watcher, verranno eseguite automaticamente tutte le transazioni sintetiche predefinite e non verranno eseguite le transazioni sintetiche non predefinite.</span><span class="sxs-lookup"><span data-stu-id="945b9-112">(That's the purpose of the Tests parameter used by the **New-CsWatcherNodeConfiguration** cmdlet.) If you do not use the Tests parameter when the watcher node is created, it will automatically run all the Default synthetic transactions and will not run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="945b9-113">Ciò significa,ad esempio, che il nodo Watcher verrà configurato per eseguire il test Test-CsAddressBookService, ma non il test Test-CsExumConnectivity.</span><span class="sxs-lookup"><span data-stu-id="945b9-113">That means, for example, that the watcher node will be configured to run the Test-CsAddressBookService test, but will not be configured to run the Test-CsExumConnectivity test.</span></span>

  - <span data-ttu-id="945b9-114">**Non predefinito**.</span><span class="sxs-lookup"><span data-stu-id="945b9-114">**Non-default**.</span></span> <span data-ttu-id="945b9-115">Come indica il nome, le transazioni sintetiche non predefinite sono i test che non vengono eseguiti per impostazione predefinita dai nodi Watcher.</span><span class="sxs-lookup"><span data-stu-id="945b9-115">As the name implies, Non-default synthetic transactions are tests that watcher nodes do not run by default.</span></span> <span data-ttu-id="945b9-116">Il nodo Watcher può essere tuttavia abilitato all'esecuzione di qualsiasi transazione sintetica non predefinita.</span><span class="sxs-lookup"><span data-stu-id="945b9-116">However, the watcher node can be enabled to run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="945b9-117">È possibile specificare questa impostazione durante la creazione del nodo Watcher (tramite il cmdlet **New-CsWatcherNodeConfiguration**) o in qualsiasi momento in seguito.</span><span class="sxs-lookup"><span data-stu-id="945b9-117">You can do this when you create the watcher node (by using the **New-CsWatcherNodeConfiguration** cmdlet), or at any time after that.</span></span> <span data-ttu-id="945b9-118">Per molte delle transazioni sintetiche non predefinite sono necessari passaggi aggiuntivi di configurazione.</span><span class="sxs-lookup"><span data-stu-id="945b9-118">Many of the Non-default synthetic transactions require extra setup steps.</span></span> <span data-ttu-id="945b9-119">Per informazioni dettagliate, vedere [istruzioni di installazione speciali per le transazioni sintetiche in Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="945b9-119">For details, see [Special setup instructions for synthetic transactions in Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md).</span></span>

  - <span data-ttu-id="945b9-120">**Extended**.</span><span class="sxs-lookup"><span data-stu-id="945b9-120">**Extended**.</span></span> <span data-ttu-id="945b9-121">I test estesi sono un tipo speciale di transazione sintetica non predefinita.</span><span class="sxs-lookup"><span data-stu-id="945b9-121">Extended tests are a special type of Non-default synthetic transaction.</span></span> <span data-ttu-id="945b9-122">Diversamente da altre transazioni sintetiche, i test estesi possono essere eseguiti più volte durante ogni passaggio.</span><span class="sxs-lookup"><span data-stu-id="945b9-122">Unlike other synthetic transactions, Extended tests can be run multiple times during each pass.</span></span> <span data-ttu-id="945b9-123">Si tratta di un'opzione utile durante la verifica di comportamenti come più route vocali PSTN (Public Switched Telephone Network) per un pool.</span><span class="sxs-lookup"><span data-stu-id="945b9-123">This can be useful when verifying behavior such as multiple public switched telephone network (PSTN) voice routes for a pool.</span></span> <span data-ttu-id="945b9-124">Per ottenere questa configurazione è sufficiente aggiungere più istanze di un test esteso a un nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="945b9-124">This can be configured simply by adding multiple instances of an Extended test to a watcher node.</span></span>

<span data-ttu-id="945b9-125">Per informazioni dettagliate sul processo di aggiunta di altre transazioni sintetiche a un nodo Watcher, vedere [Managing Watcher nodes in Lync Server 2013](lync-server-2013-managing-watcher-nodes.md).</span><span class="sxs-lookup"><span data-stu-id="945b9-125">For details about the process of adding other synthetic transactions to a watcher node, see [Managing watcher nodes in Lync Server 2013](lync-server-2013-managing-watcher-nodes.md).</span></span> <span data-ttu-id="945b9-126">È possibile utilizzare Lync Server Management Shell per rimuovere le transazioni sintetiche da un nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="945b9-126">You can use the Lync Server Management Shell to remove synthetic transactions from a watcher node.</span></span>

<span data-ttu-id="945b9-127">Le transazioni sintetiche disponibili per i nodi Watcher includono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="945b9-127">The synthetic transactions available to watcher nodes include the following:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="945b9-128">Nome del cmdlet (nome test)</span><span class="sxs-lookup"><span data-stu-id="945b9-128">Cmdlet Name (Test Name)</span></span></th>
<th><span data-ttu-id="945b9-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="945b9-129">Description</span></span></th>
<th><span data-ttu-id="945b9-130">Tipo di transazione sintetica</span><span class="sxs-lookup"><span data-stu-id="945b9-130">Synthetic Transaction Type</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="945b9-131">Test-CsAddressBookService (ABS)</span><span class="sxs-lookup"><span data-stu-id="945b9-131">Test-CsAddressBookService (ABS)</span></span></p></td>
<td><p><span data-ttu-id="945b9-132">Conferma che gli utenti siano in grado di cercare utenti non presenti nel loro elenco contatti.</span><span class="sxs-lookup"><span data-stu-id="945b9-132">Confirms that users are able to look up users that aren’t in their contact list.</span></span></p></td>
<td><p><span data-ttu-id="945b9-133">Predefiniti</span><span class="sxs-lookup"><span data-stu-id="945b9-133">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="945b9-134">Test-CsAddressBookWebQuery (ABWQ)</span><span class="sxs-lookup"><span data-stu-id="945b9-134">Test-CsAddressBookWebQuery (ABWQ)</span></span></p></td>
<td><p><span data-ttu-id="945b9-135">Conferma che gli utenti siano in grado di cercare utenti non presenti nel loro elenco contatti tramite HTTP.</span><span class="sxs-lookup"><span data-stu-id="945b9-135">Confirms that users are able to look up users that aren’t in their contact list via HTTP.</span></span></p></td>
<td><p><span data-ttu-id="945b9-136">Predefiniti</span><span class="sxs-lookup"><span data-stu-id="945b9-136">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="945b9-137">Test-CsIM (IM)</span><span class="sxs-lookup"><span data-stu-id="945b9-137">Test-CsIM (IM)</span></span></p></td>
<td><p><span data-ttu-id="945b9-138">Conferma che gli utenti siano in grado di inviare messaggi istantanei peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="945b9-138">Confirms that users are able to send peer-to-peer instant messages.</span></span></p></td>
<td><p><span data-ttu-id="945b9-139">Predefiniti</span><span class="sxs-lookup"><span data-stu-id="945b9-139">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="945b9-140">Test-CsP2PAV (P2PAV)</span><span class="sxs-lookup"><span data-stu-id="945b9-140">Test-CsP2PAV (P2PAV)</span></span></p></td>
<td><p><span data-ttu-id="945b9-141">Conferma che gli utenti siano in grado di effettuare chiamate audio peer-to-peer (solo segnalazione).</span><span class="sxs-lookup"><span data-stu-id="945b9-141">Confirms that users are able to place peer-to-peer audio calls (signaling only).</span></span></p></td>
<td><p><span data-ttu-id="945b9-142">Predefiniti</span><span class="sxs-lookup"><span data-stu-id="945b9-142">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="945b9-143">Test-CsPresence (Presence)</span><span class="sxs-lookup"><span data-stu-id="945b9-143">Test-CsPresence (Presence)</span></span></p></td>
<td><p><span data-ttu-id="945b9-144">Conferma che gli utenti siano in grado visualizzare la presenza di altri utenti.</span><span class="sxs-lookup"><span data-stu-id="945b9-144">Confirms that users are able to view other users’ presence.</span></span></p></td>
<td><p><span data-ttu-id="945b9-145">Predefiniti</span><span class="sxs-lookup"><span data-stu-id="945b9-145">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="945b9-146">Test-CsRegistration (Registration)</span><span class="sxs-lookup"><span data-stu-id="945b9-146">Test-CsRegistration (Registration)</span></span></p></td>
<td><p><span data-ttu-id="945b9-147">Conferma che gli utenti siano in grado di accedere a Lync.</span><span class="sxs-lookup"><span data-stu-id="945b9-147">Confirms that users are able sign in to Lync.</span></span></p></td>
<td><p><span data-ttu-id="945b9-148">Predefiniti</span><span class="sxs-lookup"><span data-stu-id="945b9-148">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="945b9-149">Test-CsAudioConferencingProvider (ACP)</span><span class="sxs-lookup"><span data-stu-id="945b9-149">Test-CsAudioConferencingProvider (ACP)</span></span></p></td>
<td><p><span data-ttu-id="945b9-150">Non utilizzata con la versione locale di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="945b9-150">Not used with the on-premises version of Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="945b9-151">Estesa</span><span class="sxs-lookup"><span data-stu-id="945b9-151">Extended</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="945b9-152">Test-CsPstnPeerToPeerCall (PSTN)</span><span class="sxs-lookup"><span data-stu-id="945b9-152">Test-CsPstnPeerToPeerCall (PSTN)</span></span></p></td>
<td><p><span data-ttu-id="945b9-153">Conferma che gli utenti siano in grado di effettuare e ricevere chiamate con persone esterne all'organizzazione (numeri PSTN).</span><span class="sxs-lookup"><span data-stu-id="945b9-153">Confirms that users are able to place and receive calls with people outside of the enterprise (PSTN numbers).</span></span></p></td>
<td><p><span data-ttu-id="945b9-154">Non predefinita, estesa</span><span class="sxs-lookup"><span data-stu-id="945b9-154">Non-default, Extended</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="945b9-155">Test-CsAVConference (AvConference)</span><span class="sxs-lookup"><span data-stu-id="945b9-155">Test-CsAVConference (AvConference)</span></span></p></td>
<td><p><span data-ttu-id="945b9-156">Conferma che gli utenti siano in grado di creare conferenze audio/video e di parteciparvi.</span><span class="sxs-lookup"><span data-stu-id="945b9-156">Confirms that users are able to create and participate in an audio/video conference.</span></span></p></td>
<td><p><span data-ttu-id="945b9-157">Predefiniti</span><span class="sxs-lookup"><span data-stu-id="945b9-157">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="945b9-158">Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</span><span class="sxs-lookup"><span data-stu-id="945b9-158">Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</span></span></p></td>
<td><p><span data-ttu-id="945b9-159">Conferma che gli A/V Edge Server siano in grado di accettare connessioni da chiamate e conferenze telefoniche peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="945b9-159">Confirms that the A/V Edge servers are able to accept connections for peer-to-peer calls and conference calls.</span></span></p></td>
<td><p><span data-ttu-id="945b9-160">Non predefinito</span><span class="sxs-lookup"><span data-stu-id="945b9-160">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="945b9-161">Test-CsDataConference (dataconference)</span><span class="sxs-lookup"><span data-stu-id="945b9-161">Test-CsDataConference (DataConference)</span></span></p></td>
<td><p><span data-ttu-id="945b9-162">Conferma che gli utenti possano partecipare a conferenze con collaborazione dati, ovvero una riunione online che include attività come lavagne e sondaggi.</span><span class="sxs-lookup"><span data-stu-id="945b9-162">Confirms that users can participate in a data collaboration conference, an online meeting that includes activities such as whiteboards and polls.</span></span></p></td>
<td><p><span data-ttu-id="945b9-163">Non predefinito</span><span class="sxs-lookup"><span data-stu-id="945b9-163">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="945b9-164">Test-CsExumConnectivity (ExumConnectivity)</span><span class="sxs-lookup"><span data-stu-id="945b9-164">Test-CsExumConnectivity (ExumConnectivity)</span></span></p></td>
<td><p><span data-ttu-id="945b9-165">Conferma che un utente può connettersi alla messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="945b9-165">Confirms that a user can connect to Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="945b9-166">Non predefinito</span><span class="sxs-lookup"><span data-stu-id="945b9-166">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="945b9-167">Test-CsGroupIM (GroupIM)</span><span class="sxs-lookup"><span data-stu-id="945b9-167">Test-CsGroupIM (GroupIM)</span></span></p></td>
<td><p><span data-ttu-id="945b9-168">Conferma che gli utenti siano in grado di inviare messaggi istantanei in conferenze e partecipare a conversazioni istantanee con tre o più persone.</span><span class="sxs-lookup"><span data-stu-id="945b9-168">Confirms that users are able to send instant messages in conferences and participate in instant message conversations with three or more people.</span></span></p></td>
<td><p><span data-ttu-id="945b9-169">Predefiniti</span><span class="sxs-lookup"><span data-stu-id="945b9-169">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="945b9-170">Test-CsGroupIM – TestJoinLauncher (JoinLauncher)</span><span class="sxs-lookup"><span data-stu-id="945b9-170">Test-CsGroupIM –TestJoinLauncher (JoinLauncher)</span></span></p></td>
<td><p><span data-ttu-id="945b9-171">Conferma che gli utenti siano in grado di creare riunioni pianificate e parteciparvi tramite un collegamento a un indirizzo Web.</span><span class="sxs-lookup"><span data-stu-id="945b9-171">Confirms that users are able to create and join scheduled meetings via a web address link.</span></span></p></td>
<td><p><span data-ttu-id="945b9-172">Non predefinito</span><span class="sxs-lookup"><span data-stu-id="945b9-172">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="945b9-173">Test-CsMCXP2PIM (MCXP2PIM)</span><span class="sxs-lookup"><span data-stu-id="945b9-173">Test-CsMCXP2PIM (MCXP2PIM)</span></span></p></td>
<td><p><span data-ttu-id="945b9-174">Conferma che gli utenti di dispositivi mobili siano in grado di registrarsi e inviare messaggi istantanei.</span><span class="sxs-lookup"><span data-stu-id="945b9-174">Confirms that mobile device users are able to register and send instant messages.</span></span></p></td>
<td><p><span data-ttu-id="945b9-175">Non predefinito</span><span class="sxs-lookup"><span data-stu-id="945b9-175">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="945b9-176">Test-CsPersistentChatMessage (PersistentChatMessage)</span><span class="sxs-lookup"><span data-stu-id="945b9-176">Test-CsPersistentChatMessage (PersistentChatMessage)</span></span></p></td>
<td><p><span data-ttu-id="945b9-177">Conferma che gli utenti possono scambiare messaggi tramite il servizio chat persistente.</span><span class="sxs-lookup"><span data-stu-id="945b9-177">Confirms that users can exchange messages by using the Persistent Chat service.</span></span></p></td>
<td><p><span data-ttu-id="945b9-178">Non predefinito</span><span class="sxs-lookup"><span data-stu-id="945b9-178">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="945b9-179">Test-CsUnifiedContactStore (UnifiedContactStore)</span><span class="sxs-lookup"><span data-stu-id="945b9-179">Test-CsUnifiedContactStore (UnifiedContactStore)</span></span></p></td>
<td><p><span data-ttu-id="945b9-180">Conferma che è possibile accedere ai contatti di un utente tramite l'archivio contatti unificato.</span><span class="sxs-lookup"><span data-stu-id="945b9-180">Confirms that a user's contacts can be accessed through the unified contact store.</span></span> <span data-ttu-id="945b9-181">L'archivio contatti unificato consente agli utenti di gestire un singolo gruppo di contatti a cui è possibile accedere utilizzando Lync 2013, Outlook e/o Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="945b9-181">The unified contact store provides a way for users to maintain a single set of contacts that can be accessed by using Lync 2013, Outlook, and/or Outlook Web Access.</span></span></p></td>
<td><p><span data-ttu-id="945b9-182">Non predefinito</span><span class="sxs-lookup"><span data-stu-id="945b9-182">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="945b9-183">Test-CsXmppIM (XmppIM)</span><span class="sxs-lookup"><span data-stu-id="945b9-183">Test-CsXmppIM (XmppIM)</span></span></p></td>
<td><p><span data-ttu-id="945b9-184">Conferma che sia possibile inviare un messaggio istantaneo attraverso il gateway XMPP (Extensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="945b9-184">Confirms that an instant message can be sent across the XMPP (Extensible Messaging and Presence Protocol) gateway.</span></span></p></td>
<td><p><span data-ttu-id="945b9-185">Non predefinito</span><span class="sxs-lookup"><span data-stu-id="945b9-185">Non-default</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="945b9-186">Non è necessario installare i nodi Watcher per poter utilizzare System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="945b9-186">You do not need to install watcher nodes in order to use System Center Operations Manager.</span></span> <span data-ttu-id="945b9-187">Se non si installano questi nodi, è comunque possibile ottenere avvisi in tempo reale dai componenti di Lync Server 2013 quando si verifica un problema.</span><span class="sxs-lookup"><span data-stu-id="945b9-187">If you do not install these nodes, you can still get real-time alerts from Lync Server 2013 components when an issue occurs.</span></span> <span data-ttu-id="945b9-188">(Il componente e il Management Pack degli utenti non utilizzano i nodi Watcher). Tuttavia, i nodi Watcher sono obbligatori se si desidera monitorare gli scenari end-to-end tramite Active Monitoring Management Pack.</span><span class="sxs-lookup"><span data-stu-id="945b9-188">(The Component and User Management Pack does not use watcher nodes.) However, watcher nodes are required if you want to monitor end-to-end scenarios by using the Active Monitoring Management pack.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="945b9-189">Gli amministratori possono inoltre eseguire transazioni sintetiche manualmente, senza dover utilizzare o installare Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="945b9-189">Administrators can also run synthetic transactions manually, without needing to use, or install, Operations Manager.</span></span> <span data-ttu-id="945b9-190">Per informazioni dettagliate sui vari cmdlet di Test-Cs, vedere l' <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">Indice dei cmdlet di Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="945b9-190">For details about the various Test-Cs cmdlets, see the <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">Lync Server 2013 cmdlets index</A>.</span></span>



</div>

<span data-ttu-id="945b9-191">A seconda delle dimensioni della distribuzione, le transazioni sintetiche potrebbero utilizzare una grande quantità di memoria e tempo del processore del computer.</span><span class="sxs-lookup"><span data-stu-id="945b9-191">Depending on the size of your deployment, synthetic transactions may use a large amount of computer memory and processor time.</span></span> <span data-ttu-id="945b9-192">Per questo motivo, è consigliabile utilizzare un computer dedicato come nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="945b9-192">For this reason, we recommend that you use a dedicated computer as a watcher node.</span></span> <span data-ttu-id="945b9-193">Ad esempio, non è necessario configurare un front end server come nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="945b9-193">For example, you should not configure a Front End Server to act as a watcher node.</span></span> <span data-ttu-id="945b9-194">I nodi Watcher devono rispondere alle specifiche hardware seguenti:</span><span class="sxs-lookup"><span data-stu-id="945b9-194">Watcher nodes should meet the following hardware specifications:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="945b9-195">Un nodo Microsoft Lync Server 2010 Watcher legacy non può essere collocato nello stesso computer con un nodo di monitoraggio di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="945b9-195">A legacy Microsoft Lync Server 2010 watcher node cannot be collocated on the same machine with a Lync Server 2013 watcher node.</span></span> <span data-ttu-id="945b9-196">Ciò è dovuto al fatto che i file di sistema di base per Lync Server 2010 e Lync Server 2013 non possono essere installati nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="945b9-196">This is because the core system files for Lync Server 2010 and Lync Server 2013 cannot be installed on the same computer.</span></span><BR><span data-ttu-id="945b9-197">Tuttavia, i nodi di monitoraggio di Lync Server 2013 possono monitorare contemporaneamente sia Lync Server 2013 che Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="945b9-197">However, Lync Server 2013 watcher nodes can simultaneously monitor both Lync Server 2013 and Lync Server 2010.</span></span> <span data-ttu-id="945b9-198">Le transazioni sintetiche predefinite sono supportate in entrambe le versioni.</span><span class="sxs-lookup"><span data-stu-id="945b9-198">The Default synthetic transactions are supported on both product versions.</span></span>



</div>

<span data-ttu-id="945b9-199">I nodi di Watcher di Lync Server 2013 possono essere distribuiti all'interno o all'esterno di un'organizzazione per consentirne la verifica:</span><span class="sxs-lookup"><span data-stu-id="945b9-199">Lync Server 2013 watcher nodes may be deployed inside or outside of an enterprise to help verify:</span></span>

  - <span></span>  
    <span data-ttu-id="945b9-200">Connettività ai pool per gli utenti all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="945b9-200">Connectivity to pools for users inside the enterprise.</span></span>

  - <span></span>  
    <span data-ttu-id="945b9-201">Connettività tramite reti perimetrali per gli utenti remoti che lavorano all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="945b9-201">Connectivity through perimeter networks for remote users who work outside the enterprise.</span></span>

  - <span></span>  
    <span data-ttu-id="945b9-202">Connettività a Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="945b9-202">Connectivity to branch office appliances.</span></span>

  - <span></span>  
    <span data-ttu-id="945b9-203">Connettività a Lync Server 2010 all'interno dell'organizzazione e tramite reti perimetrali.</span><span class="sxs-lookup"><span data-stu-id="945b9-203">Connectivity to Lync Server 2010 inside the enterprise and through perimeter networks.</span></span>

<span data-ttu-id="945b9-204">Sono disponibili opzioni di autenticazione diverse per le connessioni dall'interno e dall'esterno per semplificare l'amministrazione.</span><span class="sxs-lookup"><span data-stu-id="945b9-204">Different authentication options are available for inside and outside of the enterprise to help simplify administration.</span></span> <span data-ttu-id="945b9-205">Per ulteriori informazioni, vedere [configurazione di un nodo Watcher per l'esecuzione di transazioni sintetiche in Lync Server 2013](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="945b9-205">For details, see [Configuring a watcher node to run synthetic transactions in Lync Server 2013](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md).</span></span>

<span data-ttu-id="945b9-206">Per configurare un computer come nodo Watcher, è necessario eseguire i passaggi seguenti dopo aver installato System Center Operations Manager e aver importato Lync Server 2013 Management Pack.</span><span class="sxs-lookup"><span data-stu-id="945b9-206">To configure a computer to act as a watcher node, you must complete the following steps after you have installed System Center Operations Manager and imported the Lync Server 2013 management packs.</span></span>

<span data-ttu-id="945b9-207">Prima di installare i file di base di Lync Server 2013 e i file dell'agente centro di sistema, è inoltre necessario verificare che il computer del nodo Watcher soddisfi tutti i prerequisiti per l'installazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="945b9-207">Before you install the Lync Server 2013 core files and the System Center agent files, you should also make sure that the watcher node computer meets all the prerequisites for installing Lync Server 2013.</span></span> <span data-ttu-id="945b9-208">Nel computer del nodo Watcher, inoltre, dovrebbero essere installati gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="945b9-208">In addition, the watcher node computer should also have the following items installed:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="945b9-209">Componente hardware</span><span class="sxs-lookup"><span data-stu-id="945b9-209">Hardware component</span></span></th>
<th><span data-ttu-id="945b9-210">Requisito minimo</span><span class="sxs-lookup"><span data-stu-id="945b9-210">Minimum requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="945b9-211">CPU</span><span class="sxs-lookup"><span data-stu-id="945b9-211">CPU</span></span></p></td>
<td><p><span data-ttu-id="945b9-212">Una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="945b9-212">One of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="945b9-213">processore a 64 bit, quad-core, 2,33 GHz o superiore</span><span class="sxs-lookup"><span data-stu-id="945b9-213">64-bit processor, quad-core, 2.33 GHz or higher</span></span></p></li>
<li><p><span data-ttu-id="945b9-214">processore 2-Way a 64 bit, Dual Core, 2,33 GHz o superiore</span><span class="sxs-lookup"><span data-stu-id="945b9-214">64-bit 2-way processor, dual-core, 2.33 GHz or higher</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="945b9-215">Memoria</span><span class="sxs-lookup"><span data-stu-id="945b9-215">Memory</span></span></p></td>
<td><p><span data-ttu-id="945b9-216">8 GB</span><span class="sxs-lookup"><span data-stu-id="945b9-216">8 GB</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="945b9-217">Sistema operativo di rete</span><span class="sxs-lookup"><span data-stu-id="945b9-217">Network operating system</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="945b9-218">1 scheda di rete 1 Gbps</span><span class="sxs-lookup"><span data-stu-id="945b9-218">1 network adapter 1 Gbps</span></span></p></li>
<li><p><span data-ttu-id="945b9-219">Windows Server 2008 R2, Windows Server 2012 o</span><span class="sxs-lookup"><span data-stu-id="945b9-219">Windows Server 2008 R2, Windows Server 2012, or</span></span></p>
<p><span data-ttu-id="945b9-220">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="945b9-220">Windows Server 2012 R2</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


  - <span data-ttu-id="945b9-221">Versione completa di .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="945b9-221">The full version of .NET Framework 4.5.</span></span>

  - <span data-ttu-id="945b9-222">Windows Identity Foundation.</span><span class="sxs-lookup"><span data-stu-id="945b9-222">Windows Identity Foundation.</span></span>

  - <span data-ttu-id="945b9-223">Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="945b9-223">Windows PowerShell 3.0.</span></span>

<span data-ttu-id="945b9-224">Quando tutti questi prerequisiti sono soddisfatti è possibile procedere alla configurazione del nodo Watcher con i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="945b9-224">As soon as all these prerequisites have been met, you can configure the watcher node by:</span></span>

  - <span data-ttu-id="945b9-225">Installazione dei file di base di Lync Server 2013 nel computer del nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="945b9-225">Installing the Lync Server 2013 core files on the watcher node computer.</span></span>

  - <span data-ttu-id="945b9-226">Installazione dell'agente System Center Operations Manager nel computer del nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="945b9-226">Installing System Center Operations Manager agent on the watcher node computer.</span></span>

  - <span data-ttu-id="945b9-227">Esecuzione del file eseguibile Watchernode.msi.</span><span class="sxs-lookup"><span data-stu-id="945b9-227">Running the Watchernode.msi executable file.</span></span>

  - <span data-ttu-id="945b9-228">Utilizzo dei cmdlet **CsWatcherNodeConfiguration** per configurare gli utenti di prova utilizzati dal nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="945b9-228">Using the **CsWatcherNodeConfiguration** cmdlets to configure test users to be employed by the watcher node.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


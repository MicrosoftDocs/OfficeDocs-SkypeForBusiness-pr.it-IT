---
title: 'Lync Server 2013: installazione e configurazione di nodi Watcher'
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
ms.openlocfilehash: 0cd57e3b78e3e16ac9d640536771cf2b5b90773a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154758"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-and-configuring-watcher-nodes-in-lync-server-2013"></a><span data-ttu-id="53a12-102">Installazione e configurazione di nodi Watcher in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53a12-102">Installing and configuring watcher nodes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53a12-103">_**Ultimo argomento modificato:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="53a12-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="53a12-104">I *nodi Watcher* sono computer che eseguono periodicamente transazioni sintetiche di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="53a12-104">*Watcher nodes* are computers that periodically run Lync Server synthetic transactions.</span></span> <span data-ttu-id="53a12-105">*Le transazioni sintetiche* sono cmdlet di Windows PowerShell che verificano che gli scenari fondamentali degli utenti finali, ad esempio la possibilità di accedere al sistema o la possibilità di scambiare messaggi istantanei, funzionino come previsto.</span><span class="sxs-lookup"><span data-stu-id="53a12-105">*Synthetic transactions* are Windows PowerShell cmdlets that verify that key end user scenarios—such as the ability to sign in to the system, or the ability to exchange instant messages—are working as expected.</span></span> <span data-ttu-id="53a12-106">Per Lync Server 2013, System Center Operations Manager è in grado di eseguire le transazioni sintetiche illustrate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="53a12-106">For Lync Server 2013, System Center Operations Manager can run the synthetic transactions shown in the following table.</span></span> <span data-ttu-id="53a12-107">Esistono tre tipi diversi di transazioni sintetiche:</span><span class="sxs-lookup"><span data-stu-id="53a12-107">There are three different synthetic transaction types shown in the table:</span></span>

  - <span data-ttu-id="53a12-108">**Valore predefinito**.</span><span class="sxs-lookup"><span data-stu-id="53a12-108">**Default**.</span></span> <span data-ttu-id="53a12-109">Queste sono le transazioni sintetiche eseguite per impostazione predefinita da un nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="53a12-109">These are the synthetic transactions that a watcher node will run by default.</span></span> <span data-ttu-id="53a12-110">Quando si crea un nuovo nodo Watcher esiste la possibilità di specificare quali transazioni sintetiche verranno eseguite dal nodo.</span><span class="sxs-lookup"><span data-stu-id="53a12-110">When you create a new watcher node, you have the option of specifying which synthetic transactions that node will run.</span></span> <span data-ttu-id="53a12-111">(Questo è lo scopo del parametro tests utilizzato dal cmdlet **New-CsWatcherNodeConfiguration** ). Se non si utilizza il parametro tests quando viene creato il nodo Watcher, verranno eseguite automaticamente tutte le transazioni sintetiche predefinite e non verranno eseguite le transazioni sintetiche non predefinite.</span><span class="sxs-lookup"><span data-stu-id="53a12-111">(That's the purpose of the Tests parameter used by the **New-CsWatcherNodeConfiguration** cmdlet.) If you do not use the Tests parameter when the watcher node is created, it will automatically run all the Default synthetic transactions and will not run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="53a12-112">Ciò significa,ad esempio, che il nodo Watcher verrà configurato per eseguire il test Test-CsAddressBookService, ma non il test Test-CsExumConnectivity.</span><span class="sxs-lookup"><span data-stu-id="53a12-112">That means, for example, that the watcher node will be configured to run the Test-CsAddressBookService test, but will not be configured to run the Test-CsExumConnectivity test.</span></span>

  - <span data-ttu-id="53a12-113">**Non predefinito**.</span><span class="sxs-lookup"><span data-stu-id="53a12-113">**Non-default**.</span></span> <span data-ttu-id="53a12-114">Come indica il nome, le transazioni sintetiche non predefinite sono i test che non vengono eseguiti per impostazione predefinita dai nodi Watcher.</span><span class="sxs-lookup"><span data-stu-id="53a12-114">As the name implies, Non-default synthetic transactions are tests that watcher nodes do not run by default.</span></span> <span data-ttu-id="53a12-115">Il nodo Watcher può essere tuttavia abilitato all'esecuzione di qualsiasi transazione sintetica non predefinita.</span><span class="sxs-lookup"><span data-stu-id="53a12-115">However, the watcher node can be enabled to run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="53a12-116">È possibile specificare questa impostazione durante la creazione del nodo Watcher (tramite il cmdlet **New-CsWatcherNodeConfiguration**) o in qualsiasi momento in seguito.</span><span class="sxs-lookup"><span data-stu-id="53a12-116">You can do this when you create the watcher node (by using the **New-CsWatcherNodeConfiguration** cmdlet), or at any time after that.</span></span> <span data-ttu-id="53a12-117">Per molte delle transazioni sintetiche non predefinite sono necessari passaggi aggiuntivi di configurazione.</span><span class="sxs-lookup"><span data-stu-id="53a12-117">Many of the Non-default synthetic transactions require extra setup steps.</span></span> <span data-ttu-id="53a12-118">Per informazioni dettagliate, vedere [istruzioni di installazione speciali per le transazioni sintetiche in Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="53a12-118">For details, see [Special setup instructions for synthetic transactions in Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md).</span></span>

  - <span data-ttu-id="53a12-119">**Extended**.</span><span class="sxs-lookup"><span data-stu-id="53a12-119">**Extended**.</span></span> <span data-ttu-id="53a12-120">I test estesi sono un tipo speciale di transazione sintetica non predefinita.</span><span class="sxs-lookup"><span data-stu-id="53a12-120">Extended tests are a special type of Non-default synthetic transaction.</span></span> <span data-ttu-id="53a12-121">Diversamente da altre transazioni sintetiche, i test estesi possono essere eseguiti più volte durante ogni passaggio.</span><span class="sxs-lookup"><span data-stu-id="53a12-121">Unlike other synthetic transactions, Extended tests can be run multiple times during each pass.</span></span> <span data-ttu-id="53a12-122">Si tratta di un'opzione utile durante la verifica di comportamenti come più route vocali PSTN (Public Switched Telephone Network) per un pool.</span><span class="sxs-lookup"><span data-stu-id="53a12-122">This can be useful when verifying behavior such as multiple public switched telephone network (PSTN) voice routes for a pool.</span></span> <span data-ttu-id="53a12-123">Per ottenere questa configurazione è sufficiente aggiungere più istanze di un test esteso a un nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="53a12-123">This can be configured simply by adding multiple instances of an Extended test to a watcher node.</span></span>

<span data-ttu-id="53a12-124">Per informazioni dettagliate sul processo di aggiunta di altre transazioni sintetiche a un nodo Watcher, vedere [Managing Watcher nodes in Lync Server 2013](lync-server-2013-managing-watcher-nodes.md).</span><span class="sxs-lookup"><span data-stu-id="53a12-124">For details about the process of adding other synthetic transactions to a watcher node, see [Managing watcher nodes in Lync Server 2013](lync-server-2013-managing-watcher-nodes.md).</span></span> <span data-ttu-id="53a12-125">È possibile utilizzare Lync Server Management Shell per rimuovere le transazioni sintetiche da un nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="53a12-125">You can use the Lync Server Management Shell to remove synthetic transactions from a watcher node.</span></span>

<span data-ttu-id="53a12-126">Le transazioni sintetiche disponibili per i nodi Watcher includono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="53a12-126">The synthetic transactions available to watcher nodes include the following:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="53a12-127">Nome del cmdlet (nome test)</span><span class="sxs-lookup"><span data-stu-id="53a12-127">Cmdlet Name (Test Name)</span></span></th>
<th><span data-ttu-id="53a12-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53a12-128">Description</span></span></th>
<th><span data-ttu-id="53a12-129">Tipo di transazione sintetica</span><span class="sxs-lookup"><span data-stu-id="53a12-129">Synthetic Transaction Type</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="53a12-130">Test-CsAddressBookService (ABS)</span><span class="sxs-lookup"><span data-stu-id="53a12-130">Test-CsAddressBookService (ABS)</span></span></p></td>
<td><p><span data-ttu-id="53a12-131">Conferma che gli utenti siano in grado di cercare utenti non presenti nel loro elenco contatti.</span><span class="sxs-lookup"><span data-stu-id="53a12-131">Confirms that users are able to look up users that aren’t in their contact list.</span></span></p></td>
<td><p><span data-ttu-id="53a12-132">Predefinita</span><span class="sxs-lookup"><span data-stu-id="53a12-132">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a12-133">Test-CsAddressBookWebQuery (ABWQ)</span><span class="sxs-lookup"><span data-stu-id="53a12-133">Test-CsAddressBookWebQuery (ABWQ)</span></span></p></td>
<td><p><span data-ttu-id="53a12-134">Conferma che gli utenti siano in grado di cercare utenti non presenti nel loro elenco contatti tramite HTTP.</span><span class="sxs-lookup"><span data-stu-id="53a12-134">Confirms that users are able to look up users that aren’t in their contact list via HTTP.</span></span></p></td>
<td><p><span data-ttu-id="53a12-135">Predefinita</span><span class="sxs-lookup"><span data-stu-id="53a12-135">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a12-136">Test-CsIM (IM)</span><span class="sxs-lookup"><span data-stu-id="53a12-136">Test-CsIM (IM)</span></span></p></td>
<td><p><span data-ttu-id="53a12-137">Conferma che gli utenti siano in grado di inviare messaggi istantanei peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="53a12-137">Confirms that users are able to send peer-to-peer instant messages.</span></span></p></td>
<td><p><span data-ttu-id="53a12-138">Predefinita</span><span class="sxs-lookup"><span data-stu-id="53a12-138">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a12-139">Test-CsP2PAV (P2PAV)</span><span class="sxs-lookup"><span data-stu-id="53a12-139">Test-CsP2PAV (P2PAV)</span></span></p></td>
<td><p><span data-ttu-id="53a12-140">Conferma che gli utenti siano in grado di effettuare chiamate audio peer-to-peer (solo segnalazione).</span><span class="sxs-lookup"><span data-stu-id="53a12-140">Confirms that users are able to place peer-to-peer audio calls (signaling only).</span></span></p></td>
<td><p><span data-ttu-id="53a12-141">Predefinita</span><span class="sxs-lookup"><span data-stu-id="53a12-141">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a12-142">Test-CsPresence (Presence)</span><span class="sxs-lookup"><span data-stu-id="53a12-142">Test-CsPresence (Presence)</span></span></p></td>
<td><p><span data-ttu-id="53a12-143">Conferma che gli utenti siano in grado visualizzare la presenza di altri utenti.</span><span class="sxs-lookup"><span data-stu-id="53a12-143">Confirms that users are able to view other users’ presence.</span></span></p></td>
<td><p><span data-ttu-id="53a12-144">Predefinita</span><span class="sxs-lookup"><span data-stu-id="53a12-144">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a12-145">Test-CsRegistration (Registration)</span><span class="sxs-lookup"><span data-stu-id="53a12-145">Test-CsRegistration (Registration)</span></span></p></td>
<td><p><span data-ttu-id="53a12-146">Conferma che gli utenti siano in grado di accedere a Lync.</span><span class="sxs-lookup"><span data-stu-id="53a12-146">Confirms that users are able sign in to Lync.</span></span></p></td>
<td><p><span data-ttu-id="53a12-147">Predefinita</span><span class="sxs-lookup"><span data-stu-id="53a12-147">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a12-148">Test-CsAudioConferencingProvider (ACP)</span><span class="sxs-lookup"><span data-stu-id="53a12-148">Test-CsAudioConferencingProvider (ACP)</span></span></p></td>
<td><p><span data-ttu-id="53a12-149">Non utilizzata con la versione locale di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53a12-149">Not used with the on-premises version of Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="53a12-150">Estesa</span><span class="sxs-lookup"><span data-stu-id="53a12-150">Extended</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a12-151">Test-CsPstnPeerToPeerCall (PSTN)</span><span class="sxs-lookup"><span data-stu-id="53a12-151">Test-CsPstnPeerToPeerCall (PSTN)</span></span></p></td>
<td><p><span data-ttu-id="53a12-152">Conferma che gli utenti siano in grado di effettuare e ricevere chiamate con persone esterne all'organizzazione (numeri PSTN).</span><span class="sxs-lookup"><span data-stu-id="53a12-152">Confirms that users are able to place and receive calls with people outside of the enterprise (PSTN numbers).</span></span></p></td>
<td><p><span data-ttu-id="53a12-153">Non predefinita, estesa</span><span class="sxs-lookup"><span data-stu-id="53a12-153">Non-default, Extended</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a12-154">Test-CsAVConference (AvConference)</span><span class="sxs-lookup"><span data-stu-id="53a12-154">Test-CsAVConference (AvConference)</span></span></p></td>
<td><p><span data-ttu-id="53a12-155">Conferma che gli utenti siano in grado di creare conferenze audio/video e di parteciparvi.</span><span class="sxs-lookup"><span data-stu-id="53a12-155">Confirms that users are able to create and participate in an audio/video conference.</span></span></p></td>
<td><p><span data-ttu-id="53a12-156">Predefinita</span><span class="sxs-lookup"><span data-stu-id="53a12-156">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a12-157">Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</span><span class="sxs-lookup"><span data-stu-id="53a12-157">Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</span></span></p></td>
<td><p><span data-ttu-id="53a12-158">Conferma che gli A/V Edge Server siano in grado di accettare connessioni da chiamate e conferenze telefoniche peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="53a12-158">Confirms that the A/V Edge servers are able to accept connections for peer-to-peer calls and conference calls.</span></span></p></td>
<td><p><span data-ttu-id="53a12-159">Non predefinito</span><span class="sxs-lookup"><span data-stu-id="53a12-159">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a12-160">Test-CsDataConference (dataconference)</span><span class="sxs-lookup"><span data-stu-id="53a12-160">Test-CsDataConference (DataConference)</span></span></p></td>
<td><p><span data-ttu-id="53a12-161">Conferma che gli utenti possano partecipare a conferenze con collaborazione dati, ovvero una riunione online che include attività come lavagne e sondaggi.</span><span class="sxs-lookup"><span data-stu-id="53a12-161">Confirms that users can participate in a data collaboration conference, an online meeting that includes activities such as whiteboards and polls.</span></span></p></td>
<td><p><span data-ttu-id="53a12-162">Non predefinito</span><span class="sxs-lookup"><span data-stu-id="53a12-162">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a12-163">Test-CsExumConnectivity (ExumConnectivity)</span><span class="sxs-lookup"><span data-stu-id="53a12-163">Test-CsExumConnectivity (ExumConnectivity)</span></span></p></td>
<td><p><span data-ttu-id="53a12-164">Conferma che un utente può connettersi alla messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="53a12-164">Confirms that a user can connect to Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="53a12-165">Non predefinito</span><span class="sxs-lookup"><span data-stu-id="53a12-165">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a12-166">Test-CsGroupIM (GroupIM)</span><span class="sxs-lookup"><span data-stu-id="53a12-166">Test-CsGroupIM (GroupIM)</span></span></p></td>
<td><p><span data-ttu-id="53a12-167">Conferma che gli utenti siano in grado di inviare messaggi istantanei in conferenze e partecipare a conversazioni istantanee con tre o più persone.</span><span class="sxs-lookup"><span data-stu-id="53a12-167">Confirms that users are able to send instant messages in conferences and participate in instant message conversations with three or more people.</span></span></p></td>
<td><p><span data-ttu-id="53a12-168">Predefinita</span><span class="sxs-lookup"><span data-stu-id="53a12-168">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a12-169">Test-CsGroupIM – TestJoinLauncher (JoinLauncher)</span><span class="sxs-lookup"><span data-stu-id="53a12-169">Test-CsGroupIM –TestJoinLauncher (JoinLauncher)</span></span></p></td>
<td><p><span data-ttu-id="53a12-170">Conferma che gli utenti siano in grado di creare riunioni pianificate e parteciparvi tramite un collegamento a un indirizzo Web.</span><span class="sxs-lookup"><span data-stu-id="53a12-170">Confirms that users are able to create and join scheduled meetings via a web address link.</span></span></p></td>
<td><p><span data-ttu-id="53a12-171">Non predefinito</span><span class="sxs-lookup"><span data-stu-id="53a12-171">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a12-172">Test-CsMCXP2PIM (MCXP2PIM)</span><span class="sxs-lookup"><span data-stu-id="53a12-172">Test-CsMCXP2PIM (MCXP2PIM)</span></span></p></td>
<td><p><span data-ttu-id="53a12-173">Conferma che gli utenti di dispositivi mobili siano in grado di registrarsi e inviare messaggi istantanei.</span><span class="sxs-lookup"><span data-stu-id="53a12-173">Confirms that mobile device users are able to register and send instant messages.</span></span></p></td>
<td><p><span data-ttu-id="53a12-174">Non predefinito</span><span class="sxs-lookup"><span data-stu-id="53a12-174">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a12-175">Test-CsPersistentChatMessage (PersistentChatMessage)</span><span class="sxs-lookup"><span data-stu-id="53a12-175">Test-CsPersistentChatMessage (PersistentChatMessage)</span></span></p></td>
<td><p><span data-ttu-id="53a12-176">Conferma che gli utenti possono scambiare messaggi tramite il servizio chat persistente.</span><span class="sxs-lookup"><span data-stu-id="53a12-176">Confirms that users can exchange messages by using the Persistent Chat service.</span></span></p></td>
<td><p><span data-ttu-id="53a12-177">Non predefinito</span><span class="sxs-lookup"><span data-stu-id="53a12-177">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a12-178">Test-CsUnifiedContactStore (UnifiedContactStore)</span><span class="sxs-lookup"><span data-stu-id="53a12-178">Test-CsUnifiedContactStore (UnifiedContactStore)</span></span></p></td>
<td><p><span data-ttu-id="53a12-179">Conferma che è possibile accedere ai contatti di un utente tramite l'archivio contatti unificato.</span><span class="sxs-lookup"><span data-stu-id="53a12-179">Confirms that a user's contacts can be accessed through the unified contact store.</span></span> <span data-ttu-id="53a12-180">L'archivio contatti unificato consente agli utenti di gestire un singolo gruppo di contatti a cui è possibile accedere utilizzando Lync 2013, Outlook e/o Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="53a12-180">The unified contact store provides a way for users to maintain a single set of contacts that can be accessed by using Lync 2013, Outlook, and/or Outlook Web Access.</span></span></p></td>
<td><p><span data-ttu-id="53a12-181">Non predefinito</span><span class="sxs-lookup"><span data-stu-id="53a12-181">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a12-182">Test-CsXmppIM (XmppIM)</span><span class="sxs-lookup"><span data-stu-id="53a12-182">Test-CsXmppIM (XmppIM)</span></span></p></td>
<td><p><span data-ttu-id="53a12-183">Conferma che sia possibile inviare un messaggio istantaneo attraverso il gateway XMPP (Extensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="53a12-183">Confirms that an instant message can be sent across the XMPP (Extensible Messaging and Presence Protocol) gateway.</span></span></p></td>
<td><p><span data-ttu-id="53a12-184">Non predefinito</span><span class="sxs-lookup"><span data-stu-id="53a12-184">Non-default</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="53a12-185">Non è necessario installare i nodi Watcher per poter utilizzare System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="53a12-185">You do not need to install watcher nodes in order to use System Center Operations Manager.</span></span> <span data-ttu-id="53a12-186">Se non si installano questi nodi, è comunque possibile ottenere avvisi in tempo reale dai componenti di Lync Server 2013 quando si verifica un problema.</span><span class="sxs-lookup"><span data-stu-id="53a12-186">If you do not install these nodes, you can still get real-time alerts from Lync Server 2013 components when an issue occurs.</span></span> <span data-ttu-id="53a12-187">(Il componente e il Management Pack degli utenti non utilizzano i nodi Watcher). Tuttavia, i nodi Watcher sono obbligatori se si desidera monitorare gli scenari end-to-end tramite Active Monitoring Management Pack.</span><span class="sxs-lookup"><span data-stu-id="53a12-187">(The Component and User Management Pack does not use watcher nodes.) However, watcher nodes are required if you want to monitor end-to-end scenarios by using the Active Monitoring Management pack.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="53a12-188">Gli amministratori possono inoltre eseguire transazioni sintetiche manualmente, senza dover utilizzare o installare Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="53a12-188">Administrators can also run synthetic transactions manually, without needing to use, or install, Operations Manager.</span></span> <span data-ttu-id="53a12-189">Per informazioni dettagliate sui vari cmdlet test-CS, vedere l' <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">Indice dei cmdlet di Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="53a12-189">For details about the various Test-Cs cmdlets, see the <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">Lync Server 2013 cmdlets index</A>.</span></span>



</div>

<span data-ttu-id="53a12-190">A seconda delle dimensioni della distribuzione, le transazioni sintetiche potrebbero utilizzare una grande quantità di memoria e tempo del processore del computer.</span><span class="sxs-lookup"><span data-stu-id="53a12-190">Depending on the size of your deployment, synthetic transactions may use a large amount of computer memory and processor time.</span></span> <span data-ttu-id="53a12-191">Per questo motivo, è consigliabile utilizzare un computer dedicato come nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="53a12-191">For this reason, we recommend that you use a dedicated computer as a watcher node.</span></span> <span data-ttu-id="53a12-192">Ad esempio, non è necessario configurare un front end server come nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="53a12-192">For example, you should not configure a Front End Server to act as a watcher node.</span></span> <span data-ttu-id="53a12-193">I nodi Watcher devono rispondere alle specifiche hardware seguenti:</span><span class="sxs-lookup"><span data-stu-id="53a12-193">Watcher nodes should meet the following hardware specifications:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="53a12-194">Un nodo Microsoft Lync Server 2010 Watcher legacy non può essere collocato nello stesso computer con un nodo di monitoraggio di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a12-194">A legacy Microsoft Lync Server 2010 watcher node cannot be collocated on the same machine with a Lync Server 2013 watcher node.</span></span> <span data-ttu-id="53a12-195">Ciò è dovuto al fatto che i file di sistema di base per Lync Server 2010 e Lync Server 2013 non possono essere installati nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="53a12-195">This is because the core system files for Lync Server 2010 and Lync Server 2013 cannot be installed on the same computer.</span></span><BR><span data-ttu-id="53a12-196">Tuttavia, i nodi di monitoraggio di Lync Server 2013 possono monitorare contemporaneamente sia Lync Server 2013 che Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="53a12-196">However, Lync Server 2013 watcher nodes can simultaneously monitor both Lync Server 2013 and Lync Server 2010.</span></span> <span data-ttu-id="53a12-197">Le transazioni sintetiche predefinite sono supportate in entrambe le versioni.</span><span class="sxs-lookup"><span data-stu-id="53a12-197">The Default synthetic transactions are supported on both product versions.</span></span>



</div>

<span data-ttu-id="53a12-198">I nodi di Watcher di Lync Server 2013 possono essere distribuiti all'interno o all'esterno di un'organizzazione per consentirne la verifica:</span><span class="sxs-lookup"><span data-stu-id="53a12-198">Lync Server 2013 watcher nodes may be deployed inside or outside of an enterprise to help verify:</span></span>

  - <span></span>  
    <span data-ttu-id="53a12-199">Connettività ai pool per gli utenti all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="53a12-199">Connectivity to pools for users inside the enterprise.</span></span>

  - <span></span>  
    <span data-ttu-id="53a12-200">Connettività tramite reti perimetrali per gli utenti remoti che lavorano all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="53a12-200">Connectivity through perimeter networks for remote users who work outside the enterprise.</span></span>

  - <span></span>  
    <span data-ttu-id="53a12-201">Connettività a Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="53a12-201">Connectivity to branch office appliances.</span></span>

  - <span></span>  
    <span data-ttu-id="53a12-202">Connettività a Lync Server 2010 all'interno dell'organizzazione e tramite reti perimetrali.</span><span class="sxs-lookup"><span data-stu-id="53a12-202">Connectivity to Lync Server 2010 inside the enterprise and through perimeter networks.</span></span>

<span data-ttu-id="53a12-203">Sono disponibili opzioni di autenticazione diverse per le connessioni dall'interno e dall'esterno per semplificare l'amministrazione.</span><span class="sxs-lookup"><span data-stu-id="53a12-203">Different authentication options are available for inside and outside of the enterprise to help simplify administration.</span></span> <span data-ttu-id="53a12-204">Per ulteriori informazioni, vedere [configurazione di un nodo Watcher per l'esecuzione di transazioni sintetiche in Lync Server 2013](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="53a12-204">For details, see [Configuring a watcher node to run synthetic transactions in Lync Server 2013](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md).</span></span>

<span data-ttu-id="53a12-205">Per configurare un computer come nodo Watcher, è necessario eseguire i passaggi seguenti dopo aver installato System Center Operations Manager e aver importato Lync Server 2013 Management Pack.</span><span class="sxs-lookup"><span data-stu-id="53a12-205">To configure a computer to act as a watcher node, you must complete the following steps after you have installed System Center Operations Manager and imported the Lync Server 2013 management packs.</span></span>

<span data-ttu-id="53a12-206">Prima di installare i file di base di Lync Server 2013 e i file dell'agente centro di sistema, è inoltre necessario verificare che il computer del nodo Watcher soddisfi tutti i prerequisiti per l'installazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a12-206">Before you install the Lync Server 2013 core files and the System Center agent files, you should also make sure that the watcher node computer meets all the prerequisites for installing Lync Server 2013.</span></span> <span data-ttu-id="53a12-207">Nel computer del nodo Watcher, inoltre, dovrebbero essere installati gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="53a12-207">In addition, the watcher node computer should also have the following items installed:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="53a12-208">Componente hardware</span><span class="sxs-lookup"><span data-stu-id="53a12-208">Hardware component</span></span></th>
<th><span data-ttu-id="53a12-209">Requisito minimo</span><span class="sxs-lookup"><span data-stu-id="53a12-209">Minimum requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="53a12-210">CPU</span><span class="sxs-lookup"><span data-stu-id="53a12-210">CPU</span></span></p></td>
<td><p><span data-ttu-id="53a12-211">Una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="53a12-211">One of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="53a12-212">processore a 64 bit, quad-core, 2,33 GHz o superiore</span><span class="sxs-lookup"><span data-stu-id="53a12-212">64-bit processor, quad-core, 2.33 GHz or higher</span></span></p></li>
<li><p><span data-ttu-id="53a12-213">processore 2-Way a 64 bit, Dual Core, 2,33 GHz o superiore</span><span class="sxs-lookup"><span data-stu-id="53a12-213">64-bit 2-way processor, dual-core, 2.33 GHz or higher</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a12-214">Memoria</span><span class="sxs-lookup"><span data-stu-id="53a12-214">Memory</span></span></p></td>
<td><p><span data-ttu-id="53a12-215">8 GB</span><span class="sxs-lookup"><span data-stu-id="53a12-215">8 GB</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a12-216">Sistema operativo di rete</span><span class="sxs-lookup"><span data-stu-id="53a12-216">Network operating system</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="53a12-217">1 scheda di rete 1 Gbps</span><span class="sxs-lookup"><span data-stu-id="53a12-217">1 network adapter 1 Gbps</span></span></p></li>
<li><p><span data-ttu-id="53a12-218">Windows Server 2008 R2, Windows Server 2012 o</span><span class="sxs-lookup"><span data-stu-id="53a12-218">Windows Server 2008 R2, Windows Server 2012, or</span></span></p>
<p><span data-ttu-id="53a12-219">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="53a12-219">Windows Server 2012 R2</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


  - <span data-ttu-id="53a12-220">Versione completa di .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="53a12-220">The full version of .NET Framework 4.5.</span></span>

  - <span data-ttu-id="53a12-221">Windows Identity Foundation.</span><span class="sxs-lookup"><span data-stu-id="53a12-221">Windows Identity Foundation.</span></span>

  - <span data-ttu-id="53a12-222">Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="53a12-222">Windows PowerShell 3.0.</span></span>

<span data-ttu-id="53a12-223">Quando tutti questi prerequisiti sono soddisfatti è possibile procedere alla configurazione del nodo Watcher con i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="53a12-223">As soon as all these prerequisites have been met, you can configure the watcher node by:</span></span>

  - <span data-ttu-id="53a12-224">Installazione dei file di base di Lync Server 2013 nel computer del nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="53a12-224">Installing the Lync Server 2013 core files on the watcher node computer.</span></span>

  - <span data-ttu-id="53a12-225">Installazione dell'agente System Center Operations Manager nel computer del nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="53a12-225">Installing System Center Operations Manager agent on the watcher node computer.</span></span>

  - <span data-ttu-id="53a12-226">Esecuzione del file eseguibile Watchernode.msi.</span><span class="sxs-lookup"><span data-stu-id="53a12-226">Running the Watchernode.msi executable file.</span></span>

  - <span data-ttu-id="53a12-227">Utilizzo dei cmdlet **CsWatcherNodeConfiguration** per configurare gli utenti di prova utilizzati dal nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="53a12-227">Using the **CsWatcherNodeConfiguration** cmdlets to configure test users to be employed by the watcher node.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


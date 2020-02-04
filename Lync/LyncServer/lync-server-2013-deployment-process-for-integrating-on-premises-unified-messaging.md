---
title: Processo di distribuzione per l'integrazione della messaggistica unificata locale
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 269a4436-f09f-415b-96ab-49a64370a385
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425737(v=OCS.15)
ms:contentKeyID: 48183664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76a45210fa90e5d2493885e54f07bb922f6d0495
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762614"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="dfafd-102">Processo di distribuzione per l'integrazione della messaggistica unificata locale con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfafd-102">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dfafd-103">_**Argomento Ultima modifica:** 2012-12-17_</span><span class="sxs-lookup"><span data-stu-id="dfafd-103">_**Topic Last Modified:** 2012-12-17_</span></span>

<span data-ttu-id="dfafd-104">Se si vuole integrare la messaggistica UNIFICAta di Exchange con Lync Server 2013, è necessario eseguire le attività descritte in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="dfafd-104">If you want to integrate Exchange Unified Messaging (UM) with Lync Server 2013, you must perform the tasks described in this topic.</span></span> <span data-ttu-id="dfafd-105">Verificare inoltre le procedure consigliate per la pianificazione e la distribuzione descritte in [linee guida per l'integrazione della messaggistica unificata locale e di Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md).</span><span class="sxs-lookup"><span data-stu-id="dfafd-105">Also be sure that you review the planning and deployment best practices described in [Guidelines for integrating on-premises Unified Messaging and Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md).</span></span> <span data-ttu-id="dfafd-106">Questo argomento presuppone che sia stato distribuito Lync Server 2013 con un Mediation Server collocato e che siano stati abilitati gli utenti per Lync Server 2013, ma non necessariamente che siano stati eseguiti tutti i passaggi per la distribuzione e la configurazione per abilitare VoIP aziendale, come descritto in [distribuzione di VoIP aziendale in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="dfafd-106">This topic assumes that you have deployed Lync Server 2013 with a collocated Mediation Server and that you have enabled users for Lync Server 2013, but not necessarily that you have performed all deployment and configuration steps to enable Enterprise Voice, as described in [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span>

<div>

## <a name="unified-messaging-integration-process"></a><span data-ttu-id="dfafd-107">Processo di integrazione della messaggistica unificata</span><span class="sxs-lookup"><span data-stu-id="dfafd-107">Unified Messaging Integration Process</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="dfafd-108">È importante coordinarsi con gli amministratori di Exchange dell'organizzazione per confermare le attività che ognuno di voi eseguirà per garantire una corretta integrazione.</span><span class="sxs-lookup"><span data-stu-id="dfafd-108">It is important that you coordinate with your organization’s Exchange administrators to confirm the tasks that each of you will perform to help ensure a smooth, successful integration.</span></span>



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
<th><span data-ttu-id="dfafd-109">Fase</span><span class="sxs-lookup"><span data-stu-id="dfafd-109">Phase</span></span></th>
<th><span data-ttu-id="dfafd-110">Passaggi</span><span class="sxs-lookup"><span data-stu-id="dfafd-110">Steps</span></span></th>
<th><span data-ttu-id="dfafd-111">Gruppi e ruoli obbligatori</span><span class="sxs-lookup"><span data-stu-id="dfafd-111">Required groups and roles</span></span></th>
<th><span data-ttu-id="dfafd-112">Documentazione di distribuzione</span><span class="sxs-lookup"><span data-stu-id="dfafd-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dfafd-113">Distribuire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dfafd-113">Deploy one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="dfafd-114">Microsoft Exchange Server 2007 Service Pack 1 (SP2) o Service Pack più recente</span><span class="sxs-lookup"><span data-stu-id="dfafd-114">Microsoft Exchange Server 2007 Service Pack 1 (SP2) or latest service pack</span></span></p></li>
<li><p><span data-ttu-id="dfafd-115">Microsoft Exchange Server 2010 o Service Pack più recente</span><span class="sxs-lookup"><span data-stu-id="dfafd-115">Microsoft Exchange Server 2010 or latest service pack</span></span></p></li>
<li><p><span data-ttu-id="dfafd-116">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfafd-116">Microsoft Exchange Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="dfafd-117">Se si usa Microsoft Exchange Server 2013, installare i ruoli di Exchange Server seguenti nella stessa foresta o in un'altra foresta come Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="dfafd-117">If you are using Microsoft Exchange Server 2013, install the following Exchange Server roles in either the same forest or a different forest as Lync Server 2013:</span></span></p>
<ul>
<li><p><span data-ttu-id="dfafd-118">Accesso client</span><span class="sxs-lookup"><span data-stu-id="dfafd-118">Client Access</span></span></p></li>
<li><p><span data-ttu-id="dfafd-119">Cassetta postale</span><span class="sxs-lookup"><span data-stu-id="dfafd-119">Mailbox</span></span></p></li>
</ul>
<p><span data-ttu-id="dfafd-120">Se Microsoft Exchange Server 2013 e la messaggistica unificata di Exchange sono installati in foreste diverse, configurare ogni foresta di Exchange per considerare attendibile la foresta di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dfafd-120">If Microsoft Exchange Server 2013 and Exchange Unified Messaging (UM) are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest.</span></span></p>
<p><span data-ttu-id="dfafd-121">Se si usa Exchange 2010, installare i ruoli di Exchange Server seguenti nella stessa foresta o in un'altra foresta come Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="dfafd-121">If you are using Exchange 2010, install the following Exchange Server roles in either the same forest or a different forest as Lync Server 2013:</span></span></p>
<ul>
<li><p><span data-ttu-id="dfafd-122">Messaggistica unificata</span><span class="sxs-lookup"><span data-stu-id="dfafd-122">Unified Messaging</span></span></p></li>
<li><p><span data-ttu-id="dfafd-123">Trasporto Hub</span><span class="sxs-lookup"><span data-stu-id="dfafd-123">Hub Transport</span></span></p></li>
<li><p><span data-ttu-id="dfafd-124">Accesso client</span><span class="sxs-lookup"><span data-stu-id="dfafd-124">Client Access</span></span></p></li>
<li><p><span data-ttu-id="dfafd-125">Cassetta postale</span><span class="sxs-lookup"><span data-stu-id="dfafd-125">Mailbox</span></span></p></li>
</ul>
<p><span data-ttu-id="dfafd-126">Se Lync Server 2013 e la messaggistica unificata di Exchange sono installati in foreste diverse, configurare ogni foresta di Exchange per considerare attendibile la foresta di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dfafd-126">If Lync Server 2013 and Exchange Unified Messaging (UM) are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest.</span></span></p></td>
<td><p><span data-ttu-id="dfafd-127">Amministratori organizzazione (se si tratta del primo server di Exchange nell'organizzazione)</span><span class="sxs-lookup"><span data-stu-id="dfafd-127">Enterprise administrators (if this is the first Exchange Server in the organization)</span></span></p>
<p><span data-ttu-id="dfafd-128">O</span><span class="sxs-lookup"><span data-stu-id="dfafd-128">-OR-</span></span></p>
<p><span data-ttu-id="dfafd-129">Amministratore dell'organizzazione di Exchange (se non si tratta del primo server di Exchange nell'organizzazione)</span><span class="sxs-lookup"><span data-stu-id="dfafd-129">Exchange Organization administrator (if this is not the first Exchange Server in the organization)</span></span></p></td>
<td><p><span data-ttu-id="dfafd-130">Vedere la documentazione appropriata per la versione di Exchange Server:</span><span class="sxs-lookup"><span data-stu-id="dfafd-130">See the appropriate documentation for your version of Exchange Server:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="dfafd-131">Documentazione di distribuzione di <a href="http://go.microsoft.com/fwlink/p/?linkid=268694">http://go.microsoft.com/fwlink/p/?LinkId=268694</a>Exchange Server 2007.</span><span class="sxs-lookup"><span data-stu-id="dfafd-131">Exchange Server 2007 deployment documentation at <a href="http://go.microsoft.com/fwlink/p/?linkid=268694">http://go.microsoft.com/fwlink/p/?LinkId=268694</a>.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="dfafd-132">Exchange Server 2010 o la documentazione di distribuzione del <a href="http://go.microsoft.com/fwlink/p/?linkid=268695">http://go.microsoft.com/fwlink/p/?LinkId=268695</a>Service Pack più recente.</span><span class="sxs-lookup"><span data-stu-id="dfafd-132">Exchange Server 2010 or latest service pack deployment documentation at <a href="http://go.microsoft.com/fwlink/p/?linkid=268695">http://go.microsoft.com/fwlink/p/?LinkId=268695</a>.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="dfafd-133">Pianificazione e distribuzione di <a href="http://go.microsoft.com/fwlink/p/?linkid=266569">http://go.microsoft.com/fwlink/p/?LinkId=266569</a>Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dfafd-133">Microsoft Exchange Server 2013 Planning and Deployment at <a href="http://go.microsoft.com/fwlink/p/?linkid=266569">http://go.microsoft.com/fwlink/p/?LinkId=266569</a>.</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfafd-134">Installare i certificati.</span><span class="sxs-lookup"><span data-stu-id="dfafd-134">Install certificates.</span></span></p></td>
<td><p><span data-ttu-id="dfafd-135">Scaricare e installare certificati per ogni server Messaggistica unificata di Exchange da un'autorità di certificazione radice attendibile (CA).</span><span class="sxs-lookup"><span data-stu-id="dfafd-135">Download and install certificates for each Exchange UM server from a trusted root certificate authority (CA).</span></span> <span data-ttu-id="dfafd-136">I certificati sono necessari per la sicurezza MTLS (Mutual Transport Level Security) tra i server che usano Exchange UM e Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dfafd-136">The certificates are required for mutual Transport Level Security (MTLS) between the servers running Exchange UM and Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="dfafd-137">Gli amministratori</span><span class="sxs-lookup"><span data-stu-id="dfafd-137">Administrators</span></span></p></td>
<td><p><span data-ttu-id="dfafd-138"><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Configurare i certificati nel server in cui è in uso la messaggistica unificata di Microsoft Exchange Server</a></span><span class="sxs-lookup"><span data-stu-id="dfafd-138"><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfafd-139">Creare e configurare un nuovo dial plan di messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="dfafd-139">Create and configure a new Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="dfafd-140">Nel server Messaggistica unificata di Exchange creare un dial plan SIP basato sui requisiti di distribuzione specifici dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="dfafd-140">On the Exchange UM server, create a SIP dial plan based on your organization’s specific deployment requirements.</span></span></p></td>
<td><p><span data-ttu-id="dfafd-141">Amministratore dell'organizzazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="dfafd-141">Exchange Organization administrator</span></span></p></td>
<td><p><span data-ttu-id="dfafd-142">Per Exchange 2007 SP1 o Service Pack più recente, &quot;vedere come creare un dial plan&quot; URI SIP di messaggistica unificata <a href="http://go.microsoft.com/fwlink/p/?linkid=268632">http://go.microsoft.com/fwlink/p/?linkId=268632</a>.</span><span class="sxs-lookup"><span data-stu-id="dfafd-142">For Exchange 2007 SP1 or latest service pack, see &quot;How to Create a Unified Messaging SIP URI Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268632">http://go.microsoft.com/fwlink/p/?linkId=268632</a>.</span></span></p>
<p><span data-ttu-id="dfafd-143">Per Exchange 2010 o Service Pack più recente, &quot;vedere creare un dial plan&quot; di <a href="http://go.microsoft.com/fwlink/p/?linkid=268674">http://go.microsoft.com/fwlink/p/?linkId=268674</a>messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="dfafd-143">For Exchange 2010 or latest service pack, see &quot;Create a UM Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268674">http://go.microsoft.com/fwlink/p/?linkId=268674</a>.</span></span></p>
<p><span data-ttu-id="dfafd-144">Per Exchange 2013, vedere Messaggistica unificata <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span><span class="sxs-lookup"><span data-stu-id="dfafd-144">For Exchange 2013, see Unified Messaging at <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfafd-145">Configurare le impostazioni di sicurezza per il dial plan di messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="dfafd-145">Configure security settings for the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="dfafd-146">Per crittografare il traffico VoIP aziendale, configurare le impostazioni di sicurezza nel dial plan di messaggistica unificata di Exchange come <strong>protetto tramite SIP</strong> o <strong>protetto</strong>.</span><span class="sxs-lookup"><span data-stu-id="dfafd-146">To encrypt Enterprise Voice traffic, configure the security settings on the Exchange UM SIP dial plan as <strong>SIP Secured</strong> or <strong>Secured</strong>.</span></span> <span data-ttu-id="dfafd-147">Si tratta di un passaggio particolarmente importante se si è distribuito o si prevede di distribuire i dispositivi Lync Phone Edition nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="dfafd-147">This is an especially important step if you have deployed or plan to deploy Lync Phone Edition devices in your environment.</span></span> <span data-ttu-id="dfafd-148">Per i dispositivi Lync Phone Edition per funzionare in un ambiente con integrazione di messaggistica unificata di Exchange, le impostazioni di crittografia di Lync Server devono essere allineate alle impostazioni di sicurezza del dial plan di Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="dfafd-148">For Lync Phone Edition devices to function in an environment with Exchange UM integration, Lync Server encryption settings must align with the Exchange UM dial plan security settings.</span></span> <span data-ttu-id="dfafd-149">Per informazioni dettagliate, vedere la documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="dfafd-149">For details, refer to the Deployment documentation.</span></span></p></td>
<td><p><span data-ttu-id="dfafd-150">Amministratore dell'organizzazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="dfafd-150">Exchange Organization administrator</span></span></p></td>
<td><p><span data-ttu-id="dfafd-151"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configurare la messaggistica unificata in Microsoft Exchange per Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="dfafd-151"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="dfafd-152">Per Exchange 2007 SP1 o Service Pack più recente, vedere anche:</span><span class="sxs-lookup"><span data-stu-id="dfafd-152">For Exchange 2007 SP1 or latest service pack, see also:</span></span></p>
<p><span data-ttu-id="dfafd-153">&quot;Come configurare la sicurezza in un dial plan&quot; di <a href="http://go.microsoft.com/fwlink/p/?linkid=268696">http://go.microsoft.com/fwlink/p/?LinkId=268696</a>messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="dfafd-153">&quot;How to Configure Security on a Unified Messaging Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268696">http://go.microsoft.com/fwlink/p/?LinkId=268696</a>.</span></span></p>
<p><span data-ttu-id="dfafd-154">Per Exchange 2010 o Service Pack più recente, vedere anche:</span><span class="sxs-lookup"><span data-stu-id="dfafd-154">For Exchange 2010 or latest service pack, see also:</span></span></p>
<p><span data-ttu-id="dfafd-155">&quot;Configurare la sicurezza VoIP in un dial plan&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=268697">http://go.microsoft.com/fwlink/p/?LinkId=268697</a>di messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="dfafd-155">&quot;Configure VoIP Security on a UM Dial Plan&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=268697">http://go.microsoft.com/fwlink/p/?LinkId=268697</a>.</span></span></p>
<p><span data-ttu-id="dfafd-156">Per Exchange 2013, vedere Messaggistica unificata <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span><span class="sxs-lookup"><span data-stu-id="dfafd-156">For Exchange 2013, see Unified Messaging at <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfafd-157">Aggiungere server di messaggistica unificata al dial plan di messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="dfafd-157">Add Unified Messaging servers to the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="dfafd-158">Per abilitare un server di messaggistica unificata appena installato per rispondere ed elaborare le chiamate in arrivo, è necessario aggiungere il server Messaggistica unificata a un dial plan di messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="dfafd-158">To enable a newly installed Unified Messaging server to answer and process incoming calls, you must add the Unified Messaging server to a UM dial plan.</span></span> <span data-ttu-id="dfafd-159">In questo caso, aggiungere il server al dial plan di messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="dfafd-159">In this case, add the server to the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="dfafd-160">Gli amministratori</span><span class="sxs-lookup"><span data-stu-id="dfafd-160">Administrators</span></span></p>
<p><span data-ttu-id="dfafd-161">Amministratori di Exchange Server</span><span class="sxs-lookup"><span data-stu-id="dfafd-161">Exchange Server administrators</span></span></p></td>
<td><p><span data-ttu-id="dfafd-162">Per Exchange 2007 SP1 o Service Pack più recente, &quot;vedere come aggiungere un server di messaggistica unificata a un&quot; Dial <a href="http://go.microsoft.com/fwlink/p/?linkid=268681">http://go.microsoft.com/fwlink/p/?linkId=268681</a>Plan.</span><span class="sxs-lookup"><span data-stu-id="dfafd-162">For Exchange 2007 SP1 or latest service pack, see &quot;How to Add Unified Messaging Server to a Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268681">http://go.microsoft.com/fwlink/p/?linkId=268681</a>.</span></span></p>
<p><span data-ttu-id="dfafd-163">Per Exchange 2010 o Service Pack più recente, &quot;vedere visualizzare o configurare le proprietà di un server&quot; messaggistica <a href="http://go.microsoft.com/fwlink/p/?linkid=268682">http://go.microsoft.com/fwlink/p/?linkId=268682</a>unificata.</span><span class="sxs-lookup"><span data-stu-id="dfafd-163">For Exchange 2010 or latest service pack, see &quot;View or Configure the Properties of a UM Server&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268682">http://go.microsoft.com/fwlink/p/?linkId=268682</a>.</span></span></p>
<p><span data-ttu-id="dfafd-164">Per Exchange 2013, vedere Messaggistica unificata <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span><span class="sxs-lookup"><span data-stu-id="dfafd-164">For Exchange 2013, see Unified Messaging at <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfafd-165">Configurare le cassette postali con indirizzi SIP.</span><span class="sxs-lookup"><span data-stu-id="dfafd-165">Configure mailboxes with SIP addresses.</span></span></p></td>
<td><p><span data-ttu-id="dfafd-166">Assegna indirizzi SIP alle cassette postali degli utenti di VoIP aziendale che utilizzeranno le funzionalità di messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="dfafd-166">Assign SIP addresses to the mailboxes of Enterprise Voice users who will be using Exchange UM features.</span></span></p></td>
<td><p><span data-ttu-id="dfafd-167">Amministratore di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfafd-167">Lync Server 2013 administrator</span></span></p>
<p><span data-ttu-id="dfafd-168">Amministratore del destinatario di Exchange</span><span class="sxs-lookup"><span data-stu-id="dfafd-168">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="dfafd-169">Per Exchange 2007 SP1 o Service Pack più recente, &quot;vedere come aggiungere, rimuovere o modificare un indirizzo SIP per un utente&quot; abilitato alla <a href="http://go.microsoft.com/fwlink/p/?linkid=268698">http://go.microsoft.com/fwlink/p/?LinkId=268698</a>messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="dfafd-169">For Exchange 2007 SP1 or latest service pack, see &quot;How to Add, Remove, or Modify a SIP Address for a UM-Enabled User&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268698">http://go.microsoft.com/fwlink/p/?LinkId=268698</a>.</span></span></p>
<p><span data-ttu-id="dfafd-170">Per Exchange 2010 o Service Pack più recente, &quot;vedere Modificare un indirizzo SIP per un utente&quot; abilitato alla <a href="http://go.microsoft.com/fwlink/p/?linkid=268699">http://go.microsoft.com/fwlink/p/?LinkId=268699</a>messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="dfafd-170">For Exchange 2010 or latest service pack, see &quot;Modify a SIP Address for a UM-Enabled User&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268699">http://go.microsoft.com/fwlink/p/?LinkId=268699</a>.</span></span></p>
<p><span data-ttu-id="dfafd-171">Per Exchange 2013, vedere Messaggistica unificata <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span><span class="sxs-lookup"><span data-stu-id="dfafd-171">For Exchange 2013, see Unified Messaging at <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfafd-172">Eseguire lo script exchucutil. ps1.</span><span class="sxs-lookup"><span data-stu-id="dfafd-172">Run the exchucutil.ps1 script.</span></span></p></td>
<td><p><span data-ttu-id="dfafd-173">Nel server che esegue i servizi di messaggistica unificata di Exchange aprire Exchange Management Shell ed eseguire lo script exchucutil. ps1, che esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dfafd-173">On the server running Exchange UM services, open the Exchange Management Shell and run the exchucutil.ps1 script, which does the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="dfafd-174">Concede l'autorizzazione Lync Server 2013 per la lettura degli oggetti servizi di dominio Active Directory UM di Exchange, in particolare i dial plan SIP creati nell'attività precedente.</span><span class="sxs-lookup"><span data-stu-id="dfafd-174">Grants Lync Server 2013 permission to read Exchange UM Active Directory Domain Services objects, specifically, the SIP dial plans created in the previous task.</span></span></p></li>
<li><p><span data-ttu-id="dfafd-175">Crea un oggetto gateway IP di messaggistica unificata in Active Directory per ogni pool di Lync Server 2013 Enterprise Edition o un server Standard Edition che ospita gli utenti abilitati per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="dfafd-175">Creates a Unified Messaging IP gateway object in Active Directory for each Lync Server 2013 Enterprise Edition pool or Standard Edition server that hosts users who are enabled for Enterprise Voice.</span></span></p></li>
<li><p><span data-ttu-id="dfafd-176">Crea un gruppo di ricerca di messaggistica unificata di Exchange per ogni gateway.</span><span class="sxs-lookup"><span data-stu-id="dfafd-176">Creates an Exchange UM hunt group for each gateway.</span></span> <span data-ttu-id="dfafd-177">L'identificatore pilota del gruppo cerca sarà il nome del dial plan associato al gateway corrispondente.</span><span class="sxs-lookup"><span data-stu-id="dfafd-177">The hunt group pilot identifier will be the name of the dial plan that is associated with the corresponding gateway.</span></span> <span data-ttu-id="dfafd-178">Questi devono essere mappati a 1:1 se sono presenti più dial plan.</span><span class="sxs-lookup"><span data-stu-id="dfafd-178">These need to be mapped 1:1 if there is more than one dial plan.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="dfafd-179">Amministratore dell'organizzazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="dfafd-179">Exchange Organization administrator</span></span></p>
<p><span data-ttu-id="dfafd-180">Amministratore del destinatario di Exchange</span><span class="sxs-lookup"><span data-stu-id="dfafd-180">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="dfafd-181"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configurare la messaggistica unificata in Microsoft Exchange per Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="dfafd-181"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfafd-182">Configurare i dial plan di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dfafd-182">Configure Lync Server 2013 dial plans.</span></span></p></td>
<td><p><span data-ttu-id="dfafd-183">Se si esegue l'integrazione con Exchange 2007 SP1 o un Service Pack più recente o Exchange 2010, creare un nuovo piano VoIP aziendale con un nome che corrisponda al nome di dominio completo (FQDN) di Exchange UM dial plan.</span><span class="sxs-lookup"><span data-stu-id="dfafd-183">If you are integrating with Exchange 2007 SP1 or latest service pack, or Exchange 2010, create a new Enterprise Voice dial plan with a name that matches the Exchange UM dial plan fully qualified domain name (FQDN).</span></span></p>



> [!NOTE]
> <span data-ttu-id="dfafd-184">Sarà necessario eseguire questa operazione per ogni dial plan di messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="dfafd-184">You will need to do this for each UM Dial plan.</span></span>


<p><span data-ttu-id="dfafd-185">Se si esegue l'integrazione con Exchange 2010 SP1, verificare che siano stati configurati piani di dial-up aziendali a livello globale/sito o a livello di pool.</span><span class="sxs-lookup"><span data-stu-id="dfafd-185">If you are integrating with Exchange 2010 SP1, ensure that suitable global/site-level or pool-level Enterprise Voice dial plans have been configured.</span></span></p>



> [!NOTE]
> <span data-ttu-id="dfafd-186">Se si esegue l'integrazione con Exchange 2010 SP1, non è necessario che il dial plan di Lync Server e i nomi di dial plan di messaggistica unificata di Exchange non corrispondano.</span><span class="sxs-lookup"><span data-stu-id="dfafd-186">If you are integrating with Exchange 2010 SP1, the Lync Server dial plan and Exchange UM SIP dial plan names do not need to match.</span></span>

</td>
<td><p><span data-ttu-id="dfafd-187">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="dfafd-187">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="dfafd-188"><a href="lync-server-2013-configuring-dial-plans.md">Configurazione dei dial plan in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="dfafd-188"><a href="lync-server-2013-configuring-dial-plans.md">Configuring dial plans in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfafd-189">Eseguire lo strumento di integrazione della messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="dfafd-189">Run the Exchange UM Integration tool.</span></span></p></td>
<td><p><span data-ttu-id="dfafd-190">In Lync Server 2013 eseguire <strong>OcsUmUtil. exe</strong>, che:</span><span class="sxs-lookup"><span data-stu-id="dfafd-190">On the Lync Server 2013, run <strong>ocsumutil.exe</strong>, which:</span></span></p>
<ul>
<li><p><span data-ttu-id="dfafd-191">Crea gli oggetti contatto accesso sottoscrittore e operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="dfafd-191">Creates Subscriber Access and Auto Attendant contact objects.</span></span></p></li>
<li><p><span data-ttu-id="dfafd-192">Verifica che sia presente un piano di chiamata VoIP aziendale con un nome corrispondente all'FQDN di Exchange dial plan di messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="dfafd-192">Validates that there is an Enterprise Voice dial plan with a name that matches the Exchange UM dial plan FQDN.</span></span> <span data-ttu-id="dfafd-193">Se si esegue Exchange 2010 SP1 o versione successiva, non è necessario che i nomi dei dial plan corrispondano e si possa ignorare l'avviso dello strumento.</span><span class="sxs-lookup"><span data-stu-id="dfafd-193">If you are running Exchange 2010 SP1 or later, the dial plan names do not need to match, and you can ignore the tool’s warning about this.</span></span></p></li>
</ul>
<p><span data-ttu-id="dfafd-194">Questo strumento analizza le impostazioni della messaggistica unificata di Exchange in Active Directory e consente all'amministratore di Lync Server 2013 di visualizzare, creare e modificare oggetti contatto.</span><span class="sxs-lookup"><span data-stu-id="dfafd-194">This tool works by scanning the Active Directory for Exchange UM settings and allowing the Lync Server 2013 administrator to view, create, and edit contact objects.</span></span></p></td>
<td><p><span data-ttu-id="dfafd-195">RTCUniversalServerAdmins <em>e</em> RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="dfafd-195">RTCUniversalServerAdmins <em>and</em> RTCUniversalUserAdmins</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="dfafd-196">Per eseguire correttamente OcsUmUtil. exe, l'utente deve appartenere a entrambi questi gruppi.</span><span class="sxs-lookup"><span data-stu-id="dfafd-196">To run ocsumutil.exe successfully, the user must belong to both of these groups.</span></span>





> [!NOTE]
> <span data-ttu-id="dfafd-197">Per creare oggetti contatto, l'utente che esegue OcsUmUtil. exe deve avere l'autorizzazione corretta per l'unità organizzativa Active Directory in cui sono archiviati i nuovi oggetti contatto.</span><span class="sxs-lookup"><span data-stu-id="dfafd-197">To create Contact objects, the user who runs ocsumutil.exe must have the correct permission to the Active Directory organizational unit (OU) where the new contact objects are stored.</span></span> <span data-ttu-id="dfafd-198">Questa autorizzazione può essere concessa eseguendo il cmdlet <STRONG>Grant-CsOUPermission</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="dfafd-198">This permission can be granted by running the <STRONG>Grant-CsOUPermission</STRONG> cmdlet.</span></span> <span data-ttu-id="dfafd-199">Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="dfafd-199">For details, see the Lync Server Management Shell documentation.</span></span>

</td>
<td><p><span data-ttu-id="dfafd-200"><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Configurare Lync Server 2013 per l'utilizzo della messaggistica unificata in Microsoft Exchange Server</a></span><span class="sxs-lookup"><span data-stu-id="dfafd-200"><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfafd-201">Se necessario, eseguire altre operazioni di configurazione VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="dfafd-201">If necessary, perform other Enterprise Voice configuration steps.</span></span></p></td>
<td><p><span data-ttu-id="dfafd-202">Se non sono già state configurate le impostazioni vocali aziendali nei server o negli utenti, eseguire una o più delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dfafd-202">If you have not already configured Enterprise Voice settings on your servers or users, do one or more of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="dfafd-203">Distribuire e configurare</span><span class="sxs-lookup"><span data-stu-id="dfafd-203">Deploy and configure</span></span></p>
<p><span data-ttu-id="dfafd-204">Gateway PSTN (Public Switched Telephone Network) e Mediation Server</span><span class="sxs-lookup"><span data-stu-id="dfafd-204">Public switched telephone network (PSTN) gateways and Mediation Servers</span></span></p></li>
<li><p><span data-ttu-id="dfafd-205">Definire i criteri vocali, i record di utilizzo PSTN e le route di chiamata in uscita.</span><span class="sxs-lookup"><span data-stu-id="dfafd-205">Define voice policies, PSTN usage records, and outbound call routes.</span></span></p></li>
<li><p><span data-ttu-id="dfafd-206">Consentire agli utenti di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="dfafd-206">Enable users for Enterprise Voice.</span></span></p></li>
<li><p><span data-ttu-id="dfafd-207">Facoltativamente, configurare utenti specifici con dial plan.</span><span class="sxs-lookup"><span data-stu-id="dfafd-207">Optionally, configure specific users with dial plans.</span></span></p></li>
</ul>
<p><span data-ttu-id="dfafd-208">Altre operazioni di configurazione possono essere necessarie in base alle funzionalità vocali aziendali abilitate.</span><span class="sxs-lookup"><span data-stu-id="dfafd-208">Other configuration steps may be required depending on the Enterprise Voice features that you enable.</span></span></p></td>
<td><p><span data-ttu-id="dfafd-209">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="dfafd-209">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="dfafd-210">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="dfafd-210">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="dfafd-211">Vedere gli argomenti nelle sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dfafd-211">See topics in the following sections:</span></span></p>
<ul>
<li><p><span data-ttu-id="dfafd-212"><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Configurazione dei criteri vocali, dei record di utilizzo PSTN e delle route vocali in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="dfafd-212"><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="dfafd-213"><a href="lync-server-2013-deploying-enterprise-voice.md">Distribuzione di VoIP aziendale in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="dfafd-213"><a href="lync-server-2013-deploying-enterprise-voice.md">Deploying Enterprise Voice in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfafd-214">Abilitare gli utenti di VoIP aziendale per la messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="dfafd-214">Enable Enterprise Voice users for Exchange UM.</span></span></p></td>
<td><p><span data-ttu-id="dfafd-215">Nel server Messaggistica unificata di Exchange verificare che sia stato creato un criterio cassetta postale di messaggistica unificata e che ogni utente disponga di un'assegnazione di numero di interno univoco e quindi abilitare l'utente per la messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="dfafd-215">On the Exchange UM server, ensure that a Unified Messaging mailbox policy has been created and that each user has a unique extension number assignment, and then enable the user for Unified Messaging.</span></span></p></td>
<td><p><span data-ttu-id="dfafd-216">Amministratore del destinatario di Exchange</span><span class="sxs-lookup"><span data-stu-id="dfafd-216">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="dfafd-217">Per Exchange 2007 SP1 o Service Pack più recente, &quot;vedere come abilitare un utente per la messaggistica&quot; unificata <a href="http://go.microsoft.com/fwlink/p/?linkid=268700">http://go.microsoft.com/fwlink/p/?LinkId=268700</a>.</span><span class="sxs-lookup"><span data-stu-id="dfafd-217">For Exchange 2007 SP1 or latest service pack, see &quot;How to Enable a User for Unified Messaging&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268700">http://go.microsoft.com/fwlink/p/?LinkId=268700</a>.</span></span></p>
<p><span data-ttu-id="dfafd-218">Per Exchange 2010 o Service Pack più recente, &quot;vedere Abilitare un utente per la messaggistica&quot; unificata <a href="http://go.microsoft.com/fwlink/p/?linkid=268701">http://go.microsoft.com/fwlink/p/?LinkId=268701</a>.</span><span class="sxs-lookup"><span data-stu-id="dfafd-218">For Exchange 2010 or latest service pack, see &quot;Enable a User for Unified Messaging&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268701">http://go.microsoft.com/fwlink/p/?LinkId=268701</a>.</span></span></p>
<p><span data-ttu-id="dfafd-219">Per Exchange 2013, vedere Messaggistica unificata <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span><span class="sxs-lookup"><span data-stu-id="dfafd-219">For Exchange 2013, see Unified Messaging at <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


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
ms.openlocfilehash: d6d60b120db57ad73c33e682fa8150e99f5606e3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137165"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="c864a-102">Processo di distribuzione per l'integrazione della messaggistica unificata locale e di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c864a-102">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c864a-103">_**Ultimo argomento modificato:** 2012-12-17_</span><span class="sxs-lookup"><span data-stu-id="c864a-103">_**Topic Last Modified:** 2012-12-17_</span></span>

<span data-ttu-id="c864a-104">Se si desidera integrare la messaggistica unificata di Exchange con Lync Server 2013, è necessario eseguire le attività descritte in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="c864a-104">If you want to integrate Exchange Unified Messaging (UM) with Lync Server 2013, you must perform the tasks described in this topic.</span></span> <span data-ttu-id="c864a-105">È inoltre necessario esaminare le procedure consigliate per la pianificazione e la distribuzione descritte in [linee guida per l'integrazione della messaggistica unificata locale e di Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md).</span><span class="sxs-lookup"><span data-stu-id="c864a-105">Also be sure that you review the planning and deployment best practices described in [Guidelines for integrating on-premises Unified Messaging and Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md).</span></span> <span data-ttu-id="c864a-106">In questo argomento si presuppone che sia stato distribuito Lync Server 2013 con un Mediation Server collocato e che siano stati abilitati gli utenti per Lync Server 2013, ma non necessariamente che siano stati eseguiti tutti i passaggi di distribuzione e configurazione per abilitare VoIP aziendale, come descritto in [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c864a-106">This topic assumes that you have deployed Lync Server 2013 with a collocated Mediation Server and that you have enabled users for Lync Server 2013, but not necessarily that you have performed all deployment and configuration steps to enable Enterprise Voice, as described in [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span>

<div>

## <a name="unified-messaging-integration-process"></a><span data-ttu-id="c864a-107">Processo di integrazione di messaggistica unificata</span><span class="sxs-lookup"><span data-stu-id="c864a-107">Unified Messaging Integration Process</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="c864a-108">È importante coordinarsi con gli amministratori di Exchange dell'organizzazione per confermare le attività che ognuno di voi eseguirà per garantire un'integrazione agevole e corretta.</span><span class="sxs-lookup"><span data-stu-id="c864a-108">It is important that you coordinate with your organization’s Exchange administrators to confirm the tasks that each of you will perform to help ensure a smooth, successful integration.</span></span>



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
<th><span data-ttu-id="c864a-109">Fase</span><span class="sxs-lookup"><span data-stu-id="c864a-109">Phase</span></span></th>
<th><span data-ttu-id="c864a-110">Passaggi</span><span class="sxs-lookup"><span data-stu-id="c864a-110">Steps</span></span></th>
<th><span data-ttu-id="c864a-111">Gruppi e ruoli obbligatori</span><span class="sxs-lookup"><span data-stu-id="c864a-111">Required groups and roles</span></span></th>
<th><span data-ttu-id="c864a-112">Documentazione sulla distribuzione</span><span class="sxs-lookup"><span data-stu-id="c864a-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c864a-113">Distribuire uno dei prodotti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c864a-113">Deploy one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c864a-114">Microsoft Exchange Server 2007 Service Pack 1 (SP2) o Service Pack più recente</span><span class="sxs-lookup"><span data-stu-id="c864a-114">Microsoft Exchange Server 2007 Service Pack 1 (SP2) or latest service pack</span></span></p></li>
<li><p><span data-ttu-id="c864a-115">Microsoft Exchange Server 2010 o Service Pack più recente</span><span class="sxs-lookup"><span data-stu-id="c864a-115">Microsoft Exchange Server 2010 or latest service pack</span></span></p></li>
<li><p><span data-ttu-id="c864a-116">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="c864a-116">Microsoft Exchange Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c864a-117">Se si utilizza Microsoft Exchange Server 2013, installare i seguenti ruoli del server Exchange nella stessa foresta o in una foresta diversa come Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="c864a-117">If you are using Microsoft Exchange Server 2013, install the following Exchange Server roles in either the same forest or a different forest as Lync Server 2013:</span></span></p>
<ul>
<li><p><span data-ttu-id="c864a-118">Accesso client</span><span class="sxs-lookup"><span data-stu-id="c864a-118">Client Access</span></span></p></li>
<li><p><span data-ttu-id="c864a-119">Cassetta postale</span><span class="sxs-lookup"><span data-stu-id="c864a-119">Mailbox</span></span></p></li>
</ul>
<p><span data-ttu-id="c864a-120">Se Microsoft Exchange Server 2013 e la messaggistica unificata di Exchange vengono installati in foreste diverse, configurare ogni foresta di Exchange in modo che consideri attendibile la foresta di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c864a-120">If Microsoft Exchange Server 2013 and Exchange Unified Messaging (UM) are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest.</span></span></p>
<p><span data-ttu-id="c864a-121">Se si utilizza Exchange 2010, installare i seguenti ruoli del server Exchange nella stessa foresta o in una foresta diversa come Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="c864a-121">If you are using Exchange 2010, install the following Exchange Server roles in either the same forest or a different forest as Lync Server 2013:</span></span></p>
<ul>
<li><p><span data-ttu-id="c864a-122">Messaggistica unificata</span><span class="sxs-lookup"><span data-stu-id="c864a-122">Unified Messaging</span></span></p></li>
<li><p><span data-ttu-id="c864a-123">Trasporto Hub</span><span class="sxs-lookup"><span data-stu-id="c864a-123">Hub Transport</span></span></p></li>
<li><p><span data-ttu-id="c864a-124">Accesso client</span><span class="sxs-lookup"><span data-stu-id="c864a-124">Client Access</span></span></p></li>
<li><p><span data-ttu-id="c864a-125">Cassetta postale</span><span class="sxs-lookup"><span data-stu-id="c864a-125">Mailbox</span></span></p></li>
</ul>
<p><span data-ttu-id="c864a-126">Se Lync Server 2013 e la messaggistica unificata di Exchange sono installati in foreste diverse, configurare ogni foresta di Exchange in modo che consideri attendibile la foresta di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c864a-126">If Lync Server 2013 and Exchange Unified Messaging (UM) are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest.</span></span></p></td>
<td><p><span data-ttu-id="c864a-127">Amministratori dell'organizzazione (se è il primo Exchange Server dell'organizzazione)</span><span class="sxs-lookup"><span data-stu-id="c864a-127">Enterprise administrators (if this is the first Exchange Server in the organization)</span></span></p>
<p><span data-ttu-id="c864a-128">-O-</span><span class="sxs-lookup"><span data-stu-id="c864a-128">-OR-</span></span></p>
<p><span data-ttu-id="c864a-129">Amministratore dell'organizzazione di Exchange (se non è il primo Exchange Server dell'organizzazione)</span><span class="sxs-lookup"><span data-stu-id="c864a-129">Exchange Organization administrator (if this is not the first Exchange Server in the organization)</span></span></p></td>
<td><p><span data-ttu-id="c864a-130">Per informazioni sulla versione di Exchange di cui si dispone, vedere la documentazione appropriata:</span><span class="sxs-lookup"><span data-stu-id="c864a-130">See the appropriate documentation for your version of Exchange Server:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c864a-131">Documentazione relativa alla distribuzione di Exchange <a href="https://go.microsoft.com/fwlink/p/?linkid=268694">https://go.microsoft.com/fwlink/p/?LinkId=268694</a>Server 2007 all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="c864a-131">Exchange Server 2007 deployment documentation at <a href="https://go.microsoft.com/fwlink/p/?linkid=268694">https://go.microsoft.com/fwlink/p/?LinkId=268694</a>.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c864a-132">Documentazione relativa alla distribuzione del Service Pack di <a href="https://go.microsoft.com/fwlink/p/?linkid=268695">https://go.microsoft.com/fwlink/p/?LinkId=268695</a>Exchange Server 2010 o versione più recente.</span><span class="sxs-lookup"><span data-stu-id="c864a-132">Exchange Server 2010 or latest service pack deployment documentation at <a href="https://go.microsoft.com/fwlink/p/?linkid=268695">https://go.microsoft.com/fwlink/p/?LinkId=268695</a>.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c864a-133">Microsoft Exchange Server 2013 pianificazione e distribuzione in <a href="https://go.microsoft.com/fwlink/p/?linkid=266569">https://go.microsoft.com/fwlink/p/?LinkId=266569</a>.</span><span class="sxs-lookup"><span data-stu-id="c864a-133">Microsoft Exchange Server 2013 Planning and Deployment at <a href="https://go.microsoft.com/fwlink/p/?linkid=266569">https://go.microsoft.com/fwlink/p/?LinkId=266569</a>.</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c864a-134">Installare i certificati.</span><span class="sxs-lookup"><span data-stu-id="c864a-134">Install certificates.</span></span></p></td>
<td><p><span data-ttu-id="c864a-135">Scaricare e installare i certificati per ogni server Messaggistica unificata di Exchange da un'autorità di certificazione (CA) radice attendibile.</span><span class="sxs-lookup"><span data-stu-id="c864a-135">Download and install certificates for each Exchange UM server from a trusted root certificate authority (CA).</span></span> <span data-ttu-id="c864a-136">I certificati sono necessari per la sicurezza MTLS (Mutual Transport Level Security) tra i server che eseguono la messaggistica unificata di Exchange e Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c864a-136">The certificates are required for mutual Transport Level Security (MTLS) between the servers running Exchange UM and Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="c864a-137">Amministratori</span><span class="sxs-lookup"><span data-stu-id="c864a-137">Administrators</span></span></p></td>
<td><p><span data-ttu-id="c864a-138"><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Configurare i certificati nel server che esegue la messaggistica unificata di Microsoft Exchange Server</a></span><span class="sxs-lookup"><span data-stu-id="c864a-138"><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c864a-139">Creare e configurare un nuovo dial plan SIP di messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="c864a-139">Create and configure a new Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="c864a-140">Nel server Messaggistica unificata di Exchange, creare un dial plan SIP in base ai requisiti di distribuzione specifici dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c864a-140">On the Exchange UM server, create a SIP dial plan based on your organization’s specific deployment requirements.</span></span></p></td>
<td><p><span data-ttu-id="c864a-141">Amministratore dell'organizzazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="c864a-141">Exchange Organization administrator</span></span></p></td>
<td><p><span data-ttu-id="c864a-142">Per Exchange 2007 SP1 o Service Pack più recente, &quot;vedere come creare un dial plan&quot; URI SIP di messaggistica unificata <a href="https://go.microsoft.com/fwlink/p/?linkid=268632">https://go.microsoft.com/fwlink/p/?linkId=268632</a>in.</span><span class="sxs-lookup"><span data-stu-id="c864a-142">For Exchange 2007 SP1 or latest service pack, see &quot;How to Create a Unified Messaging SIP URI Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268632">https://go.microsoft.com/fwlink/p/?linkId=268632</a>.</span></span></p>
<p><span data-ttu-id="c864a-143">Per Exchange 2010 o Service Pack più recente, &quot;vedere creare un dial plan&quot; di <a href="https://go.microsoft.com/fwlink/p/?linkid=268674">https://go.microsoft.com/fwlink/p/?linkId=268674</a>messaggistica unificata in.</span><span class="sxs-lookup"><span data-stu-id="c864a-143">For Exchange 2010 or latest service pack, see &quot;Create a UM Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268674">https://go.microsoft.com/fwlink/p/?linkId=268674</a>.</span></span></p>
<p><span data-ttu-id="c864a-144">Per Exchange 2013, vedere Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span><span class="sxs-lookup"><span data-stu-id="c864a-144">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c864a-145">Configurare le impostazioni di protezione per il dial plan SIP di messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="c864a-145">Configure security settings for the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="c864a-146">Per crittografare il traffico VoIP aziendale, configurare le impostazioni di sicurezza nel dial plan SIP di messaggistica unificata di Exchange come <strong>SIP</strong> con protezione o <strong>protetto</strong>.</span><span class="sxs-lookup"><span data-stu-id="c864a-146">To encrypt Enterprise Voice traffic, configure the security settings on the Exchange UM SIP dial plan as <strong>SIP Secured</strong> or <strong>Secured</strong>.</span></span> <span data-ttu-id="c864a-147">Questo è un passaggio particolarmente importante se è stato distribuito o si intende distribuire i dispositivi Lync Phone Edition nell'ambiente in uso.</span><span class="sxs-lookup"><span data-stu-id="c864a-147">This is an especially important step if you have deployed or plan to deploy Lync Phone Edition devices in your environment.</span></span> <span data-ttu-id="c864a-148">Affinché i dispositivi Lync Phone Edition funzionino in un ambiente con integrazione di messaggistica unificata di Exchange, le impostazioni di crittografia di Lync Server devono essere allineate alle impostazioni di protezione di messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="c864a-148">For Lync Phone Edition devices to function in an environment with Exchange UM integration, Lync Server encryption settings must align with the Exchange UM dial plan security settings.</span></span> <span data-ttu-id="c864a-149">Per informazioni dettagliate, vedere la documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c864a-149">For details, refer to the Deployment documentation.</span></span></p></td>
<td><p><span data-ttu-id="c864a-150">Amministratore dell'organizzazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="c864a-150">Exchange Organization administrator</span></span></p></td>
<td><p><span data-ttu-id="c864a-151"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configurare la messaggistica unificata in Microsoft Exchange per Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c864a-151"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="c864a-152">Per Exchange 2007 SP1 o Service Pack più recente, vedere anche:</span><span class="sxs-lookup"><span data-stu-id="c864a-152">For Exchange 2007 SP1 or latest service pack, see also:</span></span></p>
<p><span data-ttu-id="c864a-153">&quot;Informazioni su come configurare la sicurezza in un dial plan&quot; di messaggistica <a href="https://go.microsoft.com/fwlink/p/?linkid=268696">https://go.microsoft.com/fwlink/p/?LinkId=268696</a>unificata in.</span><span class="sxs-lookup"><span data-stu-id="c864a-153">&quot;How to Configure Security on a Unified Messaging Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268696">https://go.microsoft.com/fwlink/p/?LinkId=268696</a>.</span></span></p>
<p><span data-ttu-id="c864a-154">Per Exchange 2010 o Service Pack più recente, vedere anche:</span><span class="sxs-lookup"><span data-stu-id="c864a-154">For Exchange 2010 or latest service pack, see also:</span></span></p>
<p><span data-ttu-id="c864a-155">&quot;Configurare la sicurezza VoIP su un dial plan&quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268697">https://go.microsoft.com/fwlink/p/?LinkId=268697</a>di messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="c864a-155">&quot;Configure VoIP Security on a UM Dial Plan&quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268697">https://go.microsoft.com/fwlink/p/?LinkId=268697</a>.</span></span></p>
<p><span data-ttu-id="c864a-156">Per Exchange 2013, vedere Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span><span class="sxs-lookup"><span data-stu-id="c864a-156">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c864a-157">Aggiungere i server Messaggistica unificata al dial plan SIP di messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="c864a-157">Add Unified Messaging servers to the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="c864a-158">Per consentire a un server di Messaggistica unificata appena installato di rispondere alle chiamate in arrivo e di elaborarle, è necessario aggiungere il server di Messaggistica unificata a un dial plan di Messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="c864a-158">To enable a newly installed Unified Messaging server to answer and process incoming calls, you must add the Unified Messaging server to a UM dial plan.</span></span> <span data-ttu-id="c864a-159">In questo caso, aggiungere il server al dial plan SIP di messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="c864a-159">In this case, add the server to the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="c864a-160">Amministratori</span><span class="sxs-lookup"><span data-stu-id="c864a-160">Administrators</span></span></p>
<p><span data-ttu-id="c864a-161">Amministratori di Exchange Server</span><span class="sxs-lookup"><span data-stu-id="c864a-161">Exchange Server administrators</span></span></p></td>
<td><p><span data-ttu-id="c864a-162">Per Exchange 2007 SP1 o Service Pack più recente, &quot;vedere come aggiungere il server Messaggistica unificata a un dial&quot; Plan <a href="https://go.microsoft.com/fwlink/p/?linkid=268681">https://go.microsoft.com/fwlink/p/?linkId=268681</a>all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="c864a-162">For Exchange 2007 SP1 or latest service pack, see &quot;How to Add Unified Messaging Server to a Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268681">https://go.microsoft.com/fwlink/p/?linkId=268681</a>.</span></span></p>
<p><span data-ttu-id="c864a-163">Per Exchange 2010 o Service Pack più recente, &quot;vedere Visualizzazione o configurazione delle proprietà di un server&quot; di <a href="https://go.microsoft.com/fwlink/p/?linkid=268682">https://go.microsoft.com/fwlink/p/?linkId=268682</a>messaggistica unificata in.</span><span class="sxs-lookup"><span data-stu-id="c864a-163">For Exchange 2010 or latest service pack, see &quot;View or Configure the Properties of a UM Server&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268682">https://go.microsoft.com/fwlink/p/?linkId=268682</a>.</span></span></p>
<p><span data-ttu-id="c864a-164">Per Exchange 2013, vedere Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span><span class="sxs-lookup"><span data-stu-id="c864a-164">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c864a-165">Configurare cassette postali con indirizzi SIP</span><span class="sxs-lookup"><span data-stu-id="c864a-165">Configure mailboxes with SIP addresses.</span></span></p></td>
<td><p><span data-ttu-id="c864a-166">Assegnare gli indirizzi SIP alle cassette postali degli utenti di VoIP aziendale che utilizzeranno le funzionalità di messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="c864a-166">Assign SIP addresses to the mailboxes of Enterprise Voice users who will be using Exchange UM features.</span></span></p></td>
<td><p><span data-ttu-id="c864a-167">Amministratore di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c864a-167">Lync Server 2013 administrator</span></span></p>
<p><span data-ttu-id="c864a-168">Amministratore destinatari di Exchange</span><span class="sxs-lookup"><span data-stu-id="c864a-168">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="c864a-169">Per Exchange 2007 SP1 o Service Pack più recente, &quot;vedere come aggiungere, rimuovere o modificare un indirizzo SIP per un utente&quot; abilitato alla messaggistica unificata <a href="https://go.microsoft.com/fwlink/p/?linkid=268698">https://go.microsoft.com/fwlink/p/?LinkId=268698</a>in.</span><span class="sxs-lookup"><span data-stu-id="c864a-169">For Exchange 2007 SP1 or latest service pack, see &quot;How to Add, Remove, or Modify a SIP Address for a UM-Enabled User&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268698">https://go.microsoft.com/fwlink/p/?LinkId=268698</a>.</span></span></p>
<p><span data-ttu-id="c864a-170">Per Exchange 2010 o Service Pack più recente, &quot;vedere Modificare un indirizzo SIP per un utente&quot; abilitato alla messaggistica <a href="https://go.microsoft.com/fwlink/p/?linkid=268699">https://go.microsoft.com/fwlink/p/?LinkId=268699</a>unificata in.</span><span class="sxs-lookup"><span data-stu-id="c864a-170">For Exchange 2010 or latest service pack, see &quot;Modify a SIP Address for a UM-Enabled User&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268699">https://go.microsoft.com/fwlink/p/?LinkId=268699</a>.</span></span></p>
<p><span data-ttu-id="c864a-171">Per Exchange 2013, vedere Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span><span class="sxs-lookup"><span data-stu-id="c864a-171">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c864a-172">Eseguire lo script exchucutil.ps1.</span><span class="sxs-lookup"><span data-stu-id="c864a-172">Run the exchucutil.ps1 script.</span></span></p></td>
<td><p><span data-ttu-id="c864a-173">Nel server che esegue i servizi di messaggistica unificata di Exchange, aprire Exchange Management Shell ed eseguire lo script exchucutil. ps1, che esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c864a-173">On the server running Exchange UM services, open the Exchange Management Shell and run the exchucutil.ps1 script, which does the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c864a-174">Concede l'autorizzazione di Lync Server 2013 per la lettura degli oggetti di servizi di dominio Active Directory di messaggistica unificata di Exchange, in particolare i dial plan SIP creati nell'attività precedente.</span><span class="sxs-lookup"><span data-stu-id="c864a-174">Grants Lync Server 2013 permission to read Exchange UM Active Directory Domain Services objects, specifically, the SIP dial plans created in the previous task.</span></span></p></li>
<li><p><span data-ttu-id="c864a-175">Crea un oggetto gateway IP di messaggistica unificata in Active Directory per ogni pool di Lync Server 2013 Enterprise Edition o un server Standard Edition che ospita gli utenti abilitati per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="c864a-175">Creates a Unified Messaging IP gateway object in Active Directory for each Lync Server 2013 Enterprise Edition pool or Standard Edition server that hosts users who are enabled for Enterprise Voice.</span></span></p></li>
<li><p><span data-ttu-id="c864a-176">Crea un gruppo di risposta di messaggistica unificata di Exchange per ogni gateway.</span><span class="sxs-lookup"><span data-stu-id="c864a-176">Creates an Exchange UM hunt group for each gateway.</span></span> <span data-ttu-id="c864a-177">L'identificatore pilota del gruppo di risposta sarà il nome del dial plan associato al gateway corrispondente.</span><span class="sxs-lookup"><span data-stu-id="c864a-177">The hunt group pilot identifier will be the name of the dial plan that is associated with the corresponding gateway.</span></span> <span data-ttu-id="c864a-178">Deve esistere un mapping uno a uno in caso di più dial plan.</span><span class="sxs-lookup"><span data-stu-id="c864a-178">These need to be mapped 1:1 if there is more than one dial plan.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c864a-179">Amministratore dell'organizzazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="c864a-179">Exchange Organization administrator</span></span></p>
<p><span data-ttu-id="c864a-180">Amministratore destinatari di Exchange</span><span class="sxs-lookup"><span data-stu-id="c864a-180">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="c864a-181"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configurare la messaggistica unificata in Microsoft Exchange per Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c864a-181"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c864a-182">Configurare i dial plan di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c864a-182">Configure Lync Server 2013 dial plans.</span></span></p></td>
<td><p><span data-ttu-id="c864a-183">Se si esegue l'integrazione con Exchange 2007 SP1 o Service Pack più recente o Exchange 2010, creare un nuovo dial plan VoIP aziendale con un nome che corrisponda al nome di dominio completo (FQDN) del dial plan di messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="c864a-183">If you are integrating with Exchange 2007 SP1 or latest service pack, or Exchange 2010, create a new Enterprise Voice dial plan with a name that matches the Exchange UM dial plan fully qualified domain name (FQDN).</span></span></p>



> [!NOTE]
> <span data-ttu-id="c864a-184">Sarà necessario eseguire questa operazione per ogni dial plan di messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="c864a-184">You will need to do this for each UM Dial plan.</span></span>


<p><span data-ttu-id="c864a-185">Se si esegue l'integrazione con Exchange 2010 SP1, assicurarsi che siano stati configurati piani di chiamata VoIP Enterprise a livello globale o a livello di sito o di pool.</span><span class="sxs-lookup"><span data-stu-id="c864a-185">If you are integrating with Exchange 2010 SP1, ensure that suitable global/site-level or pool-level Enterprise Voice dial plans have been configured.</span></span></p>



> [!NOTE]
> <span data-ttu-id="c864a-186">Se si esegue l'integrazione con Exchange 2010 SP1, il dial plan di Lync Server e i nomi dei dial plan SIP di messaggistica unificata di Exchange non devono corrispondere.</span><span class="sxs-lookup"><span data-stu-id="c864a-186">If you are integrating with Exchange 2010 SP1, the Lync Server dial plan and Exchange UM SIP dial plan names do not need to match.</span></span>

</td>
<td><p><span data-ttu-id="c864a-187">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="c864a-187">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="c864a-188"><a href="lync-server-2013-configuring-dial-plans.md">Configurazione di dial plan in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c864a-188"><a href="lync-server-2013-configuring-dial-plans.md">Configuring dial plans in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c864a-189">Eseguire lo strumento di integrazione della messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="c864a-189">Run the Exchange UM Integration tool.</span></span></p></td>
<td><p><span data-ttu-id="c864a-190">In Lync Server 2013 eseguire <strong>OcsUmUtil. exe</strong>, che:</span><span class="sxs-lookup"><span data-stu-id="c864a-190">On the Lync Server 2013, run <strong>ocsumutil.exe</strong>, which:</span></span></p>
<ul>
<li><p><span data-ttu-id="c864a-191">Crea oggetti contatto Accesso sottoscrittore e Operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="c864a-191">Creates Subscriber Access and Auto Attendant contact objects.</span></span></p></li>
<li><p><span data-ttu-id="c864a-192">Verifica la presenza di un dial plan VoIP aziendale con un nome che corrisponde all'FQDN del dial plan di messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="c864a-192">Validates that there is an Enterprise Voice dial plan with a name that matches the Exchange UM dial plan FQDN.</span></span> <span data-ttu-id="c864a-193">Se si esegue Exchange 2010 SP1 o versione successiva, i nomi dei dial plan non devono corrispondere ed è possibile ignorare l'avviso dello strumento.</span><span class="sxs-lookup"><span data-stu-id="c864a-193">If you are running Exchange 2010 SP1 or later, the dial plan names do not need to match, and you can ignore the tool’s warning about this.</span></span></p></li>
</ul>
<p><span data-ttu-id="c864a-194">Questo strumento funziona analizzando Active Directory per le impostazioni di messaggistica unificata di Exchange e consentendo all'amministratore di Lync Server 2013 di visualizzare, creare e modificare gli oggetti contatto.</span><span class="sxs-lookup"><span data-stu-id="c864a-194">This tool works by scanning the Active Directory for Exchange UM settings and allowing the Lync Server 2013 administrator to view, create, and edit contact objects.</span></span></p></td>
<td><p><span data-ttu-id="c864a-195">RTCUniversalServerAdmins <em>e</em> TCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="c864a-195">RTCUniversalServerAdmins <em>and</em> RTCUniversalUserAdmins</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="c864a-196">Per eseguire correttamente ocsumutil.exe, l'utente deve appartenere a entrambi i gruppi.</span><span class="sxs-lookup"><span data-stu-id="c864a-196">To run ocsumutil.exe successfully, the user must belong to both of these groups.</span></span>





> [!NOTE]
> <span data-ttu-id="c864a-197">Per creare oggetti contatto, l'utente che esegue ocsumutil.exe deve disporre dell'autorizzazione appropriata per l'unità organizzativa di Active Directory in cui sono archiviati i nuovi oggetti contatto.</span><span class="sxs-lookup"><span data-stu-id="c864a-197">To create Contact objects, the user who runs ocsumutil.exe must have the correct permission to the Active Directory organizational unit (OU) where the new contact objects are stored.</span></span> <span data-ttu-id="c864a-198">Questa autorizzazione può essere concessa eseguendo il cmdlet <STRONG>Grant-CsOUPermission</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="c864a-198">This permission can be granted by running the <STRONG>Grant-CsOUPermission</STRONG> cmdlet.</span></span> <span data-ttu-id="c864a-199">Per informazioni dettagliate, vedere la documentazione relativa a Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c864a-199">For details, see the Lync Server Management Shell documentation.</span></span>

</td>
<td><p><span data-ttu-id="c864a-200"><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Configurare Lync Server 2013 per l'utilizzo della messaggistica unificata in Microsoft Exchange Server</a></span><span class="sxs-lookup"><span data-stu-id="c864a-200"><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c864a-201">Se necessario, eseguire altre operazioni di configurazione di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="c864a-201">If necessary, perform other Enterprise Voice configuration steps.</span></span></p></td>
<td><p><span data-ttu-id="c864a-202">Se le impostazioni di VoIP aziendale non sono state già configurate nei server o negli utenti, eseguire una o più delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c864a-202">If you have not already configured Enterprise Voice settings on your servers or users, do one or more of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c864a-203">Distribuire e configurare</span><span class="sxs-lookup"><span data-stu-id="c864a-203">Deploy and configure</span></span></p>
<p><span data-ttu-id="c864a-204">Gateway PSTN (Public Switched Telephone Network) e Mediation Server</span><span class="sxs-lookup"><span data-stu-id="c864a-204">Public switched telephone network (PSTN) gateways and Mediation Servers</span></span></p></li>
<li><p><span data-ttu-id="c864a-205">Definire criteri vocali, record di utilizzo PSTN e route di chiamate in uscita.</span><span class="sxs-lookup"><span data-stu-id="c864a-205">Define voice policies, PSTN usage records, and outbound call routes.</span></span></p></li>
<li><p><span data-ttu-id="c864a-206">Abilitare gli utenti per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="c864a-206">Enable users for Enterprise Voice.</span></span></p></li>
<li><p><span data-ttu-id="c864a-207">Facoltativamente, configurare utenti specifici con i dial plan.</span><span class="sxs-lookup"><span data-stu-id="c864a-207">Optionally, configure specific users with dial plans.</span></span></p></li>
</ul>
<p><span data-ttu-id="c864a-208">È possibile che siano necessarie altre operazioni di configurazione a seconda delle funzionalità di VoIP aziendale abilitate.</span><span class="sxs-lookup"><span data-stu-id="c864a-208">Other configuration steps may be required depending on the Enterprise Voice features that you enable.</span></span></p></td>
<td><p><span data-ttu-id="c864a-209">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="c864a-209">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="c864a-210">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="c864a-210">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="c864a-211">Vedere gli argomenti nelle sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c864a-211">See topics in the following sections:</span></span></p>
<ul>
<li><p><span data-ttu-id="c864a-212"><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Configurazione di criteri vocali, record di utilizzo PSTN e route vocali in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c864a-212"><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="c864a-213"><a href="lync-server-2013-deploying-enterprise-voice.md">Distribuzione di VoIP aziendale in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c864a-213"><a href="lync-server-2013-deploying-enterprise-voice.md">Deploying Enterprise Voice in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c864a-214">Abilitare gli utenti di VoIP aziendale per la messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="c864a-214">Enable Enterprise Voice users for Exchange UM.</span></span></p></td>
<td><p><span data-ttu-id="c864a-215">Sul server Messaggistica unificata di Exchange, verificare che sia stato creato un criterio cassetta postale di messaggistica unificata e che ogni utente disponga di un'assegnazione univoca del numero di interno e quindi abilitare l'utente alla messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="c864a-215">On the Exchange UM server, ensure that a Unified Messaging mailbox policy has been created and that each user has a unique extension number assignment, and then enable the user for Unified Messaging.</span></span></p></td>
<td><p><span data-ttu-id="c864a-216">Amministratore destinatari di Exchange</span><span class="sxs-lookup"><span data-stu-id="c864a-216">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="c864a-217">Per Exchange 2007 SP1 o Service Pack più recente, &quot;vedere How to Enable a user for Unified Messaging&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268700">https://go.microsoft.com/fwlink/p/?LinkId=268700</a>.</span><span class="sxs-lookup"><span data-stu-id="c864a-217">For Exchange 2007 SP1 or latest service pack, see &quot;How to Enable a User for Unified Messaging&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268700">https://go.microsoft.com/fwlink/p/?LinkId=268700</a>.</span></span></p>
<p><span data-ttu-id="c864a-218">Per Exchange 2010 o Service Pack più recente, &quot;vedere Abilitare un utente per la messaggistica&quot; unificata in <a href="https://go.microsoft.com/fwlink/p/?linkid=268701">https://go.microsoft.com/fwlink/p/?LinkId=268701</a>.</span><span class="sxs-lookup"><span data-stu-id="c864a-218">For Exchange 2010 or latest service pack, see &quot;Enable a User for Unified Messaging&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268701">https://go.microsoft.com/fwlink/p/?LinkId=268701</a>.</span></span></p>
<p><span data-ttu-id="c864a-219">Per Exchange 2013, vedere Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span><span class="sxs-lookup"><span data-stu-id="c864a-219">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


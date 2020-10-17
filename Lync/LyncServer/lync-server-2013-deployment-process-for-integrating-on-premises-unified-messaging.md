---
title: Processo di distribuzione per l'integrazione della messaggistica unificata locale
description: Processo di distribuzione per l'integrazione della messaggistica unificata locale.
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
ms.openlocfilehash: 6c1b8f528edb970893198ed06b821535a398f09d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569522"
---
# <a name="deployment-process-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="84bd1-103">Processo di distribuzione per l'integrazione della messaggistica unificata locale e di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84bd1-103">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84bd1-104">_**Ultimo argomento modificato:** 2012-12-17_</span><span class="sxs-lookup"><span data-stu-id="84bd1-104">_**Topic Last Modified:** 2012-12-17_</span></span>

<span data-ttu-id="84bd1-105">Se si desidera integrare la messaggistica unificata di Exchange con Lync Server 2013, è necessario eseguire le attività descritte in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="84bd1-105">If you want to integrate Exchange Unified Messaging (UM) with Lync Server 2013, you must perform the tasks described in this topic.</span></span> <span data-ttu-id="84bd1-106">È inoltre necessario esaminare le procedure consigliate per la pianificazione e la distribuzione descritte in [linee guida per l'integrazione della messaggistica unificata locale e di Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md).</span><span class="sxs-lookup"><span data-stu-id="84bd1-106">Also be sure that you review the planning and deployment best practices described in [Guidelines for integrating on-premises Unified Messaging and Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md).</span></span> <span data-ttu-id="84bd1-107">In questo argomento si presuppone che sia stato distribuito Lync Server 2013 con un Mediation Server collocato e che siano stati abilitati gli utenti per Lync Server 2013, ma non necessariamente che siano stati eseguiti tutti i passaggi di distribuzione e configurazione per abilitare VoIP aziendale, come descritto in [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="84bd1-107">This topic assumes that you have deployed Lync Server 2013 with a collocated Mediation Server and that you have enabled users for Lync Server 2013, but not necessarily that you have performed all deployment and configuration steps to enable Enterprise Voice, as described in [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span>

<div>

## <a name="unified-messaging-integration-process"></a><span data-ttu-id="84bd1-108">Processo di integrazione di messaggistica unificata</span><span class="sxs-lookup"><span data-stu-id="84bd1-108">Unified Messaging Integration Process</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="84bd1-109">È importante coordinarsi con gli amministratori di Exchange dell'organizzazione per confermare le attività che ognuno di voi eseguirà per garantire un'integrazione agevole e corretta.</span><span class="sxs-lookup"><span data-stu-id="84bd1-109">It is important that you coordinate with your organization’s Exchange administrators to confirm the tasks that each of you will perform to help ensure a smooth, successful integration.</span></span>



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
<th><span data-ttu-id="84bd1-110">Fase</span><span class="sxs-lookup"><span data-stu-id="84bd1-110">Phase</span></span></th>
<th><span data-ttu-id="84bd1-111">Passaggi</span><span class="sxs-lookup"><span data-stu-id="84bd1-111">Steps</span></span></th>
<th><span data-ttu-id="84bd1-112">Gruppi e ruoli obbligatori</span><span class="sxs-lookup"><span data-stu-id="84bd1-112">Required groups and roles</span></span></th>
<th><span data-ttu-id="84bd1-113">Documentazione sulla distribuzione</span><span class="sxs-lookup"><span data-stu-id="84bd1-113">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84bd1-114">Distribuire uno dei prodotti seguenti:</span><span class="sxs-lookup"><span data-stu-id="84bd1-114">Deploy one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="84bd1-115">Microsoft Exchange Server 2007 Service Pack 1 (SP2) o Service Pack più recente</span><span class="sxs-lookup"><span data-stu-id="84bd1-115">Microsoft Exchange Server 2007 Service Pack 1 (SP2) or latest service pack</span></span></p></li>
<li><p><span data-ttu-id="84bd1-116">Microsoft Exchange Server 2010 o Service Pack più recente</span><span class="sxs-lookup"><span data-stu-id="84bd1-116">Microsoft Exchange Server 2010 or latest service pack</span></span></p></li>
<li><p><span data-ttu-id="84bd1-117">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="84bd1-117">Microsoft Exchange Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="84bd1-118">Se si utilizza Microsoft Exchange Server 2013, installare i seguenti ruoli del server Exchange nella stessa foresta o in una foresta diversa come Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="84bd1-118">If you are using Microsoft Exchange Server 2013, install the following Exchange Server roles in either the same forest or a different forest as Lync Server 2013:</span></span></p>
<ul>
<li><p><span data-ttu-id="84bd1-119">Accesso client</span><span class="sxs-lookup"><span data-stu-id="84bd1-119">Client Access</span></span></p></li>
<li><p><span data-ttu-id="84bd1-120">Cassetta postale</span><span class="sxs-lookup"><span data-stu-id="84bd1-120">Mailbox</span></span></p></li>
</ul>
<p><span data-ttu-id="84bd1-121">Se Microsoft Exchange Server 2013 e la messaggistica unificata di Exchange vengono installati in foreste diverse, configurare ogni foresta di Exchange in modo che consideri attendibile la foresta di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="84bd1-121">If Microsoft Exchange Server 2013 and Exchange Unified Messaging (UM) are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest.</span></span></p>
<p><span data-ttu-id="84bd1-122">Se si utilizza Exchange 2010, installare i seguenti ruoli del server Exchange nella stessa foresta o in una foresta diversa come Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="84bd1-122">If you are using Exchange 2010, install the following Exchange Server roles in either the same forest or a different forest as Lync Server 2013:</span></span></p>
<ul>
<li><p><span data-ttu-id="84bd1-123">Messaggistica unificata</span><span class="sxs-lookup"><span data-stu-id="84bd1-123">Unified Messaging</span></span></p></li>
<li><p><span data-ttu-id="84bd1-124">Trasporto Hub</span><span class="sxs-lookup"><span data-stu-id="84bd1-124">Hub Transport</span></span></p></li>
<li><p><span data-ttu-id="84bd1-125">Accesso client</span><span class="sxs-lookup"><span data-stu-id="84bd1-125">Client Access</span></span></p></li>
<li><p><span data-ttu-id="84bd1-126">Cassetta postale</span><span class="sxs-lookup"><span data-stu-id="84bd1-126">Mailbox</span></span></p></li>
</ul>
<p><span data-ttu-id="84bd1-127">Se Lync Server 2013 e la messaggistica unificata di Exchange sono installati in foreste diverse, configurare ogni foresta di Exchange in modo che consideri attendibile la foresta di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="84bd1-127">If Lync Server 2013 and Exchange Unified Messaging (UM) are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest.</span></span></p></td>
<td><p><span data-ttu-id="84bd1-128">Amministratori dell'organizzazione (se è il primo Exchange Server dell'organizzazione)</span><span class="sxs-lookup"><span data-stu-id="84bd1-128">Enterprise administrators (if this is the first Exchange Server in the organization)</span></span></p>
<p><span data-ttu-id="84bd1-129">-OPPURE-</span><span class="sxs-lookup"><span data-stu-id="84bd1-129">-OR-</span></span></p>
<p><span data-ttu-id="84bd1-130">Amministratore dell'organizzazione di Exchange (se non è il primo Exchange Server dell'organizzazione)</span><span class="sxs-lookup"><span data-stu-id="84bd1-130">Exchange Organization administrator (if this is not the first Exchange Server in the organization)</span></span></p></td>
<td><p><span data-ttu-id="84bd1-131">Per informazioni sulla versione di Exchange di cui si dispone, vedere la documentazione appropriata:</span><span class="sxs-lookup"><span data-stu-id="84bd1-131">See the appropriate documentation for your version of Exchange Server:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="84bd1-132">Documentazione relativa alla distribuzione di Exchange Server 2007 all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=268694">https://go.microsoft.com/fwlink/p/?LinkId=268694</a> .</span><span class="sxs-lookup"><span data-stu-id="84bd1-132">Exchange Server 2007 deployment documentation at <a href="https://go.microsoft.com/fwlink/p/?linkid=268694">https://go.microsoft.com/fwlink/p/?LinkId=268694</a>.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="84bd1-133">Documentazione relativa alla distribuzione del Service Pack di Exchange Server 2010 o versione più recente <a href="https://go.microsoft.com/fwlink/p/?linkid=268695">https://go.microsoft.com/fwlink/p/?LinkId=268695</a> .</span><span class="sxs-lookup"><span data-stu-id="84bd1-133">Exchange Server 2010 or latest service pack deployment documentation at <a href="https://go.microsoft.com/fwlink/p/?linkid=268695">https://go.microsoft.com/fwlink/p/?LinkId=268695</a>.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="84bd1-134">Microsoft Exchange Server 2013 pianificazione e distribuzione in <a href="https://go.microsoft.com/fwlink/p/?linkid=266569">https://go.microsoft.com/fwlink/p/?LinkId=266569</a> .</span><span class="sxs-lookup"><span data-stu-id="84bd1-134">Microsoft Exchange Server 2013 Planning and Deployment at <a href="https://go.microsoft.com/fwlink/p/?linkid=266569">https://go.microsoft.com/fwlink/p/?LinkId=266569</a>.</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84bd1-135">Installare i certificati.</span><span class="sxs-lookup"><span data-stu-id="84bd1-135">Install certificates.</span></span></p></td>
<td><p><span data-ttu-id="84bd1-136">Scaricare e installare i certificati per ogni server Messaggistica unificata di Exchange da un'autorità di certificazione (CA) radice attendibile.</span><span class="sxs-lookup"><span data-stu-id="84bd1-136">Download and install certificates for each Exchange UM server from a trusted root certificate authority (CA).</span></span> <span data-ttu-id="84bd1-137">I certificati sono necessari per la sicurezza MTLS (Mutual Transport Level Security) tra i server che eseguono la messaggistica unificata di Exchange e Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="84bd1-137">The certificates are required for mutual Transport Level Security (MTLS) between the servers running Exchange UM and Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="84bd1-138">Amministratori</span><span class="sxs-lookup"><span data-stu-id="84bd1-138">Administrators</span></span></p></td>
<td><p><span data-ttu-id="84bd1-139"><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Configurare i certificati nel server che esegue la messaggistica unificata di Microsoft Exchange Server</a></span><span class="sxs-lookup"><span data-stu-id="84bd1-139"><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84bd1-140">Creare e configurare un nuovo dial plan SIP di messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="84bd1-140">Create and configure a new Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="84bd1-141">Nel server Messaggistica unificata di Exchange, creare un dial plan SIP in base ai requisiti di distribuzione specifici dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="84bd1-141">On the Exchange UM server, create a SIP dial plan based on your organization’s specific deployment requirements.</span></span></p></td>
<td><p><span data-ttu-id="84bd1-142">Amministratore dell'organizzazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="84bd1-142">Exchange Organization administrator</span></span></p></td>
<td><p><span data-ttu-id="84bd1-143">Per Exchange 2007 SP1 o Service Pack più recente, vedere &quot; come creare un dial plan URI SIP di messaggistica unificata &quot; in <a href="https://go.microsoft.com/fwlink/p/?linkid=268632">https://go.microsoft.com/fwlink/p/?linkId=268632</a> .</span><span class="sxs-lookup"><span data-stu-id="84bd1-143">For Exchange 2007 SP1 or latest service pack, see &quot;How to Create a Unified Messaging SIP URI Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268632">https://go.microsoft.com/fwlink/p/?linkId=268632</a>.</span></span></p>
<p><span data-ttu-id="84bd1-144">Per Exchange 2010 o Service Pack più recente, vedere &quot; creare un dial plan di messaggistica unificata &quot; in <a href="https://go.microsoft.com/fwlink/p/?linkid=268674">https://go.microsoft.com/fwlink/p/?linkId=268674</a> .</span><span class="sxs-lookup"><span data-stu-id="84bd1-144">For Exchange 2010 or latest service pack, see &quot;Create a UM Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268674">https://go.microsoft.com/fwlink/p/?linkId=268674</a>.</span></span></p>
<p><span data-ttu-id="84bd1-145">Per Exchange 2013, vedere Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> .</span><span class="sxs-lookup"><span data-stu-id="84bd1-145">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84bd1-146">Configurare le impostazioni di protezione per il dial plan SIP di messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="84bd1-146">Configure security settings for the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="84bd1-147">Per crittografare il traffico VoIP aziendale, configurare le impostazioni di sicurezza nel dial plan SIP di messaggistica unificata di Exchange come <strong>SIP</strong> con protezione o <strong>protetto</strong>.</span><span class="sxs-lookup"><span data-stu-id="84bd1-147">To encrypt Enterprise Voice traffic, configure the security settings on the Exchange UM SIP dial plan as <strong>SIP Secured</strong> or <strong>Secured</strong>.</span></span> <span data-ttu-id="84bd1-148">Questo è un passaggio particolarmente importante se è stato distribuito o si intende distribuire i dispositivi Lync Phone Edition nell'ambiente in uso.</span><span class="sxs-lookup"><span data-stu-id="84bd1-148">This is an especially important step if you have deployed or plan to deploy Lync Phone Edition devices in your environment.</span></span> <span data-ttu-id="84bd1-149">Affinché i dispositivi Lync Phone Edition funzionino in un ambiente con integrazione di messaggistica unificata di Exchange, le impostazioni di crittografia di Lync Server devono essere allineate alle impostazioni di protezione di messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="84bd1-149">For Lync Phone Edition devices to function in an environment with Exchange UM integration, Lync Server encryption settings must align with the Exchange UM dial plan security settings.</span></span> <span data-ttu-id="84bd1-150">Per informazioni dettagliate, vedere la documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="84bd1-150">For details, refer to the Deployment documentation.</span></span></p></td>
<td><p><span data-ttu-id="84bd1-151">Amministratore dell'organizzazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="84bd1-151">Exchange Organization administrator</span></span></p></td>
<td><p><span data-ttu-id="84bd1-152"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configurare la messaggistica unificata in Microsoft Exchange per Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="84bd1-152"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="84bd1-153">Per Exchange 2007 SP1 o Service Pack più recente, vedere anche:</span><span class="sxs-lookup"><span data-stu-id="84bd1-153">For Exchange 2007 SP1 or latest service pack, see also:</span></span></p>
<p><span data-ttu-id="84bd1-154">&quot;Informazioni su come configurare la sicurezza in un dial plan di messaggistica unificata &quot; in <a href="https://go.microsoft.com/fwlink/p/?linkid=268696">https://go.microsoft.com/fwlink/p/?LinkId=268696</a> .</span><span class="sxs-lookup"><span data-stu-id="84bd1-154">&quot;How to Configure Security on a Unified Messaging Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268696">https://go.microsoft.com/fwlink/p/?LinkId=268696</a>.</span></span></p>
<p><span data-ttu-id="84bd1-155">Per Exchange 2010 o Service Pack più recente, vedere anche:</span><span class="sxs-lookup"><span data-stu-id="84bd1-155">For Exchange 2010 or latest service pack, see also:</span></span></p>
<p><span data-ttu-id="84bd1-156">&quot;Configurare la sicurezza VoIP su un dial plan di messaggistica unificata &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268697">https://go.microsoft.com/fwlink/p/?LinkId=268697</a> .</span><span class="sxs-lookup"><span data-stu-id="84bd1-156">&quot;Configure VoIP Security on a UM Dial Plan&quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268697">https://go.microsoft.com/fwlink/p/?LinkId=268697</a>.</span></span></p>
<p><span data-ttu-id="84bd1-157">Per Exchange 2013, vedere Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> .</span><span class="sxs-lookup"><span data-stu-id="84bd1-157">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84bd1-158">Aggiungere i server Messaggistica unificata al dial plan SIP di messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="84bd1-158">Add Unified Messaging servers to the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="84bd1-159">Per consentire a un server di Messaggistica unificata appena installato di rispondere alle chiamate in arrivo e di elaborarle, è necessario aggiungere il server di Messaggistica unificata a un dial plan di Messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="84bd1-159">To enable a newly installed Unified Messaging server to answer and process incoming calls, you must add the Unified Messaging server to a UM dial plan.</span></span> <span data-ttu-id="84bd1-160">In questo caso, aggiungere il server al dial plan SIP di messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="84bd1-160">In this case, add the server to the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="84bd1-161">Amministratori</span><span class="sxs-lookup"><span data-stu-id="84bd1-161">Administrators</span></span></p>
<p><span data-ttu-id="84bd1-162">Amministratori di Exchange Server</span><span class="sxs-lookup"><span data-stu-id="84bd1-162">Exchange Server administrators</span></span></p></td>
<td><p><span data-ttu-id="84bd1-163">Per Exchange 2007 SP1 o Service Pack più recente, vedere &quot; come aggiungere il server Messaggistica unificata a un dial plan &quot; all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=268681">https://go.microsoft.com/fwlink/p/?linkId=268681</a> .</span><span class="sxs-lookup"><span data-stu-id="84bd1-163">For Exchange 2007 SP1 or latest service pack, see &quot;How to Add Unified Messaging Server to a Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268681">https://go.microsoft.com/fwlink/p/?linkId=268681</a>.</span></span></p>
<p><span data-ttu-id="84bd1-164">Per Exchange 2010 o Service Pack più recente, vedere &quot; visualizzazione o configurazione delle proprietà di un server di messaggistica unificata &quot; in <a href="https://go.microsoft.com/fwlink/p/?linkid=268682">https://go.microsoft.com/fwlink/p/?linkId=268682</a> .</span><span class="sxs-lookup"><span data-stu-id="84bd1-164">For Exchange 2010 or latest service pack, see &quot;View or Configure the Properties of a UM Server&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268682">https://go.microsoft.com/fwlink/p/?linkId=268682</a>.</span></span></p>
<p><span data-ttu-id="84bd1-165">Per Exchange 2013, vedere Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> .</span><span class="sxs-lookup"><span data-stu-id="84bd1-165">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84bd1-166">Configurare cassette postali con indirizzi SIP</span><span class="sxs-lookup"><span data-stu-id="84bd1-166">Configure mailboxes with SIP addresses.</span></span></p></td>
<td><p><span data-ttu-id="84bd1-167">Assegnare gli indirizzi SIP alle cassette postali degli utenti di VoIP aziendale che utilizzeranno le funzionalità di messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="84bd1-167">Assign SIP addresses to the mailboxes of Enterprise Voice users who will be using Exchange UM features.</span></span></p></td>
<td><p><span data-ttu-id="84bd1-168">Amministratore di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84bd1-168">Lync Server 2013 administrator</span></span></p>
<p><span data-ttu-id="84bd1-169">Amministratore destinatari di Exchange</span><span class="sxs-lookup"><span data-stu-id="84bd1-169">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="84bd1-170">Per Exchange 2007 SP1 o Service Pack più recente, vedere &quot; come aggiungere, rimuovere o modificare un indirizzo SIP per un UM-Enabled utente &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268698">https://go.microsoft.com/fwlink/p/?LinkId=268698</a> .</span><span class="sxs-lookup"><span data-stu-id="84bd1-170">For Exchange 2007 SP1 or latest service pack, see &quot;How to Add, Remove, or Modify a SIP Address for a UM-Enabled User&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268698">https://go.microsoft.com/fwlink/p/?LinkId=268698</a>.</span></span></p>
<p><span data-ttu-id="84bd1-171">Per Exchange 2010 o Service Pack più recente, vedere &quot; Modify a SIP address for a UM-Enabled user &quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268699">https://go.microsoft.com/fwlink/p/?LinkId=268699</a> .</span><span class="sxs-lookup"><span data-stu-id="84bd1-171">For Exchange 2010 or latest service pack, see &quot;Modify a SIP Address for a UM-Enabled User&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268699">https://go.microsoft.com/fwlink/p/?LinkId=268699</a>.</span></span></p>
<p><span data-ttu-id="84bd1-172">Per Exchange 2013, vedere Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> .</span><span class="sxs-lookup"><span data-stu-id="84bd1-172">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84bd1-173">Eseguire lo script exchucutil.ps1.</span><span class="sxs-lookup"><span data-stu-id="84bd1-173">Run the exchucutil.ps1 script.</span></span></p></td>
<td><p><span data-ttu-id="84bd1-174">Nel server che esegue i servizi di messaggistica unificata di Exchange, aprire Exchange Management Shell ed eseguire lo script exchucutil.ps1, che esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="84bd1-174">On the server running Exchange UM services, open the Exchange Management Shell and run the exchucutil.ps1 script, which does the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="84bd1-175">Concede l'autorizzazione di Lync Server 2013 per la lettura degli oggetti di servizi di dominio Active Directory di messaggistica unificata di Exchange, in particolare i dial plan SIP creati nell'attività precedente.</span><span class="sxs-lookup"><span data-stu-id="84bd1-175">Grants Lync Server 2013 permission to read Exchange UM Active Directory Domain Services objects, specifically, the SIP dial plans created in the previous task.</span></span></p></li>
<li><p><span data-ttu-id="84bd1-176">Crea un oggetto gateway IP di messaggistica unificata in Active Directory per ogni pool di Lync Server 2013 Enterprise Edition o un server Standard Edition che ospita gli utenti abilitati per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="84bd1-176">Creates a Unified Messaging IP gateway object in Active Directory for each Lync Server 2013 Enterprise Edition pool or Standard Edition server that hosts users who are enabled for Enterprise Voice.</span></span></p></li>
<li><p><span data-ttu-id="84bd1-177">Crea un gruppo di risposta di messaggistica unificata di Exchange per ogni gateway.</span><span class="sxs-lookup"><span data-stu-id="84bd1-177">Creates an Exchange UM hunt group for each gateway.</span></span> <span data-ttu-id="84bd1-178">L'identificatore pilota del gruppo di risposta sarà il nome del dial plan associato al gateway corrispondente.</span><span class="sxs-lookup"><span data-stu-id="84bd1-178">The hunt group pilot identifier will be the name of the dial plan that is associated with the corresponding gateway.</span></span> <span data-ttu-id="84bd1-179">Deve esistere un mapping uno a uno in caso di più dial plan.</span><span class="sxs-lookup"><span data-stu-id="84bd1-179">These need to be mapped 1:1 if there is more than one dial plan.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="84bd1-180">Amministratore dell'organizzazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="84bd1-180">Exchange Organization administrator</span></span></p>
<p><span data-ttu-id="84bd1-181">Amministratore destinatari di Exchange</span><span class="sxs-lookup"><span data-stu-id="84bd1-181">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="84bd1-182"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configurare la messaggistica unificata in Microsoft Exchange per Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="84bd1-182"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84bd1-183">Configurare i dial plan di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="84bd1-183">Configure Lync Server 2013 dial plans.</span></span></p></td>
<td><p><span data-ttu-id="84bd1-184">Se si esegue l'integrazione con Exchange 2007 SP1 o Service Pack più recente o Exchange 2010, creare un nuovo dial plan VoIP aziendale con un nome che corrisponda al nome di dominio completo (FQDN) del dial plan di messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="84bd1-184">If you are integrating with Exchange 2007 SP1 or latest service pack, or Exchange 2010, create a new Enterprise Voice dial plan with a name that matches the Exchange UM dial plan fully qualified domain name (FQDN).</span></span></p>



> [!NOTE]
> <span data-ttu-id="84bd1-185">Sarà necessario eseguire questa operazione per ogni dial plan di messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="84bd1-185">You will need to do this for each UM Dial plan.</span></span>


<p><span data-ttu-id="84bd1-186">Se si esegue l'integrazione con Exchange 2010 SP1, assicurarsi che siano stati configurati piani di chiamata VoIP Enterprise a livello globale o a livello di sito o di pool.</span><span class="sxs-lookup"><span data-stu-id="84bd1-186">If you are integrating with Exchange 2010 SP1, ensure that suitable global/site-level or pool-level Enterprise Voice dial plans have been configured.</span></span></p>



> [!NOTE]
> <span data-ttu-id="84bd1-187">Se si esegue l'integrazione con Exchange 2010 SP1, il dial plan di Lync Server e i nomi dei dial plan SIP di messaggistica unificata di Exchange non devono corrispondere.</span><span class="sxs-lookup"><span data-stu-id="84bd1-187">If you are integrating with Exchange 2010 SP1, the Lync Server dial plan and Exchange UM SIP dial plan names do not need to match.</span></span>

</td>
<td><p><span data-ttu-id="84bd1-188">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="84bd1-188">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="84bd1-189"><a href="lync-server-2013-configuring-dial-plans.md">Configurazione di dial plan in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="84bd1-189"><a href="lync-server-2013-configuring-dial-plans.md">Configuring dial plans in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84bd1-190">Eseguire lo strumento di integrazione della messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="84bd1-190">Run the Exchange UM Integration tool.</span></span></p></td>
<td><p><span data-ttu-id="84bd1-191">Nel Lync Server 2013, eseguire <strong>ocsumutil.exe</strong>, che:</span><span class="sxs-lookup"><span data-stu-id="84bd1-191">On the Lync Server 2013, run <strong>ocsumutil.exe</strong>, which:</span></span></p>
<ul>
<li><p><span data-ttu-id="84bd1-192">Crea oggetti contatto Accesso sottoscrittore e Operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="84bd1-192">Creates Subscriber Access and Auto Attendant contact objects.</span></span></p></li>
<li><p><span data-ttu-id="84bd1-193">Verifica la presenza di un dial plan VoIP aziendale con un nome che corrisponde all'FQDN del dial plan di messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="84bd1-193">Validates that there is an Enterprise Voice dial plan with a name that matches the Exchange UM dial plan FQDN.</span></span> <span data-ttu-id="84bd1-194">Se si esegue Exchange 2010 SP1 o versione successiva, i nomi dei dial plan non devono corrispondere ed è possibile ignorare l'avviso dello strumento.</span><span class="sxs-lookup"><span data-stu-id="84bd1-194">If you are running Exchange 2010 SP1 or later, the dial plan names do not need to match, and you can ignore the tool’s warning about this.</span></span></p></li>
</ul>
<p><span data-ttu-id="84bd1-195">Questo strumento funziona analizzando Active Directory per le impostazioni di messaggistica unificata di Exchange e consentendo all'amministratore di Lync Server 2013 di visualizzare, creare e modificare gli oggetti contatto.</span><span class="sxs-lookup"><span data-stu-id="84bd1-195">This tool works by scanning the Active Directory for Exchange UM settings and allowing the Lync Server 2013 administrator to view, create, and edit contact objects.</span></span></p></td>
<td><p><span data-ttu-id="84bd1-196">RTCUniversalServerAdmins <em>e</em> TCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="84bd1-196">RTCUniversalServerAdmins <em>and</em> RTCUniversalUserAdmins</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="84bd1-197">Per eseguire correttamente ocsumutil.exe, l'utente deve appartenere a entrambi i gruppi.</span><span class="sxs-lookup"><span data-stu-id="84bd1-197">To run ocsumutil.exe successfully, the user must belong to both of these groups.</span></span>





> [!NOTE]
> <span data-ttu-id="84bd1-198">Per creare oggetti contatto, l'utente che esegue ocsumutil.exe deve disporre dell'autorizzazione appropriata per l'unità organizzativa di Active Directory in cui sono archiviati i nuovi oggetti contatto.</span><span class="sxs-lookup"><span data-stu-id="84bd1-198">To create Contact objects, the user who runs ocsumutil.exe must have the correct permission to the Active Directory organizational unit (OU) where the new contact objects are stored.</span></span> <span data-ttu-id="84bd1-199">Questa autorizzazione può essere concessa eseguendo il cmdlet <STRONG>Grant-CsOUPermission</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="84bd1-199">This permission can be granted by running the <STRONG>Grant-CsOUPermission</STRONG> cmdlet.</span></span> <span data-ttu-id="84bd1-200">Per informazioni dettagliate, vedere la documentazione relativa a Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="84bd1-200">For details, see the Lync Server Management Shell documentation.</span></span>

</td>
<td><p><span data-ttu-id="84bd1-201"><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Configurare Lync Server 2013 per l'utilizzo della messaggistica unificata in Microsoft Exchange Server</a></span><span class="sxs-lookup"><span data-stu-id="84bd1-201"><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84bd1-202">Se necessario, eseguire altre operazioni di configurazione di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="84bd1-202">If necessary, perform other Enterprise Voice configuration steps.</span></span></p></td>
<td><p><span data-ttu-id="84bd1-203">Se le impostazioni di VoIP aziendale non sono state già configurate nei server o negli utenti, eseguire una o più delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="84bd1-203">If you have not already configured Enterprise Voice settings on your servers or users, do one or more of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="84bd1-204">Distribuire e configurare</span><span class="sxs-lookup"><span data-stu-id="84bd1-204">Deploy and configure</span></span></p>
<p><span data-ttu-id="84bd1-205">Gateway PSTN (Public Switched Telephone Network) e Mediation Server</span><span class="sxs-lookup"><span data-stu-id="84bd1-205">Public switched telephone network (PSTN) gateways and Mediation Servers</span></span></p></li>
<li><p><span data-ttu-id="84bd1-206">Definire criteri vocali, record di utilizzo PSTN e route di chiamate in uscita.</span><span class="sxs-lookup"><span data-stu-id="84bd1-206">Define voice policies, PSTN usage records, and outbound call routes.</span></span></p></li>
<li><p><span data-ttu-id="84bd1-207">Abilitare gli utenti per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="84bd1-207">Enable users for Enterprise Voice.</span></span></p></li>
<li><p><span data-ttu-id="84bd1-208">Facoltativamente, configurare utenti specifici con i dial plan.</span><span class="sxs-lookup"><span data-stu-id="84bd1-208">Optionally, configure specific users with dial plans.</span></span></p></li>
</ul>
<p><span data-ttu-id="84bd1-209">È possibile che siano necessarie altre operazioni di configurazione a seconda delle funzionalità di VoIP aziendale abilitate.</span><span class="sxs-lookup"><span data-stu-id="84bd1-209">Other configuration steps may be required depending on the Enterprise Voice features that you enable.</span></span></p></td>
<td><p><span data-ttu-id="84bd1-210">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="84bd1-210">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="84bd1-211">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="84bd1-211">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="84bd1-212">Vedere gli argomenti nelle sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="84bd1-212">See topics in the following sections:</span></span></p>
<ul>
<li><p><span data-ttu-id="84bd1-213"><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Configurazione di criteri vocali, record di utilizzo PSTN e route vocali in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="84bd1-213"><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="84bd1-214"><a href="lync-server-2013-deploying-enterprise-voice.md">Distribuzione di VoIP aziendale in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="84bd1-214"><a href="lync-server-2013-deploying-enterprise-voice.md">Deploying Enterprise Voice in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84bd1-215">Abilitare gli utenti di VoIP aziendale per la messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="84bd1-215">Enable Enterprise Voice users for Exchange UM.</span></span></p></td>
<td><p><span data-ttu-id="84bd1-216">Sul server Messaggistica unificata di Exchange, verificare che sia stato creato un criterio cassetta postale di messaggistica unificata e che ogni utente disponga di un'assegnazione univoca del numero di interno e quindi abilitare l'utente alla messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="84bd1-216">On the Exchange UM server, ensure that a Unified Messaging mailbox policy has been created and that each user has a unique extension number assignment, and then enable the user for Unified Messaging.</span></span></p></td>
<td><p><span data-ttu-id="84bd1-217">Amministratore destinatari di Exchange</span><span class="sxs-lookup"><span data-stu-id="84bd1-217">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="84bd1-218">Per Exchange 2007 SP1 o Service Pack più recente, vedere &quot; How to Enable a user for Unified Messaging &quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268700">https://go.microsoft.com/fwlink/p/?LinkId=268700</a> .</span><span class="sxs-lookup"><span data-stu-id="84bd1-218">For Exchange 2007 SP1 or latest service pack, see &quot;How to Enable a User for Unified Messaging&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268700">https://go.microsoft.com/fwlink/p/?LinkId=268700</a>.</span></span></p>
<p><span data-ttu-id="84bd1-219">Per Exchange 2010 o Service Pack più recente, vedere &quot; abilitare un utente per la messaggistica unificata &quot; in <a href="https://go.microsoft.com/fwlink/p/?linkid=268701">https://go.microsoft.com/fwlink/p/?LinkId=268701</a> .</span><span class="sxs-lookup"><span data-stu-id="84bd1-219">For Exchange 2010 or latest service pack, see &quot;Enable a User for Unified Messaging&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268701">https://go.microsoft.com/fwlink/p/?LinkId=268701</a>.</span></span></p>
<p><span data-ttu-id="84bd1-220">Per Exchange 2013, vedere Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> .</span><span class="sxs-lookup"><span data-stu-id="84bd1-220">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: elenco di controllo di distribuzione per il server Chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for Persistent Chat Server
ms:assetid: b1108f8f-88a2-4660-8086-d25ba76f7239
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412851(v=OCS.15)
ms:contentKeyID: 48185155
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a67d8a755a5647424a00aa7e534f736a4c0b5aa3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135873"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="cc9bf-102">Elenco di controllo di distribuzione per il server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc9bf-102">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc9bf-103">_**Ultimo argomento modificato:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="cc9bf-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="cc9bf-104">Distribuzione di Lync Server 2013, il server Chat persistente richiede che venga distribuito nella sequenza corretta e che vengano completati tutti i passaggi necessari per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="cc9bf-104">Deployment of Lync Server 2013, Persistent Chat Server requires that you deploy it in the correct sequence and that you complete all required deployment steps.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="cc9bf-105">Sequenza di distribuzione</span><span class="sxs-lookup"><span data-stu-id="cc9bf-105">Deployment Sequence</span></span>

<span data-ttu-id="cc9bf-106">È possibile distribuire il server Chat persistente dopo la distribuzione della topologia iniziale, tra cui almeno un Lync Server 2013, un pool Front end o un server Lync Server 2013, Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="cc9bf-106">You can deploy Persistent Chat Server after you deploy your initial topology, including at least one Lync Server 2013, Front End pool or one Lync Server 2013, Standard Edition server.</span></span> <span data-ttu-id="cc9bf-107">In questo argomento viene descritto come distribuire il server Chat persistente aggiungendolo a una distribuzione esistente.</span><span class="sxs-lookup"><span data-stu-id="cc9bf-107">This topic describes how to deploy Persistent Chat Server by adding it to an existing deployment.</span></span>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="cc9bf-108">Processo di distribuzione</span><span class="sxs-lookup"><span data-stu-id="cc9bf-108">Deployment Process</span></span>

<span data-ttu-id="cc9bf-109">Nella tabella seguente sono elencati i passaggi di base per la distribuzione del server Chat persistente e vengono forniti collegamenti per ulteriori dettagli.</span><span class="sxs-lookup"><span data-stu-id="cc9bf-109">The following table lists the basic steps to deploy Persistent Chat Server and provides links for more details.</span></span>

### <a name="persistent-chat-server-deployment-process"></a><span data-ttu-id="cc9bf-110">Processo di distribuzione del server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="cc9bf-110">Persistent Chat Server Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cc9bf-111">Attività</span><span class="sxs-lookup"><span data-stu-id="cc9bf-111">Task</span></span></th>
<th><span data-ttu-id="cc9bf-112">Passaggi</span><span class="sxs-lookup"><span data-stu-id="cc9bf-112">Steps</span></span></th>
<th><span data-ttu-id="cc9bf-113">Appartenenze a gruppi e ruoli richiesti</span><span class="sxs-lookup"><span data-stu-id="cc9bf-113">Required roles and group memberships</span></span></th>
<th><span data-ttu-id="cc9bf-114">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="cc9bf-114">Related topics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cc9bf-115"><strong>Installare l'hardware e il software prerequisiti</strong></span><span class="sxs-lookup"><span data-stu-id="cc9bf-115"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="cc9bf-116">Nell'hardware che soddisfa i requisiti di sistema installare gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="cc9bf-116">On hardware that meets system requirements, install the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="cc9bf-117">Nei front end server di Persistent Chat:</span><span class="sxs-lookup"><span data-stu-id="cc9bf-117">On the Persistent Chat Server Front End Servers:</span></span></p></li>
</ul>
<ul>
<li><p><span data-ttu-id="cc9bf-118">Sistema operativo che soddisfa i requisiti di sistema seguenti</span><span class="sxs-lookup"><span data-stu-id="cc9bf-118">An operating system that meets system requirements</span></span></p></li>
<li><p><span data-ttu-id="cc9bf-119">Prerequisiti software per i computer in cui è in esecuzione Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc9bf-119">Software prerequisites for computers running Lync Server 2013</span></span></p></li>
<li><p><span data-ttu-id="cc9bf-120">SQL Server nel server che ospiterà il database del server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="cc9bf-120">SQL Server on the server that will host Persistent Chat Server database</span></span></p></li>
</ul>
<p><span data-ttu-id="cc9bf-121">Se è necessaria la conformità del server Chat persistente:</span><span class="sxs-lookup"><span data-stu-id="cc9bf-121">If Persistent Chat Server compliance is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="cc9bf-122">SQL Server nel server che ospiterà il database di conformità del server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="cc9bf-122">SQL Server on the server that will host Persistent Chat Server compliance database</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="cc9bf-123">Tutti gli utenti membri del gruppo Administrators locale.</span><span class="sxs-lookup"><span data-stu-id="cc9bf-123">Any user who is a member of the local Administrators group.</span></span></p></td>
<td><p><span data-ttu-id="cc9bf-124"><a href="lync-server-2013-supported-hardware.md">Hardware supportato per Lync Server 2013</a> nella documentazione relativa alla supportabilità</span><span class="sxs-lookup"><span data-stu-id="cc9bf-124"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="cc9bf-125"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Supporto dell'infrastruttura e del software server in Lync server 2013</a> nella documentazione relativa alla supportabilità</span><span class="sxs-lookup"><span data-stu-id="cc9bf-125"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="cc9bf-126"><a href="lync-server-2013-determining-your-system-requirements.md">Determinazione dei requisiti di sistema per Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cc9bf-126"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="cc9bf-127"><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Requisiti tecnici per il server Chat persistente in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cc9bf-127"><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Technical requirements for Persistent Chat Server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc9bf-128"><strong>Creare la topologia interna appropriata per supportare il server Chat persistente (e, facoltativamente, la conformità chat persistente)</strong></span><span class="sxs-lookup"><span data-stu-id="cc9bf-128"><strong>Create the appropriate internal topology to support Persistent Chat Server (and optionally, Persistent Chat compliance)</strong></span></span></p></td>
<td><p><span data-ttu-id="cc9bf-129">Eseguire Generatore di topologie per aggiungere un pool di server Chat persistente alla topologia:</span><span class="sxs-lookup"><span data-stu-id="cc9bf-129">Run Topology Builder to add a Persistent Chat Server pool to your topology:</span></span></p>
<ul>
<li><p><span data-ttu-id="cc9bf-130">Aggiungere componenti del server Chat persistente alla topologia</span><span class="sxs-lookup"><span data-stu-id="cc9bf-130">Add Persistent Chat Server components to the topology</span></span></p></li>
<li><p><span data-ttu-id="cc9bf-131">Creare un database di SQL Server per l'archivio del server Chat persistente (e un backup di SQL Server per il ripristino di emergenza)</span><span class="sxs-lookup"><span data-stu-id="cc9bf-131">Create a SQL Server database for the Persistent Chat Server store (and a backup SQL Server for disaster recovery)</span></span></p></li>
<li><p><span data-ttu-id="cc9bf-132">Definire un nuovo archivio file di Lync o utilizzare un archivio file di Lync esistente per i file del server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="cc9bf-132">Define a new Lync File Store or use an existing Lync File Store for Persistent Chat Server files</span></span></p></li>
<li><p><span data-ttu-id="cc9bf-133">Associare il pool di Lync Server 2013 in grado di instradare le richieste al pool di server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="cc9bf-133">Associate the Lync Server 2013 pool that can route requests to this Persistent Chat Server pool</span></span></p></li>
</ul>
<p><span data-ttu-id="cc9bf-134">Se è necessaria la conformità della chat persistente:</span><span class="sxs-lookup"><span data-stu-id="cc9bf-134">If Persistent Chat compliance is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="cc9bf-135">Aggiungere l'archivio di conformità di chat persistente</span><span class="sxs-lookup"><span data-stu-id="cc9bf-135">Add Persistent Chat Compliance Store</span></span></p></li>
<li><p><span data-ttu-id="cc9bf-136">Fare clic sulla casella di controllo definizione pool di server Chat persistente per abilitare la conformità</span><span class="sxs-lookup"><span data-stu-id="cc9bf-136">Click the Persistent Chat Server pool definition check box for enabling compliance</span></span></p></li>
<li><p><span data-ttu-id="cc9bf-137">Pubblicare la topologia</span><span class="sxs-lookup"><span data-stu-id="cc9bf-137">Publish the topology</span></span></p></li>
</ul>
<p><span data-ttu-id="cc9bf-138">Se si installa il server Chat persistente in Standard Edition, il nome di dominio completo (FQDN) del pool del server di chat persistente deve corrispondere al server Standard Edition e i database di SQL Server sono collocati nell'istanza di SQL Server Express nello standard Server Edition</span><span class="sxs-lookup"><span data-stu-id="cc9bf-138">If you install Persistent Chat Server on Standard Edition, the fully qualified domain name (FQDN) of the Persistent Chat Server pool must match the Standard Edition server, and the SQL Server databases are collocated on the SQL Server Express instance on the Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="cc9bf-139">Per definire una topologia, un account membro del gruppo Users locale.</span><span class="sxs-lookup"><span data-stu-id="cc9bf-139">To define a topology, an account that is a member of the local Users group.</span></span></p>
<p><span data-ttu-id="cc9bf-140">Per pubblicare la topologia, un account membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins e l'utente deve disporre anche di autorizzazioni di controllo completo (lettura/scrittura/modifica) nell'archivio file di Lync per i file del server Chat persistente, in modo che il generatore di topologie possa configurare gli elenchi DACL necessari.</span><span class="sxs-lookup"><span data-stu-id="cc9bf-140">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and the user should also have full control permissions (read/write/modify) on the Lync File Store for Persistent Chat Server files (so that Topology Builder can configure the required DACLs).</span></span></p></td>
<td><p><span data-ttu-id="cc9bf-141"><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Aggiunta del server Chat persistente alla distribuzione in Lync server 2013</a> nella documentazione relativa alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="cc9bf-141"><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc9bf-142"><strong>Distribuire il server Chat persistente</strong></span><span class="sxs-lookup"><span data-stu-id="cc9bf-142"><strong>Deploy Persistent Chat Server</strong></span></span></p></td>
<td><p><span data-ttu-id="cc9bf-143">Eseguire il programma di installazione di Lync Server in tutti i computer che eseguono il server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="cc9bf-143">Run the Lync Server setup on all the computers running Persistent Chat Server.</span></span> <span data-ttu-id="cc9bf-144">La configurazione del server Chat persistente è integrata nella distribuzione guidata di Lync Server 2013 che fornisce le istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cc9bf-144">The Persistent Chat Server setup is integrated into the Lync Server 2013 Deployment wizard that provides the following instructions:</span></span></p>
<ul>
<li><p><span data-ttu-id="cc9bf-145">Distribuire l'archivio di gestione locale</span><span class="sxs-lookup"><span data-stu-id="cc9bf-145">Deploy local management store</span></span></p></li>
<li><p><span data-ttu-id="cc9bf-146">Installare i servizi del server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="cc9bf-146">Install Persistent Chat Server services</span></span></p></li>
<li><p><span data-ttu-id="cc9bf-147">Richiedere e assegnare i certificati</span><span class="sxs-lookup"><span data-stu-id="cc9bf-147">Request and assign certificates</span></span></p></li>
<li><p><span data-ttu-id="cc9bf-148">Eseguire e avviare i servizi</span><span class="sxs-lookup"><span data-stu-id="cc9bf-148">Run and start the services</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="cc9bf-149">Tutti gli utenti membri del gruppo Administrators locale.</span><span class="sxs-lookup"><span data-stu-id="cc9bf-149">Any user who is a member of the local Administrators group.</span></span></p></td>
<td><p><span data-ttu-id="cc9bf-150"><a href="lync-server-2013-deploying-persistent-chat-server.md">Distribuzione del server Chat persistente in Lync server 2013</a> nella documentazione relativa alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="cc9bf-150"><a href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc9bf-151"><strong>Creare un amministratore di chat persistente</strong></span><span class="sxs-lookup"><span data-stu-id="cc9bf-151"><strong>Create a Persistent Chat administrator</strong></span></span></p></td>
<td><p><span data-ttu-id="cc9bf-152">Aggiungere gli utenti al gruppo di sicurezza CsPersistentChatAdministrator.</span><span class="sxs-lookup"><span data-stu-id="cc9bf-152">Add users to the CsPersistentChatAdministrator security group.</span></span></p></td>
<td><p><span data-ttu-id="cc9bf-153">Tutti gli utenti membri del gruppo degli amministratori di dominio.</span><span class="sxs-lookup"><span data-stu-id="cc9bf-153">Any user who is a member of domain administrators.</span></span></p></td>
<td><p><span data-ttu-id="cc9bf-154"><a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Aggiunta di un amministratore di chat persistente in Lync Server 2013</a> nella documentazione relativa alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="cc9bf-154"><a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Adding a Persistent Chat administrator in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc9bf-155"><strong>Configurare il server chat persistente</strong></span><span class="sxs-lookup"><span data-stu-id="cc9bf-155"><strong>Configure Persistent Chat Server</strong></span></span></p></td>
<td><p><span data-ttu-id="cc9bf-156">Configurare gli utenti:</span><span class="sxs-lookup"><span data-stu-id="cc9bf-156">Configure users:</span></span></p>
<ul>
<li><p><span data-ttu-id="cc9bf-157">L'utente deve essere abilitato dai criteri per accedere al server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="cc9bf-157">User has to be enabled by policy to access Persistent Chat Server.</span></span> <span data-ttu-id="cc9bf-158">Per impostazione predefinita, i criteri sono disattivati per tutti gli utenti e possono essere definiti nell'ambito globale, del sito, del pool e dell'utente</span><span class="sxs-lookup"><span data-stu-id="cc9bf-158">By default, the policy is turned off for all users and can be defined at global/site/pool/user scopes.</span></span></p></li>
<li><p><span data-ttu-id="cc9bf-159">Configurare le impostazioni</span><span class="sxs-lookup"><span data-stu-id="cc9bf-159">Configure settings</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="cc9bf-p104">L'utente deve essere membro di CsPersistentChatAdministrator. Per modificare i criteri, l'utente deve essere almeno membro di CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="cc9bf-p104">User must be a member of CsPersistentChatAdministrator. To change policy, user must be in CsUserAdministrator, at a minimum.</span></span></p></td>
<td><p><span data-ttu-id="cc9bf-162"><a href="lync-server-2013-configuring-persistent-chat-server.md">Configurazione del server Chat persistente in Lync server 2013</a> nella documentazione relativa alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="cc9bf-162"><a href="lync-server-2013-configuring-persistent-chat-server.md">Configuring Persistent Chat Server in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="cc9bf-163">È possibile distribuire uno o più pool di server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="cc9bf-163">You can deploy one or more Persistent Chat Server pools.</span></span> <span data-ttu-id="cc9bf-164">Sono supportati più pool di server Chat persistente per motivi normativi per i quali è necessario che i dati generati in un'area geografica siano presenti in tale area.</span><span class="sxs-lookup"><span data-stu-id="cc9bf-164">We support multiple Persistent Chat Server pools for regulatory reasons whereby data generated in a given region is required to stay in that region.</span></span> <span data-ttu-id="cc9bf-165">Ad esempio, se si distribuisce un pool di server Chat persistente a Chicago e un altro a Zurigo per conformarsi alle normative per i dati svizzeri, gli utenti possono connettersi alle chat room in entrambi i pool di server con persistent, a condizione che dispongano dell'accesso.</span><span class="sxs-lookup"><span data-stu-id="cc9bf-165">For example, if you deploy a Persistent Chat Server pool in Chicago, and another in Zurich to comply with regulations for data in Switzerland, users can connect to rooms in both the Persistent Chat Server pools, provided they have access.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Elenco di controllo di distribuzione per il server Chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for Persistent Chat Server
ms:assetid: b1108f8f-88a2-4660-8086-d25ba76f7239
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412851(v=OCS.15)
ms:contentKeyID: 48185155
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e539a1aa6883863228aaab19ddaa38300ae45591
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984797"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="80131-102">Elenco di controllo di distribuzione per il server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80131-102">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80131-103">_**Argomento Ultima modifica:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="80131-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="80131-104">Distribuzione di Lync Server 2013, il server di chat persistente richiede di distribuirlo nella sequenza corretta e di completare tutti i passaggi necessari per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="80131-104">Deployment of Lync Server 2013, Persistent Chat Server requires that you deploy it in the correct sequence and that you complete all required deployment steps.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="80131-105">Sequenza di distribuzione</span><span class="sxs-lookup"><span data-stu-id="80131-105">Deployment Sequence</span></span>

<span data-ttu-id="80131-106">È possibile distribuire il server di chat persistente dopo la distribuzione della topologia iniziale, incluso almeno un Lync Server 2013, un pool Front end o un Lync Server 2013, un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="80131-106">You can deploy Persistent Chat Server after you deploy your initial topology, including at least one Lync Server 2013, Front End pool or one Lync Server 2013, Standard Edition server.</span></span> <span data-ttu-id="80131-107">Questo argomento descrive come distribuire il server di chat persistente aggiungendolo a una distribuzione esistente.</span><span class="sxs-lookup"><span data-stu-id="80131-107">This topic describes how to deploy Persistent Chat Server by adding it to an existing deployment.</span></span>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="80131-108">Processo di distribuzione</span><span class="sxs-lookup"><span data-stu-id="80131-108">Deployment Process</span></span>

<span data-ttu-id="80131-109">La tabella seguente elenca i passaggi di base per distribuire il server di chat persistente e fornisce collegamenti per ulteriori dettagli.</span><span class="sxs-lookup"><span data-stu-id="80131-109">The following table lists the basic steps to deploy Persistent Chat Server and provides links for more details.</span></span>

### <a name="persistent-chat-server-deployment-process"></a><span data-ttu-id="80131-110">Processo di distribuzione del server di chat persistente</span><span class="sxs-lookup"><span data-stu-id="80131-110">Persistent Chat Server Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="80131-111">Attività</span><span class="sxs-lookup"><span data-stu-id="80131-111">Task</span></span></th>
<th><span data-ttu-id="80131-112">Passaggi</span><span class="sxs-lookup"><span data-stu-id="80131-112">Steps</span></span></th>
<th><span data-ttu-id="80131-113">Ruoli obbligatori e appartenenze ai gruppi</span><span class="sxs-lookup"><span data-stu-id="80131-113">Required roles and group memberships</span></span></th>
<th><span data-ttu-id="80131-114">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="80131-114">Related topics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="80131-115"><strong>Installare hardware e software prerequisiti</strong></span><span class="sxs-lookup"><span data-stu-id="80131-115"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="80131-116">Sull'hardware che soddisfa i requisiti di sistema, installare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="80131-116">On hardware that meets system requirements, install the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="80131-117">Nei server front end del server di chat persistente:</span><span class="sxs-lookup"><span data-stu-id="80131-117">On the Persistent Chat Server Front End Servers:</span></span></p></li>
</ul>
<ul>
<li><p><span data-ttu-id="80131-118">Sistema operativo che soddisfa i requisiti di sistema</span><span class="sxs-lookup"><span data-stu-id="80131-118">An operating system that meets system requirements</span></span></p></li>
<li><p><span data-ttu-id="80131-119">Prerequisiti software per i computer che eseguono Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80131-119">Software prerequisites for computers running Lync Server 2013</span></span></p></li>
<li><p><span data-ttu-id="80131-120">SQL Server nel server che ospiterà il database del server di chat persistente</span><span class="sxs-lookup"><span data-stu-id="80131-120">SQL Server on the server that will host Persistent Chat Server database</span></span></p></li>
</ul>
<p><span data-ttu-id="80131-121">Se è necessaria la conformità del server di chat persistente:</span><span class="sxs-lookup"><span data-stu-id="80131-121">If Persistent Chat Server compliance is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="80131-122">SQL Server nel server che ospita il database di conformità del server di chat persistente</span><span class="sxs-lookup"><span data-stu-id="80131-122">SQL Server on the server that will host Persistent Chat Server compliance database</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="80131-123">Qualsiasi utente membro del gruppo Administrators locale.</span><span class="sxs-lookup"><span data-stu-id="80131-123">Any user who is a member of the local Administrators group.</span></span></p></td>
<td><p><span data-ttu-id="80131-124"><a href="lync-server-2013-supported-hardware.md">Hardware supportato per Lync Server 2013</a> nella documentazione relativa alla supportabilità</span><span class="sxs-lookup"><span data-stu-id="80131-124"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="80131-125"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Supporto di software e infrastrutture server in Lync server 2013</a> nella documentazione relativa al supporto tecnico</span><span class="sxs-lookup"><span data-stu-id="80131-125"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="80131-126"><a href="lync-server-2013-determining-your-system-requirements.md">Determinazione dei requisiti di sistema per Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="80131-126"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="80131-127"><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Requisiti tecnici per il server di chat persistente in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="80131-127"><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Technical requirements for Persistent Chat Server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80131-128"><strong>Creare la topologia interna appropriata per supportare il server di chat persistente e, facoltativamente, la conformità della chat persistente</strong></span><span class="sxs-lookup"><span data-stu-id="80131-128"><strong>Create the appropriate internal topology to support Persistent Chat Server (and optionally, Persistent Chat compliance)</strong></span></span></p></td>
<td><p><span data-ttu-id="80131-129">Eseguire Generatore di topologie per aggiungere un pool di server di chat persistente alla topologia:</span><span class="sxs-lookup"><span data-stu-id="80131-129">Run Topology Builder to add a Persistent Chat Server pool to your topology:</span></span></p>
<ul>
<li><p><span data-ttu-id="80131-130">Aggiungere componenti del server di chat persistenti alla topologia</span><span class="sxs-lookup"><span data-stu-id="80131-130">Add Persistent Chat Server components to the topology</span></span></p></li>
<li><p><span data-ttu-id="80131-131">Creare un database di SQL Server per l'archivio di Chat Server persistente (e un backup di SQL Server per il ripristino di emergenza)</span><span class="sxs-lookup"><span data-stu-id="80131-131">Create a SQL Server database for the Persistent Chat Server store (and a backup SQL Server for disaster recovery)</span></span></p></li>
<li><p><span data-ttu-id="80131-132">Definire un nuovo archivio di file di Lync o usare un archivio file di Lync esistente per i file del server di chat persistente</span><span class="sxs-lookup"><span data-stu-id="80131-132">Define a new Lync File Store or use an existing Lync File Store for Persistent Chat Server files</span></span></p></li>
<li><p><span data-ttu-id="80131-133">Associare il pool di Lync Server 2013 che può instradare le richieste a questo pool di server di chat persistente</span><span class="sxs-lookup"><span data-stu-id="80131-133">Associate the Lync Server 2013 pool that can route requests to this Persistent Chat Server pool</span></span></p></li>
</ul>
<p><span data-ttu-id="80131-134">Se è necessaria la conformità della chat persistente:</span><span class="sxs-lookup"><span data-stu-id="80131-134">If Persistent Chat compliance is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="80131-135">Aggiungere lo Store di conformità della chat persistente</span><span class="sxs-lookup"><span data-stu-id="80131-135">Add Persistent Chat Compliance Store</span></span></p></li>
<li><p><span data-ttu-id="80131-136">Fare clic sulla casella di controllo della definizione del pool di Persistent Chat Server per abilitare la conformità</span><span class="sxs-lookup"><span data-stu-id="80131-136">Click the Persistent Chat Server pool definition check box for enabling compliance</span></span></p></li>
<li><p><span data-ttu-id="80131-137">Pubblicare la topologia</span><span class="sxs-lookup"><span data-stu-id="80131-137">Publish the topology</span></span></p></li>
</ul>
<p><span data-ttu-id="80131-138">Se si installa il server di chat persistente in Standard Edition, il nome di dominio completo (FQDN) del pool del server di chat persistente deve corrispondere al server Standard Edition e i database di SQL Server sono collocati nell'istanza di SQL Server Express nello standard Server Edition</span><span class="sxs-lookup"><span data-stu-id="80131-138">If you install Persistent Chat Server on Standard Edition, the fully qualified domain name (FQDN) of the Persistent Chat Server pool must match the Standard Edition server, and the SQL Server databases are collocated on the SQL Server Express instance on the Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="80131-139">Per definire una topologia, un account membro del gruppo utenti locali.</span><span class="sxs-lookup"><span data-stu-id="80131-139">To define a topology, an account that is a member of the local Users group.</span></span></p>
<p><span data-ttu-id="80131-140">Per pubblicare la topologia, un account che sia un membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins e che l'utente disponga anche delle autorizzazioni di controllo completo (lettura/scrittura/modifica) nell'archivio di file di Lync per i file del server di chat permanenti, in modo che il generatore di topologia possa configurare gli elenchi DACL necessari.</span><span class="sxs-lookup"><span data-stu-id="80131-140">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and the user should also have full control permissions (read/write/modify) on the Lync File Store for Persistent Chat Server files (so that Topology Builder can configure the required DACLs).</span></span></p></td>
<td><p><span data-ttu-id="80131-141"><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Aggiunta di un server di chat persistente alla distribuzione in Lync Server 2013</a> nella documentazione relativa alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="80131-141"><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80131-142"><strong>Distribuire il server Chat persistente</strong></span><span class="sxs-lookup"><span data-stu-id="80131-142"><strong>Deploy Persistent Chat Server</strong></span></span></p></td>
<td><p><span data-ttu-id="80131-143">Eseguire la configurazione di Lync Server in tutti i computer che eseguono il server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="80131-143">Run the Lync Server setup on all the computers running Persistent Chat Server.</span></span> <span data-ttu-id="80131-144">La configurazione del server di chat persistente è integrata nella distribuzione guidata di Lync Server 2013 che fornisce le istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="80131-144">The Persistent Chat Server setup is integrated into the Lync Server 2013 Deployment wizard that provides the following instructions:</span></span></p>
<ul>
<li><p><span data-ttu-id="80131-145">Distribuire l'archivio di gestione locale</span><span class="sxs-lookup"><span data-stu-id="80131-145">Deploy local management store</span></span></p></li>
<li><p><span data-ttu-id="80131-146">Installare i servizi server di chat persistenti</span><span class="sxs-lookup"><span data-stu-id="80131-146">Install Persistent Chat Server services</span></span></p></li>
<li><p><span data-ttu-id="80131-147">Richiedere e assegnare certificati</span><span class="sxs-lookup"><span data-stu-id="80131-147">Request and assign certificates</span></span></p></li>
<li><p><span data-ttu-id="80131-148">Eseguire e avviare i servizi</span><span class="sxs-lookup"><span data-stu-id="80131-148">Run and start the services</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="80131-149">Qualsiasi utente membro del gruppo Administrators locale.</span><span class="sxs-lookup"><span data-stu-id="80131-149">Any user who is a member of the local Administrators group.</span></span></p></td>
<td><p><span data-ttu-id="80131-150"><a href="lync-server-2013-deploying-persistent-chat-server.md">Distribuzione di un server di chat persistente in Lync server 2013</a> nella documentazione di distribuzione</span><span class="sxs-lookup"><span data-stu-id="80131-150"><a href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80131-151"><strong>Creare un amministratore di Chat persistente</strong></span><span class="sxs-lookup"><span data-stu-id="80131-151"><strong>Create a Persistent Chat administrator</strong></span></span></p></td>
<td><p><span data-ttu-id="80131-152">Aggiungere utenti al gruppo di sicurezza CsPersistentChatAdministrator.</span><span class="sxs-lookup"><span data-stu-id="80131-152">Add users to the CsPersistentChatAdministrator security group.</span></span></p></td>
<td><p><span data-ttu-id="80131-153">Qualsiasi utente membro di Domain Administrators.</span><span class="sxs-lookup"><span data-stu-id="80131-153">Any user who is a member of domain administrators.</span></span></p></td>
<td><p><span data-ttu-id="80131-154"><a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Aggiunta di un amministratore di chat persistente in Lync Server 2013</a> nella documentazione di distribuzione</span><span class="sxs-lookup"><span data-stu-id="80131-154"><a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Adding a Persistent Chat administrator in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80131-155"><strong>Configurare il server Chat persistente</strong></span><span class="sxs-lookup"><span data-stu-id="80131-155"><strong>Configure Persistent Chat Server</strong></span></span></p></td>
<td><p><span data-ttu-id="80131-156">Configurare gli utenti:</span><span class="sxs-lookup"><span data-stu-id="80131-156">Configure users:</span></span></p>
<ul>
<li><p><span data-ttu-id="80131-157">L'utente deve essere abilitato tramite criteri per accedere al server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="80131-157">User has to be enabled by policy to access Persistent Chat Server.</span></span> <span data-ttu-id="80131-158">Per impostazione predefinita, il criterio è disattivato per tutti gli utenti e può essere definito in ambito globale/sito/pool/User.</span><span class="sxs-lookup"><span data-stu-id="80131-158">By default, the policy is turned off for all users and can be defined at global/site/pool/user scopes.</span></span></p></li>
<li><p><span data-ttu-id="80131-159">Configurare le impostazioni</span><span class="sxs-lookup"><span data-stu-id="80131-159">Configure settings</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="80131-160">L'utente deve essere un membro di CsPersistentChatAdministrator.</span><span class="sxs-lookup"><span data-stu-id="80131-160">User must be a member of CsPersistentChatAdministrator.</span></span> <span data-ttu-id="80131-161">Per modificare i criteri, l'utente deve essere in CsUserAdministrator, almeno.</span><span class="sxs-lookup"><span data-stu-id="80131-161">To change policy, user must be in CsUserAdministrator, at a minimum.</span></span></p></td>
<td><p><span data-ttu-id="80131-162"><a href="lync-server-2013-configuring-persistent-chat-server.md">Configurazione del server di chat persistente in Lync server 2013</a> nella documentazione di distribuzione</span><span class="sxs-lookup"><span data-stu-id="80131-162"><a href="lync-server-2013-configuring-persistent-chat-server.md">Configuring Persistent Chat Server in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="80131-163">È possibile distribuire uno o più pool di server di chat permanenti.</span><span class="sxs-lookup"><span data-stu-id="80131-163">You can deploy one or more Persistent Chat Server pools.</span></span> <span data-ttu-id="80131-164">Supportiamo più pool di server di chat persistenti per motivi normativi per cui i dati generati in una determinata area geografica devono rimanere in quell'area geografica.</span><span class="sxs-lookup"><span data-stu-id="80131-164">We support multiple Persistent Chat Server pools for regulatory reasons whereby data generated in a given region is required to stay in that region.</span></span> <span data-ttu-id="80131-165">Ad esempio, se si distribuisce un pool di server di chat persistente a Chicago e un altro a Zurigo per conformarsi alle normative per i dati in Svizzera, gli utenti possono connettersi alle camere in entrambi i pool di server della chat persistente, purché abbiano accesso.</span><span class="sxs-lookup"><span data-stu-id="80131-165">For example, if you deploy a Persistent Chat Server pool in Chicago, and another in Zurich to comply with regulations for data in Switzerland, users can connect to rooms in both the Persistent Chat Server pools, provided they have access.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


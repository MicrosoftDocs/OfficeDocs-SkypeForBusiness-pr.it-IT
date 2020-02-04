---
title: "Lync Server 2013: Elenco di controllo di distribuzione per l'archiviazione"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for Archiving
ms:assetid: 7479734d-be01-40d9-ad82-320a09d19d04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205009(v=OCS.15)
ms:contentKeyID: 48184516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e55e2471a71c985861c35c4ec2e07582dbfa0f23
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740756"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-archiving-in-lync-server-2013"></a><span data-ttu-id="7333a-102">Elenco di controllo di distribuzione per l'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7333a-102">Deployment checklist for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7333a-103">_**Argomento Ultima modifica:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="7333a-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="7333a-104">L'archiviazione viene installata automaticamente in ogni server front-end nella distribuzione di Lync Server 2013, ma è comunque necessario configurarla prima di poterla usare.</span><span class="sxs-lookup"><span data-stu-id="7333a-104">Archiving is automatically installed on each Front End Server in your Lync Server 2013 deployment, but you still need to set it up before you can use it.</span></span> <span data-ttu-id="7333a-105">I passaggi necessari per configurarla, come riepilogati in questa sezione, costituiscono la distribuzione dell'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="7333a-105">The steps required to set it up, as summarized in this section, constitute the deployment of Archiving.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="7333a-106">Sequenza di distribuzione</span><span class="sxs-lookup"><span data-stu-id="7333a-106">Deployment Sequence</span></span>

<span data-ttu-id="7333a-107">La modalità di configurazione dell'archiviazione dipende dall'opzione di archiviazione scelta:</span><span class="sxs-lookup"><span data-stu-id="7333a-107">How you set up Archiving depends on which storage option you choose:</span></span>

  - <span data-ttu-id="7333a-108">Se si usa l'integrazione di Microsoft Exchange per tutti gli utenti della distribuzione, non è necessario configurare i criteri di archiviazione di Lync Server 2013 per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="7333a-108">If you use Microsoft Exchange integration for all users in your deployment, you don’t need to configure Lync Server 2013 Archiving policies for your users.</span></span> <span data-ttu-id="7333a-109">Configurare invece i criteri di blocco sul posto di Exchange per supportare l'archiviazione per gli utenti ospitati in Exchange 2013, con le cassette postali inserite sul posto.</span><span class="sxs-lookup"><span data-stu-id="7333a-109">Instead, configure your Exchange In-Place Hold policies to support archiving for users homed on Exchange 2013, with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="7333a-110">Per informazioni dettagliate sulla configurazione di questi criteri, vedere la documentazione del prodotto Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="7333a-110">For details about configuring these policies, see the Exchange 2013 product documentation.</span></span>

  - <span data-ttu-id="7333a-111">Se non si usa l'integrazione di Microsoft Exchange per tutti gli utenti della distribuzione, è necessario aggiungere i database di archiviazione di Lync Server (database di SQL Server) alla topologia e quindi pubblicarlo, nonché configurare i criteri e le impostazioni per gli utenti, prima di poter archiviare i dati per tali utenti.</span><span class="sxs-lookup"><span data-stu-id="7333a-111">If you do not use Microsoft Exchange integration for all users in your deployment, you need to add Lync Server Archiving databases (SQL Server databases) to your topology and then publish it, as well as configure policies and settings for your users, before you can archive data for those users.</span></span> <span data-ttu-id="7333a-112">È possibile distribuire i database di archiviazione contemporaneamente alla distribuzione della topologia iniziale o dopo avere distribuito almeno un pool di front-end o un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="7333a-112">You can deploy Archiving databases at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span> <span data-ttu-id="7333a-113">Questo documento descrive come distribuire i database di archiviazione aggiungendoli a una distribuzione esistente.</span><span class="sxs-lookup"><span data-stu-id="7333a-113">This document describes how to deploy Archiving databases by adding them to an existing deployment.</span></span>

<span data-ttu-id="7333a-114">Se si Abilita l'archiviazione in un pool Front-end o in un server Standard Edition, è consigliabile abilitarlo per tutti gli altri pool Front end e i server Standard Edition nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="7333a-114">If you enable archiving in one Front End pool or Standard Edition server, you should enable it for all other Front End pools and Standard Edition servers in your deployment.</span></span> <span data-ttu-id="7333a-115">Il motivo è che gli utenti le cui comunicazioni devono essere archiviati possono essere invitati a una conversazione di messaggistica istantanea di gruppo o a riunioni ospitate in un pool diverso.</span><span class="sxs-lookup"><span data-stu-id="7333a-115">This is because users whose communications are required to be archived can be invited to a group IM conversation or meetings hosted on a different pool.</span></span> <span data-ttu-id="7333a-116">Se l'archiviazione non è abilitata nel pool in cui è ospitata la conversazione o la riunione, la sessione completa potrebbe non essere archiviata.</span><span class="sxs-lookup"><span data-stu-id="7333a-116">If archiving is not enabled on the pool where the conversation or meeting is hosted, the complete session may not be archived.</span></span> <span data-ttu-id="7333a-117">In questi casi, è ancora possibile archiviare messaggi istantanei con utenti abilitati all'archiviazione, ma non per i file di contenuto di conferenza e gli eventi di conferenza o di uscita.</span><span class="sxs-lookup"><span data-stu-id="7333a-117">In these cases, IMs with archiving-enabled users still can be archived, but not for conferencing content files, and conference join or leave events.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7333a-118">Se l'archiviazione è fondamentale per i motivi di conformità dell'organizzazione, assicurarsi di distribuire l'archiviazione, configurare i criteri e altre opzioni a livello appropriato e abilitarla per tutti gli utenti appropriati prima di abilitare gli utenti per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7333a-118">If archiving is critical in your organization for compliance reasons, be sure to deploy Archiving, configure policies and other options at the appropriate level, and enable it for all appropriate users, before you enable those users for Lync Server 2013.</span></span>



</div>

</div>

<div>

## <a name="archiving-deployment-process"></a><span data-ttu-id="7333a-119">Processo di distribuzione dell'archiviazione</span><span class="sxs-lookup"><span data-stu-id="7333a-119">Archiving Deployment Process</span></span>

<span data-ttu-id="7333a-120">La tabella seguente offre una panoramica dei passaggi necessari per distribuire l'archiviazione in una topologia esistente.</span><span class="sxs-lookup"><span data-stu-id="7333a-120">The following table provides an overview of the steps required to deploy archiving in an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7333a-121">Fase</span><span class="sxs-lookup"><span data-stu-id="7333a-121">Phase</span></span></th>
<th><span data-ttu-id="7333a-122">Passaggi</span><span class="sxs-lookup"><span data-stu-id="7333a-122">Steps</span></span></th>
<th><span data-ttu-id="7333a-123">Ruoli e appartenenze ai gruppi</span><span class="sxs-lookup"><span data-stu-id="7333a-123">Roles and group memberships</span></span></th>
<th><span data-ttu-id="7333a-124">Documentazione</span><span class="sxs-lookup"><span data-stu-id="7333a-124">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7333a-125"><strong>Installare hardware e software prerequisiti</strong></span><span class="sxs-lookup"><span data-stu-id="7333a-125"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7333a-126">Per usare l'integrazione di Microsoft Exchange (usando Exchange 2013 per l'archiviazione dello spazio di archiviazione per alcuni o tutti gli utenti), è necessaria una distribuzione di Exchange 2013 esistente.</span><span class="sxs-lookup"><span data-stu-id="7333a-126">To use Microsoft Exchange integration (using Exchange 2013 for archiving storage for some or all users), you need an existing Exchange 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="7333a-127">Per usare database di archiviazione distinti (tramite database di SQL Server) per l'archiviazione dello spazio di archiviazione per alcuni o tutti gli utenti, SQL Server nel server in cui verranno archiviati i dati di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="7333a-127">To use separate Archiving databases (using SQL Server databases) for archiving storage for some or all users, SQL Server on the server that will store archiving data.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="7333a-128">L'archiviazione viene eseguita nei server front-end di un pool Enterprise e di server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="7333a-128">Archiving runs on Front End Servers of an Enterprise pool and Standard Edition servers.</span></span> <span data-ttu-id="7333a-129">Non ha requisiti hardware o software aggiuntivi oltre a ciò che è necessario per installare tali server.</span><span class="sxs-lookup"><span data-stu-id="7333a-129">It has no additional hardware or software requirements beyond what is required to install those servers.</span></span>


</div></td>
<td><p><span data-ttu-id="7333a-130">Utente del dominio che è un membro del gruppo Administrators locale.</span><span class="sxs-lookup"><span data-stu-id="7333a-130">Domain user who is a member of the local administrators group.</span></span></p></td>
<td><p><span data-ttu-id="7333a-131"><a href="lync-server-2013-supported-hardware.md">Hardware supportato per Lync Server 2013</a> nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="7333a-131"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation.</span></span></p>
<p><span data-ttu-id="7333a-132"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Supporto di software e infrastrutture server in Lync server 2013</a> nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="7333a-132"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation.</span></span></p>
<p><span data-ttu-id="7333a-133"><a href="lync-server-2013-technical-requirements-for-archiving.md">Requisiti tecnici per l'archiviazione in Lync Server 2013</a> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="7333a-133"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="7333a-134"><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Configurazione di sistemi e infrastrutture per l'archiviazione in Lync Server 2013</a> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="7333a-134"><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Setting up systems and infrastructure for Archiving in Lync Server 2013</a> in the Deployment documentation.</span></span></p>
<p><span data-ttu-id="7333a-135"><a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Supporto di Exchange Server e integrazione di SharePoint in Lync server 2013</a> nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="7333a-135"><a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Exchange Server and SharePoint integration support in Lync Server 2013</a> in the Supportability documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7333a-136"><strong>Creare la topologia interna appropriata per supportare l'archiviazione (solo se non si usa l'integrazione di Microsoft Exchange per tutti gli utenti della distribuzione)</strong></span><span class="sxs-lookup"><span data-stu-id="7333a-136"><strong>Create the appropriate internal topology to support archiving (only if not using Microsoft Exchange integration for all users in your deployment)</strong></span></span></p></td>
<td><p><span data-ttu-id="7333a-137">Eseguire Generatore di topologia per aggiungere i database di archiviazione di Lync Server 2013 (database di SQL Server) alla topologia e quindi pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="7333a-137">Run Topology Builder to add Lync Server 2013 Archiving databases (SQL Server databases) to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="7333a-138">Per definire una topologia per incorporare i database di archiviazione, un account membro del gruppo utenti locali.</span><span class="sxs-lookup"><span data-stu-id="7333a-138">To define a topology to incorporate Archiving databases, an account that is a member of the local users group.</span></span></p>
<p><span data-ttu-id="7333a-139">Per pubblicare la topologia, un account che sia un membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins e che disponga delle autorizzazioni controllo completo (lettura/scrittura/modifica) nella condivisione file da usare per l'archivio di file di Lync Server 2013 (in modo che il generatore di topologia possa configurare gli elenchi DACL necessari).</span><span class="sxs-lookup"><span data-stu-id="7333a-139">To publish the topology, an account that is a member of the domain admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs).</span></span></p></td>
<td><p><span data-ttu-id="7333a-140"><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">Aggiunta di database di archiviazione a una distribuzione di Lync Server 2013 esistente</a> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="7333a-140"><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">Adding Archiving databases to an existing Lync Server 2013 Deployment</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7333a-141"><strong>Configurare l'autenticazione da server a server (solo se si usa l'integrazione di Microsoft Exchange)</strong></span><span class="sxs-lookup"><span data-stu-id="7333a-141"><strong>Configure server-to-server authentication (only if using Microsoft Exchange integration)</strong></span></span></p></td>
<td><p><span data-ttu-id="7333a-142">Configurare i server per consentire l'autenticazione tra Lync Server 2013 ed Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="7333a-142">Configure servers to enable authentication between Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="7333a-143">È consigliabile eseguire <strong>test-CsExchangeStorageConnectivity testuser_sipUri-dumpster della cartella</strong> per convalidare la connettività di archiviazione dell'archiviazione di Exchange prima di abilitare l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="7333a-143">We recommend running <strong>Test-CsExchangeStorageConnectivity testuser_sipUri –Folder Dumpster</strong> to validate Exchange Archiving storage connectivity before enabling archiving.</span></span></p></td>
<td><p><span data-ttu-id="7333a-144">Un account con le autorizzazioni appropriate per la gestione dei certificati nei server.</span><span class="sxs-lookup"><span data-stu-id="7333a-144">An account with the appropriate permissions for managing certificates on the servers.</span></span></p></td>
<td><p><span data-ttu-id="7333a-145"><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Gestione dell'autenticazione server-Server (OAuth) e delle applicazioni partner in Lync server 2013</a> nella documentazione relativa alla distribuzione o nella documentazione delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="7333a-145"><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</a> in the Deployment documentation or the Operations documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7333a-146"><strong>Configurare i criteri di archiviazione e le configurazioni</strong></span><span class="sxs-lookup"><span data-stu-id="7333a-146"><strong>Configure archiving policies and configurations</strong></span></span></p></td>
<td><p><span data-ttu-id="7333a-147">Configurare l'archiviazione, ad esempio se usare l'integrazione di Microsoft Exchange, i criteri globali e tutti i criteri per i siti e gli utenti (quando non si usa l'integrazione di Microsoft Exchange per tutti gli archivi dati) e le opzioni di archiviazione specifiche, come la modalità critica e i dati esportare ed eliminare.</span><span class="sxs-lookup"><span data-stu-id="7333a-147">Configure archiving, including whether to use Microsoft Exchange integration, the global policy and any site and user policies (when not using Microsoft Exchange integration for all data storage), and specific archiving options, such as critical mode and data export and purging.</span></span></p>
<p><span data-ttu-id="7333a-148">Se si usa l'integrazione di Microsoft Exchange, configurare i criteri di blocco sul posto di Exchange in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="7333a-148">If using Microsoft Exchange integration, configure Exchange In-Place Hold policies as appropriate.</span></span></p></td>
<td><p><span data-ttu-id="7333a-149">Gruppo RTCUniversalServerAdmins (solo Windows PowerShell) o assegna agli utenti il ruolo CSArchivingAdministrator o CSAdministrator.</span><span class="sxs-lookup"><span data-stu-id="7333a-149">RTCUniversalServerAdmins group (Windows PowerShell only) or assign users to the CSArchivingAdministrator or CSAdministrator role.</span></span></p></td>
<td><p><span data-ttu-id="7333a-150"><a href="lync-server-2013-configuring-support-for-archiving.md">Configurazione del supporto per l'archiviazione in Lync Server 2013</a> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="7333a-150"><a href="lync-server-2013-configuring-support-for-archiving.md">Configuring support for Archiving in Lync Server 2013</a> in the Deployment documentation.</span></span></p>
<p><span data-ttu-id="7333a-151">Documentazione del prodotto Exchange (se si usa l'integrazione di Microsoft Exchange).</span><span class="sxs-lookup"><span data-stu-id="7333a-151">Exchange product documentation (if using Microsoft Exchange integration).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="deploying-lync-server-and-microsoft-exchange-in-different-forests"></a><span data-ttu-id="7333a-152">Distribuzione di Lync Server e Microsoft Exchange in foreste diverse</span><span class="sxs-lookup"><span data-stu-id="7333a-152">Deploying Lync Server and Microsoft Exchange in Different Forests</span></span>

<span data-ttu-id="7333a-153">Se Microsoft Exchange Server non è distribuito nella stessa foresta di Lync Server, è necessario verificare che gli attributi di Exchange Active Directory seguenti siano sincronizzati con la foresta in cui è distribuito Lync Server:</span><span class="sxs-lookup"><span data-stu-id="7333a-153">If Microsoft Exchange Server is not deployed in the same forest as Lync Server, you must make sure that the following Exchange Active Directory attributes are synchronized to the forest where Lync Server is deployed:</span></span>

1.  <span data-ttu-id="7333a-154">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="7333a-154">msExchUserHoldPolicies</span></span>

2.  <span data-ttu-id="7333a-155">proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="7333a-155">proxyAddresses</span></span>

<span data-ttu-id="7333a-156">Questo è un attributo multivalore.</span><span class="sxs-lookup"><span data-stu-id="7333a-156">This is a multi-value attribute.</span></span> <span data-ttu-id="7333a-157">Quando si sincronizza questo attributo, è necessario unire i valori, non sostituirli per evitare che i valori esistenti vengano persi.</span><span class="sxs-lookup"><span data-stu-id="7333a-157">When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


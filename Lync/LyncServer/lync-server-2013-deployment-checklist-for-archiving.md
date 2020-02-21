---
title: "Lync Server 2013: elenco di controllo di distribuzione per l'archiviazione"
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
ms.openlocfilehash: 2df74bda74f1b9af01e1c4e73fa2f21b7119363f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-archiving-in-lync-server-2013"></a><span data-ttu-id="18ff4-102">Elenco di controllo di distribuzione per l'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18ff4-102">Deployment checklist for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18ff4-103">_**Ultimo argomento modificato:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="18ff4-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="18ff4-104">L'archiviazione viene automaticamente installata su ogni Front End Server nella distribuzione di Lync Server 2013, ma è comunque necessario configurarla prima di poterla utilizzare.</span><span class="sxs-lookup"><span data-stu-id="18ff4-104">Archiving is automatically installed on each Front End Server in your Lync Server 2013 deployment, but you still need to set it up before you can use it.</span></span> <span data-ttu-id="18ff4-105">I passaggi necessari per la configurazione, riepilogati in questa sezione, costituiscono la distribuzione dell'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="18ff4-105">The steps required to set it up, as summarized in this section, constitute the deployment of Archiving.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="18ff4-106">Sequenza di distribuzione</span><span class="sxs-lookup"><span data-stu-id="18ff4-106">Deployment Sequence</span></span>

<span data-ttu-id="18ff4-107">La modalità di configurazione dell'archiviazione dipende dall'opzione di archiviazione che si seleziona:</span><span class="sxs-lookup"><span data-stu-id="18ff4-107">How you set up Archiving depends on which storage option you choose:</span></span>

  - <span data-ttu-id="18ff4-108">Se si utilizza l'integrazione di Microsoft Exchange per tutti gli utenti nella distribuzione, non è necessario configurare i criteri di archiviazione di Lync Server 2013 per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="18ff4-108">If you use Microsoft Exchange integration for all users in your deployment, you don’t need to configure Lync Server 2013 Archiving policies for your users.</span></span> <span data-ttu-id="18ff4-109">Al contrario, configurare i criteri di conservazione sul posto di Exchange per supportare l'archiviazione per gli utenti ospitati in Exchange 2013, con le cassette postali inserite sul posto.</span><span class="sxs-lookup"><span data-stu-id="18ff4-109">Instead, configure your Exchange In-Place Hold policies to support archiving for users homed on Exchange 2013, with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="18ff4-110">Per informazioni dettagliate sulla configurazione di questi criteri, vedere la documentazione del prodotto Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="18ff4-110">For details about configuring these policies, see the Exchange 2013 product documentation.</span></span>

  - <span data-ttu-id="18ff4-111">Se non si utilizza l'integrazione di Microsoft Exchange per tutti gli utenti nella distribuzione, è necessario aggiungere i database di archiviazione di Lync Server (database di SQL Server) alla topologia e quindi pubblicarli, nonché configurare i criteri e le impostazioni per gli utenti, prima di poter Archivia i dati per tali utenti.</span><span class="sxs-lookup"><span data-stu-id="18ff4-111">If you do not use Microsoft Exchange integration for all users in your deployment, you need to add Lync Server Archiving databases (SQL Server databases) to your topology and then publish it, as well as configure policies and settings for your users, before you can archive data for those users.</span></span> <span data-ttu-id="18ff4-112">È possibile distribuire i database di archiviazione mentre si distribuisce la topologia iniziale o dopo avere distribuito almeno un pool Front End o un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="18ff4-112">You can deploy Archiving databases at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span> <span data-ttu-id="18ff4-113">In questo documento viene illustrato come distribuire database di archiviazione aggiungendoli a una distribuzione esistente.</span><span class="sxs-lookup"><span data-stu-id="18ff4-113">This document describes how to deploy Archiving databases by adding them to an existing deployment.</span></span>

<span data-ttu-id="18ff4-p104">Se si abilita l'archiviazione in un pool Front End o in un server Standard Edition, sarà necessario abilitarla per tutti gli altri pool Front End e server Standard Edition nella distribuzione. Questo è dovuto al fatto che gli utenti di cui devono essere archiviate le comunicazioni possono essere invitati a una conversazione di messaggistica istantanea di gruppo oppure a riunioni ospitate in un altro pool. Se l'archiviazione non è abilitata nel pool in cui viene ospitata la conversazione o la riunione, potrebbe non essere possibile archiviare l'intera sessione. In questi casi, è possibile archiviare la messaggistica istantanea con utenti abilitati per l'archiviazione, ma non per file di contenuto delle conferenze e eventi di accesso o abbandono della conferenza.</span><span class="sxs-lookup"><span data-stu-id="18ff4-p104">If you enable archiving in one Front End pool or Standard Edition server, you should enable it for all other Front End pools and Standard Edition servers in your deployment. This is because users whose communications are required to be archived can be invited to a group IM conversation or meetings hosted on a different pool. If archiving is not enabled on the pool where the conversation or meeting is hosted, the complete session may not be archived. In these cases, IMs with archiving-enabled users still can be archived, but not for conferencing content files, and conference join or leave events.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="18ff4-118">Se l'archiviazione è critica nell'organizzazione per motivi di conformità, assicurarsi di distribuire l'archiviazione, configurare i criteri e altre opzioni al livello appropriato e abilitarla per tutti gli utenti idonei, prima di abilitare tali utenti per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="18ff4-118">If archiving is critical in your organization for compliance reasons, be sure to deploy Archiving, configure policies and other options at the appropriate level, and enable it for all appropriate users, before you enable those users for Lync Server 2013.</span></span>



</div>

</div>

<div>

## <a name="archiving-deployment-process"></a><span data-ttu-id="18ff4-119">Processo di distribuzione dell'archiviazione</span><span class="sxs-lookup"><span data-stu-id="18ff4-119">Archiving Deployment Process</span></span>

<span data-ttu-id="18ff4-120">Nella tabella seguente viene fornita una panoramica dei passaggi da eseguire per distribuire l'archiviazione in una topologia esistente.</span><span class="sxs-lookup"><span data-stu-id="18ff4-120">The following table provides an overview of the steps required to deploy archiving in an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="18ff4-121">Fase</span><span class="sxs-lookup"><span data-stu-id="18ff4-121">Phase</span></span></th>
<th><span data-ttu-id="18ff4-122">Passaggi</span><span class="sxs-lookup"><span data-stu-id="18ff4-122">Steps</span></span></th>
<th><span data-ttu-id="18ff4-123">Ruoli e gruppi a cui è necessario appartenere</span><span class="sxs-lookup"><span data-stu-id="18ff4-123">Roles and group memberships</span></span></th>
<th><span data-ttu-id="18ff4-124">Documentazione</span><span class="sxs-lookup"><span data-stu-id="18ff4-124">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="18ff4-125"><strong>Installare l'hardware e il software prerequisiti</strong></span><span class="sxs-lookup"><span data-stu-id="18ff4-125"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="18ff4-126">Per utilizzare l'integrazione di Microsoft Exchange (utilizzando Exchange 2013 per l'archiviazione di alcuni o tutti gli utenti), è necessaria una distribuzione di Exchange 2013 esistente.</span><span class="sxs-lookup"><span data-stu-id="18ff4-126">To use Microsoft Exchange integration (using Exchange 2013 for archiving storage for some or all users), you need an existing Exchange 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="18ff4-127">Per utilizzare database di archiviazione separati (utilizzando database SQL Server) per l'archiviazione di alcuni o tutti gli utenti, è necessario SQL Server sul server che memorizzerà i dati di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="18ff4-127">To use separate Archiving databases (using SQL Server databases) for archiving storage for some or all users, SQL Server on the server that will store archiving data.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="18ff4-p105">L'archiviazione è eseguita sui server Front End di un pool Enterprise e server Standard Edition. Non esistono ulteriori requisiti di hardware o software oltre a quelli necessari per l'installazione di questi server.</span><span class="sxs-lookup"><span data-stu-id="18ff4-p105">Archiving runs on Front End Servers of an Enterprise pool and Standard Edition servers. It has no additional hardware or software requirements beyond what is required to install those servers.</span></span>


</div></td>
<td><p><span data-ttu-id="18ff4-130">Utente del dominio membro del gruppo Administrators locale</span><span class="sxs-lookup"><span data-stu-id="18ff4-130">Domain user who is a member of the local administrators group.</span></span></p></td>
<td><p><span data-ttu-id="18ff4-131"><a href="lync-server-2013-supported-hardware.md">Hardware supportato per Lync Server 2013</a> nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="18ff4-131"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation.</span></span></p>
<p><span data-ttu-id="18ff4-132"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Supporto dell'infrastruttura e del software server in Lync server 2013</a> nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="18ff4-132"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation.</span></span></p>
<p><span data-ttu-id="18ff4-133"><a href="lync-server-2013-technical-requirements-for-archiving.md">Requisiti tecnici per l'archiviazione in Lync Server 2013</a> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="18ff4-133"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="18ff4-134"><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Configurazione dei sistemi e dell'infrastruttura per l'archiviazione in Lync Server 2013</a> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="18ff4-134"><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Setting up systems and infrastructure for Archiving in Lync Server 2013</a> in the Deployment documentation.</span></span></p>
<p><span data-ttu-id="18ff4-135"><a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Supporto per l'integrazione di Exchange Server e SharePoint in Lync server 2013</a> nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="18ff4-135"><a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Exchange Server and SharePoint integration support in Lync Server 2013</a> in the Supportability documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18ff4-136"><strong>Creare la topologia interna appropriata per supportare l'archiviazione (solo se non si utilizza l'integrazione di Microsoft Exchange per tutti gli utenti nella distribuzione)</strong></span><span class="sxs-lookup"><span data-stu-id="18ff4-136"><strong>Create the appropriate internal topology to support archiving (only if not using Microsoft Exchange integration for all users in your deployment)</strong></span></span></p></td>
<td><p><span data-ttu-id="18ff4-137">Eseguire Generatore di topologie per aggiungere database di archiviazione di Lync Server 2013 (database di SQL Server) alla topologia e quindi pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="18ff4-137">Run Topology Builder to add Lync Server 2013 Archiving databases (SQL Server databases) to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="18ff4-138">Per definire una topologia che incorpori database di archiviazione, un account membro del gruppo Users locale.</span><span class="sxs-lookup"><span data-stu-id="18ff4-138">To define a topology to incorporate Archiving databases, an account that is a member of the local users group.</span></span></p>
<p><span data-ttu-id="18ff4-139">Per pubblicare la topologia, un account che sia membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins e che disponga di autorizzazioni di controllo completo (lettura/scrittura/modifica) sulla condivisione file da utilizzare per l'archivio file di Lync Server 2013 (in modo che il generatore di topologie possa configurare gli elenchi DACL necessari).</span><span class="sxs-lookup"><span data-stu-id="18ff4-139">To publish the topology, an account that is a member of the domain admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs).</span></span></p></td>
<td><p><span data-ttu-id="18ff4-140"><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">Aggiunta dei database di archiviazione a una distribuzione di Lync Server 2013 esistente</a> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="18ff4-140"><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">Adding Archiving databases to an existing Lync Server 2013 Deployment</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18ff4-141"><strong>Configurare l'autenticazione da server a server (solo se si utilizza l'integrazione di Microsoft Exchange)</strong></span><span class="sxs-lookup"><span data-stu-id="18ff4-141"><strong>Configure server-to-server authentication (only if using Microsoft Exchange integration)</strong></span></span></p></td>
<td><p><span data-ttu-id="18ff4-142">Configurare i server per l'abilitazione dell'autenticazione tra Lync Server 2013 ed Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="18ff4-142">Configure servers to enable authentication between Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="18ff4-143">Per convalidare la connettività dello spazio di archiviazione di Exchange prima di abilitare l'archiviazione, è consigliabile eseguire il <strong>dumpster test-CsExchangeStorageConnectivity testuser_sipUri – Folder</strong> .</span><span class="sxs-lookup"><span data-stu-id="18ff4-143">We recommend running <strong>Test-CsExchangeStorageConnectivity testuser_sipUri –Folder Dumpster</strong> to validate Exchange Archiving storage connectivity before enabling archiving.</span></span></p></td>
<td><p><span data-ttu-id="18ff4-144">Un account con le autorizzazioni appropriate per la gestione dei certificati sul server.</span><span class="sxs-lookup"><span data-stu-id="18ff4-144">An account with the appropriate permissions for managing certificates on the servers.</span></span></p></td>
<td><p><span data-ttu-id="18ff4-145"><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Gestione dell'autenticazione da server a server (OAuth) e delle applicazioni partner in Lync server 2013</a> nella documentazione relativa alla distribuzione o nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="18ff4-145"><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</a> in the Deployment documentation or the Operations documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18ff4-146"><strong>Configurare i criteri e le configurazioni per l'archiviazione</strong></span><span class="sxs-lookup"><span data-stu-id="18ff4-146"><strong>Configure archiving policies and configurations</strong></span></span></p></td>
<td><p><span data-ttu-id="18ff4-147">Configurare l'archiviazione, se si desidera utilizzare l'integrazione di Microsoft Exchange, il criterio globale e tutti i criteri di sito e utente (quando non si utilizza l'integrazione di Microsoft Exchange per tutti gli archivi dati) e le opzioni di archiviazione specifiche, ad esempio la modalità critica e i dati esportazione ed eliminazione.</span><span class="sxs-lookup"><span data-stu-id="18ff4-147">Configure archiving, including whether to use Microsoft Exchange integration, the global policy and any site and user policies (when not using Microsoft Exchange integration for all data storage), and specific archiving options, such as critical mode and data export and purging.</span></span></p>
<p><span data-ttu-id="18ff4-148">Se si utilizza l'integrazione di Microsoft Exchange, configurare i criteri di archiviazione sul posto di Exchange in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="18ff4-148">If using Microsoft Exchange integration, configure Exchange In-Place Hold policies as appropriate.</span></span></p></td>
<td><p><span data-ttu-id="18ff4-149">Gruppo RTCUniversalServerAdmins (solo Windows PowerShell) oppure assegnare gli utenti al ruolo CSArchivingAdministrator o CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="18ff4-149">RTCUniversalServerAdmins group (Windows PowerShell only) or assign users to the CSArchivingAdministrator or CSAdministrator role.</span></span></p></td>
<td><p><span data-ttu-id="18ff4-150"><a href="lync-server-2013-configuring-support-for-archiving.md">Configurazione del supporto per l'archiviazione in Lync Server 2013</a> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="18ff4-150"><a href="lync-server-2013-configuring-support-for-archiving.md">Configuring support for Archiving in Lync Server 2013</a> in the Deployment documentation.</span></span></p>
<p><span data-ttu-id="18ff4-151">Documentazione del prodotto Exchange (se si utilizza l'integrazione di Microsoft Exchange).</span><span class="sxs-lookup"><span data-stu-id="18ff4-151">Exchange product documentation (if using Microsoft Exchange integration).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="deploying-lync-server-and-microsoft-exchange-in-different-forests"></a><span data-ttu-id="18ff4-152">Distribuzione di Lync Server e di Microsoft Exchange in foreste diverse</span><span class="sxs-lookup"><span data-stu-id="18ff4-152">Deploying Lync Server and Microsoft Exchange in Different Forests</span></span>

<span data-ttu-id="18ff4-153">Se Microsoft Exchange Server non è distribuito nella stessa foresta di Lync Server, è necessario verificare che i seguenti attributi di Active Directory di Exchange siano sincronizzati con la foresta in cui è distribuito Lync Server:</span><span class="sxs-lookup"><span data-stu-id="18ff4-153">If Microsoft Exchange Server is not deployed in the same forest as Lync Server, you must make sure that the following Exchange Active Directory attributes are synchronized to the forest where Lync Server is deployed:</span></span>

1.  <span data-ttu-id="18ff4-154">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="18ff4-154">msExchUserHoldPolicies</span></span>

2.  <span data-ttu-id="18ff4-155">proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="18ff4-155">proxyAddresses</span></span>

<span data-ttu-id="18ff4-p107">Si tratta di un attributo a valore multiplo. Quando si sincronizza questo attributo, è necessario unire i valori, e non sostituirli, per evitare che i valori esistenti vengano persi.</span><span class="sxs-lookup"><span data-stu-id="18ff4-p107">This is a multi-value attribute. When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


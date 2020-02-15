---
title: 'Lync Server 2013: Panoramica della preparazione di servizi di dominio Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Active Directory Domain Services preparation
ms:assetid: cdd2a652-6a0d-4728-9950-3fcaa7a80066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398869(v=OCS.15)
ms:contentKeyID: 48185662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3085caf0b118b20bf52a4ff82a14b399d1ee6594
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036344"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-active-directory-domain-services-preparation-in-lync-server-2013"></a><span data-ttu-id="72121-102">Panoramica della preparazione di servizi di dominio Active Directory in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72121-102">Overview of Active Directory Domain Services preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72121-103">_**Ultimo argomento modificato:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="72121-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="72121-104">Per preparare Servizi di dominio Active Directory per la distribuzione di Lync Server 2013, è necessario eseguire tre passaggi in una sequenza specifica.</span><span class="sxs-lookup"><span data-stu-id="72121-104">To prepare Active Directory Domain Services for your Lync Server 2013 deployment, you must perform three steps in a specific sequence.</span></span>

<span data-ttu-id="72121-105">Nella tabella seguente vengono illustrati i passaggi necessari per preparare Servizi di dominio Active Directory per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="72121-105">The following table describes the steps required to prepare AD DS for Lync Server.</span></span>

### <a name="active-directory-preparation-steps"></a><span data-ttu-id="72121-106">Passaggi di preparazione di Active Directory</span><span class="sxs-lookup"><span data-stu-id="72121-106">Active Directory Preparation Steps</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="72121-107">Passaggio</span><span class="sxs-lookup"><span data-stu-id="72121-107">Step</span></span></th>
<th><span data-ttu-id="72121-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="72121-108">Description</span></span></th>
<th><span data-ttu-id="72121-109">Esecuzione</span><span class="sxs-lookup"><span data-stu-id="72121-109">Where run</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.</p></td>
<td><p><span data-ttu-id="72121-110"><a href="lync-server-2013-preparing-the-active-directory-schema.md">Preparazione dello schema di Active Directory in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="72121-110"><a href="lync-server-2013-preparing-the-active-directory-schema.md">Preparing the Active Directory schema in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="72121-111">Estende lo schema di Active Directory aggiungendo nuove classi e attributi utilizzati da Lync Server.</span><span class="sxs-lookup"><span data-stu-id="72121-111">Extends the Active Directory schema by adding new classes and attributes that are used by Lync Server.</span></span></p>
<p><span data-ttu-id="72121-112">Eseguire una sola volta per ogni foresta nella distribuzione in cui verrà distribuito Lync Server.</span><span class="sxs-lookup"><span data-stu-id="72121-112">Run once for each forest in your deployment where Lync Server will be deployed.</span></span></p></td>
<td><p><span data-ttu-id="72121-113">In base al master schema nel dominio radice di ogni foresta in cui verrà distribuito Lync Server.</span><span class="sxs-lookup"><span data-stu-id="72121-113">Against the schema master in the root domain of each forest where Lync Server will be deployed.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="72121-p101">Non è necessario eseguire questo passaggio nel dominio radice se si dispone delle autorizzazioni sul master di schemi, ma è necessario essere un membro del gruppo Schema Admins nel dominio radice e un membro del gruppo Enterprise Admins nel master di schemi. In una topologia di foresta di risorse eseguire questo passaggio solo nella foresta di risorse e non nelle foreste di utenti. In una topologia di foresta centrale eseguire questo passaggio solo nella foresta centrale e non nelle foreste di utenti.</span><span class="sxs-lookup"><span data-stu-id="72121-p101">You do not need to run this step in the root domain if you have permissions on the schema master, but you must be a member of the Schema Admins group in the root domain and a member of the Enterprise Admins group on the schema master. In a resource forest topology, run this step only in the resource forest, not in any user forests. In a central forest topology, run this step only in the central forest, not in any user forests.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p>2.</p></td>
<td><p><span data-ttu-id="72121-117"><a href="lync-server-2013-preparing-the-forest.md">Preparazione della foresta per Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="72121-117"><a href="lync-server-2013-preparing-the-forest.md">Preparing the forest for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="72121-118">Crea le impostazioni globali e i gruppi universali utilizzati da Lync Server.</span><span class="sxs-lookup"><span data-stu-id="72121-118">Creates global settings and universal groups that are used by Lync Server.</span></span></p>
<p><span data-ttu-id="72121-119">Eseguire una sola volta per ogni foresta nella distribuzione in cui verrà distribuito Lync Server.</span><span class="sxs-lookup"><span data-stu-id="72121-119">Run once for each forest in your deployment where Lync Server will be deployed.</span></span></p></td>
<td><p><span data-ttu-id="72121-120">Nel dominio radice di ogni foresta in cui verrà distribuito Lync Server.</span><span class="sxs-lookup"><span data-stu-id="72121-120">In the root domain of each forest where Lync Server will be deployed.</span></span> <span data-ttu-id="72121-121">Per eseguire questo passaggio, è necessario essere un membro del gruppo Enterprise Admins.</span><span class="sxs-lookup"><span data-stu-id="72121-121">To run this step, you must be a member of the Enterprise Admins group.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="72121-p103">In una topologia di foresta di risorse eseguire questo passaggio solo nella foresta di risorse e non nelle foreste di utenti. In una topologia di foresta centrale eseguire questo passaggio solo nella foresta centrale e non nelle foreste di utenti.</span><span class="sxs-lookup"><span data-stu-id="72121-p103">In a resource forest topology, run this step only in the resource forest, not in any user forests. In a central forest topology, run this step only in the central forest, not in any user forests.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p>3.</p></td>
<td><p><span data-ttu-id="72121-124"><a href="lync-server-2013-preparing-domains.md">Preparazione dei domini per Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="72121-124"><a href="lync-server-2013-preparing-domains.md">Preparing domains for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="72121-125">Aggiunge autorizzazioni per gli oggetti che verranno utilizzati dai membri dei gruppi universali.</span><span class="sxs-lookup"><span data-stu-id="72121-125">Adds permissions on objects to be used by members of universal groups.</span></span></p>
<p><span data-ttu-id="72121-126">Eseguire il passaggio una volta per ogni dominio utente o server.</span><span class="sxs-lookup"><span data-stu-id="72121-126">Run once per user domain or server domain.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="72121-127">Se si esegue la migrazione da Lync Server 2010 a Lync Server 2013, la distribuzione guidata potrebbe indicare che la preparazione del dominio è già stata completata.</span><span class="sxs-lookup"><span data-stu-id="72121-127">If you are migrating from Lync Server 2010 to Lync Server 2013, the Deployment Wizard may indicate that domain preparation is already complete.</span></span> <span data-ttu-id="72121-128">Non è necessario eseguire di nuovo la preparazione del dominio.</span><span class="sxs-lookup"><span data-stu-id="72121-128">You do not need to run domain preparation again.</span></span> <span data-ttu-id="72121-129">Le autorizzazioni non sono state modificate da Lync Server 2010 a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="72121-129">Permissions were not changed from Lync Server 2010 to Lync Server 2013.</span></span>


</div></td>
<td><p><span data-ttu-id="72121-130">Su un server membro in ogni dominio in cui verrà distribuito Lync Server.</span><span class="sxs-lookup"><span data-stu-id="72121-130">On a member server in each domain where Lync Server will be deployed.</span></span> <span data-ttu-id="72121-131">Per eseguire questo passaggio, è necessario essere un membro del gruppo Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="72121-131">To run this step, you must be a member of the Domain Admins group.</span></span></p></td>
</tr>
</tbody>
</table>


<div id="sectionSection0" class="section">

<span data-ttu-id="72121-132">Lync Server 2013, come Lync Server 2010, archivia molte delle informazioni di configurazione nell'archivio di gestione centrale invece che in servizi di dominio Active Directory come nel caso di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="72121-132">Lync Server 2013, like Lync Server 2010, stores much of the configuration information in the Central Management store instead of in AD DS as was the case in Office Communications Server 2007 R2.</span></span> <span data-ttu-id="72121-133">Tuttavia, le informazioni seguenti sono archiviate in servizi di dominio Active Directory:</span><span class="sxs-lookup"><span data-stu-id="72121-133">However, the following information is stored in AD DS:</span></span>

  - <span data-ttu-id="72121-134">**Estensioni dello schema**:</span><span class="sxs-lookup"><span data-stu-id="72121-134">**Schema extensions**:</span></span>
    
      - <span data-ttu-id="72121-135">Estensioni degli oggetti utente</span><span class="sxs-lookup"><span data-stu-id="72121-135">User object extensions</span></span>
    
      - <span data-ttu-id="72121-136">Estensioni per le classi di Office Communications Server 2007 R2 per mantenere la compatibilità con le versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="72121-136">Extensions for Office Communications Server 2007 R2 classes to maintain backward compatibility</span></span>

<!-- end list -->

  - <span data-ttu-id="72121-137">**Dati** (memorizzati nello schema esteso di Lync Server e nelle classi dello schema esistenti):</span><span class="sxs-lookup"><span data-stu-id="72121-137">**Data** (stored in Lync Server extended schema and in existing schema classes):</span></span>
    
      - <span data-ttu-id="72121-138">URI (Uniform Resource Identifier) SIP dell'utente e altre impostazioni utente</span><span class="sxs-lookup"><span data-stu-id="72121-138">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
      - <span data-ttu-id="72121-139">Oggetti contatto per applicazioni quali Response Group e Operatore Conferenza</span><span class="sxs-lookup"><span data-stu-id="72121-139">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
      - <span data-ttu-id="72121-140">Puntatore all'archivio di gestione centrale</span><span class="sxs-lookup"><span data-stu-id="72121-140">A pointer to the Central Management store</span></span>
    
      - <span data-ttu-id="72121-141">Account di autenticazione Kerberos (un oggetto computer facoltativo)</span><span class="sxs-lookup"><span data-stu-id="72121-141">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="72121-142">In Lync Server 2013, è possibile delegare l'installazione e l'amministrazione concedendo le autorizzazioni di installazione al gruppo universale RTCUniversalServerAdmins in modo che i membri di tale gruppo possano installare e attivare Lync Server 2013 su un server locale (dopo che il server è stato aggiunto all' topologia, pubblicazione e abilitazione.</span><span class="sxs-lookup"><span data-stu-id="72121-142">In Lync Server 2013, you delegate setup and administration by granting setup permissions to the RTCUniversalServerAdmins universal group so that members of that group can install and activate Lync Server 2013 on a local server (after the server has been added to the topology, published, and enabled).</span></span> <span data-ttu-id="72121-143">Gli utenti delegati devono essere amministratori locali nel computer in cui eseguono l'installazione e l'attivazione di Lync Server 2013, ma non devono essere membri del gruppo Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="72121-143">The delegated users must be local administrators on the computer where they are installing and activating Lync Server 2013, but they do not need to be members of the Domain Admins group.</span></span> <span data-ttu-id="72121-144">È anche possibile concedere autorizzazioni per gli oggetti di unità organizzative specificate, in modo che i membri dei gruppi universali creati durante la preparazione della foresta possano accedere a tali oggetti senza essere membri del gruppo Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="72121-144">You can also grant permissions for objects in specified organizational units (OUs) so that members of the universal groups created during forest preparation can access those objects without being members of the Domain Admins group.</span></span>

<span data-ttu-id="72121-145">Per le nuove distribuzioni di Lync Server 2013, le impostazioni globali devono essere archiviate nel contenitore di configurazione.</span><span class="sxs-lookup"><span data-stu-id="72121-145">For new deployments of Lync Server 2013, global settings must be stored in the Configuration container.</span></span> <span data-ttu-id="72121-146">Se l'organizzazione sta eseguendo l'aggiornamento da una versione precedente e le impostazioni globali sono ancora presenti nel contenitore di sistema, il contenitore di sistema è ancora supportato.</span><span class="sxs-lookup"><span data-stu-id="72121-146">If your organization is upgrading from an earlier version and you still have global settings in the System container, the System container is still supported.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="72121-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72121-147">See Also</span></span>


[<span data-ttu-id="72121-148">Preparazione dello schema di Active Directory in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72121-148">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
[<span data-ttu-id="72121-149">Estensioni, classi e attributi dello schema di Active Directory utilizzati da Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72121-149">Active Directory schema extensions, classes, and attributes used by Lync Server 2013</span></span>](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)  


[<span data-ttu-id="72121-150">Preparazione della foresta per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72121-150">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
[<span data-ttu-id="72121-151">Preparazione dei domini per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72121-151">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: attività necessarie'
description: 'Lync Server 2013: attività necessarie.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: As-needed tasks
ms:assetid: b66bc6fe-f138-4cf4-ba7f-aee9a3e0497e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722431(v=OCS.15)
ms:contentKeyID: 63969643
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91fe249d9615bb619426c58b22606c3ef182f9a7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560002"
---
# <a name="as-needed-tasks-in-lync-server-2013"></a><span data-ttu-id="22825-103">Attività necessarie in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22825-103">As-needed tasks in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22825-104">_**Ultimo argomento modificato:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="22825-104">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="22825-105">Eseguire le attività seguenti in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="22825-105">Perform the following tasks as necessary.</span></span> <span data-ttu-id="22825-106">Essi sono spesso anche coperti da procedure standard:</span><span class="sxs-lookup"><span data-stu-id="22825-106">They are frequently also covered by standard procedures:</span></span>

  - <span data-ttu-id="22825-107">**Controllo completo della sicurezza   ** È possibile eseguire questa verifica regolarmente, in risposta a un aggiornamento o riprogettazione del sistema di messaggistica, o in risposta a una violazione della protezione tentata (o riuscita).</span><span class="sxs-lookup"><span data-stu-id="22825-107">**Full Security Auditing   **You can perform this audit regularly, in response to an upgrade or redesign of the messaging system, or in response to an attempted (or successful) security breach.</span></span> <span data-ttu-id="22825-108">La procedura può comportare l'analisi delle porte sui server e sui firewall, sulle verifiche delle correzioni di sicurezza e sui test di penetrazione di terze parti.</span><span class="sxs-lookup"><span data-stu-id="22825-108">The procedure may involve port scans on servers and firewalls, audits of security fixes, and third-party penetration tests.</span></span>

  - <span data-ttu-id="22825-109">**Sostituire i certificati per la scadenza**     Controllare i certificati di Lync Server è una delle attività settimanali regolari e, nell'ambito della procedura, un amministratore deve disporre di un record di tutte le date di scadenza dei certificati.</span><span class="sxs-lookup"><span data-stu-id="22825-109">**Replace Certificates about to Expire**   Checking Lync Server Certificates is one of regular weekly tasks, and as part of the procedure an administrator should have a record of all certificates’ expiry dates.</span></span> <span data-ttu-id="22825-110">Questo record consente a un amministratore di creare una notifica quando un determinato certificato sta per essere scaduto e sostituito in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="22825-110">This record enables an administrator to create a notification when a particular certificate is about to be expired and replaced as needed.</span></span>

  - <span data-ttu-id="22825-111">**Aggiornamento delle linee di base**     delle prestazioni Aggiornare le linee di base delle prestazioni dopo un aggiornamento o una modifica della configurazione.</span><span class="sxs-lookup"><span data-stu-id="22825-111">**Updating Performance Baselines**   Update performance baselines after an upgrade or configuration change.</span></span> <span data-ttu-id="22825-112">L'organizzazione può utilizzare le linee di base per misurare le modifiche alle prestazioni e rilevare i problemi che influiscono sulle prestazioni del sistema.</span><span class="sxs-lookup"><span data-stu-id="22825-112">Your organization can use baselines to measure performance changes and to detect issues that affect system performance.</span></span>

  - <span data-ttu-id="22825-113">**Gestione del pool Enterprise**     La configurazione iniziale di pool Enterprise, server Standard Edition e qualsiasi altro server nell'ambiente dell'organizzazione sono state eseguite durante la distribuzione dei singoli server.</span><span class="sxs-lookup"><span data-stu-id="22825-113">**Managing Enterprise Pool**   Initial configuration of Enterprise pools, Standard Edition servers, and any other servers in your organization's environment were done during deployment of the individual servers.</span></span> <span data-ttu-id="22825-114">La gestione dopo la distribuzione di server e pool per i server Standard Edition e i pool Enterprise include le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="22825-114">Post-deployment management of servers and pools for Standard Edition servers and Enterprise pools includes the following tasks:</span></span>
    
      - <span data-ttu-id="22825-115">Gestione dei Front End Server</span><span class="sxs-lookup"><span data-stu-id="22825-115">Managing Front End Servers</span></span>
    
      - <span data-ttu-id="22825-116">Gestione delle conferenze Web</span><span class="sxs-lookup"><span data-stu-id="22825-116">Managing Web Conferencing</span></span>
    
      - <span data-ttu-id="22825-117">Gestione delle conferenze</span><span class="sxs-lookup"><span data-stu-id="22825-117">Managing Conferencing</span></span>
    
      - <span data-ttu-id="22825-118">Modifica delle credenziali dell'account di servizio</span><span class="sxs-lookup"><span data-stu-id="22825-118">Changing Service Account Credentials</span></span>
    
      - <span data-ttu-id="22825-119">Gestione dei database</span><span class="sxs-lookup"><span data-stu-id="22825-119">Managing Databases</span></span>
    
      - <span data-ttu-id="22825-120">Avvio e arresto di servizi e disattivazione dei ruoli del server</span><span class="sxs-lookup"><span data-stu-id="22825-120">Starting and Stopping Services and Deactivating Server Roles</span></span>
    
      - <span data-ttu-id="22825-121">Rimozione di server e ruoli del server, rimozione di pool e disattivazione di server e pool</span><span class="sxs-lookup"><span data-stu-id="22825-121">Removing Servers and Server Roles, Removing Pools, and Decommissioning Servers and Pools</span></span>

  - <span data-ttu-id="22825-122">**Gestione dell'utilizzo**     È possibile configurare Lync Server 2013 per fornire le funzionalità e le funzionalità più appropriate per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="22825-122">**Managing Usage**   You can configure Lync Server 2013 to provide the features and functionality that are most appropriate for your organization.</span></span> <span data-ttu-id="22825-123">Sono incluse le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="22825-123">This includes the following:</span></span>
    
      - <span data-ttu-id="22825-124">Gestione del supporto per le riunioni di Web Conferencing locali</span><span class="sxs-lookup"><span data-stu-id="22825-124">Managing Support for On-Premise Web Conferencing Meetings</span></span>
    
      - <span data-ttu-id="22825-125">Gestione dell'utilizzo di gruppi di distribuzione per l'invio di messaggi istantanei</span><span class="sxs-lookup"><span data-stu-id="22825-125">Managing the Use of Distribution Groups to Send Instant Messages</span></span>
    
      - <span data-ttu-id="22825-126">Gestione di contatti, presenza e query</span><span class="sxs-lookup"><span data-stu-id="22825-126">Managing Contacts, Presence, and Queries</span></span>
    
      - <span data-ttu-id="22825-127">Configurazione del filtro delle versioni client</span><span class="sxs-lookup"><span data-stu-id="22825-127">Configuring Client Version Filtering</span></span>
    
      - <span data-ttu-id="22825-128">Configurazione del filtro di messaggistica istantanea intelligente</span><span class="sxs-lookup"><span data-stu-id="22825-128">Configuring Intelligent IM Filtering</span></span>
    
      - <span data-ttu-id="22825-129">Configurazione dell'archiviazione, registrazione dettagli chiamata e conformità alle riunioni</span><span class="sxs-lookup"><span data-stu-id="22825-129">Configuring Archiving, Call Detail Recording, and Meeting Compliance</span></span>

  - <span data-ttu-id="22825-130">**Gestione della connettività**     dei server perimetrali La gestione continua dei server e delle impostazioni necessarie per fornire la connettività esterna include gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="22825-130">**Managing Edge Server Connectivity**   Ongoing management of the servers and settings required to provide external connectivity includes the following:</span></span>
    
      - <span data-ttu-id="22825-131">Gestione della connettività tra server interni e server perimetrali</span><span class="sxs-lookup"><span data-stu-id="22825-131">Managing Connectivity between Internal Servers and Edge Servers</span></span>
    
      - <span data-ttu-id="22825-132">Configurazione di interfacce e certificati interni ed esterni per server perimetrali</span><span class="sxs-lookup"><span data-stu-id="22825-132">Configuring Internal and External Interfaces and Certificates for Edge Servers</span></span>
    
      - <span data-ttu-id="22825-133">Gestione dell'accesso dei partner federati</span><span class="sxs-lookup"><span data-stu-id="22825-133">Managing Federated Partner Access</span></span>

  - <span data-ttu-id="22825-134">**Amministrazione della rubrica**     L'amministrazione dei server della rubrica include gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="22825-134">**Administering the Address Book**   Administering Address Book Servers includes the following:</span></span>
    
      - <span data-ttu-id="22825-135">Configurazione della normalizzazione del telefono del server rubrica</span><span class="sxs-lookup"><span data-stu-id="22825-135">Configuring Address Book Server phone normalization</span></span>
    
      - <span data-ttu-id="22825-136">Gestione del server della rubrica dalla riga di comando</span><span class="sxs-lookup"><span data-stu-id="22825-136">Managing the Address Book Server from the command line</span></span>

  - <span data-ttu-id="22825-137">**Gestione degli account utente**     La gestione degli account utente include gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="22825-137">**Managing User Accounts**   Management of user accounts includes the following:</span></span>
    
      - <span data-ttu-id="22825-138">Abilitazione degli account utente per Lync Server</span><span class="sxs-lookup"><span data-stu-id="22825-138">Enabling User Accounts for Lync Server</span></span>
    
      - <span data-ttu-id="22825-139">Configurazione degli utenti di Lync Server tramite la procedura guidata</span><span class="sxs-lookup"><span data-stu-id="22825-139">Configuring Lync Server Users using the Wizard</span></span>
    
      - <span data-ttu-id="22825-140">Configurazione di singole proprietà dell'account utente di Lync Server</span><span class="sxs-lookup"><span data-stu-id="22825-140">Configuring Individual Lync Server User Account Properties</span></span>
    
      - <span data-ttu-id="22825-141">Ricerca di utenti di Lync Server</span><span class="sxs-lookup"><span data-stu-id="22825-141">Searching for Lync Server Users</span></span>
    
      - <span data-ttu-id="22825-142">Spostamento degli utenti di Lync Server</span><span class="sxs-lookup"><span data-stu-id="22825-142">Moving Lync Server Users</span></span>
    
      - <span data-ttu-id="22825-143">Eliminazione degli utenti di Lync Server</span><span class="sxs-lookup"><span data-stu-id="22825-143">Deleting Lync Server Users</span></span>

  - <span data-ttu-id="22825-144">**Analisi dei file**     di registro di Lync Server 2013 Uno strumento molto utile, generalmente utilizzato per la risoluzione dei problemi, è lo strumento di registrazione di Lync Server 2013 descritto in dettaglio nell' [utilizzo dello strumento di registrazione di Lync server 2013](https://technet.microsoft.com/library/gg558599.aspx).</span><span class="sxs-lookup"><span data-stu-id="22825-144">**Analyzing Lync Server 2013 Log Files**   One very helpful tool, generally used for troubleshooting, is the Lync Server 2013 Logging Tool described in detail in [Using Lync Server 2013 Logging Tool](https://technet.microsoft.com/library/gg558599.aspx).</span></span>

<span data-ttu-id="22825-145">Poiché lo strumento di registrazione genera file di registro (per ogni server), questi file di registro possono essere visualizzati e analizzati utilizzando lo strumento Snooper, se gli strumenti di Microsoft Office Server 12 Resource Kit sono installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="22825-145">Because the Logging Tool generates log files (on a per-server basis), these log files can be viewed and analyzed by using the Snooper tool, if the Microsoft Office Server 12 Resource Kit Tools are installed on the computer.</span></span> <span data-ttu-id="22825-146">In caso contrario, i registri possono essere analizzati anche utilizzando un editor di testo, molto meno trasparente e più complesso rispetto all'utilizzo dell'utilità Snooper.</span><span class="sxs-lookup"><span data-stu-id="22825-146">Otherwise, logs can also be analyzed by using a text editor, which is much less transparent and more complex than using the Snooper utility.</span></span>

<span data-ttu-id="22825-147">Per visualizzare e analizzare i messaggi di protocollo</span><span class="sxs-lookup"><span data-stu-id="22825-147">To View and Analyze Protocol Messages</span></span>

<span data-ttu-id="22825-148">Nello strumento di registrazione, dopo aver terminato la sessione di debug, fare clic su Analizza file di registro per visualizzare i file di registro utilizzando lo strumento Snooper.</span><span class="sxs-lookup"><span data-stu-id="22825-148">In the Logging Tool, when you have ended the debug session, click Analyze Log Files to view the log files by using the Snooper tool.</span></span> <span data-ttu-id="22825-149">È possibile analizzare i registri di protocollo per i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="22825-149">You can analyze protocol logs for the following components:</span></span>

  - <span data-ttu-id="22825-150">Lync Server SipStack (SIP)</span><span class="sxs-lookup"><span data-stu-id="22825-150">Lync Server SipStack (SIP)</span></span>

  - <span data-ttu-id="22825-151">Lync Server S4 (SIP)</span><span class="sxs-lookup"><span data-stu-id="22825-151">Lync Server S4 (SIP)</span></span>

  - <span data-ttu-id="22825-152">Lync Server Conferencing signaling Traffic (C3P), tra cui MCU infra C3P e Focus C3P</span><span class="sxs-lookup"><span data-stu-id="22825-152">Lync Server Conferencing signaling traffic (C3P), including MCU Infra C3P and Focus C3P</span></span>

  - <span data-ttu-id="22825-153">Traffico Web Conferencing di Lync Server (PSOM)</span><span class="sxs-lookup"><span data-stu-id="22825-153">Lync Server Web conferencing traffic (PSOM)</span></span>

  - <span data-ttu-id="22825-154">Client della piattaforma client per le comunicazioni unificate di Lync Server (UCCP)</span><span class="sxs-lookup"><span data-stu-id="22825-154">Lync Server Unified Communications Client Platform client (UCCP)</span></span>

  - <span data-ttu-id="22825-155">Segnalazioni di errori dal database di archiviazione</span><span class="sxs-lookup"><span data-stu-id="22825-155">Error reports from the archiving database</span></span>

<span data-ttu-id="22825-156">Per facilitare l'organizzazione delle prestazioni delle attività necessarie, vedere As-Needed checklist Operations.</span><span class="sxs-lookup"><span data-stu-id="22825-156">To help organize the performance of as-needed tasks, see As-Needed Operations Checklist.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="22825-157">Per le procedure dettagliate per l'amministrazione e la gestione, vedere la Guida all'amministrazione di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="22825-157">For detailed administration and management procedures, see the Microsoft Lync Server 2013 Administration Guide.</span></span>



</div>

<div>

## <a name="backup-and-restore-policies-or-configuration-settings"></a><span data-ttu-id="22825-158">Criteri di backup (e ripristino) o impostazioni di configurazione</span><span class="sxs-lookup"><span data-stu-id="22825-158">Backup (and restore) policies or configuration settings</span></span>

<span data-ttu-id="22825-159">Lync Server 2013 consente di eseguire il backup e il ripristino dell'intero sistema.</span><span class="sxs-lookup"><span data-stu-id="22825-159">Lync Server 2013 lets you back up and restore the whole system.</span></span> <span data-ttu-id="22825-160">Se si desidera eseguire il backup (e quindi magari un giorno di ripristino) un singolo criterio o una singola raccolta di impostazioni di configurazione, recuperare il criterio appropriato e quindi eseguire il piping dell'oggetto al cmdlet Export-Clixml, che salva le informazioni sui criteri come file XML:</span><span class="sxs-lookup"><span data-stu-id="22825-160">Iif you want to back up (and then maybe someday restore) a single policy or a single collection of configuration settings, retrieve the appropriate policy, and then pipe that object to the Export-Clixml cmdlet, which saves the policy information as an XML file:</span></span>

`Get-CsClientPolicy -Identity "RedmondClientPolicy" | Export-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

<span data-ttu-id="22825-161">È ora possibile provare a utilizzare RedmondClientPolicy e modificare molte impostazioni.</span><span class="sxs-lookup"><span data-stu-id="22825-161">You may now experiment with RedmondClientPolicy and change lots of the settings.</span></span> <span data-ttu-id="22825-162">Se si decide invece di ripristinare i criteri obsoleti, immettere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="22825-162">If you decide instead to restore the old policy, enter:</span></span>

`$x = Import-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

`Set-CsClientPolicy -Instance $x`

<span data-ttu-id="22825-163">Si noti che questo approccio funzionerà per la maggior parte dei criteri e delle impostazioni, ma non funzionerà con alcuni degli elementi più complessi, ovvero gli elementi che contengono più oggetti secondari, ad esempio le impostazioni di configurazione del routing, che contengono molte route vocali separate.</span><span class="sxs-lookup"><span data-stu-id="22825-163">Note that this approach will work for most policies and settings but it won't work with some of the more complex items—items that contain multiple sub-objects (like routing configuration settings, which contain many separate voice routes).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: attività necessarie'
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
ms.openlocfilehash: 67a0355d32e5e704d6609335c82f8cfe1fe7aa86
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029287"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="as-needed-tasks-in-lync-server-2013"></a><span data-ttu-id="a9def-102">Attività necessarie in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9def-102">As-needed tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9def-103">_**Ultimo argomento modificato:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="a9def-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="a9def-104">Eseguire le attività seguenti in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="a9def-104">Perform the following tasks as necessary.</span></span> <span data-ttu-id="a9def-105">Essi sono spesso anche coperti da procedure standard:</span><span class="sxs-lookup"><span data-stu-id="a9def-105">They are frequently also covered by standard procedures:</span></span>

  - <span data-ttu-id="a9def-106">**Controllo completo della sicurezza   ** È possibile eseguire questa verifica regolarmente, in risposta a un aggiornamento o riprogettazione del sistema di messaggistica, o in risposta a una violazione della protezione tentata (o riuscita).</span><span class="sxs-lookup"><span data-stu-id="a9def-106">**Full Security Auditing   **You can perform this audit regularly, in response to an upgrade or redesign of the messaging system, or in response to an attempted (or successful) security breach.</span></span> <span data-ttu-id="a9def-107">La procedura può comportare l'analisi delle porte sui server e sui firewall, sulle verifiche delle correzioni di sicurezza e sui test di penetrazione di terze parti.</span><span class="sxs-lookup"><span data-stu-id="a9def-107">The procedure may involve port scans on servers and firewalls, audits of security fixes, and third-party penetration tests.</span></span>

  - <span data-ttu-id="a9def-108">**Sostituire i certificati per la scadenza**   del controllo i certificati di Lync Server sono una delle attività settimanali regolari e, nell'ambito della procedura, un amministratore deve disporre di un record di tutte le date di scadenza dei certificati.</span><span class="sxs-lookup"><span data-stu-id="a9def-108">**Replace Certificates about to Expire**   Checking Lync Server Certificates is one of regular weekly tasks, and as part of the procedure an administrator should have a record of all certificates’ expiry dates.</span></span> <span data-ttu-id="a9def-109">Questo record consente a un amministratore di creare una notifica quando un determinato certificato sta per essere scaduto e sostituito in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="a9def-109">This record enables an administrator to create a notification when a particular certificate is about to be expired and replaced as needed.</span></span>

  - <span data-ttu-id="a9def-110">**Aggiornamento delle linee di base delle**   prestazioni aggiornare le linee di base delle prestazioni dopo un aggiornamento o una modifica alla configurazione.</span><span class="sxs-lookup"><span data-stu-id="a9def-110">**Updating Performance Baselines**   Update performance baselines after an upgrade or configuration change.</span></span> <span data-ttu-id="a9def-111">L'organizzazione può utilizzare le linee di base per misurare le modifiche alle prestazioni e rilevare i problemi che influiscono sulle prestazioni del sistema.</span><span class="sxs-lookup"><span data-stu-id="a9def-111">Your organization can use baselines to measure performance changes and to detect issues that affect system performance.</span></span>

  - <span data-ttu-id="a9def-112">**Gestione del pool**   Enterprise la configurazione iniziale dei pool Enterprise, server Standard Edition e qualsiasi altro server nell'ambiente dell'organizzazione sono stati eseguiti durante la distribuzione dei singoli server.</span><span class="sxs-lookup"><span data-stu-id="a9def-112">**Managing Enterprise Pool**   Initial configuration of Enterprise pools, Standard Edition servers, and any other servers in your organization's environment were done during deployment of the individual servers.</span></span> <span data-ttu-id="a9def-113">La gestione dopo la distribuzione di server e pool per i server Standard Edition e i pool Enterprise include le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="a9def-113">Post-deployment management of servers and pools for Standard Edition servers and Enterprise pools includes the following tasks:</span></span>
    
      - <span data-ttu-id="a9def-114">Gestione dei Front End Server</span><span class="sxs-lookup"><span data-stu-id="a9def-114">Managing Front End Servers</span></span>
    
      - <span data-ttu-id="a9def-115">Gestione delle conferenze Web</span><span class="sxs-lookup"><span data-stu-id="a9def-115">Managing Web Conferencing</span></span>
    
      - <span data-ttu-id="a9def-116">Gestione delle conferenze</span><span class="sxs-lookup"><span data-stu-id="a9def-116">Managing Conferencing</span></span>
    
      - <span data-ttu-id="a9def-117">Modifica delle credenziali dell'account di servizio</span><span class="sxs-lookup"><span data-stu-id="a9def-117">Changing Service Account Credentials</span></span>
    
      - <span data-ttu-id="a9def-118">Gestione dei database</span><span class="sxs-lookup"><span data-stu-id="a9def-118">Managing Databases</span></span>
    
      - <span data-ttu-id="a9def-119">Avvio e arresto di servizi e disattivazione dei ruoli del server</span><span class="sxs-lookup"><span data-stu-id="a9def-119">Starting and Stopping Services and Deactivating Server Roles</span></span>
    
      - <span data-ttu-id="a9def-120">Rimozione di server e ruoli del server, rimozione di pool e disattivazione di server e pool</span><span class="sxs-lookup"><span data-stu-id="a9def-120">Removing Servers and Server Roles, Removing Pools, and Decommissioning Servers and Pools</span></span>

  - <span data-ttu-id="a9def-121">**Gestione dell'utilizzo**   è possibile configurare Lync Server 2013 per fornire le caratteristiche e le funzionalità più appropriate per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a9def-121">**Managing Usage**   You can configure Lync Server 2013 to provide the features and functionality that are most appropriate for your organization.</span></span> <span data-ttu-id="a9def-122">Sono incluse le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="a9def-122">This includes the following:</span></span>
    
      - <span data-ttu-id="a9def-123">Gestione del supporto per le riunioni di Web Conferencing locali</span><span class="sxs-lookup"><span data-stu-id="a9def-123">Managing Support for On-Premise Web Conferencing Meetings</span></span>
    
      - <span data-ttu-id="a9def-124">Gestione dell'utilizzo di gruppi di distribuzione per l'invio di messaggi istantanei</span><span class="sxs-lookup"><span data-stu-id="a9def-124">Managing the Use of Distribution Groups to Send Instant Messages</span></span>
    
      - <span data-ttu-id="a9def-125">Gestione di contatti, presenza e query</span><span class="sxs-lookup"><span data-stu-id="a9def-125">Managing Contacts, Presence, and Queries</span></span>
    
      - <span data-ttu-id="a9def-126">Configurazione del filtro delle versioni client</span><span class="sxs-lookup"><span data-stu-id="a9def-126">Configuring Client Version Filtering</span></span>
    
      - <span data-ttu-id="a9def-127">Configurazione del filtro di messaggistica istantanea intelligente</span><span class="sxs-lookup"><span data-stu-id="a9def-127">Configuring Intelligent IM Filtering</span></span>
    
      - <span data-ttu-id="a9def-128">Configurazione dell'archiviazione, registrazione dettagli chiamata e conformità alle riunioni</span><span class="sxs-lookup"><span data-stu-id="a9def-128">Configuring Archiving, Call Detail Recording, and Meeting Compliance</span></span>

  - <span data-ttu-id="a9def-129">\*\*\*\*   Gestione della connettività del server perimetrale la gestione continua dei server e delle impostazioni necessarie per fornire la connettività esterna include quanto segue:</span><span class="sxs-lookup"><span data-stu-id="a9def-129">**Managing Edge Server Connectivity**   Ongoing management of the servers and settings required to provide external connectivity includes the following:</span></span>
    
      - <span data-ttu-id="a9def-130">Gestione della connettività tra server interni e server perimetrali</span><span class="sxs-lookup"><span data-stu-id="a9def-130">Managing Connectivity between Internal Servers and Edge Servers</span></span>
    
      - <span data-ttu-id="a9def-131">Configurazione di interfacce e certificati interni ed esterni per server perimetrali</span><span class="sxs-lookup"><span data-stu-id="a9def-131">Configuring Internal and External Interfaces and Certificates for Edge Servers</span></span>
    
      - <span data-ttu-id="a9def-132">Gestione dell'accesso dei partner federati</span><span class="sxs-lookup"><span data-stu-id="a9def-132">Managing Federated Partner Access</span></span>

  - <span data-ttu-id="a9def-133">**L'amministrazione della**   rubrica che amministra i server della rubrica include gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a9def-133">**Administering the Address Book**   Administering Address Book Servers includes the following:</span></span>
    
      - <span data-ttu-id="a9def-134">Configurazione della normalizzazione del telefono del server rubrica</span><span class="sxs-lookup"><span data-stu-id="a9def-134">Configuring Address Book Server phone normalization</span></span>
    
      - <span data-ttu-id="a9def-135">Gestione del server della rubrica dalla riga di comando</span><span class="sxs-lookup"><span data-stu-id="a9def-135">Managing the Address Book Server from the command line</span></span>

  - <span data-ttu-id="a9def-136">**Gestione degli account utente la**   gestione degli account utente include gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a9def-136">**Managing User Accounts**   Management of user accounts includes the following:</span></span>
    
      - <span data-ttu-id="a9def-137">Abilitazione degli account utente per Lync Server</span><span class="sxs-lookup"><span data-stu-id="a9def-137">Enabling User Accounts for Lync Server</span></span>
    
      - <span data-ttu-id="a9def-138">Configurazione degli utenti di Lync Server tramite la procedura guidata</span><span class="sxs-lookup"><span data-stu-id="a9def-138">Configuring Lync Server Users using the Wizard</span></span>
    
      - <span data-ttu-id="a9def-139">Configurazione di singole proprietà dell'account utente di Lync Server</span><span class="sxs-lookup"><span data-stu-id="a9def-139">Configuring Individual Lync Server User Account Properties</span></span>
    
      - <span data-ttu-id="a9def-140">Ricerca di utenti di Lync Server</span><span class="sxs-lookup"><span data-stu-id="a9def-140">Searching for Lync Server Users</span></span>
    
      - <span data-ttu-id="a9def-141">Spostamento degli utenti di Lync Server</span><span class="sxs-lookup"><span data-stu-id="a9def-141">Moving Lync Server Users</span></span>
    
      - <span data-ttu-id="a9def-142">Eliminazione degli utenti di Lync Server</span><span class="sxs-lookup"><span data-stu-id="a9def-142">Deleting Lync Server Users</span></span>

  - <span data-ttu-id="a9def-143">**Analisi dei file**   di registro di Lync Server 2013 uno strumento molto utile, generalmente utilizzato per la risoluzione dei problemi, è lo strumento di registrazione di Lync Server 2013 descritto in dettaglio nell' [utilizzo dello strumento di registrazione di Lync Server 2013](http://technet.microsoft.com/library/gg558599.aspx).</span><span class="sxs-lookup"><span data-stu-id="a9def-143">**Analyzing Lync Server 2013 Log Files**   One very helpful tool, generally used for troubleshooting, is the Lync Server 2013 Logging Tool described in detail in [Using Lync Server 2013 Logging Tool](http://technet.microsoft.com/library/gg558599.aspx).</span></span>

<span data-ttu-id="a9def-144">Poiché lo strumento di registrazione genera file di registro (per ogni server), questi file di registro possono essere visualizzati e analizzati utilizzando lo strumento Snooper, se gli strumenti di Microsoft Office Server 12 Resource Kit sono installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="a9def-144">Because the Logging Tool generates log files (on a per-server basis), these log files can be viewed and analyzed by using the Snooper tool, if the Microsoft Office Server 12 Resource Kit Tools are installed on the computer.</span></span> <span data-ttu-id="a9def-145">In caso contrario, i registri possono essere analizzati anche utilizzando un editor di testo, molto meno trasparente e più complesso rispetto all'utilizzo dell'utilità Snooper.</span><span class="sxs-lookup"><span data-stu-id="a9def-145">Otherwise, logs can also be analyzed by using a text editor, which is much less transparent and more complex than using the Snooper utility.</span></span>

<span data-ttu-id="a9def-146">Per visualizzare e analizzare i messaggi di protocollo</span><span class="sxs-lookup"><span data-stu-id="a9def-146">To View and Analyze Protocol Messages</span></span>

<span data-ttu-id="a9def-147">Nello strumento di registrazione, dopo aver terminato la sessione di debug, fare clic su Analizza file di registro per visualizzare i file di registro utilizzando lo strumento Snooper.</span><span class="sxs-lookup"><span data-stu-id="a9def-147">In the Logging Tool, when you have ended the debug session, click Analyze Log Files to view the log files by using the Snooper tool.</span></span> <span data-ttu-id="a9def-148">È possibile analizzare i registri di protocollo per i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a9def-148">You can analyze protocol logs for the following components:</span></span>

  - <span data-ttu-id="a9def-149">Lync Server SipStack (SIP)</span><span class="sxs-lookup"><span data-stu-id="a9def-149">Lync Server SipStack (SIP)</span></span>

  - <span data-ttu-id="a9def-150">Lync Server S4 (SIP)</span><span class="sxs-lookup"><span data-stu-id="a9def-150">Lync Server S4 (SIP)</span></span>

  - <span data-ttu-id="a9def-151">Lync Server Conferencing signaling Traffic (C3P), tra cui MCU infra C3P e Focus C3P</span><span class="sxs-lookup"><span data-stu-id="a9def-151">Lync Server Conferencing signaling traffic (C3P), including MCU Infra C3P and Focus C3P</span></span>

  - <span data-ttu-id="a9def-152">Traffico Web Conferencing di Lync Server (PSOM)</span><span class="sxs-lookup"><span data-stu-id="a9def-152">Lync Server Web conferencing traffic (PSOM)</span></span>

  - <span data-ttu-id="a9def-153">Client della piattaforma client per le comunicazioni unificate di Lync Server (UCCP)</span><span class="sxs-lookup"><span data-stu-id="a9def-153">Lync Server Unified Communications Client Platform client (UCCP)</span></span>

  - <span data-ttu-id="a9def-154">Segnalazioni di errori dal database di archiviazione</span><span class="sxs-lookup"><span data-stu-id="a9def-154">Error reports from the archiving database</span></span>

<span data-ttu-id="a9def-155">Per facilitare l'organizzazione delle prestazioni delle attività necessarie, vedere l'elenco di controllo delle operazioni necessario.</span><span class="sxs-lookup"><span data-stu-id="a9def-155">To help organize the performance of as-needed tasks, see As-Needed Operations Checklist.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a9def-156">Per le procedure dettagliate per l'amministrazione e la gestione, vedere la Guida all'amministrazione di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a9def-156">For detailed administration and management procedures, see the Microsoft Lync Server 2013 Administration Guide.</span></span>



</div>

<div>

## <a name="backup-and-restore-policies-or-configuration-settings"></a><span data-ttu-id="a9def-157">Criteri di backup (e ripristino) o impostazioni di configurazione</span><span class="sxs-lookup"><span data-stu-id="a9def-157">Backup (and restore) policies or configuration settings</span></span>

<span data-ttu-id="a9def-158">Lync Server 2013 consente di eseguire il backup e il ripristino dell'intero sistema.</span><span class="sxs-lookup"><span data-stu-id="a9def-158">Lync Server 2013 lets you back up and restore the whole system.</span></span> <span data-ttu-id="a9def-159">Se si desidera eseguire il backup (e quindi eventualmente ripristinare) un singolo criterio o una singola raccolta di impostazioni di configurazione, recuperare il criterio appropriato e quindi indirizzare l'oggetto al cmdlet Export-Clixml, che consente di salvare le informazioni sui criteri come file XML:</span><span class="sxs-lookup"><span data-stu-id="a9def-159">Iif you want to back up (and then maybe someday restore) a single policy or a single collection of configuration settings, retrieve the appropriate policy, and then pipe that object to the Export-Clixml cmdlet, which saves the policy information as an XML file:</span></span>

`Get-CsClientPolicy -Identity "RedmondClientPolicy" | Export-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

<span data-ttu-id="a9def-160">È ora possibile provare a utilizzare RedmondClientPolicy e modificare molte impostazioni.</span><span class="sxs-lookup"><span data-stu-id="a9def-160">You may now experiment with RedmondClientPolicy and change lots of the settings.</span></span> <span data-ttu-id="a9def-161">Se si decide invece di ripristinare i criteri obsoleti, immettere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="a9def-161">If you decide instead to restore the old policy, enter:</span></span>

`$x = Import-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

`Set-CsClientPolicy -Instance $x`

<span data-ttu-id="a9def-162">Si noti che questo approccio funzionerà per la maggior parte dei criteri e delle impostazioni, ma non funzionerà con alcuni degli elementi più complessi, ovvero gli elementi che contengono più oggetti secondari, ad esempio le impostazioni di configurazione del routing, che contengono molte route vocali separate.</span><span class="sxs-lookup"><span data-stu-id="a9def-162">Note that this approach will work for most policies and settings but it won't work with some of the more complex items—items that contain multiple sub-objects (like routing configuration settings, which contain many separate voice routes).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


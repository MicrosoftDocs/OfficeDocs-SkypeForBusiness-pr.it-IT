---
title: 'Lync Server 2013: attività necessarie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: As-needed tasks
ms:assetid: b66bc6fe-f138-4cf4-ba7f-aee9a3e0497e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722431(v=OCS.15)
ms:contentKeyID: 63969643
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e96fd6e73e043c5ea7c476f939b3a3e06eadbdfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980958"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="as-needed-tasks-in-lync-server-2013"></a><span data-ttu-id="3e0cf-102">Attività necessarie in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e0cf-102">As-needed tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e0cf-103">_**Argomento Ultima modifica:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="3e0cf-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="3e0cf-104">Eseguire le attività seguenti in modo necessario.</span><span class="sxs-lookup"><span data-stu-id="3e0cf-104">Perform the following tasks as necessary.</span></span> <span data-ttu-id="3e0cf-105">Sono spesso coperti anche da procedure standard:</span><span class="sxs-lookup"><span data-stu-id="3e0cf-105">They are frequently also covered by standard procedures:</span></span>

  - <span data-ttu-id="3e0cf-106">**Controllo di sicurezza completo   ** È possibile eseguire regolarmente questo controllo, in risposta a un aggiornamento o alla riprogettazione del sistema di messaggistica oppure in risposta a una violazione della sicurezza tentata (o riuscita).</span><span class="sxs-lookup"><span data-stu-id="3e0cf-106">**Full Security Auditing   **You can perform this audit regularly, in response to an upgrade or redesign of the messaging system, or in response to an attempted (or successful) security breach.</span></span> <span data-ttu-id="3e0cf-107">La procedura può comportare la scansione di porte su server e firewall, verifiche di correzioni di sicurezza e test di penetrazione di terze parti.</span><span class="sxs-lookup"><span data-stu-id="3e0cf-107">The procedure may involve port scans on servers and firewalls, audits of security fixes, and third-party penetration tests.</span></span>

  - <span data-ttu-id="3e0cf-108">**Sostituire i certificati relativi alla scadenza**   il controllo dei certificati di Lync Server è una delle attività settimanali regolari e, come parte della procedura, un amministratore deve avere un record delle date di scadenza di tutti i certificati.</span><span class="sxs-lookup"><span data-stu-id="3e0cf-108">**Replace Certificates about to Expire**   Checking Lync Server Certificates is one of regular weekly tasks, and as part of the procedure an administrator should have a record of all certificates’ expiry dates.</span></span> <span data-ttu-id="3e0cf-109">Questo record consente a un amministratore di creare una notifica quando un determinato certificato sta per essere scaduto e sostituito in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="3e0cf-109">This record enables an administrator to create a notification when a particular certificate is about to be expired and replaced as needed.</span></span>

  - <span data-ttu-id="3e0cf-110">**Aggiornamento delle previsioni delle prestazioni**   aggiornare le previsioni delle prestazioni dopo un aggiornamento o una modifica della configurazione.</span><span class="sxs-lookup"><span data-stu-id="3e0cf-110">**Updating Performance Baselines**   Update performance baselines after an upgrade or configuration change.</span></span> <span data-ttu-id="3e0cf-111">L'organizzazione può usare le previsioni per misurare le prestazioni e rilevare i problemi che influiscono sulle prestazioni del sistema.</span><span class="sxs-lookup"><span data-stu-id="3e0cf-111">Your organization can use baselines to measure performance changes and to detect issues that affect system performance.</span></span>

  - <span data-ttu-id="3e0cf-112">**La gestione**   della configurazione iniziale del pool aziendale di pool Enterprise, server Standard Edition e qualsiasi altro server nell'ambiente dell'organizzazione sono stati eseguiti durante la distribuzione dei singoli server.</span><span class="sxs-lookup"><span data-stu-id="3e0cf-112">**Managing Enterprise Pool**   Initial configuration of Enterprise pools, Standard Edition servers, and any other servers in your organization's environment were done during deployment of the individual servers.</span></span> <span data-ttu-id="3e0cf-113">La gestione post-distribuzione di server e pool per i server standard e i pool Enterprise include le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="3e0cf-113">Post-deployment management of servers and pools for Standard Edition servers and Enterprise pools includes the following tasks:</span></span>
    
      - <span data-ttu-id="3e0cf-114">Gestione dei server front-end</span><span class="sxs-lookup"><span data-stu-id="3e0cf-114">Managing Front End Servers</span></span>
    
      - <span data-ttu-id="3e0cf-115">Gestione delle conferenze Web</span><span class="sxs-lookup"><span data-stu-id="3e0cf-115">Managing Web Conferencing</span></span>
    
      - <span data-ttu-id="3e0cf-116">Gestione dei servizi di conferenza</span><span class="sxs-lookup"><span data-stu-id="3e0cf-116">Managing Conferencing</span></span>
    
      - <span data-ttu-id="3e0cf-117">Modifica delle credenziali dell'account del servizio</span><span class="sxs-lookup"><span data-stu-id="3e0cf-117">Changing Service Account Credentials</span></span>
    
      - <span data-ttu-id="3e0cf-118">Gestione dei database</span><span class="sxs-lookup"><span data-stu-id="3e0cf-118">Managing Databases</span></span>
    
      - <span data-ttu-id="3e0cf-119">Avvio e arresto di servizi e disattivazione dei ruoli del server</span><span class="sxs-lookup"><span data-stu-id="3e0cf-119">Starting and Stopping Services and Deactivating Server Roles</span></span>
    
      - <span data-ttu-id="3e0cf-120">Rimozione di server e ruoli del server, rimozione di pool e disattivazione di server e pool</span><span class="sxs-lookup"><span data-stu-id="3e0cf-120">Removing Servers and Server Roles, Removing Pools, and Decommissioning Servers and Pools</span></span>

  - <span data-ttu-id="3e0cf-121">**Gestione dell'utilizzo**   è possibile configurare Lync Server 2013 in modo da specificare le funzionalità e le funzionalità più appropriate per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3e0cf-121">**Managing Usage**   You can configure Lync Server 2013 to provide the features and functionality that are most appropriate for your organization.</span></span> <span data-ttu-id="3e0cf-122">Sono inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="3e0cf-122">This includes the following:</span></span>
    
      - <span data-ttu-id="3e0cf-123">Gestione del supporto per le riunioni di conferenza Web locale</span><span class="sxs-lookup"><span data-stu-id="3e0cf-123">Managing Support for On-Premise Web Conferencing Meetings</span></span>
    
      - <span data-ttu-id="3e0cf-124">Gestione dell'uso di gruppi di distribuzione per l'invio di messaggi istantanei</span><span class="sxs-lookup"><span data-stu-id="3e0cf-124">Managing the Use of Distribution Groups to Send Instant Messages</span></span>
    
      - <span data-ttu-id="3e0cf-125">Gestione di contatti, presenza e query</span><span class="sxs-lookup"><span data-stu-id="3e0cf-125">Managing Contacts, Presence, and Queries</span></span>
    
      - <span data-ttu-id="3e0cf-126">Configurazione del filtro della versione client</span><span class="sxs-lookup"><span data-stu-id="3e0cf-126">Configuring Client Version Filtering</span></span>
    
      - <span data-ttu-id="3e0cf-127">Configurazione del filtro ISTANTANEo intelligente</span><span class="sxs-lookup"><span data-stu-id="3e0cf-127">Configuring Intelligent IM Filtering</span></span>
    
      - <span data-ttu-id="3e0cf-128">Configurazione dell'archiviazione, della registrazione del dettaglio delle chiamate e della conformità delle riunioni</span><span class="sxs-lookup"><span data-stu-id="3e0cf-128">Configuring Archiving, Call Detail Recording, and Meeting Compliance</span></span>

  - <span data-ttu-id="3e0cf-129">\*\*\*\*   Gestione della connettività di Edge Server la gestione continua dei server e delle impostazioni necessarie per la connettività esterna include quanto segue:</span><span class="sxs-lookup"><span data-stu-id="3e0cf-129">**Managing Edge Server Connectivity**   Ongoing management of the servers and settings required to provide external connectivity includes the following:</span></span>
    
      - <span data-ttu-id="3e0cf-130">Gestione della connettività tra server interni e Edge Server</span><span class="sxs-lookup"><span data-stu-id="3e0cf-130">Managing Connectivity between Internal Servers and Edge Servers</span></span>
    
      - <span data-ttu-id="3e0cf-131">Configurazione di interfacce e certificati interni ed esterni per Edge Server</span><span class="sxs-lookup"><span data-stu-id="3e0cf-131">Configuring Internal and External Interfaces and Certificates for Edge Servers</span></span>
    
      - <span data-ttu-id="3e0cf-132">Gestione dell'accesso dei partner federati</span><span class="sxs-lookup"><span data-stu-id="3e0cf-132">Managing Federated Partner Access</span></span>

  - <span data-ttu-id="3e0cf-133">**L'amministrazione della**   rubrica che amministra i server della rubrica include le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3e0cf-133">**Administering the Address Book**   Administering Address Book Servers includes the following:</span></span>
    
      - <span data-ttu-id="3e0cf-134">Configurazione della normalizzazione telefonica del server rubrica</span><span class="sxs-lookup"><span data-stu-id="3e0cf-134">Configuring Address Book Server phone normalization</span></span>
    
      - <span data-ttu-id="3e0cf-135">Gestione del server rubrica dalla riga di comando</span><span class="sxs-lookup"><span data-stu-id="3e0cf-135">Managing the Address Book Server from the command line</span></span>

  - <span data-ttu-id="3e0cf-136">\*\*\*\* La gestione degli account utente che gestiscono gli account utente include le operazioni seguenti:   </span><span class="sxs-lookup"><span data-stu-id="3e0cf-136">**Managing User Accounts**   Management of user accounts includes the following:</span></span>
    
      - <span data-ttu-id="3e0cf-137">Abilitazione degli account utente per Lync Server</span><span class="sxs-lookup"><span data-stu-id="3e0cf-137">Enabling User Accounts for Lync Server</span></span>
    
      - <span data-ttu-id="3e0cf-138">Configurazione degli utenti di Lync Server tramite la procedura guidata</span><span class="sxs-lookup"><span data-stu-id="3e0cf-138">Configuring Lync Server Users using the Wizard</span></span>
    
      - <span data-ttu-id="3e0cf-139">Configurazione delle singole proprietà degli account utente di Lync Server</span><span class="sxs-lookup"><span data-stu-id="3e0cf-139">Configuring Individual Lync Server User Account Properties</span></span>
    
      - <span data-ttu-id="3e0cf-140">Ricerca di utenti di Lync Server</span><span class="sxs-lookup"><span data-stu-id="3e0cf-140">Searching for Lync Server Users</span></span>
    
      - <span data-ttu-id="3e0cf-141">Spostamento degli utenti di Lync Server</span><span class="sxs-lookup"><span data-stu-id="3e0cf-141">Moving Lync Server Users</span></span>
    
      - <span data-ttu-id="3e0cf-142">Eliminazione degli utenti di Lync Server</span><span class="sxs-lookup"><span data-stu-id="3e0cf-142">Deleting Lync Server Users</span></span>

  - <span data-ttu-id="3e0cf-143">**Analisi dei file**   di log di Lync Server 2013 uno strumento molto utile, in genere usato per la risoluzione dei problemi, è lo strumento di registrazione di Lync Server 2013 descritto in dettaglio nell' [uso dello strumento di registrazione di Lync Server 2013](http://technet.microsoft.com/en-us/library/gg558599.aspx).</span><span class="sxs-lookup"><span data-stu-id="3e0cf-143">**Analyzing Lync Server 2013 Log Files**   One very helpful tool, generally used for troubleshooting, is the Lync Server 2013 Logging Tool described in detail in [Using Lync Server 2013 Logging Tool](http://technet.microsoft.com/en-us/library/gg558599.aspx).</span></span>

<span data-ttu-id="3e0cf-144">Poiché lo strumento di registrazione genera i file di log (in base al server), questi file di log possono essere visualizzati e analizzati usando lo strumento Snooper, se nel computer sono installati gli strumenti di Microsoft Office Server 12 Resource Kit.</span><span class="sxs-lookup"><span data-stu-id="3e0cf-144">Because the Logging Tool generates log files (on a per-server basis), these log files can be viewed and analyzed by using the Snooper tool, if the Microsoft Office Server 12 Resource Kit Tools are installed on the computer.</span></span> <span data-ttu-id="3e0cf-145">In caso contrario, i log possono essere analizzati anche usando un editor di testo, che è molto meno trasparente e più complesso rispetto all'uso dell'utilità Snooper.</span><span class="sxs-lookup"><span data-stu-id="3e0cf-145">Otherwise, logs can also be analyzed by using a text editor, which is much less transparent and more complex than using the Snooper utility.</span></span>

<span data-ttu-id="3e0cf-146">Per visualizzare e analizzare i messaggi di protocollo</span><span class="sxs-lookup"><span data-stu-id="3e0cf-146">To View and Analyze Protocol Messages</span></span>

<span data-ttu-id="3e0cf-147">Quando si termina la sessione di debug nello strumento registrazione, fare clic su Analizza file di log per visualizzare i file di log usando lo strumento Snooper.</span><span class="sxs-lookup"><span data-stu-id="3e0cf-147">In the Logging Tool, when you have ended the debug session, click Analyze Log Files to view the log files by using the Snooper tool.</span></span> <span data-ttu-id="3e0cf-148">È possibile analizzare i registri di protocollo per i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="3e0cf-148">You can analyze protocol logs for the following components:</span></span>

  - <span data-ttu-id="3e0cf-149">Lync Server SipStack (SIP)</span><span class="sxs-lookup"><span data-stu-id="3e0cf-149">Lync Server SipStack (SIP)</span></span>

  - <span data-ttu-id="3e0cf-150">Lync Server S4 (SIP)</span><span class="sxs-lookup"><span data-stu-id="3e0cf-150">Lync Server S4 (SIP)</span></span>

  - <span data-ttu-id="3e0cf-151">Lync Server Conference signaling Traffic (C3P), tra cui MCU infra C3P e lo stato di attivazione C3P</span><span class="sxs-lookup"><span data-stu-id="3e0cf-151">Lync Server Conferencing signaling traffic (C3P), including MCU Infra C3P and Focus C3P</span></span>

  - <span data-ttu-id="3e0cf-152">Traffico per le conferenze Web di Lync Server (PSOM)</span><span class="sxs-lookup"><span data-stu-id="3e0cf-152">Lync Server Web conferencing traffic (PSOM)</span></span>

  - <span data-ttu-id="3e0cf-153">Client della piattaforma client per le comunicazioni unificate di Lync Server (UCCP)</span><span class="sxs-lookup"><span data-stu-id="3e0cf-153">Lync Server Unified Communications Client Platform client (UCCP)</span></span>

  - <span data-ttu-id="3e0cf-154">Report sugli errori dal database di archiviazione</span><span class="sxs-lookup"><span data-stu-id="3e0cf-154">Error reports from the archiving database</span></span>

<span data-ttu-id="3e0cf-155">Per organizzare le prestazioni delle attività necessarie, vedere elenco di controllo delle operazioni necessario.</span><span class="sxs-lookup"><span data-stu-id="3e0cf-155">To help organize the performance of as-needed tasks, see As-Needed Operations Checklist.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3e0cf-156">Per informazioni dettagliate sull'amministrazione e le procedure di gestione, vedere la Guida all'amministrazione di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3e0cf-156">For detailed administration and management procedures, see the Microsoft Lync Server 2013 Administration Guide.</span></span>



</div>

<div>

## <a name="backup-and-restore-policies-or-configuration-settings"></a><span data-ttu-id="3e0cf-157">Criteri di backup (e ripristino) o impostazioni di configurazione</span><span class="sxs-lookup"><span data-stu-id="3e0cf-157">Backup (and restore) policies or configuration settings</span></span>

<span data-ttu-id="3e0cf-158">Lync Server 2013 consente di eseguire il backup e il ripristino dell'intero sistema.</span><span class="sxs-lookup"><span data-stu-id="3e0cf-158">Lync Server 2013 lets you back up and restore the whole system.</span></span> <span data-ttu-id="3e0cf-159">IIF di cui si vuole eseguire il backup (e quindi magari un giorno ripristinare) un singolo criterio o una singola raccolta di impostazioni di configurazione, recuperare i criteri appropriati e quindi reindirizzare l'oggetto al cmdlet Export-Clixml, che salva le informazioni sui criteri come file XML:</span><span class="sxs-lookup"><span data-stu-id="3e0cf-159">Iif you want to back up (and then maybe someday restore) a single policy or a single collection of configuration settings, retrieve the appropriate policy, and then pipe that object to the Export-Clixml cmdlet, which saves the policy information as an XML file:</span></span>

`Get-CsClientPolicy -Identity "RedmondClientPolicy" | Export-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

<span data-ttu-id="3e0cf-160">Ora puoi provare a usare RedmondClientPolicy e modificare molte delle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="3e0cf-160">You may now experiment with RedmondClientPolicy and change lots of the settings.</span></span> <span data-ttu-id="3e0cf-161">Se invece si decide di ripristinare il vecchio criterio, immettere:</span><span class="sxs-lookup"><span data-stu-id="3e0cf-161">If you decide instead to restore the old policy, enter:</span></span>

`$x = Import-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

`Set-CsClientPolicy -Instance $x`

<span data-ttu-id="3e0cf-162">Tieni presente che questo approccio funzionerà per la maggior parte dei criteri e delle impostazioni, ma non funzionerà con alcuni degli elementi più complessi, ovvero gli elementi che contengono più oggetti secondari, ad esempio le impostazioni di configurazione del routing, che contengono molte route vocali separate.</span><span class="sxs-lookup"><span data-stu-id="3e0cf-162">Note that this approach will work for most policies and settings but it won't work with some of the more complex items—items that contain multiple sub-objects (like routing configuration settings, which contain many separate voice routes).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


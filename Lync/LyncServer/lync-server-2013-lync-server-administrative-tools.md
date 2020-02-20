---
title: 'Lync Server 2013: strumenti di amministrazione di Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server administrative tools
ms:assetid: 9b006f93-4f3d-461d-89b8-e80a34fdb3c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195756(v=OCS.15)
ms:contentKeyID: 48184972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85ba9b1d9848fa51d798dd93b9cbc53daf69a6b7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150427"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-administrative-tools"></a><span data-ttu-id="d69b2-102">Strumenti di amministrazione di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d69b2-102">Lync Server 2013 administrative tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d69b2-103">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="d69b2-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="d69b2-104">In questo argomento vengono descritti gli strumenti di amministrazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d69b2-104">This topic describes the administrative tools for Lync Server 2013.</span></span>

<span data-ttu-id="d69b2-105">Gli strumenti di amministrazione vengono installati per impostazione predefinita in ogni server Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d69b2-105">The administrative tools are installed by default on each Lync Server server.</span></span> <span data-ttu-id="d69b2-106">Inoltre, è possibile installare gli strumenti di amministrazione in altri computer, ad esempio le console amministrative dedicate.</span><span class="sxs-lookup"><span data-stu-id="d69b2-106">Additionally, you can install the administrative tools on other computers, such as dedicated administrative consoles.</span></span> <span data-ttu-id="d69b2-107">Per le procedure per l'installazione degli strumenti di amministrazione, vedere [Install Lync Server 2013 Administrative Tools](lync-server-2013-install-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d69b2-107">For procedures to install the administrative tools, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span> <span data-ttu-id="d69b2-108">Per le procedure per l'apertura degli strumenti per l'esecuzione di attività di gestione, vedere [Open Lync Server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d69b2-108">For procedures to open the tools to perform management tasks, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

<span data-ttu-id="d69b2-109">Assicurarsi di esaminare l'infrastruttura, il sistema operativo, il software e i requisiti di diritti di amministratore prima di installare o utilizzare gli strumenti di amministrazione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d69b2-109">Ensure that you review infrastructure, operating system, software, and administrator rights requirements before you install or use the Lync Server administrative tools.</span></span> <span data-ttu-id="d69b2-110">Per informazioni dettagliate sui requisiti dell'infrastruttura, vedere [Administrative Tools Infrastructure requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d69b2-110">For details about infrastructure requirements, see [Administrative tools infrastructure requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span></span> <span data-ttu-id="d69b2-111">Per informazioni dettagliate sui requisiti software e del sistema operativo per l'installazione degli strumenti di amministrazione di Lync Server, vedere [Server and Tools Operating System Support in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [Additional Software Requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md), and [additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d69b2-111">For details about operating system and software requirements to install the Lync Server administrative tools, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md), and [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span> <span data-ttu-id="d69b2-112">I diritti e le autorizzazioni degli utenti necessari per installare e utilizzare gli strumenti sono descritti in [autorizzazioni e diritti di amministratore necessari per l'installazione e l'amministrazione di Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).</span><span class="sxs-lookup"><span data-stu-id="d69b2-112">The user rights and permissions required to install and use the tools are described in [Administrator rights and permissions required for setup and administration of Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).</span></span>

<span data-ttu-id="d69b2-113">Gli strumenti di amministrazione sono costituiti dai seguenti:</span><span class="sxs-lookup"><span data-stu-id="d69b2-113">The administrative tools consist of the following:</span></span>

  - <span data-ttu-id="d69b2-114">**La distribuzione guidata**   di Lync Server consente di distribuire Lync Server e di installare tutti gli strumenti di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="d69b2-114">**Lync Server Deployment Wizard**   Use to deploy Lync Server and to install all administrative tools.</span></span>

  - <span data-ttu-id="d69b2-115">**Il generatore**   di topologie di Lync Server utilizza per definire i componenti della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d69b2-115">**Lync Server Topology Builder**   Use to define components in your deployment.</span></span>

  - <span data-ttu-id="d69b2-116">**Il pannello**   di controllo di Lync Server utilizza un'interfaccia basata sul Web per la gestione continua della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d69b2-116">**Lync Server Control Panel**   Use for ongoing management of your deployment by using a web-based interface.</span></span>

  - <span data-ttu-id="d69b2-117">**Lync Server Management Shell**   utilizza la riga di comando per la gestione continua della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d69b2-117">**Lync Server Management Shell**   Use for ongoing management of your deployment by using the command line.</span></span>

  - <span data-ttu-id="d69b2-118">**Strumento di registrazione di Lync Server**   utilizzato per la risoluzione dei problemi della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d69b2-118">**Lync Server Logging tool**   Use to troubleshoot problems in your deployment.</span></span>

  - <span data-ttu-id="d69b2-119">**Servizio di registrazione centralizzato**   raccogliere i registri e i file di traccia da un computer, un pool, un sito o un globale.</span><span class="sxs-lookup"><span data-stu-id="d69b2-119">**Centralized Logging Service**   Collect logs and trace files from one computer, pool, site or global.</span></span> <span data-ttu-id="d69b2-120">Selezionare e definire gli scenari che contengono provider, flag e livelli di traccia.</span><span class="sxs-lookup"><span data-stu-id="d69b2-120">Select and define scenarios that contain providers, flags and trace levels.</span></span> <span data-ttu-id="d69b2-121">La registrazione viene raccolta, aggregata e visualizzata con strumenti quali qualsiasi strumento basato su testo o Snooper. exe.</span><span class="sxs-lookup"><span data-stu-id="d69b2-121">Logging is collected, aggregated and displayed with tools such as any text-based tool or Snooper.exe.</span></span>

<span data-ttu-id="d69b2-122">È possibile gestire la distribuzione principalmente utilizzando il generatore di topologie e il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d69b2-122">You can manage your deployment by primarily using Topology Builder and Lync Server Control Panel.</span></span>

<div>

## <a name="deployment-wizard"></a><span data-ttu-id="d69b2-123">Distribuzione guidata</span><span class="sxs-lookup"><span data-stu-id="d69b2-123">Deployment Wizard</span></span>

<span data-ttu-id="d69b2-124">È necessario utilizzare la distribuzione guidata di Lync Server inclusa nel supporto di installazione per installare tutti gli strumenti di amministrazione su un computer in cui non è stato ancora installato Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d69b2-124">You must use the Lync Server Deployment Wizard included on the installation media to install all administrative tools onto a computer on which you have not already installed Lync Server.</span></span> <span data-ttu-id="d69b2-125">Durante il processo di installazione degli strumenti di amministrazione, la distribuzione guidata di Lync Server viene installata localmente insieme agli altri strumenti, in modo che sia possibile utilizzarla in un secondo momento per installare i file per i componenti aggiuntivi o rimuovere i file per i componenti che non si desidera utilizzare nel computer.</span><span class="sxs-lookup"><span data-stu-id="d69b2-125">During the administrative tools installation process, the Lync Server Deployment Wizard is installed locally along with the other tools so that you can later use it to install files for additional components or remove files for components that you do not want on the computer.</span></span>

<span data-ttu-id="d69b2-126">Per informazioni dettagliate sull'esecuzione della distribuzione guidata di Lync Server per la prima volta dal supporto di installazione di Lync Server, vedere [Install Lync server 2013 Administrative Tools](lync-server-2013-install-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d69b2-126">For details about how to run the Lync Server Deployment Wizard for the first time from the Lync Server installation media, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span>

</div>

<div>

## <a name="topology-builder"></a><span data-ttu-id="d69b2-127">Strumento di generazione topologia</span><span class="sxs-lookup"><span data-stu-id="d69b2-127">Topology Builder</span></span>

<span data-ttu-id="d69b2-128">Per informazioni dettagliate sulle attività di distribuzione che è possibile eseguire utilizzando Generatore di topologie, vedere la documentazione relativa alla distribuzione per ogni ruolo del server.</span><span class="sxs-lookup"><span data-stu-id="d69b2-128">For details about deployment tasks that you can you perform by using Topology Builder, see the Deployment documentation for each server role.</span></span>

</div>

<div>

## <a name="lync-server-control-panel"></a><span data-ttu-id="d69b2-129">Pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="d69b2-129">Lync Server Control Panel</span></span>

<span data-ttu-id="d69b2-130">È possibile utilizzare il pannello di controllo di Lync Server 2013 per eseguire la maggior parte delle attività amministrative necessarie per la gestione e la manutenzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d69b2-130">You can use Lync Server 2013 Control Panel to perform most of the administrative tasks required to manage and maintain Lync Server 2013.</span></span> <span data-ttu-id="d69b2-131">Nel pannello di controllo di Lync Server è disponibile un'interfaccia utente grafica (GUI) per gestire la configurazione dei server che eseguono Lync Server, oltre a utenti, client e dispositivi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d69b2-131">Lync Server Control Panel provides you with a graphical user interface (GUI) to manage the configuration of the servers running Lync Server, in addition to the users, clients, and devices in your organization.</span></span> <span data-ttu-id="d69b2-132">Lync Server Management Shell utilizza il pannello di controllo di Lync Server come meccanismo sottostante per eseguire la configurazione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d69b2-132">Lync Server Management Shell uses Lync Server Control Panel as the underlying mechanism to perform Lync Server configuration.</span></span>

<span data-ttu-id="d69b2-133">Il pannello di controllo di Lync Server viene installato automaticamente in ogni server Lync Server front end server o Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="d69b2-133">Lync Server Control Panel is automatically installed on every Lync Server Front End Server or Standard Edition server.</span></span> <span data-ttu-id="d69b2-134">In questa versione è possibile amministrare i server perimetrali in remoto.</span><span class="sxs-lookup"><span data-stu-id="d69b2-134">In this release, you administer Edge Servers remotely.</span></span> <span data-ttu-id="d69b2-135">È inoltre possibile installare il pannello di controllo di Lync Server in un altro computer, ad esempio una console di gestione da cui si desidera gestire in modo centralizzato Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d69b2-135">You can also install Lync Server Control Panel on another computer, such as a management console from which you want to centrally manage Lync Server.</span></span> <span data-ttu-id="d69b2-136">Per informazioni dettagliate, vedere [Install Lync Server 2013 Administrative Tools](lync-server-2013-install-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d69b2-136">For details, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="d69b2-137">Per configurare le impostazioni utilizzando il pannello di controllo di Lync Server, è necessario essere connessi utilizzando un account assegnato al ruolo CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="d69b2-137">To configure settings using Lync Server Control Panel, you must be logged in using an account that is assigned to the CsAdministrator role.</span></span> <span data-ttu-id="d69b2-138">Per informazioni dettagliate sui ruoli amministrativi predefiniti disponibili in Lync Server 2013, vedere <A href="lync-server-2013-planning-for-role-based-access-control.md">pianificazione del controllo di accesso basato sui ruoli in Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d69b2-138">For details about the predefined administrative roles available in Lync Server 2013, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="d69b2-139">Per configurare le impostazioni utilizzando il pannello di controllo di Lync Server, è necessario utilizzare anche un computer con una risoluzione minima dello schermo pari a 1024 x 768.</span><span class="sxs-lookup"><span data-stu-id="d69b2-139">To configure settings using Lync Server Control Panel, you must also use a computer with a minimum screen resolution of 1024 x 768.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="lync-server-management-shell"></a><span data-ttu-id="d69b2-140">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="d69b2-140">Lync Server Management Shell</span></span>

<span data-ttu-id="d69b2-141">In Lync Server, Lync Server Management Shell fornisce un nuovo metodo per l'amministrazione e la gestione.</span><span class="sxs-lookup"><span data-stu-id="d69b2-141">In Lync Server, the Lync Server Management Shell provides a new method for administration and management.</span></span> <span data-ttu-id="d69b2-142">Lync Server Management Shell è un'interfaccia di gestione potente, basata sull'interfaccia della riga di comando di Windows PowerShell, che include un set completo di cmdlet specifici di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d69b2-142">Lync Server Management Shell is a powerful management interface, built on the Windows PowerShell command-line interface, that includes a comprehensive set of cmdlets that are specific to Lync Server.</span></span> <span data-ttu-id="d69b2-143">Con Lync Server Management Shell, è possibile ottenere un set completo di controlli di configurazione e automazione.</span><span class="sxs-lookup"><span data-stu-id="d69b2-143">With Lync Server Management Shell, you gain a rich set of configuration and automation controls.</span></span> <span data-ttu-id="d69b2-144">Il generatore di topologie e il pannello di controllo di Lync Server implementano sottoinsiemi di questi cmdlet per supportare la gestione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d69b2-144">Topology Builder and Lync Server Control Panel both implement subsets of these cmdlets to support management of Lync Server.</span></span> <span data-ttu-id="d69b2-145">Lync Server Management Shell include cmdlet per tutte le attività di amministrazione di Lync Server ed è possibile utilizzare i cmdlet singolarmente per gestire la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d69b2-145">The Lync Server Management Shell includes cmdlets for all Lync Server administration tasks, and you can use the cmdlets individually to manage your deployment.</span></span> <span data-ttu-id="d69b2-146">Per informazioni dettagliate, vedere la documentazione relativa a [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) o la guida della riga di comando per ogni cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d69b2-146">For details, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation or the command-line help for each cmdlet.</span></span>

</div>

<div>

## <a name="logging-tool"></a><span data-ttu-id="d69b2-147">Strumento di registrazione</span><span class="sxs-lookup"><span data-stu-id="d69b2-147">Logging Tool</span></span>

<span data-ttu-id="d69b2-148">Lo strumento di registrazione di Lync Server facilita la risoluzione dei problemi acquisendo le informazioni di registrazione e traccia dal prodotto durante l'esecuzione del prodotto.</span><span class="sxs-lookup"><span data-stu-id="d69b2-148">The Lync Server Logging Tool facilitates troubleshooting by capturing logging and tracing information from the product while the product is running.</span></span> <span data-ttu-id="d69b2-149">È possibile utilizzare lo strumento per eseguire le sessioni di debug su qualsiasi ruolo del server Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d69b2-149">You can use the tool to run debug sessions on any Lync Server server role.</span></span> <span data-ttu-id="d69b2-150">Per informazioni dettagliate sullo strumento di registrazione, vedere la documentazione dello strumento di registrazione di Lync Server 2010 nella [https://go.microsoft.com/fwlink/p/?linkId=199265](https://go.microsoft.com/fwlink/p/?linkid=199265)libreria TechNet all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="d69b2-150">For details about the Logging Tool, see the Lync Server 2010 Logging Tool documentation on the TechNet Library at [https://go.microsoft.com/fwlink/p/?linkId=199265](https://go.microsoft.com/fwlink/p/?linkid=199265).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d69b2-151">Il servizio di registrazione centralizzato è consigliato per tutte le raccolte di registrazione tramite lo strumento di registrazione di Lync Server in tutte le circostanze.</span><span class="sxs-lookup"><span data-stu-id="d69b2-151">The Centralized Logging Service is recommended for all logging collection over the Lync Server Logging Tool in all circumstances.</span></span> <span data-ttu-id="d69b2-152">Lo strumento di registrazione di Lync Server continuerà a funzionare, ma interferirà o verrà reso prevalentemente inefficace se il servizio di registrazione centralizzato è già in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d69b2-152">The Lync Server Logging Tool will still work, but it will interfere or be rendered mostly ineffective if the Centralized Logging Service is already running.</span></span> <span data-ttu-id="d69b2-153">È consigliabile utilizzare solo il servizio di registrazione centralizzato o lo strumento di registrazione di Lync Server, ma non contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="d69b2-153">You should use only the Centralized Logging Service or the Lync Server Logging Tool, but never both concurrently.</span></span> <span data-ttu-id="d69b2-154">Per ulteriori informazioni sul servizio di registrazione centralizzato e sul motivo per cui utilizzarlo in modo esclusivo, vedere <A href="lync-server-2013-using-the-centralized-logging-service.md">utilizzo del servizio di registrazione centralizzato in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d69b2-154">For more information on the Centralized Logging Service and why you should use it exclusively, see <A href="lync-server-2013-using-the-centralized-logging-service.md">Using the Centralized Logging Service in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d69b2-155">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="d69b2-155">In This Section</span></span>

  - [<span data-ttu-id="d69b2-156">Requisiti dell'infrastruttura degli strumenti di amministrazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d69b2-156">Administrative tools infrastructure requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-infrastructure-requirements.md)

  - [<span data-ttu-id="d69b2-157">Supporto del sistema operativo per server e strumenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d69b2-157">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)

  - [<span data-ttu-id="d69b2-158">Requisiti software per gli strumenti di amministrazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d69b2-158">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)

  - [<span data-ttu-id="d69b2-159">Autorizzazioni e diritti di amministratore necessari per l'installazione e l'amministrazione di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d69b2-159">Administrator rights and permissions required for setup and administration of Lync Server 2013</span></span>](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

  - [<span data-ttu-id="d69b2-160">Requisiti per la pubblicazione di una topologia in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d69b2-160">Requirements to publish a topology in Lync Server 2013</span></span>](lync-server-2013-requirements-to-publish-a-topology.md)

  - [<span data-ttu-id="d69b2-161">Installare gli strumenti di amministrazione di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d69b2-161">Install Lync Server 2013 administrative tools</span></span>](lync-server-2013-install-lync-server-administrative-tools.md)

  - [<span data-ttu-id="d69b2-162">Aprire gli strumenti di amministrazione di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d69b2-162">Open Lync Server 2013 administrative tools</span></span>](lync-server-2013-open-lync-server-administrative-tools.md)

  - [<span data-ttu-id="d69b2-163">Risoluzione dei problemi relativi al Pannello di controllo di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d69b2-163">Troubleshooting Lync Server 2013 Control Panel</span></span>](lync-server-2013-troubleshooting-lync-server-2013-control-panel.md)

  - [<span data-ttu-id="d69b2-164">Utilizzo del servizio di registrazione centralizzato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d69b2-164">Using the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-using-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d69b2-165">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d69b2-165">See Also</span></span>


[<span data-ttu-id="d69b2-166">Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="d69b2-166">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


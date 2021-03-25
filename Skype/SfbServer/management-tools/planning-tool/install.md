---
title: Installare lo strumento di pianificazione in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: Prima di iniziare a progettare e pianificare l'infrastruttura di Skype for Business Server 2015 utilizzando lo strumento di pianificazione di Skype for Business Server 2015, è necessario installare lo strumento di pianificazione. Lo strumento di pianificazione non deve essere distribuito in una workstation o in un server che fa parte del dominio o dell'infrastruttura in cui si prevede di installare Skype for Business Server 2015. Il file Readme che accompagna lo strumento di pianificazione contiene informazioni importanti sull'installazione e sull'utilizzo dello strumento. Alcune delle informazioni contenute nel file Leggimi vengono riportate in questo argomento per maggiore chiarezza.
ms.openlocfilehash: 29a3bd35191cf326cafd1f4ad4f14fab50e47ea3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122380"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a><span data-ttu-id="2ef95-106">Installare lo strumento di pianificazione in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2ef95-106">Install the Planning Tool in Skype for Business Server 2015</span></span>

<span data-ttu-id="2ef95-107">Prima di iniziare a progettare e pianificare l'infrastruttura di Skype for Business Server 2015 utilizzando lo strumento di pianificazione di Skype for Business Server 2015, è necessario installare lo strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="2ef95-107">Before you begin designing and planning your Skype for Business Server 2015 infrastructure by using the Skype for Business Server 2015 Planning Tool, you must first install the Planning Tool.</span></span> <span data-ttu-id="2ef95-108">Lo strumento di pianificazione non deve essere distribuito in una workstation o in un server che fa parte del dominio o dell'infrastruttura in cui si prevede di installare Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2ef95-108">The Planning Tool does not need to be deployed to a workstation or server that is part of the domain or infrastructure where you plan to install Skype for Business Server 2015.</span></span> <span data-ttu-id="2ef95-109">Il file Readme che accompagna lo strumento di pianificazione contiene informazioni importanti sull'installazione e sull'utilizzo dello strumento.</span><span class="sxs-lookup"><span data-stu-id="2ef95-109">The Readme file that accompanies the Planning Tool details important information about installing and using the tool.</span></span> <span data-ttu-id="2ef95-110">Alcune delle informazioni contenute nel file Leggimi vengono riportate in questo argomento per maggiore chiarezza.</span><span class="sxs-lookup"><span data-stu-id="2ef95-110">Some of the information in the Readme file is duplicated here for clarity.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2ef95-111">Lo strumento di pianificazione richiede l'installazione da parte di un utente con diritti e autorizzazioni di amministratore nel computer in cui deve essere installato lo strumento.</span><span class="sxs-lookup"><span data-stu-id="2ef95-111">The Planning Tool requires installation by a user with administrator rights and permissions on the computer on which the tool is to be installed.</span></span>

<span data-ttu-id="2ef95-112">I sistemi operativi supportati per l'installazione e il funzionamento dello strumento di pianificazione sono:</span><span class="sxs-lookup"><span data-stu-id="2ef95-112">The supported operating systems for installation and operation of the Planning Tool are:</span></span>

- <span data-ttu-id="2ef95-113">Windows 10</span><span class="sxs-lookup"><span data-stu-id="2ef95-113">Windows 10</span></span>

- <span data-ttu-id="2ef95-114">Windows 8</span><span class="sxs-lookup"><span data-stu-id="2ef95-114">Windows 8</span></span>

- <span data-ttu-id="2ef95-115">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="2ef95-115">Windows 8.1</span></span>

- <span data-ttu-id="2ef95-116">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="2ef95-116">Windows Server 2012</span></span>

- <span data-ttu-id="2ef95-117">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="2ef95-117">Windows Server 2012 R2</span></span>

- <span data-ttu-id="2ef95-118">Windows 7, edizione a 32 bit</span><span class="sxs-lookup"><span data-stu-id="2ef95-118">Windows 7, 32-bit edition</span></span>

- <span data-ttu-id="2ef95-119">Windows 7, edizione a 64 bit con Windows on Win32 (WOW)</span><span class="sxs-lookup"><span data-stu-id="2ef95-119">Windows 7, 64-bit edition using Windows on Win32 (WOW)</span></span>

- <span data-ttu-id="2ef95-120">Windows Server 2008 R2, con WOW</span><span class="sxs-lookup"><span data-stu-id="2ef95-120">Windows Server 2008 R2, using WOW</span></span>

<span data-ttu-id="2ef95-121">Inoltre, lo strumento di pianificazione richiede Microsoft .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="2ef95-121">Additionally, the Planning Tool requires Microsoft .NET Framework 4.5.</span></span>

<span data-ttu-id="2ef95-122">Dopo aver soddisfatto i requisiti di preinstallazione, è possibile installare lo strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="2ef95-122">After the preinstallation requirements are met, you can then install the Planning Tool.</span></span>



## <a name="to-install-the-planning-tool"></a><span data-ttu-id="2ef95-123">Per installare lo strumento di pianificazione</span><span class="sxs-lookup"><span data-stu-id="2ef95-123">To install the Planning Tool</span></span>

1. <span data-ttu-id="2ef95-124">Accedere al computer locale come membro del gruppo Administrators.</span><span class="sxs-lookup"><span data-stu-id="2ef95-124">Log on to the local computer as a member of the Administrators group.</span></span>

2. <span data-ttu-id="2ef95-125">Utilizzando Esplora risorse o una finestra di comando, individuare la directory in cui sono stati scaricati i file di installazione dello strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="2ef95-125">Using Windows Explorer or a command window, locate the directory where you downloaded the Planning Tool installation files.</span></span>

3. <span data-ttu-id="2ef95-126">Individuare il SkypeForBusinessPlanningTool.msi.</span><span class="sxs-lookup"><span data-stu-id="2ef95-126">Locate the SkypeForBusinessPlanningTool.msi.</span></span> <span data-ttu-id="2ef95-127">In Esplora risorse fare doppio clic sul file.</span><span class="sxs-lookup"><span data-stu-id="2ef95-127">In Windows Explorer, double-click the file.</span></span> <span data-ttu-id="2ef95-128">Nella finestra di comando digitare il nome del file e quindi premere **INVIO** per eseguire il file.</span><span class="sxs-lookup"><span data-stu-id="2ef95-128">In the command window, type the name of the file, and then press **Enter** to run the file.</span></span>

4. <span data-ttu-id="2ef95-129">Nella pagina iniziale di **Skype for Business Server 2015, Configurazione** guidata strumento di pianificazione, fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="2ef95-129">On the Welcome page of the **Skype for Business Server 2015, Planning Tool Setup Wizard**, click **Next**.</span></span>

5. <span data-ttu-id="2ef95-130">Leggere il **Contratto di Licenza con l'utente finale**, selezionare **Accetto i termini del Contratto di Licenza** se si sceglie di accettare le condizioni per l'utilizzo riportate nel contratto e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="2ef95-130">Review the **End-User License Agreement**, select **I accept the terms in the License Agreement** if you choose to accept the terms of use in the license agreement, and then click **Next**.</span></span>

6. <span data-ttu-id="2ef95-131">Scegliere dove installare i file dello strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="2ef95-131">Choose where to install the Planning Tool files.</span></span> <span data-ttu-id="2ef95-132">Il percorso predefinito è C:\Programmi (x86)\Skype for Business Server 2015\Planning Tool.</span><span class="sxs-lookup"><span data-stu-id="2ef95-132">The default location is C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool.</span></span> <span data-ttu-id="2ef95-133">Se si desidera cambiarlo, fare clic su **Cambia**.</span><span class="sxs-lookup"><span data-stu-id="2ef95-133">If you want to change the installation location, click **Change**.</span></span> <span data-ttu-id="2ef95-134">In **Modifica cartella di destinazione**, individuare o digitare il percorso in cui installare i file, fare clic su **OK** e quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="2ef95-134">On **Change destination folder**, browse or type the location to install the files, click **OK**, and then click **Next**.</span></span>

7. <span data-ttu-id="2ef95-135">Il programma di installazione è ora pronto per installare lo strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="2ef95-135">The installer is now ready to install the Planning Tool.</span></span> <span data-ttu-id="2ef95-136">Fare clic su **Installa** per avviare il processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="2ef95-136">Click **Install** to begin the installation process.</span></span>

8. <span data-ttu-id="2ef95-137">L'installazione verrà avviata e verrà visualizzato il relativo stato.</span><span class="sxs-lookup"><span data-stu-id="2ef95-137">The installation will start, and the progress will be displayed.</span></span> <span data-ttu-id="2ef95-138">Al termine dell'installazione, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="2ef95-138">After the installation is successfully completed, click **Finish**.</span></span>

9. <span data-ttu-id="2ef95-139">Lo strumento di pianificazione è pronto per l'uso.</span><span class="sxs-lookup"><span data-stu-id="2ef95-139">The Planning Tool is ready for use.</span></span>

## <a name="optional-software"></a><span data-ttu-id="2ef95-140">Software facoltativo</span><span class="sxs-lookup"><span data-stu-id="2ef95-140">Optional Software</span></span>
<span data-ttu-id="2ef95-141"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="2ef95-141"><a name="Optional_Software"> </a></span></span>

<span data-ttu-id="2ef95-142">Lo strumento di pianificazione di Skype for Business Server 2015 è progettato per l'esportazione in Microsoft Excel e Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="2ef95-142">The Skype for Business Server 2015 Planning Tool is designed to export to Microsoft Excel and Microsoft Visio.</span></span> <span data-ttu-id="2ef95-143">Anche se queste applicazioni non sono necessarie per il funzionamento dello strumento di pianificazione, aggiungono un valore significativo alla distribuzione e alla documentazione della progettazione.</span><span class="sxs-lookup"><span data-stu-id="2ef95-143">While these applications are not required for the operation of the Planning Tool, they do add significant value to the deployment and documentation of your design.</span></span>

### <a name="microsoft-excel"></a><span data-ttu-id="2ef95-144">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="2ef95-144">Microsoft Excel</span></span>

<span data-ttu-id="2ef95-145">L'esportazione della struttura in Microsoft Excel crea un report che visualizza sette schede nel foglio di calcolo:</span><span class="sxs-lookup"><span data-stu-id="2ef95-145">Exporting your design to Microsoft Excel creates a report that displays seven tabs in the spreadsheet:</span></span>

- <span data-ttu-id="2ef95-146">Riepilogo: visualizza informazioni sulla configurazione del sito, tra cui il numero di utenti, le impostazioni di capacità e le informazioni sul profilo del server.</span><span class="sxs-lookup"><span data-stu-id="2ef95-146">Summary - Displays information on site configuration, including user count, capacity settings, and server profile information.</span></span>

- <span data-ttu-id="2ef95-147">Profilo hardware - Visualizza un report sulle configurazioni hardware consigliate per i server specificati nella topologia, tra cui CPU, memoria, disco e interfaccia di rete.</span><span class="sxs-lookup"><span data-stu-id="2ef95-147">Hardware Profile - Displays a report on the recommended hardware configurations for servers that are specified in the topology, including CPU, memory, disk, and network interface.</span></span> <span data-ttu-id="2ef95-148">Sono incluse anche la quantità e le specifiche consigliate per i componenti server.</span><span class="sxs-lookup"><span data-stu-id="2ef95-148">The quantity and recommended specifications for the server components are also included.</span></span> <span data-ttu-id="2ef95-149">Inoltre, ogni server viene definito dal sito per fornire una rappresentazione completa dei requisiti del server in base al sito.</span><span class="sxs-lookup"><span data-stu-id="2ef95-149">In addition, each server is defined by site to provide a complete representation of server requirements by site.</span></span>

- <span data-ttu-id="2ef95-150">Requisiti delle porte - Visualizza un report di tutte le porte abilitate e l'associazione al bilanciamento del carico DNS (Domain Name System) e ai servizi di bilanciamento del carico hardware (HLB).</span><span class="sxs-lookup"><span data-stu-id="2ef95-150">Ports Requirements - Displays a report of all ports that are enabled, and the association to Domain Name System load balancing (DNS LB) and hardware load balancers (HLB).</span></span> <span data-ttu-id="2ef95-151">È consigliabile utilizzare questo report per pianificare le configurazioni firewall e DNS LB e HLB.</span><span class="sxs-lookup"><span data-stu-id="2ef95-151">You should use this report to plan your firewall and DNS LB and HLB configurations.</span></span>

- <span data-ttu-id="2ef95-152">Rapporto riepilogativo- Visualizza il riepilogo generale delle impostazioni necessarie per configurare la rete di server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="2ef95-152">Summary Report - Displays the general summary of the settings that are required to set up your Edge Server network.</span></span>

- <span data-ttu-id="2ef95-153">Rapporto certificati - Visualizza il nome soggetto e i nomi alternativi soggetto necessari per i certificati necessari per l'esecuzione dei server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="2ef95-153">Certificates Report - Displays the subject name and subject alternate names that are required for the certificates needed to get the Edge Servers running.</span></span>

- <span data-ttu-id="2ef95-154">Rapporto firewall - Visualizza le porte di origine e di destinazione e gli indirizzi IP per le interfacce esterne e interne.</span><span class="sxs-lookup"><span data-stu-id="2ef95-154">Firewall Report - Displays the source and destination ports and IP addresses for both External and Internal interfaces.</span></span>

- <span data-ttu-id="2ef95-155">Rapporto DNS - Visualizza il nome di dominio completo (FQDN) e gli indirizzi IP/VIP necessari per ogni voce DNS creata.</span><span class="sxs-lookup"><span data-stu-id="2ef95-155">DNS Report - Displays the fully qualified domain name (FQDN) and IP/VIP addresses required for each DNS entry that you create.</span></span>

### <a name="microsoft-visio"></a><span data-ttu-id="2ef95-156">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="2ef95-156">Microsoft Visio</span></span>

<span data-ttu-id="2ef95-p110">L'esportazione del progetto in Microsoft Visio consente di creare un diagramma da usare per la documentazione della topologia e dell'infrastruttura configurate. Il diagramma importato può essere modificato e riorganizzato in base alle specifiche esigenze per la documentazione. Il diagramma di Visio tipico includerà:</span><span class="sxs-lookup"><span data-stu-id="2ef95-p110">Exporting your design to Microsoft Visio creates a diagram for use in your documentation purposes of your configured topology and infrastructure. The imported diagram can be edited and rearranged to meet your documentation needs. The typical Visio diagram will include:</span></span>

> [!NOTE]
> <span data-ttu-id="2ef95-160">Se la struttura è sufficientemente grande da richiedere più di tre Front End Server, verrà creata una pagina aggiuntiva per il pool Front End, i Front End Server, il computer che esegue SQL Server, gli indirizzi IP e gli FQDN.</span><span class="sxs-lookup"><span data-stu-id="2ef95-160">If your design is large enough to require more than three Front End Servers, an additional page will be created for the Front End pool, Front End Servers, the computer running SQL Server, IP addresses, and FQDNs.</span></span>

- <span data-ttu-id="2ef95-161">Topologia globale - Diagramma dei siti di Skype for Business Server 2015 configurati.</span><span class="sxs-lookup"><span data-stu-id="2ef95-161">Global Topology - Diagram of configured Skype for Business Server 2015 sites.</span></span>

- <span data-ttu-id="2ef95-162">Scheda Nome sito - Visualizza la topologia di configurazione del sito con server perimetrali, firewall, PSTN (Public Switched Telephone Network) con gateway e la distribuzione interna del server.</span><span class="sxs-lookup"><span data-stu-id="2ef95-162">Site Name tab - Displays the site configuration topology with Edge Server, firewall, public switched telephone network (PSTN) with gateways, and the internal server deployment.</span></span> <span data-ttu-id="2ef95-163">La distribuzione interna è costituita da server e pool configurati, inclusi pool Front End, server basati su SQL Server, Servizi di dominio Active Directory, Director, server Messaggistica unificata di Exchange, server Cassette postali di Exchange, server Office Web Apps, Mediation Server e server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="2ef95-163">Internal deployment consists of configured servers and pools, including the Front End pools, SQL Server-based servers, Active Directory Domain Services, Directors, Exchange Unified Messaging (UM) servers, Exchange Mailbox Servers, Office Web Apps Servers, Mediation Servers, and Persistent Chat Servers.</span></span>

- <span data-ttu-id="2ef95-164">Edge Network Diagram - Diagramma che illustra in dettaglio la configurazione del server perimetrale con indirizzi IP e FQDN associati.</span><span class="sxs-lookup"><span data-stu-id="2ef95-164">Edge Network Diagram - Diagram detailing the Edge Server configuration with associated IP addresses and FQDNs.</span></span> <span data-ttu-id="2ef95-165">Sono inoltre inclusi il bilanciamento del carico DNS e i dispositivi di bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="2ef95-165">DNS load balancing and hardware load balancers are also included.</span></span> <span data-ttu-id="2ef95-166">Vengono inoltre visualizzati i Director e il Front End Server o il pool Front End, con LB DNS o HLB associati e l'indirizzo IP assegnato (lo strumento di pianificazione supporta sia gli indirizzi IPv4 che IPv6) e fqdn.</span><span class="sxs-lookup"><span data-stu-id="2ef95-166">Additionally, Directors and the Front End Server or Front End pool are displayed, with associated DNS LB or HLB and the assigned IP address (the Planning Tool supports both IPv4 and IPv6 addresses) and FQDN.</span></span>

## <a name="see-also"></a><span data-ttu-id="2ef95-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ef95-167">See also</span></span>
<span data-ttu-id="2ef95-168"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="2ef95-168"><a name="Optional_Software"> </a></span></span>

[<span data-ttu-id="2ef95-169">Installazione dello strumento di pianificazione</span><span class="sxs-lookup"><span data-stu-id="2ef95-169">Installing the Planning Tool</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-installing-the-planning-tool)
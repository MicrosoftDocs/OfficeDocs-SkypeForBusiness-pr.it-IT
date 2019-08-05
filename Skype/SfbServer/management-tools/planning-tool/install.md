---
title: Installazione di software facoltativo in Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: Prima di iniziare a progettare e pianificare l'infrastruttura di Skype for Business Server 2015 usando lo strumento di pianificazione di Skype for Business Server 2015, è necessario prima di tutto installare lo strumento di pianificazione. Lo strumento di pianificazione non deve essere distribuito in una workstation o un server che fa parte del dominio o dell'infrastruttura in cui si prevede di installare Skype for Business Server 2015. Il file Readme che accompagna lo strumento di pianificazione descrive in dettaglio informazioni importanti sull'installazione e l'uso dello strumento. Alcune delle informazioni contenute nel file Leggimi vengono duplicate qui per chiarezza.
ms.openlocfilehash: 192eae34bf6cf3fa53be82d8cb4450f960c90314
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188459"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a><span data-ttu-id="1c3fb-106">Installazione di software facoltativo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c3fb-106">Install the Planning Tool in Skype for Business Server 2015</span></span>

<span data-ttu-id="1c3fb-107">Prima di iniziare a progettare e pianificare l'infrastruttura di Skype for Business Server 2015 usando lo strumento di pianificazione di Skype for Business Server 2015, è necessario prima di tutto installare lo strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-107">Before you begin designing and planning your Skype for Business Server 2015 infrastructure by using the Skype for Business Server 2015 Planning Tool, you must first install the Planning Tool.</span></span> <span data-ttu-id="1c3fb-108">Lo strumento di pianificazione non deve essere distribuito in una workstation o un server che fa parte del dominio o dell'infrastruttura in cui si prevede di installare Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-108">The Planning Tool does not need to be deployed to a workstation or server that is part of the domain or infrastructure where you plan to install Skype for Business Server 2015.</span></span> <span data-ttu-id="1c3fb-109">Il file Readme che accompagna lo strumento di pianificazione descrive in dettaglio informazioni importanti sull'installazione e l'uso dello strumento.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-109">The Readme file that accompanies the Planning Tool details important information about installing and using the tool.</span></span> <span data-ttu-id="1c3fb-110">Alcune delle informazioni contenute nel file Leggimi vengono duplicate qui per chiarezza.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-110">Some of the information in the Readme file is duplicated here for clarity.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1c3fb-111">Lo strumento di pianificazione richiede l'installazione da parte di un utente con diritti e autorizzazioni di amministratore nel computer in cui deve essere installato lo strumento.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-111">The Planning Tool requires installation by a user with administrator rights and permissions on the computer on which the tool is to be installed.</span></span>

<span data-ttu-id="1c3fb-112">I sistemi operativi supportati per l'installazione e il funzionamento dello strumento di pianificazione sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="1c3fb-112">The supported operating systems for installation and operation of the Planning Tool are:</span></span>

- <span data-ttu-id="1c3fb-113">Windows 10</span><span class="sxs-lookup"><span data-stu-id="1c3fb-113">Windows 10</span></span>

- <span data-ttu-id="1c3fb-114">Windows 8</span><span class="sxs-lookup"><span data-stu-id="1c3fb-114">Windows 8</span></span>

- <span data-ttu-id="1c3fb-115">Windows 8,1</span><span class="sxs-lookup"><span data-stu-id="1c3fb-115">Windows 8.1</span></span>

- <span data-ttu-id="1c3fb-116">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="1c3fb-116">Windows Server 2012</span></span>

- <span data-ttu-id="1c3fb-117">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="1c3fb-117">Windows Server 2012 R2</span></span>

- <span data-ttu-id="1c3fb-118">Windows 7, 32 bit Edition</span><span class="sxs-lookup"><span data-stu-id="1c3fb-118">Windows 7, 32-bit edition</span></span>

- <span data-ttu-id="1c3fb-119">Windows 7, 64 bit Edition con Windows su Win32 (WOW)</span><span class="sxs-lookup"><span data-stu-id="1c3fb-119">Windows 7, 64-bit edition using Windows on Win32 (WOW)</span></span>

- <span data-ttu-id="1c3fb-120">Windows Server 2008 R2 con WOW</span><span class="sxs-lookup"><span data-stu-id="1c3fb-120">Windows Server 2008 R2, using WOW</span></span>

<span data-ttu-id="1c3fb-121">Inoltre, lo strumento di pianificazione richiede Microsoft .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-121">Additionally, the Planning Tool requires Microsoft .NET Framework 4.5.</span></span>

<span data-ttu-id="1c3fb-122">Dopo aver soddisfatto i requisiti di preinstallazione, è possibile installare lo strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-122">After the preinstallation requirements are met, you can then install the Planning Tool.</span></span>



## <a name="to-install-the-planning-tool"></a><span data-ttu-id="1c3fb-123">Per installare lo strumento di pianificazione</span><span class="sxs-lookup"><span data-stu-id="1c3fb-123">To install the Planning Tool</span></span>

1. <span data-ttu-id="1c3fb-124">Accedere al computer locale come membro del gruppo Administrators.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-124">Log on to the local computer as a member of the Administrators group.</span></span>

2. <span data-ttu-id="1c3fb-125">Usando Esplora risorse o una finestra di comando, individuare la directory in cui sono stati scaricati i file di installazione dello strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-125">Using Windows Explorer or a command window, locate the directory where you downloaded the Planning Tool installation files.</span></span>

3. <span data-ttu-id="1c3fb-126">Individuare il file SkypeForBusinessPlanningTool. msi.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-126">Locate the SkypeForBusinessPlanningTool.msi.</span></span> <span data-ttu-id="1c3fb-127">In Esplora risorse fare doppio clic sul file.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-127">In Windows Explorer, double-click the file.</span></span> <span data-ttu-id="1c3fb-128">Nella finestra di comando digitare il nome del file e quindi premere **invio** per eseguire il file.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-128">In the command window, type the name of the file, and then press **Enter** to run the file.</span></span>

4. <span data-ttu-id="1c3fb-129">Nella pagina iniziale di **Skype for Business Server 2015, configurazione guidata strumento di pianificazione**, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-129">On the Welcome page of the **Skype for Business Server 2015, Planning Tool Setup Wizard**, click **Next**.</span></span>

5. <span data-ttu-id="1c3fb-130">Esaminare il **contratto di licenza con l'utente finale**, selezionare **Accetto i termini del contratto di licenza** se si sceglie di accettare le condizioni per l'uso nel contratto di licenza e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-130">Review the **End-User License Agreement**, select **I accept the terms in the License Agreement** if you choose to accept the terms of use in the license agreement, and then click **Next**.</span></span>

6. <span data-ttu-id="1c3fb-131">Scegliere la posizione in cui installare i file dello strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-131">Choose where to install the Planning Tool files.</span></span> <span data-ttu-id="1c3fb-132">Il percorso predefinito è C:\Programmi (x86) \Skype for Business Server 2015 \ Planning Tool.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-132">The default location is C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool.</span></span> <span data-ttu-id="1c3fb-133">Se si vuole modificare il percorso di installazione, fare clic su **Cambia**.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-133">If you want to change the installation location, click **Change**.</span></span> <span data-ttu-id="1c3fb-134">In **modifica cartella di destinazione**selezionare o digitare la posizione in cui installare i file, fare clic su **OK**e quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-134">On **Change destination folder**, browse or type the location to install the files, click **OK**, and then click **Next**.</span></span>

7. <span data-ttu-id="1c3fb-135">Il programma di installazione è ora pronto per l'installazione dello strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-135">The installer is now ready to install the Planning Tool.</span></span> <span data-ttu-id="1c3fb-136">Fare clic su **Installa** per avviare il processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-136">Click **Install** to begin the installation process.</span></span>

8. <span data-ttu-id="1c3fb-137">L'installazione verrà avviata e verrà visualizzato lo stato di avanzamento.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-137">The installation will start, and the progress will be displayed.</span></span> <span data-ttu-id="1c3fb-138">Dopo aver completato l'installazione, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-138">After the installation is successfully completed, click **Finish**.</span></span>

9. <span data-ttu-id="1c3fb-139">Lo strumento di pianificazione è pronto per l'uso.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-139">The Planning Tool is ready for use.</span></span>

## <a name="optional-software"></a><span data-ttu-id="1c3fb-140">Software facoltativo</span><span class="sxs-lookup"><span data-stu-id="1c3fb-140">Optional Software</span></span>
<span data-ttu-id="1c3fb-141"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="1c3fb-141"></span></span>

<span data-ttu-id="1c3fb-142">Lo strumento di pianificazione di Skype for Business Server 2015 è progettato per l'esportazione in Microsoft Excel e Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-142">The Skype for Business Server 2015 Planning Tool is designed to export to Microsoft Excel and Microsoft Visio.</span></span> <span data-ttu-id="1c3fb-143">Anche se queste applicazioni non sono necessarie per il funzionamento dello strumento di pianificazione, aggiungono un valore significativo alla distribuzione e alla documentazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-143">While these applications are not required for the operation of the Planning Tool, they do add significant value to the deployment and documentation of your design.</span></span>

### <a name="microsoft-excel"></a><span data-ttu-id="1c3fb-144">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="1c3fb-144">Microsoft Excel</span></span>

<span data-ttu-id="1c3fb-145">L'esportazione della progettazione in Microsoft Excel consente di creare un report che visualizza sette schede nel foglio di calcolo:</span><span class="sxs-lookup"><span data-stu-id="1c3fb-145">Exporting your design to Microsoft Excel creates a report that displays seven tabs in the spreadsheet:</span></span>

- <span data-ttu-id="1c3fb-146">Riepilogo: Visualizza le informazioni sulla configurazione del sito, inclusi il conteggio degli utenti, le impostazioni della capacità e le informazioni sul profilo del server.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-146">Summary - Displays information on site configuration, including user count, capacity settings, and server profile information.</span></span>

- <span data-ttu-id="1c3fb-147">Profilo hardware: Visualizza un report sulle configurazioni hardware consigliate per i server specificati nella topologia, tra cui CPU, memoria, disco e interfaccia di rete.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-147">Hardware Profile - Displays a report on the recommended hardware configurations for servers that are specified in the topology, including CPU, memory, disk, and network interface.</span></span> <span data-ttu-id="1c3fb-148">Sono incluse anche la quantità e le specifiche consigliate per i componenti server.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-148">The quantity and recommended specifications for the server components are also included.</span></span> <span data-ttu-id="1c3fb-149">Ogni server viene inoltre definito dal sito per ottenere una rappresentazione completa dei requisiti del server per sito.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-149">In addition, each server is defined by site to provide a complete representation of server requirements by site.</span></span>

- <span data-ttu-id="1c3fb-150">Requisiti per le porte: Visualizza un report di tutte le porte abilitate e l'associazione a Domain Name System Load Balancing (DNS LB) e hardware load balancers (HLB).</span><span class="sxs-lookup"><span data-stu-id="1c3fb-150">Ports Requirements - Displays a report of all ports that are enabled, and the association to Domain Name System load balancing (DNS LB) and hardware load balancers (HLB).</span></span> <span data-ttu-id="1c3fb-151">È consigliabile usare questo report per pianificare le configurazioni firewall e DNS LB e HLB.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-151">You should use this report to plan your firewall and DNS LB and HLB configurations.</span></span>

- <span data-ttu-id="1c3fb-152">Report di riepilogo: Visualizza il riepilogo generale delle impostazioni necessarie per configurare la rete Edge Server.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-152">Summary Report - Displays the general summary of the settings that are required to set up your Edge Server network.</span></span>

- <span data-ttu-id="1c3fb-153">Report certificati: Visualizza il nome dell'oggetto e i nomi alternativi oggetto necessari per i certificati necessari per l'uso dei server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-153">Certificates Report - Displays the subject name and subject alternate names that are required for the certificates needed to get the Edge Servers running.</span></span>

- <span data-ttu-id="1c3fb-154">Report firewall: Visualizza le porte di origine e di destinazione e gli indirizzi IP per le interfacce esterne ed interne.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-154">Firewall Report - Displays the source and destination ports and IP addresses for both External and Internal interfaces.</span></span>

- <span data-ttu-id="1c3fb-155">Report DNS: Visualizza il nome di dominio completo (FQDN) e gli indirizzi IP/VIP necessari per ogni voce DNS creata.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-155">DNS Report - Displays the fully qualified domain name (FQDN) and IP/VIP addresses required for each DNS entry that you create.</span></span>

### <a name="microsoft-visio"></a><span data-ttu-id="1c3fb-156">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="1c3fb-156">Microsoft Visio</span></span>

<span data-ttu-id="1c3fb-157">L'esportazione della progettazione in Microsoft Visio crea un diagramma da usare per la documentazione della topologia e dell'infrastruttura configurate.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-157">Exporting your design to Microsoft Visio creates a diagram for use in your documentation purposes of your configured topology and infrastructure.</span></span> <span data-ttu-id="1c3fb-158">Il diagramma importato può essere modificato e ridisposto per soddisfare le esigenze della documentazione.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-158">The imported diagram can be edited and rearranged to meet your documentation needs.</span></span> <span data-ttu-id="1c3fb-159">Il diagramma di Visio tipico includerà:</span><span class="sxs-lookup"><span data-stu-id="1c3fb-159">The typical Visio diagram will include:</span></span>

> [!NOTE]
> <span data-ttu-id="1c3fb-160">Se la struttura è abbastanza grande da richiedere più di tre server front-end, verrà creata una pagina aggiuntiva per il pool Front-End, i server front-end, il computer in cui sono in esecuzione SQL Server, gli indirizzi IP e i nomi di dominio completi.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-160">If your design is large enough to require more than three Front End Servers, an additional page will be created for the Front End pool, Front End Servers, the computer running SQL Server, IP addresses, and FQDNs.</span></span>

- <span data-ttu-id="1c3fb-161">Topologia globale-diagramma dei siti di Skype for Business Server 2015 configurati.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-161">Global Topology - Diagram of configured Skype for Business Server 2015 sites.</span></span>

- <span data-ttu-id="1c3fb-162">Scheda nome sito: Visualizza la topologia di configurazione del sito con Edge Server, firewall, PSTN (Public Switched Telephone Network) con gateway e la distribuzione del server interno.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-162">Site Name tab - Displays the site configuration topology with Edge Server, firewall, public switched telephone network (PSTN) with gateways, and the internal server deployment.</span></span> <span data-ttu-id="1c3fb-163">La distribuzione interna è costituita da server e pool configurati, inclusi i pool Front-End, i server basati su SQL Server, i servizi di dominio Active Directory, i direttori, i server di messaggistica unificata di Exchange, i server cassette postali di Exchange, i server di Office Web Apps Mediation Server e server di chat permanenti.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-163">Internal deployment consists of configured servers and pools, including the Front End pools, SQL Server-based servers, Active Directory Domain Services, Directors, Exchange Unified Messaging (UM) servers, Exchange Mailbox Servers, Office Web Apps Servers, Mediation Servers, and Persistent Chat Servers.</span></span>

- <span data-ttu-id="1c3fb-164">Diagramma reticolare Edge-diagramma che descrive la configurazione del server perimetrale con gli indirizzi IP associati e i nomi di dominio completi.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-164">Edge Network Diagram - Diagram detailing the Edge Server configuration with associated IP addresses and FQDNs.</span></span> <span data-ttu-id="1c3fb-165">Sono inclusi anche il bilanciamento del carico DNS e i dispositivi di bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-165">DNS load balancing and hardware load balancers are also included.</span></span> <span data-ttu-id="1c3fb-166">Vengono inoltre visualizzati i direttori e il server front-end o il pool Front-End, con il DNS LB o HLB associato e l'indirizzo IP assegnato (lo strumento di pianificazione supporta sia gli indirizzi IPv4 che IPv6) e il nome di dominio completo.</span><span class="sxs-lookup"><span data-stu-id="1c3fb-166">Additionally, Directors and the Front End Server or Front End pool are displayed, with associated DNS LB or HLB and the assigned IP address (the Planning Tool supports both IPv4 and IPv6 addresses) and FQDN.</span></span>

## <a name="see-also"></a><span data-ttu-id="1c3fb-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c3fb-167">See also</span></span>
<span data-ttu-id="1c3fb-168"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="1c3fb-168"></span></span>

[<span data-ttu-id="1c3fb-169">Installazione dello strumento di pianificazione</span><span class="sxs-lookup"><span data-stu-id="1c3fb-169">Installing the Planning Tool</span></span>](https://technet.microsoft.com/library/ebdc9e26-4b22-4b02-85b9-7462bcfe7c93.aspx)

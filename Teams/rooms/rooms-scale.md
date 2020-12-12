---
title: Distribuire le sale di Microsoft teams usando Microsoft endpoint Configuration Manager
author: dstrome
ms.author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection:
- M365-collaboration
description: Informazioni sulla distribuzione di sale Microsoft teams su distribuzioni su larga scala con Microsoft endpoint Configuration Manager.
no-loc:
- Microsoft
- Microsoft Corporation
- Microsoft Teams Rooms
- Microsoft Teams Room
- System Center
- Configuration Manager
- Windows
- Surface
- Surface Pro
- Windows PE
- Windows 10
- Windows 10 Enterprise
- Azure
- Azure Monitor
- Log Analytics
- Operations Management Suite
ms.openlocfilehash: 1d8fc0090264a7a39051cfedb9c3584a08e3ebb9
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662421"
---
# <a name="deploy-microsoft-teams-rooms-by-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="fb316-103">Distribuire le sale di Microsoft teams usando Microsoft endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="fb316-103">Deploy Microsoft Teams Rooms by using Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="fb316-104">In questo articolo vengono fornite tutte le informazioni necessarie per creare le distribuzioni delle sale di Microsoft teams usando Microsoft endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="fb316-104">This article gives you all the necessary information to create your Microsoft Teams Rooms deployments by using Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="fb316-105">Con i metodi di facile utilizzo forniti da Configuration Manager, è possibile distribuire il sistema operativo e altre applicazioni in più dispositivi di destinazione.</span><span class="sxs-lookup"><span data-stu-id="fb316-105">With the easy-to-use methods provided by Configuration Manager, you can deploy the operating system and other applications to multiple target devices.</span></span>

<span data-ttu-id="fb316-106">Usare l'approccio illustrato di seguito per guidarvi alla configurazione di Configuration Manager e personalizzare i pacchetti di esempio e gli script forniti in tutte le linee guida necessarie per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fb316-106">Use the approach illustrated below to guide you through your Configuration Manager configuration, and customize the sample packages and scripts provided throughout this guidance as needed for your organization.</span></span>

![Processo di distribuzione di Microsoft teams Rooms con Configuration Manager](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> <span data-ttu-id="fb316-108">Questa soluzione è stata testata solo con distribuzioni basate su Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="fb316-108">This solution has only been tested with Surface Pro–based deployments.</span></span> <span data-ttu-id="fb316-109">Seguire le linee guida del produttore per le configurazioni che non sono basate su Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="fb316-109">Follow the manufacturer's guidelines for configurations that aren't based on Surface Pro.</span></span>

## <a name="validate-prerequisites"></a><span data-ttu-id="fb316-110">Convalidare i prerequisiti</span><span class="sxs-lookup"><span data-stu-id="fb316-110">Validate prerequisites</span></span>

<span data-ttu-id="fb316-111">Per distribuire le sale di Microsoft teams con Configuration Manager, verificare di soddisfare i requisiti e i prerequisiti seguenti.</span><span class="sxs-lookup"><span data-stu-id="fb316-111">To deploy Microsoft Teams Rooms with Configuration Manager, ensure that you meet the following prerequisites and requirements.</span></span>

### <a name="microsoft-endpoint-configuration-manager-requirements"></a><span data-ttu-id="fb316-112">Requisiti di Microsoft endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="fb316-112">Microsoft Endpoint Configuration Manager requirements</span></span>

-   <span data-ttu-id="fb316-113">La versione di Microsoft endpoint Configuration Manager deve essere almeno 1706 o superiore.</span><span class="sxs-lookup"><span data-stu-id="fb316-113">Microsoft Endpoint Configuration Manager version must be at least 1706 or above.</span></span> <span data-ttu-id="fb316-114">È consigliabile usare 1710 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="fb316-114">We recommend using 1710 or later.</span></span> <span data-ttu-id="fb316-115">Per informazioni sulle versioni di Windows 10 supportate da Configuration Manager, vedere [supporto per Windows 10 in Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) .</span><span class="sxs-lookup"><span data-stu-id="fb316-115">Check out [Support for Windows 10 in Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) to learn about the Windows 10 versions that Configuration Manager supports.</span></span>

-   <span data-ttu-id="fb316-116">È necessario installare una versione supportata di Windows Assessment and Deployment Kit (ADK) per Windows 10.</span><span class="sxs-lookup"><span data-stu-id="fb316-116">A supported version of Windows Assessment and Deployment Kit (ADK) for Windows 10 must be installed.</span></span> <span data-ttu-id="fb316-117">Vedere le versioni di [Windows 10 ADK](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk) che è possibile usare con versioni diverse di Configuration Manager e verificare che la distribuzione includa la versione corretta.</span><span class="sxs-lookup"><span data-stu-id="fb316-117">See the versions of the [Windows 10 ADK](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk) that you can use with different versions of Configuration Manager, and ensure that your deployment includes the correct version.</span></span>

-   <span data-ttu-id="fb316-118">Ai server di sistema del sito deve essere stato assegnato il ruolo del punto di distribuzione e le immagini di avvio devono essere abilitate per il [supporto PXE (Preboot Execution Environment)](https://docs.microsoft.com/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) per abilitare le distribuzioni avviate dalla rete.</span><span class="sxs-lookup"><span data-stu-id="fb316-118">The site system servers must have been assigned the distribution point role, and the boot images should be enabled for [preboot execution environment (PXE) support](https://docs.microsoft.com/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) to enable network-initiated deployments.</span></span> <span data-ttu-id="fb316-119">Se il supporto PXE non è abilitato, è possibile usare i [supporti di avvio](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) per le distribuzioni.</span><span class="sxs-lookup"><span data-stu-id="fb316-119">If PXE support isn't enabled, you can use [bootable media](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments.</span></span>

-   <span data-ttu-id="fb316-120">Un account di accesso alla rete deve essere configurato per supportare scenari di distribuzione di nuovi computer (Bare Metal).</span><span class="sxs-lookup"><span data-stu-id="fb316-120">A network access account must be configured to support new computer (bare metal) deployment scenarios.</span></span> <span data-ttu-id="fb316-121">Per ulteriori informazioni sulla configurazione di un account di accesso alla rete, vedere [account usati in Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span><span class="sxs-lookup"><span data-stu-id="fb316-121">To learn more about the configuration of a network access account, see [Accounts used in Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

-   <span data-ttu-id="fb316-122">È consigliabile abilitare il [supporto multicast](https://docs.microsoft.com/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), se è probabile che si stia distribuendo la stessa immagine di Microsoft teams rooms in più unità contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="fb316-122">We recommend that you enable [multicast support](https://docs.microsoft.com/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), if you're likely to deploy the same Microsoft Teams Rooms image to multiple units at the same time.</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="fb316-123">Requisiti di rete</span><span class="sxs-lookup"><span data-stu-id="fb316-123">Networking requirements</span></span>

-   <span data-ttu-id="fb316-124">La rete deve avere un server DHCP (Dynamic Host Configuration Protocol) configurato per la distribuzione automatica degli indirizzi IP alle subnet in cui verranno distribuite le unità di Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="fb316-124">Your network should have a Dynamic Host Configuration Protocol (DHCP) server, configured for automatic IP address distribution to the subnets where Microsoft Teams Rooms units will be deployed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fb316-125">La durata del lease DHCP deve essere impostata su un valore superiore alla durata della distribuzione delle immagini.</span><span class="sxs-lookup"><span data-stu-id="fb316-125">DHCP lease duration must be set to a value longer than the image deployment duration.</span></span> <span data-ttu-id="fb316-126">In caso contrario, la distribuzione potrebbe non riuscire.</span><span class="sxs-lookup"><span data-stu-id="fb316-126">Otherwise, the deployment might fail.</span></span>

-   <span data-ttu-id="fb316-127">La rete, inclusi gli interruttori e le LAN virtuali (VLAN), deve essere configurata per supportare PXE.</span><span class="sxs-lookup"><span data-stu-id="fb316-127">Your network, including switches and virtual LANs (VLANs), should be configured to support PXE.</span></span> <span data-ttu-id="fb316-128">Per altre informazioni sull'helper IP e la configurazione PXE, vedere il fornitore di rete.</span><span class="sxs-lookup"><span data-stu-id="fb316-128">Refer to your network vendor for more information about IP Helper and PXE configuration.</span></span> <span data-ttu-id="fb316-129">In alternativa, puoi usare il supporto di [avvio](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) per le distribuzioni, se il supporto PXE non è abilitato.</span><span class="sxs-lookup"><span data-stu-id="fb316-129">Alternatively, you can use [bootable media](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments, if PXE support isn't enabled.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fb316-130">Per i dispositivi Surface Pro, l'avvio dalla rete (avvio PXE) è supportato solo quando si usa un adattatore Ethernet o una stazione di ancoraggio da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fb316-130">For Surface Pro devices, booting from the network (PXE boot) is only supported when you use an Ethernet adapter or docking station from Microsoft.</span></span> <span data-ttu-id="fb316-131">Le schede Ethernet di terze parti non supportano l'avvio PXE con Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="fb316-131">Third-party Ethernet adapters don't support PXE boot with Surface Pro.</span></span> <span data-ttu-id="fb316-132">Per altre informazioni, vedere [schede Ethernet e distribuzione di superfici](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) .</span><span class="sxs-lookup"><span data-stu-id="fb316-132">See [Ethernet adapters and Surface deployment](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) for more information.</span></span>

## <a name="configure-microsoft-endpoint-configuration-manager-for-operating-system-deployment"></a><span data-ttu-id="fb316-133">Configurare Microsoft endpoint Configuration Manager per la distribuzione del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="fb316-133">Configure Microsoft Endpoint Configuration Manager for operating system deployment</span></span>

<span data-ttu-id="fb316-134">Questo articolo presuppone che tu abbia già una distribuzione di Configuration Manager sano e non dettagli tutti i passaggi necessari per la distribuzione e la configurazione di Configuration Manager da zero.</span><span class="sxs-lookup"><span data-stu-id="fb316-134">This article assumes you already have a healthy Configuration Manager deployment, and doesn't detail all the steps required to deploy and configure Configuration Manager from scratch.</span></span> <span data-ttu-id="fb316-135">La [documentazione e le indicazioni](https://docs.microsoft.com/configmgr/) per la configurazione di Microsoft endpoint Configuration Manager sono un'ottima risorsa. Se non è stato ancora distribuito Configuration Manager, è consigliabile iniziare con queste risorse.</span><span class="sxs-lookup"><span data-stu-id="fb316-135">The [documentation and the configuration guidance](https://docs.microsoft.com/configmgr/) on the Microsoft Endpoint Configuration Manager is a great resource; we recommend you start with these resources if you haven't yet deployed Configuration Manager.</span></span>

<span data-ttu-id="fb316-136">Seguire le istruzioni seguenti per verificare che le caratteristiche OSD (Operating System Deployment) siano configurate correttamente.</span><span class="sxs-lookup"><span data-stu-id="fb316-136">Use the following instructions to verify that the operating system deployment (OSD) features are configured properly.</span></span>

### <a name="validate-and-upgrade-configuration-manager"></a><span data-ttu-id="fb316-137">Convalidare e aggiornare Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="fb316-137">Validate and upgrade Configuration Manager</span></span>

1.  <span data-ttu-id="fb316-138">Nella console di Configuration Manager, vedere  \> **aggiornamenti e manutenzione** di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="fb316-138">In the Configuration Manager console, go to **Administration** \> **Updates and Servicing**.</span></span>

2.  <span data-ttu-id="fb316-139">Controllare la build installata e gli aggiornamenti applicabili che non sono ancora stati installati.</span><span class="sxs-lookup"><span data-stu-id="fb316-139">Check the installed build and applicable updates that haven't been installed yet.</span></span>

3.  <span data-ttu-id="fb316-140">Rivedere il [supporto per Windows 10 in Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); Se è necessario aggiornare la distribuzione, selezionare l'aggiornamento che si vuole installare e quindi selezionare **Scarica**.</span><span class="sxs-lookup"><span data-stu-id="fb316-140">Review [Support for Windows 10 in Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); if you need to upgrade your deployment, select the update you want to install, and then select **Download**.</span></span>

4.  <span data-ttu-id="fb316-141">Al termine del download, selezionare l'aggiornamento e quindi selezionare **Installa Update Pack**.</span><span class="sxs-lookup"><span data-stu-id="fb316-141">After the download is complete, select the update, and then select **Install Update Pack**.</span></span>

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a><span data-ttu-id="fb316-142">Configurare i punti di distribuzione per supportare PXE e multicast</span><span class="sxs-lookup"><span data-stu-id="fb316-142">Configure distribution points to support PXE and multicast</span></span>

1.  <span data-ttu-id="fb316-143">Nella console di Configuration Manager accedere ai punti di distribuzione di **Amministrazione** \> .</span><span class="sxs-lookup"><span data-stu-id="fb316-143">In the Configuration Manager console, go to **Administration** \> **Distribution Points**.</span></span>

2.  <span data-ttu-id="fb316-144">Selezionare il server del punto di distribuzione che servirà la distribuzione di Microsoft teams Rooms e quindi selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="fb316-144">Select the distribution point server that will serve the Microsoft Teams Rooms deployment, and then select **Properties**.</span></span>

3.  <span data-ttu-id="fb316-145">Selezionare la scheda **PXE** e verificare che siano abilitate le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fb316-145">Select the **PXE** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="fb316-146">Abilitare il supporto PXE per i client</span><span class="sxs-lookup"><span data-stu-id="fb316-146">Enable PXE support for clients</span></span>
    -   <span data-ttu-id="fb316-147">Consentire a questo punto di distribuzione di rispondere alle richieste PXE in arrivo</span><span class="sxs-lookup"><span data-stu-id="fb316-147">Allow this distribution point to respond to incoming PXE requests</span></span>
    -   <span data-ttu-id="fb316-148">Abilitare il supporto computer sconosciuto</span><span class="sxs-lookup"><span data-stu-id="fb316-148">Enable unknown computer support</span></span>

4.  <span data-ttu-id="fb316-149">*Facoltativo:* Per abilitare il supporto multicast, selezionare la scheda **multicast** e verificare che siano abilitate le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fb316-149">*Optional:* To enable multicast support, select the **Multicast** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="fb316-150">Abilitare il multicast per inviare simultaneamente i dati a più client</span><span class="sxs-lookup"><span data-stu-id="fb316-150">Enable multicast to simultaneously send data to multiple clients</span></span>
    -   <span data-ttu-id="fb316-151">Configurare l'intervallo di porte UDP secondo le indicazioni del team di rete</span><span class="sxs-lookup"><span data-stu-id="fb316-151">Configure the UDP port range as per your network team's recommendation</span></span>

### <a name="configure-the-network-access-account"></a><span data-ttu-id="fb316-152">Configurare l'account di accesso alla rete</span><span class="sxs-lookup"><span data-stu-id="fb316-152">Configure the Network Access Account</span></span>

1.  <span data-ttu-id="fb316-153">Nella console di Configuration Manager accedere ai siti di configurazione del sito di **Amministrazione** \>  \> e quindi selezionare il sito.</span><span class="sxs-lookup"><span data-stu-id="fb316-153">In the Configuration Manager console, go to **Administration** \> **Site Configuration** \> **Sites**, and then select the site.</span></span>

2.  <span data-ttu-id="fb316-154">Nel gruppo **Impostazioni** selezionare **Configura** \> **distribuzione software** componenti sito.</span><span class="sxs-lookup"><span data-stu-id="fb316-154">In the **Settings** group, select **Configure Site Components** \> **Software Distribution**.</span></span>

3.  <span data-ttu-id="fb316-155">Selezionare la scheda **account di accesso alla rete** . Configurare uno o più account e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb316-155">Select the **Network Access Account** tab. Set up one or more accounts, and then select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="fb316-156">Gli account non necessitano di diritti speciali, ad eccezione del fatto che il **computer di Access si** trova direttamente sul server del punto di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="fb316-156">The accounts don't need any special rights, except for the **Access this computer from the network** right on the distribution point server.</span></span> <span data-ttu-id="fb316-157">Un account utente di dominio generico sarà appropriato.</span><span class="sxs-lookup"><span data-stu-id="fb316-157">A generic domain user account will be appropriate.</span></span> <span data-ttu-id="fb316-158">Per altre informazioni, vedere [account usati in Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span><span class="sxs-lookup"><span data-stu-id="fb316-158">For more information, see [Accounts used in Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

### <a name="configure-a-boot-image"></a><span data-ttu-id="fb316-159">Configurare un'immagine di avvio</span><span class="sxs-lookup"><span data-stu-id="fb316-159">Configure a boot image</span></span>

1.  <span data-ttu-id="fb316-160">Nella console di Configuration Manager accedere alle  \> Immagini di avvio del **sistema operativo** della raccolta software \> .</span><span class="sxs-lookup"><span data-stu-id="fb316-160">In the Configuration Manager console, go to **Software Library** \> **Operating System** \> **Boot Images**.</span></span>

2.  <span data-ttu-id="fb316-161">Selezionare **immagine di avvio (x64)**, quindi selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="fb316-161">Select **Boot image (x64)**, and then select **Properties**.</span></span>

3.  <span data-ttu-id="fb316-162">Selezionare la scheda **origine dati** e abilitare **Distribuisci questa immagine di avvio dal punto di distribuzione abilitato per PXE**.</span><span class="sxs-lookup"><span data-stu-id="fb316-162">Select the **Data Source** tab, and enable **Deploy this boot image from the PXE-enabled distribution point**.</span></span>

4.  <span data-ttu-id="fb316-163">Selezionare la scheda **componenti facoltativi** per installare i componenti necessari:</span><span class="sxs-lookup"><span data-stu-id="fb316-163">Select the **Optional Components** tab to install required components:</span></span>

    1.  <span data-ttu-id="fb316-164">Selezionare l'icona stella e cercare **HTML (WinPE-HTA)**</span><span class="sxs-lookup"><span data-stu-id="fb316-164">Select the star icon, and search for **HTML (WinPE-HTA)**</span></span>

    2.  <span data-ttu-id="fb316-165">Selezionare **OK** per aggiungere il supporto dell'applicazione HTML all'immagine di avvio.</span><span class="sxs-lookup"><span data-stu-id="fb316-165">Select **OK** to add HTML application support in to the boot image.</span></span>

5.  <span data-ttu-id="fb316-166">*Facoltativo:* Per personalizzare l'esperienza di distribuzione, selezionare la scheda **personalizzazione** .</span><span class="sxs-lookup"><span data-stu-id="fb316-166">*Optional:* To customize the deployment experience, select the **Customization** tab.</span></span>
    -   <span data-ttu-id="fb316-167">Abilitare il **supporto dei comandi (solo test)** se si vuole avere accesso a un prompt dei comandi durante la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="fb316-167">Enable **command support (testing only)** if you want to have access to a command prompt during the deployment.</span></span> <span data-ttu-id="fb316-168">Quando questa opzione è abilitata, è possibile avviare un prompt dei comandi selezionando **F8** in qualsiasi momento durante la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="fb316-168">When this is enabled, you can start a command prompt by selecting **F8** at any time during the deployment.</span></span>
    -   <span data-ttu-id="fb316-169">È anche possibile specificare un'immagine di sfondo personalizzata da visualizzare durante la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="fb316-169">You can also specify a custom background image to be displayed during the deployment.</span></span> <span data-ttu-id="fb316-170">Per impostare un'immagine, abilitare **specificare il file di immagine di sfondo personalizzato (percorso UNC** e selezionare lo sfondo.</span><span class="sxs-lookup"><span data-stu-id="fb316-170">To set an image, enable **Specify the custom background image file (UNC path** and select your background.</span></span>

6.  <span data-ttu-id="fb316-171">Quando richiesto, selezionare **Sì** e distribuire l'immagine di avvio aggiornata ai punti di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="fb316-171">When asked, select **Yes** and distribute the updated boot image to your distribution points.</span></span>

<span data-ttu-id="fb316-172">Per altre informazioni, vedere [gestire le immagini di avvio con Configuration Manager](https://docs.microsoft.com/configmgr/osd/get-started/manage-boot-images).</span><span class="sxs-lookup"><span data-stu-id="fb316-172">For more information, see [Manage boot images with Configuration Manager](https://docs.microsoft.com/configmgr/osd/get-started/manage-boot-images).</span></span>

> [!NOTE]
> <span data-ttu-id="fb316-173">Puoi creare un supporto USB avviabile per avviare distribuzioni basate su Sequence Manager di configurazione per gli ambienti che non hanno supporto PXE.</span><span class="sxs-lookup"><span data-stu-id="fb316-173">You can create a bootable USB media to initiate Configuration Manager task sequence–based deployments for environments that have no PXE support.</span></span> <span data-ttu-id="fb316-174">Il supporto di avvio contiene solo l'immagine di avvio, i comandi di preavvio facoltativi e i file necessari e i binari di Configuration Manager per supportare l'avvio in Windows PE e la connessione a Gestione configurazione per il resto del processo di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="fb316-174">The bootable media contains only the boot image, optional prestart commands and their required files, and Configuration Manager binaries to support booting into Windows PE and connecting to Configuration Manager for the rest of the deployment process.</span></span> <span data-ttu-id="fb316-175">Per altre informazioni, vedere [creare elementi multimediali avviabili](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span><span class="sxs-lookup"><span data-stu-id="fb316-175">For more information, see [Create bootable media](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span></span>

## <a name="create-configuration-manager-packages"></a><span data-ttu-id="fb316-176">Creare pacchetti di Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="fb316-176">Create Configuration Manager packages</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fb316-177">La versione del sistema operativo necessaria per ogni versione del programma di installazione di SRS cambia con ogni rilascio MSI.</span><span class="sxs-lookup"><span data-stu-id="fb316-177">The required operating system version for each SRS installer version changes with every MSI release.</span></span> <span data-ttu-id="fb316-178">Per determinare la versione del sistema operativo migliore per un determinato MSI, eseguire lo script di configurazione della console una sola volta.</span><span class="sxs-lookup"><span data-stu-id="fb316-178">To determine the best operating system version for a given MSI, run the console setup script once.</span></span> <span data-ttu-id="fb316-179">Per altre informazioni, vedere [distribuire le sale di Microsoft teams usando Microsoft endpoint Configuration Manager](rooms-scale.md).</span><span class="sxs-lookup"><span data-stu-id="fb316-179">To learn more, see [Deploy Microsoft Teams Rooms by using Microsoft Endpoint Configuration Manager](rooms-scale.md).</span></span>

<span data-ttu-id="fb316-180">Configuration Manager richiede un certo numero di pacchetti per la distribuzione e la configurazione delle unità di Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="fb316-180">Configuration Manager requires a number of packages to deploy and configure the Microsoft Teams Rooms units.</span></span>

<span data-ttu-id="fb316-181">È necessario creare e configurare i pacchetti seguenti e quindi distribuirli ai sistemi del sito di Configuration Manager a cui è stato assegnato il ruolo del server del punto di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="fb316-181">You need to create and configure the following packages, and then distribute them to the Configuration Manager site systems that have been assigned the distribution point server role.</span></span>

| <span data-ttu-id="fb316-182">**Nome pacchetto**</span><span class="sxs-lookup"><span data-stu-id="fb316-182">**Package name**</span></span>                     | <span data-ttu-id="fb316-183">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="fb316-183">**Type**</span></span>               | <span data-ttu-id="fb316-184">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="fb316-184">**Description**</span></span>                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| <span data-ttu-id="fb316-185">Pacchetto di applicazione SRS V2-SRS</span><span class="sxs-lookup"><span data-stu-id="fb316-185">SRS v2 - SRS Application Package</span></span>     | <span data-ttu-id="fb316-186">Pacchetto software</span><span class="sxs-lookup"><span data-stu-id="fb316-186">Software package</span></span>       | <span data-ttu-id="fb316-187">Pacchetto per il kit di distribuzione di Microsoft teams rooms</span><span class="sxs-lookup"><span data-stu-id="fb316-187">Package for the Microsoft Teams Rooms deployment kit</span></span>                                      |
| <span data-ttu-id="fb316-188">SRS v2-pacchetto Sysprep</span><span class="sxs-lookup"><span data-stu-id="fb316-188">SRS v2 - Sysprep Package</span></span>             | <span data-ttu-id="fb316-189">Pacchetto software</span><span class="sxs-lookup"><span data-stu-id="fb316-189">Software package</span></span>       | <span data-ttu-id="fb316-190">Pacchetto per la Unattended.xml personalizzata per configurare le unità di Microsoft teams rooms</span><span class="sxs-lookup"><span data-stu-id="fb316-190">Package for the custom Unattended.xml to configure Microsoft Teams Rooms units</span></span>            |
| <span data-ttu-id="fb316-191">Pacchetto SRS V2-Set-SRSComputerName</span><span class="sxs-lookup"><span data-stu-id="fb316-191">SRS v2 - Set-SRSComputerName Package</span></span> | <span data-ttu-id="fb316-192">Pacchetto software</span><span class="sxs-lookup"><span data-stu-id="fb316-192">Software package</span></span>       | <span data-ttu-id="fb316-193">Pacchetto per l'applicazione HTML (HTA) per assegnare un nome di computer durante la distribuzione</span><span class="sxs-lookup"><span data-stu-id="fb316-193">Package for the HTML application (HTA) to assign a computer name during the deployment</span></span>    |
| <span data-ttu-id="fb316-194">SRS V2-configurare l'installazione di SRS</span><span class="sxs-lookup"><span data-stu-id="fb316-194">SRS v2 - Configure SRS Setup</span></span>         | <span data-ttu-id="fb316-195">Pacchetto software</span><span class="sxs-lookup"><span data-stu-id="fb316-195">Software package</span></span>       | <span data-ttu-id="fb316-196">Pacchetto per configurare la distribuzione dell'app Microsoft teams rooms</span><span class="sxs-lookup"><span data-stu-id="fb316-196">Package to configure deployment of the Microsoft Teams Rooms app</span></span>                          |
| <span data-ttu-id="fb316-197">Pacchetto aggiornamenti di SRS V2-OS</span><span class="sxs-lookup"><span data-stu-id="fb316-197">SRS v2 - OS Updates Package</span></span>          | <span data-ttu-id="fb316-198">Pacchetto software</span><span class="sxs-lookup"><span data-stu-id="fb316-198">Software package</span></span>       | <span data-ttu-id="fb316-199">Pacchetto per distribuire gli aggiornamenti obbligatori del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="fb316-199">Package to deploy mandatory operating system updates</span></span>                                      |
| <span data-ttu-id="fb316-200">Pacchetto di certificato radice SRS V2</span><span class="sxs-lookup"><span data-stu-id="fb316-200">SRS v2 - Root Certificate Package</span></span>    | <span data-ttu-id="fb316-201">Pacchetto software</span><span class="sxs-lookup"><span data-stu-id="fb316-201">Software package</span></span>       | <span data-ttu-id="fb316-202">Pacchetto facoltativo per distribuire il certificato radice (non necessario per le unità Unite per il dominio)</span><span class="sxs-lookup"><span data-stu-id="fb316-202">Optional - Package to deploy the root certificate (not required for domain-joined units)</span></span>  |
| <span data-ttu-id="fb316-203">SRS v2-pacchetto agente di monitoraggio Microsoft</span><span class="sxs-lookup"><span data-stu-id="fb316-203">SRS v2 - Microsoft Monitoring Agent Package</span></span> | <span data-ttu-id="fb316-204">Pacchetto software</span><span class="sxs-lookup"><span data-stu-id="fb316-204">Software package</span></span>       | <span data-ttu-id="fb316-205">Pacchetto facoltativo per la distribuzione e la configurazione dell'agente Microsoft Operations Management Suite</span><span class="sxs-lookup"><span data-stu-id="fb316-205">Optional - Package to deploy and configure the Microsoft Operations Management Suite agent</span></span>|
| <span data-ttu-id="fb316-206">Pacchetto di sfondo SRS V2-WinPE</span><span class="sxs-lookup"><span data-stu-id="fb316-206">SRS v2 - WinPE Background Package</span></span>    | <span data-ttu-id="fb316-207">Pacchetto software</span><span class="sxs-lookup"><span data-stu-id="fb316-207">Software package</span></span>       | <span data-ttu-id="fb316-208">Pacchetto per l'immagine di sfondo personalizzata da usare con le immagini di avvio</span><span class="sxs-lookup"><span data-stu-id="fb316-208">Package for the custom background image to use with boot images</span></span>                           |
| <span data-ttu-id="fb316-209">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="fb316-209">Windows 10 Enterprise</span></span>                | <span data-ttu-id="fb316-210">Immagine del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="fb316-210">Operating system image</span></span> | <span data-ttu-id="fb316-211">Pacchetto per il file di installazione del sistema operativo (Install. wim)</span><span class="sxs-lookup"><span data-stu-id="fb316-211">Package for the operating system installation file (install.wim)</span></span>                          |
| <span data-ttu-id="fb316-212">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="fb316-212">Surface Pro</span></span>                          | <span data-ttu-id="fb316-213">Pacchetto del driver</span><span class="sxs-lookup"><span data-stu-id="fb316-213">Driver package</span></span>         | <span data-ttu-id="fb316-214">Pacchetto per i driver di dispositivo e il firmware per Microsoft Surface Pro</span><span class="sxs-lookup"><span data-stu-id="fb316-214">Package for the device drivers and firmware for Microsoft Surface Pro</span></span>                     |
| <span data-ttu-id="fb316-215">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="fb316-215">Surface Pro 4</span></span>                        | <span data-ttu-id="fb316-216">Pacchetto del driver</span><span class="sxs-lookup"><span data-stu-id="fb316-216">Driver package</span></span>         | <span data-ttu-id="fb316-217">Pacchetto per i driver di dispositivo e il firmware per Microsoft Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="fb316-217">Package for the device drivers and firmware for Microsoft Surface Pro 4</span></span>                   |

<span data-ttu-id="fb316-218">Per altre informazioni, vedere [pacchetti e programmi in Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs).</span><span class="sxs-lookup"><span data-stu-id="fb316-218">For more information, see [Packages and programs in Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs).</span></span>

### <a name="create-folders-for-the-package-source-files"></a><span data-ttu-id="fb316-219">Creare cartelle per i file di origine del pacchetto</span><span class="sxs-lookup"><span data-stu-id="fb316-219">Create folders for the package source files</span></span>

<span data-ttu-id="fb316-220">Configuration Manager richiede che i file di origine del pacchetto vengano organizzati in una struttura di cartelle specifica quando vengono creati e aggiornati.</span><span class="sxs-lookup"><span data-stu-id="fb316-220">Configuration Manager requires package source files to be organized in a specific folder structure when they're first created and when they're updated.</span></span>

<span data-ttu-id="fb316-221">Creare la struttura di cartelle seguente nel sito di amministrazione centrale o nel sito principale di Microsoft endpoint Configuration Manager oppure in una condivisione server che si sta usando per ospitare i file di origine del pacchetto:</span><span class="sxs-lookup"><span data-stu-id="fb316-221">Create the following folder structure on the Microsoft Endpoint Configuration Manager central administration site or primary site, or on a server share you're using to host package source files:</span></span>

-   <span data-ttu-id="fb316-222">SRS v2-pacchetto agente di monitoraggio Microsoft</span><span class="sxs-lookup"><span data-stu-id="fb316-222">SRS v2 - Microsoft Monitoring Agent Package</span></span>
-   <span data-ttu-id="fb316-223">Pacchetto aggiornamenti di SRS V2-OS</span><span class="sxs-lookup"><span data-stu-id="fb316-223">SRS v2 - OS Updates Package</span></span>
-   <span data-ttu-id="fb316-224">Pacchetto di certificato radice SRS V2</span><span class="sxs-lookup"><span data-stu-id="fb316-224">SRS v2 - Root Certificate Package</span></span>
-   <span data-ttu-id="fb316-225">Pacchetto SRS V2-Set-SRSComputerName</span><span class="sxs-lookup"><span data-stu-id="fb316-225">SRS v2 - Set-SRSComputerName Package</span></span>
-   <span data-ttu-id="fb316-226">Pacchetto di applicazione SRS V2-SRS</span><span class="sxs-lookup"><span data-stu-id="fb316-226">SRS v2 - SRS Application Package</span></span>
-   <span data-ttu-id="fb316-227">SRS V2-configurare l'installazione di SRS</span><span class="sxs-lookup"><span data-stu-id="fb316-227">SRS v2 - Configure SRS Setup</span></span>
-   <span data-ttu-id="fb316-228">SRS v2-pacchetto Sysprep</span><span class="sxs-lookup"><span data-stu-id="fb316-228">SRS v2 - Sysprep Package</span></span>
-   <span data-ttu-id="fb316-229">Driver</span><span class="sxs-lookup"><span data-stu-id="fb316-229">Drivers</span></span>
    -   <span data-ttu-id="fb316-230">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="fb316-230">Surface Pro</span></span>
    -   <span data-ttu-id="fb316-231">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="fb316-231">Surface Pro 4</span></span>
-   <span data-ttu-id="fb316-232">Sistemi operativi</span><span class="sxs-lookup"><span data-stu-id="fb316-232">Operating Systems</span></span>
    -   <span data-ttu-id="fb316-233">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="fb316-233">Windows 10 Enterprise</span></span>

> [!TIP]
> <span data-ttu-id="fb316-234">È anche possibile [scaricare](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) e usare il file zip che include la struttura delle cartelle per i pacchetti, gli script che è necessario usare e il modello di sequenza di attività che è necessario importare.</span><span class="sxs-lookup"><span data-stu-id="fb316-234">You may also [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) and use the zip file that includes the folder structure for the packages, the scripts that you need to use, and the task sequence template, that you need to import.</span></span>

### <a name="create-the-monitoring-agent-package"></a><span data-ttu-id="fb316-235">Creare il pacchetto agente di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="fb316-235">Create the Monitoring agent package</span></span>

1. <span data-ttu-id="fb316-236">Scaricare l'agente di monitoraggio da <https://go.microsoft.com/fwlink/?LinkId=828603> .</span><span class="sxs-lookup"><span data-stu-id="fb316-236">Download the Monitoring agent from <https://go.microsoft.com/fwlink/?LinkId=828603>.</span></span>

2. <span data-ttu-id="fb316-237">Estrarre il pacchetto nella cartella **SRS V2-Microsoft Monitoring Agent Package** aprendo una finestra del prompt dei comandi e immettendo **MMASetup-AMD64.exe/c:**     al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="fb316-237">Extract the package into the **SRS v2 - Microsoft Monitoring Agent Package** folder by opening a Command Prompt window and entering **MMASetup-AMD64.exe /C:**     at the command prompt.</span></span>

3. <span data-ttu-id="fb316-238">Nella console di Configuration Manager, passa a pacchetti di gestione applicazioni della **raccolta software** \>  \> e quindi scegli **Crea pacchetto**.</span><span class="sxs-lookup"><span data-stu-id="fb316-238">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="fb316-239">Immettere le informazioni seguenti per creare il pacchetto:</span><span class="sxs-lookup"><span data-stu-id="fb316-239">Enter the following information to create the package:</span></span>

   - <span data-ttu-id="fb316-240">Nome<strong>: SRS v2-pacchetto agente di monitoraggio Microsoft</strong></span><span class="sxs-lookup"><span data-stu-id="fb316-240">Name<strong>: SRS v2 - Microsoft Monitoring Agent Package</strong></span></span>

   - <span data-ttu-id="fb316-241">Produttore<strong>: Microsoft Corporation</strong></span><span class="sxs-lookup"><span data-stu-id="fb316-241">Manufacturer<strong>: Microsoft Corporation</strong></span></span>

   - <span data-ttu-id="fb316-242">Versione<strong>: 8.1.11081.0</strong> (immettere la versione del file di installazione scaricata)</span><span class="sxs-lookup"><span data-stu-id="fb316-242">Version<strong>: 8.1.11081.0</strong> (enter the version of the downloaded installation file)</span></span>

   - <span data-ttu-id="fb316-243">Selezionare la casella di controllo **questo pacchetto contiene i file di origine** , immettere il percorso della cartella del **pacchetto di agente di monitoraggio SRS V2-Microsoft** e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-243">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Microsoft Monitoring Agent Package** folder, and then select **Next**.</span></span>

5. <span data-ttu-id="fb316-244">Selezionare non **creare un programma** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-244">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="fb316-245">Esaminare la pagina **confermare le impostazioni** e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-245">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="fb316-246">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="fb316-246">Select **Close**.</span></span>

### <a name="create-the-operating-system-updates-package"></a><span data-ttu-id="fb316-247">Creare il pacchetto aggiornamenti del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="fb316-247">Create the operating system updates package</span></span>

1. <span data-ttu-id="fb316-248">Nella cartella **SRS V2-OS Updates Package** creare un nuovo script di PowerShell denominato **Install-SRSv2-OS-Updates.ps1**.</span><span class="sxs-lookup"><span data-stu-id="fb316-248">In the **SRS v2 - OS Updates Package** folder, create a new PowerShell script named **Install-SRSv2-OS-Updates.ps1**.</span></span>

2. <span data-ttu-id="fb316-249">Copiare lo script seguente nello script **Install-SRSv2-OS-Updates.ps1** .</span><span class="sxs-lookup"><span data-stu-id="fb316-249">Copy the script below into the **Install-SRSv2-OS-Updates.ps1** script.</span></span> <span data-ttu-id="fb316-250">In alternativa, è possibile scaricare lo script Install-SRSv2-OS-Updates.ps1 da [qui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="fb316-250">Alternatively, you can download the Install-SRSv2-OS-Updates.ps1 script from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
   ```
   # Install-SRSv2-OS-Updates.ps1
   $strPath = split-path -parent $MyInvocation.MyCommand.Definition
   $total = gci $strPath *.msu | measure | Select-Object -expand Count
   $i = 0
   gci $strPath *.msu | ForEach-Object {
     $i++
     WUSA ""$_.FullName /quiet /norestart""
     Write-Progress -activity "Applying Mandatory Updates" -status "Installing
     $_ .. $i of $total" -percentComplete (($i / $total) * 100)
     Wait-Process -name wusa
   }
   ```
3. <span data-ttu-id="fb316-251">Scaricare i pacchetti di Windows Update obbligatori nella stessa cartella.</span><span class="sxs-lookup"><span data-stu-id="fb316-251">Download the mandatory Windows Update packages into the same folder.</span></span>
   > [!NOTE]
   > <span data-ttu-id="fb316-252">Al momento della pubblicazione di questo articolo è stato richiesto solo [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) .</span><span class="sxs-lookup"><span data-stu-id="fb316-252">At the time this article was published, only [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) was required.</span></span> <span data-ttu-id="fb316-253">Selezionare [Configura una console Microsoft teams Rooms](console.md)per verificare se sono necessari altri aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="fb316-253">Check [Configure a Microsoft Teams Rooms console](console.md), to see whether any other updates are required.</span></span>

4. <span data-ttu-id="fb316-254">Nella console di Configuration Manager, passa a pacchetti di gestione applicazioni della **raccolta software** \>  \> e quindi scegli **Crea pacchetto**.</span><span class="sxs-lookup"><span data-stu-id="fb316-254">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

5. <span data-ttu-id="fb316-255">Immettere le informazioni seguenti per creare il pacchetto:</span><span class="sxs-lookup"><span data-stu-id="fb316-255">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="fb316-256">Nome: **SRS v2-pacchetto OS Updates**</span><span class="sxs-lookup"><span data-stu-id="fb316-256">Name: **SRS v2 – OS Updates Package**</span></span>
   -   <span data-ttu-id="fb316-257">Produttore: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="fb316-257">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="fb316-258">Versione: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="fb316-258">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="fb316-259">Selezionare la casella di controllo **questo pacchetto contiene i file di origine** , immettere il percorso della cartella **SRS V2-OS Updates Package** e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-259">Select the **This package contains source files** check box, enter the path to the **SRS v2 - OS Updates Package** folder, and then select **Next**.</span></span>

6. <span data-ttu-id="fb316-260">Selezionare non **creare un programma** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-260">Select **Do not create a program**, and then select **Next**.</span></span>

7. <span data-ttu-id="fb316-261">Esaminare la pagina **confermare le impostazioni** e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-261">Review the **Confirm the settings** page, and then select **Next**.</span></span>

8. <span data-ttu-id="fb316-262">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="fb316-262">Select **Close**.</span></span>

### <a name="create-the-root-certificate-package-optional"></a><span data-ttu-id="fb316-263">Creare il pacchetto di certificato radice (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="fb316-263">Create the root certificate package (optional)</span></span>

<span data-ttu-id="fb316-264">Questo pacchetto viene creato per distribuire il certificato radice per i dispositivi che non verranno aggiunti a un dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fb316-264">You create this package to distribute the root certificate for devices that won't be joined to an Active Directory domain.</span></span> <span data-ttu-id="fb316-265">Creare questo pacchetto solo se si applicano entrambe le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fb316-265">Create this package only if both the following conditions apply:</span></span>
-   <span data-ttu-id="fb316-266">La distribuzione include Lync locale o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fb316-266">Your deployment includes on-premises Lync or Skype for Business Server.</span></span>
-   <span data-ttu-id="fb316-267">Le unità di Microsoft teams Rooms sono configurate per l'utilizzo in un gruppo di lavoro anziché in un membro del dominio.</span><span class="sxs-lookup"><span data-stu-id="fb316-267">Microsoft Teams Rooms units are configured to work in a workgroup instead of a domain member.</span></span>

1.  <span data-ttu-id="fb316-268">Copiare il certificato radice nella cartella **SRS V2-Root Certificate Package** .</span><span class="sxs-lookup"><span data-stu-id="fb316-268">Copy the root certificate into the **SRS v2 – Root Certificate Package** folder.</span></span>

2.  <span data-ttu-id="fb316-269">Nella console di Configuration Manager, passa a pacchetti di gestione applicazioni della **raccolta software** \>  \> e quindi scegli **Crea pacchetto**.</span><span class="sxs-lookup"><span data-stu-id="fb316-269">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

3.  <span data-ttu-id="fb316-270">Immettere le informazioni seguenti per creare il pacchetto:</span><span class="sxs-lookup"><span data-stu-id="fb316-270">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="fb316-271">Nome: **SRS v2-pacchetto del certificato radice**</span><span class="sxs-lookup"><span data-stu-id="fb316-271">Name: **SRS v2 – Root Certificate Package**</span></span>
    -   <span data-ttu-id="fb316-272">Produttore: *nome dell'organizzazione*</span><span class="sxs-lookup"><span data-stu-id="fb316-272">Manufacturer: *Your organization's name*</span></span>
    -   <span data-ttu-id="fb316-273">Versione: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="fb316-273">Version: **1.0.0**</span></span>
    -   <span data-ttu-id="fb316-274">Selezionare la casella di controllo **questo pacchetto contiene i file di origine** , immettere il percorso della cartella **SRS V2-Root Certificate Package** e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-274">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Root Certificate Package** folder, and then select **Next**.</span></span>

4.  <span data-ttu-id="fb316-275">Selezionare non **creare un programma** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-275">Select **Do not create a program**, and then select **Next**.</span></span>

5.  <span data-ttu-id="fb316-276">Esaminare la pagina **confermare le impostazioni** e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-276">Review the **Confirm the settings** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="fb316-277">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="fb316-277">Select **Close**.</span></span>

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a><span data-ttu-id="fb316-278">Creare il pacchetto kit di distribuzione di Microsoft teams rooms</span><span class="sxs-lookup"><span data-stu-id="fb316-278">Create the Microsoft Teams Rooms deployment kit package</span></span>

1.  <span data-ttu-id="fb316-279">Scaricare la versione più recente del **Kit di distribuzione di Microsoft teams Rooms** <https://go.microsoft.com/fwlink/?linkid=851168> e installarla in una workstation.</span><span class="sxs-lookup"><span data-stu-id="fb316-279">Download the latest version of the **Microsoft Teams Rooms deployment kit** from <https://go.microsoft.com/fwlink/?linkid=851168>, and install it to a workstation.</span></span>

2.  <span data-ttu-id="fb316-280">Copiare il contenuto da **C: \\ Program Files (x86) \\ Skype room System Deployment Kit** nella cartella **SRS V2-SRS Application Package** .</span><span class="sxs-lookup"><span data-stu-id="fb316-280">Copy the content from **C:\\Program Files (x86)\\Skype Room System Deployment Kit** to the **SRS v2 - SRS Application Package** folder.</span></span>

3.  <span data-ttu-id="fb316-281">Nella console di Configuration Manager, passa a pacchetti di gestione applicazioni della **raccolta software** \>  \> e quindi scegli **Crea pacchetto**.</span><span class="sxs-lookup"><span data-stu-id="fb316-281">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="fb316-282">Immettere le informazioni seguenti per creare il pacchetto:</span><span class="sxs-lookup"><span data-stu-id="fb316-282">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="fb316-283">Nome: **SRS v2-pacchetto di applicazioni SRS**</span><span class="sxs-lookup"><span data-stu-id="fb316-283">Name: **SRS v2 – SRS Application Package**</span></span>
    -   <span data-ttu-id="fb316-284">Produttore: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="fb316-284">Manufacturer: **Microsoft Corporation**</span></span>
    -   <span data-ttu-id="fb316-285">Versione: **3.1.104.0** (immettere la versione del file di installazione scaricata)</span><span class="sxs-lookup"><span data-stu-id="fb316-285">Version: **3.1.104.0** (enter the version of the downloaded installation file)</span></span>
    -   <span data-ttu-id="fb316-286">Selezionare la casella di controllo **questo pacchetto contiene i file di origine** , immettere il percorso della cartella **SRS V2-SRS Application Package** e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-286">Select the **This package contains source files** check box, enter the path to the **SRS v2 – SRS Application Package** folder, and then select **Next**.</span></span>
5.  <span data-ttu-id="fb316-287">Selezionare non **creare un programma** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-287">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="fb316-288">Esaminare la pagina **confermare le impostazioni** e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-288">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="fb316-289">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="fb316-289">Select **Close**.</span></span>

### <a name="create-the-computer-name-assignment-package"></a><span data-ttu-id="fb316-290">Creare il pacchetto assegnazione nome computer</span><span class="sxs-lookup"><span data-stu-id="fb316-290">Create the computer name assignment package</span></span>

1.  <span data-ttu-id="fb316-291">Nella cartella **SRS V2-Set-SRSComputerName Package** creare una nuova applicazione HTML denominata **set-SRSComputerName. HTA** .</span><span class="sxs-lookup"><span data-stu-id="fb316-291">In the **SRS v2 - Set-SRSComputerName Package** folder, create a new HTML application named **Set-SRSComputerName.hta** .</span></span>

2.  <span data-ttu-id="fb316-292">Copiare lo script seguente nel file **set-SRSComputerName. HTA** .</span><span class="sxs-lookup"><span data-stu-id="fb316-292">Copy the following script into the **Set-SRSComputerName.hta** file.</span></span> <span data-ttu-id="fb316-293">In alternativa, è possibile scaricare il file Set-SRSComputerName. hta da [qui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="fb316-293">Alternatively, you can download the Set-SRSComputerName.hta file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
    ```HTML
    <!DOCTYPE HTML>
    <html>
    <head>
    <title>Set SRS Computer Name</title>
    <HTA:APPLICATION
      APPLICATIONNAME="Set SRS Computer Name"
      ID="SetSRSComputerName"
      VERSION="1.0"
      SCROLL="no"
      SINGLEINSTANCE="yes"
      WINDOWSTATE="maximize"
      MaximizeButton="no"
      MinimizeButton="no"
      SysMenu="no"
      ShowInTaskbar="no"
      Caption="no"
      />
    <style type="text/css">
    body {
        background-color: #fdfeff;
        color: darkblue;
        font-family: Calibri;
        font-size: 12pt;
        margin: 4em 3em;
    }
    </style>
    </head>
    <script language="VBScript">
    Public strNewComputerName
    Sub GenerateComputerName()
        strComputer = "."
        Set objWMIService = GetObject("winmgmts:\\" & strComputer & "\root\cimv2")
        Set colItems = objWMIService.ExecQuery("Select * from Win32_BIOS",,48)
        For Each objItem in colItems
            strSerialNumber = objItem.SerialNumber
        Next
        strNewComputerName = "SRS-"  & right(replace(strSerialNumber, "-","") ,10)
        TextArea1.innerHTML = "The serial number of the device: " & strSerialNumber
        strHTMLText = strHTMLText & "<br> Computer name to be assigned: <font color = red>" & strNewComputerName & "</font>"
        strHTMLText = strHTMLText & "<br><br> Click Accept to use this as the computer name and continue deployment, or Change to set a new name."
        strHTMLText = strHTMLText & "<p><input type=""button"" value=""Accept"" name = ""Accept_Button"" onclick=""SetComputerName"" />"
        strHTMLText = strHTMLText & " <input type=""button"" value=""Change"" name = ""Change_Button"" onclick=""ChangeComputerName"" />"
        TextArea2.innerHTML = strHTMLText
    End Sub

    Sub SetComputerName()
        dim result
        result = MsgBox("Computer Name to be assigned: " & strNewComputerName &vbcrlf & "Are you sure you want to continue?", 36)
        If (result = vbYes) then
            SET env = CreateObject("Microsoft.SMS.TSEnvironment")
            env("OSDComputerName") = strNewComputerName
            self.close
        elseif (result = vbNo) then
            Window_OnLoad
        End If
    End Sub

    Sub UpdateComputerName()
        strNewComputerName = newcomputername.value
        if len(trim(strNewComputerName)) = 0 then
            MsgBox "Computer name cannot be empty." &vbcrlf & "Update and try again.",16
            exit sub
        end if
        SetComputerName
    End Sub

    Sub ChangeComputerName()
        TextArea2.innerHTML = "<p>Type the new computer name and click Accept:  <input type=""text"" name=""newcomputername"" value =" & strNewComputerName & " />"
        TextArea2.innerHTML = TextArea2.innerHTML & "<br><input type=""button"" value=""Update"" name = ""Update_Button"" onclick=""UpdateComputerName"" />"
    End Sub

    Sub Window_OnLoad
        Set oTSProgressUI = CreateObject("Microsoft.SMS.TsProgressUI")
        oTSProgressUI.CloseProgressDialog
        GenerateComputerName
    End Sub
    </script>

    <body>
    <span id = "TextArea1"></span>
    <span id = "TextArea2">
    </span>
    </body>
    </html>

    ```
3.  <span data-ttu-id="fb316-294">Nella console di Configuration Manager, passa a pacchetti di gestione applicazioni della **raccolta software** \>  \> e quindi scegli **Crea pacchetto**.</span><span class="sxs-lookup"><span data-stu-id="fb316-294">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="fb316-295">Immettere le informazioni seguenti per creare il pacchetto:</span><span class="sxs-lookup"><span data-stu-id="fb316-295">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="fb316-296">Nome: **Pacchetto SRS V2-Set-SRSComputerName**</span><span class="sxs-lookup"><span data-stu-id="fb316-296">Name: **SRS v2 - Set-SRSComputerName Package**</span></span>

    -   <span data-ttu-id="fb316-297">Produttore: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="fb316-297">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="fb316-298">Versione: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="fb316-298">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="fb316-299">Selezionare la casella di controllo **questo pacchetto contiene i file di origine** , immettere il percorso della cartella del **Pacchetto SRS V2-Set-SRSComputerName** e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-299">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Set-SRSComputerName Package** folder, and then select **Next**.</span></span>

5.  <span data-ttu-id="fb316-300">Selezionare non **creare un programma** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-300">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="fb316-301">Esaminare la pagina **confermare le impostazioni** e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-301">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="fb316-302">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="fb316-302">Select **Close**.</span></span>

### <a name="create-the-sysprep-package"></a><span data-ttu-id="fb316-303">Creare il pacchetto Sysprep</span><span class="sxs-lookup"><span data-stu-id="fb316-303">Create the Sysprep package</span></span>

1. <span data-ttu-id="fb316-304">Nella cartella **SRS v2-pacchetto Sysprep** creare un nuovo file XML denominato **Unattend.xml** .</span><span class="sxs-lookup"><span data-stu-id="fb316-304">In the **SRS v2 – Sysprep Package** folder, create a new XML file named **Unattend.xml** .</span></span>

2. <span data-ttu-id="fb316-305">Copiare il testo seguente nel file **Unattend.xml** .</span><span class="sxs-lookup"><span data-stu-id="fb316-305">Copy the following text into the **Unattend.xml** file.</span></span> <span data-ttu-id="fb316-306">In alternativa, è possibile scaricare il file Unattend.xml da [qui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="fb316-306">Alternatively, you can download the Unattend.xml file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
   ```XML
   <?xml version="1.0" encoding="utf-8"?>
   <unattend xmlns="urn:schemas-microsoft-com:unattend">
   <settings pass="specialize">
       <component name="Microsoft-Windows-Embedded-BootExp" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="NonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <DisableBootMenu>1</DisableBootMenu>
           <DisplayDisabled>1</DisplayDisabled>
       </component>
       <component name="Microsoft-Windows-powercpl" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <PreferredPlan>8c5e7fda-e8bf-4a96-9a85-a6e23a8c635c</PreferredPlan>
       </component>
   </settings>
   <settings pass="oobeSystem">
       <component name="Microsoft-Windows-Shell-Setup" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <OOBE>
               <HideEULAPage>true</HideEULAPage>
               <HideLocalAccountScreen>true</HideLocalAccountScreen>
               <HideOEMRegistrationScreen>true</HideOEMRegistrationScreen>
               <HideOnlineAccountScreens>true</HideOnlineAccountScreens>
               <HideWirelessSetupInOOBE>true</HideWirelessSetupInOOBE>
               <SkipMachineOOBE>true</SkipMachineOOBE>
               <SkipUserOOBE>true</SkipUserOOBE>
               <ProtectYourPC>1</ProtectYourPC>
           </OOBE>
           <AutoLogon>
               <Enabled>true</Enabled>
               <Username>Skype</Username>
               <Password>
                   <Value>UABhAHMAcwB3AG8AcgBkAA==</Value>
                   <PlainText>false</PlainText>
               </Password>
           </AutoLogon>
           <UserAccounts>
               <LocalAccounts>
                   <LocalAccount wcm:action="add">
                       <Password>
                           <Value>cwBmAGIAUABhAHMAcwB3AG8AcgBkAA==</Value>
                           <PlainText>false</PlainText>
                       </Password>
                       <Name>Admin</Name>
                       <Group>Administrators</Group>
                       <DisplayName>Administrator</DisplayName>
                       <Description>Administrator</Description>
                   </LocalAccount>
               </LocalAccounts>
           </UserAccounts>
       </component>
   </settings>
   <cpi:offlineImage cpi:source="wim:h:/install.wim#Windows 10 Enterprise" xmlns:cpi="urn:schemas-microsoft-com:cpi" />
   </unattend>
   ```
3. <span data-ttu-id="fb316-307">Nella console di Configuration Manager, passa a pacchetti di gestione applicazioni della **raccolta software** \>  \> e quindi scegli **Crea pacchetto**.</span><span class="sxs-lookup"><span data-stu-id="fb316-307">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="fb316-308">Immettere le informazioni seguenti per creare il pacchetto:</span><span class="sxs-lookup"><span data-stu-id="fb316-308">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="fb316-309">Nome: **SRS v2-pacchetto Sysprep**</span><span class="sxs-lookup"><span data-stu-id="fb316-309">Name: **SRS v2 - Sysprep Package**</span></span>
   -   <span data-ttu-id="fb316-310">Produttore: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="fb316-310">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="fb316-311">Versione: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="fb316-311">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="fb316-312">Selezionare la casella di controllo **questo pacchetto contiene i file di origine** , immettere il percorso della cartella del **Pacchetto SRS V2-Sysprep** e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-312">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Sysprep Package** folder, and then select **Next**.</span></span>
5. <span data-ttu-id="fb316-313">Selezionare non **creare un programma** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-313">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="fb316-314">Esaminare la pagina **confermare le impostazioni** e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-314">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="fb316-315">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="fb316-315">Select **Close**.</span></span>

### <a name="create-the-windows-10-enterprise-package"></a><span data-ttu-id="fb316-316">Creare il pacchetto Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="fb316-316">Create the Windows 10 Enterprise package</span></span>

1.  <span data-ttu-id="fb316-317">Ottenere un supporto di Windows 10 Enterprise x64 e copiare il file **Install. wim** nella cartella **sistemi operativi \\ Windows 10 Enterprise** .</span><span class="sxs-lookup"><span data-stu-id="fb316-317">Obtain a Windows 10 Enterprise x64 media, and copy the **install.wim** file to the **Operating Systems\\Windows 10 Enterprise** folder.</span></span>

2.  <span data-ttu-id="fb316-318">Nella console di Configuration Manager, passa a immagini del sistema operativo dei sistemi operativi della **raccolta software** \>  \> e quindi seleziona **Aggiungi immagine del sistema operativo**.</span><span class="sxs-lookup"><span data-stu-id="fb316-318">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**, and then select **Add Operating System Image**.</span></span>

3.  <span data-ttu-id="fb316-319">Specificare il percorso del file **Install. wim** appena copiato e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-319">Specify the path to the **install.wim** file you just copied, and then select **Next**.</span></span>

4.  <span data-ttu-id="fb316-320">Aggiornare il campo **Version** per corrispondere al numero di build dell'immagine Enterprise di Windows 10 e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-320">Update the **Version** field to match the build number of the Windows 10 Enterprise image, and then select **Next**.</span></span>

5.  <span data-ttu-id="fb316-321">Esaminare la pagina dei **Dettagli** e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-321">Review the **Details** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="fb316-322">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="fb316-322">Select **Close**.</span></span>

<span data-ttu-id="fb316-323">Per altre informazioni, vedere [gestire le immagini del sistema operativo con Configuration Manager](https://docs.microsoft.com/configmgr/osd/get-started/manage-operating-system-images).</span><span class="sxs-lookup"><span data-stu-id="fb316-323">For more information, see [Manage OS images with Configuration Manager](https://docs.microsoft.com/configmgr/osd/get-started/manage-operating-system-images).</span></span>

### <a name="create-surface-pro-device-driver-packages"></a><span data-ttu-id="fb316-324">Creare pacchetti di driver di dispositivo Surface Pro</span><span class="sxs-lookup"><span data-stu-id="fb316-324">Create Surface Pro device driver packages</span></span>

<span data-ttu-id="fb316-325">Microsoft teams Rooms è supportato sia per Surface Pro che per Surface Pro 4.</span><span class="sxs-lookup"><span data-stu-id="fb316-325">Microsoft Teams Rooms is supported for both Surface Pro and Surface Pro 4.</span></span> <span data-ttu-id="fb316-326">È necessario creare un pacchetto di driver per ogni modello Surface Pro presente nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="fb316-326">You need to create a driver package for each Surface Pro model you have in your environment.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fb316-327">I driver devono essere compatibili con Windows 10 Enterprise Build e la versione del kit di distribuzione di Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="fb316-327">The drivers must be compatible with the Windows 10 Enterprise build and the Microsoft Teams Rooms deployment kit version.</span></span> <span data-ttu-id="fb316-328">Per altre informazioni, vedere [scaricare il firmware e i driver più recenti per i dispositivi Surface](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) e [configurare una console](console.md).</span><span class="sxs-lookup"><span data-stu-id="fb316-328">For more information, see [Download the latest firmware and drivers for Surface devices](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) and [Configure a console](console.md).</span></span>

1.  <span data-ttu-id="fb316-329">Scaricare i driver e il firmware più recenti.</span><span class="sxs-lookup"><span data-stu-id="fb316-329">Download the latest drivers and firmware.</span></span>
    -   <span data-ttu-id="fb316-330">Per Surface Pro: <https://www.microsoft.com/download/details.aspx?id=55484></span><span class="sxs-lookup"><span data-stu-id="fb316-330">For Surface Pro: <https://www.microsoft.com/download/details.aspx?id=55484></span></span>
    -   <span data-ttu-id="fb316-331">Per Surface Pro 4: <https://www.microsoft.com/download/details.aspx?id=49498></span><span class="sxs-lookup"><span data-stu-id="fb316-331">For Surface Pro 4: <https://www.microsoft.com/download/details.aspx?id=49498></span></span>

2.  <span data-ttu-id="fb316-332">Estrarre il driver e il firmware scaricati.</span><span class="sxs-lookup"><span data-stu-id="fb316-332">Extract the downloaded driver and firmware.</span></span> <span data-ttu-id="fb316-333">Aprire una finestra del prompt dei comandi e, al prompt dei comandi, immettere uno di questi comandi:</span><span class="sxs-lookup"><span data-stu-id="fb316-333">Open a Command Prompt window and at the command prompt, enter one of the following commands:</span></span>
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  <span data-ttu-id="fb316-334">Nella console di Configuration Manager accedere ai driver dei sistemi operativi della **raccolta software** \>  \> e quindi selezionare **Importa driver**.</span><span class="sxs-lookup"><span data-stu-id="fb316-334">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Drivers**, and then select **Import Driver**.</span></span>

4.  <span data-ttu-id="fb316-335">Selezionare **Importa tutti i driver nel percorso di rete seguente (UNC)**, selezionare la cartella di origine, ad esempio C: \\ _Sources \\ driver \\ Surface Pro, quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-335">Select **Import all drivers in the following network path (UNC)**, select the source folder (for example, C:\\_Sources\\Drivers\\Surface Pro), and then select **Next**.</span></span>

5.  <span data-ttu-id="fb316-336">Nella pagina **specificare i dettagli per i driver importati** selezionare tutti i driver elencati e quindi selezionare **Abilita questi driver e consentire ai computer di installarli**.</span><span class="sxs-lookup"><span data-stu-id="fb316-336">On the **Specify the details for the imported drivers** page, select all the listed drivers, and then select **Enable these drivers and allow computers to install them**.</span></span>

6.  <span data-ttu-id="fb316-337">Selezionare **categorie**, creare una nuova categoria che corrisponda al modello di superficie, selezionare **OK** e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-337">Select **Categories**, create a new category that matches the Surface model, select **OK**, and then select **Next**.</span></span>

7.  <span data-ttu-id="fb316-338">Selezionare **nuovo pacchetto**.</span><span class="sxs-lookup"><span data-stu-id="fb316-338">Select **New Package**.</span></span>

8.  <span data-ttu-id="fb316-339">Specificare il nome del pacchetto che corrisponde al modello Surface Pro, immettere il percorso di una cartella in cui archiviare i file del pacchetto del driver, selezionare **OK** e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-339">Specify the package name that matches the Surface Pro model, enter a folder path to store the driver package files in, select **OK**, and then select **Next**.</span></span>

9.  <span data-ttu-id="fb316-340">Nella pagina **Immagini di avvio** verificare che non siano selezionate immagini di avvio e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-340">On the **boot images** page, ensure that no boot images are selected, and then select **Next**.</span></span>

10. <span data-ttu-id="fb316-341">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="fb316-341">Select **Close**.</span></span>

11. <span data-ttu-id="fb316-342">Passare a  \> driver dei **sistemi operativi** \> della raccolta software, selezionare **cartella \> Crea cartella** e immettere il nome di una cartella corrispondente al modello Surface Pro a cui sono stati appena importati i driver.</span><span class="sxs-lookup"><span data-stu-id="fb316-342">Go to **Software Library** \> **Operating Systems** \> **Drivers**, select **Folder \> Create Folder**, and enter a folder name that matches the Surface Pro model that you just imported the drivers for.</span></span>

12. <span data-ttu-id="fb316-343">Sposta tutti i driver importati nella cartella appena creata per semplificare l'esplorazione e l'operazione.</span><span class="sxs-lookup"><span data-stu-id="fb316-343">Move all the imported drivers to the newly created folder for easier navigation and operation.</span></span>

> [!NOTE]
> <span data-ttu-id="fb316-344">Ripetere gli stessi passaggi per altri modelli di Surface Pro che si potrebbero avere.</span><span class="sxs-lookup"><span data-stu-id="fb316-344">Repeat the same steps for other Surface Pro models you might have.</span></span> <span data-ttu-id="fb316-345">Per altre informazioni, vedere [gestire i driver in Configuration Manager](https://docs.microsoft.com/configmgr/osd/get-started/manage-drivers).</span><span class="sxs-lookup"><span data-stu-id="fb316-345">For more information, see [Manage drivers in Configuration Manager](https://docs.microsoft.com/configmgr/osd/get-started/manage-drivers).</span></span>

### <a name="create-microsoft-teams-rooms-configuration-package"></a><span data-ttu-id="fb316-346">Creare un pacchetto di configurazione di Microsoft teams rooms</span><span class="sxs-lookup"><span data-stu-id="fb316-346">Create Microsoft Teams Rooms Configuration Package</span></span>

1.  <span data-ttu-id="fb316-347">Nella console di Configuration Manager, passa a pacchetti di gestione applicazioni della **raccolta software** \>  \> e quindi scegli **Crea pacchetto**.</span><span class="sxs-lookup"><span data-stu-id="fb316-347">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

2.  <span data-ttu-id="fb316-348">Immettere le informazioni seguenti per creare il pacchetto:</span><span class="sxs-lookup"><span data-stu-id="fb316-348">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="fb316-349">Nome: **SRS V2-configurare il pacchetto di installazione di SRS**</span><span class="sxs-lookup"><span data-stu-id="fb316-349">Name: **SRS v2 - Configure SRS Setup Package**</span></span>

    -   <span data-ttu-id="fb316-350">Produttore: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="fb316-350">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="fb316-351">Versione: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="fb316-351">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="fb316-352">Selezionare la casella di controllo **questo pacchetto contiene i file di origine** , immettere il percorso della cartella **SRS V2-Configure SRS Setup** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-352">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Configure SRS Setup** folder, and then select **Next**.</span></span>

3.  <span data-ttu-id="fb316-353">Selezionare non **creare un programma** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-353">Select **Do not create a program**, and then select **Next**.</span></span>

4.  <span data-ttu-id="fb316-354">Esaminare la pagina **confermare le impostazioni** e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-354">Review the **Confirm the settings** page, and then select **Next**.</span></span>

5.  <span data-ttu-id="fb316-355">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="fb316-355">Select **Close**.</span></span>



## <a name="distribute-configuration-manager-packages"></a><span data-ttu-id="fb316-356">Distribuire pacchetti di Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="fb316-356">Distribute Configuration Manager packages</span></span>

<span data-ttu-id="fb316-357">Tutti i pacchetti devono essere distribuiti ai server a cui è stato assegnato il ruolo del punto di distribuzione nella gerarchia di Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="fb316-357">All the packages must be distributed to the servers that have been assigned the distribution point role in the Configuration Manager hierarchy.</span></span> <span data-ttu-id="fb316-358">Seguire le istruzioni riportate di seguito per avviare la distribuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="fb316-358">Follow the instructions below to initiate package distribution.</span></span>

1.  <span data-ttu-id="fb316-359">Distribuire pacchetti software.</span><span class="sxs-lookup"><span data-stu-id="fb316-359">Distribute software packages.</span></span>

    1.  <span data-ttu-id="fb316-360">Nella console di Configuration Manager, passa a  \> pacchetti di **Gestione applicazioni** della raccolta software \> .</span><span class="sxs-lookup"><span data-stu-id="fb316-360">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**.</span></span> <span data-ttu-id="fb316-361">Selezionare tutti i pacchetti software che si desidera distribuire e quindi selezionare **Distribuisci contenuto**.</span><span class="sxs-lookup"><span data-stu-id="fb316-361">Select all the software packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="fb316-362">Esaminare l'elenco dei pacchetti e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-362">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="fb316-363">Aggiungere tutti i server del punto di distribuzione (o i gruppi di punti di distribuzione, a seconda della gerarchia di Configuration Manager) all'elenco e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-363">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="fb316-364">Selezionare **Avanti**, quindi selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="fb316-364">Select **Next**, and then select **Close**.</span></span>

2.  <span data-ttu-id="fb316-365">Distribuire pacchetti driver.</span><span class="sxs-lookup"><span data-stu-id="fb316-365">Distribute driver packages.</span></span>

    1.  <span data-ttu-id="fb316-366">Nella console di Configuration Manager passa a  \>  \> **pacchetti driver** dei sistemi operativi della raccolta software.</span><span class="sxs-lookup"><span data-stu-id="fb316-366">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Driver Packages**.</span></span> <span data-ttu-id="fb316-367">Selezionare tutti i pacchetti di driver che si desidera distribuire e quindi selezionare **Distribuisci contenuto**.</span><span class="sxs-lookup"><span data-stu-id="fb316-367">Select all the driver packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="fb316-368">Esaminare l'elenco dei pacchetti e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-368">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="fb316-369">Aggiungere tutti i server del punto di distribuzione (o i gruppi di punti di distribuzione, a seconda della gerarchia di Configuration Manager) all'elenco e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-369">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="fb316-370">Selezionare **Avanti**, quindi selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="fb316-370">Select **Next**, and then select **Close**.</span></span>

3.  <span data-ttu-id="fb316-371">Distribuire pacchetti di sistemi operativi.</span><span class="sxs-lookup"><span data-stu-id="fb316-371">Distribute operating system packages.</span></span>

    1.  <span data-ttu-id="fb316-372">Nella console di Configuration Manager accedere alle immagini del sistema operativo della **raccolta software** \>  \> .</span><span class="sxs-lookup"><span data-stu-id="fb316-372">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**.</span></span> <span data-ttu-id="fb316-373">Selezionare tutte le immagini del sistema operativo che si desidera distribuire e quindi selezionare **Distribuisci contenuto**.</span><span class="sxs-lookup"><span data-stu-id="fb316-373">Select all the operating system images you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="fb316-374">Esaminare l'elenco dei pacchetti e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-374">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="fb316-375">Aggiungere tutti i server del punto di distribuzione (o i gruppi di punti di distribuzione, a seconda della gerarchia di Configuration Manager) all'elenco e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-375">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="fb316-376">Selezionare **Avanti**, quindi selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="fb316-376">Select **Next**, and then select **Close**.</span></span>

> [!NOTE]
> <span data-ttu-id="fb316-377">La distribuzione del pacchetto può richiedere del tempo, a seconda delle dimensioni del pacchetto, della gerarchia di Configuration Manager, del numero di server del punto di distribuzione e della larghezza di banda disponibile nella rete.</span><span class="sxs-lookup"><span data-stu-id="fb316-377">Package distribution might take some time, depending on the package size, Configuration Manager hierarchy, number of distribution point servers, and the bandwidth available in your network.</span></span>
> 
> <span data-ttu-id="fb316-378">Tutti i pacchetti devono essere distribuiti prima di poter avviare la distribuzione di un'unità Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="fb316-378">All the packages must be distributed before you can start deploying a Microsoft Teams Rooms unit.</span></span>
> 
> <span data-ttu-id="fb316-379">Per verificare lo stato della distribuzione del pacchetto nella console di Configuration Manager, è possibile **monitorare** lo stato del contenuto della \> **distribuzione** \> .</span><span class="sxs-lookup"><span data-stu-id="fb316-379">You can review the status of your package distribution in the Configuration Manager console by going to **Monitoring** \> **Distribution Status** \> **Content Status**.</span></span>

## <a name="configuration-manager-task-sequences"></a><span data-ttu-id="fb316-380">Sequenze di attività di gestione configurazione</span><span class="sxs-lookup"><span data-stu-id="fb316-380">Configuration Manager task sequences</span></span>

<span data-ttu-id="fb316-381">Puoi usare le sequenze di attività con Configuration Manager per automatizzare i passaggi per la distribuzione di un'immagine del sistema operativo in un computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="fb316-381">You use task sequences with Configuration Manager to automate the steps for deploying an operating system image to a destination computer.</span></span> <span data-ttu-id="fb316-382">Per distribuire un'unità Microsoft teams rooms in modo automatico, è possibile creare una sequenza di attività che faccia riferimento all'immagine di avvio usata per avviare il computer di Microsoft teams rooms, l'immagine del sistema operativo Windows 10 Enterprise che si vuole installare e qualsiasi altro contenuto aggiuntivo, ad esempio altre applicazioni o aggiornamenti software.</span><span class="sxs-lookup"><span data-stu-id="fb316-382">To deploy a Microsoft Teams Rooms unit in an automated fashion, you create a task sequence that references the boot image used to start the destination Microsoft Teams Rooms computer, the Windows 10 Enterprise operating system image that you want to install, and any other additional content, such as other applications or software updates.</span></span>

### <a name="import-the-sample-task-sequence"></a><span data-ttu-id="fb316-383">Importare la sequenza di attività di esempio</span><span class="sxs-lookup"><span data-stu-id="fb316-383">Import the sample task sequence</span></span>

<span data-ttu-id="fb316-384">È possibile scaricare e importare facilmente una sequenza di attività di esempio e personalizzarla per soddisfare le proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="fb316-384">You can download and easily import a sample task sequence and customize it to meet your needs.</span></span>

1.  <span data-ttu-id="fb316-385">[**Scaricare**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) la sequenza di attività di esempio e copiare il file zip scaricato in un percorso condiviso.</span><span class="sxs-lookup"><span data-stu-id="fb316-385">[**Download**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) the sample task sequence, and copy the downloaded zip file to a shared location.</span></span>
2.  <span data-ttu-id="fb316-386">Nella console di Configuration Manager accedere alle sequenze di attività dei sistemi operativi della **raccolta software** \>  \> e quindi selezionare **Importa sequenza attività**.</span><span class="sxs-lookup"><span data-stu-id="fb316-386">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Task Sequences**, and then select **Import Task Sequence**.</span></span>

3.  <span data-ttu-id="fb316-387">Selezionare **Sfoglia**, passare al percorso della cartella condivisa usato nel passaggio 1, selezionare il file **Microsoft teams Deployment Rooms (en-US). zip** e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-387">Select **Browse**, go to the shared folder location you used in step 1, select the **Microsoft Teams Rooms Deployment (EN-US).zip** file, and then select **Next**.</span></span>

4.  <span data-ttu-id="fb316-388">Impostare **Action** per **creare nuovi** e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-388">Set **Action** to **Create New**, and then select **Next**.</span></span>

5.  <span data-ttu-id="fb316-389">Confermare le impostazioni e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-389">Confirm the settings, and then select **Next**.</span></span>

6.  <span data-ttu-id="fb316-390">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="fb316-390">Select **Close**.</span></span>

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a><span data-ttu-id="fb316-391">Verificare che i pacchetti di riferimento siano collegati correttamente a ogni passaggio di sequenza delle attività.</span><span class="sxs-lookup"><span data-stu-id="fb316-391">Validate that the reference packages are correctly linked to each task sequence step.</span></span>

1. <span data-ttu-id="fb316-392">Selezionare la sequenza di attività importata e quindi selezionare **modifica**.</span><span class="sxs-lookup"><span data-stu-id="fb316-392">Select the imported task sequence, and then select **Edit**.</span></span>

    <span data-ttu-id="fb316-393">Viene aperto l'editor sequenza attività e viene visualizzato ogni passaggio sequenziale necessario per la distribuzione e la configurazione di un'unità Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="fb316-393">The Task Sequence Editor opens and displays each sequential step that you need to deploy and configure a Microsoft Teams Rooms unit.</span></span>

2. <span data-ttu-id="fb316-394">Scorrere ogni passaggio e completare gli aggiornamenti consigliati:</span><span class="sxs-lookup"><span data-stu-id="fb316-394">Walk through each step and complete the recommended updates:</span></span>

   1. <span data-ttu-id="fb316-395">**Riavvio in Windows PE**: questo passaggio viene riavviato e il computer viene avviato in Windows PXE.</span><span class="sxs-lookup"><span data-stu-id="fb316-395">**Restart in Windows PE**: This step restarts and then boots the computer into Windows PXE.</span></span> <span data-ttu-id="fb316-396">Per questo passaggio non sono necessarie modifiche.</span><span class="sxs-lookup"><span data-stu-id="fb316-396">No changes are required for this step.</span></span>

   2. <span data-ttu-id="fb316-397">**Partizione disco 0-UEFI**: questo passaggio consente di Wipe la configurazione del disco e crea partizioni in base alle impostazioni configurate.</span><span class="sxs-lookup"><span data-stu-id="fb316-397">**Partition Disk 0 – UEFI**: This step wipes the disk configuration and creates partitions based on the configured settings.</span></span> <span data-ttu-id="fb316-398">È consigliabile non apportare modifiche a questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="fb316-398">We recommend that you not make any changes to this step.</span></span>

   3. <span data-ttu-id="fb316-399">**Impostare il nome di computer SRS**: questo passaggio include un'applicazione HTML che fornisce un'interfaccia utente per impostare un nome di computer per l'unità Microsoft teams Rooms durante la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="fb316-399">**Set SRS Computer Name**: This step includes an HTML application to provide a UI to set a computer name for the Microsoft Teams Rooms unit during the deployment.</span></span>
      -  <span data-ttu-id="fb316-400">Si tratta di un passaggio facoltativo, ma può essere disabilitato solo se si vuole gestire la denominazione dei computer tramite un processo alternativo.</span><span class="sxs-lookup"><span data-stu-id="fb316-400">This is an optional step, but it can only be disabled if you want to manage computer naming through an alternate process.</span></span>
      -  <span data-ttu-id="fb316-401">Verificare che sia selezionato il pacchetto **SRS v2-set-SRSComputerName** .</span><span class="sxs-lookup"><span data-stu-id="fb316-401">Verify that the **SRS v2 - Set-SRSComputerName** package is selected.</span></span> <span data-ttu-id="fb316-402">In caso affermativo, passare al pacchetto e selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="fb316-402">If it isn't, browse to the package and select it.</span></span>

   4. <span data-ttu-id="fb316-403">**Applica sistema operativo**: questo passaggio specifica l'immagine del sistema operativo da distribuire e il file di risposte di Sysprep non presidiato da usare.</span><span class="sxs-lookup"><span data-stu-id="fb316-403">**Apply Operating System**: This step specifies the operating system image to be deployed and the unattended Sysprep answer file to use.</span></span>
      -  <span data-ttu-id="fb316-404">Verificare che sia selezionato il file di immagine del sistema operativo Windows 10 corretto.</span><span class="sxs-lookup"><span data-stu-id="fb316-404">Verify that the correct Windows 10 Enterprise operating system image file is selected.</span></span>
      -  <span data-ttu-id="fb316-405">Verificare che sia abilitato l' **uso di un file di risposte non presidiato o Sysprep per un'installazione personalizzata** e che sia selezionato il **Pacchetto SRS V2-Sysprep** .</span><span class="sxs-lookup"><span data-stu-id="fb316-405">Verify that **Use an unattended or Sysprep answer file for a custom installation** is enabled, and the **SRS v2 - Sysprep Package** is selected.</span></span> <span data-ttu-id="fb316-406">Verificare inoltre che il **nome file** sia impostato su **unattend.xml**.</span><span class="sxs-lookup"><span data-stu-id="fb316-406">Also ensure that **File Name** is set to **unattend.xml**.</span></span>

   5. <span data-ttu-id="fb316-407">**Applica impostazioni di Windows**: questo passaggio raccoglie informazioni sull'installazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="fb316-407">**Apply Windows Settings**: This step gathers information about the Windows installation.</span></span>
      -  <span data-ttu-id="fb316-408">Fornisci informazioni sulle licenze e la registrazione, tra cui il codice Product Key, la password dell'account di amministratore locale e il fuso orario (a seconda delle esigenze).</span><span class="sxs-lookup"><span data-stu-id="fb316-408">Provide licensing and registration information including the product key, local administrator account password, and time zone (depending on your needs).</span></span>

   6. <span data-ttu-id="fb316-409">**Applica impostazioni di rete**: questo passaggio consente di specificare un nome di dominio e un'unità organizzativa di gruppo di lavoro o Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fb316-409">**Apply Network Settings**: This step allows you to specify a workgroup or Active Directory domain name and organizational unit.</span></span>
      > [!NOTE]
      > <span data-ttu-id="fb316-410">Vedi [considerazioni sul dominio del sistema room di Skype](domain-joining-considerations.md) per le azioni consigliate necessarie per la distribuzione delle unità di Microsoft teams rooms come membri di un dominio della directory actve.</span><span class="sxs-lookup"><span data-stu-id="fb316-410">See [Skype Room System domain joining considerations](domain-joining-considerations.md) for recommended actions you need to take in deploying Microsoft Teams Rooms units as members of an Actve Directory domain.</span></span>
   7. <span data-ttu-id="fb316-411">**Applicare i driver:** Questo passaggio e i relativi passaggi secondari vengono usati per distribuire i driver di dispositivo e il firmware applicabili in base al modello Surface Pro in uso.</span><span class="sxs-lookup"><span data-stu-id="fb316-411">**Apply Drivers:** This step and its sub-steps are used to deploy applicable device drivers and firmware based on the Surface Pro model you have.</span></span> <span data-ttu-id="fb316-412">Aggiornare ogni passaggio per specificare il pacchetto del driver pertinente associato alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="fb316-412">Update each step to specify the relevant driver package associated with this deployment.</span></span>
      -   <span data-ttu-id="fb316-413">Ogni pacchetto di driver è configurato per sfruttare i filtri di Strumentazione gestione Windows (WMI) per distribuire driver e firmware rilevanti in base alla creazione e al modello di Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="fb316-413">Each driver package is configured to leverage Windows Management Instrumentation (WMI) filters to deploy relevant drivers and firmware based on the Surface Pro make and model.</span></span>
      -   <span data-ttu-id="fb316-414">Ti consigliamo vivamente di non modificare la configurazione di questi driver, altrimenti la distribuzione potrebbe non riuscire.</span><span class="sxs-lookup"><span data-stu-id="fb316-414">We highly recommend that you not alter the configuration of these drivers, otherwise deployment might fail.</span></span>

   8. <span data-ttu-id="fb316-415">Configurare **Windows e Configuration Manager**: questo passaggio consente di distribuire e configurare il client di Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="fb316-415">**Set up Windows and Configuration Manager**: This step deploys and configures the Configuration Manager client.</span></span> <span data-ttu-id="fb316-416">Aggiornare questo passaggio per specificare il pacchetto client predefinito di Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="fb316-416">Update this step to specify the built-in Configuration Manager Client Package.</span></span>

   9. <span data-ttu-id="fb316-417">**Installa certificato radice**: questo passaggio distribuisce il certificato radice per i dispositivi non collegati al dominio e quindi è facoltativo e disabilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="fb316-417">**Install Root Certificate**: This step distributes the root certificate for non–domain-joined devices, and therefore is optional and disabled by default.</span></span>
      -   <span data-ttu-id="fb316-418">Abilitare questo passaggio se è necessario distribuire un certificato radice nelle unità di Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="fb316-418">Enable this step if you need to deploy a root certificate to the Microsoft Teams Rooms units.</span></span>
      -   <span data-ttu-id="fb316-419">Se è necessario eseguire questo passaggio, verificare che il **Pacchetto SRS V2-root certificate** e **disabilitare il reindirizzamento del file System di 64 bit** siano selezionati.</span><span class="sxs-lookup"><span data-stu-id="fb316-419">If you do need to perform this step, verify that the **SRS v2 – Root Certificate Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   10. <span data-ttu-id="fb316-420">**Installare e configurare agente di monitoraggio**: in questo passaggio viene installata la versione a 64 bit dell'agente di monitoraggio Microsoft Azure e viene configurato l'agente per la connessione all'area di lavoro analisi log.</span><span class="sxs-lookup"><span data-stu-id="fb316-420">**Install and Configure Monitoring Agent**: This step installs the 64-bit version of the Microsoft Azure Monitor agent and configures the agent to connect to your Log Analytics workspace.</span></span>
       -   <span data-ttu-id="fb316-421">Questo passaggio è disabilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="fb316-421">This step is disabled by default.</span></span> <span data-ttu-id="fb316-422">Abilitare questo passaggio solo se si vuole usare l'agente di monitoraggio per monitorare l'integrità delle unità di Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="fb316-422">Enable this step only if you're going to use the Monitoring Agent to monitor the health of your Microsoft Teams Rooms units.</span></span>
       -   <span data-ttu-id="fb316-423">Modificare questo passaggio e aggiornare i parametri della riga di comando per specificare l' **ID area** di lavoro e la **chiave dell'area di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="fb316-423">Edit this step and update the command-line parameters to specify your **Workspace ID** and **Workspace Key**.</span></span>
       -   <span data-ttu-id="fb316-424">Per altre informazioni su come ottenere l'ID area di lavoro di Operations Management Suite e la chiave primaria, vedere [configurare i dispositivi di test per il monitoraggio di Azure](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) .</span><span class="sxs-lookup"><span data-stu-id="fb316-424">See [Configure test devices for Azure Monitoring](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) for more information about obtaining the Operations Management Suite Workspace ID and the primary key.</span></span>
       -   <span data-ttu-id="fb316-425">Verificare che il **Pacchetto SRS V2-Microsoft Monitoring Agent** e **disabilitare il reindirizzamento del file System di 64 bit** siano selezionati.</span><span class="sxs-lookup"><span data-stu-id="fb316-425">Verify that the **SRS v2 – Microsoft Monitoring Agent Package** and **Disable 64-bit file system redirection** are selected.</span></span>
       -   <span data-ttu-id="fb316-426">Per altre informazioni sul monitoraggio dell'integrità della distribuzione di Microsoft teams rooms, vedere [pianificare la gestione di Microsoft teams Rooms con Azure monitor](azure-monitor-plan.md), [distribuire Gestione di Microsoft teams Rooms con Azure monitor](azure-monitor-deploy.md) e [gestire i dispositivi Microsoft teams Rooms con Azure monitor](azure-monitor-manage.md).</span><span class="sxs-lookup"><span data-stu-id="fb316-426">For more information about monitoring the health of your Microsoft Teams Rooms deployment, see [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md) and [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-manage.md).</span></span>

   11. <span data-ttu-id="fb316-427">**Copiare i file di configurazione di SRS V2**: in questo passaggio vengono copiati i file di installazione e configurazione necessari dal kit di distribuzione di Microsoft teams Rooms nel disco rigido locale.</span><span class="sxs-lookup"><span data-stu-id="fb316-427">**Copy SRS v2 Configuration Files**: This step copies the required setup and configuration files from the Microsoft Teams Rooms deployment kit to the local hard drive.</span></span> <span data-ttu-id="fb316-428">Per questo passaggio non è necessario alcun adattamento.</span><span class="sxs-lookup"><span data-stu-id="fb316-428">No customization is required for this step.</span></span>
       -   <span data-ttu-id="fb316-429">Verificare che il **pacchetto di applicazione SRS V2-SRS** e **disabilitare il reindirizzamento del file System di 64 bit** siano selezionati.</span><span class="sxs-lookup"><span data-stu-id="fb316-429">Verify that the **SRS v2 – SRS Application Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   12. <span data-ttu-id="fb316-430">**Install-SRSv2-OS-Updates**: questo passaggio distribuisce gli eventuali aggiornamenti obbligatori del sistema operativo necessari con la distribuzione di Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="fb316-430">**Install-SRSv2-OS-Updates**: This step deploys any mandatory operating system updates required with the Microsoft Teams Rooms deployment.</span></span> <span data-ttu-id="fb316-431">Eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fb316-431">Do the following:</span></span>
       -   <span data-ttu-id="fb316-432">Selezionare [Configura una console Microsoft teams Rooms](console.md) per vedere quali aggiornamenti sono necessari.</span><span class="sxs-lookup"><span data-stu-id="fb316-432">Check [Configure a Microsoft Teams Rooms console](console.md) to see which updates are required.</span></span>
       -   <span data-ttu-id="fb316-433">Verificare che il **pacchetto degli aggiornamenti di SRS V2-OS** includa tutti gli aggiornamenti necessari.</span><span class="sxs-lookup"><span data-stu-id="fb316-433">Verify that your **SRS v2 – OS Updates Package** includes all the required updates.</span></span>
       -   <span data-ttu-id="fb316-434">Verificare che sia selezionato il **Pacchetto SRS V2-OS Updates** .</span><span class="sxs-lookup"><span data-stu-id="fb316-434">Verify that the **SRS v2 – OS Updates Package** is selected.</span></span>
       -   <span data-ttu-id="fb316-435">Verificare che il criterio di esecuzione di PowerShell sia impostato su **bypass**.</span><span class="sxs-lookup"><span data-stu-id="fb316-435">Verify that the PowerShell execution policy is set to **Bypass**.</span></span>

   13. <span data-ttu-id="fb316-436">**Riavviare il computer**: questo passaggio riavvia il computer dopo l'installazione degli aggiornamenti obbligatori del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="fb316-436">**Restart Computer**: This step reboots the computer after the mandatory operating system updates are installed.</span></span> <span data-ttu-id="fb316-437">Per questo passaggio non è necessario alcun adattamento.</span><span class="sxs-lookup"><span data-stu-id="fb316-437">No customization is required for this step.</span></span>

   14. <span data-ttu-id="fb316-438">**Configurare i componenti di Windows**: questo passaggio Configura le funzionalità di Windows necessarie.</span><span class="sxs-lookup"><span data-stu-id="fb316-438">**Configure Windows Components**: This step configures the required Windows features.</span></span> <span data-ttu-id="fb316-439">Per questo passaggio non è necessario alcun adattamento.</span><span class="sxs-lookup"><span data-stu-id="fb316-439">No customization is required for this step.</span></span>

   15. <span data-ttu-id="fb316-440">**Riavviare il computer**: questo passaggio riavvia il computer dopo la configurazione delle funzionalità di Windows.</span><span class="sxs-lookup"><span data-stu-id="fb316-440">**Restart Computer**: This step reboots the computer after the Windows features are configured.</span></span> <span data-ttu-id="fb316-441">Per questo passaggio non è necessario alcun adattamento.</span><span class="sxs-lookup"><span data-stu-id="fb316-441">No customization is required for this step.</span></span>

   16. <span data-ttu-id="fb316-442">**Aggiungere un utente locale di Skype**: questo passaggio crea l'account Skype locale usato per accedere automaticamente a Windows e avviare l'applicazione Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="fb316-442">**Add Local Skype User**: This step creates the local Skype account used to automatically sign in to Windows and start the Microsoft Teams Rooms application.</span></span> <span data-ttu-id="fb316-443">Questo passaggio non contiene alcun pacchetto software associato e non è necessario alcun adattamento.</span><span class="sxs-lookup"><span data-stu-id="fb316-443">This step doesn't have any software package associated with it, and no customization is required for it.</span></span>

   17. <span data-ttu-id="fb316-444">**Impostare e configurare l'applicazione SRS**: in questo passaggio viene configurata l'installazione dell'applicazione Microsoft teams Rooms per l'avvio successivo del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="fb316-444">**Set up and configure SRS application**: This step configures the Microsoft Teams Rooms application installation for the next boot of the operating system.</span></span>
       -   <span data-ttu-id="fb316-445">Verificare che il **pacchetto di installazione SRS V2-configura SRS** e **disabilitare il reindirizzamento del file System di 64 bit** sia selezionato.</span><span class="sxs-lookup"><span data-stu-id="fb316-445">Verify that the **SRS v2 – Configure SRS Setup Package** and **Disable 64-bit file system redirection** are selected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fb316-446">È molto importante che i passaggi della sequenza di attività siano nell'ordine specificato.</span><span class="sxs-lookup"><span data-stu-id="fb316-446">It is very important that the task sequence steps must be in the provided order.</span></span> <span data-ttu-id="fb316-447">La modifica dell'ordine dei passaggi o la configurazione di passaggi aggiuntivi potrebbero interrompere la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="fb316-447">Modifying the order of steps, or configuring additional steps might break the deployment.</span></span>
>
> <span data-ttu-id="fb316-448">**Impostare e configurare il passaggio dell'applicazione SRS** deve essere l'ultimo passaggio della sequenza di attività, altrimenti la distribuzione potrebbe non riuscire.</span><span class="sxs-lookup"><span data-stu-id="fb316-448">**Set up and configure SRS application** step must be the last step in the task sequence, otherwise the deployment might fail.</span></span>

### <a name="create-deployment-for-the-task-sequence"></a><span data-ttu-id="fb316-449">Creare la distribuzione per la sequenza di attività</span><span class="sxs-lookup"><span data-stu-id="fb316-449">Create deployment for the task sequence</span></span>

1. <span data-ttu-id="fb316-450">Selezionare la sequenza di attività e quindi fare clic su **Distribuisci**.</span><span class="sxs-lookup"><span data-stu-id="fb316-450">Select the task sequence, and then select **Deploy**.</span></span>

2. <span data-ttu-id="fb316-451">Selezionare **Sfoglia** per selezionare la raccolta di destinazione per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="fb316-451">Select **Browse** to select target collection for deployment.</span></span>

3. <span data-ttu-id="fb316-452">Selezionare **tutti i computer sconosciuti** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb316-452">Select **All Unknown Computers** and then select **OK**.</span></span>

4. <span data-ttu-id="fb316-453">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-453">Select **Next**.</span></span>

5. <span data-ttu-id="fb316-454">Selezionare **disponibile** nell'elenco a discesa **scopo** .</span><span class="sxs-lookup"><span data-stu-id="fb316-454">Select **Available** on the **Purpose** drop down list.</span></span>

6. <span data-ttu-id="fb316-455">Selezionare **solo elementi multimediali e PXE** nell'elenco **Rendi disponibile per il seguente** e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-455">Select **Only Media and PXE** in the **Make available to the following** list, and then select **Next**.</span></span>
   > [!WARNING]
   > <span data-ttu-id="fb316-456">È molto importante che **lo scopo** sia impostato su **available**.</span><span class="sxs-lookup"><span data-stu-id="fb316-456">It is very important that **Purpose** is set to **Available**.</span></span> <span data-ttu-id="fb316-457">Verificare che lo **scopo** **non** sia impostato su **obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="fb316-457">Make sure that the **Purpose** is **NOT** set to **Required**.</span></span> <span data-ttu-id="fb316-458">Assicurarsi inoltre di selezionare **solo elementi multimediali e PXE** nella finestra **Rendi disponibile per le operazioni seguenti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-458">Also make sure that you select **Only Media and PXE** in the **Make available to the following**.</span></span>
   >
   > <span data-ttu-id="fb316-459">L'impostazione di questi valori su qualcos'altro può causare l'avvio di tutti i computer per ottenere l'immagine di distribuzione delle sale di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="fb316-459">Setting these values to something else might cause all computers to get the Microsoft Teams Rooms deployment image when booted.</span></span>
7. <span data-ttu-id="fb316-460">Non specificare alcuna pianificazione e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-460">Do not specify any schedule and select **Next**.</span></span>

8. <span data-ttu-id="fb316-461">Non modificare nulla nella sezione **esperienza utente** e selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-461">Do not change anything within the **User Experience** section and select **Next**.</span></span>

9. <span data-ttu-id="fb316-462">Non modificare nulla nella sezione **avvisi** e selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-462">Do not change anything within the **Alerts** section and select **Next**.</span></span>

10. <span data-ttu-id="fb316-463">Non modificare nulla nella sezione **punti di distribuzione** e selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-463">Do not change anything within the **Distribution Points** section and select **Next**.</span></span>

11. <span data-ttu-id="fb316-464">Confermare le impostazioni e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-464">Confirm the settings and then select **Next**.</span></span>

12. <span data-ttu-id="fb316-465">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="fb316-465">Select **Close**.</span></span>

<a name="validate-and-troubleshoot-the-solution"></a><span data-ttu-id="fb316-466">Convalidare e risolvere i problemi della soluzione</span><span class="sxs-lookup"><span data-stu-id="fb316-466">Validate and troubleshoot the solution</span></span>
--------------------------------------

<span data-ttu-id="fb316-467">Dopo aver completato le sequenze di attività di Microsoft endpoint Configuration Manager, è necessario eseguire un'esecuzione di test per verificare che la sequenza di attività sia in grado di distribuire e configurare le unità di Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="fb316-467">After you've completed the Microsoft Endpoint Configuration Manager task sequences, you'll need to perform a test run to validate that the task sequence can deploy and configure Microsoft Teams Rooms units.</span></span>

1.  <span data-ttu-id="fb316-468">Connettere il dispositivo di test alla rete cablata usando una delle schede Ethernet supportate o usando Surface Dock.</span><span class="sxs-lookup"><span data-stu-id="fb316-468">Connect the test device to the wired network by using one of the supported Ethernet adapters or using the Surface dock.</span></span> <span data-ttu-id="fb316-469">Se la funzionalità di avvio PXE non è stata configurata per l'ambiente in uso, è possibile usare l'immagine di avvio dell'unità flash USB [creata in precedenza](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media) per l'avvio da USB e la connessione a Gestione configurazione.</span><span class="sxs-lookup"><span data-stu-id="fb316-469">If PXE boot functionality hasn't been configured for your environment, you can use the boot image on the USB flash drive [that you created earlier](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media) to boot from USB and connect to Configuration Manager.</span></span>

2.  <span data-ttu-id="fb316-470">Accedere al firmware e avviare l'avvio PXE:</span><span class="sxs-lookup"><span data-stu-id="fb316-470">Access the firmware and initiate PXE boot:</span></span>

    1.  <span data-ttu-id="fb316-471">Verificare che il dispositivo Surface sia spento.</span><span class="sxs-lookup"><span data-stu-id="fb316-471">Ensure the Surface device is powered off.</span></span>

    2.  <span data-ttu-id="fb316-472">Premere e tenere premuto il pulsante **volume su** .</span><span class="sxs-lookup"><span data-stu-id="fb316-472">Press and hold the **Volume Up** button.</span></span>

    3.  <span data-ttu-id="fb316-473">Premere e rilasciare il pulsante di **accensione** .</span><span class="sxs-lookup"><span data-stu-id="fb316-473">Press and release the **Power** button.</span></span>

    4.  <span data-ttu-id="fb316-474">Dopo l'avvio del dispositivo, rilasciare il pulsante **volume su** .</span><span class="sxs-lookup"><span data-stu-id="fb316-474">After the device begins to boot, release the **Volume Up** button.</span></span>

    5.  <span data-ttu-id="fb316-475">Selezionare **configurazione di avvio**.</span><span class="sxs-lookup"><span data-stu-id="fb316-475">Select **Boot configuration**.</span></span>

    6.  <span data-ttu-id="fb316-476">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fb316-476">Do one of the following:</span></span>

        -   <span data-ttu-id="fb316-477">Selezionare **avvio PXE** e trascinarlo nella parte superiore dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="fb316-477">Select **PXE boot**, and drag it to the top of the list.</span></span> <span data-ttu-id="fb316-478">In alternativa, è possibile scorrere rapidamente verso sinistra sulla scheda di rete per avviare immediatamente il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fb316-478">Alternatively, you can swipe left on the network adapter to boot to the device immediately.</span></span> <span data-ttu-id="fb316-479">Questo non influirà sull'ordine di avvio.</span><span class="sxs-lookup"><span data-stu-id="fb316-479">This won't affect the boot order.</span></span>
        -   <span data-ttu-id="fb316-480">Selezionare l'unità flash USB che contiene il supporto di avvio.</span><span class="sxs-lookup"><span data-stu-id="fb316-480">Select the USB flash drive that holds the boot media.</span></span>

3.  <span data-ttu-id="fb316-481">Selezionare **Esci** e quindi **Riavvia ora**.</span><span class="sxs-lookup"><span data-stu-id="fb316-481">Select **Exit**, and then select **Restart Now**.</span></span>

4.  <span data-ttu-id="fb316-482">Quando richiesto, selezionare **invio** per il servizio di avvio di rete.</span><span class="sxs-lookup"><span data-stu-id="fb316-482">When prompted, select **Enter** for network boot service.</span></span>

5.  <span data-ttu-id="fb316-483">Windows PE verrà caricato in memoria e verrà avviata la procedura guidata per la sequenza di attività.</span><span class="sxs-lookup"><span data-stu-id="fb316-483">Windows PE will load into memory, and the Task Sequence Wizard will start.</span></span> <span data-ttu-id="fb316-484">Selezionare **Avanti** per continuare.</span><span class="sxs-lookup"><span data-stu-id="fb316-484">Select **Next** to continue.</span></span>

6.  <span data-ttu-id="fb316-485">Selezionare la sequenza di attività importata in precedenza e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fb316-485">Select the task sequence that you imported earlier, and then select **Next**.</span></span>

7.  <span data-ttu-id="fb316-486">Dopo aver applicato la configurazione del disco, verrà chiesto di specificare un nome di computer per il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fb316-486">After the disk configuration is applied, you'll be prompted to specify a computer name for the device.</span></span> <span data-ttu-id="fb316-487">L'interfaccia utente visualizzerà un nome di computer consigliato in base al numero seriale del dispositivo Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="fb316-487">The user interface will display a recommended computer name based on the serial number of the Surface Pro device.</span></span> <span data-ttu-id="fb316-488">Puoi accettare il nome proposto o specificarne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="fb316-488">You can either accept the proposed name or specify a new one.</span></span> <span data-ttu-id="fb316-489">Seguire le istruzioni nella schermata Assegnazione nome computer.</span><span class="sxs-lookup"><span data-stu-id="fb316-489">Follow the instructions on the computer name assignment screen.</span></span> <span data-ttu-id="fb316-490">Quando si seleziona **accetta**, viene avviata la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="fb316-490">When you select **Accept**, the deployment begins.</span></span>

8.  <span data-ttu-id="fb316-491">Il resto del processo di distribuzione è automatico e non richiede più input da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="fb316-491">The rest of the deployment process is automatic and doesn't ask for any more user input.</span></span>

9.  <span data-ttu-id="fb316-492">Al termine della configurazione dell'attività di distribuzione, verrà visualizzata la schermata di configurazione seguente che chiede di configurare le impostazioni dell'applicazione Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="fb316-492">After the deployment task sequence finishes configuring the device, you'll see the following configuration screen that asks you to configure the Microsoft Teams Rooms application settings.</span></span>

    ![Schermata di configurazione iniziale per l'applicazione Microsoft teams rooms](../media/room-systems-scale-image2.png)

10.  <span data-ttu-id="fb316-494">Collegare Surface Pro alla console Microsoft teams Rooms e configurare le impostazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fb316-494">Plug the Surface Pro into the Microsoft Teams Rooms console, and configure the application settings.</span></span>

11.  <span data-ttu-id="fb316-495">Verificare che le funzionalità elencate nella [Guida di Microsoft teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) stiano lavorando sul dispositivo distribuito.</span><span class="sxs-lookup"><span data-stu-id="fb316-495">Validate that the capabilities listed in [Microsoft Teams Rooms help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) are working on the deployed device.</span></span>


<span data-ttu-id="fb316-496">Per risolvere i problemi di un'installazione non riuscita, selezionare il file **Smsts. log** , che registra tutti i passaggi eseguiti in una sequenza di attività di gestione configurazione.</span><span class="sxs-lookup"><span data-stu-id="fb316-496">To troubleshoot a failed installation, check the **SMSTS.log** file, which logs all the steps executed in a Configuration Manager task sequence.</span></span>

<span data-ttu-id="fb316-497">Il file SMSTS. log viene archiviato in uno di un certo numero di percorsi, a seconda della fase del processo di compilazione.</span><span class="sxs-lookup"><span data-stu-id="fb316-497">The SMSTS.log file is stored on one of a number of paths, depending on the stage of the build process.</span></span> <span data-ttu-id="fb316-498">Selezionare la tabella seguente per identificare il percorso del file SMSTS. log.</span><span class="sxs-lookup"><span data-stu-id="fb316-498">Check the following table to identify the path to the SMSTS.log file.</span></span>


| <span data-ttu-id="fb316-499">**Fase di distribuzione**</span><span class="sxs-lookup"><span data-stu-id="fb316-499">**Deployment phase**</span></span>                                                            | <span data-ttu-id="fb316-500">**Percorso log sequenza attività**</span><span class="sxs-lookup"><span data-stu-id="fb316-500">**Task sequence log path**</span></span>                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| <span data-ttu-id="fb316-501">WinPE, prima del formato HDD</span><span class="sxs-lookup"><span data-stu-id="fb316-501">WinPE, before HDD format</span></span>                                                        | <span data-ttu-id="fb316-502">X: \\ Windows \\ temp \\ smstslog \\ Smsts. log</span><span class="sxs-lookup"><span data-stu-id="fb316-502">X:\\Windows\\Temp\\smstslog\\smsts.log</span></span>             |
| <span data-ttu-id="fb316-503">WinPE, dopo il formato HDD</span><span class="sxs-lookup"><span data-stu-id="fb316-503">WinPE, after HDD format</span></span>                                                         | <span data-ttu-id="fb316-504">C: \\ _SMSTaskSequence \\ log \\ Smstslog \\ Smsts. log</span><span class="sxs-lookup"><span data-stu-id="fb316-504">C:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="fb316-505">Sistema operativo distribuito prima dell'installazione dell'agente Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="fb316-505">Operating system deployed, before the Configuration Manager agent was installed</span></span> | <span data-ttu-id="fb316-506">c: \\ _SMSTaskSequence \\ log \\ Smstslog \\ Smsts. log</span><span class="sxs-lookup"><span data-stu-id="fb316-506">c:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="fb316-507">Sistema operativo e agente Configuration Manager distribuito</span><span class="sxs-lookup"><span data-stu-id="fb316-507">Operating system and the Configuration Manager agent deployed</span></span>                   | <span data-ttu-id="fb316-508">% WINDIR% \\ system32 \\ CCM \\ logs \\ Smstslog \\ Smsts. log</span><span class="sxs-lookup"><span data-stu-id="fb316-508">%windir%\\System32\\ccm\\logs\\Smstslog\\smsts.log</span></span> |
| <span data-ttu-id="fb316-509">Esecuzione della sequenza di attività completata</span><span class="sxs-lookup"><span data-stu-id="fb316-509">Task sequence execution complete</span></span>                                                | <span data-ttu-id="fb316-510">% WINDIR% \\ system32 \\ CCM \\ logs \\ Smsts. log</span><span class="sxs-lookup"><span data-stu-id="fb316-510">%windir%\\System32\\ccm\\logs\\smsts.log</span></span>           |

> [!TIP]
> <span data-ttu-id="fb316-511">È possibile selezionare **F8** in qualsiasi momento durante la sequenza di attività per aprire una console dei comandi e quindi accedere al file Smsts. log.</span><span class="sxs-lookup"><span data-stu-id="fb316-511">You can select **F8** at any time during the task sequence to open a command console, and then get access to the SMSTS.log file.</span></span>

<span data-ttu-id="fb316-512">Per risolvere i problemi di avvio PXE, controllare i due file di log nel server Configuration Manager specifici delle azioni PXE:</span><span class="sxs-lookup"><span data-stu-id="fb316-512">To troubleshoot PXE boot issues, check the two log files on the Configuration Manager server that are specific to PXE actions:</span></span>

-   <span data-ttu-id="fb316-513">**Pxecontrol. log**, disponibile nella directory log di installazione di Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="fb316-513">**Pxecontrol.log**, located in the Configuration Manager installation logs directory</span></span>

-   <span data-ttu-id="fb316-514">**SMSPXE. log**, situato nella directory dei registri di Configuration Manager Management Point (MP)</span><span class="sxs-lookup"><span data-stu-id="fb316-514">**Smspxe.log**, located in Configuration Manager Management Point (MP) logs directory</span></span>

<span data-ttu-id="fb316-515">Per un elenco completo dei file di log che è possibile usare per risolvere ulteriormente la procedura di installazione di Configuration Manager, vedere il [riferimento al file di log](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/log-files)di Microsoft endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="fb316-515">For a complete list of the log files that you can use to further troubleshoot your Configuration Manager installation, see the Microsoft Endpoint Configuration Manager [Log file reference](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/log-files).</span></span>

---
title: Distribuire le chat room di Microsoft Teams con Microsoft Endpoint Configuration Manager
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
description: Informazioni sulla distribuzione di Microsoft Teams Rooms su distribuzioni su larga scala con Microsoft Endpoint Configuration Manager.
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
ms.openlocfilehash: 2348d0f3e9d94aed80494155fbaab8288ddd97a6
ms.sourcegitcommit: 95386369e2256ba382b4d6e34adb7473de050b26
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/29/2021
ms.locfileid: "51410112"
---
# <a name="deploy-microsoft-teams-rooms-by-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="a4cdb-103">Distribuire le chat room di Microsoft Teams usando Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a4cdb-103">Deploy Microsoft Teams Rooms by using Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="a4cdb-104">Questo articolo fornisce tutte le informazioni necessarie per creare le distribuzioni di Microsoft Teams Rooms usando Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-104">This article gives you all the necessary information to create your Microsoft Teams Rooms deployments by using Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="a4cdb-105">Con i metodi di facile utilizzo forniti da Configuration Manager, è possibile distribuire il sistema operativo e altre applicazioni in più dispositivi di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-105">With the easy-to-use methods provided by Configuration Manager, you can deploy the operating system and other applications to multiple target devices.</span></span>

<span data-ttu-id="a4cdb-106">Usare l'approccio illustrato di seguito per illustrare la configurazione di Configuration Manager e personalizzare i pacchetti e gli script di esempio forniti in questa guida in base alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-106">Use the approach illustrated below to guide you through your Configuration Manager configuration, and customize the sample packages and scripts provided throughout this guidance as needed for your organization.</span></span>

![Processo di distribuzione di Microsoft Teams Rooms con Configuration Manager](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> <span data-ttu-id="a4cdb-108">Questa soluzione è stata testata solo con le distribuzioni basate su Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-108">This solution has only been tested with Surface Pro–based deployments.</span></span> <span data-ttu-id="a4cdb-109">Seguire le linee guida del produttore per le configurazioni non basate su Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-109">Follow the manufacturer's guidelines for configurations that aren't based on Surface Pro.</span></span>

## <a name="validate-prerequisites"></a><span data-ttu-id="a4cdb-110">Convalidare i prerequisiti</span><span class="sxs-lookup"><span data-stu-id="a4cdb-110">Validate prerequisites</span></span>

<span data-ttu-id="a4cdb-111">Per distribuire Microsoft Teams Rooms con Configuration Manager, assicurarsi di soddisfare i prerequisiti e i requisiti seguenti.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-111">To deploy Microsoft Teams Rooms with Configuration Manager, ensure that you meet the following prerequisites and requirements.</span></span>

### <a name="microsoft-endpoint-configuration-manager-requirements"></a><span data-ttu-id="a4cdb-112">Requisiti di Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a4cdb-112">Microsoft Endpoint Configuration Manager requirements</span></span>

-   <span data-ttu-id="a4cdb-113">La versione di Microsoft Endpoint Configuration Manager deve essere almeno 1706 o successiva.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-113">Microsoft Endpoint Configuration Manager version must be at least 1706 or above.</span></span> <span data-ttu-id="a4cdb-114">È consigliabile usare 1710 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-114">We recommend using 1710 or later.</span></span> <span data-ttu-id="a4cdb-115">Vedere [Supporto per Windows 10 in Configuration Manager](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) per informazioni sulle versioni di Windows 10 supportate da Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-115">Check out [Support for Windows 10 in Configuration Manager](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) to learn about the Windows 10 versions that Configuration Manager supports.</span></span>

-   <span data-ttu-id="a4cdb-116">Deve essere installata una versione supportata di Windows Assessment and Deployment Kit (ADK) per Windows 10.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-116">A supported version of Windows Assessment and Deployment Kit (ADK) for Windows 10 must be installed.</span></span> <span data-ttu-id="a4cdb-117">Vedere le versioni di [Windows 10 ADK](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk) che è possibile usare con diverse versioni di Configuration Manager e verificare che la distribuzione includa la versione corretta.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-117">See the versions of the [Windows 10 ADK](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk) that you can use with different versions of Configuration Manager, and ensure that your deployment includes the correct version.</span></span>

-   <span data-ttu-id="a4cdb-118">Ai server del sistema del sito deve essere stato assegnato il ruolo di punto di distribuzione e le immagini di avvio devono essere abilitate per il supporto [PXE (Preboot Execution Environment)](/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) per abilitare le distribuzioni avviate dalla rete.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-118">The site system servers must have been assigned the distribution point role, and the boot images should be enabled for [preboot execution environment (PXE) support](/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) to enable network-initiated deployments.</span></span> <span data-ttu-id="a4cdb-119">Se il supporto PXE non è abilitato, è possibile usare i supporti [di](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) avvio per le distribuzioni.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-119">If PXE support isn't enabled, you can use [bootable media](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments.</span></span>

-   <span data-ttu-id="a4cdb-120">Un account di accesso alla rete deve essere configurato per supportare nuovi scenari di distribuzione di computer (bare metal).</span><span class="sxs-lookup"><span data-stu-id="a4cdb-120">A network access account must be configured to support new computer (bare metal) deployment scenarios.</span></span> <span data-ttu-id="a4cdb-121">Per altre informazioni sulla configurazione di un account di accesso di rete, vedere [Account usati in Configuration Manager.](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)</span><span class="sxs-lookup"><span data-stu-id="a4cdb-121">To learn more about the configuration of a network access account, see [Accounts used in Configuration Manager](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

-   <span data-ttu-id="a4cdb-122">È consigliabile abilitare il [supporto multicast,](/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network)se è probabile che si distribuirà la stessa immagine di Microsoft Teams Rooms in più unità contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-122">We recommend that you enable [multicast support](/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), if you're likely to deploy the same Microsoft Teams Rooms image to multiple units at the same time.</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="a4cdb-123">Requisiti di rete</span><span class="sxs-lookup"><span data-stu-id="a4cdb-123">Networking requirements</span></span>

-   <span data-ttu-id="a4cdb-124">La rete deve avere un server DHCP (Dynamic Host Configuration Protocol), configurato per la distribuzione automatica degli indirizzi IP alle subnet in cui verranno distribuite le unità di Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-124">Your network should have a Dynamic Host Configuration Protocol (DHCP) server, configured for automatic IP address distribution to the subnets where Microsoft Teams Rooms units will be deployed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a4cdb-125">La durata del lease DHCP deve essere impostata su un valore più lungo della durata della distribuzione dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-125">DHCP lease duration must be set to a value longer than the image deployment duration.</span></span> <span data-ttu-id="a4cdb-126">In caso contrario, la distribuzione potrebbe non riuscire.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-126">Otherwise, the deployment might fail.</span></span>

-   <span data-ttu-id="a4cdb-127">La rete, inclusi gli switch e le reti LAN virtuali (VLAN), deve essere configurata per supportare PXE.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-127">Your network, including switches and virtual LANs (VLANs), should be configured to support PXE.</span></span> <span data-ttu-id="a4cdb-128">Per altre informazioni sulla configurazione di HELPER IP e PXE, vedere il fornitore della rete.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-128">Refer to your network vendor for more information about IP Helper and PXE configuration.</span></span> <span data-ttu-id="a4cdb-129">In alternativa, è possibile usare i supporti [di](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) avvio per le distribuzioni, se il supporto PXE non è abilitato.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-129">Alternatively, you can use [bootable media](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments, if PXE support isn't enabled.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a4cdb-130">Per i dispositivi Surface Pro, l'avvio dalla rete (avvio PXE) è supportato solo quando si usa un adattatore Ethernet o un'alloggiamento di espansione da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-130">For Surface Pro devices, booting from the network (PXE boot) is only supported when you use an Ethernet adapter or docking station from Microsoft.</span></span> <span data-ttu-id="a4cdb-131">Gli adattatori Ethernet di terze parti non supportano l'avvio PXE con Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-131">Third-party Ethernet adapters don't support PXE boot with Surface Pro.</span></span> <span data-ttu-id="a4cdb-132">Per altre [informazioni, vedere Adattatori Ethernet](/surface/ethernet-adapters-and-surface-device-deployment) e distribuzione di Surface.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-132">See [Ethernet adapters and Surface deployment](/surface/ethernet-adapters-and-surface-device-deployment) for more information.</span></span>

## <a name="configure-microsoft-endpoint-configuration-manager-for-operating-system-deployment"></a><span data-ttu-id="a4cdb-133">Configurare Microsoft Endpoint Configuration Manager per la distribuzione del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="a4cdb-133">Configure Microsoft Endpoint Configuration Manager for operating system deployment</span></span>

<span data-ttu-id="a4cdb-134">Questo articolo presuppone che sia già presente una distribuzione di Configuration Manager integra e non descrive in dettaglio tutti i passaggi necessari per distribuire e configurare Configuration Manager da zero.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-134">This article assumes you already have a healthy Configuration Manager deployment, and doesn't detail all the steps required to deploy and configure Configuration Manager from scratch.</span></span> <span data-ttu-id="a4cdb-135">La [documentazione e le indicazioni sulla configurazione](/configmgr/) di Microsoft Endpoint Configuration Manager sono una risorsa eccezionale. se Configuration Manager non è ancora stato distribuito, è consigliabile iniziare con queste risorse.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-135">The [documentation and the configuration guidance](/configmgr/) on the Microsoft Endpoint Configuration Manager is a great resource; we recommend you start with these resources if you haven't yet deployed Configuration Manager.</span></span>

<span data-ttu-id="a4cdb-136">Usare le istruzioni seguenti per verificare che le funzionalità di distribuzione del sistema operativo (OSD) siano configurate correttamente.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-136">Use the following instructions to verify that the operating system deployment (OSD) features are configured properly.</span></span>

### <a name="validate-and-upgrade-configuration-manager"></a><span data-ttu-id="a4cdb-137">Convalidare e aggiornare Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a4cdb-137">Validate and upgrade Configuration Manager</span></span>

1.  <span data-ttu-id="a4cdb-138">Nella console di Configuration Manager passare a **Amministrazione** \> **aggiornamenti e manutenzione.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-138">In the Configuration Manager console, go to **Administration** \> **Updates and Servicing**.</span></span>

2.  <span data-ttu-id="a4cdb-139">Controllare la build installata e gli aggiornamenti applicabili che non sono ancora stati installati.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-139">Check the installed build and applicable updates that haven't been installed yet.</span></span>

3.  <span data-ttu-id="a4cdb-140">Esaminare [il supporto per Windows 10 in Configuration Manager;](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) se è necessario aggiornare la distribuzione, selezionare l'aggiornamento da installare e quindi selezionare **Scarica**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-140">Review [Support for Windows 10 in Configuration Manager](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); if you need to upgrade your deployment, select the update you want to install, and then select **Download**.</span></span>

4.  <span data-ttu-id="a4cdb-141">Al termine del download, selezionare l'aggiornamento e quindi **selezionare Installa pacchetto di aggiornamento.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-141">After the download is complete, select the update, and then select **Install Update Pack**.</span></span>

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a><span data-ttu-id="a4cdb-142">Configurare i punti di distribuzione per supportare PXE e multicast</span><span class="sxs-lookup"><span data-stu-id="a4cdb-142">Configure distribution points to support PXE and multicast</span></span>

1.  <span data-ttu-id="a4cdb-143">Nella console di Configuration Manager passare a **Punti di** distribuzione \> **di amministrazione**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-143">In the Configuration Manager console, go to **Administration** \> **Distribution Points**.</span></span>

2.  <span data-ttu-id="a4cdb-144">Selezionare il server del punto di distribuzione che servirà la distribuzione di Microsoft Teams Rooms e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-144">Select the distribution point server that will serve the Microsoft Teams Rooms deployment, and then select **Properties**.</span></span>

3.  <span data-ttu-id="a4cdb-145">Selezionare la **scheda PXE** e verificare che le impostazioni seguenti siano abilitate:</span><span class="sxs-lookup"><span data-stu-id="a4cdb-145">Select the **PXE** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="a4cdb-146">Abilitare il supporto PXE per i client</span><span class="sxs-lookup"><span data-stu-id="a4cdb-146">Enable PXE support for clients</span></span>
    -   <span data-ttu-id="a4cdb-147">Consenti a questo punto di distribuzione di rispondere alle richieste PXE in arrivo</span><span class="sxs-lookup"><span data-stu-id="a4cdb-147">Allow this distribution point to respond to incoming PXE requests</span></span>
    -   <span data-ttu-id="a4cdb-148">Abilitare il supporto per computer sconosciuti</span><span class="sxs-lookup"><span data-stu-id="a4cdb-148">Enable unknown computer support</span></span>

4.  <span data-ttu-id="a4cdb-149">*Facoltativo:* Per abilitare il supporto multicast, selezionare la **scheda Multicast** e verificare che siano abilitate le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a4cdb-149">*Optional:* To enable multicast support, select the **Multicast** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="a4cdb-150">Abilitare il multicast per l'invio simultaneo di dati a più client</span><span class="sxs-lookup"><span data-stu-id="a4cdb-150">Enable multicast to simultaneously send data to multiple clients</span></span>
    -   <span data-ttu-id="a4cdb-151">Configurare l'intervallo di porte UDP come da raccomandazione del team di rete</span><span class="sxs-lookup"><span data-stu-id="a4cdb-151">Configure the UDP port range as per your network team's recommendation</span></span>

### <a name="configure-the-network-access-account"></a><span data-ttu-id="a4cdb-152">Configurare l'account di accesso alla rete</span><span class="sxs-lookup"><span data-stu-id="a4cdb-152">Configure the Network Access Account</span></span>

1.  <span data-ttu-id="a4cdb-153">Nella console di Configuration Manager passare a **Siti di** configurazione del sito \> **di** \> **amministrazione** e quindi selezionare il sito.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-153">In the Configuration Manager console, go to **Administration** \> **Site Configuration** \> **Sites**, and then select the site.</span></span>

2.  <span data-ttu-id="a4cdb-154">Nel gruppo **Impostazioni** selezionare **Configura distribuzione** software componenti \> **del sito.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-154">In the **Settings** group, select **Configure Site Components** \> **Software Distribution**.</span></span>

3.  <span data-ttu-id="a4cdb-155">Selezionare la **scheda Account di accesso alla** rete. Configurare uno o più account e quindi scegliere **OK.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-155">Select the **Network Access Account** tab. Set up one or more accounts, and then select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="a4cdb-156">Gli account non hanno bisogno di diritti speciali, ad eccezione dell'accesso al **computer** dalla rete direttamente nel server del punto di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-156">The accounts don't need any special rights, except for the **Access this computer from the network** right on the distribution point server.</span></span> <span data-ttu-id="a4cdb-157">Un account utente di dominio generico sarà appropriato.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-157">A generic domain user account will be appropriate.</span></span> <span data-ttu-id="a4cdb-158">Per altre informazioni, vedere [Account usati in Configuration Manager.](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)</span><span class="sxs-lookup"><span data-stu-id="a4cdb-158">For more information, see [Accounts used in Configuration Manager](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

### <a name="configure-a-boot-image"></a><span data-ttu-id="a4cdb-159">Configurare un'immagine di avvio</span><span class="sxs-lookup"><span data-stu-id="a4cdb-159">Configure a boot image</span></span>

1.  <span data-ttu-id="a4cdb-160">Nella console di Configuration Manager passare a **Immagini di avvio** del sistema \> **operativo** \> **raccolta software**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-160">In the Configuration Manager console, go to **Software Library** \> **Operating System** \> **Boot Images**.</span></span>

2.  <span data-ttu-id="a4cdb-161">Selezionare **Immagine di avvio (x64)** e quindi proprietà . </span><span class="sxs-lookup"><span data-stu-id="a4cdb-161">Select **Boot image (x64)**, and then select **Properties**.</span></span>

3.  <span data-ttu-id="a4cdb-162">Selezionare la **scheda Origine dati** e abilitare Distribuisci l'immagine di avvio dal punto di distribuzione abilitato per **PXE.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-162">Select the **Data Source** tab, and enable **Deploy this boot image from the PXE-enabled distribution point**.</span></span>

4.  <span data-ttu-id="a4cdb-163">Selezionare la **scheda Componenti facoltativi** per installare i componenti necessari:</span><span class="sxs-lookup"><span data-stu-id="a4cdb-163">Select the **Optional Components** tab to install required components:</span></span>

    1.  <span data-ttu-id="a4cdb-164">Selezionare l'icona a forma di stella e cercare **HTML (WinPE-HTA)**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-164">Select the star icon, and search for **HTML (WinPE-HTA)**</span></span>

    2.  <span data-ttu-id="a4cdb-165">Selezionare **OK per** aggiungere il supporto dell'applicazione HTML all'immagine di avvio.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-165">Select **OK** to add HTML application support in to the boot image.</span></span>

5.  <span data-ttu-id="a4cdb-166">*Facoltativo:* Per personalizzare l'esperienza di distribuzione, selezionare la **scheda Personalizzazione.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-166">*Optional:* To customize the deployment experience, select the **Customization** tab.</span></span>
    -   <span data-ttu-id="a4cdb-167">Abilitare **il supporto dei comandi (solo test)** se si vuole avere accesso a un prompt dei comandi durante la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-167">Enable **command support (testing only)** if you want to have access to a command prompt during the deployment.</span></span> <span data-ttu-id="a4cdb-168">Quando questa opzione è abilitata, è possibile avviare un prompt dei comandi selezionando **F8** in qualsiasi momento durante la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-168">When this is enabled, you can start a command prompt by selecting **F8** at any time during the deployment.</span></span>
    -   <span data-ttu-id="a4cdb-169">È anche possibile specificare un'immagine di sfondo personalizzata da visualizzare durante la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-169">You can also specify a custom background image to be displayed during the deployment.</span></span> <span data-ttu-id="a4cdb-170">Per impostare un'immagine, abilitare Specificare il file di immagine **di sfondo personalizzato (percorso UNC** e selezionare lo sfondo.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-170">To set an image, enable **Specify the custom background image file (UNC path** and select your background.</span></span>

6.  <span data-ttu-id="a4cdb-171">Quando richiesto, selezionare **Sì** e distribuire l'immagine di avvio aggiornata ai punti di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-171">When asked, select **Yes** and distribute the updated boot image to your distribution points.</span></span>

<span data-ttu-id="a4cdb-172">Per altre informazioni, vedere [Gestire le immagini di avvio con Configuration Manager.](/configmgr/osd/get-started/manage-boot-images)</span><span class="sxs-lookup"><span data-stu-id="a4cdb-172">For more information, see [Manage boot images with Configuration Manager](/configmgr/osd/get-started/manage-boot-images).</span></span>

> [!NOTE]
> <span data-ttu-id="a4cdb-173">È possibile creare un supporto USB avviabile per avviare distribuzioni basate sulla sequenza di attività di Configuration Manager per ambienti che non supportano PXE.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-173">You can create a bootable USB media to initiate Configuration Manager task sequence–based deployments for environments that have no PXE support.</span></span> <span data-ttu-id="a4cdb-174">Il supporto di avvio contiene solo l'immagine di avvio, i comandi di preavvio facoltativi e i file necessari e i file binari di Configuration Manager per supportare l'avvio in Windows PE e la connessione a Configuration Manager per il resto del processo di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-174">The bootable media contains only the boot image, optional prestart commands and their required files, and Configuration Manager binaries to support booting into Windows PE and connecting to Configuration Manager for the rest of the deployment process.</span></span> <span data-ttu-id="a4cdb-175">Per altre informazioni, vedere [Creare supporti avviabili.](/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia)</span><span class="sxs-lookup"><span data-stu-id="a4cdb-175">For more information, see [Create bootable media](/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span></span>

## <a name="create-configuration-manager-packages"></a><span data-ttu-id="a4cdb-176">Creare pacchetti di Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a4cdb-176">Create Configuration Manager packages</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4cdb-177">La versione del sistema operativo richiesta per ogni versione del programma di installazione di SRS cambia a ogni versione msi.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-177">The required operating system version for each SRS installer version changes with every MSI release.</span></span> <span data-ttu-id="a4cdb-178">Per determinare la versione migliore del sistema operativo per un determinato file MSI, eseguire lo script di configurazione della console una sola volta.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-178">To determine the best operating system version for a given MSI, run the console setup script once.</span></span> <span data-ttu-id="a4cdb-179">Per altre informazioni, vedere [Distribuire le chat room di Microsoft Teams usando Microsoft Endpoint Configuration Manager.](rooms-scale.md)</span><span class="sxs-lookup"><span data-stu-id="a4cdb-179">To learn more, see [Deploy Microsoft Teams Rooms by using Microsoft Endpoint Configuration Manager](rooms-scale.md).</span></span>

<span data-ttu-id="a4cdb-180">Configuration Manager richiede diversi pacchetti per distribuire e configurare le unità di Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-180">Configuration Manager requires a number of packages to deploy and configure the Microsoft Teams Rooms units.</span></span>

<span data-ttu-id="a4cdb-181">È necessario creare e configurare i pacchetti seguenti e quindi distribuirli ai sistemi del sito di Configuration Manager a cui è stato assegnato il ruolo di server del punto di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-181">You need to create and configure the following packages, and then distribute them to the Configuration Manager site systems that have been assigned the distribution point server role.</span></span>

| <span data-ttu-id="a4cdb-182">**Nome pacchetto**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-182">**Package name**</span></span>                     | <span data-ttu-id="a4cdb-183">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-183">**Type**</span></span>               | <span data-ttu-id="a4cdb-184">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-184">**Description**</span></span>                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| <span data-ttu-id="a4cdb-185">SRS v2 - Pacchetto di applicazioni SRS</span><span class="sxs-lookup"><span data-stu-id="a4cdb-185">SRS v2 - SRS Application Package</span></span>     | <span data-ttu-id="a4cdb-186">Pacchetto software</span><span class="sxs-lookup"><span data-stu-id="a4cdb-186">Software package</span></span>       | <span data-ttu-id="a4cdb-187">Pacchetto per il kit di distribuzione di Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="a4cdb-187">Package for the Microsoft Teams Rooms deployment kit</span></span>                                      |
| <span data-ttu-id="a4cdb-188">SRS v2 - Pacchetto Sysprep</span><span class="sxs-lookup"><span data-stu-id="a4cdb-188">SRS v2 - Sysprep Package</span></span>             | <span data-ttu-id="a4cdb-189">Pacchetto software</span><span class="sxs-lookup"><span data-stu-id="a4cdb-189">Software package</span></span>       | <span data-ttu-id="a4cdb-190">Pacchetto per il pacchetto Unattended.xml configurare le unità di Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="a4cdb-190">Package for the custom Unattended.xml to configure Microsoft Teams Rooms units</span></span>            |
| <span data-ttu-id="a4cdb-191">SRS v2 - Set-SRSComputerName pacchetto</span><span class="sxs-lookup"><span data-stu-id="a4cdb-191">SRS v2 - Set-SRSComputerName Package</span></span> | <span data-ttu-id="a4cdb-192">Pacchetto software</span><span class="sxs-lookup"><span data-stu-id="a4cdb-192">Software package</span></span>       | <span data-ttu-id="a4cdb-193">Pacchetto per l'applicazione HTML (HTA) per assegnare un nome di computer durante la distribuzione</span><span class="sxs-lookup"><span data-stu-id="a4cdb-193">Package for the HTML application (HTA) to assign a computer name during the deployment</span></span>    |
| <span data-ttu-id="a4cdb-194">SRS v2 - Configurare la configurazione di SRS</span><span class="sxs-lookup"><span data-stu-id="a4cdb-194">SRS v2 - Configure SRS Setup</span></span>         | <span data-ttu-id="a4cdb-195">Pacchetto software</span><span class="sxs-lookup"><span data-stu-id="a4cdb-195">Software package</span></span>       | <span data-ttu-id="a4cdb-196">Pacchetto per configurare la distribuzione dell'app Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="a4cdb-196">Package to configure deployment of the Microsoft Teams Rooms app</span></span>                          |
| <span data-ttu-id="a4cdb-197">SRS v2 - Pacchetto di aggiornamenti del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="a4cdb-197">SRS v2 - OS Updates Package</span></span>          | <span data-ttu-id="a4cdb-198">Pacchetto software</span><span class="sxs-lookup"><span data-stu-id="a4cdb-198">Software package</span></span>       | <span data-ttu-id="a4cdb-199">Pacchetto per distribuire gli aggiornamenti obbligatori del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="a4cdb-199">Package to deploy mandatory operating system updates</span></span>                                      |
| <span data-ttu-id="a4cdb-200">SRS v2 - Pacchetto di certificati radice</span><span class="sxs-lookup"><span data-stu-id="a4cdb-200">SRS v2 - Root Certificate Package</span></span>    | <span data-ttu-id="a4cdb-201">Pacchetto software</span><span class="sxs-lookup"><span data-stu-id="a4cdb-201">Software package</span></span>       | <span data-ttu-id="a4cdb-202">Facoltativo: pacchetto per distribuire il certificato radice (non necessario per le unità appartenenti al dominio)</span><span class="sxs-lookup"><span data-stu-id="a4cdb-202">Optional - Package to deploy the root certificate (not required for domain-joined units)</span></span>  |
| <span data-ttu-id="a4cdb-203">SRS v2 - Pacchetto Microsoft Monitoring Agent</span><span class="sxs-lookup"><span data-stu-id="a4cdb-203">SRS v2 - Microsoft Monitoring Agent Package</span></span> | <span data-ttu-id="a4cdb-204">Pacchetto software</span><span class="sxs-lookup"><span data-stu-id="a4cdb-204">Software package</span></span>       | <span data-ttu-id="a4cdb-205">Facoltativo: pacchetto per distribuire e configurare l'agente di Microsoft Operations Management Suite</span><span class="sxs-lookup"><span data-stu-id="a4cdb-205">Optional - Package to deploy and configure the Microsoft Operations Management Suite agent</span></span>|
| <span data-ttu-id="a4cdb-206">SRS v2 - Pacchetto in background WinPE</span><span class="sxs-lookup"><span data-stu-id="a4cdb-206">SRS v2 - WinPE Background Package</span></span>    | <span data-ttu-id="a4cdb-207">Pacchetto software</span><span class="sxs-lookup"><span data-stu-id="a4cdb-207">Software package</span></span>       | <span data-ttu-id="a4cdb-208">Pacchetto per l'immagine di sfondo personalizzata da usare con le immagini di avvio</span><span class="sxs-lookup"><span data-stu-id="a4cdb-208">Package for the custom background image to use with boot images</span></span>                           |
| <span data-ttu-id="a4cdb-209">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a4cdb-209">Windows 10 Enterprise</span></span>                | <span data-ttu-id="a4cdb-210">Immagine del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="a4cdb-210">Operating system image</span></span> | <span data-ttu-id="a4cdb-211">Pacchetto per il file di installazione del sistema operativo (install.wim)</span><span class="sxs-lookup"><span data-stu-id="a4cdb-211">Package for the operating system installation file (install.wim)</span></span>                          |
| <span data-ttu-id="a4cdb-212">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="a4cdb-212">Surface Pro</span></span>                          | <span data-ttu-id="a4cdb-213">Pacchetto driver</span><span class="sxs-lookup"><span data-stu-id="a4cdb-213">Driver package</span></span>         | <span data-ttu-id="a4cdb-214">Pacchetto per i driver di dispositivo e il firmware per Microsoft Surface Pro</span><span class="sxs-lookup"><span data-stu-id="a4cdb-214">Package for the device drivers and firmware for Microsoft Surface Pro</span></span>                     |
| <span data-ttu-id="a4cdb-215">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="a4cdb-215">Surface Pro 4</span></span>                        | <span data-ttu-id="a4cdb-216">Pacchetto driver</span><span class="sxs-lookup"><span data-stu-id="a4cdb-216">Driver package</span></span>         | <span data-ttu-id="a4cdb-217">Pacchetto per i driver di dispositivo e il firmware per Microsoft Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="a4cdb-217">Package for the device drivers and firmware for Microsoft Surface Pro 4</span></span>                   |

<span data-ttu-id="a4cdb-218">Per altre informazioni, vedere [Pacchetti e programmi in Configuration Manager.](/configmgr/apps/deploy-use/packages-and-programs)</span><span class="sxs-lookup"><span data-stu-id="a4cdb-218">For more information, see [Packages and programs in Configuration Manager](/configmgr/apps/deploy-use/packages-and-programs).</span></span>

### <a name="create-folders-for-the-package-source-files"></a><span data-ttu-id="a4cdb-219">Creare cartelle per i file di origine del pacchetto</span><span class="sxs-lookup"><span data-stu-id="a4cdb-219">Create folders for the package source files</span></span>

<span data-ttu-id="a4cdb-220">Configuration Manager richiede che i file di origine del pacchetto siano organizzati in una struttura di cartelle specifica quando vengono creati per la prima volta e quando vengono aggiornati.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-220">Configuration Manager requires package source files to be organized in a specific folder structure when they're first created and when they're updated.</span></span>

<span data-ttu-id="a4cdb-221">Creare la struttura di cartelle seguente nel sito di amministrazione centrale o nel sito principale di Microsoft Endpoint Configuration Manager oppure in una condivisione server in uso per ospitare i file di origine del pacchetto:</span><span class="sxs-lookup"><span data-stu-id="a4cdb-221">Create the following folder structure on the Microsoft Endpoint Configuration Manager central administration site or primary site, or on a server share you're using to host package source files:</span></span>

-   <span data-ttu-id="a4cdb-222">SRS v2 - Pacchetto Microsoft Monitoring Agent</span><span class="sxs-lookup"><span data-stu-id="a4cdb-222">SRS v2 - Microsoft Monitoring Agent Package</span></span>
-   <span data-ttu-id="a4cdb-223">SRS v2 - Pacchetto di aggiornamenti del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="a4cdb-223">SRS v2 - OS Updates Package</span></span>
-   <span data-ttu-id="a4cdb-224">SRS v2 - Pacchetto di certificati radice</span><span class="sxs-lookup"><span data-stu-id="a4cdb-224">SRS v2 - Root Certificate Package</span></span>
-   <span data-ttu-id="a4cdb-225">SRS v2 - Set-SRSComputerName pacchetto</span><span class="sxs-lookup"><span data-stu-id="a4cdb-225">SRS v2 - Set-SRSComputerName Package</span></span>
-   <span data-ttu-id="a4cdb-226">SRS v2 - Pacchetto di applicazioni SRS</span><span class="sxs-lookup"><span data-stu-id="a4cdb-226">SRS v2 - SRS Application Package</span></span>
-   <span data-ttu-id="a4cdb-227">SRS v2 - Configurare la configurazione di SRS</span><span class="sxs-lookup"><span data-stu-id="a4cdb-227">SRS v2 - Configure SRS Setup</span></span>
-   <span data-ttu-id="a4cdb-228">SRS v2 - Pacchetto Sysprep</span><span class="sxs-lookup"><span data-stu-id="a4cdb-228">SRS v2 - Sysprep Package</span></span>
-   <span data-ttu-id="a4cdb-229">Driver</span><span class="sxs-lookup"><span data-stu-id="a4cdb-229">Drivers</span></span>
    -   <span data-ttu-id="a4cdb-230">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="a4cdb-230">Surface Pro</span></span>
    -   <span data-ttu-id="a4cdb-231">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="a4cdb-231">Surface Pro 4</span></span>
-   <span data-ttu-id="a4cdb-232">Sistemi operativi</span><span class="sxs-lookup"><span data-stu-id="a4cdb-232">Operating Systems</span></span>
    -   <span data-ttu-id="a4cdb-233">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a4cdb-233">Windows 10 Enterprise</span></span>

> [!TIP]
> <span data-ttu-id="a4cdb-234">È anche possibile [scaricare](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) e usare il file ZIP che include la struttura delle cartelle per i pacchetti, gli script da usare e il modello di sequenza di attività da importare.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-234">You may also [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) and use the zip file that includes the folder structure for the packages, the scripts that you need to use, and the task sequence template, that you need to import.</span></span>

### <a name="create-the-monitoring-agent-package"></a><span data-ttu-id="a4cdb-235">Creare il pacchetto dell'agente di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="a4cdb-235">Create the Monitoring agent package</span></span>

1. <span data-ttu-id="a4cdb-236">Scaricare l'agente di monitoraggio da <https://go.microsoft.com/fwlink/?LinkId=828603> .</span><span class="sxs-lookup"><span data-stu-id="a4cdb-236">Download the Monitoring agent from <https://go.microsoft.com/fwlink/?LinkId=828603>.</span></span>

2. <span data-ttu-id="a4cdb-237">Estrarre il pacchetto nella cartella **SRS v2 - Pacchetto** di Microsoft Monitoring Agent aprendo una finestra del prompt dei comandi e immettendo **MMASetup-AMD64.exe /C:**     al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-237">Extract the package into the **SRS v2 - Microsoft Monitoring Agent Package** folder by opening a Command Prompt window and entering **MMASetup-AMD64.exe /C:**     at the command prompt.</span></span>

3. <span data-ttu-id="a4cdb-238">Nella console di Configuration Manager passare a **Pacchetti di gestione** applicazioni raccolta software e quindi selezionare Crea \>  \>  **pacchetto.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-238">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="a4cdb-239">Immettere le informazioni seguenti per creare il pacchetto:</span><span class="sxs-lookup"><span data-stu-id="a4cdb-239">Enter the following information to create the package:</span></span>

   - <span data-ttu-id="a4cdb-240">Nome<strong>: SRS v2 - Pacchetto Microsoft Monitoring Agent</strong></span><span class="sxs-lookup"><span data-stu-id="a4cdb-240">Name<strong>: SRS v2 - Microsoft Monitoring Agent Package</strong></span></span>

   - <span data-ttu-id="a4cdb-241">Produttore<strong>: Microsoft Corporation</strong></span><span class="sxs-lookup"><span data-stu-id="a4cdb-241">Manufacturer<strong>: Microsoft Corporation</strong></span></span>

   - <span data-ttu-id="a4cdb-242">Versione<strong>: 8.1.11081.0</strong> (immettere la versione del file di installazione scaricato)</span><span class="sxs-lookup"><span data-stu-id="a4cdb-242">Version<strong>: 8.1.11081.0</strong> (enter the version of the downloaded installation file)</span></span>

   - <span data-ttu-id="a4cdb-243">Selezionare la **casella di controllo** Il pacchetto contiene i file di origine, immettere il percorso della cartella **SRS v2 - Pacchetto di Microsoft Monitoring Agent** e quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-243">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Microsoft Monitoring Agent Package** folder, and then select **Next**.</span></span>

5. <span data-ttu-id="a4cdb-244">Selezionare **Non creare un programma** e quindi avanti. </span><span class="sxs-lookup"><span data-stu-id="a4cdb-244">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="a4cdb-245">Esaminare la **pagina Conferma le** impostazioni e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-245">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="a4cdb-246">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-246">Select **Close**.</span></span>

### <a name="create-the-operating-system-updates-package"></a><span data-ttu-id="a4cdb-247">Creare il pacchetto di aggiornamenti del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="a4cdb-247">Create the operating system updates package</span></span>

1. <span data-ttu-id="a4cdb-248">Nella cartella **SRS v2 - Pacchetto** aggiornamenti del sistema operativo creare un nuovo script di PowerShell denominato **Install-SRSv2-OS-Updates.ps1**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-248">In the **SRS v2 - OS Updates Package** folder, create a new PowerShell script named **Install-SRSv2-OS-Updates.ps1**.</span></span>

2. <span data-ttu-id="a4cdb-249">Copiare lo script seguente nello script **Install-SRSv2-OS-Updates.ps1.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-249">Copy the script below into the **Install-SRSv2-OS-Updates.ps1** script.</span></span> <span data-ttu-id="a4cdb-250">In alternativa, è possibile scaricare lo script Install-SRSv2-OS-Updates.ps1 da [qui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="a4cdb-250">Alternatively, you can download the Install-SRSv2-OS-Updates.ps1 script from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3. <span data-ttu-id="a4cdb-251">Scaricare i pacchetti obbligatori di Windows Update nella stessa cartella.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-251">Download the mandatory Windows Update packages into the same folder.</span></span>
   > [!NOTE]
   > <span data-ttu-id="a4cdb-252">Al momento della pubblicazione di questo articolo, era necessario [solo KB4056892.](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu)</span><span class="sxs-lookup"><span data-stu-id="a4cdb-252">At the time this article was published, only [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) was required.</span></span> <span data-ttu-id="a4cdb-253">Selezionare [Configura una console di Microsoft Teams Rooms](console.md)per verificare se sono necessari altri aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-253">Check [Configure a Microsoft Teams Rooms console](console.md), to see whether any other updates are required.</span></span>

4. <span data-ttu-id="a4cdb-254">Nella console di Configuration Manager passare a **Pacchetti di gestione** applicazioni raccolta software e quindi selezionare Crea \>  \>  **pacchetto.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-254">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

5. <span data-ttu-id="a4cdb-255">Immettere le informazioni seguenti per creare il pacchetto:</span><span class="sxs-lookup"><span data-stu-id="a4cdb-255">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="a4cdb-256">Nome: **SRS v2 – Pacchetto di aggiornamenti del sistema operativo**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-256">Name: **SRS v2 – OS Updates Package**</span></span>
   -   <span data-ttu-id="a4cdb-257">Produttore: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-257">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="a4cdb-258">Versione: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-258">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="a4cdb-259">Selezionare la **casella di controllo** Il pacchetto contiene i file di origine, immettere il percorso della cartella **SRS v2 - Pacchetto** aggiornamenti del sistema operativo e quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-259">Select the **This package contains source files** check box, enter the path to the **SRS v2 - OS Updates Package** folder, and then select **Next**.</span></span>

6. <span data-ttu-id="a4cdb-260">Selezionare **Non creare un programma** e quindi avanti. </span><span class="sxs-lookup"><span data-stu-id="a4cdb-260">Select **Do not create a program**, and then select **Next**.</span></span>

7. <span data-ttu-id="a4cdb-261">Esaminare la **pagina Conferma le** impostazioni e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-261">Review the **Confirm the settings** page, and then select **Next**.</span></span>

8. <span data-ttu-id="a4cdb-262">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-262">Select **Close**.</span></span>

### <a name="create-the-root-certificate-package-optional"></a><span data-ttu-id="a4cdb-263">Creare il pacchetto del certificato radice (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="a4cdb-263">Create the root certificate package (optional)</span></span>

<span data-ttu-id="a4cdb-264">Questo pacchetto viene creato per distribuire il certificato radice per i dispositivi che non verranno aggiunti a un dominio di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-264">You create this package to distribute the root certificate for devices that won't be joined to an Active Directory domain.</span></span> <span data-ttu-id="a4cdb-265">Creare questo pacchetto solo se si applicano entrambe le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a4cdb-265">Create this package only if both the following conditions apply:</span></span>
-   <span data-ttu-id="a4cdb-266">La distribuzione include Lync locale o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-266">Your deployment includes on-premises Lync or Skype for Business Server.</span></span>
-   <span data-ttu-id="a4cdb-267">Le unità di Microsoft Teams Rooms sono configurate per lavorare in un gruppo di lavoro invece che in un membro di dominio.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-267">Microsoft Teams Rooms units are configured to work in a workgroup instead of a domain member.</span></span>

1.  <span data-ttu-id="a4cdb-268">Copiare il certificato radice nella **cartella SRS v2 - Root Certificate Package.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-268">Copy the root certificate into the **SRS v2 – Root Certificate Package** folder.</span></span>

2.  <span data-ttu-id="a4cdb-269">Nella console di Configuration Manager passare a **Pacchetti di gestione** applicazioni raccolta software e quindi selezionare Crea \>  \>  **pacchetto.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-269">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

3.  <span data-ttu-id="a4cdb-270">Immettere le informazioni seguenti per creare il pacchetto:</span><span class="sxs-lookup"><span data-stu-id="a4cdb-270">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="a4cdb-271">Nome: **SRS v2 - Pacchetto di certificati radice**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-271">Name: **SRS v2 – Root Certificate Package**</span></span>
    -   <span data-ttu-id="a4cdb-272">Produttore: *nome dell'organizzazione*</span><span class="sxs-lookup"><span data-stu-id="a4cdb-272">Manufacturer: *Your organization's name*</span></span>
    -   <span data-ttu-id="a4cdb-273">Versione: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-273">Version: **1.0.0**</span></span>
    -   <span data-ttu-id="a4cdb-274">Selezionare la **casella di controllo** Il pacchetto contiene i file di origine, immettere il percorso della cartella **SRS v2 - Pacchetto** certificato radice e quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-274">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Root Certificate Package** folder, and then select **Next**.</span></span>

4.  <span data-ttu-id="a4cdb-275">Selezionare **Non creare un programma** e quindi avanti. </span><span class="sxs-lookup"><span data-stu-id="a4cdb-275">Select **Do not create a program**, and then select **Next**.</span></span>

5.  <span data-ttu-id="a4cdb-276">Esaminare la **pagina Conferma le** impostazioni e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-276">Review the **Confirm the settings** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="a4cdb-277">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-277">Select **Close**.</span></span>

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a><span data-ttu-id="a4cdb-278">Creare il pacchetto del kit di distribuzione di Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="a4cdb-278">Create the Microsoft Teams Rooms deployment kit package</span></span>

1.  <span data-ttu-id="a4cdb-279">Scaricare l'ultima versione del kit di distribuzione **di Microsoft Teams Rooms** da e <https://go.microsoft.com/fwlink/?linkid=851168> installarlo in una workstation.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-279">Download the latest version of the **Microsoft Teams Rooms deployment kit** from <https://go.microsoft.com/fwlink/?linkid=851168>, and install it to a workstation.</span></span>

2.  <span data-ttu-id="a4cdb-280">Copiare il contenuto **da C: \\ Programmi (x86) \\ Skype Room System Deployment Kit** nella cartella **SRS v2 - Pacchetto applicazioni SRS.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-280">Copy the content from **C:\\Program Files (x86)\\Skype Room System Deployment Kit** to the **SRS v2 - SRS Application Package** folder.</span></span>

3.  <span data-ttu-id="a4cdb-281">Nella console di Configuration Manager passare a **Pacchetti di gestione** applicazioni raccolta software e quindi selezionare Crea \>  \>  **pacchetto.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-281">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="a4cdb-282">Immettere le informazioni seguenti per creare il pacchetto:</span><span class="sxs-lookup"><span data-stu-id="a4cdb-282">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="a4cdb-283">Nome: **SRS v2 - Pacchetto dell'applicazione SRS**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-283">Name: **SRS v2 – SRS Application Package**</span></span>
    -   <span data-ttu-id="a4cdb-284">Produttore: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-284">Manufacturer: **Microsoft Corporation**</span></span>
    -   <span data-ttu-id="a4cdb-285">Versione: **3.1.104.0** (immettere la versione del file di installazione scaricato)</span><span class="sxs-lookup"><span data-stu-id="a4cdb-285">Version: **3.1.104.0** (enter the version of the downloaded installation file)</span></span>
    -   <span data-ttu-id="a4cdb-286">Selezionare la **casella di controllo** Il pacchetto contiene i file di origine, immettere il percorso della cartella **SRS v2 - Pacchetto** applicazioni SRS e quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-286">Select the **This package contains source files** check box, enter the path to the **SRS v2 – SRS Application Package** folder, and then select **Next**.</span></span>
5.  <span data-ttu-id="a4cdb-287">Selezionare **Non creare un programma** e quindi avanti. </span><span class="sxs-lookup"><span data-stu-id="a4cdb-287">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="a4cdb-288">Esaminare la **pagina Conferma le** impostazioni e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-288">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="a4cdb-289">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-289">Select **Close**.</span></span>

### <a name="create-the-computer-name-assignment-package"></a><span data-ttu-id="a4cdb-290">Creare il pacchetto di assegnazione del nome computer</span><span class="sxs-lookup"><span data-stu-id="a4cdb-290">Create the computer name assignment package</span></span>

1.  <span data-ttu-id="a4cdb-291">Nella cartella **SRS v2 - Set-SRSComputerName package** creare una nuova applicazione HTML denominata **Set-SRSComputerName.hta.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-291">In the **SRS v2 - Set-SRSComputerName Package** folder, create a new HTML application named **Set-SRSComputerName.hta** .</span></span>

2.  <span data-ttu-id="a4cdb-292">Copiare lo script seguente nel file **Set-SRSComputerName.hta.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-292">Copy the following script into the **Set-SRSComputerName.hta** file.</span></span> <span data-ttu-id="a4cdb-293">In alternativa, è possibile scaricare il file Set-SRSComputerName.hta da [qui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="a4cdb-293">Alternatively, you can download the Set-SRSComputerName.hta file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3.  <span data-ttu-id="a4cdb-294">Nella console di Configuration Manager passare a **Pacchetti di gestione** applicazioni raccolta software e quindi selezionare Crea \>  \>  **pacchetto.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-294">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="a4cdb-295">Immettere le informazioni seguenti per creare il pacchetto:</span><span class="sxs-lookup"><span data-stu-id="a4cdb-295">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="a4cdb-296">Nome: **SRS v2 - Set-SRSComputerName pacchetto**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-296">Name: **SRS v2 - Set-SRSComputerName Package**</span></span>

    -   <span data-ttu-id="a4cdb-297">Produttore: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-297">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="a4cdb-298">Versione: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-298">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="a4cdb-299">Selezionare la **casella di controllo** Il pacchetto contiene i file di origine, immettere il percorso della cartella **SRS v2 - Set-SRSComputerName Pacchetto** e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-299">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Set-SRSComputerName Package** folder, and then select **Next**.</span></span>

5.  <span data-ttu-id="a4cdb-300">Selezionare **Non creare un programma** e quindi avanti. </span><span class="sxs-lookup"><span data-stu-id="a4cdb-300">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="a4cdb-301">Esaminare la **pagina Conferma le** impostazioni e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-301">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="a4cdb-302">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-302">Select **Close**.</span></span>

### <a name="create-the-sysprep-package"></a><span data-ttu-id="a4cdb-303">Creare il pacchetto Sysprep</span><span class="sxs-lookup"><span data-stu-id="a4cdb-303">Create the Sysprep package</span></span>

1. <span data-ttu-id="a4cdb-304">Nella cartella **SRS v2 - Pacchetto Sysprep** creare un nuovo file XML denominato **Unattend.xml** .</span><span class="sxs-lookup"><span data-stu-id="a4cdb-304">In the **SRS v2 – Sysprep Package** folder, create a new XML file named **Unattend.xml** .</span></span>

2. <span data-ttu-id="a4cdb-305">Copiare il testo seguente nel **Unattend.xml** file.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-305">Copy the following text into the **Unattend.xml** file.</span></span> <span data-ttu-id="a4cdb-306">In alternativa, è possibile scaricare il file Unattend.xml file da [qui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="a4cdb-306">Alternatively, you can download the Unattend.xml file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3. <span data-ttu-id="a4cdb-307">Nella console di Configuration Manager passare a **Pacchetti di gestione** applicazioni raccolta software e quindi selezionare Crea \>  \>  **pacchetto.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-307">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="a4cdb-308">Immettere le informazioni seguenti per creare il pacchetto:</span><span class="sxs-lookup"><span data-stu-id="a4cdb-308">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="a4cdb-309">Nome: **SRS v2 - Pacchetto Sysprep**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-309">Name: **SRS v2 - Sysprep Package**</span></span>
   -   <span data-ttu-id="a4cdb-310">Produttore: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-310">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="a4cdb-311">Versione: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-311">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="a4cdb-312">Selezionare la **casella di controllo Questo** pacchetto contiene file di origine, immettere il percorso della cartella **SRS v2 - Pacchetto Sysprep** e quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-312">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Sysprep Package** folder, and then select **Next**.</span></span>
5. <span data-ttu-id="a4cdb-313">Selezionare **Non creare un programma** e quindi avanti. </span><span class="sxs-lookup"><span data-stu-id="a4cdb-313">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="a4cdb-314">Esaminare la **pagina Conferma le** impostazioni e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-314">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="a4cdb-315">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-315">Select **Close**.</span></span>

### <a name="create-the-windows-10-enterprise-package"></a><span data-ttu-id="a4cdb-316">Creare il pacchetto di Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a4cdb-316">Create the Windows 10 Enterprise package</span></span>

1.  <span data-ttu-id="a4cdb-317">Ottenere un supporto x64 windows 10 Enterprise e copiare il file **install.wim** nella cartella Sistemi operativi **\\ Windows 10 Enterprise.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-317">Obtain a Windows 10 Enterprise x64 media, and copy the **install.wim** file to the **Operating Systems\\Windows 10 Enterprise** folder.</span></span>

2.  <span data-ttu-id="a4cdb-318">Nella console di Configuration Manager passare a **Software Library** Operating Systems \> **Operating System** \> **Images** e quindi selezionare **Add Operating System Image**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-318">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**, and then select **Add Operating System Image**.</span></span>

3.  <span data-ttu-id="a4cdb-319">Specificare il percorso del file **install.wim** appena copiato e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-319">Specify the path to the **install.wim** file you just copied, and then select **Next**.</span></span>

4.  <span data-ttu-id="a4cdb-320">Aggiornare il **campo Versione** in modo che corrisponda al numero di build dell'immagine di Windows 10 Enterprise e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-320">Update the **Version** field to match the build number of the Windows 10 Enterprise image, and then select **Next**.</span></span>

5.  <span data-ttu-id="a4cdb-321">Esaminare la **pagina** Dettagli e quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-321">Review the **Details** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="a4cdb-322">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-322">Select **Close**.</span></span>

<span data-ttu-id="a4cdb-323">Per altre informazioni, vedere [Gestire le immagini del sistema operativo con Configuration Manager.](/configmgr/osd/get-started/manage-operating-system-images)</span><span class="sxs-lookup"><span data-stu-id="a4cdb-323">For more information, see [Manage OS images with Configuration Manager](/configmgr/osd/get-started/manage-operating-system-images).</span></span>

### <a name="create-surface-pro-device-driver-packages"></a><span data-ttu-id="a4cdb-324">Creare pacchetti di driver di dispositivo Surface Pro</span><span class="sxs-lookup"><span data-stu-id="a4cdb-324">Create Surface Pro device driver packages</span></span>

<span data-ttu-id="a4cdb-325">Microsoft Teams Rooms è supportato sia per Surface Pro che per Surface Pro 4.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-325">Microsoft Teams Rooms is supported for both Surface Pro and Surface Pro 4.</span></span> <span data-ttu-id="a4cdb-326">Devi creare un pacchetto driver per ogni modello di Surface Pro che hai nel tuo ambiente.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-326">You need to create a driver package for each Surface Pro model you have in your environment.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4cdb-327">I driver devono essere compatibili con la build di Windows 10 Enterprise e con la versione del kit di distribuzione di Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-327">The drivers must be compatible with the Windows 10 Enterprise build and the Microsoft Teams Rooms deployment kit version.</span></span> <span data-ttu-id="a4cdb-328">Per altre informazioni, vedere Scaricare il firmware e i driver più [recenti per i dispositivi Surface](/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) e Configurare una [console.](console.md)</span><span class="sxs-lookup"><span data-stu-id="a4cdb-328">For more information, see [Download the latest firmware and drivers for Surface devices](/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) and [Configure a console](console.md).</span></span>

1.  <span data-ttu-id="a4cdb-329">Scarica i driver e il firmware più recenti.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-329">Download the latest drivers and firmware.</span></span>
    -   <span data-ttu-id="a4cdb-330">Per Surface Pro: <https://www.microsoft.com/download/details.aspx?id=55484></span><span class="sxs-lookup"><span data-stu-id="a4cdb-330">For Surface Pro: <https://www.microsoft.com/download/details.aspx?id=55484></span></span>
    -   <span data-ttu-id="a4cdb-331">Per Surface Pro 4: <https://www.microsoft.com/download/details.aspx?id=49498></span><span class="sxs-lookup"><span data-stu-id="a4cdb-331">For Surface Pro 4: <https://www.microsoft.com/download/details.aspx?id=49498></span></span>

2.  <span data-ttu-id="a4cdb-332">Estrarre il driver e il firmware scaricati.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-332">Extract the downloaded driver and firmware.</span></span> <span data-ttu-id="a4cdb-333">Aprire una finestra del prompt dei comandi e al prompt dei comandi immettere uno dei comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a4cdb-333">Open a Command Prompt window and at the command prompt, enter one of the following commands:</span></span>
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\Drivers\Surface Pro 4"`

3.  <span data-ttu-id="a4cdb-334">Nella console di Configuration Manager passare a Driver dei sistemi operativi della raccolta **software** e quindi selezionare \>  \> Importa **driver.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-334">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Drivers**, and then select **Import Driver**.</span></span>

4.  <span data-ttu-id="a4cdb-335">Selezionare Importa tutti i driver nel percorso di rete **seguente (UNC),** selezionare la cartella di origine , ad esempio C: \\ _Sources Drivers Surface \\ Pro, quindi \\ scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-335">Select **Import all drivers in the following network path (UNC)**, select the source folder (for example, C:\\_Sources\\Drivers\\Surface Pro), and then select **Next**.</span></span>

5.  <span data-ttu-id="a4cdb-336">Nella pagina **Specificare i dettagli per i** driver importati selezionare tutti i driver elencati e quindi selezionare Abilita questi driver e consentire ai computer di **installarli.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-336">On the **Specify the details for the imported drivers** page, select all the listed drivers, and then select **Enable these drivers and allow computers to install them**.</span></span>

6.  <span data-ttu-id="a4cdb-337">Seleziona **Categorie**, crea una nuova categoria che corrisponda al modello Surface, seleziona **OK** e quindi **seleziona Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-337">Select **Categories**, create a new category that matches the Surface model, select **OK**, and then select **Next**.</span></span>

7.  <span data-ttu-id="a4cdb-338">Selezionare **Nuovo pacchetto**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-338">Select **New Package**.</span></span>

8.  <span data-ttu-id="a4cdb-339">Specificare il nome del pacchetto che corrisponde al modello Surface Pro, immettere un percorso di cartella in cui archiviare i file del pacchetto driver, selezionare **OK** e quindi **selezionare Avanti.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-339">Specify the package name that matches the Surface Pro model, enter a folder path to store the driver package files in, select **OK**, and then select **Next**.</span></span>

9.  <span data-ttu-id="a4cdb-340">Nella pagina **immagini di avvio** verificare che non sia selezionata alcuna immagine di avvio e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-340">On the **boot images** page, ensure that no boot images are selected, and then select **Next**.</span></span>

10. <span data-ttu-id="a4cdb-341">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-341">Select **Close**.</span></span>

11. <span data-ttu-id="a4cdb-342">Passare a Driver dei sistemi operativi della raccolta **software,** selezionare Crea cartella e immettere un nome di cartella corrispondente al modello di Surface Pro per cui sono stati appena importati \>  \> i driver. **\>**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-342">Go to **Software Library** \> **Operating Systems** \> **Drivers**, select **Folder \> Create Folder**, and enter a folder name that matches the Surface Pro model that you just imported the drivers for.</span></span>

12. <span data-ttu-id="a4cdb-343">Spostare tutti i driver importati nella cartella appena creata per semplificare l'esplorazione e il funzionamento.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-343">Move all the imported drivers to the newly created folder for easier navigation and operation.</span></span>

> [!NOTE]
> <span data-ttu-id="a4cdb-344">Ripetere gli stessi passaggi per altri modelli di Surface Pro che potrebbero essere disponibili.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-344">Repeat the same steps for other Surface Pro models you might have.</span></span> <span data-ttu-id="a4cdb-345">Per altre informazioni, vedere [Gestire i driver in Configuration Manager.](/configmgr/osd/get-started/manage-drivers)</span><span class="sxs-lookup"><span data-stu-id="a4cdb-345">For more information, see [Manage drivers in Configuration Manager](/configmgr/osd/get-started/manage-drivers).</span></span>

### <a name="create-microsoft-teams-rooms-configuration-package"></a><span data-ttu-id="a4cdb-346">Creare il pacchetto di configurazione di Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="a4cdb-346">Create Microsoft Teams Rooms Configuration Package</span></span>

1.  <span data-ttu-id="a4cdb-347">Nella console di Configuration Manager passare a **Pacchetti di gestione** applicazioni raccolta software e quindi selezionare Crea \>  \>  **pacchetto.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-347">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

2.  <span data-ttu-id="a4cdb-348">Immettere le informazioni seguenti per creare il pacchetto:</span><span class="sxs-lookup"><span data-stu-id="a4cdb-348">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="a4cdb-349">Nome: **SRS v2 - Configurare il pacchetto di installazione di SRS**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-349">Name: **SRS v2 - Configure SRS Setup Package**</span></span>

    -   <span data-ttu-id="a4cdb-350">Produttore: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-350">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="a4cdb-351">Versione: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-351">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="a4cdb-352">Selezionare la **casella di controllo** Il pacchetto contiene i file di origine, immettere il percorso della cartella **SRS v2 - Configurazione configurazione SRS** e quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-352">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Configure SRS Setup** folder, and then select **Next**.</span></span>

3.  <span data-ttu-id="a4cdb-353">Selezionare **Non creare un programma** e quindi avanti. </span><span class="sxs-lookup"><span data-stu-id="a4cdb-353">Select **Do not create a program**, and then select **Next**.</span></span>

4.  <span data-ttu-id="a4cdb-354">Esaminare la **pagina Conferma le** impostazioni e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-354">Review the **Confirm the settings** page, and then select **Next**.</span></span>

5.  <span data-ttu-id="a4cdb-355">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-355">Select **Close**.</span></span>



## <a name="distribute-configuration-manager-packages"></a><span data-ttu-id="a4cdb-356">Distribuire pacchetti di Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a4cdb-356">Distribute Configuration Manager packages</span></span>

<span data-ttu-id="a4cdb-357">Tutti i pacchetti devono essere distribuiti ai server a cui è stato assegnato il ruolo di punto di distribuzione nella gerarchia di Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-357">All the packages must be distributed to the servers that have been assigned the distribution point role in the Configuration Manager hierarchy.</span></span> <span data-ttu-id="a4cdb-358">Seguire le istruzioni seguenti per avviare la distribuzione dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-358">Follow the instructions below to initiate package distribution.</span></span>

1.  <span data-ttu-id="a4cdb-359">Distribuire pacchetti software.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-359">Distribute software packages.</span></span>

    1.  <span data-ttu-id="a4cdb-360">Nella console di Configuration Manager passare a **Pacchetti di gestione applicazioni** \> **raccolta** \> **software**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-360">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**.</span></span> <span data-ttu-id="a4cdb-361">Selezionare tutti i pacchetti software da distribuire e quindi **scegliere Distribuisci contenuto.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-361">Select all the software packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="a4cdb-362">Esaminare l'elenco dei pacchetti e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-362">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="a4cdb-363">Aggiungere all'elenco tutti i server dei punti di distribuzione (o gruppi di punti di distribuzione, a seconda della gerarchia di Configuration Manager) e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-363">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="a4cdb-364">Selezionare **Avanti** e quindi **chiudi.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-364">Select **Next**, and then select **Close**.</span></span>

2.  <span data-ttu-id="a4cdb-365">Distribuire pacchetti driver.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-365">Distribute driver packages.</span></span>

    1.  <span data-ttu-id="a4cdb-366">Nella console di Configuration Manager passare a **Pacchetti driver** dei sistemi operativi \> **della** \> **raccolta** software .</span><span class="sxs-lookup"><span data-stu-id="a4cdb-366">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Driver Packages**.</span></span> <span data-ttu-id="a4cdb-367">Selezionare tutti i pacchetti driver da distribuire e quindi **scegliere Distribuisci contenuto**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-367">Select all the driver packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="a4cdb-368">Esaminare l'elenco dei pacchetti e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-368">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="a4cdb-369">Aggiungere all'elenco tutti i server dei punti di distribuzione (o gruppi di punti di distribuzione, a seconda della gerarchia di Configuration Manager) e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-369">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="a4cdb-370">Selezionare **Avanti** e quindi **chiudi.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-370">Select **Next**, and then select **Close**.</span></span>

3.  <span data-ttu-id="a4cdb-371">Distribuire pacchetti del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-371">Distribute operating system packages.</span></span>

    1.  <span data-ttu-id="a4cdb-372">Nella console di Configuration Manager passare a **Software Library** Operating Systems \> **Operating System** \> **Images**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-372">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**.</span></span> <span data-ttu-id="a4cdb-373">Selezionare tutte le immagini del sistema operativo da distribuire e quindi **scegliere Distribuisci contenuto.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-373">Select all the operating system images you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="a4cdb-374">Esaminare l'elenco dei pacchetti e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-374">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="a4cdb-375">Aggiungere all'elenco tutti i server dei punti di distribuzione (o gruppi di punti di distribuzione, a seconda della gerarchia di Configuration Manager) e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-375">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="a4cdb-376">Selezionare **Avanti** e quindi **chiudi.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-376">Select **Next**, and then select **Close**.</span></span>

> [!NOTE]
> <span data-ttu-id="a4cdb-377">La distribuzione dei pacchetti può richiedere del tempo, a seconda delle dimensioni del pacchetto, della gerarchia di Configuration Manager, del numero di server dei punti di distribuzione e della larghezza di banda disponibile nella rete.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-377">Package distribution might take some time, depending on the package size, Configuration Manager hierarchy, number of distribution point servers, and the bandwidth available in your network.</span></span>
> 
> <span data-ttu-id="a4cdb-378">Tutti i pacchetti devono essere distribuiti prima di iniziare a distribuire un'unità di Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-378">All the packages must be distributed before you can start deploying a Microsoft Teams Rooms unit.</span></span>
> 
> <span data-ttu-id="a4cdb-379">Per esaminare lo stato della distribuzione dei pacchetti nella console di Configuration Manager, vedere Monitoraggio **dello** stato del contenuto \> **dello stato** della \> **distribuzione.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-379">You can review the status of your package distribution in the Configuration Manager console by going to **Monitoring** \> **Distribution Status** \> **Content Status**.</span></span>

## <a name="configuration-manager-task-sequences"></a><span data-ttu-id="a4cdb-380">Sequenze di attività di Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a4cdb-380">Configuration Manager task sequences</span></span>

<span data-ttu-id="a4cdb-381">Le sequenze di attività con Configuration Manager consentono di automatizzare i passaggi per la distribuzione di un'immagine del sistema operativo in un computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-381">You use task sequences with Configuration Manager to automate the steps for deploying an operating system image to a destination computer.</span></span> <span data-ttu-id="a4cdb-382">Per distribuire un'unità Sale di Microsoft Teams in modo automatizzato, creare una sequenza di attività che fa riferimento all'immagine di avvio usata per avviare il computer microsoft Teams Rooms di destinazione, all'immagine del sistema operativo Windows 10 Enterprise che si vuole installare e a qualsiasi altro contenuto aggiuntivo, ad esempio altre applicazioni o aggiornamenti software.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-382">To deploy a Microsoft Teams Rooms unit in an automated fashion, you create a task sequence that references the boot image used to start the destination Microsoft Teams Rooms computer, the Windows 10 Enterprise operating system image that you want to install, and any other additional content, such as other applications or software updates.</span></span>

### <a name="import-the-sample-task-sequence"></a><span data-ttu-id="a4cdb-383">Importare la sequenza di attività di esempio</span><span class="sxs-lookup"><span data-stu-id="a4cdb-383">Import the sample task sequence</span></span>

<span data-ttu-id="a4cdb-384">È possibile scaricare e importare facilmente una sequenza di attività di esempio e personalizzarla in base alle proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-384">You can download and easily import a sample task sequence and customize it to meet your needs.</span></span>

1.  <span data-ttu-id="a4cdb-385">[**Scaricare**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) la sequenza di attività di esempio e copiare il file ZIP scaricato in un percorso condiviso.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-385">[**Download**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) the sample task sequence, and copy the downloaded zip file to a shared location.</span></span>
2.  <span data-ttu-id="a4cdb-386">Nella console di Configuration Manager passare a Sequenze di attività dei sistemi operativi della raccolta **software** \>  \> e quindi selezionare Importa **sequenza di attività.** </span><span class="sxs-lookup"><span data-stu-id="a4cdb-386">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Task Sequences**, and then select **Import Task Sequence**.</span></span>

3.  <span data-ttu-id="a4cdb-387">Selezionare **Sfoglia**, passare al percorso della cartella condivisa usato nel passaggio 1, selezionare il file **Microsoft Teams Rooms Deployment (EN-US).zip** e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-387">Select **Browse**, go to the shared folder location you used in step 1, select the **Microsoft Teams Rooms Deployment (EN-US).zip** file, and then select **Next**.</span></span>

4.  <span data-ttu-id="a4cdb-388">Impostare **Azione** **su Crea nuovo** e quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-388">Set **Action** to **Create New**, and then select **Next**.</span></span>

5.  <span data-ttu-id="a4cdb-389">Confermare le impostazioni e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-389">Confirm the settings, and then select **Next**.</span></span>

6.  <span data-ttu-id="a4cdb-390">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-390">Select **Close**.</span></span>

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a><span data-ttu-id="a4cdb-391">Verificare che i pacchetti di riferimento siano collegati correttamente a ogni passaggio della sequenza di attività.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-391">Validate that the reference packages are correctly linked to each task sequence step.</span></span>

1. <span data-ttu-id="a4cdb-392">Selezionare la sequenza di attività importata e quindi scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-392">Select the imported task sequence, and then select **Edit**.</span></span>

    <span data-ttu-id="a4cdb-393">Si apre l'Editor sequenza di attività e vengono visualizzati tutti i passaggi sequenziali necessari per distribuire e configurare un'unità di Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-393">The Task Sequence Editor opens and displays each sequential step that you need to deploy and configure a Microsoft Teams Rooms unit.</span></span>

2. <span data-ttu-id="a4cdb-394">Eseguire ogni passaggio e completare gli aggiornamenti consigliati:</span><span class="sxs-lookup"><span data-stu-id="a4cdb-394">Walk through each step and complete the recommended updates:</span></span>

   1. <span data-ttu-id="a4cdb-395">**Riavvia in Windows PE:** questo passaggio riavvia e quindi avvia il computer in Windows PXE.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-395">**Restart in Windows PE**: This step restarts and then boots the computer into Windows PXE.</span></span> <span data-ttu-id="a4cdb-396">Per questo passaggio non sono necessarie modifiche.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-396">No changes are required for this step.</span></span>

   2. <span data-ttu-id="a4cdb-397">**Disco di partizione 0 - UEFI:** questo passaggio cancella la configurazione del disco e crea le partizioni in base alle impostazioni configurate.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-397">**Partition Disk 0 – UEFI**: This step wipes the disk configuration and creates partitions based on the configured settings.</span></span> <span data-ttu-id="a4cdb-398">È consigliabile non apportare modifiche a questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-398">We recommend that you not make any changes to this step.</span></span>

   3. <span data-ttu-id="a4cdb-399">**Imposta nome computer SRS:** questo passaggio include un'applicazione HTML per fornire un'interfaccia utente per impostare un nome di computer per l'unità Microsoft Teams Rooms durante la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-399">**Set SRS Computer Name**: This step includes an HTML application to provide a UI to set a computer name for the Microsoft Teams Rooms unit during the deployment.</span></span>
      -  <span data-ttu-id="a4cdb-400">Si tratta di un passaggio facoltativo, ma può essere disabilitato solo se si vuole gestire la denominazione dei computer tramite un processo alternativo.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-400">This is an optional step, but it can only be disabled if you want to manage computer naming through an alternate process.</span></span>
      -  <span data-ttu-id="a4cdb-401">Verificare che il **pacchetto SRS v2 - Set-SRSComputerName** sia selezionato.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-401">Verify that the **SRS v2 - Set-SRSComputerName** package is selected.</span></span> <span data-ttu-id="a4cdb-402">In caso contrario, passare al pacchetto e selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-402">If it isn't, browse to the package and select it.</span></span>

   4. <span data-ttu-id="a4cdb-403">**Applica sistema operativo:** questo passaggio specifica l'immagine del sistema operativo da distribuire e il file di risposte Sysprep automatico da usare.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-403">**Apply Operating System**: This step specifies the operating system image to be deployed and the unattended Sysprep answer file to use.</span></span>
      -  <span data-ttu-id="a4cdb-404">Verificare che sia selezionato il file di immagine del sistema operativo Windows 10 Enterprise corretto.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-404">Verify that the correct Windows 10 Enterprise operating system image file is selected.</span></span>
      -  <span data-ttu-id="a4cdb-405">Verificare che **l'opzione** Usa un file di risposte automatico o Sysprep per un'installazione personalizzata sia abilitata ed è selezionato il pacchetto **SRS v2 - Sysprep.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-405">Verify that **Use an unattended or Sysprep answer file for a custom installation** is enabled, and the **SRS v2 - Sysprep Package** is selected.</span></span> <span data-ttu-id="a4cdb-406">Assicurarsi inoltre che **Nome file** sia impostato su **unattend.xml**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-406">Also ensure that **File Name** is set to **unattend.xml**.</span></span>

   5. <span data-ttu-id="a4cdb-407">**Applica impostazioni di Windows:** questo passaggio raccoglie informazioni sull'installazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-407">**Apply Windows Settings**: This step gathers information about the Windows installation.</span></span>
      -  <span data-ttu-id="a4cdb-408">Fornire informazioni sulle licenze e sulla registrazione, tra cui il codice Product Key, la password dell'account dell'amministratore locale e il fuso orario (a seconda delle esigenze).</span><span class="sxs-lookup"><span data-stu-id="a4cdb-408">Provide licensing and registration information including the product key, local administrator account password, and time zone (depending on your needs).</span></span>

   6. <span data-ttu-id="a4cdb-409">**Applica impostazioni di rete:** questo passaggio consente di specificare un nome di dominio e un'unità organizzativa di Active Directory o un gruppo di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-409">**Apply Network Settings**: This step allows you to specify a workgroup or Active Directory domain name and organizational unit.</span></span>
      > [!NOTE]
      > <span data-ttu-id="a4cdb-410">Per le azioni consigliate da eseguire per la distribuzione delle unità di Microsoft Teams Rooms come membri di un dominio directory Actve, vedere Considerazioni sull'aggiunta al dominio di Sistema sala [Skype.](domain-joining-considerations.md)</span><span class="sxs-lookup"><span data-stu-id="a4cdb-410">See [Skype Room System domain joining considerations](domain-joining-considerations.md) for recommended actions you need to take in deploying Microsoft Teams Rooms units as members of an Actve Directory domain.</span></span>
   7. <span data-ttu-id="a4cdb-411">**Applica driver:** Questo passaggio e i relativi passaggi secondari vengono usati per distribuire i driver di dispositivo e il firmware applicabili in base al modello Surface Pro in uso.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-411">**Apply Drivers:** This step and its sub-steps are used to deploy applicable device drivers and firmware based on the Surface Pro model you have.</span></span> <span data-ttu-id="a4cdb-412">Aggiornare ogni passaggio per specificare il pacchetto driver pertinente associato a questa distribuzione.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-412">Update each step to specify the relevant driver package associated with this deployment.</span></span>
      -   <span data-ttu-id="a4cdb-413">Ogni pacchetto di driver è configurato per sfruttare i filtri di Strumentazione gestione Windows (WMI) per distribuire driver e firmware pertinenti in base alla creazione e al modello di Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-413">Each driver package is configured to leverage Windows Management Instrumentation (WMI) filters to deploy relevant drivers and firmware based on the Surface Pro make and model.</span></span>
      -   <span data-ttu-id="a4cdb-414">È consigliabile non modificare la configurazione di questi driver, altrimenti la distribuzione potrebbe non riuscire.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-414">We highly recommend that you not alter the configuration of these drivers, otherwise deployment might fail.</span></span>

   8. <span data-ttu-id="a4cdb-415">**Configurare Windows e Configuration Manager:** questo passaggio distribuisce e configura il client di Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-415">**Set up Windows and Configuration Manager**: This step deploys and configures the Configuration Manager client.</span></span> <span data-ttu-id="a4cdb-416">Aggiornare questo passaggio per specificare il pacchetto client predefinito di Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-416">Update this step to specify the built-in Configuration Manager Client Package.</span></span>

   9. <span data-ttu-id="a4cdb-417">**Installa certificato radice:** questo passaggio distribuisce il certificato radice per i dispositivi non appartenenti al dominio e pertanto è facoltativo e disabilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-417">**Install Root Certificate**: This step distributes the root certificate for non–domain-joined devices, and therefore is optional and disabled by default.</span></span>
      -   <span data-ttu-id="a4cdb-418">Abilitare questo passaggio se è necessario distribuire un certificato radice nelle unità di Microsoft Teams Rooms.Enable this step if you need to deploy a root certificate to the Microsoft Teams Rooms units.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-418">Enable this step if you need to deploy a root certificate to the Microsoft Teams Rooms units.</span></span>
      -   <span data-ttu-id="a4cdb-419">Se è necessario eseguire questo passaggio, verificare che siano selezionate le impostazioni **SRS v2 - Root Certificate Package** e Disable **64-bit file system redirection.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-419">If you do need to perform this step, verify that the **SRS v2 – Root Certificate Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   10. <span data-ttu-id="a4cdb-420">**Installare e configurare l'agente** di monitoraggio: questo passaggio installa la versione a 64 bit dell'agente di monitoraggio di Microsoft Azure e configura l'agente per la connessione all'area di lavoro Log Analytics.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-420">**Install and Configure Monitoring Agent**: This step installs the 64-bit version of the Microsoft Azure Monitor agent and configures the agent to connect to your Log Analytics workspace.</span></span>
       -   <span data-ttu-id="a4cdb-421">Questo passaggio è disabilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-421">This step is disabled by default.</span></span> <span data-ttu-id="a4cdb-422">Abilitare questo passaggio solo se si userà l'agente di monitoraggio per monitorare l'integrità delle unità di Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-422">Enable this step only if you're going to use the Monitoring Agent to monitor the health of your Microsoft Teams Rooms units.</span></span>
       -   <span data-ttu-id="a4cdb-423">Modificare questo passaggio e aggiornare i parametri della riga di comando per specificare l'ID area **di lavoro** e la **chiave dell'area di lavoro.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-423">Edit this step and update the command-line parameters to specify your **Workspace ID** and **Workspace Key**.</span></span>
       -   <span data-ttu-id="a4cdb-424">Per altre informazioni su come ottenere l'ID area di lavoro di Operations Management Suite e la chiave primaria, vedere Configurare i dispositivi di test per il monitoraggio di [Azure.](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring)</span><span class="sxs-lookup"><span data-stu-id="a4cdb-424">See [Configure test devices for Azure Monitoring](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) for more information about obtaining the Operations Management Suite Workspace ID and the primary key.</span></span>
       -   <span data-ttu-id="a4cdb-425">Verificare che **l'opzione SRS v2 - Pacchetto Microsoft Monitoring Agent** e Disabilita reindirizzamento del file system a **64 bit** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-425">Verify that the **SRS v2 – Microsoft Monitoring Agent Package** and **Disable 64-bit file system redirection** are selected.</span></span>
       -   <span data-ttu-id="a4cdb-426">Per altre informazioni sul monitoraggio dell'integrità della distribuzione di Microsoft Teams Rooms, vedere Pianificare la gestione delle sale di Microsoft Teams con [Monitor di Azure,](azure-monitor-plan.md)Distribuire la gestione delle sale di Microsoft Teams con [Monitor di Azure](azure-monitor-deploy.md) e Gestire i dispositivi Microsoft Teams Rooms con Monitor [di Azure.](azure-monitor-manage.md)</span><span class="sxs-lookup"><span data-stu-id="a4cdb-426">For more information about monitoring the health of your Microsoft Teams Rooms deployment, see [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md) and [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-manage.md).</span></span>

   11. <span data-ttu-id="a4cdb-427">**Copia file di configurazione SRS v2:** questo passaggio copia i file di configurazione e di configurazione necessari dal kit di distribuzione di Microsoft Teams Rooms al disco rigido locale.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-427">**Copy SRS v2 Configuration Files**: This step copies the required setup and configuration files from the Microsoft Teams Rooms deployment kit to the local hard drive.</span></span> <span data-ttu-id="a4cdb-428">Per questo passaggio non è necessaria alcuna personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-428">No customization is required for this step.</span></span>
       -   <span data-ttu-id="a4cdb-429">Verificare che siano selezionati **il pacchetto dell'applicazione SRS v2 - SRS** e il reindirizzamento del file system a **64 bit.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-429">Verify that the **SRS v2 – SRS Application Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   12. <span data-ttu-id="a4cdb-430">**Install-SRSv2-OS-Updates:** questo passaggio distribuisce tutti gli aggiornamenti obbligatori del sistema operativo necessari con la distribuzione di Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-430">**Install-SRSv2-OS-Updates**: This step deploys any mandatory operating system updates required with the Microsoft Teams Rooms deployment.</span></span> <span data-ttu-id="a4cdb-431">Eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a4cdb-431">Do the following:</span></span>
       -   <span data-ttu-id="a4cdb-432">Selezionare [Configura una console di Microsoft Teams Rooms](console.md) per vedere quali aggiornamenti sono necessari.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-432">Check [Configure a Microsoft Teams Rooms console](console.md) to see which updates are required.</span></span>
       -   <span data-ttu-id="a4cdb-433">Verificare che il **pacchetto di aggiornamenti del sistema operativo SRS v2 includa** tutti gli aggiornamenti necessari.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-433">Verify that your **SRS v2 – OS Updates Package** includes all the required updates.</span></span>
       -   <span data-ttu-id="a4cdb-434">Verificare che sia **selezionato il pacchetto SRS v2 - Aggiornamenti** del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-434">Verify that the **SRS v2 – OS Updates Package** is selected.</span></span>
       -   <span data-ttu-id="a4cdb-435">Verificare che i criteri di esecuzione di PowerShell siano impostati su **Ignora**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-435">Verify that the PowerShell execution policy is set to **Bypass**.</span></span>

   13. <span data-ttu-id="a4cdb-436">**Riavvia computer:** questo passaggio riavvia il computer dopo l'installazione degli aggiornamenti obbligatori del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-436">**Restart Computer**: This step reboots the computer after the mandatory operating system updates are installed.</span></span> <span data-ttu-id="a4cdb-437">Per questo passaggio non è necessaria alcuna personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-437">No customization is required for this step.</span></span>

   14. <span data-ttu-id="a4cdb-438">**Configurare i componenti di Windows:** questo passaggio configura le funzionalità di Windows necessarie.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-438">**Configure Windows Components**: This step configures the required Windows features.</span></span> <span data-ttu-id="a4cdb-439">Per questo passaggio non è necessaria alcuna personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-439">No customization is required for this step.</span></span>

   15. <span data-ttu-id="a4cdb-440">**Riavvia computer:** questo passaggio riavvia il computer dopo la configurazione delle funzionalità di Windows.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-440">**Restart Computer**: This step reboots the computer after the Windows features are configured.</span></span> <span data-ttu-id="a4cdb-441">Per questo passaggio non è necessaria alcuna personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-441">No customization is required for this step.</span></span>

   16. <span data-ttu-id="a4cdb-442">**Aggiungi utente Skype locale:** questo passaggio crea l'account Skype locale usato per accedere automaticamente a Windows e avviare l'applicazione Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-442">**Add Local Skype User**: This step creates the local Skype account used to automatically sign in to Windows and start the Microsoft Teams Rooms application.</span></span> <span data-ttu-id="a4cdb-443">A questo passaggio non è associato alcun pacchetto software e non è necessaria alcuna personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-443">This step doesn't have any software package associated with it, and no customization is required for it.</span></span>

   17. <span data-ttu-id="a4cdb-444">**Configurare e configurare l'applicazione SRS:** questo passaggio configura l'installazione dell'applicazione Microsoft Teams Rooms per l'avvio successivo del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-444">**Set up and configure SRS application**: This step configures the Microsoft Teams Rooms application installation for the next boot of the operating system.</span></span>
       -   <span data-ttu-id="a4cdb-445">Verificare che **l'opzione SRS v2 - Configura pacchetto** di installazione SRS e Disabilita il reindirizzamento del file system a **64 bit** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-445">Verify that the **SRS v2 – Configure SRS Setup Package** and **Disable 64-bit file system redirection** are selected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4cdb-446">È molto importante che i passaggi della sequenza di attività siano nell'ordine specificato.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-446">It is very important that the task sequence steps must be in the provided order.</span></span> <span data-ttu-id="a4cdb-447">La modifica dell'ordine dei passaggi o la configurazione di passaggi aggiuntivi potrebbero interrompere la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-447">Modifying the order of steps, or configuring additional steps might break the deployment.</span></span>
>
> <span data-ttu-id="a4cdb-448">**Il passaggio dell'applicazione SRS** deve essere l'ultimo passaggio della sequenza di attività, altrimenti la distribuzione potrebbe non riuscire.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-448">**Set up and configure SRS application** step must be the last step in the task sequence, otherwise the deployment might fail.</span></span>

### <a name="create-deployment-for-the-task-sequence"></a><span data-ttu-id="a4cdb-449">Creare la distribuzione per la sequenza di attività</span><span class="sxs-lookup"><span data-stu-id="a4cdb-449">Create deployment for the task sequence</span></span>

1. <span data-ttu-id="a4cdb-450">Selezionare la sequenza di attività e quindi scegliere **Distribuisci**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-450">Select the task sequence, and then select **Deploy**.</span></span>

2. <span data-ttu-id="a4cdb-451">Selezionare **Sfoglia per** selezionare la raccolta di destinazione per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-451">Select **Browse** to select target collection for deployment.</span></span>

3. <span data-ttu-id="a4cdb-452">Selezionare **Tutti i computer sconosciuti** e quindi scegliere **OK.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-452">Select **All Unknown Computers** and then select **OK**.</span></span>

4. <span data-ttu-id="a4cdb-453">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-453">Select **Next**.</span></span>

5. <span data-ttu-id="a4cdb-454">Selezionare **Disponibile** **nell'elenco a** discesa Scopo.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-454">Select **Available** on the **Purpose** drop down list.</span></span>

6. <span data-ttu-id="a4cdb-455">Selezionare **Solo elementi multimediali e PXE** nell'elenco Rendi disponibile **per** il seguente e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-455">Select **Only Media and PXE** in the **Make available to the following** list, and then select **Next**.</span></span>
   > [!WARNING]
   > <span data-ttu-id="a4cdb-456">È molto importante che **Scopo** sia impostato su **Disponibile**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-456">It is very important that **Purpose** is set to **Available**.</span></span> <span data-ttu-id="a4cdb-457">Assicurarsi che **l'opzione Scopo** **NON sia** impostata su **Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-457">Make sure that the **Purpose** is **NOT** set to **Required**.</span></span> <span data-ttu-id="a4cdb-458">Assicurarsi inoltre di selezionare Solo elementi multimediali **e PXE** nell'elenco **Rendi disponibile per l'elemento seguente.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-458">Also make sure that you select **Only Media and PXE** in the **Make available to the following**.</span></span>
   >
   > <span data-ttu-id="a4cdb-459">Se si impostano questi valori su un altro valore, tutti i computer potrebbero ottenere l'immagine di distribuzione di Microsoft Teams Rooms all'avvio.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-459">Setting these values to something else might cause all computers to get the Microsoft Teams Rooms deployment image when booted.</span></span>
7. <span data-ttu-id="a4cdb-460">Non specificare alcuna pianificazione e selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-460">Do not specify any schedule and select **Next**.</span></span>

8. <span data-ttu-id="a4cdb-461">Non modificare nulla all'interno **della sezione Esperienza** utente e selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-461">Do not change anything within the **User Experience** section and select **Next**.</span></span>

9. <span data-ttu-id="a4cdb-462">Non modificare nulla all'interno **della sezione Avvisi** e selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-462">Do not change anything within the **Alerts** section and select **Next**.</span></span>

10. <span data-ttu-id="a4cdb-463">Non modificare nulla all'interno **della sezione Punti di** distribuzione e selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-463">Do not change anything within the **Distribution Points** section and select **Next**.</span></span>

11. <span data-ttu-id="a4cdb-464">Confermare le impostazioni e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-464">Confirm the settings and then select **Next**.</span></span>

12. <span data-ttu-id="a4cdb-465">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-465">Select **Close**.</span></span>

<a name="validate-and-troubleshoot-the-solution"></a><span data-ttu-id="a4cdb-466">Convalidare e risolvere i problemi della soluzione</span><span class="sxs-lookup"><span data-stu-id="a4cdb-466">Validate and troubleshoot the solution</span></span>
--------------------------------------

<span data-ttu-id="a4cdb-467">Dopo aver completato le sequenze di attività di Microsoft Endpoint Configuration Manager, è necessario eseguire un'esecuzione dei test per verificare che la sequenza di attività sia in grado di distribuire e configurare le unità di Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-467">After you've completed the Microsoft Endpoint Configuration Manager task sequences, you'll need to perform a test run to validate that the task sequence can deploy and configure Microsoft Teams Rooms units.</span></span>

1.  <span data-ttu-id="a4cdb-468">Connettere il dispositivo di test alla rete cablata usando uno degli adattatori Ethernet supportati o il dock surface.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-468">Connect the test device to the wired network by using one of the supported Ethernet adapters or using the Surface dock.</span></span> <span data-ttu-id="a4cdb-469">Se la funzionalità di avvio PXE non è stata configurata per l'ambiente, è possibile usare l'immagine di avvio nell'unità flash USB creata in precedenza per eseguire l'avvio da USB e connettersi a Configuration Manager. [](/configmgr/osd/deploy-use/create-bootable-media)</span><span class="sxs-lookup"><span data-stu-id="a4cdb-469">If PXE boot functionality hasn't been configured for your environment, you can use the boot image on the USB flash drive [that you created earlier](/configmgr/osd/deploy-use/create-bootable-media) to boot from USB and connect to Configuration Manager.</span></span>

2.  <span data-ttu-id="a4cdb-470">Accedere al firmware e avviare l'avvio PXE:</span><span class="sxs-lookup"><span data-stu-id="a4cdb-470">Access the firmware and initiate PXE boot:</span></span>

    1.  <span data-ttu-id="a4cdb-471">Assicurati che il dispositivo Surface sia spento.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-471">Ensure the Surface device is powered off.</span></span>

    2.  <span data-ttu-id="a4cdb-472">Tieni premuto il **pulsante Volume** su.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-472">Press and hold the **Volume Up** button.</span></span>

    3.  <span data-ttu-id="a4cdb-473">Premere e rilasciare il **pulsante** Alimentazione.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-473">Press and release the **Power** button.</span></span>

    4.  <span data-ttu-id="a4cdb-474">Dopo l'avvio del dispositivo, rilasciare il **pulsante Volume** su.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-474">After the device begins to boot, release the **Volume Up** button.</span></span>

    5.  <span data-ttu-id="a4cdb-475">Selezionare **Configurazione di avvio**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-475">Select **Boot configuration**.</span></span>

    6.  <span data-ttu-id="a4cdb-476">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a4cdb-476">Do one of the following:</span></span>

        -   <span data-ttu-id="a4cdb-477">Selezionare **Avvio PXE** e trascinarlo all'inizio dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-477">Select **PXE boot**, and drag it to the top of the list.</span></span> <span data-ttu-id="a4cdb-478">In alternativa, è possibile scorrere rapidamente verso sinistra sulla scheda di rete per avviare immediatamente il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-478">Alternatively, you can swipe left on the network adapter to boot to the device immediately.</span></span> <span data-ttu-id="a4cdb-479">Questo non influisce sull'ordine di avvio.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-479">This won't affect the boot order.</span></span>
        -   <span data-ttu-id="a4cdb-480">Selezionare l'unità flash USB che contiene il supporto di avvio.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-480">Select the USB flash drive that holds the boot media.</span></span>

3.  <span data-ttu-id="a4cdb-481">Selezionare **Esci** e quindi selezionare **Riavvia adesso.**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-481">Select **Exit**, and then select **Restart Now**.</span></span>

4.  <span data-ttu-id="a4cdb-482">Quando richiesto, selezionare **INVIO per** il servizio di avvio di rete.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-482">When prompted, select **Enter** for network boot service.</span></span>

5.  <span data-ttu-id="a4cdb-483">Windows PE verrà caricato in memoria e verrà avviata la Creazione guidata Sequenza attività.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-483">Windows PE will load into memory, and the Task Sequence Wizard will start.</span></span> <span data-ttu-id="a4cdb-484">Selezionare **Avanti** per continuare.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-484">Select **Next** to continue.</span></span>

6.  <span data-ttu-id="a4cdb-485">Selezionare la sequenza di attività importata in precedenza e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-485">Select the task sequence that you imported earlier, and then select **Next**.</span></span>

7.  <span data-ttu-id="a4cdb-486">Dopo l'applicazione della configurazione del disco, verrà richiesto di specificare un nome di computer per il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-486">After the disk configuration is applied, you'll be prompted to specify a computer name for the device.</span></span> <span data-ttu-id="a4cdb-487">L'interfaccia utente visualizza un nome di computer consigliato in base al numero di serie del dispositivo Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-487">The user interface will display a recommended computer name based on the serial number of the Surface Pro device.</span></span> <span data-ttu-id="a4cdb-488">È possibile accettare il nome proposto o specificarne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-488">You can either accept the proposed name or specify a new one.</span></span> <span data-ttu-id="a4cdb-489">Seguire le istruzioni visualizzate nella schermata di assegnazione del nome del computer.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-489">Follow the instructions on the computer name assignment screen.</span></span> <span data-ttu-id="a4cdb-490">Quando si seleziona **Accetta**, viene avviata la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-490">When you select **Accept**, the deployment begins.</span></span>

8.  <span data-ttu-id="a4cdb-491">Il resto del processo di distribuzione è automatico e non richiede altri input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-491">The rest of the deployment process is automatic and doesn't ask for any more user input.</span></span>

9.  <span data-ttu-id="a4cdb-492">Al termine della configurazione del dispositivo da parte della sequenza di attività di distribuzione, verrà visualizzata la schermata di configurazione seguente che chiede di configurare le impostazioni dell'applicazione Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-492">After the deployment task sequence finishes configuring the device, you'll see the following configuration screen that asks you to configure the Microsoft Teams Rooms application settings.</span></span>

    ![Schermata di configurazione iniziale per l'applicazione Microsoft Teams Rooms](../media/room-systems-scale-image2.png)

10.  <span data-ttu-id="a4cdb-494">Collega Surface Pro alla console di Microsoft Teams Rooms e configura le impostazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-494">Plug the Surface Pro into the Microsoft Teams Rooms console, and configure the application settings.</span></span>

11.  <span data-ttu-id="a4cdb-495">Verificare che le funzionalità elencate nella [Guida di Microsoft Teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) funzionino sul dispositivo distribuito.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-495">Validate that the capabilities listed in [Microsoft Teams Rooms help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) are working on the deployed device.</span></span>


<span data-ttu-id="a4cdb-496">Per risolvere i problemi relativi a un'installazione non riuscita, controllare il file **SMSTS.log,** che registra tutti i passaggi eseguiti in una sequenza di attività di Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-496">To troubleshoot a failed installation, check the **SMSTS.log** file, which logs all the steps executed in a Configuration Manager task sequence.</span></span>

<span data-ttu-id="a4cdb-497">Il file SMSTS.log viene archiviato in uno dei diversi percorsi, a seconda della fase del processo di compilazione.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-497">The SMSTS.log file is stored on one of a number of paths, depending on the stage of the build process.</span></span> <span data-ttu-id="a4cdb-498">Controllare la tabella seguente per identificare il percorso del file SMSTS.log.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-498">Check the following table to identify the path to the SMSTS.log file.</span></span>


| <span data-ttu-id="a4cdb-499">**Fase di distribuzione**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-499">**Deployment phase**</span></span>                                                            | <span data-ttu-id="a4cdb-500">**Percorso del log della sequenza di attività**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-500">**Task sequence log path**</span></span>                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| <span data-ttu-id="a4cdb-501">WinPE, prima del formato HDD</span><span class="sxs-lookup"><span data-stu-id="a4cdb-501">WinPE, before HDD format</span></span>                                                        | <span data-ttu-id="a4cdb-502">X: \\ Windows \\ Temp \\ smstslog \\ smsts.log</span><span class="sxs-lookup"><span data-stu-id="a4cdb-502">X:\\Windows\\Temp\\smstslog\\smsts.log</span></span>             |
| <span data-ttu-id="a4cdb-503">WinPE, dopo il formato HDD</span><span class="sxs-lookup"><span data-stu-id="a4cdb-503">WinPE, after HDD format</span></span>                                                         | <span data-ttu-id="a4cdb-504">C: \\ _SMSTaskSequence \\ log \\ Smstslog \\ smsts.log</span><span class="sxs-lookup"><span data-stu-id="a4cdb-504">C:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="a4cdb-505">Sistema operativo distribuito prima dell'installazione dell'agente di Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a4cdb-505">Operating system deployed, before the Configuration Manager agent was installed</span></span> | <span data-ttu-id="a4cdb-506">c: \\ _SMSTaskSequence \\ log \\ Smstslog \\ smsts.log</span><span class="sxs-lookup"><span data-stu-id="a4cdb-506">c:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="a4cdb-507">Sistema operativo e agente di Configuration Manager distribuiti</span><span class="sxs-lookup"><span data-stu-id="a4cdb-507">Operating system and the Configuration Manager agent deployed</span></span>                   | <span data-ttu-id="a4cdb-508">%windir% \\ System32 \\ ccm \\ registra \\ Smstslog \\ smsts.log</span><span class="sxs-lookup"><span data-stu-id="a4cdb-508">%windir%\\System32\\ccm\\logs\\Smstslog\\smsts.log</span></span> |
| <span data-ttu-id="a4cdb-509">Esecuzione della sequenza di attività completata</span><span class="sxs-lookup"><span data-stu-id="a4cdb-509">Task sequence execution complete</span></span>                                                | <span data-ttu-id="a4cdb-510">%windir% \\ System32 \\ ccm \\ registra \\ smsts.log</span><span class="sxs-lookup"><span data-stu-id="a4cdb-510">%windir%\\System32\\ccm\\logs\\smsts.log</span></span>           |

> [!TIP]
> <span data-ttu-id="a4cdb-511">È possibile selezionare **F8** in qualsiasi momento durante la sequenza di attività per aprire una console dei comandi e quindi accedere al file SMSTS.log.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-511">You can select **F8** at any time during the task sequence to open a command console, and then get access to the SMSTS.log file.</span></span>

<span data-ttu-id="a4cdb-512">Per risolvere i problemi di avvio PXE, controllare i due file di log nel server di Configuration Manager specifici per le azioni PXE:</span><span class="sxs-lookup"><span data-stu-id="a4cdb-512">To troubleshoot PXE boot issues, check the two log files on the Configuration Manager server that are specific to PXE actions:</span></span>

-   <span data-ttu-id="a4cdb-513">**Pxecontrol.log**, che si trova nella directory dei log di installazione di Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a4cdb-513">**Pxecontrol.log**, located in the Configuration Manager installation logs directory</span></span>

-   <span data-ttu-id="a4cdb-514">**Smspxe.log**, che si trova nella directory dei log di Configuration Manager Management Point (MP)</span><span class="sxs-lookup"><span data-stu-id="a4cdb-514">**Smspxe.log**, located in Configuration Manager Management Point (MP) logs directory</span></span>

<span data-ttu-id="a4cdb-515">Per un elenco completo dei file di log che è possibile usare per risolvere ulteriormente i problemi di installazione di Configuration Manager, vedere le informazioni di riferimento sul [file di](/configmgr/core/plan-design/hierarchy/log-files)log di Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="a4cdb-515">For a complete list of the log files that you can use to further troubleshoot your Configuration Manager installation, see the Microsoft Endpoint Configuration Manager [Log file reference](/configmgr/core/plan-design/hierarchy/log-files).</span></span>

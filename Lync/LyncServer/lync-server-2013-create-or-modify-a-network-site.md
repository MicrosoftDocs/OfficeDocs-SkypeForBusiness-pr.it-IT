---
title: 'Lync Server 2013: Creare o modificare un sito di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a network site
ms:assetid: 14e24856-9996-4da4-9f31-300940bdf5aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398218(v=OCS.15)
ms:contentKeyID: 48183488
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed721a48b12a497b25d58e7ebb65ff3a91980904
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722572"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-site-in-lync-server-2013"></a><span data-ttu-id="12e11-102">Creare o modificare un sito di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12e11-102">Create or modify a network site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12e11-103">_**Argomento Ultima modifica:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="12e11-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="12e11-104">Le distribuzioni di controllo di ammissione alle chiamate (CAC), E9-1-1 e bypass multimediale si basano sulla configurazione dei *siti di rete* definiti all'interno e sempre associati a un'area geografica di rete.</span><span class="sxs-lookup"><span data-stu-id="12e11-104">Call admission control (CAC), E9-1-1, and media bypass deployments rely on the configuration of *network sites* which are defined within and always associated with a network region.</span></span> <span data-ttu-id="12e11-105">Un sito di rete rappresenta una posizione di filiale, un set di edifici o un campus.</span><span class="sxs-lookup"><span data-stu-id="12e11-105">A network site represents a branch office location, a set of buildings, or a campus.</span></span> <span data-ttu-id="12e11-106">I siti di rete rappresentano insiemi di subnet con larghezza di banda simile.</span><span class="sxs-lookup"><span data-stu-id="12e11-106">Network sites represent collections of subnets with similar bandwidth.</span></span>

<span data-ttu-id="12e11-107">Usare le procedure seguenti per creare o modificare siti di rete.</span><span class="sxs-lookup"><span data-stu-id="12e11-107">Use the following procedures to create or modify network sites.</span></span> <span data-ttu-id="12e11-108">Se ad esempio sono già stati creati siti di rete per una sola funzionalità vocale, non è necessario creare nuovi siti di rete. altre caratteristiche vocali useranno gli stessi siti.</span><span class="sxs-lookup"><span data-stu-id="12e11-108">For example, if you have already created network sites for one Voice feature, you do not need to create new network sites; other Voice features will use those same sites.</span></span> <span data-ttu-id="12e11-109">Può tuttavia essere necessario modificare una definizione di sito di rete esistente per applicare impostazioni specifiche delle caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="12e11-109">You may, however, need to modify an existing network site definition to apply feature-specific settings.</span></span> <span data-ttu-id="12e11-110">Se ad esempio è stato creato un sito di rete per E9-1-1, è necessario modificare il sito di rete durante la distribuzione del controllo di ammissione delle chiamate per applicare un profilo dei criteri di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="12e11-110">For example, if you created a network site for E9-1-1, you need to modify the network site during deployment of call admission control to apply a bandwidth policy profile.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="12e11-111">Dove esistono, è possibile trovare esempi e requisiti specifici per i siti di rete in quanto riguardano una funzionalità vocale avanzata nella documentazione di distribuzione per ogni caratteristica:</span><span class="sxs-lookup"><span data-stu-id="12e11-111">Where they exist, you can find specific examples and requirements for network sites as they pertain to an advanced Voice feature in the Deployment documentation for each feature:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="12e11-112"><A href="lync-server-2013-configure-network-sites-for-cac.md">Configurare i siti di rete per CAC in Lync Server 2013</A></span><span class="sxs-lookup"><span data-stu-id="12e11-112"><A href="lync-server-2013-configure-network-sites-for-cac.md">Configure network sites for CAC in Lync Server 2013</A></span></span></P></LI></UL>



</div>

<span data-ttu-id="12e11-113">Per informazioni dettagliate sull'uso dei siti di rete, vedere la documentazione di Lync Server Management Shell per i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="12e11-113">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="12e11-114">New-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="12e11-114">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

  - [<span data-ttu-id="12e11-115">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="12e11-115">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)

  - [<span data-ttu-id="12e11-116">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="12e11-116">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

  - [<span data-ttu-id="12e11-117">Remove-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="12e11-117">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)

<div>

## <a name="create-a-network-site"></a><span data-ttu-id="12e11-118">Creare un sito di rete</span><span class="sxs-lookup"><span data-stu-id="12e11-118">Create a Network Site</span></span>

<span data-ttu-id="12e11-119">Creare un'area di rete che può essere usata tramite il controllo di ammissione alle chiamate, E9-1-1 o bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="12e11-119">Create a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-create-a-network-site-by-using-management-shell"></a><span data-ttu-id="12e11-120">Per creare un sito di rete tramite Management Shell</span><span class="sxs-lookup"><span data-stu-id="12e11-120">To create a network site by using Management Shell</span></span>

1.  <span data-ttu-id="12e11-121">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="12e11-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="12e11-122">Eseguire il cmdlet New-CsNetworkSite per creare siti di rete:</span><span class="sxs-lookup"><span data-stu-id="12e11-122">Run the New-CsNetworkSite cmdlet to create network sites:</span></span>
    
        New-CsNetworkSite -NetworkSiteID <string>
    
    <span data-ttu-id="12e11-123">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="12e11-123">For example:</span></span>
    
        New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
    
    <span data-ttu-id="12e11-124">In questo esempio è stato creato un sito di rete denominato "Chicago" che si trova nell'area di rete "NorthAmerica".</span><span class="sxs-lookup"><span data-stu-id="12e11-124">In this example, you created a network site called “Chicago” that is in the “NorthAmerica” network region.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="12e11-125">L'area di rete NorthAmerica deve esistere già affinché il comando venga eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="12e11-125">The NorthAmerica network region must already exist for this command to run successfully.</span></span>

    
    </div>

3.  <span data-ttu-id="12e11-126">Per completare la creazione di siti di rete per la topologia, ripetere il passaggio 2 con le impostazioni per altri siti.</span><span class="sxs-lookup"><span data-stu-id="12e11-126">To finish creating network sites for your topology, repeat step 2 with settings for other sites.</span></span>

</div>

<div>

## <a name="to-create-a-network-site-by-using-lync-server-control-panel"></a><span data-ttu-id="12e11-127">Per creare un sito di rete tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="12e11-127">To create a network site by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="12e11-128">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="12e11-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="12e11-129">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="12e11-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="12e11-130">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="12e11-130">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="12e11-131">Fare clic sul pulsante di spostamento del **sito** .</span><span class="sxs-lookup"><span data-stu-id="12e11-131">Click the **Site** navigation button.</span></span>

4.  <span data-ttu-id="12e11-132">Fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="12e11-132">Click **New**.</span></span>

5.  <span data-ttu-id="12e11-133">Nella pagina **nuovo sito** fare clic su **nome** e quindi digitare un nome per il sito di rete.</span><span class="sxs-lookup"><span data-stu-id="12e11-133">On the **New Site** page, click **Name** and then type a name for the network site.</span></span>

6.  <span data-ttu-id="12e11-134">Fare clic su **area geografica**e quindi fare clic su un'area nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="12e11-134">Click **Region**, and then click a region in the list.</span></span>

7.  <span data-ttu-id="12e11-135">Facoltativamente, fare clic su **criteri di larghezza di banda**e quindi fare clic su un criterio di larghezza di banda nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="12e11-135">Optionally, click **Bandwidth policy**, and then click a bandwidth policy in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="12e11-136">I criteri di larghezza di banda sono necessari solo se si distribuisce il controllo di ammissione delle chiamate nel sito.</span><span class="sxs-lookup"><span data-stu-id="12e11-136">Bandwidth policy is required only if you deploy call admission control at the site.</span></span>

    
    </div>

8.  <span data-ttu-id="12e11-137">Facoltativamente, fare clic su **criteri posizione**e quindi fare clic su un criterio di posizione nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="12e11-137">Optionally, click **Location policy**, and then click a location policy in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="12e11-138">I criteri di posizione sono necessari solo se si distribuisce E9-1-1 nel sito.</span><span class="sxs-lookup"><span data-stu-id="12e11-138">Location policy is required only if you deploy E9-1-1 at the site.</span></span>

    
    </div>

9.  <span data-ttu-id="12e11-139">Facoltativamente, fare clic su **Descrizione**e quindi digitare altre informazioni per descrivere questo sito di rete.</span><span class="sxs-lookup"><span data-stu-id="12e11-139">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

10. <span data-ttu-id="12e11-140">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="12e11-140">Click **Commit**.</span></span>

11. <span data-ttu-id="12e11-141">Per completare la creazione di siti di rete per la topologia, ripetere i passaggi da 4 a 10 con le impostazioni per altri siti.</span><span class="sxs-lookup"><span data-stu-id="12e11-141">To finish creating network sites for your topology, repeat steps 4 through 10 with settings for other sites.</span></span>

</div>

</div>

<div>

## <a name="modify-a-network-site"></a><span data-ttu-id="12e11-142">Modificare un sito di rete</span><span class="sxs-lookup"><span data-stu-id="12e11-142">Modify a Network Site</span></span>

<span data-ttu-id="12e11-143">Modificare un'area di rete che può essere usata tramite il controllo di ammissione alle chiamate, E9-1-1 o bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="12e11-143">Modify a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-modify-a-network-site"></a><span data-ttu-id="12e11-144">Per modificare un sito di rete</span><span class="sxs-lookup"><span data-stu-id="12e11-144">To modify a network site</span></span>

1.  <span data-ttu-id="12e11-145">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="12e11-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="12e11-146">Eseguire il cmdlet Set-CsNetworkSite per modificare i siti di rete:</span><span class="sxs-lookup"><span data-stu-id="12e11-146">Run the Set-CsNetworkSite cmdlet to modify network sites:</span></span>
    
        Set-CsNetworkSite -Identity <string>
    
    <span data-ttu-id="12e11-147">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="12e11-147">For example:</span></span>
    
        Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
    
    <span data-ttu-id="12e11-148">In questo esempio, il sito denominato "Albuquerque" viene spostato nell'area di rete "NorthAmerica".</span><span class="sxs-lookup"><span data-stu-id="12e11-148">In this example, the site called “Albuquerque” is moved to the “NorthAmerica” network region.</span></span> <span data-ttu-id="12e11-149">Per modificare la configurazione del sito di rete per distribuire il controllo di ammissione alle chiamate, E9-1-1 o bypass multimediale, modificare le impostazioni del sito di rete eseguendo il cmdlet Set-CsNetworkSite rispettivamente con il parametro BWPolicyProfileID o LocationPolicy.</span><span class="sxs-lookup"><span data-stu-id="12e11-149">To modify the network site configuration to deploy call admission control, E9-1-1, or media bypass, modify the network site settings by running the Set-CsNetworkSite cmdlet with the BWPolicyProfileID or LocationPolicy parameter, respectively.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="12e11-150">Anche se il parametro BypassID esiste per il bypass multimediale, ti consigliamo vivamente di non eseguire l'override degli ID di bypass generati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="12e11-150">Although the BypassID parameter exists for media bypass, we strongly recommend that you do not override automatically generated bypass IDs.</span></span> <span data-ttu-id="12e11-151">Non è necessario specificare parametri aggiuntivi per configurare un sito di rete per il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="12e11-151">You do not need to specify additional parameters to configure a network site for media bypass.</span></span>

    
    </div>

3.  <span data-ttu-id="12e11-152">Per completare la modifica dei siti di rete per la topologia, ripetere il passaggio 2 con le impostazioni per altri siti.</span><span class="sxs-lookup"><span data-stu-id="12e11-152">To finish modifying network sites for your topology, repeat step 2 with settings for other sites.</span></span>

</div>

<div>

## <a name="to-modify-a-network-site-by-using-lync-server-control-panel"></a><span data-ttu-id="12e11-153">Per modificare un sito di rete tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="12e11-153">To modify a network site by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="12e11-154">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="12e11-154">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="12e11-155">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="12e11-155">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="12e11-156">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="12e11-156">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="12e11-157">Fare clic sul pulsante di spostamento del **sito** .</span><span class="sxs-lookup"><span data-stu-id="12e11-157">Click the **Site** navigation button.</span></span>

4.  <span data-ttu-id="12e11-158">Nella tabella fare clic sul sito di rete che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="12e11-158">In the table, click the network site that you want to modify.</span></span>

5.  <span data-ttu-id="12e11-159">Fare clic su **modifica**e quindi su **Mostra dettagli.**</span><span class="sxs-lookup"><span data-stu-id="12e11-159">Click **Edit**, and then click **Show details…**.</span></span>

6.  <span data-ttu-id="12e11-160">Nella pagina **modifica sito** modificare i valori delle impostazioni del sito di rete in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="12e11-160">On the **Edit Site** page, change the values for this network site’s settings as appropriate.</span></span>

7.  <span data-ttu-id="12e11-161">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="12e11-161">Click **Commit**.</span></span>

8.  <span data-ttu-id="12e11-162">Per completare la modifica dei siti di rete, ripetere i passaggi da 4 a 7 con le impostazioni per altri siti.</span><span class="sxs-lookup"><span data-stu-id="12e11-162">To finish modify network sites, repeat steps 4 through 7 with settings for other sites.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


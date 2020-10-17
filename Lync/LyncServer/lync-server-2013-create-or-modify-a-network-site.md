---
title: 'Lync Server 2013: creare o modificare un sito di rete'
description: 'Lync Server 2013: creare o modificare un sito di rete.'
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
ms.openlocfilehash: c4db9080f866becfcb94972787e099a69eac28c9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562202"
---
# <a name="create-or-modify-a-network-site-in-lync-server-2013"></a><span data-ttu-id="28238-103">Creare o modificare un sito di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28238-103">Create or modify a network site in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28238-104">_**Ultimo argomento modificato:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="28238-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="28238-105">Le distribuzioni del servizio Controllo di ammissione di chiamata e delle funzionalità E9-1-1 e Media Bypass sono basate sulla configurazione dei *siti di rete* che sono definiti all'interno e che sono sempre associati a un'area di rete.</span><span class="sxs-lookup"><span data-stu-id="28238-105">Call admission control (CAC), E9-1-1, and media bypass deployments rely on the configuration of *network sites* which are defined within and always associated with a network region.</span></span> <span data-ttu-id="28238-106">Un sito di rete rappresenta un percorso di succursale, un insieme di edifici o un campus.</span><span class="sxs-lookup"><span data-stu-id="28238-106">A network site represents a branch office location, a set of buildings, or a campus.</span></span> <span data-ttu-id="28238-107">I siti di rete rappresentano insiemi di subnet con larghezza di banda analoga.</span><span class="sxs-lookup"><span data-stu-id="28238-107">Network sites represent collections of subnets with similar bandwidth.</span></span>

<span data-ttu-id="28238-p102">Eseguire le procedure seguenti per creare o modificare siti di rete. Se ad esempio sono già stati creati siti di rete per una funzionalità vocale, non è necessario crearne di nuovi. Per le altre funzionalità vocali verranno utilizzati gli stessi siti. Potrebbe tuttavia essere necessario modificare la definizione di un sito di rete esistente per applicare le impostazioni specifiche di una funzionalità. Se ad esempio è stato creato un sito di rete per il servizio E9-1-1, sarà necessario modificarlo durante la distribuzione del controllo di ammissione di chiamata per applicare un profilo criteri larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="28238-p102">Use the following procedures to create or modify network sites. For example, if you have already created network sites for one Voice feature, you do not need to create new network sites; other Voice features will use those same sites. You may, however, need to modify an existing network site definition to apply feature-specific settings. For example, if you created a network site for E9-1-1, you need to modify the network site during deployment of call admission control to apply a bandwidth policy profile.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="28238-112">Nella documentazione di distribuzione relativa a ogni funzionalità sono disponibili, se applicabili, esempi e requisiti specifici per i siti di rete per una funzionalità vocale avanzata:</span><span class="sxs-lookup"><span data-stu-id="28238-112">Where they exist, you can find specific examples and requirements for network sites as they pertain to an advanced Voice feature in the Deployment documentation for each feature:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="28238-113"><A href="lync-server-2013-configure-network-sites-for-cac.md">Configurazione dei siti di rete per il servizio di controllo di ammissione in Lync Server 2013</A></span><span class="sxs-lookup"><span data-stu-id="28238-113"><A href="lync-server-2013-configure-network-sites-for-cac.md">Configure network sites for CAC in Lync Server 2013</A></span></span></P></LI></UL>



</div>

<span data-ttu-id="28238-114">Per informazioni dettagliate sull'utilizzo dei siti di rete, vedere la documentazione di Lync Server Management Shell relativa ai cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="28238-114">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="28238-115">New-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="28238-115">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

  - [<span data-ttu-id="28238-116">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="28238-116">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)

  - [<span data-ttu-id="28238-117">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="28238-117">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

  - [<span data-ttu-id="28238-118">Remove-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="28238-118">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)

<div>

## <a name="create-a-network-site"></a><span data-ttu-id="28238-119">Creare un sito di rete</span><span class="sxs-lookup"><span data-stu-id="28238-119">Create a Network Site</span></span>

<span data-ttu-id="28238-120">Creare un'area di rete utilizzabile dal controllo di ammissione di chiamata, dal servizio E9-1-1 o dal bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="28238-120">Create a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-create-a-network-site-by-using-management-shell"></a><span data-ttu-id="28238-121">Per creare un sito di rete utilizzando Management Shell</span><span class="sxs-lookup"><span data-stu-id="28238-121">To create a network site by using Management Shell</span></span>

1.  <span data-ttu-id="28238-122">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="28238-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="28238-123">Eseguire il cmdlet New-CsNetworkSite per creare i siti di rete:</span><span class="sxs-lookup"><span data-stu-id="28238-123">Run the New-CsNetworkSite cmdlet to create network sites:</span></span>
    
        New-CsNetworkSite -NetworkSiteID <string>
    
    <span data-ttu-id="28238-124">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="28238-124">For example:</span></span>
    
        New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
    
    <span data-ttu-id="28238-125">In questo esempio è stato creato un sito di rete denominato "Chicago" contenuto nell'area di rete "NorthAmerica".</span><span class="sxs-lookup"><span data-stu-id="28238-125">In this example, you created a network site called “Chicago” that is in the “NorthAmerica” network region.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="28238-126">Per il corretto funzionamento di questo comando, l'area di rete NorthAmerica deve esistere già.</span><span class="sxs-lookup"><span data-stu-id="28238-126">The NorthAmerica network region must already exist for this command to run successfully.</span></span>

    
    </div>

3.  <span data-ttu-id="28238-127">Per completare la creazione dei siti di rete per la propria topologia, ripetere il passaggio 2 con le impostazioni relative agli altri siti.</span><span class="sxs-lookup"><span data-stu-id="28238-127">To finish creating network sites for your topology, repeat step 2 with settings for other sites.</span></span>

</div>

<div>

## <a name="to-create-a-network-site-by-using-lync-server-control-panel"></a><span data-ttu-id="28238-128">Per creare un sito di rete utilizzando il Pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="28238-128">To create a network site by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="28238-129">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="28238-129">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="28238-130">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="28238-130">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="28238-131">Nella barra di spostamento sinistra fare clic su **Configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="28238-131">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="28238-132">Fare clic sul pulsante di spostamento **Sito**.</span><span class="sxs-lookup"><span data-stu-id="28238-132">Click the **Site** navigation button.</span></span>

4.  <span data-ttu-id="28238-133">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="28238-133">Click **New**.</span></span>

5.  <span data-ttu-id="28238-134">Nella pagina **Nuovo sito** fare clic su **Nome** e quindi digitare un nome per il sito di rete.</span><span class="sxs-lookup"><span data-stu-id="28238-134">On the **New Site** page, click **Name** and then type a name for the network site.</span></span>

6.  <span data-ttu-id="28238-135">Fare clic su **Area** e quindi selezionare un'area nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="28238-135">Click **Region**, and then click a region in the list.</span></span>

7.  <span data-ttu-id="28238-136">Facoltativamente, fare clic su **Criteri larghezza di banda** e quindi selezionare un criterio larghezza di banda nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="28238-136">Optionally, click **Bandwidth policy**, and then click a bandwidth policy in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="28238-137">Il criterio larghezza di banda è necessario solo se nel sito viene distribuito il controllo di ammissione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="28238-137">Bandwidth policy is required only if you deploy call admission control at the site.</span></span>

    
    </div>

8.  <span data-ttu-id="28238-138">Facoltativamente, fare clic su **Criteri percorso** e quindi selezionare un criterio percorso nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="28238-138">Optionally, click **Location policy**, and then click a location policy in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="28238-139">Il criterio percorso è necessario solo se nel sito viene distribuito il servizio E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="28238-139">Location policy is required only if you deploy E9-1-1 at the site.</span></span>

    
    </div>

9.  <span data-ttu-id="28238-140">Facoltativamente, fare clic su **Descrizione** e quindi digitare ulteriori informazioni per descrivere il sito di rete.</span><span class="sxs-lookup"><span data-stu-id="28238-140">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

10. <span data-ttu-id="28238-141">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="28238-141">Click **Commit**.</span></span>

11. <span data-ttu-id="28238-142">Per completare la creazione dei siti di rete per la propria topologia, ripetere i passaggi da 4 a 10 con le impostazioni relative agli altri siti.</span><span class="sxs-lookup"><span data-stu-id="28238-142">To finish creating network sites for your topology, repeat steps 4 through 10 with settings for other sites.</span></span>

</div>

</div>

<div>

## <a name="modify-a-network-site"></a><span data-ttu-id="28238-143">Modificare un sito di rete</span><span class="sxs-lookup"><span data-stu-id="28238-143">Modify a Network Site</span></span>

<span data-ttu-id="28238-144">Modificare un'area di rete utilizzabile dal controllo di ammissione di chiamata, dal servizio E9-1-1 o dal bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="28238-144">Modify a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-modify-a-network-site"></a><span data-ttu-id="28238-145">Per modificare un sito di rete</span><span class="sxs-lookup"><span data-stu-id="28238-145">To modify a network site</span></span>

1.  <span data-ttu-id="28238-146">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="28238-146">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="28238-147">Eseguire il cmdlet Set-CsNetworkSite per modificare i siti di rete:</span><span class="sxs-lookup"><span data-stu-id="28238-147">Run the Set-CsNetworkSite cmdlet to modify network sites:</span></span>
    
        Set-CsNetworkSite -Identity <string>
    
    <span data-ttu-id="28238-148">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="28238-148">For example:</span></span>
    
        Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
    
    <span data-ttu-id="28238-p104">In questo esempio il sito denominato "Albuquerque" viene spostato nell'area di rete "NorthAmerica". Per modificare la configurazione del sito di rete in modo da distribuire il controllo di ammissione di chiamata, il servizio E9-1-1 o il bypass multimediale, modificare le impostazioni del sito di rete eseguendo il cmdlet Set-CsNetworkSite rispettivamente con il parametro BWPolicyProfileID o LocationPolicy.</span><span class="sxs-lookup"><span data-stu-id="28238-p104">In this example, the site called “Albuquerque” is moved to the “NorthAmerica” network region. To modify the network site configuration to deploy call admission control, E9-1-1, or media bypass, modify the network site settings by running the Set-CsNetworkSite cmdlet with the BWPolicyProfileID or LocationPolicy parameter, respectively.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="28238-p105">Anche se per il bypass multimediale esiste il parametro BypassID, è consigliabile non sostituire gli ID bypass generati automaticamente. Non è necessario specificare ulteriori parametri per configurare un sito di rete per il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="28238-p105">Although the BypassID parameter exists for media bypass, we strongly recommend that you do not override automatically generated bypass IDs. You do not need to specify additional parameters to configure a network site for media bypass.</span></span>

    
    </div>

3.  <span data-ttu-id="28238-153">Per completare la modifica dei siti di rete per la propria topologia, ripetere il passaggio 2 con le impostazioni relative agli altri siti.</span><span class="sxs-lookup"><span data-stu-id="28238-153">To finish modifying network sites for your topology, repeat step 2 with settings for other sites.</span></span>

</div>

<div>

## <a name="to-modify-a-network-site-by-using-lync-server-control-panel"></a><span data-ttu-id="28238-154">Per modificare un sito di rete utilizzando il Pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="28238-154">To modify a network site by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="28238-155">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="28238-155">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="28238-156">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="28238-156">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="28238-157">Nella barra di spostamento sinistra fare clic su **Configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="28238-157">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="28238-158">Fare clic sul pulsante di spostamento **Sito**.</span><span class="sxs-lookup"><span data-stu-id="28238-158">Click the **Site** navigation button.</span></span>

4.  <span data-ttu-id="28238-159">Nella tabella fare clic sul sito di rete che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="28238-159">In the table, click the network site that you want to modify.</span></span>

5.  <span data-ttu-id="28238-160">Scegliere **Mostra dettagli** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="28238-160">Click **Edit**, and then click **Show details…**.</span></span>

6.  <span data-ttu-id="28238-161">Nella pagina **Modifica sito** modificare i valori relativi alle impostazioni del sito di rete in base alle proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="28238-161">On the **Edit Site** page, change the values for this network site’s settings as appropriate.</span></span>

7.  <span data-ttu-id="28238-162">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="28238-162">Click **Commit**.</span></span>

8.  <span data-ttu-id="28238-163">Per completare la modifica dei siti di rete, ripetere i passaggi da 4 a 7 con le impostazioni relative agli altri siti.</span><span class="sxs-lookup"><span data-stu-id="28238-163">To finish modify network sites, repeat steps 4 through 7 with settings for other sites.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


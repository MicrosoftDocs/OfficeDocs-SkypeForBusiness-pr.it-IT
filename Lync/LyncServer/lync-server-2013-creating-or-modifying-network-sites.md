---
title: 'Lync Server 2013: creazione o modifica di siti di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network sites
ms:assetid: 358aa08a-c5bc-45fc-8017-19e6202f88c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520975(v=OCS.15)
ms:contentKeyID: 48183801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 67d4fedf5931a85772e42a87fb80c382a364ae96
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135493"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-sites-in-lync-server-2013"></a><span data-ttu-id="fbd7a-102">Creazione o modifica di siti di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fbd7a-102">Creating or modifying network sites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fbd7a-103">_**Ultimo argomento modificato:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="fbd7a-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="fbd7a-104">I siti di rete sono gli uffici o le postazioni configurate in ogni area di una distribuzione del servizio Controllo di ammissione di chiamata (CAC) o del servizio per chiamate di emergenza Enhanced 9-1-1.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-104">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="fbd7a-105">È possibile utilizzare il pannello di controllo di Microsoft Lync Server 2013 per configurare i siti e associarli alle aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-105">You can use the Microsoft Lync Server 2013 Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="fbd7a-106">Ad esempio, un'area di rete per il Nord America potrebbe essere associata a siti di rete come Chicago, Redmond e Vancouver.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-106">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="fbd7a-107">Deve essere creato un sito di rete del servizio Controllo di ammissione di chiamata per ogni sito di un'organizzazione, anche se tale sito non presenta limitazioni della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-107">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="fbd7a-108">Nel pannello di controllo di Lync Server è possibile creare, modificare ed eliminare siti di rete.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-108">From the Lync Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="fbd7a-109">Seguire le procedure seguenti per creare o modificare un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-109">Use the following procedures to create or modify a network site.</span></span> <span data-ttu-id="fbd7a-110">Per informazioni dettagliate sull'eliminazione di un sito di rete esistente, vedere [eliminazione di un sito di rete esistente in Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="fbd7a-110">For details on deleting an existing network site, see [Deleting an existing network site in Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md).</span></span>

<div>

## <a name="to-create-a-network-site"></a><span data-ttu-id="fbd7a-111">Per creare un sito di rete</span><span class="sxs-lookup"><span data-stu-id="fbd7a-111">To create a network site</span></span>

1.  <span data-ttu-id="fbd7a-112">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fbd7a-113">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fbd7a-114">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fbd7a-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fbd7a-115">Nella barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Sito**.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-115">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="fbd7a-116">Nella pagina **Sito** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-116">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="fbd7a-117">In **Nuovo sito** digitare un nome per il sito nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-117">In **New Site**, type a name for this site in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fbd7a-118">I nomi dei siti devono essere univoci all'interno della distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-118">Site names must be unique within the Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="fbd7a-119">Nell'elenco a discesa **Area** selezionare un'area di rete da associare al sito.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-119">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="fbd7a-120">(Facoltativo) Se si desidera applicare limiti di larghezza di banda per le chiamate audio o video per il sito, selezionare il profilo del criterio larghezza di banda con le impostazioni appropriate nell'elenco a discesa **Criteri larghezza di banda**.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-120">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fbd7a-121">È possibile visualizzare i dettagli dei profili dei criteri larghezza di banda disponibili o creare un nuovo profilo di criterio larghezza di banda nella pagina <STRONG>Profilo criteri</STRONG> del gruppo <STRONG>Configurazione di rete</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-121">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the <STRONG>Policy Profile</STRONG> page of the <STRONG>Network Configuration</STRONG> group.</span></span> <span data-ttu-id="fbd7a-122">Per ulteriori informazioni, vedere <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">creazione o modifica di profili di criteri di larghezza di banda in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-122">For details, see <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">Creating or modifying bandwidth policy profiles in Lync Server 2013</A>.</span></span>

    
    </div>

8.  <span data-ttu-id="fbd7a-123">(Facoltativo) Se si desidera specificare impostazioni di posizione per questo sito, selezionare un criterio percorso nell'elenco a discesa **Criteri percorso**.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-123">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fbd7a-124">Il criterio percorso assegna impostazioni specifiche di Enhanced 9-1-1 (E9-1-1) e delle posizioni client al sito.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-124">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="fbd7a-125">È possibile visualizzare i dettagli dei criteri percorso disponibili o creare un nuovo criterio percorso nella pagina <STRONG>Criteri percorso</STRONG> del gruppo <STRONG>Configurazione di rete</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-125">You can view the details of the available location policies, or create a new location policy, from the <STRONG>Location Policy</STRONG> page of the <STRONG>Network Configuration</STRONG> group.</span></span> <span data-ttu-id="fbd7a-126">Per ulteriori informazioni, vedere <A href="lync-server-2013-viewing-location-policy-information.md">viewing location policy Information in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-126">For details, see <A href="lync-server-2013-viewing-location-policy-information.md">Viewing location policy information in Lync Server 2013</A>.</span></span>

    
    </div>

9.  <span data-ttu-id="fbd7a-127">(Facoltativo) Digitare un valore nel campo **Descrizione** per fornire ulteriori informazioni sul sito che non possono essere espresse utilizzando solo il nome.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-127">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="fbd7a-128">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-128">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fbd7a-129">Quando si crea un nuovo sito di rete, non si utilizza la tabella <STRONG>Subnet associate</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-129">You do not use the <STRONG>Associated Subnets</STRONG> table when you create a new network site.</span></span> <span data-ttu-id="fbd7a-130">L'associazione di una subnet a un sito viene effettuata quando si crea o si modifica la subnet.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-130">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="fbd7a-131">Per informazioni dettagliate, vedere <A href="lync-server-2013-create-or-modify-network-subnets.md">creare o modificare le subnet di rete in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-131">For details, see <A href="lync-server-2013-create-or-modify-network-subnets.md">Create or modify network subnets in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-a-network-site"></a><span data-ttu-id="fbd7a-132">Per modificare un sito di rete</span><span class="sxs-lookup"><span data-stu-id="fbd7a-132">To modify a network site</span></span>

1.  <span data-ttu-id="fbd7a-133">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-133">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fbd7a-134">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-134">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fbd7a-135">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fbd7a-135">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fbd7a-136">Nella barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Sito**.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-136">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="fbd7a-137">Nella pagina **Sito** fare clic sul sito che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-137">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="fbd7a-138">Scegliere **Mostra dettagli** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-138">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="fbd7a-p107">Nella pagina **Modifica sito** è possibile modificare la descrizione, l'area, il profilo del criterio larghezza di banda e il criterio percorso associati al sito. Per informazioni dettagliate, vedere la sezione "Per creare un sito di rete" più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-p107">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site. For details, see "To create a network site" section earlier in this topic.</span></span>

7.  <span data-ttu-id="fbd7a-141">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-141">Click **Commit**.</span></span>

<span data-ttu-id="fbd7a-p108">Non è possibile modificare la tabella **Subnet associate** in questa pagina. L'elenco di subnet associate viene fornito come riferimento per indicare quali subnet saranno interessate in caso di modifica delle impostazioni del sito.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-p108">You cannot modify the **Associated Subnets** table on this page. The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>

</div>

<div>

## <a name="to-delete-a-network-site"></a><span data-ttu-id="fbd7a-144">Per eliminare un sito di rete</span><span class="sxs-lookup"><span data-stu-id="fbd7a-144">To delete a network site</span></span>

1.  <span data-ttu-id="fbd7a-145">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fbd7a-146">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-146">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fbd7a-147">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fbd7a-147">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fbd7a-148">Nella barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Sito**.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-148">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="fbd7a-149">Nella pagina **Sito** fare clic sul sito che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-149">On the **Site** page, click the site that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fbd7a-p110">È possibile eliminare più siti contemporaneamente. A tale scopo, premere CTRL e selezionare più siti sempre tenendo premuto CTRL. In alternativa, per selezionare tutti i siti, scegliere <STRONG>Seleziona tutto</STRONG> dal menu <STRONG>Modifica</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-p110">You can delete more than one site at a time. To do this, press CTRL and select multiple sites while holding down the CTRL key. Or, to select all sites, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="fbd7a-153">Scegliere **Elimina** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-153">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="fbd7a-154">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-154">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="fbd7a-p111">Se un sito di rete è associato a una subnet di rete, non è possibile rimuoverlo. Se si tenta di rimuovere un sito associato a una subnet, verrà visualizzato un messaggio di errore. Per controllare se un sito è associato a eventuali subnet, fare clic sul sito e quindi scegliere <STRONG>Mostra dettagli</STRONG> dal menu <STRONG>Modifica</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-p111">You cannot remove a network site if it is associated with a network subnet. If you attempt to remove a site associated with a subnet you will receive an error message. To see if a site is associated with any subnets, click the site and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fbd7a-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fbd7a-158">See Also</span></span>


[<span data-ttu-id="fbd7a-159">Eliminazione di un sito di rete esistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fbd7a-159">Deleting an existing network site in Lync Server 2013</span></span>](lync-server-2013-deleting-an-existing-network-site.md)  


[<span data-ttu-id="fbd7a-160">New-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="fbd7a-160">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)  
[<span data-ttu-id="fbd7a-161">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="fbd7a-161">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)  
[<span data-ttu-id="fbd7a-162">Remove-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="fbd7a-162">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  
[<span data-ttu-id="fbd7a-163">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="fbd7a-163">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


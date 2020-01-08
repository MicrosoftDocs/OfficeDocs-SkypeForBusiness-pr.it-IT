---
title: 'Lync Server 2013: creazione o modifica di siti di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating or modifying network sites
ms:assetid: 358aa08a-c5bc-45fc-8017-19e6202f88c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520975(v=OCS.15)
ms:contentKeyID: 48183801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bb09dfcd490d47de1bbfbbde48f538e95fc64cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981419"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-sites-in-lync-server-2013"></a><span data-ttu-id="ed355-102">Creazione o modifica di siti di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed355-102">Creating or modifying network sites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed355-103">_**Argomento Ultima modifica:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="ed355-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="ed355-104">I siti di rete sono gli uffici o i percorsi configurati in ogni area geografica di un controllo di ammissione alle chiamate (CAC) o una distribuzione avanzata di 9-1-1.</span><span class="sxs-lookup"><span data-stu-id="ed355-104">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="ed355-105">È possibile usare il pannello di controllo di Microsoft Lync Server 2013 per configurare i siti e associarli alle aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="ed355-105">You can use the Microsoft Lync Server 2013 Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="ed355-106">Ad esempio, un'area di rete per il Nord America potrebbe essere associata a siti di reti come Chicago, Redmond e Vancouver.</span><span class="sxs-lookup"><span data-stu-id="ed355-106">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="ed355-107">È necessario creare un sito di rete CAC per ogni sito all'interno di un'organizzazione, anche se il sito non ha limitazioni di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="ed355-107">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="ed355-108">Dal pannello di controllo di Lync Server è possibile creare, modificare ed eliminare siti di rete.</span><span class="sxs-lookup"><span data-stu-id="ed355-108">From the Lync Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="ed355-109">Usare le procedure seguenti per creare o modificare un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="ed355-109">Use the following procedures to create or modify a network site.</span></span> <span data-ttu-id="ed355-110">Per informazioni dettagliate sull'eliminazione di un sito di rete esistente, vedere [eliminazione di un sito di rete esistente in Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="ed355-110">For details on deleting an existing network site, see [Deleting an existing network site in Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md).</span></span>

<div>

## <a name="to-create-a-network-site"></a><span data-ttu-id="ed355-111">Per creare un sito di rete</span><span class="sxs-lookup"><span data-stu-id="ed355-111">To create a network site</span></span>

1.  <span data-ttu-id="ed355-112">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="ed355-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ed355-113">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ed355-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ed355-114">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ed355-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ed355-115">Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **sito**.</span><span class="sxs-lookup"><span data-stu-id="ed355-115">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="ed355-116">Nella pagina del **sito** fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="ed355-116">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="ed355-117">In **nuovo sito**Digitare un nome per il sito nel campo **nome** .</span><span class="sxs-lookup"><span data-stu-id="ed355-117">In **New Site**, type a name for this site in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ed355-118">I nomi dei siti devono essere univoci all'interno della distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ed355-118">Site names must be unique within the Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="ed355-119">Nell'elenco a discesa **Region** selezionare un'area di rete da associare al sito.</span><span class="sxs-lookup"><span data-stu-id="ed355-119">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="ed355-120">Opzionale Se si vogliono inserire limitazioni della larghezza di banda per le chiamate audio o video a questo sito, selezionare il profilo dei criteri di larghezza di banda con le impostazioni appropriate nell'elenco a discesa **criteri di larghezza** di banda.</span><span class="sxs-lookup"><span data-stu-id="ed355-120">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ed355-121">È possibile visualizzare i dettagli dei profili di criteri di larghezza di banda disponibili oppure creare un nuovo profilo per i criteri di larghezza di banda nella pagina del <STRONG>profilo dei criteri</STRONG> del gruppo <STRONG>configurazione di rete</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="ed355-121">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the <STRONG>Policy Profile</STRONG> page of the <STRONG>Network Configuration</STRONG> group.</span></span> <span data-ttu-id="ed355-122">Per informazioni dettagliate, vedere <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">creazione o modifica di profili dei criteri di larghezza di banda in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ed355-122">For details, see <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">Creating or modifying bandwidth policy profiles in Lync Server 2013</A>.</span></span>

    
    </div>

8.  <span data-ttu-id="ed355-123">Opzionale Per specificare le impostazioni di posizione per questo sito, selezionare un criterio di posizione dall'elenco a discesa **criteri di posizione** .</span><span class="sxs-lookup"><span data-stu-id="ed355-123">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ed355-124">Il criterio posizione assegna al sito specifiche impostazioni avanzate di 9-1-1 (E9-1-1) e di posizione del client.</span><span class="sxs-lookup"><span data-stu-id="ed355-124">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="ed355-125">È possibile visualizzare i dettagli dei criteri di posizione disponibili oppure creare un nuovo criterio di posizione dalla pagina <STRONG>criteri posizione</STRONG> del gruppo Configurazione di <STRONG>rete</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="ed355-125">You can view the details of the available location policies, or create a new location policy, from the <STRONG>Location Policy</STRONG> page of the <STRONG>Network Configuration</STRONG> group.</span></span> <span data-ttu-id="ed355-126">Per informazioni dettagliate, vedere <A href="lync-server-2013-viewing-location-policy-information.md">visualizzazione delle informazioni sui criteri di posizione in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ed355-126">For details, see <A href="lync-server-2013-viewing-location-policy-information.md">Viewing location policy information in Lync Server 2013</A>.</span></span>

    
    </div>

9.  <span data-ttu-id="ed355-127">Opzionale Digitare un valore nel campo **Description** per ottenere altre informazioni su questo sito che non possono essere espresse solo dal nome.</span><span class="sxs-lookup"><span data-stu-id="ed355-127">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="ed355-128">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="ed355-128">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ed355-129">Quando si crea un nuovo sito di rete, non si usa la tabella <STRONG>subnet associata</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="ed355-129">You do not use the <STRONG>Associated Subnets</STRONG> table when you create a new network site.</span></span> <span data-ttu-id="ed355-130">Si associa una subnet a un sito quando si crea o si modifica la subnet.</span><span class="sxs-lookup"><span data-stu-id="ed355-130">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="ed355-131">Per informazioni dettagliate, vedere <A href="lync-server-2013-create-or-modify-network-subnets.md">creare o modificare subnet di rete in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ed355-131">For details, see <A href="lync-server-2013-create-or-modify-network-subnets.md">Create or modify network subnets in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-a-network-site"></a><span data-ttu-id="ed355-132">Per modificare un sito di rete</span><span class="sxs-lookup"><span data-stu-id="ed355-132">To modify a network site</span></span>

1.  <span data-ttu-id="ed355-133">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="ed355-133">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ed355-134">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ed355-134">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ed355-135">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ed355-135">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ed355-136">Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **sito**.</span><span class="sxs-lookup"><span data-stu-id="ed355-136">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="ed355-137">Nella pagina del **sito** fare clic sul sito che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="ed355-137">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="ed355-138">Nel menu **modifica** fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="ed355-138">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="ed355-139">Nella pagina **modifica sito** è possibile modificare la descrizione, l'area geografica, il profilo dei criteri di larghezza di banda e i criteri di posizione associati al sito.</span><span class="sxs-lookup"><span data-stu-id="ed355-139">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site.</span></span> <span data-ttu-id="ed355-140">Per informazioni dettagliate, vedere la sezione "per creare un sito di rete" più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="ed355-140">For details, see "To create a network site" section earlier in this topic.</span></span>

7.  <span data-ttu-id="ed355-141">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="ed355-141">Click **Commit**.</span></span>

<span data-ttu-id="ed355-142">Non è possibile modificare la tabella **subnet associata** in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="ed355-142">You cannot modify the **Associated Subnets** table on this page.</span></span> <span data-ttu-id="ed355-143">L'elenco delle subnet associate viene fornito come riferimento in modo da essere a conoscenza delle subnet che verranno modificate quando si modificano le impostazioni del sito.</span><span class="sxs-lookup"><span data-stu-id="ed355-143">The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>

</div>

<div>

## <a name="to-delete-a-network-site"></a><span data-ttu-id="ed355-144">Per eliminare un sito di rete</span><span class="sxs-lookup"><span data-stu-id="ed355-144">To delete a network site</span></span>

1.  <span data-ttu-id="ed355-145">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="ed355-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ed355-146">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ed355-146">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ed355-147">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ed355-147">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ed355-148">Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **sito**.</span><span class="sxs-lookup"><span data-stu-id="ed355-148">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="ed355-149">Nella pagina del **sito** fare clic sul sito che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="ed355-149">On the **Site** page, click the site that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ed355-150">È possibile eliminare più di un sito alla volta.</span><span class="sxs-lookup"><span data-stu-id="ed355-150">You can delete more than one site at a time.</span></span> <span data-ttu-id="ed355-151">Per eseguire questa operazione, premere CTRL e selezionare più siti tenendo premuto il tasto CTRL.</span><span class="sxs-lookup"><span data-stu-id="ed355-151">To do this, press CTRL and select multiple sites while holding down the CTRL key.</span></span> <span data-ttu-id="ed355-152">In alternativa, per selezionare tutti i siti, fare clic su <STRONG>Seleziona tutto</STRONG> dal menu <STRONG>modifica</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="ed355-152">Or, to select all sites, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="ed355-153">Scegliere **Elimina**dal menu **modifica** .</span><span class="sxs-lookup"><span data-stu-id="ed355-153">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="ed355-154">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ed355-154">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="ed355-155">Non è possibile rimuovere un sito di rete se associato a una subnet di rete.</span><span class="sxs-lookup"><span data-stu-id="ed355-155">You cannot remove a network site if it is associated with a network subnet.</span></span> <span data-ttu-id="ed355-156">Se si tenta di rimuovere un sito associato a una subnet, viene visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="ed355-156">If you attempt to remove a site associated with a subnet you will receive an error message.</span></span> <span data-ttu-id="ed355-157">Per verificare se un sito è associato a qualsiasi subnet, fare clic sul sito e quindi su <STRONG>Mostra dettagli</STRONG> dal menu <STRONG>modifica</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="ed355-157">To see if a site is associated with any subnets, click the site and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ed355-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed355-158">See Also</span></span>


[<span data-ttu-id="ed355-159">Eliminazione di un sito di rete esistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed355-159">Deleting an existing network site in Lync Server 2013</span></span>](lync-server-2013-deleting-an-existing-network-site.md)  


[<span data-ttu-id="ed355-160">New-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="ed355-160">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)  
[<span data-ttu-id="ed355-161">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="ed355-161">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)  
[<span data-ttu-id="ed355-162">Remove-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="ed355-162">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  
[<span data-ttu-id="ed355-163">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="ed355-163">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


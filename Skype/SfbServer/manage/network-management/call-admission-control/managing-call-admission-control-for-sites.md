---
title: Gestione del controllo dell'ammissione delle chiamate per i siti
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: I siti di rete sono gli uffici o le posizioni all'interno di ogni area di rete delle distribuzioni di controllo di ammissione di chiamata (CAC), E9-1-1 e bypass multimediale.
ms.openlocfilehash: a90781eae38d92d560dd1bf34db3b6918e8aeaf5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188582"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a><span data-ttu-id="f6666-103">Gestione del controllo dell'ammissione delle chiamate per i siti in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f6666-103">Managing call admission control for sites in Skype for Business Server</span></span>

<span data-ttu-id="f6666-104">I siti di rete sono gli uffici o le posizioni all'interno di ogni area di rete delle distribuzioni di controllo di ammissione di chiamata (CAC), E9-1-1 e bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="f6666-104">Network sites are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments.</span></span> <span data-ttu-id="f6666-105">Usare le procedure descritte in questo articolo per configurare il controllo di ammissione delle chiamate per i siti di rete.</span><span class="sxs-lookup"><span data-stu-id="f6666-105">Use the procedures in this article to configure call admission control for network sites.</span></span>

## <a name="configure-network-site-links"></a><span data-ttu-id="f6666-106">Configurare i collegamenti ai siti di rete</span><span class="sxs-lookup"><span data-stu-id="f6666-106">Configure network site links</span></span>

<span data-ttu-id="f6666-107">All'interno di una configurazione di controllo di ammissione chiamata (CAC), è possibile creare criteri intersito di rete che definiscono le limitazioni della larghezza di banda tra i siti direttamente collegati.</span><span class="sxs-lookup"><span data-stu-id="f6666-107">Within a call admission control (CAC) configuration, you can create network inter-site policies that define bandwidth limitations between sites that are directly linked.</span></span> <span data-ttu-id="f6666-108">Quando i siti di rete condividono un collegamento diretto, è possibile definire limitazioni della larghezza di banda per le connessioni audio e video tra questi due siti.</span><span class="sxs-lookup"><span data-stu-id="f6666-108">When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.</span></span> <span data-ttu-id="f6666-109">Non è possibile usare il pannello di controllo di Skype for Business Server per configurare i criteri del sito di rete, questo può essere eseguito solo usando i cmdlet di Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f6666-109">You cannot use the Skype for Business Server Control Panel to configure network site policies, this can be done only by using cmdlets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="f6666-110">È possibile creare, modificare e rimuovere un collegamento al sito di rete (noto anche come criterio intersito di rete) da Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f6666-110">You can create, modify, and remove a network site link (also known as a network inter-site policy) from the Skype for Business Server Management Shell.</span></span>

### <a name="to-create-a-network-site-link"></a><span data-ttu-id="f6666-111">Per creare un collegamento al sito di rete</span><span class="sxs-lookup"><span data-stu-id="f6666-111">To create a network site link</span></span>

1.  <span data-ttu-id="f6666-112">Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari.</span><span class="sxs-lookup"><span data-stu-id="f6666-112">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="f6666-113">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business**server e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f6666-113">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="f6666-114">Dal prompt dei comandi digitare il comando seguente, sostituendo i valori validi per la configurazione:</span><span class="sxs-lookup"><span data-stu-id="f6666-114">From the command prompt, type the following command, substituting values that are valid for your configuration:</span></span>
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    <span data-ttu-id="f6666-115">Questo esempio crea un nuovo collegamento di sito di rete\_denominato Reno Portland che imposta le limitazioni della larghezza di banda tra i siti di rete Reno e Portland.</span><span class="sxs-lookup"><span data-stu-id="f6666-115">This example creates a new network site link named Reno\_Portland that sets bandwidth limitations between the Reno and Portland network sites.</span></span> <span data-ttu-id="f6666-116">I siti di rete e il profilo dei criteri di larghezza di banda devono già esistere prima di eseguire questo comando.</span><span class="sxs-lookup"><span data-stu-id="f6666-116">The network sites and the bandwidth policy profile must already exist before running this command.</span></span>

<span data-ttu-id="f6666-117">Per una descrizione dettagliata dei parametri, vedere [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy).</span><span class="sxs-lookup"><span data-stu-id="f6666-117">For detailed parameter descriptions, see [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy).</span></span> <span data-ttu-id="f6666-118">Per recuperare un elenco di profili dei criteri di larghezza di banda che possono essere applicati al collegamento al sito di rete, chiama il cmdlet **Get-CsNetworkBandwidthPolicyProfile** .</span><span class="sxs-lookup"><span data-stu-id="f6666-118">To retrieve a list of bandwidth policy profiles that can be applied to the network site link, call the **Get-CsNetworkBandwidthPolicyProfile** cmdlet.</span></span> <span data-ttu-id="f6666-119">Per informazioni dettagliate, vedere [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span><span class="sxs-lookup"><span data-stu-id="f6666-119">For details, see [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span></span>

### <a name="to-modify-a-network-site-link"></a><span data-ttu-id="f6666-120">Per modificare un collegamento al sito di rete</span><span class="sxs-lookup"><span data-stu-id="f6666-120">To modify a network site link</span></span>

1.  <span data-ttu-id="f6666-121">Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari.</span><span class="sxs-lookup"><span data-stu-id="f6666-121">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="f6666-122">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business**server e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f6666-122">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="f6666-123">Utilizzare il cmdlet **set-CsNetworkInterSitePolicy** per modificare le proprietà di un collegamento al sito di rete specifico.</span><span class="sxs-lookup"><span data-stu-id="f6666-123">Use the **Set-CsNetworkInterSitePolicy** cmdlet to modify the properties of a given network site link.</span></span> <span data-ttu-id="f6666-124">È possibile modificare uno o entrambi i siti connessi e modificare il profilo dei criteri di larghezza di banda associato al collegamento.</span><span class="sxs-lookup"><span data-stu-id="f6666-124">You can modify either (or both) or the connected sites, and you can modify the bandwidth policy profile associated with the link.</span></span> <span data-ttu-id="f6666-125">Ecco un esempio di modifica del profilo dei criteri di larghezza di banda di un collegamento\_di sito denominato Reno Portland:</span><span class="sxs-lookup"><span data-stu-id="f6666-125">Here is an example of modifying the bandwidth policy profile of a site link named Reno\_Portland:</span></span>
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

<span data-ttu-id="f6666-126">Per descrizioni dettagliate sui parametri, vedere [set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).</span><span class="sxs-lookup"><span data-stu-id="f6666-126">For detailed parameter descriptions, see [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).</span></span>


### <a name="to-delete-a-network-site-link"></a><span data-ttu-id="f6666-127">Per eliminare un collegamento al sito di rete</span><span class="sxs-lookup"><span data-stu-id="f6666-127">To delete a network site link</span></span>

1.  <span data-ttu-id="f6666-128">Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari.</span><span class="sxs-lookup"><span data-stu-id="f6666-128">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="f6666-129">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business**server e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f6666-129">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="f6666-130">Utilizzare il cmdlet **Remove-CsNetworkInterSitePolicy** per rimuovere un collegamento al sito di rete.</span><span class="sxs-lookup"><span data-stu-id="f6666-130">Use the **Remove-CsNetworkInterSitePolicy** cmdlet to remove a network site link.</span></span> <span data-ttu-id="f6666-131">L'esempio seguente elimina il collegamento\_al sito network di Reno Portland:</span><span class="sxs-lookup"><span data-stu-id="f6666-131">The following example deletes the Reno\_Portland network site link:</span></span>
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

<span data-ttu-id="f6666-132">Per descrizioni dettagliate dei parametri, vedere [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).</span><span class="sxs-lookup"><span data-stu-id="f6666-132">For detailed parameter descriptions, see [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).</span></span>


## <a name="view-network-site-information"></a><span data-ttu-id="f6666-133">Visualizzare le informazioni sul sito di rete</span><span class="sxs-lookup"><span data-stu-id="f6666-133">View network site information</span></span>

<span data-ttu-id="f6666-134">I siti di rete sono gli uffici o i percorsi configurati in ogni area geografica di un controllo di ammissione alle chiamate (CAC) o una distribuzione avanzata di 9-1-1.</span><span class="sxs-lookup"><span data-stu-id="f6666-134">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="f6666-135">È possibile visualizzare le informazioni sul sito di rete sia nel pannello di controllo di Skype for Business Server che in Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f6666-135">You can view network site information in either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="f6666-136">Per visualizzare le informazioni sul sito di rete nel pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f6666-136">To view network site information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="f6666-137">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="f6666-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f6666-138">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f6666-138">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f6666-139">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su **sito**.</span><span class="sxs-lookup"><span data-stu-id="f6666-139">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="f6666-140">Nella pagina del **sito** fare clic sul sito che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="f6666-140">On the **Site** page, click the site that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="f6666-141">È possibile visualizzare le informazioni solo per un sito alla volta.</span><span class="sxs-lookup"><span data-stu-id="f6666-141">You can only view information for one site at a time.</span></span>

5.  <span data-ttu-id="f6666-142">Nel menu **modifica** fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="f6666-142">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f6666-143">Visualizzazione delle informazioni sul sito di rete tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f6666-143">Viewing network site information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="f6666-144">È possibile visualizzare le informazioni sul sito di rete usando Windows PowerShell e il cmdlet Get-CsNetworkSite.</span><span class="sxs-lookup"><span data-stu-id="f6666-144">You can view network site information by using Windows PowerShell and the Get-CsNetworkSite cmdlet.</span></span> <span data-ttu-id="f6666-145">Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f6666-145">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-site-information"></a><span data-ttu-id="f6666-146">Per visualizzare le informazioni sul sito di rete</span><span class="sxs-lookup"><span data-stu-id="f6666-146">To view network site information</span></span>

  - <span data-ttu-id="f6666-147">Per visualizzare informazioni su tutti i siti di rete, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="f6666-147">To view information about all your network sites, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkSite
    
    <span data-ttu-id="f6666-148">Questo restituirà informazioni simili alla seguente:</span><span class="sxs-lookup"><span data-stu-id="f6666-148">That will return information similar to this:</span></span>
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

<span data-ttu-id="f6666-149">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) .</span><span class="sxs-lookup"><span data-stu-id="f6666-149">For more information, see the help topic for the [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) cmdlet.</span></span>


## <a name="create-or-modify-network-sites"></a><span data-ttu-id="f6666-150">Creare o modificare siti di rete</span><span class="sxs-lookup"><span data-stu-id="f6666-150">Create or modify network sites</span></span> 

<span data-ttu-id="f6666-151">I siti di rete sono gli uffici o i percorsi configurati in ogni area geografica di un controllo di ammissione alle chiamate (CAC) o una distribuzione avanzata di 9-1-1.</span><span class="sxs-lookup"><span data-stu-id="f6666-151">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="f6666-152">Puoi usare il pannello di controllo di Skype for Business Server per configurare i siti e associarli alle aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="f6666-152">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="f6666-153">Ad esempio, un'area di rete per il Nord America potrebbe essere associata a siti di reti come Chicago, Redmond e Vancouver.</span><span class="sxs-lookup"><span data-stu-id="f6666-153">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="f6666-154">È necessario creare un sito di rete CAC per ogni sito all'interno di un'organizzazione, anche se il sito non ha limitazioni di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="f6666-154">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="f6666-155">Nel pannello di controllo di Skype for Business Server è possibile creare, modificare ed eliminare siti di rete.</span><span class="sxs-lookup"><span data-stu-id="f6666-155">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="f6666-156">Usare le procedure seguenti per creare o modificare un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="f6666-156">Use the following procedures to create or modify a network site.</span></span> 

### <a name="to-create-a-network-site"></a><span data-ttu-id="f6666-157">Per creare un sito di rete</span><span class="sxs-lookup"><span data-stu-id="f6666-157">To create a network site</span></span>

1.  <span data-ttu-id="f6666-158">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="f6666-158">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f6666-159">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f6666-159">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f6666-160">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su **sito**.</span><span class="sxs-lookup"><span data-stu-id="f6666-160">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="f6666-161">Nella pagina del **sito** fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="f6666-161">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="f6666-162">In **nuovo sito**Digitare un nome per il sito nel campo **nome** .</span><span class="sxs-lookup"><span data-stu-id="f6666-162">In **New Site**, type a name for this site in the **Name** field.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="f6666-163">I nomi dei siti devono essere univoci all'interno della distribuzione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f6666-163">Site names must be unique within the Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="f6666-164">Nell'elenco a discesa **Region** selezionare un'area di rete da associare al sito.</span><span class="sxs-lookup"><span data-stu-id="f6666-164">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="f6666-165">Opzionale Se si vogliono inserire limitazioni della larghezza di banda per le chiamate audio o video a questo sito, selezionare il profilo dei criteri di larghezza di banda con le impostazioni appropriate nell'elenco a discesa **criteri di larghezza** di banda.</span><span class="sxs-lookup"><span data-stu-id="f6666-165">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="f6666-166">È possibile visualizzare i dettagli dei profili di criteri di larghezza di banda disponibili oppure creare un nuovo profilo per i criteri di larghezza di banda nella pagina **Profil Policy** del gruppo **configurazione di rete** .</span><span class="sxs-lookup"><span data-stu-id="f6666-166">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the **Policy Profil** page of the **Network Configuration** group.</span></span> <span data-ttu-id="f6666-167">Per informazioni dettagliate, vedere [gestione dei profili di criteri di larghezza di banda di rete](managing-network-bandwidth-policy-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="f6666-167">For details, see [Managing network bandwidth policy profiles](managing-network-bandwidth-policy-profiles.md).</span></span>

8.  <span data-ttu-id="f6666-168">Opzionale Per specificare le impostazioni di posizione per questo sito, selezionare un criterio di posizione dall'elenco a discesa **criteri di posizione** .</span><span class="sxs-lookup"><span data-stu-id="f6666-168">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="f6666-169">Il criterio posizione assegna al sito specifiche impostazioni avanzate di 9-1-1 (E9-1-1) e di posizione del client.</span><span class="sxs-lookup"><span data-stu-id="f6666-169">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="f6666-170">È possibile visualizzare i dettagli dei criteri di posizione disponibili oppure creare un nuovo criterio di posizione dalla pagina **criteri posizione** del gruppo Configurazione di **rete** .</span><span class="sxs-lookup"><span data-stu-id="f6666-170">You can view the details of the available location policies, or create a new location policy, from the **Location Policy** page of the **Network Configuration** group.</span></span> 

9.  <span data-ttu-id="f6666-171">Opzionale Digitare un valore nel campo **Description** per ottenere altre informazioni su questo sito che non possono essere espresse solo dal nome.</span><span class="sxs-lookup"><span data-stu-id="f6666-171">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="f6666-172">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="f6666-172">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="f6666-173">Quando si crea un nuovo sito di rete, non si usa la tabella **subnet associata** .</span><span class="sxs-lookup"><span data-stu-id="f6666-173">You do not use the **Associated Subnets** table when you create a new network site.</span></span> <span data-ttu-id="f6666-174">Si associa una subnet a un sito quando si crea o si modifica la subnet.</span><span class="sxs-lookup"><span data-stu-id="f6666-174">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="f6666-175">Per informazioni dettagliate, vedere [gestione delle subnet di rete](managing-network-subnets.md).</span><span class="sxs-lookup"><span data-stu-id="f6666-175">For details, see [Managing network subnets](managing-network-subnets.md).</span></span>

### <a name="to-modify-a-network-site"></a><span data-ttu-id="f6666-176">Per modificare un sito di rete</span><span class="sxs-lookup"><span data-stu-id="f6666-176">To modify a network site</span></span>

1.  <span data-ttu-id="f6666-177">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="f6666-177">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f6666-178">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f6666-178">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f6666-179">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su **sito**.</span><span class="sxs-lookup"><span data-stu-id="f6666-179">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="f6666-180">Nella pagina del **sito** fare clic sul sito che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="f6666-180">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="f6666-181">Nel menu **modifica** fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="f6666-181">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="f6666-182">Nella pagina **modifica sito** è possibile modificare la descrizione, l'area geografica, il profilo dei criteri di larghezza di banda e i criteri di posizione associati al sito.</span><span class="sxs-lookup"><span data-stu-id="f6666-182">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site.</span></span> <span data-ttu-id="f6666-183">Per informazioni dettagliate, vedere [creare un sito di rete](#to-create-a-network-site) sopra.</span><span class="sxs-lookup"><span data-stu-id="f6666-183">For details, see [To create a network site](#to-create-a-network-site) above.</span></span>

7.  <span data-ttu-id="f6666-184">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="f6666-184">Click **Commit**.</span></span>

<span data-ttu-id="f6666-185">Non è possibile modificare la tabella **subnet associata** in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="f6666-185">You cannot modify the **Associated Subnets** table on this page.</span></span> <span data-ttu-id="f6666-186">L'elenco delle subnet associate viene fornito come riferimento in modo da essere a conoscenza delle subnet che verranno modificate quando si modificano le impostazioni del sito.</span><span class="sxs-lookup"><span data-stu-id="f6666-186">The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>


## <a name="delete-an-existing-network-site"></a><span data-ttu-id="f6666-187">Eliminare un sito di rete esistente</span><span class="sxs-lookup"><span data-stu-id="f6666-187">Delete an existing network site</span></span>

<span data-ttu-id="f6666-188">I siti di rete sono gli uffici o i percorsi configurati in ogni area geografica di un controllo di ammissione alle chiamate (CAC) o una distribuzione avanzata di 9-1-1.</span><span class="sxs-lookup"><span data-stu-id="f6666-188">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="f6666-189">Puoi usare il pannello di controllo di Skype for Business Server per configurare i siti e associarli alle aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="f6666-189">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="f6666-190">Ad esempio, un'area di rete per il Nord America potrebbe essere associata a siti di reti come Chicago, Redmond e Vancouver.</span><span class="sxs-lookup"><span data-stu-id="f6666-190">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="f6666-191">È necessario creare un sito di rete CAC per ogni sito all'interno di un'organizzazione, anche se il sito non ha limitazioni di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="f6666-191">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="f6666-192">Nel pannello di controllo di Skype for Business Server è possibile creare, modificare ed eliminare siti di rete.</span><span class="sxs-lookup"><span data-stu-id="f6666-192">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="f6666-193">Usare la procedura seguente per eliminare un sito di rete esistente.</span><span class="sxs-lookup"><span data-stu-id="f6666-193">Use the following procedure to delete an existing network site.</span></span> <span data-ttu-id="f6666-194">Per informazioni dettagliate sulla creazione o la modifica di siti di rete, vedere [gestione del controllo dell'ammissione delle chiamate per i siti](managing-call-admission-control-for-sites.md).</span><span class="sxs-lookup"><span data-stu-id="f6666-194">For details about creating or modifying network sites, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>


### <a name="to-delete-a-network-site"></a><span data-ttu-id="f6666-195">Per eliminare un sito di rete</span><span class="sxs-lookup"><span data-stu-id="f6666-195">To delete a network site</span></span>

1.  <span data-ttu-id="f6666-196">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="f6666-196">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f6666-197">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f6666-197">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f6666-198">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su **sito**.</span><span class="sxs-lookup"><span data-stu-id="f6666-198">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="f6666-199">Nella pagina del **sito** fare clic sul sito che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="f6666-199">On the **Site** page, click the site that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="f6666-200">È possibile eliminare più di un sito alla volta.</span><span class="sxs-lookup"><span data-stu-id="f6666-200">You can delete more than one site at a time.</span></span> <span data-ttu-id="f6666-201">Per eseguire questa operazione, premere CTRL e selezionare più siti tenendo premuto il tasto CTRL.</span><span class="sxs-lookup"><span data-stu-id="f6666-201">To do this, press CTRL and select multiple sites while holding down the CTRL key.</span></span> <span data-ttu-id="f6666-202">In alternativa, per selezionare tutti i siti, fare clic su **Seleziona tutto** dal menu **modifica** .</span><span class="sxs-lookup"><span data-stu-id="f6666-202">Or, to select all sites, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="f6666-203">Scegliere **Elimina**dal menu **modifica** .</span><span class="sxs-lookup"><span data-stu-id="f6666-203">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="f6666-204">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6666-204">Click **OK**.</span></span>
    

    > [!WARNING]  
    > <span data-ttu-id="f6666-205">Non è possibile rimuovere un sito di rete se associato a una subnet di rete.</span><span class="sxs-lookup"><span data-stu-id="f6666-205">You cannot remove a network site if it is associated with a network subnet.</span></span> <span data-ttu-id="f6666-206">Se si tenta di rimuovere un sito associato a una subnet, viene visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="f6666-206">If you attempt to remove a site associated with a subnet you will receive an error message.</span></span> <span data-ttu-id="f6666-207">Per verificare se un sito è associato a qualsiasi subnet, fare clic sul sito e quindi su **Mostra dettagli** dal menu **modifica** .</span><span class="sxs-lookup"><span data-stu-id="f6666-207">To see if a site is associated with any subnets, click the site and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="f6666-208">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6666-208">See Also</span></span>


[<span data-ttu-id="f6666-209">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="f6666-209">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[<span data-ttu-id="f6666-210">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="f6666-210">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[<span data-ttu-id="f6666-211">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="f6666-211">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[<span data-ttu-id="f6666-212">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="f6666-212">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[<span data-ttu-id="f6666-213">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="f6666-213">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="f6666-214">New-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="f6666-214">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

[<span data-ttu-id="f6666-215">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="f6666-215">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

[<span data-ttu-id="f6666-216">Remove-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="f6666-216">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  

[<span data-ttu-id="f6666-217">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="f6666-217">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  

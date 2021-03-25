---
title: Gestione del controllo di ammissione di chiamata per i siti
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: I siti di rete sono gli uffici o le postazioni in ogni area di rete delle distribuzioni del servizio Controllo di ammissione di chiamata (CAC, Call Admission Control), del servizio per chiamate di emergenza E9-1-1 e di bypass multimediale.
ms.openlocfilehash: 0b339f15e53dd94bda655884f70c041f9da9e5a8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118565"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a><span data-ttu-id="49d02-103">Gestione del controllo di ammissione di chiamata per i siti in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="49d02-103">Managing call admission control for sites in Skype for Business Server</span></span>

<span data-ttu-id="49d02-104">I siti di rete sono gli uffici o le postazioni in ogni area di rete delle distribuzioni del servizio Controllo di ammissione di chiamata (CAC, Call Admission Control), del servizio per chiamate di emergenza E9-1-1 e di bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="49d02-104">Network sites are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments.</span></span> <span data-ttu-id="49d02-105">Utilizzare le procedure descritte in questo articolo per configurare il controllo di ammissione di chiamata per i siti di rete.</span><span class="sxs-lookup"><span data-stu-id="49d02-105">Use the procedures in this article to configure call admission control for network sites.</span></span>

## <a name="configure-network-site-links"></a><span data-ttu-id="49d02-106">Configurare i collegamenti di sito di rete</span><span class="sxs-lookup"><span data-stu-id="49d02-106">Configure network site links</span></span>

<span data-ttu-id="49d02-107">All'interno di una configurazione del servizio Controllo di ammissione di chiamata è possibile creare criteri tra siti di rete che definiscono le limitazioni di larghezza di banda tra i siti direttamente collegati.</span><span class="sxs-lookup"><span data-stu-id="49d02-107">Within a call admission control (CAC) configuration, you can create network inter-site policies that define bandwidth limitations between sites that are directly linked.</span></span> <span data-ttu-id="49d02-108">Se due siti di rete condividono un collegamento diretto, è possibile definire dei limiti della larghezza di banda per le connessioni audio e video tra tali siti.</span><span class="sxs-lookup"><span data-stu-id="49d02-108">When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.</span></span> <span data-ttu-id="49d02-109">Non è possibile utilizzare il Pannello di controllo di Skype for Business Server per configurare i criteri del sito di rete, ma è possibile farlo solo utilizzando i cmdlet di Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="49d02-109">You cannot use the Skype for Business Server Control Panel to configure network site policies, this can be done only by using cmdlets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="49d02-110">È possibile creare, modificare e rimuovere un collegamento di sito di rete (noto anche come criterio tra siti di rete) da Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="49d02-110">You can create, modify, and remove a network site link (also known as a network inter-site policy) from the Skype for Business Server Management Shell.</span></span>

### <a name="to-create-a-network-site-link"></a><span data-ttu-id="49d02-111">Per creare un collegamento di sito di rete</span><span class="sxs-lookup"><span data-stu-id="49d02-111">To create a network site link</span></span>

1.  <span data-ttu-id="49d02-112">Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari.</span><span class="sxs-lookup"><span data-stu-id="49d02-112">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="49d02-113">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business Server** e quindi Skype for Business Server Management **Shell.**</span><span class="sxs-lookup"><span data-stu-id="49d02-113">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="49d02-114">Al prompt dei comandi digitare il comando seguente, utilizzando valori validi per la configurazione in uso:</span><span class="sxs-lookup"><span data-stu-id="49d02-114">From the command prompt, type the following command, substituting values that are valid for your configuration:</span></span>
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    <span data-ttu-id="49d02-115">In questo esempio viene creato un nuovo collegamento di sito di rete denominato Reno Portland che imposta i limiti di larghezza di banda tra i siti di rete di Reno e \_ Portland.</span><span class="sxs-lookup"><span data-stu-id="49d02-115">This example creates a new network site link named Reno\_Portland that sets bandwidth limitations between the Reno and Portland network sites.</span></span> <span data-ttu-id="49d02-116">Il profilo dei criteri di larghezza di banda e siti di rete deve essere già presente prima dell'esecuzione di questo comando.</span><span class="sxs-lookup"><span data-stu-id="49d02-116">The network sites and the bandwidth policy profile must already exist before running this command.</span></span>

<span data-ttu-id="49d02-117">Per descrizioni dettagliate dei parametri, [vedere New-CsNetworkInterSitePolicy.](/powershell/module/skype/New-CsNetworkInterSitePolicy)</span><span class="sxs-lookup"><span data-stu-id="49d02-117">For detailed parameter descriptions, see [New-CsNetworkInterSitePolicy](/powershell/module/skype/New-CsNetworkInterSitePolicy).</span></span> <span data-ttu-id="49d02-118">Per ottenere un elenco dei profili dei criteri di larghezza di banda che è possibile applicare al collegamento di sito di rete, chiamare il cmdlet **Get-CsNetworkBandwidthPolicyProfile**.</span><span class="sxs-lookup"><span data-stu-id="49d02-118">To retrieve a list of bandwidth policy profiles that can be applied to the network site link, call the **Get-CsNetworkBandwidthPolicyProfile** cmdlet.</span></span> <span data-ttu-id="49d02-119">Per informazioni dettagliate, [vedere Get-CsNetworkBandwidthPolicyProfile.](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)</span><span class="sxs-lookup"><span data-stu-id="49d02-119">For details, see [Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span></span>

### <a name="to-modify-a-network-site-link"></a><span data-ttu-id="49d02-120">Per modificare un collegamento di sito di rete</span><span class="sxs-lookup"><span data-stu-id="49d02-120">To modify a network site link</span></span>

1.  <span data-ttu-id="49d02-121">Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari.</span><span class="sxs-lookup"><span data-stu-id="49d02-121">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="49d02-122">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business Server** e quindi Skype for Business Server Management **Shell.**</span><span class="sxs-lookup"><span data-stu-id="49d02-122">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="49d02-123">Utilizzare il cmdlet **CsNetworkInterSitePolicy Set** per modificare le proprietà di un collegamento di sito di rete specifico.</span><span class="sxs-lookup"><span data-stu-id="49d02-123">Use the **Set-CsNetworkInterSitePolicy** cmdlet to modify the properties of a given network site link.</span></span> <span data-ttu-id="49d02-124">È possibile modificare uno dei siti connessi o entrambi ed è possibile modificare il profilo dei criteri di larghezza di banda associato al collegamento.</span><span class="sxs-lookup"><span data-stu-id="49d02-124">You can modify either (or both) or the connected sites, and you can modify the bandwidth policy profile associated with the link.</span></span> <span data-ttu-id="49d02-125">Ecco un esempio di modifica del profilo dei criteri di larghezza di banda di un collegamento di sito denominato Reno \_ Portland:</span><span class="sxs-lookup"><span data-stu-id="49d02-125">Here is an example of modifying the bandwidth policy profile of a site link named Reno\_Portland:</span></span>
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

<span data-ttu-id="49d02-126">Per descrizioni dettagliate dei parametri, [vedere Set-CsNetworkInterSitePolicy.](/powershell/module/skype/Set-CsNetworkInterSitePolicy)</span><span class="sxs-lookup"><span data-stu-id="49d02-126">For detailed parameter descriptions, see [Set-CsNetworkInterSitePolicy](/powershell/module/skype/Set-CsNetworkInterSitePolicy).</span></span>


### <a name="to-delete-a-network-site-link"></a><span data-ttu-id="49d02-127">Per eliminare un collegamento di sito di rete</span><span class="sxs-lookup"><span data-stu-id="49d02-127">To delete a network site link</span></span>

1.  <span data-ttu-id="49d02-128">Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari.</span><span class="sxs-lookup"><span data-stu-id="49d02-128">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="49d02-129">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business Server** e quindi Skype for Business Server Management **Shell.**</span><span class="sxs-lookup"><span data-stu-id="49d02-129">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="49d02-130">Utilizzare il cmdlet **Remove-CsNetworkInterSitePolicy** per rimuovere un collegamento di sito di rete.</span><span class="sxs-lookup"><span data-stu-id="49d02-130">Use the **Remove-CsNetworkInterSitePolicy** cmdlet to remove a network site link.</span></span> <span data-ttu-id="49d02-131">Nell'esempio seguente viene eliminato il collegamento di sito di rete Reno \_ Portland:</span><span class="sxs-lookup"><span data-stu-id="49d02-131">The following example deletes the Reno\_Portland network site link:</span></span>
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

<span data-ttu-id="49d02-132">Per descrizioni dettagliate dei parametri, [vedere Remove-CsNetworkInterSitePolicy.](/powershell/module/skype/Remove-CsNetworkInterSitePolicy)</span><span class="sxs-lookup"><span data-stu-id="49d02-132">For detailed parameter descriptions, see [Remove-CsNetworkInterSitePolicy](/powershell/module/skype/Remove-CsNetworkInterSitePolicy).</span></span>


## <a name="view-network-site-information"></a><span data-ttu-id="49d02-133">Visualizzare le informazioni sui siti di rete</span><span class="sxs-lookup"><span data-stu-id="49d02-133">View network site information</span></span>

<span data-ttu-id="49d02-134">I siti di rete sono gli uffici o le postazioni configurate in ogni area di una distribuzione del servizio Controllo di ammissione di chiamata (CAC) o del servizio per chiamate di emergenza Enhanced 9-1-1.</span><span class="sxs-lookup"><span data-stu-id="49d02-134">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="49d02-135">È possibile visualizzare le informazioni sul sito di rete nel Pannello di controllo di Skype for Business Server o in Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="49d02-135">You can view network site information in either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="49d02-136">Per visualizzare le informazioni sui siti di rete nel Pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="49d02-136">To view network site information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="49d02-137">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="49d02-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="49d02-138">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="49d02-138">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="49d02-139">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Sito.**</span><span class="sxs-lookup"><span data-stu-id="49d02-139">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="49d02-140">Nella pagina **Sito** fare clic sul sito che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="49d02-140">On the **Site** page, click the site that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="49d02-141">È possibile visualizzare informazioni per un solo sito alla volta.</span><span class="sxs-lookup"><span data-stu-id="49d02-141">You can only view information for one site at a time.</span></span>

5.  <span data-ttu-id="49d02-142">Scegliere **Mostra dettagli** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="49d02-142">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="49d02-143">Visualizzazione delle informazioni sui siti di rete tramite Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="49d02-143">Viewing network site information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="49d02-144">È possibile visualizzare le informazioni sui siti di rete utilizzando Windows PowerShell e il cmdlet Get-CsNetworkSite rete.</span><span class="sxs-lookup"><span data-stu-id="49d02-144">You can view network site information by using Windows PowerShell and the Get-CsNetworkSite cmdlet.</span></span> <span data-ttu-id="49d02-145">Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="49d02-145">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-site-information"></a><span data-ttu-id="49d02-146">Per visualizzare informazioni sui siti di rete</span><span class="sxs-lookup"><span data-stu-id="49d02-146">To view network site information</span></span>

  - <span data-ttu-id="49d02-147">Per visualizzare informazioni su tutti i siti di rete, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="49d02-147">To view information about all your network sites, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkSite
    
    <span data-ttu-id="49d02-148">Verranno restituite informazioni simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="49d02-148">That will return information similar to this:</span></span>
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

<span data-ttu-id="49d02-149">Per ulteriori informazioni, vedere l'argomento della guida relativo al cmdlet [Get-CsNetworkSite](/powershell/module/skype/Get-CsNetworkSite).</span><span class="sxs-lookup"><span data-stu-id="49d02-149">For more information, see the help topic for the [Get-CsNetworkSite](/powershell/module/skype/Get-CsNetworkSite) cmdlet.</span></span>


## <a name="create-or-modify-network-sites"></a><span data-ttu-id="49d02-150">Creare o modificare siti di rete</span><span class="sxs-lookup"><span data-stu-id="49d02-150">Create or modify network sites</span></span> 

<span data-ttu-id="49d02-151">I siti di rete sono gli uffici o le postazioni configurate in ogni area di una distribuzione del servizio Controllo di ammissione di chiamata (CAC) o del servizio per chiamate di emergenza Enhanced 9-1-1.</span><span class="sxs-lookup"><span data-stu-id="49d02-151">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="49d02-152">Puoi usare il Pannello di controllo di Skype for Business Server per configurare i siti e associarli alle aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="49d02-152">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="49d02-153">Ad esempio, un'area di rete per il Nord America potrebbe essere associata a siti di rete come Chicago, Redmond e Vancouver.</span><span class="sxs-lookup"><span data-stu-id="49d02-153">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="49d02-154">Deve essere creato un sito di rete del servizio Controllo di ammissione di chiamata per ogni sito di un'organizzazione, anche se tale sito non presenta limitazioni della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="49d02-154">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="49d02-155">Dal Pannello di controllo di Skype for Business Server è possibile creare, modificare ed eliminare siti di rete.</span><span class="sxs-lookup"><span data-stu-id="49d02-155">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="49d02-156">Seguire le procedure seguenti per creare o modificare un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="49d02-156">Use the following procedures to create or modify a network site.</span></span> 

### <a name="to-create-a-network-site"></a><span data-ttu-id="49d02-157">Per creare un sito di rete</span><span class="sxs-lookup"><span data-stu-id="49d02-157">To create a network site</span></span>

1.  <span data-ttu-id="49d02-158">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="49d02-158">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="49d02-159">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="49d02-159">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="49d02-160">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Sito.**</span><span class="sxs-lookup"><span data-stu-id="49d02-160">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="49d02-161">Nella pagina **Sito** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="49d02-161">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="49d02-162">In **Nuovo sito** digitare un nome per il sito nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="49d02-162">In **New Site**, type a name for this site in the **Name** field.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="49d02-163">I nomi dei siti devono essere univoci all'interno della distribuzione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="49d02-163">Site names must be unique within the Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="49d02-164">Nell'elenco a discesa **Area** selezionare un'area di rete da associare al sito.</span><span class="sxs-lookup"><span data-stu-id="49d02-164">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="49d02-165">(Facoltativo) Se si desidera applicare limiti di larghezza di banda per le chiamate audio o video per il sito, selezionare il profilo del criterio larghezza di banda con le impostazioni appropriate nell'elenco a discesa **Criteri larghezza di banda**.</span><span class="sxs-lookup"><span data-stu-id="49d02-165">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="49d02-166">È possibile visualizzare i dettagli dei profili dei criteri di larghezza  di banda disponibili o creare un nuovo profilo di criteri di larghezza di banda nella pagina Profilo criteri del **gruppo Configurazione di** rete.</span><span class="sxs-lookup"><span data-stu-id="49d02-166">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the **Policy Profil** page of the **Network Configuration** group.</span></span> <span data-ttu-id="49d02-167">Per informazioni dettagliate, vedere [Managing network bandwidth policy profiles](managing-network-bandwidth-policy-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="49d02-167">For details, see [Managing network bandwidth policy profiles](managing-network-bandwidth-policy-profiles.md).</span></span>

8.  <span data-ttu-id="49d02-168">(Facoltativo) Se si desidera specificare impostazioni di posizione per questo sito, selezionare un criterio percorso nell'elenco a discesa **Criteri percorso**.</span><span class="sxs-lookup"><span data-stu-id="49d02-168">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="49d02-169">Il criterio percorso assegna impostazioni specifiche di Enhanced 9-1-1 (E9-1-1) e delle posizioni client al sito.</span><span class="sxs-lookup"><span data-stu-id="49d02-169">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="49d02-170">È possibile visualizzare i dettagli dei criteri percorso disponibili o creare un nuovo criterio percorso nella pagina **Criteri percorso** del gruppo **Configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="49d02-170">You can view the details of the available location policies, or create a new location policy, from the **Location Policy** page of the **Network Configuration** group.</span></span> 

9.  <span data-ttu-id="49d02-171">(Facoltativo) Digitare un valore nel campo **Descrizione** per fornire ulteriori informazioni sul sito che non possono essere espresse utilizzando solo il nome.</span><span class="sxs-lookup"><span data-stu-id="49d02-171">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="49d02-172">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="49d02-172">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="49d02-173">Quando si crea un nuovo sito di rete, non si utilizza la tabella **Subnet associate**.</span><span class="sxs-lookup"><span data-stu-id="49d02-173">You do not use the **Associated Subnets** table when you create a new network site.</span></span> <span data-ttu-id="49d02-174">L'associazione di una subnet a un sito viene effettuata quando si crea o si modifica la subnet.</span><span class="sxs-lookup"><span data-stu-id="49d02-174">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="49d02-175">Per informazioni dettagliate, vedere [Managing network subnets](managing-network-subnets.md).</span><span class="sxs-lookup"><span data-stu-id="49d02-175">For details, see [Managing network subnets](managing-network-subnets.md).</span></span>

### <a name="to-modify-a-network-site"></a><span data-ttu-id="49d02-176">Per modificare un sito di rete</span><span class="sxs-lookup"><span data-stu-id="49d02-176">To modify a network site</span></span>

1.  <span data-ttu-id="49d02-177">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="49d02-177">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="49d02-178">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="49d02-178">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="49d02-179">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Sito.**</span><span class="sxs-lookup"><span data-stu-id="49d02-179">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="49d02-180">Nella pagina **Sito** fare clic sul sito che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="49d02-180">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="49d02-181">Scegliere **Mostra dettagli** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="49d02-181">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="49d02-182">Nella pagina **Modifica sito** è possibile modificare la descrizione, l'area, il profilo del criterio larghezza di banda e il criterio percorso associati al sito.</span><span class="sxs-lookup"><span data-stu-id="49d02-182">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site.</span></span> <span data-ttu-id="49d02-183">Per informazioni dettagliate, vedere [Per creare un sito di rete sopra.](#to-create-a-network-site)</span><span class="sxs-lookup"><span data-stu-id="49d02-183">For details, see [To create a network site](#to-create-a-network-site) above.</span></span>

7.  <span data-ttu-id="49d02-184">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="49d02-184">Click **Commit**.</span></span>

<span data-ttu-id="49d02-p114">Non è possibile modificare la tabella **Subnet associate** in questa pagina. L'elenco di subnet associate viene fornito come riferimento per indicare quali subnet saranno interessate in caso di modifica delle impostazioni del sito.</span><span class="sxs-lookup"><span data-stu-id="49d02-p114">You cannot modify the **Associated Subnets** table on this page. The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>


## <a name="delete-an-existing-network-site"></a><span data-ttu-id="49d02-187">Eliminare un sito di rete esistente</span><span class="sxs-lookup"><span data-stu-id="49d02-187">Delete an existing network site</span></span>

<span data-ttu-id="49d02-188">I siti di rete sono gli uffici o le postazioni configurate in ogni area di una distribuzione del servizio Controllo di ammissione di chiamata (CAC) o del servizio per chiamate di emergenza Enhanced 9-1-1.</span><span class="sxs-lookup"><span data-stu-id="49d02-188">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="49d02-189">Puoi usare il Pannello di controllo di Skype for Business Server per configurare i siti e associarli alle aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="49d02-189">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="49d02-190">Ad esempio, un'area di rete per il Nord America potrebbe essere associata a siti di rete come Chicago, Redmond e Vancouver.</span><span class="sxs-lookup"><span data-stu-id="49d02-190">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="49d02-191">Deve essere creato un sito di rete del servizio Controllo di ammissione di chiamata per ogni sito di un'organizzazione, anche se tale sito non presenta limitazioni della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="49d02-191">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="49d02-192">Dal Pannello di controllo di Skype for Business Server è possibile creare, modificare ed eliminare siti di rete.</span><span class="sxs-lookup"><span data-stu-id="49d02-192">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="49d02-193">Per eliminare un sito di rete esistente, usare la procedura che segue.</span><span class="sxs-lookup"><span data-stu-id="49d02-193">Use the following procedure to delete an existing network site.</span></span> <span data-ttu-id="49d02-194">Per informazioni dettagliate sulla creazione o la modifica di siti di rete, vedere [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span><span class="sxs-lookup"><span data-stu-id="49d02-194">For details about creating or modifying network sites, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>


### <a name="to-delete-a-network-site"></a><span data-ttu-id="49d02-195">Per eliminare un sito di rete</span><span class="sxs-lookup"><span data-stu-id="49d02-195">To delete a network site</span></span>

1.  <span data-ttu-id="49d02-196">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="49d02-196">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="49d02-197">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="49d02-197">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="49d02-198">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Sito.**</span><span class="sxs-lookup"><span data-stu-id="49d02-198">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="49d02-199">Nella pagina **Sito** fare clic sul sito che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="49d02-199">On the **Site** page, click the site that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="49d02-p116">È possibile eliminare più siti contemporaneamente. A tale scopo, premere CTRL e selezionare più siti sempre tenendo premuto CTRL. In alternativa, per selezionare tutti i siti, scegliere **Seleziona tutto** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="49d02-p116">You can delete more than one site at a time. To do this, press CTRL and select multiple sites while holding down the CTRL key. Or, to select all sites, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="49d02-203">Scegliere **Elimina** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="49d02-203">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="49d02-204">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="49d02-204">Click **OK**.</span></span>
    

    > [!WARNING]  
    > <span data-ttu-id="49d02-p117">Se un sito di rete è associato a una subnet di rete, non è possibile rimuoverlo. Se si tenta di rimuovere un sito associato a una subnet, verrà visualizzato un messaggio di errore. Per controllare se un sito è associato a eventuali subnet, fare clic sul sito e quindi scegliere **Mostra dettagli** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="49d02-p117">You cannot remove a network site if it is associated with a network subnet. If you attempt to remove a site associated with a subnet you will receive an error message. To see if a site is associated with any subnets, click the site and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="49d02-208">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49d02-208">See Also</span></span>


[<span data-ttu-id="49d02-209">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="49d02-209">New-CsNetworkInterSitePolicy</span></span>](/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[<span data-ttu-id="49d02-210">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="49d02-210">Set-CsNetworkInterSitePolicy</span></span>](/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[<span data-ttu-id="49d02-211">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="49d02-211">Remove-CsNetworkInterSitePolicy</span></span>](/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[<span data-ttu-id="49d02-212">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="49d02-212">Get-CsNetworkInterSitePolicy</span></span>](/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[<span data-ttu-id="49d02-213">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="49d02-213">Get-CsNetworkBandwidthPolicyProfile</span></span>](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="49d02-214">New-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="49d02-214">New-CsNetworkSite</span></span>](/powershell/module/skype/New-CsNetworkSite)

[<span data-ttu-id="49d02-215">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="49d02-215">Set-CsNetworkSite</span></span>](/powershell/module/skype/Set-CsNetworkSite)

[<span data-ttu-id="49d02-216">Remove-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="49d02-216">Remove-CsNetworkSite</span></span>](/powershell/module/skype/Remove-CsNetworkSite)  

[<span data-ttu-id="49d02-217">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="49d02-217">Get-CsNetworkSite</span></span>](/powershell/module/skype/Get-CsNetworkSite)
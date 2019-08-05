---
title: Gestione delle aree di rete
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Area di rete * sono gli hub di rete o i backbone usati nella configurazione del controllo di ammissione alle chiamate, E9-1-1 e bypass multimediale.
ms.openlocfilehash: 8d1d60389fe910e2b5c2b8b1c357520aad30db96
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188564"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a><span data-ttu-id="03437-103">Gestione delle aree di rete in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="03437-103">Managing network regions in Skype for Business Server</span></span>

<span data-ttu-id="03437-104">Le *aree di rete* sono gli hub di rete o le backbone usati nella configurazione del controllo di ammissione alle chiamate, E9-1-1 e bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="03437-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="03437-105">Usare le procedure seguenti per visualizzare, creare o modificare le aree di rete.</span><span class="sxs-lookup"><span data-stu-id="03437-105">Use the following procedures to view, create, or modify network regions.</span></span> <span data-ttu-id="03437-106">Se ad esempio sono già state create aree di rete per una sola funzionalità vocale, non è necessario creare nuove aree di rete. altre funzionalità vocali avanzate di Enterprise useranno le stesse aree di rete.</span><span class="sxs-lookup"><span data-stu-id="03437-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="03437-107">Può tuttavia essere necessario modificare una definizione di area di rete esistente per applicare impostazioni specifiche delle caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="03437-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="03437-108">Ad esempio, se sono state create aree di rete per E9-1-1 (che non richiedono un sito centrale associato) e quindi si distribuisce il controllo di ammissione delle chiamate, è necessario modificare le definizioni dell'area di rete per specificare un sito centrale.</span><span class="sxs-lookup"><span data-stu-id="03437-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> 

<span data-ttu-id="03437-109">Usare le procedure descritte in questo articolo per visualizzare le informazioni sull'area di rete o per creare, modificare o eliminare aree di rete.</span><span class="sxs-lookup"><span data-stu-id="03437-109">Use the procedures in this article to view network region information or create, modify, or delete network regions.</span></span> 

## <a name="view-network-region-information"></a><span data-ttu-id="03437-110">Visualizzare le informazioni relative all'area di rete</span><span class="sxs-lookup"><span data-stu-id="03437-110">View network region information</span></span> 


<span data-ttu-id="03437-111">Un'area geografica di rete interconnette varie parti di una rete in più aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="03437-111">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="03437-112">Ogni area di rete deve essere associata a un sito centrale.</span><span class="sxs-lookup"><span data-stu-id="03437-112">Every network region must be associated with a central site.</span></span> <span data-ttu-id="03437-113">Il sito centrale è il sito centro dati in cui è in uso il servizio criteri di larghezza di banda di controllo delle chiamate (CAC).</span><span class="sxs-lookup"><span data-stu-id="03437-113">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="03437-114">Puoi usare il pannello di controllo di Skype for Business Server per visualizzare le aree di rete.</span><span class="sxs-lookup"><span data-stu-id="03437-114">You can use Skype for Business Server Control Panel to view network regions.</span></span> <span data-ttu-id="03437-115">Le aree di rete includono impostazioni che determinano se i percorsi alternativi tramite Internet sono consentiti per le connessioni audio e video.</span><span class="sxs-lookup"><span data-stu-id="03437-115">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="03437-116">Usare questo argomento per visualizzare le aree di rete esistenti.</span><span class="sxs-lookup"><span data-stu-id="03437-116">Use this topic to view existing network regions.</span></span> 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a><span data-ttu-id="03437-117">Per visualizzare informazioni su un'area geografica di rete con il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="03437-117">To view information about a network region with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="03437-118">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="03437-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="03437-119">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="03437-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="03437-120">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su area geografica. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="03437-120">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="03437-121">Nella pagina **area geografica** fare clic sull'area che si vuole visualizzare.</span><span class="sxs-lookup"><span data-stu-id="03437-121">On the **Region** page, click the region you want to view.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="03437-122">È possibile visualizzare una sola area alla volta.</span><span class="sxs-lookup"><span data-stu-id="03437-122">You can only view one region at a time.</span></span>

5.  <span data-ttu-id="03437-123">Nel menu **modifica** fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="03437-123">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="03437-124">Visualizzazione delle informazioni relative all'area di rete tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="03437-124">Viewing network region information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="03437-125">Per visualizzare le informazioni relative all'area di rete, è possibile usare Windows PowerShell e il cmdlet **Get-CsNetworkRegion** .</span><span class="sxs-lookup"><span data-stu-id="03437-125">You can view network region information by using Windows PowerShell and the **Get-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="03437-126">Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="03437-126">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-information"></a><span data-ttu-id="03437-127">Per visualizzare le informazioni relative all'area di rete</span><span class="sxs-lookup"><span data-stu-id="03437-127">To view network region information</span></span>

  - <span data-ttu-id="03437-128">Per visualizzare informazioni su tutte le aree geografiche di rete, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="03437-128">To view information about all your network regions, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegion
    
    <span data-ttu-id="03437-129">Questo restituirà informazioni simili alla seguente:</span><span class="sxs-lookup"><span data-stu-id="03437-129">That will return information similar to this:</span></span>
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

<span data-ttu-id="03437-130">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) .</span><span class="sxs-lookup"><span data-stu-id="03437-130">For more information, see the help topic for the [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet.</span></span>


## <a name="create-or-modify-network-regions"></a><span data-ttu-id="03437-131">Creare o modificare aree di rete</span><span class="sxs-lookup"><span data-stu-id="03437-131">Create or modify network regions</span></span> 

<span data-ttu-id="03437-132">Un'area geografica di rete interconnette varie parti di una rete in più aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="03437-132">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="03437-133">Ogni area di rete deve essere associata a un sito centrale.</span><span class="sxs-lookup"><span data-stu-id="03437-133">Every network region must be associated with a central site.</span></span> <span data-ttu-id="03437-134">Il sito centrale è il sito centro dati in cui è in uso il servizio criteri di larghezza di banda di controllo delle chiamate (CAC).</span><span class="sxs-lookup"><span data-stu-id="03437-134">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="03437-135">Puoi usare il pannello di controllo di Skype for Business Server per configurare le aree geografiche di rete.</span><span class="sxs-lookup"><span data-stu-id="03437-135">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="03437-136">Le aree di rete includono impostazioni che determinano se i percorsi alternativi tramite Internet sono consentiti per le connessioni audio e video.</span><span class="sxs-lookup"><span data-stu-id="03437-136">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="03437-137">Dal pannello di controllo di Skype for Business Server è possibile creare, modificare o eliminare un'area geografica di rete.</span><span class="sxs-lookup"><span data-stu-id="03437-137">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="03437-138">Usare questo argomento per creare e modificare le aree di rete.</span><span class="sxs-lookup"><span data-stu-id="03437-138">Use this topic to create and modify network regions.</span></span> 

### <a name="to-create-a-network-region"></a><span data-ttu-id="03437-139">Per creare un'area di rete</span><span class="sxs-lookup"><span data-stu-id="03437-139">To create a network region</span></span>

1.  <span data-ttu-id="03437-140">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="03437-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="03437-141">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="03437-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="03437-142">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su area geografica. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="03437-142">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="03437-143">Nella pagina **area** fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="03437-143">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="03437-144">Nella pagina **nuova area** Digitare un valore nel campo **nome** .</span><span class="sxs-lookup"><span data-stu-id="03437-144">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="03437-145">Questo valore deve essere univoco all'interno della distribuzione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="03437-145">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="03437-146">Nell'elenco a discesa **sito centrale** selezionare il sito centrale per l'area di rete.</span><span class="sxs-lookup"><span data-stu-id="03437-146">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="03437-147">La casella di controllo **Attiva percorso alternativo audio** è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="03437-147">The **Enable audio alternate path** check box is checked by default.</span></span> <span data-ttu-id="03437-148">Questo campo determina se le chiamate audio verranno instradate tramite un percorso alternativo se la larghezza di banda adeguata non esiste nel percorso principale.</span><span class="sxs-lookup"><span data-stu-id="03437-148">This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="03437-149">Deselezionare questa casella di controllo solo se è necessario disattivare l'offload su Internet.</span><span class="sxs-lookup"><span data-stu-id="03437-149">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="03437-150">Se le chiamate saranno chiamate Internet, questa casella di controllo deve essere selezionata, indipendentemente dalle impostazioni di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="03437-150">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="03437-151">La casella di controllo **Attiva percorso alternativo video** è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="03437-151">The **Enable video alternate path** check box is checked by default.</span></span> <span data-ttu-id="03437-152">Questo campo determina se le videochiamate verranno instradate tramite un percorso alternativo se la larghezza di banda adeguata non esiste nel percorso principale.</span><span class="sxs-lookup"><span data-stu-id="03437-152">This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="03437-153">Deselezionare questa casella di controllo solo se è necessario disattivare l'offload su Internet.</span><span class="sxs-lookup"><span data-stu-id="03437-153">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="03437-154">Se le chiamate saranno chiamate Internet, questa casella di controllo deve essere selezionata, indipendentemente dalle impostazioni di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="03437-154">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="03437-155">Opzionale Digitare un valore nel campo **Description** per ottenere altre informazioni sull'area geografica che non può essere espressa solo dal nome.</span><span class="sxs-lookup"><span data-stu-id="03437-155">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="03437-156">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="03437-156">Click **Commit**.</span></span>

<span data-ttu-id="03437-157">La tabella **siti associati** non viene usata per la creazione di un'area di rete.</span><span class="sxs-lookup"><span data-stu-id="03437-157">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="03437-158">Quando si crea o si modifica il sito, si associa un sito a un'area geografica.</span><span class="sxs-lookup"><span data-stu-id="03437-158">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="03437-159">Per informazioni dettagliate, vedere [gestione del controllo dell'ammissione delle chiamate per i siti](managing-call-admission-control-for-sites.md).</span><span class="sxs-lookup"><span data-stu-id="03437-159">For details, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>

### <a name="to-modify-a-network-region"></a><span data-ttu-id="03437-160">Per modificare un'area di rete</span><span class="sxs-lookup"><span data-stu-id="03437-160">To modify a network region</span></span>

1.  <span data-ttu-id="03437-161">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="03437-161">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="03437-162">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="03437-162">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="03437-163">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su area geografica. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="03437-163">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="03437-164">Nella pagina **area** fare clic sull'area che si vuole modificare.</span><span class="sxs-lookup"><span data-stu-id="03437-164">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="03437-165">Nel menu **modifica** fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="03437-165">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="03437-166">Nella pagina **modifica area** è possibile modificare le impostazioni per l'abilitazione e la disabilitazione di percorsi alternativi audio e video e modificare la descrizione (per informazioni dettagliate, vedere la sezione "per creare un'area di rete" in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="03437-166">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="03437-167">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="03437-167">Click **Commit**.</span></span>

<span data-ttu-id="03437-168">Non è possibile modificare i **siti associati** in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="03437-168">You cannot modify the **Associated sites** on this page.</span></span> <span data-ttu-id="03437-169">L'elenco dei siti associati viene fornito per il riferimento, in modo da sapere quali siti verranno modificati quando si modificano le impostazioni dell'area geografica.</span><span class="sxs-lookup"><span data-stu-id="03437-169">The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>


## <a name="delete-existing-network-regions"></a><span data-ttu-id="03437-170">Eliminare le aree di rete esistenti</span><span class="sxs-lookup"><span data-stu-id="03437-170">Delete existing network regions</span></span> 

<span data-ttu-id="03437-171">Un'area geografica di rete interconnette varie parti di una rete in più aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="03437-171">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="03437-172">Ogni area di rete deve essere associata a un sito centrale.</span><span class="sxs-lookup"><span data-stu-id="03437-172">Every network region must be associated with a central site.</span></span> <span data-ttu-id="03437-173">Il sito centrale è il sito centro dati in cui è in uso il servizio criteri di larghezza di banda di controllo delle chiamate (CAC).</span><span class="sxs-lookup"><span data-stu-id="03437-173">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="03437-174">Puoi usare il pannello di controllo di Skype for Business Server per configurare le aree geografiche di rete.</span><span class="sxs-lookup"><span data-stu-id="03437-174">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="03437-175">Le aree di rete includono impostazioni che determinano se i percorsi alternativi tramite Internet sono consentiti per le connessioni audio e video.</span><span class="sxs-lookup"><span data-stu-id="03437-175">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="03437-176">Dal pannello di controllo di Skype for Business Server è possibile creare, modificare o eliminare un'area geografica di rete.</span><span class="sxs-lookup"><span data-stu-id="03437-176">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="03437-177">Usare questo argomento per eliminare le aree di rete esistenti.</span><span class="sxs-lookup"><span data-stu-id="03437-177">Use this topic to delete existing network regions.</span></span> 

### <a name="to-delete-a-network-region"></a><span data-ttu-id="03437-178">Per eliminare un'area di rete</span><span class="sxs-lookup"><span data-stu-id="03437-178">To delete a network region</span></span>

1.  <span data-ttu-id="03437-179">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="03437-179">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="03437-180">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="03437-180">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="03437-181">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su area geografica. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="03437-181">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="03437-182">Nella pagina **area** fare clic sull'area che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="03437-182">On the **Region** page, click the region you want to delete.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="03437-183">Puoi eliminare più di un'area alla volta.</span><span class="sxs-lookup"><span data-stu-id="03437-183">You can delete more than one region at a time.</span></span> <span data-ttu-id="03437-184">A tale scopo, premere CTRL e selezionare più aree mentre si tiene premuto il tasto CTRL.</span><span class="sxs-lookup"><span data-stu-id="03437-184">To do this, press CTRL and select multiple regions while holding down the CTRL key.</span></span> <span data-ttu-id="03437-185">In alternativa, per selezionare tutte le aree geografiche, fare clic su **Seleziona tutto** dal menu **modifica** .</span><span class="sxs-lookup"><span data-stu-id="03437-185">Or, to select all regions, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="03437-186">Scegliere **Elimina**dal menu **modifica** .</span><span class="sxs-lookup"><span data-stu-id="03437-186">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="03437-187">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="03437-187">Click **OK**.</span></span>


    > [!WARNING]  
    > <span data-ttu-id="03437-188">Un'area di rete non può essere rimossa se associata a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="03437-188">A network region cannot be removed if it is associated with a network site.</span></span> <span data-ttu-id="03437-189">Se si tenta di rimuovere un'area associata a un sito, viene visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="03437-189">If you attempt to remove a region associated with a site, you will receive an error message.</span></span> <span data-ttu-id="03437-190">Per verificare se un'area è associata a qualsiasi sito, selezionare l'area geografica e quindi fare clic su **Mostra dettagli** dal menu **modifica** .</span><span class="sxs-lookup"><span data-stu-id="03437-190">To see if a region is associated with any sites, select the region and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="03437-191">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03437-191">See Also</span></span>

[<span data-ttu-id="03437-192">Gestione delle route dell'area di rete</span><span class="sxs-lookup"><span data-stu-id="03437-192">Managing network region routes</span></span>](managing-network-region-routes.md)

[<span data-ttu-id="03437-193">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="03437-193">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  

[<span data-ttu-id="03437-194">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="03437-194">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  

[<span data-ttu-id="03437-195">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="03437-195">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  

[<span data-ttu-id="03437-196">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="03437-196">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  

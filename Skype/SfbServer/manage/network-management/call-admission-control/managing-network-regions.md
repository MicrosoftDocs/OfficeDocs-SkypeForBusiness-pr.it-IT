---
title: Gestione delle aree di rete
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
description: Area di rete* sono gli hub di rete o backbone utilizzati nella configurazione del controllo di ammissione di chiamata, del servizio E9-1-1 e del bypass multimediale.
ms.openlocfilehash: 14c8004ddd14c0a37c25d700edae845ac9adfe29
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816416"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a><span data-ttu-id="49d37-103">Gestione delle aree di rete in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="49d37-103">Managing network regions in Skype for Business Server</span></span>

<span data-ttu-id="49d37-104">*Le aree di* rete sono hub di rete o backbone utilizzati nella configurazione del controllo di ammissione di chiamata, del servizio E9-1-1 e del bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="49d37-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="49d37-105">Utilizzare le procedure seguenti per visualizzare, creare o modificare aree di rete.</span><span class="sxs-lookup"><span data-stu-id="49d37-105">Use the following procedures to view, create, or modify network regions.</span></span> <span data-ttu-id="49d37-106">Ad esempio, se sono già state create aree di rete per una funzionalità vocale, non è necessario creare nuove aree di rete. altre funzionalità avanzate VoIP aziendale utilizzeranno le stesse aree di rete.</span><span class="sxs-lookup"><span data-stu-id="49d37-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="49d37-107">Potrebbe tuttavia essere necessario modificare una definizione di area di rete esistente per applicare impostazioni specifiche della caratteristica.</span><span class="sxs-lookup"><span data-stu-id="49d37-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="49d37-108">Ad esempio, se sono state create aree di rete per il servizio E9-1-1 (che non richiedono un sito centrale associato) e quindi si distribuisce il controllo di ammissione di chiamata, è necessario modificare le definizioni delle aree di rete per specificare un sito centrale.</span><span class="sxs-lookup"><span data-stu-id="49d37-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> 

<span data-ttu-id="49d37-109">Utilizzare le procedure descritte in questo articolo per visualizzare informazioni sulle aree di rete oppure per creare, modificare o eliminare aree di rete.</span><span class="sxs-lookup"><span data-stu-id="49d37-109">Use the procedures in this article to view network region information or create, modify, or delete network regions.</span></span> 

## <a name="view-network-region-information"></a><span data-ttu-id="49d37-110">Visualizzare le informazioni sull'area di rete</span><span class="sxs-lookup"><span data-stu-id="49d37-110">View network region information</span></span> 


<span data-ttu-id="49d37-111">Un'area di rete interconnette diverse parti di una rete dislocate su più aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="49d37-111">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="49d37-112">Ogni area di rete deve essere associata a un sito centrale.</span><span class="sxs-lookup"><span data-stu-id="49d37-112">Every network region must be associated with a central site.</span></span> <span data-ttu-id="49d37-113">Il sito centrale è il sito del data center in cui è in esecuzione il servizio dei criteri di larghezza di banda del controllo di ammissione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="49d37-113">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="49d37-114">Puoi usare il Pannello di controllo di Skype for Business Server per visualizzare le aree di rete.</span><span class="sxs-lookup"><span data-stu-id="49d37-114">You can use Skype for Business Server Control Panel to view network regions.</span></span> <span data-ttu-id="49d37-115">Per le aree di rete sono disponibili impostazioni che determinano se sono consentiti percorsi alternativi attraverso Internet per le connessioni audio e video.</span><span class="sxs-lookup"><span data-stu-id="49d37-115">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="49d37-116">Le informazioni in questo argomento descrivono come visualizzare le aree di rete esistenti.</span><span class="sxs-lookup"><span data-stu-id="49d37-116">Use this topic to view existing network regions.</span></span> 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a><span data-ttu-id="49d37-117">Per visualizzare informazioni su un'area di rete con il Pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="49d37-117">To view information about a network region with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="49d37-118">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="49d37-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="49d37-119">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="49d37-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="49d37-120">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Area.**</span><span class="sxs-lookup"><span data-stu-id="49d37-120">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="49d37-121">Nella pagina **Area** fare clic sull'area che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="49d37-121">On the **Region** page, click the region you want to view.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="49d37-122">È possibile visualizzare una sola area alla volta.</span><span class="sxs-lookup"><span data-stu-id="49d37-122">You can only view one region at a time.</span></span>

5.  <span data-ttu-id="49d37-123">Scegliere **Mostra dettagli** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="49d37-123">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="49d37-124">Visualizzazione delle informazioni sulle aree di rete tramite Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="49d37-124">Viewing network region information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="49d37-125">È possibile visualizzare le informazioni sulle aree di rete utilizzando Windows PowerShell e il cmdlet **Get-CsNetworkRegion.**</span><span class="sxs-lookup"><span data-stu-id="49d37-125">You can view network region information by using Windows PowerShell and the **Get-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="49d37-126">È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="49d37-126">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-information"></a><span data-ttu-id="49d37-127">Per visualizzare le informazioni sulle aree di rete</span><span class="sxs-lookup"><span data-stu-id="49d37-127">To view network region information</span></span>

  - <span data-ttu-id="49d37-128">Per visualizzare informazioni su tutte le aree di rete, digitare il comando seguente in Skype for Business Server Management Shell, quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="49d37-128">To view information about all your network regions, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegion
    
    <span data-ttu-id="49d37-129">Verranno restituite informazioni simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="49d37-129">That will return information similar to this:</span></span>
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

<span data-ttu-id="49d37-130">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span><span class="sxs-lookup"><span data-stu-id="49d37-130">For more information, see the help topic for the [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet.</span></span>


## <a name="create-or-modify-network-regions"></a><span data-ttu-id="49d37-131">Creare o modificare aree di rete</span><span class="sxs-lookup"><span data-stu-id="49d37-131">Create or modify network regions</span></span> 

<span data-ttu-id="49d37-132">Un'area di rete interconnette diverse parti di una rete dislocate su più aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="49d37-132">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="49d37-133">Ogni area di rete deve essere associata a un sito centrale.</span><span class="sxs-lookup"><span data-stu-id="49d37-133">Every network region must be associated with a central site.</span></span> <span data-ttu-id="49d37-134">Il sito centrale è il sito del data center in cui è in esecuzione il servizio dei criteri di larghezza di banda del controllo di ammissione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="49d37-134">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="49d37-135">È possibile utilizzare il Pannello di controllo di Skype for Business Server per configurare le aree di rete.</span><span class="sxs-lookup"><span data-stu-id="49d37-135">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="49d37-136">Queste includono impostazioni che determinano se consentire percorsi alternativi Internet per le connessioni audio e video.</span><span class="sxs-lookup"><span data-stu-id="49d37-136">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="49d37-137">Dal Pannello di controllo di Skype for Business Server puoi creare, modificare o eliminare un'area di rete.</span><span class="sxs-lookup"><span data-stu-id="49d37-137">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="49d37-138">Utilizzare questo argomento per creare e modificare le aree di rete.</span><span class="sxs-lookup"><span data-stu-id="49d37-138">Use this topic to create and modify network regions.</span></span> 

### <a name="to-create-a-network-region"></a><span data-ttu-id="49d37-139">Per creare un'area di rete</span><span class="sxs-lookup"><span data-stu-id="49d37-139">To create a network region</span></span>

1.  <span data-ttu-id="49d37-140">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="49d37-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="49d37-141">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="49d37-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="49d37-142">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Area.**</span><span class="sxs-lookup"><span data-stu-id="49d37-142">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="49d37-143">Nella pagina **Area** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="49d37-143">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="49d37-144">Nella pagina **Nuova area** digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="49d37-144">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="49d37-145">Questo valore deve essere univoco all'interno della distribuzione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="49d37-145">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="49d37-146">Nell'elenco a discesa **Sito centrale** selezionare il sito centrale per questa area di rete.</span><span class="sxs-lookup"><span data-stu-id="49d37-146">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="49d37-p106">La casella di controllo **Abilita percorso alternativo audio** è selezionata per impostazione predefinita. Questo campo determina se le chiamate audio verranno instradate tramite un percorso alternativo se non è disponibile una larghezza di banda adeguata nel percorso principale. Deselezionare questa casella di controllo solo se è necessario disattivare l'offload su Internet. Se alcune delle chiamate vengono effettuate via Internet, questa casella di controllo deve essere selezionata, indipendentemente dalle impostazioni della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="49d37-p106">The **Enable audio alternate path** check box is checked by default. This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path. Clear this check box only if you need to turn off the offload to the Internet. If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="49d37-p107">La casella di controllo **Abilita percorso alternativo video** è selezionata per impostazione predefinita. Questo parametro determina se le chiamate video verranno instradate tramite un percorso alternativo se non è disponibile una larghezza di banda adeguata nel percorso principale. Deselezionare questa casella di controllo solo se è necessario disattivare l'offload su Internet. Se alcune delle chiamate vengono effettuate via Internet, questa casella di controllo deve essere selezionata, indipendentemente dalle impostazioni della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="49d37-p107">The **Enable video alternate path** check box is checked by default. This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path. Clear this check box only if you need to turn off the offload to the Internet. If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="49d37-155">(Facoltativo) Digitare un valore nel campo **Descrizione** per specificare ulteriori informazioni sull'area che non è possibile fornire solo con il nome.</span><span class="sxs-lookup"><span data-stu-id="49d37-155">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="49d37-156">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="49d37-156">Click **Commit**.</span></span>

<span data-ttu-id="49d37-157">La tabella **Siti associati** non viene utilizzata per la creazione di un'area di rete.</span><span class="sxs-lookup"><span data-stu-id="49d37-157">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="49d37-158">Si associa un sito a un'area durante la creazione o la modifica del sito.</span><span class="sxs-lookup"><span data-stu-id="49d37-158">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="49d37-159">Per informazioni dettagliate, vedere [Managing call admission control for sites.](managing-call-admission-control-for-sites.md)</span><span class="sxs-lookup"><span data-stu-id="49d37-159">For details, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>

### <a name="to-modify-a-network-region"></a><span data-ttu-id="49d37-160">Per modificare un'area di rete</span><span class="sxs-lookup"><span data-stu-id="49d37-160">To modify a network region</span></span>

1.  <span data-ttu-id="49d37-161">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="49d37-161">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="49d37-162">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="49d37-162">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="49d37-163">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Area.**</span><span class="sxs-lookup"><span data-stu-id="49d37-163">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="49d37-164">Nella pagina **Area** fare clic sull'area che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="49d37-164">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="49d37-165">Scegliere **Mostra dettagli** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="49d37-165">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="49d37-166">Nella pagina **Modifica area** è possibile modificare le impostazioni per abilitare e disabilitare i percorsi alternativi per audio e video, nonché modificare la descrizione. Per informazioni dettagliate, vedere la sezione "Per creare un'area di rete" più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="49d37-166">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="49d37-167">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="49d37-167">Click **Commit**.</span></span>

<span data-ttu-id="49d37-p109">Non è possibile modificare i **Siti associati** in questa pagina. L'elenco dei siti associati viene fornito per riferimento in modo da sapere quali siti saranno interessati dalla modifica delle impostazioni dell'area.</span><span class="sxs-lookup"><span data-stu-id="49d37-p109">You cannot modify the **Associated sites** on this page. The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>


## <a name="delete-existing-network-regions"></a><span data-ttu-id="49d37-170">Eliminare aree di rete esistenti</span><span class="sxs-lookup"><span data-stu-id="49d37-170">Delete existing network regions</span></span> 

<span data-ttu-id="49d37-171">Un'area di rete interconnette diverse parti di una rete dislocate su più aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="49d37-171">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="49d37-172">Ogni area di rete deve essere associata a un sito centrale.</span><span class="sxs-lookup"><span data-stu-id="49d37-172">Every network region must be associated with a central site.</span></span> <span data-ttu-id="49d37-173">Il sito centrale è il sito del data center in cui è in esecuzione il servizio dei criteri di larghezza di banda del controllo di ammissione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="49d37-173">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="49d37-174">È possibile utilizzare il Pannello di controllo di Skype for Business Server per configurare le aree di rete.</span><span class="sxs-lookup"><span data-stu-id="49d37-174">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="49d37-175">Queste includono impostazioni che determinano se consentire percorsi alternativi Internet per le connessioni audio e video.</span><span class="sxs-lookup"><span data-stu-id="49d37-175">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="49d37-176">Dal Pannello di controllo di Skype for Business Server puoi creare, modificare o eliminare un'area di rete.</span><span class="sxs-lookup"><span data-stu-id="49d37-176">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="49d37-177">Utilizzare questo argomento per eliminare le aree di rete esistenti.</span><span class="sxs-lookup"><span data-stu-id="49d37-177">Use this topic to delete existing network regions.</span></span> 

### <a name="to-delete-a-network-region"></a><span data-ttu-id="49d37-178">Per eliminare un'area di rete</span><span class="sxs-lookup"><span data-stu-id="49d37-178">To delete a network region</span></span>

1.  <span data-ttu-id="49d37-179">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="49d37-179">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="49d37-180">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="49d37-180">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="49d37-181">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Area.**</span><span class="sxs-lookup"><span data-stu-id="49d37-181">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="49d37-182">Nella pagina **Area** fare clic sull'area che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="49d37-182">On the **Region** page, click the region you want to delete.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="49d37-p111">È possibile eliminare più aree contemporaneamente. A tale scopo, premere CTRL e selezionare più aree tenendo premuto CTRL. Per selezionare tutte le aree, scegliere **Seleziona tutto** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="49d37-p111">You can delete more than one region at a time. To do this, press CTRL and select multiple regions while holding down the CTRL key. Or, to select all regions, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="49d37-186">Scegliere **Elimina** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="49d37-186">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="49d37-187">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="49d37-187">Click **OK**.</span></span>


    > [!WARNING]  
    > <span data-ttu-id="49d37-188">Non è possibile rimuovere un'area di rete se è associata a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="49d37-188">A network region cannot be removed if it is associated with a network site.</span></span> <span data-ttu-id="49d37-189">Se si tenta di rimuovere un'area associata a un sito, verrà visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="49d37-189">If you attempt to remove a region associated with a site, you will receive an error message.</span></span> <span data-ttu-id="49d37-190">Per scoprire se un'area è associata a siti, selezionare l'area e quindi scegliere **Mostra dettagli** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="49d37-190">To see if a region is associated with any sites, select the region and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="49d37-191">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49d37-191">See Also</span></span>

[<span data-ttu-id="49d37-192">Gestione delle route area di rete</span><span class="sxs-lookup"><span data-stu-id="49d37-192">Managing network region routes</span></span>](managing-network-region-routes.md)

[<span data-ttu-id="49d37-193">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="49d37-193">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  

[<span data-ttu-id="49d37-194">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="49d37-194">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  

[<span data-ttu-id="49d37-195">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="49d37-195">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  

[<span data-ttu-id="49d37-196">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="49d37-196">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  

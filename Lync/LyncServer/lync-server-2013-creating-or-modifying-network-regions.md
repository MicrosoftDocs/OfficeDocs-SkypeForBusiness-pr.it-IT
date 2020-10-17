---
title: 'Lync Server 2013: creazione o modifica di aree di rete'
description: 'Lync Server 2013: creazione o modifica di aree di rete.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network regions
ms:assetid: bd08bb66-5976-4ece-b45c-7de19569f814
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182579(v=OCS.15)
ms:contentKeyID: 48185266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b02a041272f0df27d2133ca26096caeb01816c7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544032"
---
# <a name="creating-or-modifying-network-regions-in-lync-server-2013"></a><span data-ttu-id="921a1-103">Creazione o modifica di aree di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="921a1-103">Creating or modifying network regions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="921a1-104">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="921a1-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="921a1-105">Un'area di rete interconnette diverse parti di una rete dislocate su più aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="921a1-105">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="921a1-106">Ogni area di rete deve essere associata a un sito centrale.</span><span class="sxs-lookup"><span data-stu-id="921a1-106">Every network region must be associated with a central site.</span></span> <span data-ttu-id="921a1-107">Il sito centrale è il sito del data center in cui è in esecuzione il servizio dei criteri di larghezza di banda del controllo di ammissione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="921a1-107">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="921a1-108">È possibile utilizzare il pannello di controllo di Lync Server per configurare le aree di rete.</span><span class="sxs-lookup"><span data-stu-id="921a1-108">You can use Lync Server Control Panel to configure network regions.</span></span> <span data-ttu-id="921a1-109">Queste includono impostazioni che determinano se consentire percorsi alternativi Internet per le connessioni audio e video.</span><span class="sxs-lookup"><span data-stu-id="921a1-109">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="921a1-110">Dal pannello di controllo di Lync Server, è possibile creare, modificare o eliminare un'area di rete.</span><span class="sxs-lookup"><span data-stu-id="921a1-110">From the Lync Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="921a1-111">Utilizzare questo argomento per creare e modificare le aree di rete.</span><span class="sxs-lookup"><span data-stu-id="921a1-111">Use this topic to create and modify network regions.</span></span> <span data-ttu-id="921a1-112">Per informazioni dettagliate sull'eliminazione di aree di rete esistenti, vedere [eliminazione di aree di rete esistenti in Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md).</span><span class="sxs-lookup"><span data-stu-id="921a1-112">For details about deleting existing network regions, see [Deleting existing network regions in Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md).</span></span>

<div>

## <a name="to-create-a-network-region"></a><span data-ttu-id="921a1-113">Per creare un'area di rete</span><span class="sxs-lookup"><span data-stu-id="921a1-113">To create a network region</span></span>

1.  <span data-ttu-id="921a1-114">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="921a1-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="921a1-115">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="921a1-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="921a1-116">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="921a1-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="921a1-117">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Area**.</span><span class="sxs-lookup"><span data-stu-id="921a1-117">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="921a1-118">Nella pagina **Area** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="921a1-118">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="921a1-119">Nella pagina **Nuova area** digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="921a1-119">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="921a1-120">Questo valore deve essere univoco all'interno della distribuzione di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="921a1-120">This value must be unique within your Microsoft Lync Server 2013 deployment.</span></span>

6.  <span data-ttu-id="921a1-121">Nell'elenco a discesa **Sito centrale** selezionare il sito centrale per questa area di rete.</span><span class="sxs-lookup"><span data-stu-id="921a1-121">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="921a1-p104">La casella di controllo **Abilita percorso alternativo audio** è selezionata per impostazione predefinita. Questo campo determina se le chiamate audio verranno instradate tramite un percorso alternativo se non è disponibile una larghezza di banda adeguata nel percorso principale. Deselezionare questa casella di controllo solo se è necessario disattivare l'offload su Internet. Se alcune delle chiamate vengono effettuate via Internet, questa casella di controllo deve essere selezionata, indipendentemente dalle impostazioni della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="921a1-p104">The **Enable audio alternate path** check box is checked by default. This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path. Clear this check box only if you need to turn off the offload to the Internet. If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="921a1-p105">La casella di controllo **Abilita percorso alternativo video** è selezionata per impostazione predefinita. Questo parametro determina se le chiamate video verranno instradate tramite un percorso alternativo se non è disponibile una larghezza di banda adeguata nel percorso principale. Deselezionare questa casella di controllo solo se è necessario disattivare l'offload su Internet. Se alcune delle chiamate vengono effettuate via Internet, questa casella di controllo deve essere selezionata, indipendentemente dalle impostazioni della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="921a1-p105">The **Enable video alternate path** check box is checked by default. This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path. Clear this check box only if you need to turn off the offload to the Internet. If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="921a1-130">(Facoltativo) Digitare un valore nel campo **Descrizione** per specificare ulteriori informazioni sull'area che non è possibile fornire solo con il nome.</span><span class="sxs-lookup"><span data-stu-id="921a1-130">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="921a1-131">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="921a1-131">Click **Commit**.</span></span>

<span data-ttu-id="921a1-132">La tabella **Siti associati** non viene utilizzata per la creazione di un'area di rete.</span><span class="sxs-lookup"><span data-stu-id="921a1-132">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="921a1-133">Si associa un sito a un'area durante la creazione o la modifica del sito.</span><span class="sxs-lookup"><span data-stu-id="921a1-133">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="921a1-134">Per ulteriori informazioni, vedere [creazione o modifica di siti di rete in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span><span class="sxs-lookup"><span data-stu-id="921a1-134">For details, see [Creating or modifying network sites in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span></span>

</div>

<div>

## <a name="to-modify-a-network-region"></a><span data-ttu-id="921a1-135">Per modificare un'area di rete</span><span class="sxs-lookup"><span data-stu-id="921a1-135">To modify a network region</span></span>

1.  <span data-ttu-id="921a1-136">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="921a1-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="921a1-137">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="921a1-137">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="921a1-138">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="921a1-138">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="921a1-139">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Area**.</span><span class="sxs-lookup"><span data-stu-id="921a1-139">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="921a1-140">Nella pagina **Area** fare clic sull'area che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="921a1-140">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="921a1-141">Scegliere **Mostra dettagli** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="921a1-141">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="921a1-142">Nella pagina **Modifica area** è possibile modificare le impostazioni per abilitare e disabilitare i percorsi alternativi per audio e video, nonché modificare la descrizione. Per informazioni dettagliate, vedere la sezione "Per creare un'area di rete" più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="921a1-142">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="921a1-143">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="921a1-143">Click **Commit**.</span></span>

<span data-ttu-id="921a1-p108">Non è possibile modificare i **Siti associati** in questa pagina. L'elenco dei siti associati viene fornito per riferimento in modo da sapere quali siti saranno interessati dalla modifica delle impostazioni dell'area.</span><span class="sxs-lookup"><span data-stu-id="921a1-p108">You cannot modify the **Associated sites** on this page. The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="921a1-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="921a1-146">See Also</span></span>


[<span data-ttu-id="921a1-147">Eliminazione di aree di rete esistenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="921a1-147">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)  
[<span data-ttu-id="921a1-148">Configurare le aree di rete per il servizio di controllo di ammissione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="921a1-148">Configure network regions for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-regions-for-cac.md)  


[<span data-ttu-id="921a1-149">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="921a1-149">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  
[<span data-ttu-id="921a1-150">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="921a1-150">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  
[<span data-ttu-id="921a1-151">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="921a1-151">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  
[<span data-ttu-id="921a1-152">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="921a1-152">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


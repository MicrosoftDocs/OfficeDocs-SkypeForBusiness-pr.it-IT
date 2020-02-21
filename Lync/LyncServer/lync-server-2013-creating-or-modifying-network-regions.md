---
title: 'Lync Server 2013: creazione o modifica di aree di rete'
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
ms.openlocfilehash: 52518c76efdb302661ed3f097cb382d399299798
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-regions-in-lync-server-2013"></a><span data-ttu-id="3f798-102">Creazione o modifica di aree di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f798-102">Creating or modifying network regions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f798-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3f798-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3f798-104">Un'area di rete interconnette diverse parti di una rete dislocate su più aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="3f798-104">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="3f798-105">Ogni area di rete deve essere associata a un sito centrale.</span><span class="sxs-lookup"><span data-stu-id="3f798-105">Every network region must be associated with a central site.</span></span> <span data-ttu-id="3f798-106">Il sito centrale è il sito del data center in cui è in esecuzione il servizio dei criteri di larghezza di banda del controllo di ammissione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="3f798-106">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="3f798-107">È possibile utilizzare il pannello di controllo di Lync Server per configurare le aree di rete.</span><span class="sxs-lookup"><span data-stu-id="3f798-107">You can use Lync Server Control Panel to configure network regions.</span></span> <span data-ttu-id="3f798-108">Queste includono impostazioni che determinano se consentire percorsi alternativi Internet per le connessioni audio e video.</span><span class="sxs-lookup"><span data-stu-id="3f798-108">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="3f798-109">Dal pannello di controllo di Lync Server, è possibile creare, modificare o eliminare un'area di rete.</span><span class="sxs-lookup"><span data-stu-id="3f798-109">From the Lync Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="3f798-110">Utilizzare questo argomento per creare e modificare le aree di rete.</span><span class="sxs-lookup"><span data-stu-id="3f798-110">Use this topic to create and modify network regions.</span></span> <span data-ttu-id="3f798-111">Per informazioni dettagliate sull'eliminazione di aree di rete esistenti, vedere [eliminazione di aree di rete esistenti in Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md).</span><span class="sxs-lookup"><span data-stu-id="3f798-111">For details about deleting existing network regions, see [Deleting existing network regions in Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md).</span></span>

<div>

## <a name="to-create-a-network-region"></a><span data-ttu-id="3f798-112">Per creare un'area di rete</span><span class="sxs-lookup"><span data-stu-id="3f798-112">To create a network region</span></span>

1.  <span data-ttu-id="3f798-113">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="3f798-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3f798-114">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3f798-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3f798-115">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3f798-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3f798-116">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Area**.</span><span class="sxs-lookup"><span data-stu-id="3f798-116">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="3f798-117">Nella pagina **Area** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="3f798-117">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="3f798-118">Nella pagina **Nuova area** digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="3f798-118">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="3f798-119">Questo valore deve essere univoco all'interno della distribuzione di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3f798-119">This value must be unique within your Microsoft Lync Server 2013 deployment.</span></span>

6.  <span data-ttu-id="3f798-120">Nell'elenco a discesa **Sito centrale** selezionare il sito centrale per questa area di rete.</span><span class="sxs-lookup"><span data-stu-id="3f798-120">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="3f798-p104">La casella di controllo **Abilita percorso alternativo audio** è selezionata per impostazione predefinita. Questo campo determina se le chiamate audio verranno instradate tramite un percorso alternativo se non è disponibile una larghezza di banda adeguata nel percorso principale. Deselezionare questa casella di controllo solo se è necessario disattivare l'offload su Internet. Se alcune delle chiamate vengono effettuate via Internet, questa casella di controllo deve essere selezionata, indipendentemente dalle impostazioni della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="3f798-p104">The **Enable audio alternate path** check box is checked by default. This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path. Clear this check box only if you need to turn off the offload to the Internet. If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="3f798-p105">La casella di controllo **Abilita percorso alternativo video** è selezionata per impostazione predefinita. Questo parametro determina se le chiamate video verranno instradate tramite un percorso alternativo se non è disponibile una larghezza di banda adeguata nel percorso principale. Deselezionare questa casella di controllo solo se è necessario disattivare l'offload su Internet. Se alcune delle chiamate vengono effettuate via Internet, questa casella di controllo deve essere selezionata, indipendentemente dalle impostazioni della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="3f798-p105">The **Enable video alternate path** check box is checked by default. This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path. Clear this check box only if you need to turn off the offload to the Internet. If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="3f798-129">(Facoltativo) Digitare un valore nel campo **Descrizione** per specificare ulteriori informazioni sull'area che non è possibile fornire solo con il nome.</span><span class="sxs-lookup"><span data-stu-id="3f798-129">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="3f798-130">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="3f798-130">Click **Commit**.</span></span>

<span data-ttu-id="3f798-131">La tabella **Siti associati** non viene utilizzata per la creazione di un'area di rete.</span><span class="sxs-lookup"><span data-stu-id="3f798-131">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="3f798-132">Si associa un sito a un'area durante la creazione o la modifica del sito.</span><span class="sxs-lookup"><span data-stu-id="3f798-132">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="3f798-133">Per ulteriori informazioni, vedere [creazione o modifica di siti di rete in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span><span class="sxs-lookup"><span data-stu-id="3f798-133">For details, see [Creating or modifying network sites in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span></span>

</div>

<div>

## <a name="to-modify-a-network-region"></a><span data-ttu-id="3f798-134">Per modificare un'area di rete</span><span class="sxs-lookup"><span data-stu-id="3f798-134">To modify a network region</span></span>

1.  <span data-ttu-id="3f798-135">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="3f798-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3f798-136">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3f798-136">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3f798-137">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3f798-137">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3f798-138">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Area**.</span><span class="sxs-lookup"><span data-stu-id="3f798-138">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="3f798-139">Nella pagina **Area** fare clic sull'area che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="3f798-139">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="3f798-140">Scegliere **Mostra dettagli** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="3f798-140">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="3f798-141">Nella pagina **Modifica area** è possibile modificare le impostazioni per abilitare e disabilitare i percorsi alternativi per audio e video, nonché modificare la descrizione. Per informazioni dettagliate, vedere la sezione "Per creare un'area di rete" più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="3f798-141">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="3f798-142">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="3f798-142">Click **Commit**.</span></span>

<span data-ttu-id="3f798-p108">Non è possibile modificare i **Siti associati** in questa pagina. L'elenco dei siti associati viene fornito per riferimento in modo da sapere quali siti saranno interessati dalla modifica delle impostazioni dell'area.</span><span class="sxs-lookup"><span data-stu-id="3f798-p108">You cannot modify the **Associated sites** on this page. The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3f798-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f798-145">See Also</span></span>


[<span data-ttu-id="3f798-146">Eliminazione di aree di rete esistenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f798-146">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)  
[<span data-ttu-id="3f798-147">Configurare le aree di rete per il servizio di controllo di ammissione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f798-147">Configure network regions for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-regions-for-cac.md)  


[<span data-ttu-id="3f798-148">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="3f798-148">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  
[<span data-ttu-id="3f798-149">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="3f798-149">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  
[<span data-ttu-id="3f798-150">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="3f798-150">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  
[<span data-ttu-id="3f798-151">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="3f798-151">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


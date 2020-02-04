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
ms.openlocfilehash: fbebccd02b74c4fbfb69225a6397c1dd7cef862d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756280"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-regions-in-lync-server-2013"></a><span data-ttu-id="e4188-102">Creazione o modifica di aree di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4188-102">Creating or modifying network regions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4188-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e4188-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e4188-104">Un'area geografica di rete interconnette varie parti di una rete in più aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="e4188-104">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="e4188-105">Ogni area di rete deve essere associata a un sito centrale.</span><span class="sxs-lookup"><span data-stu-id="e4188-105">Every network region must be associated with a central site.</span></span> <span data-ttu-id="e4188-106">Il sito centrale è il sito centro dati in cui è in uso il servizio criteri di larghezza di banda di controllo delle chiamate (CAC).</span><span class="sxs-lookup"><span data-stu-id="e4188-106">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="e4188-107">È possibile usare il pannello di controllo di Lync Server per configurare le aree di rete.</span><span class="sxs-lookup"><span data-stu-id="e4188-107">You can use Lync Server Control Panel to configure network regions.</span></span> <span data-ttu-id="e4188-108">Le aree di rete includono impostazioni che determinano se i percorsi alternativi tramite Internet sono consentiti per le connessioni audio e video.</span><span class="sxs-lookup"><span data-stu-id="e4188-108">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="e4188-109">Dal pannello di controllo di Lync Server è possibile creare, modificare o eliminare un'area geografica di rete.</span><span class="sxs-lookup"><span data-stu-id="e4188-109">From the Lync Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="e4188-110">Usare questo argomento per creare e modificare le aree di rete.</span><span class="sxs-lookup"><span data-stu-id="e4188-110">Use this topic to create and modify network regions.</span></span> <span data-ttu-id="e4188-111">Per informazioni dettagliate sull'eliminazione delle aree di rete esistenti, vedere [eliminazione di aree di rete esistenti in Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md).</span><span class="sxs-lookup"><span data-stu-id="e4188-111">For details about deleting existing network regions, see [Deleting existing network regions in Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md).</span></span>

<div>

## <a name="to-create-a-network-region"></a><span data-ttu-id="e4188-112">Per creare un'area di rete</span><span class="sxs-lookup"><span data-stu-id="e4188-112">To create a network region</span></span>

1.  <span data-ttu-id="e4188-113">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="e4188-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e4188-114">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e4188-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e4188-115">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e4188-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e4188-116">Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **area geografica**.</span><span class="sxs-lookup"><span data-stu-id="e4188-116">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="e4188-117">Nella pagina **area** fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="e4188-117">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="e4188-118">Nella pagina **nuova area** Digitare un valore nel campo **nome** .</span><span class="sxs-lookup"><span data-stu-id="e4188-118">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="e4188-119">Questo valore deve essere univoco all'interno della distribuzione di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e4188-119">This value must be unique within your Microsoft Lync Server 2013 deployment.</span></span>

6.  <span data-ttu-id="e4188-120">Nell'elenco a discesa **sito centrale** selezionare il sito centrale per l'area di rete.</span><span class="sxs-lookup"><span data-stu-id="e4188-120">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="e4188-121">La casella di controllo **Attiva percorso alternativo audio** è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="e4188-121">The **Enable audio alternate path** check box is checked by default.</span></span> <span data-ttu-id="e4188-122">Questo campo determina se le chiamate audio verranno instradate tramite un percorso alternativo se la larghezza di banda adeguata non esiste nel percorso principale.</span><span class="sxs-lookup"><span data-stu-id="e4188-122">This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="e4188-123">Deselezionare questa casella di controllo solo se è necessario disattivare l'offload su Internet.</span><span class="sxs-lookup"><span data-stu-id="e4188-123">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="e4188-124">Se le chiamate saranno chiamate Internet, questa casella di controllo deve essere selezionata, indipendentemente dalle impostazioni di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="e4188-124">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="e4188-125">La casella di controllo **Attiva percorso alternativo video** è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="e4188-125">The **Enable video alternate path** check box is checked by default.</span></span> <span data-ttu-id="e4188-126">Questo campo determina se le videochiamate verranno instradate tramite un percorso alternativo se la larghezza di banda adeguata non esiste nel percorso principale.</span><span class="sxs-lookup"><span data-stu-id="e4188-126">This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="e4188-127">Deselezionare questa casella di controllo solo se è necessario disattivare l'offload su Internet.</span><span class="sxs-lookup"><span data-stu-id="e4188-127">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="e4188-128">Se le chiamate saranno chiamate Internet, questa casella di controllo deve essere selezionata, indipendentemente dalle impostazioni di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="e4188-128">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="e4188-129">Opzionale Digitare un valore nel campo **Description** per ottenere altre informazioni sull'area geografica che non può essere espressa solo dal nome.</span><span class="sxs-lookup"><span data-stu-id="e4188-129">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="e4188-130">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="e4188-130">Click **Commit**.</span></span>

<span data-ttu-id="e4188-131">La tabella **siti associati** non viene usata per la creazione di un'area di rete.</span><span class="sxs-lookup"><span data-stu-id="e4188-131">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="e4188-132">Quando si crea o si modifica il sito, si associa un sito a un'area geografica.</span><span class="sxs-lookup"><span data-stu-id="e4188-132">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="e4188-133">Per informazioni dettagliate, vedere [creazione o modifica di siti di rete in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span><span class="sxs-lookup"><span data-stu-id="e4188-133">For details, see [Creating or modifying network sites in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span></span>

</div>

<div>

## <a name="to-modify-a-network-region"></a><span data-ttu-id="e4188-134">Per modificare un'area di rete</span><span class="sxs-lookup"><span data-stu-id="e4188-134">To modify a network region</span></span>

1.  <span data-ttu-id="e4188-135">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="e4188-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e4188-136">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e4188-136">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e4188-137">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e4188-137">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e4188-138">Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **area geografica**.</span><span class="sxs-lookup"><span data-stu-id="e4188-138">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="e4188-139">Nella pagina **area** fare clic sull'area che si vuole modificare.</span><span class="sxs-lookup"><span data-stu-id="e4188-139">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="e4188-140">Nel menu **modifica** fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="e4188-140">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="e4188-141">Nella pagina **modifica area** è possibile modificare le impostazioni per l'abilitazione e la disabilitazione di percorsi alternativi audio e video e modificare la descrizione (per informazioni dettagliate, vedere la sezione "per creare un'area di rete" in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="e4188-141">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="e4188-142">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="e4188-142">Click **Commit**.</span></span>

<span data-ttu-id="e4188-143">Non è possibile modificare i **siti associati** in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="e4188-143">You cannot modify the **Associated sites** on this page.</span></span> <span data-ttu-id="e4188-144">L'elenco dei siti associati viene fornito per il riferimento, in modo da sapere quali siti verranno modificati quando si modificano le impostazioni dell'area geografica.</span><span class="sxs-lookup"><span data-stu-id="e4188-144">The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e4188-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4188-145">See Also</span></span>


[<span data-ttu-id="e4188-146">Eliminazione delle aree di rete esistenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4188-146">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)  
[<span data-ttu-id="e4188-147">Configurare le aree di rete per CAC in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4188-147">Configure network regions for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-regions-for-cac.md)  


[<span data-ttu-id="e4188-148">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="e4188-148">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  
[<span data-ttu-id="e4188-149">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="e4188-149">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  
[<span data-ttu-id="e4188-150">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="e4188-150">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  
[<span data-ttu-id="e4188-151">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="e4188-151">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


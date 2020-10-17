---
title: 'Lync Server 2013: accertarsi che i dial plan abbiano assegnato aree geografiche'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Make sure dial plans have assigned regions
ms:assetid: 3da3a907-0dbf-4440-b12f-370f94dd4c17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425903(v=OCS.15)
ms:contentKeyID: 48183937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f9f9a67a65b870edd75259bca7c74a1fae2749f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534563"
---
# <a name="make-sure-dial-plans-lync-server-2013-have-assigned-regions"></a><span data-ttu-id="080b2-102">Assicurarsi che i dial plan Lync Server 2013 abbiano assegnato aree geografiche</span><span class="sxs-lookup"><span data-stu-id="080b2-102">Make sure dial plans Lync Server 2013 have assigned regions</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="080b2-103">_**Ultimo argomento modificato:** 2010-11-02_</span><span class="sxs-lookup"><span data-stu-id="080b2-103">_**Topic Last Modified:** 2010-11-02_</span></span>

<span data-ttu-id="080b2-p101">Per i dial plan utilizzati per le conferenze telefoniche con accesso esterno deve essere specificata un'**Area per conferenze telefoniche con accesso esterno**, in modo che i numeri di accesso a tali conferenze vengano associati al dial plan appropriato. Quando si imposta un dial plan, si specifica l'area per conferenze telefoniche con accesso esterno applicabile. Quando quindi si crea il numero di accesso esterno, si selezionano le aree che associano il numero di accesso ai dial plan appropriati.</span><span class="sxs-lookup"><span data-stu-id="080b2-p101">Dial plans that are used for dial-in conferencing need to have a **Dial-in conferencing region** specified to associate dial-in conferencing access numbers with the appropriate dial plan. When you set up a dial plan, you specify the dial-in conferencing region that applies to that dial plan. Then, when you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span>

<span data-ttu-id="080b2-p102">Poiché è importante specificare un'area per tutti i dial plan, è consigliabile utilizzare questa procedura per verificare che tutti i dial plan siano associati ad aree. Questo passaggio è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="080b2-p102">Because it important to specify a region for all dial plans, we recommend that you use this procedure to verify that all dial plans have regions. This step is optional.</span></span>

<span data-ttu-id="080b2-109">Utilizzare il cmdlet **Get-CsDialPlan** per verificare se l'area è impostata per tutti i dial plan di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="080b2-109">Use the **Get-CsDialPlan** cmdlet to verify whether the region is set for all dial-in conferencing dial plans.</span></span> <span data-ttu-id="080b2-110">Se l'area non è inclusa nei dial plan, è possibile utilizzare il cmdlet **Set-CsDialPlan** per impostarla.</span><span class="sxs-lookup"><span data-stu-id="080b2-110">If the region is missing from dial plans, you can use the **Set-CsDialPlan** cmdlet to set the region.</span></span> <span data-ttu-id="080b2-111">È inoltre possibile utilizzare il pannello di controllo di Lync Server per aggiornare l'area in dial plan esistenti.</span><span class="sxs-lookup"><span data-stu-id="080b2-111">You can also use Lync Server Control Panel to update the region in existing dial plans.</span></span> <span data-ttu-id="080b2-112">Per informazioni dettagliate sull'utilizzo del pannello di controllo di Lync Server, vedere [Modify a dial plan in Lync server 2013](lync-server-2013-modify-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="080b2-112">For details about using Lync Server Control Panel, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

<div>

## <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a><span data-ttu-id="080b2-113">Per verificare se nei dial plan è impostata la proprietà relativa all'area</span><span class="sxs-lookup"><span data-stu-id="080b2-113">To verify whether dial plans have the region property set</span></span>

1.  <span data-ttu-id="080b2-114">Eseguire l'accesso al computer come membro del gruppo RTCUniversalServerAdmins oppure del ruolo **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** o **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="080b2-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="080b2-115">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="080b2-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="080b2-116">Al prompt dei comandi eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="080b2-116">Run the following at the command prompt:</span></span>
    
        Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
    
    <span data-ttu-id="080b2-117">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="080b2-117">For example:</span></span>
    
        Get-CsDialPlan
    
    <span data-ttu-id="080b2-118">In questo esempio vengono restituiti tutti i dial plan configurati per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="080b2-118">In this example, all the dial plans configured for your organization are returned.</span></span>

4.  <span data-ttu-id="080b2-119">Esaminare i dial plan restituiti per identificare eventualmente quelli che non includono l'area di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="080b2-119">Review the returned dial plans to identify any that are missing the dial-in conferencing region.</span></span> <span data-ttu-id="080b2-120">Per informazioni dettagliate, vedere la documentazione relativa a Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="080b2-120">For details, see the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-set-the-region-property-for-a-dial-plan"></a><span data-ttu-id="080b2-121">Per impostare la proprietà relativa all'area per un dial plan</span><span class="sxs-lookup"><span data-stu-id="080b2-121">To set the region property for a dial plan</span></span>

1.  <span data-ttu-id="080b2-122">Eseguire l'accesso al computer come membro del gruppo RTCUniversalServerAdmins oppure del ruolo **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** o **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="080b2-122">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="080b2-123">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="080b2-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="080b2-124">Per gli eventuali dial plan che non includono l'area di conferenza telefonica con accesso esterno, eseguire:</span><span class="sxs-lookup"><span data-stu-id="080b2-124">For any dial plans that are missing the dial-in conferencing region, run:</span></span>
    
        Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
    
    <span data-ttu-id="080b2-125">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="080b2-125">For example:</span></span>
    
        Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
    
    <span data-ttu-id="080b2-126">In questo esempio il dial plan con Identity Redmond viene modificato per impostare la proprietà DialinConferencingRegion su "US West Coast".</span><span class="sxs-lookup"><span data-stu-id="080b2-126">In this example, the dial plan with the Identity of Redmond is modified to set the DialinConferencingRegion property to "US West Coast".</span></span> <span data-ttu-id="080b2-127">Per informazioni dettagliate, vedere la documentazione relativa a Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="080b2-127">For details, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


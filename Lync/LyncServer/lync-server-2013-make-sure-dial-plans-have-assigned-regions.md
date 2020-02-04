---
title: 'Lync Server 2013: Verificare che ai dial plan siano state assegnate aree'
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
ms.openlocfilehash: cd8790671157b823464a3b4b594ea8428a888f46
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="make-sure-dial-plans-lync-server-2013-have-assigned-regions"></a><span data-ttu-id="91282-102">Assicurarsi che i dial plan di Lync Server 2013 abbiano assegnato aree geografiche</span><span class="sxs-lookup"><span data-stu-id="91282-102">Make sure dial plans Lync Server 2013 have assigned regions</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91282-103">_**Argomento Ultima modifica:** 2010-11-02_</span><span class="sxs-lookup"><span data-stu-id="91282-103">_**Topic Last Modified:** 2010-11-02_</span></span>

<span data-ttu-id="91282-104">I dial plan usati per i servizi di conferenza telefonica con accesso esterno devono essere specificati nell' **area** dei servizi di conferenza telefonica con accesso esterno con il dial plan appropriato.</span><span class="sxs-lookup"><span data-stu-id="91282-104">Dial plans that are used for dial-in conferencing need to have a **Dial-in conferencing region** specified to associate dial-in conferencing access numbers with the appropriate dial plan.</span></span> <span data-ttu-id="91282-105">Quando si configura un dial plan, si specifica l'area dei servizi di conferenza telefonica con accesso esterno che si applica a tale dial plan.</span><span class="sxs-lookup"><span data-stu-id="91282-105">When you set up a dial plan, you specify the dial-in conferencing region that applies to that dial plan.</span></span> <span data-ttu-id="91282-106">Quando si crea il numero di accesso per la chiamata in ingresso, si selezionano le aree geografiche che associano il numero di accesso con i dial plan appropriati.</span><span class="sxs-lookup"><span data-stu-id="91282-106">Then, when you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span>

<span data-ttu-id="91282-107">Poiché è importante specificare un'area geografica per tutti i dial plan, è consigliabile usare questa procedura per verificare che tutti i dial plan abbiano aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="91282-107">Because it important to specify a region for all dial plans, we recommend that you use this procedure to verify that all dial plans have regions.</span></span> <span data-ttu-id="91282-108">Questo passaggio è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="91282-108">This step is optional.</span></span>

<span data-ttu-id="91282-109">Usa il cmdlet **Get-CsDialPlan** per verificare se l'area geografica è impostata per tutti i piani di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="91282-109">Use the **Get-CsDialPlan** cmdlet to verify whether the region is set for all dial-in conferencing dial plans.</span></span> <span data-ttu-id="91282-110">Se l'area non è presente nei dial plan, è possibile usare il cmdlet **Set-CsDialPlan** per impostare l'area geografica.</span><span class="sxs-lookup"><span data-stu-id="91282-110">If the region is missing from dial plans, you can use the **Set-CsDialPlan** cmdlet to set the region.</span></span> <span data-ttu-id="91282-111">È anche possibile usare il pannello di controllo di Lync Server per aggiornare l'area nei dial plan esistenti.</span><span class="sxs-lookup"><span data-stu-id="91282-111">You can also use Lync Server Control Panel to update the region in existing dial plans.</span></span> <span data-ttu-id="91282-112">Per informazioni dettagliate sull'uso del pannello di controllo di Lync Server, vedere [modificare un dial plan in Lync server 2013](lync-server-2013-modify-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="91282-112">For details about using Lync Server Control Panel, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

<div>

## <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a><span data-ttu-id="91282-113">Per verificare se i dial plan hanno la proprietà Region impostata</span><span class="sxs-lookup"><span data-stu-id="91282-113">To verify whether dial plans have the region property set</span></span>

1.  <span data-ttu-id="91282-114">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo **Cs-voiceadministrator**, **Cs-ServerAdministrator**o **CsAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="91282-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="91282-115">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="91282-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="91282-116">Eseguire la procedura seguente al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="91282-116">Run the following at the command prompt:</span></span>
    
        Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
    
    <span data-ttu-id="91282-117">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="91282-117">For example:</span></span>
    
        Get-CsDialPlan
    
    <span data-ttu-id="91282-118">In questo esempio vengono restituiti tutti i dial plan configurati per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="91282-118">In this example, all the dial plans configured for your organization are returned.</span></span>

4.  <span data-ttu-id="91282-119">Esaminare i piani di chiamata restituiti per identificare gli elementi mancanti nell'area dei servizi di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="91282-119">Review the returned dial plans to identify any that are missing the dial-in conferencing region.</span></span> <span data-ttu-id="91282-120">Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="91282-120">For details, see the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-set-the-region-property-for-a-dial-plan"></a><span data-ttu-id="91282-121">Per impostare la proprietà Region per un dial plan</span><span class="sxs-lookup"><span data-stu-id="91282-121">To set the region property for a dial plan</span></span>

1.  <span data-ttu-id="91282-122">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo **Cs-voiceadministrator**, **Cs-ServerAdministrator**o **CsAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="91282-122">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="91282-123">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="91282-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="91282-124">Per gli eventuali dial plan mancanti dell'area di conferenza telefonica con accesso esterno, eseguire:</span><span class="sxs-lookup"><span data-stu-id="91282-124">For any dial plans that are missing the dial-in conferencing region, run:</span></span>
    
        Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
    
    <span data-ttu-id="91282-125">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="91282-125">For example:</span></span>
    
        Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
    
    <span data-ttu-id="91282-126">In questo esempio, il dial plan con l'identità di Redmond viene modificato per impostare la proprietà DialinConferencingRegion su "US West Coast".</span><span class="sxs-lookup"><span data-stu-id="91282-126">In this example, the dial plan with the Identity of Redmond is modified to set the DialinConferencingRegion property to "US West Coast".</span></span> <span data-ttu-id="91282-127">Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="91282-127">For details, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


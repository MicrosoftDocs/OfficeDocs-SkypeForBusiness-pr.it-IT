---
title: 'Lync Server 2013: creare o modificare un criterio per dispositivi mobili'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a mobility policy
ms:assetid: fc2dfea0-2215-440d-9f4b-7c985da29211
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721946(v=OCS.15)
ms:contentKeyID: 49733884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b4246569ad7d66788cef507488b78567b6b892f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="5f06f-102">Creare o modificare un criterio per dispositivi mobili in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f06f-102">Create or modify a mobility policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f06f-103">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="5f06f-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="5f06f-104">È possibile creare o modificare i criteri di mobilità per consentire agli utenti mobili di utilizzare i dispositivi mobili supportati per le funzionalità di Lync, quali messaggistica istantanea, presenza e contatti.</span><span class="sxs-lookup"><span data-stu-id="5f06f-104">You can create or modify mobility policy to allow mobile users to use supported mobile devices for Lync functionality such as instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="5f06f-105">È possibile creare o modificare i criteri per dispositivi mobili dal pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="5f06f-105">You can create or modify mobility policies from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell</span></span>

<div>

## <a name="to-create-a-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="5f06f-106">Per creare un criterio per dispositivi mobili con il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="5f06f-106">To create a mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="5f06f-107">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="5f06f-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5f06f-108">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5f06f-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5f06f-109">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5f06f-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5f06f-110">Sulla barra di spostamento sinistra fare clic su **client**e quindi sul pulsante di spostamento dei **criteri per dispositivi mobili** .</span><span class="sxs-lookup"><span data-stu-id="5f06f-110">In the left navigation bar, click **Clients**, and then click the **Mobility Policy** navigation button.</span></span>

4.  <span data-ttu-id="5f06f-111">Nella pagina **criteri dispositivi mobili** fare clic su **nuovo**e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5f06f-111">On the **Mobility Policy** page, click **New**, and do one of the following:</span></span>
    
    1.  <span data-ttu-id="5f06f-112">Per creare un criterio per dispositivi mobili per il sito, fare clic su **criteri sito**, fare clic su un sito, fare clic su **OK**, rivedere le impostazioni predefinite e, se si desidera, apportare eventuali modifiche.</span><span class="sxs-lookup"><span data-stu-id="5f06f-112">To create a site mobility policy, click **Site policy**, click a site, click **OK**, review the default settings, and, if you want to, make any changes.</span></span>
    
    2.  <span data-ttu-id="5f06f-113">Per creare un criterio per dispositivi mobili per gli utenti, fare clic su **criteri utente**, digitare un nome, esaminare le impostazioni predefinite e, se lo si desidera, apportare eventuali modifiche.</span><span class="sxs-lookup"><span data-stu-id="5f06f-113">To create a user mobility policy, click **User policy**, type a name, review the default settings, and if you want to, make any changes.</span></span>

5.  <span data-ttu-id="5f06f-114">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="5f06f-114">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="5f06f-115">Per modificare un criterio per dispositivi mobili con il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="5f06f-115">To modify a mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="5f06f-116">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="5f06f-116">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5f06f-117">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5f06f-117">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5f06f-118">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5f06f-118">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5f06f-119">Sulla barra di spostamento sinistra fare clic su **client**e quindi sul pulsante di spostamento dei **criteri per dispositivi mobili** .</span><span class="sxs-lookup"><span data-stu-id="5f06f-119">In the left navigation bar, click **Clients**, and then click the **Mobility Policy** navigation button.</span></span>

4.  <span data-ttu-id="5f06f-120">Nella pagina **criteri dispositivi mobili** fare clic su uno dei criteri per dispositivi mobili esistenti.</span><span class="sxs-lookup"><span data-stu-id="5f06f-120">On the **Mobility Policy** page, click one of the existing mobility policies.</span></span>

5.  <span data-ttu-id="5f06f-121">Scegliere **Mostra dettagli** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="5f06f-121">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="5f06f-122">Modificare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="5f06f-122">Edit any of the settings.</span></span>

7.  <span data-ttu-id="5f06f-123">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="5f06f-123">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5f06f-124">Creazione di criteri di accesso esterno tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5f06f-124">Creating External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="5f06f-125">È possibile creare i criteri per dispositivi mobili (nell'ambito del sito o nell'ambito per utente) utilizzando Windows PowerShell e il cmdlet **New-CsMobilityPolicy** .</span><span class="sxs-lookup"><span data-stu-id="5f06f-125">You can create mobility policies (at the site scope or the per-user scope) by using Windows PowerShell and the **New-CsMobilityPolicy** cmdlet.</span></span> <span data-ttu-id="5f06f-126">Inoltre, è possibile utilizzare il cmdlet **Set-CsMobilityPolicy** per modificare i criteri esistenti, inclusi i criteri globali.</span><span class="sxs-lookup"><span data-stu-id="5f06f-126">Additionally, you can use the **Set-CsMobilityPolicy** cmdlet to modify any of your existing policies, including the global policy.</span></span> <span data-ttu-id="5f06f-127">Questi cmdlet possono essere eseguiti da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5f06f-127">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="5f06f-128">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="5f06f-128">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-mobility-policy-at-the-site-scope"></a><span data-ttu-id="5f06f-129">Per creare un criterio per dispositivi mobili nell'ambito del sito</span><span class="sxs-lookup"><span data-stu-id="5f06f-129">To create a mobility policy at the site scope</span></span>

  - <span data-ttu-id="5f06f-130">Questo comando consente di creare un nuovo criterio per dispositivi mobili per il sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="5f06f-130">This command creates a new mobility policy for the Redmond site:</span></span>
    
        New-CsMobilityPolicy -Identity "site:Redmond"
    
    <span data-ttu-id="5f06f-131">Poiché nel comando precedente non sono stati specificati parametri (oltre al parametro Identity obbligatorio), i criteri utilizzeranno i valori predefiniti per tutte le proprietà.</span><span class="sxs-lookup"><span data-stu-id="5f06f-131">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the policies will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-create-a-mobility-policy-at-the-per-user-scope"></a><span data-ttu-id="5f06f-132">Per creare un criterio per dispositivi mobili nell'ambito per utente</span><span class="sxs-lookup"><span data-stu-id="5f06f-132">To create a mobility policy at the per-user scope</span></span>

  - <span data-ttu-id="5f06f-133">Per creare un criterio per dispositivi mobili nell'ambito per utente, specificare un'identità univoca per il criterio:</span><span class="sxs-lookup"><span data-stu-id="5f06f-133">To create a mobility policy at the per-user scope, specify a unique Identity for the policy:</span></span>
    
        New-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-a-mobility-policy"></a><span data-ttu-id="5f06f-134">Per modificare un singolo valore di proprietà durante la creazione di un criterio per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="5f06f-134">To change a single property value when creating a mobility policy</span></span>

  - <span data-ttu-id="5f06f-135">Per creare criteri che utilizzano valori di proprietà diversi, includere il parametro e il valore del parametro corretti.</span><span class="sxs-lookup"><span data-stu-id="5f06f-135">To create policies that use different property values, include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="5f06f-136">Ad esempio, questo comando consente di creare i criteri per dispositivi mobili che disabilitano la chiamata tramite lavoro:</span><span class="sxs-lookup"><span data-stu-id="5f06f-136">For example, this command creates mobility policy that disables Call via Work:</span></span>
    
        New-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-a-mobility-policy"></a><span data-ttu-id="5f06f-137">Per modificare più valori di proprietà durante la creazione di un criterio per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="5f06f-137">To change multiple property values when creating a mobility policy</span></span>

  - <span data-ttu-id="5f06f-138">È possibile modificare più valori di proprietà includendo più parametri.</span><span class="sxs-lookup"><span data-stu-id="5f06f-138">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="5f06f-139">Ad esempio, questo comando consente di creare un criterio che Disabilita sia la mobilità che la chiamata tramite lavoro:</span><span class="sxs-lookup"><span data-stu-id="5f06f-139">For example, this command creates a policy that disables both mobility and Call via Work:</span></span>
    
        New-CsMobilityPolicy "site:Redmond" -EnableMobility $False -EnableOutsideVoice $False

</div>

<span data-ttu-id="5f06f-140">Per ulteriori informazioni, vedere l'argomento della Guida relativo ai cmdlet [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) e [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy) .</span><span class="sxs-lookup"><span data-stu-id="5f06f-140">For details, see the Help topic for the [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) and the [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy) cmdlets.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5f06f-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f06f-141">See Also</span></span>


[<span data-ttu-id="5f06f-142">Configurazione di criteri per dispositivi mobili in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f06f-142">Configuring mobility policy in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: visualizzazione delle informazioni sul profilo dei criteri di larghezza di banda di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing network bandwidth policy profile information
ms:assetid: eed453fc-04e9-4971-959c-6fad54bf1c96
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721931(v=OCS.15)
ms:contentKeyID: 49733866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 513bd20e9a1ecd40f061c4873e7da8bff4738f36
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985037"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-bandwidth-policy-profile-information-in-lync-server-2013"></a><span data-ttu-id="9fb9f-102">Visualizzazione delle informazioni del profilo dei criteri di larghezza di banda di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fb9f-102">Viewing network bandwidth policy profile information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9fb9f-103">_**Argomento Ultima modifica:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="9fb9f-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="9fb9f-104">Nell'ambito del controllo di ammissione di chiamata (CAC) viene usato un criterio di larghezza di banda per definire le limitazioni della larghezza di banda per determinate modalità.</span><span class="sxs-lookup"><span data-stu-id="9fb9f-104">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="9fb9f-105">In Microsoft Lync Server 2013 solo le modalità audio e video possono essere assegnate alle limitazioni della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="9fb9f-105">In Microsoft Lync Server 2013, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="9fb9f-106">Puoi impostare limitazioni generali della larghezza di banda e limitazioni della sessione.</span><span class="sxs-lookup"><span data-stu-id="9fb9f-106">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="9fb9f-107">È possibile usare il pannello di controllo di Lync Server per creare, modificare o eliminare un profilo contenitore per questi criteri.</span><span class="sxs-lookup"><span data-stu-id="9fb9f-107">You can use the Lync Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="9fb9f-108">Ogni profilo dei criteri di larghezza di banda può essere associato a uno o più siti di rete.</span><span class="sxs-lookup"><span data-stu-id="9fb9f-108">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="9fb9f-109">Usare le procedure seguenti per visualizzare un profilo dei criteri di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="9fb9f-109">Use the following procedures to view a bandwidth policy profile.</span></span> <span data-ttu-id="9fb9f-110">Per creare o modificare un profilo dei criteri di larghezza di banda, vedere [creazione o modifica dei profili dei criteri di larghezza di banda in Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="9fb9f-110">To create or modify a bandwidth policy profile, see [Creating or modifying bandwidth policy profiles in Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).</span></span>

<div>

## <a name="to-view-a-bandwidth-policy-profile"></a><span data-ttu-id="9fb9f-111">Per visualizzare un profilo dei criteri di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="9fb9f-111">To view a bandwidth policy profile</span></span>

1.  <span data-ttu-id="9fb9f-112">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="9fb9f-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9fb9f-113">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9fb9f-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9fb9f-114">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9fb9f-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9fb9f-115">Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **criteri larghezza di banda**.</span><span class="sxs-lookup"><span data-stu-id="9fb9f-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="9fb9f-116">Nella pagina **criteri di larghezza di banda** fare clic sul profilo dei criteri di larghezza di banda che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="9fb9f-116">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to view.</span></span>

5.  <span data-ttu-id="9fb9f-117">Nel menu **modifica** fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="9fb9f-117">On the **Edit** menu, click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9fb9f-118">Visualizzazione delle informazioni del profilo dei criteri di larghezza di banda di rete tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9fb9f-118">Viewing Network Bandwidth Policy Profile Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9fb9f-119">I profili di larghezza di banda di rete possono essere visualizzati usando Windows PowerShell e il cmdlet Get-CsNetworkBandwidthPolicyProfile.</span><span class="sxs-lookup"><span data-stu-id="9fb9f-119">Network bandwidth profiles can be viewed by using Windows PowerShell and the Get-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="9fb9f-120">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9fb9f-120">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9fb9f-121">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="9fb9f-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="9fb9f-122">Per visualizzare le informazioni sul profilo dei criteri di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="9fb9f-122">To view network bandwidth policy profile information</span></span>

  - <span data-ttu-id="9fb9f-123">Per visualizzare informazioni su tutti i profili dei criteri di larghezza di banda della rete, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="9fb9f-123">To view information about all your network bandwidth policy profiles, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkBandwidthPolicyProfile
    
    <span data-ttu-id="9fb9f-124">Questo restituirà informazioni simili alla seguente:</span><span class="sxs-lookup"><span data-stu-id="9fb9f-124">That will return information similar to this:</span></span>
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :

</div>

<span data-ttu-id="9fb9f-125">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) .</span><span class="sxs-lookup"><span data-stu-id="9fb9f-125">For more information, see the help topic for the [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9fb9f-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9fb9f-126">See Also</span></span>


[<span data-ttu-id="9fb9f-127">Creazione o modifica dei profili dei criteri di larghezza di banda in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fb9f-127">Creating or modifying bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[<span data-ttu-id="9fb9f-128">Eliminazione dei profili dei criteri di larghezza di banda di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fb9f-128">Deleting network bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[<span data-ttu-id="9fb9f-129">Configurare il controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fb9f-129">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


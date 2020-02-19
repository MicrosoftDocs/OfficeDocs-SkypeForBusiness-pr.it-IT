---
title: 'Lync Server 2013: visualizzazione delle informazioni sul profilo del criterio larghezza di banda di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network bandwidth policy profile information
ms:assetid: eed453fc-04e9-4971-959c-6fad54bf1c96
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721931(v=OCS.15)
ms:contentKeyID: 49733866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51e0ec43758823666809321c2abe424ce7f480ef
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-network-bandwidth-policy-profile-information-in-lync-server-2013"></a><span data-ttu-id="9a625-102">Visualizzazione delle informazioni sul profilo del criterio larghezza di banda di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a625-102">Viewing network bandwidth policy profile information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a625-103">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="9a625-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="9a625-104">In Controllo di ammissione di chiamata (CAC) i criteri di larghezza di banda vengono utilizzati per definire le limitazioni della larghezza di banda per alcune modalità.</span><span class="sxs-lookup"><span data-stu-id="9a625-104">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="9a625-105">In Microsoft Lync Server 2013, è possibile assegnare limitazioni della larghezza di banda solo alle modalità audio e video.</span><span class="sxs-lookup"><span data-stu-id="9a625-105">In Microsoft Lync Server 2013, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="9a625-106">È possibile impostare limitazioni della larghezza di banda globali o per le sessioni.</span><span class="sxs-lookup"><span data-stu-id="9a625-106">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="9a625-107">È possibile utilizzare il pannello di controllo di Lync Server per creare, modificare o eliminare un profilo contenitore per questi criteri.</span><span class="sxs-lookup"><span data-stu-id="9a625-107">You can use the Lync Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="9a625-108">Ogni profilo di criteri della larghezza di banda può essere associato a uno o più siti di rete.</span><span class="sxs-lookup"><span data-stu-id="9a625-108">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="9a625-109">Utilizzare le procedure seguenti per visualizzare un profilo di criteri della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="9a625-109">Use the following procedures to view a bandwidth policy profile.</span></span> <span data-ttu-id="9a625-110">Per creare o modificare un profilo dei criteri di larghezza di banda, vedere [creazione o modifica di profili di criteri di larghezza di banda in Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="9a625-110">To create or modify a bandwidth policy profile, see [Creating or modifying bandwidth policy profiles in Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).</span></span>

<div>

## <a name="to-view-a-bandwidth-policy-profile"></a><span data-ttu-id="9a625-111">Per visualizzare un profilo dei criteri di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="9a625-111">To view a bandwidth policy profile</span></span>

1.  <span data-ttu-id="9a625-112">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="9a625-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9a625-113">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9a625-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9a625-114">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9a625-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9a625-115">Nella barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Criteri larghezza di banda**.</span><span class="sxs-lookup"><span data-stu-id="9a625-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="9a625-116">Nella pagina **criteri larghezza di banda** fare clic sul profilo dei criteri di larghezza di banda che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="9a625-116">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to view.</span></span>

5.  <span data-ttu-id="9a625-117">Scegliere **Mostra dettagli** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="9a625-117">On the **Edit** menu, click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9a625-118">Visualizzazione delle informazioni sul profilo dei criteri di larghezza di banda di rete tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9a625-118">Viewing Network Bandwidth Policy Profile Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9a625-119">I profili di larghezza di banda di rete possono essere visualizzati utilizzando Windows PowerShell e il cmdlet Get-CsNetworkBandwidthPolicyProfile.</span><span class="sxs-lookup"><span data-stu-id="9a625-119">Network bandwidth profiles can be viewed by using Windows PowerShell and the Get-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="9a625-120">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a625-120">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9a625-121">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="9a625-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="9a625-122">Per visualizzare le informazioni sul profilo dei criteri di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="9a625-122">To view network bandwidth policy profile information</span></span>

  - <span data-ttu-id="9a625-123">Per visualizzare informazioni su tutti i profili dei criteri di larghezza di banda di rete, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="9a625-123">To view information about all your network bandwidth policy profiles, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkBandwidthPolicyProfile
    
    <span data-ttu-id="9a625-124">Verranno restituite informazioni simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="9a625-124">That will return information similar to this:</span></span>
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :

</div>

<span data-ttu-id="9a625-125">Per ulteriori informazioni, vedere l'argomento della Guida per il cmdlet [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span><span class="sxs-lookup"><span data-stu-id="9a625-125">For more information, see the help topic for the [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9a625-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a625-126">See Also</span></span>


[<span data-ttu-id="9a625-127">Creazione o modifica di profili di criteri di larghezza di banda in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a625-127">Creating or modifying bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[<span data-ttu-id="9a625-128">Eliminazione dei profili dei criteri di larghezza di banda di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a625-128">Deleting network bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[<span data-ttu-id="9a625-129">Configurare il controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a625-129">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


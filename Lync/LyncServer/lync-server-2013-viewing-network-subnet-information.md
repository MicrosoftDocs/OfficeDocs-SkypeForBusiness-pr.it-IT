---
title: 'Lync Server 2013: visualizzazione delle informazioni sulla subnet di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network subnet information
ms:assetid: 46f165f2-efe3-4cc1-9fee-a78b7f2ed41e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688044(v=OCS.15)
ms:contentKeyID: 49733636
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c0877db4871403c93dffe2fabd0c30df495b9ae
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138107"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-network-subnet-information-in-lync-server-2013"></a><span data-ttu-id="213e9-102">Visualizzazione delle informazioni sulla subnet di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="213e9-102">Viewing network subnet information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="213e9-103">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="213e9-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="213e9-104">Per visualizzare una subnet di rete è possibile attenersi alla procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="213e9-104">You can use the following procedure to view a network subnet.</span></span> <span data-ttu-id="213e9-105">Dal pannello di controllo di Lync Server, è possibile creare, modificare o eliminare una subnet di rete.</span><span class="sxs-lookup"><span data-stu-id="213e9-105">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="213e9-106">Per informazioni dettagliate sulla creazione o la modifica di subnet di rete, vedere [creare o modificare le subnet di rete in Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).</span><span class="sxs-lookup"><span data-stu-id="213e9-106">For details about creating or modifying network subnets, see [Create or modify network subnets in Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).</span></span>

<div>

## <a name="to-view-a-network-subnet"></a><span data-ttu-id="213e9-107">Per visualizzare una subnet di rete</span><span class="sxs-lookup"><span data-stu-id="213e9-107">To view a network subnet</span></span>

1.  <span data-ttu-id="213e9-108">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="213e9-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="213e9-109">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="213e9-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="213e9-110">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="213e9-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="213e9-111">Nella barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Subnet**.</span><span class="sxs-lookup"><span data-stu-id="213e9-111">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="213e9-112">Nella pagina **Subnet** fare clic sulla subnet che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="213e9-112">On the **Subnet** page, click the subnet that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="213e9-113">È possibile visualizzare una sola subnet alla volta.</span><span class="sxs-lookup"><span data-stu-id="213e9-113">You can only view one subnet at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="213e9-114">Scegliere **Mostra dettagli** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="213e9-114">On the **Edit** menu, click **Show details…**.</span></span>

</div>

<div>

## <a name="viewing-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="213e9-115">Visualizzazione delle informazioni di configurazione della subnet di rete tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="213e9-115">Viewing Network Subnet Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="213e9-116">È possibile visualizzare le informazioni sulla subnet di rete utilizzando Windows PowerShell e il cmdlet Get-CsNetworkSubnet.</span><span class="sxs-lookup"><span data-stu-id="213e9-116">Network subnet information can be viewed by using Windows PowerShell and the Get-CsNetworkSubnet cmdlet.</span></span> <span data-ttu-id="213e9-117">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="213e9-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="213e9-118">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="213e9-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-subnet-information"></a><span data-ttu-id="213e9-119">Per visualizzare le informazioni sulla subnet di rete</span><span class="sxs-lookup"><span data-stu-id="213e9-119">To view network subnet information</span></span>

  - <span data-ttu-id="213e9-120">Per visualizzare informazioni su tutte le subnet di rete, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="213e9-120">To view information about all your network subnets, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSubnet
    
    <span data-ttu-id="213e9-121">Verranno restituite informazioni simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="213e9-121">That will return information similar to this:</span></span>
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0

</div>

<span data-ttu-id="213e9-122">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="213e9-122">For more information, see the help topic for the [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="213e9-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="213e9-123">See Also</span></span>


[<span data-ttu-id="213e9-124">Creare o modificare le subnet di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="213e9-124">Create or modify network subnets in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-network-subnets.md)  
[<span data-ttu-id="213e9-125">Eliminazione di subnet di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="213e9-125">Deleting network subnets in Lync Server 2013</span></span>](lync-server-2013-deleting-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


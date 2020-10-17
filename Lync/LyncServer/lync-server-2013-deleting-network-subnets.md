---
title: 'Lync Server 2013: eliminazione di subnet di rete'
description: 'Lync Server 2013: eliminazione delle subnet di rete.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network subnets
ms:assetid: c1850f38-40a3-48c9-b6f1-f181c5e63b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721873(v=OCS.15)
ms:contentKeyID: 49733806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6635ec99b68c4ceb10d1cda343fef35c951bf152
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557882"
---
# <a name="deleting-network-subnets-in-lync-server-2013"></a><span data-ttu-id="ba3d7-103">Eliminazione di subnet di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba3d7-103">Deleting network subnets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba3d7-104">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="ba3d7-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="ba3d7-105">È possibile utilizzare la procedura seguente per eliminare una subnet.</span><span class="sxs-lookup"><span data-stu-id="ba3d7-105">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="ba3d7-106">Dal pannello di controllo di Lync Server, è possibile creare, modificare o eliminare una subnet di rete.</span><span class="sxs-lookup"><span data-stu-id="ba3d7-106">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="ba3d7-107">Per informazioni dettagliate sulla creazione o la modifica di subnet di rete, vedere [creare o modificare le subnet di rete in Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).</span><span class="sxs-lookup"><span data-stu-id="ba3d7-107">For details on creating or modifying network subnets, see [Create or modify network subnets in Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).</span></span>

<span data-ttu-id="ba3d7-108">Nella maggior parte delle distribuzioni di Microsoft Lync Server 2013 in cui è implementato il controllo di ammissione di chiamata (CAC), in genere vi sarà un numero elevato di subnet.</span><span class="sxs-lookup"><span data-stu-id="ba3d7-108">In most deployments of Microsoft Lync Server 2013 where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="ba3d7-109">Per questo motivo, è spesso preferibile configurare le subnet da Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ba3d7-109">Because of this, it is often best to configure subnets from the Lync Server Management Shell.</span></span> <span data-ttu-id="ba3d7-110">Da questa pagina è possibile chiamare **New-CsNetworkSubnet** in combinazione con il cmdlet **Import-CSV**di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ba3d7-110">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="ba3d7-111">Se si utilizzano questi cmdlet insieme, è possibile leggere le impostazioni della subnet da un file con valori delimitati da virgole (con estensione CSV) e creare più subnet contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="ba3d7-111">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="ba3d7-112">Per esempi su come creare subnet da un file CSV, vedere [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="ba3d7-112">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<div>

## <a name="to-delete-a-network-subnet"></a><span data-ttu-id="ba3d7-113">Per eliminare una subnet di rete</span><span class="sxs-lookup"><span data-stu-id="ba3d7-113">To delete a network subnet</span></span>

1.  <span data-ttu-id="ba3d7-114">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="ba3d7-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ba3d7-115">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ba3d7-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ba3d7-116">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ba3d7-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ba3d7-117">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Subnet**.</span><span class="sxs-lookup"><span data-stu-id="ba3d7-117">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="ba3d7-118">Nella pagina **Subnet** fare clic sulla subnet che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="ba3d7-118">On the **Subnet** page, click the subnet that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ba3d7-p104">È possibile eliminare più subnet contemporaneamente. A tale scopo, tenere premuto CTRL e selezionare le diverse subnet. In alternativa, per selezionare tutte le subnet, scegliere <STRONG>Seleziona tutto</STRONG> dal menu <STRONG>Modifica</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="ba3d7-p104">You can delete more than one subnet at a time. To do this, press CTRL and select multiple subnets while holding down the CTRL key. Or, to select all subnets, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="ba3d7-122">Scegliere **Elimina** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="ba3d7-122">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="ba3d7-123">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ba3d7-123">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ba3d7-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba3d7-124">See Also</span></span>


[<span data-ttu-id="ba3d7-125">Creare o modificare le subnet di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba3d7-125">Create or modify network subnets in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


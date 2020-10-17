---
title: Verificare le informazioni sulla topologia
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify topology information
ms:assetid: aa4c424e-f87c-4be6-8df6-a0cd193b11fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205151(v=OCS.15)
ms:contentKeyID: 48185046
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ef4c2884d9810793b6431c9d518c92bdcd1a3a4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518043"
---
# <a name="verify-topology-information"></a><span data-ttu-id="ba6f4-102">Verificare le informazioni sulla topologia</span><span class="sxs-lookup"><span data-stu-id="ba6f4-102">Verify topology information</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba6f4-103">_**Ultimo argomento modificato:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="ba6f4-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="ba6f4-104">Il primo passaggio per la verifica dell'Unione completata ha esito positivo per visualizzare le informazioni sulla topologia di Office Communications Server 2007 R2 Unite a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ba6f4-104">The first step in verifying the merge completed successfully is to view the Office Communications Server 2007 R2 topology information that you merged with Lync Server 2013.</span></span> <span data-ttu-id="ba6f4-105">In Generatore di topologie il nodo **BackCompatSite** Visualizza il nome di dominio completo (FQDN) di ogni pool e server di Office Communications Server 2007 R2 che è stato Unito.</span><span class="sxs-lookup"><span data-stu-id="ba6f4-105">In Topology Builder, the **BackCompatSite** node displays the fully qualified domain name (FQDN) of each Office Communications Server 2007 R2 pool and server that you merged.</span></span>

<div>

## <a name="to-view-backcompatsite-in-topology-builder"></a><span data-ttu-id="ba6f4-106">Per visualizzare BackCompatSite in Generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="ba6f4-106">To view BackCompatSite in Topology Builder</span></span>

1.  <span data-ttu-id="ba6f4-107">Nell'ambiente Office Communications Server 2007 R2, aprire lo strumento di amministrazione di Office Communications Server 2007 R2 e prendere nota dei nomi FQDN dei pool e server legacy.</span><span class="sxs-lookup"><span data-stu-id="ba6f4-107">In your Office Communications Server 2007 R2 environment, open the Office Communications Server 2007 R2 administrative tool and note the FQDNs of the legacy pools and servers.</span></span>

2.  <span data-ttu-id="ba6f4-108">Nell'ambiente Lync Server 2013 aprire Generatore di topologie e quindi espandere il nodo **BackCompatSite** .</span><span class="sxs-lookup"><span data-stu-id="ba6f4-108">In your Lync Server 2013 environment, open Topology Builder and then expand the **BackCompatSite** node.</span></span>

3.  <span data-ttu-id="ba6f4-109">Verificare che siano visualizzati gli FQDN dei pool e dei server da unire.</span><span class="sxs-lookup"><span data-stu-id="ba6f4-109">Verify that the FQDNs for the pools and servers that you merge are displayed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ba6f4-110">In <STRONG>BackCompatSite</STRONG> non viene visualizzata alcuna informazione per i ruoli del server collocati in un Front End Server o in un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="ba6f4-110">You do not see any information in <STRONG>BackCompatSite</STRONG> for server roles that are collocated on a Front End Server or Standard Edition server.</span></span> <span data-ttu-id="ba6f4-111">Vengono visualizzati solo i ruoli del server necessari per l'interoperabilità tra Office Communications Server 2007 R2 e Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ba6f4-111">Only server roles that are required for interoperability between Office Communications Server 2007 R2 and Lync Server 2013 are shown.</span></span>

    
    </div>

<span data-ttu-id="ba6f4-112">![Finestra di dialogo Generatore di topologie BackCompatSite](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Finestra di dialogo Generatore di topologie BackCompatSite")</span><span class="sxs-lookup"><span data-stu-id="ba6f4-112">![Topology Builder BackCompatSite dialog box](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Topology Builder BackCompatSite dialog box")</span></span>

<span data-ttu-id="ba6f4-113">È inoltre possibile utilizzare il pannello di controllo di Lync Server 2013 per visualizzare la topologia unita.</span><span class="sxs-lookup"><span data-stu-id="ba6f4-113">You can also use Lync Server 2013 Control Panel to view your merged topology.</span></span> <span data-ttu-id="ba6f4-114">Nel pannello di controllo di Lync Server 2013, è possibile visualizzare ogni server FQDN, FQDN del pool e nome del sito per la topologia unita.</span><span class="sxs-lookup"><span data-stu-id="ba6f4-114">In Lync Server 2013 Control Panel, you can see each server FQDN, pool FQDN, and site name for your merged topology.</span></span> <span data-ttu-id="ba6f4-115">Il **Sito** dei server uniti si chiama **BackCompatSite**.</span><span class="sxs-lookup"><span data-stu-id="ba6f4-115">Merged servers have a **Site** name of **BackCompatSite**.</span></span>

</div>

<div>

## <a name="to-view-the-merged-topology-in-lync-server-2013-control-panel"></a><span data-ttu-id="ba6f4-116">Per visualizzare la topologia unita nel pannello di controllo di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba6f4-116">To view the merged topology in Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="ba6f4-117">Aprire il pannello di controllo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ba6f4-117">Open Lync Server 2013 Control Panel.</span></span>

2.  <span data-ttu-id="ba6f4-118">Fare clic su **Topologia**.</span><span class="sxs-lookup"><span data-stu-id="ba6f4-118">Click **Topology**.</span></span>

3.  <span data-ttu-id="ba6f4-119">Nella scheda **Stato** verificare che i server e i pool uniti siano visualizzati cercando **BackCompatSite** nella colonna **Sito**.</span><span class="sxs-lookup"><span data-stu-id="ba6f4-119">On the **Status** tab, verify that servers and pools you merged appear by looking for **BackCompatSite** in the **Site** column.</span></span>

<span data-ttu-id="ba6f4-120">![Pannello di controllo di Lync Server che mostra la topologia unita](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "Pannello di controllo di Lync Server che mostra la topologia unita")</span><span class="sxs-lookup"><span data-stu-id="ba6f4-120">![Lync Server Control Panel showing merged topology](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "Lync Server Control Panel showing merged topology")</span></span>

<span data-ttu-id="ba6f4-121">Per visualizzare altri dettagli su un pool unito, utilizzare il cmdlet **Get-CsPool**.</span><span class="sxs-lookup"><span data-stu-id="ba6f4-121">To see more detail about a merged pool, use the **Get-CsPool** cmdlet.</span></span> <span data-ttu-id="ba6f4-122">Oltre alle informazioni disponibili nel pannello di controllo di generatore di topologie e Lync Server 2013, questo cmdlet consente di visualizzare i servizi in esecuzione nel pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ba6f4-122">In addition to the information that is available in Topology Builder and Lync Server 2013 Control Panel, this cmdlet displays the services that run on the Lync Server 2013 pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ba6f4-123">Quando si pubblica la topologia dopo aver eseguito la procedura di Unione guidata in Generatore di topologie, le directory conferenze vengono unite a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ba6f4-123">When you publish the topology after running the Merge wizard in Topology Builder, conference directories are merged to Lync Server 2013.</span></span> <span data-ttu-id="ba6f4-124">Le directory conferenze possono essere verificate eseguendo il cmdlet <STRONG>Get-CsConferenceDirectory</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="ba6f4-124">Conference directories can be verified by running the <STRONG>Get-CsConferenceDirectory</STRONG> cmdlet.</span></span>



</div>

</div>

<div>

## <a name="to-view-services-on-a-merged-pool"></a><span data-ttu-id="ba6f4-125">Per visualizzare i servizi in un pool unito</span><span class="sxs-lookup"><span data-stu-id="ba6f4-125">To view services on a merged pool</span></span>

1.  <span data-ttu-id="ba6f4-126">Aprire Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ba6f4-126">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="ba6f4-127">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="ba6f4-127">At the command line, type the following:</span></span>
    
        Get-CsPool [-Identity <FQDN of the pool>]
    
    <span data-ttu-id="ba6f4-128">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ba6f4-128">For example:</span></span>
    
        Get-CsPool -Identity pool02.contoso.net

</div>

<div>

## <a name="to-verify-conference-directories-merged"></a><span data-ttu-id="ba6f4-129">Per verificare le directory conferenze unite</span><span class="sxs-lookup"><span data-stu-id="ba6f4-129">To verify conference directories merged</span></span>

1.  <span data-ttu-id="ba6f4-130">Aprire Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ba6f4-130">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="ba6f4-131">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="ba6f4-131">At the command line, type the following:</span></span>
    
        Get-CsConferenceDirectory

3.  <span data-ttu-id="ba6f4-132">Verificare che tutte le directory conferenze per il pool o il server in cui si esegue l'Unione siano presenti in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ba6f4-132">Verify that all the conference directories for the pool or server you are merging are now in Lync Server 2013.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


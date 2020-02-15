---
title: Aggiungere il sito di succursale del Survivable Branch Appliance di Lync Server 2013 alla topologia
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add Lync Server 2013 Survivable Branch Appliance branch site to your topology
ms:assetid: d3142a37-4606-456d-8ea9-6cc0e51e55f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721896(v=OCS.15)
ms:contentKeyID: 49733830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e57a7b062cd95012102ba30a527c99c2fba71d6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038628"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology"></a><span data-ttu-id="db093-102">Aggiungere il sito di succursale del Survivable Branch Appliance di Lync Server 2013 alla topologia</span><span class="sxs-lookup"><span data-stu-id="db093-102">Add Lync Server 2013 Survivable Branch Appliance branch site to your topology</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db093-103">_**Ultimo argomento modificato:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="db093-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="db093-104">Microsoft Lync Server 2013 Survivable Branch Appliance (SBA) non può essere associato a un pool Front End di Microsoft Lync Server 2010 come registrar di backup.</span><span class="sxs-lookup"><span data-stu-id="db093-104">Microsoft Lync Server 2013 Survivable Branch Appliances (SBA) cannot be associated to a Microsoft Lync Server 2010 Front End pool as a backup Registrar.</span></span> <span data-ttu-id="db093-105">L'ASB deve essere associato a un pool Front End di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="db093-105">The SBA must be associated with a Microsoft Lync Server 2013 Front End pool.</span></span> <span data-ttu-id="db093-106">In questa procedura si presuppone che Microsoft Lync Server 2013 SBA.</span><span class="sxs-lookup"><span data-stu-id="db093-106">These steps assume a Microsoft Lync Server 2013 SBA.</span></span> <span data-ttu-id="db093-107">Eseguire questa procedura nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="db093-107">Perform this procedure at the central site.</span></span>

<div>

## <a name="to-add-branch-sites-with-microsoft-lync-server-2013-sba-to-your-topology"></a><span data-ttu-id="db093-108">Per aggiungere siti di succursale con Microsoft Lync Server 2013 SBA alla propria topologia</span><span class="sxs-lookup"><span data-stu-id="db093-108">To add branch sites with Microsoft Lync Server 2013 SBA to your topology</span></span>

1.  <span data-ttu-id="db093-109">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.</span><span class="sxs-lookup"><span data-stu-id="db093-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="db093-110">Nell'albero della console espandere il sito centrale, espandere **Siti di succursale** e quindi fare clic su **Nuovo sito di succursale**.</span><span class="sxs-lookup"><span data-stu-id="db093-110">In the console tree, expand the central site, expand **Branch Sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="db093-111">Nella finestra di dialogo **Definisci nuovo sito di succursale** fare clic su **Nome** e quindi digitare un nome per il nuovo sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="db093-111">In the **Define New Branch Site** dialog box, click **Name**, and then type a name for the new branch site.</span></span>

4.  <span data-ttu-id="db093-112">(Facoltativo) Fare clic su **Descrizione** e quindi digitare una descrizione significativa del sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="db093-112">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="db093-113">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="db093-113">Click **Next**.</span></span>

6.  <span data-ttu-id="db093-114">(Facoltativo) Nella successiva finestra di dialogo **Definisci nuovo sito di succursale** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="db093-114">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
      - <span data-ttu-id="db093-115">Fare clic su **Città** e quindi digitare il nome della città in cui si trova il sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="db093-115">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
      - <span data-ttu-id="db093-116">Fare clic su **Paese** e quindi digitare il nome del paese in cui si trova il sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="db093-116">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
      - <span data-ttu-id="db093-117">Fare clic su **Codice paese** e quindi digitare il codice di chiamata in due cifre per il paese/area geografica in cui si trova il sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="db093-117">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="db093-118">Fare clic su **Avanti** e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="db093-118">Click **Next**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="db093-119">Se si utilizza un Survivable Branch Appliance o Survivable Branch Server in questo sito, accertarsi che la casella di controllo **Apri la procedura guidata nuovo Survivable Wizard al termine della procedura guidata** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="db093-119">If you are using a Survivable Branch Appliance or Survivable Branch Server at this site, be sure that the **Open the New Survivable Wizard when this wizard closes** check box is selected.</span></span>
    
      - <span data-ttu-id="db093-120">Se non si utilizza un Survivable Branch Appliance o Survivable Branch Server in questo sito, deselezionare la casella di controllo **aprire la procedura guidata nuovo Survivable Wizard quando la procedura guidata viene chiusa** .</span><span class="sxs-lookup"><span data-stu-id="db093-120">If you are not using a Survivable Branch Appliance or Survivable Branch Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span>
    
      - <span data-ttu-id="db093-121">Fare clic su **Fine** e quindi seguire le indicazioni fornite nella procedura guidata che verrà visualizzata.</span><span class="sxs-lookup"><span data-stu-id="db093-121">Click **Finish**, and then follow the directions in the wizard that opens.</span></span> <span data-ttu-id="db093-122">Per informazioni sugli elementi della procedura guidata, vedere [define a Survivable Branch Appliance or server in Lync server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="db093-122">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>

8.  <span data-ttu-id="db093-123">Ripetere i passaggi precedenti per ogni sito di succursale che si desidera aggiungere alla topologia.</span><span class="sxs-lookup"><span data-stu-id="db093-123">Repeat the previous steps for each branch site that you want to add to the topology.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="db093-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db093-124">See Also</span></span>


[<span data-ttu-id="db093-125">Definire un Survivable Branch Appliance o un server di succursale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db093-125">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[<span data-ttu-id="db093-126">Definire un gateway PSTN per un sito di succursale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db093-126">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[<span data-ttu-id="db093-127">Configurare un trunk con bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db093-127">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="db093-128">Configurare un trunk senza bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db093-128">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


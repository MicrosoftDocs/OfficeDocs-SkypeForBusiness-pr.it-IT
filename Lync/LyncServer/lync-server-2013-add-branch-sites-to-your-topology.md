---
title: 'Lync Server 2013: aggiungere siti di succursale alla topologia'
description: 'Lync Server 2013: aggiungere siti di succursale alla topologia.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add branch sites to your topology
ms:assetid: b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412905(v=OCS.15)
ms:contentKeyID: 48185216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c7a12373c6a60a2902ee451d39c99f756e2b2f5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544572"
---
# <a name="add-branch-sites-to-your-topology-in-lync-server-2013"></a><span data-ttu-id="e69b7-103">Aggiungere siti di succursale alla topologia in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e69b7-103">Add branch sites to your topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e69b7-104">_**Ultimo argomento modificato:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="e69b7-104">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="e69b7-p101">I siti di succursale rappresentano le succursali fisiche connesse alle sedi principali tramite un collegamento WAN. Per aggiungere un sito di succursale alla topologia di Lync, eseguire questa procedura nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="e69b7-p101">Branch sites represent physical branch offices that are connected to your main offices over a WAN link. To add a branch site to your Lync topology, perform this procedure at the central site.</span></span>

<div>

## <a name="to-add-branch-sites-to-your-topology"></a><span data-ttu-id="e69b7-107">Per aggiungere siti di succursale alla topologia</span><span class="sxs-lookup"><span data-stu-id="e69b7-107">To add branch sites to your topology</span></span>

1.  <span data-ttu-id="e69b7-108">Fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server** e quindi **Generatore di topologie di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e69b7-108">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="e69b7-109">Nell'albero della console espandere il sito centrale, fare clic con il pulsante destro del mouse su **Siti di succursale** e quindi scegliere **Nuovo sito di succursale**.</span><span class="sxs-lookup"><span data-stu-id="e69b7-109">In the console tree, expand the central site, right-click **Branch Sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="e69b7-110">Nella finestra di dialogo **Definisci nuovo sito di succursale** fare clic su **Nome** e quindi digitare il nome del sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="e69b7-110">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>

4.  <span data-ttu-id="e69b7-111">(Facoltativo) Fare clic su **Descrizione** e quindi digitare una descrizione significativa del sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="e69b7-111">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="e69b7-112">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e69b7-112">Click **Next**.</span></span>

6.  <span data-ttu-id="e69b7-113">(Facoltativo) Nella successiva finestra di dialogo **Definisci nuovo sito di succursale** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e69b7-113">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
      - <span data-ttu-id="e69b7-114">Fare clic su **Città** e quindi digitare il nome della città in cui si trova il sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="e69b7-114">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
      - <span data-ttu-id="e69b7-115">Fare clic su **Paese** e quindi digitare il nome del paese in cui si trova il sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="e69b7-115">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
      - <span data-ttu-id="e69b7-116">Fare clic su **Codice paese** e quindi digitare il codice di chiamata in due cifre per il paese/area geografica in cui si trova il sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="e69b7-116">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="e69b7-117">Fare clic su **Avanti** e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e69b7-117">Click **Next**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="e69b7-118">Se si utilizza un Survivable Branch Appliance o server in questo sito, accertarsi che la casella di controllo **Apri la procedura guidata nuovo Survivable Wizard al termine della procedura guidata** sia selezionata, fare clic su **fine**e quindi seguire le istruzioni nella procedura guidata che verrà aperta.</span><span class="sxs-lookup"><span data-stu-id="e69b7-118">If you are using a Survivable Branch Appliance or Server at this site, be sure that the **Open the New Survivable Wizard when this wizard closes** check box is selected, click **Finish**, and then follow the directions in the wizard that opens.</span></span> <span data-ttu-id="e69b7-119">Per informazioni sugli elementi della procedura guidata, vedere [define a Survivable Branch Appliance or server in Lync server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="e69b7-119">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>
    
      - <span data-ttu-id="e69b7-120">Se nel sito non si utilizza un Survivable Branch Appliance o un Survivable Branch Server, deselezionare la casella di controllo **Aprire la procedura guidata Nuovo Survivable Branch Appliance al termine di questa procedura guidata** e quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="e69b7-120">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>

8.  <span data-ttu-id="e69b7-121">Ripetere i passaggi precedenti per ogni sito di succursale che si desidera aggiungere alla topologia.</span><span class="sxs-lookup"><span data-stu-id="e69b7-121">Repeat the previous steps for each branch site that you want to add to the topology.</span></span>

<span data-ttu-id="e69b7-122">**Passaggio successivo:**</span><span class="sxs-lookup"><span data-stu-id="e69b7-122">**Next step:**</span></span>

<span data-ttu-id="e69b7-123">Per i server o gli appliance Survivable Branch: [definire un Survivable Branch Appliance o un server in Lync server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)</span><span class="sxs-lookup"><span data-stu-id="e69b7-123">For Survivable Branch Appliances or Servers: [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)</span></span>

<span data-ttu-id="e69b7-124">Per la connettività PSTN non resiliente: [definire un gateway PSTN per un sito di succursale in Lync server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md), [configurare un trunk con bypass multimediale in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)o [configurare un trunk senza bypass multimediale in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="e69b7-124">For non-resilient PSTN connectivity: [Define a PSTN gateway for a branch site in Lync Server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md), [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md), or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


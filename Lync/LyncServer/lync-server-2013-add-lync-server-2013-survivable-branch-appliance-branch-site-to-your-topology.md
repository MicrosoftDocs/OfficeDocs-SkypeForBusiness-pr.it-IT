---
title: Aggiungere un sito di succursale Survivable Branch Appliance di Lync Server 2013 alla topologia
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add Lync Server 2013 Survivable Branch Appliance branch site to your topology
ms:assetid: d3142a37-4606-456d-8ea9-6cc0e51e55f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721896(v=OCS.15)
ms:contentKeyID: 49733830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83ae19b3683b725db64b2f598eb6fc3d182bac17
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology"></a><span data-ttu-id="c001a-102">Aggiungere un sito di succursale Survivable Branch Appliance di Lync Server 2013 alla topologia</span><span class="sxs-lookup"><span data-stu-id="c001a-102">Add Lync Server 2013 Survivable Branch Appliance branch site to your topology</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c001a-103">_**Argomento Ultima modifica:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="c001a-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="c001a-104">Microsoft Lync Server 2013 Survivable Branch Appliances (SBA) non può essere associato a un pool di front end di Microsoft Lync Server 2010 come registrar di backup.</span><span class="sxs-lookup"><span data-stu-id="c001a-104">Microsoft Lync Server 2013 Survivable Branch Appliances (SBA) cannot be associated to a Microsoft Lync Server 2010 Front End pool as a backup Registrar.</span></span> <span data-ttu-id="c001a-105">L'SBA deve essere associato a un pool Front-End di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c001a-105">The SBA must be associated with a Microsoft Lync Server 2013 Front End pool.</span></span> <span data-ttu-id="c001a-106">Questi passaggi presuppongono un SBA di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c001a-106">These steps assume a Microsoft Lync Server 2013 SBA.</span></span> <span data-ttu-id="c001a-107">Eseguire questa procedura nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="c001a-107">Perform this procedure at the central site.</span></span>

<div>

## <a name="to-add-branch-sites-with-microsoft-lync-server-2013-sba-to-your-topology"></a><span data-ttu-id="c001a-108">Per aggiungere siti di succursale con Microsoft Lync Server 2013 SBA alla propria topologia</span><span class="sxs-lookup"><span data-stu-id="c001a-108">To add branch sites with Microsoft Lync Server 2013 SBA to your topology</span></span>

1.  <span data-ttu-id="c001a-109">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="c001a-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="c001a-110">Nell'albero della console espandere il sito centrale, espandere **siti di succursale**e quindi fare clic su **nuovo sito filiale**.</span><span class="sxs-lookup"><span data-stu-id="c001a-110">In the console tree, expand the central site, expand **Branch Sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="c001a-111">Nella finestra di dialogo **Definisci nuovo sito succursale** fare clic su **nome**e quindi digitare un nome per il nuovo sito della filiale.</span><span class="sxs-lookup"><span data-stu-id="c001a-111">In the **Define New Branch Site** dialog box, click **Name**, and then type a name for the new branch site.</span></span>

4.  <span data-ttu-id="c001a-112">Opzionale Fare clic su **Descrizione**e quindi digitare una descrizione significativa per il sito della filiale.</span><span class="sxs-lookup"><span data-stu-id="c001a-112">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="c001a-113">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c001a-113">Click **Next**.</span></span>

6.  <span data-ttu-id="c001a-114">Opzionale Nella finestra di dialogo **Definisci nuovo sito della filiale** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c001a-114">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
      - <span data-ttu-id="c001a-115">Fare clic su **città**e quindi digitare il nome della città in cui si trova il sito della filiale.</span><span class="sxs-lookup"><span data-stu-id="c001a-115">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
      - <span data-ttu-id="c001a-116">Fare clic su **stato/area geografica**e quindi digitare il nome dello stato o dell'area geografica in cui si trova il sito della filiale.</span><span class="sxs-lookup"><span data-stu-id="c001a-116">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
      - <span data-ttu-id="c001a-117">Fare clic su **codice paese**e quindi digitare il codice di chiamata a due cifre per il paese/area geografica in cui si trova il sito della filiale.</span><span class="sxs-lookup"><span data-stu-id="c001a-117">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="c001a-118">Fare clic su **Avanti**e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c001a-118">Click **Next**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="c001a-119">Se si usa un Survivable Branch Appliance o Survivable Branch Server in questo sito, verificare che la casella di controllo **Apri la nuova procedura guidata per la procedura** guidata sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="c001a-119">If you are using a Survivable Branch Appliance or Survivable Branch Server at this site, be sure that the **Open the New Survivable Wizard when this wizard closes** check box is selected.</span></span>
    
      - <span data-ttu-id="c001a-120">Se non si usa un Survivable Branch Appliance o Survivable Branch Server in questo sito, deselezionare la casella di controllo **Apri la nuova procedura guidata per** la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="c001a-120">If you are not using a Survivable Branch Appliance or Survivable Branch Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span>
    
      - <span data-ttu-id="c001a-121">Fare clic su **fine**e quindi seguire le istruzioni visualizzate nella procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="c001a-121">Click **Finish**, and then follow the directions in the wizard that opens.</span></span> <span data-ttu-id="c001a-122">Per informazioni sugli elementi della procedura guidata, vedere [definire un Survivable Branch Appliance o un server in Lync server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="c001a-122">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>

8.  <span data-ttu-id="c001a-123">Ripetere i passaggi precedenti per ogni sito della filiale che si vuole aggiungere alla topologia.</span><span class="sxs-lookup"><span data-stu-id="c001a-123">Repeat the previous steps for each branch site that you want to add to the topology.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c001a-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c001a-124">See Also</span></span>


[<span data-ttu-id="c001a-125">Definire un Survivable Branch Appliance o un Survivable Branch Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c001a-125">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[<span data-ttu-id="c001a-126">Definire un gateway PSTN per un sito di succursale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c001a-126">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[<span data-ttu-id="c001a-127">Configurare un trunk con il bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c001a-127">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="c001a-128">Configurare un trunk senza bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c001a-128">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


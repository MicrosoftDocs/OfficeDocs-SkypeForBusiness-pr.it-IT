---
title: 'Lync Server 2013: Aggiungere siti di succursale alla topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add branch sites to your topology
ms:assetid: b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412905(v=OCS.15)
ms:contentKeyID: 48185216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 029627060ff03b804d0d2f76f40fdd4052f0d1c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-branch-sites-to-your-topology-in-lync-server-2013"></a><span data-ttu-id="5c09f-102">Aggiungere siti di succursale alla topologia in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5c09f-102">Add branch sites to your topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5c09f-103">_**Argomento Ultima modifica:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="5c09f-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="5c09f-104">I siti di succursale rappresentano le filiali fisiche connesse agli uffici principali tramite un collegamento WAN.</span><span class="sxs-lookup"><span data-stu-id="5c09f-104">Branch sites represent physical branch offices that are connected to your main offices over a WAN link.</span></span> <span data-ttu-id="5c09f-105">Per aggiungere un sito di succursale alla topologia di Lync, eseguire questa procedura nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="5c09f-105">To add a branch site to your Lync topology, perform this procedure at the central site.</span></span>

<div>

## <a name="to-add-branch-sites-to-your-topology"></a><span data-ttu-id="5c09f-106">Per aggiungere siti di succursale alla topologia</span><span class="sxs-lookup"><span data-stu-id="5c09f-106">To add branch sites to your topology</span></span>

1.  <span data-ttu-id="5c09f-107">Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Microsoft Lync Server**e quindi su **Generatore di topologia di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="5c09f-107">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="5c09f-108">Nell'albero della console espandere il sito centrale, fare clic con il pulsante destro del mouse su **siti di succursale**e quindi scegliere **nuovo sito filiale**.</span><span class="sxs-lookup"><span data-stu-id="5c09f-108">In the console tree, expand the central site, right-click **Branch Sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="5c09f-109">Nella finestra di dialogo **Definisci nuovo sito succursale** fare clic su **nome**e quindi digitare il nome del sito della filiale.</span><span class="sxs-lookup"><span data-stu-id="5c09f-109">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>

4.  <span data-ttu-id="5c09f-110">Opzionale Fare clic su **Descrizione**e quindi digitare una descrizione significativa per il sito della filiale.</span><span class="sxs-lookup"><span data-stu-id="5c09f-110">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="5c09f-111">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5c09f-111">Click **Next**.</span></span>

6.  <span data-ttu-id="5c09f-112">Opzionale Nella finestra di dialogo **Definisci nuovo sito della filiale** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5c09f-112">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
      - <span data-ttu-id="5c09f-113">Fare clic su **città**e quindi digitare il nome della città in cui si trova il sito della filiale.</span><span class="sxs-lookup"><span data-stu-id="5c09f-113">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
      - <span data-ttu-id="5c09f-114">Fare clic su **stato/area geografica**e quindi digitare il nome dello stato o dell'area geografica in cui si trova il sito della filiale.</span><span class="sxs-lookup"><span data-stu-id="5c09f-114">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
      - <span data-ttu-id="5c09f-115">Fare clic su **codice paese**e quindi digitare il codice di chiamata a due cifre per il paese/area geografica in cui si trova il sito della filiale.</span><span class="sxs-lookup"><span data-stu-id="5c09f-115">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="5c09f-116">Fare clic su **Avanti**e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5c09f-116">Click **Next**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="5c09f-117">Se si usa un Survivable Branch Appliance o un server in questo sito, verificare che la casella di controllo **Apri la nuova procedura guidata per** la procedura guidata sia selezionata, fare clic su **fine**e quindi seguire le istruzioni della procedura guidata visualizzata.</span><span class="sxs-lookup"><span data-stu-id="5c09f-117">If you are using a Survivable Branch Appliance or Server at this site, be sure that the **Open the New Survivable Wizard when this wizard closes** check box is selected, click **Finish**, and then follow the directions in the wizard that opens.</span></span> <span data-ttu-id="5c09f-118">Per informazioni sugli elementi della procedura guidata, vedere [definire un Survivable Branch Appliance o un server in Lync server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="5c09f-118">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>
    
      - <span data-ttu-id="5c09f-119">Se non si usa un Survivable Branch Appliance o un server in questo sito, deselezionare la casella di controllo **Apri la nuova procedura guidata per** la procedura guidata e quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="5c09f-119">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>

8.  <span data-ttu-id="5c09f-120">Ripetere i passaggi precedenti per ogni sito della filiale che si vuole aggiungere alla topologia.</span><span class="sxs-lookup"><span data-stu-id="5c09f-120">Repeat the previous steps for each branch site that you want to add to the topology.</span></span>

<span data-ttu-id="5c09f-121">**Passaggio successivo:**</span><span class="sxs-lookup"><span data-stu-id="5c09f-121">**Next step:**</span></span>

<span data-ttu-id="5c09f-122">Per gli elettrodomestici o i server Survivable Branch: [definire un Survivable Branch Appliance o un server in Lync server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)</span><span class="sxs-lookup"><span data-stu-id="5c09f-122">For Survivable Branch Appliances or Servers: [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)</span></span>

<span data-ttu-id="5c09f-123">Per la connettività PSTN non resiliente: [definire un gateway PSTN per un sito di succursale in Lync server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md), [configurare un trunk con il bypass multimediale in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)o [configurare un trunk senza bypass multimediale in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="5c09f-123">For non-resilient PSTN connectivity: [Define a PSTN gateway for a branch site in Lync Server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md), [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md), or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


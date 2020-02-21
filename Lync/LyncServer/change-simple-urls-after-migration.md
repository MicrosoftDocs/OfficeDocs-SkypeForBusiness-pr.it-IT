---
title: Modificare gli URL semplici dopo la migrazione
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Change simple URLs after migration
ms:assetid: addb0dc8-8324-42b1-9a00-f4bd14fdf5c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721844(v=OCS.15)
ms:contentKeyID: 49733777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: def26afe2bae21a7a3b6d0ffae4b358c76296e6d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181029"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="f5d11-102">Modificare gli URL semplici dopo la migrazione</span><span class="sxs-lookup"><span data-stu-id="f5d11-102">Change simple URLs after migration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5d11-103">_**Ultimo argomento modificato:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="f5d11-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="f5d11-104">Lync Server supporta tre URL semplici:</span><span class="sxs-lookup"><span data-stu-id="f5d11-104">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="f5d11-p101">L'URL **riunione** (meet) viene utilizzato come URL di base per tutte le conferenze nel sito o nell'organizzazione. Con l'URL semplice riunione, i collegamenti per partecipare alle riunioni sono semplici da capire, da comunicare e da distribuire.</span><span class="sxs-lookup"><span data-stu-id="f5d11-p101">**Meet** is used as the base URL for all conferences in the site or organization. With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="f5d11-p102">L'URL **per accesso esterno** (dialin) consente di accedere alla pagina Web Impostazioni conferenza telefonica con accesso esterno. L'URL semplice per accesso esterno è incluso in tutti gli inviti a riunioni, in modo che gli utenti che desiderano eseguire l'accesso esterno alla riunione dispongano delle informazioni necessarie sul numero di telefono e sul PIN.</span><span class="sxs-lookup"><span data-stu-id="f5d11-p102">**Dial-in** enables access to the Dial-in Conferencing Settings webpage. The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span>

  - <span data-ttu-id="f5d11-109">L' **amministratore** consente di accedere rapidamente al pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f5d11-109">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="f5d11-110">L'URL semplice di amministrazione è interno all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f5d11-110">The Admin simple URL is internal to your organization.</span></span>

<span data-ttu-id="f5d11-111">Dopo aver eseguito la migrazione a Lync Server 2013, è necessario essere a conoscenza del modo in cui la modifica incide sui record DNS e sui certificati per gli URL semplici.</span><span class="sxs-lookup"><span data-stu-id="f5d11-111">After migrating to Lync Server 2013, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="f5d11-112">Se l'amministratore di Lync Server 2010 Legacy rimane in uso nella topologia, non sono necessarie modifiche agli URL semplici.</span><span class="sxs-lookup"><span data-stu-id="f5d11-112">If the legacy Lync Server 2010 Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="f5d11-113">Se Lync Server 2010 Director è stato rimosso dalla topologia dopo la migrazione, è necessario aggiornare i record DNS degli URL semplificati in modo che puntino a uno dei pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5d11-113">If the Lync Server 2010 Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Lync Server 2013 pools.</span></span> <span data-ttu-id="f5d11-114">Ogni volta che si modifica il nome di un URL semplice, è necessario però eseguire Enable-CsComputer in ogni Director e Front End Server per registrare la modifica.</span><span class="sxs-lookup"><span data-stu-id="f5d11-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

<div>

## <a name="changing-simple-urls-after-migration"></a><span data-ttu-id="f5d11-115">Modifica degli URL semplici dopo la migrazione</span><span class="sxs-lookup"><span data-stu-id="f5d11-115">Changing Simple URLs after Migration</span></span>

<span data-ttu-id="f5d11-116">**Per aggiornare l'URL semplice riunione**</span><span class="sxs-lookup"><span data-stu-id="f5d11-116">**To update the Meet simple URL**</span></span>

1.  <span data-ttu-id="f5d11-117">In Generatore di topologie fare clic con il pulsante destro del mouse sul nodo principale **Lync Server**e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="f5d11-117">In Topology Builder, right-click the top node **Lync Server**, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="f5d11-118">Nel riquadro sinistro selezionare URL **semplici** , quindi fare clic su URL di **riunione** e quindi su **modifica URL**.</span><span class="sxs-lookup"><span data-stu-id="f5d11-118">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>

3.  <span data-ttu-id="f5d11-119">Aggiornare l'URL in base al valore desiderato e quindi fare clic su **OK** per salvare l'URL modificato.</span><span class="sxs-lookup"><span data-stu-id="f5d11-119">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span>

<span data-ttu-id="f5d11-120">**Per aggiornare l'URL semplice di amministrazione**</span><span class="sxs-lookup"><span data-stu-id="f5d11-120">**To update the Admin simple URL**</span></span>

1.  <span data-ttu-id="f5d11-121">In Generatore di topologie fare clic con il pulsante destro del mouse sul nodo principale **Lync Server**e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="f5d11-121">In Topology Builder, right-click the top node **Lync Server**, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="f5d11-122">Nel riquadro sinistro selezionare URL **semplici** , quindi nella casella **URL di accesso amministrativo** immettere l'URL semplice desiderato per l'accesso amministrativo al pannello di controllo di Lync Server 2013 e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f5d11-122">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Lync Server 2013 Control Panel, and then click **OK**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="f5d11-123">È consigliabile utilizzare l'URL più semplice possibile per l'accesso amministrativo.</span><span class="sxs-lookup"><span data-stu-id="f5d11-123">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="f5d11-124">L'opzione più semplice è <STRONG> https://admin.</STRONG> &lt;dominio&gt;.</span><span class="sxs-lookup"><span data-stu-id="f5d11-124">The simplest option is <STRONG>https://admin.</STRONG>&lt;domain&gt;.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f5d11-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5d11-125">See Also</span></span>


[<span data-ttu-id="f5d11-126">Pianificazione degli URL semplici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5d11-126">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


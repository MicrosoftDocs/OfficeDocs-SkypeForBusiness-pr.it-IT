---
title: Modificare gli URL semplici dopo la migrazione
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Change simple URLs after migration
ms:assetid: addb0dc8-8324-42b1-9a00-f4bd14fdf5c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721844(v=OCS.15)
ms:contentKeyID: 49733777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 811296efc12badd61d148b7dbd60a3489e74a747
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "40975980"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="f7c47-102">Modificare gli URL semplici dopo la migrazione</span><span class="sxs-lookup"><span data-stu-id="f7c47-102">Change simple URLs after migration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7c47-103">_**Argomento Ultima modifica:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="f7c47-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="f7c47-104">Lync Server supporta tre semplici URL:</span><span class="sxs-lookup"><span data-stu-id="f7c47-104">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="f7c47-105">L' **incontro** viene usato come URL di base per tutte le conferenze nel sito o nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f7c47-105">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="f7c47-106">Con l'URL semplice Meet, i collegamenti alle riunioni di partecipazione sono facili da comprendere e facili da comunicare e distribuire.</span><span class="sxs-lookup"><span data-stu-id="f7c47-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="f7c47-107">L'accesso esterno consente di accedere alla pagina Web delle impostazioni dei servizi di conferenza telefonica con **chiamata in ingresso** .</span><span class="sxs-lookup"><span data-stu-id="f7c47-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="f7c47-108">L'URL semplice per la chiamata in ingresso è incluso in tutti gli inviti alle riunioni, in modo che gli utenti che vogliono connettersi alla riunione possano accedere al numero di telefono e alle informazioni PIN necessarie.</span><span class="sxs-lookup"><span data-stu-id="f7c47-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span>

  - <span data-ttu-id="f7c47-109">L' **amministratore** consente l'accesso rapido al pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f7c47-109">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="f7c47-110">L'URL semplice amministratore è interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f7c47-110">The Admin simple URL is internal to your organization.</span></span>

<span data-ttu-id="f7c47-111">Dopo aver eseguito la migrazione a Lync Server 2013, è necessario essere consapevoli del modo in cui la modifica influisce sui record DNS e sui certificati per gli URL semplici.</span><span class="sxs-lookup"><span data-stu-id="f7c47-111">After migrating to Lync Server 2013, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="f7c47-112">Se l'eredità di Lync Server 2010 Director rimane in uso nella topologia, non sono necessarie modifiche agli URL semplici.</span><span class="sxs-lookup"><span data-stu-id="f7c47-112">If the legacy Lync Server 2010 Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="f7c47-113">Se il Director di Lync Server 2010 viene rimosso dalla topologia dopo la migrazione, è necessario che i record DNS URL semplici vengano aggiornati in modo che puntino a uno dei pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f7c47-113">If the Lync Server 2010 Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Lync Server 2013 pools.</span></span> <span data-ttu-id="f7c47-114">Ogni volta che si modifica un nome di URL semplice, è necessario eseguire Enable-CsComputer su ogni Director e front end server per registrare la modifica.</span><span class="sxs-lookup"><span data-stu-id="f7c47-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

<div>

## <a name="changing-simple-urls-after-migration"></a><span data-ttu-id="f7c47-115">Modifica di URL semplici dopo la migrazione</span><span class="sxs-lookup"><span data-stu-id="f7c47-115">Changing Simple URLs after Migration</span></span>

<span data-ttu-id="f7c47-116">**Per aggiornare l'URL semplice riunione**</span><span class="sxs-lookup"><span data-stu-id="f7c47-116">**To update the Meet simple URL**</span></span>

1.  <span data-ttu-id="f7c47-117">In Generatore di topologie fare clic con il pulsante destro del mouse sul **Server Lync**superiore e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="f7c47-117">In Topology Builder, right-click the top node **Lync Server**, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="f7c47-118">Selezionare **URL semplici** nel riquadro sinistro, quindi sotto gli **URL delle riunioni:** Selezionare l'URL di riunione e quindi fare clic su **modifica URL**.</span><span class="sxs-lookup"><span data-stu-id="f7c47-118">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>

3.  <span data-ttu-id="f7c47-119">Aggiornare l'URL con il valore desiderato e quindi fare clic su **OK** per salvare l'URL modificato.</span><span class="sxs-lookup"><span data-stu-id="f7c47-119">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span>

<span data-ttu-id="f7c47-120">**Per aggiornare l'URL semplice dell'amministratore**</span><span class="sxs-lookup"><span data-stu-id="f7c47-120">**To update the Admin simple URL**</span></span>

1.  <span data-ttu-id="f7c47-121">In Generatore di topologie fare clic con il pulsante destro del mouse sul **Server Lync**superiore e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="f7c47-121">In Topology Builder, right-click the top node **Lync Server**, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="f7c47-122">Selezionare **URL semplici** nel riquadro sinistro, quindi sotto la casella **URL di accesso amministrativo** immettere l'URL semplice desiderato per l'accesso amministrativo al pannello di controllo di Lync Server 2013 e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f7c47-122">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Lync Server 2013 Control Panel, and then click **OK**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="f7c47-123">È consigliabile usare l'URL più semplice possibile per l'URL di amministratore.</span><span class="sxs-lookup"><span data-stu-id="f7c47-123">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="f7c47-124">L'opzione più semplice è <STRONG> https://admin.</STRONG> &lt;domain&gt;.</span><span class="sxs-lookup"><span data-stu-id="f7c47-124">The simplest option is <STRONG>https://admin.</STRONG>&lt;domain&gt;.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f7c47-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7c47-125">See Also</span></span>


[<span data-ttu-id="f7c47-126">Pianificazione degli URL semplici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7c47-126">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


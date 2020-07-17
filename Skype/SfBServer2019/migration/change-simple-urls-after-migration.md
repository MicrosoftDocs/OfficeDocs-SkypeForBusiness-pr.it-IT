---
title: Modificare gli URL semplici dopo la migrazione
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server supporta gli URL semplici.
ms.openlocfilehash: 1b25dd74f5bdca433554091b3f8ce1c1d2dfa8ce
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753906"
---
# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="03043-103">Modificare gli URL semplici dopo la migrazione</span><span class="sxs-lookup"><span data-stu-id="03043-103">Change simple URLs after migration</span></span>

<span data-ttu-id="03043-104">Skype for Business Server supporta tre URL semplici:</span><span class="sxs-lookup"><span data-stu-id="03043-104">Skype for Business Server supports three simple URLs:</span></span>
  
- <span data-ttu-id="03043-p101">L'URL **riunione** (meet) viene utilizzato come URL di base per tutte le conferenze nel sito o nell'organizzazione. Con l'URL semplice riunione, i collegamenti per partecipare alle riunioni sono semplici da capire, da comunicare e da distribuire.</span><span class="sxs-lookup"><span data-stu-id="03043-p101">**Meet** is used as the base URL for all conferences in the site or organization. With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span> 
    
- <span data-ttu-id="03043-p102">L'URL **per accesso esterno** (dialin) consente di accedere alla pagina Web Impostazioni conferenza telefonica con accesso esterno. L'URL semplice per accesso esterno è incluso in tutti gli inviti a riunioni, in modo che gli utenti che desiderano eseguire l'accesso esterno alla riunione dispongano delle informazioni necessarie sul numero di telefono e sul PIN.</span><span class="sxs-lookup"><span data-stu-id="03043-p102">**Dial-in** enables access to the Dial-in Conferencing Settings webpage. The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> 
    
- <span data-ttu-id="03043-109">L' **amministratore** consente di accedere rapidamente al pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="03043-109">**Admin** enables quick access to the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="03043-110">L'URL semplice di amministrazione è interno all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="03043-110">The Admin simple URL is internal to your organization.</span></span> 
    
<span data-ttu-id="03043-111">Dopo aver eseguito la migrazione a Skype for Business Server, è necessario essere a conoscenza del modo in cui la modifica incide sui record DNS e sui certificati per gli URL semplici.</span><span class="sxs-lookup"><span data-stu-id="03043-111">After migrating to Skype for Business Server, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="03043-112">Se il Director di Skype for Business Server legacy rimane in uso nella topologia, non sono necessarie modifiche agli URL semplici.</span><span class="sxs-lookup"><span data-stu-id="03043-112">If the legacy Skype for Business Server Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="03043-113">Se il Director di Skype for Business Server è stato rimosso dalla topologia dopo la migrazione, è necessario aggiornare i record DNS degli URL semplificati in modo che puntino a uno dei pool di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="03043-113">If the Skype for Business Server Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Skype for Business Server pools.</span></span> <span data-ttu-id="03043-114">Ogni volta che si modifica il nome di un URL semplice, è necessario però eseguire Enable-CsComputer in ogni Director e Front End Server per registrare la modifica.</span><span class="sxs-lookup"><span data-stu-id="03043-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

## <a name="to-update-the-meet-simple-url"></a><span data-ttu-id="03043-115">Per aggiornare l'URL semplice riunione</span><span class="sxs-lookup"><span data-stu-id="03043-115">To update the Meet simple URL</span></span>

1. <span data-ttu-id="03043-116">In Generatore di topologie fare clic con il pulsante destro del mouse sul nodo principale **di Skype for Business Server**e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="03043-116">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="03043-117">Nel riquadro sinistro selezionare URL **semplici** , quindi fare clic su URL di **riunione** e quindi su **modifica URL**.</span><span class="sxs-lookup"><span data-stu-id="03043-117">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>
    
3. <span data-ttu-id="03043-118">Aggiornare l'URL in base al valore desiderato e quindi fare clic su **OK** per salvare l'URL modificato.</span><span class="sxs-lookup"><span data-stu-id="03043-118">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> 
    
## <a name="to-update-the-admin-simple-url"></a><span data-ttu-id="03043-119">Per aggiornare l'URL semplice di amministrazione</span><span class="sxs-lookup"><span data-stu-id="03043-119">To update the Admin simple URL</span></span>

1. <span data-ttu-id="03043-120">In Generatore di topologie fare clic con il pulsante destro del mouse sul nodo principale **di Skype for Business Server**e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="03043-120">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="03043-121">Selezionare gli URL **semplici** nel riquadro sinistro, quindi sotto la casella **URL di accesso amministrativo** , immettere l'URL semplice desiderato per l'accesso amministrativo al pannello di controllo di Skype for Business Server e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="03043-121">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Skype for Business Server Control Panel, and then click **OK**.</span></span>
    
   > [!TIP]
   > <span data-ttu-id="03043-122">È consigliabile utilizzare l'URL più semplice possibile per l'accesso amministrativo.</span><span class="sxs-lookup"><span data-stu-id="03043-122">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="03043-123">L'opzione più semplice è https://admin . <em>\<domain\></em> .</span><span class="sxs-lookup"><span data-stu-id="03043-123">The simplest option is https://admin.<em>\<domain\></em>.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="03043-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03043-124">See also</span></span>

[<span data-ttu-id="03043-125">Requisiti DNS per gli URL semplici in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="03043-125">DNS requirements for simple URLs in Skype for Business Server</span></span>](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)

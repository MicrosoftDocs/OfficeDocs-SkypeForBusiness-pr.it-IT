---
title: Modificare gli URL semplici dopo la migrazione
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype for Business Server supporta URL semplici.
ms.openlocfilehash: 786e3f5d7ed273c0f3c2ccc39ef1b539714de61b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195024"
---
# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="dc4c9-103">Modificare gli URL semplici dopo la migrazione</span><span class="sxs-lookup"><span data-stu-id="dc4c9-103">Change simple URLs after migration</span></span>

<span data-ttu-id="dc4c9-104">Skype for Business Server supporta tre semplici URL:</span><span class="sxs-lookup"><span data-stu-id="dc4c9-104">Skype for Business Server supports three simple URLs:</span></span>
  
- <span data-ttu-id="dc4c9-105">L' **incontro** viene usato come URL di base per tutte le conferenze nel sito o nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="dc4c9-105">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="dc4c9-106">Con l'URL semplice Meet, i collegamenti alle riunioni di partecipazione sono facili da comprendere e facili da comunicare e distribuire.</span><span class="sxs-lookup"><span data-stu-id="dc4c9-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span> 
    
- <span data-ttu-id="dc4c9-107">\*\*\*\* L'accesso esterno consente di accedere alla pagina Web delle impostazioni dei servizi di conferenza telefonica con chiamata in ingresso.</span><span class="sxs-lookup"><span data-stu-id="dc4c9-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="dc4c9-108">L'URL semplice per la chiamata in ingresso è incluso in tutti gli inviti alle riunioni, in modo che gli utenti che vogliono connettersi alla riunione possano accedere al numero di telefono e alle informazioni PIN necessarie.</span><span class="sxs-lookup"><span data-stu-id="dc4c9-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> 
    
- <span data-ttu-id="dc4c9-109">L' **amministratore** consente l'accesso rapido al pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="dc4c9-109">**Admin** enables quick access to the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="dc4c9-110">L'URL semplice amministratore è interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="dc4c9-110">The Admin simple URL is internal to your organization.</span></span> 
    
<span data-ttu-id="dc4c9-111">Dopo aver eseguito la migrazione a Skype for Business Server, è necessario essere consapevoli del modo in cui la modifica influisce sui record DNS e sui certificati per gli URL semplici.</span><span class="sxs-lookup"><span data-stu-id="dc4c9-111">After migrating to Skype for Business Server, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="dc4c9-112">Se il Director di Skype for Business Server legacy rimane in uso nella topologia, non sono necessarie modifiche agli URL semplici.</span><span class="sxs-lookup"><span data-stu-id="dc4c9-112">If the legacy Skype for Business Server Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="dc4c9-113">Se il Director di Skype for Business Server viene rimosso dalla topologia dopo la migrazione, è necessario che i record DNS URL semplici vengano aggiornati in modo che puntino a uno dei pool di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="dc4c9-113">If the Skype for Business Server Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Skype for Business Server pools.</span></span> <span data-ttu-id="dc4c9-114">Ogni volta che si modifica un nome di URL semplice, è necessario eseguire Enable-CsComputer su ogni Director e front end server per registrare la modifica.</span><span class="sxs-lookup"><span data-stu-id="dc4c9-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

## <a name="to-update-the-meet-simple-url"></a><span data-ttu-id="dc4c9-115">Per aggiornare l'URL semplice riunione</span><span class="sxs-lookup"><span data-stu-id="dc4c9-115">To update the Meet simple URL</span></span>

1. <span data-ttu-id="dc4c9-116">In Generatore di topologie fare clic con il pulsante destro del mouse sul nodo superiore **di Skype for Business Server**e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="dc4c9-116">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="dc4c9-117">Selezionare **URL semplici** nel riquadro sinistro, quindi sotto gli **URL delle riunioni:** Selezionare l'URL di riunione e quindi fare clic su **modifica URL**.</span><span class="sxs-lookup"><span data-stu-id="dc4c9-117">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>
    
3. <span data-ttu-id="dc4c9-118">Aggiornare l'URL con il valore desiderato e quindi fare clic su **OK** per salvare l'URL modificato.</span><span class="sxs-lookup"><span data-stu-id="dc4c9-118">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> 
    
## <a name="to-update-the-admin-simple-url"></a><span data-ttu-id="dc4c9-119">Per aggiornare l'URL semplice dell'amministratore</span><span class="sxs-lookup"><span data-stu-id="dc4c9-119">To update the Admin simple URL</span></span>

1. <span data-ttu-id="dc4c9-120">In Generatore di topologie fare clic con il pulsante destro del mouse sul nodo superiore **di Skype for Business Server**e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="dc4c9-120">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="dc4c9-121">Selezionare **URL semplici** nel riquadro sinistro, quindi sotto la casella **URL di accesso amministrativo** immettere l'URL semplice da usare per l'accesso amministrativo al pannello di controllo di Skype for Business Server e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="dc4c9-121">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Skype for Business Server Control Panel, and then click **OK**.</span></span>
    
   > [!TIP]
   > <span data-ttu-id="dc4c9-122">È consigliabile usare l'URL più semplice possibile per l'URL di amministratore.</span><span class="sxs-lookup"><span data-stu-id="dc4c9-122">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="dc4c9-123">L'opzione più semplice è https://admin. <em> \<domain\></em>.</span><span class="sxs-lookup"><span data-stu-id="dc4c9-123">The simplest option is https://admin.<em>\<domain\></em>.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="dc4c9-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc4c9-124">See also</span></span>

[<span data-ttu-id="dc4c9-125">Requisiti DNS per gli URL semplici in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dc4c9-125">DNS requirements for simple URLs in Skype for Business Server</span></span>](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)

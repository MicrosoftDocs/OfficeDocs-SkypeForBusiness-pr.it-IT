---
title: Definire l'esperienza utente per l'acquisizione manuale di una posizione in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d37f67d3-e248-483b-b64c-3986559ef357
description: Pianificazione per gli utenti mobili in una distribuzione E9-1-1 con i provider di trunking SIP, in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 85bf13325d3c7c16958877d50f49057a7f402226
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802716"
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server"></a><span data-ttu-id="cd5d1-103">Definire l'esperienza utente per l'acquisizione manuale di una posizione in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="cd5d1-103">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>
 
<span data-ttu-id="cd5d1-104">Pianificazione per gli utenti mobili in una distribuzione E9-1-1 con i provider di trunking SIP, in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="cd5d1-104">Planning for roaming users in an E9-1-1 deployment using SIP trunking providers, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="cd5d1-105">Se un client si trova all'esterno della rete o in una subnet non definita, l'utente può immettere manualmente una posizione.</span><span class="sxs-lookup"><span data-stu-id="cd5d1-105">If a client is located outside the network, or in an undefined subnet, the user can manually enter a location.</span></span> <span data-ttu-id="cd5d1-106">Durante una chiamata di emergenza, però, la chiamata verrà prima instradata a un dispatcher di Emergency Call Centre (ECRC) National/Regional E9-1-1, prima di essere indirizzato a un punto di risposta di sicurezza pubblica (PSAP).</span><span class="sxs-lookup"><span data-stu-id="cd5d1-106">But during an emergency call, the call will first be routed to a national/regional E9-1-1 Emergency Call Response Center (ECRC) dispatcher before being routed to a Public Safety Answering Point (PSAP).</span></span> <span data-ttu-id="cd5d1-107">ECRC eseguirà una query verbale sul chiamante per una posizione e quindi inoltra la chiamata al PSAP appropriato, in base alle informazioni fornite.</span><span class="sxs-lookup"><span data-stu-id="cd5d1-107">The ECRC will verbally query the caller for a location and then forward the call to the appropriate PSAP, based on the information provided.</span></span> 
  
<span data-ttu-id="cd5d1-108">**Gli utenti devono essere invitati a immettere una posizione quando non vengono forniti automaticamente dal servizio informazioni sulla posizione?**</span><span class="sxs-lookup"><span data-stu-id="cd5d1-108">**Should users be prompted to enter a location when one is not automatically provided by the Location Information service?**</span></span>
  
<span data-ttu-id="cd5d1-109">Ad esempio, se un client si trova in una subnet non definita, a casa, in un hotel o in qualsiasi altro punto all'esterno della rete, l'utente deve essere tenuto a immettere una posizione?</span><span class="sxs-lookup"><span data-stu-id="cd5d1-109">For example, if a client is located in an undefined subnet, at home, in a hotel, or anywhere else outside the network, should the user be required to enter a location?</span></span>
    
<span data-ttu-id="cd5d1-110">Per definire il comportamento del client, è possibile configurare l'impostazione della **posizione necessaria** nel criterio della posizione.</span><span class="sxs-lookup"><span data-stu-id="cd5d1-110">You can configure the **Location Required** setting in the location policy to define the client behavior.</span></span> <span data-ttu-id="cd5d1-111">L'impostazione di questo valore non significa che l'utente non verrà richiesto per una posizione.</span><span class="sxs-lookup"><span data-stu-id="cd5d1-111">Setting this value to No means that the user will not be prompted for a location.</span></span> <span data-ttu-id="cd5d1-112">L'impostazione di questo valore su Sì significa che l'utente verrà richiesto per una posizione, ma può chiudere la richiesta.</span><span class="sxs-lookup"><span data-stu-id="cd5d1-112">Setting this value to Yes means that the user will be prompted for a location, but can dismiss the prompt.</span></span> <span data-ttu-id="cd5d1-113">L'impostazione di questo valore su Disclaimer indica che all'utente verrà richiesto di trovare una posizione e verrà visualizzata una dichiarazione di non responsabilità se tenta di chiudere il messaggio.</span><span class="sxs-lookup"><span data-stu-id="cd5d1-113">Setting this value to Disclaimer means that the user will be prompted for a location, and will be shown a disclaimer if they try to dismiss the prompt.</span></span> <span data-ttu-id="cd5d1-114">In tutti i casi, l'utente può continuare a usare il client come di consueto.</span><span class="sxs-lookup"><span data-stu-id="cd5d1-114">In all cases, the user can continue to use the client as usual.</span></span>
    
<span data-ttu-id="cd5d1-115">Quando un utente immette manualmente una posizione, la posizione viene mappata all'indirizzo MAC del gateway predefinito della rete del client e viene archiviata in una tabella per utente che si trova nel client.</span><span class="sxs-lookup"><span data-stu-id="cd5d1-115">When a user manually enters a location, the location is mapped to the MAC address of the default gateway of the client's network, and is stored in a per-user table located on the client.</span></span> <span data-ttu-id="cd5d1-116">Quando l'utente torna in qualsiasi posizione precedentemente archiviata, il client Skype for business si imposta automaticamente in tale posizione.</span><span class="sxs-lookup"><span data-stu-id="cd5d1-116">When the user returns to any previously stored location, the Skype for Business client automatically sets itself to that location.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="cd5d1-117">È possibile modificare solo la posizione corrente del client, ma è anche possibile eliminare qualsiasi posizione archiviata nella tabella dell'utente locale.</span><span class="sxs-lookup"><span data-stu-id="cd5d1-117">You can modify only the current location of your client, but you can also delete any location stored in the local user's table.</span></span> 
  


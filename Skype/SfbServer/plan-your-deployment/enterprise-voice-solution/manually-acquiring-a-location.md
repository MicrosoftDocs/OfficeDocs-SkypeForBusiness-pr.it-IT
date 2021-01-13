---
title: Definire l'esperienza utente per l'acquisizione manuale di una posizione in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Pianificazione per gli utenti in roaming in una distribuzione di E9-1-1 utilizzando i provider di trunking SIP, in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: dd43d78b4c139b4fb30a0b4ba379d96150314332
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825426"
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server"></a><span data-ttu-id="7790c-103">Definire l'esperienza utente per l'acquisizione manuale di una posizione in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7790c-103">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>
 
<span data-ttu-id="7790c-104">Pianificazione per gli utenti in roaming in una distribuzione di E9-1-1 utilizzando i provider di trunking SIP, in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="7790c-104">Planning for roaming users in an E9-1-1 deployment using SIP trunking providers, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="7790c-p101">Se un client si trova all'esterno della rete o in una subnet non definita, l'utente può immettere manualmente una posizione. La chiamata di emergenza però verrà innanzitutto instradata a un dispatcher ECRC (Emergency Call Response Center) del servizio E9-1-1 nazionale/regionale prima di essere instradata a un centro di raccolta delle chiamate di emergenza (PSAP, Public Safety Answering Point). Il dispatcher ECRC richiederà verbalmente al chiamante la posizione e inoltrerà quindi la chiamata al centro PSAP appropriato in base alle informazioni fornite.</span><span class="sxs-lookup"><span data-stu-id="7790c-p101">If a client is located outside the network, or in an undefined subnet, the user can manually enter a location. But during an emergency call, the call will first be routed to a national/regional E9-1-1 Emergency Call Response Center (ECRC) dispatcher before being routed to a Public Safety Answering Point (PSAP). The ECRC will verbally query the caller for a location and then forward the call to the appropriate PSAP, based on the information provided.</span></span> 
  
<span data-ttu-id="7790c-108">**È necessario che agli utenti venga richiesto di immettere un percorso quando uno non viene fornito automaticamente dal servizio informazioni percorso?**</span><span class="sxs-lookup"><span data-stu-id="7790c-108">**Should users be prompted to enter a location when one is not automatically provided by the Location Information service?**</span></span>
  
<span data-ttu-id="7790c-109">Se, ad esempio, un client si trova in una subnet non definita, a casa, in un albergo o in qualsiasi altro luogo esterno alla rete, è necessario richiedere all'utente la specifica di una posizione?</span><span class="sxs-lookup"><span data-stu-id="7790c-109">For example, if a client is located in an undefined subnet, at home, in a hotel, or anywhere else outside the network, should the user be required to enter a location?</span></span>
    
<span data-ttu-id="7790c-p102">È possibile configurare l'impostazione **Posizione obbligatoria** nei criteri percorso per definire il comportamento del client. L'impostazione di questo valore su No indica che all'utente non verrà richiesta una posizione. Se invece si imposta il valore su Sì, all'utente verrà richiesta la specifica della posizione ma potrà ignorare il messaggio. Il valore Dichiarazione di non responsabilità indica invece che all'utente verrà richiesta una posizione e visualizzata una dichiarazione di non responsabilità se tenta di ignorare il messaggio. In tutti i casi, l'utente potrà continuare a utilizzare il client come sempre.</span><span class="sxs-lookup"><span data-stu-id="7790c-p102">You can configure the **Location Required** setting in the location policy to define the client behavior. Setting this value to No means that the user will not be prompted for a location. Setting this value to Yes means that the user will be prompted for a location, but can dismiss the prompt. Setting this value to Disclaimer means that the user will be prompted for a location, and will be shown a disclaimer if they try to dismiss the prompt. In all cases, the user can continue to use the client as usual.</span></span>
    
<span data-ttu-id="7790c-115">Quando un utente immette manualmente una posizione, il percorso viene mappato all'indirizzo MAC del gateway predefinito della rete del client ed è archiviato in una tabella per utente che si trova nel client.</span><span class="sxs-lookup"><span data-stu-id="7790c-115">When a user manually enters a location, the location is mapped to the MAC address of the default gateway of the client's network, and is stored in a per-user table located on the client.</span></span> <span data-ttu-id="7790c-116">Quando l'utente torna a qualsiasi percorso precedentemente memorizzato, il client Skype for business si imposta automaticamente su tale percorso.</span><span class="sxs-lookup"><span data-stu-id="7790c-116">When the user returns to any previously stored location, the Skype for Business client automatically sets itself to that location.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="7790c-117">È possibile modificare solo la posizione corrente del client, ma è anche possibile eliminare qualsiasi percorso memorizzato nella tabella dell'utente locale.</span><span class="sxs-lookup"><span data-stu-id="7790c-117">You can modify only the current location of your client, but you can also delete any location stored in the local user's table.</span></span> 
  


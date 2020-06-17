---
title: Verificare la federazione e l'accesso remoto per gli utenti esterni
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
description: Dopo la transizione della route di federazione al server perimetrale di Skype for Business Server 2019, è consigliabile eseguire alcuni test funzionali per verificare che la Federazione venga eseguita come previsto. I test per l'accesso utente esterno devono includere ogni tipo di utente esterno supportato dall'organizzazione, inclusi alcuni o tutti quelli indicati di seguito.
ms.openlocfilehash: b2567f4e46bd39d2748e3a4a3ba6cc5d6c197b11
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751668"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="4860b-104">Verificare la federazione e l'accesso remoto per gli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="4860b-104">Verify federation and remote access for external users</span></span>

<span data-ttu-id="4860b-105">Dopo la transizione della route di federazione al server perimetrale di Skype for Business Server 2019, è consigliabile eseguire alcuni test funzionali per verificare che la Federazione venga eseguita come previsto.</span><span class="sxs-lookup"><span data-stu-id="4860b-105">After transitioning the federation route to the Skype for Business Server 2019 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="4860b-106">I test per l'accesso utente esterno devono includere ogni tipo di utente esterno supportato dall'organizzazione, inclusi alcuni o tutti quelli indicati di seguito.</span><span class="sxs-lookup"><span data-stu-id="4860b-106">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>
  
### <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="4860b-107">Testare la connettività degli utenti esterni e l'accesso esterno</span><span class="sxs-lookup"><span data-stu-id="4860b-107">Test connectivity of external users and external access</span></span>

- <span data-ttu-id="4860b-108">Utenti provenienti da almeno un dominio federato, un utente interno su Skype for Business Server 2019 e un utente nell'installazione legacy.</span><span class="sxs-lookup"><span data-stu-id="4860b-108">Users from at least one federated domain, an internal user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="4860b-109">Testare la messaggistica istantanea, il traffico audio/video e la condivisione del desktop.</span><span class="sxs-lookup"><span data-stu-id="4860b-109">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>
    
- <span data-ttu-id="4860b-110">Utenti di ogni provider di servizi di messaggistica istantanea supportato dall'organizzazione (e per i quali è stato completato il provisioning) che comunicano con un utente in Skype for Business Server 2019 e un utente nell'installazione legacy.</span><span class="sxs-lookup"><span data-stu-id="4860b-110">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Skype for Business Server 2019 and a user on the legacy install.</span></span> 
    
- <span data-ttu-id="4860b-111">Verificare che gli utenti anonimi siano in grado di partecipare alle conferenze.</span><span class="sxs-lookup"><span data-stu-id="4860b-111">Verify that anonymous users are able to join conferences.</span></span>
    
- <span data-ttu-id="4860b-112">Un utente ospitato nell'installazione legacy utilizzando l'accesso degli utenti remoti (logging i nPer Lync Server/Skype for business dall'esterno della rete Intranet ma senza VPN) con un utente in Skype for Business Server 2019 e un utente nell'installazione legacy.</span><span class="sxs-lookup"><span data-stu-id="4860b-112">A user hosted on the legacy install using remote user access (logging i nto Lync Server/Skype for Business from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="4860b-113">Testare la messaggistica istantanea, la presenza, il traffico audio/video e la condivisione del desktop.</span><span class="sxs-lookup"><span data-stu-id="4860b-113">Test IM, presence, A/V, and desktop sharing.</span></span>
    
- <span data-ttu-id="4860b-114">Un utente ospitato in Skype for Business Server 2019 utilizzando l'accesso degli utenti remoti (accedere a Skype for Business Server 2019 dall'esterno della rete Intranet ma senza VPN) con un utente in Skype for Business Server 2019 e un utente nell'installazione legacy.</span><span class="sxs-lookup"><span data-stu-id="4860b-114">A user hosted on Skype for Business Server 2019 using remote user access (logging in to Skype for Business Server 2019 from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="4860b-115">Testare la messaggistica istantanea, la presenza, il traffico audio/video e la condivisione del desktop.</span><span class="sxs-lookup"><span data-stu-id="4860b-115">Test IM, presence, A/V, and desktop sharing.</span></span>
    


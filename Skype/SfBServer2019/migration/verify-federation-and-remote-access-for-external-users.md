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
description: Dopo aver eseguito la transizione della route di federazione al server perimetrale Skype for Business Server 2019, è necessario eseguire alcuni test funzionali per verificare che la federazione funzioni come previsto. I test per l'accesso utente esterno devono includere ogni tipo di utente esterno supportato dall'organizzazione, inclusi alcuni o tutti quelli indicati di seguito.
ms.openlocfilehash: b2567f4e46bd39d2748e3a4a3ba6cc5d6c197b11
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751668"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="aa736-104">Verificare la federazione e l'accesso remoto per gli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="aa736-104">Verify federation and remote access for external users</span></span>

<span data-ttu-id="aa736-105">Dopo aver eseguito la transizione della route di federazione al server perimetrale Skype for Business Server 2019, è necessario eseguire alcuni test funzionali per verificare che la federazione funzioni come previsto.</span><span class="sxs-lookup"><span data-stu-id="aa736-105">After transitioning the federation route to the Skype for Business Server 2019 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="aa736-106">I test per l'accesso utente esterno devono includere ogni tipo di utente esterno supportato dall'organizzazione, inclusi alcuni o tutti quelli indicati di seguito.</span><span class="sxs-lookup"><span data-stu-id="aa736-106">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>
  
### <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="aa736-107">Testare la connettività degli utenti esterni e l'accesso esterno</span><span class="sxs-lookup"><span data-stu-id="aa736-107">Test connectivity of external users and external access</span></span>

- <span data-ttu-id="aa736-108">Utenti di almeno un dominio federato, un utente interno in Skype for Business Server 2019 e un utente nell'installazione legacy.</span><span class="sxs-lookup"><span data-stu-id="aa736-108">Users from at least one federated domain, an internal user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="aa736-109">Testare la messaggistica istantanea, il traffico audio/video e la condivisione del desktop.</span><span class="sxs-lookup"><span data-stu-id="aa736-109">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>
    
- <span data-ttu-id="aa736-110">Utenti di ogni provider di servizi di messaggistica istantanea pubblica supportati dall'organizzazione (e per i quali è stato completato il provisioning) che comunicano con un utente in Skype for Business Server 2019 e con un utente nell'installazione legacy.</span><span class="sxs-lookup"><span data-stu-id="aa736-110">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Skype for Business Server 2019 and a user on the legacy install.</span></span> 
    
- <span data-ttu-id="aa736-111">Verificare che gli utenti anonimi siano in grado di partecipare alle conferenze.</span><span class="sxs-lookup"><span data-stu-id="aa736-111">Verify that anonymous users are able to join conferences.</span></span>
    
- <span data-ttu-id="aa736-112">Un utente ospitato nell'installazione legacy usando l'accesso utente remoto (registrazione i nto Lync Server/Skype for Business dall'esterno della Intranet ma senza VPN) con un utente in Skype for Business Server 2019 e un utente nell'installazione legacy.</span><span class="sxs-lookup"><span data-stu-id="aa736-112">A user hosted on the legacy install using remote user access (logging i nto Lync Server/Skype for Business from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="aa736-113">Testare la messaggistica istantanea, la presenza, il traffico audio/video e la condivisione del desktop.</span><span class="sxs-lookup"><span data-stu-id="aa736-113">Test IM, presence, A/V, and desktop sharing.</span></span>
    
- <span data-ttu-id="aa736-114">Un utente ospitato su Skype for Business Server 2019 con accesso utente remoto (accesso a Skype for Business Server 2019 dall'esterno della intranet ma senza VPN) con un utente in Skype for Business Server 2019 e un utente nell'installazione legacy.</span><span class="sxs-lookup"><span data-stu-id="aa736-114">A user hosted on Skype for Business Server 2019 using remote user access (logging in to Skype for Business Server 2019 from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="aa736-115">Testare la messaggistica istantanea, la presenza, il traffico audio/video e la condivisione del desktop.</span><span class="sxs-lookup"><span data-stu-id="aa736-115">Test IM, presence, A/V, and desktop sharing.</span></span>
    


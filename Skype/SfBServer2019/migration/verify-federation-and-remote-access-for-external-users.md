---
title: Verificare la Federazione e l'accesso remoto per gli utenti esterni
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Dopo aver eseguito la transizione alla route della Federazione al server Edge di Skype for Business Server 2019, è necessario eseguire alcuni test funzionali per verificare che la Federazione venga eseguita come previsto. I test per l'accesso degli utenti esterni devono includere ogni tipo di utente esterno supportato dall'organizzazione, inclusi uno o tutti gli elementi seguenti.
ms.openlocfilehash: ea17cbc8643d864f464da8e8a582191504970059
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244087"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="f50fd-104">Verificare la Federazione e l'accesso remoto per gli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="f50fd-104">Verify federation and remote access for external users</span></span>

<span data-ttu-id="f50fd-105">Dopo aver eseguito la transizione alla route della Federazione al server Edge di Skype for Business Server 2019, è necessario eseguire alcuni test funzionali per verificare che la Federazione venga eseguita come previsto.</span><span class="sxs-lookup"><span data-stu-id="f50fd-105">After transitioning the federation route to the Skype for Business Server 2019 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="f50fd-106">I test per l'accesso degli utenti esterni devono includere ogni tipo di utente esterno supportato dall'organizzazione, inclusi uno o tutti gli elementi seguenti.</span><span class="sxs-lookup"><span data-stu-id="f50fd-106">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>
  
### <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="f50fd-107">Testare la connettività degli utenti esterni e dell'accesso esterno</span><span class="sxs-lookup"><span data-stu-id="f50fd-107">Test connectivity of external users and external access</span></span>

- <span data-ttu-id="f50fd-108">Utenti di almeno un dominio federato, un utente interno in Skype for Business Server 2019 e un utente nell'installazione legacy.</span><span class="sxs-lookup"><span data-stu-id="f50fd-108">Users from at least one federated domain, an internal user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="f50fd-109">Test di messaggistica istantanea (IM), presenza, audio/video (A/V) e condivisione desktop.</span><span class="sxs-lookup"><span data-stu-id="f50fd-109">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>
    
- <span data-ttu-id="f50fd-110">Utenti di ogni provider di servizi di messaggistica istantanea pubblico supportato dall'organizzazione (e per il quale è stato completato il provisioning) che comunica con un utente in Skype for Business Server 2019 e un utente nell'installazione legacy.</span><span class="sxs-lookup"><span data-stu-id="f50fd-110">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Skype for Business Server 2019 and a user on the legacy install.</span></span> 
    
- <span data-ttu-id="f50fd-111">Verificare che gli utenti anonimi siano in grado di partecipare a conferenze.</span><span class="sxs-lookup"><span data-stu-id="f50fd-111">Verify that anonymous users are able to join conferences.</span></span>
    
- <span data-ttu-id="f50fd-112">Un utente ospitato nell'installazione legacy che usa l'accesso degli utenti remoti (registrazione i nPer Lync Server/Skype for business dall'esterno della Intranet ma senza VPN) con un utente in Skype for Business Server 2019 e un utente nell'installazione legacy.</span><span class="sxs-lookup"><span data-stu-id="f50fd-112">A user hosted on the legacy install using remote user access (logging i nto Lync Server/Skype for Business from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="f50fd-113">Test di messaggistica istantanea, presenza, A/V e condivisione desktop.</span><span class="sxs-lookup"><span data-stu-id="f50fd-113">Test IM, presence, A/V, and desktop sharing.</span></span>
    
- <span data-ttu-id="f50fd-114">Un utente ospitato in Skype for Business Server 2019 usando l'accesso degli utenti remoti (accedere a Skype for Business Server 2019 dall'esterno della Intranet ma senza VPN) con un utente in Skype for Business Server 2019 e un utente nell'installazione legacy.</span><span class="sxs-lookup"><span data-stu-id="f50fd-114">A user hosted on Skype for Business Server 2019 using remote user access (logging in to Skype for Business Server 2019 from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="f50fd-115">Test di messaggistica istantanea, presenza, A/V e condivisione desktop.</span><span class="sxs-lookup"><span data-stu-id="f50fd-115">Test IM, presence, A/V, and desktop sharing.</span></span>
    


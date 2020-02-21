---
title: Verificare la federazione e l'accesso remoto per gli utenti esterni
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify federation and remote access for external users
ms:assetid: a383fefb-c428-4462-93fd-15ba540fa867
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688163(v=OCS.15)
ms:contentKeyID: 49733768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f95f08997a9a65bdbb6c21a8850ee059b0dc64c6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188959"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="91bea-102">Verificare la federazione e l'accesso remoto per gli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="91bea-102">Verify federation and remote access for external users</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91bea-103">_**Ultimo argomento modificato:** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="91bea-103">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="91bea-104">Dopo la transizione della route di federazione al server perimetrale di Lync Server 2013, è necessario eseguire alcuni test funzionali per verificare che la Federazione venga eseguita come previsto.</span><span class="sxs-lookup"><span data-stu-id="91bea-104">After transitioning the federation route to the Lync Server 2013 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="91bea-105">I test per l'accesso utente esterno devono includere ogni tipo di utente esterno supportato dall'organizzazione, inclusi alcuni o tutti quelli indicati di seguito.</span><span class="sxs-lookup"><span data-stu-id="91bea-105">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="91bea-106">Testare la connettività degli utenti esterni e dell'accesso esterno</span><span class="sxs-lookup"><span data-stu-id="91bea-106">Test Connectivity of External Users and External access</span></span>

  - <span data-ttu-id="91bea-107">Utenti provenienti da almeno un dominio federato, un utente interno in Lync Server 2013 e un utente in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="91bea-107">Users from at least one federated domain, an internal user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="91bea-108">Testare la messaggistica istantanea, il traffico audio/video e la condivisione del desktop.</span><span class="sxs-lookup"><span data-stu-id="91bea-108">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>

  - <span data-ttu-id="91bea-109">Utenti di ogni provider di servizi di messaggistica istantanea supportato dall'organizzazione (e per i quali è stato completato il provisioning) che comunicano con un utente in Lync Server 2013 e un utente in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="91bea-109">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Lync Server 2013 and a user on Lync Server 2010.</span></span>

  - <span data-ttu-id="91bea-110">Verificare che gli utenti anonimi siano in grado di partecipare alle conferenze.</span><span class="sxs-lookup"><span data-stu-id="91bea-110">Verify that anonymous users are able to join conferences.</span></span>

  - <span data-ttu-id="91bea-111">Un utente ospitato in Lync Server 2010 utilizzando l'accesso degli utenti remoti (accedendo a Lync Server 2010 dall'esterno della rete Intranet ma senza VPN) con un utente in Lync Server 2013 e un utente in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="91bea-111">A user hosted on Lync Server 2010 using remote user access (logging into Lync Server 2010 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="91bea-112">Testare la messaggistica istantanea, la presenza, il traffico audio/video e la condivisione del desktop.</span><span class="sxs-lookup"><span data-stu-id="91bea-112">Test IM, presence, A/V, and desktop sharing.</span></span>

  - <span data-ttu-id="91bea-113">Un utente ospitato in Lync Server 2013 utilizzando l'accesso degli utenti remoti (accedendo a Lync Server 2013 dall'esterno della rete Intranet ma senza VPN) con un utente in Lync Server 2013 e un utente in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="91bea-113">A user hosted on Lync Server 2013 using remote user access (logging into Lync Server 2013 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="91bea-114">Testare la messaggistica istantanea, la presenza, il traffico audio/video e la condivisione del desktop.</span><span class="sxs-lookup"><span data-stu-id="91bea-114">Test IM, presence, A/V, and desktop sharing.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


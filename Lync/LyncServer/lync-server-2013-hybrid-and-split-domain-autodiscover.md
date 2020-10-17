---
title: 'Lync Server 2013: ibrido e Split-Domain-individuazione automatica'
description: 'Lync Server 2013: ibrido e Split-Domain-individuazione automatica.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hybrid and split-domain - Autodiscover
ms:assetid: c855bcc5-b656-4d2d-92d6-f016f2797d3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945652(v=OCS.15)
ms:contentKeyID: 51541520
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 972233fd10d2b68a002d2d3a203f61bb0bd29574
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554882"
---
# <a name="hybrid-and-split-domain---autodiscover-in-lync-server-2013"></a><span data-ttu-id="d4a45-103">Ambiente ibrido e Split-Domain-individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4a45-103">Hybrid and split-domain - Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4a45-104">_**Ultimo argomento modificato:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="d4a45-104">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="d4a45-105">Uno spazio di indirizzi SIP condiviso, noto anche come distribuzione di *domini intermedi* o una distribuzione *ibrida* , è una configurazione in cui gli utenti vengono distribuiti in una distribuzione locale e in un ambiente online.</span><span class="sxs-lookup"><span data-stu-id="d4a45-105">A shared SIP address space, also known as a *split-domain* deployment, or a *hybrid* deployment, is a configuration where users are deployed across an on-premise deployment and an online environment.</span></span> <span data-ttu-id="d4a45-106">L'esito desiderato consiste nel fatto che un utente, indipendentemente dal luogo in cui si trova il server Home (locale o online), acceda alla distribuzione e venga reindirizzato al percorso del server principale.</span><span class="sxs-lookup"><span data-stu-id="d4a45-106">The desired outcome is to have a user, regardless of where their home server is located (on-premise or online), log into the deployment and be redirected to their home server location.</span></span> <span data-ttu-id="d4a45-107">A tale scopo, la caratteristica di individuazione automatica di Lync Server 2013 viene utilizzata per reindirizzare l'utente online alla topologia online.</span><span class="sxs-lookup"><span data-stu-id="d4a45-107">To accomplish this, the Autodiscover feature of Lync Server 2013 is used to redirect the online user to the online topology.</span></span> <span data-ttu-id="d4a45-108">È possibile eseguire questa operazione configurando l'URL (Uniform Resource Locator) di individuazione automatica utilizzando Lync Server Management Shell, il cmdlet **Get-CsHostingProvider** e il cmdlet **Set-CsHostingProvider** .</span><span class="sxs-lookup"><span data-stu-id="d4a45-108">You can do this by configuring the Autodiscover uniform resource locator (URL) by using the Lync Server Management Shell, the **Get-CsHostingProvider** cmdlet, and the **Set-CsHostingProvider** cmdlet.</span></span>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a><span data-ttu-id="d4a45-109">Mobilità per la distribuzione del dominio diviso</span><span class="sxs-lookup"><span data-stu-id="d4a45-109">Mobility for the Split Domain Deployment</span></span>

<span data-ttu-id="d4a45-110">Sarà necessario raccogliere e prendere nota degli attributi distribuiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4a45-110">You will need to collect and record the following deployed attributes:</span></span>

  - <span data-ttu-id="d4a45-111">Da Lync Server Management Shell, digitare</span><span class="sxs-lookup"><span data-stu-id="d4a45-111">From the Lync Server Management Shell, type</span></span>
    
        Get-CsHostingProvider

  - <span data-ttu-id="d4a45-112">Nei risultati, individuare il provider online con l'attributo **ProxyFQDN**.</span><span class="sxs-lookup"><span data-stu-id="d4a45-112">In the results, find the online provider with the attribute **ProxyFQDN**.</span></span> <span data-ttu-id="d4a45-113">Ad esempio, sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d4a45-113">For example, sipfed.online.lync.com.</span></span>

  - <span data-ttu-id="d4a45-114">Registrare il valore di ProxyFQDN.</span><span class="sxs-lookup"><span data-stu-id="d4a45-114">Record the value of the ProxyFQDN.</span></span>

  - <span data-ttu-id="d4a45-115">Abilitare la Federazione nel pannello di controllo di Lync Server locale, consentendo la Federazione con il provider online.</span><span class="sxs-lookup"><span data-stu-id="d4a45-115">Enable federation in the on-premise Lync Server Control Panel, allowing federation with the online provider.</span></span>

  - <span data-ttu-id="d4a45-116">Abilitare la federazione per il provider online.</span><span class="sxs-lookup"><span data-stu-id="d4a45-116">Enable federation for the online provider.</span></span> <span data-ttu-id="d4a45-117">Per impostazione predefinita, tutti gli utenti online sono abilitati per la Federazione dei domini e possono comunicare con tutti i domini.</span><span class="sxs-lookup"><span data-stu-id="d4a45-117">By default, all online users are enabled for domain federation and can communicate with all domains.</span></span>

  - <span data-ttu-id="d4a45-118">Se si definiscono domini bloccati e consentiti, determinare i domini che verranno esplicitamente consentiti o bloccati in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="d4a45-118">If you will define blocked and allowed domains, determine the domains that you will explicitly allow or explicitly block.</span></span>

  - <span data-ttu-id="d4a45-119">Per la Federazione online, è necessario pianificare le eccezioni del firewall, i certificati e i record host DNS (A o AAAA, se si utilizza IPv6).</span><span class="sxs-lookup"><span data-stu-id="d4a45-119">For online federation, you must plan for firewall exceptions, certificates, and DNS host (A or AAAA, if using IPv6) records.</span></span> <span data-ttu-id="d4a45-120">È inoltre necessario configurare i criteri di federazione.</span><span class="sxs-lookup"><span data-stu-id="d4a45-120">Additionally, you must configure federation policies.</span></span> <span data-ttu-id="d4a45-121">Per informazioni dettagliate, vedere [Planning for Lync Server 2013 e Office Communications Server Federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md).</span><span class="sxs-lookup"><span data-stu-id="d4a45-121">For details, see [Planning for Lync Server 2013 and Office Communications Server federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


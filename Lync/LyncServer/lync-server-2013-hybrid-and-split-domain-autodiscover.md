---
title: 'Lync Server 2013: Hybrid e Split-Domain-individuazione automatica'
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
ms.openlocfilehash: ce38bba4717e3340e7eacf33ce67fc357d208b83
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763014"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hybrid-and-split-domain---autodiscover-in-lync-server-2013"></a><span data-ttu-id="822c6-102">Hybrid e Split-Domain-individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="822c6-102">Hybrid and split-domain - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="822c6-103">_**Argomento Ultima modifica:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="822c6-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="822c6-104">Uno spazio di indirizzi SIP condiviso, noto anche come distribuzione di *domini separati* o una distribuzione *ibrida* , è una configurazione in cui gli utenti vengono distribuiti in una distribuzione locale e in un ambiente online.</span><span class="sxs-lookup"><span data-stu-id="822c6-104">A shared SIP address space, also known as a *split-domain* deployment, or a *hybrid* deployment, is a configuration where users are deployed across an on-premise deployment and an online environment.</span></span> <span data-ttu-id="822c6-105">Il risultato desiderato consiste nell'avere un utente, indipendentemente da dove si trova il proprio Home Server (locale o online), accedere alla distribuzione ed essere reindirizzati alla posizione del proprio Home Server.</span><span class="sxs-lookup"><span data-stu-id="822c6-105">The desired outcome is to have a user, regardless of where their home server is located (on-premise or online), log into the deployment and be redirected to their home server location.</span></span> <span data-ttu-id="822c6-106">A questo scopo, la funzionalità di individuazione automatica di Lync Server 2013 viene usata per reindirizzare l'utente online alla topologia online.</span><span class="sxs-lookup"><span data-stu-id="822c6-106">To accomplish this, the Autodiscover feature of Lync Server 2013 is used to redirect the online user to the online topology.</span></span> <span data-ttu-id="822c6-107">Puoi eseguire questa operazione configurando l'URL (Uniform Resource Locator) di individuazione automatica tramite Lync Server Management Shell, il cmdlet **Get-CsHostingProvider** e il cmdlet **Set-CsHostingProvider** .</span><span class="sxs-lookup"><span data-stu-id="822c6-107">You can do this by configuring the Autodiscover uniform resource locator (URL) by using the Lync Server Management Shell, the **Get-CsHostingProvider** cmdlet, and the **Set-CsHostingProvider** cmdlet.</span></span>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a><span data-ttu-id="822c6-108">Mobilità per la distribuzione di domini divisi</span><span class="sxs-lookup"><span data-stu-id="822c6-108">Mobility for the Split Domain Deployment</span></span>

<span data-ttu-id="822c6-109">Sarà necessario raccogliere e registrare i seguenti attributi distribuiti:</span><span class="sxs-lookup"><span data-stu-id="822c6-109">You will need to collect and record the following deployed attributes:</span></span>

  - <span data-ttu-id="822c6-110">In Lync Server Management Shell digitare</span><span class="sxs-lookup"><span data-stu-id="822c6-110">From the Lync Server Management Shell, type</span></span>
    
        Get-CsHostingProvider

  - <span data-ttu-id="822c6-111">Nei risultati trovare il provider online con l'attributo **ProxyFqdn**.</span><span class="sxs-lookup"><span data-stu-id="822c6-111">In the results, find the online provider with the attribute **ProxyFQDN**.</span></span> <span data-ttu-id="822c6-112">Ad esempio, sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="822c6-112">For example, sipfed.online.lync.com.</span></span>

  - <span data-ttu-id="822c6-113">Registrare il valore di ProxyFQDN.</span><span class="sxs-lookup"><span data-stu-id="822c6-113">Record the value of the ProxyFQDN.</span></span>

  - <span data-ttu-id="822c6-114">Abilitare la Federazione nel pannello di controllo di Lync Server locale, consentendo la Federazione con il provider online.</span><span class="sxs-lookup"><span data-stu-id="822c6-114">Enable federation in the on-premise Lync Server Control Panel, allowing federation with the online provider.</span></span>

  - <span data-ttu-id="822c6-115">Abilitare la Federazione per il provider online.</span><span class="sxs-lookup"><span data-stu-id="822c6-115">Enable federation for the online provider.</span></span> <span data-ttu-id="822c6-116">Per impostazione predefinita, tutti gli utenti online sono abilitati per la Federazione del dominio e possono comunicare con tutti i domini.</span><span class="sxs-lookup"><span data-stu-id="822c6-116">By default, all online users are enabled for domain federation and can communicate with all domains.</span></span>

  - <span data-ttu-id="822c6-117">Se si definiscono i domini bloccati e consentiti, determinare i domini che verranno esplicitamente consentiti o bloccati esplicitamente.</span><span class="sxs-lookup"><span data-stu-id="822c6-117">If you will define blocked and allowed domains, determine the domains that you will explicitly allow or explicitly block.</span></span>

  - <span data-ttu-id="822c6-118">Per la Federazione online, è necessario pianificare le eccezioni, i certificati e l'host DNS (A o AAAA, se si usano i record IPv6).</span><span class="sxs-lookup"><span data-stu-id="822c6-118">For online federation, you must plan for firewall exceptions, certificates, and DNS host (A or AAAA, if using IPv6) records.</span></span> <span data-ttu-id="822c6-119">È inoltre necessario configurare i criteri federativi.</span><span class="sxs-lookup"><span data-stu-id="822c6-119">Additionally, you must configure federation policies.</span></span> <span data-ttu-id="822c6-120">Per informazioni dettagliate, vedere [pianificazione per Lync server 2013 e Office Communications Server Federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md).</span><span class="sxs-lookup"><span data-stu-id="822c6-120">For details, see [Planning for Lync Server 2013 and Office Communications Server federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


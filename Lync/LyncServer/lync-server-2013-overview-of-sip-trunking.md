---
title: 'Lync Server 2013: Panoramica del trunking SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of SIP trunking
ms:assetid: 204f2c21-436f-4b2d-93ea-d6db98fa2952
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398285(v=OCS.15)
ms:contentKeyID: 48183601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e2c79261923456575e208aa472daae4aaab5f55
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978632"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="2b488-102">Panoramica del trunking SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b488-102">Overview of SIP trunking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b488-103">_**Argomento Ultima modifica:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="2b488-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="2b488-104">La distribuzione del trunking SIP può essere un grande passo verso la semplificazione delle telecomunicazioni dell'organizzazione e la preparazione di miglioramenti aggiornati alle comunicazioni in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="2b488-104">Deploying SIP trunking can be a big step toward simplifying your organization’s telecommunications and preparing for up-to-date enhancements to real-time communications.</span></span> <span data-ttu-id="2b488-105">Uno dei vantaggi principali del trunking SIP è che puoi consolidare le connessioni dell'organizzazione con la rete PSTN (Public Switched Telephone Network) in un sito centrale, in contrapposizione al suo predecessore, il trunking di Time Division Multiplexing (TDM), che in genere richiede un trunk separato da ogni sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="2b488-105">One of the primary advantages of SIP trunking is that you can consolidate your organization’s connections to the public switched telephone network (PSTN) at a central site, as opposed to its predecessor, time division multiplexing (TDM) trunking, which typically requires a separate trunk from each branch site.</span></span>

<div>

## <a name="sip-trunking-in-lync-server"></a><span data-ttu-id="2b488-106">Trunking SIP in Lync Server</span><span class="sxs-lookup"><span data-stu-id="2b488-106">SIP Trunking in Lync Server</span></span>

<span data-ttu-id="2b488-107">Le funzionalità di trunking SIP di Lync Server 2013 consentono le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2b488-107">The Lync Server 2013 SIP trunking capabilities enable the following:</span></span>

  - <span data-ttu-id="2b488-108">Un utente aziendale, sia all'interno che all'esterno del firewall aziendale, può effettuare una chiamata locale o una chiamata a lunga distanza specificata da un numero conforme E. 164 che viene terminato sulla rete PSTN come servizio del provider di servizi corrispondente.</span><span class="sxs-lookup"><span data-stu-id="2b488-108">An enterprise user, whether inside or outside the corporate firewall, can make a local call or a long-distance call that is specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>

  - <span data-ttu-id="2b488-109">Qualsiasi abbonato PSTN può contattare un utente aziendale all'interno o all'esterno del firewall aziendale componendo un numero DID (Direct Interior Dialing) associato all'utente aziendale.</span><span class="sxs-lookup"><span data-stu-id="2b488-109">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number that is associated with that enterprise user.</span></span>

</div>

<div>

## <a name="cost-savings"></a><span data-ttu-id="2b488-110">Risparmi sui costi</span><span class="sxs-lookup"><span data-stu-id="2b488-110">Cost Savings</span></span>

<span data-ttu-id="2b488-111">Il risparmio di costi associato al trunking SIP può essere sostanziale:</span><span class="sxs-lookup"><span data-stu-id="2b488-111">The cost savings associated with SIP trunking can be substantial:</span></span>

  - <span data-ttu-id="2b488-112">Le chiamate interurbane in genere costano molto meno attraverso un trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="2b488-112">Long distance calls typically cost much less through a SIP trunk.</span></span>

  - <span data-ttu-id="2b488-113">È possibile tagliare i costi di gestibilità e ridurre la complessità della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="2b488-113">You can cut manageability costs and reduce the complexity of deployment.</span></span>

  - <span data-ttu-id="2b488-114">Le tariffe BRI (Basic Rate Interface) e PRI (Primary Rate Interface) possono essere eliminate se si connette un trunk SIP direttamente al proprio ITSP a costi decisamente più bassi.</span><span class="sxs-lookup"><span data-stu-id="2b488-114">Basic rate interface (BRI) and primary rate interface (PRI) fees can be eliminated if you connect a SIP trunk directly to your ITSP at significantly lower cost.</span></span> <span data-ttu-id="2b488-115">In TDM trunking i provider di servizi caricano le chiamate al minuto.</span><span class="sxs-lookup"><span data-stu-id="2b488-115">In TDM trunking, service providers charge for calls by the minute.</span></span> <span data-ttu-id="2b488-116">Il costo del trunking SIP può essere basato sull'utilizzo della larghezza di banda, che è possibile acquistare in incrementi più piccoli e più economici.</span><span class="sxs-lookup"><span data-stu-id="2b488-116">The cost of SIP trunking may be based on bandwidth usage, which you can buy in smaller, more economical increments.</span></span> <span data-ttu-id="2b488-117">Il costo effettivo dipende dal modello di servizio della ITSP scelta.</span><span class="sxs-lookup"><span data-stu-id="2b488-117">(The actual cost depends on the service model of the ITSP you choose.)</span></span>

<div>

## <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a><span data-ttu-id="2b488-118">Trunking SIP e hosting di un gateway PSTN o IP-PBX</span><span class="sxs-lookup"><span data-stu-id="2b488-118">SIP Trunking vs. Hosting a PSTN Gateway or IP-PBX</span></span>

<span data-ttu-id="2b488-119">Poiché i trunk SIP si connettono direttamente al provider di servizi, è possibile eliminare i gateway PSTN e i costi e la complessità della gestione.</span><span class="sxs-lookup"><span data-stu-id="2b488-119">Because SIP trunks connect directly to your service provider, you can eliminate your PSTN gateways and their management cost and complexity.</span></span> <span data-ttu-id="2b488-120">L'uso di un trunk SIP può determinare un notevole risparmio di costi tramite la riduzione della manutenzione e dell'amministrazione.</span><span class="sxs-lookup"><span data-stu-id="2b488-120">Using a SIP trunk can lead to substantial cost savings through reduced maintenance and administration.</span></span>

</div>

</div>

<div>

## <a name="expanded-voip-services"></a><span data-ttu-id="2b488-121">Servizi VoIP espansi</span><span class="sxs-lookup"><span data-stu-id="2b488-121">Expanded VoIP Services</span></span>

<span data-ttu-id="2b488-122">Le funzionalità vocali sono spesso la motivazione principale per la distribuzione del trunking SIP, ma il supporto vocale è solo il primo passaggio.</span><span class="sxs-lookup"><span data-stu-id="2b488-122">Voice features are often the primary motivation for deploying SIP trunking, but voice support is just the first step.</span></span> <span data-ttu-id="2b488-123">Con il trunking SIP è possibile estendere le funzionalità VoIP e consentire a Lync Server 2013 di offrire un set di servizi più completo.</span><span class="sxs-lookup"><span data-stu-id="2b488-123">With SIP trunking, you can extend VoIP capabilities and enable Lync Server 2013 to deliver a richer set of services.</span></span> <span data-ttu-id="2b488-124">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2b488-124">For example:</span></span>

  - <span data-ttu-id="2b488-125">Il rilevamento della presenza avanzata per i dispositivi che non esegue Lync Server 2013 può offrire una migliore integrazione con i telefoni cellulari, consentendo di verificare quando un utente si trova in una chiamata telefonica mobile.</span><span class="sxs-lookup"><span data-stu-id="2b488-125">Enhanced presence detection for devices that are not running Lync Server 2013 can provide better integration with mobile phones, enabling you to see when a user is on a mobile phone call.</span></span>

  - <span data-ttu-id="2b488-126">La chiamata di emergenza E9-1-1 consente alle autorità che rispondono alle chiamate di 911 di determinare la posizione del chiamante dal proprio numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="2b488-126">E9-1-1 emergency calling enables the authorities who answer 911 calls to determine the caller’s location from his or her telephone number.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2b488-127">Contattare l'ITSP per un elenco dei servizi supportati e che possono essere abilitati per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2b488-127">Contact your ITSP for a list of services that they support and can enable for your organization.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Panoramica del trunking SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of SIP trunking
ms:assetid: 204f2c21-436f-4b2d-93ea-d6db98fa2952
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398285(v=OCS.15)
ms:contentKeyID: 48183601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbf29b02af831f82050e9a032a35f0fa57c1eb1e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046249"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="6f70a-102">Panoramica del trunking SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f70a-102">Overview of SIP trunking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f70a-103">_**Ultimo argomento modificato:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="6f70a-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="6f70a-p101">La distribuzione del trunking SIP può costituire un importante passo verso la semplificazione delle telecomunicazioni nella propria organizzazione e per prepararsi agli ultimi aggiornamenti relativi alle comunicazioni in tempo reale. Uno dei principali vantaggi del trunking SIP è rappresentato dalla possibilità di consolidare le connessioni dell'organizzazione alla rete PSTN (public switched telephone network) presso un sito centrale, mentre il relativo predecessore, il trunking TDM (time division multiplexing) in genere richiede un trunk separato per ogni sito derivato.</span><span class="sxs-lookup"><span data-stu-id="6f70a-p101">Deploying SIP trunking can be a big step toward simplifying your organization’s telecommunications and preparing for up-to-date enhancements to real-time communications. One of the primary advantages of SIP trunking is that you can consolidate your organization’s connections to the public switched telephone network (PSTN) at a central site, as opposed to its predecessor, time division multiplexing (TDM) trunking, which typically requires a separate trunk from each branch site.</span></span>

<div>

## <a name="sip-trunking-in-lync-server"></a><span data-ttu-id="6f70a-106">Trunking SIP in Lync Server</span><span class="sxs-lookup"><span data-stu-id="6f70a-106">SIP Trunking in Lync Server</span></span>

<span data-ttu-id="6f70a-107">Le funzionalità di trunking SIP di Lync Server 2013 consentono di:</span><span class="sxs-lookup"><span data-stu-id="6f70a-107">The Lync Server 2013 SIP trunking capabilities enable the following:</span></span>

  - <span data-ttu-id="6f70a-108">Un utente Enterprise all'interno o all'esterno del firewall aziendale può effettuare una chiamata locale o interurbana specificata da un numero compatibile con E.164 che viene terminata sulla rete PSTN come servizio del provider di servizi corrispondente.</span><span class="sxs-lookup"><span data-stu-id="6f70a-108">An enterprise user, whether inside or outside the corporate firewall, can make a local call or a long-distance call that is specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>

  - <span data-ttu-id="6f70a-109">Qualsiasi sottoscrittore PSTN può contattare un utente Enterprise all'interno o all'esterno del firewall aziendale componendo un numero DID (Direct Inward Dialing) associato all'utente Enterprise.</span><span class="sxs-lookup"><span data-stu-id="6f70a-109">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number that is associated with that enterprise user.</span></span>

</div>

<div>

## <a name="cost-savings"></a><span data-ttu-id="6f70a-110">Risparmi sui costi</span><span class="sxs-lookup"><span data-stu-id="6f70a-110">Cost Savings</span></span>

<span data-ttu-id="6f70a-111">I risparmi sui costi associati al trunking SIP possono essere significativi:</span><span class="sxs-lookup"><span data-stu-id="6f70a-111">The cost savings associated with SIP trunking can be substantial:</span></span>

  - <span data-ttu-id="6f70a-112">Le chiamate interurbane in genere sono molto meno costose tramite un trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="6f70a-112">Long distance calls typically cost much less through a SIP trunk.</span></span>

  - <span data-ttu-id="6f70a-113">È possibile tagliare i costi di gestione e ridurre la complessità della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="6f70a-113">You can cut manageability costs and reduce the complexity of deployment.</span></span>

  - <span data-ttu-id="6f70a-p102">Le tariffe BRI (Basic Rate Interface) e PRI (Primary Rate Interface) possono essere eliminate se si connette un trunk SIP direttamente al provider di servizi di telefonia Internet (ITSP) con un costo significativamente inferiore. Nel trunking TDM i provider di servizi applicano alle chiamate una tariffa al minuto. Il costo del trunking SIP può basarsi sull'utilizzo della larghezza di banda, che può essere acquistato con incrementi inferiori, più economici. Il costo effettivo dipende dal modello di servizio dell'ITSP scelto.</span><span class="sxs-lookup"><span data-stu-id="6f70a-p102">Basic rate interface (BRI) and primary rate interface (PRI) fees can be eliminated if you connect a SIP trunk directly to your ITSP at significantly lower cost. In TDM trunking, service providers charge for calls by the minute. The cost of SIP trunking may be based on bandwidth usage, which you can buy in smaller, more economical increments. (The actual cost depends on the service model of the ITSP you choose.)</span></span>

<div>

## <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a><span data-ttu-id="6f70a-118">Confronto tra trunking SIP e hosting di un gateway PSTN o di un sistema IP-PBX</span><span class="sxs-lookup"><span data-stu-id="6f70a-118">SIP Trunking vs. Hosting a PSTN Gateway or IP-PBX</span></span>

<span data-ttu-id="6f70a-p103">Poiché i trunk SIP si connettono direttamente al provider di servizi, è possibile eliminare i gateway PSTN con relativa complessità e con i costi di gestione a essi associati. L'utilizzo di un trunk SIP può determinare significativi risparmi sui costi grazie a una riduzione delle attività di manutenzione e amministrazione.</span><span class="sxs-lookup"><span data-stu-id="6f70a-p103">Because SIP trunks connect directly to your service provider, you can eliminate your PSTN gateways and their management cost and complexity. Using a SIP trunk can lead to substantial cost savings through reduced maintenance and administration.</span></span>

</div>

</div>

<div>

## <a name="expanded-voip-services"></a><span data-ttu-id="6f70a-121">Servizi VoIP estesi</span><span class="sxs-lookup"><span data-stu-id="6f70a-121">Expanded VoIP Services</span></span>

<span data-ttu-id="6f70a-122">Le funzionalità vocali sono spesso la motivazione principale per la distribuzione del trunking SIP, ma il supporto vocale è solo il primo passaggio.</span><span class="sxs-lookup"><span data-stu-id="6f70a-122">Voice features are often the primary motivation for deploying SIP trunking, but voice support is just the first step.</span></span> <span data-ttu-id="6f70a-123">Con il trunking SIP, è possibile estendere le funzionalità VoIP e consentire a Lync Server 2013 di fornire un set di servizi più completo.</span><span class="sxs-lookup"><span data-stu-id="6f70a-123">With SIP trunking, you can extend VoIP capabilities and enable Lync Server 2013 to deliver a richer set of services.</span></span> <span data-ttu-id="6f70a-124">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6f70a-124">For example:</span></span>

  - <span data-ttu-id="6f70a-125">Il rilevamento della presenza avanzata per i dispositivi che non eseguono Lync Server 2013 è in grado di offrire una migliore integrazione con i telefoni cellulari, consentendo di vedere quando un utente è su una chiamata di telefonia mobile.</span><span class="sxs-lookup"><span data-stu-id="6f70a-125">Enhanced presence detection for devices that are not running Lync Server 2013 can provide better integration with mobile phones, enabling you to see when a user is on a mobile phone call.</span></span>

  - <span data-ttu-id="6f70a-126">La funzionalità per le chiamate di emergenza E9-1-1 consente alle autorità che rispondono a tali chiamate di determinare il luogo da cui proviene la chiamata dal numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="6f70a-126">E9-1-1 emergency calling enables the authorities who answer 911 calls to determine the caller’s location from his or her telephone number.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6f70a-127">Contattare il provider di servizi Internet per un elenco dei servizi supportati e che possono essere abilitati per la propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6f70a-127">Contact your ITSP for a list of services that they support and can enable for your organization.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: pianificazione della connettività PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for PSTN connectivity
ms:assetid: 280f684a-740a-443d-8ecf-574241382a42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425749(v=OCS.15)
ms:contentKeyID: 48183684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41de8ee220ef1bbe88601d53886046c28f72e954
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521943"
---
# <a name="planning-for-pstn-connectivity-in-lync-server-2013"></a><span data-ttu-id="530c5-102">Pianificazione della connettività PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="530c5-102">Planning for PSTN connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="530c5-103">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="530c5-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="530c5-104">Una soluzione VoIP di livello aziendale deve essere in grado di garantire le chiamate da e verso la rete PSTN (Public Switched Telephone Network) senza alcun decadimento della qualità del servizio (QoS).</span><span class="sxs-lookup"><span data-stu-id="530c5-104">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="530c5-105">Gli utenti che effettuano e ricevono chiamate non devono essere a conoscenza della tecnologia sottostante: dal punto di vista dell'utente, una chiamata tra l'infrastruttura VoIP aziendale e la rete PSTN dovrebbe sembrare solo un'altra telefonata.</span><span class="sxs-lookup"><span data-stu-id="530c5-105">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>

<span data-ttu-id="530c5-106">Lync Server 2013 fornisce connettività PSTN affidabile e scalabile utilizzando le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="530c5-106">Lync Server 2013 provides reliable, scalable PSTN connectivity by using the following options:</span></span>

  - <span data-ttu-id="530c5-107">**Trunk SIP** con un provider di servizi di telefonia Internet (ITSP)</span><span class="sxs-lookup"><span data-stu-id="530c5-107">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>

  - <span data-ttu-id="530c5-108">**Connessioni SIP dirette** con un gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="530c5-108">**Direct SIP connections** to a PSTN gateway</span></span>

  - <span data-ttu-id="530c5-109">**Connessioni SIP dirette** con un PBX</span><span class="sxs-lookup"><span data-stu-id="530c5-109">**Direct SIP connections** to a PBX</span></span>

<span data-ttu-id="530c5-110">A seconda delle dimensioni, della copertura geografica e dell'infrastruttura vocale esistente, un'azienda può usare una, due o addirittura tutte e tre le opzioni in ubicazioni diverse.</span><span class="sxs-lookup"><span data-stu-id="530c5-110">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="530c5-111">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="530c5-111">In This Section</span></span>

  - [<span data-ttu-id="530c5-112">Trunking SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="530c5-112">SIP trunking in Lync Server 2013</span></span>](lync-server-2013-sip-trunking.md)

  - [<span data-ttu-id="530c5-113">Connessioni SIP dirette in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="530c5-113">Direct SIP connections in Lync Server 2013</span></span>](lync-server-2013-direct-sip-connections.md)

  - [<span data-ttu-id="530c5-114">Trunk M:N in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="530c5-114">M:N trunk in Lync Server 2013</span></span>](lync-server-2013-m-n-trunk.md)

  - [<span data-ttu-id="530c5-115">Regole di conversione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="530c5-115">Translation rules in Lync Server 2013</span></span>](lync-server-2013-translation-rules.md)

  - [<span data-ttu-id="530c5-116">Pianificazione del routing vocale in uscita in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="530c5-116">Planning outbound voice routing in Lync Server 2013</span></span>](lync-server-2013-planning-outbound-voice-routing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


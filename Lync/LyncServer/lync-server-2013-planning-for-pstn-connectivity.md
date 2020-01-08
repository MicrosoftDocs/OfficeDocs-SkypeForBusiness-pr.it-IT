---
title: 'Lync Server 2013: pianificazione della connettività PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for PSTN connectivity
ms:assetid: 280f684a-740a-443d-8ecf-574241382a42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425749(v=OCS.15)
ms:contentKeyID: 48183684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d64089661b5d185362a8e47128e9a890b03edfd8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981239"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-pstn-connectivity-in-lync-server-2013"></a><span data-ttu-id="49e19-102">Pianificazione della connettività PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49e19-102">Planning for PSTN connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49e19-103">_**Argomento Ultima modifica:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="49e19-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="49e19-104">Una soluzione VoIP di livello aziendale deve prevedere le chiamate da e verso la rete PSTN (Public Switched Telephone Network) senza alcun calo di qualità del servizio (QoS).</span><span class="sxs-lookup"><span data-stu-id="49e19-104">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="49e19-105">Gli utenti che dispongono e ricevono chiamate non devono essere a conoscenza della tecnologia sottostante: dal punto di vista dell'utente, una chiamata tra l'infrastruttura VoIP aziendale e la rete PSTN dovrebbe sembrare solo un'altra telefonata.</span><span class="sxs-lookup"><span data-stu-id="49e19-105">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>

<span data-ttu-id="49e19-106">Lync Server 2013 offre connettività PSTN affidabile e scalabile usando le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="49e19-106">Lync Server 2013 provides reliable, scalable PSTN connectivity by using the following options:</span></span>

  - <span data-ttu-id="49e19-107">**Trunk SIP** in un provider di servizi di telefonia Internet (ITSP)</span><span class="sxs-lookup"><span data-stu-id="49e19-107">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>

  - <span data-ttu-id="49e19-108">**Connessioni SIP dirette** a un gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="49e19-108">**Direct SIP connections** to a PSTN gateway</span></span>

  - <span data-ttu-id="49e19-109">**Connessioni SIP dirette** a un PBX</span><span class="sxs-lookup"><span data-stu-id="49e19-109">**Direct SIP connections** to a PBX</span></span>

<span data-ttu-id="49e19-110">A seconda delle dimensioni, della copertura geografica e dell'infrastruttura vocale esistente, un'organizzazione può usare una, due o anche tutte e tre le opzioni in varie posizioni.</span><span class="sxs-lookup"><span data-stu-id="49e19-110">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="49e19-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="49e19-111">In This Section</span></span>

  - [<span data-ttu-id="49e19-112">Trunking SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49e19-112">SIP trunking in Lync Server 2013</span></span>](lync-server-2013-sip-trunking.md)

  - [<span data-ttu-id="49e19-113">Connessioni SIP dirette in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49e19-113">Direct SIP connections in Lync Server 2013</span></span>](lync-server-2013-direct-sip-connections.md)

  - [<span data-ttu-id="49e19-114">Trunk M:N in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49e19-114">M:N trunk in Lync Server 2013</span></span>](lync-server-2013-m-n-trunk.md)

  - [<span data-ttu-id="49e19-115">Regole di traduzione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49e19-115">Translation rules in Lync Server 2013</span></span>](lync-server-2013-translation-rules.md)

  - [<span data-ttu-id="49e19-116">Pianificazione del routing vocale in uscita in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49e19-116">Planning outbound voice routing in Lync Server 2013</span></span>](lync-server-2013-planning-outbound-voice-routing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


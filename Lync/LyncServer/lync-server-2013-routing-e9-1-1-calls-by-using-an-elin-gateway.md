---
title: 'Lync Server 2013: Routing delle chiamate di emergenza tramite un gateway ELIN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Routing E9-1-1 calls by using an ELIN gateway
ms:assetid: 5a3997e3-898d-49cb-922a-4184c3373350
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204919(v=OCS.15)
ms:contentKeyID: 48184221
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97c921a0b31438103ba74dcc64925e5b2069a8e8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732848"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-an-elin-gateway-in-lync-server-2013"></a><span data-ttu-id="c679b-102">Routing delle chiamate di emergenza tramite un gateway ELIN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c679b-102">Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c679b-103">_**Argomento Ultima modifica:** 2013-02-05_</span><span class="sxs-lookup"><span data-stu-id="c679b-103">_**Topic Last Modified:** 2013-02-05_</span></span>

<span data-ttu-id="c679b-104">Alcuni partner del programma Unified Communications Open Interoperability offrono i gateway con funzionalità di sicurezza per le chiamate di emergenza qualificati (ELIN), che possono fungere da alternativa a una connessione trunk SIP a un provider di servizi E9-1-1 qualificato.</span><span class="sxs-lookup"><span data-stu-id="c679b-104">Some partners in the Unified Communications Open Interoperability Program provide qualified Emergency Location Identification Number (ELIN)-capable gateways, which can serve as an alternative to a SIP trunk connection to a qualified E9-1-1 service provider.</span></span> <span data-ttu-id="c679b-105">I gateway ELIN supportano la connettività (CAMA) ISDN o centralizzata per l'accounting automatico dei messaggi con servizi E9-1-1 basati su PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="c679b-105">ELIN gateways support ISDN or Centralized Automatic Message Accounting (CAMA) connectivity to public switched telephone network (PSTN)-based E9-1-1 services.</span></span> <span data-ttu-id="c679b-106">Per informazioni dettagliate sui partner che includono gateway ELIN e collegamenti alla propria documentazione, vedere [http://go.microsoft.com/fwlink/p/?LinkId=248425](http://go.microsoft.com/fwlink/p/?linkid=248425).</span><span class="sxs-lookup"><span data-stu-id="c679b-106">For details about partners who provide ELIN gateways and links to their documentation, see [http://go.microsoft.com/fwlink/p/?LinkId=248425](http://go.microsoft.com/fwlink/p/?linkid=248425).</span></span>

<span data-ttu-id="c679b-107">Analogamente alle connessioni trunk SIP ai provider di servizi E9-1-1, i gateway ELIN supportano anche i mezzi per il routing di una chiamata di emergenza al punto di risposta di sicurezza pubblica più appropriato del chiamante (PSAP), ma questi gateway usano un ELIN come identificatore della posizione.</span><span class="sxs-lookup"><span data-stu-id="c679b-107">Like SIP trunk connections to E9-1-1 service providers, ELIN gateways also provide the means of routing an emergency call to the caller's most appropriate Public Safety Answering Point (PSAP), but these gateways use an ELIN as the location identifier.</span></span> <span data-ttu-id="c679b-108">Si definiscono gli ELIN per ogni posizione di risposta all'emergenza nell'organizzazione (per informazioni dettagliate, vedere [gestione delle posizioni per i gateway ELIN in Lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)).</span><span class="sxs-lookup"><span data-stu-id="c679b-108">You define ELINs for each Emergency Response Location (ERL) in your organization (for details, see [Managing locations for ELIN gateways in Lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)).</span></span>

<span data-ttu-id="c679b-109">Quando si usa un gateway ELIN per le chiamate di emergenza, si usa la stessa infrastruttura E9-1-1 di Lync Server che si usa per una connessione trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="c679b-109">When you use an ELIN gateway for emergency calls, you use the same Lync Server E9-1-1 infrastructure that you would use for a SIP trunk connection.</span></span> <span data-ttu-id="c679b-110">Il database del servizio informazioni sulla posizione fornisce la posizione al client Lync Server e il criterio della posizione Abilita la caratteristica e definisce il routing.</span><span class="sxs-lookup"><span data-stu-id="c679b-110">That is, the Location Information service database provides the location to the Lync Server client, and the location policy enables the feature and defines the routing.</span></span> <span data-ttu-id="c679b-111">Con un gateway ELIN, tuttavia, è necessario aggiungere il contrassegno ELINs al database del servizio informazioni sulla posizione e fare in modo che il gestore PSTN li carichi nel database ALI (Automatic Location Identification).</span><span class="sxs-lookup"><span data-stu-id="c679b-111">With an ELIN gateway, however, you need to add the ELINs to the Location Information service database and have your PSTN carrier upload them to the Automatic Location Identification (ALI) database.</span></span>

<span data-ttu-id="c679b-112">Quando un client Lync ottiene la propria posizione dal servizio informazioni sulla posizione, la posizione include il valore ELIN.</span><span class="sxs-lookup"><span data-stu-id="c679b-112">When a Lync client obtains its location from the Location Information service, the location includes the ELIN.</span></span> <span data-ttu-id="c679b-113">Durante una chiamata di emergenza, il ELIN è incluso nella posizione inviata al gateway ELIN.</span><span class="sxs-lookup"><span data-stu-id="c679b-113">During an emergency call, the ELIN is included with the location sent to the ELIN gateway.</span></span> <span data-ttu-id="c679b-114">Il gateway ELIN identifica la chiamata come chiamata di emergenza e scambia il numero della parte chiamante con ELIN.</span><span class="sxs-lookup"><span data-stu-id="c679b-114">The ELIN gateway identifies the call as an emergency call and swaps the calling party's number with the ELIN.</span></span> <span data-ttu-id="c679b-115">Il gateway ELIN instrada quindi la chiamata alla rete PSTN con il numero di chiamata ELIN.</span><span class="sxs-lookup"><span data-stu-id="c679b-115">The ELIN gateway then routes the call to the PSTN with the ELIN as the calling number.</span></span> <span data-ttu-id="c679b-116">Il provider E9-1-1 PSTN cerca il numero ELIN nel database ALI, un database complementare per il database stradario (Master Street Address Guide).</span><span class="sxs-lookup"><span data-stu-id="c679b-116">The PSTN E9-1-1 provider looks up the ELIN in the ALI database, which is a companion database to the Master Street Address Guide (MSAG) database.</span></span> <span data-ttu-id="c679b-117">La rete PSTN invia quindi la chiamata al PSAP più appropriato in base alla ricerca di ALI e PSAP invia i primi soccorritori alla posizione del chiamante in base alla ricerca di ALI.</span><span class="sxs-lookup"><span data-stu-id="c679b-117">The PSTN then sends the call to the most appropriate PSAP based on the ALI lookup, and the PSAP sends first responders to the caller's location based on the ALI lookup.</span></span> <span data-ttu-id="c679b-118">Il numero chiamante viene memorizzato nella cache del gateway ELIN per un periodo di tempo predefinito per i callback.</span><span class="sxs-lookup"><span data-stu-id="c679b-118">The calling number is cached on the ELIN gateway for a predefined amount of time for callbacks.</span></span> <span data-ttu-id="c679b-119">Durante un callback, il PSAP raggiunge il gateway ELIN, che scambia il numero ELIN per il num DID (Direct Interior Dialing) del chiamante.</span><span class="sxs-lookup"><span data-stu-id="c679b-119">During a callback, the PSAP reaches the ELIN gateway, which swaps the ELIN for the caller's direct inward dialing (DID) number.</span></span>

<span data-ttu-id="c679b-120">I gateway ELIN supportano le chiamate di emergenza solo dall'interno della rete dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c679b-120">ELIN gateways support emergency calls only from within your organization's network.</span></span> <span data-ttu-id="c679b-121">Non supportano le chiamate di emergenza effettuate dall'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="c679b-121">They do not support emergency calls made from outside your network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c679b-122">Per informazioni dettagliate sull'uso di una connessione trunk SIP per le chiamate di emergenza, vedere <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">routing di chiamate E9-1-1 tramite trunk SIP in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c679b-122">For details about using a SIP trunk connection for emergency calls, see <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="c679b-123">Il diagramma seguente mostra il modo in cui una chiamata di emergenza viene instradata da Lync Server a PSAP quando si usa un gateway ELIN.</span><span class="sxs-lookup"><span data-stu-id="c679b-123">The following diagram shows how an emergency call is routed from Lync Server to the PSAP when you use an ELIN gateway.</span></span>

<span data-ttu-id="c679b-124">**Routing delle chiamate E9-1-1 con un gateway ELIN**</span><span class="sxs-lookup"><span data-stu-id="c679b-124">**Routing E9-1-1 calls with an ELIN gateway**</span></span>

<span data-ttu-id="c679b-125">![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")</span><span class="sxs-lookup"><span data-stu-id="c679b-125">![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")</span></span>

1.  <span data-ttu-id="c679b-126">Un invito SIP contenente la posizione, il numero di callback del chiamante e l'URL di notifica (facoltativo) e il numero di callback della conferenza vengono instradati a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c679b-126">A SIP INVITE containing the location, the caller's callback number, and the (optional) Notification URL and conference callback number is routed to Lync Server.</span></span>

2.  <span data-ttu-id="c679b-127">Lync Server corrisponde al numero di emergenza e quindi instrada la chiamata (in base al valore di **utilizzo PSTN** definito nel criterio di posizione applicabile) a un Mediation Server e da lì a un gateway ELIN.</span><span class="sxs-lookup"><span data-stu-id="c679b-127">Lync Server matches the emergency number and then routes the call (based on the **PSTN Usage** value defined in the applicable location policy) to a Mediation Server, and from there to an ELIN gateway.</span></span>

3.  <span data-ttu-id="c679b-128">Il gateway ELIN instrada la chiamata su un trunk ISDN o CAMA verso la rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="c679b-128">The ELIN gateway routes the call over an ISDN or CAMA trunk to the PSTN.</span></span>

4.  <span data-ttu-id="c679b-129">La PSTN identifica la chiamata come chiamata di emergenza e la instrada a un router selettivo E9-1-1 nella rete.</span><span class="sxs-lookup"><span data-stu-id="c679b-129">The PSTN identifies the call as an emergency call and routes it to an E9-1-1 selective router in the network.</span></span> <span data-ttu-id="c679b-130">Il router selettivo E9-1-1 Cerca il numero del chiamante nel database ALI per ottenere la posizione geografica.</span><span class="sxs-lookup"><span data-stu-id="c679b-130">The E9-1-1 selective router looks up the caller's number in the ALI database to obtain the geographical location.</span></span> <span data-ttu-id="c679b-131">Il router selettivo E9-1-1 Invia la chiamata al PSAP più appropriato in base alle informazioni sulla posizione recuperate dal database ALI.</span><span class="sxs-lookup"><span data-stu-id="c679b-131">The E9-1-1 selective router sends the call to the most appropriate PSAP based on the location information that was retrieved from the ALI database.</span></span>

5.  <span data-ttu-id="c679b-132">Se sono stati configurati i criteri di posizione per le notifiche, uno o più agenti di sicurezza dell'organizzazione riceveranno un messaggio istantaneo speciale di notifica di emergenza Lync.</span><span class="sxs-lookup"><span data-stu-id="c679b-132">If you configured the location policy for notifications, one or more of your organization’s security officers are sent a special Lync emergency notification instant message.</span></span> <span data-ttu-id="c679b-133">Questo messaggio compare sempre nella schermata degli addetti alla sicurezza e contiene il nome, il numero di telefono, l'ora e la posizione del chiamante, che consente al personale di sicurezza di rispondere rapidamente al chiamante di emergenza usando un messaggio istantaneo o una voce.</span><span class="sxs-lookup"><span data-stu-id="c679b-133">This message always pops up on the security officers’ screen(s) and contains the caller’s name, phone number, time, and location, enabling security personnel to quickly respond to the emergency caller by using an instant message or voice.</span></span>

6.  <span data-ttu-id="c679b-134">Se la chiamata viene interrotta prematuramente, PSAP usa il ELIN per contattare direttamente il chiamante.</span><span class="sxs-lookup"><span data-stu-id="c679b-134">If the call is broken prematurely, the PSAP uses the ELIN to contact the caller directly.</span></span> <span data-ttu-id="c679b-135">Il gateway ELIN scambia il ELIN per il chiamante.</span><span class="sxs-lookup"><span data-stu-id="c679b-135">The ELIN gateway swaps the ELIN for the caller's DID.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


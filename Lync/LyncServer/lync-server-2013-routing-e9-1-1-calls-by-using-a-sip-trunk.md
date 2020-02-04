---
title: 'Lync Server 2013: Routing delle chiamate di emergenza tramite un trunk SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Routing E9-1-1 calls by using a SIP trunk
ms:assetid: 157753c3-fe74-4e2c-81da-ee06911d4cc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204701(v=OCS.15)
ms:contentKeyID: 48183492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 918aaf97b1567f012a2b41de7128db23aa383acb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732855"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-a-sip-trunk-in-lync-server-2013"></a><span data-ttu-id="32c24-102">Routing delle chiamate di emergenza tramite un trunk SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32c24-102">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32c24-103">_**Argomento Ultima modifica:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="32c24-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="32c24-104">L'uso di un trunk SIP per connettersi a un provider di servizi E9-1-1 qualificato è un modo in cui è possibile distribuire E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="32c24-104">Using a SIP trunk to connect to a qualified E9-1-1 service provider is one way that you can deploy E9-1-1.</span></span> <span data-ttu-id="32c24-105">Per informazioni dettagliate sull'uso di un gateway ELIN per la connessione a un provider di servizi E9-1-1 Basato su PSTN (Public Switched Telephone Network), vedere [routing delle chiamate di E9-1-1 tramite un gateway ELIN in Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md).</span><span class="sxs-lookup"><span data-stu-id="32c24-105">For details about using an ELIN gateway to connect to a public switched telephone network (PSTN)-based E9-1-1 service provider, see [Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md).</span></span>

<span data-ttu-id="32c24-106">Il diagramma seguente mostra il modo in cui una chiamata di emergenza viene instradata da Lync Server al punto di PSAP (Public Safety Answering Point) quando si usa un trunk SIP e un provider di servizi E9-1-1 qualificato.</span><span class="sxs-lookup"><span data-stu-id="32c24-106">The following diagram shows how an emergency call is routed from Lync Server to the Public Safety Answering Point (PSAP) when you use a SIP trunk and qualified E9-1-1 service provider.</span></span>

<span data-ttu-id="32c24-107">**Routing di chiamate E9-1-1 tramite trunk SIP**</span><span class="sxs-lookup"><span data-stu-id="32c24-107">**Routing E9-1-1 calls through a SIP trunk**</span></span>

<span data-ttu-id="32c24-108">![Routing delle chiamate di emergenza da Lync Server a PSAP](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "Routing delle chiamate di emergenza da Lync Server a PSAP")</span><span class="sxs-lookup"><span data-stu-id="32c24-108">![Emergency Call Routing from Lync Server to PSAP](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "Emergency Call Routing from Lync Server to PSAP")</span></span>

<span data-ttu-id="32c24-109">Quando una chiamata di emergenza viene inserita da un client Lync Server compatibile:</span><span class="sxs-lookup"><span data-stu-id="32c24-109">When an emergency call is placed from a compatible Lync Server client:</span></span>

1.  <span data-ttu-id="32c24-110">Un invito SIP che contiene la posizione, il numero di callback del chiamante e l'URL di notifica (facoltativo) e il numero di callback di conferenza vengono instradati a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="32c24-110">A SIP INVITE that contains the location, the caller's callback number, and the (optional) Notification URL and conference callback number is routed to Lync Server.</span></span>

2.  <span data-ttu-id="32c24-111">Lync Server corrisponde al numero di emergenza e instrada la chiamata (in base al valore di **utilizzo PSTN** definito nel criterio di posizione applicabile) a un Mediation Server e da lì, tramite un trunk SIP al provider di servizi E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="32c24-111">Lync Server matches the emergency number and routes the call (based on the **PSTN Usage** value that is defined in the applicable location policy) to a Mediation Server, and from there, over a SIP trunk to the E9-1-1 service provider.</span></span>

3.  <span data-ttu-id="32c24-112">Il provider di servizi E9-1-1 instrada la chiamata di emergenza alla PSAP corretta in base alla posizione fornita con la chiamata.</span><span class="sxs-lookup"><span data-stu-id="32c24-112">The E9-1-1 service provider routes the emergency call to the correct PSAP based on the location that is provided with the call.</span></span> <span data-ttu-id="32c24-113">Quando il client include un percorso di risposta di emergenza convalidato con la chiamata di emergenza, il provider instrada automaticamente la chiamata al PSAP appropriato.</span><span class="sxs-lookup"><span data-stu-id="32c24-113">When the client includes a validated Emergency Response Location (ERL) with the emergency call, the provider automatically routes the call to the appropriate PSAP.</span></span> <span data-ttu-id="32c24-114">Se la posizione è stata immessa manualmente dall'utente, il centro risposte per le chiamate di emergenza (ECRC) verifica verbalmente la precisione della posizione con il chiamante prima di instradare la chiamata di emergenza al PSAP.</span><span class="sxs-lookup"><span data-stu-id="32c24-114">If the location was manually entered by the user, the Emergency Call Response Center (ECRC) first verbally verifies the accuracy of the location with the caller before routing the emergency call to the PSAP.</span></span>

4.  <span data-ttu-id="32c24-115">Se sono stati configurati i criteri di posizione per le notifiche, uno o più agenti di sicurezza dell'organizzazione riceveranno un messaggio istantaneo speciale di notifica di emergenza Lync.</span><span class="sxs-lookup"><span data-stu-id="32c24-115">If you configured the location policy for notifications, one or more of your organization’s security officers are sent a special Lync emergency notification instant message.</span></span> <span data-ttu-id="32c24-116">Questo messaggio compare sempre nella schermata degli addetti alla sicurezza e contiene il nome, il numero di telefono, l'ora e la posizione del chiamante, che consente al personale di sicurezza di rispondere rapidamente al chiamante di emergenza usando un messaggio istantaneo o una voce.</span><span class="sxs-lookup"><span data-stu-id="32c24-116">This message always pops up on the security officers’ screen(s) and contains the caller’s name, phone number, time, and location, enabling security personnel to quickly respond to the emergency caller by using an instant message or voice.</span></span>

5.  <span data-ttu-id="32c24-117">Se sono stati configurati i criteri di posizione per le conferenze ed è supportato dal provider di servizi E9-1-1, è possibile partecipare a una conferenza di sicurezza interna alla chiamata con audio unidirezionale o audio bidirezionale.</span><span class="sxs-lookup"><span data-stu-id="32c24-117">If you configured the location policy for conferencing and it is supported by the E9-1-1 service provider, an internal Security Desk is conferenced into the call with either one-way audio or two-way audio.</span></span>

6.  <span data-ttu-id="32c24-118">Se la chiamata viene interrotta prematuramente, PSAP usa il numero di callback per contattare direttamente il chiamante.</span><span class="sxs-lookup"><span data-stu-id="32c24-118">If the call is broken prematurely, the PSAP uses the callback number to contact the caller directly.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


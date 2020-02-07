---
title: Instradamento diretto di Sistema telefonico
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/16/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: Protocolli di routing diretto
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7462822626b698f95b80a716a55f94dfe92148ff
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41835026"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a><span data-ttu-id="76cc8-103">Routing diretto-definizioni e standard RFC</span><span class="sxs-lookup"><span data-stu-id="76cc8-103">Direct Routing - Definitions and RFC standards</span></span>

<span data-ttu-id="76cc8-104">Questo articolo descrive il modo in cui routing diretto di Microsoft Phone System implementa protocolli standard RFC.</span><span class="sxs-lookup"><span data-stu-id="76cc8-104">This article describes how Microsoft Phone System Direct Routing implements RFC standard protocols.</span></span> <span data-ttu-id="76cc8-105">Questo articolo è destinato agli amministratori vocali responsabili della configurazione della connessione tra il controller del bordo sessione locale (SBC) e il servizio proxy SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="76cc8-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises Session Border Controller (SBC) and the Session Initiation Protocol (SIP) proxy service.</span></span>

<span data-ttu-id="76cc8-106">Le interfacce Customer SBC con i componenti seguenti nel backend di Microsoft teams:</span><span class="sxs-lookup"><span data-stu-id="76cc8-106">The customer SBC interfaces with the following components in the Microsoft Teams backend:</span></span> 

- <span data-ttu-id="76cc8-107">**Proxy SIP per la** segnalazione.</span><span class="sxs-lookup"><span data-stu-id="76cc8-107">**The SIP proxy** for signaling.</span></span> <span data-ttu-id="76cc8-108">Questo è il componente a Internet del routing diretto che gestisce le connessioni SIP (TLS) tra SBCs e routing diretto.</span><span class="sxs-lookup"><span data-stu-id="76cc8-108">This is the Internet-facing component of Direct Routing that handles SIP (TLS) connections between the SBCs and Direct Routing.</span></span>

- <span data-ttu-id="76cc8-109">**Processori multimediali** per elementi multimediali.</span><span class="sxs-lookup"><span data-stu-id="76cc8-109">**The media processors** for media.</span></span> <span data-ttu-id="76cc8-110">Questo è il componente a Internet di routing diretto che gestisce il traffico multimediale.</span><span class="sxs-lookup"><span data-stu-id="76cc8-110">This is the Internet-facing component of Direct Routing that handles media traffic.</span></span> <span data-ttu-id="76cc8-111">Questo componente usa i protocolli SRTP e SRTCP.</span><span class="sxs-lookup"><span data-stu-id="76cc8-111">This component uses SRTP and SRTCP protocols.</span></span>


<span data-ttu-id="76cc8-112">Per altre informazioni sul routing diretto, vedere [routing diretto del sistema telefonico](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="76cc8-112">For more information about Direct Routing, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="76cc8-113">Per altre informazioni sul modo in cui il routing diretto implementa il protocollo SIP, vedere [routing diretto-protocollo SIP](direct-routing-protocols-sip.md).</span><span class="sxs-lookup"><span data-stu-id="76cc8-113">For more information about how Direct Routing implements the SIP protocol, see [Direct Routing - SIP protocol](direct-routing-protocols-sip.md).</span></span>

## <a name="rfc-standards"></a><span data-ttu-id="76cc8-114">Standard RFC</span><span class="sxs-lookup"><span data-stu-id="76cc8-114">RFC standards</span></span>

<span data-ttu-id="76cc8-115">Il routing diretto è conforme agli standard RFC.</span><span class="sxs-lookup"><span data-stu-id="76cc8-115">Direct Routing complies with RFC standards.</span></span>  <span data-ttu-id="76cc8-116">Il servizio SBC collegato al routing diretto deve essere conforme alle RFC seguenti (o ai relativi successori).</span><span class="sxs-lookup"><span data-stu-id="76cc8-116">The SBC connected to Direct Routing must also comply with the following RFCs (or their successors).</span></span> 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a><span data-ttu-id="76cc8-117">Standard applicabili ai dispositivi che supportano la modalità di bypass non multimediale</span><span class="sxs-lookup"><span data-stu-id="76cc8-117">Standards applicable to devices that support non-media bypass mode</span></span> 

<span data-ttu-id="76cc8-118">Gli standard seguenti si applicano ai dispositivi che supportano solo la modalità non media bypass:</span><span class="sxs-lookup"><span data-stu-id="76cc8-118">The following standards are applicable to devices that support only non-media bypass mode:</span></span>

- <span data-ttu-id="76cc8-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): protocollo di avvio della sessione</span><span class="sxs-lookup"><span data-stu-id="76cc8-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Session Initiation Protocol</span></span>
- <span data-ttu-id="76cc8-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span><span class="sxs-lookup"><span data-stu-id="76cc8-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span></span> <span data-ttu-id="76cc8-121">Estensione privata al protocollo di avvio della sessione per l'identità asserita all'interno di reti attendibili: sezioni sulla gestione dell'intestazione P-Asserted-Identity.</span><span class="sxs-lookup"><span data-stu-id="76cc8-121">Private Extension to the Session Initiation Protocol for asserted identity within Trusted Networks--Sections about handling P-Asserted-Identity header.</span></span> <span data-ttu-id="76cc8-122">Il routing diretto Invia l'identità P-asserzione con le intestazioni di ID privacy.</span><span class="sxs-lookup"><span data-stu-id="76cc8-122">Direct Routing sends P-Asserted-Identity with Privacy ID headers.</span></span> 
- <span data-ttu-id="76cc8-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Estensione del protocollo SIP (Session Initiation Protocol) per informazioni sulla cronologia richieste.</span><span class="sxs-lookup"><span data-stu-id="76cc8-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) An extension to Session Initiation Protocol (SIP) for required History Information.</span></span> <span data-ttu-id="76cc8-124">Per altre informazioni, vedere anche: routing SIP Protocol Description.</span><span class="sxs-lookup"><span data-stu-id="76cc8-124">See also: Routing SIP Protocol description for more information.</span></span>
- <span data-ttu-id="76cc8-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) Meccanismo di riferimento per il protocollo di avvio della sessione</span><span class="sxs-lookup"><span data-stu-id="76cc8-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) The Session Initiation Protocol Referred-By mechanism</span></span>
- <span data-ttu-id="76cc8-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) Intestazione SIP (Session Initiation Protocol) "sostituisce"</span><span class="sxs-lookup"><span data-stu-id="76cc8-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) The Session Initiation Protocol (SIP) "Replaces" Header</span></span> 
- <span data-ttu-id="76cc8-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) Uso SIP (Session Initiation Protocol) del modello di offerta/risposta.</span><span class="sxs-lookup"><span data-stu-id="76cc8-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) Session Initiation Protocol (SIP) Usage of the Offer/Answer Model.</span></span>
  <span data-ttu-id="76cc8-128">Vedere la sezione "deviazioni da RFC".</span><span class="sxs-lookup"><span data-stu-id="76cc8-128">See the “Deviations from RFC” section.</span></span>
- <span data-ttu-id="76cc8-129">[Rfc 3711](https://tools.ietf.org/html/rfc3711) e [RFC 4771](https://tools.ietf.org/html/rfc4771).</span><span class="sxs-lookup"><span data-stu-id="76cc8-129">[RFC 3711](https://tools.ietf.org/html/rfc3711) and [RFC 4771](https://tools.ietf.org/html/rfc4771).</span></span> <span data-ttu-id="76cc8-130">Proteggere il traffico RTP con SRTP.</span><span class="sxs-lookup"><span data-stu-id="76cc8-130">Protect RTP traffic using SRTP.</span></span> <span data-ttu-id="76cc8-131">Il SBC deve essere in grado di stabilire le chiavi usando SDES.</span><span class="sxs-lookup"><span data-stu-id="76cc8-131">The SBC must be able to establish keys using SDES.</span></span> 
- <span data-ttu-id="76cc8-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Proposta di soluzione di Session Description Protocol (SDP) per il multiplexing RTP/RTCP</span><span class="sxs-lookup"><span data-stu-id="76cc8-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Session Description Protocol (SDP) Offer/Answer Clarifications for RTP/RTCP Multiplexing</span></span>

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a><span data-ttu-id="76cc8-133">Standard applicabili ai dispositivi che supportano la modalità di bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="76cc8-133">Standards applicable to devices that support media bypass mode</span></span>

<span data-ttu-id="76cc8-134">Oltre agli standard elencati come applicabili alla modalità non di bypass, vengono usati i seguenti standard per la modalità di bypass multimediale:</span><span class="sxs-lookup"><span data-stu-id="76cc8-134">In addition to the standards listed as applicable to non-bypass mode, the following standards are used for media bypass mode:</span></span>

- <span data-ttu-id="76cc8-135">[RFC 5245 Interactive Connectivity Establishment (Ice) per il bypass multimediale](https://tools.ietf.org/html/rfc5245).</span><span class="sxs-lookup"><span data-stu-id="76cc8-135">[RFC 5245 Interactive Connectivity Establishment (ICE) for media bypass](https://tools.ietf.org/html/rfc5245).</span></span>  <span data-ttu-id="76cc8-136">Il servizio SBC deve supportare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="76cc8-136">The SBC must support the following:</span></span>
  - <span data-ttu-id="76cc8-137">ICE Lite: i client di teams sono client ICE completi</span><span class="sxs-lookup"><span data-stu-id="76cc8-137">ICE Lite - the Teams clients are full ICE clients</span></span>
  - <span data-ttu-id="76cc8-138">[Riavvia il ghiaccio](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span><span class="sxs-lookup"><span data-stu-id="76cc8-138">[ICE Restarts](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span></span> <span data-ttu-id="76cc8-139">Vedere altre informazioni su ICE riavvii use case ed esempi in ICE Restart: la chiamata di bypass multimediale viene trasferita a un endpoint che non supporta il bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="76cc8-139">See more on ICE restarts use case and examples in ICE Restart:  Media bypass call transferred to an endpoint which does not support media bypass</span></span>   
- <span data-ttu-id="76cc8-140">[Controllo delle chiamate SIP (Session Initiation Protocol) rfc 5589-Transfer](https://tools.ietf.org/html/rfc5589).</span><span class="sxs-lookup"><span data-stu-id="76cc8-140">[RFC RFC 5589 Session Initiation Protocol (SIP) Call Control – Transfer](https://tools.ietf.org/html/rfc5589).</span></span> 
- <span data-ttu-id="76cc8-141">[RFC 3960 Early media e la generazione di suonerie nel protocollo SIP (Session Initiation Protocol)](https://tools.ietf.org/html/rfc3960), vedi sezioni 3,1, fork e 3,2, generazione di suonerie</span><span class="sxs-lookup"><span data-stu-id="76cc8-141">[RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960), see sections 3.1, Forking, and 3.2, Ringing Tone Generation</span></span> 
- [<span data-ttu-id="76cc8-142">Utilità per l'attraversamento delle sessioni RFC 5389 per NAT (STUN)</span><span class="sxs-lookup"><span data-stu-id="76cc8-142">RFC 5389 Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5389)
- [<span data-ttu-id="76cc8-143">RFC 5766 Traversal using relays about NAT (TURN): estensioni di inoltro alle utilità per l'attraversamento delle sessioni per NAT (STUN)</span><span class="sxs-lookup"><span data-stu-id="76cc8-143">RFC 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a><span data-ttu-id="76cc8-144">Standard applicabili per supportare il trasporto delle informazioni sulla posizione ai provider di E911</span><span class="sxs-lookup"><span data-stu-id="76cc8-144">Standards applicable to support conveying location information to E911 providers</span></span>

- [<span data-ttu-id="76cc8-145">RFC 6442, trasferimento di posizione per il protocollo di avvio della sessione</span><span class="sxs-lookup"><span data-stu-id="76cc8-145">RFC 6442, Location Conveyance for the Session Initiation Protocol</span></span>](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a><span data-ttu-id="76cc8-146">Deviazioni dalla RFC</span><span class="sxs-lookup"><span data-stu-id="76cc8-146">Deviations from the RFC's</span></span>

<span data-ttu-id="76cc8-147">La tabella seguente elenca le sezioni delle RFC in cui l'implementazione di Microsoft del SIP o dello stack multimediale differisce dallo standard:</span><span class="sxs-lookup"><span data-stu-id="76cc8-147">The following table lists the sections of the RFC(s) in which Microsoft's implementation of the SIP or media stack deviates from the standard:</span></span>

| <span data-ttu-id="76cc8-148">RFC e sezioni</span><span class="sxs-lookup"><span data-stu-id="76cc8-148">RFC and sections</span></span> | <span data-ttu-id="76cc8-149">Descrizione</span><span class="sxs-lookup"><span data-stu-id="76cc8-149">Description</span></span> | <span data-ttu-id="76cc8-150">Deviazione</span><span class="sxs-lookup"><span data-stu-id="76cc8-150">Deviation</span></span> |
| :---------------------  |:---------------------- |:-----------------------|
| [<span data-ttu-id="76cc8-151">RFC 6337, sezione 5,3 blocco e ripresa di elementi multimediali</span><span class="sxs-lookup"><span data-stu-id="76cc8-151">RFC 6337, section 5.3 Hold and Resume of Media</span></span>](https://tools.ietf.org/html/rfc6337#section-5.3) | <span data-ttu-id="76cc8-152">RFC consente di usare "a = inattivo", "a = sendonly", a = recvonly "per effettuare una chiamata in attesa.</span><span class="sxs-lookup"><span data-stu-id="76cc8-152">RFC allows using “a=inactive”, “a=sendonly”, a=recvonly” to place a call on hold.</span></span> |<span data-ttu-id="76cc8-153">Il proxy SIP supporta solo "a = inattivo" e non capisce se il SBC Invia "a = sendonly" o "a = recvonly".</span><span class="sxs-lookup"><span data-stu-id="76cc8-153">The SIP proxy only supports “a=inactive” and does not understand if the SBC sends “a=sendonly” or “a=recvonly”.</span></span>
| [<span data-ttu-id="76cc8-154">RFC 6337, sezione 5,4 "comportamento sulla ricezione di SDP con c = 0.0.0.0</span><span class="sxs-lookup"><span data-stu-id="76cc8-154">RFC 6337, section 5.4 “Behavior on Receiving SDP with c=0.0.0.0</span></span>](https://tools.ietf.org/html/rfc6337#section-5.4) | <span data-ttu-id="76cc8-155">[RFC3264](https://tools.ietf.org/html/rfc3264) richiede che un agente sia in grado di ricevere SDP con un indirizzo di connessione di 0.0.0.0, in questo caso significa che né RTP né RTCP devono essere inviati al peer.</span><span class="sxs-lookup"><span data-stu-id="76cc8-155">[RFC3264](https://tools.ietf.org/html/rfc3264) requires that an agent is capable of receiving SDP with a connection address of 0.0.0.0, in which case it means that neither  RTP nor RTCP should be sent to the peer.</span></span> | <span data-ttu-id="76cc8-156">Il proxy SIP non supporta questa opzione.</span><span class="sxs-lookup"><span data-stu-id="76cc8-156">The SIP proxy does not support this option.</span></span> |

## <a name="operational-modes"></a><span data-ttu-id="76cc8-157">Modalità operative</span><span class="sxs-lookup"><span data-stu-id="76cc8-157">Operational modes</span></span>

<span data-ttu-id="76cc8-158">Esistono due modalità operative per il routing diretto:</span><span class="sxs-lookup"><span data-stu-id="76cc8-158">There are two operational modes for Direct Routing:</span></span>

- <span data-ttu-id="76cc8-159">**Senza bypass multimediale** in cui tutti i flussi di traffico RTP tra il client teams, i processori multimediali e il SBC.</span><span class="sxs-lookup"><span data-stu-id="76cc8-159">**Without media bypass** in which all RTP traffic flows between the Teams client, the media processors, and the SBC.</span></span>  

- <span data-ttu-id="76cc8-160">**Con il bypass multimediale** in cui tutti i flussi di supporto RTP si alternano tra endpoint teams e SBC.</span><span class="sxs-lookup"><span data-stu-id="76cc8-160">**With media bypass** in which all RTP media flows between the Teams endpoints and the SBC.</span></span> 

<span data-ttu-id="76cc8-161">Tieni presente che il traffico SIP scorre sempre tramite il proxy SIP.</span><span class="sxs-lookup"><span data-stu-id="76cc8-161">Note that SIP traffic always flows via the SIP proxy.</span></span>   

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
ms.openlocfilehash: 88fb4459192ad9ff5af8702878d1cbf6a59d8e9d
ms.sourcegitcommit: 6227667c9941cc3289029099b7b6781581f16ea7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52569204"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a><span data-ttu-id="a5a8d-103">Routing diretto - Definizioni e standard RFC</span><span class="sxs-lookup"><span data-stu-id="a5a8d-103">Direct Routing - Definitions and RFC standards</span></span>

<span data-ttu-id="a5a8d-104">Questo articolo descrive come Telefono Microsoft system direct routing implementa i protocolli standard RFC.</span><span class="sxs-lookup"><span data-stu-id="a5a8d-104">This article describes how Microsoft Phone System Direct Routing implements RFC standard protocols.</span></span> <span data-ttu-id="a5a8d-105">Questo articolo è rivolto agli amministratori vocali responsabili della configurazione della connessione tra il session border controller (SBC) locale e il servizio proxy SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="a5a8d-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises Session Border Controller (SBC) and the Session Initiation Protocol (SIP) proxy service.</span></span>

<span data-ttu-id="a5a8d-106">Il client SBC si interfaccia con i componenti seguenti nel back-end Microsoft Teams back-end:</span><span class="sxs-lookup"><span data-stu-id="a5a8d-106">The customer SBC interfaces with the following components in the Microsoft Teams backend:</span></span> 

- <span data-ttu-id="a5a8d-107">**Proxy SIP per** la segnalazione.</span><span class="sxs-lookup"><span data-stu-id="a5a8d-107">**The SIP proxy** for signaling.</span></span> <span data-ttu-id="a5a8d-108">Questo è il componente di Routing diretto rivolto a Internet che gestisce le connessioni SIP (TLS) tra gli SBC e il routing diretto.</span><span class="sxs-lookup"><span data-stu-id="a5a8d-108">This is the Internet-facing component of Direct Routing that handles SIP (TLS) connections between the SBCs and Direct Routing.</span></span>

- <span data-ttu-id="a5a8d-109">**Processori multimediali per** supporti multimediali.</span><span class="sxs-lookup"><span data-stu-id="a5a8d-109">**The media processors** for media.</span></span> <span data-ttu-id="a5a8d-110">Questo è il componente di Routing diretto rivolto a Internet che gestisce il traffico multimediale.</span><span class="sxs-lookup"><span data-stu-id="a5a8d-110">This is the Internet-facing component of Direct Routing that handles media traffic.</span></span> <span data-ttu-id="a5a8d-111">Questo componente usa i protocolli SRTP e SRTCP.</span><span class="sxs-lookup"><span data-stu-id="a5a8d-111">This component uses SRTP and SRTCP protocols.</span></span>


<span data-ttu-id="a5a8d-112">Per altre informazioni sul routing diretto, vedere Sistema telefonico [Routing diretto](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="a5a8d-112">For more information about Direct Routing, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="a5a8d-113">Per altre informazioni sull'implementazione del protocollo SIP da parte di Routing diretto, vedere [Routing diretto - Protocollo SIP.](direct-routing-protocols-sip.md)</span><span class="sxs-lookup"><span data-stu-id="a5a8d-113">For more information about how Direct Routing implements the SIP protocol, see [Direct Routing - SIP protocol](direct-routing-protocols-sip.md).</span></span>

## <a name="rfc-standards"></a><span data-ttu-id="a5a8d-114">Standard RFC</span><span class="sxs-lookup"><span data-stu-id="a5a8d-114">RFC standards</span></span>

<span data-ttu-id="a5a8d-115">Il routing diretto è conforme agli standard RFC.</span><span class="sxs-lookup"><span data-stu-id="a5a8d-115">Direct Routing complies with RFC standards.</span></span>  <span data-ttu-id="a5a8d-116">Anche il servizio SBC connesso al routing diretto deve essere conforme alle RFC seguenti (o ai relativi successori).</span><span class="sxs-lookup"><span data-stu-id="a5a8d-116">The SBC connected to Direct Routing must also comply with the following RFCs (or their successors).</span></span> 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a><span data-ttu-id="a5a8d-117">Standard applicabili ai dispositivi che supportano la modalità di bypass non multimediale</span><span class="sxs-lookup"><span data-stu-id="a5a8d-117">Standards applicable to devices that support non-media bypass mode</span></span> 

<span data-ttu-id="a5a8d-118">Gli standard seguenti sono applicabili ai dispositivi che supportano solo la modalità di bypass non multimediale:</span><span class="sxs-lookup"><span data-stu-id="a5a8d-118">The following standards are applicable to devices that support only non-media bypass mode:</span></span>

- <span data-ttu-id="a5a8d-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Session Initiation Protocol</span><span class="sxs-lookup"><span data-stu-id="a5a8d-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Session Initiation Protocol</span></span>
- <span data-ttu-id="a5a8d-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span><span class="sxs-lookup"><span data-stu-id="a5a8d-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span></span> <span data-ttu-id="a5a8d-121">Estensione privata al protocollo di avvio sessione per l'identità asserta all'interno di reti attendibili: sezioni sulla gestione dell'intestazione P-Asserted-Identity.</span><span class="sxs-lookup"><span data-stu-id="a5a8d-121">Private Extension to the Session Initiation Protocol for asserted identity within Trusted Networks--Sections about handling P-Asserted-Identity header.</span></span> <span data-ttu-id="a5a8d-122">Il routing diretto invia P-Asserted-Identity con intestazioni ID privacy.</span><span class="sxs-lookup"><span data-stu-id="a5a8d-122">Direct Routing sends P-Asserted-Identity with Privacy ID headers.</span></span> 
- <span data-ttu-id="a5a8d-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Estensione del protocollo SIP (Session Initiation Protocol) per le informazioni sulla cronologia necessarie.</span><span class="sxs-lookup"><span data-stu-id="a5a8d-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) An extension to Session Initiation Protocol (SIP) for required History Information.</span></span> <span data-ttu-id="a5a8d-124">Per altre informazioni, vedere anche: Descrizione del protocollo SIP di routing.</span><span class="sxs-lookup"><span data-stu-id="a5a8d-124">See also: Routing SIP Protocol description for more information.</span></span>
- <span data-ttu-id="a5a8d-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) Meccanismo di Referred-By Session Initiation Protocol</span><span class="sxs-lookup"><span data-stu-id="a5a8d-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) The Session Initiation Protocol Referred-By mechanism</span></span>
- <span data-ttu-id="a5a8d-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) Intestazione SIP (Session Initiation Protocol) "Sostituisce"</span><span class="sxs-lookup"><span data-stu-id="a5a8d-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) The Session Initiation Protocol (SIP) "Replaces" Header</span></span> 
- <span data-ttu-id="a5a8d-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) Utilizzo sip (Session Initiation Protocol) del modello di offerta/risposta.</span><span class="sxs-lookup"><span data-stu-id="a5a8d-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) Session Initiation Protocol (SIP) Usage of the Offer/Answer Model.</span></span>
  <span data-ttu-id="a5a8d-128">Vedere la sezione "Deviazioni da RFC".</span><span class="sxs-lookup"><span data-stu-id="a5a8d-128">See the “Deviations from RFC” section.</span></span>
- <span data-ttu-id="a5a8d-129">[RFC 3711 e](https://tools.ietf.org/html/rfc3711) [RFC 4771](https://tools.ietf.org/html/rfc4771).</span><span class="sxs-lookup"><span data-stu-id="a5a8d-129">[RFC 3711](https://tools.ietf.org/html/rfc3711) and [RFC 4771](https://tools.ietf.org/html/rfc4771).</span></span> <span data-ttu-id="a5a8d-130">Proteggere il traffico RTP usando SRTP.</span><span class="sxs-lookup"><span data-stu-id="a5a8d-130">Protect RTP traffic using SRTP.</span></span> <span data-ttu-id="a5a8d-131">SBC deve essere in grado di stabilire le chiavi usando SDES.</span><span class="sxs-lookup"><span data-stu-id="a5a8d-131">The SBC must be able to establish keys using SDES.</span></span> 
- <span data-ttu-id="a5a8d-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Chiarimenti di offerta/risposta SDP (Session Description Protocol) per RTP/RTCP Multiplexing</span><span class="sxs-lookup"><span data-stu-id="a5a8d-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Session Description Protocol (SDP) Offer/Answer Clarifications for RTP/RTCP Multiplexing</span></span>

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a><span data-ttu-id="a5a8d-133">Standard applicabili ai dispositivi che supportano la modalità bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="a5a8d-133">Standards applicable to devices that support media bypass mode</span></span>

<span data-ttu-id="a5a8d-134">Oltre agli standard elencati come applicabili alla modalità non bypass, per la modalità di bypass multimediale vengono usati gli standard seguenti:</span><span class="sxs-lookup"><span data-stu-id="a5a8d-134">In addition to the standards listed as applicable to non-bypass mode, the following standards are used for media bypass mode:</span></span>

- <span data-ttu-id="a5a8d-135">[RFC 5245 Interactive Connectivity Establishment (ICE) per bypass multimediale](https://tools.ietf.org/html/rfc5245).</span><span class="sxs-lookup"><span data-stu-id="a5a8d-135">[RFC 5245 Interactive Connectivity Establishment (ICE) for media bypass](https://tools.ietf.org/html/rfc5245).</span></span>  <span data-ttu-id="a5a8d-136">SBC deve supportare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="a5a8d-136">The SBC must support the following:</span></span>
  - <span data-ttu-id="a5a8d-137">ICE Lite : i clienti Teams clienti ICE completi</span><span class="sxs-lookup"><span data-stu-id="a5a8d-137">ICE Lite - the Teams clients are full ICE clients</span></span>
  - <span data-ttu-id="a5a8d-138">[ICE Riavvia](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span><span class="sxs-lookup"><span data-stu-id="a5a8d-138">[ICE Restarts](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span></span> <span data-ttu-id="a5a8d-139">Per altre informazioni sul caso di utilizzo dei riavvii ICE, vedere Riavvio ICE: chiamata bypass multimediale trasferita a un endpoint che non supporta il bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="a5a8d-139">See more on ICE restarts use case and examples in ICE Restart:  Media bypass call transferred to an endpoint which does not support media bypass</span></span>   
- <span data-ttu-id="a5a8d-140">[RFC RFC 5589 Session Initiation Protocol (SIP) Call Control – Transfer](https://tools.ietf.org/html/rfc5589).</span><span class="sxs-lookup"><span data-stu-id="a5a8d-140">[RFC RFC 5589 Session Initiation Protocol (SIP) Call Control – Transfer](https://tools.ietf.org/html/rfc5589).</span></span> 
- <span data-ttu-id="a5a8d-141">[RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960), vedere le sezioni 3.1, Forking e 3.2, Ringing Tone Generation</span><span class="sxs-lookup"><span data-stu-id="a5a8d-141">[RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960), see sections 3.1, Forking, and 3.2, Ringing Tone Generation</span></span> 
- [<span data-ttu-id="a5a8d-142">RFC 5389 Session Traversal Utilities for NAT (STUN)</span><span class="sxs-lookup"><span data-stu-id="a5a8d-142">RFC 5389 Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5389)
- [<span data-ttu-id="a5a8d-143">RFC 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)</span><span class="sxs-lookup"><span data-stu-id="a5a8d-143">RFC 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a><span data-ttu-id="a5a8d-144">Standard applicabili per supportare la trasmissione di informazioni sulla posizione ai provider E911</span><span class="sxs-lookup"><span data-stu-id="a5a8d-144">Standards applicable to support conveying location information to E911 providers</span></span>

- [<span data-ttu-id="a5a8d-145">RFC 6442, Informazioni sulla posizione per il protocollo di avvio della sessione</span><span class="sxs-lookup"><span data-stu-id="a5a8d-145">RFC 6442, Location Conveyance for the Session Initiation Protocol</span></span>](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a><span data-ttu-id="a5a8d-146">Deviazioni dalla RFC</span><span class="sxs-lookup"><span data-stu-id="a5a8d-146">Deviations from the RFC's</span></span>

<span data-ttu-id="a5a8d-147">La tabella seguente elenca le sezioni delle RFC in cui l'implementazione microsoft dello stack SIP o multimediale si discosta dallo standard:</span><span class="sxs-lookup"><span data-stu-id="a5a8d-147">The following table lists the sections of the RFC(s) in which Microsoft's implementation of the SIP or media stack deviates from the standard:</span></span>

| <span data-ttu-id="a5a8d-148">RFC e sezioni</span><span class="sxs-lookup"><span data-stu-id="a5a8d-148">RFC and sections</span></span> | <span data-ttu-id="a5a8d-149">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a5a8d-149">Description</span></span> | <span data-ttu-id="a5a8d-150">Deviazione</span><span class="sxs-lookup"><span data-stu-id="a5a8d-150">Deviation</span></span> |
| :---------------------  |:---------------------- |:-----------------------|
| [<span data-ttu-id="a5a8d-151">RFC 6337, sezione 5.3 Blocco e riprendi elementi multimediali</span><span class="sxs-lookup"><span data-stu-id="a5a8d-151">RFC 6337, section 5.3 Hold and Resume of Media</span></span>](https://tools.ietf.org/html/rfc6337#section-5.3) | <span data-ttu-id="a5a8d-152">RFC consente di usare "a=inattivo", "a=sendonly", a=recvonly" per mettere una chiamata in attesa.</span><span class="sxs-lookup"><span data-stu-id="a5a8d-152">RFC allows using “a=inactive”, “a=sendonly”, a=recvonly” to place a call on hold.</span></span> |<span data-ttu-id="a5a8d-153">Il proxy SIP supporta solo "a=inattivo" e non comprende se SBC invia "a=sendonly" o "a=recvonly".</span><span class="sxs-lookup"><span data-stu-id="a5a8d-153">The SIP proxy only supports “a=inactive” and does not understand if the SBC sends “a=sendonly” or “a=recvonly”.</span></span>
| [<span data-ttu-id="a5a8d-154">RFC 6337, sezione 5.4 "Comportamento della ricezione di SDP con c=0.0.0.0</span><span class="sxs-lookup"><span data-stu-id="a5a8d-154">RFC 6337, section 5.4 “Behavior on Receiving SDP with c=0.0.0.0</span></span>](https://tools.ietf.org/html/rfc6337#section-5.4) | <span data-ttu-id="a5a8d-155">[RFC3264](https://tools.ietf.org/html/rfc3264) richiede che un agente sia in grado di ricevere SDP con un indirizzo di connessione 0.0.0.0, nel qual caso significa che né RTP né RTCP devono essere inviati al peer.</span><span class="sxs-lookup"><span data-stu-id="a5a8d-155">[RFC3264](https://tools.ietf.org/html/rfc3264) requires that an agent is capable of receiving SDP with a connection address of 0.0.0.0, in which case it means that neither  RTP nor RTCP should be sent to the peer.</span></span> | <span data-ttu-id="a5a8d-156">Il proxy SIP non supporta questa opzione.</span><span class="sxs-lookup"><span data-stu-id="a5a8d-156">The SIP proxy does not support this option.</span></span> |

## <a name="operational-modes"></a><span data-ttu-id="a5a8d-157">Modalità operative</span><span class="sxs-lookup"><span data-stu-id="a5a8d-157">Operational modes</span></span>

<span data-ttu-id="a5a8d-158">Esistono due modalità operative per il routing diretto:</span><span class="sxs-lookup"><span data-stu-id="a5a8d-158">There are two operational modes for Direct Routing:</span></span>

- <span data-ttu-id="a5a8d-159">**Senza bypass multimediale** in cui tutto il traffico RTP fluisce tra il client Teams, i processori multimediali e sBC.</span><span class="sxs-lookup"><span data-stu-id="a5a8d-159">**Without media bypass** in which all RTP traffic flows between the Teams client, the media processors, and the SBC.</span></span>  

- <span data-ttu-id="a5a8d-160">**Con bypass multimediale** in cui tutti i supporti RTP fluire tra gli endpoint Teams e SBC.</span><span class="sxs-lookup"><span data-stu-id="a5a8d-160">**With media bypass** in which all RTP media flows between the Teams endpoints and the SBC.</span></span> 

<span data-ttu-id="a5a8d-161">Si noti che il traffico SIP fluisce sempre tramite il proxy SIP.</span><span class="sxs-lookup"><span data-stu-id="a5a8d-161">Note that SIP traffic always flows via the SIP proxy.</span></span> 

## <a name="dtmf"></a><span data-ttu-id="a5a8d-162">DTMF</span><span class="sxs-lookup"><span data-stu-id="a5a8d-162">DTMF</span></span>
<span data-ttu-id="a5a8d-163">Il DTMF in banda non è supportato dallo stack multimediale.</span><span class="sxs-lookup"><span data-stu-id="a5a8d-163">In-band DTMF is not supported by media stack.</span></span>

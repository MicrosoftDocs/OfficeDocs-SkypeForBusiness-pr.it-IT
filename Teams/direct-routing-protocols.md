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
# <a name="direct-routing---definitions-and-rfc-standards"></a><span data-ttu-id="d60c0-103">Routing diretto - Definizioni e standard RFC</span><span class="sxs-lookup"><span data-stu-id="d60c0-103">Direct Routing - Definitions and RFC standards</span></span>

<span data-ttu-id="d60c0-104">In questo articolo viene descritto Telefono Microsoft System Direct Routing implementa i protocolli standard RFC.</span><span class="sxs-lookup"><span data-stu-id="d60c0-104">This article describes how Microsoft Phone System Direct Routing implements RFC standard protocols.</span></span> <span data-ttu-id="d60c0-105">Questo articolo è destinato agli amministratori vocali responsabili della configurazione della connessione tra il controller SBC (Session Border Controller) locale e il servizio proxy SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="d60c0-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises Session Border Controller (SBC) and the Session Initiation Protocol (SIP) proxy service.</span></span>

<span data-ttu-id="d60c0-106">Il cliente SBC si interfaccia con i seguenti componenti nel back-end Microsoft Teams'interno:</span><span class="sxs-lookup"><span data-stu-id="d60c0-106">The customer SBC interfaces with the following components in the Microsoft Teams backend:</span></span> 

- <span data-ttu-id="d60c0-107">**Proxy SIP per** la segnalazione.</span><span class="sxs-lookup"><span data-stu-id="d60c0-107">**The SIP proxy** for signaling.</span></span> <span data-ttu-id="d60c0-108">Si tratta del componente di Routing diretto con connessione Internet che gestisce le connessioni SIP (TLS) tra le SBC e il routing diretto.</span><span class="sxs-lookup"><span data-stu-id="d60c0-108">This is the Internet-facing component of Direct Routing that handles SIP (TLS) connections between the SBCs and Direct Routing.</span></span>

- <span data-ttu-id="d60c0-109">**Processori multimediali** per supporti.</span><span class="sxs-lookup"><span data-stu-id="d60c0-109">**The media processors** for media.</span></span> <span data-ttu-id="d60c0-110">Si tratta del componente di Routing diretto rivolto a Internet che gestisce il traffico multimediale.</span><span class="sxs-lookup"><span data-stu-id="d60c0-110">This is the Internet-facing component of Direct Routing that handles media traffic.</span></span> <span data-ttu-id="d60c0-111">Questo componente utilizza protocolli SRTP e SRTCP.</span><span class="sxs-lookup"><span data-stu-id="d60c0-111">This component uses SRTP and SRTCP protocols.</span></span>


<span data-ttu-id="d60c0-112">Per ulteriori informazioni sul routing diretto, vedere [Sistema telefonico Direct Routing](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="d60c0-112">For more information about Direct Routing, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="d60c0-113">Per ulteriori informazioni sull'implementazione del protocollo SIP da parte del routing diretto, vedere [Protocollo Direct Routing - SIP](direct-routing-protocols-sip.md).</span><span class="sxs-lookup"><span data-stu-id="d60c0-113">For more information about how Direct Routing implements the SIP protocol, see [Direct Routing - SIP protocol](direct-routing-protocols-sip.md).</span></span>

## <a name="rfc-standards"></a><span data-ttu-id="d60c0-114">Standard RFC</span><span class="sxs-lookup"><span data-stu-id="d60c0-114">RFC standards</span></span>

<span data-ttu-id="d60c0-115">Il routing diretto è conforme agli standard RFC.</span><span class="sxs-lookup"><span data-stu-id="d60c0-115">Direct Routing complies with RFC standards.</span></span>  <span data-ttu-id="d60c0-116">L'SBC collegato al routing diretto deve inoltre essere conforme alle seguenti RFC (o ai loro successori).</span><span class="sxs-lookup"><span data-stu-id="d60c0-116">The SBC connected to Direct Routing must also comply with the following RFCs (or their successors).</span></span> 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a><span data-ttu-id="d60c0-117">Standard applicabili ai dispositivi che supportano la modalità bypass non multimediale</span><span class="sxs-lookup"><span data-stu-id="d60c0-117">Standards applicable to devices that support non-media bypass mode</span></span> 

<span data-ttu-id="d60c0-118">Gli standard seguenti sono applicabili ai dispositivi che supportano solo la modalità di bypass non multimediale:</span><span class="sxs-lookup"><span data-stu-id="d60c0-118">The following standards are applicable to devices that support only non-media bypass mode:</span></span>

- <span data-ttu-id="d60c0-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Protocollo di avvio della sessione</span><span class="sxs-lookup"><span data-stu-id="d60c0-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Session Initiation Protocol</span></span>
- <span data-ttu-id="d60c0-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span><span class="sxs-lookup"><span data-stu-id="d60c0-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span></span> <span data-ttu-id="d60c0-121">Estensione privata al protocollo di avvio della sessione per l'identità asserta all'interno di reti attendibili- Sezioni sulla gestione dell'intestazione P-Asserted-Identity.</span><span class="sxs-lookup"><span data-stu-id="d60c0-121">Private Extension to the Session Initiation Protocol for asserted identity within Trusted Networks--Sections about handling P-Asserted-Identity header.</span></span> <span data-ttu-id="d60c0-122">Il routing diretto invia p-asserted-identity con intestazioni ID privacy.</span><span class="sxs-lookup"><span data-stu-id="d60c0-122">Direct Routing sends P-Asserted-Identity with Privacy ID headers.</span></span> 
- <span data-ttu-id="d60c0-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Estensione del SIP (Session Initiation Protocol) per le informazioni necessarie sulla cronologia.</span><span class="sxs-lookup"><span data-stu-id="d60c0-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) An extension to Session Initiation Protocol (SIP) for required History Information.</span></span> <span data-ttu-id="d60c0-124">Per ulteriori informazioni, vedere anche: Routing SIP Protocol description.</span><span class="sxs-lookup"><span data-stu-id="d60c0-124">See also: Routing SIP Protocol description for more information.</span></span>
- <span data-ttu-id="d60c0-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) Meccanismo di avvio della sessione Referred-By sessione</span><span class="sxs-lookup"><span data-stu-id="d60c0-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) The Session Initiation Protocol Referred-By mechanism</span></span>
- <span data-ttu-id="d60c0-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) Intestazione SIP (Session Initiation Protocol) "Replaces"</span><span class="sxs-lookup"><span data-stu-id="d60c0-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) The Session Initiation Protocol (SIP) "Replaces" Header</span></span> 
- <span data-ttu-id="d60c0-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) Utilizzo SIP (Session Initiation Protocol) del modello di offerta/risposta.</span><span class="sxs-lookup"><span data-stu-id="d60c0-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) Session Initiation Protocol (SIP) Usage of the Offer/Answer Model.</span></span>
  <span data-ttu-id="d60c0-128">Vedere la sezione "Deviazioni da RFC".</span><span class="sxs-lookup"><span data-stu-id="d60c0-128">See the “Deviations from RFC” section.</span></span>
- <span data-ttu-id="d60c0-129">[RFC 3711](https://tools.ietf.org/html/rfc3711) e [RFC 4771](https://tools.ietf.org/html/rfc4771).</span><span class="sxs-lookup"><span data-stu-id="d60c0-129">[RFC 3711](https://tools.ietf.org/html/rfc3711) and [RFC 4771](https://tools.ietf.org/html/rfc4771).</span></span> <span data-ttu-id="d60c0-130">Proteggere il traffico RTP utilizzando SRTP.</span><span class="sxs-lookup"><span data-stu-id="d60c0-130">Protect RTP traffic using SRTP.</span></span> <span data-ttu-id="d60c0-131">L'SBC deve essere in grado di stabilire chiavi utilizzando SDES.</span><span class="sxs-lookup"><span data-stu-id="d60c0-131">The SBC must be able to establish keys using SDES.</span></span> 
- <span data-ttu-id="d60c0-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Chiarimenti su offerta/risposta SDP (Session Description Protocol) per il multiplexing RTP/RTCP</span><span class="sxs-lookup"><span data-stu-id="d60c0-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Session Description Protocol (SDP) Offer/Answer Clarifications for RTP/RTCP Multiplexing</span></span>

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a><span data-ttu-id="d60c0-133">Standard applicabili ai dispositivi che supportano la modalità di bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="d60c0-133">Standards applicable to devices that support media bypass mode</span></span>

<span data-ttu-id="d60c0-134">Oltre agli standard elencati come applicabili alla modalità non bypass, vengono utilizzati i seguenti standard per la modalità bypass multimediale:</span><span class="sxs-lookup"><span data-stu-id="d60c0-134">In addition to the standards listed as applicable to non-bypass mode, the following standards are used for media bypass mode:</span></span>

- <span data-ttu-id="d60c0-135">[RFC 5245 Interactive Connectivity Establishment (ICE) per il bypass multimediale](https://tools.ietf.org/html/rfc5245).</span><span class="sxs-lookup"><span data-stu-id="d60c0-135">[RFC 5245 Interactive Connectivity Establishment (ICE) for media bypass](https://tools.ietf.org/html/rfc5245).</span></span>  <span data-ttu-id="d60c0-136">L'SBC deve supportare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="d60c0-136">The SBC must support the following:</span></span>
  - <span data-ttu-id="d60c0-137">ICE Lite : i Teams clienti sono clienti ICE completi</span><span class="sxs-lookup"><span data-stu-id="d60c0-137">ICE Lite - the Teams clients are full ICE clients</span></span>
  - <span data-ttu-id="d60c0-138">[ICE Riavvia](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span><span class="sxs-lookup"><span data-stu-id="d60c0-138">[ICE Restarts](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span></span> <span data-ttu-id="d60c0-139">Scopri di più su ICE riavvia il caso d'uso e gli esempi in ICE Restart: Chiamata di bypass multimediale trasferita a un endpoint che non supporta il bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="d60c0-139">See more on ICE restarts use case and examples in ICE Restart:  Media bypass call transferred to an endpoint which does not support media bypass</span></span>   
- <span data-ttu-id="d60c0-140">[RFC RFC 5589 Session Initiation Protocol (SIP) Call Control – Transfer](https://tools.ietf.org/html/rfc5589).</span><span class="sxs-lookup"><span data-stu-id="d60c0-140">[RFC RFC 5589 Session Initiation Protocol (SIP) Call Control – Transfer](https://tools.ietf.org/html/rfc5589).</span></span> 
- <span data-ttu-id="d60c0-141">[RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960), vedere le sezioni 3.1, Forking e 3.2, Ringing Tone Generation</span><span class="sxs-lookup"><span data-stu-id="d60c0-141">[RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960), see sections 3.1, Forking, and 3.2, Ringing Tone Generation</span></span> 
- [<span data-ttu-id="d60c0-142">Utilità di attraversamento sessione RFC 5389 per NAT (STUN)</span><span class="sxs-lookup"><span data-stu-id="d60c0-142">RFC 5389 Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5389)
- [<span data-ttu-id="d60c0-143">RFC 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)</span><span class="sxs-lookup"><span data-stu-id="d60c0-143">RFC 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a><span data-ttu-id="d60c0-144">Norme applicabili per supportare il trasporto di informazioni sulla posizione ai fornitori dell'E911</span><span class="sxs-lookup"><span data-stu-id="d60c0-144">Standards applicable to support conveying location information to E911 providers</span></span>

- [<span data-ttu-id="d60c0-145">RFC 6442, Trasporto posizione per il protocollo di avvio della sessione</span><span class="sxs-lookup"><span data-stu-id="d60c0-145">RFC 6442, Location Conveyance for the Session Initiation Protocol</span></span>](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a><span data-ttu-id="d60c0-146">Deviazioni dagli RFC</span><span class="sxs-lookup"><span data-stu-id="d60c0-146">Deviations from the RFC's</span></span>

<span data-ttu-id="d60c0-147">Nella tabella seguente sono elencate le sezioni delle RFC in cui l'implementazione microsoft del SIP o dello stack multimediale si discosta dallo standard:</span><span class="sxs-lookup"><span data-stu-id="d60c0-147">The following table lists the sections of the RFC(s) in which Microsoft's implementation of the SIP or media stack deviates from the standard:</span></span>

| <span data-ttu-id="d60c0-148">RFC e sezioni</span><span class="sxs-lookup"><span data-stu-id="d60c0-148">RFC and sections</span></span> | <span data-ttu-id="d60c0-149">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d60c0-149">Description</span></span> | <span data-ttu-id="d60c0-150">deviazione</span><span class="sxs-lookup"><span data-stu-id="d60c0-150">Deviation</span></span> |
| :---------------------  |:---------------------- |:-----------------------|
| [<span data-ttu-id="d60c0-151">RFC 6337, sezione 5.3 Sospensione e ripresa dei supporti</span><span class="sxs-lookup"><span data-stu-id="d60c0-151">RFC 6337, section 5.3 Hold and Resume of Media</span></span>](https://tools.ietf.org/html/rfc6337#section-5.3) | <span data-ttu-id="d60c0-152">RFC consente di utilizzare "a=inactive", "a=sendonly", a=recvonly" per mettere una chiamata in attesa.</span><span class="sxs-lookup"><span data-stu-id="d60c0-152">RFC allows using “a=inactive”, “a=sendonly”, a=recvonly” to place a call on hold.</span></span> |<span data-ttu-id="d60c0-153">Il proxy SIP supporta solo "a=inactive" e non capisce se l'SBC invia "a=sendonly" o "a=recvonly".</span><span class="sxs-lookup"><span data-stu-id="d60c0-153">The SIP proxy only supports “a=inactive” and does not understand if the SBC sends “a=sendonly” or “a=recvonly”.</span></span>
| [<span data-ttu-id="d60c0-154">RFC 6337, sezione 5.4 "Comportamento durante la ricezione di SDP con c=0.0.0.0</span><span class="sxs-lookup"><span data-stu-id="d60c0-154">RFC 6337, section 5.4 “Behavior on Receiving SDP with c=0.0.0.0</span></span>](https://tools.ietf.org/html/rfc6337#section-5.4) | <span data-ttu-id="d60c0-155">[RFC3264 richiede](https://tools.ietf.org/html/rfc3264) che un agente sia in grado di ricevere SDP con un indirizzo di connessione 0.0.0.0, nel qual caso significa che né RTP né RTCP devono essere inviati al peer.</span><span class="sxs-lookup"><span data-stu-id="d60c0-155">[RFC3264](https://tools.ietf.org/html/rfc3264) requires that an agent is capable of receiving SDP with a connection address of 0.0.0.0, in which case it means that neither  RTP nor RTCP should be sent to the peer.</span></span> | <span data-ttu-id="d60c0-156">Il proxy SIP non supporta questa opzione.</span><span class="sxs-lookup"><span data-stu-id="d60c0-156">The SIP proxy does not support this option.</span></span> |

## <a name="operational-modes"></a><span data-ttu-id="d60c0-157">Modalità operative</span><span class="sxs-lookup"><span data-stu-id="d60c0-157">Operational modes</span></span>

<span data-ttu-id="d60c0-158">Esistono due modalità operative per il routing diretto:</span><span class="sxs-lookup"><span data-stu-id="d60c0-158">There are two operational modes for Direct Routing:</span></span>

- <span data-ttu-id="d60c0-159">**Senza bypass multimediale** in cui tutto il traffico RTP scorre tra il client Teams, i processori multimediali e l'SBC.</span><span class="sxs-lookup"><span data-stu-id="d60c0-159">**Without media bypass** in which all RTP traffic flows between the Teams client, the media processors, and the SBC.</span></span>  

- <span data-ttu-id="d60c0-160">**Con bypass multimediale** in cui tutti i supporti RTP fluisce tra gli endpoint Teams e l'SBC.</span><span class="sxs-lookup"><span data-stu-id="d60c0-160">**With media bypass** in which all RTP media flows between the Teams endpoints and the SBC.</span></span> 

<span data-ttu-id="d60c0-161">Si noti che il traffico SIP scorre sempre tramite il proxy SIP.</span><span class="sxs-lookup"><span data-stu-id="d60c0-161">Note that SIP traffic always flows via the SIP proxy.</span></span> 

## <a name="dtmf"></a><span data-ttu-id="d60c0-162">Dtmf</span><span class="sxs-lookup"><span data-stu-id="d60c0-162">DTMF</span></span>
<span data-ttu-id="d60c0-163">DTMF in banda non è supportato dallo stack multimediale.</span><span class="sxs-lookup"><span data-stu-id="d60c0-163">In-band DTMF is not supported by media stack.</span></span>

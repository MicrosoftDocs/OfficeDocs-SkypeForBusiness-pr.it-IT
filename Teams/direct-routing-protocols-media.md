---
title: Instradamento diretto di Sistema telefonico
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
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
ms.openlocfilehash: 43673c2b6a1928ab2ca21579339324f01d5ada9e
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888575"
---
# <a name="overview"></a><span data-ttu-id="6cb7b-103">Panoramica</span><span class="sxs-lookup"><span data-stu-id="6cb7b-103">Overview</span></span>

<span data-ttu-id="6cb7b-104">Questo articolo descrive in che modo il routing diretto supporta il bypass multimediale con un session border controller (SBC) abilitato per ICE Lite, come descritto in [RFC 5245.](https://tools.ietf.org/html/rfc5245)</span><span class="sxs-lookup"><span data-stu-id="6cb7b-104">This article describes how Direct Routing supports media bypass with a Session Border Controller (SBC) enabled for ICE Lite as described in [RFC 5245](https://tools.ietf.org/html/rfc5245).</span></span> <span data-ttu-id="6cb7b-105">Questo articolo è rivolto agli amministratori vocali responsabili della configurazione della connessione tra il servizio SBC locale e il servizio proxy SIP.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises SBC and the SIP proxy service.</span></span>

<span data-ttu-id="6cb7b-106">Questo articolo fornisce una panoramica degli scenari e dei requisiti ice Lite per l'interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-106">This article provides an overview of the ICE Lite scenarios and requirements for interoperability.</span></span> <span data-ttu-id="6cb7b-107">L'articolo descrive i formati dei messaggi e le transizioni richieste della macchina a stati per garantire un flusso affidabile di chiamate e supporti.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-107">The article describes the message formats and the required state machine transitions for ensuring reliable call and media flow.</span></span>

## <a name="terminology"></a><span data-ttu-id="6cb7b-108">Terminologia</span><span class="sxs-lookup"><span data-stu-id="6cb7b-108">Terminology</span></span>

- <span data-ttu-id="6cb7b-109">First Hello: le prime parole pronunciate dal chiamante e dal chiamato.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-109">First Hello – The first words spoken by the caller and callee.</span></span> <span data-ttu-id="6cb7b-110">È importante fare tutto il possibile per garantire che i primi pacchetti degli endpoint siano recapitati in modo affidabile per la maggior parte dei casi d'uso.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-110">It is important that all efforts are made to ensure that the first packets from the endpoints are delivered reliably for most use cases.</span></span>

- <span data-ttu-id="6cb7b-111">Forking: l'offerta del chiamante potrebbe essere recapitata a più endpoint del chiamato se il chiamato è disponibile su più dispositivi (ad esempio, un utente di Teams potrebbe aver eseguito l'accesso a Teams per Windows e Teams per Android o iPhone).</span><span class="sxs-lookup"><span data-stu-id="6cb7b-111">Forking – The offer from the caller might be delivered to multiple callee endpoints if the callee is available on multiple devices (for example, a Teams user might be signed into Teams for Windows and Teams for Android or iPhone).</span></span>

- <span data-ttu-id="6cb7b-112">Risposta provvisoria (183) - Gli endpoint del chiamato per una configurazione più rapida della chiamata inviano una risposta con i candidati e i tasti necessari per stabilire il flusso multimediale.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-112">Provisional Answer (183) – The callee endpoints for faster call setup send an answer with the candidates and keys required to establish media flow.</span></span> <span data-ttu-id="6cb7b-113">Questa operazione viene eseguita in previsione che l'utente risponda potenzialmente alla chiamata(200OK) da quella specifica istanza del chiamato.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-113">This is done in anticipation of the user potentially answering the call(200OK) from that specific callee instance.</span></span> <span data-ttu-id="6cb7b-114">Con il forking, il chiamante dovrebbe essere pronto a ricevere più risposte provvisorie.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-114">With forking, the caller should be ready to receive multiple provisional answers.</span></span>

- <span data-ttu-id="6cb7b-115">Re-Invite: offerta con i candidati finali selezionati dall'endpoint di controllo ICE.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-115">Re-Invite – Offer with final candidates selected by the ICE controlling endpoint.</span></span> <span data-ttu-id="6cb7b-116">Questo avrà l'attributo a=remote-candidate per risolvere eventuali condizioni di gara dalla gestione di più forche.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-116">This will have the a=remote-candidate attribute to resolve any race conditions from handling multiple forks.</span></span>

- <span data-ttu-id="6cb7b-117">Teams Endpoint: può trattarsi di un server (Processore multimediale, Inoltro di trasporto) o Teams client.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-117">Teams Endpoint – This could either be a server (Media Processor, Transport Relay) or the Teams client.</span></span>

## <a name="message-format"></a><span data-ttu-id="6cb7b-118">Formato del messaggio</span><span class="sxs-lookup"><span data-stu-id="6cb7b-118">Message format</span></span>

<span data-ttu-id="6cb7b-119">L Teams dell'infrastruttura segue l'RFC 5245 per ICE-Lite.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-119">The Teams infrastructure follows RFC 5245 for ICE-Lite.</span></span> <span data-ttu-id="6cb7b-120">Questo implica che tutti i messaggi STUN saranno conformi a [RFC 5389.](https://tools.ietf.org/html/rfc5389)</span><span class="sxs-lookup"><span data-stu-id="6cb7b-120">This implies that all the STUN messages will be compliant with [RFC 5389](https://tools.ietf.org/html/rfc5389).</span></span>

<span data-ttu-id="6cb7b-121">Gli SBC come richiesto da RFC 5389 devono ignorare gli attributi STUN che non riconoscono e continuare a elaborare i messaggi con gli attributi noti.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-121">The SBCs as required by RFC 5389 must ignore any STUN attributes that they do not recognize, and continue to process the messages with the known attributes.</span></span> 

<span data-ttu-id="6cb7b-122">Se vengono ricevuti pacchetti in formato non corretto, i pacchetti devono essere eliminati senza influire sulla creazione della sessione multimediale.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-122">If any malformed packets are received, the packets must be discarded without impacting the media session establishment.</span></span>

## <a name="ice-lite-requirements"></a><span data-ttu-id="6cb7b-123">Requisiti ice Lite</span><span class="sxs-lookup"><span data-stu-id="6cb7b-123">ICE Lite requirements</span></span>

<span data-ttu-id="6cb7b-124">Questa sezione acquisisce brevemente i requisiti per ICE Lite.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-124">This section briefly captures the requirements for ICE Lite.</span></span>

### <a name="candidate-gathering"></a><span data-ttu-id="6cb7b-125">Raccolta di candidati</span><span class="sxs-lookup"><span data-stu-id="6cb7b-125">Candidate gathering</span></span>

<span data-ttu-id="6cb7b-126">L'SBC deve offrire un solo candidato accessibile pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-126">The SBC must offer only one candidate that is publicly reachable.</span></span> <span data-ttu-id="6cb7b-127">Attualmente sono supportati solo i candidati IPV4.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-127">Currently, only IPV4 candidates are supported.</span></span>


#### <a name="connectivity-checks"></a><span data-ttu-id="6cb7b-128">Controlli di connettività</span><span class="sxs-lookup"><span data-stu-id="6cb7b-128">Connectivity checks</span></span>

<span data-ttu-id="6cb7b-129">L'implementazione ICE Lite deve rispondere a tutti i controlli di connettività ricevuti.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-129">The ICE Lite implementation must respond to any connectivity checks received.</span></span> <span data-ttu-id="6cb7b-130">L'endpoint ICE Lite non deve inviare richieste di controllo della connettività.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-130">The ICE Lite endpoint must not send any connectivity check requests.</span></span> <span data-ttu-id="6cb7b-131">Se i controlli di connettività vengono inviati in violazione, l'implementazione completa risponderà, il che può comportare l'individuarsi di candidati imprevisti derivati da peer e potenzialmente errori di chiamata.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-131">(If connectivity checks are sent in violation, the full implementation will respond, which can result in unexpected peer-derived candidates being discovered and potentially result in call failures.)</span></span>

#### <a name="nominations"></a><span data-ttu-id="6cb7b-132">Candidature</span><span class="sxs-lookup"><span data-stu-id="6cb7b-132">Nominations</span></span>

<span data-ttu-id="6cb7b-133">L'endpoint di implementazione completa ICE sarà sempre l'endpoint di controllo e seguirà le nomine "regolari" per la selezione dei candidati finali da usare per il flusso multimediale.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-133">The ICE full implementation endpoint will always be the Controlling endpoint, and will follow “Regular” nominations for selecting the final candidates to be used for media flow.</span></span> <span data-ttu-id="6cb7b-134">L'endpoint ICE Lite può usare le nomine per concludere il percorso da usare per i supporti multimediali e completare la creazione di chiamate.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-134">The ICE Lite endpoint can use the nominations to conclude the path to be used for media and complete call establishment.</span></span>

<span data-ttu-id="6cb7b-135">Nota: nel caso di un forking con endpoint peer che inviano 183 risposte provvisorie, SBC deve essere pronto a rispondere ai controlli provenienti da più endpoint e anche alle nomine da più endpoint se le nomine si verificano prima del 200OK.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-135">Note: In the case of forking with peer endpoints sending 183 provisional answers, the SBC must be ready to respond to checks from multiple endpoints and also nominations from multiple endpoints if the nominations happen before 200OK.</span></span> <span data-ttu-id="6cb7b-136">A seconda della convergenza della macchina a stati ICE sul percorso finale e dell'intervallo di risposta dell'utente, le nomine possono avvenire prima o dopo il 200OK.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-136">Depending on the convergence of the ICE state machine on the final path and timing of the user answering, the nominations can happen before or after 200OK.</span></span> <span data-ttu-id="6cb7b-137">SBC deve essere in grado di gestire entrambi i casi.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-137">The SBC must be able to handle both cases.</span></span>

#### <a name="converging-for-forking"></a><span data-ttu-id="6cb7b-138">Convergenza per il forking</span><span class="sxs-lookup"><span data-stu-id="6cb7b-138">Converging for forking</span></span>

<span data-ttu-id="6cb7b-139">Se l'offerta da SBC viene forcata a più endpoint Teams, gli endpoint Teams possono rispondere con una risposta provvisoria e avviare i controlli di connettività.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-139">If the offer from the SBC forks to multiple Teams endpoints, the Teams endpoints may respond with a provisional answer and start connectivity checks.</span></span> <span data-ttu-id="6cb7b-140">SBC deve essere preparato per ricevere i controlli di connettività e rispondere ai controlli di connettività da più endpoint peer.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-140">The SBC must be prepared to receive connectivity checks and respond to connectivity checks from multiple peer endpoints.</span></span> <span data-ttu-id="6cb7b-141">Ad esempio, l Teams utente potrebbe essere connesso sia a un desktop che a un cellulare.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-141">For example, the Teams user could be signed on to both a desktop and a cell phone.</span></span> <span data-ttu-id="6cb7b-142">Entrambi i dispositivi riceveranno una notifica della chiamata in ingresso e tenteranno di verificare la connettività con SBC.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-142">Both devices will be notified of the inbound call and will attempt connectivity checks with the SBC.</span></span>

<span data-ttu-id="6cb7b-143">Alla fine solo uno degli endpoint risponderà alla chiamata (200OK).</span><span class="sxs-lookup"><span data-stu-id="6cb7b-143">Eventually only one of the endpoints will answer the call (200OK).</span></span> <span data-ttu-id="6cb7b-144">Quando si riceve 200OK, SBC può configurare il contesto giusto per l'elaborazione dei pacchetti multimediali.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-144">On receiving the 200OK, the SBC can set up the right context for processing the media packets.</span></span>

## <a name="scenarios"></a><span data-ttu-id="6cb7b-145">Scenari</span><span class="sxs-lookup"><span data-stu-id="6cb7b-145">Scenarios</span></span>

###  <a name="inbound-call-from-sbc"></a><span data-ttu-id="6cb7b-146">Chiamata in ingresso da SBC</span><span class="sxs-lookup"><span data-stu-id="6cb7b-146">Inbound call from SBC</span></span>

<span data-ttu-id="6cb7b-147">Per questo scenario, sono disponibili diversi endpoint peer che il servizio SBC deve gestire:</span><span class="sxs-lookup"><span data-stu-id="6cb7b-147">For this scenario, there are several possible peer endpoints that the SBC must handle:</span></span>

- <span data-ttu-id="6cb7b-148">Gli endpoint del server in genere rispondono direttamente con 200OK.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-148">Server endpoints will typically respond directly with 200OK.</span></span> <span data-ttu-id="6cb7b-149">Si tratta di endpoint ICE completi che in genere sono coinvolti negli scenari di segreteria telefonica, coda di chiamata e operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-149">These are full ICE endpoints that are typically involved in Voicemail, Call queue, and Auto attendant scenarios.</span></span>

- <span data-ttu-id="6cb7b-150">Gli endpoint client possono inviare più risposte provvisorie con tag From/To diversi (183) seguiti da un 200OK dall'endpoint che risponde alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-150">Client endpoints can send multiple provisional answers with different From/To tags (183) followed by a 200OK from the endpoint that answers the call.</span></span> <span data-ttu-id="6cb7b-151">Si tratta di endpoint ICE completi che rappresentano in genere i client degli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-151">These are full ICE endpoints typically representing end user clients.</span></span>

- <span data-ttu-id="6cb7b-152">Altri endpoint SBC.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-152">Other SBC endpoints.</span></span> <span data-ttu-id="6cb7b-153">Si tratta di endpoint ICE Lite in genere coinvolti nello scenario di squillo simultaneo degli endpoint client e di altri numeri di telefono.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-153">These are ICE Lite endpoints typically involved in the scenario of simultaneously ringing client endpoints and another phone number(s).</span></span>

<span data-ttu-id="6cb7b-154">SBC deve rispondere a tutte le richieste di controllo della connettività valide ricevute dagli endpoint ICE completi.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-154">The SBC must respond to all valid connectivity check requests received from the full ICE endpoints.</span></span> <span data-ttu-id="6cb7b-155">Per RFC, gli endpoint ICE completi diventeranno Controllo degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-155">Per RFC, the full ICE endpoints will become Controlling endpoints.</span></span> <span data-ttu-id="6cb7b-156">Gli endpoint Teams (client/server) eseguiranno nomine "regolari" per completare i controlli di connettività.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-156">The Teams (client/server) endpoints will perform “Regular” nominations to complete connectivity checks.</span></span> <span data-ttu-id="6cb7b-157">Il 200Ok finale può essere da un endpoint che ha inviato elementi multimediali iniziali o da un endpoint diverso.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-157">The final 200Ok can either be from an endpoint that sent early media or from a different endpoint.</span></span> <span data-ttu-id="6cb7b-158">Quando si riceve 200Ok, SBC deve configurare il contesto giusto per il flusso multimediale.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-158">On receiving the 200Ok, the SBC must set up the right context for media flow.</span></span> 

###  <a name="early-media"></a><span data-ttu-id="6cb7b-159">Elementi multimediali iniziali</span><span class="sxs-lookup"><span data-stu-id="6cb7b-159">Early media</span></span>

<span data-ttu-id="6cb7b-160">Se è presente un flusso multimediale iniziale, il dispositivo SBC deve eseguire il latch al primo endpoint che avvia lo streaming multimediale. il flusso multimediale può iniziare prima della nomina dei candidati.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-160">If there is early media flow, the SBC must latch to the first endpoint that starts streaming media; media flow can start before candidates are nominated.</span></span> <span data-ttu-id="6cb7b-161">L'SBC dovrebbe avere il supporto per l'invio di DTMF durante questa fase per abilitare gli scenari IVR/segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-161">The SBC should have support for sending DTMF during this phase to enable IVR/voicemail scenarios.</span></span> <span data-ttu-id="6cb7b-162">L'SBC deve usare il percorso con la priorità più alta in cui ha ricevuto i controlli se le nomine non sono state completate.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-162">The SBC should use the highest priority path on which it has received checks if nominations have not completed.</span></span>

### <a name="outbound-call-to-sbc"></a><span data-ttu-id="6cb7b-163">Chiamata in uscita a SBC</span><span class="sxs-lookup"><span data-stu-id="6cb7b-163">Outbound call to SBC</span></span>

<span data-ttu-id="6cb7b-164">Gli Teams endpoint sono il Chiamante per questo scenario e saranno l'endpoint di controllo.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-164">The Teams endpoints are the Caller for this scenario and will be the Controlling Endpoint.</span></span> <span data-ttu-id="6cb7b-165">Quando si riceve una risposta provvisoria (183) o una risposta finale(200OK), l'endpoint di Teams avvia i controlli di connettività e procede alle nomine "regolari" per completare i controlli di connettività.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-165">On receiving either a provisional answer (183) or a final answer(200OK), the Teams endpoint  will start connectivity checks and proceed to “Regular” nominations to complete the connectivity checks.</span></span>

<span data-ttu-id="6cb7b-166">Nota: se SBC invia una risposta provvisoria (183), deve essere pronto per ricevere le richieste di verifica della connettività e potenzialmente completare le nomine prima che il 200OK venga inviato dalla SBC.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-166">Note: If the SBC sends a provisional answer (183), the SBC must be ready to receive connectivity check requests and potentially complete the nominations  before the 200OK is sent by the SBC.</span></span> <span data-ttu-id="6cb7b-167">Se i controlli e/o le nomine vengono completate prima della ricezione del 200OK, i controlli e/o le nomine non verranno eseguiti di nuovo dopo la ricezione di 200OK.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-167">If checks and/or nominations are completed before the 200OK is received, checks and/or nominations will not be performed again after 200OK is received.</span></span> <span data-ttu-id="6cb7b-168">L'SBC non deve modificare i candidati ICE, la password e l'ufrag (frammento del nome utente) tra 183 e 200.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-168">The SBC must not change ICE candidates, password, and ufrag (username fragment) between 183 and 200.</span></span>

<span data-ttu-id="6cb7b-169">Per supportare i primi media, la SBC può iniziare a trasmettere i contenuti multimediali al candidato ICE peer, con la priorità più alta in base ai controlli di connettività ricevuti, anche prima che le candidature siano completate da un endpoint Teams finale.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-169">To support early media, the SBC may start streaming the media to the peer ICE candidate, with the highest priority based on received connectivity checks, even before nominations are completed by Teams endpoint.</span></span> <span data-ttu-id="6cb7b-170">La SBC dovrebbe aspettarsi che i media Teams su qualsiasi candidato fino al completamento delle candidature.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-170">The SBC should expect media from Teams on any candidate until nominations are completed.</span></span> <span data-ttu-id="6cb7b-171">Dopo la nomina di un candidato, il SBC deve reimpostare il contesto giusto per inviare e ricevere pacchetti multimediali.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-171">Once a candidate is nominated, the SBC must reset to the right context to send and receive media packets.</span></span>

## <a name="srtp-support-requirements"></a><span data-ttu-id="6cb7b-172">Requisiti di supporto SRTP</span><span class="sxs-lookup"><span data-stu-id="6cb7b-172">SRTP support requirements</span></span>

<span data-ttu-id="6cb7b-173">La crittografia SBC deve supportare i AES_CM_128_HMAC_SHA1_80 crittografia SRTP per offrire e rispondere nel formato seguente:</span><span class="sxs-lookup"><span data-stu-id="6cb7b-173">The SBC must support SRTP encryption cipher AES_CM_128_HMAC_SHA1_80 for offer and answer in the following format:</span></span>

```console
"inline:" <key||salt> ["|" lifetime]
```

<span data-ttu-id="6cb7b-174">Di seguito è riportato un esempio dell'attributo crypto nell'offerta SDP da SBC:</span><span class="sxs-lookup"><span data-stu-id="6cb7b-174">The following is an example of the crypto attribute in the SDP offer from the SBC:</span></span>

```console
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

<span data-ttu-id="6cb7b-175">I parametri MKI e Length non sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-175">MKI and Length parameters are not required.</span></span>

<span data-ttu-id="6cb7b-176">Per altre informazioni, vedere [RFC 4568, sezione 6.1.](https://tools.ietf.org/html/rfc4568#section-6.1)</span><span class="sxs-lookup"><span data-stu-id="6cb7b-176">For more information, see [RFC 4568, section 6.1](https://tools.ietf.org/html/rfc4568#section-6.1).</span></span>

## <a name="sdes-support-requirements"></a><span data-ttu-id="6cb7b-177">Requisiti di supporto per SDES</span><span class="sxs-lookup"><span data-stu-id="6cb7b-177">SDES support requirements</span></span>

<span data-ttu-id="6cb7b-178">Il dispositivo deve essere in grado di offrire SDES nel formato descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-178">The device must be able to offer SDES in the format as described below.</span></span> <span data-ttu-id="6cb7b-179">I processori Microsoft Media preferiscono sempre SDES.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-179">Microsoft Media Processors always prefer SDES.</span></span>

- <span data-ttu-id="6cb7b-180">Con il bypass non multimediale, anche se un client supporta solo DTLS, i processori multimediali verranno convertiti in SDES.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-180">With non-media bypass, even if a client only supports DTLS, the Media Processors will convert to SDES.</span></span>

- <span data-ttu-id="6cb7b-181">Con il bypass multimediale, se un client è solo DTLS (stato futuro di Google Chrome), Direct Routing inserirà un MP nel percorso, convertendo la chiamata da bypass multimediale a bypass non multimediale.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-181">With media bypass, if a client is DTLS only (future Google Chrome state), Direct Routing will insert an MP in the path, converting the call from media bypass to non-media bypass.</span></span> <span data-ttu-id="6cb7b-182">Tra il componente SBC e il processore multimediale di Direct Routing, viene sempre usato SDES.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-182">Between the SBC and media processor component of Direct Routing, SDES is always used.</span></span>

<span data-ttu-id="6cb7b-183">Attualmente non sono disponibili client Teams che offrono solo DTLS. Tuttavia, Google ha annunciato che, a un certo punto, smetterà di supportare SDES.</span><span class="sxs-lookup"><span data-stu-id="6cb7b-183">Currently, there are no Teams client that offer only DTLS; however Google has announced that at some point in time they will stop supporting SDES.</span></span>

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a><span data-ttu-id="6cb7b-184">Formato per l'offerta da SBC in modalità bypass</span><span class="sxs-lookup"><span data-stu-id="6cb7b-184">Format for offer from SBC in bypass mode</span></span> 

<span data-ttu-id="6cb7b-185">Offer deve contenere SDES e può contenere DTLS facoltativo nel formato seguente:</span><span class="sxs-lookup"><span data-stu-id="6cb7b-185">Offer must contain SDES and can contain DTLS optional in the following format:</span></span>

```console
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a><span data-ttu-id="6cb7b-186">Formato per la risposta contenente da SDES a SBC</span><span class="sxs-lookup"><span data-stu-id="6cb7b-186">Format for answer containing SDES to SBC</span></span>

```console
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a><span data-ttu-id="6cb7b-187">Formato per l'offerta da Teams a SBC</span><span class="sxs-lookup"><span data-stu-id="6cb7b-187">Format for offer from Teams to SBC</span></span> 

### <a name="format-for-sdes-only-offer-to-sbc"></a><span data-ttu-id="6cb7b-188">Format for SDES only offer to SBC</span><span class="sxs-lookup"><span data-stu-id="6cb7b-188">Format for SDES only offer to SBC</span></span>

```console
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```


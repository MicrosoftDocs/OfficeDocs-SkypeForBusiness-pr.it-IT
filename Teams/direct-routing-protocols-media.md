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
description: Protocolli di routing diretto
appliesto:
- Microsoft Teams
ms.openlocfilehash: 08b022799b2c8bf80ee30cbb0a5ef3e74f0a29e1
ms.sourcegitcommit: 89106cfda0d900d8be541943b7d1537bc69ed57f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/16/2019
ms.locfileid: "40065666"
---
# <a name="overview"></a><span data-ttu-id="93b26-103">Panoramica</span><span class="sxs-lookup"><span data-stu-id="93b26-103">Overview</span></span>

<span data-ttu-id="93b26-104">Questo articolo descrive il modo in cui il routing diretto supporta il bypass multimediale con un SBC (Session Border Controller) abilitato per ICE Lite, come descritto in [RFC 5245](https://tools.ietf.org/html/rfc5245).</span><span class="sxs-lookup"><span data-stu-id="93b26-104">This article describes how Direct Routing supports media bypass with a Session Border Controller (SBC) enabled for ICE Lite as described in [RFC 5245](https://tools.ietf.org/html/rfc5245).</span></span> <span data-ttu-id="93b26-105">Questo articolo è destinato agli amministratori vocali responsabili della configurazione della connessione tra l'SBC locale e il servizio proxy SIP.</span><span class="sxs-lookup"><span data-stu-id="93b26-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises SBC and the SIP proxy service.</span></span>

<span data-ttu-id="93b26-106">Questo articolo offre una panoramica degli scenari e dei requisiti ICE Lite per l'interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="93b26-106">This article provides an overview of the ICE Lite scenarios and requirements for interoperability.</span></span> <span data-ttu-id="93b26-107">L'articolo descrive i formati dei messaggi e le transizioni necessarie della macchina a stati per garantire la chiamata e il flusso di elementi multimediali affidabili.</span><span class="sxs-lookup"><span data-stu-id="93b26-107">The article describes the message formats and the required state machine transitions for ensuring reliable call and media flow.</span></span>

## <a name="terminology"></a><span data-ttu-id="93b26-108">Terminologia</span><span class="sxs-lookup"><span data-stu-id="93b26-108">Terminology</span></span>

- <span data-ttu-id="93b26-109">Primo saluto: le prime parole pronunciate dal chiamante e dal chiamato.</span><span class="sxs-lookup"><span data-stu-id="93b26-109">First Hello – The first words spoken by the caller and callee.</span></span> <span data-ttu-id="93b26-110">È importante che tutti gli sforzi vengano effettuati per garantire che i primi pacchetti degli endpoint vengano recapitati in modo affidabile per la maggior parte dei casi di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="93b26-110">It is important that all efforts are made to ensure that the first packets from the endpoints are delivered reliably for most use cases.</span></span>

- <span data-ttu-id="93b26-111">Fork: l'offerta del chiamante può essere recapitata a più endpoint di chiamata, se il chiamato è disponibile su più dispositivi (ad esempio, un utente di teams può essere connesso a team per Windows e teams per Android o iPhone).</span><span class="sxs-lookup"><span data-stu-id="93b26-111">Forking – The offer from the caller might be delivered to multiple callee endpoints if the callee is available on multiple devices (for example, a Teams user might be signed into Teams for Windows and Teams for Android or iPhone).</span></span>

- <span data-ttu-id="93b26-112">Risposta provvisoria (183): gli endpoint dei chiamanti per una configurazione più rapida delle chiamate inviano una risposta con i candidati e le chiavi necessarie per stabilire il flusso multimediale.</span><span class="sxs-lookup"><span data-stu-id="93b26-112">Provisional Answer (183) – The callee endpoints for faster call setup send an answer with the candidates and keys required to establish media flow.</span></span> <span data-ttu-id="93b26-113">Questa operazione viene eseguita in previsione dell'utente che può potenzialmente rispondere alla chiamata (200OK) da quella specifica istanza di chiamato.</span><span class="sxs-lookup"><span data-stu-id="93b26-113">This is done in anticipation of the user potentially answering the call(200OK) from that specific callee instance.</span></span> <span data-ttu-id="93b26-114">Con il fork, il chiamante dovrebbe essere pronto per ricevere più risposte provvisorie.</span><span class="sxs-lookup"><span data-stu-id="93b26-114">With forking, the caller should be ready to receive multiple provisional answers.</span></span>

- <span data-ttu-id="93b26-115">Re-invite-offerta con i candidati finali selezionati dall'endpoint di controllo del ghiaccio.</span><span class="sxs-lookup"><span data-stu-id="93b26-115">Re-Invite – Offer with final candidates selected by the ICE controlling endpoint.</span></span> <span data-ttu-id="93b26-116">Questo avrà l'attributo a = Remote-candidate per risolvere qualsiasi condizione di competizione dalla gestione di più fork.</span><span class="sxs-lookup"><span data-stu-id="93b26-116">This will have the a=remote-candidate attribute to resolve any race conditions from handling multiple forks.</span></span>

- <span data-ttu-id="93b26-117">Endpoint teams: può essere un server (media processor, Transport Relay) o il client teams.</span><span class="sxs-lookup"><span data-stu-id="93b26-117">Teams Endpoint – This could either be a server (Media Processor, Transport Relay) or the Teams client.</span></span>

## <a name="message-format"></a><span data-ttu-id="93b26-118">Formato messaggio</span><span class="sxs-lookup"><span data-stu-id="93b26-118">Message format</span></span>

<span data-ttu-id="93b26-119">L'infrastruttura teams segue l'RFC 5245 per ICE-Lite.</span><span class="sxs-lookup"><span data-stu-id="93b26-119">The Teams infrastructure follows RFC 5245 for ICE-Lite.</span></span> <span data-ttu-id="93b26-120">Ciò significa che tutti i messaggi STUN saranno conformi alla [specifica RFC 5389](https://tools.ietf.org/html/rfc5389).</span><span class="sxs-lookup"><span data-stu-id="93b26-120">This implies that all the STUN messages will be compliant with [RFC 5389](https://tools.ietf.org/html/rfc5389).</span></span>

<span data-ttu-id="93b26-121">SBCs come richiesto da RFC 5389 deve ignorare gli attributi STUN che non riconoscono e continuare a elaborare i messaggi con gli attributi noti.</span><span class="sxs-lookup"><span data-stu-id="93b26-121">The SBCs as required by RFC 5389 must ignore any STUN attributes that they do not recognize, and continue to process the messages with the known attributes.</span></span> 

<span data-ttu-id="93b26-122">Se vengono ricevuti pacchetti non validi, i pacchetti devono essere eliminati senza impatto sullo stabilimento della sessione multimediale.</span><span class="sxs-lookup"><span data-stu-id="93b26-122">If any malformed packets are received, the packets must be discarded without impacting the media session establishment.</span></span>

## <a name="ice-lite-requirements"></a><span data-ttu-id="93b26-123">Requisiti per ICE Lite</span><span class="sxs-lookup"><span data-stu-id="93b26-123">ICE Lite requirements</span></span>

<span data-ttu-id="93b26-124">Questa sezione acquisisce brevemente i requisiti per ICE Lite.</span><span class="sxs-lookup"><span data-stu-id="93b26-124">This section briefly captures the requirements for ICE Lite.</span></span>

### <a name="candidate-gathering"></a><span data-ttu-id="93b26-125">Riunione candidata</span><span class="sxs-lookup"><span data-stu-id="93b26-125">Candidate gathering</span></span>

<span data-ttu-id="93b26-126">Il SBC deve offrire solo un candidato che sia accessibile pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="93b26-126">The SBC must offer only one candidate that is publicly reachable.</span></span> <span data-ttu-id="93b26-127">Attualmente sono supportati solo i candidati IPV4.</span><span class="sxs-lookup"><span data-stu-id="93b26-127">Currently, only IPV4 candidates are supported.</span></span>


#### <a name="connectivity-checks"></a><span data-ttu-id="93b26-128">Controlli di connettività</span><span class="sxs-lookup"><span data-stu-id="93b26-128">Connectivity checks</span></span>

<span data-ttu-id="93b26-129">L'implementazione di ICE Lite deve rispondere a tutti i controlli di connettività ricevuti.</span><span class="sxs-lookup"><span data-stu-id="93b26-129">The ICE Lite implementation must respond to any connectivity checks received.</span></span> <span data-ttu-id="93b26-130">L'endpoint ICE Lite non deve inviare richieste di controllo della connettività.</span><span class="sxs-lookup"><span data-stu-id="93b26-130">The ICE Lite endpoint must not send any connectivity check requests.</span></span> <span data-ttu-id="93b26-131">Se i controlli di connettività vengono inviati in violazione, verrà restituita l'implementazione completa, che può causare la scoperta di candidati derivati da peer imprevisti e potenzialmente causare errori di chiamata.</span><span class="sxs-lookup"><span data-stu-id="93b26-131">(If connectivity checks are sent in violation, the full implementation will respond, which can result in unexpected peer-derived candidates being discovered and potentially result in call failures.)</span></span>

#### <a name="nominations"></a><span data-ttu-id="93b26-132">Nomination</span><span class="sxs-lookup"><span data-stu-id="93b26-132">Nominations</span></span>

<span data-ttu-id="93b26-133">L'endpoint di implementazione completa di ICE sarà sempre l'endpoint di controllo e seguirà le nomine "regolari" per selezionare i candidati finali da usare per il flusso multimediale.</span><span class="sxs-lookup"><span data-stu-id="93b26-133">The ICE full implementation endpoint will always be the Controlling endpoint, and will follow “Regular” nominations for selecting the final candidates to be used for media flow.</span></span> <span data-ttu-id="93b26-134">L'endpoint ICE Lite può usare le nomine per concludere il percorso da usare per il supporto e per completare la creazione di chiamate.</span><span class="sxs-lookup"><span data-stu-id="93b26-134">The ICE Lite endpoint can use the nominations to conclude the path to be used for media and complete call establishment.</span></span>

<span data-ttu-id="93b26-135">Nota: nel caso di forking con endpoint peer che inviano risposte provvisorie di 183, il SBC deve essere pronto per rispondere ai controlli da più endpoint e anche alle nomine di più endpoint se le nomine si verificano prima di 200OK.</span><span class="sxs-lookup"><span data-stu-id="93b26-135">Note: In the case of forking with peer endpoints sending 183 provisional answers, the SBC must be ready to respond to checks from multiple endpoints and also nominations from multiple endpoints if the nominations happen before 200OK.</span></span> <span data-ttu-id="93b26-136">A seconda della convergenza della macchina a stati di ghiaccio sul percorso finale e la tempistica della risposta degli utenti, le nomine possono succedere prima o dopo 200OK.</span><span class="sxs-lookup"><span data-stu-id="93b26-136">Depending on the convergence of the ICE state machine on the final path and timing of the user answering, the nominations can happen before or after 200OK.</span></span> <span data-ttu-id="93b26-137">Il controllo SBC deve essere in grado di gestire entrambi i casi.</span><span class="sxs-lookup"><span data-stu-id="93b26-137">The SBC must be able to handle both cases.</span></span>

#### <a name="converging-for-forking"></a><span data-ttu-id="93b26-138">Convergenza per la diramazione</span><span class="sxs-lookup"><span data-stu-id="93b26-138">Converging for forking</span></span>

<span data-ttu-id="93b26-139">Se l'offerta proveniente da SBC si biforca a più endpoint di Team, gli endpoint di teams potrebbero rispondere con una risposta provvisoria e avviare i controlli di connettività.</span><span class="sxs-lookup"><span data-stu-id="93b26-139">If the offer from the SBC forks to multiple Teams endpoints, the Teams endpoints may respond with a provisional answer and start connectivity checks.</span></span> <span data-ttu-id="93b26-140">SBC deve essere pronto per ricevere i controlli di connettività e rispondere ai controlli di connettività da più endpoint peer.</span><span class="sxs-lookup"><span data-stu-id="93b26-140">The SBC must be prepared to receive connectivity checks and respond to connectivity checks from multiple peer endpoints.</span></span> <span data-ttu-id="93b26-141">Ad esempio, l'utente di teams può essere connesso sia a un desktop che a un telefono cellulare.</span><span class="sxs-lookup"><span data-stu-id="93b26-141">For example, the Teams user could be signed on to both a desktop and a cell phone.</span></span> <span data-ttu-id="93b26-142">Entrambi i dispositivi riceveranno una notifica della chiamata in ingresso e tenteranno i controlli di connettività con SBC.</span><span class="sxs-lookup"><span data-stu-id="93b26-142">Both devices will be notified of the inbound call and will attempt connectivity checks with the SBC.</span></span>

<span data-ttu-id="93b26-143">Alla fine solo uno degli endpoint risponderà alla chiamata (200OK).</span><span class="sxs-lookup"><span data-stu-id="93b26-143">Eventually only one of the endpoints will answer the call (200OK).</span></span> <span data-ttu-id="93b26-144">Quando si riceve il 200OK, il SBC può configurare il contesto appropriato per l'elaborazione dei pacchetti multimediali.</span><span class="sxs-lookup"><span data-stu-id="93b26-144">On receiving the 200OK, the SBC can set up the right context for processing the media packets.</span></span>

## <a name="scenarios"></a><span data-ttu-id="93b26-145">Scenari</span><span class="sxs-lookup"><span data-stu-id="93b26-145">Scenarios</span></span>

###  <a name="inbound-call-from-sbc"></a><span data-ttu-id="93b26-146">Chiamata in ingresso da SBC</span><span class="sxs-lookup"><span data-stu-id="93b26-146">Inbound call from SBC</span></span>

<span data-ttu-id="93b26-147">Per questo scenario, esistono diversi endpoint peer possibili che devono essere gestiti da SBC:</span><span class="sxs-lookup"><span data-stu-id="93b26-147">For this scenario, there are several possible peer endpoints that the SBC must handle:</span></span>

- <span data-ttu-id="93b26-148">Gli endpoint del server in genere rispondono direttamente a 200OK.</span><span class="sxs-lookup"><span data-stu-id="93b26-148">Server endpoints will typically respond directly with 200OK.</span></span> <span data-ttu-id="93b26-149">Si tratta di endpoint Full ICE che in genere sono coinvolti in messaggi vocali, in coda di chiamata e in scenari di operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="93b26-149">These are full ICE endpoints that are typically involved in Voicemail, Call queue, and Auto attendant scenarios.</span></span>

- <span data-ttu-id="93b26-150">Gli endpoint client possono inviare più risposte provvisorie con diversi tag from/to (183) seguiti da un 200OK dall'endpoint che risponde alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="93b26-150">Client endpoints can send multiple provisional answers with different From/To tags (183) followed by a 200OK from the endpoint that answers the call.</span></span> <span data-ttu-id="93b26-151">Si tratta di endpoint Full ICE che rappresentano in genere i client degli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="93b26-151">These are full ICE endpoints typically representing end user clients.</span></span>

- <span data-ttu-id="93b26-152">Altri endpoint SBC.</span><span class="sxs-lookup"><span data-stu-id="93b26-152">Other SBC endpoints.</span></span> <span data-ttu-id="93b26-153">Si tratta di endpoint ICE Lite in genere coinvolti nello scenario di squillo simultaneo di endpoint client e di un altro numero di telefono (s).</span><span class="sxs-lookup"><span data-stu-id="93b26-153">These are ICE Lite endpoints typically involved in the scenario of simultaneously ringing client endpoints and another phone number(s).</span></span>

<span data-ttu-id="93b26-154">SBC deve rispondere a tutte le richieste di controllo della connettività valide ricevute dagli endpoint Full ICE.</span><span class="sxs-lookup"><span data-stu-id="93b26-154">The SBC must respond to all valid connectivity check requests received from the full ICE endpoints.</span></span> <span data-ttu-id="93b26-155">Per RFC, gli endpoint ICE completi diventeranno il controllo degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="93b26-155">Per RFC, the full ICE endpoints will become Controlling endpoints.</span></span> <span data-ttu-id="93b26-156">Gli endpoint Teams (client/server) eseguiranno le nomine "regolari" per completare i controlli di connettività.</span><span class="sxs-lookup"><span data-stu-id="93b26-156">The Teams (client/server) endpoints will perform “Regular” nominations to complete connectivity checks.</span></span> <span data-ttu-id="93b26-157">Il 200Ok finale può essere proveniente da un endpoint che ha inviato elementi multimediali iniziali o da un endpoint diverso.</span><span class="sxs-lookup"><span data-stu-id="93b26-157">The final 200Ok can either be from an endpoint that sent early media or from a different endpoint.</span></span> <span data-ttu-id="93b26-158">Quando si riceve il 200Ok, il SBC deve configurare il contesto giusto per il flusso multimediale.</span><span class="sxs-lookup"><span data-stu-id="93b26-158">On receiving the 200Ok, the SBC must set up the right context for media flow.</span></span> 

###  <a name="early-media"></a><span data-ttu-id="93b26-159">Elementi multimediali iniziali</span><span class="sxs-lookup"><span data-stu-id="93b26-159">Early media</span></span>

<span data-ttu-id="93b26-160">Se è presente un flusso multimediale iniziale, il controllo SBC deve essere bloccato sul primo endpoint che avvia il flusso multimediale; il flusso multimediale può iniziare prima che i candidati vengano nominati.</span><span class="sxs-lookup"><span data-stu-id="93b26-160">If there is early media flow, the SBC must latch to the first endpoint that starts streaming media; media flow can start before candidates are nominated.</span></span> <span data-ttu-id="93b26-161">SBC dovrebbe avere il supporto per l'invio di DTMF durante questa fase per abilitare gli scenari IVR/Voicemail.</span><span class="sxs-lookup"><span data-stu-id="93b26-161">The SBC should have support for sending DTMF during this phase to enable IVR/voicemail scenarios.</span></span> <span data-ttu-id="93b26-162">L'SBC deve usare il percorso con priorità più alta in cui ha ricevuto i controlli se le nomine non sono state completate.</span><span class="sxs-lookup"><span data-stu-id="93b26-162">The SBC should use the highest priority path on which it has received checks if nominations have not completed.</span></span>

### <a name="outbound-call-to-sbc"></a><span data-ttu-id="93b26-163">Chiamata in uscita a SBC</span><span class="sxs-lookup"><span data-stu-id="93b26-163">Outbound call to SBC</span></span>

<span data-ttu-id="93b26-164">Gli endpoint di teams sono il chiamante per questo scenario e saranno l'endpoint di controllo.</span><span class="sxs-lookup"><span data-stu-id="93b26-164">The Teams endpoints are the Caller for this scenario and will be the Controlling Endpoint.</span></span> <span data-ttu-id="93b26-165">Quando si riceve una risposta provvisoria (183) o una risposta finale (200OK), l'endpoint di teams avvierà i controlli di connettività e procederà con le nomine "regolari" per completare i controlli di connettività.</span><span class="sxs-lookup"><span data-stu-id="93b26-165">On receiving either a provisional answer (183) or a final answer(200OK), the Teams endpoint  will start connectivity checks and proceed to “Regular” nominations to complete the connectivity checks.</span></span>

<span data-ttu-id="93b26-166">Nota: se il SBC invia una risposta provvisoria (183), il SBC deve essere pronto per ricevere le richieste di controllo della connettività e completare potenzialmente le nomine prima che il 200OK venga inviato dall'SBC.</span><span class="sxs-lookup"><span data-stu-id="93b26-166">Note: If the SBC sends a provisional answer (183), the SBC must be ready to receive connectivity check requests and potentially complete the nominations  before the 200OK is sent by the SBC.</span></span> <span data-ttu-id="93b26-167">Se i controlli e/o le nomine vengono completati prima della ricezione di 200OK, i controlli e/o le nomine non verranno eseguiti dopo la ricezione di 200OK.</span><span class="sxs-lookup"><span data-stu-id="93b26-167">If checks and/or nominations are completed before the 200OK is received, checks and/or nominations will not be performed again after 200OK is received.</span></span> <span data-ttu-id="93b26-168">Il SBC non deve cambiare i candidati ICE, la password e ufrag (frammento di nome utente) tra 183 e 200.</span><span class="sxs-lookup"><span data-stu-id="93b26-168">The SBC must not change ICE candidates, password, and ufrag (username fragment) between 183 and 200.</span></span>

<span data-ttu-id="93b26-169">Per supportare i primi elementi multimediali, il SBC può iniziare a trasmettere il contenuto multimediale al candidato ICE peer, con la massima priorità in base ai controlli di connettività ricevuti, anche prima che le nomine vengano completate dall'endpoint teams.</span><span class="sxs-lookup"><span data-stu-id="93b26-169">To support early media, the SBC may start streaming the media to the peer ICE candidate, with the highest priority based on received connectivity checks, even before nominations are completed by Teams endpoint.</span></span> <span data-ttu-id="93b26-170">Il SBC dovrebbe aspettarsi che il supporto di teams su qualsiasi candidato fino al completamento delle nomine.</span><span class="sxs-lookup"><span data-stu-id="93b26-170">The SBC should expect media from Teams on any candidate until nominations are completed.</span></span> <span data-ttu-id="93b26-171">Una volta nominato un candidato, il SBC deve reimpostare il contesto giusto per inviare e ricevere pacchetti multimediali.</span><span class="sxs-lookup"><span data-stu-id="93b26-171">Once a candidate is nominated, the SBC must reset to the right context to send and receive media packets.</span></span>

## <a name="srtp-support-requirements"></a><span data-ttu-id="93b26-172">Requisiti di supporto per SRTP</span><span class="sxs-lookup"><span data-stu-id="93b26-172">SRTP support requirements</span></span>

<span data-ttu-id="93b26-173">Il servizio SBC deve supportare le AES_CM_128_HMAC_SHA1_80 crittografiche di crittografia SRTP per offrire e rispondere con il formato seguente:</span><span class="sxs-lookup"><span data-stu-id="93b26-173">The SBC must support SRTP encryption cipher AES_CM_128_HMAC_SHA1_80 for offer and answer in the following format:</span></span>

```
"inline:" <key||salt> ["|" lifetime]
```

<span data-ttu-id="93b26-174">Di seguito è riportato un esempio di attributo Crypto nell'offerta SDP da SBC:</span><span class="sxs-lookup"><span data-stu-id="93b26-174">The following is an example of the crypto attribute in the SDP offer from the SBC:</span></span>

```
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

<span data-ttu-id="93b26-175">I parametri MKI e length non sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="93b26-175">MKI and Length parameters are not required.</span></span>

<span data-ttu-id="93b26-176">Per altre informazioni, vedere [RFC 4568, sezione 6,1](https://tools.ietf.org/html/rfc4568#section-6.1).</span><span class="sxs-lookup"><span data-stu-id="93b26-176">For more information, see [RFC 4568, section 6.1](https://tools.ietf.org/html/rfc4568#section-6.1).</span></span>

## <a name="sdes-support-requirements"></a><span data-ttu-id="93b26-177">Requisiti di supporto per SDES</span><span class="sxs-lookup"><span data-stu-id="93b26-177">SDES support requirements</span></span>

<span data-ttu-id="93b26-178">Il dispositivo deve essere in grado di offrire SDES nel formato come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="93b26-178">The device must be able to offer SDES in the format as described below.</span></span> <span data-ttu-id="93b26-179">I processori Microsoft Media preferiscono sempre SDES.</span><span class="sxs-lookup"><span data-stu-id="93b26-179">Microsoft Media Processors always prefer SDES.</span></span>

- <span data-ttu-id="93b26-180">Con il bypass non multimediale, anche se un client supporta solo DTLS, i processori multimediali verranno convertiti in SDES.</span><span class="sxs-lookup"><span data-stu-id="93b26-180">With non-media bypass, even if a client only supports DTLS, the Media Processors will convert to SDES.</span></span>

- <span data-ttu-id="93b26-181">Con il bypass multimediale, se un client è solo DTLS (futuro stato di Google Chrome), il routing diretto inserirà un MP nel percorso, convertendo la chiamata da un bypass multimediale a un bypass non multimediale.</span><span class="sxs-lookup"><span data-stu-id="93b26-181">With media bypass, if a client is DTLS only (future Google Chrome state), Direct Routing will insert an MP in the path, converting the call from media bypass to non-media bypass.</span></span> <span data-ttu-id="93b26-182">Tra il componente SBC e il processore multimediale di routing diretto, SDES viene sempre usato.</span><span class="sxs-lookup"><span data-stu-id="93b26-182">Between the SBC and media processor component of Direct Routing, SDES is always used.</span></span>

<span data-ttu-id="93b26-183">Attualmente, non ci sono client di team che offrono solo DTLS; Tuttavia, Google ha annunciato che ad un certo punto nel tempo smetterà di supportare SDES.</span><span class="sxs-lookup"><span data-stu-id="93b26-183">Currently, there are no Teams client that offer only DTLS; however Google has announced that at some point in time they will stop supporting SDES.</span></span>

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a><span data-ttu-id="93b26-184">Formato per l'offerta da SBC in modalità bypass</span><span class="sxs-lookup"><span data-stu-id="93b26-184">Format for offer from SBC in bypass mode</span></span> 

<span data-ttu-id="93b26-185">L'offerta deve contenere SDES e può contenere DTLS facoltativa con il formato seguente:</span><span class="sxs-lookup"><span data-stu-id="93b26-185">Offer must contain SDES and can contain DTLS optional in the following format:</span></span>

```
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a><span data-ttu-id="93b26-186">Formato per la risposta contenente SDES a SBC</span><span class="sxs-lookup"><span data-stu-id="93b26-186">Format for answer containing SDES to SBC</span></span>

```
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a><span data-ttu-id="93b26-187">Formato per l'offerta da Teams a SBC</span><span class="sxs-lookup"><span data-stu-id="93b26-187">Format for offer from Teams to SBC</span></span> 

### <a name="format-for-sdes-only-offer-to-sbc"></a><span data-ttu-id="93b26-188">Formato per SDES offerta solo per SBC</span><span class="sxs-lookup"><span data-stu-id="93b26-188">Format for SDES only offer to SBC</span></span>

```
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```


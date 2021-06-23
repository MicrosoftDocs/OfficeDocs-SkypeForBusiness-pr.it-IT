---
title: Pianificare il bypass multimediale con Instradamento diretto
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Informazioni su come pianificare il bypass multimediale con Sistema telefonico Direct Routing, che consente di abbreviare il percorso del traffico multimediale e migliorare le prestazioni.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8d60513dbcf1128d303102f494600a67335b366d
ms.sourcegitcommit: cae94cd5761baafde51aea1137e6d164722eead9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2021
ms.locfileid: "53075399"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="4ee96-103">Pianificare il bypass multimediale con Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="4ee96-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="4ee96-104">Informazioni sul bypass multimediale con Routing diretto</span><span class="sxs-lookup"><span data-stu-id="4ee96-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="4ee96-105">Il bypass multimediale consente di abbreviare il percorso del traffico multimediale e ridurre il numero di hop in transito per migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="4ee96-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="4ee96-106">Con il bypass multimediale, i contenuti multimediali vengono mantenuti tra session border controller (SBC) e il client invece di inviarlo tramite Telefono Microsoft System.</span><span class="sxs-lookup"><span data-stu-id="4ee96-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="4ee96-107">Per configurare il bypass multimediale, SBC e il client devono essere nella stessa posizione o rete.</span><span class="sxs-lookup"><span data-stu-id="4ee96-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="4ee96-108">È possibile controllare il bypass multimediale per ogni SBC usando il **comando Set-CSOnlinePSTNGateway** con il **parametro -MediaBypass** impostato su true o false.</span><span class="sxs-lookup"><span data-stu-id="4ee96-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="4ee96-109">Se si abilita il bypass multimediale, questo non significa che tutto il traffico multimediale rimarrà all'interno della rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="4ee96-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="4ee96-110">Questo articolo descrive il flusso delle chiamate in scenari diversi.</span><span class="sxs-lookup"><span data-stu-id="4ee96-110">This article describes the call flow in different scenarios.</span></span>

<span data-ttu-id="4ee96-111">I diagrammi seguenti illustrano la differenza nel flusso delle chiamate con e senza bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="4ee96-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="4ee96-112">Senza bypass multimediale, quando un client effettua o riceve una chiamata, sia la segnalazione che il flusso multimediale tra SBC, Telefono Microsoft System e il client Teams, come illustrato nel diagramma seguente:</span><span class="sxs-lookup"><span data-stu-id="4ee96-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4ee96-113">![Mostra la segnalazione e il flusso multimediale senza bypass multimediale](media/direct-routing-media-bypass-1.png)</span><span class="sxs-lookup"><span data-stu-id="4ee96-113">![Shows signaling and media flow without media bypass](media/direct-routing-media-bypass-1.png)</span></span>


<span data-ttu-id="4ee96-114">Si supponga però che un utente si trova nello stesso edificio o nella stessa rete di SBC.</span><span class="sxs-lookup"><span data-stu-id="4ee96-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="4ee96-115">Si supponga ad esempio che un utente che si trova in un edificio di Francoforte esempli una chiamata a un utente PSTN:</span><span class="sxs-lookup"><span data-stu-id="4ee96-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="4ee96-116">**Senza bypass multimediale,** i supporti multimediali fluiranno tramite Amsterdam o Dublino (dove sono distribuiti i data center Microsoft) e di nuovo alla SBC di Francoforte.</span><span class="sxs-lookup"><span data-stu-id="4ee96-116">**Without media bypass**, media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="4ee96-117">Il data center in Europa è selezionato perché il database SBC è in Europa e Microsoft usa il data center più vicino a SBC.</span><span class="sxs-lookup"><span data-stu-id="4ee96-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="4ee96-118">Anche se questo approccio non influisce sulla qualità delle chiamate a causa dell'ottimizzazione del flusso di traffico all'interno delle reti Microsoft nella maggior parte delle aree geografiche, il traffico ha un ciclo non necessario.</span><span class="sxs-lookup"><span data-stu-id="4ee96-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="4ee96-119">**Con il bypass multimediale,** i supporti multimediali vengono mantenuti direttamente tra l'Teams utente e SBC, come illustrato nel diagramma seguente:</span><span class="sxs-lookup"><span data-stu-id="4ee96-119">**With media bypass**, the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="4ee96-120">![Mostra la segnalazione e il flusso multimediale con bypass multimediale](media/direct-routing-media-bypass-2.png)</span><span class="sxs-lookup"><span data-stu-id="4ee96-120">![Shows signaling and media flow with media bypass](media/direct-routing-media-bypass-2.png)</span></span>

<span data-ttu-id="4ee96-121">Il bypass multimediale usa protocolli chiamati Interactive Connectivity Establishment (ICE) nel client Teams e ICE lite sul SBC.</span><span class="sxs-lookup"><span data-stu-id="4ee96-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE lite on the SBC.</span></span> <span data-ttu-id="4ee96-122">Questi protocolli consentono al routing diretto di usare il percorso multimediale più diretto per una qualità ottimale.</span><span class="sxs-lookup"><span data-stu-id="4ee96-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="4ee96-123">ICE e ICE Lite sono standard WebRTC.</span><span class="sxs-lookup"><span data-stu-id="4ee96-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="4ee96-124">Per informazioni dettagliate su questi protocolli, vedere RFC 5245.</span><span class="sxs-lookup"><span data-stu-id="4ee96-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="4ee96-125">Pianificazione del flusso delle chiamate e del firewall</span><span class="sxs-lookup"><span data-stu-id="4ee96-125">Call flow and firewall planning</span></span>

<span data-ttu-id="4ee96-126">La pianificazione del flusso delle chiamate e del firewall dipende dal fatto che l'utente abbia accesso diretto all'indirizzo IP pubblico dell'SBC e se l'utente si trova all'interno o all'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="4ee96-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="4ee96-127">Flusso delle chiamate se l'utente ha accesso diretto all'indirizzo IP pubblico dell'SBC</span><span class="sxs-lookup"><span data-stu-id="4ee96-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="4ee96-128">Se l'utente ha accesso diretto all'indirizzo IP pubblico del SBC, il flusso di chiamata è il seguente:</span><span class="sxs-lookup"><span data-stu-id="4ee96-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="4ee96-129">Per il bypass multimediale, il client Teams deve avere accesso all'indirizzo IP pubblico della SBC anche da una rete interna.</span><span class="sxs-lookup"><span data-stu-id="4ee96-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="4ee96-130">Se non si desidera supporti diretti, i supporti multimediali possono fluire tramite i relè di trasporto.</span><span class="sxs-lookup"><span data-stu-id="4ee96-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="4ee96-131">Questa è la soluzione consigliata quando un utente si trova nello stesso edificio e/o rete di SBC, rimuovendo i componenti Microsoft Cloud dal percorso multimediale.</span><span class="sxs-lookup"><span data-stu-id="4ee96-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="4ee96-132">La segnalazione fluisce sempre tramite il cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4ee96-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="4ee96-133">Il diagramma seguente mostra il flusso delle chiamate quando è abilitato il bypass multimediale, il client è interno e il client può raggiungere l'indirizzo IP pubblico del SBC (supporto diretto):</span><span class="sxs-lookup"><span data-stu-id="4ee96-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="4ee96-134">Le frecce e i valori numerici dei percorsi sono conformi ai flussi Microsoft Teams [chiamate.](./microsoft-teams-online-call-flows.md)</span><span class="sxs-lookup"><span data-stu-id="4ee96-134">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md).</span></span>

- <span data-ttu-id="4ee96-135">La segnalazione SIP accetta sempre i percorsi 4 e 4' (a seconda della direzione del traffico).</span><span class="sxs-lookup"><span data-stu-id="4ee96-135">The SIP signaling always takes paths 4 and 4' (depending on the direction of the traffic).</span></span> <span data-ttu-id="4ee96-136">Il supporto rimane locale e prende il percorso 5b.</span><span class="sxs-lookup"><span data-stu-id="4ee96-136">Media stays local and takes path 5b.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4ee96-137">![Mostra il flusso delle chiamate con Bypass multimediale abilitato, il client è interno](media/direct-routing-media-bypass-3.png)</span><span class="sxs-lookup"><span data-stu-id="4ee96-137">![Shows Call flow with Media Bypass enabled, client is internal](media/direct-routing-media-bypass-3.png)</span></span>


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="4ee96-138">Flusso delle chiamate se l'utente non ha accesso all'indirizzo IP pubblico dell'SBC</span><span class="sxs-lookup"><span data-stu-id="4ee96-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="4ee96-139">Di seguito viene descritto il flusso delle chiamate se l'utente non ha accesso all'indirizzo IP pubblico del servizio SBC.</span><span class="sxs-lookup"><span data-stu-id="4ee96-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="4ee96-140">Si supponga ad esempio che l'utente sia esterno e che l'amministratore del tenant abbia deciso di non aprire l'indirizzo IP pubblico della SBC a tutti gli utenti di Internet, ma solo a Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="4ee96-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="4ee96-141">I componenti interni del traffico possono fluire tramite Teams di trasporto.</span><span class="sxs-lookup"><span data-stu-id="4ee96-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="4ee96-142">Tenere in considerazione gli aspetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4ee96-142">Consider the following:</span></span>

- <span data-ttu-id="4ee96-143">Teams Vengono usati i relè di trasporto.</span><span class="sxs-lookup"><span data-stu-id="4ee96-143">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="4ee96-144">Per il bypass multimediale, Microsoft usa una versione di Transport Relays che richiede l'apertura delle porte da 50 000 a 59 999 tra i Teams Transport Relays e SBC (in futuro si prevede di passare alla versione che richiede 3478-3481 porte).</span><span class="sxs-lookup"><span data-stu-id="4ee96-144">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires 3478-3481 ports).</span></span>


<span data-ttu-id="4ee96-145">Il diagramma seguente mostra il flusso delle chiamate quando è abilitato il bypass multimediale, il client è esterno e il client non riesce a raggiungere l'indirizzo IP pubblico del Session Border Controller (i supporti vengono inoltrati da Teams Transport Relay).</span><span class="sxs-lookup"><span data-stu-id="4ee96-145">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="4ee96-146">Le frecce e i valori numerici dei percorsi sono conformi ai flussi Microsoft Teams [chiamate.](./microsoft-teams-online-call-flows.md)</span><span class="sxs-lookup"><span data-stu-id="4ee96-146">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md).</span></span>

- <span data-ttu-id="4ee96-147">I file multimediali vengono inoltrati tramite i percorsi 3, 3', 4 e 4'</span><span class="sxs-lookup"><span data-stu-id="4ee96-147">Media is relayed via paths 3, 3', 4 and 4'</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4ee96-148">![Mostra il flusso delle chiamate se l'utente non ha accesso all'IP pubblico dell'SBC](media/direct-routing-media-bypass-4.png)</span><span class="sxs-lookup"><span data-stu-id="4ee96-148">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-4.png)</span></span>


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="4ee96-149">Flusso delle chiamate se un utente si trova all'esterno della rete e ha accesso all'IP pubblico dell'SBC</span><span class="sxs-lookup"><span data-stu-id="4ee96-149">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="4ee96-150">Questa configurazione non è consigliata perché non sfrutta i Teams di trasporto.</span><span class="sxs-lookup"><span data-stu-id="4ee96-150">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="4ee96-151">È invece consigliabile considerare lo scenario precedente in cui l'utente non ha accesso all'indirizzo IP pubblico dell'SBC.</span><span class="sxs-lookup"><span data-stu-id="4ee96-151">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="4ee96-152">Il diagramma seguente mostra il flusso delle chiamate quando è abilitato il bypass multimediale, il client è esterno e il client può raggiungere l'indirizzo IP pubblico del SBC (supporto diretto).</span><span class="sxs-lookup"><span data-stu-id="4ee96-152">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="4ee96-153">Le frecce e i valori numerici dei percorsi sono conformi all'articolo Microsoft Teams [dei flussi di](./microsoft-teams-online-call-flows.md) chiamata.</span><span class="sxs-lookup"><span data-stu-id="4ee96-153">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md) article.</span></span>

- <span data-ttu-id="4ee96-154">La segnalazione SIP accetta sempre i percorsi 3 e 3' (a seconda della direzione del traffico).</span><span class="sxs-lookup"><span data-stu-id="4ee96-154">The SIP signaling always takes paths 3 and 3' (depending on the direction of the traffic).</span></span> <span data-ttu-id="4ee96-155">Flussi multimediali usando il percorso 2.</span><span class="sxs-lookup"><span data-stu-id="4ee96-155">Media flows using path 2.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4ee96-156">![Mostra il flusso delle chiamate se l'utente non ha accesso all'IP pubblico dell'SBC](media/direct-routing-media-bypass-5.png)</span><span class="sxs-lookup"><span data-stu-id="4ee96-156">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-5.png)</span></span>


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="4ee96-157">Uso di processori multimediali e relay di trasporto</span><span class="sxs-lookup"><span data-stu-id="4ee96-157">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="4ee96-158">In Microsoft Cloud sono disponibili due componenti che possono essere nel percorso del traffico multimediale: Processori multimediali e Relay di trasporto.</span><span class="sxs-lookup"><span data-stu-id="4ee96-158">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="4ee96-159">Il Processore multimediale è un componente pubblico che gestisce i supporti multimediali in casi non di bypass e gestisce gli elementi multimediali per le applicazioni vocali.</span><span class="sxs-lookup"><span data-stu-id="4ee96-159">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="4ee96-160">I processori multimediali sono sempre nel percorso per le chiamate non bypassate dell'utente finale, ma mai nel percorso per le chiamate ignorate.</span><span class="sxs-lookup"><span data-stu-id="4ee96-160">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="4ee96-161">I processori multimediali sono sempre nel percorso per tutte le applicazioni vocali, ad esempio Call Park, Organizational Operatore automatico e Call Queues.</span><span class="sxs-lookup"><span data-stu-id="4ee96-161">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="4ee96-162">L'inoltro di trasporto viene usato per connettersi al servizio di trasporto più vicino per inviare traffico in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="4ee96-162">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="4ee96-163">Gli inoltri di trasporto potrebbero essere o meno nel percorso per le chiamate ignorate, originate o destinate agli utenti finali, a seconda della posizione dell'utente e della configurazione della rete.</span><span class="sxs-lookup"><span data-stu-id="4ee96-163">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="4ee96-164">Il diagramma seguente mostra due flussi di chiamata: uno con il bypass multimediale abilitato e il secondo con bypass multimediale disabilitato.</span><span class="sxs-lookup"><span data-stu-id="4ee96-164">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span>

> [!NOTE]
> <span data-ttu-id="4ee96-165">Il diagramma illustra solo il traffico proveniente da utenti finali o destinati a utenti finali.</span><span class="sxs-lookup"><span data-stu-id="4ee96-165">The diagram only illustrates traffic originating from--or destined to--end users.</span></span>  

- <span data-ttu-id="4ee96-166">Il Controller multimediale è un microservizio in Azure che assegna processori multimediali e crea offerte SDP (Session Description Protocol).</span><span class="sxs-lookup"><span data-stu-id="4ee96-166">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="4ee96-167">Il proxy SIP è un componente che converte la segnalazione REST HTTP usata Teams in SIP.</span><span class="sxs-lookup"><span data-stu-id="4ee96-167">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4ee96-168">![Mostra i flussi delle chiamate con Bypass multimediale abilitato e disabilitato](media/direct-routing-media-bypass-6.png)</span><span class="sxs-lookup"><span data-stu-id="4ee96-168">![Shows call flows with Media Bypass enabled and disabled](media/direct-routing-media-bypass-6.png)</span></span>


<span data-ttu-id="4ee96-169">La tabella seguente riepiloga la differenza tra processori multimediali e relay di trasporto.</span><span class="sxs-lookup"><span data-stu-id="4ee96-169">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="4ee96-170">Processori multimediali</span><span class="sxs-lookup"><span data-stu-id="4ee96-170">Media Processors</span></span> | <span data-ttu-id="4ee96-171">Relè di trasporto</span><span class="sxs-lookup"><span data-stu-id="4ee96-171">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="4ee96-172">Percorso multimediale per le chiamate non bypassate per gli utenti finali</span><span class="sxs-lookup"><span data-stu-id="4ee96-172">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="4ee96-173">Sempre</span><span class="sxs-lookup"><span data-stu-id="4ee96-173">Always</span></span> | <span data-ttu-id="4ee96-174">Se il client non riesce a raggiungere direttamente il Processore multimediale</span><span class="sxs-lookup"><span data-stu-id="4ee96-174">If client cannot reach the Media Processor directly</span></span> | 
<span data-ttu-id="4ee96-175">Percorso multimediale per le chiamate ignorate per gli utenti finali</span><span class="sxs-lookup"><span data-stu-id="4ee96-175">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="4ee96-176">Mai</span><span class="sxs-lookup"><span data-stu-id="4ee96-176">Never</span></span> | <span data-ttu-id="4ee96-177">Se il client non riesce a raggiungere SBC nell'indirizzo IP pubblico</span><span class="sxs-lookup"><span data-stu-id="4ee96-177">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="4ee96-178">Percorso multimediale per le applicazioni vocali</span><span class="sxs-lookup"><span data-stu-id="4ee96-178">In media path for voice applications</span></span> | <span data-ttu-id="4ee96-179">Sempre</span><span class="sxs-lookup"><span data-stu-id="4ee96-179">Always</span></span> | <span data-ttu-id="4ee96-180">Mai</span><span class="sxs-lookup"><span data-stu-id="4ee96-180">Never</span></span> | 
<span data-ttu-id="4ee96-181">Può eseguire la trascodtura (B2BUA)\*</span><span class="sxs-lookup"><span data-stu-id="4ee96-181">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="4ee96-182">Sì</span><span class="sxs-lookup"><span data-stu-id="4ee96-182">Yes</span></span> | <span data-ttu-id="4ee96-183">No, solo l'inoltro audio tra endpoint</span><span class="sxs-lookup"><span data-stu-id="4ee96-183">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="4ee96-184">Numero di istanze in tutto il mondo e località</span><span class="sxs-lookup"><span data-stu-id="4ee96-184">Number of instances worldwide and location</span></span> | <span data-ttu-id="4ee96-185">10 in totale: 2 negli Stati Uniti orientali e occidentali; 2 ad Amsterdam e Dublino; 2 a Hong Kong e Singapore; 2 in Giappone ; 2 in Australia Est e Sudest</span><span class="sxs-lookup"><span data-stu-id="4ee96-185">10 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan ; 2 in Australia East and Southeast</span></span> | <span data-ttu-id="4ee96-186">Multiplo</span><span class="sxs-lookup"><span data-stu-id="4ee96-186">Multiple</span></span>

<span data-ttu-id="4ee96-187">Gli intervalli IP sono:</span><span class="sxs-lookup"><span data-stu-id="4ee96-187">The IP ranges are:</span></span>
- <span data-ttu-id="4ee96-188">52.112.0.0/14 (indirizzi IP da 52.112.0.1 a 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="4ee96-188">52.112.0.0/14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>
- <span data-ttu-id="4ee96-189">52.120.0.0/14 (indirizzi IP da 52.120.0.1 a 52.123.255.254)</span><span class="sxs-lookup"><span data-stu-id="4ee96-189">52.120.0.0/14 (IP addresses from 52.120.0.1 to 52.123.255.254)</span></span>

<span data-ttu-id="4ee96-190">\* Spiegazione trascodico:</span><span class="sxs-lookup"><span data-stu-id="4ee96-190">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="4ee96-191">Processore multimediale è B2BUA, il che significa che può modificare un codec,ad esempio SILK da client Teams a MP e G.711 tra MP e SBC.</span><span class="sxs-lookup"><span data-stu-id="4ee96-191">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="4ee96-192">Gli inoltri di trasporto non sono B2BUA, il che significa che il codec non viene mai modificato tra il client e il SBC, anche se il traffico passa attraverso i relè.</span><span class="sxs-lookup"><span data-stu-id="4ee96-192">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="4ee96-193">Uso di processori Teams multimediali se il trunk è configurato per il bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="4ee96-193">Use of Teams Media Processors if trunk is configured for media bypass</span></span>

<span data-ttu-id="4ee96-194">Teams I processori multimediali vengono sempre inseriti nel percorso multimediale negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="4ee96-194">Teams Media Processors are always inserted in the media path in the following scenarios:</span></span>

- <span data-ttu-id="4ee96-195">La chiamata viene riassegnata dall'1:1 a una chiamata di gruppo</span><span class="sxs-lookup"><span data-stu-id="4ee96-195">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="4ee96-196">Chiamata a un utente Teams federato</span><span class="sxs-lookup"><span data-stu-id="4ee96-196">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="4ee96-197">La chiamata viene inoltrata o trasferita a un Skype for Business utente</span><span class="sxs-lookup"><span data-stu-id="4ee96-197">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="4ee96-198">Verificare che SBC abbia accesso agli intervalli Media Processors e Transport Relays come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="4ee96-198">Ensure your SBC has access to the Media Processors and Transport Relays ranges as described below.</span></span>    


## <a name="sip-signaling-fqdns"></a><span data-ttu-id="4ee96-199">Segnalazione SIP: FQDN</span><span class="sxs-lookup"><span data-stu-id="4ee96-199">SIP Signaling: FQDNs</span></span>

<span data-ttu-id="4ee96-200">Per la segnalazione SIP, i requisiti di FQDN e firewall sono gli stessi dei casi non bypassati.</span><span class="sxs-lookup"><span data-stu-id="4ee96-200">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="4ee96-201">Il routing diretto è disponibile negli ambienti Microsoft 365 o Office 365 seguenti:</span><span class="sxs-lookup"><span data-stu-id="4ee96-201">Direct Routing is offered in the following Microsoft 365 or Office 365 environments:</span></span>
- <span data-ttu-id="4ee96-202">Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="4ee96-202">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="4ee96-203">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="4ee96-203">Office 365 GCC</span></span>
- <span data-ttu-id="4ee96-204">Office 365 GCC alta</span><span class="sxs-lookup"><span data-stu-id="4ee96-204">Office 365 GCC High</span></span>
- <span data-ttu-id="4ee96-205">Office 365 DoD Altre informazioni sugli [ambienti governativi Office 365](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) Stati Uniti, ad esempio GCC, GCC High e DoD.</span><span class="sxs-lookup"><span data-stu-id="4ee96-205">Office 365 DoD Learn more about [Office 365 and US Government environments](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="4ee96-206">Microsoft 365, Office 365 e Office 365 GCC di lavoro</span><span class="sxs-lookup"><span data-stu-id="4ee96-206">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

<span data-ttu-id="4ee96-207">I punti di connessione per il routing diretto sono i tre FQDN seguenti:</span><span class="sxs-lookup"><span data-stu-id="4ee96-207">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="4ee96-208">**sip.pstnhub.microsoft.com,** fqdn globale, deve essere provato prima di tutto.</span><span class="sxs-lookup"><span data-stu-id="4ee96-208">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="4ee96-209">Quando il servizio SBC invia una richiesta di risoluzione del nome, i server DNS Microsoft Azure restituiscono un indirizzo IP che punta al data center primario di Azure assegnato a SBC.</span><span class="sxs-lookup"><span data-stu-id="4ee96-209">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="4ee96-210">L'assegnazione si basa sulle metriche delle prestazioni dei data center e sulla vicinanza geografica al SBC.</span><span class="sxs-lookup"><span data-stu-id="4ee96-210">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="4ee96-211">L'indirizzo IP restituito corrisponde all'FQDN primario.</span><span class="sxs-lookup"><span data-stu-id="4ee96-211">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="4ee96-212">**sip2.pstnhub.microsoft.com** , FQDN secondario, mappato geograficamente alla seconda area di priorità.</span><span class="sxs-lookup"><span data-stu-id="4ee96-212">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="4ee96-213">**sip3.pstnhub.microsoft.com,** fqdn terziario, viene mappato geograficamente alla terza area prioritaria.</span><span class="sxs-lookup"><span data-stu-id="4ee96-213">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="4ee96-214">È necessario inserire questi tre FQDN per:</span><span class="sxs-lookup"><span data-stu-id="4ee96-214">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="4ee96-215">Offrire un'esperienza ottimale, meno caricata e più vicina al data center SBC assegnato tramite query sul primo FQDN.</span><span class="sxs-lookup"><span data-stu-id="4ee96-215">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="4ee96-216">Fornire il failover quando viene stabilita una connessione da un SBC a un data center in cui si verifica un problema temporaneo.</span><span class="sxs-lookup"><span data-stu-id="4ee96-216">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="4ee96-217">Per altre informazioni, vedere Meccanismo di failover più avanti.</span><span class="sxs-lookup"><span data-stu-id="4ee96-217">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="4ee96-218">I nomi FQDN **sip.pstnhub.microsoft.com,** **sip2.pstnhub.microsoft.com** e sip3.pstnhub.microsoft.com  verranno risolti in indirizzi IP dalle subnet seguenti:</span><span class="sxs-lookup"><span data-stu-id="4ee96-218">The FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**, and **sip3.pstnhub.microsoft.com** will be resolved to IP addresses from the following subnets:</span></span>
- <span data-ttu-id="4ee96-219">52.112.0.0/14</span><span class="sxs-lookup"><span data-stu-id="4ee96-219">52.112.0.0/14</span></span>
- <span data-ttu-id="4ee96-220">52.120.0.0/14</span><span class="sxs-lookup"><span data-stu-id="4ee96-220">52.120.0.0/14</span></span>

<span data-ttu-id="4ee96-221">È necessario aprire le porte per tutti questi intervalli IP nel firewall per consentire il traffico in ingresso e in uscita da e verso gli indirizzi per la segnalazione.</span><span class="sxs-lookup"><span data-stu-id="4ee96-221">You need to open ports for all these IP ranges in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="4ee96-222">Se il firewall supporta i nomi DNS, l'FQDN **sip-all.pstnhub.microsoft.com** viene risolto in tutte queste subnet IP.</span><span class="sxs-lookup"><span data-stu-id="4ee96-222">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all these IP subnets.</span></span> 

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="4ee96-223">Office 365 GCC DoD</span><span class="sxs-lookup"><span data-stu-id="4ee96-223">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="4ee96-224">Il punto di connessione per il routing diretto è il seguente FQDN:</span><span class="sxs-lookup"><span data-stu-id="4ee96-224">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="4ee96-225">**sip.pstnhub.dod.teams.microsoft.us** : FQDN globale.</span><span class="sxs-lookup"><span data-stu-id="4ee96-225">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="4ee96-226">Poiché l'Office 365 DoD esiste solo nei data center degli Stati Uniti, non sono disponibili FQDN secondari e terziari.</span><span class="sxs-lookup"><span data-stu-id="4ee96-226">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="4ee96-227">Il nome fqdn sip.pstnhub.dod.teams.microsoft.us verrà risolto in un indirizzo IP dalla subnet seguente:</span><span class="sxs-lookup"><span data-stu-id="4ee96-227">The FQDN sip.pstnhub.dod.teams.microsoft.us will be resolved to an IP address from the following subnet:</span></span>

- <span data-ttu-id="4ee96-228">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="4ee96-228">52.127.64.0/21</span></span>

<span data-ttu-id="4ee96-229">È necessario aprire le porte per tutti questi intervalli IP nel firewall per consentire il traffico in ingresso e in uscita da e verso gli indirizzi per la segnalazione.</span><span class="sxs-lookup"><span data-stu-id="4ee96-229">You need to open ports for all these IP ranges in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="4ee96-230">Se il firewall supporta i nomi DNS, l'FQDN sip.pstnhub.dod.teams.microsoft.us viene risolto in tutte queste subnet IP.</span><span class="sxs-lookup"><span data-stu-id="4ee96-230">If your firewall supports DNS names, the FQDN  sip.pstnhub.dod.teams.microsoft.us resolves to all these IP subnets.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="4ee96-231">Office 365 GCC ambiente High</span><span class="sxs-lookup"><span data-stu-id="4ee96-231">Office 365 GCC High environment</span></span>

<span data-ttu-id="4ee96-232">Il punto di connessione per il routing diretto è il seguente FQDN:</span><span class="sxs-lookup"><span data-stu-id="4ee96-232">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="4ee96-233">**sip.pstnhub.gov.teams.microsoft.us** : FQDN globale.</span><span class="sxs-lookup"><span data-stu-id="4ee96-233">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="4ee96-234">Poiché l'GCC High è presente solo nei data center degli Stati Uniti, non sono disponibili fqdn secondari e terziari.</span><span class="sxs-lookup"><span data-stu-id="4ee96-234">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="4ee96-235">Il nome fqdn sip.pstnhub.gov.teams.microsoft.us verrà risolto in un indirizzo IP della subnet seguente:</span><span class="sxs-lookup"><span data-stu-id="4ee96-235">The FQDN sip.pstnhub.gov.teams.microsoft.us will be resolved to an IP address from the following subnet:</span></span>

- <span data-ttu-id="4ee96-236">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="4ee96-236">52.127.64.0/21</span></span>

<span data-ttu-id="4ee96-237">È necessario aprire le porte per tutti questi intervalli IP nel firewall per consentire il traffico in ingresso e in uscita da e verso gli indirizzi per la segnalazione.</span><span class="sxs-lookup"><span data-stu-id="4ee96-237">You need to open ports for all these IP ranges in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="4ee96-238">Se il firewall supporta i nomi DNS, l'FQDN sip.pstnhub.gov.teams.microsoft.us viene risolto in tutte queste subnet IP.</span><span class="sxs-lookup"><span data-stu-id="4ee96-238">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP subnets.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="4ee96-239">Segnalazione SIP: Porte</span><span class="sxs-lookup"><span data-stu-id="4ee96-239">SIP Signaling: Ports</span></span>

<span data-ttu-id="4ee96-240">I requisiti di porta sono gli stessi per tutti gli Office 365 in cui è disponibile il routing diretto:</span><span class="sxs-lookup"><span data-stu-id="4ee96-240">Port requirements are the same for all Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="4ee96-241">Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="4ee96-241">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="4ee96-242">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="4ee96-242">Office 365 GCC</span></span>
- <span data-ttu-id="4ee96-243">Office 365 GCC alta</span><span class="sxs-lookup"><span data-stu-id="4ee96-243">Office 365 GCC High</span></span>
- <span data-ttu-id="4ee96-244">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="4ee96-244">Office 365 DoD</span></span>

<span data-ttu-id="4ee96-245">È necessario usare le porte seguenti:</span><span class="sxs-lookup"><span data-stu-id="4ee96-245">You must use the following ports:</span></span>

| <span data-ttu-id="4ee96-246">Traffico</span><span class="sxs-lookup"><span data-stu-id="4ee96-246">Traffic</span></span> | <span data-ttu-id="4ee96-247">Da</span><span class="sxs-lookup"><span data-stu-id="4ee96-247">From</span></span> | <span data-ttu-id="4ee96-248">A</span><span class="sxs-lookup"><span data-stu-id="4ee96-248">To</span></span> | <span data-ttu-id="4ee96-249">Porta di origine</span><span class="sxs-lookup"><span data-stu-id="4ee96-249">Source port</span></span> | <span data-ttu-id="4ee96-250">Porta di destinazione</span><span class="sxs-lookup"><span data-stu-id="4ee96-250">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="4ee96-251">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="4ee96-251">SIP/TLS</span></span>| <span data-ttu-id="4ee96-252">SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="4ee96-252">SIP Proxy</span></span> | <span data-ttu-id="4ee96-253">SBC</span><span class="sxs-lookup"><span data-stu-id="4ee96-253">SBC</span></span> | <span data-ttu-id="4ee96-254">1024 - 65535</span><span class="sxs-lookup"><span data-stu-id="4ee96-254">1024 - 65535</span></span> | <span data-ttu-id="4ee96-255">Definito nell'SBC</span><span class="sxs-lookup"><span data-stu-id="4ee96-255">Defined on the SBC</span></span> |
| <span data-ttu-id="4ee96-256">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="4ee96-256">SIP/TLS</span></span> | <span data-ttu-id="4ee96-257">SBC</span><span class="sxs-lookup"><span data-stu-id="4ee96-257">SBC</span></span> | <span data-ttu-id="4ee96-258">SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="4ee96-258">SIP Proxy</span></span> | <span data-ttu-id="4ee96-259">Definito nell'SBC</span><span class="sxs-lookup"><span data-stu-id="4ee96-259">Defined on the SBC</span></span> | <span data-ttu-id="4ee96-260">5061</span><span class="sxs-lookup"><span data-stu-id="4ee96-260">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="4ee96-261">Traffico multimediale: intervalli ip e porte</span><span class="sxs-lookup"><span data-stu-id="4ee96-261">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="4ee96-262">Il traffico multimediale fluisce tra il client SBC e il client Teams se è disponibile la connettività diretta o tramite gli inoltri di trasporto Teams se il client non riesce a raggiungere SBC usando l'indirizzo IP pubblico.</span><span class="sxs-lookup"><span data-stu-id="4ee96-262">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="4ee96-263">Requisiti per il traffico multimediale diretto (tra Teams client e SBC)</span><span class="sxs-lookup"><span data-stu-id="4ee96-263">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="4ee96-264">Il client deve avere accesso alle porte specificate (vedere la tabella) nell'indirizzo IP pubblico dell'SBC.</span><span class="sxs-lookup"><span data-stu-id="4ee96-264">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

> [!NOTE]
> <span data-ttu-id="4ee96-265">Se il client si trova in una rete interna, il contenuto multimediale passa all'indirizzo IP pubblico del servizio SBC.</span><span class="sxs-lookup"><span data-stu-id="4ee96-265">If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="4ee96-266">È possibile configurare l'aggiunta di capelli nel dispositivo NAT in modo che il traffico non lasci mai l'apparecchiatura di rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="4ee96-266">You can configure hair pinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="4ee96-267">Traffico</span><span class="sxs-lookup"><span data-stu-id="4ee96-267">Traffic</span></span> | <span data-ttu-id="4ee96-268">Da</span><span class="sxs-lookup"><span data-stu-id="4ee96-268">From</span></span> | <span data-ttu-id="4ee96-269">A</span><span class="sxs-lookup"><span data-stu-id="4ee96-269">To</span></span> | <span data-ttu-id="4ee96-270">Porta di origine</span><span class="sxs-lookup"><span data-stu-id="4ee96-270">Source port</span></span> | <span data-ttu-id="4ee96-271">Porta di destinazione</span><span class="sxs-lookup"><span data-stu-id="4ee96-271">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="4ee96-272">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="4ee96-272">UDP/SRTP</span></span> | <span data-ttu-id="4ee96-273">Client</span><span class="sxs-lookup"><span data-stu-id="4ee96-273">Client</span></span> | <span data-ttu-id="4ee96-274">SBC</span><span class="sxs-lookup"><span data-stu-id="4ee96-274">SBC</span></span> | <span data-ttu-id="4ee96-275">3478-3481 e 49152 – 53247</span><span class="sxs-lookup"><span data-stu-id="4ee96-275">3478-3481 and 49152 – 53247</span></span>| <span data-ttu-id="4ee96-276">Definito nell'SBC</span><span class="sxs-lookup"><span data-stu-id="4ee96-276">Defined on the SBC</span></span> |
| <span data-ttu-id="4ee96-277">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="4ee96-277">UDP/SRTP</span></span> | <span data-ttu-id="4ee96-278">SBC</span><span class="sxs-lookup"><span data-stu-id="4ee96-278">SBC</span></span> | <span data-ttu-id="4ee96-279">Client</span><span class="sxs-lookup"><span data-stu-id="4ee96-279">Client</span></span> | <span data-ttu-id="4ee96-280">Definito nell'SBC</span><span class="sxs-lookup"><span data-stu-id="4ee96-280">Defined on the SBC</span></span> | <span data-ttu-id="4ee96-281">3478-3481 e 49152 – 53247</span><span class="sxs-lookup"><span data-stu-id="4ee96-281">3478-3481 and 49152 – 53247</span></span>  |


> [!NOTE]
> <span data-ttu-id="4ee96-282">Se si dispone di un dispositivo di rete che traduce le porte di origine del client, assicurarsi che le porte tradotte siano aperte tra l'apparecchiatura di rete e la SBC.</span><span class="sxs-lookup"><span data-stu-id="4ee96-282">If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="4ee96-283">Requisiti per l'uso degli inoltri di trasporto</span><span class="sxs-lookup"><span data-stu-id="4ee96-283">Requirements for using Transport Relays</span></span>

<span data-ttu-id="4ee96-284">I relè di trasporto sono nello stesso intervallo dei processori multimediali (per i casi non di bypass):</span><span class="sxs-lookup"><span data-stu-id="4ee96-284">Transport Relays are in the same range as Media Processors (for non-bypass cases):</span></span> 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="4ee96-285">Microsoft 365, Office 365 e Office 365 GCC di lavoro</span><span class="sxs-lookup"><span data-stu-id="4ee96-285">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

- <span data-ttu-id="4ee96-286">52.112.0.0 /14 (indirizzi IP da 52.112.0.1 a 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="4ee96-286">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="4ee96-287">Office 365 GCC DoD</span><span class="sxs-lookup"><span data-stu-id="4ee96-287">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="4ee96-288">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="4ee96-288">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="4ee96-289">Office 365 GCC ambiente High</span><span class="sxs-lookup"><span data-stu-id="4ee96-289">Office 365 GCC High environment</span></span>

- <span data-ttu-id="4ee96-290">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="4ee96-290">52.127.88.0/21</span></span>


<span data-ttu-id="4ee96-291">L'intervallo di porte dei Teams di trasporto (applicabile a tutti gli ambienti) è illustrato nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="4ee96-291">The port range of the Teams Transport Relays (applicable to all environments) is shown in the following table:</span></span>


| <span data-ttu-id="4ee96-292">Traffico</span><span class="sxs-lookup"><span data-stu-id="4ee96-292">Traffic</span></span> | <span data-ttu-id="4ee96-293">Da</span><span class="sxs-lookup"><span data-stu-id="4ee96-293">From</span></span> | <span data-ttu-id="4ee96-294">A</span><span class="sxs-lookup"><span data-stu-id="4ee96-294">To</span></span> | <span data-ttu-id="4ee96-295">Porta di origine</span><span class="sxs-lookup"><span data-stu-id="4ee96-295">Source port</span></span> | <span data-ttu-id="4ee96-296">Porta di destinazione</span><span class="sxs-lookup"><span data-stu-id="4ee96-296">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="4ee96-297">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="4ee96-297">UDP/SRTP</span></span> | <span data-ttu-id="4ee96-298">Inoltro di trasporto</span><span class="sxs-lookup"><span data-stu-id="4ee96-298">Transport Relay</span></span> | <span data-ttu-id="4ee96-299">SBC</span><span class="sxs-lookup"><span data-stu-id="4ee96-299">SBC</span></span> | <span data-ttu-id="4ee96-300">50 000 -59 999</span><span class="sxs-lookup"><span data-stu-id="4ee96-300">50 000 -59 999</span></span>    | <span data-ttu-id="4ee96-301">Definito nell'SBC</span><span class="sxs-lookup"><span data-stu-id="4ee96-301">Defined on the SBC</span></span> |
| <span data-ttu-id="4ee96-302">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="4ee96-302">UDP/SRTP</span></span> | <span data-ttu-id="4ee96-303">SBC</span><span class="sxs-lookup"><span data-stu-id="4ee96-303">SBC</span></span> | <span data-ttu-id="4ee96-304">Inoltro di trasporto</span><span class="sxs-lookup"><span data-stu-id="4ee96-304">Transport Relay</span></span> | <span data-ttu-id="4ee96-305">Definito nell'SBC</span><span class="sxs-lookup"><span data-stu-id="4ee96-305">Defined on the SBC</span></span> | <span data-ttu-id="4ee96-306">50 000 – 59 999, 3478-3481</span><span class="sxs-lookup"><span data-stu-id="4ee96-306">50 000 – 59 999, 3478-3481</span></span>     |


> [!NOTE]
> <span data-ttu-id="4ee96-307">Microsoft consiglia almeno due porte per ogni chiamata simultanea su SBC.</span><span class="sxs-lookup"><span data-stu-id="4ee96-307">Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="4ee96-308">Poiché Microsoft ha due versioni di Inoltro di trasporto, sono necessarie le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4ee96-308">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>
> 
> - <span data-ttu-id="4ee96-309">v4, che può funzionare solo con l'intervallo di porte da 50 000 a 59 999</span><span class="sxs-lookup"><span data-stu-id="4ee96-309">v4, which can only work with port range 50 000 to 59 999</span></span>
> 
> - <span data-ttu-id="4ee96-310">v6, che funziona con le porte 3478-3481</span><span class="sxs-lookup"><span data-stu-id="4ee96-310">v6, which works with ports 3478-3481</span></span>

<span data-ttu-id="4ee96-311">Al momento, il bypass multimediale supporta solo la versione v4 di Transport Relays.</span><span class="sxs-lookup"><span data-stu-id="4ee96-311">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="4ee96-312">In futuro verrà introdotto il supporto della versione v6.</span><span class="sxs-lookup"><span data-stu-id="4ee96-312">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="4ee96-313">È necessario aprire le porte 3478-3481 per la transizione.</span><span class="sxs-lookup"><span data-stu-id="4ee96-313">You need to open ports 3478-3481 for transitioning.</span></span> <span data-ttu-id="4ee96-314">Quando Microsoft introduce il supporto per i relay di trasporto v6 con Media Bypass, non sarà necessario riconfigurare le apparecchiature di rete o gli SBC.</span><span class="sxs-lookup"><span data-stu-id="4ee96-314">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="4ee96-315">Requisiti per l'uso di processori multimediali</span><span class="sxs-lookup"><span data-stu-id="4ee96-315">Requirements for using media processors</span></span>

<span data-ttu-id="4ee96-316">I processori multimediali sono sempre nel percorso multimediale per le applicazioni vocali e per i client Web(ad esempio, i client Teams in Edge o Google Chrome).</span><span class="sxs-lookup"><span data-stu-id="4ee96-316">Media Processors are always in the media path for voice applications and for Web clients (for example, Teams clients in Edge or Google Chrome).</span></span> <span data-ttu-id="4ee96-317">I requisiti sono gli stessi per la configurazione non bypass.</span><span class="sxs-lookup"><span data-stu-id="4ee96-317">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="4ee96-318">L'intervallo IP per il traffico multimediale è</span><span class="sxs-lookup"><span data-stu-id="4ee96-318">The IP range for media traffic is</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="4ee96-319">Office 365 e Office 365 GCC di lavoro</span><span class="sxs-lookup"><span data-stu-id="4ee96-319">Office 365 and Office 365 GCC environments</span></span>

- <span data-ttu-id="4ee96-320">52.112.0.0 /14 (indirizzi IP da 52.112.0.1 a 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="4ee96-320">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="4ee96-321">Office 365 GCC DoD</span><span class="sxs-lookup"><span data-stu-id="4ee96-321">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="4ee96-322">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="4ee96-322">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="4ee96-323">Office 365 GCC ambiente High</span><span class="sxs-lookup"><span data-stu-id="4ee96-323">Office 365 GCC High environment</span></span>

- <span data-ttu-id="4ee96-324">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="4ee96-324">52.127.88.0/21</span></span>

<span data-ttu-id="4ee96-325">L'intervallo di porte dei processori multimediali (applicabile a tutti gli ambienti) è illustrato nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="4ee96-325">The port range of the Media Processors (applicable to all environments) is shown in the following table:</span></span>

| <span data-ttu-id="4ee96-326">Traffico</span><span class="sxs-lookup"><span data-stu-id="4ee96-326">Traffic</span></span> | <span data-ttu-id="4ee96-327">Da</span><span class="sxs-lookup"><span data-stu-id="4ee96-327">From</span></span> | <span data-ttu-id="4ee96-328">A</span><span class="sxs-lookup"><span data-stu-id="4ee96-328">To</span></span> | <span data-ttu-id="4ee96-329">Porta di origine</span><span class="sxs-lookup"><span data-stu-id="4ee96-329">Source port</span></span> | <span data-ttu-id="4ee96-330">Porta di destinazione</span><span class="sxs-lookup"><span data-stu-id="4ee96-330">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="4ee96-331">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="4ee96-331">UDP/SRTP</span></span> | <span data-ttu-id="4ee96-332">Processore multimediale</span><span class="sxs-lookup"><span data-stu-id="4ee96-332">Media Processor</span></span> | <span data-ttu-id="4ee96-333">SBC</span><span class="sxs-lookup"><span data-stu-id="4ee96-333">SBC</span></span> | <span data-ttu-id="4ee96-334">3478-3481 e 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="4ee96-334">3478-3481 and 49 152 – 53 247</span></span>    | <span data-ttu-id="4ee96-335">Definito nell'SBC</span><span class="sxs-lookup"><span data-stu-id="4ee96-335">Defined on the SBC</span></span> |
| <span data-ttu-id="4ee96-336">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="4ee96-336">UDP/SRTP</span></span> | <span data-ttu-id="4ee96-337">SBC</span><span class="sxs-lookup"><span data-stu-id="4ee96-337">SBC</span></span> | <span data-ttu-id="4ee96-338">Processore multimediale</span><span class="sxs-lookup"><span data-stu-id="4ee96-338">Media Processor</span></span> | <span data-ttu-id="4ee96-339">Definito nell'SBC</span><span class="sxs-lookup"><span data-stu-id="4ee96-339">Defined on the SBC</span></span> | <span data-ttu-id="4ee96-340">3478-3481 e 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="4ee96-340">3478-3481 and 49 152 – 53 247</span></span>     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a><span data-ttu-id="4ee96-341">Configurare trunk separati per bypass multimediale e bypass non multimediale</span><span class="sxs-lookup"><span data-stu-id="4ee96-341">Configure separate trunks for media bypass and non-media bypass</span></span>  

<span data-ttu-id="4ee96-342">Se si esegue la migrazione al bypass multimediale da un bypass non multimediale e si vuole confermare la funzionalità prima di eseguire la migrazione di tutti gli utilizzi al bypass multimediale, è possibile creare un trunk separato e un criterio di routing vocale online separato da instradare al trunk di bypass multimediale e assegnare a utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="4ee96-342">If you are migrating to media bypass from non-media bypass and want to confirm functionality before migrating all usage to media bypass, you can create a separate trunk and separate Online Voice Routing policy to route to the media bypass trunk and assign to specific users.</span></span> 

<span data-ttu-id="4ee96-343">Passaggi di configurazione di alto livello:</span><span class="sxs-lookup"><span data-stu-id="4ee96-343">High-level configuration steps:</span></span>

- <span data-ttu-id="4ee96-344">Identificare gli utenti per testare il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="4ee96-344">Identify users to test media bypass.</span></span>

- <span data-ttu-id="4ee96-345">Creare due trunk separati con fqdn diversi: uno abilitato per il bypass multimediale; l'altro no.</span><span class="sxs-lookup"><span data-stu-id="4ee96-345">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="4ee96-346">Entrambi i trunk puntano allo stesso SBC.</span><span class="sxs-lookup"><span data-stu-id="4ee96-346">Both trunks point to the same SBC.</span></span> <span data-ttu-id="4ee96-347">Le porte per la segnalazione SIP TLS devono essere diverse.</span><span class="sxs-lookup"><span data-stu-id="4ee96-347">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="4ee96-348">Le porte per i supporti multimediali devono essere uguali.</span><span class="sxs-lookup"><span data-stu-id="4ee96-348">The ports for media must be the same.</span></span>

- <span data-ttu-id="4ee96-349">Creare un nuovo criterio routing vocale online e assegnare il trunk di bypass multimediale alle route corrispondenti associate all'utilizzo PSTN per questo criterio.</span><span class="sxs-lookup"><span data-stu-id="4ee96-349">Create a new Online Voice Routing policy and assign the media bypass trunk to the corresponding routes associated with the PSTN usage for this policy.</span></span>

- <span data-ttu-id="4ee96-350">Assegnare il nuovo criterio Routing vocale online agli utenti identificati per testare il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="4ee96-350">Assign the new Online Voice Routing policy to users you have identified to test media bypass.</span></span>

<span data-ttu-id="4ee96-351">L'esempio seguente illustra questa logica.</span><span class="sxs-lookup"><span data-stu-id="4ee96-351">The example below illustrates this logic.</span></span>

| <span data-ttu-id="4ee96-352">Set di utenti</span><span class="sxs-lookup"><span data-stu-id="4ee96-352">Set of users</span></span> | <span data-ttu-id="4ee96-353">Numero di utenti</span><span class="sxs-lookup"><span data-stu-id="4ee96-353">Number of users</span></span> | <span data-ttu-id="4ee96-354">FQDN trunk assegnato in OVRP</span><span class="sxs-lookup"><span data-stu-id="4ee96-354">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="4ee96-355">Bypass multimediale abilitato</span><span class="sxs-lookup"><span data-stu-id="4ee96-355">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="4ee96-356">Utenti con trunk di bypass non multimediali</span><span class="sxs-lookup"><span data-stu-id="4ee96-356">Users with non-media bypass trunk</span></span> | <span data-ttu-id="4ee96-357">980</span><span class="sxs-lookup"><span data-stu-id="4ee96-357">980</span></span> | <span data-ttu-id="4ee96-358">sbc1.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="4ee96-358">sbc1.contoso.com:5061</span></span> | <span data-ttu-id="4ee96-359">false</span><span class="sxs-lookup"><span data-stu-id="4ee96-359">false</span></span> |
<span data-ttu-id="4ee96-360">Utenti con trunk bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="4ee96-360">Users with media bypass trunk</span></span> | <span data-ttu-id="4ee96-361">20</span><span class="sxs-lookup"><span data-stu-id="4ee96-361">20</span></span> | <span data-ttu-id="4ee96-362">sbc2.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="4ee96-362">sbc2.contoso.com:5060</span></span> | <span data-ttu-id="4ee96-363">true</span><span class="sxs-lookup"><span data-stu-id="4ee96-363">true</span></span> | 

<span data-ttu-id="4ee96-364">Entrambi i trunk possono puntare allo stesso SBC con lo stesso indirizzo IP pubblico.</span><span class="sxs-lookup"><span data-stu-id="4ee96-364">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="4ee96-365">Le porte di segnalazione TLS nel SBC devono essere diverse, come illustrato nel diagramma seguente.</span><span class="sxs-lookup"><span data-stu-id="4ee96-365">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="4ee96-366">Si noti che è necessario assicurarsi che il certificato supporti entrambi i trunk.</span><span class="sxs-lookup"><span data-stu-id="4ee96-366">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="4ee96-367">Nella rete SAN è necessario avere due nomi (**sbc1.contoso.com** e **sbc2.contoso.com**) o avere un certificato con caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="4ee96-367">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4ee96-368">![Mostra che entrambi i trunk possono puntare allo stesso SBC con lo stesso ip pubblico](media/direct-routing-media-bypass-7.png)</span><span class="sxs-lookup"><span data-stu-id="4ee96-368">![Shows both trunks can point to the same SBC with the same public IP](media/direct-routing-media-bypass-7.png)</span></span>

<span data-ttu-id="4ee96-369">Per informazioni su come configurare due trunk nello stesso SBC, vedere la documentazione fornita dal fornitore SBC:</span><span class="sxs-lookup"><span data-stu-id="4ee96-369">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

 - [<span data-ttu-id="4ee96-370">Documentazione sulla distribuzione di AudioCodes</span><span class="sxs-lookup"><span data-stu-id="4ee96-370">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="4ee96-371">Documentazione sulla distribuzione Oracle</span><span class="sxs-lookup"><span data-stu-id="4ee96-371">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="4ee96-372">Documentazione sulla distribuzione di Ribbon Communications</span><span class="sxs-lookup"><span data-stu-id="4ee96-372">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="4ee96-373">Documentazione sulla distribuzione di TE-Systems (anynode)</span><span class="sxs-lookup"><span data-stu-id="4ee96-373">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="4ee96-374">Endpoint client supportati con bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="4ee96-374">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="4ee96-375">Il bypass multimediale è supportato con tutti i client desktop Teams, i client Android e iOS e Teams Telefono dispositivi.</span><span class="sxs-lookup"><span data-stu-id="4ee96-375">Media bypass is supported with all standalone Teams Desktop clients, Android and iOS clients and Teams Phone Devices.</span></span> 

<span data-ttu-id="4ee96-376">Per tutti gli altri endpoint che non supportano il bypass multimediale, la chiamata verrà convertita in non bypass anche se è stata avviata come chiamata di bypass.</span><span class="sxs-lookup"><span data-stu-id="4ee96-376">For all other endpoints that do not support media bypass, we will convert the call to non-bypass even if it started as a bypass call.</span></span> <span data-ttu-id="4ee96-377">Questa operazione viene eseguita automaticamente e non richiede alcuna azione da parte dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="4ee96-377">This happens automatically and does not require any actions from the administrator.</span></span> <span data-ttu-id="4ee96-378">Sono inclusi Skype for Business telefoni 3PIP e client Web Teams che supportano le chiamate di routing diretto (client basati su WebRTC in esecuzione su Microsoft Edge, Google Chrome, Mozilla Firefox).</span><span class="sxs-lookup"><span data-stu-id="4ee96-378">This includes Skype for Business 3PIP Phones, and Teams Web Clients that support Direct Routing calling (WebRTC based clients running on Microsoft Edge, Google Chrome, Mozilla Firefox).</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="4ee96-379">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ee96-379">See also</span></span>

[<span data-ttu-id="4ee96-380">Configurare il bypass multimediale con Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="4ee96-380">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)

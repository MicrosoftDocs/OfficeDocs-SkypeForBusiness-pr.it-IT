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
ms.openlocfilehash: 9b6624a81994c1d6797ed996fbcc233fe75f8907
ms.sourcegitcommit: 83f14c4c79559ef28357ff076938e52b369fc0c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2021
ms.locfileid: "52308355"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="a3194-103">Pianificare il bypass multimediale con Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="a3194-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="a3194-104">Informazioni sul bypass multimediale con Routing diretto</span><span class="sxs-lookup"><span data-stu-id="a3194-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="a3194-105">Il bypass multimediale consente di abbreviare il percorso del traffico multimediale e ridurre il numero di hop in transito per migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="a3194-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="a3194-106">Con il bypass multimediale, i contenuti multimediali vengono mantenuti tra session border controller (SBC) e il client invece di inviarlo tramite Telefono Microsoft System.</span><span class="sxs-lookup"><span data-stu-id="a3194-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="a3194-107">Per configurare il bypass multimediale, SBC e il client devono essere nella stessa posizione o rete.</span><span class="sxs-lookup"><span data-stu-id="a3194-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="a3194-108">È possibile controllare il bypass multimediale per ogni SBC usando il **comando Set-CSOnlinePSTNGateway** con il **parametro -MediaBypass** impostato su true o false.</span><span class="sxs-lookup"><span data-stu-id="a3194-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="a3194-109">Se si abilita il bypass multimediale, questo non significa che tutto il traffico multimediale rimarrà all'interno della rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="a3194-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="a3194-110">Questo articolo descrive il flusso delle chiamate in scenari diversi.</span><span class="sxs-lookup"><span data-stu-id="a3194-110">This article describes the call flow in different scenarios.</span></span>

<span data-ttu-id="a3194-111">I diagrammi seguenti illustrano la differenza nel flusso delle chiamate con e senza bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="a3194-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="a3194-112">Senza bypass multimediale, quando un client effettua o riceve una chiamata, sia la segnalazione che il flusso multimediale tra SBC, Telefono Microsoft System e il client Teams, come illustrato nel diagramma seguente:</span><span class="sxs-lookup"><span data-stu-id="a3194-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a3194-113">![Mostra la segnalazione e il flusso multimediale senza bypass multimediale](media/direct-routing-media-bypass-1.png)</span><span class="sxs-lookup"><span data-stu-id="a3194-113">![Shows signaling and media flow without media bypass](media/direct-routing-media-bypass-1.png)</span></span>


<span data-ttu-id="a3194-114">Si supponga però che un utente si trova nello stesso edificio o nella stessa rete di SBC.</span><span class="sxs-lookup"><span data-stu-id="a3194-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="a3194-115">Si supponga ad esempio che un utente che si trova in un edificio di Francoforte esempli una chiamata a un utente PSTN:</span><span class="sxs-lookup"><span data-stu-id="a3194-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="a3194-116">**Senza bypass multimediale,** i supporti multimediali fluiranno tramite Amsterdam o Dublino (dove sono distribuiti i data center Microsoft) e di nuovo alla SBC di Francoforte.</span><span class="sxs-lookup"><span data-stu-id="a3194-116">**Without media bypass**, media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="a3194-117">Il data center in Europa è selezionato perché il database SBC è in Europa e Microsoft usa il data center più vicino a SBC.</span><span class="sxs-lookup"><span data-stu-id="a3194-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="a3194-118">Anche se questo approccio non influisce sulla qualità delle chiamate a causa dell'ottimizzazione del flusso di traffico all'interno delle reti Microsoft nella maggior parte delle aree geografiche, il traffico ha un ciclo non necessario.</span><span class="sxs-lookup"><span data-stu-id="a3194-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="a3194-119">**Con il bypass multimediale,** i supporti multimediali vengono mantenuti direttamente tra l'Teams utente e SBC, come illustrato nel diagramma seguente:</span><span class="sxs-lookup"><span data-stu-id="a3194-119">**With media bypass**, the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="a3194-120">![Mostra la segnalazione e il flusso multimediale con bypass multimediale](media/direct-routing-media-bypass-2.png)</span><span class="sxs-lookup"><span data-stu-id="a3194-120">![Shows signaling and media flow with media bypass](media/direct-routing-media-bypass-2.png)</span></span>

<span data-ttu-id="a3194-121">Il bypass multimediale usa protocolli chiamati Interactive Connectivity Establishment (ICE) nel client Teams e ICE lite sul SBC.</span><span class="sxs-lookup"><span data-stu-id="a3194-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE lite on the SBC.</span></span> <span data-ttu-id="a3194-122">Questi protocolli consentono al routing diretto di usare il percorso multimediale più diretto per una qualità ottimale.</span><span class="sxs-lookup"><span data-stu-id="a3194-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="a3194-123">ICE e ICE Lite sono standard WebRTC.</span><span class="sxs-lookup"><span data-stu-id="a3194-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="a3194-124">Per informazioni dettagliate su questi protocolli, vedere RFC 5245.</span><span class="sxs-lookup"><span data-stu-id="a3194-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="a3194-125">Pianificazione del flusso delle chiamate e del firewall</span><span class="sxs-lookup"><span data-stu-id="a3194-125">Call flow and firewall planning</span></span>

<span data-ttu-id="a3194-126">La pianificazione del flusso delle chiamate e del firewall dipende dal fatto che l'utente abbia accesso diretto all'indirizzo IP pubblico dell'SBC e se l'utente si trova all'interno o all'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="a3194-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="a3194-127">Flusso delle chiamate se l'utente ha accesso diretto all'indirizzo IP pubblico dell'SBC</span><span class="sxs-lookup"><span data-stu-id="a3194-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="a3194-128">Se l'utente ha accesso diretto all'indirizzo IP pubblico del SBC, il flusso di chiamata è il seguente:</span><span class="sxs-lookup"><span data-stu-id="a3194-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="a3194-129">Per il bypass multimediale, il client Teams deve avere accesso all'indirizzo IP pubblico della SBC anche da una rete interna.</span><span class="sxs-lookup"><span data-stu-id="a3194-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="a3194-130">Se non si desidera supporti diretti, i supporti multimediali possono fluire tramite i relè di trasporto.</span><span class="sxs-lookup"><span data-stu-id="a3194-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="a3194-131">Questa è la soluzione consigliata quando un utente si trova nello stesso edificio e/o rete di SBC, rimuovendo i componenti Microsoft Cloud dal percorso multimediale.</span><span class="sxs-lookup"><span data-stu-id="a3194-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="a3194-132">La segnalazione fluisce sempre tramite il cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a3194-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="a3194-133">Il diagramma seguente mostra il flusso delle chiamate quando è abilitato il bypass multimediale, il client è interno e il client può raggiungere l'indirizzo IP pubblico del SBC (supporto diretto):</span><span class="sxs-lookup"><span data-stu-id="a3194-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="a3194-134">Le frecce e i valori numerici dei percorsi sono conformi ai flussi Microsoft Teams [chiamate.](./microsoft-teams-online-call-flows.md)</span><span class="sxs-lookup"><span data-stu-id="a3194-134">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md).</span></span>

- <span data-ttu-id="a3194-135">La segnalazione SIP accetta sempre i percorsi 4 e 4' (a seconda della direzione del traffico).</span><span class="sxs-lookup"><span data-stu-id="a3194-135">The SIP signaling always takes paths 4 and 4' (depending on the direction of the traffic).</span></span> <span data-ttu-id="a3194-136">Il supporto rimane locale e prende il percorso 5b.</span><span class="sxs-lookup"><span data-stu-id="a3194-136">Media stays local and takes path 5b.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a3194-137">![Mostra il flusso delle chiamate con Bypass multimediale abilitato, il client è interno](media/direct-routing-media-bypass-3.png)</span><span class="sxs-lookup"><span data-stu-id="a3194-137">![Shows Call flow with Media Bypass enabled, client is internal](media/direct-routing-media-bypass-3.png)</span></span>


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="a3194-138">Flusso delle chiamate se l'utente non ha accesso all'indirizzo IP pubblico dell'SBC</span><span class="sxs-lookup"><span data-stu-id="a3194-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="a3194-139">Di seguito viene descritto il flusso delle chiamate se l'utente non ha accesso all'indirizzo IP pubblico del servizio SBC.</span><span class="sxs-lookup"><span data-stu-id="a3194-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="a3194-140">Si supponga ad esempio che l'utente sia esterno e che l'amministratore del tenant abbia deciso di non aprire l'indirizzo IP pubblico della SBC a tutti gli utenti di Internet, ma solo a Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="a3194-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="a3194-141">I componenti interni del traffico possono fluire tramite Teams di trasporto.</span><span class="sxs-lookup"><span data-stu-id="a3194-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="a3194-142">Tenere in considerazione gli aspetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a3194-142">Consider the following:</span></span>

- <span data-ttu-id="a3194-143">Teams Vengono usati i relè di trasporto.</span><span class="sxs-lookup"><span data-stu-id="a3194-143">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="a3194-144">Per il bypass multimediale, Microsoft usa una versione di Transport Relays che richiede l'apertura delle porte da 50 000 a 59 999 tra i Teams Transport Relays e SBC (in futuro si prevede di passare alla versione che richiede 3478-3481 porte).</span><span class="sxs-lookup"><span data-stu-id="a3194-144">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires 3478-3481 ports).</span></span>


<span data-ttu-id="a3194-145">Il diagramma seguente mostra il flusso delle chiamate quando è abilitato il bypass multimediale, il client è esterno e il client non riesce a raggiungere l'indirizzo IP pubblico del Session Border Controller (i supporti vengono inoltrati da Teams Transport Relay).</span><span class="sxs-lookup"><span data-stu-id="a3194-145">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="a3194-146">Le frecce e i valori numerici dei percorsi sono conformi ai flussi Microsoft Teams [chiamate.](./microsoft-teams-online-call-flows.md)</span><span class="sxs-lookup"><span data-stu-id="a3194-146">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md).</span></span>

- <span data-ttu-id="a3194-147">I file multimediali vengono inoltrati tramite i percorsi 3, 3', 4 e 4'</span><span class="sxs-lookup"><span data-stu-id="a3194-147">Media is relayed via paths 3, 3', 4 and 4'</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a3194-148">![Mostra il flusso delle chiamate se l'utente non ha accesso all'IP pubblico dell'SBC](media/direct-routing-media-bypass-4.png)</span><span class="sxs-lookup"><span data-stu-id="a3194-148">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-4.png)</span></span>


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="a3194-149">Flusso delle chiamate se un utente si trova all'esterno della rete e ha accesso all'IP pubblico dell'SBC</span><span class="sxs-lookup"><span data-stu-id="a3194-149">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="a3194-150">Questa configurazione non è consigliata perché non sfrutta i Teams di trasporto.</span><span class="sxs-lookup"><span data-stu-id="a3194-150">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="a3194-151">È invece consigliabile considerare lo scenario precedente in cui l'utente non ha accesso all'indirizzo IP pubblico dell'SBC.</span><span class="sxs-lookup"><span data-stu-id="a3194-151">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="a3194-152">Il diagramma seguente mostra il flusso delle chiamate quando è abilitato il bypass multimediale, il client è esterno e il client può raggiungere l'indirizzo IP pubblico del SBC (supporto diretto).</span><span class="sxs-lookup"><span data-stu-id="a3194-152">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="a3194-153">Le frecce e i valori numerici dei percorsi sono conformi all'articolo Microsoft Teams [dei flussi di](./microsoft-teams-online-call-flows.md) chiamata.</span><span class="sxs-lookup"><span data-stu-id="a3194-153">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md) article.</span></span>

- <span data-ttu-id="a3194-154">La segnalazione SIP accetta sempre i percorsi 3 e 3' (a seconda della direzione del traffico).</span><span class="sxs-lookup"><span data-stu-id="a3194-154">The SIP signaling always takes paths 3 and 3' (depending on the direction of the traffic).</span></span> <span data-ttu-id="a3194-155">Flussi multimediali usando il percorso 2.</span><span class="sxs-lookup"><span data-stu-id="a3194-155">Media flows using path 2.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a3194-156">![Mostra il flusso delle chiamate se l'utente non ha accesso all'IP pubblico dell'SBC](media/direct-routing-media-bypass-5.png)</span><span class="sxs-lookup"><span data-stu-id="a3194-156">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-5.png)</span></span>


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="a3194-157">Uso di processori multimediali e relay di trasporto</span><span class="sxs-lookup"><span data-stu-id="a3194-157">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="a3194-158">In Microsoft Cloud sono disponibili due componenti che possono essere nel percorso del traffico multimediale: Processori multimediali e Relay di trasporto.</span><span class="sxs-lookup"><span data-stu-id="a3194-158">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="a3194-159">Il Processore multimediale è un componente pubblico che gestisce i supporti multimediali in casi non di bypass e gestisce gli elementi multimediali per le applicazioni vocali.</span><span class="sxs-lookup"><span data-stu-id="a3194-159">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="a3194-160">I processori multimediali sono sempre nel percorso per le chiamate non bypassate dell'utente finale, ma mai nel percorso per le chiamate ignorate.</span><span class="sxs-lookup"><span data-stu-id="a3194-160">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="a3194-161">I processori multimediali sono sempre nel percorso per tutte le applicazioni vocali, ad esempio Call Park, Organizational Operatore automatico e Call Queues.</span><span class="sxs-lookup"><span data-stu-id="a3194-161">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="a3194-162">L'inoltro di trasporto viene usato per connettersi al servizio di trasporto più vicino per inviare traffico in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="a3194-162">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="a3194-163">Gli inoltri di trasporto potrebbero essere o meno nel percorso per le chiamate ignorate, originate o destinate agli utenti finali, a seconda della posizione dell'utente e della configurazione della rete.</span><span class="sxs-lookup"><span data-stu-id="a3194-163">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="a3194-164">Il diagramma seguente mostra due flussi di chiamata: uno con il bypass multimediale abilitato e il secondo con bypass multimediale disabilitato.</span><span class="sxs-lookup"><span data-stu-id="a3194-164">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span>

> [!NOTE]
> <span data-ttu-id="a3194-165">Il diagramma illustra solo il traffico proveniente da utenti finali o destinati a utenti finali.</span><span class="sxs-lookup"><span data-stu-id="a3194-165">The diagram only illustrates traffic originating from--or destined to--end users.</span></span>  

- <span data-ttu-id="a3194-166">Il Controller multimediale è un microservizio in Azure che assegna processori multimediali e crea offerte SDP (Session Description Protocol).</span><span class="sxs-lookup"><span data-stu-id="a3194-166">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="a3194-167">Il proxy SIP è un componente che converte la segnalazione REST HTTP usata Teams in SIP.</span><span class="sxs-lookup"><span data-stu-id="a3194-167">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a3194-168">![Mostra i flussi delle chiamate con Bypass multimediale abilitato e disabilitato](media/direct-routing-media-bypass-6.png)</span><span class="sxs-lookup"><span data-stu-id="a3194-168">![Shows call flows with Media Bypass enabled and disabled](media/direct-routing-media-bypass-6.png)</span></span>


<span data-ttu-id="a3194-169">La tabella seguente riepiloga la differenza tra processori multimediali e relay di trasporto.</span><span class="sxs-lookup"><span data-stu-id="a3194-169">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="a3194-170">Processori multimediali</span><span class="sxs-lookup"><span data-stu-id="a3194-170">Media Processors</span></span> | <span data-ttu-id="a3194-171">Relè di trasporto</span><span class="sxs-lookup"><span data-stu-id="a3194-171">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="a3194-172">Percorso multimediale per le chiamate non bypassate per gli utenti finali</span><span class="sxs-lookup"><span data-stu-id="a3194-172">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="a3194-173">Sempre</span><span class="sxs-lookup"><span data-stu-id="a3194-173">Always</span></span> | <span data-ttu-id="a3194-174">Se il client non riesce a raggiungere direttamente il Processore multimediale</span><span class="sxs-lookup"><span data-stu-id="a3194-174">If client cannot reach the Media Processor directly</span></span> | 
<span data-ttu-id="a3194-175">Percorso multimediale per le chiamate ignorate per gli utenti finali</span><span class="sxs-lookup"><span data-stu-id="a3194-175">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="a3194-176">Mai</span><span class="sxs-lookup"><span data-stu-id="a3194-176">Never</span></span> | <span data-ttu-id="a3194-177">Se il client non riesce a raggiungere SBC nell'indirizzo IP pubblico</span><span class="sxs-lookup"><span data-stu-id="a3194-177">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="a3194-178">Percorso multimediale per le applicazioni vocali</span><span class="sxs-lookup"><span data-stu-id="a3194-178">In media path for voice applications</span></span> | <span data-ttu-id="a3194-179">Sempre</span><span class="sxs-lookup"><span data-stu-id="a3194-179">Always</span></span> | <span data-ttu-id="a3194-180">Mai</span><span class="sxs-lookup"><span data-stu-id="a3194-180">Never</span></span> | 
<span data-ttu-id="a3194-181">Può eseguire la trascodtura (B2BUA)\*</span><span class="sxs-lookup"><span data-stu-id="a3194-181">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="a3194-182">Sì</span><span class="sxs-lookup"><span data-stu-id="a3194-182">Yes</span></span> | <span data-ttu-id="a3194-183">No, solo l'inoltro audio tra endpoint</span><span class="sxs-lookup"><span data-stu-id="a3194-183">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="a3194-184">Numero di istanze in tutto il mondo e località</span><span class="sxs-lookup"><span data-stu-id="a3194-184">Number of instances worldwide and location</span></span> | <span data-ttu-id="a3194-185">10 in totale: 2 negli Stati Uniti orientali e occidentali; 2 ad Amsterdam e Dublino; 2 a Hong Kong e Singapore; 2 in Giappone ; 2 in Australia Est e Sudest</span><span class="sxs-lookup"><span data-stu-id="a3194-185">10 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan ; 2 in Australia East and Southeast</span></span> | <span data-ttu-id="a3194-186">Multiplo</span><span class="sxs-lookup"><span data-stu-id="a3194-186">Multiple</span></span>

<span data-ttu-id="a3194-187">Gli intervalli IP sono:</span><span class="sxs-lookup"><span data-stu-id="a3194-187">The IP ranges are:</span></span>
- <span data-ttu-id="a3194-188">52.112.0.0/14 (indirizzi IP da 52.112.0.1 a 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="a3194-188">52.112.0.0/14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>
- <span data-ttu-id="a3194-189">52.120.0.0/14 (indirizzi IP da 52.120.0.1 a 52.123.255.254)</span><span class="sxs-lookup"><span data-stu-id="a3194-189">52.120.0.0/14 (IP addresses from 52.120.0.1 to 52.123.255.254)</span></span>

<span data-ttu-id="a3194-190">\* Spiegazione trascodico:</span><span class="sxs-lookup"><span data-stu-id="a3194-190">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="a3194-191">Processore multimediale è B2BUA, il che significa che può modificare un codec,ad esempio SILK da client Teams a MP e G.711 tra MP e SBC.</span><span class="sxs-lookup"><span data-stu-id="a3194-191">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="a3194-192">Gli inoltri di trasporto non sono B2BUA, il che significa che il codec non viene mai modificato tra il client e il SBC, anche se il traffico passa attraverso i relè.</span><span class="sxs-lookup"><span data-stu-id="a3194-192">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="a3194-193">Uso di processori Teams multimediali se il trunk è configurato per il bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="a3194-193">Use of Teams Media Processors if trunk is configured for media bypass</span></span>

<span data-ttu-id="a3194-194">Teams I processori multimediali vengono sempre inseriti nel percorso multimediale negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="a3194-194">Teams Media Processors are always inserted in the media path in the following scenarios:</span></span>

- <span data-ttu-id="a3194-195">La chiamata viene riassegnata dall'1:1 a una chiamata di gruppo</span><span class="sxs-lookup"><span data-stu-id="a3194-195">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="a3194-196">Chiamata a un utente Teams federato</span><span class="sxs-lookup"><span data-stu-id="a3194-196">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="a3194-197">La chiamata viene inoltrata o trasferita a un Skype for Business utente</span><span class="sxs-lookup"><span data-stu-id="a3194-197">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="a3194-198">Verificare che SBC abbia accesso agli intervalli Media Processors e Transport Relays come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="a3194-198">Ensure your SBC has access to the Media Processors and Transport Relays ranges as described below.</span></span>    


## <a name="sip-signaling-fqdns"></a><span data-ttu-id="a3194-199">Segnalazione SIP: FQDN</span><span class="sxs-lookup"><span data-stu-id="a3194-199">SIP Signaling: FQDNs</span></span>

<span data-ttu-id="a3194-200">Per la segnalazione SIP, i requisiti di FQDN e firewall sono gli stessi dei casi non bypassati.</span><span class="sxs-lookup"><span data-stu-id="a3194-200">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="a3194-201">Il routing diretto è disponibile negli ambienti Microsoft 365 o Office 365 seguenti:</span><span class="sxs-lookup"><span data-stu-id="a3194-201">Direct Routing is offered in the following Microsoft 365 or Office 365 environments:</span></span>
- <span data-ttu-id="a3194-202">Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="a3194-202">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="a3194-203">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="a3194-203">Office 365 GCC</span></span>
- <span data-ttu-id="a3194-204">Office 365 GCC alta</span><span class="sxs-lookup"><span data-stu-id="a3194-204">Office 365 GCC High</span></span>
- <span data-ttu-id="a3194-205">Office 365 DoD Altre informazioni sugli [ambienti governativi Office 365](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) Stati Uniti, ad esempio GCC, GCC High e DoD.</span><span class="sxs-lookup"><span data-stu-id="a3194-205">Office 365 DoD Learn more about [Office 365 and US Government environments](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="a3194-206">Microsoft 365, Office 365 e Office 365 GCC di lavoro</span><span class="sxs-lookup"><span data-stu-id="a3194-206">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

<span data-ttu-id="a3194-207">I punti di connessione per il routing diretto sono i tre FQDN seguenti:</span><span class="sxs-lookup"><span data-stu-id="a3194-207">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="a3194-208">**sip.pstnhub.microsoft.com,** fqdn globale, deve essere provato prima di tutto.</span><span class="sxs-lookup"><span data-stu-id="a3194-208">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="a3194-209">Quando il servizio SBC invia una richiesta di risoluzione del nome, i server DNS Microsoft Azure restituiscono un indirizzo IP che punta al data center primario di Azure assegnato a SBC.</span><span class="sxs-lookup"><span data-stu-id="a3194-209">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="a3194-210">L'assegnazione si basa sulle metriche delle prestazioni dei data center e sulla vicinanza geografica al SBC.</span><span class="sxs-lookup"><span data-stu-id="a3194-210">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="a3194-211">L'indirizzo IP restituito corrisponde all'FQDN primario.</span><span class="sxs-lookup"><span data-stu-id="a3194-211">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="a3194-212">**sip2.pstnhub.microsoft.com** , FQDN secondario, mappato geograficamente alla seconda area di priorità.</span><span class="sxs-lookup"><span data-stu-id="a3194-212">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="a3194-213">**sip3.pstnhub.microsoft.com,** fqdn terziario, viene mappato geograficamente alla terza area prioritaria.</span><span class="sxs-lookup"><span data-stu-id="a3194-213">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="a3194-214">È necessario inserire questi tre FQDN per:</span><span class="sxs-lookup"><span data-stu-id="a3194-214">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="a3194-215">Offrire un'esperienza ottimale, meno caricata e più vicina al data center SBC assegnato tramite query sul primo FQDN.</span><span class="sxs-lookup"><span data-stu-id="a3194-215">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="a3194-216">Fornire il failover quando viene stabilita una connessione da un SBC a un data center in cui si verifica un problema temporaneo.</span><span class="sxs-lookup"><span data-stu-id="a3194-216">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="a3194-217">Per altre informazioni, vedere Meccanismo di failover più avanti.</span><span class="sxs-lookup"><span data-stu-id="a3194-217">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="a3194-218">I nomi FQDN **sip.pstnhub.microsoft.com,** **sip2.pstnhub.microsoft.com** e **sip3.pstnhub.microsoft.com** verranno risolti in uno degli indirizzi IP seguenti:</span><span class="sxs-lookup"><span data-stu-id="a3194-218">The FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**, and **sip3.pstnhub.microsoft.com** will be resolved to one of the following IP addresses:</span></span>
- <span data-ttu-id="a3194-219">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="a3194-219">52.114.148.0</span></span>
- <span data-ttu-id="a3194-220">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="a3194-220">52.114.132.46</span></span> 
- <span data-ttu-id="a3194-221">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="a3194-221">52.114.75.24</span></span> 
- <span data-ttu-id="a3194-222">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="a3194-222">52.114.76.76</span></span> 
- <span data-ttu-id="a3194-223">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="a3194-223">52.114.7.24</span></span> 
- <span data-ttu-id="a3194-224">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="a3194-224">52.114.14.70</span></span>
- <span data-ttu-id="a3194-225">52.114.16.74</span><span class="sxs-lookup"><span data-stu-id="a3194-225">52.114.16.74</span></span>
- <span data-ttu-id="a3194-226">52.114.20.29</span><span class="sxs-lookup"><span data-stu-id="a3194-226">52.114.20.29</span></span>
- <span data-ttu-id="a3194-227">52.114.36.156</span><span class="sxs-lookup"><span data-stu-id="a3194-227">52.114.36.156</span></span> 
- <span data-ttu-id="a3194-228">52.114.32.169</span><span class="sxs-lookup"><span data-stu-id="a3194-228">52.114.32.169</span></span>

<span data-ttu-id="a3194-229">È necessario aprire le porte per tutti questi indirizzi IP nel firewall per consentire il traffico in ingresso e in uscita da e verso gli indirizzi per la segnalazione.</span><span class="sxs-lookup"><span data-stu-id="a3194-229">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="a3194-230">Se il firewall supporta i nomi DNS, l'FQDN **sip-all.pstnhub.microsoft.com** si risolve in tutti questi indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="a3194-230">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="a3194-231">Office 365 GCC DoD</span><span class="sxs-lookup"><span data-stu-id="a3194-231">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="a3194-232">Il punto di connessione per il routing diretto è il seguente FQDN:</span><span class="sxs-lookup"><span data-stu-id="a3194-232">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="a3194-233">**sip.pstnhub.dod.teams.microsoft.us** : FQDN globale.</span><span class="sxs-lookup"><span data-stu-id="a3194-233">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="a3194-234">Poiché l'Office 365 DoD esiste solo nei data center degli Stati Uniti, non sono disponibili FQDN secondari e terziari.</span><span class="sxs-lookup"><span data-stu-id="a3194-234">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="a3194-235">I nomi FQDN - sip.pstnhub.dod.teams.microsoft.us verranno risolti in uno degli indirizzi IP seguenti:</span><span class="sxs-lookup"><span data-stu-id="a3194-235">The FQDNs – sip.pstnhub.dod.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="a3194-236">52.127.64.33</span><span class="sxs-lookup"><span data-stu-id="a3194-236">52.127.64.33</span></span>
- <span data-ttu-id="a3194-237">52.127.68.34</span><span class="sxs-lookup"><span data-stu-id="a3194-237">52.127.68.34</span></span>

<span data-ttu-id="a3194-238">È necessario aprire le porte per tutti questi indirizzi IP nel firewall per consentire il traffico in ingresso e in uscita da e verso gli indirizzi per la segnalazione.</span><span class="sxs-lookup"><span data-stu-id="a3194-238">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="a3194-239">Se il firewall supporta i nomi DNS, l'FQDN sip.pstnhub.dod.teams.microsoft.us si risolve in tutti questi indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="a3194-239">If your firewall supports DNS names, the FQDN  sip.pstnhub.dod.teams.microsoft.us resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="a3194-240">Office 365 GCC ambiente High</span><span class="sxs-lookup"><span data-stu-id="a3194-240">Office 365 GCC High environment</span></span>

<span data-ttu-id="a3194-241">Il punto di connessione per il routing diretto è il seguente FQDN:</span><span class="sxs-lookup"><span data-stu-id="a3194-241">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="a3194-242">**sip.pstnhub.gov.teams.microsoft.us** : FQDN globale.</span><span class="sxs-lookup"><span data-stu-id="a3194-242">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="a3194-243">Poiché l'GCC High è presente solo nei data center degli Stati Uniti, non sono disponibili fqdn secondari e terziari.</span><span class="sxs-lookup"><span data-stu-id="a3194-243">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="a3194-244">I nomi FQDN - sip.pstnhub.gov.teams.microsoft.us verranno risolti in uno degli indirizzi IP seguenti:</span><span class="sxs-lookup"><span data-stu-id="a3194-244">The FQDNs – sip.pstnhub.gov.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="a3194-245">52.127.88.59</span><span class="sxs-lookup"><span data-stu-id="a3194-245">52.127.88.59</span></span>
- <span data-ttu-id="a3194-246">52.127.92.64</span><span class="sxs-lookup"><span data-stu-id="a3194-246">52.127.92.64</span></span>

<span data-ttu-id="a3194-247">È necessario aprire le porte per tutti questi indirizzi IP nel firewall per consentire il traffico in ingresso e in uscita da e verso gli indirizzi per la segnalazione.</span><span class="sxs-lookup"><span data-stu-id="a3194-247">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="a3194-248">Se il firewall supporta i nomi DNS, l'FQDN sip.pstnhub.gov.teams.microsoft.us viene risolto in tutti questi indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="a3194-248">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP addresses.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="a3194-249">Segnalazione SIP: Porte</span><span class="sxs-lookup"><span data-stu-id="a3194-249">SIP Signaling: Ports</span></span>

<span data-ttu-id="a3194-250">I requisiti di porta sono gli stessi per tutti gli Office 365 in cui è disponibile il routing diretto:</span><span class="sxs-lookup"><span data-stu-id="a3194-250">Port requirements are the same for all Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="a3194-251">Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="a3194-251">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="a3194-252">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="a3194-252">Office 365 GCC</span></span>
- <span data-ttu-id="a3194-253">Office 365 GCC alta</span><span class="sxs-lookup"><span data-stu-id="a3194-253">Office 365 GCC High</span></span>
- <span data-ttu-id="a3194-254">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="a3194-254">Office 365 DoD</span></span>

<span data-ttu-id="a3194-255">È necessario usare le porte seguenti:</span><span class="sxs-lookup"><span data-stu-id="a3194-255">You must use the following ports:</span></span>

| <span data-ttu-id="a3194-256">Traffico</span><span class="sxs-lookup"><span data-stu-id="a3194-256">Traffic</span></span> | <span data-ttu-id="a3194-257">Da</span><span class="sxs-lookup"><span data-stu-id="a3194-257">From</span></span> | <span data-ttu-id="a3194-258">A</span><span class="sxs-lookup"><span data-stu-id="a3194-258">To</span></span> | <span data-ttu-id="a3194-259">Porta di origine</span><span class="sxs-lookup"><span data-stu-id="a3194-259">Source port</span></span> | <span data-ttu-id="a3194-260">Porta di destinazione</span><span class="sxs-lookup"><span data-stu-id="a3194-260">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="a3194-261">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="a3194-261">SIP/TLS</span></span>| <span data-ttu-id="a3194-262">SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="a3194-262">SIP Proxy</span></span> | <span data-ttu-id="a3194-263">SBC</span><span class="sxs-lookup"><span data-stu-id="a3194-263">SBC</span></span> | <span data-ttu-id="a3194-264">1024 - 65535</span><span class="sxs-lookup"><span data-stu-id="a3194-264">1024 - 65535</span></span> | <span data-ttu-id="a3194-265">Definito nell'SBC</span><span class="sxs-lookup"><span data-stu-id="a3194-265">Defined on the SBC</span></span> |
| <span data-ttu-id="a3194-266">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="a3194-266">SIP/TLS</span></span> | <span data-ttu-id="a3194-267">SBC</span><span class="sxs-lookup"><span data-stu-id="a3194-267">SBC</span></span> | <span data-ttu-id="a3194-268">SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="a3194-268">SIP Proxy</span></span> | <span data-ttu-id="a3194-269">Definito nell'SBC</span><span class="sxs-lookup"><span data-stu-id="a3194-269">Defined on the SBC</span></span> | <span data-ttu-id="a3194-270">5061</span><span class="sxs-lookup"><span data-stu-id="a3194-270">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="a3194-271">Traffico multimediale: intervalli ip e porte</span><span class="sxs-lookup"><span data-stu-id="a3194-271">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="a3194-272">Il traffico multimediale fluisce tra il client SBC e il client Teams se è disponibile la connettività diretta o tramite gli inoltri di trasporto Teams se il client non riesce a raggiungere SBC usando l'indirizzo IP pubblico.</span><span class="sxs-lookup"><span data-stu-id="a3194-272">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="a3194-273">Requisiti per il traffico multimediale diretto (tra Teams client e SBC)</span><span class="sxs-lookup"><span data-stu-id="a3194-273">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="a3194-274">Il client deve avere accesso alle porte specificate (vedere la tabella) nell'indirizzo IP pubblico dell'SBC.</span><span class="sxs-lookup"><span data-stu-id="a3194-274">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

> [!NOTE]
> <span data-ttu-id="a3194-275">Se il client si trova in una rete interna, il contenuto multimediale passa all'indirizzo IP pubblico del servizio SBC.</span><span class="sxs-lookup"><span data-stu-id="a3194-275">If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="a3194-276">È possibile configurare l'aggiunta di capelli nel dispositivo NAT in modo che il traffico non lasci mai l'apparecchiatura di rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="a3194-276">You can configure hair pinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="a3194-277">Traffico</span><span class="sxs-lookup"><span data-stu-id="a3194-277">Traffic</span></span> | <span data-ttu-id="a3194-278">Da</span><span class="sxs-lookup"><span data-stu-id="a3194-278">From</span></span> | <span data-ttu-id="a3194-279">A</span><span class="sxs-lookup"><span data-stu-id="a3194-279">To</span></span> | <span data-ttu-id="a3194-280">Porta di origine</span><span class="sxs-lookup"><span data-stu-id="a3194-280">Source port</span></span> | <span data-ttu-id="a3194-281">Porta di destinazione</span><span class="sxs-lookup"><span data-stu-id="a3194-281">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="a3194-282">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="a3194-282">UDP/SRTP</span></span> | <span data-ttu-id="a3194-283">Client</span><span class="sxs-lookup"><span data-stu-id="a3194-283">Client</span></span> | <span data-ttu-id="a3194-284">SBC</span><span class="sxs-lookup"><span data-stu-id="a3194-284">SBC</span></span> | <span data-ttu-id="a3194-285">3478-3481 e 49152 – 53247</span><span class="sxs-lookup"><span data-stu-id="a3194-285">3478-3481 and 49152 – 53247</span></span>| <span data-ttu-id="a3194-286">Definito nell'SBC</span><span class="sxs-lookup"><span data-stu-id="a3194-286">Defined on the SBC</span></span> |
| <span data-ttu-id="a3194-287">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="a3194-287">UDP/SRTP</span></span> | <span data-ttu-id="a3194-288">SBC</span><span class="sxs-lookup"><span data-stu-id="a3194-288">SBC</span></span> | <span data-ttu-id="a3194-289">Client</span><span class="sxs-lookup"><span data-stu-id="a3194-289">Client</span></span> | <span data-ttu-id="a3194-290">Definito nell'SBC</span><span class="sxs-lookup"><span data-stu-id="a3194-290">Defined on the SBC</span></span> | <span data-ttu-id="a3194-291">3478-3481 e 49152 – 53247</span><span class="sxs-lookup"><span data-stu-id="a3194-291">3478-3481 and 49152 – 53247</span></span>  |


> [!NOTE]
> <span data-ttu-id="a3194-292">Se si dispone di un dispositivo di rete che traduce le porte di origine del client, assicurarsi che le porte tradotte siano aperte tra l'apparecchiatura di rete e la SBC.</span><span class="sxs-lookup"><span data-stu-id="a3194-292">If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="a3194-293">Requisiti per l'uso degli inoltri di trasporto</span><span class="sxs-lookup"><span data-stu-id="a3194-293">Requirements for using Transport Relays</span></span>

<span data-ttu-id="a3194-294">I relè di trasporto sono nello stesso intervallo dei processori multimediali (per i casi non di bypass):</span><span class="sxs-lookup"><span data-stu-id="a3194-294">Transport Relays are in the same range as Media Processors (for non-bypass cases):</span></span> 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="a3194-295">Microsoft 365, Office 365 e Office 365 GCC di lavoro</span><span class="sxs-lookup"><span data-stu-id="a3194-295">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

- <span data-ttu-id="a3194-296">52.112.0.0 /14 (indirizzi IP da 52.112.0.1 a 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="a3194-296">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="a3194-297">Office 365 GCC DoD</span><span class="sxs-lookup"><span data-stu-id="a3194-297">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="a3194-298">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="a3194-298">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="a3194-299">Office 365 GCC ambiente High</span><span class="sxs-lookup"><span data-stu-id="a3194-299">Office 365 GCC High environment</span></span>

- <span data-ttu-id="a3194-300">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="a3194-300">52.127.88.0/21</span></span>


<span data-ttu-id="a3194-301">L'intervallo di porte dei Teams di trasporto (applicabile a tutti gli ambienti) è illustrato nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="a3194-301">The port range of the Teams Transport Relays (applicable to all environments) is shown in the following table:</span></span>


| <span data-ttu-id="a3194-302">Traffico</span><span class="sxs-lookup"><span data-stu-id="a3194-302">Traffic</span></span> | <span data-ttu-id="a3194-303">Da</span><span class="sxs-lookup"><span data-stu-id="a3194-303">From</span></span> | <span data-ttu-id="a3194-304">A</span><span class="sxs-lookup"><span data-stu-id="a3194-304">To</span></span> | <span data-ttu-id="a3194-305">Porta di origine</span><span class="sxs-lookup"><span data-stu-id="a3194-305">Source port</span></span> | <span data-ttu-id="a3194-306">Porta di destinazione</span><span class="sxs-lookup"><span data-stu-id="a3194-306">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="a3194-307">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="a3194-307">UDP/SRTP</span></span> | <span data-ttu-id="a3194-308">Inoltro di trasporto</span><span class="sxs-lookup"><span data-stu-id="a3194-308">Transport Relay</span></span> | <span data-ttu-id="a3194-309">SBC</span><span class="sxs-lookup"><span data-stu-id="a3194-309">SBC</span></span> | <span data-ttu-id="a3194-310">50 000 -59 999</span><span class="sxs-lookup"><span data-stu-id="a3194-310">50 000 -59 999</span></span>    | <span data-ttu-id="a3194-311">Definito nell'SBC</span><span class="sxs-lookup"><span data-stu-id="a3194-311">Defined on the SBC</span></span> |
| <span data-ttu-id="a3194-312">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="a3194-312">UDP/SRTP</span></span> | <span data-ttu-id="a3194-313">SBC</span><span class="sxs-lookup"><span data-stu-id="a3194-313">SBC</span></span> | <span data-ttu-id="a3194-314">Inoltro di trasporto</span><span class="sxs-lookup"><span data-stu-id="a3194-314">Transport Relay</span></span> | <span data-ttu-id="a3194-315">Definito nell'SBC</span><span class="sxs-lookup"><span data-stu-id="a3194-315">Defined on the SBC</span></span> | <span data-ttu-id="a3194-316">50 000 – 59 999, 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="a3194-316">50 000 – 59 999, 3478, 3479</span></span>     |


> [!NOTE]
> <span data-ttu-id="a3194-317">Microsoft consiglia almeno due porte per ogni chiamata simultanea su SBC.</span><span class="sxs-lookup"><span data-stu-id="a3194-317">Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="a3194-318">Poiché Microsoft ha due versioni di Inoltro di trasporto, sono necessarie le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a3194-318">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>
> 
> - <span data-ttu-id="a3194-319">v4, che può funzionare solo con l'intervallo di porte da 50 000 a 59 999</span><span class="sxs-lookup"><span data-stu-id="a3194-319">v4, which can only work with port range 50 000 to 59 999</span></span>
> 
> - <span data-ttu-id="a3194-320">v6, che funziona con le porte 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="a3194-320">v6, which works with ports 3478, 3479</span></span>

<span data-ttu-id="a3194-321">Al momento, il bypass multimediale supporta solo la versione v4 di Transport Relays.</span><span class="sxs-lookup"><span data-stu-id="a3194-321">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="a3194-322">In futuro verrà introdotto il supporto della versione v6.</span><span class="sxs-lookup"><span data-stu-id="a3194-322">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="a3194-323">È necessario aprire le porte 3478 e 3479 per la transizione.</span><span class="sxs-lookup"><span data-stu-id="a3194-323">You need to open ports 3478 and 3479 for transitioning.</span></span> <span data-ttu-id="a3194-324">Quando Microsoft introduce il supporto per i relay di trasporto v6 con Media Bypass, non sarà necessario riconfigurare le apparecchiature di rete o gli SBC.</span><span class="sxs-lookup"><span data-stu-id="a3194-324">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="a3194-325">Requisiti per l'uso di processori multimediali</span><span class="sxs-lookup"><span data-stu-id="a3194-325">Requirements for using media processors</span></span>

<span data-ttu-id="a3194-326">I processori multimediali sono sempre nel percorso multimediale per le applicazioni vocali e per i client Web(ad esempio, i client Teams in Edge o Google Chrome).</span><span class="sxs-lookup"><span data-stu-id="a3194-326">Media Processors are always in the media path for voice applications and for Web clients (for example, Teams clients in Edge or Google Chrome).</span></span> <span data-ttu-id="a3194-327">I requisiti sono gli stessi per la configurazione non bypass.</span><span class="sxs-lookup"><span data-stu-id="a3194-327">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="a3194-328">L'intervallo IP per il traffico multimediale è</span><span class="sxs-lookup"><span data-stu-id="a3194-328">The IP range for media traffic is</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="a3194-329">Office 365 e Office 365 GCC di lavoro</span><span class="sxs-lookup"><span data-stu-id="a3194-329">Office 365 and Office 365 GCC environments</span></span>

- <span data-ttu-id="a3194-330">52.112.0.0 /14 (indirizzi IP da 52.112.0.1 a 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="a3194-330">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="a3194-331">Office 365 GCC DoD</span><span class="sxs-lookup"><span data-stu-id="a3194-331">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="a3194-332">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="a3194-332">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="a3194-333">Office 365 GCC ambiente High</span><span class="sxs-lookup"><span data-stu-id="a3194-333">Office 365 GCC High environment</span></span>

- <span data-ttu-id="a3194-334">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="a3194-334">52.127.88.0/21</span></span>

<span data-ttu-id="a3194-335">L'intervallo di porte dei processori multimediali (applicabile a tutti gli ambienti) è illustrato nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="a3194-335">The port range of the Media Processors (applicable to all environments) is shown in the following table:</span></span>

| <span data-ttu-id="a3194-336">Traffico</span><span class="sxs-lookup"><span data-stu-id="a3194-336">Traffic</span></span> | <span data-ttu-id="a3194-337">Da</span><span class="sxs-lookup"><span data-stu-id="a3194-337">From</span></span> | <span data-ttu-id="a3194-338">A</span><span class="sxs-lookup"><span data-stu-id="a3194-338">To</span></span> | <span data-ttu-id="a3194-339">Porta di origine</span><span class="sxs-lookup"><span data-stu-id="a3194-339">Source port</span></span> | <span data-ttu-id="a3194-340">Porta di destinazione</span><span class="sxs-lookup"><span data-stu-id="a3194-340">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="a3194-341">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="a3194-341">UDP/SRTP</span></span> | <span data-ttu-id="a3194-342">Processore multimediale</span><span class="sxs-lookup"><span data-stu-id="a3194-342">Media Processor</span></span> | <span data-ttu-id="a3194-343">SBC</span><span class="sxs-lookup"><span data-stu-id="a3194-343">SBC</span></span> | <span data-ttu-id="a3194-344">3478, 3479 e 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="a3194-344">3478, 3479 and 49 152 – 53 247</span></span>    | <span data-ttu-id="a3194-345">Definito nell'SBC</span><span class="sxs-lookup"><span data-stu-id="a3194-345">Defined on the SBC</span></span> |
| <span data-ttu-id="a3194-346">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="a3194-346">UDP/SRTP</span></span> | <span data-ttu-id="a3194-347">SBC</span><span class="sxs-lookup"><span data-stu-id="a3194-347">SBC</span></span> | <span data-ttu-id="a3194-348">Processore multimediale</span><span class="sxs-lookup"><span data-stu-id="a3194-348">Media Processor</span></span> | <span data-ttu-id="a3194-349">Definito nell'SBC</span><span class="sxs-lookup"><span data-stu-id="a3194-349">Defined on the SBC</span></span> | <span data-ttu-id="a3194-350">3478, 3479 e 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="a3194-350">3478, 3479 and 49 152 – 53 247</span></span>     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a><span data-ttu-id="a3194-351">Configurare trunk separati per bypass multimediale e bypass non multimediale</span><span class="sxs-lookup"><span data-stu-id="a3194-351">Configure separate trunks for media bypass and non-media bypass</span></span>  

<span data-ttu-id="a3194-352">Se si esegue la migrazione al bypass multimediale da un bypass non multimediale e si vuole confermare la funzionalità prima di eseguire la migrazione di tutti gli utilizzi al bypass multimediale, è possibile creare un trunk separato e un criterio di routing vocale online separato da instradare al trunk di bypass multimediale e assegnare a utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="a3194-352">If you are migrating to media bypass from non-media bypass and want to confirm functionality before migrating all usage to media bypass, you can create a separate trunk and separate Online Voice Routing policy to route to the media bypass trunk and assign to specific users.</span></span> 

<span data-ttu-id="a3194-353">Passaggi di configurazione di alto livello:</span><span class="sxs-lookup"><span data-stu-id="a3194-353">High-level configuration steps:</span></span>

- <span data-ttu-id="a3194-354">Identificare gli utenti per testare il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="a3194-354">Identify users to test media bypass.</span></span>

- <span data-ttu-id="a3194-355">Creare due trunk separati con fqdn diversi: uno abilitato per il bypass multimediale; l'altro no.</span><span class="sxs-lookup"><span data-stu-id="a3194-355">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="a3194-356">Entrambi i trunk puntano allo stesso SBC.</span><span class="sxs-lookup"><span data-stu-id="a3194-356">Both trunks point to the same SBC.</span></span> <span data-ttu-id="a3194-357">Le porte per la segnalazione SIP TLS devono essere diverse.</span><span class="sxs-lookup"><span data-stu-id="a3194-357">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="a3194-358">Le porte per i supporti multimediali devono essere uguali.</span><span class="sxs-lookup"><span data-stu-id="a3194-358">The ports for media must be the same.</span></span>

- <span data-ttu-id="a3194-359">Creare un nuovo criterio routing vocale online e assegnare il trunk di bypass multimediale alle route corrispondenti associate all'utilizzo PSTN per questo criterio.</span><span class="sxs-lookup"><span data-stu-id="a3194-359">Create a new Online Voice Routing policy and assign the media bypass trunk to the corresponding routes associated with the PSTN usage for this policy.</span></span>

- <span data-ttu-id="a3194-360">Assegnare il nuovo criterio Routing vocale online agli utenti identificati per testare il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="a3194-360">Assign the new Online Voice Routing policy to users you have identified to test media bypass.</span></span>

<span data-ttu-id="a3194-361">L'esempio seguente illustra questa logica.</span><span class="sxs-lookup"><span data-stu-id="a3194-361">The example below illustrates this logic.</span></span>

| <span data-ttu-id="a3194-362">Set di utenti</span><span class="sxs-lookup"><span data-stu-id="a3194-362">Set of users</span></span> | <span data-ttu-id="a3194-363">Numero di utenti</span><span class="sxs-lookup"><span data-stu-id="a3194-363">Number of users</span></span> | <span data-ttu-id="a3194-364">FQDN trunk assegnato in OVRP</span><span class="sxs-lookup"><span data-stu-id="a3194-364">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="a3194-365">Bypass multimediale abilitato</span><span class="sxs-lookup"><span data-stu-id="a3194-365">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="a3194-366">Utenti con trunk di bypass non multimediali</span><span class="sxs-lookup"><span data-stu-id="a3194-366">Users with non-media bypass trunk</span></span> | <span data-ttu-id="a3194-367">980</span><span class="sxs-lookup"><span data-stu-id="a3194-367">980</span></span> | <span data-ttu-id="a3194-368">sbc1.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="a3194-368">sbc1.contoso.com:5061</span></span> | <span data-ttu-id="a3194-369">false</span><span class="sxs-lookup"><span data-stu-id="a3194-369">false</span></span> |
<span data-ttu-id="a3194-370">Utenti con trunk bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="a3194-370">Users with media bypass trunk</span></span> | <span data-ttu-id="a3194-371">20</span><span class="sxs-lookup"><span data-stu-id="a3194-371">20</span></span> | <span data-ttu-id="a3194-372">sbc2.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="a3194-372">sbc2.contoso.com:5060</span></span> | <span data-ttu-id="a3194-373">true</span><span class="sxs-lookup"><span data-stu-id="a3194-373">true</span></span> | 

<span data-ttu-id="a3194-374">Entrambi i trunk possono puntare allo stesso SBC con lo stesso indirizzo IP pubblico.</span><span class="sxs-lookup"><span data-stu-id="a3194-374">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="a3194-375">Le porte di segnalazione TLS nel SBC devono essere diverse, come illustrato nel diagramma seguente.</span><span class="sxs-lookup"><span data-stu-id="a3194-375">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="a3194-376">Si noti che è necessario assicurarsi che il certificato supporti entrambi i trunk.</span><span class="sxs-lookup"><span data-stu-id="a3194-376">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="a3194-377">Nella rete SAN è necessario avere due nomi (**sbc1.contoso.com** e **sbc2.contoso.com**) o avere un certificato con caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="a3194-377">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a3194-378">![Mostra che entrambi i trunk possono puntare allo stesso SBC con lo stesso ip pubblico](media/direct-routing-media-bypass-7.png)</span><span class="sxs-lookup"><span data-stu-id="a3194-378">![Shows both trunks can point to the same SBC with the same public IP](media/direct-routing-media-bypass-7.png)</span></span>

<span data-ttu-id="a3194-379">Per informazioni su come configurare due trunk nello stesso SBC, vedere la documentazione fornita dal fornitore SBC:</span><span class="sxs-lookup"><span data-stu-id="a3194-379">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

 - [<span data-ttu-id="a3194-380">Documentazione sulla distribuzione di AudioCodes</span><span class="sxs-lookup"><span data-stu-id="a3194-380">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="a3194-381">Documentazione sulla distribuzione Oracle</span><span class="sxs-lookup"><span data-stu-id="a3194-381">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="a3194-382">Documentazione sulla distribuzione di Ribbon Communications</span><span class="sxs-lookup"><span data-stu-id="a3194-382">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="a3194-383">Documentazione sulla distribuzione di TE-Systems (anynode)</span><span class="sxs-lookup"><span data-stu-id="a3194-383">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="a3194-384">Endpoint client supportati con bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="a3194-384">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="a3194-385">Il bypass multimediale è supportato con tutti i client desktop Teams, i client Android e iOS e Teams Telefono dispositivi.</span><span class="sxs-lookup"><span data-stu-id="a3194-385">Media bypass is supported with all standalone Teams Desktop clients, Android and iOS clients and Teams Phone Devices.</span></span> 

<span data-ttu-id="a3194-386">Per tutti gli altri endpoint che non supportano il bypass multimediale, la chiamata verrà convertita in non bypass anche se è stata avviata come chiamata di bypass.</span><span class="sxs-lookup"><span data-stu-id="a3194-386">For all other endpoints that do not support media bypass, we will convert the call to non-bypass even if it started as a bypass call.</span></span> <span data-ttu-id="a3194-387">Questa operazione viene eseguita automaticamente e non richiede alcuna azione da parte dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="a3194-387">This happens automatically and does not require any actions from the administrator.</span></span> <span data-ttu-id="a3194-388">Sono inclusi Skype for Business telefoni 3PIP e client Web Teams che supportano le chiamate di routing diretto (client basati su WebRTC in esecuzione su Microsoft Edge, Google Chrome, Mozilla Firefox).</span><span class="sxs-lookup"><span data-stu-id="a3194-388">This includes Skype for Business 3PIP Phones, and Teams Web Clients that support Direct Routing calling (WebRTC based clients running on Microsoft Edge, Google Chrome, Mozilla Firefox).</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="a3194-389">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3194-389">See also</span></span>

[<span data-ttu-id="a3194-390">Configurare il bypass multimediale con Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="a3194-390">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)

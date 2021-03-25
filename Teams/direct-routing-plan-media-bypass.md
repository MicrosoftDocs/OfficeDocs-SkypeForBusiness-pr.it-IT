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
description: Informazioni su come pianificare il bypass multimediale con Phone System Direct Routing, che consente di abbreviare il percorso del traffico multimediale e migliorare le prestazioni.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bbd31a62bf6ebcd481a3cdafeabaf29bb4767f2d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115594"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="ec5e1-103">Pianificare il bypass multimediale con Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="ec5e1-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="ec5e1-104">Informazioni sul bypass multimediale con Routing diretto</span><span class="sxs-lookup"><span data-stu-id="ec5e1-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="ec5e1-105">Il bypass multimediale consente di abbreviare il percorso del traffico multimediale e ridurre il numero di hop in transito per migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="ec5e1-106">Con il bypass multimediale, i supporti multimediali vengono mantenuti tra session border controller (SBC) e il client invece di inviarlo tramite Il sistema telefonico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="ec5e1-107">Per configurare il bypass multimediale, SBC e il client devono essere nella stessa posizione o rete.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="ec5e1-108">È possibile controllare il bypass multimediale per ogni SBC usando il **comando Set-CSOnlinePSTNGateway** con il **parametro -MediaBypass** impostato su true o false.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="ec5e1-109">Se si abilita il bypass multimediale, questo non significa che tutto il traffico multimediale rimarrà all'interno della rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="ec5e1-110">Questo articolo descrive il flusso delle chiamate in scenari diversi.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-110">This article describes the call flow in different scenarios.</span></span>    

<span data-ttu-id="ec5e1-111">I diagrammi seguenti illustrano la differenza nel flusso delle chiamate con e senza bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="ec5e1-112">Senza bypass multimediale, quando un client effettua o riceve una chiamata, sia la segnalazione che il flusso multimediale tra SBC, Microsoft Phone System e il client Teams, come illustrato nel diagramma seguente:</span><span class="sxs-lookup"><span data-stu-id="ec5e1-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ec5e1-113">![Mostra la segnalazione e il flusso multimediale senza bypass multimediale](media/direct-routing-media-bypass-1.png)</span><span class="sxs-lookup"><span data-stu-id="ec5e1-113">![Shows signaling and media flow without media bypass](media/direct-routing-media-bypass-1.png)</span></span>


<span data-ttu-id="ec5e1-114">Si supponga però che un utente si trova nello stesso edificio o nella stessa rete di SBC.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="ec5e1-115">Si supponga ad esempio che un utente che si trova in un edificio di Francoforte esempli una chiamata a un utente PSTN:</span><span class="sxs-lookup"><span data-stu-id="ec5e1-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="ec5e1-116">**Senza bypass multimediale,** i supporti multimediali fluiranno tramite Amsterdam o Dublino (dove sono distribuiti i data center Microsoft) e di nuovo alla SBC di Francoforte.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-116">**Without media bypass**, media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="ec5e1-117">Il data center in Europa è selezionato perché il database SBC è in Europa e Microsoft usa il data center più vicino a SBC.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="ec5e1-118">Anche se questo approccio non influisce sulla qualità delle chiamate a causa dell'ottimizzazione del flusso di traffico all'interno delle reti Microsoft nella maggior parte delle aree geografiche, il traffico ha un ciclo non necessario.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="ec5e1-119">**Con il bypass multimediale,** i supporti multimediali vengono mantenuti direttamente tra l'utente di Teams e SBC, come illustrato nel diagramma seguente:</span><span class="sxs-lookup"><span data-stu-id="ec5e1-119">**With media bypass**, the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="ec5e1-120">![Mostra la segnalazione e il flusso multimediale con bypass multimediale](media/direct-routing-media-bypass-2.png)</span><span class="sxs-lookup"><span data-stu-id="ec5e1-120">![Shows signaling and media flow with media bypass](media/direct-routing-media-bypass-2.png)</span></span>

<span data-ttu-id="ec5e1-121">Il bypass multimediale usa protocolli chiamati Interactive Connectivity Establishment (ICE) sul client Teams e ICE lite su SBC.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE lite on the SBC.</span></span> <span data-ttu-id="ec5e1-122">Questi protocolli consentono al routing diretto di usare il percorso multimediale più diretto per una qualità ottimale.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="ec5e1-123">ICE e ICE Lite sono standard WebRTC.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="ec5e1-124">Per informazioni dettagliate su questi protocolli, vedere RFC 5245.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="ec5e1-125">Pianificazione del flusso delle chiamate e del firewall</span><span class="sxs-lookup"><span data-stu-id="ec5e1-125">Call flow and firewall planning</span></span>

<span data-ttu-id="ec5e1-126">La pianificazione del flusso delle chiamate e del firewall dipende dal fatto che l'utente abbia accesso diretto all'indirizzo IP pubblico dell'SBC e se l'utente si trova all'interno o all'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="ec5e1-127">Flusso delle chiamate se l'utente ha accesso diretto all'indirizzo IP pubblico dell'SBC</span><span class="sxs-lookup"><span data-stu-id="ec5e1-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="ec5e1-128">Se l'utente ha accesso diretto all'indirizzo IP pubblico del SBC, il flusso di chiamata è il seguente:</span><span class="sxs-lookup"><span data-stu-id="ec5e1-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="ec5e1-129">Per il bypass multimediale, il client Teams deve avere accesso all'indirizzo IP pubblico del SBC anche da una rete interna.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="ec5e1-130">Se non si desidera supporti diretti, i supporti multimediali possono fluire tramite i relè di trasporto.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="ec5e1-131">Questa è la soluzione consigliata quando un utente si trova nello stesso edificio e/o rete di SBC, rimuovendo i componenti Microsoft Cloud dal percorso multimediale.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="ec5e1-132">La segnalazione fluisce sempre tramite il cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="ec5e1-133">Il diagramma seguente mostra il flusso delle chiamate quando è abilitato il bypass multimediale, il client è interno e il client può raggiungere l'indirizzo IP pubblico del SBC (supporto diretto):</span><span class="sxs-lookup"><span data-stu-id="ec5e1-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="ec5e1-134">Le frecce e i valori numerici dei percorsi sono conformi ai [flussi delle chiamate di Microsoft Teams.](./microsoft-teams-online-call-flows.md)</span><span class="sxs-lookup"><span data-stu-id="ec5e1-134">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md).</span></span>

- <span data-ttu-id="ec5e1-135">La segnalazione SIP accetta sempre i percorsi 4 e 4' (a seconda della direzione del traffico).</span><span class="sxs-lookup"><span data-stu-id="ec5e1-135">The SIP signaling always takes paths 4 and 4' (depending on the direction of the traffic).</span></span> <span data-ttu-id="ec5e1-136">Il supporto rimane locale e prende il percorso 5b.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-136">Media stays local and takes path 5b.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ec5e1-137">![Mostra il flusso delle chiamate con Bypass multimediale abilitato, il client è interno](media/direct-routing-media-bypass-3.png)</span><span class="sxs-lookup"><span data-stu-id="ec5e1-137">![Shows Call flow with Media Bypass enabled, client is internal](media/direct-routing-media-bypass-3.png)</span></span>


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="ec5e1-138">Flusso delle chiamate se l'utente non ha accesso all'indirizzo IP pubblico dell'SBC</span><span class="sxs-lookup"><span data-stu-id="ec5e1-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="ec5e1-139">Di seguito viene descritto il flusso delle chiamate se l'utente non ha accesso all'indirizzo IP pubblico del servizio SBC.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="ec5e1-140">Si supponga ad esempio che l'utente sia esterno e che l'amministratore del tenant abbia deciso di non aprire l'indirizzo IP pubblico della SBC a tutti gli utenti di Internet, ma solo a Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="ec5e1-141">I componenti interni del traffico possono fluire tramite i relè di trasporto di Teams.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="ec5e1-142">Tenere in considerazione gli aspetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec5e1-142">Consider the following:</span></span>

- <span data-ttu-id="ec5e1-143">Vengono usati i relè di trasporto di Teams.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-143">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="ec5e1-144">Per il bypass multimediale, Microsoft usa una versione di Transport Relays che richiede l'apertura delle porte da 50 000 a 59 999 tra Teams Transport Relays e SBC (in futuro si prevede di passare alla versione che richiede solo 3478 e 3479 porte).</span><span class="sxs-lookup"><span data-stu-id="ec5e1-144">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires only 3478 and 3479 ports).</span></span>


<span data-ttu-id="ec5e1-145">Il diagramma seguente mostra il flusso delle chiamate quando il bypass multimediale è abilitato, il client è esterno e il client non riesce a raggiungere l'indirizzo IP pubblico del Session Border Controller (i supporti vengono inoltrati da Teams Transport Relay).</span><span class="sxs-lookup"><span data-stu-id="ec5e1-145">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="ec5e1-146">Le frecce e i valori numerici dei percorsi sono conformi ai [flussi delle chiamate di Microsoft Teams.](./microsoft-teams-online-call-flows.md)</span><span class="sxs-lookup"><span data-stu-id="ec5e1-146">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md).</span></span>

- <span data-ttu-id="ec5e1-147">I file multimediali vengono inoltrati tramite i percorsi 3, 3', 4 e 4'</span><span class="sxs-lookup"><span data-stu-id="ec5e1-147">Media is relayed via paths 3, 3', 4 and 4'</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ec5e1-148">![Mostra il flusso delle chiamate se l'utente non ha accesso all'IP pubblico dell'SBC](media/direct-routing-media-bypass-4.png)</span><span class="sxs-lookup"><span data-stu-id="ec5e1-148">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-4.png)</span></span>


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="ec5e1-149">Flusso delle chiamate se un utente si trova all'esterno della rete e ha accesso all'IP pubblico dell'SBC</span><span class="sxs-lookup"><span data-stu-id="ec5e1-149">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="ec5e1-150">Questa configurazione non è consigliata perché non sfrutta i relay di trasporto di Teams.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-150">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="ec5e1-151">È invece consigliabile considerare lo scenario precedente in cui l'utente non ha accesso all'indirizzo IP pubblico dell'SBC.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-151">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="ec5e1-152">Il diagramma seguente mostra il flusso delle chiamate quando è abilitato il bypass multimediale, il client è esterno e il client può raggiungere l'indirizzo IP pubblico del SBC (supporto diretto).</span><span class="sxs-lookup"><span data-stu-id="ec5e1-152">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="ec5e1-153">Le frecce e i valori numerici dei percorsi sono conformi all'articolo [Flussi di chiamate di Microsoft Teams.](./microsoft-teams-online-call-flows.md)</span><span class="sxs-lookup"><span data-stu-id="ec5e1-153">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md) article.</span></span>

- <span data-ttu-id="ec5e1-154">La segnalazione SIP accetta sempre i percorsi 3 e 3' (a seconda della direzione del traffico).</span><span class="sxs-lookup"><span data-stu-id="ec5e1-154">The SIP signaling always takes paths 3 and 3' (depending on the direction of the traffic).</span></span> <span data-ttu-id="ec5e1-155">Flussi multimediali usando il percorso 2.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-155">Media flows using path 2.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ec5e1-156">![Mostra il flusso delle chiamate se l'utente non ha accesso all'IP pubblico dell'SBC](media/direct-routing-media-bypass-5.png)</span><span class="sxs-lookup"><span data-stu-id="ec5e1-156">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-5.png)</span></span>


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="ec5e1-157">Uso di processori multimediali e relay di trasporto</span><span class="sxs-lookup"><span data-stu-id="ec5e1-157">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="ec5e1-158">In Microsoft Cloud sono disponibili due componenti che possono essere nel percorso del traffico multimediale: Processori multimediali e Relay di trasporto.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-158">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="ec5e1-159">Il Processore multimediale è un componente pubblico che gestisce i supporti multimediali in casi non di bypass e gestisce gli elementi multimediali per le applicazioni vocali.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-159">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="ec5e1-160">I processori multimediali sono sempre nel percorso per le chiamate non bypassate dell'utente finale, ma mai nel percorso per le chiamate ignorate.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-160">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="ec5e1-161">I processori multimediali sono sempre nel percorso per tutte le applicazioni vocali, ad esempio Call Park, Organizational Operatore automatico e Call Queues.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-161">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="ec5e1-162">L'inoltro di trasporto viene usato per connettersi al servizio di trasporto più vicino per inviare traffico in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-162">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="ec5e1-163">Gli inoltri di trasporto potrebbero essere o meno nel percorso per le chiamate ignorate, originate o destinate agli utenti finali, a seconda della posizione dell'utente e della configurazione della rete.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-163">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="ec5e1-164">Il diagramma seguente mostra due flussi di chiamata: uno con il bypass multimediale abilitato e il secondo con bypass multimediale disabilitato.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-164">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span> <span data-ttu-id="ec5e1-165">Si noti che il diagramma illustra solo il traffico proveniente da o destinato agli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-165">Note the diagram only illustrates traffic originating from--or destined to--end users.</span></span>  
- <span data-ttu-id="ec5e1-166">Il Controller multimediale è un microservizio in Azure che assegna processori multimediali e crea offerte SDP (Session Description Protocol).</span><span class="sxs-lookup"><span data-stu-id="ec5e1-166">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="ec5e1-167">Il proxy SIP è un componente che converte la segnalazione REST HTTP usata in Teams in SIP.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-167">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ec5e1-168">![Mostra i flussi delle chiamate con Bypass multimediale abilitato e disabilitato](media/direct-routing-media-bypass-6.png)</span><span class="sxs-lookup"><span data-stu-id="ec5e1-168">![Shows call flows with Media Bypass enabled and disabled](media/direct-routing-media-bypass-6.png)</span></span>


<span data-ttu-id="ec5e1-169">La tabella seguente riepiloga la differenza tra processori multimediali e relay di trasporto.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-169">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="ec5e1-170">Processori multimediali</span><span class="sxs-lookup"><span data-stu-id="ec5e1-170">Media Processors</span></span> | <span data-ttu-id="ec5e1-171">Relè di trasporto</span><span class="sxs-lookup"><span data-stu-id="ec5e1-171">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="ec5e1-172">Percorso multimediale per le chiamate non bypassate per gli utenti finali</span><span class="sxs-lookup"><span data-stu-id="ec5e1-172">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="ec5e1-173">Sempre</span><span class="sxs-lookup"><span data-stu-id="ec5e1-173">Always</span></span> | <span data-ttu-id="ec5e1-174">Se il client non riesce a raggiungere direttamente il Processore multimediale</span><span class="sxs-lookup"><span data-stu-id="ec5e1-174">If client cannot reach the Media Processor directly</span></span> | 
<span data-ttu-id="ec5e1-175">Percorso multimediale per le chiamate ignorate per gli utenti finali</span><span class="sxs-lookup"><span data-stu-id="ec5e1-175">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="ec5e1-176">Mai</span><span class="sxs-lookup"><span data-stu-id="ec5e1-176">Never</span></span> | <span data-ttu-id="ec5e1-177">Se il client non riesce a raggiungere SBC nell'indirizzo IP pubblico</span><span class="sxs-lookup"><span data-stu-id="ec5e1-177">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="ec5e1-178">Percorso multimediale per le applicazioni vocali</span><span class="sxs-lookup"><span data-stu-id="ec5e1-178">In media path for voice applications</span></span> | <span data-ttu-id="ec5e1-179">Sempre</span><span class="sxs-lookup"><span data-stu-id="ec5e1-179">Always</span></span> | <span data-ttu-id="ec5e1-180">Mai</span><span class="sxs-lookup"><span data-stu-id="ec5e1-180">Never</span></span> | 
<span data-ttu-id="ec5e1-181">Può eseguire la trascodtura (B2BUA)\*</span><span class="sxs-lookup"><span data-stu-id="ec5e1-181">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="ec5e1-182">Sì</span><span class="sxs-lookup"><span data-stu-id="ec5e1-182">Yes</span></span> | <span data-ttu-id="ec5e1-183">No, solo l'inoltro audio tra endpoint</span><span class="sxs-lookup"><span data-stu-id="ec5e1-183">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="ec5e1-184">Numero di istanze in tutto il mondo e località</span><span class="sxs-lookup"><span data-stu-id="ec5e1-184">Number of instances worldwide and location</span></span> | <span data-ttu-id="ec5e1-185">10 in totale: 2 negli Stati Uniti orientali e occidentali; 2 ad Amsterdam e Dublino; 2 a Hong Kong e Singapore; 2 in Giappone ; 2 in Australia Est e Sudest</span><span class="sxs-lookup"><span data-stu-id="ec5e1-185">10 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan ; 2 in Australia East and Southeast</span></span> | <span data-ttu-id="ec5e1-186">Multiplo</span><span class="sxs-lookup"><span data-stu-id="ec5e1-186">Multiple</span></span>

<span data-ttu-id="ec5e1-187">Gli intervalli IP sono:</span><span class="sxs-lookup"><span data-stu-id="ec5e1-187">The IP ranges are:</span></span>
- <span data-ttu-id="ec5e1-188">52.112.0.0/14 (indirizzi IP da 52.112.0.1 a 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="ec5e1-188">52.112.0.0/14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>
- <span data-ttu-id="ec5e1-189">52.120.0.0/14 (indirizzi IP da 52.120.0.1 a 52.123.255.254)</span><span class="sxs-lookup"><span data-stu-id="ec5e1-189">52.120.0.0/14 (IP addresses from 52.120.0.1 to 52.123.255.254)</span></span>

<span data-ttu-id="ec5e1-190">\* Spiegazione trascodico:</span><span class="sxs-lookup"><span data-stu-id="ec5e1-190">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="ec5e1-191">Processore multimediale è B2BUA, che significa che può modificare un codec (ad esempio, SILK dal client Teams a MP e G.711 tra MP e SBC).</span><span class="sxs-lookup"><span data-stu-id="ec5e1-191">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="ec5e1-192">Gli inoltri di trasporto non sono B2BUA, il che significa che il codec non viene mai modificato tra il client e il SBC, anche se il traffico passa attraverso i relè.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-192">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="ec5e1-193">Uso dei processori multimediali di Teams se il trunk è configurato per il bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="ec5e1-193">Use of Teams Media Processors if trunk is configured for media bypass</span></span>

<span data-ttu-id="ec5e1-194">I processori multimediali di Teams vengono sempre inseriti nel percorso multimediale negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec5e1-194">Teams Media Processors are always inserted in the media path in the following scenarios:</span></span>

- <span data-ttu-id="ec5e1-195">La chiamata viene riassegnata dall'1:1 a una chiamata di gruppo</span><span class="sxs-lookup"><span data-stu-id="ec5e1-195">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="ec5e1-196">La chiamata è in corso a un utente di Teams federato</span><span class="sxs-lookup"><span data-stu-id="ec5e1-196">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="ec5e1-197">La chiamata viene inoltrata o trasferita a un utente Skype for Business</span><span class="sxs-lookup"><span data-stu-id="ec5e1-197">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="ec5e1-198">Verificare che SBC abbia accesso agli intervalli Media Processors e Transport Relays come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-198">Ensure your SBC has access to the Media Processors and Transport Relays ranges as described below.</span></span>    


## <a name="sip-signaling-fqdns"></a><span data-ttu-id="ec5e1-199">Segnalazione SIP: FQDN</span><span class="sxs-lookup"><span data-stu-id="ec5e1-199">SIP Signaling: FQDNs</span></span>

<span data-ttu-id="ec5e1-200">Per la segnalazione SIP, i requisiti di FQDN e firewall sono gli stessi dei casi non bypassati.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-200">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="ec5e1-201">Il routing diretto è disponibile negli ambienti Microsoft 365 o Office 365 seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec5e1-201">Direct Routing is offered in the following Microsoft 365 or Office 365 environments:</span></span>
- <span data-ttu-id="ec5e1-202">Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="ec5e1-202">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="ec5e1-203">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="ec5e1-203">Office 365 GCC</span></span>
- <span data-ttu-id="ec5e1-204">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="ec5e1-204">Office 365 GCC High</span></span>
- <span data-ttu-id="ec5e1-205">Office 365 DoD Altre informazioni sugli ambienti [office 365](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) e per enti pubblici degli Stati Uniti, come GCC, GCC High e DoD.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-205">Office 365 DoD Learn more about [Office 365 and US Government environments](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="ec5e1-206">Ambienti Microsoft 365, Office 365 e Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="ec5e1-206">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

<span data-ttu-id="ec5e1-207">I punti di connessione per il routing diretto sono i tre FQDN seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec5e1-207">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="ec5e1-208">**sip.pstnhub.microsoft.com,** fqdn globale, deve essere provato prima di tutto.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-208">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="ec5e1-209">Quando il servizio SBC invia una richiesta di risoluzione di questo nome, i server DNS di Microsoft Azure restituiscono un indirizzo IP che punta al data center primario di Azure assegnato a SBC.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-209">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="ec5e1-210">L'assegnazione si basa sulle metriche delle prestazioni dei data center e sulla vicinanza geografica al SBC.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-210">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="ec5e1-211">L'indirizzo IP restituito corrisponde all'FQDN primario.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-211">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="ec5e1-212">**sip2.pstnhub.microsoft.com** , FQDN secondario, mappato geograficamente alla seconda area di priorità.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-212">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="ec5e1-213">**sip3.pstnhub.microsoft.com,** fqdn terziario, viene mappato geograficamente alla terza area prioritaria.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-213">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="ec5e1-214">È necessario inserire questi tre FQDN per:</span><span class="sxs-lookup"><span data-stu-id="ec5e1-214">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="ec5e1-215">Offrire un'esperienza ottimale, meno caricata e più vicina al data center SBC assegnato tramite query sul primo FQDN.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-215">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="ec5e1-216">Fornire il failover quando viene stabilita una connessione da un SBC a un data center in cui si verifica un problema temporaneo.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-216">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="ec5e1-217">Per altre informazioni, vedere Meccanismo di failover più avanti.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-217">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="ec5e1-218">I nomi FQDN **sip.pstnhub.microsoft.com,** **sip2.pstnhub.microsoft.com** e **sip3.pstnhub.microsoft.com** verranno risolti in uno degli indirizzi IP seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec5e1-218">The FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**, and **sip3.pstnhub.microsoft.com** will be resolved to one of the following IP addresses:</span></span>
- <span data-ttu-id="ec5e1-219">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="ec5e1-219">52.114.148.0</span></span>
- <span data-ttu-id="ec5e1-220">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="ec5e1-220">52.114.132.46</span></span>
- <span data-ttu-id="ec5e1-221">52.114.16.74</span><span class="sxs-lookup"><span data-stu-id="ec5e1-221">52.114.16.74</span></span>
- <span data-ttu-id="ec5e1-222">52.114.20.29</span><span class="sxs-lookup"><span data-stu-id="ec5e1-222">52.114.20.29</span></span>
- <span data-ttu-id="ec5e1-223">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="ec5e1-223">52.114.75.24</span></span>
- <span data-ttu-id="ec5e1-224">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="ec5e1-224">52.114.76.76</span></span>
- <span data-ttu-id="ec5e1-225">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="ec5e1-225">52.114.7.24</span></span>
- <span data-ttu-id="ec5e1-226">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="ec5e1-226">52.114.14.70</span></span>

<span data-ttu-id="ec5e1-227">È necessario aprire le porte per tutti questi indirizzi IP nel firewall per consentire il traffico in ingresso e in uscita da e verso gli indirizzi per la segnalazione.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-227">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="ec5e1-228">Se il firewall supporta i nomi DNS, l'FQDN **sip-all.pstnhub.microsoft.com** si risolve in tutti questi indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-228">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="ec5e1-229">Ambiente DoD GCC di Office 365</span><span class="sxs-lookup"><span data-stu-id="ec5e1-229">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="ec5e1-230">Il punto di connessione per il routing diretto è il seguente FQDN:</span><span class="sxs-lookup"><span data-stu-id="ec5e1-230">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="ec5e1-231">**sip.pstnhub.dod.teams.microsoft.us** : FQDN globale.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-231">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="ec5e1-232">Poiché l'ambiente DoD di Office 365 esiste solo nei data center degli Stati Uniti, non sono disponibili FQDN secondari e terziari.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-232">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="ec5e1-233">I nomi FQDN - sip.pstnhub.dod.teams.microsoft.us verranno risolti in uno degli indirizzi IP seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec5e1-233">The FQDNs – sip.pstnhub.dod.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="ec5e1-234">52.127.64.33</span><span class="sxs-lookup"><span data-stu-id="ec5e1-234">52.127.64.33</span></span>
- <span data-ttu-id="ec5e1-235">52.127.68.34</span><span class="sxs-lookup"><span data-stu-id="ec5e1-235">52.127.68.34</span></span>

<span data-ttu-id="ec5e1-236">È necessario aprire le porte per tutti questi indirizzi IP nel firewall per consentire il traffico in ingresso e in uscita da e verso gli indirizzi per la segnalazione.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-236">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="ec5e1-237">Se il firewall supporta i nomi DNS, l'FQDN sip.pstnhub.dod.teams.microsoft.us si risolve in tutti questi indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-237">If your firewall supports DNS names, the FQDN  sip.pstnhub.dod.teams.microsoft.us resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="ec5e1-238">Ambiente Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="ec5e1-238">Office 365 GCC High environment</span></span>

<span data-ttu-id="ec5e1-239">Il punto di connessione per il routing diretto è il seguente FQDN:</span><span class="sxs-lookup"><span data-stu-id="ec5e1-239">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="ec5e1-240">**sip.pstnhub.gov.teams.microsoft.us** : FQDN globale.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-240">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="ec5e1-241">Poiché l'ambiente GCC High esiste solo nei data center degli Stati Uniti, non sono disponibili fqdn secondari e terziari.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-241">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="ec5e1-242">I nomi FQDN - sip.pstnhub.gov.teams.microsoft.us verranno risolti in uno degli indirizzi IP seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec5e1-242">The FQDNs – sip.pstnhub.gov.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="ec5e1-243">52.127.88.59</span><span class="sxs-lookup"><span data-stu-id="ec5e1-243">52.127.88.59</span></span>
- <span data-ttu-id="ec5e1-244">52.127.92.64</span><span class="sxs-lookup"><span data-stu-id="ec5e1-244">52.127.92.64</span></span>

<span data-ttu-id="ec5e1-245">È necessario aprire le porte per tutti questi indirizzi IP nel firewall per consentire il traffico in ingresso e in uscita da e verso gli indirizzi per la segnalazione.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-245">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="ec5e1-246">Se il firewall supporta i nomi DNS, l'FQDN sip.pstnhub.gov.teams.microsoft.us viene risolto in tutti questi indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-246">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP addresses.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="ec5e1-247">Segnalazione SIP: Porte</span><span class="sxs-lookup"><span data-stu-id="ec5e1-247">SIP Signaling: Ports</span></span>

<span data-ttu-id="ec5e1-248">I requisiti di porta sono gli stessi per tutti gli ambienti di Office 365 in cui è disponibile il routing diretto:</span><span class="sxs-lookup"><span data-stu-id="ec5e1-248">Port requirements are the same for all Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="ec5e1-249">Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="ec5e1-249">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="ec5e1-250">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="ec5e1-250">Office 365 GCC</span></span>
- <span data-ttu-id="ec5e1-251">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="ec5e1-251">Office 365 GCC High</span></span>
- <span data-ttu-id="ec5e1-252">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="ec5e1-252">Office 365 DoD</span></span>

<span data-ttu-id="ec5e1-253">È necessario usare le porte seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec5e1-253">You must use the following ports:</span></span>

| <span data-ttu-id="ec5e1-254">Traffico</span><span class="sxs-lookup"><span data-stu-id="ec5e1-254">Traffic</span></span> | <span data-ttu-id="ec5e1-255">Da</span><span class="sxs-lookup"><span data-stu-id="ec5e1-255">From</span></span> | <span data-ttu-id="ec5e1-256">A</span><span class="sxs-lookup"><span data-stu-id="ec5e1-256">To</span></span> | <span data-ttu-id="ec5e1-257">Porta di origine</span><span class="sxs-lookup"><span data-stu-id="ec5e1-257">Source port</span></span> | <span data-ttu-id="ec5e1-258">Porta di destinazione</span><span class="sxs-lookup"><span data-stu-id="ec5e1-258">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="ec5e1-259">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="ec5e1-259">SIP/TLS</span></span>| <span data-ttu-id="ec5e1-260">SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="ec5e1-260">SIP Proxy</span></span> | <span data-ttu-id="ec5e1-261">SBC</span><span class="sxs-lookup"><span data-stu-id="ec5e1-261">SBC</span></span> | <span data-ttu-id="ec5e1-262">1024 - 65535</span><span class="sxs-lookup"><span data-stu-id="ec5e1-262">1024 - 65535</span></span> | <span data-ttu-id="ec5e1-263">Definito nell'SBC</span><span class="sxs-lookup"><span data-stu-id="ec5e1-263">Defined on the SBC</span></span> |
| <span data-ttu-id="ec5e1-264">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="ec5e1-264">SIP/TLS</span></span> | <span data-ttu-id="ec5e1-265">SBC</span><span class="sxs-lookup"><span data-stu-id="ec5e1-265">SBC</span></span> | <span data-ttu-id="ec5e1-266">SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="ec5e1-266">SIP Proxy</span></span> | <span data-ttu-id="ec5e1-267">Definito nell'SBC</span><span class="sxs-lookup"><span data-stu-id="ec5e1-267">Defined on the SBC</span></span> | <span data-ttu-id="ec5e1-268">5061</span><span class="sxs-lookup"><span data-stu-id="ec5e1-268">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="ec5e1-269">Traffico multimediale: intervalli ip e porte</span><span class="sxs-lookup"><span data-stu-id="ec5e1-269">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="ec5e1-270">Il traffico multimediale fluisce tra il client SBC e il client Teams se è disponibile la connettività diretta o tramite l'inoltro di trasporto di Teams se il client non riesce a raggiungere la SBC usando l'indirizzo IP pubblico.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-270">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="ec5e1-271">Requisiti per il traffico multimediale diretto (tra il client Teams e SBC)</span><span class="sxs-lookup"><span data-stu-id="ec5e1-271">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="ec5e1-272">Il client deve avere accesso alle porte specificate (vedere la tabella) nell'indirizzo IP pubblico dell'SBC.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-272">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

<span data-ttu-id="ec5e1-273">Nota: se il client si trova in una rete interna, i supporti multimediali vengono indirizzati all'indirizzo IP pubblico del servizio SBC.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-273">Note: If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="ec5e1-274">È possibile configurare l'aggiunta di capelli nel dispositivo NAT in modo che il traffico non lasci mai l'apparecchiatura di rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-274">You can configure hair pinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="ec5e1-275">Traffico</span><span class="sxs-lookup"><span data-stu-id="ec5e1-275">Traffic</span></span> | <span data-ttu-id="ec5e1-276">Da</span><span class="sxs-lookup"><span data-stu-id="ec5e1-276">From</span></span> | <span data-ttu-id="ec5e1-277">A</span><span class="sxs-lookup"><span data-stu-id="ec5e1-277">To</span></span> | <span data-ttu-id="ec5e1-278">Porta di origine</span><span class="sxs-lookup"><span data-stu-id="ec5e1-278">Source port</span></span> | <span data-ttu-id="ec5e1-279">Porta di destinazione</span><span class="sxs-lookup"><span data-stu-id="ec5e1-279">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="ec5e1-280">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="ec5e1-280">UDP/SRTP</span></span> | <span data-ttu-id="ec5e1-281">Client</span><span class="sxs-lookup"><span data-stu-id="ec5e1-281">Client</span></span> | <span data-ttu-id="ec5e1-282">SBC</span><span class="sxs-lookup"><span data-stu-id="ec5e1-282">SBC</span></span> | <span data-ttu-id="ec5e1-283">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="ec5e1-283">50 000 – 50 019</span></span>  | <span data-ttu-id="ec5e1-284">Definito nell'SBC</span><span class="sxs-lookup"><span data-stu-id="ec5e1-284">Defined on the SBC</span></span> |
| <span data-ttu-id="ec5e1-285">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="ec5e1-285">UDP/SRTP</span></span> | <span data-ttu-id="ec5e1-286">SBC</span><span class="sxs-lookup"><span data-stu-id="ec5e1-286">SBC</span></span> | <span data-ttu-id="ec5e1-287">Client</span><span class="sxs-lookup"><span data-stu-id="ec5e1-287">Client</span></span> | <span data-ttu-id="ec5e1-288">Definito nell'SBC</span><span class="sxs-lookup"><span data-stu-id="ec5e1-288">Defined on the SBC</span></span> | <span data-ttu-id="ec5e1-289">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="ec5e1-289">50 000 – 50 019</span></span>  |


> [!NOTE]
> <span data-ttu-id="ec5e1-290">Se si dispone di un dispositivo di rete che traduce le porte di origine del client, assicurarsi che le porte tradotte siano aperte tra l'apparecchiatura di rete e la SBC.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-290">If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="ec5e1-291">Requisiti per l'uso degli inoltri di trasporto</span><span class="sxs-lookup"><span data-stu-id="ec5e1-291">Requirements for using Transport Relays</span></span>

<span data-ttu-id="ec5e1-292">I relè di trasporto sono nello stesso intervallo dei processori multimediali (per i casi non di bypass):</span><span class="sxs-lookup"><span data-stu-id="ec5e1-292">Transport Relays are in the same range as Media Processors (for non-bypass cases):</span></span> 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="ec5e1-293">Ambienti Microsoft 365, Office 365 e Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="ec5e1-293">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

- <span data-ttu-id="ec5e1-294">52.112.0.0 /14 (indirizzi IP da 52.112.0.1 a 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="ec5e1-294">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="ec5e1-295">Ambiente DoD GCC di Office 365</span><span class="sxs-lookup"><span data-stu-id="ec5e1-295">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="ec5e1-296">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="ec5e1-296">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="ec5e1-297">Ambiente Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="ec5e1-297">Office 365 GCC High environment</span></span>

- <span data-ttu-id="ec5e1-298">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="ec5e1-298">52.127.88.0/21</span></span>


<span data-ttu-id="ec5e1-299">L'intervallo di porte degli inoltri di trasporto di Teams (applicabile a tutti gli ambienti) è illustrato nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="ec5e1-299">The port range of the Teams Transport Relays (applicable to all environments) is shown in the following table:</span></span>


| <span data-ttu-id="ec5e1-300">Traffico</span><span class="sxs-lookup"><span data-stu-id="ec5e1-300">Traffic</span></span> | <span data-ttu-id="ec5e1-301">Da</span><span class="sxs-lookup"><span data-stu-id="ec5e1-301">From</span></span> | <span data-ttu-id="ec5e1-302">A</span><span class="sxs-lookup"><span data-stu-id="ec5e1-302">To</span></span> | <span data-ttu-id="ec5e1-303">Porta di origine</span><span class="sxs-lookup"><span data-stu-id="ec5e1-303">Source port</span></span> | <span data-ttu-id="ec5e1-304">Porta di destinazione</span><span class="sxs-lookup"><span data-stu-id="ec5e1-304">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="ec5e1-305">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="ec5e1-305">UDP/SRTP</span></span> | <span data-ttu-id="ec5e1-306">Inoltro di trasporto</span><span class="sxs-lookup"><span data-stu-id="ec5e1-306">Transport Relay</span></span> | <span data-ttu-id="ec5e1-307">SBC</span><span class="sxs-lookup"><span data-stu-id="ec5e1-307">SBC</span></span> | <span data-ttu-id="ec5e1-308">50 000 -59 999</span><span class="sxs-lookup"><span data-stu-id="ec5e1-308">50 000 -59 999</span></span>    | <span data-ttu-id="ec5e1-309">Definito nell'SBC</span><span class="sxs-lookup"><span data-stu-id="ec5e1-309">Defined on the SBC</span></span> |
| <span data-ttu-id="ec5e1-310">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="ec5e1-310">UDP/SRTP</span></span> | <span data-ttu-id="ec5e1-311">SBC</span><span class="sxs-lookup"><span data-stu-id="ec5e1-311">SBC</span></span> | <span data-ttu-id="ec5e1-312">Inoltro di trasporto</span><span class="sxs-lookup"><span data-stu-id="ec5e1-312">Transport Relay</span></span> | <span data-ttu-id="ec5e1-313">Definito nell'SBC</span><span class="sxs-lookup"><span data-stu-id="ec5e1-313">Defined on the SBC</span></span> | <span data-ttu-id="ec5e1-314">50 000 – 59 999, 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="ec5e1-314">50 000 – 59 999, 3478, 3479</span></span>     |


> [!NOTE]
> <span data-ttu-id="ec5e1-315">Microsoft consiglia almeno due porte per ogni chiamata simultanea su SBC.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-315">Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="ec5e1-316">Poiché Microsoft ha due versioni di Inoltro di trasporto, sono necessarie le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec5e1-316">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>
> 
> - <span data-ttu-id="ec5e1-317">v4, che può funzionare solo con l'intervallo di porte da 50 000 a 59 999</span><span class="sxs-lookup"><span data-stu-id="ec5e1-317">v4, which can only work with port range 50 000 to 59 999</span></span>
> 
> - <span data-ttu-id="ec5e1-318">v6, che funziona con le porte 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="ec5e1-318">v6, which works with ports 3478, 3479</span></span>

<span data-ttu-id="ec5e1-319">Al momento, il bypass multimediale supporta solo la versione v4 di Transport Relays.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-319">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="ec5e1-320">In futuro verrà introdotto il supporto della versione v6.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-320">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="ec5e1-321">È necessario aprire le porte 3478 e 3479 per la transizione.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-321">You need to open ports 3478 and 3479 for transitioning.</span></span> <span data-ttu-id="ec5e1-322">Quando Microsoft introduce il supporto per i relay di trasporto v6 con Media Bypass, non sarà necessario riconfigurare le apparecchiature di rete o gli SBC.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-322">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="ec5e1-323">Requisiti per l'uso di processori multimediali</span><span class="sxs-lookup"><span data-stu-id="ec5e1-323">Requirements for using media processors</span></span>

<span data-ttu-id="ec5e1-324">I processori multimediali sono sempre nel percorso multimediale per le applicazioni vocali e per i client Web, ad esempio i client di Teams in Edge o Google Chrome.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-324">Media Processors are always in the media path for voice applications and for Web clients (for example, Teams clients in Edge or Google Chrome).</span></span> <span data-ttu-id="ec5e1-325">I requisiti sono gli stessi per la configurazione non bypass.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-325">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="ec5e1-326">L'intervallo IP per il traffico multimediale è</span><span class="sxs-lookup"><span data-stu-id="ec5e1-326">The IP range for media traffic is</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="ec5e1-327">Ambienti GCC di Office 365 e Office 365</span><span class="sxs-lookup"><span data-stu-id="ec5e1-327">Office 365 and Office 365 GCC environments</span></span>

- <span data-ttu-id="ec5e1-328">52.112.0.0 /14 (indirizzi IP da 52.112.0.1 a 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="ec5e1-328">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="ec5e1-329">Ambiente DoD GCC di Office 365</span><span class="sxs-lookup"><span data-stu-id="ec5e1-329">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="ec5e1-330">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="ec5e1-330">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="ec5e1-331">Ambiente Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="ec5e1-331">Office 365 GCC High environment</span></span>

- <span data-ttu-id="ec5e1-332">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="ec5e1-332">52.127.88.0/21</span></span>

<span data-ttu-id="ec5e1-333">L'intervallo di porte dei processori multimediali (applicabile a tutti gli ambienti) è illustrato nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="ec5e1-333">The port range of the Media Processors (applicable to all environments) is shown in the following table:</span></span>

| <span data-ttu-id="ec5e1-334">Traffico</span><span class="sxs-lookup"><span data-stu-id="ec5e1-334">Traffic</span></span> | <span data-ttu-id="ec5e1-335">Da</span><span class="sxs-lookup"><span data-stu-id="ec5e1-335">From</span></span> | <span data-ttu-id="ec5e1-336">A</span><span class="sxs-lookup"><span data-stu-id="ec5e1-336">To</span></span> | <span data-ttu-id="ec5e1-337">Porta di origine</span><span class="sxs-lookup"><span data-stu-id="ec5e1-337">Source port</span></span> | <span data-ttu-id="ec5e1-338">Porta di destinazione</span><span class="sxs-lookup"><span data-stu-id="ec5e1-338">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="ec5e1-339">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="ec5e1-339">UDP/SRTP</span></span> | <span data-ttu-id="ec5e1-340">Processore multimediale</span><span class="sxs-lookup"><span data-stu-id="ec5e1-340">Media Processor</span></span> | <span data-ttu-id="ec5e1-341">SBC</span><span class="sxs-lookup"><span data-stu-id="ec5e1-341">SBC</span></span> | <span data-ttu-id="ec5e1-342">3478, 3479 e 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="ec5e1-342">3478, 3479 and 49 152 – 53 247</span></span>    | <span data-ttu-id="ec5e1-343">Definito nell'SBC</span><span class="sxs-lookup"><span data-stu-id="ec5e1-343">Defined on the SBC</span></span> |
| <span data-ttu-id="ec5e1-344">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="ec5e1-344">UDP/SRTP</span></span> | <span data-ttu-id="ec5e1-345">SBC</span><span class="sxs-lookup"><span data-stu-id="ec5e1-345">SBC</span></span> | <span data-ttu-id="ec5e1-346">Processore multimediale</span><span class="sxs-lookup"><span data-stu-id="ec5e1-346">Media Processor</span></span> | <span data-ttu-id="ec5e1-347">Definito nell'SBC</span><span class="sxs-lookup"><span data-stu-id="ec5e1-347">Defined on the SBC</span></span> | <span data-ttu-id="ec5e1-348">3478, 3479 e 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="ec5e1-348">3478, 3479 and 49 152 – 53 247</span></span>     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a><span data-ttu-id="ec5e1-349">Configurare trunk separati per bypass multimediale e bypass non multimediale</span><span class="sxs-lookup"><span data-stu-id="ec5e1-349">Configure separate trunks for media bypass and non-media bypass</span></span>  

<span data-ttu-id="ec5e1-350">Se si esegue la migrazione al bypass multimediale da un bypass non multimediale e si vuole confermare la funzionalità prima di eseguire la migrazione di tutti gli utilizzi al bypass multimediale, è possibile creare un trunk separato e un criterio di routing vocale online separato da instradare al trunk di bypass multimediale e assegnare a utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-350">If you are migrating to media bypass from non-media bypass and want to confirm functionality before migrating all usage to media bypass, you can create a separate trunk and separate Online Voice Routing policy to route to the media bypass trunk and assign to specific users.</span></span> 

<span data-ttu-id="ec5e1-351">Passaggi di configurazione di alto livello:</span><span class="sxs-lookup"><span data-stu-id="ec5e1-351">High-level configuration steps:</span></span>

- <span data-ttu-id="ec5e1-352">Identificare gli utenti per testare il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-352">Identify users to test media bypass.</span></span>

- <span data-ttu-id="ec5e1-353">Creare due trunk separati con fqdn diversi: uno abilitato per il bypass multimediale; l'altro no.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-353">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="ec5e1-354">Entrambi i trunk puntano allo stesso SBC.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-354">Both trunks point to the same SBC.</span></span> <span data-ttu-id="ec5e1-355">Le porte per la segnalazione SIP TLS devono essere diverse.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-355">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="ec5e1-356">Le porte per i supporti multimediali devono essere uguali.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-356">The ports for media must be the same.</span></span>

- <span data-ttu-id="ec5e1-357">Creare un nuovo criterio routing vocale online e assegnare il trunk di bypass multimediale alle route corrispondenti associate all'utilizzo PSTN per questo criterio.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-357">Create a new Online Voice Routing policy and assign the media bypass trunk to the corresponding routes associated with the PSTN usage for this policy.</span></span>

- <span data-ttu-id="ec5e1-358">Assegnare il nuovo criterio Routing vocale online agli utenti identificati per testare il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-358">Assign the new Online Voice Routing policy to users you have identified to test media bypass.</span></span>

<span data-ttu-id="ec5e1-359">L'esempio seguente illustra questa logica.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-359">The example below illustrates this logic.</span></span>

| <span data-ttu-id="ec5e1-360">Set di utenti</span><span class="sxs-lookup"><span data-stu-id="ec5e1-360">Set of users</span></span> | <span data-ttu-id="ec5e1-361">Numero di utenti</span><span class="sxs-lookup"><span data-stu-id="ec5e1-361">Number of users</span></span> | <span data-ttu-id="ec5e1-362">FQDN trunk assegnato in OVRP</span><span class="sxs-lookup"><span data-stu-id="ec5e1-362">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="ec5e1-363">Bypass multimediale abilitato</span><span class="sxs-lookup"><span data-stu-id="ec5e1-363">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="ec5e1-364">Utenti con trunk di bypass non multimediali</span><span class="sxs-lookup"><span data-stu-id="ec5e1-364">Users with non-media bypass trunk</span></span> | <span data-ttu-id="ec5e1-365">980</span><span class="sxs-lookup"><span data-stu-id="ec5e1-365">980</span></span> | <span data-ttu-id="ec5e1-366">sbc1.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="ec5e1-366">sbc1.contoso.com:5060</span></span> | <span data-ttu-id="ec5e1-367">true</span><span class="sxs-lookup"><span data-stu-id="ec5e1-367">true</span></span>
<span data-ttu-id="ec5e1-368">Utenti con trunk bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="ec5e1-368">Users with media bypass trunk</span></span> | <span data-ttu-id="ec5e1-369">20</span><span class="sxs-lookup"><span data-stu-id="ec5e1-369">20</span></span> | <span data-ttu-id="ec5e1-370">sbc2.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="ec5e1-370">sbc2.contoso.com:5061</span></span> | <span data-ttu-id="ec5e1-371">false</span><span class="sxs-lookup"><span data-stu-id="ec5e1-371">false</span></span> | 

<span data-ttu-id="ec5e1-372">Entrambi i trunk possono puntare allo stesso SBC con lo stesso indirizzo IP pubblico.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-372">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="ec5e1-373">Le porte di segnalazione TLS nel SBC devono essere diverse, come illustrato nel diagramma seguente.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-373">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="ec5e1-374">Si noti che è necessario assicurarsi che il certificato supporti entrambi i trunk.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-374">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="ec5e1-375">Nella rete SAN è necessario avere due nomi (**sbc1.contoso.com** e **sbc2.contoso.com**) o avere un certificato con caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-375">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ec5e1-376">![Mostra che entrambi i trunk possono puntare allo stesso SBC con lo stesso ip pubblico](media/direct-routing-media-bypass-7.png)</span><span class="sxs-lookup"><span data-stu-id="ec5e1-376">![Shows both trunks can point to the same SBC with the same public IP](media/direct-routing-media-bypass-7.png)</span></span>

<span data-ttu-id="ec5e1-377">Per informazioni su come configurare due trunk nello stesso SBC, vedere la documentazione fornita dal fornitore SBC:</span><span class="sxs-lookup"><span data-stu-id="ec5e1-377">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

 - [<span data-ttu-id="ec5e1-378">Documentazione sulla distribuzione di AudioCodes</span><span class="sxs-lookup"><span data-stu-id="ec5e1-378">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="ec5e1-379">Documentazione sulla distribuzione Oracle</span><span class="sxs-lookup"><span data-stu-id="ec5e1-379">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="ec5e1-380">Documentazione sulla distribuzione di Ribbon Communications</span><span class="sxs-lookup"><span data-stu-id="ec5e1-380">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="ec5e1-381">Documentazione sulla distribuzione di TE-Systems (anynode)</span><span class="sxs-lookup"><span data-stu-id="ec5e1-381">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="ec5e1-382">Endpoint client supportati con bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="ec5e1-382">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="ec5e1-383">Il bypass multimediale è supportato con tutti i client desktop di Teams autonomi, i client Android e iOS e i dispositivi telefonici di Teams.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-383">Media bypass is supported with all standalone Teams Desktop clients, Android and iOS clients and Teams Phone Devices.</span></span> 

<span data-ttu-id="ec5e1-384">Per tutti gli altri endpoint che non supportano il bypass multimediale, la chiamata verrà convertita in non bypass anche se è stata avviata come chiamata di bypass.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-384">For all other endpoints that do not support media bypass, we will convert the call to non-bypass even if it started as a bypass call.</span></span> <span data-ttu-id="ec5e1-385">Questa operazione viene eseguita automaticamente e non richiede alcuna azione da parte dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="ec5e1-385">This happens automatically and does not require any actions from the administrator.</span></span> <span data-ttu-id="ec5e1-386">Sono inclusi i telefoni Skype for Business 3PIP e i client Web di Teams che supportano le chiamate di routing diretto (client basati su WebRTC in esecuzione su Microsoft Edge, Google Chrome, Mozilla Firefox).</span><span class="sxs-lookup"><span data-stu-id="ec5e1-386">This includes Skype for Business 3PIP Phones, and Teams Web Clients that support Direct Routing calling (WebRTC based clients running on Microsoft Edge, Google Chrome, Mozilla Firefox).</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="ec5e1-387">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec5e1-387">See also</span></span>

[<span data-ttu-id="ec5e1-388">Configurare il bypass multimediale con Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="ec5e1-388">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)
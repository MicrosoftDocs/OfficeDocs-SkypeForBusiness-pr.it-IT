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
description: Informazioni su come pianificare il bypass multimediale con l'instradamento diretto del sistema telefonico, che consente di abbreviare il percorso del traffico multimediale e migliorare le prestazioni.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e21007c31dca540e4f659aad627911b4aec2e456
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460866"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="6598c-103">Pianificare il bypass multimediale con Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="6598c-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="6598c-104">Informazioni sul bypass multimediale con routing diretto</span><span class="sxs-lookup"><span data-stu-id="6598c-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="6598c-105">Il bypass multimediale consente di abbreviare il percorso del traffico multimediale e ridurre il numero di hop in transito per migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="6598c-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="6598c-106">Con il bypass multimediale, gli elementi multimediali vengono mantenuti tra il session border controller (SBC) e il client invece di inviarli tramite il Sistema telefonico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6598c-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="6598c-107">Per configurare il bypass multimediale, SBC e il client devono essere nella stessa posizione o rete.</span><span class="sxs-lookup"><span data-stu-id="6598c-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="6598c-108">È possibile controllare il bypass multimediale per ogni SBC usando il comando **Set-CSOnlinePSTNGateway** con il parametro **-MediaBypass** impostato su true o false.</span><span class="sxs-lookup"><span data-stu-id="6598c-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="6598c-109">Se abiliti il bypass multimediale, ciò non significa che tutto il traffico multimediale resterà all'interno della rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="6598c-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="6598c-110">Questo articolo descrive il flusso delle chiamate in diversi scenari.</span><span class="sxs-lookup"><span data-stu-id="6598c-110">This article describes the call flow in different scenarios.</span></span>    

<span data-ttu-id="6598c-111">I diagrammi seguenti illustrano la differenza nel flusso delle chiamate con e senza bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="6598c-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="6598c-112">Senza bypass multimediale, quando un client effettua o riceve una chiamata, sia il traffico di segnalazione che il flusso multimediale tra SBC, Il Sistema telefonico Microsoft e il client Teams, come illustrato nel diagramma seguente:</span><span class="sxs-lookup"><span data-stu-id="6598c-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6598c-113">![Mostra il traffico di segnalazione e il flusso multimediale senza bypass multimediale](media/direct-routing-media-bypass-1.png)</span><span class="sxs-lookup"><span data-stu-id="6598c-113">![Shows signaling and media flow without media bypass](media/direct-routing-media-bypass-1.png)</span></span>


<span data-ttu-id="6598c-114">Si supponga però che un utente si trova nello stesso edificio o rete del database SBC.</span><span class="sxs-lookup"><span data-stu-id="6598c-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="6598c-115">Si supponga, ad esempio, che un utente che si trova in un edificio di Gateway effettua una chiamata a un utente PSTN:</span><span class="sxs-lookup"><span data-stu-id="6598c-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="6598c-116">**Senza bypass multimediale,** gli elementi multimediali fluiranno attraverso Amsterdam o Dublino (in cui sono distribuiti i data center Microsoft) e tornano alla SBC in Avi.</span><span class="sxs-lookup"><span data-stu-id="6598c-116">**Without media bypass**, media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="6598c-117">Il data center in Europa è selezionato perché il database SBC si trova in Europa e Microsoft usa il data center più vicino a SBC.</span><span class="sxs-lookup"><span data-stu-id="6598c-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="6598c-118">Anche se questo approccio non influisce sulla qualità delle chiamate dovuta all'ottimizzazione del flusso del traffico nelle reti Microsoft nella maggior parte delle aree geografiche, il traffico presenta un ciclo non necessario.</span><span class="sxs-lookup"><span data-stu-id="6598c-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="6598c-119">**Con il bypass** multimediale, i contenuti multimediali vengono mantenuti direttamente tra l'utente di Teams e il controller SBC, come illustrato nel diagramma seguente:</span><span class="sxs-lookup"><span data-stu-id="6598c-119">**With media bypass**, the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="6598c-120">![Mostra il traffico di segnalazione e il flusso multimediale con bypass multimediale](media/direct-routing-media-bypass-2.png)</span><span class="sxs-lookup"><span data-stu-id="6598c-120">![Shows signaling and media flow with media bypass](media/direct-routing-media-bypass-2.png)</span></span>

<span data-ttu-id="6598c-121">Il bypass multimediale utilizza protocolli chiamati Interactive Connectivity Connectivity (ICE) sul client Teams e ICE lite sul sistema SBC.</span><span class="sxs-lookup"><span data-stu-id="6598c-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE lite on the SBC.</span></span> <span data-ttu-id="6598c-122">Questi protocolli consentono di usare il percorso multimediale più diretto per una qualità ottimale.</span><span class="sxs-lookup"><span data-stu-id="6598c-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="6598c-123">ICE e ICE Lite sono standard WebRTC.</span><span class="sxs-lookup"><span data-stu-id="6598c-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="6598c-124">Per informazioni dettagliate su questi protocolli, vedere RFC 5245.</span><span class="sxs-lookup"><span data-stu-id="6598c-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="6598c-125">Flusso delle chiamate e pianificazione del firewall</span><span class="sxs-lookup"><span data-stu-id="6598c-125">Call flow and firewall planning</span></span>

<span data-ttu-id="6598c-126">Il flusso delle chiamate e la pianificazione del firewall dipendono dal fatto che l'utente abbia accesso diretto all'indirizzo IP pubblico del database SBC e che l'utente sia all'interno o all'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="6598c-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="6598c-127">Flusso delle chiamate se l'utente ha accesso diretto all'indirizzo IP pubblico del servizio SBC</span><span class="sxs-lookup"><span data-stu-id="6598c-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="6598c-128">Se l'utente ha accesso diretto all'indirizzo IP pubblico del servizio SBC, il flusso delle chiamate è il seguente:</span><span class="sxs-lookup"><span data-stu-id="6598c-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="6598c-129">Per il bypass multimediale, il client Teams deve avere accesso all'indirizzo IP pubblico del servizio SBC anche da una rete interna.</span><span class="sxs-lookup"><span data-stu-id="6598c-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="6598c-130">Se non si desidera utilizzare elementi multimediali diretti, il flusso degli elementi multimediali può essere inoltrato tramite Transport Relays.</span><span class="sxs-lookup"><span data-stu-id="6598c-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="6598c-131">Questa è la soluzione consigliata quando un utente si trova nella stessa edificio e/o rete del servizio SBC, rimuovendo i componenti Microsoft Cloud dal percorso multimediale.</span><span class="sxs-lookup"><span data-stu-id="6598c-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="6598c-132">Il traffico di segnalazione fluisce sempre attraverso il cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6598c-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="6598c-133">Il diagramma seguente mostra il flusso delle chiamate quando è abilitato il bypass multimediale, il client è interno e può raggiungere l'indirizzo IP pubblico del SBC (supporto diretto):</span><span class="sxs-lookup"><span data-stu-id="6598c-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="6598c-134">Le frecce e i valori numerici dei percorsi sono conformi ai flussi delle [chiamate di Microsoft Teams.](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)</span><span class="sxs-lookup"><span data-stu-id="6598c-134">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows).</span></span>

- <span data-ttu-id="6598c-135">Il traffico di segnalazione SIP prende sempre i percorsi 4 e 4' (a seconda della direzione del traffico).</span><span class="sxs-lookup"><span data-stu-id="6598c-135">The SIP signaling always takes paths 4 and 4' (depending on the direction of the traffic).</span></span> <span data-ttu-id="6598c-136">L'elemento multimediale rimane locale e prende il percorso 5b.</span><span class="sxs-lookup"><span data-stu-id="6598c-136">Media stays local and takes path 5b.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6598c-137">![Mostra il flusso delle chiamate con il bypass multimediale abilitato, il client è interno](media/direct-routing-media-bypass-3.png)</span><span class="sxs-lookup"><span data-stu-id="6598c-137">![Shows Call flow with Media Bypass enabled, client is internal](media/direct-routing-media-bypass-3.png)</span></span>


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="6598c-138">Flusso delle chiamate se l'utente non ha accesso all'indirizzo IP pubblico del servizio SBC</span><span class="sxs-lookup"><span data-stu-id="6598c-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="6598c-139">Di seguito viene descritto il flusso delle chiamate se l'utente non ha accesso all'indirizzo IP pubblico del servizio SBC.</span><span class="sxs-lookup"><span data-stu-id="6598c-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="6598c-140">Ad esempio, si supponga che l'utente sia esterno e che l'amministratore del tenant abbia deciso di non aprire l'indirizzo IP pubblico del servizio SBC a tutti gli utenti in Internet, ma solo a Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="6598c-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="6598c-141">I componenti interni del traffico possono essere trasmessi tramite i Relay di trasporto di Teams.</span><span class="sxs-lookup"><span data-stu-id="6598c-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="6598c-142">Tenere in considerazione gli aspetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="6598c-142">Consider the following:</span></span>

- <span data-ttu-id="6598c-143">Vengono usati i Relay di trasporto di Teams.</span><span class="sxs-lookup"><span data-stu-id="6598c-143">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="6598c-144">Per il bypass multimediale, Microsoft usa una versione di Transport Relays che richiede l'apertura delle porte da 50 000 a 59 999 tra i Inoltro di trasporto di Teams e SBC (in futuro prevede di passare alla versione che richiede solo 3478 e 3479 porte).</span><span class="sxs-lookup"><span data-stu-id="6598c-144">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires only 3478 and 3479 ports).</span></span>


<span data-ttu-id="6598c-145">Il diagramma seguente mostra il flusso delle chiamate quando è abilitato il bypass multimediale, il client è esterno e il client non può raggiungere l'indirizzo IP pubblico del controller dei confini della sessione (il supporto viene inoltrato da Teams Transport Relay).</span><span class="sxs-lookup"><span data-stu-id="6598c-145">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="6598c-146">Le frecce e i valori numerici dei percorsi sono conformi ai flussi delle [chiamate di Microsoft Teams.](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)</span><span class="sxs-lookup"><span data-stu-id="6598c-146">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows).</span></span>

- <span data-ttu-id="6598c-147">Gli elementi multimediali vengono inoltrati tramite percorsi 3, 3', 4 e 4'</span><span class="sxs-lookup"><span data-stu-id="6598c-147">Media is relayed via paths 3, 3', 4 and 4'</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6598c-148">![Mostra il flusso delle chiamate se l'utente non ha accesso all'IP pubblico di SBC](media/direct-routing-media-bypass-4.png)</span><span class="sxs-lookup"><span data-stu-id="6598c-148">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-4.png)</span></span>


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="6598c-149">Flusso delle chiamate se un utente è esterno alla rete e ha accesso all'INDIRIZZO IP pubblico dell'SBC</span><span class="sxs-lookup"><span data-stu-id="6598c-149">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="6598c-150">Questa non è una configurazione consigliata perché non sfrutta i servizi di inoltro di trasporto di Teams.</span><span class="sxs-lookup"><span data-stu-id="6598c-150">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="6598c-151">È invece consigliabile considerare lo scenario precedente in cui l'utente non ha accesso all'indirizzo IP pubblico del database SBC.</span><span class="sxs-lookup"><span data-stu-id="6598c-151">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="6598c-152">Il diagramma seguente mostra il flusso delle chiamate quando è abilitato il bypass multimediale, il client è esterno e può raggiungere l'indirizzo IP pubblico del SBC (supporto diretto).</span><span class="sxs-lookup"><span data-stu-id="6598c-152">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="6598c-153">Le frecce e i valori numerici dei percorsi sono conformi all'articolo flussi delle chiamate [di Microsoft Teams.](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)</span><span class="sxs-lookup"><span data-stu-id="6598c-153">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="6598c-154">Il traffico di segnalazione SIP prende sempre i percorsi 3 e 3' (a seconda della direzione del traffico).</span><span class="sxs-lookup"><span data-stu-id="6598c-154">The SIP signaling always takes paths 3 and 3' (depending on the direction of the traffic).</span></span> <span data-ttu-id="6598c-155">Flussi multimediali utilizzando il percorso 2.</span><span class="sxs-lookup"><span data-stu-id="6598c-155">Media flows using path 2.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6598c-156">![Mostra il flusso delle chiamate se l'utente non ha accesso all'IP pubblico dell'SBC](media/direct-routing-media-bypass-5.png)</span><span class="sxs-lookup"><span data-stu-id="6598c-156">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-5.png)</span></span>


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="6598c-157">Uso di processori multimediali e relay di trasporto</span><span class="sxs-lookup"><span data-stu-id="6598c-157">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="6598c-158">Nel cloud Microsoft possono essere presenti due componenti nel percorso del traffico multimediale: Processori multimediali e Inoltro di trasporto.</span><span class="sxs-lookup"><span data-stu-id="6598c-158">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="6598c-159">Il processore multimediale è un componente pubblico che gestisce gli elementi multimediali in casi di bypass e gestisce gli elementi multimediali per le applicazioni vocali.</span><span class="sxs-lookup"><span data-stu-id="6598c-159">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="6598c-160">I processori multimediali sono sempre nel percorso per le chiamate senza bypass da parte dell'utente finale, ma mai nel percorso per le chiamate bypassate.</span><span class="sxs-lookup"><span data-stu-id="6598c-160">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="6598c-161">I processori multimediali sono sempre nel percorso per tutte le applicazioni vocali, ad esempio Call Park, Organizational Operatore automatico e Call Queues.</span><span class="sxs-lookup"><span data-stu-id="6598c-161">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="6598c-162">L'inoltro di trasporto viene usato per connettersi al servizio di trasporto più vicino per inviare il traffico in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="6598c-162">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="6598c-163">I Transport Relay possono essere o meno nel percorso per le chiamate ignorate, provenienti o destinate agli utenti finali, a seconda di dove si trova l'utente e di come è configurata la rete.</span><span class="sxs-lookup"><span data-stu-id="6598c-163">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="6598c-164">Il diagramma seguente mostra due flussi delle chiamate: uno con il bypass multimediale abilitato e il secondo con il bypass multimediale disabilitato.</span><span class="sxs-lookup"><span data-stu-id="6598c-164">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span> <span data-ttu-id="6598c-165">Si noti che il diagramma illustra solo il traffico proveniente dagli utenti finali, o destinato a loro.</span><span class="sxs-lookup"><span data-stu-id="6598c-165">Note the diagram only illustrates traffic originating from--or destined to--end users.</span></span>  
- <span data-ttu-id="6598c-166">Il controller multimediale è un microservice in Azure che assegna processori multimediali e crea offerte SDP (Session Description Protocol).</span><span class="sxs-lookup"><span data-stu-id="6598c-166">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="6598c-167">Il proxy SIP è un componente che traduce il traffico REST HTTP utilizzato in Teams in SIP.</span><span class="sxs-lookup"><span data-stu-id="6598c-167">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6598c-168">![Mostra i flussi delle chiamate con il bypass multimediale abilitato e disabilitato](media/direct-routing-media-bypass-6.png)</span><span class="sxs-lookup"><span data-stu-id="6598c-168">![Shows call flows with Media Bypass enabled and disabled](media/direct-routing-media-bypass-6.png)</span></span>


<span data-ttu-id="6598c-169">La tabella seguente riepiloga la differenza tra processori multimediali e inoltro di trasporto.</span><span class="sxs-lookup"><span data-stu-id="6598c-169">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="6598c-170">Processori multimediali</span><span class="sxs-lookup"><span data-stu-id="6598c-170">Media Processors</span></span> | <span data-ttu-id="6598c-171">Inoltro di trasporto</span><span class="sxs-lookup"><span data-stu-id="6598c-171">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="6598c-172">Percorso multimediale per chiamate senza bypass per gli utenti finali</span><span class="sxs-lookup"><span data-stu-id="6598c-172">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="6598c-173">Sempre</span><span class="sxs-lookup"><span data-stu-id="6598c-173">Always</span></span> | <span data-ttu-id="6598c-174">Se il client non può raggiungere direttamente il processore multimediale</span><span class="sxs-lookup"><span data-stu-id="6598c-174">If client cannot reach the Media Processor directly</span></span> | 
<span data-ttu-id="6598c-175">Percorso multimediale per le chiamate ignorate per gli utenti finali</span><span class="sxs-lookup"><span data-stu-id="6598c-175">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="6598c-176">Mai</span><span class="sxs-lookup"><span data-stu-id="6598c-176">Never</span></span> | <span data-ttu-id="6598c-177">Se il client non riesce a raggiungere SBC nell'indirizzo IP pubblico</span><span class="sxs-lookup"><span data-stu-id="6598c-177">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="6598c-178">Percorso multimediale per le applicazioni vocali</span><span class="sxs-lookup"><span data-stu-id="6598c-178">In media path for voice applications</span></span> | <span data-ttu-id="6598c-179">Sempre</span><span class="sxs-lookup"><span data-stu-id="6598c-179">Always</span></span> | <span data-ttu-id="6598c-180">Mai</span><span class="sxs-lookup"><span data-stu-id="6598c-180">Never</span></span> | 
<span data-ttu-id="6598c-181">Può eseguire la trascodtura (B2BUA)\*</span><span class="sxs-lookup"><span data-stu-id="6598c-181">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="6598c-182">Sì</span><span class="sxs-lookup"><span data-stu-id="6598c-182">Yes</span></span> | <span data-ttu-id="6598c-183">No, l'audio viene inoltrato solo tra gli endpoint</span><span class="sxs-lookup"><span data-stu-id="6598c-183">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="6598c-184">Numero di istanze in tutto il mondo e località</span><span class="sxs-lookup"><span data-stu-id="6598c-184">Number of instances worldwide and location</span></span> | <span data-ttu-id="6598c-185">10 totale: 2 negli Stati Uniti orientali e orientali; 2 ad Amsterdam e Dublino; 2 a Hong Kong e Singapore; 2 in Giappone; 2 in Australia orientale e sud-orientale</span><span class="sxs-lookup"><span data-stu-id="6598c-185">10 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan ; 2 in Australia East and Southeast</span></span> | <span data-ttu-id="6598c-186">Multiplo</span><span class="sxs-lookup"><span data-stu-id="6598c-186">Multiple</span></span>

<span data-ttu-id="6598c-187">Gli intervalli IP sono:</span><span class="sxs-lookup"><span data-stu-id="6598c-187">The IP ranges are:</span></span>
- <span data-ttu-id="6598c-188">52.112.0.0/14 (indirizzi IP da 52.112.0.1 a 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="6598c-188">52.112.0.0/14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>
- <span data-ttu-id="6598c-189">52.120.0.0/14 (indirizzi IP da 52.120.0.1 a 52.123.255.254)</span><span class="sxs-lookup"><span data-stu-id="6598c-189">52.120.0.0/14 (IP addresses from 52.120.0.1 to 52.123.255.254)</span></span>

<span data-ttu-id="6598c-190">\* Spiegazione della trascodzione:</span><span class="sxs-lookup"><span data-stu-id="6598c-190">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="6598c-191">Processore multimediale è B2BUA, il che significa che può modificare un codec (ad esempio, SILK dal client Teams a MP e G.711 tra MP e SBC).</span><span class="sxs-lookup"><span data-stu-id="6598c-191">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="6598c-192">I transport relays non sono B2BUA, il che significa che il codec non viene mai modificato tra il client e SBC, anche se il traffico passa attraverso gli inoltri.</span><span class="sxs-lookup"><span data-stu-id="6598c-192">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="6598c-193">Uso dei processori multimediali di Teams se è configurato il trunk per il bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="6598c-193">Use of Teams Media Processors if trunk is configured for media bypass</span></span>

<span data-ttu-id="6598c-194">I processori multimediali di Teams vengono sempre inseriti nel percorso multimediale negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="6598c-194">Teams Media Processors are always inserted in the media path in the following scenarios:</span></span>

- <span data-ttu-id="6598c-195">La chiamata viene inoltrata da 1:1 a una chiamata di gruppo</span><span class="sxs-lookup"><span data-stu-id="6598c-195">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="6598c-196">La chiamata è per un utente di Teams federato</span><span class="sxs-lookup"><span data-stu-id="6598c-196">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="6598c-197">La chiamata viene inoltrata o trasferita a un utente Skype for Business</span><span class="sxs-lookup"><span data-stu-id="6598c-197">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="6598c-198">Assicurarsi che SBC abbia accesso agli intervalli Media Processors e Transport Relays come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="6598c-198">Ensure your SBC has access to the Media Processors and Transport Relays ranges as described below.</span></span>    


## <a name="sip-signaling-fqdns"></a><span data-ttu-id="6598c-199">Segnalazione SIP: FQDN</span><span class="sxs-lookup"><span data-stu-id="6598c-199">SIP Signaling: FQDNs</span></span>

<span data-ttu-id="6598c-200">Per il traffico di segnalazione SIP, i requisiti di FQDN e firewall sono gli stessi dei casi non bypassati.</span><span class="sxs-lookup"><span data-stu-id="6598c-200">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="6598c-201">Il routing diretto è offerto nei seguenti ambienti Microsoft 365 o Office 365:</span><span class="sxs-lookup"><span data-stu-id="6598c-201">Direct Routing is offered in the following Microsoft 365 or Office 365 environments:</span></span>
- <span data-ttu-id="6598c-202">Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="6598c-202">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="6598c-203">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="6598c-203">Office 365 GCC</span></span>
- <span data-ttu-id="6598c-204">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="6598c-204">Office 365 GCC High</span></span>
- <span data-ttu-id="6598c-205">Office 365 DoD Altre informazioni sugli ambienti di [Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) e US Government come GCC, GCC High e DoD.</span><span class="sxs-lookup"><span data-stu-id="6598c-205">Office 365 DoD Learn more about [Office 365 and US Government environments](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="6598c-206">Ambienti Microsoft 365, Office 365 e Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="6598c-206">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

<span data-ttu-id="6598c-207">I punti di connessione per il routing diretto sono i tre FQDN seguenti:</span><span class="sxs-lookup"><span data-stu-id="6598c-207">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="6598c-208">**sip.pstnhub.microsoft.com-** FQDN globale: è necessario prima di tutto provarsi.</span><span class="sxs-lookup"><span data-stu-id="6598c-208">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="6598c-209">Quando SBC invia una richiesta di risoluzione di questo nome, i server DNS di Microsoft Azure restituiscono un indirizzo IP che punta al data center primario di Azure assegnato a SBC.</span><span class="sxs-lookup"><span data-stu-id="6598c-209">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="6598c-210">L'assegnazione si basa sulle metriche di prestazioni dei data center e sulla prossimità geografica del centro dati per SBC.</span><span class="sxs-lookup"><span data-stu-id="6598c-210">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="6598c-211">L'indirizzo IP restituito corrisponde all'FQDN principale.</span><span class="sxs-lookup"><span data-stu-id="6598c-211">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="6598c-212">**sip2.pstnhub.microsoft.com** - FQDN secondario: corrisponde geograficamente alla seconda area geografica di priorità.</span><span class="sxs-lookup"><span data-stu-id="6598c-212">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="6598c-213">**sip3.pstnhub.microsoft.com-** FQDN terziario: geograficamente associato alla terza area geografica di priorità.</span><span class="sxs-lookup"><span data-stu-id="6598c-213">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="6598c-214">È necessario inserire questi tre FQDN per:</span><span class="sxs-lookup"><span data-stu-id="6598c-214">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="6598c-215">Offrire un'esperienza ottimale, ovvero meno caricata e più vicina al data center SBC assegnato mediante query sul primo FQDN.</span><span class="sxs-lookup"><span data-stu-id="6598c-215">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="6598c-216">Fornire il failover quando viene stabilita una connessione da un database SBC a un data center in cui si verifica un problema temporaneo.</span><span class="sxs-lookup"><span data-stu-id="6598c-216">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="6598c-217">Per altre informazioni, vedere il meccanismo di failover seguente.</span><span class="sxs-lookup"><span data-stu-id="6598c-217">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="6598c-218">I nomi di **sip.pstnhub.microsoft.com,** **sip2.pstnhub.microsoft.com** **e** sip3.pstnhub.microsoft.com vengono risolti in uno degli indirizzi IP seguenti:</span><span class="sxs-lookup"><span data-stu-id="6598c-218">The FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**, and **sip3.pstnhub.microsoft.com** will be resolved to one of the following IP addresses:</span></span>
- <span data-ttu-id="6598c-219">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="6598c-219">52.114.148.0</span></span>
- <span data-ttu-id="6598c-220">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="6598c-220">52.114.132.46</span></span>
- <span data-ttu-id="6598c-221">52.114.16.74</span><span class="sxs-lookup"><span data-stu-id="6598c-221">52.114.16.74</span></span>
- <span data-ttu-id="6598c-222">52.114.20.29</span><span class="sxs-lookup"><span data-stu-id="6598c-222">52.114.20.29</span></span>
- <span data-ttu-id="6598c-223">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="6598c-223">52.114.75.24</span></span>
- <span data-ttu-id="6598c-224">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="6598c-224">52.114.76.76</span></span>
- <span data-ttu-id="6598c-225">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="6598c-225">52.114.7.24</span></span>
- <span data-ttu-id="6598c-226">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="6598c-226">52.114.14.70</span></span>

<span data-ttu-id="6598c-227">Devi aprire le porte per tutti questi indirizzi IP nel firewall per consentire il traffico in ingresso e in uscita da e verso gli indirizzi per il traffico di segnalazione.</span><span class="sxs-lookup"><span data-stu-id="6598c-227">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="6598c-228">Se il firewall supporta i nomi DNS, l'FQDN **sip-all.pstnhub.microsoft.com** risolve in tutti questi indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="6598c-228">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="6598c-229">Ambiente DoD GCC di Office 365</span><span class="sxs-lookup"><span data-stu-id="6598c-229">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="6598c-230">Il punto di connessione per il routing diretto è il seguente FQDN:</span><span class="sxs-lookup"><span data-stu-id="6598c-230">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="6598c-231">**sip.pstnhub.dod.teams.microsoft.us:** FQDN globale.</span><span class="sxs-lookup"><span data-stu-id="6598c-231">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="6598c-232">Poiché l'ambiente DoD di Office 365 esiste solo nei data center degli Stati Uniti, non sono presenti FQDN secondari e terziari.</span><span class="sxs-lookup"><span data-stu-id="6598c-232">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="6598c-233">I nomi di sip.pstnhub.dod.teams.microsoft.us vengono risolti in uno degli indirizzi IP seguenti:</span><span class="sxs-lookup"><span data-stu-id="6598c-233">The FQDNs – sip.pstnhub.dod.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="6598c-234">52.127.64.33</span><span class="sxs-lookup"><span data-stu-id="6598c-234">52.127.64.33</span></span>
- <span data-ttu-id="6598c-235">52.127.68.34</span><span class="sxs-lookup"><span data-stu-id="6598c-235">52.127.68.34</span></span>

<span data-ttu-id="6598c-236">Devi aprire le porte per tutti questi indirizzi IP nel firewall per consentire il traffico in ingresso e in uscita da e verso gli indirizzi per il traffico di segnalazione.</span><span class="sxs-lookup"><span data-stu-id="6598c-236">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="6598c-237">Se il firewall supporta i nomi DNS, l'FQDN sip.pstnhub.dod.teams.microsoft.us risolve in tutti questi indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="6598c-237">If your firewall supports DNS names, the FQDN  sip.pstnhub.dod.teams.microsoft.us resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="6598c-238">Ambiente Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="6598c-238">Office 365 GCC High environment</span></span>

<span data-ttu-id="6598c-239">Il punto di connessione per il routing diretto è il seguente FQDN:</span><span class="sxs-lookup"><span data-stu-id="6598c-239">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="6598c-240">**sip.pstnhub.gov.teams.microsoft.us:** FQDN globale.</span><span class="sxs-lookup"><span data-stu-id="6598c-240">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="6598c-241">Poiché l'ambiente GCC High esiste solo nei data center degli Stati Uniti, non sono presenti FQDN secondari e terziari.</span><span class="sxs-lookup"><span data-stu-id="6598c-241">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="6598c-242">I nomi di sip.pstnhub.gov.teams.microsoft.us sono stati risolti in uno degli indirizzi IP seguenti:</span><span class="sxs-lookup"><span data-stu-id="6598c-242">The FQDNs – sip.pstnhub.gov.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="6598c-243">52.127.88.59</span><span class="sxs-lookup"><span data-stu-id="6598c-243">52.127.88.59</span></span>
- <span data-ttu-id="6598c-244">52.127.92.64</span><span class="sxs-lookup"><span data-stu-id="6598c-244">52.127.92.64</span></span>

<span data-ttu-id="6598c-245">Devi aprire le porte per tutti questi indirizzi IP nel firewall per consentire il traffico in ingresso e in uscita da e verso gli indirizzi per il traffico di segnalazione.</span><span class="sxs-lookup"><span data-stu-id="6598c-245">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="6598c-246">Se il firewall supporta i nomi DNS, l'FQDN sip.pstnhub.gov.teams.microsoft.us risolve in tutti questi indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="6598c-246">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP addresses.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="6598c-247">Segnalazione SIP: Porte</span><span class="sxs-lookup"><span data-stu-id="6598c-247">SIP Signaling: Ports</span></span>

<span data-ttu-id="6598c-248">I requisiti di porta sono gli stessi per tutti gli ambienti di Office 365 in cui è offerto il routing diretto:</span><span class="sxs-lookup"><span data-stu-id="6598c-248">Port requirements are the same for all Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="6598c-249">Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="6598c-249">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="6598c-250">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="6598c-250">Office 365 GCC</span></span>
- <span data-ttu-id="6598c-251">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="6598c-251">Office 365 GCC High</span></span>
- <span data-ttu-id="6598c-252">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="6598c-252">Office 365 DoD</span></span>

<span data-ttu-id="6598c-253">È necessario usare le porte seguenti:</span><span class="sxs-lookup"><span data-stu-id="6598c-253">You must use the following ports:</span></span>

| <span data-ttu-id="6598c-254">Traffico</span><span class="sxs-lookup"><span data-stu-id="6598c-254">Traffic</span></span> | <span data-ttu-id="6598c-255">Da</span><span class="sxs-lookup"><span data-stu-id="6598c-255">From</span></span> | <span data-ttu-id="6598c-256">A</span><span class="sxs-lookup"><span data-stu-id="6598c-256">To</span></span> | <span data-ttu-id="6598c-257">Porta di origine</span><span class="sxs-lookup"><span data-stu-id="6598c-257">Source port</span></span> | <span data-ttu-id="6598c-258">Porta di destinazione</span><span class="sxs-lookup"><span data-stu-id="6598c-258">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="6598c-259">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="6598c-259">SIP/TLS</span></span>| <span data-ttu-id="6598c-260">SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="6598c-260">SIP Proxy</span></span> | <span data-ttu-id="6598c-261">SBC</span><span class="sxs-lookup"><span data-stu-id="6598c-261">SBC</span></span> | <span data-ttu-id="6598c-262">1024 - 65535</span><span class="sxs-lookup"><span data-stu-id="6598c-262">1024 - 65535</span></span> | <span data-ttu-id="6598c-263">Definito nel controller SBC</span><span class="sxs-lookup"><span data-stu-id="6598c-263">Defined on the SBC</span></span> |
| <span data-ttu-id="6598c-264">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="6598c-264">SIP/TLS</span></span> | <span data-ttu-id="6598c-265">SBC</span><span class="sxs-lookup"><span data-stu-id="6598c-265">SBC</span></span> | <span data-ttu-id="6598c-266">SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="6598c-266">SIP Proxy</span></span> | <span data-ttu-id="6598c-267">Definito nel controller SBC</span><span class="sxs-lookup"><span data-stu-id="6598c-267">Defined on the SBC</span></span> | <span data-ttu-id="6598c-268">5061</span><span class="sxs-lookup"><span data-stu-id="6598c-268">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="6598c-269">Traffico multimediale: intervalli ip e di porta</span><span class="sxs-lookup"><span data-stu-id="6598c-269">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="6598c-270">Il traffico multimediale passa tra il client SBC e il client Teams se la connettività diretta è disponibile o tramite i Relay di trasporto di Teams se il client non può raggiungere il valore SBC usando l'indirizzo IP pubblico.</span><span class="sxs-lookup"><span data-stu-id="6598c-270">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="6598c-271">Requisiti per il traffico multimediale diretto (tra il client Teams e SBC)</span><span class="sxs-lookup"><span data-stu-id="6598c-271">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="6598c-272">Il client deve avere accesso alle porte specificate (vedere la tabella) nell'indirizzo IP pubblico del servizio SBC.</span><span class="sxs-lookup"><span data-stu-id="6598c-272">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

<span data-ttu-id="6598c-273">Nota: se il client si trova in una rete interna, il flusso degli elementi multimediali viene indirizzato all'indirizzo IP pubblico del servizio SBC.</span><span class="sxs-lookup"><span data-stu-id="6598c-273">Note: If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="6598c-274">Puoi configurare il blocco dei capelli nel tuo dispositivo NAT in modo che il traffico non lasci mai l'apparecchiatura di rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="6598c-274">You can configure hair pinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="6598c-275">Traffico</span><span class="sxs-lookup"><span data-stu-id="6598c-275">Traffic</span></span> | <span data-ttu-id="6598c-276">Da</span><span class="sxs-lookup"><span data-stu-id="6598c-276">From</span></span> | <span data-ttu-id="6598c-277">A</span><span class="sxs-lookup"><span data-stu-id="6598c-277">To</span></span> | <span data-ttu-id="6598c-278">Porta di origine</span><span class="sxs-lookup"><span data-stu-id="6598c-278">Source port</span></span> | <span data-ttu-id="6598c-279">Porta di destinazione</span><span class="sxs-lookup"><span data-stu-id="6598c-279">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="6598c-280">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="6598c-280">UDP/SRTP</span></span> | <span data-ttu-id="6598c-281">Client</span><span class="sxs-lookup"><span data-stu-id="6598c-281">Client</span></span> | <span data-ttu-id="6598c-282">SBC</span><span class="sxs-lookup"><span data-stu-id="6598c-282">SBC</span></span> | <span data-ttu-id="6598c-283">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="6598c-283">50 000 – 50 019</span></span>  | <span data-ttu-id="6598c-284">Definito nel controller SBC</span><span class="sxs-lookup"><span data-stu-id="6598c-284">Defined on the SBC</span></span> |
| <span data-ttu-id="6598c-285">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="6598c-285">UDP/SRTP</span></span> | <span data-ttu-id="6598c-286">SBC</span><span class="sxs-lookup"><span data-stu-id="6598c-286">SBC</span></span> | <span data-ttu-id="6598c-287">Client</span><span class="sxs-lookup"><span data-stu-id="6598c-287">Client</span></span> | <span data-ttu-id="6598c-288">Definito nel controller SBC</span><span class="sxs-lookup"><span data-stu-id="6598c-288">Defined on the SBC</span></span> | <span data-ttu-id="6598c-289">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="6598c-289">50 000 – 50 019</span></span>  |


> [!NOTE]
> <span data-ttu-id="6598c-290">Se si dispone di un dispositivo di rete che traduce le porte di origine del client, assicurarsi che le porte tradotte siano aperte tra l'apparecchiatura di rete e SBC.</span><span class="sxs-lookup"><span data-stu-id="6598c-290">If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="6598c-291">Requisiti per l'uso degli inoltri di trasporto</span><span class="sxs-lookup"><span data-stu-id="6598c-291">Requirements for using Transport Relays</span></span>

<span data-ttu-id="6598c-292">Gli Inoltro di trasporto sono nello stesso intervallo dei processori multimediali (per casi non bypass):</span><span class="sxs-lookup"><span data-stu-id="6598c-292">Transport Relays are in the same range as Media Processors (for non-bypass cases):</span></span> 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="6598c-293">Ambienti Microsoft 365, Office 365 e Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="6598c-293">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

- <span data-ttu-id="6598c-294">52.112.0.0 /14 (indirizzi IP da 52.112.0.1 a 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="6598c-294">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="6598c-295">Ambiente DoD GCC di Office 365</span><span class="sxs-lookup"><span data-stu-id="6598c-295">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="6598c-296">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="6598c-296">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="6598c-297">Ambiente Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="6598c-297">Office 365 GCC High environment</span></span>

- <span data-ttu-id="6598c-298">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="6598c-298">52.127.88.0/21</span></span>


<span data-ttu-id="6598c-299">L'intervallo di porta dei relay di trasporto di Teams (applicabili a tutti gli ambienti) è indicato nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="6598c-299">The port range of the Teams Transport Relays (applicable to all environments) is shown in the following table:</span></span>


| <span data-ttu-id="6598c-300">Traffico</span><span class="sxs-lookup"><span data-stu-id="6598c-300">Traffic</span></span> | <span data-ttu-id="6598c-301">Da</span><span class="sxs-lookup"><span data-stu-id="6598c-301">From</span></span> | <span data-ttu-id="6598c-302">A</span><span class="sxs-lookup"><span data-stu-id="6598c-302">To</span></span> | <span data-ttu-id="6598c-303">Porta di origine</span><span class="sxs-lookup"><span data-stu-id="6598c-303">Source port</span></span> | <span data-ttu-id="6598c-304">Porta di destinazione</span><span class="sxs-lookup"><span data-stu-id="6598c-304">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="6598c-305">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="6598c-305">UDP/SRTP</span></span> | <span data-ttu-id="6598c-306">Inoltro di trasporto</span><span class="sxs-lookup"><span data-stu-id="6598c-306">Transport Relay</span></span> | <span data-ttu-id="6598c-307">SBC</span><span class="sxs-lookup"><span data-stu-id="6598c-307">SBC</span></span> | <span data-ttu-id="6598c-308">50 000 -59 999</span><span class="sxs-lookup"><span data-stu-id="6598c-308">50 000 -59 999</span></span>    | <span data-ttu-id="6598c-309">Definito nel controller SBC</span><span class="sxs-lookup"><span data-stu-id="6598c-309">Defined on the SBC</span></span> |
| <span data-ttu-id="6598c-310">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="6598c-310">UDP/SRTP</span></span> | <span data-ttu-id="6598c-311">SBC</span><span class="sxs-lookup"><span data-stu-id="6598c-311">SBC</span></span> | <span data-ttu-id="6598c-312">Inoltro di trasporto</span><span class="sxs-lookup"><span data-stu-id="6598c-312">Transport Relay</span></span> | <span data-ttu-id="6598c-313">Definito nel controller SBC</span><span class="sxs-lookup"><span data-stu-id="6598c-313">Defined on the SBC</span></span> | <span data-ttu-id="6598c-314">50 000 – 59 999, 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="6598c-314">50 000 – 59 999, 3478, 3479</span></span>     |


> [!NOTE]
> <span data-ttu-id="6598c-315">Microsoft consiglia almeno due porte per ogni chiamata simultanea sull'SBC.</span><span class="sxs-lookup"><span data-stu-id="6598c-315">Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="6598c-316">Poiché Microsoft ha due versioni di Inoltro di trasporto, sono necessarie le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6598c-316">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>
> 
> - <span data-ttu-id="6598c-317">v4, che può funzionare solo con l'intervallo di porta da 50 000 a 59 999</span><span class="sxs-lookup"><span data-stu-id="6598c-317">v4, which can only work with port range 50 000 to 59 999</span></span>
> 
> - <span data-ttu-id="6598c-318">v6, che funziona con le porte 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="6598c-318">v6, which works with ports 3478, 3479</span></span>

<span data-ttu-id="6598c-319">Al momento, il bypass multimediale supporta solo la versione v4 dei transport relay.</span><span class="sxs-lookup"><span data-stu-id="6598c-319">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="6598c-320">In futuro verrà introdotto il supporto della v6.</span><span class="sxs-lookup"><span data-stu-id="6598c-320">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="6598c-321">È necessario aprire le porte 3478 e 3479 per la transizione.</span><span class="sxs-lookup"><span data-stu-id="6598c-321">You need to open ports 3478 and 3479 for transitioning.</span></span> <span data-ttu-id="6598c-322">Quando Microsoft introduce il supporto per i Transport Relay v6 con Media Bypass, non sarà necessario riconfigurare le apparecchiature di rete o gli SBC.</span><span class="sxs-lookup"><span data-stu-id="6598c-322">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="6598c-323">Requisiti per l'uso dei processori multimediali</span><span class="sxs-lookup"><span data-stu-id="6598c-323">Requirements for using media processors</span></span>

<span data-ttu-id="6598c-324">I processori multimediali sono sempre nel percorso multimediale per le applicazioni vocali e per i client Web (ad esempio, i client Teams in Edge o Google Chrome).</span><span class="sxs-lookup"><span data-stu-id="6598c-324">Media Processors are always in the media path for voice applications and for Web clients (for example, Teams clients in Edge or Google Chrome).</span></span> <span data-ttu-id="6598c-325">I requisiti sono gli stessi della configurazione senza bypass.</span><span class="sxs-lookup"><span data-stu-id="6598c-325">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="6598c-326">L'intervallo IP per il traffico multimediale è</span><span class="sxs-lookup"><span data-stu-id="6598c-326">The IP range for media traffic is</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="6598c-327">Ambienti GCC di Office 365 e Office 365</span><span class="sxs-lookup"><span data-stu-id="6598c-327">Office 365 and Office 365 GCC environments</span></span>

- <span data-ttu-id="6598c-328">52.112.0.0 /14 (indirizzi IP da 52.112.0.1 a 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="6598c-328">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="6598c-329">Ambiente DoD GCC di Office 365</span><span class="sxs-lookup"><span data-stu-id="6598c-329">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="6598c-330">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="6598c-330">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="6598c-331">Ambiente Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="6598c-331">Office 365 GCC High environment</span></span>

- <span data-ttu-id="6598c-332">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="6598c-332">52.127.88.0/21</span></span>

<span data-ttu-id="6598c-333">L'intervallo di porta dei processori multimediali (applicabile a tutti gli ambienti) è indicato nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="6598c-333">The port range of the Media Processors (applicable to all environments) is shown in the following table:</span></span>

| <span data-ttu-id="6598c-334">Traffico</span><span class="sxs-lookup"><span data-stu-id="6598c-334">Traffic</span></span> | <span data-ttu-id="6598c-335">Da</span><span class="sxs-lookup"><span data-stu-id="6598c-335">From</span></span> | <span data-ttu-id="6598c-336">A</span><span class="sxs-lookup"><span data-stu-id="6598c-336">To</span></span> | <span data-ttu-id="6598c-337">Porta di origine</span><span class="sxs-lookup"><span data-stu-id="6598c-337">Source port</span></span> | <span data-ttu-id="6598c-338">Porta di destinazione</span><span class="sxs-lookup"><span data-stu-id="6598c-338">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="6598c-339">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="6598c-339">UDP/SRTP</span></span> | <span data-ttu-id="6598c-340">Processore multimediale</span><span class="sxs-lookup"><span data-stu-id="6598c-340">Media Processor</span></span> | <span data-ttu-id="6598c-341">SBC</span><span class="sxs-lookup"><span data-stu-id="6598c-341">SBC</span></span> | <span data-ttu-id="6598c-342">3478, 3479 e 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="6598c-342">3478, 3479 and 49 152 – 53 247</span></span>    | <span data-ttu-id="6598c-343">Definito nel controller SBC</span><span class="sxs-lookup"><span data-stu-id="6598c-343">Defined on the SBC</span></span> |
| <span data-ttu-id="6598c-344">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="6598c-344">UDP/SRTP</span></span> | <span data-ttu-id="6598c-345">SBC</span><span class="sxs-lookup"><span data-stu-id="6598c-345">SBC</span></span> | <span data-ttu-id="6598c-346">Processore multimediale</span><span class="sxs-lookup"><span data-stu-id="6598c-346">Media Processor</span></span> | <span data-ttu-id="6598c-347">Definito nel controller SBC</span><span class="sxs-lookup"><span data-stu-id="6598c-347">Defined on the SBC</span></span> | <span data-ttu-id="6598c-348">3478, 3479 e 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="6598c-348">3478, 3479 and 49 152 – 53 247</span></span>     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a><span data-ttu-id="6598c-349">Configurare trunk separati per il bypass multimediale e il bypass non multimediale</span><span class="sxs-lookup"><span data-stu-id="6598c-349">Configure separate trunks for media bypass and non-media bypass</span></span>  

<span data-ttu-id="6598c-350">Se si esegue la migrazione al bypass multimediale da un bypass non multimediale e si vuole confermare la funzionalità prima di eseguire la migrazione di tutto l'utilizzo al bypass multimediale, è possibile creare un trunk separato e criteri di routing vocale separati da instradare al trunk di bypass multimediale e assegnarlo a utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="6598c-350">If you are migrating to media bypass from non-media bypass and want to confirm functionality before migrating all usage to media bypass, you can create a separate trunk and separate Online Voice Routing policy to route to the media bypass trunk and assign to specific users.</span></span> 

<span data-ttu-id="6598c-351">Passaggi di configurazione di alto livello:</span><span class="sxs-lookup"><span data-stu-id="6598c-351">High-level configuration steps:</span></span>

- <span data-ttu-id="6598c-352">Identificare gli utenti per testare il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="6598c-352">Identify users to test media bypass.</span></span>

- <span data-ttu-id="6598c-353">Creare due trunk separati con fqdn diversi: uno abilitato per il bypass multimediale; l'altra no.</span><span class="sxs-lookup"><span data-stu-id="6598c-353">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="6598c-354">Entrambi i trunk puntano allo stesso SBC.</span><span class="sxs-lookup"><span data-stu-id="6598c-354">Both trunks point to the same SBC.</span></span> <span data-ttu-id="6598c-355">Le porte per il traffico di segnalazione SIP TLS devono essere diverse.</span><span class="sxs-lookup"><span data-stu-id="6598c-355">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="6598c-356">Le porte per gli elementi multimediali devono essere uguali.</span><span class="sxs-lookup"><span data-stu-id="6598c-356">The ports for media must be the same.</span></span>

- <span data-ttu-id="6598c-357">Creare un nuovo criterio di routing vocale online e assegnare il trunk di bypass multimediale alle route corrispondenti associate all'utilizzo di PSTN per questo criterio.</span><span class="sxs-lookup"><span data-stu-id="6598c-357">Create a new Online Voice Routing policy and assign the media bypass trunk to the corresponding routes associated with the PSTN usage for this policy.</span></span>

- <span data-ttu-id="6598c-358">Assegnare il nuovo criterio Routing vocale online agli utenti identificati per testare il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="6598c-358">Assign the new Online Voice Routing policy to users you have identified to test media bypass.</span></span>

<span data-ttu-id="6598c-359">L'esempio seguente illustra questa logica.</span><span class="sxs-lookup"><span data-stu-id="6598c-359">The example below illustrates this logic.</span></span>

| <span data-ttu-id="6598c-360">Set di utenti</span><span class="sxs-lookup"><span data-stu-id="6598c-360">Set of users</span></span> | <span data-ttu-id="6598c-361">Numero di utenti</span><span class="sxs-lookup"><span data-stu-id="6598c-361">Number of users</span></span> | <span data-ttu-id="6598c-362">FQDN trunk assegnati in OVRP</span><span class="sxs-lookup"><span data-stu-id="6598c-362">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="6598c-363">Bypass multimediale abilitato</span><span class="sxs-lookup"><span data-stu-id="6598c-363">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="6598c-364">Utenti con trunk di bypass non multimediale</span><span class="sxs-lookup"><span data-stu-id="6598c-364">Users with non-media bypass trunk</span></span> | <span data-ttu-id="6598c-365">980</span><span class="sxs-lookup"><span data-stu-id="6598c-365">980</span></span> | <span data-ttu-id="6598c-366">sbc1.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="6598c-366">sbc1.contoso.com:5060</span></span> | <span data-ttu-id="6598c-367">true</span><span class="sxs-lookup"><span data-stu-id="6598c-367">true</span></span>
<span data-ttu-id="6598c-368">Utenti con trunk del bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="6598c-368">Users with media bypass trunk</span></span> | <span data-ttu-id="6598c-369">20</span><span class="sxs-lookup"><span data-stu-id="6598c-369">20</span></span> | <span data-ttu-id="6598c-370">sbc2.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="6598c-370">sbc2.contoso.com:5061</span></span> | <span data-ttu-id="6598c-371">false</span><span class="sxs-lookup"><span data-stu-id="6598c-371">false</span></span> | 

<span data-ttu-id="6598c-372">Entrambi i trunk possono puntare allo stesso SBC con lo stesso indirizzo IP pubblico.</span><span class="sxs-lookup"><span data-stu-id="6598c-372">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="6598c-373">Le porte di segnalazione TLS nell'SBC devono essere diverse, come illustrato nel diagramma seguente.</span><span class="sxs-lookup"><span data-stu-id="6598c-373">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="6598c-374">Tenere presente che è necessario verificare che il certificato supporti entrambi i trunk.</span><span class="sxs-lookup"><span data-stu-id="6598c-374">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="6598c-375">In SAN è necessario avere due nomi (**sbc1.contoso.com** e **sbc2.contoso.com**) o un certificato con caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="6598c-375">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6598c-376">![Mostra che entrambi i trunk possono puntare allo stesso SBC con lo stesso IP pubblico](media/direct-routing-media-bypass-7.png)</span><span class="sxs-lookup"><span data-stu-id="6598c-376">![Shows both trunks can point to the same SBC with the same public IP](media/direct-routing-media-bypass-7.png)</span></span>

<span data-ttu-id="6598c-377">Per informazioni su come configurare due trunk nello stesso SBC, vedere la documentazione fornita dal fornitore di SBC:</span><span class="sxs-lookup"><span data-stu-id="6598c-377">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

 - [<span data-ttu-id="6598c-378">Documentazione sulla distribuzione di AudioCodes</span><span class="sxs-lookup"><span data-stu-id="6598c-378">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="6598c-379">Documentazione della distribuzione Oracle</span><span class="sxs-lookup"><span data-stu-id="6598c-379">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="6598c-380">Documentazione sulla distribuzione di Ribbon Communications</span><span class="sxs-lookup"><span data-stu-id="6598c-380">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="6598c-381">Documentazione sulla distribuzione di TE-Systems (anynode)</span><span class="sxs-lookup"><span data-stu-id="6598c-381">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="6598c-382">Endpoint client supportati con bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="6598c-382">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="6598c-383">Il bypass multimediale è supportato con tutti i client autonomi di Teams Desktop, i client Android e iOS e i dispositivi telefonici di Teams.</span><span class="sxs-lookup"><span data-stu-id="6598c-383">Media bypass is supported with all standalone Teams Desktop clients, Android and iOS clients and Teams Phone Devices.</span></span> 

<span data-ttu-id="6598c-384">Per tutti gli altri endpoint che non supportano il bypass multimediale, la chiamata verrà convertita in non bypass anche se è stata avviata come chiamata di bypass.</span><span class="sxs-lookup"><span data-stu-id="6598c-384">For all other endpoints that do not support media bypass, we will convert the call to non-bypass even if it started as a bypass call.</span></span> <span data-ttu-id="6598c-385">Questa operazione viene eseguita automaticamente e non richiede alcuna azione da parte dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="6598c-385">This happens automatically and does not require any actions from the administrator.</span></span> <span data-ttu-id="6598c-386">Sono inclusi i telefoni 3PIP di Skype for Business e i client Web di Teams che supportano le chiamate di routing diretto (client basati su WebRTC in esecuzione su Microsoft Edge, Google Chrome, Mozilla Firefox).</span><span class="sxs-lookup"><span data-stu-id="6598c-386">This includes Skype for Business 3PIP Phones, and Teams Web Clients that support Direct Routing calling (WebRTC based clients running on Microsoft Edge, Google Chrome, Mozilla Firefox).</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="6598c-387">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6598c-387">See also</span></span>

[<span data-ttu-id="6598c-388">Configurare il bypass multimediale con Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="6598c-388">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)



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
ms.openlocfilehash: efd6d4275d1e83df7821f178ddac8027039b6fce
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790658"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="4f5d0-103">Pianificare il bypass multimediale con Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="4f5d0-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="4f5d0-104">Informazioni sul bypass multimediale con routing diretto</span><span class="sxs-lookup"><span data-stu-id="4f5d0-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="4f5d0-105">Il bypass multimediale consente di abbreviare il percorso del traffico multimediale e ridurre il numero di hop in transito per migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="4f5d0-106">Con il bypass multimediale, gli elementi multimediali vengono mantenuti tra il session border controller (SBC) e il client invece di inviarli tramite il Sistema telefonico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="4f5d0-107">Per configurare il bypass multimediale, SBC e il client devono essere nella stessa posizione o rete.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="4f5d0-108">È possibile controllare il bypass multimediale per ogni SBC usando il comando **Set-CSOnlinePSTNGateway** con il parametro **-MediaBypass** impostato su true o false.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="4f5d0-109">Se abiliti il bypass multimediale, ciò non significa che tutto il traffico multimediale resterà all'interno della rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="4f5d0-110">Questo articolo descrive il flusso delle chiamate in diversi scenari.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-110">This article describes the call flow in different scenarios.</span></span>    

<span data-ttu-id="4f5d0-111">I diagrammi seguenti illustrano la differenza nel flusso delle chiamate con e senza bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="4f5d0-112">Senza bypass multimediale, quando un client effettua o riceve una chiamata, sia il traffico di segnalazione che il flusso multimediale tra SBC, Il Sistema telefonico Microsoft e il client Teams, come illustrato nel diagramma seguente:</span><span class="sxs-lookup"><span data-stu-id="4f5d0-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4f5d0-113">![Mostra il traffico di segnalazione e il flusso multimediale senza bypass multimediale](media/direct-routing-media-bypass-1.png)</span><span class="sxs-lookup"><span data-stu-id="4f5d0-113">![Shows signaling and media flow without media bypass](media/direct-routing-media-bypass-1.png)</span></span>


<span data-ttu-id="4f5d0-114">Si supponga però che un utente si trova nello stesso edificio o rete del database SBC.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="4f5d0-115">Si supponga, ad esempio, che un utente che si trova in un edificio di Gateway effettua una chiamata a un utente PSTN:</span><span class="sxs-lookup"><span data-stu-id="4f5d0-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="4f5d0-116">**Senza bypass multimediale,** gli elementi multimediali fluiranno attraverso Amsterdam o Dublino (in cui sono distribuiti i data center Microsoft) e tornano alla SBC in Avi.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-116">**Without media bypass**, media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="4f5d0-117">Il data center in Europa è selezionato perché il database SBC si trova in Europa e Microsoft usa il data center più vicino a SBC.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="4f5d0-118">Anche se questo approccio non influisce sulla qualità delle chiamate a causa dell'ottimizzazione del flusso del traffico all'interno delle reti Microsoft nella maggior parte delle aree geografiche, il traffico presenta un ciclo non necessario.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="4f5d0-119">**Con il bypass** multimediale, i contenuti multimediali vengono mantenuti direttamente tra l'utente di Teams e il controller SBC, come illustrato nel diagramma seguente:</span><span class="sxs-lookup"><span data-stu-id="4f5d0-119">**With media bypass**, the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="4f5d0-120">![Mostra il traffico di segnalazione e il flusso multimediale con bypass multimediale](media/direct-routing-media-bypass-2.png)</span><span class="sxs-lookup"><span data-stu-id="4f5d0-120">![Shows signaling and media flow with media bypass](media/direct-routing-media-bypass-2.png)</span></span>

<span data-ttu-id="4f5d0-121">Il bypass multimediale utilizza protocolli chiamati Interactive Connectivity Connectivity (ICE) sul client Teams e ICE lite sul sistema SBC.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE lite on the SBC.</span></span> <span data-ttu-id="4f5d0-122">Questi protocolli consentono di usare il percorso multimediale più diretto per una qualità ottimale.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="4f5d0-123">ICE e ICE Lite sono standard WebRTC.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="4f5d0-124">Per informazioni dettagliate su questi protocolli, vedere RFC 5245.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="4f5d0-125">Flusso delle chiamate e pianificazione del firewall</span><span class="sxs-lookup"><span data-stu-id="4f5d0-125">Call flow and firewall planning</span></span>

<span data-ttu-id="4f5d0-126">Il flusso delle chiamate e la pianificazione del firewall dipendono dal fatto che l'utente abbia accesso diretto all'indirizzo IP pubblico del database SBC e che l'utente sia all'interno o all'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="4f5d0-127">Flusso delle chiamate se l'utente ha accesso diretto all'indirizzo IP pubblico del servizio SBC</span><span class="sxs-lookup"><span data-stu-id="4f5d0-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="4f5d0-128">Se l'utente ha accesso diretto all'indirizzo IP pubblico del servizio SBC, il flusso delle chiamate è il seguente:</span><span class="sxs-lookup"><span data-stu-id="4f5d0-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="4f5d0-129">Per il bypass multimediale, il client Teams deve avere accesso all'indirizzo IP pubblico del servizio SBC anche da una rete interna.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="4f5d0-130">Se non si desidera utilizzare elementi multimediali diretti, il flusso degli elementi multimediali può essere inoltrato tramite Transport Relays.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="4f5d0-131">Questa è la soluzione consigliata quando un utente si trova nella stessa edificio e/o rete del servizio SBC, rimuovendo i componenti Microsoft Cloud dal percorso multimediale.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="4f5d0-132">Il traffico di segnalazione fluisce sempre attraverso il cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="4f5d0-133">Il diagramma seguente mostra il flusso delle chiamate quando è abilitato il bypass multimediale, il client è interno e può raggiungere l'indirizzo IP pubblico del SBC (supporto diretto):</span><span class="sxs-lookup"><span data-stu-id="4f5d0-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="4f5d0-134">Le frecce e i valori numerici dei percorsi sono conformi ai flussi delle [chiamate di Microsoft Teams.](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)</span><span class="sxs-lookup"><span data-stu-id="4f5d0-134">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows).</span></span>

- <span data-ttu-id="4f5d0-135">Il traffico di segnalazione SIP prende sempre i percorsi 4 e 4' (a seconda della direzione del traffico).</span><span class="sxs-lookup"><span data-stu-id="4f5d0-135">The SIP signaling always takes paths 4 and 4' (depending on the direction of the traffic).</span></span> <span data-ttu-id="4f5d0-136">L'elemento multimediale rimane locale e prende il percorso 5b.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-136">Media stays local and takes path 5b.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4f5d0-137">![Mostra il flusso delle chiamate con il bypass multimediale abilitato, il client è interno](media/direct-routing-media-bypass-3.png)</span><span class="sxs-lookup"><span data-stu-id="4f5d0-137">![Shows Call flow with Media Bypass enabled, client is internal](media/direct-routing-media-bypass-3.png)</span></span>


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="4f5d0-138">Flusso delle chiamate se l'utente non ha accesso all'indirizzo IP pubblico del servizio SBC</span><span class="sxs-lookup"><span data-stu-id="4f5d0-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="4f5d0-139">Di seguito viene descritto il flusso delle chiamate se l'utente non ha accesso all'indirizzo IP pubblico del servizio SBC.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="4f5d0-140">Ad esempio, si supponga che l'utente sia esterno e che l'amministratore del tenant abbia deciso di non aprire l'indirizzo IP pubblico del servizio SBC a tutti gli utenti in Internet, ma solo a Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="4f5d0-141">I componenti interni del traffico possono essere trasmessi tramite i Relay di trasporto di Teams.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="4f5d0-142">Tenere in considerazione gli aspetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4f5d0-142">Consider the following:</span></span>

- <span data-ttu-id="4f5d0-143">Vengono usati i Relay di trasporto di Teams.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-143">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="4f5d0-144">Per il bypass multimediale, Microsoft usa una versione di Transport Relays che richiede l'apertura delle porte da 50 000 a 59 999 tra i Inoltro di trasporto di Teams e SBC (in futuro prevede di passare alla versione che richiede solo 3478 e 3479 porte).</span><span class="sxs-lookup"><span data-stu-id="4f5d0-144">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires only 3478 and 3479 ports).</span></span>


<span data-ttu-id="4f5d0-145">Il diagramma seguente mostra il flusso delle chiamate quando è abilitato il bypass multimediale, il client è esterno e il client non può raggiungere l'indirizzo IP pubblico del controller dei confini della sessione (il supporto viene inoltrato da Teams Transport Relay).</span><span class="sxs-lookup"><span data-stu-id="4f5d0-145">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="4f5d0-146">Le frecce e i valori numerici dei percorsi sono conformi ai flussi delle [chiamate di Microsoft Teams.](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)</span><span class="sxs-lookup"><span data-stu-id="4f5d0-146">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows).</span></span>

- <span data-ttu-id="4f5d0-147">Gli elementi multimediali vengono inoltrati tramite percorsi 3, 3', 4 e 4'</span><span class="sxs-lookup"><span data-stu-id="4f5d0-147">Media is relayed via paths 3, 3', 4 and 4'</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4f5d0-148">![Mostra il flusso delle chiamate se l'utente non ha accesso all'IP pubblico di SBC](media/direct-routing-media-bypass-4.png)</span><span class="sxs-lookup"><span data-stu-id="4f5d0-148">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-4.png)</span></span>


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="4f5d0-149">Flusso delle chiamate se un utente è esterno alla rete e ha accesso all'indirizzo IP pubblico dell'SBC</span><span class="sxs-lookup"><span data-stu-id="4f5d0-149">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="4f5d0-150">Questa non è una configurazione consigliata perché non sfrutta i servizi di inoltro di trasporto di Teams.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-150">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="4f5d0-151">È invece opportuno considerare lo scenario precedente in cui l'utente non ha accesso all'indirizzo IP pubblico del database SBC.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-151">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="4f5d0-152">Il diagramma seguente mostra il flusso delle chiamate quando è abilitato il bypass multimediale, il client è esterno e può raggiungere l'indirizzo IP pubblico del SBC (supporto diretto).</span><span class="sxs-lookup"><span data-stu-id="4f5d0-152">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="4f5d0-153">Le frecce e i valori numerici dei percorsi sono conformi all'articolo flussi delle chiamate [di Microsoft Teams.](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)</span><span class="sxs-lookup"><span data-stu-id="4f5d0-153">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="4f5d0-154">Il traffico di segnalazione SIP prende sempre i percorsi 3 e 3' (a seconda della direzione del traffico).</span><span class="sxs-lookup"><span data-stu-id="4f5d0-154">The SIP signaling always takes paths 3 and 3' (depending on the direction of the traffic).</span></span> <span data-ttu-id="4f5d0-155">Flussi multimediali utilizzando il percorso 2.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-155">Media flows using path 2.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4f5d0-156">![Mostra il flusso delle chiamate se l'utente non ha accesso all'IP pubblico di SBC](media/direct-routing-media-bypass-5.png)</span><span class="sxs-lookup"><span data-stu-id="4f5d0-156">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-5.png)</span></span>


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="4f5d0-157">Uso dei processori multimediali e degli inoltri di trasporto</span><span class="sxs-lookup"><span data-stu-id="4f5d0-157">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="4f5d0-158">Nel cloud Microsoft possono essere presenti due componenti nel percorso del traffico multimediale: Processori multimediali e Inoltro di trasporto.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-158">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="4f5d0-159">Il processore multimediale è un componente pubblico che gestisce gli elementi multimediali in casi di bypass e gestisce gli elementi multimediali per le applicazioni vocali.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-159">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="4f5d0-160">I processori multimediali sono sempre nel percorso per le chiamate senza bypass da parte dell'utente finale, ma mai nel percorso per le chiamate bypassate.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-160">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="4f5d0-161">I processori multimediali sono sempre presenti nel percorso per tutte le applicazioni vocali, ad esempio Il Parco chiamate, l'organizzazione Operatore automatico e le code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-161">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="4f5d0-162">L'inoltro di trasporto viene usato per connettersi al servizio di trasporto più vicino per inviare il traffico in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-162">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="4f5d0-163">I Transport Relay possono essere o meno nel percorso per le chiamate ignorate, provenienti o destinate agli utenti finali, a seconda di dove si trova l'utente e di come è configurata la rete.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-163">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="4f5d0-164">Il diagramma seguente mostra due flussi delle chiamate: uno con il bypass multimediale abilitato e il secondo con il bypass multimediale disabilitato.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-164">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span> <span data-ttu-id="4f5d0-165">Si noti che il diagramma illustra solo il traffico proveniente da, o destinato a, gli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-165">Note the diagram only illustrates traffic originating from--or destined to--end users.</span></span>  
- <span data-ttu-id="4f5d0-166">Il controller multimediale è un microservice in Azure che assegna processori multimediali e crea offerte SDP (Session Description Protocol).</span><span class="sxs-lookup"><span data-stu-id="4f5d0-166">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="4f5d0-167">Il proxy SIP è un componente che traduce il traffico REST HTTP utilizzato in Teams in SIP.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-167">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4f5d0-168">![Mostra i flussi delle chiamate con il bypass multimediale abilitato e disabilitato](media/direct-routing-media-bypass-6.png)</span><span class="sxs-lookup"><span data-stu-id="4f5d0-168">![Shows call flows with Media Bypass enabled and disabled](media/direct-routing-media-bypass-6.png)</span></span>


<span data-ttu-id="4f5d0-169">La tabella seguente riepiloga la differenza tra processori multimediali e inoltro di trasporto.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-169">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="4f5d0-170">Processori multimediali</span><span class="sxs-lookup"><span data-stu-id="4f5d0-170">Media Processors</span></span> | <span data-ttu-id="4f5d0-171">Inoltro di trasporto</span><span class="sxs-lookup"><span data-stu-id="4f5d0-171">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="4f5d0-172">Percorso multimediale per chiamate senza bypass per gli utenti finali</span><span class="sxs-lookup"><span data-stu-id="4f5d0-172">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="4f5d0-173">Sempre</span><span class="sxs-lookup"><span data-stu-id="4f5d0-173">Always</span></span> | <span data-ttu-id="4f5d0-174">Mai</span><span class="sxs-lookup"><span data-stu-id="4f5d0-174">Never</span></span> | 
<span data-ttu-id="4f5d0-175">Percorso multimediale per le chiamate ignorate per gli utenti finali</span><span class="sxs-lookup"><span data-stu-id="4f5d0-175">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="4f5d0-176">Mai</span><span class="sxs-lookup"><span data-stu-id="4f5d0-176">Never</span></span> | <span data-ttu-id="4f5d0-177">Se il client non riesce a raggiungere SBC nell'indirizzo IP pubblico</span><span class="sxs-lookup"><span data-stu-id="4f5d0-177">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="4f5d0-178">Percorso multimediale per le applicazioni vocali</span><span class="sxs-lookup"><span data-stu-id="4f5d0-178">In media path for voice applications</span></span> | <span data-ttu-id="4f5d0-179">Sempre</span><span class="sxs-lookup"><span data-stu-id="4f5d0-179">Always</span></span> | <span data-ttu-id="4f5d0-180">Mai</span><span class="sxs-lookup"><span data-stu-id="4f5d0-180">Never</span></span> | 
<span data-ttu-id="4f5d0-181">Può eseguire la trascodtura (B2BUA)\*</span><span class="sxs-lookup"><span data-stu-id="4f5d0-181">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="4f5d0-182">Sì</span><span class="sxs-lookup"><span data-stu-id="4f5d0-182">Yes</span></span> | <span data-ttu-id="4f5d0-183">No, l'audio viene inoltrato solo tra gli endpoint</span><span class="sxs-lookup"><span data-stu-id="4f5d0-183">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="4f5d0-184">Numero di istanze in tutto il mondo e località</span><span class="sxs-lookup"><span data-stu-id="4f5d0-184">Number of instances worldwide and location</span></span> | <span data-ttu-id="4f5d0-185">10 totale: 2 negli Stati Uniti orientali e orientali; 2 ad Amsterdam e Dublino; 2 a Hong Kong e Singapore; 2 in Giappone ; 2 in Australia orientale e sud-orientale</span><span class="sxs-lookup"><span data-stu-id="4f5d0-185">10 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan ; 2 in Australia East and Southeast</span></span> | <span data-ttu-id="4f5d0-186">Multiplo</span><span class="sxs-lookup"><span data-stu-id="4f5d0-186">Multiple</span></span>

<span data-ttu-id="4f5d0-187">Gli intervalli IP sono:</span><span class="sxs-lookup"><span data-stu-id="4f5d0-187">The IP ranges are:</span></span>
- <span data-ttu-id="4f5d0-188">52.112.0.0/14 (indirizzi IP da 52.112.0.1 a 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="4f5d0-188">52.112.0.0/14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>
- <span data-ttu-id="4f5d0-189">52.120.0.0/14 (indirizzi IP da 52.120.0.1 a 52.123.255.254)</span><span class="sxs-lookup"><span data-stu-id="4f5d0-189">52.120.0.0/14 (IP addresses from 52.120.0.1 to 52.123.255.254)</span></span>

<span data-ttu-id="4f5d0-190">\* Spiegazione trascrittura:</span><span class="sxs-lookup"><span data-stu-id="4f5d0-190">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="4f5d0-191">Processore multimediale è B2BUA, il che significa che può modificare un codec (ad esempio, SILK dal client Teams a MP e G.711 tra MP e SBC).</span><span class="sxs-lookup"><span data-stu-id="4f5d0-191">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="4f5d0-192">I inoltro di trasporto non sono B2BUA, il che significa che il codec non viene mai modificato tra il client e SBC, anche se il traffico passa attraverso gli inoltri.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-192">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="4f5d0-193">Uso dei processori multimediali di Teams se è configurato il trunk per il bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="4f5d0-193">Use of Teams Media Processors if trunk is configured for media bypass</span></span>

<span data-ttu-id="4f5d0-194">I processori multimediali di Teams vengono sempre inseriti nel percorso multimediale negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="4f5d0-194">Teams Media Processors are always inserted in the media path in the following scenarios:</span></span>

- <span data-ttu-id="4f5d0-195">La chiamata viene inoltrata da una chiamata 1:1 a una chiamata di gruppo</span><span class="sxs-lookup"><span data-stu-id="4f5d0-195">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="4f5d0-196">La chiamata è per un utente di Teams federato</span><span class="sxs-lookup"><span data-stu-id="4f5d0-196">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="4f5d0-197">La chiamata viene inoltrata o trasferita a un utente Skype for Business</span><span class="sxs-lookup"><span data-stu-id="4f5d0-197">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="4f5d0-198">Assicurarsi che SBC abbia accesso agli intervalli Media Processors e Transport Relays come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-198">Ensure your SBC has access to the Media Processors and Transport Relays ranges as described below.</span></span>    


## <a name="sip-signaling-fqdns"></a><span data-ttu-id="4f5d0-199">Segnalazione SIP: FQDN</span><span class="sxs-lookup"><span data-stu-id="4f5d0-199">SIP Signaling: FQDNs</span></span>

<span data-ttu-id="4f5d0-200">Per il traffico di segnalazione SIP, i requisiti di FQDN e firewall sono gli stessi dei casi non bypassati.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-200">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="4f5d0-201">Il routing diretto è offerto nei seguenti ambienti Microsoft 365 o Office 365:</span><span class="sxs-lookup"><span data-stu-id="4f5d0-201">Direct Routing is offered in the following Microsoft 365 or Office 365 environments:</span></span>
- <span data-ttu-id="4f5d0-202">Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="4f5d0-202">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="4f5d0-203">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="4f5d0-203">Office 365 GCC</span></span>
- <span data-ttu-id="4f5d0-204">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="4f5d0-204">Office 365 GCC High</span></span>
- <span data-ttu-id="4f5d0-205">Office 365 DoD Altre informazioni sugli ambienti di [Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) e US Government come GCC, GCC High e DoD.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-205">Office 365 DoD Learn more about [Office 365 and US Government environments](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="4f5d0-206">Ambienti Microsoft 365, Office 365 e Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="4f5d0-206">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

<span data-ttu-id="4f5d0-207">I punti di connessione per il routing diretto sono i tre FQDN seguenti:</span><span class="sxs-lookup"><span data-stu-id="4f5d0-207">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="4f5d0-208">**sip.pstnhub.microsoft.com,** nome di dominio completo globale, devono essere provati prima.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-208">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="4f5d0-209">Quando SBC invia una richiesta di risoluzione di questo nome, i server DNS di Microsoft Azure restituiscono un indirizzo IP che punta al data center primario di Azure assegnato a SBC.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-209">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="4f5d0-210">L'assegnazione si basa sulle metriche di prestazioni dei data center e sulla prossimità geografica del centro dati per SBC.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-210">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="4f5d0-211">L'indirizzo IP restituito corrisponde all'FQDN principale.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-211">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="4f5d0-212">**sip2.pstnhub.microsoft.com** - FQDN secondario: corrisponde geograficamente alla seconda area geografica di priorità.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-212">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="4f5d0-213">**sip3.pstnhub.microsoft.com-** FQDN terziario: corrisponde geograficamente alla terza area geografica con priorità.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-213">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="4f5d0-214">È necessario inserire questi tre FQDN per:</span><span class="sxs-lookup"><span data-stu-id="4f5d0-214">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="4f5d0-215">Offrire un'esperienza ottimale, ovvero meno caricata e più vicina al data center SBC assegnato mediante query sul primo FQDN.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-215">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="4f5d0-216">Fornire il failover quando viene stabilita una connessione da un database SBC a un data center in cui si verifica un problema temporaneo.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-216">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="4f5d0-217">Per altre informazioni, vedere il meccanismo di failover seguente.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-217">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="4f5d0-218">I nomi di **sip.pstnhub.microsoft.com,** **sip2.pstnhub.microsoft.com** **e** sip3.pstnhub.microsoft.com verranno risolti in uno degli indirizzi IP seguenti:</span><span class="sxs-lookup"><span data-stu-id="4f5d0-218">The FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**, and **sip3.pstnhub.microsoft.com** will be resolved to one of the following IP addresses:</span></span>
- <span data-ttu-id="4f5d0-219">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="4f5d0-219">52.114.148.0</span></span>
- <span data-ttu-id="4f5d0-220">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="4f5d0-220">52.114.132.46</span></span>
- <span data-ttu-id="4f5d0-221">52.114.16.74</span><span class="sxs-lookup"><span data-stu-id="4f5d0-221">52.114.16.74</span></span>
- <span data-ttu-id="4f5d0-222">52.114.20.29</span><span class="sxs-lookup"><span data-stu-id="4f5d0-222">52.114.20.29</span></span>
- <span data-ttu-id="4f5d0-223">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="4f5d0-223">52.114.75.24</span></span>
- <span data-ttu-id="4f5d0-224">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="4f5d0-224">52.114.76.76</span></span>
- <span data-ttu-id="4f5d0-225">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="4f5d0-225">52.114.7.24</span></span>
- <span data-ttu-id="4f5d0-226">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="4f5d0-226">52.114.14.70</span></span>

<span data-ttu-id="4f5d0-227">Devi aprire le porte di tutti questi indirizzi IP nel firewall per consentire il traffico in ingresso e in uscita da e verso gli indirizzi per il traffico di segnalazione.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-227">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="4f5d0-228">Se il firewall supporta i nomi DNS, l'FQDN **sip-all.pstnhub.microsoft.com** risolve in tutti questi indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-228">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="4f5d0-229">Ambiente DoD GCC di Office 365</span><span class="sxs-lookup"><span data-stu-id="4f5d0-229">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="4f5d0-230">Il punto di connessione per il routing diretto è il seguente FQDN:</span><span class="sxs-lookup"><span data-stu-id="4f5d0-230">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="4f5d0-231">**sip.pstnhub.dod.teams.microsoft.us:** FQDN globale.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-231">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="4f5d0-232">Poiché l'ambiente DoD di Office 365 esiste solo nei data center degli Stati Uniti, non sono presenti FQDN secondari e terziari.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-232">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="4f5d0-233">I nomi di sip.pstnhub.dod.teams.microsoft.us sono stati risolti in uno degli indirizzi IP seguenti:</span><span class="sxs-lookup"><span data-stu-id="4f5d0-233">The FQDNs – sip.pstnhub.dod.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="4f5d0-234">52.127.64.33</span><span class="sxs-lookup"><span data-stu-id="4f5d0-234">52.127.64.33</span></span>
- <span data-ttu-id="4f5d0-235">52.127.68.34</span><span class="sxs-lookup"><span data-stu-id="4f5d0-235">52.127.68.34</span></span>

<span data-ttu-id="4f5d0-236">Devi aprire le porte di tutti questi indirizzi IP nel firewall per consentire il traffico in ingresso e in uscita da e verso gli indirizzi per il traffico di segnalazione.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-236">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="4f5d0-237">Se il firewall supporta i nomi DNS, l'FQDN sip.pstnhub.dod.teams.microsoft.us risolve in tutti questi indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-237">If your firewall supports DNS names, the FQDN  sip.pstnhub.dod.teams.microsoft.us resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="4f5d0-238">Ambiente Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="4f5d0-238">Office 365 GCC High environment</span></span>

<span data-ttu-id="4f5d0-239">Il punto di connessione per il routing diretto è il seguente FQDN:</span><span class="sxs-lookup"><span data-stu-id="4f5d0-239">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="4f5d0-240">**sip.pstnhub.gov.teams.microsoft.us:** FQDN globale.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-240">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="4f5d0-241">Poiché l'ambiente GCC High esiste solo nei data center degli Stati Uniti, non sono presenti FQDN secondari e terziari.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-241">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="4f5d0-242">I nomi di sip.pstnhub.gov.teams.microsoft.us sono stati risolti in uno degli indirizzi IP seguenti:</span><span class="sxs-lookup"><span data-stu-id="4f5d0-242">The FQDNs – sip.pstnhub.gov.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="4f5d0-243">52.127.88.59</span><span class="sxs-lookup"><span data-stu-id="4f5d0-243">52.127.88.59</span></span>
- <span data-ttu-id="4f5d0-244">52.127.92.64</span><span class="sxs-lookup"><span data-stu-id="4f5d0-244">52.127.92.64</span></span>

<span data-ttu-id="4f5d0-245">Devi aprire le porte di tutti questi indirizzi IP nel firewall per consentire il traffico in ingresso e in uscita da e verso gli indirizzi per il traffico di segnalazione.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-245">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="4f5d0-246">Se il firewall supporta i nomi DNS, l'FQDN sip.pstnhub.gov.teams.microsoft.us risolve in tutti questi indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-246">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP addresses.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="4f5d0-247">Segnalazione SIP: Porte</span><span class="sxs-lookup"><span data-stu-id="4f5d0-247">SIP Signaling: Ports</span></span>

<span data-ttu-id="4f5d0-248">I requisiti di porta sono gli stessi per tutti gli ambienti di Office 365 in cui è offerto il routing diretto:</span><span class="sxs-lookup"><span data-stu-id="4f5d0-248">Port requirements are the same for all Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="4f5d0-249">Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="4f5d0-249">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="4f5d0-250">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="4f5d0-250">Office 365 GCC</span></span>
- <span data-ttu-id="4f5d0-251">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="4f5d0-251">Office 365 GCC High</span></span>
- <span data-ttu-id="4f5d0-252">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="4f5d0-252">Office 365 DoD</span></span>

<span data-ttu-id="4f5d0-253">È necessario usare le porte seguenti:</span><span class="sxs-lookup"><span data-stu-id="4f5d0-253">You must use the following ports:</span></span>

| <span data-ttu-id="4f5d0-254">Traffico</span><span class="sxs-lookup"><span data-stu-id="4f5d0-254">Traffic</span></span> | <span data-ttu-id="4f5d0-255">Da</span><span class="sxs-lookup"><span data-stu-id="4f5d0-255">From</span></span> | <span data-ttu-id="4f5d0-256">A</span><span class="sxs-lookup"><span data-stu-id="4f5d0-256">To</span></span> | <span data-ttu-id="4f5d0-257">Porta di origine</span><span class="sxs-lookup"><span data-stu-id="4f5d0-257">Source port</span></span> | <span data-ttu-id="4f5d0-258">Porta di destinazione</span><span class="sxs-lookup"><span data-stu-id="4f5d0-258">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="4f5d0-259">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="4f5d0-259">SIP/TLS</span></span>| <span data-ttu-id="4f5d0-260">SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="4f5d0-260">SIP Proxy</span></span> | <span data-ttu-id="4f5d0-261">SBC</span><span class="sxs-lookup"><span data-stu-id="4f5d0-261">SBC</span></span> | <span data-ttu-id="4f5d0-262">1024 - 65535</span><span class="sxs-lookup"><span data-stu-id="4f5d0-262">1024 - 65535</span></span> | <span data-ttu-id="4f5d0-263">Definito nell'SBC</span><span class="sxs-lookup"><span data-stu-id="4f5d0-263">Defined on the SBC</span></span> |
| <span data-ttu-id="4f5d0-264">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="4f5d0-264">SIP/TLS</span></span> | <span data-ttu-id="4f5d0-265">SBC</span><span class="sxs-lookup"><span data-stu-id="4f5d0-265">SBC</span></span> | <span data-ttu-id="4f5d0-266">SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="4f5d0-266">SIP Proxy</span></span> | <span data-ttu-id="4f5d0-267">Definito nell'SBC</span><span class="sxs-lookup"><span data-stu-id="4f5d0-267">Defined on the SBC</span></span> | <span data-ttu-id="4f5d0-268">5061</span><span class="sxs-lookup"><span data-stu-id="4f5d0-268">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="4f5d0-269">Traffico multimediale: intervalli ip e di porta</span><span class="sxs-lookup"><span data-stu-id="4f5d0-269">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="4f5d0-270">Il traffico multimediale passa tra il client SBC e il client Teams se la connettività diretta è disponibile o tramite i Relay di trasporto di Teams se il client non può raggiungere sBC usando l'indirizzo IP pubblico.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-270">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="4f5d0-271">Requisiti per il traffico multimediale diretto (tra il client Teams e SBC)</span><span class="sxs-lookup"><span data-stu-id="4f5d0-271">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="4f5d0-272">Il client deve avere accesso alle porte specificate (vedere la tabella) nell'indirizzo IP pubblico del servizio SBC.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-272">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

<span data-ttu-id="4f5d0-273">Nota: se il client si trova in una rete interna, il flusso degli elementi multimediali viene indirizzato all'indirizzo IP pubblico del servizio SBC.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-273">Note: If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="4f5d0-274">Puoi configurare il blocco dei capelli nel tuo dispositivo NAT in modo che il traffico non lasci mai l'apparecchiatura di rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-274">You can configure hair pinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="4f5d0-275">Traffico</span><span class="sxs-lookup"><span data-stu-id="4f5d0-275">Traffic</span></span> | <span data-ttu-id="4f5d0-276">Da</span><span class="sxs-lookup"><span data-stu-id="4f5d0-276">From</span></span> | <span data-ttu-id="4f5d0-277">A</span><span class="sxs-lookup"><span data-stu-id="4f5d0-277">To</span></span> | <span data-ttu-id="4f5d0-278">Porta di origine</span><span class="sxs-lookup"><span data-stu-id="4f5d0-278">Source port</span></span> | <span data-ttu-id="4f5d0-279">Porta di destinazione</span><span class="sxs-lookup"><span data-stu-id="4f5d0-279">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="4f5d0-280">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="4f5d0-280">UDP/SRTP</span></span> | <span data-ttu-id="4f5d0-281">Client</span><span class="sxs-lookup"><span data-stu-id="4f5d0-281">Client</span></span> | <span data-ttu-id="4f5d0-282">SBC</span><span class="sxs-lookup"><span data-stu-id="4f5d0-282">SBC</span></span> | <span data-ttu-id="4f5d0-283">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="4f5d0-283">50 000 – 50 019</span></span>  | <span data-ttu-id="4f5d0-284">Definito nell'SBC</span><span class="sxs-lookup"><span data-stu-id="4f5d0-284">Defined on the SBC</span></span> |
| <span data-ttu-id="4f5d0-285">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="4f5d0-285">UDP/SRTP</span></span> | <span data-ttu-id="4f5d0-286">SBC</span><span class="sxs-lookup"><span data-stu-id="4f5d0-286">SBC</span></span> | <span data-ttu-id="4f5d0-287">Client</span><span class="sxs-lookup"><span data-stu-id="4f5d0-287">Client</span></span> | <span data-ttu-id="4f5d0-288">Definito nell'SBC</span><span class="sxs-lookup"><span data-stu-id="4f5d0-288">Defined on the SBC</span></span> | <span data-ttu-id="4f5d0-289">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="4f5d0-289">50 000 – 50 019</span></span>  |


> [!NOTE]
> <span data-ttu-id="4f5d0-290">Se si dispone di un dispositivo di rete che traduce le porte di origine del client, assicurarsi che le porte tradotte siano aperte tra l'apparecchiatura di rete e SBC.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-290">If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="4f5d0-291">Requisiti per l'uso degli inoltri di trasporto</span><span class="sxs-lookup"><span data-stu-id="4f5d0-291">Requirements for using Transport Relays</span></span>

<span data-ttu-id="4f5d0-292">Gli Inoltro di trasporto sono nello stesso intervallo dei processori multimediali (per i casi non bypass):</span><span class="sxs-lookup"><span data-stu-id="4f5d0-292">Transport Relays are in the same range as Media Processors (for non-bypass cases):</span></span> 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="4f5d0-293">Ambienti Microsoft 365, Office 365 e Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="4f5d0-293">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

- <span data-ttu-id="4f5d0-294">52.112.0.0 /14 (indirizzi IP da 52.112.0.1 a 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="4f5d0-294">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="4f5d0-295">Ambiente DoD GCC di Office 365</span><span class="sxs-lookup"><span data-stu-id="4f5d0-295">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="4f5d0-296">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="4f5d0-296">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="4f5d0-297">Ambiente Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="4f5d0-297">Office 365 GCC High environment</span></span>

- <span data-ttu-id="4f5d0-298">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="4f5d0-298">52.127.88.0/21</span></span>


<span data-ttu-id="4f5d0-299">L'intervallo di porta dei relay di trasporto di Teams (applicabili a tutti gli ambienti) è illustrato nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="4f5d0-299">The port range of the Teams Transport Relays (applicable to all environments) is shown in the following table:</span></span>


| <span data-ttu-id="4f5d0-300">Traffico</span><span class="sxs-lookup"><span data-stu-id="4f5d0-300">Traffic</span></span> | <span data-ttu-id="4f5d0-301">Da</span><span class="sxs-lookup"><span data-stu-id="4f5d0-301">From</span></span> | <span data-ttu-id="4f5d0-302">A</span><span class="sxs-lookup"><span data-stu-id="4f5d0-302">To</span></span> | <span data-ttu-id="4f5d0-303">Porta di origine</span><span class="sxs-lookup"><span data-stu-id="4f5d0-303">Source port</span></span> | <span data-ttu-id="4f5d0-304">Porta di destinazione</span><span class="sxs-lookup"><span data-stu-id="4f5d0-304">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="4f5d0-305">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="4f5d0-305">UDP/SRTP</span></span> | <span data-ttu-id="4f5d0-306">Inoltro di trasporto</span><span class="sxs-lookup"><span data-stu-id="4f5d0-306">Transport Relay</span></span> | <span data-ttu-id="4f5d0-307">SBC</span><span class="sxs-lookup"><span data-stu-id="4f5d0-307">SBC</span></span> | <span data-ttu-id="4f5d0-308">50 000 -59 999</span><span class="sxs-lookup"><span data-stu-id="4f5d0-308">50 000 -59 999</span></span>    | <span data-ttu-id="4f5d0-309">Definito nell'SBC</span><span class="sxs-lookup"><span data-stu-id="4f5d0-309">Defined on the SBC</span></span> |
| <span data-ttu-id="4f5d0-310">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="4f5d0-310">UDP/SRTP</span></span> | <span data-ttu-id="4f5d0-311">SBC</span><span class="sxs-lookup"><span data-stu-id="4f5d0-311">SBC</span></span> | <span data-ttu-id="4f5d0-312">Inoltro di trasporto</span><span class="sxs-lookup"><span data-stu-id="4f5d0-312">Transport Relay</span></span> | <span data-ttu-id="4f5d0-313">Definito nell'SBC</span><span class="sxs-lookup"><span data-stu-id="4f5d0-313">Defined on the SBC</span></span> | <span data-ttu-id="4f5d0-314">50 000 – 59 999, 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="4f5d0-314">50 000 – 59 999, 3478, 3479</span></span>     |


> [!NOTE]
> <span data-ttu-id="4f5d0-315">Microsoft consiglia almeno due porte per ogni chiamata simultanea sull'SBC.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-315">Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="4f5d0-316">Poiché Microsoft ha due versioni di Inoltro di trasporto, sono necessarie le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4f5d0-316">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>
> 
> - <span data-ttu-id="4f5d0-317">v4, che può funzionare solo con l'intervallo di porte da 50 000 a 59 999</span><span class="sxs-lookup"><span data-stu-id="4f5d0-317">v4, which can only work with port range 50 000 to 59 999</span></span>
> 
> - <span data-ttu-id="4f5d0-318">v6, che funziona con le porte 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="4f5d0-318">v6, which works with ports 3478, 3479</span></span>

<span data-ttu-id="4f5d0-319">Al momento, il bypass multimediale supporta solo la versione v4 dei transport relay.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-319">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="4f5d0-320">In futuro verrà introdotto il supporto della v6.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-320">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="4f5d0-321">È necessario aprire le porte 3478 e 3479 per la transizione.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-321">You need to open ports 3478 and 3479 for transitioning.</span></span> <span data-ttu-id="4f5d0-322">Quando Microsoft introduce il supporto per i Transport Relay v6 con Media Bypass, non sarà necessario riconfigurare le apparecchiature di rete o i dispositivi di rete.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-322">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="4f5d0-323">Requisiti per l'uso dei processori multimediali</span><span class="sxs-lookup"><span data-stu-id="4f5d0-323">Requirements for using media processors</span></span>

<span data-ttu-id="4f5d0-324">I processori multimediali sono sempre nel percorso multimediale per le applicazioni vocali e per i client Web (ad esempio, i client Teams in Edge o Google Chrome).</span><span class="sxs-lookup"><span data-stu-id="4f5d0-324">Media Processors are always in the media path for voice applications and for Web clients (for example, Teams clients in Edge or Google Chrome).</span></span> <span data-ttu-id="4f5d0-325">I requisiti sono gli stessi della configurazione senza bypass.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-325">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="4f5d0-326">L'intervallo IP per il traffico multimediale è</span><span class="sxs-lookup"><span data-stu-id="4f5d0-326">The IP range for media traffic is</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="4f5d0-327">Ambienti GCC di Office 365 e Office 365</span><span class="sxs-lookup"><span data-stu-id="4f5d0-327">Office 365 and Office 365 GCC environments</span></span>

- <span data-ttu-id="4f5d0-328">52.112.0.0 /14 (indirizzi IP da 52.112.0.1 a 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="4f5d0-328">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="4f5d0-329">Ambiente DoD GCC di Office 365</span><span class="sxs-lookup"><span data-stu-id="4f5d0-329">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="4f5d0-330">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="4f5d0-330">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="4f5d0-331">Ambiente Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="4f5d0-331">Office 365 GCC High environment</span></span>

- <span data-ttu-id="4f5d0-332">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="4f5d0-332">52.127.88.0/21</span></span>

<span data-ttu-id="4f5d0-333">L'intervallo di porta dei processori multimediali (applicabile a tutti gli ambienti) è illustrato nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="4f5d0-333">The port range of the Media Processors (applicable to all environments) is shown in the following table:</span></span>

| <span data-ttu-id="4f5d0-334">Traffico</span><span class="sxs-lookup"><span data-stu-id="4f5d0-334">Traffic</span></span> | <span data-ttu-id="4f5d0-335">Da</span><span class="sxs-lookup"><span data-stu-id="4f5d0-335">From</span></span> | <span data-ttu-id="4f5d0-336">A</span><span class="sxs-lookup"><span data-stu-id="4f5d0-336">To</span></span> | <span data-ttu-id="4f5d0-337">Porta di origine</span><span class="sxs-lookup"><span data-stu-id="4f5d0-337">Source port</span></span> | <span data-ttu-id="4f5d0-338">Porta di destinazione</span><span class="sxs-lookup"><span data-stu-id="4f5d0-338">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="4f5d0-339">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="4f5d0-339">UDP/SRTP</span></span> | <span data-ttu-id="4f5d0-340">Processore multimediale</span><span class="sxs-lookup"><span data-stu-id="4f5d0-340">Media Processor</span></span> | <span data-ttu-id="4f5d0-341">SBC</span><span class="sxs-lookup"><span data-stu-id="4f5d0-341">SBC</span></span> | <span data-ttu-id="4f5d0-342">3478, 3479 e 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="4f5d0-342">3478, 3479 and 49 152 – 53 247</span></span>    | <span data-ttu-id="4f5d0-343">Definito nell'SBC</span><span class="sxs-lookup"><span data-stu-id="4f5d0-343">Defined on the SBC</span></span> |
| <span data-ttu-id="4f5d0-344">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="4f5d0-344">UDP/SRTP</span></span> | <span data-ttu-id="4f5d0-345">SBC</span><span class="sxs-lookup"><span data-stu-id="4f5d0-345">SBC</span></span> | <span data-ttu-id="4f5d0-346">Processore multimediale</span><span class="sxs-lookup"><span data-stu-id="4f5d0-346">Media Processor</span></span> | <span data-ttu-id="4f5d0-347">Definito nell'SBC</span><span class="sxs-lookup"><span data-stu-id="4f5d0-347">Defined on the SBC</span></span> | <span data-ttu-id="4f5d0-348">3478, 3479 e 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="4f5d0-348">3478, 3479 and 49 152 – 53 247</span></span>     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a><span data-ttu-id="4f5d0-349">Configurare trunk separati per il bypass multimediale e il bypass non multimediale</span><span class="sxs-lookup"><span data-stu-id="4f5d0-349">Configure separate trunks for media bypass and non-media bypass</span></span>  

<span data-ttu-id="4f5d0-350">Se si esegue la migrazione al bypass multimediale da un bypass non multimediale e si vuole confermare la funzionalità prima di eseguire la migrazione di tutto l'utilizzo al bypass multimediale, è possibile creare un trunk separato e criteri di routing vocale separati da instradare al trunk di bypass multimediale e assegnarlo a utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-350">If you are migrating to media bypass from non-media bypass and want to confirm functionality before migrating all usage to media bypass, you can create a separate trunk and separate Online Voice Routing policy to route to the media bypass trunk and assign to specific users.</span></span> 

<span data-ttu-id="4f5d0-351">Passaggi di configurazione di alto livello:</span><span class="sxs-lookup"><span data-stu-id="4f5d0-351">High-level configuration steps:</span></span>

- <span data-ttu-id="4f5d0-352">Identificare gli utenti per testare il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-352">Identify users to test media bypass.</span></span>

- <span data-ttu-id="4f5d0-353">Creare due trunk separati con fqdn diversi: uno abilitato per il bypass multimediale; l'altra no.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-353">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="4f5d0-354">Entrambi i trunk puntano allo stesso SBC.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-354">Both trunks point to the same SBC.</span></span> <span data-ttu-id="4f5d0-355">Le porte per il traffico di segnalazione SIP TLS devono essere diverse.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-355">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="4f5d0-356">Le porte dei supporti multimediali devono essere uguali.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-356">The ports for media must be the same.</span></span>

- <span data-ttu-id="4f5d0-357">Creare un nuovo criterio di routing vocale online e assegnare il trunk di bypass multimediale alle route corrispondenti associate all'utilizzo di PSTN per questo criterio.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-357">Create a new Online Voice Routing policy and assign the media bypass trunk to the corresponding routes associated with the PSTN usage for this policy.</span></span>

- <span data-ttu-id="4f5d0-358">Assegnare il nuovo criterio Routing vocale online agli utenti identificati per testare il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-358">Assign the new Online Voice Routing policy to users you have identified to test media bypass.</span></span>

<span data-ttu-id="4f5d0-359">L'esempio seguente illustra questa logica.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-359">The example below illustrates this logic.</span></span>

| <span data-ttu-id="4f5d0-360">Set di utenti</span><span class="sxs-lookup"><span data-stu-id="4f5d0-360">Set of users</span></span> | <span data-ttu-id="4f5d0-361">Numero di utenti</span><span class="sxs-lookup"><span data-stu-id="4f5d0-361">Number of users</span></span> | <span data-ttu-id="4f5d0-362">FQDN trunk assegnati in OVRP</span><span class="sxs-lookup"><span data-stu-id="4f5d0-362">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="4f5d0-363">Bypass multimediale abilitato</span><span class="sxs-lookup"><span data-stu-id="4f5d0-363">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="4f5d0-364">Utenti con trunk di bypass non multimediale</span><span class="sxs-lookup"><span data-stu-id="4f5d0-364">Users with non-media bypass trunk</span></span> | <span data-ttu-id="4f5d0-365">980</span><span class="sxs-lookup"><span data-stu-id="4f5d0-365">980</span></span> | <span data-ttu-id="4f5d0-366">sbc1.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="4f5d0-366">sbc1.contoso.com:5060</span></span> | <span data-ttu-id="4f5d0-367">true</span><span class="sxs-lookup"><span data-stu-id="4f5d0-367">true</span></span>
<span data-ttu-id="4f5d0-368">Utenti con trunk del bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="4f5d0-368">Users with media bypass trunk</span></span> | <span data-ttu-id="4f5d0-369">20</span><span class="sxs-lookup"><span data-stu-id="4f5d0-369">20</span></span> | <span data-ttu-id="4f5d0-370">sbc2.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="4f5d0-370">sbc2.contoso.com:5061</span></span> | <span data-ttu-id="4f5d0-371">false</span><span class="sxs-lookup"><span data-stu-id="4f5d0-371">false</span></span> | 

<span data-ttu-id="4f5d0-372">Entrambi i trunk possono puntare allo stesso SBC con lo stesso indirizzo IP pubblico.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-372">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="4f5d0-373">Le porte di segnalazione TLS nell'SBC devono essere diverse, come illustrato nel diagramma seguente.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-373">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="4f5d0-374">Tenere presente che è necessario verificare che il certificato supporti entrambi i trunk.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-374">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="4f5d0-375">In SAN è necessario avere due nomi (**sbc1.contoso.com** e **sbc2.contoso.com**) o un certificato con caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-375">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4f5d0-376">![Mostra che entrambi i trunk possono puntare allo stesso SBC con lo stesso IP pubblico](media/direct-routing-media-bypass-7.png)</span><span class="sxs-lookup"><span data-stu-id="4f5d0-376">![Shows both trunks can point to the same SBC with the same public IP](media/direct-routing-media-bypass-7.png)</span></span>

<span data-ttu-id="4f5d0-377">Per informazioni su come configurare due trunk nello stesso SBC, vedere la documentazione fornita dal fornitore di SBC:</span><span class="sxs-lookup"><span data-stu-id="4f5d0-377">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

 - [<span data-ttu-id="4f5d0-378">Documentazione sulla distribuzione di AudioCodes</span><span class="sxs-lookup"><span data-stu-id="4f5d0-378">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="4f5d0-379">Documentazione della distribuzione Oracle</span><span class="sxs-lookup"><span data-stu-id="4f5d0-379">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="4f5d0-380">Documentazione sulla distribuzione di Ribbon Communications</span><span class="sxs-lookup"><span data-stu-id="4f5d0-380">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="4f5d0-381">Documentazione sulla distribuzione di TE-Systems (anynode)</span><span class="sxs-lookup"><span data-stu-id="4f5d0-381">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="4f5d0-382">Endpoint client supportati con bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="4f5d0-382">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="4f5d0-383">Il bypass multimediale è supportato con tutti i client autonomi di Teams Desktop, i client Android e iOS e i dispositivi telefonici di Teams.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-383">Media bypass is supported with all standalone Teams Desktop clients, Android and iOS clients and Teams Phone Devices.</span></span> 

<span data-ttu-id="4f5d0-384">Per tutti gli altri endpoint che non supportano il bypass multimediale, la chiamata verrà convertita in non bypass anche se è stata avviata come chiamata di bypass.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-384">For all other endpoints that do not support media bypass, we will convert the call to non-bypass even if it started as a bypass call.</span></span> <span data-ttu-id="4f5d0-385">Questa operazione viene eseguita automaticamente e non richiede alcuna azione da parte dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="4f5d0-385">This happens automatically and does not require any actions from the administrator.</span></span> <span data-ttu-id="4f5d0-386">Sono inclusi i telefoni 3PIP di Skype for Business e i client Web di Teams che supportano le chiamate di routing diretto (client basati su WebRTC in esecuzione su Microsoft Edge, Google Chrome, Mozilla Firefox).</span><span class="sxs-lookup"><span data-stu-id="4f5d0-386">This includes Skype for Business 3PIP Phones, and Teams Web Clients that support Direct Routing calling (WebRTC based clients running on Microsoft Edge, Google Chrome, Mozilla Firefox).</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="4f5d0-387">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f5d0-387">See also</span></span>

[<span data-ttu-id="4f5d0-388">Configurare il bypass multimediale con Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="4f5d0-388">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)



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
description: Informazioni su come pianificare il bypass multimediale con il routing diretto del sistema telefonico, che consente di ridurre il percorso del traffico multimediale e migliorare le prestazioni.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a4f8995c3972da8fd2d060b7083edb61138b97ac
ms.sourcegitcommit: f63cf7fdde333a7cb36c39e9b6cdc33afd2b4601
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "44338246"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="1ff4a-103">Pianificare il bypass multimediale con Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="1ff4a-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="1ff4a-104">Informazioni sul bypass multimediale con routing diretto</span><span class="sxs-lookup"><span data-stu-id="1ff4a-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="1ff4a-105">Il bypass multimediale consente di abbreviare il percorso del traffico multimediale e ridurre il numero di hop in transito per migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="1ff4a-106">Con il bypass multimediale, l'elemento multimediale viene mantenuto tra l'SBC (Session Border Controller) e il client invece di inviarlo tramite il sistema telefonico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="1ff4a-107">Per configurare il bypass multimediale, il SBC e il client devono trovarsi nella stessa posizione o rete.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="1ff4a-108">Puoi controllare il bypass multimediale per ogni SBC usando il comando **set-CSOnlinePSTNGateway** con il parametro **-MediaBypass** impostato su true o false.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="1ff4a-109">Se si Abilita il bypass multimediale, questo non significa che tutto il traffico multimediale rimarrà all'interno della rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="1ff4a-110">In questo articolo viene descritto il flusso delle chiamate in scenari diversi.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-110">This article describes the call flow in different scenarios.</span></span>    

<span data-ttu-id="1ff4a-111">I diagrammi seguenti illustrano la differenza di flusso delle chiamate con e senza bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="1ff4a-112">Senza bypass multimediale, quando un client effettua o riceve una chiamata, sia la segnalazione che il flusso multimediale tra SBC, Microsoft Phone System e il client teams, come illustrato nel diagramma seguente:</span><span class="sxs-lookup"><span data-stu-id="1ff4a-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

![Mostra la segnalazione e il flusso multimediale senza bypass multimediale](media/direct-routing-media-bypass-1.png)


<span data-ttu-id="1ff4a-114">Supponiamo però che un utente si trovi nello stesso edificio o rete di SBC.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="1ff4a-115">Supponiamo ad esempio che un utente che si trova in un edificio di Francoforte effettua una chiamata a un utente PSTN:</span><span class="sxs-lookup"><span data-stu-id="1ff4a-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="1ff4a-116">**Senza bypass multimediale**, il flusso multimediale verrà eseguito tramite Amsterdam o Dublin (dove vengono distribuiti i datacenter Microsoft) e di nuovo all'SBC di Francoforte.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-116">**Without media bypass**, media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="1ff4a-117">Il Data Center in Europa è selezionato perché il SBC è in Europa e Microsoft usa il data center più vicino a SBC.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="1ff4a-118">Sebbene questo approccio non influenzi la qualità della chiamata a causa dell'ottimizzazione del flusso di traffico all'interno delle reti Microsoft nella maggior parte delle aree geografiche, il traffico ha un ciclo non necessario.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="1ff4a-119">**Con il bypass multimediale**, il supporto viene mantenuto direttamente tra l'utente teams e il SBC, come illustrato nel diagramma seguente:</span><span class="sxs-lookup"><span data-stu-id="1ff4a-119">**With media bypass**, the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

![Mostra la segnalazione e il flusso multimediale con il bypass multimediale](media/direct-routing-media-bypass-2.png)

<span data-ttu-id="1ff4a-121">Il bypass multimediale sfrutta i protocolli denominati Interactive Connectivity Establishment (ICE) nel client teams e ICE Lite su SBC.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE lite on the SBC.</span></span> <span data-ttu-id="1ff4a-122">Questi protocolli consentono al routing diretto di usare il percorso multimediale più diretto per ottenere una qualità ottimale.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="1ff4a-123">ICE e ICE Lite sono standard WebRTC.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="1ff4a-124">Per informazioni dettagliate su questi protocolli, vedere RFC 5245.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="1ff4a-125">Pianificazione del flusso delle chiamate e del firewall</span><span class="sxs-lookup"><span data-stu-id="1ff4a-125">Call flow and firewall planning</span></span>

<span data-ttu-id="1ff4a-126">Il flusso delle chiamate e la pianificazione del firewall variano a seconda che l'utente abbia accesso diretto all'indirizzo IP pubblico dell'SBC e se l'utente si trova all'interno o all'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="1ff4a-127">Flusso delle chiamate se l'utente ha accesso diretto all'indirizzo IP pubblico di SBC</span><span class="sxs-lookup"><span data-stu-id="1ff4a-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="1ff4a-128">Se l'utente ha accesso diretto all'indirizzo IP pubblico dell'SBC, il flusso delle chiamate è il seguente:</span><span class="sxs-lookup"><span data-stu-id="1ff4a-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="1ff4a-129">Per il bypass multimediale, il client Teams deve avere accesso all'indirizzo IP pubblico dell'SBC anche da una rete interna.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="1ff4a-130">Se l'elemento multimediale diretto non è desiderato, il contenuto multimediale può scorrere tramite Relay di trasporto.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="1ff4a-131">Questa è la soluzione consigliata quando un utente si trova nello stesso edificio e/o rete come SBC: rimuove i componenti cloud Microsoft dal percorso multimediale.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="1ff4a-132">La segnalazione scorre sempre tramite il cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="1ff4a-133">Il diagramma seguente mostra il flusso delle chiamate quando il bypass multimediale è abilitato, il client è interno e il client può raggiungere l'indirizzo IP pubblico di SBC (Direct Media):</span><span class="sxs-lookup"><span data-stu-id="1ff4a-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="1ff4a-134">Le frecce e i valori numerici dei percorsi sono conformi all'articolo [flussi di chiamata di Microsoft teams](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) .</span><span class="sxs-lookup"><span data-stu-id="1ff4a-134">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="1ff4a-135">La segnalazione SIP prende sempre i percorsi 4 e 4' (a seconda della direzione del traffico).</span><span class="sxs-lookup"><span data-stu-id="1ff4a-135">The SIP signaling always takes paths 4 and 4' (depending on the direction of the traffic).</span></span> <span data-ttu-id="1ff4a-136">Media rimane locale e prende il percorso 5B.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-136">Media stays local and takes path 5b.</span></span>

![Mostra il flusso delle chiamate con il bypass multimediale abilitato, il client è interno](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="1ff4a-138">Flusso delle chiamate se l'utente non ha accesso all'indirizzo IP pubblico di SBC</span><span class="sxs-lookup"><span data-stu-id="1ff4a-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="1ff4a-139">Di seguito viene descritto il flusso delle chiamate se l'utente non ha accesso all'indirizzo IP pubblico di SBC.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="1ff4a-140">Supponiamo ad esempio che l'utente sia esterno e che l'amministratore del tenant abbia deciso di non aprire l'indirizzo IP pubblico di SBC a tutti gli utenti di Internet, ma solo al cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="1ff4a-141">I componenti interni del traffico possono fluire tramite i relay di trasporto di teams.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="1ff4a-142">Questa è la configurazione consigliata per gli utenti esterni alla rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-142">This is the recommended configuration for users outside of the corporate network.</span></span> <span data-ttu-id="1ff4a-143">Tenere in considerazione gli aspetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="1ff4a-143">Consider the following:</span></span>

- <span data-ttu-id="1ff4a-144">Vengono usati i relè di trasporto teams.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-144">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="1ff4a-145">Per il bypass multimediale, Microsoft usa una versione di relay di trasporto che richiede l'apertura delle porte da 50 000 a 59 999 tra i relay di trasporto di teams e il SBC (in futuro prevediamo di passare alla versione che richiede solo le porte 3478 e 3479).</span><span class="sxs-lookup"><span data-stu-id="1ff4a-145">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires only 3478 and 3479 ports).</span></span>

- <span data-ttu-id="1ff4a-146">Per scopi di ottimizzazione multimediale, Microsoft consiglia di aprire l'indirizzo IP pubblico di SBC solo ai relay di trasporto di teams.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-146">For media optimization purposes, Microsoft recommends opening the public IP address of the SBC only to Teams Transport Relays.</span></span> <span data-ttu-id="1ff4a-147">Per i client esterni alla rete aziendale, Microsoft consiglia di usare i relay di trasporto invece di raggiungere direttamente l'indirizzo IP pubblico di SBC.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-147">For clients outside of the corporate network, Microsoft recommends using Transport Relays instead of reaching the public IP address of the SBC directly.</span></span>

<span data-ttu-id="1ff4a-148">Il diagramma seguente mostra il flusso delle chiamate quando l'esclusione multimediale è abilitata, il client è esterno e il client non riesce a raggiungere l'indirizzo IP pubblico del controller di bordo della sessione (il supporto viene inoltrato dall'inoltro del trasporto di Teams).</span><span class="sxs-lookup"><span data-stu-id="1ff4a-148">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="1ff4a-149">Le frecce e i valori numerici dei percorsi sono conformi all'articolo [flussi di chiamata di Microsoft teams](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) .</span><span class="sxs-lookup"><span data-stu-id="1ff4a-149">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="1ff4a-150">Il supporto viene inoltrato tramite i percorsi 3, 3', 4 e 4'</span><span class="sxs-lookup"><span data-stu-id="1ff4a-150">Media is relayed via paths 3, 3', 4 and 4'</span></span>

![Mostra il flusso delle chiamate se l'utente non ha accesso a un IP pubblico di SBC](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="1ff4a-152">Flusso delle chiamate se un utente si trova all'esterno della rete e ha accesso all'IP pubblico di SBC</span><span class="sxs-lookup"><span data-stu-id="1ff4a-152">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="1ff4a-153">Non si tratta di una configurazione consigliata perché non sfrutta i relè di trasporto di teams.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-153">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="1ff4a-154">Dovresti invece prendere in considerazione lo scenario precedente in cui l'utente non ha accesso all'indirizzo IP pubblico di SBC.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-154">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="1ff4a-155">Il diagramma seguente mostra il flusso delle chiamate quando il bypass multimediale è abilitato, il client è esterno e il client può raggiungere l'indirizzo IP pubblico del SBC (Direct Media).</span><span class="sxs-lookup"><span data-stu-id="1ff4a-155">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="1ff4a-156">Le frecce e i valori numerici dei percorsi sono conformi all'articolo [flussi di chiamata di Microsoft teams](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) .</span><span class="sxs-lookup"><span data-stu-id="1ff4a-156">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="1ff4a-157">La segnalazione SIP accetta sempre i percorsi 3 e 3' (a seconda della direzione del traffico).</span><span class="sxs-lookup"><span data-stu-id="1ff4a-157">The SIP signaling always takes paths 3 and 3' (depending on the direction of the traffic).</span></span> <span data-ttu-id="1ff4a-158">Flussi multimediali tramite il percorso 2.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-158">Media flows using path 2.</span></span>

![Mostra il flusso delle chiamate se l'utente non ha accesso a un IP pubblico di SBC](media/direct-routing-media-bypass-5.png)


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="1ff4a-160">Uso di processori multimediali e relè di trasporto</span><span class="sxs-lookup"><span data-stu-id="1ff4a-160">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="1ff4a-161">Nel cloud Microsoft sono presenti due componenti che possono essere nel percorso del traffico multimediale: processori multimediali e relay di trasporto.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-161">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="1ff4a-162">Il media processor è un componente pubblico che gestisce i contenuti multimediali in casi non di bypass e gestisce elementi multimediali per le applicazioni vocali.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-162">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="1ff4a-163">I processori multimediali sono sempre nel percorso per le chiamate non ignorate dall'utente finale, ma non nel percorso per le chiamate ignorate.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-163">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="1ff4a-164">I processori multimediali sono sempre nel percorso per tutte le applicazioni vocali, ad esempio Call Park, operatore automatico dell'organizzazione e code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-164">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="1ff4a-165">L'inoltro di trasporto viene usato per connettersi al servizio di trasporto più vicino per inviare il traffico in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-165">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="1ff4a-166">I relè di trasporto potrebbero non essere nel percorso per le chiamate ignorate, provenienti da o destinati agli utenti finali, a seconda della posizione dell'utente e della configurazione della rete.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-166">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="1ff4a-167">Il diagramma seguente mostra due flussi di chiamata: uno con bypass multimediale abilitato e il secondo con bypass multimediale disabilitato.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-167">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span> <span data-ttu-id="1ff4a-168">Nota il diagramma illustra solo il traffico proveniente da-o destinato agli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-168">Note the diagram only illustrates traffic originating from--or destined to--end users.</span></span>  
- <span data-ttu-id="1ff4a-169">Il controller multimediale è un microservizio in Azure che assegna processori multimediali e crea offerte SDP (Session Description Protocol).</span><span class="sxs-lookup"><span data-stu-id="1ff4a-169">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="1ff4a-170">Il proxy SIP è un componente che traduce il segnale di REST HTTP usato in teams per il SIP.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-170">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

![Mostra i flussi di chiamata con il bypass multimediale abilitato e disabilitato](media/direct-routing-media-bypass-6.png)


<span data-ttu-id="1ff4a-172">La tabella seguente riepiloga la differenza tra i processori multimediali e i relè di trasporto.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-172">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="1ff4a-173">Processori multimediali</span><span class="sxs-lookup"><span data-stu-id="1ff4a-173">Media Processors</span></span> | <span data-ttu-id="1ff4a-174">Relè di trasporto</span><span class="sxs-lookup"><span data-stu-id="1ff4a-174">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="1ff4a-175">Nel percorso multimediale per le chiamate non ignorate per gli utenti finali</span><span class="sxs-lookup"><span data-stu-id="1ff4a-175">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="1ff4a-176">Sempre</span><span class="sxs-lookup"><span data-stu-id="1ff4a-176">Always</span></span> | <span data-ttu-id="1ff4a-177">Mai</span><span class="sxs-lookup"><span data-stu-id="1ff4a-177">Never</span></span> | 
<span data-ttu-id="1ff4a-178">Nel percorso multimediale per le chiamate ignorate per gli utenti finali</span><span class="sxs-lookup"><span data-stu-id="1ff4a-178">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="1ff4a-179">Mai</span><span class="sxs-lookup"><span data-stu-id="1ff4a-179">Never</span></span> | <span data-ttu-id="1ff4a-180">Se il client non riesce a raggiungere il SBC nell'indirizzo IP pubblico</span><span class="sxs-lookup"><span data-stu-id="1ff4a-180">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="1ff4a-181">Nel percorso multimediale per le applicazioni vocali</span><span class="sxs-lookup"><span data-stu-id="1ff4a-181">In media path for voice applications</span></span> | <span data-ttu-id="1ff4a-182">Sempre</span><span class="sxs-lookup"><span data-stu-id="1ff4a-182">Always</span></span> | <span data-ttu-id="1ff4a-183">Mai</span><span class="sxs-lookup"><span data-stu-id="1ff4a-183">Never</span></span> | 
<span data-ttu-id="1ff4a-184">Può eseguire la transcodifica (B2BUA)\*</span><span class="sxs-lookup"><span data-stu-id="1ff4a-184">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="1ff4a-185">Sì</span><span class="sxs-lookup"><span data-stu-id="1ff4a-185">Yes</span></span> | <span data-ttu-id="1ff4a-186">No, inoltra solo l'audio tra gli endpoint</span><span class="sxs-lookup"><span data-stu-id="1ff4a-186">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="1ff4a-187">Numero di istanze nel mondo e nella posizione</span><span class="sxs-lookup"><span data-stu-id="1ff4a-187">Number of instances worldwide and location</span></span> | <span data-ttu-id="1ff4a-188">8 totale: 2 in Stati Uniti Est e ovest; 2 in Amsterdam e Dublino; 2 a Hong Kong e Singapore; 2 in Giappone</span><span class="sxs-lookup"><span data-stu-id="1ff4a-188">8 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan</span></span>  | <span data-ttu-id="1ff4a-189">Più</span><span class="sxs-lookup"><span data-stu-id="1ff4a-189">Multiple</span></span>

<span data-ttu-id="1ff4a-190">Gli intervalli IP sono:</span><span class="sxs-lookup"><span data-stu-id="1ff4a-190">The IP ranges are:</span></span>
- <span data-ttu-id="1ff4a-191">52.112.0.0/14 (indirizzi IP da 52.112.0.1 a 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="1ff4a-191">52.112.0.0/14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>
- <span data-ttu-id="1ff4a-192">52.120.0.0/14 (indirizzi IP da 52.120.0.1 a 52.123.255.254)</span><span class="sxs-lookup"><span data-stu-id="1ff4a-192">52.120.0.0/14 (IP addresses from 52.120.0.1 to 52.123.255.254)</span></span>

<span data-ttu-id="1ff4a-193">\*Spiegazione della transcodifica:</span><span class="sxs-lookup"><span data-stu-id="1ff4a-193">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="1ff4a-194">Il media processor è B2BUA, il che significa che può cambiare un codec (ad esempio, SILK from teams client to MP e G. 711 tra MP e SBC).</span><span class="sxs-lookup"><span data-stu-id="1ff4a-194">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="1ff4a-195">I relè di trasporto non sono B2BUA, il che significa che il codec non viene mai modificato tra il client e il SBC, anche se i flussi di traffico tramite Relay.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-195">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="1ff4a-196">Uso dei processori multimediali di teams se trunk è configurato per il bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="1ff4a-196">Use of Teams Media Processors if trunk is configured for media bypass</span></span>

<span data-ttu-id="1ff4a-197">I processori multimediali di teams vengono sempre inseriti nel percorso multimediale negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="1ff4a-197">Teams Media Processors are always inserted in the media path in the following scenarios:</span></span>

- <span data-ttu-id="1ff4a-198">La chiamata viene escalated da 1:1 a una chiamata di gruppo</span><span class="sxs-lookup"><span data-stu-id="1ff4a-198">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="1ff4a-199">Chiamata sta per un utente di Team federati</span><span class="sxs-lookup"><span data-stu-id="1ff4a-199">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="1ff4a-200">La chiamata viene inoltrata o trasferita a un utente di Skype for business</span><span class="sxs-lookup"><span data-stu-id="1ff4a-200">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="1ff4a-201">Verificare che SBC abbia accesso ai processori multimediali e ai relè di trasporto, come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-201">Ensure your SBC has access to the Media Processors and Transport Relays ranges as described below.</span></span>    


## <a name="sip-signaling-fqdns"></a><span data-ttu-id="1ff4a-202">Segnalazione SIP: FQDN</span><span class="sxs-lookup"><span data-stu-id="1ff4a-202">SIP Signaling: FQDNs</span></span>

<span data-ttu-id="1ff4a-203">Per la segnalazione SIP, i requisiti di FQDN e firewall sono gli stessi per i casi non bypassati.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-203">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="1ff4a-204">Il routing diretto è disponibile nei seguenti ambienti di Office 365:</span><span class="sxs-lookup"><span data-stu-id="1ff4a-204">Direct Routing is offered in the following Office 365 environments:</span></span>
- <span data-ttu-id="1ff4a-205">Office 365</span><span class="sxs-lookup"><span data-stu-id="1ff4a-205">Office 365</span></span>
- <span data-ttu-id="1ff4a-206">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="1ff4a-206">Office 365 GCC</span></span>
- <span data-ttu-id="1ff4a-207">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="1ff4a-207">Office 365 GCC High</span></span>
- <span data-ttu-id="1ff4a-208">Office 365 DoD ulteriori informazioni su [office 365 e gli ambienti governativi degli Stati Uniti](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) , ad esempio GCC, GCC High e DOD.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-208">Office 365 DoD Learn more about [Office 365 and US Government environments](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="1ff4a-209">Ambienti Office 365 e Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="1ff4a-209">Office 365 and Office 365 GCC environments</span></span>

<span data-ttu-id="1ff4a-210">I punti di connessione per il routing diretto sono i tre FQDN seguenti:</span><span class="sxs-lookup"><span data-stu-id="1ff4a-210">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="1ff4a-211">**SIP.pstnhub.Microsoft.com** -FQDN globale-deve essere provato per primo.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-211">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="1ff4a-212">Quando il SBC invia una richiesta di risoluzione di questo nome, i server DNS di Microsoft Azure restituiscono un indirizzo IP che punta al Data Center di Azure principale assegnato a SBC.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-212">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="1ff4a-213">L'assegnazione si basa sulle metriche delle prestazioni dei datacenter e sulla vicinanza geografica a SBC.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-213">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="1ff4a-214">L'indirizzo IP restituito corrisponde al nome di dominio completo principale.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-214">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="1ff4a-215">**SIP2.pstnhub.Microsoft.com** -FQDN secondario-Mappa geograficamente alla seconda area di priorità.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-215">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="1ff4a-216">**SIP3.pstnhub.Microsoft.com** -FQDN terziario-Mappa geograficamente alla terza area prioritaria.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-216">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="1ff4a-217">È necessario inserire questi tre nomi di dominio completi per:</span><span class="sxs-lookup"><span data-stu-id="1ff4a-217">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="1ff4a-218">Offre un'esperienza ottimale (meno caricato e più vicino al Data Center SBC assegnato eseguendo una query sul primo FQDN).</span><span class="sxs-lookup"><span data-stu-id="1ff4a-218">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="1ff4a-219">Fornisci il failover quando viene stabilita una connessione da un SBC a un centro dati che sta vivendo un problema temporaneo.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-219">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="1ff4a-220">Per altre informazioni, vedi meccanismo di failover seguente.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-220">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="1ff4a-221">Gli FQDN **SIP.pstnhub.Microsoft.com**, **SIP2.pstnhub.Microsoft.com**e **SIP3.pstnhub.Microsoft.com** verranno risolti in uno degli indirizzi IP seguenti:</span><span class="sxs-lookup"><span data-stu-id="1ff4a-221">The FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**, and **sip3.pstnhub.microsoft.com** will be resolved to one of the following IP addresses:</span></span>
- <span data-ttu-id="1ff4a-222">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="1ff4a-222">52.114.148.0</span></span>
- <span data-ttu-id="1ff4a-223">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="1ff4a-223">52.114.132.46</span></span>
- <span data-ttu-id="1ff4a-224">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="1ff4a-224">52.114.75.24</span></span>
- <span data-ttu-id="1ff4a-225">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="1ff4a-225">52.114.76.76</span></span>
- <span data-ttu-id="1ff4a-226">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="1ff4a-226">52.114.7.24</span></span>
- <span data-ttu-id="1ff4a-227">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="1ff4a-227">52.114.14.70</span></span>

<span data-ttu-id="1ff4a-228">È necessario aprire le porte per tutti questi indirizzi IP nel firewall per consentire il traffico in entrata e in uscita da e verso gli indirizzi per la segnalazione.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-228">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="1ff4a-229">Se il firewall supporta i nomi DNS, il nome FQDN **SIP-all.pstnhub.Microsoft.com** si risolve in tutti questi indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-229">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="1ff4a-230">Office 365 GCC DoD Environment</span><span class="sxs-lookup"><span data-stu-id="1ff4a-230">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="1ff4a-231">Il punto di connessione per il routing diretto è il nome di dominio completo seguente:</span><span class="sxs-lookup"><span data-stu-id="1ff4a-231">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="1ff4a-232">**SIP.pstnhub.DoD.teams.Microsoft.US** -FQDN globale.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-232">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="1ff4a-233">Poiché l'ambiente Office 365 DoD esiste solo nei data center degli Stati Uniti, non esistono nomi di dominio completi secondari e terziari.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-233">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="1ff4a-234">Gli FQDN-sip.pstnhub.dod.teams.microsoft.us verranno risolti in uno degli indirizzi IP seguenti:</span><span class="sxs-lookup"><span data-stu-id="1ff4a-234">The FQDNs – sip.pstnhub.dod.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="1ff4a-235">52.127.64.33</span><span class="sxs-lookup"><span data-stu-id="1ff4a-235">52.127.64.33</span></span>
- <span data-ttu-id="1ff4a-236">52.127.68.34</span><span class="sxs-lookup"><span data-stu-id="1ff4a-236">52.127.68.34</span></span>

<span data-ttu-id="1ff4a-237">È necessario aprire le porte per tutti questi indirizzi IP nel firewall per consentire il traffico in entrata e in uscita da e verso gli indirizzi per la segnalazione.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-237">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="1ff4a-238">Se il firewall supporta i nomi DNS, il nome FQDN sip.pstnhub.dod.teams.microsoft.us si risolve in tutti questi indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-238">If your firewall supports DNS names, the FQDN  sip.pstnhub.dod.teams.microsoft.us resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="1ff4a-239">Ambiente Office 365 GCC High Environment</span><span class="sxs-lookup"><span data-stu-id="1ff4a-239">Office 365 GCC High environment</span></span>

<span data-ttu-id="1ff4a-240">Il punto di connessione per il routing diretto è il nome di dominio completo seguente:</span><span class="sxs-lookup"><span data-stu-id="1ff4a-240">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="1ff4a-241">**SIP.pstnhub.gov.teams.Microsoft.US** -FQDN globale.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-241">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="1ff4a-242">Dato che l'ambiente GCC High esiste solo nei data center americani, non esistono nomi di dominio completi secondari e terziari.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-242">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="1ff4a-243">Gli FQDN-sip.pstnhub.gov.teams.microsoft.us verranno risolti in uno degli indirizzi IP seguenti:</span><span class="sxs-lookup"><span data-stu-id="1ff4a-243">The FQDNs – sip.pstnhub.gov.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="1ff4a-244">52.127.88.59</span><span class="sxs-lookup"><span data-stu-id="1ff4a-244">52.127.88.59</span></span>
- <span data-ttu-id="1ff4a-245">52.127.92.64</span><span class="sxs-lookup"><span data-stu-id="1ff4a-245">52.127.92.64</span></span>

<span data-ttu-id="1ff4a-246">È necessario aprire le porte per tutti questi indirizzi IP nel firewall per consentire il traffico in entrata e in uscita da e verso gli indirizzi per la segnalazione.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-246">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="1ff4a-247">Se il firewall supporta i nomi DNS, il nome FQDN sip.pstnhub.gov.teams.microsoft.us si risolve in tutti questi indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-247">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP addresses.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="1ff4a-248">Segnalazione SIP: porte</span><span class="sxs-lookup"><span data-stu-id="1ff4a-248">SIP Signaling: Ports</span></span>

<span data-ttu-id="1ff4a-249">I requisiti della porta sono gli stessi per tutti gli ambienti di Office 365 in cui viene offerto il routing diretto:</span><span class="sxs-lookup"><span data-stu-id="1ff4a-249">Port requirements are the same for all Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="1ff4a-250">Office 365</span><span class="sxs-lookup"><span data-stu-id="1ff4a-250">Office 365</span></span>
- <span data-ttu-id="1ff4a-251">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="1ff4a-251">Office 365 GCC</span></span>
- <span data-ttu-id="1ff4a-252">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="1ff4a-252">Office 365 GCC High</span></span>
- <span data-ttu-id="1ff4a-253">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="1ff4a-253">Office 365 DoD</span></span>

<span data-ttu-id="1ff4a-254">È necessario usare le porte seguenti:</span><span class="sxs-lookup"><span data-stu-id="1ff4a-254">You must use the following ports:</span></span>

| <span data-ttu-id="1ff4a-255">Traffico</span><span class="sxs-lookup"><span data-stu-id="1ff4a-255">Traffic</span></span> | <span data-ttu-id="1ff4a-256">Da</span><span class="sxs-lookup"><span data-stu-id="1ff4a-256">From</span></span> | <span data-ttu-id="1ff4a-257">A</span><span class="sxs-lookup"><span data-stu-id="1ff4a-257">To</span></span> | <span data-ttu-id="1ff4a-258">Porta di origine</span><span class="sxs-lookup"><span data-stu-id="1ff4a-258">Source port</span></span> | <span data-ttu-id="1ff4a-259">Porta di destinazione</span><span class="sxs-lookup"><span data-stu-id="1ff4a-259">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="1ff4a-260">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="1ff4a-260">SIP/TLS</span></span>| <span data-ttu-id="1ff4a-261">Proxy SIP</span><span class="sxs-lookup"><span data-stu-id="1ff4a-261">SIP Proxy</span></span> | <span data-ttu-id="1ff4a-262">SBC</span><span class="sxs-lookup"><span data-stu-id="1ff4a-262">SBC</span></span> | <span data-ttu-id="1ff4a-263">1024-65535</span><span class="sxs-lookup"><span data-stu-id="1ff4a-263">1024 - 65535</span></span> | <span data-ttu-id="1ff4a-264">Definita nell'SBC</span><span class="sxs-lookup"><span data-stu-id="1ff4a-264">Defined on the SBC</span></span> |
| <span data-ttu-id="1ff4a-265">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="1ff4a-265">SIP/TLS</span></span> | <span data-ttu-id="1ff4a-266">SBC</span><span class="sxs-lookup"><span data-stu-id="1ff4a-266">SBC</span></span> | <span data-ttu-id="1ff4a-267">Proxy SIP</span><span class="sxs-lookup"><span data-stu-id="1ff4a-267">SIP Proxy</span></span> | <span data-ttu-id="1ff4a-268">Definita nell'SBC</span><span class="sxs-lookup"><span data-stu-id="1ff4a-268">Defined on the SBC</span></span> | <span data-ttu-id="1ff4a-269">5061</span><span class="sxs-lookup"><span data-stu-id="1ff4a-269">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="1ff4a-270">Traffico multimediale: intervalli di indirizzi IP e di porte</span><span class="sxs-lookup"><span data-stu-id="1ff4a-270">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="1ff4a-271">I flussi di traffico multimediale tra il client SBC e teams se la connettività diretta è disponibile o tramite Relay di trasporto teams se il client non riesce a raggiungere il SBC usando l'indirizzo IP pubblico.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-271">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="1ff4a-272">Requisiti per il traffico multimediale diretto (tra il client teams e il SBC)</span><span class="sxs-lookup"><span data-stu-id="1ff4a-272">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="1ff4a-273">Il client deve avere accesso alle porte specificate (Vedi tabella) nell'indirizzo IP pubblico di SBC.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-273">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

<span data-ttu-id="1ff4a-274">Nota: se il client si trova in una rete interna, il contenuto multimediale passa all'indirizzo IP pubblico di SBC.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-274">Note: If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="1ff4a-275">Puoi configurare il blocco dei capelli nel dispositivo NAT in modo che il traffico non lasci mai l'apparecchiatura di rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-275">You can configure hair pinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="1ff4a-276">Traffico</span><span class="sxs-lookup"><span data-stu-id="1ff4a-276">Traffic</span></span> | <span data-ttu-id="1ff4a-277">Da</span><span class="sxs-lookup"><span data-stu-id="1ff4a-277">From</span></span> | <span data-ttu-id="1ff4a-278">A</span><span class="sxs-lookup"><span data-stu-id="1ff4a-278">To</span></span> | <span data-ttu-id="1ff4a-279">Porta di origine</span><span class="sxs-lookup"><span data-stu-id="1ff4a-279">Source port</span></span> | <span data-ttu-id="1ff4a-280">Porta di destinazione</span><span class="sxs-lookup"><span data-stu-id="1ff4a-280">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="1ff4a-281">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="1ff4a-281">UDP/SRTP</span></span> | <span data-ttu-id="1ff4a-282">Client</span><span class="sxs-lookup"><span data-stu-id="1ff4a-282">Client</span></span> | <span data-ttu-id="1ff4a-283">SBC</span><span class="sxs-lookup"><span data-stu-id="1ff4a-283">SBC</span></span> | <span data-ttu-id="1ff4a-284">50 000-50 019</span><span class="sxs-lookup"><span data-stu-id="1ff4a-284">50 000 – 50 019</span></span>  | <span data-ttu-id="1ff4a-285">Definita nell'SBC</span><span class="sxs-lookup"><span data-stu-id="1ff4a-285">Defined on the SBC</span></span> |
| <span data-ttu-id="1ff4a-286">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="1ff4a-286">UDP/SRTP</span></span> | <span data-ttu-id="1ff4a-287">SBC</span><span class="sxs-lookup"><span data-stu-id="1ff4a-287">SBC</span></span> | <span data-ttu-id="1ff4a-288">Client</span><span class="sxs-lookup"><span data-stu-id="1ff4a-288">Client</span></span> | <span data-ttu-id="1ff4a-289">Definita nell'SBC</span><span class="sxs-lookup"><span data-stu-id="1ff4a-289">Defined on the SBC</span></span> | <span data-ttu-id="1ff4a-290">50 000-50 019</span><span class="sxs-lookup"><span data-stu-id="1ff4a-290">50 000 – 50 019</span></span>  |


> [!NOTE]
> <span data-ttu-id="1ff4a-291">Se si dispone di un dispositivo di rete che converte le porte di origine del client, verificare che le porte tradotte vengano aperte tra l'apparecchiatura di rete e il SBC.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-291">If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="1ff4a-292">Requisiti per l'uso dei relè di trasporto</span><span class="sxs-lookup"><span data-stu-id="1ff4a-292">Requirements for using Transport Relays</span></span>

<span data-ttu-id="1ff4a-293">I relè di trasporto si trovano nello stesso intervallo dei processori multimediali (per i casi non di bypass):</span><span class="sxs-lookup"><span data-stu-id="1ff4a-293">Transport Relays are in the same range as Media Processors (for non-bypass cases):</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="1ff4a-294">Ambienti Office 365 e Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="1ff4a-294">Office 365 and Office 365 GCC environments</span></span>

- <span data-ttu-id="1ff4a-295">52.112.0.0/14 (indirizzi IP da 52.112.0.1 a 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="1ff4a-295">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="1ff4a-296">Office 365 GCC DoD Environment</span><span class="sxs-lookup"><span data-stu-id="1ff4a-296">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="1ff4a-297">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="1ff4a-297">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="1ff4a-298">Ambiente Office 365 GCC High Environment</span><span class="sxs-lookup"><span data-stu-id="1ff4a-298">Office 365 GCC High environment</span></span>

- <span data-ttu-id="1ff4a-299">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="1ff4a-299">52.127.88.0/21</span></span>


<span data-ttu-id="1ff4a-300">L'intervallo di porte dei relè di trasporto Teams (applicabile a tutti gli ambienti) è illustrato nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="1ff4a-300">The port range of the Teams Transport Relays (applicable to all environments) is shown in the following table:</span></span>


| <span data-ttu-id="1ff4a-301">Traffico</span><span class="sxs-lookup"><span data-stu-id="1ff4a-301">Traffic</span></span> | <span data-ttu-id="1ff4a-302">Da</span><span class="sxs-lookup"><span data-stu-id="1ff4a-302">From</span></span> | <span data-ttu-id="1ff4a-303">A</span><span class="sxs-lookup"><span data-stu-id="1ff4a-303">To</span></span> | <span data-ttu-id="1ff4a-304">Porta di origine</span><span class="sxs-lookup"><span data-stu-id="1ff4a-304">Source port</span></span> | <span data-ttu-id="1ff4a-305">Porta di destinazione</span><span class="sxs-lookup"><span data-stu-id="1ff4a-305">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="1ff4a-306">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="1ff4a-306">UDP/SRTP</span></span> | <span data-ttu-id="1ff4a-307">Inoltro di trasporto</span><span class="sxs-lookup"><span data-stu-id="1ff4a-307">Transport Relay</span></span> | <span data-ttu-id="1ff4a-308">SBC</span><span class="sxs-lookup"><span data-stu-id="1ff4a-308">SBC</span></span> | <span data-ttu-id="1ff4a-309">50 000-59 999</span><span class="sxs-lookup"><span data-stu-id="1ff4a-309">50 000 -59 999</span></span>    | <span data-ttu-id="1ff4a-310">Definita nell'SBC</span><span class="sxs-lookup"><span data-stu-id="1ff4a-310">Defined on the SBC</span></span> |
| <span data-ttu-id="1ff4a-311">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="1ff4a-311">UDP/SRTP</span></span> | <span data-ttu-id="1ff4a-312">SBC</span><span class="sxs-lookup"><span data-stu-id="1ff4a-312">SBC</span></span> | <span data-ttu-id="1ff4a-313">Inoltro di trasporto</span><span class="sxs-lookup"><span data-stu-id="1ff4a-313">Transport Relay</span></span> | <span data-ttu-id="1ff4a-314">Definita nell'SBC</span><span class="sxs-lookup"><span data-stu-id="1ff4a-314">Defined on the SBC</span></span> | <span data-ttu-id="1ff4a-315">50 000-59 999, 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="1ff4a-315">50 000 – 59 999, 3478, 3479</span></span>     |


> [!NOTE]
> <span data-ttu-id="1ff4a-316">Microsoft consiglia almeno due porte per chiamata simultanea su SBC.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-316">Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="1ff4a-317">Poiché Microsoft ha due versioni di relay di trasporto, sono necessarie le seguenti:</span><span class="sxs-lookup"><span data-stu-id="1ff4a-317">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>
> 
> - <span data-ttu-id="1ff4a-318">V4, che può funzionare solo con l'intervallo di porte da 50 000 a 59 999</span><span class="sxs-lookup"><span data-stu-id="1ff4a-318">v4, which can only work with port range 50 000 to 59 999</span></span>
> 
> - <span data-ttu-id="1ff4a-319">V6, che funziona con le porte 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="1ff4a-319">v6, which works with ports 3478, 3479</span></span>

<span data-ttu-id="1ff4a-320">In questo momento, il bypass multimediale supporta solo la versione v4 dei relay di trasporto.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-320">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="1ff4a-321">In futuro presenteremo il supporto di V6.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-321">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="1ff4a-322">È necessario aprire le porte 3478 e 3479 per la transizione.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-322">You need to open ports 3478 and 3479 for transitioning.</span></span> <span data-ttu-id="1ff4a-323">Quando Microsoft introduce il supporto per i relay di trasporto V6 con il bypass multimediale, non sarà necessario riconfigurare l'equipaggiamento di rete o SBCs.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-323">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="1ff4a-324">Requisiti per l'uso dei processori multimediali</span><span class="sxs-lookup"><span data-stu-id="1ff4a-324">Requirements for using media processors</span></span>

<span data-ttu-id="1ff4a-325">I processori multimediali sono sempre nel percorso multimediale per le applicazioni vocali e per i client Web, ad esempio i client teams in Edge o Google Chrome.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-325">Media Processors are always in the media path for voice applications and for Web clients (for example, Teams clients in Edge or Google Chrome).</span></span> <span data-ttu-id="1ff4a-326">I requisiti sono gli stessi della configurazione non di bypass.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-326">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="1ff4a-327">L'intervallo IP per il traffico multimediale è</span><span class="sxs-lookup"><span data-stu-id="1ff4a-327">The IP range for media traffic is</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="1ff4a-328">Ambienti Office 365 e Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="1ff4a-328">Office 365 and Office 365 GCC environments</span></span>

- <span data-ttu-id="1ff4a-329">52.112.0.0/14 (indirizzi IP da 52.112.0.1 a 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="1ff4a-329">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="1ff4a-330">Office 365 GCC DoD Environment</span><span class="sxs-lookup"><span data-stu-id="1ff4a-330">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="1ff4a-331">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="1ff4a-331">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="1ff4a-332">Ambiente Office 365 GCC High Environment</span><span class="sxs-lookup"><span data-stu-id="1ff4a-332">Office 365 GCC High environment</span></span>

- <span data-ttu-id="1ff4a-333">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="1ff4a-333">52.127.88.0/21</span></span>

<span data-ttu-id="1ff4a-334">L'intervallo di porte dei processori multimediali (applicabile a tutti gli ambienti) è illustrato nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="1ff4a-334">The port range of the Media Processors (applicable to all environments) is shown in the following table:</span></span>

| <span data-ttu-id="1ff4a-335">Traffico</span><span class="sxs-lookup"><span data-stu-id="1ff4a-335">Traffic</span></span> | <span data-ttu-id="1ff4a-336">Da</span><span class="sxs-lookup"><span data-stu-id="1ff4a-336">From</span></span> | <span data-ttu-id="1ff4a-337">A</span><span class="sxs-lookup"><span data-stu-id="1ff4a-337">To</span></span> | <span data-ttu-id="1ff4a-338">Porta di origine</span><span class="sxs-lookup"><span data-stu-id="1ff4a-338">Source port</span></span> | <span data-ttu-id="1ff4a-339">Porta di destinazione</span><span class="sxs-lookup"><span data-stu-id="1ff4a-339">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="1ff4a-340">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="1ff4a-340">UDP/SRTP</span></span> | <span data-ttu-id="1ff4a-341">Media processor</span><span class="sxs-lookup"><span data-stu-id="1ff4a-341">Media Processor</span></span> | <span data-ttu-id="1ff4a-342">SBC</span><span class="sxs-lookup"><span data-stu-id="1ff4a-342">SBC</span></span> | <span data-ttu-id="1ff4a-343">3478, 3479 e 49 152-53 247</span><span class="sxs-lookup"><span data-stu-id="1ff4a-343">3478, 3479 and 49 152 – 53 247</span></span>    | <span data-ttu-id="1ff4a-344">Definita nell'SBC</span><span class="sxs-lookup"><span data-stu-id="1ff4a-344">Defined on the SBC</span></span> |
| <span data-ttu-id="1ff4a-345">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="1ff4a-345">UDP/SRTP</span></span> | <span data-ttu-id="1ff4a-346">SBC</span><span class="sxs-lookup"><span data-stu-id="1ff4a-346">SBC</span></span> | <span data-ttu-id="1ff4a-347">Media processor</span><span class="sxs-lookup"><span data-stu-id="1ff4a-347">Media Processor</span></span> | <span data-ttu-id="1ff4a-348">Definita nell'SBC</span><span class="sxs-lookup"><span data-stu-id="1ff4a-348">Defined on the SBC</span></span> | <span data-ttu-id="1ff4a-349">3478, 3479 e 49 152-53 247</span><span class="sxs-lookup"><span data-stu-id="1ff4a-349">3478, 3479 and 49 152 – 53 247</span></span>     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a><span data-ttu-id="1ff4a-350">Configurare trunk separati per il bypass multimediale e il bypass non multimediale</span><span class="sxs-lookup"><span data-stu-id="1ff4a-350">Configure separate trunks for media bypass and non-media bypass</span></span>  

<span data-ttu-id="1ff4a-351">Se si esegue la migrazione a un bypass multimediale da un bypass non multimediale e si vuole confermare la funzionalità prima di eseguire la migrazione di tutto l'utilizzo al bypass multimediale, è possibile creare un trunk separato e separare i criteri di routing vocale online per instradare il trunk di bypass multimediale e assegnare a utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-351">If you are migrating to media bypass from non-media bypass and want to confirm functionality before migrating all usage to media bypass, you can create a separate trunk and separate Online Voice Routing policy to route to the media bypass trunk and assign to specific users.</span></span> 

<span data-ttu-id="1ff4a-352">Passaggi di configurazione di alto livello:</span><span class="sxs-lookup"><span data-stu-id="1ff4a-352">High-level configuration steps:</span></span>

- <span data-ttu-id="1ff4a-353">Identificare gli utenti per testare il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-353">Identify users to test media bypass.</span></span>

- <span data-ttu-id="1ff4a-354">Creare due trunk distinti con nomi di dominio completi diversi: uno abilitato per il bypass multimediale; l'altro no.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-354">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="1ff4a-355">Entrambi i trunk puntano allo stesso SBC.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-355">Both trunks point to the same SBC.</span></span> <span data-ttu-id="1ff4a-356">Le porte per la segnalazione SIP TLS devono essere diverse.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-356">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="1ff4a-357">Le porte per elementi multimediali devono essere le stesse.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-357">The ports for media must be the same.</span></span>

- <span data-ttu-id="1ff4a-358">Creare un nuovo criterio di routing vocale online e assegnare il trunk bypass multimediale alle route corrispondenti associate all'utilizzo PSTN per questo criterio.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-358">Create a new Online Voice Routing policy and assign the media bypass trunk to the corresponding routes associated with the PSTN usage for this policy.</span></span>

- <span data-ttu-id="1ff4a-359">Assegnare i nuovi criteri di routing vocale online agli utenti identificati per testare il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-359">Assign the new Online Voice Routing policy to users you have identified to test media bypass.</span></span>

<span data-ttu-id="1ff4a-360">L'esempio seguente illustra questa logica.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-360">The example below illustrates this logic.</span></span>

| <span data-ttu-id="1ff4a-361">Set di utenti</span><span class="sxs-lookup"><span data-stu-id="1ff4a-361">Set of users</span></span> | <span data-ttu-id="1ff4a-362">Numero di utenti</span><span class="sxs-lookup"><span data-stu-id="1ff4a-362">Number of users</span></span> | <span data-ttu-id="1ff4a-363">FQDN trunk assegnato in OVRP</span><span class="sxs-lookup"><span data-stu-id="1ff4a-363">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="1ff4a-364">Bypass multimediale abilitato</span><span class="sxs-lookup"><span data-stu-id="1ff4a-364">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="1ff4a-365">Utenti con trunk di bypass non multimediale</span><span class="sxs-lookup"><span data-stu-id="1ff4a-365">Users with non-media bypass trunk</span></span> | <span data-ttu-id="1ff4a-366">980</span><span class="sxs-lookup"><span data-stu-id="1ff4a-366">980</span></span> | <span data-ttu-id="1ff4a-367">sbc1.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="1ff4a-367">sbc1.contoso.com:5060</span></span> | <span data-ttu-id="1ff4a-368">true</span><span class="sxs-lookup"><span data-stu-id="1ff4a-368">true</span></span>
<span data-ttu-id="1ff4a-369">Utenti con trunk bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="1ff4a-369">Users with media bypass trunk</span></span> | <span data-ttu-id="1ff4a-370">20</span><span class="sxs-lookup"><span data-stu-id="1ff4a-370">20</span></span> | <span data-ttu-id="1ff4a-371">sbc2.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="1ff4a-371">sbc2.contoso.com:5061</span></span> | <span data-ttu-id="1ff4a-372">false</span><span class="sxs-lookup"><span data-stu-id="1ff4a-372">false</span></span> | 

<span data-ttu-id="1ff4a-373">Entrambi i trunk possono puntare allo stesso SBC con lo stesso indirizzo IP pubblico.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-373">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="1ff4a-374">Le porte di segnalazione TLS sull'SBC devono essere diverse, come illustrato nel diagramma seguente.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-374">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="1ff4a-375">Nota sarà necessario verificare che il certificato supporti entrambi i trunk.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-375">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="1ff4a-376">In SAN è necessario avere due nomi (**sbc1.contoso.com** e **sbc2.contoso.com**) o avere un certificato con carattere jolly.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-376">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>


![Mostra che entrambi i trunk possono puntare allo stesso SBC con lo stesso IP pubblico](media/direct-routing-media-bypass-7.png)

<span data-ttu-id="1ff4a-378">Per informazioni su come configurare due trunk nello stesso SBC, vedere la documentazione fornita dal fornitore SBC:</span><span class="sxs-lookup"><span data-stu-id="1ff4a-378">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

 - [<span data-ttu-id="1ff4a-379">Documentazione di distribuzione di AudioCodes</span><span class="sxs-lookup"><span data-stu-id="1ff4a-379">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="1ff4a-380">Documentazione di distribuzione Oracle</span><span class="sxs-lookup"><span data-stu-id="1ff4a-380">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="1ff4a-381">Documentazione sulla distribuzione delle comunicazioni della barra multifunzione</span><span class="sxs-lookup"><span data-stu-id="1ff4a-381">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="1ff4a-382">Documentazione sulla distribuzione di TE-Systems (anynode)</span><span class="sxs-lookup"><span data-stu-id="1ff4a-382">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="1ff4a-383">Endpoint client supportati con il bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="1ff4a-383">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="1ff4a-384">Il bypass multimediale è supportato con tutti i client desktop di teams e i dispositivi telefonici teams.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-384">Media bypass is supported with all Teams Desktop clients and Teams Phone Devices.</span></span> 

<span data-ttu-id="1ff4a-385">Per tutti gli altri endpoint che non supportano il bypass multimediale, è possibile nascondere la chiamata al non-bypass anche se è stata avviata come chiamata di bypass.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-385">For all other endpoints that do not support media bypass, we will covert the call to non-bypass even if it started as a bypass call.</span></span> <span data-ttu-id="1ff4a-386">Questo problema si verifica automaticamente e non richiede alcuna azione da parte dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="1ff4a-386">This happens automatically and does not require any actions from the administrator.</span></span> <span data-ttu-id="1ff4a-387">Questo include i telefoni di Skype for business 3PIP e i client Web teams che supportano le chiamate di routing diretto (New Microsoft Edge basato su Chromium, Google Chrome, Mozilla Firefox).</span><span class="sxs-lookup"><span data-stu-id="1ff4a-387">This includes Skype for Business 3PIP Phones, and Teams Web Clients that support Direct Routing calling (New Microsoft Edge based on Chromium, Google Chrome, Mozilla Firefox).</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="1ff4a-388">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1ff4a-388">See also</span></span>

[<span data-ttu-id="1ff4a-389">Configurare il bypass multimediale con Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="1ff4a-389">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)




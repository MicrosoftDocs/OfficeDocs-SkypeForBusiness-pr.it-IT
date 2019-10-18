---
title: Preparare la rete dell'organizzazione per Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/25/2019
ms.topic: reference
ms.service: msteams
ms.reviewer: arachman
audience: admin
description: Informazioni su come preparare e gestire la rete Microsoft teams. Le informazioni includono requisiti di rete, requisiti di larghezza di banda e considerazioni aggiuntive.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a9013eb1048d022244166906edb1737b01757ed6
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573224"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="5832d-104">Preparare la rete dell'organizzazione per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5832d-104">Prepare your organization's network for Microsoft Teams</span></span>


<span data-ttu-id="5832d-105">Teams combina tre forme di traffico:</span><span class="sxs-lookup"><span data-stu-id="5832d-105">Teams combines three forms of traffic:</span></span>

-   <span data-ttu-id="5832d-106">Traffico dati tra l'ambiente Office 365 online e il client Teams (segnalazione, presenza, chat, caricamento e download di file, sincronizzazione di OneNote).</span><span class="sxs-lookup"><span data-stu-id="5832d-106">Data traffic between the Office 365 online environment and the Teams client (signaling, presence, chat, file upload and download, OneNote synchronization).</span></span>

-   <span data-ttu-id="5832d-107">Traffico di comunicazioni in tempo reale peer-to-peer (audio, video, condivisione desktop).</span><span class="sxs-lookup"><span data-stu-id="5832d-107">Peer-to-peer real-time communications traffic (audio, video, desktop sharing).</span></span>

-   <span data-ttu-id="5832d-108">Traffico delle comunicazioni in tempo reale per i servizi di conferenza (audio, video, condivisione desktop).</span><span class="sxs-lookup"><span data-stu-id="5832d-108">Conferencing real-time communications traffic (audio, video, desktop sharing).</span></span>

<span data-ttu-id="5832d-109">Questo ha un impatto sulla rete su due livelli: il traffico scorrerà tra i client di Microsoft teams direttamente per gli scenari peer-to-peer e il traffico scorrerà tra l'ambiente di Office 365 e i client di Microsoft teams per gli scenari di riunione.</span><span class="sxs-lookup"><span data-stu-id="5832d-109">This impacts the network on two levels: traffic will flow between the Microsoft Teams clients directly for peer-to-peer scenarios, and traffic will flow between the Office 365 environment and the Microsoft Teams clients for meeting scenarios.</span></span> <span data-ttu-id="5832d-110">Per garantire un flusso di traffico ottimale, il traffico deve essere consentita per il flusso sia tra i segmenti di rete interni, ad esempio tra i siti della WAN, sia tra i siti di rete e Office 365.</span><span class="sxs-lookup"><span data-stu-id="5832d-110">To ensure optimal traffic flow, traffic must be allowed to flow both between the internal network segments (for example, between sites over the WAN) as well as between the network sites and Office 365.</span></span> <span data-ttu-id="5832d-111">Non aprire le porte corrette o bloccare attivamente porte specifiche comporterà un'esperienza degradata.</span><span class="sxs-lookup"><span data-stu-id="5832d-111">Not opening the correct ports or actively blocking specific ports will lead to a degraded experience.</span></span>


<span data-ttu-id="5832d-112">Per ottenere un'esperienza ottimale con i contenuti multimediali in tempo reale in Microsoft teams, la rete deve soddisfare i requisiti di rete per Office 365.</span><span class="sxs-lookup"><span data-stu-id="5832d-112">To get an optimal experience with real time media within Microsoft Teams, your network must meet the networking requirements for Office 365.</span></span> <span data-ttu-id="5832d-113">Per altre informazioni, Vedi [qualità multimediale e prestazioni della connettività di rete per Skype for business online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span><span class="sxs-lookup"><span data-stu-id="5832d-113">For more information, see [Media Quality and Network Connectivity Performance for Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span></span>

<span data-ttu-id="5832d-114">Per i due segmenti di rete che definiscono (client per Microsoft Edge e Customer Edge in Microsoft Edge), prendere in considerazione i seguenti suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="5832d-114">For the two defining network segments (Client to Microsoft Edge and Customer Edge to Microsoft Edge), consider the following recommendations.</span></span>


|<span data-ttu-id="5832d-115">Valore</span><span class="sxs-lookup"><span data-stu-id="5832d-115">Value</span></span>  |<span data-ttu-id="5832d-116">Client in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="5832d-116">Client to Microsoft Edge</span></span>  |<span data-ttu-id="5832d-117">Customer Edge to Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="5832d-117">Customer Edge to Microsoft Edge</span></span>  |
|:--- |:--- |:--- |
|<span data-ttu-id="5832d-118">**Latenza (solo andata)**\*</span><span class="sxs-lookup"><span data-stu-id="5832d-118">**Latency (one way)** \*</span></span>  |<span data-ttu-id="5832d-119">< 50ms</span><span class="sxs-lookup"><span data-stu-id="5832d-119">< 50ms</span></span>          |<span data-ttu-id="5832d-120">< 30ms</span><span class="sxs-lookup"><span data-stu-id="5832d-120">< 30ms</span></span>         |
|<span data-ttu-id="5832d-121">**Latenza (RTT o periodo di andata e ritorno)**\*</span><span class="sxs-lookup"><span data-stu-id="5832d-121">**Latency (RTT or Round-trip Time)** \*</span></span> |<span data-ttu-id="5832d-122">< 100ms</span><span class="sxs-lookup"><span data-stu-id="5832d-122">< 100ms</span></span>   |<span data-ttu-id="5832d-123">< 60ms</span><span class="sxs-lookup"><span data-stu-id="5832d-123">< 60ms</span></span> |
|<span data-ttu-id="5832d-124">**Perdita di pacchetti burst**</span><span class="sxs-lookup"><span data-stu-id="5832d-124">**Burst packet loss**</span></span>    |<span data-ttu-id="5832d-125"><10% durante l'intervallo di 200ms</span><span class="sxs-lookup"><span data-stu-id="5832d-125"><10% during any 200ms interval</span></span>         |<span data-ttu-id="5832d-126"><1% durante l'intervallo di 200ms</span><span class="sxs-lookup"><span data-stu-id="5832d-126"><1% during any 200ms interval</span></span>         |
|<span data-ttu-id="5832d-127">**Perdita di pacchetti**</span><span class="sxs-lookup"><span data-stu-id="5832d-127">**Packet loss**</span></span>     |<span data-ttu-id="5832d-128"><1% durante qualsiasi intervallo di 15s</span><span class="sxs-lookup"><span data-stu-id="5832d-128"><1% during any 15s interval</span></span>          |<span data-ttu-id="5832d-129"><0,1% durante qualsiasi intervallo di 15s</span><span class="sxs-lookup"><span data-stu-id="5832d-129"><0.1% during any 15s interval</span></span>         |
|<span data-ttu-id="5832d-130">**Jitter tra i pacchetti di arrivo**</span><span class="sxs-lookup"><span data-stu-id="5832d-130">**Packet inter-arrival Jitter**</span></span>    |<span data-ttu-id="5832d-131"><30ms durante qualsiasi intervallo di 15s</span><span class="sxs-lookup"><span data-stu-id="5832d-131"><30ms during any 15s interval</span></span>         |<span data-ttu-id="5832d-132"><15ms durante qualsiasi intervallo di 15s</span><span class="sxs-lookup"><span data-stu-id="5832d-132"><15ms during any 15s interval</span></span>         |
|<span data-ttu-id="5832d-133">**Riordino dei pacchetti**</span><span class="sxs-lookup"><span data-stu-id="5832d-133">**Packet reorder**</span></span>    |<span data-ttu-id="5832d-134"><pacchetti fuori ordine di 0,05%</span><span class="sxs-lookup"><span data-stu-id="5832d-134"><0.05% out-of-order packets</span></span>         |<span data-ttu-id="5832d-135"><pacchetti fuori ordine di 0,01%</span><span class="sxs-lookup"><span data-stu-id="5832d-135"><0.01% out-of-order packets</span></span>         |

<span data-ttu-id="5832d-136">\*Le destinazioni metriche per la latenza presuppongono che il sito o i siti aziendali e i bordi Microsoft si trovino nello stesso continente.</span><span class="sxs-lookup"><span data-stu-id="5832d-136">\* The latency metric targets assume your company site or sites and the Microsoft edges are on the same continent.</span></span>

<span data-ttu-id="5832d-137">La connessione del sito aziendale a Microsoft Network Edge include il primo accesso alla rete hop, che può essere Wi-Fi o un'altra tecnologia wireless.</span><span class="sxs-lookup"><span data-stu-id="5832d-137">Your company site connection to the Microsoft network edge includes first hop network access, which can be WiFi or another wireless technology.</span></span>

<span data-ttu-id="5832d-138">Le destinazioni delle prestazioni di rete presuppongono una corretta pianificazione della larghezza di banda e/o [QoS](QoS-in-Teams.md).</span><span class="sxs-lookup"><span data-stu-id="5832d-138">The network performance targets assume proper bandwidth and/or [QoS planning](QoS-in-Teams.md).</span></span> <span data-ttu-id="5832d-139">In altre parole, i requisiti si applicano direttamente al traffico multimediale in tempo reale dei team quando la connessione di rete è sotto un carico di picco.</span><span class="sxs-lookup"><span data-stu-id="5832d-139">In other words, the requirements apply directly to Teams real-time media traffic when the network connection is under a peak load.</span></span>

<span data-ttu-id="5832d-140">Per altre informazioni sulla preparazione della rete per i team, vedere [Network Planner](https://docs.microsoft.com/microsoftteams/network-planner).</span><span class="sxs-lookup"><span data-stu-id="5832d-140">For more help with preparing your network for Teams, check out [Network Planner](https://docs.microsoft.com/microsoftteams/network-planner).</span></span>


## <a name="bandwidth-requirements"></a><span data-ttu-id="5832d-141">Requisiti di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="5832d-141">Bandwidth requirements</span></span>
<span data-ttu-id="5832d-142">Microsoft teams offre la migliore esperienza di condivisione di audio, video e contenuti indipendentemente dalle condizioni della rete.</span><span class="sxs-lookup"><span data-stu-id="5832d-142">Microsoft Teams gives you the best audio, video and content sharing experience regardless of your network conditions.</span></span> <span data-ttu-id="5832d-143">Con i codec variabili, i contenuti multimediali possono essere negoziati in ambienti con larghezza di banda limitata con un impatto minimo.</span><span class="sxs-lookup"><span data-stu-id="5832d-143">With variable codecs, media can be negotiated in limited bandwidth environments with minimal impact.</span></span> <span data-ttu-id="5832d-144">Ma se la larghezza di banda non è un problema, le esperienze possono essere ottimizzate per la qualità, ad esempio fino a risoluzione video 1080p, fino a 30fps per video e 15fps per il contenuto e audio ad alta fedeltà.</span><span class="sxs-lookup"><span data-stu-id="5832d-144">But where bandwidth is not a concern, experiences can be optimized for quality, including up to 1080p video resolution, up to 30fps for video and 15fps for content, and high-fidelity audio.</span></span>

[!INCLUDE [Bandwidth requirements](includes/bandwidth-requirements.md)]


<!--
The content you will find below can be used as supplemental background information; however, it is recommended that customers use [Network Planner](https://aka.ms/bwcalc) to track their needs.

> [!IMPORTANT]
>If the required bandwidth is not available, the media stack inside Teams will degrade the quality of the audio/video session to accommodate for that lower amount of available bandwidth, impacting the quality of the call/meeting. The Teams client will attempt to prioritize the quality of audio over the quality of video. It is therefore extremely important to have the expected bandwidth available.


|Activity  |Download Bandwidth  |Upload Bandwidth  |Traffic Flow |
|---------|---------|---------|---------|
|**Peer to peer Audio Call**     |0.1 Mb         |0.1Mb         |Client <> Client         |
|**Peer to peer Video Call (full screen)**     |4 Mb         |4Mb         |Client <> Client          |
|**Peer to peer Desktop Sharing (1920*1080 resolution)**     |4 Mb         |4 Mb         |Client <> Client          |
|**2 Participant Meeting**     |4 Mb         |4 Mb         |Client <> Office 365         |
|**3 participant meeting**     |8 Mb         |6.5 Mb         |Client <> Office 365           |
|**4 participant meeting**     |5.5 Mb         |4 Mb         |Client <> Office 365           |
|**5 participant+ meeting**     |6 Mb         |1.5 Mb         |Client <> Office 365           |
-->

<a name="additional-network-considerations"></a><span data-ttu-id="5832d-145">Considerazioni di rete aggiuntive</span><span class="sxs-lookup"><span data-stu-id="5832d-145">Additional network considerations</span></span>
---------------

#### <a name="external-name-resolution"></a><span data-ttu-id="5832d-146">Risoluzione dei nomi esterni</span><span class="sxs-lookup"><span data-stu-id="5832d-146">External Name Resolution</span></span>

<span data-ttu-id="5832d-147">Assicurarsi che tutti i computer client che eseguono teams client possano risolvere le query DNS esterne per individuare i servizi forniti da Office 365 e che i firewall non impediscano l'accesso.</span><span class="sxs-lookup"><span data-stu-id="5832d-147">Ensure that all the client computers running Teams client can resolve external DNS queries to discover the services provided by Office 365, and that your firewalls are not preventing access.</span></span> <span data-ttu-id="5832d-148">Per informazioni sulla configurazione delle porte del firewall, vedere [URL e intervalli di indirizzi IP di Office 365](office-365-urls-ip-address-ranges.md).</span><span class="sxs-lookup"><span data-stu-id="5832d-148">For information about configuring firewall ports, go to [Office 365 URLs and IP ranges](office-365-urls-ip-address-ranges.md).</span></span>

#### <a name="nat-pool-size"></a><span data-ttu-id="5832d-149">Dimensioni pool NAT</span><span class="sxs-lookup"><span data-stu-id="5832d-149">NAT Pool Size</span></span>

<span data-ttu-id="5832d-150">Quando più utenti/dispositivi accedono a Office 365 tramite NAT (Network Address Translation) o PAT (Port Address Translation), è necessario assicurarsi che i dispositivi nascosti dietro ogni indirizzo IP instradabile pubblicamente non superino il numero supportato.</span><span class="sxs-lookup"><span data-stu-id="5832d-150">When multiple users/devices access Office 365 using Network Address Translation (NAT) or Port Address Translation (PAT), you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span>

<span data-ttu-id="5832d-151">Per ovviare a questo rischio, assicurati che siano assegnati indirizzi IP pubblici adeguati ai pool NAT per evitare l'esaurimento della porta.</span><span class="sxs-lookup"><span data-stu-id="5832d-151">To mitigate this risk, ensure adequate Public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="5832d-152">L'esaurimento della porta causerà gli utenti e i dispositivi finali interni per affrontare i problemi quando si connette ai servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="5832d-152">Port exhaustion will cause internal end users and devices to face issues when connecting to the Office 365 services.</span></span> <span data-ttu-id="5832d-153">Per altre informazioni, vedere [supporto NAT con Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span><span class="sxs-lookup"><span data-stu-id="5832d-153">For more information, see [NAT support with Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span></span>

#### <a name="intrusion-detection-and-prevention-guidance"></a><span data-ttu-id="5832d-154">**Istruzioni per il rilevamento delle intrusioni e la prevenzione**</span><span class="sxs-lookup"><span data-stu-id="5832d-154">**Intrusion Detection and Prevention Guidance**</span></span>

<span data-ttu-id="5832d-155">Se l'ambiente ha un sistema di rilevamento delle intrusioni e/o sistemi di prevenzione (IDS/IPS) distribuiti per un ulteriore livello di sicurezza per le connessioni in uscita, verificare che il traffico con gli URL di Office 365 sia in whitelist.</span><span class="sxs-lookup"><span data-stu-id="5832d-155">If your environment has an Intrusion Detection and/or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, ensure that any traffic with destination to Office 365 URLs is whitelisted.</span></span>

<a name="network-health-determination"></a><span data-ttu-id="5832d-156">Determinazione dell'integrità della rete</span><span class="sxs-lookup"><span data-stu-id="5832d-156">Network health determination</span></span>
-----------------

<span data-ttu-id="5832d-157">Quando si pianifica l'implementazione di Microsoft teams all'interno della rete, è necessario assicurarsi di avere la larghezza di banda necessaria, si ha accesso a tutti gli indirizzi IP necessari, alle porte corrette aperte e si soddisfano i requisiti di prestazioni per i supporti in tempo reale .</span><span class="sxs-lookup"><span data-stu-id="5832d-157">When planning on the implementation of Microsoft Teams within your network, you must ensure you have the required bandwidth, you have access to all required IP addresses, the correct ports opened, and you are meeting the performance requirements for real-time media.</span></span>

<span data-ttu-id="5832d-158">Se si sa che non si soddisfano questi criteri, gli utenti finali non otterranno un'esperienza ottimale da parte di Teams a causa della cattiva qualità durante le chiamate e le riunioni.</span><span class="sxs-lookup"><span data-stu-id="5832d-158">If you know you will not meet these criteria, your end users will not get an optimal experience from Teams due to bad quality during calls and meetings.</span></span>

<span data-ttu-id="5832d-159">Se non si soddisfano questi criteri, è il momento di prendere in considerazione la possibilità di sospendere il progetto per verificare che i criteri vengano soddisfatti prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="5832d-159">Should you not meet these criteria, this is the time to consider pausing the project to ensure you meet the criteria before continuing.</span></span>


|  |  |  |
|---------|---------|---------|
|![Icona che rappresenta un punto decisionale](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |<span data-ttu-id="5832d-161">Punto decisionale</span><span class="sxs-lookup"><span data-stu-id="5832d-161">Decision Point</span></span>         |<span data-ttu-id="5832d-162">Hai valutato le funzionalità di rete per il supporto di elementi multimediali in tempo reale?</span><span class="sxs-lookup"><span data-stu-id="5832d-162">Have you evaluated your network capabilities for supporting real time media?</span></span><br></br><span data-ttu-id="5832d-163">Se la rete non è stata valutata correttamente o se si è certi che non supporta il supporto in tempo reale, si disabilitano le funzionalità di condivisione di video e schermo per ridurre l'impatto della rete e le esperienze dei team poveri?</span><span class="sxs-lookup"><span data-stu-id="5832d-163">If your network has not been properly assessed, or you know it will not support real time media, will you disable video and screen sharing capabilities to reduce network impact and poor Teams experiences?</span></span>         |
|![Icona che rappresenta i passaggi successivi](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |<span data-ttu-id="5832d-165">Operazioni successive</span><span class="sxs-lookup"><span data-stu-id="5832d-165">Next Steps</span></span>         |<span data-ttu-id="5832d-166">Qualità della rete sconosciuta: eseguire una valutazione della conformità della rete per determinare se la rete è pronta per il supporto in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="5832d-166">Network Quality Unknown: Perform a Network Readiness Assessment to determine if your network is ready for Real Time Media.</span></span><br></br><span data-ttu-id="5832d-167">Qualità della rete scadente: eseguire i passaggi per la risoluzione dei problemi di rete per garantire un ambiente appropriato per i media in tempo reale di alta qualità.</span><span class="sxs-lookup"><span data-stu-id="5832d-167">Network Quality Poor: Perform network remediation steps to provide a proper environment for high quality Real Time Media.</span></span><br></br><span data-ttu-id="5832d-168">Rete soddisfacente: verificare che tutti gli indirizzi IP e le porte siano correttamente accessibili.</span><span class="sxs-lookup"><span data-stu-id="5832d-168">Network Satisfactory: Ensure all IP addresses and ports are properly accessible.</span></span>           |

## <a name="related-topics"></a><span data-ttu-id="5832d-169">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="5832d-169">Related Topics</span></span>

[<span data-ttu-id="5832d-170">Video: pianificazione della rete</span><span class="sxs-lookup"><span data-stu-id="5832d-170">Video: Network Planning</span></span>](https://aka.ms/teams-networking)

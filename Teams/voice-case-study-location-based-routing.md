---
title: Case Study di teams Voice contoso
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Case Study di teams Voice per società multinazionali
appliesto:
- Microsoft Teams
ms.openlocfilehash: f1ba92794b2ba17cc23e1bca55800c9307707636
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786006"
---
# <a name="contoso-case-study-location-based-routing"></a><span data-ttu-id="1d503-103">Case Study di Contoso: routing basato sulla posizione</span><span class="sxs-lookup"><span data-stu-id="1d503-103">Contoso case study: Location-Based Routing</span></span>

<span data-ttu-id="1d503-104">Il routing basato sulla posizione (LBR) è una funzionalità che limita l'esclusione dei pedaggi in base ai criteri e alla posizione fisica dell'utente al momento dell'immissione o della ricezione di una chiamata.</span><span class="sxs-lookup"><span data-stu-id="1d503-104">Location-Based Routing (LBR) is a feature that restricts toll bypass based on policy and the user's physical location at the time of placing or receiving a call.</span></span>  

## <a name="overview"></a><span data-ttu-id="1d503-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="1d503-105">Overview</span></span>

<span data-ttu-id="1d503-106">Contoso ha due uffici in un paese in cui è illegale ignorare il provider PSTN (Public Switched Telephone Network) per diminuire i costi delle chiamate interurbane.</span><span class="sxs-lookup"><span data-stu-id="1d503-106">Contoso has two offices in a country where it is illegal to bypass the Public Switched Telephone Network (PSTN) provider to decrease long-distance calling costs.</span></span> <span data-ttu-id="1d503-107">L'ufficio principale ha una connessione Internet usata dall'ufficio principale e dal secondo ufficio.</span><span class="sxs-lookup"><span data-stu-id="1d503-107">The main office has an Internet connection that is used by the main office and by the second office.</span></span> <span data-ttu-id="1d503-108">Ogni Office ha il proprio session border controller (SBC) connesso a un gestore PSTN.</span><span class="sxs-lookup"><span data-stu-id="1d503-108">Each office has their own Session Border Controller (SBC) connected to a PSTN carrier.</span></span>  
 
<span data-ttu-id="1d503-109">In questo paese, Contoso ha configurato LBR per la distribuzione di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="1d503-109">In this country, Contoso had LBR configured for their Skype for Business deployment.</span></span> <span data-ttu-id="1d503-110">Per determinare come configurare LBR per Teams, contoso Read [routing basato sulla posizione del piano per il routing diretto](location-based-routing-plan.md).</span><span class="sxs-lookup"><span data-stu-id="1d503-110">To determine how to configure LBR for Teams, Contoso read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md).</span></span> <span data-ttu-id="1d503-111">Contoso ha determinato che i team e Skype for business seguono gli stessi scenari in cui può essere inserita una chiamata, quando può essere ricevuta, quando è possibile trasferire una chiamata PSTN a un utente di teams e quando è possibile trasferire un altro utente di teams alla chiamata PSTN.</span><span class="sxs-lookup"><span data-stu-id="1d503-111">Contoso determined that Teams and Skype for Business follow the same scenarios on when a call can be placed, when it can be received, when a PSTN call can be transferred to a Teams user, and when you can transfer another Teams user to the PSTN call.</span></span>  

<span data-ttu-id="1d503-112">Per Skype for business, LBR è stato configurato con il trunk SIP Session Border Controller (SBC) che si connette al gestore PSTN.</span><span class="sxs-lookup"><span data-stu-id="1d503-112">For Skype for Business, LBR was configured with the Session Border Controller (SBC) SIP Trunk connecting to the PSTN carrier.</span></span> <span data-ttu-id="1d503-113">Per questo SBC, Contoso ha esaminato l' [elenco di sbcs certificati](direct-routing-border-controllers.md) e ha determinato che SBC distribuito è certificato per il routing diretto ma non è certificato per il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="1d503-113">For this SBC, Contoso reviewed the [list of certified SBCs](direct-routing-border-controllers.md) and determined that the SBC deployed is certified for Direct Routing but is not certified for Media Bypass.</span></span> <span data-ttu-id="1d503-114">Per supportare LBR, il routing diretto deve essere configurato per il SBC in loco, deve essere disponibile un'uscita Internet locale e il SBC deve essere configurato per il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="1d503-114">To support LBR, Direct Routing needs to be configured to the SBC on-site, there needs to be a local Internet egress, and the SBC needs to be configured for Media Bypass.</span></span> <span data-ttu-id="1d503-115">In base a queste informazioni, Contoso ha deciso quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1d503-115">Based on this information, Contoso decided the following:</span></span>

- <span data-ttu-id="1d503-116">Per ritardare l'abilitazione di teams LBR fino a quando l'attuale SBC non è certificato per il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="1d503-116">To delay the enablement of Teams LBR until the existing SBC is certified for Media Bypass.</span></span>   

- <span data-ttu-id="1d503-117">Contoso ha deciso di usare il SBC del sito principale per la route Direct a Office 365.</span><span class="sxs-lookup"><span data-stu-id="1d503-117">Contoso decided to use the main site SBC for the Direct Route to Office 365.</span></span>  <span data-ttu-id="1d503-118">Il SBC del sito principale sarà l'SBC proxy per il sito remoto.</span><span class="sxs-lookup"><span data-stu-id="1d503-118">The main site SBC will be the proxy SBC for the remote site.</span></span>  

- <span data-ttu-id="1d503-119">Contoso ha usato un consulente di terze parti basato in India per facilitare la certificazione della configurazione di LBR con la società di telefonia in un paese.</span><span class="sxs-lookup"><span data-stu-id="1d503-119">Contoso used a third-party consultant based in India to assist with certification of the LBR configuration with the telephony company in country.</span></span>  

- <span data-ttu-id="1d503-120">Per supportare gli utenti che lavorano dall'esterno dell'ufficio per effettuare chiamate PSTN, il telefono cellulare rilasciato dalla società è stato fornito ai dipendenti.</span><span class="sxs-lookup"><span data-stu-id="1d503-120">To support users working from outside of the office to place PSTN calls, the company issued mobile phone was provided to their employees.</span></span> 

<span data-ttu-id="1d503-121">I diagrammi seguenti mostrano le distribuzioni prima e dopo per un paese con regole per la telefonia che richiedono il routing basato sulla posizione:</span><span class="sxs-lookup"><span data-stu-id="1d503-121">The following diagrams show the before and after deployments for a country with telephony regulations that require Location-Based Routing:</span></span>

<span data-ttu-id="1d503-122">**Distribuzione originale**</span><span class="sxs-lookup"><span data-stu-id="1d503-122">**Original deployment**</span></span>

![Diagramma che mostra prima dello stato](media/voice-case-study-5.png)

<span data-ttu-id="1d503-124">**Distribuzione con routing diretto**</span><span class="sxs-lookup"><span data-stu-id="1d503-124">**Deployment with Direct Routing**</span></span>

![Diagramma che mostra prima dello stato](media/voice-case-study-6.png)


## <a name="configuration"></a><span data-ttu-id="1d503-126">Configurazione</span><span class="sxs-lookup"><span data-stu-id="1d503-126">Configuration:</span></span> 

<span data-ttu-id="1d503-127">Per configurare i componenti di rete in teams, Contoso ha seguito le istruzioni in [gestire la topologia di rete per le funzionalità vocali di cloud](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="1d503-127">To configure the network components in Teams, Contoso followed the instructions in [Manage your network topology for cloud voice features](manage-your-network-topology.md).</span></span> <span data-ttu-id="1d503-128">Contoso ha completato la procedura descritta di seguito per configurare il routing basato sulla posizione:</span><span class="sxs-lookup"><span data-stu-id="1d503-128">Contoso completed the below steps to configure Location-Based Routing:</span></span> 

- <span data-ttu-id="1d503-129">Definire le aree di rete-è stata definita un'area di rete.</span><span class="sxs-lookup"><span data-stu-id="1d503-129">Define Network regions -  One network region was defined.</span></span> 

- <span data-ttu-id="1d503-130">Definire i siti di rete: sono stati definiti due siti di rete.</span><span class="sxs-lookup"><span data-stu-id="1d503-130">Define Network sites - Two network sites were defined.</span></span> <span data-ttu-id="1d503-131">Un sito per ogni posizione di Office nell'area geografica.</span><span class="sxs-lookup"><span data-stu-id="1d503-131">One site for each office location in the region.</span></span>

- <span data-ttu-id="1d503-132">Definire le subnet di rete: ogni piano all'interno di una posizione di Office ha la propria subnet per la rete cablata e wireless.</span><span class="sxs-lookup"><span data-stu-id="1d503-132">Define Network subnets - Each floor within an office location has their own subnet for the wired and wireless network.</span></span> <span data-ttu-id="1d503-133">Questa configurazione ha generato 20 subnet per contoso.</span><span class="sxs-lookup"><span data-stu-id="1d503-133">This configuration resulted in 20 subnets for Contoso.</span></span> 

- <span data-ttu-id="1d503-134">Definire indirizzi IP attendibili: gli indirizzi IP di fronte esterno per il SBC sono stati aggiunti all'indirizzo IP attendibile.</span><span class="sxs-lookup"><span data-stu-id="1d503-134">Define trusted IP addresses - The external facing IP addresses for the SBC were added to the trusted IP address.</span></span>  


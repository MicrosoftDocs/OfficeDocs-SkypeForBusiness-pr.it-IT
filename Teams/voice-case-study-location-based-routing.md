---
title: Case study su Teams per Contoso
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
description: Case study vocale di Teams per multi-national corporation
appliesto:
- Microsoft Teams
ms.openlocfilehash: f1ba92794b2ba17cc23e1bca55800c9307707636
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786006"
---
# <a name="contoso-case-study-location-based-routing"></a><span data-ttu-id="cc219-103">Case study Contoso: Location-Based distribuzione</span><span class="sxs-lookup"><span data-stu-id="cc219-103">Contoso case study: Location-Based Routing</span></span>

<span data-ttu-id="cc219-104">Location-Based Routing a pedaggio (LBR) è una funzionalità che limita il bypass a pedaggio in base ai criteri e alla posizione fisica dell'utente al momento dell'esecuzione o della ricezione di una chiamata.</span><span class="sxs-lookup"><span data-stu-id="cc219-104">Location-Based Routing (LBR) is a feature that restricts toll bypass based on policy and the user's physical location at the time of placing or receiving a call.</span></span>  

## <a name="overview"></a><span data-ttu-id="cc219-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="cc219-105">Overview</span></span>

<span data-ttu-id="cc219-106">Contoso ha due uffici in un paese in cui non è valido bypassare il provider PSTN (Public Switched Telephone Network) per ridurre i costi per le chiamate a distanza.</span><span class="sxs-lookup"><span data-stu-id="cc219-106">Contoso has two offices in a country where it is illegal to bypass the Public Switched Telephone Network (PSTN) provider to decrease long-distance calling costs.</span></span> <span data-ttu-id="cc219-107">L'ufficio principale ha una connessione Internet usata dall'ufficio principale e dal secondo ufficio.</span><span class="sxs-lookup"><span data-stu-id="cc219-107">The main office has an Internet connection that is used by the main office and by the second office.</span></span> <span data-ttu-id="cc219-108">Ogni ufficio ha un proprio Session Border Controller (SBC) connesso a un gestore PSTN.</span><span class="sxs-lookup"><span data-stu-id="cc219-108">Each office has their own Session Border Controller (SBC) connected to a PSTN carrier.</span></span>  
 
<span data-ttu-id="cc219-109">In questo paese, Contoso aveva configurato LBR per la distribuzione di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="cc219-109">In this country, Contoso had LBR configured for their Skype for Business deployment.</span></span> <span data-ttu-id="cc219-110">Per determinare come configurare LBR per Teams, Contoso legge il piano [Location-Based routing per il routing diretto.](location-based-routing-plan.md)</span><span class="sxs-lookup"><span data-stu-id="cc219-110">To determine how to configure LBR for Teams, Contoso read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md).</span></span> <span data-ttu-id="cc219-111">Contoso ha determinato che Teams e Skype for Business seguono gli stessi scenari in cui è possibile effettuare una chiamata, quando può essere ricevuta, quando una chiamata PSTN può essere trasferita a un utente di Teams e quando è possibile trasferire un altro utente di Teams alla chiamata PSTN.</span><span class="sxs-lookup"><span data-stu-id="cc219-111">Contoso determined that Teams and Skype for Business follow the same scenarios on when a call can be placed, when it can be received, when a PSTN call can be transferred to a Teams user, and when you can transfer another Teams user to the PSTN call.</span></span>  

<span data-ttu-id="cc219-112">Per Skype for Business, la rete LBR è stata configurata con il trunk SIP di Session Border Controller (SBC) che si connette al gestore PSTN.</span><span class="sxs-lookup"><span data-stu-id="cc219-112">For Skype for Business, LBR was configured with the Session Border Controller (SBC) SIP Trunk connecting to the PSTN carrier.</span></span> <span data-ttu-id="cc219-113">Per questo SBC, Contoso ha esaminato l'elenco di [SBC](direct-routing-border-controllers.md) certificati e determinato che il servizio SBC distribuito è certificato per l'instradamento diretto, ma non è certificato per Media Bypass.</span><span class="sxs-lookup"><span data-stu-id="cc219-113">For this SBC, Contoso reviewed the [list of certified SBCs](direct-routing-border-controllers.md) and determined that the SBC deployed is certified for Direct Routing but is not certified for Media Bypass.</span></span> <span data-ttu-id="cc219-114">Per supportare LBR, il routing diretto deve essere configurato per il servizio SBC in locale, deve esserci un punto di uscita Internet locale e SBC deve essere configurato per media bypass.</span><span class="sxs-lookup"><span data-stu-id="cc219-114">To support LBR, Direct Routing needs to be configured to the SBC on-site, there needs to be a local Internet egress, and the SBC needs to be configured for Media Bypass.</span></span> <span data-ttu-id="cc219-115">Sulla base di queste informazioni, Contoso ha deciso quanto segue:</span><span class="sxs-lookup"><span data-stu-id="cc219-115">Based on this information, Contoso decided the following:</span></span>

- <span data-ttu-id="cc219-116">Per posticipare l'abilitazione di Teams LBR finché l'SBC esistente non viene certificato per Media Bypass.</span><span class="sxs-lookup"><span data-stu-id="cc219-116">To delay the enablement of Teams LBR until the existing SBC is certified for Media Bypass.</span></span>   

- <span data-ttu-id="cc219-117">Contoso ha deciso di usare il sito principale SBC per la route diretta a Office 365.</span><span class="sxs-lookup"><span data-stu-id="cc219-117">Contoso decided to use the main site SBC for the Direct Route to Office 365.</span></span>  <span data-ttu-id="cc219-118">Il sito principale SBC sarà il proxy SBC per il sito remoto.</span><span class="sxs-lookup"><span data-stu-id="cc219-118">The main site SBC will be the proxy SBC for the remote site.</span></span>  

- <span data-ttu-id="cc219-119">Contoso ha usato un consulente di terze parti in India per fornire assistenza nella certificazione della configurazione LBR con la società di telefonia del paese.</span><span class="sxs-lookup"><span data-stu-id="cc219-119">Contoso used a third-party consultant based in India to assist with certification of the LBR configuration with the telephony company in country.</span></span>  

- <span data-ttu-id="cc219-120">Per supportare gli utenti che lavorano dall'esterno dell'ufficio per effettuare chiamate PSTN, ai dipendenti è stato fornito un telefono cellulare rilasciato dalla società.</span><span class="sxs-lookup"><span data-stu-id="cc219-120">To support users working from outside of the office to place PSTN calls, the company issued mobile phone was provided to their employees.</span></span> 

<span data-ttu-id="cc219-121">I diagrammi seguenti mostrano le distribuzioni prima e dopo per un paese con normative di telefonia che richiedono Location-Based distribuzione:</span><span class="sxs-lookup"><span data-stu-id="cc219-121">The following diagrams show the before and after deployments for a country with telephony regulations that require Location-Based Routing:</span></span>

<span data-ttu-id="cc219-122">**Distribuzione originale**</span><span class="sxs-lookup"><span data-stu-id="cc219-122">**Original deployment**</span></span>

![Diagramma che mostra lo stato precedente](media/voice-case-study-5.png)

<span data-ttu-id="cc219-124">**Distribuzione con routing diretto**</span><span class="sxs-lookup"><span data-stu-id="cc219-124">**Deployment with Direct Routing**</span></span>

![Diagramma che mostra lo stato precedente](media/voice-case-study-6.png)


## <a name="configuration"></a><span data-ttu-id="cc219-126">Configurazione:</span><span class="sxs-lookup"><span data-stu-id="cc219-126">Configuration:</span></span> 

<span data-ttu-id="cc219-127">Per configurare i componenti di rete in Teams, Contoso ha seguito le istruzioni in Gestire la topologia [di rete per le funzionalità vocali del cloud.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="cc219-127">To configure the network components in Teams, Contoso followed the instructions in [Manage your network topology for cloud voice features](manage-your-network-topology.md).</span></span> <span data-ttu-id="cc219-128">Contoso ha completato i passaggi seguenti per configurare Location-Based distribuzione:</span><span class="sxs-lookup"><span data-stu-id="cc219-128">Contoso completed the below steps to configure Location-Based Routing:</span></span> 

- <span data-ttu-id="cc219-129">Definire le aree di rete: è stata definita un'area di rete.</span><span class="sxs-lookup"><span data-stu-id="cc219-129">Define Network regions -  One network region was defined.</span></span> 

- <span data-ttu-id="cc219-130">Definizione dei siti di rete: sono stati definiti due siti di rete.</span><span class="sxs-lookup"><span data-stu-id="cc219-130">Define Network sites - Two network sites were defined.</span></span> <span data-ttu-id="cc219-131">Un sito per ogni ufficio dell'area geografica.</span><span class="sxs-lookup"><span data-stu-id="cc219-131">One site for each office location in the region.</span></span>

- <span data-ttu-id="cc219-132">Definire le subnet di rete: ogni piano all'interno di una sede ha la propria subnet per la rete cablata e wireless.</span><span class="sxs-lookup"><span data-stu-id="cc219-132">Define Network subnets - Each floor within an office location has their own subnet for the wired and wireless network.</span></span> <span data-ttu-id="cc219-133">Questa configurazione ha comportato 20 subnet per Contoso.</span><span class="sxs-lookup"><span data-stu-id="cc219-133">This configuration resulted in 20 subnets for Contoso.</span></span> 

- <span data-ttu-id="cc219-134">Definire indirizzi IP attendibili: gli indirizzi IP esterni per SBC sono stati aggiunti all'indirizzo IP attendibile.</span><span class="sxs-lookup"><span data-stu-id="cc219-134">Define trusted IP addresses - The external facing IP addresses for the SBC were added to the trusted IP address.</span></span>  


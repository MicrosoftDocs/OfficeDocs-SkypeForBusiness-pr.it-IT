---
title: Definire l'ambito della distribuzione di E9-1-1 in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: Le decisioni necessarie per la pianificazione di una distribuzione di E9-1-1 in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: bec80e94c5bc2044359875f7c56f92a1348464c9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813426"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a><span data-ttu-id="202ee-103">Definire l'ambito della distribuzione di E9-1-1 in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="202ee-103">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>

<span data-ttu-id="202ee-104">Le decisioni necessarie per la pianificazione di una distribuzione di E9-1-1 in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="202ee-104">Decisions necessary for planning an E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="202ee-105">Prima di configurare Skype for business per il servizio E9-1-1, è necessario pianificare la distribuzione di E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="202ee-105">Before you configure Skype for Business for E9-1-1, you need to plan your E9-1-1 deployment.</span></span> <span data-ttu-id="202ee-106">Di seguito sono riportati alcuni aspetti di cui tenere conto:</span><span class="sxs-lookup"><span data-stu-id="202ee-106">Some of the questions to consider include:</span></span>

 <span data-ttu-id="202ee-107">**Quali sono i criteri e gli obblighi legali dell'organizzazione per quanto riguarda il servizio E9-1-1?**</span><span class="sxs-lookup"><span data-stu-id="202ee-107">**What are your organization's policy and legal obligations with regard to E9-1-1?**</span></span>

 <span data-ttu-id="202ee-108">Le disposizioni legali del servizio E9-1-1 per i PBX (denominati sistemi telefonici multilinea, o MLTS, nella terminologia relativa a E9-1-1) variano a seconda delle località.</span><span class="sxs-lookup"><span data-stu-id="202ee-108">E9-1-1 legal requirements for PBXs (called Multi-line Telephone Systems, or MLTS, in E9-1-1 parlance) differ from state to state.</span></span> <span data-ttu-id="202ee-109">È consigliabile rivolgersi al proprio team legale per capire gli obblighi che possono essere applicati alla distribuzione di Skype for business nelle rispettive aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="202ee-109">You should consult with your legal team to understand the obligations that may apply to your deployment of Skype for Business in your relevant geographies.</span></span>

 <span data-ttu-id="202ee-110">**Aree dell'organizzazione che devono essere abilitate per il servizio E9-1-1**</span><span class="sxs-lookup"><span data-stu-id="202ee-110">**What areas within your enterprise need to be enabled for E9-1-1?**</span></span>

 <span data-ttu-id="202ee-p103">È possibile abilitare il servizio E9-1-1 per l'intera organizzazione o solo per località selezionate. È ad esempio possibile applicare requisiti E9-1-1 diversi per gli uffici di stati diversi oppure escludere le sedi al di fuori degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="202ee-p103">You can enable E9-1-1 for the entire enterprise or for selected locations. For example, you may have varying E9-1-1 requirements for offices in different states, or you may want to exclude sites outside the U.S.</span></span>

 <span data-ttu-id="202ee-113">**Modalità di distribuzione del servizio E9-1-1 nei siti di succursale**</span><span class="sxs-lookup"><span data-stu-id="202ee-113">**How will you deploy E9-1-1 to branch sites?**</span></span>

 <span data-ttu-id="202ee-114">La resilienza vocale è un concetto importante di cui tenere conto quando si distribuisce il servizio E9-1-1 in un sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="202ee-114">Voice resiliency is an important concept to understand when deploying E9-1-1 at a branch site.</span></span> <span data-ttu-id="202ee-115">Se si dispone di trunk SIP e-9-1-1 centralizzato e si verifica un'interruzione della rete WAN, i client che effettuano l'accesso potrebbero non essere in grado di ottenere un percorso dal servizio informazioni percorso o connettersi al provider di servizi di emergenza.</span><span class="sxs-lookup"><span data-stu-id="202ee-115">If you have centralized E-9-1-1 SIP trunks and a WAN outage occurs, clients signing in may not be able to obtain a location from Location Information service or to connect to the emergency services service provider.</span></span> <span data-ttu-id="202ee-116">In Skype for business sono disponibili diverse strategie per la gestione della resilienza vocale nelle succursali, tra cui: una rete di dati resilienti, la distribuzione di un trunk SIP in ogni filiale o la pressione di chiamate di emergenza verso il gateway locale durante le interruzioni.</span><span class="sxs-lookup"><span data-stu-id="202ee-116">Skype for Business provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing emergency calls out to the local gateway during outages.</span></span> <span data-ttu-id="202ee-117">Per informazioni dettagliate, vedere [Planning for Branch-Site Voice Resiliency](https://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx).</span><span class="sxs-lookup"><span data-stu-id="202ee-117">For details, see [Planning for Branch-Site Voice Resiliency](https://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx).</span></span>

 <span data-ttu-id="202ee-118">**Possibilità di abilitare il servizio E9-1-1 per gli utenti che lavorano all'esterno della rete**</span><span class="sxs-lookup"><span data-stu-id="202ee-118">**Will you enable E9-1-1 for users working outside the network?**</span></span>

 <span data-ttu-id="202ee-119">L'acquisizione automatica delle posizioni è disponibile solo per i client situati all'interno della rete dell'organizzazione, quindi è necessario che l'organizzazione decida se supporta le chiamate E9-1-1 effettuate dai client Skype for business in locale.</span><span class="sxs-lookup"><span data-stu-id="202ee-119">Automatic location acquisition is available only for clients located inside the organization's network, so your organization needs to decide whether it will support E9-1-1 calls made from Skype for Business clients while off-premises.</span></span> <span data-ttu-id="202ee-120">L'organizzazione deve pertanto decidere se supportare le chiamate E9-1-1 effettuate da client Lync non locali, ad esempio se consentire agli utenti di effettuare chiamate di emergenza quando lavorano dalla propria abitazione o dalla sede di un cliente.</span><span class="sxs-lookup"><span data-stu-id="202ee-120">For example, will you enable users to place emergency calls if they are working from home or from a customer site?</span></span> <span data-ttu-id="202ee-121">Se è posizionato all'esterno di una rete aziendale, un client può essere configurato per richiedere la posizione a un utente.</span><span class="sxs-lookup"><span data-stu-id="202ee-121">If a client is located outside the enterprise network, the client can be configured to prompt the user for a location.</span></span> <span data-ttu-id="202ee-122">Poiché tuttavia queste posizioni fornite dagli utenti non possono essere precedentemente convalidate a fronte dello stradario generale, il dispatcher del provider di servizi di emergenza dovrà verificare la validità della posizione verbalmente con il chiamante prima di instradare la chiamata al centro di raccolta delle chiamate di emergenza (PSAP, Public Safety Answering Point).</span><span class="sxs-lookup"><span data-stu-id="202ee-122">However, because these user-provided locations cannot be prevalidated against the Master Street Address Guide (MSAG), the emergency services service provider dispatcher will need to confirm the validity of the location verbally with the caller before routing the call to the Public Safety Answering Point (PSAP).</span></span>

> [!NOTE]
> <span data-ttu-id="202ee-123">I client Skype for business degli utenti che si connettono alla rete dell'organizzazione tramite VPN possono raccogliere informazioni sull'indirizzo IP interno, ma poiché questi indirizzi non possono essere utilizzati per identificare la posizione effettiva dell'utente, è essenziale che le subnet VPN siano escluse dal servizio informazioni percorso.</span><span class="sxs-lookup"><span data-stu-id="202ee-123">Skype for Business clients of users who connect to your organization's network by using VPN can pick up internal IP address information, but because these addresses cannot be used to identify the user's actual location, it is essential that VPN subnets are excluded from the Location Information service.</span></span>

 <span data-ttu-id="202ee-124">**Possibilità di fornire il routing delle chiamate di emergenza per siti al di fuori degli Stati Uniti**</span><span class="sxs-lookup"><span data-stu-id="202ee-124">**Do you want to provide emergency call routing to sites outside the U.S.?**</span></span>

 <span data-ttu-id="202ee-p106">È possibile offrire il routing delle chiamate di emergenza per aree dell'azienda non servite dal provider di servizi di emergenza, ad esempio sedi internazionali. A tale scopo, creare un nuovo sito e quindi assegnare i criteri vocali ai siti che fanno riferimento a un utilizzo PSTN che instrada le chiamate tramite il gateway PSTN locale.</span><span class="sxs-lookup"><span data-stu-id="202ee-p106">You may want to provide emergency routing to areas of your company not served by an emergency services service provider (for example, international locations). To do this, create a new site, and then assign voice policies to the sites that refer to a PSTN usage that routes the call through the local PSTN gateway.</span></span>



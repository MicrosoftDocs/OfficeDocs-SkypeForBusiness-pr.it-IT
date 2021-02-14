---
title: Configurare Instradamento diretto
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Informazioni su come configurare l'instradamento diretto del sistema telefonico Microsoft per connettere l'infrastruttura di telefonia locale a Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5388c93e741323d3dc9eda0fc51968b8b344d2cb
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701294"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="67ee6-103">Configurare Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="67ee6-103">Configure Direct Routing</span></span>

<span data-ttu-id="67ee6-104">Microsoft Phone System Direct Routing consente di connettere l'infrastruttura di telefonia locale a Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="67ee6-104">Microsoft Phone System Direct Routing enables you to connect your on-premises telephony infrastructure to Microsoft Teams.</span></span> <span data-ttu-id="67ee6-105">In questo articolo sono elencati i passaggi di alto livello necessari per connettere un controller SBC (Session Border Controller) locale supportato al routing diretto e viene spiegato come configurare gli utenti di Teams in modo che usino il routing diretto per connettersi alla rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="67ee6-105">The article lists the high-level steps required for connecting a supported on-premises Session Border Controller (SBC) to Direct Routing, and how to configure Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="67ee6-106">Questo articolo contiene collegamenti ad articoli associati per informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="67ee6-106">This article links to associated articles for details.</span></span>  

<span data-ttu-id="67ee6-107">Per informazioni sul fatto che l'instradamento diretto sia la soluzione giusta per la propria organizzazione, vedere Routing diretto sistema [telefonico.](direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="67ee6-107">For information about whether Direct Routing is the right solution for your organization, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span> <span data-ttu-id="67ee6-108">Per informazioni sui prerequisiti e la pianificazione della distribuzione, vedere [Pianificare il routing diretto.](direct-routing-plan.md)</span><span class="sxs-lookup"><span data-stu-id="67ee6-108">For information about prerequisites and planning your deployment, see [Plan Direct Routing](direct-routing-plan.md).</span></span>

> [!Tip]
> <span data-ttu-id="67ee6-109">È anche possibile guardare la sessione seguente per informazioni sui vantaggi del routing diretto, su come pianificarlo e su come distribuirlo: Routing [diretto in Microsoft Teams.](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="67ee6-109">You can also watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing).</span></span>

<span data-ttu-id="67ee6-110">Per completare i passaggi descritti in questo articolo, gli amministratori hanno bisogno di una certa familiarità con i cmdlet di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="67ee6-110">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="67ee6-111">Per altre informazioni sull'uso di PowerShell, vedere [Configurare il computer per Windows PowerShell.](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="67ee6-111">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="67ee6-112">Prima di eseguire i passaggi descritti in questi articoli, Microsoft consiglia di verificare che sBC sia già stato configurato come consigliato dal fornitore del servizio SBC:</span><span class="sxs-lookup"><span data-stu-id="67ee6-112">Before performing the steps in these articles, Microsoft recommends that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="67ee6-113">Documentazione sulla distribuzione di AudioCodes</span><span class="sxs-lookup"><span data-stu-id="67ee6-113">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="67ee6-114">Documentazione della distribuzione Oracle</span><span class="sxs-lookup"><span data-stu-id="67ee6-114">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="67ee6-115">Documentazione sulla distribuzione di Ribbon Communications</span><span class="sxs-lookup"><span data-stu-id="67ee6-115">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="67ee6-116">Documentazione sulla distribuzione di TE-Systems (anynode)</span><span class="sxs-lookup"><span data-stu-id="67ee6-116">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)
- [<span data-ttu-id="67ee6-117">Documentazione sulla distribuzione di Metapass</span><span class="sxs-lookup"><span data-stu-id="67ee6-117">Metaswitch deployment documentation</span></span>](https://www.metaswitch.com/products/core-network/perimeta-sbc)

<span data-ttu-id="67ee6-118">Per un elenco completo dei controller dei confini della sessione supportati, consulta l'elenco dei controller dei confini [della sessione certificati per l'instradamento diretto.](direct-routing-border-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="67ee6-118">For a complete list of supported SBCs, see [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>

<span data-ttu-id="67ee6-119">Per configurare il Sistema telefonico Microsoft e consentire agli utenti di usare l'instradamento diretto, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="67ee6-119">To configure Microsoft Phone System and enable users to use Direct Routing, follow these steps:</span></span> 

- <span data-ttu-id="67ee6-120">**Passaggio 1.**</span><span class="sxs-lookup"><span data-stu-id="67ee6-120">**Step 1.**</span></span> [<span data-ttu-id="67ee6-121">Collegare il servizio SBC al Sistema telefonico Microsoft e convalidare la connessione</span><span class="sxs-lookup"><span data-stu-id="67ee6-121">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md)
- <span data-ttu-id="67ee6-122">**Passaggio 2.**</span><span class="sxs-lookup"><span data-stu-id="67ee6-122">**Step 2.**</span></span> [<span data-ttu-id="67ee6-123">Abilitare gli utenti per l'instradamento diretto, la voce e la segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="67ee6-123">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="67ee6-124">**Passaggio 3.**</span><span class="sxs-lookup"><span data-stu-id="67ee6-124">**Step 3.**</span></span> [<span data-ttu-id="67ee6-125">Configurare il routing vocale</span><span class="sxs-lookup"><span data-stu-id="67ee6-125">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="67ee6-126">**Passaggio 4.**</span><span class="sxs-lookup"><span data-stu-id="67ee6-126">**Step 4.**</span></span> [<span data-ttu-id="67ee6-127">Convertire i numeri in un formato alternativo</span><span class="sxs-lookup"><span data-stu-id="67ee6-127">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="67ee6-128">Se si sta configurando un database SBC per più tenant, è anche utile leggere Configurare un [SBC per più tenant.](direct-routing-sbc-multiple-tenants.md)</span><span class="sxs-lookup"><span data-stu-id="67ee6-128">If you are configuring an SBC for multiple tenants, you'll also want to read [Configure an SBC for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="67ee6-129">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="67ee6-129">Related topics</span></span>

[<span data-ttu-id="67ee6-130">Instradamento diretto di Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="67ee6-130">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)

[<span data-ttu-id="67ee6-131">Pianificare Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="67ee6-131">Plan Direct Routing</span></span>](direct-routing-plan.md)


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
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Informazioni su come configurare il routing diretto di Microsoft Phone System.
ms.openlocfilehash: 9c56078a6d016967e518746e3567373404d1c486
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "42157874"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="13db9-103">Configurare Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="13db9-103">Configure Direct Routing</span></span>

<span data-ttu-id="13db9-104">Microsoft Phone System Direct routing consente di connettere l'infrastruttura di telefonia locale a Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="13db9-104">Microsoft Phone System Direct Routing enables you to connect your on-premises telephony infrastructure to Microsoft Teams.</span></span> <span data-ttu-id="13db9-105">L'articolo elenca i passaggi di alto livello necessari per connettere un SBC (Session Border Controller) supportato a routing diretto e come configurare gli utenti di teams in modo da usare il routing diretto per connettersi alla rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="13db9-105">The article lists the high-level steps required for connecting a supported on-premises Session Border Controller (SBC) to Direct Routing, and how to configure Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="13db9-106">Questo articolo collega agli articoli associati per i dettagli.</span><span class="sxs-lookup"><span data-stu-id="13db9-106">This article links to associated articles for details.</span></span>  

<span data-ttu-id="13db9-107">Per informazioni sul fatto che il routing diretto è la soluzione ideale per l'organizzazione, vedere [routing diretto del sistema telefonico](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="13db9-107">For information about whether Direct Routing is the right solution for your organization, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span> <span data-ttu-id="13db9-108">Per informazioni sui prerequisiti e sulla pianificazione della distribuzione, vedere [pianificare il routing diretto](direct-routing-plan.md).</span><span class="sxs-lookup"><span data-stu-id="13db9-108">For information about prerequisites and planning your deployment, see [Plan Direct Routing](direct-routing-plan.md).</span></span>

> [!Tip]
> <span data-ttu-id="13db9-109">È anche possibile guardare la sessione seguente per conoscere i vantaggi del routing diretto, come pianificare e come distribuirlo: [routing diretto in Microsoft teams](https://aka.ms/teams-direct-routing).</span><span class="sxs-lookup"><span data-stu-id="13db9-109">You can also watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing).</span></span>

<span data-ttu-id="13db9-110">Per completare la procedura descritta in questo articolo, gli amministratori hanno bisogno di una certa familiarità con i cmdlet di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="13db9-110">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="13db9-111">Per altre informazioni sull'uso di PowerShell, vedere [configurare il computer per Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="13db9-111">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="13db9-112">Prima di eseguire la procedura descritta in questi articoli, Microsoft consiglia di verificare che il SBC sia già stato configurato come consigliato dal fornitore SBC:</span><span class="sxs-lookup"><span data-stu-id="13db9-112">Before performing the steps in these articles, Microsoft recommends that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="13db9-113">Documentazione di distribuzione di AudioCodes</span><span class="sxs-lookup"><span data-stu-id="13db9-113">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="13db9-114">Documentazione di distribuzione Oracle</span><span class="sxs-lookup"><span data-stu-id="13db9-114">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="13db9-115">Documentazione sulla distribuzione delle comunicazioni della barra multifunzione</span><span class="sxs-lookup"><span data-stu-id="13db9-115">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="13db9-116">Documentazione sulla distribuzione di TE-Systems (anynode)</span><span class="sxs-lookup"><span data-stu-id="13db9-116">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

<span data-ttu-id="13db9-117">Per un elenco completo delle SBCs supportate, vedere l' [elenco dei controller di bordo della sessione certificati per il routing diretto](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="13db9-117">For a complete list of supported SBCs, see [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>

<span data-ttu-id="13db9-118">Per configurare il sistema telefonico Microsoft e consentire agli utenti di usare il routing diretto, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="13db9-118">To configure Microsoft Phone System and enable users to use Direct Routing, follow these steps:</span></span> 

- <span data-ttu-id="13db9-119">**Passaggio 1.**</span><span class="sxs-lookup"><span data-stu-id="13db9-119">**Step 1.**</span></span> [<span data-ttu-id="13db9-120">Connettere il SBC con il sistema telefonico Microsoft e convalidare la connessione</span><span class="sxs-lookup"><span data-stu-id="13db9-120">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md)
- <span data-ttu-id="13db9-121">**Passaggio 2.**</span><span class="sxs-lookup"><span data-stu-id="13db9-121">**Step 2.**</span></span> [<span data-ttu-id="13db9-122">Abilitare gli utenti per il routing diretto, la voce e la segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="13db9-122">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="13db9-123">**Passaggio 3.**</span><span class="sxs-lookup"><span data-stu-id="13db9-123">**Step 3.**</span></span> [<span data-ttu-id="13db9-124">Configurare il routing vocale</span><span class="sxs-lookup"><span data-stu-id="13db9-124">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="13db9-125">**Passaggio 4.**</span><span class="sxs-lookup"><span data-stu-id="13db9-125">**Step 4.**</span></span> [<span data-ttu-id="13db9-126">Tradurre i numeri in un formato alternativo</span><span class="sxs-lookup"><span data-stu-id="13db9-126">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="13db9-127">Se si configura un SBC per più tenant, si vorrà anche leggere [configurare un SBC per più tenant](direct-routing-sbc-multiple-tenants.md).</span><span class="sxs-lookup"><span data-stu-id="13db9-127">If you are configuring an SBC for multiple tenants, you'll also want to read [Configure an SBC for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="13db9-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13db9-128">See also</span></span>

[<span data-ttu-id="13db9-129">Instradamento diretto di Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="13db9-129">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)

[<span data-ttu-id="13db9-130">Pianificare Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="13db9-130">Plan Direct Routing</span></span>](direct-routing-plan.md)


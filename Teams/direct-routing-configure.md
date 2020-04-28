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
description: Informazioni su come configurare il routing diretto di Microsoft Phone System per connettere l'infrastruttura di telefonia locale a Microsoft teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f12eb67fd63a3d1bbed3ddcd0c4fadce16529083
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904828"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="98a9e-103">Configurare Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="98a9e-103">Configure Direct Routing</span></span>

<span data-ttu-id="98a9e-104">Microsoft Phone System Direct routing consente di connettere l'infrastruttura di telefonia locale a Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="98a9e-104">Microsoft Phone System Direct Routing enables you to connect your on-premises telephony infrastructure to Microsoft Teams.</span></span> <span data-ttu-id="98a9e-105">L'articolo elenca i passaggi di alto livello necessari per connettere un SBC (Session Border Controller) supportato a routing diretto e come configurare gli utenti di teams in modo da usare il routing diretto per connettersi alla rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="98a9e-105">The article lists the high-level steps required for connecting a supported on-premises Session Border Controller (SBC) to Direct Routing, and how to configure Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="98a9e-106">Questo articolo collega agli articoli associati per i dettagli.</span><span class="sxs-lookup"><span data-stu-id="98a9e-106">This article links to associated articles for details.</span></span>  

<span data-ttu-id="98a9e-107">Per informazioni sul fatto che il routing diretto è la soluzione ideale per l'organizzazione, vedere [routing diretto del sistema telefonico](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="98a9e-107">For information about whether Direct Routing is the right solution for your organization, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span> <span data-ttu-id="98a9e-108">Per informazioni sui prerequisiti e sulla pianificazione della distribuzione, vedere [pianificare il routing diretto](direct-routing-plan.md).</span><span class="sxs-lookup"><span data-stu-id="98a9e-108">For information about prerequisites and planning your deployment, see [Plan Direct Routing](direct-routing-plan.md).</span></span>

> [!Tip]
> <span data-ttu-id="98a9e-109">È anche possibile guardare la sessione seguente per conoscere i vantaggi del routing diretto, come pianificare e come distribuirlo: [routing diretto in Microsoft teams](https://aka.ms/teams-direct-routing).</span><span class="sxs-lookup"><span data-stu-id="98a9e-109">You can also watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing).</span></span>

<span data-ttu-id="98a9e-110">Per completare la procedura descritta in questo articolo, gli amministratori hanno bisogno di una certa familiarità con i cmdlet di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="98a9e-110">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="98a9e-111">Per altre informazioni sull'uso di PowerShell, vedere [configurare il computer per Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="98a9e-111">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="98a9e-112">Prima di eseguire la procedura descritta in questi articoli, Microsoft consiglia di verificare che il SBC sia già stato configurato come consigliato dal fornitore SBC:</span><span class="sxs-lookup"><span data-stu-id="98a9e-112">Before performing the steps in these articles, Microsoft recommends that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="98a9e-113">Documentazione di distribuzione di AudioCodes</span><span class="sxs-lookup"><span data-stu-id="98a9e-113">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="98a9e-114">Documentazione di distribuzione Oracle</span><span class="sxs-lookup"><span data-stu-id="98a9e-114">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="98a9e-115">Documentazione sulla distribuzione delle comunicazioni della barra multifunzione</span><span class="sxs-lookup"><span data-stu-id="98a9e-115">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="98a9e-116">Documentazione sulla distribuzione di TE-Systems (anynode)</span><span class="sxs-lookup"><span data-stu-id="98a9e-116">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)
- [<span data-ttu-id="98a9e-117">Documentazione di distribuzione Metaswitch</span><span class="sxs-lookup"><span data-stu-id="98a9e-117">Metaswitch deployment documentation</span></span>](https://www.metaswitch.com/products/core-network/perimeta-sbc)

<span data-ttu-id="98a9e-118">Per un elenco completo delle SBCs supportate, vedere l' [elenco dei controller di bordo della sessione certificati per il routing diretto](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="98a9e-118">For a complete list of supported SBCs, see [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>

<span data-ttu-id="98a9e-119">Per configurare il sistema telefonico Microsoft e consentire agli utenti di usare il routing diretto, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="98a9e-119">To configure Microsoft Phone System and enable users to use Direct Routing, follow these steps:</span></span> 

- <span data-ttu-id="98a9e-120">**Passaggio 1.**</span><span class="sxs-lookup"><span data-stu-id="98a9e-120">**Step 1.**</span></span> [<span data-ttu-id="98a9e-121">Connettere il SBC con il sistema telefonico Microsoft e convalidare la connessione</span><span class="sxs-lookup"><span data-stu-id="98a9e-121">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md)
- <span data-ttu-id="98a9e-122">**Passaggio 2.**</span><span class="sxs-lookup"><span data-stu-id="98a9e-122">**Step 2.**</span></span> [<span data-ttu-id="98a9e-123">Abilitare gli utenti per il routing diretto, la voce e la segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="98a9e-123">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="98a9e-124">**Passaggio 3.**</span><span class="sxs-lookup"><span data-stu-id="98a9e-124">**Step 3.**</span></span> [<span data-ttu-id="98a9e-125">Configurare il routing vocale</span><span class="sxs-lookup"><span data-stu-id="98a9e-125">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="98a9e-126">**Passaggio 4.**</span><span class="sxs-lookup"><span data-stu-id="98a9e-126">**Step 4.**</span></span> [<span data-ttu-id="98a9e-127">Tradurre i numeri in un formato alternativo</span><span class="sxs-lookup"><span data-stu-id="98a9e-127">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="98a9e-128">Se si configura un SBC per più tenant, si vorrà anche leggere [configurare un SBC per più tenant](direct-routing-sbc-multiple-tenants.md).</span><span class="sxs-lookup"><span data-stu-id="98a9e-128">If you are configuring an SBC for multiple tenants, you'll also want to read [Configure an SBC for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="98a9e-129">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="98a9e-129">Related topics</span></span>

[<span data-ttu-id="98a9e-130">Instradamento diretto di Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="98a9e-130">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)

[<span data-ttu-id="98a9e-131">Pianificare Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="98a9e-131">Plan Direct Routing</span></span>](direct-routing-plan.md)


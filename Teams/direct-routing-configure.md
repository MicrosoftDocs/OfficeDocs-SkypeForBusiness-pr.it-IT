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
description: Informazioni su come configurare Telefono Microsoft routing diretto di sistema per connettere l'infrastruttura di telefonia locale a Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ecd8579ccd092e6b82deb06aa670901cdfc3b023
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122240"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="5dd78-103">Configurare Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="5dd78-103">Configure Direct Routing</span></span>

<span data-ttu-id="5dd78-104">Telefono Microsoft System Direct Routing consente di connettere l'infrastruttura di telefonia locale a Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5dd78-104">Microsoft Phone System Direct Routing enables you to connect your on-premises telephony infrastructure to Microsoft Teams.</span></span> <span data-ttu-id="5dd78-105">L'articolo elenca i passaggi di alto livello necessari per connettere un controller SBC (Session Border Controller) locale supportato al routing diretto e come configurare gli utenti di Teams per l'uso del routing diretto per connettersi alla rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="5dd78-105">The article lists the high-level steps required for connecting a supported on-premises Session Border Controller (SBC) to Direct Routing, and how to configure Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="5dd78-106">Questo articolo contiene collegamenti ad articoli associati per informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="5dd78-106">This article links to associated articles for details.</span></span>  

<span data-ttu-id="5dd78-107">Per informazioni sul fatto che il routing diretto sia la soluzione giusta per l'organizzazione, vedere Sistema telefonico [Routing diretto](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="5dd78-107">For information about whether Direct Routing is the right solution for your organization, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span> <span data-ttu-id="5dd78-108">Per informazioni sui prerequisiti e sulla pianificazione della distribuzione, vedere [Pianificare il routing diretto.](direct-routing-plan.md)</span><span class="sxs-lookup"><span data-stu-id="5dd78-108">For information about prerequisites and planning your deployment, see [Plan Direct Routing](direct-routing-plan.md).</span></span>

> [!Tip]
> <span data-ttu-id="5dd78-109">È anche possibile guardare la sessione seguente per informazioni sui vantaggi del routing diretto, su come pianificarla e su come distribuirla: Routing diretto [in Microsoft Teams](https://aka.ms/teams-direct-routing).</span><span class="sxs-lookup"><span data-stu-id="5dd78-109">You can also watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing).</span></span>

<span data-ttu-id="5dd78-110">Per completare i passaggi descritti in questo articolo, gli amministratori hanno bisogno di una certa familiarità con i cmdlet di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5dd78-110">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="5dd78-111">Per altre informazioni sull'uso di PowerShell, vedere [Configurare il computer per Windows PowerShell.](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="5dd78-111">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="5dd78-112">Prima di eseguire i passaggi descritti in questi articoli, Microsoft consiglia di confermare che il proprio SBC è già stato configurato come consigliato dal fornitore SBC:</span><span class="sxs-lookup"><span data-stu-id="5dd78-112">Before performing the steps in these articles, Microsoft recommends that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="5dd78-113">Documentazione sulla distribuzione di AudioCodes</span><span class="sxs-lookup"><span data-stu-id="5dd78-113">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="5dd78-114">Documentazione sulla distribuzione Oracle</span><span class="sxs-lookup"><span data-stu-id="5dd78-114">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="5dd78-115">Documentazione sulla distribuzione di Ribbon Communications</span><span class="sxs-lookup"><span data-stu-id="5dd78-115">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="5dd78-116">Documentazione sulla distribuzione di TE-Systems (anynode)</span><span class="sxs-lookup"><span data-stu-id="5dd78-116">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)
- [<span data-ttu-id="5dd78-117">Documentazione sulla distribuzione di Metaswitch</span><span class="sxs-lookup"><span data-stu-id="5dd78-117">Metaswitch deployment documentation</span></span>](https://www.metaswitch.com/products/core-network/perimeta-sbc)

<span data-ttu-id="5dd78-118">Per un elenco completo dei controller SBC supportati, vedere Elenco dei controller di [bordo delle sessioni certificati per il routing diretto.](direct-routing-border-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="5dd78-118">For a complete list of supported SBCs, see [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>

<span data-ttu-id="5dd78-119">Per configurare Telefono Microsoft sistema e consentire agli utenti di usare Il routing diretto, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="5dd78-119">To configure Microsoft Phone System and enable users to use Direct Routing, follow these steps:</span></span> 

- <span data-ttu-id="5dd78-120">**Passaggio 1.**</span><span class="sxs-lookup"><span data-stu-id="5dd78-120">**Step 1.**</span></span> [<span data-ttu-id="5dd78-121">Connessione SBC con Telefono Microsoft sistema e convalidare la connessione</span><span class="sxs-lookup"><span data-stu-id="5dd78-121">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md)
- <span data-ttu-id="5dd78-122">**Passaggio 2.**</span><span class="sxs-lookup"><span data-stu-id="5dd78-122">**Step 2.**</span></span> [<span data-ttu-id="5dd78-123">Abilitare gli utenti per routing diretto, segreteria telefonica e segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="5dd78-123">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="5dd78-124">**Passaggio 3.**</span><span class="sxs-lookup"><span data-stu-id="5dd78-124">**Step 3.**</span></span> [<span data-ttu-id="5dd78-125">Configurare il routing vocale</span><span class="sxs-lookup"><span data-stu-id="5dd78-125">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="5dd78-126">**Passaggio 4.**</span><span class="sxs-lookup"><span data-stu-id="5dd78-126">**Step 4.**</span></span> [<span data-ttu-id="5dd78-127">Tradurre i numeri in un formato alternativo</span><span class="sxs-lookup"><span data-stu-id="5dd78-127">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="5dd78-128">Se si sta configurando un SBC per più tenant, è anche utile leggere Configurare un [SBC per più tenant.](direct-routing-sbc-multiple-tenants.md)</span><span class="sxs-lookup"><span data-stu-id="5dd78-128">If you are configuring an SBC for multiple tenants, you'll also want to read [Configure an SBC for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="5dd78-129">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="5dd78-129">Related topics</span></span>

[<span data-ttu-id="5dd78-130">Instradamento diretto di Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="5dd78-130">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)

[<span data-ttu-id="5dd78-131">Pianificare Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="5dd78-131">Plan Direct Routing</span></span>](direct-routing-plan.md)
---
title: Configurare la risponderia per il routing diretto
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
description: Informazioni su come usare la risponderia per il routing diretto per evitare silenzi imprevisti che si verificano quando viene stabilita una chiamata.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: ec1500d9e7d5896d1b4cd2414355602d7400591a
ms.sourcegitcommit: 207c58563b7b2aba274b067cf64242abd7a33c2c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2020
ms.locfileid: "47405783"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a><span data-ttu-id="6d543-103">Configurare la risponderia per il routing diretto</span><span class="sxs-lookup"><span data-stu-id="6d543-103">Set up the Ringback bot for Direct Routing</span></span>

<span data-ttu-id="6d543-104">In questo articolo vengono illustrate le risponderie, che è possibile usare per evitare silenzi imprevisti che possono verificarsi quando richiede più tempo per stabilire le chiamate.</span><span class="sxs-lookup"><span data-stu-id="6d543-104">This article describes the Ringback bot, which you can use to help avoid unexpected silences that can occur when it takes a longer time for calls to be established.</span></span> <span data-ttu-id="6d543-105">La risponderia è disponibile per il routing diretto in modalità bypass non multimediale.</span><span class="sxs-lookup"><span data-stu-id="6d543-105">The Ringback bot is available for Direct Routing in non-media bypass mode.</span></span>

<span data-ttu-id="6d543-106">A volte le chiamate in ingresso dalla rete PSTN (Public Switched Telephone Network) ai client teams possono richiedere più tempo del previsto.</span><span class="sxs-lookup"><span data-stu-id="6d543-106">Sometimes inbound calls from the public switched telephone network (PSTN) to Teams clients can take longer than expected to be established.</span></span> <span data-ttu-id="6d543-107">Questo problema può verificarsi per diversi motivi.</span><span class="sxs-lookup"><span data-stu-id="6d543-107">This can occur for various reasons.</span></span> <span data-ttu-id="6d543-108">In questo caso, il chiamante potrebbe non sentire nulla, il client teams non squilla e la chiamata può essere annullata da alcuni provider di telecomunicazioni.</span><span class="sxs-lookup"><span data-stu-id="6d543-108">When this happens, the caller might not hear anything, the Teams client doesn't ring, and the call might be canceled by some telecommunications providers.</span></span>

<span data-ttu-id="6d543-109">La risponderia bot aiuta ad evitare silenzi imprevisti che possono verificarsi in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="6d543-109">The Ringback bot helps to avoid unexpected silences that can occur in this scenario.</span></span> <span data-ttu-id="6d543-110">Per le chiamate in ingresso dalla rete PSTN ai client teams, la risponderia riproduce un segnale audio distintivo per il chiamante per indicare che il team sta per stabilire la chiamata.</span><span class="sxs-lookup"><span data-stu-id="6d543-110">For inbound calls from the PSTN to Teams clients, the Ringback bot plays a distinctive audio signal to the caller to indicate that Teams is in the process of establishing the call.</span></span>

> [!NOTE]
> <span data-ttu-id="6d543-111">La risponderia genera elementi multimediali iniziali dal backend teams.</span><span class="sxs-lookup"><span data-stu-id="6d543-111">The Ringback bot generates early media from the Teams backend.</span></span> <span data-ttu-id="6d543-112">In alcuni paesi e aree geografiche potrebbe essere addebitata la chiamata quando viene avviato il flusso multimediale.</span><span class="sxs-lookup"><span data-stu-id="6d543-112">In some countries and regions, you might be charged for the call when the media starts flowing.</span></span>

## <a name="configure-the-ringback-bot"></a><span data-ttu-id="6d543-113">Configurare le risponderie</span><span class="sxs-lookup"><span data-stu-id="6d543-113">Configure the Ringback bot</span></span>

<span data-ttu-id="6d543-114">USA i cmdlet [set-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) e [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) insieme al parametro **GenerateRingingWhileLocatingUser** per configurare la risponderia.</span><span class="sxs-lookup"><span data-stu-id="6d543-114">Use the [Set-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) and [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) cmdlets together with the **GenerateRingingWhileLocatingUser** parameter to configure the Ringback bot.</span></span>

<span data-ttu-id="6d543-115">Per attivare la risponderie, imposta il parametro **GenerateRingingWhileLocatingUser** su **$true**.</span><span class="sxs-lookup"><span data-stu-id="6d543-115">To turn on the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$True**.</span></span> <span data-ttu-id="6d543-116">Questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="6d543-116">This is the default value.</span></span> 

<span data-ttu-id="6d543-117">Per disattivare la risponderia bot, imposta il parametro **GenerateRingingWhileLocatingUser** su **$false**.</span><span class="sxs-lookup"><span data-stu-id="6d543-117">To turn off the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$False**.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="6d543-118">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="6d543-118">Related topics</span></span>

- [<span data-ttu-id="6d543-119">Panoramica di PowerShell per Teams</span><span class="sxs-lookup"><span data-stu-id="6d543-119">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

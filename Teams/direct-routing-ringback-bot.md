---
title: Configurare il bot Ringback per l'instradamento diretto
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
description: Informazioni su come usare il bot Ringback per l'instradamento diretto per evitare silenzi imprevisti che possono verificarsi quando viene stabilita una chiamata.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3ec53f1d4f9cd21d3b28c87c07c1bc91d48b9b58
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098422"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a><span data-ttu-id="35fb9-103">Configurare il bot Ringback per l'instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="35fb9-103">Set up the Ringback bot for Direct Routing</span></span>

<span data-ttu-id="35fb9-104">Questo articolo descrive il bot Ringback, che è possibile usare per evitare silenzi imprevisti che possono verificarsi quando le chiamate devono essere stabilite più a lungo.</span><span class="sxs-lookup"><span data-stu-id="35fb9-104">This article describes the Ringback bot, which you can use to help avoid unexpected silences that can occur when it takes a longer time for calls to be established.</span></span> <span data-ttu-id="35fb9-105">Il bot Ringback è disponibile per il routing diretto in modalità di bypass non multimediale.</span><span class="sxs-lookup"><span data-stu-id="35fb9-105">The Ringback bot is available for Direct Routing in non-media bypass mode.</span></span>

<span data-ttu-id="35fb9-106">A volte le chiamate in ingresso dalla rete PSTN (Public Switched Telephone Network) ai client di Teams possono richiedere più tempo del previsto.</span><span class="sxs-lookup"><span data-stu-id="35fb9-106">Sometimes inbound calls from the public switched telephone network (PSTN) to Teams clients can take longer than expected to be established.</span></span> <span data-ttu-id="35fb9-107">Questo problema può verificarsi per vari motivi.</span><span class="sxs-lookup"><span data-stu-id="35fb9-107">This can occur for various reasons.</span></span> <span data-ttu-id="35fb9-108">In questo caso, il chiamante potrebbe non sentire nulla, il client teams non squilla e alcuni provider di telecomunicazioni potrebbero annullare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="35fb9-108">When this happens, the caller might not hear anything, the Teams client doesn't ring, and some telecommunications providers might cancel the call.</span></span>

<span data-ttu-id="35fb9-109">Il bot Ringback consente di evitare silenzi imprevisti che possono verificarsi in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="35fb9-109">The Ringback bot helps to avoid unexpected silences that can occur in this scenario.</span></span> <span data-ttu-id="35fb9-110">Per le chiamate in ingresso dai client PSTN a Teams, il bot Ringback riproduce un segnale audio distintivo per il chiamante per indicare che Teams è in corso di definizione della chiamata.</span><span class="sxs-lookup"><span data-stu-id="35fb9-110">For inbound calls from the PSTN to Teams clients, the Ringback bot plays a distinctive audio signal to the caller to indicate that Teams is in the process of establishing the call.</span></span>

> [!NOTE]
> <span data-ttu-id="35fb9-111">Il bot Ringback genera elementi multimediali iniziali dal back-end di Teams.</span><span class="sxs-lookup"><span data-stu-id="35fb9-111">The Ringback bot generates early media from the Teams backend.</span></span> <span data-ttu-id="35fb9-112">In alcuni paesi e aree geografiche potrebbe essere addebitato l'addebito per la chiamata all'avvio del flusso multimediale.</span><span class="sxs-lookup"><span data-stu-id="35fb9-112">In some countries and regions, you might be charged for the call when the media starts flowing.</span></span>

## <a name="configure-the-ringback-bot"></a><span data-ttu-id="35fb9-113">Configurare il bot Ringback</span><span class="sxs-lookup"><span data-stu-id="35fb9-113">Configure the Ringback bot</span></span>

<span data-ttu-id="35fb9-114">Usare il cmdlet [Set-CsOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway) per modificare una configurazione SBC (Session Border Controller) definita in precedenza oppure il cmdlet [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) per creare una nuova configurazione SBC, insieme al parametro **GenerateRingingWhileLocatingUser** per configurare il bot Ringback:</span><span class="sxs-lookup"><span data-stu-id="35fb9-114">Use the [Set-CsOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway) cmdlet to modify a previously defined Session Border Controller (SBC) configuration, or the [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) cmdlet to create a new SBC configuration, together with the **GenerateRingingWhileLocatingUser** parameter to configure the Ringback bot:</span></span>

- <span data-ttu-id="35fb9-115">Per attivare il bot Ringback, impostare il **parametro GenerateRingingWhileLocatingUser** **su $True**.</span><span class="sxs-lookup"><span data-stu-id="35fb9-115">To turn on the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$True**.</span></span> <span data-ttu-id="35fb9-116">Questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="35fb9-116">This is the default value.</span></span> 

- <span data-ttu-id="35fb9-117">Per disattivare il bot Ringback, impostare il **parametro GenerateRingingWhileLocatingUser** **su $False**.</span><span class="sxs-lookup"><span data-stu-id="35fb9-117">To turn off the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$False**.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="35fb9-118">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="35fb9-118">Related topics</span></span>

- [<span data-ttu-id="35fb9-119">Panoramica di PowerShell per Teams</span><span class="sxs-lookup"><span data-stu-id="35fb9-119">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
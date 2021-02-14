---
title: Configurare il bot Ringback per il routing diretto
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
description: Scopri come usare il bot Ringback per l'instradamento diretto per evitare silenzi imprevisti che possono verificarsi durante la chiamata.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 91cea9183a85a804ca43464aab08f417ccaff1e8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827516"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a><span data-ttu-id="2a706-103">Configurare il bot Ringback per il routing diretto</span><span class="sxs-lookup"><span data-stu-id="2a706-103">Set up the Ringback bot for Direct Routing</span></span>

<span data-ttu-id="2a706-104">Questo articolo descrive il bot di Ringback, che puoi usare per evitare silenzi imprevisti che possono verificarsi quando l'esecuzione delle chiamate richiede più tempo.</span><span class="sxs-lookup"><span data-stu-id="2a706-104">This article describes the Ringback bot, which you can use to help avoid unexpected silences that can occur when it takes a longer time for calls to be established.</span></span> <span data-ttu-id="2a706-105">Il bot Ringback è disponibile per il routing diretto in modalità di bypass non multimediale.</span><span class="sxs-lookup"><span data-stu-id="2a706-105">The Ringback bot is available for Direct Routing in non-media bypass mode.</span></span>

<span data-ttu-id="2a706-106">A volte le chiamate in ingresso dalla rete PSTN (Public Switched Telephone Network) ai client Teams possono richiedere più tempo del previsto.</span><span class="sxs-lookup"><span data-stu-id="2a706-106">Sometimes inbound calls from the public switched telephone network (PSTN) to Teams clients can take longer than expected to be established.</span></span> <span data-ttu-id="2a706-107">Questo problema può verificarsi per vari motivi.</span><span class="sxs-lookup"><span data-stu-id="2a706-107">This can occur for various reasons.</span></span> <span data-ttu-id="2a706-108">In questo caso, il chiamante potrebbe non sentire nulla, il client di Teams non squilla e alcuni provider di telecomunicazioni potrebbero annullare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="2a706-108">When this happens, the caller might not hear anything, the Teams client doesn't ring, and some telecommunications providers might cancel the call.</span></span>

<span data-ttu-id="2a706-109">Il bot Ringback consente di evitare silenzi imprevisti che possono verificarsi in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="2a706-109">The Ringback bot helps to avoid unexpected silences that can occur in this scenario.</span></span> <span data-ttu-id="2a706-110">Per le chiamate in entrata dalla rete PSTN ai client di Teams, il bot Ringback riproduce un segnale audio distintivo per il chiamante, per indicare che Teams è in corso di definizione della chiamata.</span><span class="sxs-lookup"><span data-stu-id="2a706-110">For inbound calls from the PSTN to Teams clients, the Ringback bot plays a distinctive audio signal to the caller to indicate that Teams is in the process of establishing the call.</span></span>

> [!NOTE]
> <span data-ttu-id="2a706-111">Il bot Ringback genera contenuti multimediali iniziali dal back-end di Teams.</span><span class="sxs-lookup"><span data-stu-id="2a706-111">The Ringback bot generates early media from the Teams backend.</span></span> <span data-ttu-id="2a706-112">In alcuni paesi e aree geografiche, l'addebito per la chiamata potrebbe essere addebitato all'inizio del flusso degli elementi multimediali.</span><span class="sxs-lookup"><span data-stu-id="2a706-112">In some countries and regions, you might be charged for the call when the media starts flowing.</span></span>

## <a name="configure-the-ringback-bot"></a><span data-ttu-id="2a706-113">Configurare il bot Ringback</span><span class="sxs-lookup"><span data-stu-id="2a706-113">Configure the Ringback bot</span></span>

<span data-ttu-id="2a706-114">Usa il cmdlet [Set-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) per modificare una configurazione SBC (Session Border Controller) definita in precedenza oppure il cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) per creare una nuova configurazione SBC, insieme al parametro **GenerateRingingWhileLocatingUser** per configurare il bot di Ringback:</span><span class="sxs-lookup"><span data-stu-id="2a706-114">Use the [Set-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) cmdlet to modify a previously defined Session Border Controller (SBC) configuration, or the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) cmdlet to create a new SBC configuration, together with the **GenerateRingingWhileLocatingUser** parameter to configure the Ringback bot:</span></span>

- <span data-ttu-id="2a706-115">Per attivare il bot Ringback, impostare il **parametro GenerateRingingWhileLocatingUser** **su $True.**</span><span class="sxs-lookup"><span data-stu-id="2a706-115">To turn on the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$True**.</span></span> <span data-ttu-id="2a706-116">Questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="2a706-116">This is the default value.</span></span> 

- <span data-ttu-id="2a706-117">Per disattivare il bot Ringback, impostare il **parametro GenerateRingingWhileLocatingUser** **su $False.**</span><span class="sxs-lookup"><span data-stu-id="2a706-117">To turn off the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$False**.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="2a706-118">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="2a706-118">Related topics</span></span>

- [<span data-ttu-id="2a706-119">Panoramica di PowerShell per Teams</span><span class="sxs-lookup"><span data-stu-id="2a706-119">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

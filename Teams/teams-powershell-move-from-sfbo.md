---
title: Passaggio dal connettore Skype for business online al modulo di PowerShell Teams
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Informazioni su come passa da Skype for Business Online Connector al modulo teams PowerShell per gestire i team.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e1838540e57cd91578e898818e2ed12e7b63a78
ms.sourcegitcommit: 51d94d621e3411f35622e852b699275f526600dd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2020
ms.locfileid: "48469667"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a><span data-ttu-id="18d3f-103">Passaggio dal connettore Skype for business online al modulo di PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="18d3f-103">Move from Skype for Business Online Connector to the Teams PowerShell module</span></span>

<span data-ttu-id="18d3f-104">Per cambiare l'uso di Skype for Business Online Connector con il modulo teams PowerShell per gestire i team, è necessario aggiornare gli script di PowerShell esistenti.</span><span class="sxs-lookup"><span data-stu-id="18d3f-104">To move from using Skype for Business Online Connector to the Teams PowerShell module to manage Teams, you'll need to update your existing PowerShell scripts.</span></span> <span data-ttu-id="18d3f-105">Questo articolo illustra come eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="18d3f-105">This article explains how to do this.</span></span>

1. <span data-ttu-id="18d3f-106">Installare il modulo di PowerShell più recente di teams.</span><span class="sxs-lookup"><span data-stu-id="18d3f-106">Install the latest Teams PowerShell module.</span></span> <span data-ttu-id="18d3f-107">Per i passaggi, vedere [installare Microsoft teams PowerShell](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="18d3f-107">For steps, see [Install Microsoft Teams Powershell](teams-powershell-install.md).</span></span>
2. <span data-ttu-id="18d3f-108">Disinstallare Skype for Business Online Connector.</span><span class="sxs-lookup"><span data-stu-id="18d3f-108">Uninstall Skype For Business Online Connector.</span></span> <span data-ttu-id="18d3f-109">A questo scopo, nel pannello di controllo, vai a **programmi e funzionalità**, seleziona **Skype for business online, modulo di Windows PowerShell**e quindi scegli **Disinstalla**.</span><span class="sxs-lookup"><span data-stu-id="18d3f-109">To do this, in Control Panel, go **Programs and Features**, select **Skype for Business Online, Windows PowerShell Module**, and then select **Uninstall**.</span></span> 
3. <span data-ttu-id="18d3f-110">Negli script di PowerShell modificare il nome del modulo a cui si fa riferimento in ```Import-Module``` from ```SkypeOnlineConnector``` o ```LyncOnlineConnector``` to ```MicrosoftTeams``` .</span><span class="sxs-lookup"><span data-stu-id="18d3f-110">In your PowerShell scripts, change the module name that's referenced in ```Import-Module``` from ```SkypeOnlineConnector``` or ```LyncOnlineConnector``` to ```MicrosoftTeams```.</span></span>

    <span data-ttu-id="18d3f-111">Ad esempio, cambia ```Import-Module -Name SkypeOnlineConnector``` in ```Import-Module -Name MicrosoftTeams``` .</span><span class="sxs-lookup"><span data-stu-id="18d3f-111">For example, change ```Import-Module -Name SkypeOnlineConnector``` to ```Import-Module -Name MicrosoftTeams```.</span></span>

> [!NOTE]
> <span data-ttu-id="18d3f-112">Gli amministratori devono continuare a usare [New-CsOnlineSession](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession) e importare la sessione prima di usare i cmdlet di Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="18d3f-112">Admins should continue to use [New-CsOnlineSession](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession) and import the session before using Skype for Business Online cmdlets.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="18d3f-113">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="18d3f-113">Related topics</span></span>

[<span data-ttu-id="18d3f-114">Installare Microsoft teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="18d3f-114">Install Microsoft Teams Powershell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="18d3f-115">Gestire teams con teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="18d3f-115">Manage Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="18d3f-116">Note sulla versione di PowerShell per Teams</span><span class="sxs-lookup"><span data-stu-id="18d3f-116">Teams PowerShell release notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="18d3f-117">Informazioni di riferimento sui cmdlet di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="18d3f-117">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="18d3f-118">Informazioni di riferimento sui cmdlet di Skype for business</span><span class="sxs-lookup"><span data-stu-id="18d3f-118">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

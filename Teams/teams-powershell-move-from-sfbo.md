---
title: Passare da Skype for Business Online Connector al modulo di PowerShell di Teams
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Scopri come passare da Skype for Business Online Connector al modulo di PowerShell di Teams per gestire Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5a2b502edc84c853a0a140a11f8c028b7c78aca6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094127"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a><span data-ttu-id="5ea94-103">Passare da Skype for Business Online Connector al modulo di PowerShell di Teams</span><span class="sxs-lookup"><span data-stu-id="5ea94-103">Move from Skype for Business Online Connector to the Teams PowerShell module</span></span>

<span data-ttu-id="5ea94-104">Per passare dall'uso di Skype for Business Online Connector al modulo di PowerShell di Teams per gestire Teams, è necessario aggiornare gli script di PowerShell esistenti.</span><span class="sxs-lookup"><span data-stu-id="5ea94-104">To move from using Skype for Business Online Connector to the Teams PowerShell module to manage Teams, you'll need to update your existing PowerShell scripts.</span></span> <span data-ttu-id="5ea94-105">Questo articolo spiega come eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="5ea94-105">This article explains how to do this.</span></span>

1. <span data-ttu-id="5ea94-106">Installare il modulo di PowerShell più recente di Teams.</span><span class="sxs-lookup"><span data-stu-id="5ea94-106">Install the latest Teams PowerShell module.</span></span> <span data-ttu-id="5ea94-107">Per la procedura, vedere [Installare Microsoft Teams Powershell.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="5ea94-107">For steps, see [Install Microsoft Teams Powershell](teams-powershell-install.md).</span></span>
2. <span data-ttu-id="5ea94-108">Disinstallare Skype for Business Online Connector.</span><span class="sxs-lookup"><span data-stu-id="5ea94-108">Uninstall Skype For Business Online Connector.</span></span> <span data-ttu-id="5ea94-109">Per farlo, nel Pannello di controllo vai **a** Programmi e funzionalità, seleziona Skype for **Business online, Windows PowerShell Modulo** e quindi seleziona **Disinstalla**.</span><span class="sxs-lookup"><span data-stu-id="5ea94-109">To do this, in Control Panel, go **Programs and Features**, select **Skype for Business Online, Windows PowerShell Module**, and then select **Uninstall**.</span></span> 
3. <span data-ttu-id="5ea94-110">Negli script di PowerShell modificare il nome del modulo a cui viene fatto riferimento ```Import-Module``` da ```SkypeOnlineConnector``` o in ```LyncOnlineConnector``` ```MicrosoftTeams``` .</span><span class="sxs-lookup"><span data-stu-id="5ea94-110">In your PowerShell scripts, change the module name that's referenced in ```Import-Module``` from ```SkypeOnlineConnector``` or ```LyncOnlineConnector``` to ```MicrosoftTeams```.</span></span>

    <span data-ttu-id="5ea94-111">Ad esempio, passare ```Import-Module -Name SkypeOnlineConnector``` a ```Import-Module -Name MicrosoftTeams``` .</span><span class="sxs-lookup"><span data-stu-id="5ea94-111">For example, change ```Import-Module -Name SkypeOnlineConnector``` to ```Import-Module -Name MicrosoftTeams```.</span></span>
4. <span data-ttu-id="5ea94-112">Quando si usa il modulo powershell di Teams 2.0 o versione successiva, modificare New-csOnlineSession in Connect-MicrosoftTeams.</span><span class="sxs-lookup"><span data-stu-id="5ea94-112">When using Teams PowerShell Module 2.0 or later, change New-csOnlineSession to Connect-MicrosoftTeams.</span></span> 

```powershell
  # When using Teams PowerShell Module 1.1.6
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfbSession
   
   # When using Teams PowerShell Module 2.0 or later
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

## <a name="related-topics"></a><span data-ttu-id="5ea94-113">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="5ea94-113">Related topics</span></span>

[<span data-ttu-id="5ea94-114">Installare Microsoft Teams Powershell</span><span class="sxs-lookup"><span data-stu-id="5ea94-114">Install Microsoft Teams Powershell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="5ea94-115">Gestire Teams con Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="5ea94-115">Manage Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="5ea94-116">Note sulla versione di PowerShell di Teams</span><span class="sxs-lookup"><span data-stu-id="5ea94-116">Teams PowerShell release notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="5ea94-117">Informazioni di riferimento sul cmdlet di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5ea94-117">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="5ea94-118">Informazioni di riferimento sul cmdlet di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="5ea94-118">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)
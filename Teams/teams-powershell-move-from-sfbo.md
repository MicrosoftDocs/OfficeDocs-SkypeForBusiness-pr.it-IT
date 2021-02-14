---
title: Passare da Skype for Business Online Connector al modulo PowerShell di Teams
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Informazioni su come passare da Skype for Business Online Connector al modulo Di PowerShell di Teams per gestire Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e1838540e57cd91578e898818e2ed12e7b63a78
ms.sourcegitcommit: 51d94d621e3411f35622e852b699275f526600dd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2020
ms.locfileid: "48469667"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a><span data-ttu-id="7d510-103">Passare da Skype for Business Online Connector al modulo PowerShell di Teams</span><span class="sxs-lookup"><span data-stu-id="7d510-103">Move from Skype for Business Online Connector to the Teams PowerShell module</span></span>

<span data-ttu-id="7d510-104">Per passare dall'uso di Skype for Business Online Connector al modulo PowerShell di Teams per la gestione di Teams, è necessario aggiornare gli script di PowerShell esistenti.</span><span class="sxs-lookup"><span data-stu-id="7d510-104">To move from using Skype for Business Online Connector to the Teams PowerShell module to manage Teams, you'll need to update your existing PowerShell scripts.</span></span> <span data-ttu-id="7d510-105">Questo articolo spiega come fare.</span><span class="sxs-lookup"><span data-stu-id="7d510-105">This article explains how to do this.</span></span>

1. <span data-ttu-id="7d510-106">Installare l'ultima versione del modulo Di PowerShell di Teams.</span><span class="sxs-lookup"><span data-stu-id="7d510-106">Install the latest Teams PowerShell module.</span></span> <span data-ttu-id="7d510-107">Per istruzioni, vedere [Installare Microsoft Teams Powershell.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="7d510-107">For steps, see [Install Microsoft Teams Powershell](teams-powershell-install.md).</span></span>
2. <span data-ttu-id="7d510-108">Disinstallare Skype for Business Online Connector.</span><span class="sxs-lookup"><span data-stu-id="7d510-108">Uninstall Skype For Business Online Connector.</span></span> <span data-ttu-id="7d510-109">Per farlo, nel Pannello di controllo vai a Programmi e **funzionalità,** seleziona **Skype for Business online,** Windows PowerShell modulo, quindi **seleziona Disinstalla.**</span><span class="sxs-lookup"><span data-stu-id="7d510-109">To do this, in Control Panel, go **Programs and Features**, select **Skype for Business Online, Windows PowerShell Module**, and then select **Uninstall**.</span></span> 
3. <span data-ttu-id="7d510-110">Negli script di PowerShell modificare il nome del modulo a cui viene fatto riferimento ```Import-Module``` da ```SkypeOnlineConnector``` o a ```LyncOnlineConnector``` ```MicrosoftTeams``` .</span><span class="sxs-lookup"><span data-stu-id="7d510-110">In your PowerShell scripts, change the module name that's referenced in ```Import-Module``` from ```SkypeOnlineConnector``` or ```LyncOnlineConnector``` to ```MicrosoftTeams```.</span></span>

    <span data-ttu-id="7d510-111">Ad esempio, passare ```Import-Module -Name SkypeOnlineConnector``` a ```Import-Module -Name MicrosoftTeams``` .</span><span class="sxs-lookup"><span data-stu-id="7d510-111">For example, change ```Import-Module -Name SkypeOnlineConnector``` to ```Import-Module -Name MicrosoftTeams```.</span></span>

> [!NOTE]
> <span data-ttu-id="7d510-112">Gli amministratori devono continuare a usare [New-CsOnlineSession](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession) e importare la sessione prima di usare i cmdlet di Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="7d510-112">Admins should continue to use [New-CsOnlineSession](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession) and import the session before using Skype for Business Online cmdlets.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="7d510-113">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="7d510-113">Related topics</span></span>

[<span data-ttu-id="7d510-114">Installare Microsoft Teams Powershell</span><span class="sxs-lookup"><span data-stu-id="7d510-114">Install Microsoft Teams Powershell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="7d510-115">Gestire Teams con PowerShell di Teams</span><span class="sxs-lookup"><span data-stu-id="7d510-115">Manage Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="7d510-116">Note sulla versione di PowerShell di Teams</span><span class="sxs-lookup"><span data-stu-id="7d510-116">Teams PowerShell release notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="7d510-117">Informazioni di riferimento per i cmdlet di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7d510-117">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="7d510-118">Informazioni di riferimento per i cmdlet di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="7d510-118">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

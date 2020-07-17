---
title: Panoramica di Microsoft teams PowerShell
ms.reviewer: ''
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Informazioni su come usare i controlli di PowerShell per gestire Microsoft teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5385430c7db8aab0adf1efbaec546134e9adf388
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "44943989"
---
# <a name="microsoft-teams-powershell-overview"></a><span data-ttu-id="b0baa-103">Panoramica di Microsoft teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="b0baa-103">Microsoft Teams PowerShell Overview</span></span>

<span data-ttu-id="b0baa-104">Microsoft teams PowerShell è un set di cmdlet per la gestione dei team direttamente dalla riga di comando di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b0baa-104">Microsoft Teams PowerShell is a set of cmdlets for managing Teams directly from the PowerShell command line.</span></span> <span data-ttu-id="b0baa-105">Scritto in .NET standard, teams PowerShell funziona su PowerShell 5,1 in Windows, PowerShell 6. x e versioni successive in tutte le piattaforme, incluso Azure Shell.</span><span class="sxs-lookup"><span data-stu-id="b0baa-105">Written in .NET Standard, Teams PowerShell works on PowerShell 5.1 on Windows,PowerShell 6.x and higher on all platforms including Azure Shell.</span></span>

<span data-ttu-id="b0baa-106">Prima di poter iniziare a usare PowerShell, è necessario [installarlo](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="b0baa-106">Before you can start using PowerShell, you'll need to [install it](teams-powershell-install.md).</span></span> 

> [!WARNING]
> <span data-ttu-id="b0baa-107">Sono presenti problemi noti di PowerShell 7 e teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b0baa-107">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="b0baa-108">È consigliabile usare PowerShell 5,1 fino a quando non vengono risolti i problemi.</span><span class="sxs-lookup"><span data-stu-id="b0baa-108">We recommend using PowerShell 5.1 until the issues are resolved.</span></span>

## <a name="releases"></a><span data-ttu-id="b0baa-109">Versioni</span><span class="sxs-lookup"><span data-stu-id="b0baa-109">Releases</span></span>


<span data-ttu-id="b0baa-110">Teams PowerShell è disponibile nella [raccolta di PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) in due tipi di rilascio.</span><span class="sxs-lookup"><span data-stu-id="b0baa-110">Teams PowerShell is available on [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) in two release types.</span></span>

- <span data-ttu-id="b0baa-111">**Disponibilità generale (GA)**: cmdlet pronti per la produzione, aggiornati mensilmente.</span><span class="sxs-lookup"><span data-stu-id="b0baa-111">**General Availability (GA)**: Production-ready cmdlets, updated monthly.</span></span>

- <span data-ttu-id="b0baa-112">**Anteprima pubblica**: accesso anticipato alle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="b0baa-112">**Public Preview**: Early access to features.</span></span> <span data-ttu-id="b0baa-113">Può essere aggiornato più di frequente rispetto a GA.</span><span class="sxs-lookup"><span data-stu-id="b0baa-113">May be updated more frequently than GA.</span></span>

<span data-ttu-id="b0baa-114">Per informazioni dettagliate sulle aggiunte di funzionalità e sui miglioramenti per entrambe le versioni, leggere le [Note sulla versione di PowerShell](teams-powershell-release-notes.md)per i team.</span><span class="sxs-lookup"><span data-stu-id="b0baa-114">For detailed information on feature additions and improvements for both releases, read the [Teams PowerShell release notes](teams-powershell-release-notes.md).</span></span>


## <a name="manage-teams-with-powershell"></a><span data-ttu-id="b0baa-115">Gestire team con PowerShell</span><span class="sxs-lookup"><span data-stu-id="b0baa-115">Manage Teams with PowerShell</span></span>

<span data-ttu-id="b0baa-116">Si utilizzeranno entrambi i moduli di PowerShell per gestire completamente i team:</span><span class="sxs-lookup"><span data-stu-id="b0baa-116">You'll use both of these PowerShell modules to fully manage Teams:</span></span>

- <span data-ttu-id="b0baa-117">[Modulo di PowerShell per Microsoft teams](https://www.powershellgallery.com/packages/MicrosoftTeams/): il modulo di PowerShell teams contiene i cmdlet per la gestione di Team, chat e canali.</span><span class="sxs-lookup"><span data-stu-id="b0baa-117">[Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/): The Teams PowerShell module contains cmdlets for managing teams, chat, and channels.</span></span>

- <span data-ttu-id="b0baa-118">[Modulo di PowerShell per Skype for business](https://www.microsoft.com/download/details.aspx?id=39366): il modulo di PowerShell per Skype for business contiene i cmdlet per gestire le funzionalità riunioni, sistema telefonico e criteri.</span><span class="sxs-lookup"><span data-stu-id="b0baa-118">[Skype for Business PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366): The Skype for Business PowerShell module contains the cmdlets to manage meetings, phone system, and policies features.</span></span>

<span data-ttu-id="b0baa-119">Per una guida completa alla gestione dei team che usano questi moduli, vedere [gestire team con PowerShell teams](teams-powershell-managing-teams.md).</span><span class="sxs-lookup"><span data-stu-id="b0baa-119">For a complete guide to managing Teams using these modules, please see [Manage Teams with Teams PowerShell](teams-powershell-managing-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b0baa-120">La [versione di anteprima pubblica di PowerShell per Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/) più recente è integrata con Skype for Business Online Connector, che fornisce un singolo modulo per la gestione di PowerShell per Teams.</span><span class="sxs-lookup"><span data-stu-id="b0baa-120">The latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b0baa-121">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="b0baa-121">Related topics</span></span>

[<span data-ttu-id="b0baa-122">Installazione di PowerShell per Teams</span><span class="sxs-lookup"><span data-stu-id="b0baa-122">Installing Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="b0baa-123">Gestione di team con PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="b0baa-123">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="b0baa-124">Note sulla versione di PowerShell per Teams</span><span class="sxs-lookup"><span data-stu-id="b0baa-124">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="b0baa-125">Informazioni di riferimento sui cmdlet di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b0baa-125">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="b0baa-126">Informazioni di riferimento sui cmdlet di Skype for business</span><span class="sxs-lookup"><span data-stu-id="b0baa-126">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[<span data-ttu-id="b0baa-127">Usare i ruoli di amministratore di Microsoft teams per gestire Teams</span><span class="sxs-lookup"><span data-stu-id="b0baa-127">Use Microsoft Teams admin roles to manage Teams</span></span>](using-admin-roles.md)

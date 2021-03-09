---
title: Panoramica di Microsoft Teams PowerShell
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
description: Informazioni su come usare i controlli di PowerShell per gestire Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6c2c626d61a10437fc5bb349dd128415d64448a7
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569022"
---
# <a name="microsoft-teams-powershell-overview"></a><span data-ttu-id="e9feb-103">Panoramica di Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="e9feb-103">Microsoft Teams PowerShell Overview</span></span>

<span data-ttu-id="e9feb-104">Microsoft Teams PowerShell è un set di cmdlet per la gestione di Teams direttamente dalla riga di comando di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e9feb-104">Microsoft Teams PowerShell is a set of cmdlets for managing Teams directly from the PowerShell command line.</span></span> <span data-ttu-id="e9feb-105">Scritto in .NET Standard, Teams PowerShell funziona su PowerShell 5.1 su Windows, PowerShell 6.x e versioni successive su tutte le piattaforme, tra cui Azure Cloud Shell.</span><span class="sxs-lookup"><span data-stu-id="e9feb-105">Written in .NET Standard, Teams PowerShell works on PowerShell 5.1 on Windows, PowerShell 6.x and higher on all platforms including Azure Cloud Shell.</span></span>

<span data-ttu-id="e9feb-106">Prima di iniziare a usare PowerShell, è necessario [installarlo.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="e9feb-106">Before you can start using PowerShell, you'll need to [install it](teams-powershell-install.md).</span></span> 

> [!WARNING]
> <span data-ttu-id="e9feb-107">Ci sono problemi noti con PowerShell 7 e PowerShell di Teams.</span><span class="sxs-lookup"><span data-stu-id="e9feb-107">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="e9feb-108">È consigliabile usare PowerShell 5.1 finché i problemi non verranno risolti.</span><span class="sxs-lookup"><span data-stu-id="e9feb-108">We recommend using PowerShell 5.1 until the issues are resolved.</span></span>

## <a name="releases"></a><span data-ttu-id="e9feb-109">Rilasci</span><span class="sxs-lookup"><span data-stu-id="e9feb-109">Releases</span></span>


<span data-ttu-id="e9feb-110">Teams PowerShell è disponibile nella [Raccolta PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) in due tipi di rilascio.</span><span class="sxs-lookup"><span data-stu-id="e9feb-110">Teams PowerShell is available on [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) in two release types.</span></span>

- <span data-ttu-id="e9feb-111">**Disponibilità generale:** cmdlet pronti per la produzione, aggiornati mensilmente.</span><span class="sxs-lookup"><span data-stu-id="e9feb-111">**General Availability (GA)**: Production-ready cmdlets, updated monthly.</span></span>

- <span data-ttu-id="e9feb-112">**Anteprima pubblica:** accesso anticipato alle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="e9feb-112">**Public Preview**: Early access to features.</span></span> <span data-ttu-id="e9feb-113">Possono essere aggiornati più frequentemente rispetto a Ga.</span><span class="sxs-lookup"><span data-stu-id="e9feb-113">May be updated more frequently than GA.</span></span>

<span data-ttu-id="e9feb-114">Per informazioni dettagliate sulle funzionalità aggiunte e i miglioramenti per entrambi i rilasci, leggere le note sulla versione [di Teams PowerShell.](teams-powershell-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="e9feb-114">For detailed information on feature additions and improvements for both releases, read the [Teams PowerShell release notes](teams-powershell-release-notes.md).</span></span>


## <a name="manage-teams-with-powershell"></a><span data-ttu-id="e9feb-115">Gestire Teams con PowerShell</span><span class="sxs-lookup"><span data-stu-id="e9feb-115">Manage Teams with PowerShell</span></span>

<span data-ttu-id="e9feb-116">Userai i moduli di PowerShell di Teams per gestire completamente Teams:</span><span class="sxs-lookup"><span data-stu-id="e9feb-116">You'll use Teams PowerShell modules to fully manage Teams:</span></span>

- <span data-ttu-id="e9feb-117">[Modulo Di PowerShell di Microsoft Teams:](https://www.powershellgallery.com/packages/MicrosoftTeams/)il modulo PowerShell di Teams contiene i cmdlet per la gestione di team, chat e canali.</span><span class="sxs-lookup"><span data-stu-id="e9feb-117">[Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/): The Teams PowerShell module contains cmdlets for managing teams, chat, and channels.</span></span>

> [!NOTE]
> <span data-ttu-id="e9feb-118">La [versione pubblica di Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) 1.1.6 o successiva è integrata con Skype for Business Online Connector, che fornisce un singolo modulo per la gestione di PowerShell di Teams.</span><span class="sxs-lookup"><span data-stu-id="e9feb-118">The [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) version 1.1.6 or later is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

- <span data-ttu-id="e9feb-119">[Connettore PowerShell di Skype for Business:](https://www.microsoft.com/download/details.aspx?id=39366)il connettore Di PowerShell di Skype for Business ora fa parte del modulo PowerShell di Teams.</span><span class="sxs-lookup"><span data-stu-id="e9feb-119">[Skype for Business PowerShell Connector](https://www.microsoft.com/download/details.aspx?id=39366): The Skype for Business PowerShell connector is now a part of Teams PowerShell module.</span></span>

<span data-ttu-id="e9feb-120">Per una guida completa alla gestione di Teams con questi moduli, vedere [Gestire Teams con PowerShell di Teams.](teams-powershell-managing-teams.md)</span><span class="sxs-lookup"><span data-stu-id="e9feb-120">For a complete guide to managing Teams using these modules, please see [Manage Teams with Teams PowerShell](teams-powershell-managing-teams.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="e9feb-121">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="e9feb-121">Related topics</span></span>

[<span data-ttu-id="e9feb-122">Installazione di Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="e9feb-122">Installing Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="e9feb-123">Gestione di Teams con PowerShell di Teams</span><span class="sxs-lookup"><span data-stu-id="e9feb-123">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="e9feb-124">Note sulla versione di PowerShell di Teams</span><span class="sxs-lookup"><span data-stu-id="e9feb-124">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="e9feb-125">Informazioni di riferimento per i cmdlet di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e9feb-125">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="e9feb-126">Informazioni di riferimento per i cmdlet di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e9feb-126">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[<span data-ttu-id="e9feb-127">Usare i ruoli di amministratore di Microsoft Teams per gestire Teams</span><span class="sxs-lookup"><span data-stu-id="e9feb-127">Use Microsoft Teams admin roles to manage Teams</span></span>](using-admin-roles.md)

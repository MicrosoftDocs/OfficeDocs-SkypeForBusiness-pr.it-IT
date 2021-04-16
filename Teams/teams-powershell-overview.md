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
description: Informazioni sull'uso dei controlli di PowerShell per gestire Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 448658fb844052815e14b85e0c70a33cb737b72d
ms.sourcegitcommit: 616403037ddb2d44f06cd9b2eaa9da699b119ef8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768355"
---
# <a name="microsoft-teams-powershell-overview"></a><span data-ttu-id="97281-103">Panoramica di Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="97281-103">Microsoft Teams PowerShell Overview</span></span>

<span data-ttu-id="97281-104">Microsoft Teams PowerShell è un set di cmdlet per la gestione di Teams direttamente dalla riga di comando di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="97281-104">Microsoft Teams PowerShell is a set of cmdlets for managing Teams directly from the PowerShell command line.</span></span> <span data-ttu-id="97281-105">Scritto in .NET Standard, Teams PowerShell funziona in PowerShell 5.1 in Windows, PowerShell 6.x e versioni successive in tutte le piattaforme, tra cui Azure Cloud Shell.</span><span class="sxs-lookup"><span data-stu-id="97281-105">Written in .NET Standard, Teams PowerShell works on PowerShell 5.1 on Windows, PowerShell 6.x and higher on all platforms including Azure Cloud Shell.</span></span>

<span data-ttu-id="97281-106">Prima di iniziare a usare PowerShell, è necessario [installarlo.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="97281-106">Before you can start using PowerShell, you'll need to [install it](teams-powershell-install.md).</span></span> 

> [!WARNING]
> <span data-ttu-id="97281-107">Esistono problemi noti con PowerShell 7 e Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="97281-107">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="97281-108">È consigliabile usare PowerShell 5.1 finché i problemi non vengono risolti.</span><span class="sxs-lookup"><span data-stu-id="97281-108">We recommend using PowerShell 5.1 until the issues are resolved.</span></span>

## <a name="releases"></a><span data-ttu-id="97281-109">Rilasci</span><span class="sxs-lookup"><span data-stu-id="97281-109">Releases</span></span>


<span data-ttu-id="97281-110">Teams PowerShell è disponibile nella [raccolta di PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) in due tipi di rilascio.</span><span class="sxs-lookup"><span data-stu-id="97281-110">Teams PowerShell is available on [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) in two release types.</span></span>

- <span data-ttu-id="97281-111">**Disponibilità generale:** cmdlet pronti per la produzione, aggiornati mensilmente.</span><span class="sxs-lookup"><span data-stu-id="97281-111">**General Availability (GA)**: Production-ready cmdlets, updated monthly.</span></span>

- <span data-ttu-id="97281-112">**Anteprima pubblica:** accesso anticipato alle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="97281-112">**Public Preview**: Early access to features.</span></span> <span data-ttu-id="97281-113">Può essere aggiornato più frequentemente rispetto a GA.</span><span class="sxs-lookup"><span data-stu-id="97281-113">May be updated more frequently than GA.</span></span>

<span data-ttu-id="97281-114">Per informazioni dettagliate sulle aggiunte di funzionalità e sui miglioramenti per entrambi i rilasci, leggere le note sulla versione [di PowerShell di Teams.](teams-powershell-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="97281-114">For detailed information on feature additions and improvements for both releases, read the [Teams PowerShell release notes](teams-powershell-release-notes.md).</span></span>


## <a name="manage-teams-with-powershell"></a><span data-ttu-id="97281-115">Gestire Teams con PowerShell</span><span class="sxs-lookup"><span data-stu-id="97281-115">Manage Teams with PowerShell</span></span>

<span data-ttu-id="97281-116">I moduli di PowerShell di Teams verranno utilizzati per gestire completamente Teams:</span><span class="sxs-lookup"><span data-stu-id="97281-116">You'll use Teams PowerShell modules to fully manage Teams:</span></span>

- <span data-ttu-id="97281-117">[Modulo Di PowerShell di Microsoft Teams:](https://www.powershellgallery.com/packages/MicrosoftTeams/)il modulo di PowerShell di Teams contiene cmdlet per la gestione di team, chat e canali.</span><span class="sxs-lookup"><span data-stu-id="97281-117">[Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/): The Teams PowerShell module contains cmdlets for managing teams, chat, and channels.</span></span>

> [!NOTE]
> <span data-ttu-id="97281-118">La versione pubblica di [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) 2.0 o successiva include tutti i cmdlet di Skype for Business Online Connector, che forniscono un unico modulo per la gestione di PowerShell di Teams.</span><span class="sxs-lookup"><span data-stu-id="97281-118">The [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) version 2.0 or higher includes all  Skype for Business Online Connector cmdlets, providing a single module for Teams PowerShell management.</span></span>

- <span data-ttu-id="97281-119">[Connettore PowerShell](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)di Skype for Business: il connettore di PowerShell di Skype for Business fa ora parte del modulo di PowerShell di Teams.</span><span class="sxs-lookup"><span data-stu-id="97281-119">[Skype for Business PowerShell Connector](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell): The Skype for Business PowerShell connector is now a part of Teams PowerShell module.</span></span>

<span data-ttu-id="97281-120">Per una guida completa alla gestione di Teams con questi moduli, vedere [Gestire Teams con Teams PowerShell.](teams-powershell-managing-teams.md)</span><span class="sxs-lookup"><span data-stu-id="97281-120">For a complete guide to managing Teams using these modules, please see [Manage Teams with Teams PowerShell](teams-powershell-managing-teams.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="97281-121">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="97281-121">Related topics</span></span>

[<span data-ttu-id="97281-122">Installazione di Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="97281-122">Installing Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="97281-123">Gestione di Teams con Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="97281-123">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="97281-124">Note sulla versione di PowerShell di Teams</span><span class="sxs-lookup"><span data-stu-id="97281-124">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="97281-125">Informazioni di riferimento sul cmdlet di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="97281-125">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="97281-126">Informazioni di riferimento sul cmdlet di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="97281-126">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)

[<span data-ttu-id="97281-127">Usare i ruoli di amministratore di Microsoft Teams per gestire Teams</span><span class="sxs-lookup"><span data-stu-id="97281-127">Use Microsoft Teams admin roles to manage Teams</span></span>](using-admin-roles.md)

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
ms.openlocfilehash: 6d191d4d1dbb9c3d3d2f206bce76e9d3ddd7d78d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094116"
---
# <a name="microsoft-teams-powershell-overview"></a><span data-ttu-id="4b105-103">Panoramica di Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="4b105-103">Microsoft Teams PowerShell Overview</span></span>

<span data-ttu-id="4b105-104">Microsoft Teams PowerShell è un set di cmdlet per la gestione di Teams direttamente dalla riga di comando di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4b105-104">Microsoft Teams PowerShell is a set of cmdlets for managing Teams directly from the PowerShell command line.</span></span> <span data-ttu-id="4b105-105">Scritto in .NET Standard, Teams PowerShell funziona in PowerShell 5.1 in Windows, PowerShell 6.x e versioni successive in tutte le piattaforme, tra cui Azure Cloud Shell.</span><span class="sxs-lookup"><span data-stu-id="4b105-105">Written in .NET Standard, Teams PowerShell works on PowerShell 5.1 on Windows, PowerShell 6.x and higher on all platforms including Azure Cloud Shell.</span></span>

<span data-ttu-id="4b105-106">Prima di iniziare a usare PowerShell, è necessario [installarlo.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="4b105-106">Before you can start using PowerShell, you'll need to [install it](teams-powershell-install.md).</span></span> 

> [!WARNING]
> <span data-ttu-id="4b105-107">Esistono problemi noti con PowerShell 7 e Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4b105-107">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="4b105-108">È consigliabile usare PowerShell 5.1 finché i problemi non vengono risolti.</span><span class="sxs-lookup"><span data-stu-id="4b105-108">We recommend using PowerShell 5.1 until the issues are resolved.</span></span>

## <a name="releases"></a><span data-ttu-id="4b105-109">Rilasci</span><span class="sxs-lookup"><span data-stu-id="4b105-109">Releases</span></span>


<span data-ttu-id="4b105-110">Teams PowerShell è disponibile nella [raccolta di PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) in due tipi di rilascio.</span><span class="sxs-lookup"><span data-stu-id="4b105-110">Teams PowerShell is available on [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) in two release types.</span></span>

- <span data-ttu-id="4b105-111">**Disponibilità generale:** cmdlet pronti per la produzione, aggiornati mensilmente.</span><span class="sxs-lookup"><span data-stu-id="4b105-111">**General Availability (GA)**: Production-ready cmdlets, updated monthly.</span></span>

- <span data-ttu-id="4b105-112">**Anteprima pubblica:** accesso anticipato alle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="4b105-112">**Public Preview**: Early access to features.</span></span> <span data-ttu-id="4b105-113">Può essere aggiornato più frequentemente rispetto a GA.</span><span class="sxs-lookup"><span data-stu-id="4b105-113">May be updated more frequently than GA.</span></span>

<span data-ttu-id="4b105-114">Per informazioni dettagliate sulle aggiunte di funzionalità e sui miglioramenti per entrambi i rilasci, leggere le note sulla versione [di PowerShell di Teams.](teams-powershell-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="4b105-114">For detailed information on feature additions and improvements for both releases, read the [Teams PowerShell release notes](teams-powershell-release-notes.md).</span></span>


## <a name="manage-teams-with-powershell"></a><span data-ttu-id="4b105-115">Gestire Teams con PowerShell</span><span class="sxs-lookup"><span data-stu-id="4b105-115">Manage Teams with PowerShell</span></span>

<span data-ttu-id="4b105-116">I moduli di PowerShell di Teams verranno utilizzati per gestire completamente Teams:</span><span class="sxs-lookup"><span data-stu-id="4b105-116">You'll use Teams PowerShell modules to fully manage Teams:</span></span>

- <span data-ttu-id="4b105-117">[Modulo Di PowerShell di Microsoft Teams:](https://www.powershellgallery.com/packages/MicrosoftTeams/)il modulo di PowerShell di Teams contiene cmdlet per la gestione di team, chat e canali.</span><span class="sxs-lookup"><span data-stu-id="4b105-117">[Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/): The Teams PowerShell module contains cmdlets for managing teams, chat, and channels.</span></span>

> [!NOTE]
> <span data-ttu-id="4b105-118">La versione pubblica di [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) 1.1.6 o successiva è integrata con Skype for Business Online Connector, che fornisce un unico modulo per la gestione di PowerShell di Teams.</span><span class="sxs-lookup"><span data-stu-id="4b105-118">The [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) version 1.1.6 or later is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

- <span data-ttu-id="4b105-119">[Connettore PowerShell](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)di Skype for Business: il connettore di PowerShell di Skype for Business fa ora parte del modulo di PowerShell di Teams.</span><span class="sxs-lookup"><span data-stu-id="4b105-119">[Skype for Business PowerShell Connector](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell): The Skype for Business PowerShell connector is now a part of Teams PowerShell module.</span></span>

<span data-ttu-id="4b105-120">Per una guida completa alla gestione di Teams con questi moduli, vedere [Gestire Teams con Teams PowerShell.](teams-powershell-managing-teams.md)</span><span class="sxs-lookup"><span data-stu-id="4b105-120">For a complete guide to managing Teams using these modules, please see [Manage Teams with Teams PowerShell](teams-powershell-managing-teams.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="4b105-121">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="4b105-121">Related topics</span></span>

[<span data-ttu-id="4b105-122">Installazione di Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="4b105-122">Installing Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="4b105-123">Gestione di Teams con Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="4b105-123">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="4b105-124">Note sulla versione di PowerShell di Teams</span><span class="sxs-lookup"><span data-stu-id="4b105-124">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="4b105-125">Informazioni di riferimento sul cmdlet di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4b105-125">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="4b105-126">Informazioni di riferimento sul cmdlet di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="4b105-126">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)

[<span data-ttu-id="4b105-127">Usare i ruoli di amministratore di Microsoft Teams per gestire Teams</span><span class="sxs-lookup"><span data-stu-id="4b105-127">Use Microsoft Teams admin roles to manage Teams</span></span>](using-admin-roles.md)
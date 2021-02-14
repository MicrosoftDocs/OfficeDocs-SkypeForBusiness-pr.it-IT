---
title: Creare team di gestione delle persone in Microsoft Teams
ms.reviewer: pbethi
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Informazioni su come usare uno script di PowerShell per creare un team per ogni responsabile, con i relativi diretti come membri del team.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe57656eec61747dd0a43d475444e65d8600e222
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583675"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a><span data-ttu-id="b922b-103">Creare team di gestione delle persone in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b922b-103">Create people manager teams in Microsoft Teams</span></span>


<span data-ttu-id="b922b-104">Quando si implementazione di Microsoft Teams, invece di avviarlo con una "tela vuota" (senza team o canali), si consiglia di configurare una struttura di base di team e canali.</span><span class="sxs-lookup"><span data-stu-id="b922b-104">When you roll out Microsoft Teams, rather than launching with a "blank slate" (no teams or channels), we strongly recommend that you set up a base framework of teams and channels.</span></span> <span data-ttu-id="b922b-105">In questo modo si evita che gli utenti creino numerosi team quando devono creare canali nei team esistenti.</span><span class="sxs-lookup"><span data-stu-id="b922b-105">This helps to prevent "team sprawl," where users create numerous teams when they should be creating channels in existing teams.</span></span> <span data-ttu-id="b922b-106">Per aiutarti a iniziare con una struttura ben progettata per team e canali, abbiamo creato uno script di PowerShell che crea un team per ognuno dei responsabili della prima e della seconda riga, con i relativi report diretti come membri del team.</span><span class="sxs-lookup"><span data-stu-id="b922b-106">To help you get started with a well-designed teams and channels structure, we've created a PowerShell script that creates a team for each of your first and second line people managers, with each manager's direct reports as team members.</span></span> <span data-ttu-id="b922b-107">Si tratta di uno script "tempormente" (non aggiorna automaticamente i team o i canali quando le persone vengono aggiunte o rimosse da un'organizzazione).</span><span class="sxs-lookup"><span data-stu-id="b922b-107">This is a "point-in-time" script (it doesn't update your teams or channels automatically when people are added or removed from an organization).</span></span> <span data-ttu-id="b922b-108">Si tratta di uno strumento prezioso che puoi usare per imporre un certo ordine alla struttura di Teams fin dall'inizio.</span><span class="sxs-lookup"><span data-stu-id="b922b-108">But it's a valuable tool you can use to impose some order on your Teams structure from the start.</span></span> <span data-ttu-id="b922b-109">Questo script legge Azure AD e ottiene un elenco di responsabili e i relativi report diretti.</span><span class="sxs-lookup"><span data-stu-id="b922b-109">This script reads your Azure AD, gets a list of managers and their direct reports.</span></span> <span data-ttu-id="b922b-110">Usa questo elenco per creare un team per ogni responsabile delle persone.</span><span class="sxs-lookup"><span data-stu-id="b922b-110">It uses this list to create one team per people manager.</span></span> 

## <a name="how-to-use-the-powershell-script"></a><span data-ttu-id="b922b-111">Come usare lo script di PowerShell</span><span class="sxs-lookup"><span data-stu-id="b922b-111">How to use the PowerShell script</span></span> 

<span data-ttu-id="b922b-112">Per iniziare, eseguire lo script di responsabili dell'esportazione e il relativo [script](scripts/powershell-script-create-teams-from-managers-export-managers.md) diretto, presupponendo che siano già stati eseguiti i moduli [di PowerShell Connect-AzureAd](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0) e [Connect-MicrosoftTeams.](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps)</span><span class="sxs-lookup"><span data-stu-id="b922b-112">Start by running the [Export managers and their directs script](scripts/powershell-script-create-teams-from-managers-export-managers.md) (which assumes you've already run the [Connect-AzureAd](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0) and [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell modules).</span></span> <span data-ttu-id="b922b-113">I *responsabili dell'esportazione* e il relativo script diretto creano un file con valori delimitati da tabulazioni (ExportedManagerDirects.txt) che elenca tutti i responsabili con i relativi report diretti.</span><span class="sxs-lookup"><span data-stu-id="b922b-113">The *Export managers and their directs* script creates a tab-delimited file (ExportedManagerDirects.txt) that lists all managers with their direct reports.</span></span> 

<span data-ttu-id="b922b-114">Eseguire quindi lo script Crea nuovi team di gestione [utenti.](scripts/powershell-script-create-teams-from-managers-new-teams.md)</span><span class="sxs-lookup"><span data-stu-id="b922b-114">Then, run the [Create new people manager teams script](scripts/powershell-script-create-teams-from-managers-new-teams.md).</span></span> <span data-ttu-id="b922b-115">Questo script legge il file di ExportedManagerDirects.txt e crea un team per ogni responsabile, con i relativi diretti rapporti come membri.</span><span class="sxs-lookup"><span data-stu-id="b922b-115">This script reads in the ExportedManagerDirects.txt file and creates a team for each manager, with that manager's direct reports as members.</span></span> <span data-ttu-id="b922b-116">Se un responsabile o un diretto non è abilitato per Teams, lo script lo ignora e non crea un team.</span><span class="sxs-lookup"><span data-stu-id="b922b-116">If any manager or direct isn't enabled for Teams, the script skips them and doesn't create a team.</span></span> <span data-ttu-id="b922b-117">Rivedere il report, quindi eseguire di nuovo lo script dopo aver attivato Teams per chiunque ne abbia bisogno.</span><span class="sxs-lookup"><span data-stu-id="b922b-117">(Review the report, then rerun the script after you've turned on Teams for anybody who needs it.</span></span> <span data-ttu-id="b922b-118">Lo script non crea un secondo team per qualsiasi responsabile per cui è già stato creato un team.</span><span class="sxs-lookup"><span data-stu-id="b922b-118">The script won't create a second team for any manager it's already created a team for.)</span></span>

<span data-ttu-id="b922b-119">Per ogni team, lo script crea un canale Generale e un canale "Solo per divertimento".</span><span class="sxs-lookup"><span data-stu-id="b922b-119">For each team, the script creates a General and "Just for fun" channel.</span></span> 

## <a name="best-practices"></a><span data-ttu-id="b922b-120">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="b922b-120">Best practices</span></span>

- <span data-ttu-id="b922b-121">Chiedere a ogni responsabile delle persone di aggiungere il sito Web per le comunicazioni relative alle emergenza dell'organizzazione come scheda al canale Generale di ogni team.</span><span class="sxs-lookup"><span data-stu-id="b922b-121">Ask each people manager to add your organization's crisis communications website as a tab to the General channel for each team.</span></span> 

- <span data-ttu-id="b922b-122">Consultare la nuova app Crisis Communications leggendo questo post del blog dell'8 marzo 2020: Coordinare le comunicazioni di emergenza [con Microsoft Teams + Power Platform.](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715)</span><span class="sxs-lookup"><span data-stu-id="b922b-122">Check out the new Crisis Communications app by reading this March 8, 2020 blog post: [Coordinate crisis communications using Microsoft Teams + Power Platform](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b922b-123">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="b922b-123">Related topics</span></span>

[<span data-ttu-id="b922b-124">Procedure consigliate per l'organizzazione dei team</span><span class="sxs-lookup"><span data-stu-id="b922b-124">Best practices for organizing teams</span></span>](best-practices-organizing.md)

[<span data-ttu-id="b922b-125">Creare un team a livello di organizzazione in Teams</span><span class="sxs-lookup"><span data-stu-id="b922b-125">Create an org-wide team in Teams</span></span>](create-an-org-wide-team.md)

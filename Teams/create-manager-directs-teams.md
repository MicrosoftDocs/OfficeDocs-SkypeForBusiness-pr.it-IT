---
title: Creare teams manager di persone in Microsoft Teams
ms.reviewer: pbethi
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Informazioni su come usare uno script di PowerShell per creare un team per ogni Manager con i propri dirigenti come membri del team.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: eb6cd6ed74bebd0cbd729b828c152b9f04d1fc1f
ms.sourcegitcommit: cfaae3ecbf853766de788b4825a86e04f68868ca
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "42796226"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a><span data-ttu-id="7f557-103">Creare teams manager di persone in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7f557-103">Create people manager teams in Microsoft Teams</span></span>


<span data-ttu-id="7f557-104">Quando si distribuisce Microsoft teams anziché il lancio con una "tabulazione vuota" (nessun team o canale), è consigliabile configurare un Framework di base di team e canali.</span><span class="sxs-lookup"><span data-stu-id="7f557-104">When you roll out Microsoft Teams, rather than launching with a "blank slate" (no teams or channels), we strongly recommend that you set up a base framework of teams and channels.</span></span> <span data-ttu-id="7f557-105">Questo consente di evitare "espansione del team", in cui gli utenti creano numerosi team quando devono creare canali in team esistenti.</span><span class="sxs-lookup"><span data-stu-id="7f557-105">This helps to prevent "team sprawl," where users create numerous teams when they should be creating channels in existing teams.</span></span> <span data-ttu-id="7f557-106">Per iniziare a usare una struttura di team e canali ben progettata, abbiamo creato uno script di PowerShell che crea un team per ogni manager della prima e della seconda riga, con i report diretti di ogni Manager come membri del team.</span><span class="sxs-lookup"><span data-stu-id="7f557-106">To help you get started with a well-designed teams and channels structure, we've created a PowerShell script that creates a team for each of your first and second line people managers, with each manager's direct reports as team members.</span></span> <span data-ttu-id="7f557-107">Si tratta di uno script "Point-in-Time" (non aggiorna automaticamente i team o i canali quando gli utenti vengono aggiunti o rimossi da un'organizzazione).</span><span class="sxs-lookup"><span data-stu-id="7f557-107">This is a "point-in-time" script (it doesn't update your teams or channels automatically when people are added or removed from an organization).</span></span> <span data-ttu-id="7f557-108">Ma è uno strumento valido che puoi usare per imporre un ordine nella struttura teams fin dall'inizio.</span><span class="sxs-lookup"><span data-stu-id="7f557-108">But it's a valuable tool you can use to impose some order on your Teams structure from the start.</span></span> <span data-ttu-id="7f557-109">Questo script legge il tuo Azure AD, riceve un elenco di Manager e i relativi report diretti.</span><span class="sxs-lookup"><span data-stu-id="7f557-109">This script reads your Azure AD, gets a list of managers and their direct reports.</span></span> <span data-ttu-id="7f557-110">Usa questo elenco per creare un team per Manager di persone.</span><span class="sxs-lookup"><span data-stu-id="7f557-110">It uses this list to create one team per people manager.</span></span> 

## <a name="how-to-use-the-powershell-script"></a><span data-ttu-id="7f557-111">Come usare lo script di PowerShell</span><span class="sxs-lookup"><span data-stu-id="7f557-111">How to use the PowerShell script</span></span> 

<span data-ttu-id="7f557-112">Iniziare eseguendo i [responsabili dell'esportazione e il relativo script directs](scripts/powershell-script-create-teams-from-managers-export-managers.md) (che presuppone che siano già stati eseguiti i moduli di PowerShell [Connect-AzureAd](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0) e [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) ).</span><span class="sxs-lookup"><span data-stu-id="7f557-112">Start by running the [Export managers and their directs script](scripts/powershell-script-create-teams-from-managers-export-managers.md) (which assumes you've already run the [Connect-AzureAd](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0) and [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell modules).</span></span> <span data-ttu-id="7f557-113">L' *export managers and its directs* script crea un file delimitato da tabulazioni (ExportedManagerDirects. txt) che elenca tutti i responsabili con i relativi report diretti.</span><span class="sxs-lookup"><span data-stu-id="7f557-113">The *Export managers and their directs* script creates a tab-delimited file (ExportedManagerDirects.txt) that lists all managers with their direct reports.</span></span> 

<span data-ttu-id="7f557-114">Esegui quindi lo [script crea nuovi teams manager](scripts/powershell-script-create-teams-from-managers-new-teams.md).</span><span class="sxs-lookup"><span data-stu-id="7f557-114">Then, run the [Create new people manager teams script](scripts/powershell-script-create-teams-from-managers-new-teams.md).</span></span> <span data-ttu-id="7f557-115">Questo script legge il file ExportedManagerDirects. txt e crea un team per ogni Manager, con i report diretti di tale Manager come membri.</span><span class="sxs-lookup"><span data-stu-id="7f557-115">This script reads in the ExportedManagerDirects.txt file and creates a team for each manager, with that manager's direct reports as members.</span></span> <span data-ttu-id="7f557-116">Se un Manager o Direct non è abilitato per i team, lo script li ignora e non crea un team.</span><span class="sxs-lookup"><span data-stu-id="7f557-116">If any manager or direct isn't enabled for Teams, the script skips them and doesn't create a team.</span></span> <span data-ttu-id="7f557-117">(Rivedere il report, quindi rieseguire lo script dopo aver attivato team per tutti gli utenti che ne hanno bisogno.</span><span class="sxs-lookup"><span data-stu-id="7f557-117">(Review the report, then rerun the script after you've turned on Teams for anybody who needs it.</span></span> <span data-ttu-id="7f557-118">Lo script non creerà un secondo team per qualsiasi Manager per cui è già stato creato un team.</span><span class="sxs-lookup"><span data-stu-id="7f557-118">The script won't create a second team for any manager it's already created a team for.)</span></span>

<span data-ttu-id="7f557-119">Per ogni team, lo script crea un canale generale e "solo per divertimento".</span><span class="sxs-lookup"><span data-stu-id="7f557-119">For each team, the script creates a General and "Just for fun" channel.</span></span> 

## <a name="best-practices"></a><span data-ttu-id="7f557-120">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="7f557-120">Best practices</span></span>

- <span data-ttu-id="7f557-121">Chiedere a ogni responsabile del personale di aggiungere il sito Web delle comunicazioni di crisi dell'organizzazione come Tab per il canale generale per ogni team.</span><span class="sxs-lookup"><span data-stu-id="7f557-121">Ask each people manager to add your organization's crisis communications website as a tab to the General channel for each team.</span></span> 

- <span data-ttu-id="7f557-122">Vedere la nuova app crisi Communications leggendo questo post di Blog di 2020 marzo: [coordinare le comunicazioni di crisi con Microsoft teams + Power Platform](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).</span><span class="sxs-lookup"><span data-stu-id="7f557-122">Check out the new Crisis Communications app by reading this March 8, 2020 blog post: [Coordinate crisis communications using Microsoft Teams + Power Platform](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).</span></span>

## <a name="related-topics"></a><span data-ttu-id="7f557-123">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="7f557-123">Related topics</span></span>

[<span data-ttu-id="7f557-124">Procedure consigliate per organizzare i team</span><span class="sxs-lookup"><span data-stu-id="7f557-124">Best practices for organizing teams</span></span>](best-practices-organizing.md)

[<span data-ttu-id="7f557-125">Creare un team a livello di organizzazione in Teams</span><span class="sxs-lookup"><span data-stu-id="7f557-125">Create an org-wide team in Teams</span></span>](create-an-org-wide-team.md)

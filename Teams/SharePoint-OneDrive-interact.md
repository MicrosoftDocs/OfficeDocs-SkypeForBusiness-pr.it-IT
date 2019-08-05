---
title: Come interagire con SharePoint Online e OneDrive for business con Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/08/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
search.appverid: MET150
description: Informazioni su come interagire con SharePoint Online e OneDrive for business con Microsoft teams, ad esempio la modalità di archiviazione dei file di chat privati e la relazione tra il team, il canale e la raccolta documenti.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 95e43baa0e7cd03ef08b4c9737b859f4095a64bb
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2019
ms.locfileid: "36183658"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="10fc0-103">Come interagire con SharePoint Online e OneDrive for business con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="10fc0-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="10fc0-104">Per informazioni su come interagire con i team con Azure Active Directory (AAD), Office 365 groups, Exchange, SharePoint e OneDrive for business, vedere la sessione seguente: [fondazioni di Microsoft teams](https://aka.ms/teams-foundations)</span><span class="sxs-lookup"><span data-stu-id="10fc0-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Office 365 Groups, Exchange, SharePoint and OneDrive for Business: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="10fc0-105">Ogni team di Microsoft Teams ha un sito del team in SharePoint Online e ogni canale di un team ottiene una cartella all'interno della raccolta documenti predefinita del sito del team.</span><span class="sxs-lookup"><span data-stu-id="10fc0-105">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="10fc0-106">I file condivisi all'interno di una conversazione vengono automaticamente aggiunti alla raccolta documenti e le autorizzazioni e le opzioni di sicurezza dei file impostate in SharePoint vengono automaticamente riflesse in teams.</span><span class="sxs-lookup"><span data-stu-id="10fc0-106">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="10fc0-107">I file di chat privati sono archiviati nella cartella OneDrive for business del mittente e le autorizzazioni vengono concesse automaticamente a tutti i partecipanti nell'ambito del processo di condivisione file.</span><span class="sxs-lookup"><span data-stu-id="10fc0-107">Private chat files are stored in the sender’s OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="10fc0-108">Se gli utenti non sono assegnati e abilitati con le licenze di SharePoint Online, non hanno spazio di archiviazione di OneDrive for business in Office 365.</span><span class="sxs-lookup"><span data-stu-id="10fc0-108">If users aren't assigned and enabled with SharePoint Online licenses, they don't have OneDrive for Business storage in Office 365.</span></span> <span data-ttu-id="10fc0-109">La condivisione dei file continuerà a funzionare nei canali, ma gli utenti non potranno condividere file in chat senza spazio di archiviazione di OneDrive for business in Office 365.</span><span class="sxs-lookup"><span data-stu-id="10fc0-109">File sharing will continue to work in channels, but users won't be able to share files in chats without OneDrive for Business storage in Office 365.</span></span>

<span data-ttu-id="10fc0-110">Archiviando i file nella raccolta documenti di SharePoint Online e in OneDrive for business, verranno seguite tutte le regole di conformità configurate a livello di tenant.</span><span class="sxs-lookup"><span data-stu-id="10fc0-110">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="10fc0-111">L'integrazione con SharePoint locale non è supportata per Microsoft teams in questo momento.</span><span class="sxs-lookup"><span data-stu-id="10fc0-111">Integration with SharePoint On-premises is not supported for Microsoft Teams at this time.</span></span>

<span data-ttu-id="10fc0-112">Di seguito è riportato l'esempio di relazioni tra il team, il canale e la raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="10fc0-112">The following is the example of relationships between team, channel, and document library.</span></span>

<span data-ttu-id="10fc0-113">Per ogni team, viene creato un sito di SharePoint e la cartella **documenti condivisi** è la cartella predefinita creata per il team.</span><span class="sxs-lookup"><span data-stu-id="10fc0-113">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team.</span></span> <span data-ttu-id="10fc0-114">Ogni canale, incluso il canale **generale** (il canale predefinito per ogni team) ha una cartella in **documenti condivisi**.</span><span class="sxs-lookup"><span data-stu-id="10fc0-114">Each channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![Diagramma delle cartelle documenti condivisi in SharePoint Online.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> <span data-ttu-id="10fc0-116">Non è attualmente possibile sostituire il sito e la raccolta documenti predefiniti di SharePoint con un altro.</span><span class="sxs-lookup"><span data-stu-id="10fc0-116">It's not currently possible to replace the default SharePoint site and document library with another one.</span></span> <span data-ttu-id="10fc0-117">Abbiamo sentito da te che vuoi, e lo stiamo considerando.</span><span class="sxs-lookup"><span data-stu-id="10fc0-117">We've heard from you that you want it, and we're considering it.</span></span> <span data-ttu-id="10fc0-118">Controlla la [Roadmap teams](https://aka.ms/teamsroadmap) o i [Teams UserVoice](https://aka.ms/TeamsUserVoice) per rimanere in primo piano sulle caratteristiche future.</span><span class="sxs-lookup"><span data-stu-id="10fc0-118">Check the [Teams Roadmap](https://aka.ms/teamsroadmap) or [Teams UserVoice](https://aka.ms/TeamsUserVoice) to stay on top of upcoming features.</span></span>

> [!TIP]
> <span data-ttu-id="10fc0-119">Per aggiungere una scheda al team che si collega a una pagina del sito di SharePoint esistente o alla raccolta documenti di SharePoint esistente:</span><span class="sxs-lookup"><span data-stu-id="10fc0-119">To add a tab to your team that links to an existing SharePoint site page or to your existing SharePoint document library:</span></span>
> 1. <span data-ttu-id="10fc0-120">Selezionare il segno più accanto alle schede.</span><span class="sxs-lookup"><span data-stu-id="10fc0-120">Select the  plus sign next to the tabs.</span></span>
> 2. <span data-ttu-id="10fc0-121">Selezionare **SharePoint** per una pagina del sito di SharePoint o una **raccolta documenti** esistente per una raccolta documenti esistente.</span><span class="sxs-lookup"><span data-stu-id="10fc0-121">Select either **SharePoint** for an existing SharePoint site page or **Document Library** for an existing document library.</span></span>
> 3. <span data-ttu-id="10fc0-122">Selezionare la pagina o la raccolta documenti appropriata.</span><span class="sxs-lookup"><span data-stu-id="10fc0-122">Select the appropriate page or document library.</span></span>

<span data-ttu-id="10fc0-123">Per ogni utente, la cartella OneDrive **file di chat di Microsoft teams** viene usata per archiviare tutti i file condivisi all'interno di chat private con altri utenti (1:1 o 1: many), con le autorizzazioni configurate automaticamente per limitare l'accesso solo all'utente previsto.</span><span class="sxs-lookup"><span data-stu-id="10fc0-123">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![Diagramma della cartella OneDrive denominata file di chat di Microsoft Teams](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

## <a name="channel-files-tab"></a><span data-ttu-id="10fc0-125">Scheda file di canale</span><span class="sxs-lookup"><span data-stu-id="10fc0-125">Channel Files tab</span></span>

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

<span data-ttu-id="10fc0-126">La scheda **file** in teams è simile alla visualizzazione documenti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="10fc0-126">The **Files** tab in Teams closely resembles the SharePoint documents view.</span></span> <span data-ttu-id="10fc0-127">Nella scheda **file** , gli utenti possono:</span><span class="sxs-lookup"><span data-stu-id="10fc0-127">On the **Files** tab, users can:</span></span>

- <span data-ttu-id="10fc0-128">Vedere Opzioni aggiuntive nel menu **nuovo** file.</span><span class="sxs-lookup"><span data-stu-id="10fc0-128">See additional options in the **New** file menu.</span></span>
- <span data-ttu-id="10fc0-129">Sincronizzare i file con l'unità locale.</span><span class="sxs-lookup"><span data-stu-id="10fc0-129">Sync files to their local drive.</span></span>
- <span data-ttu-id="10fc0-130">Nel menu **tutti i documenti** , passare dalla **visualizzazione elenco** a **elenco compatto** alla \*\*\*\* visualizzazione riquadri.</span><span class="sxs-lookup"><span data-stu-id="10fc0-130">On the **All Documents** menu, switch from **List** view to **Compact list** to **Tiles** view.</span></span>
- <span data-ttu-id="10fc0-131">Identificare i file che richiedono attenzione o avere malware.</span><span class="sxs-lookup"><span data-stu-id="10fc0-131">Identify files that need attention or have malware.</span></span>
- <span data-ttu-id="10fc0-132">Verificare immediatamente se un file è di sola lettura o estratto.</span><span class="sxs-lookup"><span data-stu-id="10fc0-132">Immediately see whether a file is read-only or checked out.</span></span>
- <span data-ttu-id="10fc0-133">Estrarre e archiviare i file.</span><span class="sxs-lookup"><span data-stu-id="10fc0-133">Check out and check in files.</span></span>
- <span data-ttu-id="10fc0-134">Aggiungere il PIN, sbloccare e modificare l'ordinamento dei file.</span><span class="sxs-lookup"><span data-stu-id="10fc0-134">Pin, unpin, and change the sort order of files.</span></span>
- <span data-ttu-id="10fc0-135">Identificare i file necessari per i metadati</span><span class="sxs-lookup"><span data-stu-id="10fc0-135">Identify which files need metadata</span></span>
- <span data-ttu-id="10fc0-136">Scegliere tra molte altre opzioni di filtro.</span><span class="sxs-lookup"><span data-stu-id="10fc0-136">Choose from many more filter options.</span></span>
- <span data-ttu-id="10fc0-137">Raggruppare i file in base alle intestazioni di colonna.</span><span class="sxs-lookup"><span data-stu-id="10fc0-137">Group files based on column headings.</span></span>
- <span data-ttu-id="10fc0-138">Modificare le impostazioni di colonna (spostati a sinistra o a destra, Nascondi) e larghezza colonna.</span><span class="sxs-lookup"><span data-stu-id="10fc0-138">Modify column settings (move left or right, hide) and column width.</span></span>

## <a name="default-link-type-setting"></a><span data-ttu-id="10fc0-139">Impostazione del tipo di collegamento predefinito</span><span class="sxs-lookup"><span data-stu-id="10fc0-139">Default link type setting</span></span>

<span data-ttu-id="10fc0-140">SharePoint e OneDrive hanno un'impostazione di amministratore per specificare il tipo di collegamento predefinito per i collegamenti creati per un file.</span><span class="sxs-lookup"><span data-stu-id="10fc0-140">SharePoint and OneDrive have an admin setting for specifying the default link type for links that are created for a file.</span></span> <span data-ttu-id="10fc0-141">Teams adotta lo stesso approccio riutilizzando le impostazioni impostate dall'amministratore per SharePoint e OneDrive.</span><span class="sxs-lookup"><span data-stu-id="10fc0-141">Teams is adopting that same approach by reusing the settings that the admin sets for SharePoint and OneDrive.</span></span> <span data-ttu-id="10fc0-142">Altre informazioni su questo approccio sono descritte in [modificare il tipo di collegamento predefinito quando gli utenti ottengono collegamenti per la condivisione](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span><span class="sxs-lookup"><span data-stu-id="10fc0-142">More details about this approach are described in [Change the default link type when users get links for sharing](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span></span> 

## <a name="more-information"></a><span data-ttu-id="10fc0-143">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="10fc0-143">More information</span></span>

<span data-ttu-id="10fc0-144">Per altre informazioni sul funzionamento di SharePoint con i team, vedere [SharePoint e teams: meglio insieme](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span><span class="sxs-lookup"><span data-stu-id="10fc0-144">For more information about how SharePoint works with Teams, see [SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

<span data-ttu-id="10fc0-145">Per altre informazioni sull'esperienza Guest in teams, leggere [l'esperienza Guest](guest-experience.md).</span><span class="sxs-lookup"><span data-stu-id="10fc0-145">To learn more about the guest experience in Teams, read [What the guest experience is like](guest-experience.md).</span></span>


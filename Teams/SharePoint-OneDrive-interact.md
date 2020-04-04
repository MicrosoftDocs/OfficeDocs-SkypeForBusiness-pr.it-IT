---
title: Come interagire con SharePoint Online e OneDrive for business con Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint Online & interazione di OneDrive for business con teams; archiviazione di file di chat privata & interazione tra team, canale standard & raccolta documenti.
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: fd34bf368667fcfa5776de40cad0d1444440805a
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137256"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="efce5-103">Come interagire con SharePoint Online e OneDrive for business con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="efce5-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="efce5-104">Per informazioni su come interagire con i team con Azure Active Directory (AAD), Office 365 groups, Exchange, SharePoint e OneDrive for business, vedere la sessione seguente: [fondazioni di Microsoft teams](https://aka.ms/teams-foundations)</span><span class="sxs-lookup"><span data-stu-id="efce5-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Office 365 Groups, Exchange, SharePoint and OneDrive for Business: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="efce5-105">Ogni team di Microsoft Teams ha un sito del team in SharePoint Online e ogni canale standard in un team ottiene una cartella nella raccolta documenti del sito del team predefinita.</span><span class="sxs-lookup"><span data-stu-id="efce5-105">Each team in Microsoft Teams has a team site in SharePoint Online, and each standard channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="efce5-106">I file condivisi in una conversazione vengono aggiunti automaticamente alla raccolta documenti e le autorizzazioni e opzioni di sicurezza per i file impostate in SharePoint vengono applicate automaticamente all'interno di Teams.</span><span class="sxs-lookup"><span data-stu-id="efce5-106">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span> <span data-ttu-id="efce5-107">Per vedere l'impatto della modifica di un indirizzo del sito in SharePoint, leggere [modificare l'indirizzo del sito](https://docs.microsoft.com/sharepoint/change-site-address).</span><span class="sxs-lookup"><span data-stu-id="efce5-107">To see the impact of changing a site address in SharePoint, read [Change a site address](https://docs.microsoft.com/sharepoint/change-site-address).</span></span>

> [!NOTE]
> <span data-ttu-id="efce5-108">Questo articolo si applica solo ai canali standard.</span><span class="sxs-lookup"><span data-stu-id="efce5-108">This article applies only to standard channels.</span></span> <span data-ttu-id="efce5-109">L'architettura per i canali privati è diversa dai canali standard.</span><span class="sxs-lookup"><span data-stu-id="efce5-109">The architecture for private channels is different from standard channels.</span></span> <span data-ttu-id="efce5-110">Ogni canale privato ha una propria raccolta siti di SharePoint separata dal sito del team padre.</span><span class="sxs-lookup"><span data-stu-id="efce5-110">Each private channel has its own SharePoint site collection that's separate from the parent team site.</span></span> <span data-ttu-id="efce5-111">Per altre informazioni, vedere [canali privati in Microsoft teams](private-channels.md).</span><span class="sxs-lookup"><span data-stu-id="efce5-111">To learn more, see [Private channels in Microsoft Teams](private-channels.md).</span></span>

<span data-ttu-id="efce5-112">I file di chat privati sono archiviati nella cartella OneDrive for business del mittente e le autorizzazioni vengono concesse automaticamente a tutti i partecipanti nell'ambito del processo di condivisione file.</span><span class="sxs-lookup"><span data-stu-id="efce5-112">Private chat files are stored in the sender's OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="efce5-113">Se gli utenti non sono assegnati e abilitati con le licenze di SharePoint Online, non hanno spazio di archiviazione di OneDrive for business in Office 365.</span><span class="sxs-lookup"><span data-stu-id="efce5-113">If users aren't assigned and enabled with SharePoint Online licenses, they don't have OneDrive for Business storage in Office 365.</span></span> <span data-ttu-id="efce5-114">La condivisione dei file continuerà a funzionare nei canali standard, ma gli utenti non potranno condividere file in chat senza spazio di archiviazione di OneDrive for business in Office 365.</span><span class="sxs-lookup"><span data-stu-id="efce5-114">File sharing will continue to work in standard channels, but users won't be able to share files in chats without OneDrive for Business storage in Office 365.</span></span>

<span data-ttu-id="efce5-115">Archiviando i file nella raccolta documenti di SharePoint Online e in OneDrive for Business, verranno rispettate tutte le regole di conformità configurate a livello di tenant.</span><span class="sxs-lookup"><span data-stu-id="efce5-115">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="efce5-116">L'integrazione con SharePoint locale non è supportata per Microsoft teams in questo momento.</span><span class="sxs-lookup"><span data-stu-id="efce5-116">Integration with SharePoint On-premises is not supported for Microsoft Teams at this time.</span></span>

<span data-ttu-id="efce5-117">Di seguito è riportato l'esempio di relazioni tra team, canale standard e raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="efce5-117">The following is the example of relationships between team, standard channel, and document library.</span></span>

<span data-ttu-id="efce5-118">Per ogni team, viene creato un sito di SharePoint e la cartella **documenti condivisi** è la cartella predefinita creata per il team.</span><span class="sxs-lookup"><span data-stu-id="efce5-118">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team.</span></span> <span data-ttu-id="efce5-119">Ogni canale standard, incluso il canale **generale** (il canale predefinito per ogni team) ha una cartella in **documenti condivisi**.</span><span class="sxs-lookup"><span data-stu-id="efce5-119">Each standard channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![Diagramma delle cartelle documenti condivisi in SharePoint Online.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> <span data-ttu-id="efce5-121">Non è attualmente possibile sostituire il sito e la raccolta documenti predefiniti di SharePoint con un altro.</span><span class="sxs-lookup"><span data-stu-id="efce5-121">It's not currently possible to replace the default SharePoint site and document library with another one.</span></span> <span data-ttu-id="efce5-122">Abbiamo sentito da te che vuoi, e lo stiamo considerando.</span><span class="sxs-lookup"><span data-stu-id="efce5-122">We've heard from you that you want it, and we're considering it.</span></span> <span data-ttu-id="efce5-123">Controlla la [Roadmap teams](https://aka.ms/teamsroadmap) o i [Teams UserVoice](https://aka.ms/TeamsUserVoice) per rimanere in primo piano sulle caratteristiche future.</span><span class="sxs-lookup"><span data-stu-id="efce5-123">Check the [Teams Roadmap](https://aka.ms/teamsroadmap) or [Teams UserVoice](https://aka.ms/TeamsUserVoice) to stay on top of upcoming features.</span></span>

> [!TIP]
> <span data-ttu-id="efce5-124">Per aggiungere una scheda al team che si collega a una pagina del sito di SharePoint esistente o alla raccolta documenti di SharePoint esistente:</span><span class="sxs-lookup"><span data-stu-id="efce5-124">To add a tab to your team that links to an existing SharePoint site page or to your existing SharePoint document library:</span></span>
> 1. <span data-ttu-id="efce5-125">Selezionare il segno più accanto alle schede.</span><span class="sxs-lookup"><span data-stu-id="efce5-125">Select the  plus sign next to the tabs.</span></span>
> 2. <span data-ttu-id="efce5-126">Selezionare **SharePoint** per una pagina del sito di SharePoint o una **raccolta documenti** esistente per una raccolta documenti esistente.</span><span class="sxs-lookup"><span data-stu-id="efce5-126">Select either **SharePoint** for an existing SharePoint site page or **Document Library** for an existing document library.</span></span>
> 3. <span data-ttu-id="efce5-127">Selezionare la pagina o la raccolta documenti appropriata.</span><span class="sxs-lookup"><span data-stu-id="efce5-127">Select the appropriate page or document library.</span></span>

<span data-ttu-id="efce5-128">Per ogni utente, la cartella OneDrive **file di chat di Microsoft teams** viene usata per archiviare tutti i file condivisi all'interno di chat private con altri utenti (1:1 o 1: many), con le autorizzazioni configurate automaticamente per limitare l'accesso solo all'utente previsto.</span><span class="sxs-lookup"><span data-stu-id="efce5-128">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![Diagramma della cartella OneDrive denominata file di chat di Microsoft Teams](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

## <a name="channel-files-tab"></a><span data-ttu-id="efce5-130">Scheda file di canale</span><span class="sxs-lookup"><span data-stu-id="efce5-130">Channel Files tab</span></span>

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

<span data-ttu-id="efce5-131">La scheda **file** in teams è simile alla visualizzazione documenti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="efce5-131">The **Files** tab in Teams closely resembles the SharePoint documents view.</span></span> <span data-ttu-id="efce5-132">Nella scheda **file** , gli utenti possono:</span><span class="sxs-lookup"><span data-stu-id="efce5-132">On the **Files** tab, users can:</span></span>

- <span data-ttu-id="efce5-133">Vedere Opzioni aggiuntive nel menu **nuovo** file.</span><span class="sxs-lookup"><span data-stu-id="efce5-133">See additional options in the **New** file menu.</span></span>
- <span data-ttu-id="efce5-134">Sincronizzare i file con l'unità locale.</span><span class="sxs-lookup"><span data-stu-id="efce5-134">Sync files to their local drive.</span></span>
- <span data-ttu-id="efce5-135">Nel menu **tutti i documenti** , passare dalla **visualizzazione elenco** a **elenco compatto** alla visualizzazione **riquadri** .</span><span class="sxs-lookup"><span data-stu-id="efce5-135">On the **All Documents** menu, switch from **List** view to **Compact list** to **Tiles** view.</span></span>
- <span data-ttu-id="efce5-136">Identificare i file che richiedono attenzione o avere malware.</span><span class="sxs-lookup"><span data-stu-id="efce5-136">Identify files that need attention or have malware.</span></span>
- <span data-ttu-id="efce5-137">Verificare immediatamente se un file è di sola lettura o estratto.</span><span class="sxs-lookup"><span data-stu-id="efce5-137">Immediately see whether a file is read-only or checked out.</span></span>
- <span data-ttu-id="efce5-138">Estrarre e archiviare i file.</span><span class="sxs-lookup"><span data-stu-id="efce5-138">Check out and check in files.</span></span>
- <span data-ttu-id="efce5-139">Aggiungere il PIN, sbloccare e modificare l'ordinamento dei file.</span><span class="sxs-lookup"><span data-stu-id="efce5-139">Pin, unpin, and change the sort order of files.</span></span>
- <span data-ttu-id="efce5-140">Identificare i file necessari per i metadati</span><span class="sxs-lookup"><span data-stu-id="efce5-140">Identify which files need metadata</span></span>
- <span data-ttu-id="efce5-141">Scegliere tra molte altre opzioni di filtro.</span><span class="sxs-lookup"><span data-stu-id="efce5-141">Choose from many more filter options.</span></span>
- <span data-ttu-id="efce5-142">Raggruppare i file in base alle intestazioni di colonna.</span><span class="sxs-lookup"><span data-stu-id="efce5-142">Group files based on column headings.</span></span>
- <span data-ttu-id="efce5-143">Modificare le impostazioni di colonna (spostati a sinistra o a destra, Nascondi) e larghezza colonna.</span><span class="sxs-lookup"><span data-stu-id="efce5-143">Modify column settings (move left or right, hide) and column width.</span></span>

## <a name="default-link-type-setting"></a><span data-ttu-id="efce5-144">Impostazione del tipo di collegamento predefinito</span><span class="sxs-lookup"><span data-stu-id="efce5-144">Default link type setting</span></span>

<span data-ttu-id="efce5-145">SharePoint e OneDrive hanno un'impostazione di amministratore per specificare il tipo di collegamento predefinito per i collegamenti creati per un file.</span><span class="sxs-lookup"><span data-stu-id="efce5-145">SharePoint and OneDrive have an admin setting for specifying the default link type for links that are created for a file.</span></span> <span data-ttu-id="efce5-146">Teams adotta lo stesso approccio riutilizzando le impostazioni impostate dall'amministratore per SharePoint e OneDrive.</span><span class="sxs-lookup"><span data-stu-id="efce5-146">Teams is adopting that same approach by reusing the settings that the admin sets for SharePoint and OneDrive.</span></span> <span data-ttu-id="efce5-147">Altre informazioni su questo approccio sono descritte in [modificare il tipo di collegamento predefinito quando gli utenti ottengono collegamenti per la condivisione](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span><span class="sxs-lookup"><span data-stu-id="efce5-147">More details about this approach are described in [Change the default link type when users get links for sharing](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span></span> 

## <a name="more-information"></a><span data-ttu-id="efce5-148">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="efce5-148">More information</span></span>

<span data-ttu-id="efce5-149">Per altre informazioni sul funzionamento di SharePoint con i team, vedere [SharePoint e teams: meglio insieme](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span><span class="sxs-lookup"><span data-stu-id="efce5-149">For more information about how SharePoint works with Teams, see [SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

<span data-ttu-id="efce5-150">Per altre informazioni sull'esperienza Guest in teams, leggere [l'esperienza Guest](guest-experience.md).</span><span class="sxs-lookup"><span data-stu-id="efce5-150">To learn more about the guest experience in Teams, read [What the guest experience is like](guest-experience.md).</span></span>


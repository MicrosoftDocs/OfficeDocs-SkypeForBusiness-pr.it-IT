---
title: Modalità di interazione di SharePoint Online e OneDrive for Business con Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint Online & l'interazione di OneDrive for Business con Teams; Archiviazione di file di chat privata &'interazione tra team, canale standard, & raccolta documenti.
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2d063cae8b87ffcacd63676da17fc000384c432c
ms.sourcegitcommit: a731226d62d8b23fe73bd7bf61654e16367fbd90
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2021
ms.locfileid: "51948624"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="2aba6-103">Modalità di interazione di SharePoint Online e OneDrive for Business con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2aba6-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="2aba6-104">Per informazioni sull’interazione tra Teams e Azure Active Directory (AAD), i Gruppi di Microsoft 365, Exchange, SharePoint e OneDrive for Business, vedere la sessione: [Nozioni di base di Microsoft Teams](https://aka.ms/teams-foundations)</span><span class="sxs-lookup"><span data-stu-id="2aba6-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Microsoft 365 Groups, Exchange, SharePoint and OneDrive for Business: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="2aba6-105">Ogni team in Microsoft Teams ha un sito del team in SharePoint Online e ogni canale standard di un team ottiene una cartella all'interno della raccolta documenti predefinita del sito del team.</span><span class="sxs-lookup"><span data-stu-id="2aba6-105">Each team in Microsoft Teams has a team site in SharePoint Online, and each standard channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="2aba6-106">I file condivisi in una conversazione vengono aggiunti automaticamente alla raccolta documenti e le autorizzazioni e opzioni di sicurezza per i file impostate in SharePoint vengono applicate automaticamente all'interno di Teams.</span><span class="sxs-lookup"><span data-stu-id="2aba6-106">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span> <span data-ttu-id="2aba6-107">Per vedere l'impatto della modifica dell'indirizzo di un sito in SharePoint, vedere [Modificare l'indirizzo di un sito.](/sharepoint/change-site-address)</span><span class="sxs-lookup"><span data-stu-id="2aba6-107">To see the impact of changing a site address in SharePoint, read [Change a site address](/sharepoint/change-site-address).</span></span>

> [!NOTE]
> <span data-ttu-id="2aba6-108">Questo articolo si applica solo ai canali standard.</span><span class="sxs-lookup"><span data-stu-id="2aba6-108">This article applies only to standard channels.</span></span> <span data-ttu-id="2aba6-109">L'architettura per i canali privati è diversa dai canali standard.</span><span class="sxs-lookup"><span data-stu-id="2aba6-109">The architecture for private channels is different from standard channels.</span></span> <span data-ttu-id="2aba6-110">Ogni canale privato ha una raccolta siti di SharePoint separata dal sito del team padre.</span><span class="sxs-lookup"><span data-stu-id="2aba6-110">Each private channel has its own SharePoint site collection that's separate from the parent team site.</span></span> <span data-ttu-id="2aba6-111">Per altre informazioni, vedere [Canali privati in Microsoft Teams.](private-channels.md)</span><span class="sxs-lookup"><span data-stu-id="2aba6-111">To learn more, see [Private channels in Microsoft Teams](private-channels.md).</span></span>

<span data-ttu-id="2aba6-112">I file di chat privati vengono archiviati nella cartella OneDrive for Business del mittente e le autorizzazioni vengono concesse automaticamente a tutti i partecipanti nell'ambito del processo di condivisione dei file.</span><span class="sxs-lookup"><span data-stu-id="2aba6-112">Private chat files are stored in the sender's OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="2aba6-113">Se gli utenti non vengono assegnati e abilitati tramite licenze di SharePoint Online, non possono sfruttare l'archiviazione OneDrive for Business in Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="2aba6-113">If users aren't assigned and enabled with SharePoint Online licenses, they don't have OneDrive for Business storage in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="2aba6-114">La condivisione di file continuerà a funzionare nei canali standard, ma gli utenti non potranno condividere file nelle chat senza spazio di archiviazione di OneDrive for Business in Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="2aba6-114">File sharing will continue to work in standard channels, but users won't be able to share files in chats without OneDrive for Business storage in Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="2aba6-115">Archiviando i file nella raccolta documenti di SharePoint Online e in OneDrive for Business, verranno rispettate tutte le regole di conformità configurate a livello di tenant.</span><span class="sxs-lookup"><span data-stu-id="2aba6-115">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="2aba6-116">Al momento l'integrazione con SharePoint locale non è supportata per Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2aba6-116">Integration with SharePoint On-premises is not supported for Microsoft Teams at this time.</span></span>

<span data-ttu-id="2aba6-117">Di seguito è riportato l'esempio di relazioni tra il team, il canale standard e la raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="2aba6-117">The following is the example of relationships between team, standard channel, and document library.</span></span>

<span data-ttu-id="2aba6-118">Per ogni team viene creato un sito di SharePoint e la cartella Documenti **condivisi** è la cartella predefinita creata per il team.</span><span class="sxs-lookup"><span data-stu-id="2aba6-118">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team.</span></span> <span data-ttu-id="2aba6-119">Ogni canale standard, incluso **il canale Generale** (il canale predefinito per ogni team), ha una cartella in Documenti **condivisi.**</span><span class="sxs-lookup"><span data-stu-id="2aba6-119">Each standard channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![Diagramma delle cartelle Documenti condivisi in SharePoint Online.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> <span data-ttu-id="2aba6-121">Al momento non è possibile sostituire il sito e la raccolta documenti di SharePoint predefiniti con un altro.</span><span class="sxs-lookup"><span data-stu-id="2aba6-121">It's not currently possible to replace the default SharePoint site and document library with another one.</span></span> <span data-ttu-id="2aba6-122">Abbiamo sentito da te che lo desideri, e lo stiamo valutando.</span><span class="sxs-lookup"><span data-stu-id="2aba6-122">We've heard from you that you want it, and we're considering it.</span></span> <span data-ttu-id="2aba6-123">Consulta la [roadmap di Teams](https://aka.ms/teamsroadmap) o Teams [UserVoice](https://aka.ms/TeamsUserVoice) per essere sempre al corrente delle funzionalità imminenti.</span><span class="sxs-lookup"><span data-stu-id="2aba6-123">Check the [Teams Roadmap](https://aka.ms/teamsroadmap) or [Teams UserVoice](https://aka.ms/TeamsUserVoice) to stay on top of upcoming features.</span></span>

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

> [!TIP]
> <span data-ttu-id="2aba6-124">Per aggiungere al team una scheda collegata a una pagina del sito di SharePoint esistente o alla raccolta documenti di SharePoint esistente:</span><span class="sxs-lookup"><span data-stu-id="2aba6-124">To add a tab to your team that links to an existing SharePoint site page or to your existing SharePoint document library:</span></span>
> 1. <span data-ttu-id="2aba6-125">Selezionare il segno più accanto alle schede.</span><span class="sxs-lookup"><span data-stu-id="2aba6-125">Select the  plus sign next to the tabs.</span></span>
> 2. <span data-ttu-id="2aba6-126">Selezionare **SharePoint per** una pagina del sito di SharePoint esistente o una **raccolta documenti** per una raccolta documenti esistente.</span><span class="sxs-lookup"><span data-stu-id="2aba6-126">Select either **SharePoint** for an existing SharePoint site page or **Document Library** for an existing document library.</span></span>
> 3. <span data-ttu-id="2aba6-127">Selezionare la pagina o la raccolta documenti appropriata.</span><span class="sxs-lookup"><span data-stu-id="2aba6-127">Select the appropriate page or document library.</span></span>

<span data-ttu-id="2aba6-128">Per ogni utente, la cartella OneDrive File chat di **Microsoft Teams** viene usata per archiviare tutti i file condivisi all'interno di chat private con altri utenti (1:1 o 1:molti), con le autorizzazioni configurate automaticamente per limitare l'accesso solo all'utente previsto.</span><span class="sxs-lookup"><span data-stu-id="2aba6-128">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![Diagramma della cartella OneDrive denominata File di chat di Microsoft Teams](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

<span data-ttu-id="2aba6-130">Si noti che per i team pubblici, viene eseguito il provisioning del sito del team di SharePoint con accesso "Tutti tranne gli utenti esterni".</span><span class="sxs-lookup"><span data-stu-id="2aba6-130">Note that for public teams, the SharePoint team site is provisioned with "Everyone except external users" access.</span></span> <span data-ttu-id="2aba6-131">Il team pubblico non viene visualizzato in Teams per le persone che non sono membri del team.</span><span class="sxs-lookup"><span data-stu-id="2aba6-131">The public team isn't displayed in Teams for people who aren't members of that team.</span></span> <span data-ttu-id="2aba6-132">Tuttavia, possono accedere al contenuto del sito del team di SharePoint usando l'URL del sito del team di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2aba6-132">However, they can access content on the SharePoint team site using the URL of the SharePoint team site.</span></span> 

## <a name="channel-files-tab"></a><span data-ttu-id="2aba6-133">Scheda File del canale</span><span class="sxs-lookup"><span data-stu-id="2aba6-133">Channel Files tab</span></span>

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

<span data-ttu-id="2aba6-134">La **scheda File** in Teams è molto simile alla visualizzazione documenti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2aba6-134">The **Files** tab in Teams closely resembles the SharePoint documents view.</span></span> <span data-ttu-id="2aba6-135">Nella scheda **File** gli utenti possono:</span><span class="sxs-lookup"><span data-stu-id="2aba6-135">On the **Files** tab, users can:</span></span>

- <span data-ttu-id="2aba6-136">Vedere altre opzioni **nel** menu Nuovo file.</span><span class="sxs-lookup"><span data-stu-id="2aba6-136">See additional options in the **New** file menu.</span></span>
- <span data-ttu-id="2aba6-137">Sincronizzare i file con l'unità locale.</span><span class="sxs-lookup"><span data-stu-id="2aba6-137">Sync files to their local drive.</span></span>
- <span data-ttu-id="2aba6-138">Nel menu **Tutti i documenti** passare dalla visualizzazione **Elenco** alla visualizzazione **Elenco compatto** alla **visualizzazione** Riquadri.</span><span class="sxs-lookup"><span data-stu-id="2aba6-138">On the **All Documents** menu, switch from **List** view to **Compact list** to **Tiles** view.</span></span>
- <span data-ttu-id="2aba6-139">Identificare i file che necessitano di attenzione o che hanno malware.</span><span class="sxs-lookup"><span data-stu-id="2aba6-139">Identify files that need attention or have malware.</span></span>
- <span data-ttu-id="2aba6-140">Verificare immediatamente se un file è di sola lettura o estratto.</span><span class="sxs-lookup"><span data-stu-id="2aba6-140">Immediately see whether a file is read-only or checked out.</span></span>
- <span data-ttu-id="2aba6-141">Estrarre e archiviare i file.</span><span class="sxs-lookup"><span data-stu-id="2aba6-141">Check out and check in files.</span></span>
- <span data-ttu-id="2aba6-142">Aggiungere, rimuovere e modificare l'ordinamento dei file.</span><span class="sxs-lookup"><span data-stu-id="2aba6-142">Pin, unpin, and change the sort order of files.</span></span>
- <span data-ttu-id="2aba6-143">Identificare i file che necessitano di metadati</span><span class="sxs-lookup"><span data-stu-id="2aba6-143">Identify which files need metadata</span></span>
- <span data-ttu-id="2aba6-144">Scegliere tra molte altre opzioni di filtro.</span><span class="sxs-lookup"><span data-stu-id="2aba6-144">Choose from many more filter options.</span></span>
- <span data-ttu-id="2aba6-145">Raggruppare i file in base alle intestazioni di colonna.</span><span class="sxs-lookup"><span data-stu-id="2aba6-145">Group files based on column headings.</span></span>
- <span data-ttu-id="2aba6-146">Modificare le impostazioni delle colonne (spostarsi a sinistra o a destra, nascondere) e la larghezza delle colonne.</span><span class="sxs-lookup"><span data-stu-id="2aba6-146">Modify column settings (move left or right, hide) and column width.</span></span>

## <a name="default-link-type-setting"></a><span data-ttu-id="2aba6-147">Impostazione del tipo di collegamento predefinito</span><span class="sxs-lookup"><span data-stu-id="2aba6-147">Default link type setting</span></span>

<span data-ttu-id="2aba6-148">SharePoint e OneDrive hanno un'impostazione di amministratore per specificare il tipo di collegamento predefinito per i collegamenti creati per un file.</span><span class="sxs-lookup"><span data-stu-id="2aba6-148">SharePoint and OneDrive have an admin setting for specifying the default link type for links that are created for a file.</span></span> <span data-ttu-id="2aba6-149">Teams adotta lo stesso approccio riutilizzando le impostazioni impostate dall'amministratore per SharePoint e OneDrive.</span><span class="sxs-lookup"><span data-stu-id="2aba6-149">Teams is adopting that same approach by reusing the settings that the admin sets for SharePoint and OneDrive.</span></span> <span data-ttu-id="2aba6-150">Per altre informazioni su questo approccio, vedere Modificare il tipo di collegamento predefinito quando gli utenti [ottengono collegamenti per la condivisione.](/sharepoint/change-default-sharing-link)</span><span class="sxs-lookup"><span data-stu-id="2aba6-150">More details about this approach are described in [Change the default link type when users get links for sharing](/sharepoint/change-default-sharing-link).</span></span> 

## <a name="more-information"></a><span data-ttu-id="2aba6-151">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="2aba6-151">More information</span></span>

<span data-ttu-id="2aba6-152">Per altre informazioni sul funzionamento di SharePoint con Teams, vedere [SharePoint e Teams: meglio insieme.](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)</span><span class="sxs-lookup"><span data-stu-id="2aba6-152">For more information about how SharePoint works with Teams, see [SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

<span data-ttu-id="2aba6-153">Per altre informazioni sull'esperienza degli utenti guest in Teams, vedere [Com'è l'esperienza guest.](guest-experience.md)</span><span class="sxs-lookup"><span data-stu-id="2aba6-153">To learn more about the guest experience in Teams, read [What the guest experience is like](guest-experience.md).</span></span>
---
title: Come SharePoint e OneDrive con Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint & OneDrive'interazione con Teams; Archiviazione di file di chat privata &'interazione tra team, canale standard, & raccolta documenti.
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 21abc840ddc740d7d842767c6c864d8ff5b598dd
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2021
ms.locfileid: "52855955"
---
# <a name="how-sharepoint-and-onedrive-interact-with-microsoft-teams"></a><span data-ttu-id="5fef0-103">Come SharePoint e OneDrive con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5fef0-103">How SharePoint and OneDrive interact with Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="5fef0-104">Guardare la sessione seguente per informazioni su come Teams interagisce con Azure Active Directory (AAD), Microsoft 365 Groups, Exchange, SharePoint e OneDrive: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span><span class="sxs-lookup"><span data-stu-id="5fef0-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Microsoft 365 Groups, Exchange, SharePoint and OneDrive: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="5fef0-105">Ogni team di Microsoft Teams ha un sito del team in SharePoint e ogni canale standard di un team ottiene una cartella all'interno della raccolta documenti del sito del team predefinita.</span><span class="sxs-lookup"><span data-stu-id="5fef0-105">Each team in Microsoft Teams has a team site in SharePoint, and each standard channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="5fef0-106">Ogni [canale privato](private-channels.md) ottiene un sito SharePoint privato.</span><span class="sxs-lookup"><span data-stu-id="5fef0-106">Each [private channel](private-channels.md) gets its own, separate SharePoint site.</span></span>

<span data-ttu-id="5fef0-107">I file condivisi in una conversazione vengono aggiunti automaticamente alla raccolta documenti e le autorizzazioni e opzioni di sicurezza per i file impostate in SharePoint vengono applicate automaticamente all'interno di Teams.</span><span class="sxs-lookup"><span data-stu-id="5fef0-107">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span> <span data-ttu-id="5fef0-108">Per vedere l'impatto della modifica dell'indirizzo di un sito in SharePoint, vedere [Modificare l'indirizzo di un sito.](/sharepoint/change-site-address)</span><span class="sxs-lookup"><span data-stu-id="5fef0-108">To see the impact of changing a site address in SharePoint, read [Change a site address](/sharepoint/change-site-address).</span></span>

<span data-ttu-id="5fef0-109">I file di chat privati vengono archiviati nella cartella OneDrive del mittente e le autorizzazioni vengono concesse automaticamente a tutti i partecipanti nell'ambito del processo di condivisione file.</span><span class="sxs-lookup"><span data-stu-id="5fef0-109">Private chat files are stored in the sender's OneDrive folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="5fef0-110">Se agli utenti non sono assegnate SharePoint licenze, non hanno OneDrive di archiviazione in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5fef0-110">If users aren't assigned SharePoint licenses, they don't have OneDrive storage in Microsoft 365.</span></span> <span data-ttu-id="5fef0-111">La condivisione di file funziona nei canali standard, ma gli utenti non saranno in grado di condividere file nelle chat senza OneDrive archiviazione in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5fef0-111">File sharing works in standard channels, but users won't be able to share files in chats without OneDrive storage in Microsoft 365.</span></span>

<span data-ttu-id="5fef0-112">Archiviando i file nella raccolta SharePoint documenti OneDrive, verranno seguite tutte le regole di conformità configurate a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5fef0-112">By storing the files in the SharePoint document library and OneDrive, all compliance rules configured at the organization level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="5fef0-113">L'integrazione con SharePoint Server non è supportata per Teams.</span><span class="sxs-lookup"><span data-stu-id="5fef0-113">Integration with SharePoint Server is not supported for Teams.</span></span>

<span data-ttu-id="5fef0-114">Di seguito è riportato l'esempio di relazioni tra il team, il canale standard e la raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="5fef0-114">The following is the example of relationships between team, standard channel, and document library.</span></span>

<span data-ttu-id="5fef0-115">Per ogni team viene creato SharePoint sito di lavoro e la cartella Documenti **condivisi** è la cartella predefinita creata per il team.</span><span class="sxs-lookup"><span data-stu-id="5fef0-115">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team.</span></span> <span data-ttu-id="5fef0-116">Ogni canale standard, incluso **il canale Generale** (il canale predefinito per ogni team), ha una cartella in Documenti **condivisi.**</span><span class="sxs-lookup"><span data-stu-id="5fef0-116">Each standard channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![Diagramma delle cartelle Documenti condivisi In SharePoint.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

<span data-ttu-id="5fef0-118">Il sito SharePoint e la raccolta documenti predefiniti non possono essere sostituiti con uno diverso.</span><span class="sxs-lookup"><span data-stu-id="5fef0-118">The default SharePoint site and document library can't be replaced with a different one.</span></span>

<span data-ttu-id="5fef0-119">Per ogni utente, la cartella OneDrive **Microsoft Teams File chat** viene usata per archiviare tutti i file condivisi nelle chat private con altri utenti (1:1 o 1:molti), con le autorizzazioni configurate automaticamente per limitare l'accesso solo all'utente previsto.</span><span class="sxs-lookup"><span data-stu-id="5fef0-119">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![Diagramma della cartella OneDrive denominata Microsoft Teams chat](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

<span data-ttu-id="5fef0-121">Si noti che per i team pubblici, il SharePoint del team viene eseguito il provisioning con l'accesso "Tutti tranne gli utenti esterni".</span><span class="sxs-lookup"><span data-stu-id="5fef0-121">Note that for public teams, the SharePoint team site is provisioned with "Everyone except external users" access.</span></span> <span data-ttu-id="5fef0-122">Il team pubblico non viene visualizzato in Teams per le persone che non sono membri del team.</span><span class="sxs-lookup"><span data-stu-id="5fef0-122">The public team isn't displayed in Teams for people who aren't members of that team.</span></span> <span data-ttu-id="5fef0-123">Tuttavia, possono accedere al contenuto del SharePoint del team usando l'URL del sito SharePoint del team.</span><span class="sxs-lookup"><span data-stu-id="5fef0-123">However, they can access content on the SharePoint team site using the URL of the SharePoint team site.</span></span> 

## <a name="channel-files-tab"></a><span data-ttu-id="5fef0-124">Scheda File del canale</span><span class="sxs-lookup"><span data-stu-id="5fef0-124">Channel Files tab</span></span>

<span data-ttu-id="5fef0-125">La **scheda File** in Teams simile alla visualizzazione SharePoint documenti.</span><span class="sxs-lookup"><span data-stu-id="5fef0-125">The **Files** tab in Teams closely resembles the SharePoint documents view.</span></span> <span data-ttu-id="5fef0-126">Nella scheda **File** gli utenti possono:</span><span class="sxs-lookup"><span data-stu-id="5fef0-126">On the **Files** tab, users can:</span></span>

- <span data-ttu-id="5fef0-127">Vedere altre opzioni **nel** menu Nuovo file.</span><span class="sxs-lookup"><span data-stu-id="5fef0-127">See additional options in the **New** file menu.</span></span>
- <span data-ttu-id="5fef0-128">Sincronizzare i file con l'unità locale.</span><span class="sxs-lookup"><span data-stu-id="5fef0-128">Sync files to their local drive.</span></span>
- <span data-ttu-id="5fef0-129">Nel menu **Tutti i documenti** passare dalla visualizzazione **Elenco** alla visualizzazione **Elenco compatto** alla **visualizzazione** Riquadri.</span><span class="sxs-lookup"><span data-stu-id="5fef0-129">On the **All Documents** menu, switch from **List** view to **Compact list** to **Tiles** view.</span></span>
- <span data-ttu-id="5fef0-130">Identificare i file che necessitano di attenzione o che hanno malware.</span><span class="sxs-lookup"><span data-stu-id="5fef0-130">Identify files that need attention or have malware.</span></span>
- <span data-ttu-id="5fef0-131">Verificare immediatamente se un file è di sola lettura o estratto.</span><span class="sxs-lookup"><span data-stu-id="5fef0-131">Immediately see whether a file is read-only or checked out.</span></span>
- <span data-ttu-id="5fef0-132">Estrarre e archiviare i file.</span><span class="sxs-lookup"><span data-stu-id="5fef0-132">Check out and check in files.</span></span>
- <span data-ttu-id="5fef0-133">Aggiungere, rimuovere e modificare l'ordinamento dei file.</span><span class="sxs-lookup"><span data-stu-id="5fef0-133">Pin, unpin, and change the sort order of files.</span></span>
- <span data-ttu-id="5fef0-134">Identificare i file che necessitano di metadati</span><span class="sxs-lookup"><span data-stu-id="5fef0-134">Identify which files need metadata</span></span>
- <span data-ttu-id="5fef0-135">Scegliere tra molte altre opzioni di filtro.</span><span class="sxs-lookup"><span data-stu-id="5fef0-135">Choose from many more filter options.</span></span>
- <span data-ttu-id="5fef0-136">Raggruppare i file in base alle intestazioni di colonna.</span><span class="sxs-lookup"><span data-stu-id="5fef0-136">Group files based on column headings.</span></span>
- <span data-ttu-id="5fef0-137">Modificare le impostazioni delle colonne (spostarsi a sinistra o a destra, nascondere) e la larghezza delle colonne.</span><span class="sxs-lookup"><span data-stu-id="5fef0-137">Modify column settings (move left or right, hide) and column width.</span></span>

## <a name="default-link-type-setting"></a><span data-ttu-id="5fef0-138">Impostazione del tipo di collegamento predefinito</span><span class="sxs-lookup"><span data-stu-id="5fef0-138">Default link type setting</span></span>

<span data-ttu-id="5fef0-139">Tipo di collegamento di condivisione visualizzato per impostazione predefinita quando un utente ha condiviso un file nell'SharePoint di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="5fef0-139">The type of sharing link shown by default when a user shared a file is set in the SharePoint admin center.</span></span> <span data-ttu-id="5fef0-140">Per [informazioni, vedere Modificare il tipo di collegamento predefinito quando gli utenti ottengono collegamenti per la](/sharepoint/change-default-sharing-link) condivisione.</span><span class="sxs-lookup"><span data-stu-id="5fef0-140">See [Change the default link type when users get links for sharing](/sharepoint/change-default-sharing-link) for information.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5fef0-141">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="5fef0-141">Related topics</span></span>

<span data-ttu-id="5fef0-142">[SharePoint e Teams: meglio insieme.](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)</span><span class="sxs-lookup"><span data-stu-id="5fef0-142">[SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

[<span data-ttu-id="5fef0-143">Com'è l'esperienza guest</span><span class="sxs-lookup"><span data-stu-id="5fef0-143">What the guest experience is like</span></span>](guest-experience.md)
---
title: Condivisione di file in Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: haagaraw
audience: admin
search.appverid: MET150
description: Informazioni sull'esperienza di condivisione di file in Microsoft teams.
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 98935f7d8629e22b733b12f3f046ccb7af36b396
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138352"
---
# <a name="sharing-files-in-microsoft-teams"></a><span data-ttu-id="8203d-103">Condivisione di file in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8203d-103">Sharing files in Microsoft Teams</span></span>

<span data-ttu-id="8203d-104">In Microsoft teams gli utenti possono condividere contenuti con altri utenti di team all'interno e all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8203d-104">In Microsoft Teams, users can share content with other Teams users within and outside their organization.</span></span> <span data-ttu-id="8203d-105">La condivisione in teams si basa sulle impostazioni configurate in SharePoint e OneDrive, quindi qualsiasi configurazione per SharePoint e OneDrive controllerà la condivisione anche in teams.</span><span class="sxs-lookup"><span data-stu-id="8203d-105">Sharing in Teams is based on the settings configured in SharePoint and OneDrive, so whatever you set up for SharePoint and OneDrive will control sharing in Teams as well.</span></span>

## <a name="overview"></a><span data-ttu-id="8203d-106">Panoramica</span><span class="sxs-lookup"><span data-stu-id="8203d-106">Overview</span></span>

<span data-ttu-id="8203d-107">Gli utenti possono condividere file da OneDrive, da team e siti a cui hanno accesso e dal proprio computer.</span><span class="sxs-lookup"><span data-stu-id="8203d-107">Users can share files from OneDrive, from teams and sites they have access to, and from their computer.</span></span> <span data-ttu-id="8203d-108">Per condividere un file, gli utenti possono eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8203d-108">To share a file, users can do the following:</span></span>

- <span data-ttu-id="8203d-109">In un canale, fare clic su **Allega** (icona graffetta), selezionare **recenti**, **esplorare team e canali**, **OneDrive**o **caricare dal computer**e quindi scegliere il file che si vuole condividere.</span><span class="sxs-lookup"><span data-stu-id="8203d-109">In a channel, click **Attach** (the paperclip icon), select **Recent**, **Browse Teams and Channels**, **OneDrive**, or **Upload from my computer**, and then choose the file they want to share.</span></span> <br> 
    <span data-ttu-id="8203d-110">![Schermata che mostra la condivisione di un file da un canale](media/share-files-channel.png)</span><span class="sxs-lookup"><span data-stu-id="8203d-110">![Screenshot showing sharing a file from a channel](media/share-files-channel.png)</span></span>
- <span data-ttu-id="8203d-111">In una chat fare clic su **Allega** (icona graffetta), selezionare o **OneDrive** o **carica dal computer**e quindi scegliere il file che si vuole condividere.</span><span class="sxs-lookup"><span data-stu-id="8203d-111">In a chat, click **Attach** (the paperclip icon), select  or **OneDrive** or **Upload from my computer**, and then choose the file they want to share.</span></span> <br>
    <span data-ttu-id="8203d-112">![Schermata che mostra la condivisione di un file da una chat](media/share-files-chat.png)</span><span class="sxs-lookup"><span data-stu-id="8203d-112">![Screenshot showing sharing a file from a chat](media/share-files-chat.png)</span></span>
- <span data-ttu-id="8203d-113">Copiare e incollare il collegamento di condivisione nella casella di composizione.</span><span class="sxs-lookup"><span data-stu-id="8203d-113">Copy and paste the sharing link in the compose box.</span></span><br>
    <span data-ttu-id="8203d-114">![Screenshot che mostra l'anteprima dei file nella casella di composizione](media/share-files-link.png)</span><span class="sxs-lookup"><span data-stu-id="8203d-114">![Screenshot showing file preview in the compose box](media/share-files-link.png)</span></span>

### <a name="what-you-need-to-know-about-the-file-sharing-experience"></a><span data-ttu-id="8203d-115">Informazioni utili sull'esperienza di condivisione di file</span><span class="sxs-lookup"><span data-stu-id="8203d-115">What you need to know about the file sharing experience</span></span>

### <a name="permissions-of-shared-files-and-sharing-links"></a><span data-ttu-id="8203d-116">Autorizzazioni di file condivisi e collegamenti di condivisione</span><span class="sxs-lookup"><span data-stu-id="8203d-116">Permissions of shared files and sharing links</span></span>

<span data-ttu-id="8203d-117">Quando gli utenti condividono un file passandolo in OneDrive o in team e canali, a tutti i destinatari viene concesso l'accesso insieme alle [autorizzazioni predefinite impostate a livello di organizzazione](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span><span class="sxs-lookup"><span data-stu-id="8203d-117">When users share a file by browsing to it in OneDrive or teams and channels, all recipients are granted access along with the [default permission that's set at the organization level](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span></span>

<span data-ttu-id="8203d-118">Quando un utente copia e incolla un collegamento di condivisione, le autorizzazioni impostate per il collegamento di condivisione vengono rispettate e l'URL di SharePoint viene accorciato nel nome del file.</span><span class="sxs-lookup"><span data-stu-id="8203d-118">When a user copies and pastes a sharing link, the permissions set on that sharing link are honored and the SharePoint URL is shortened to the file name.</span></span> <span data-ttu-id="8203d-119">In altre parole, teams USA solo il nome del file per collegarsi a un file.</span><span class="sxs-lookup"><span data-stu-id="8203d-119">In other words, Teams uses just the file name to link to a file.</span></span>

<span data-ttu-id="8203d-120">Quando gli utenti condividono un file all'interno di teams, possono impostare le persone che possono accedere al file proprio come in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8203d-120">When users share a file from within Teams, they can set who can access the file just like they do across Microsoft 365.</span></span> <span data-ttu-id="8203d-121">Possono consentire l'accesso a tutti gli utenti dell'organizzazione, agli utenti con accesso esistente o a persone specifiche (che possono includere le persone in una chat di 1:1, in una chat di gruppo o in un canale).</span><span class="sxs-lookup"><span data-stu-id="8203d-121">They can give access to anyone, people in your organization, people with existing access, or specific people (which can include the people in a 1:1 chat, group chat, or channel).</span></span>  <span data-ttu-id="8203d-122">Quando si condivide un file, l'anteprima del file è disponibile nel messaggio, insieme a tutte le azioni dei file, ad esempio **Apri online**, **Scarica**e **copia collegamento**.</span><span class="sxs-lookup"><span data-stu-id="8203d-122">When a file is shared, the file preview is available in the message, along with all file actions such as **Open online**, **Download**, and **Copy link**.</span></span> <span data-ttu-id="8203d-123">Per impostazione predefinita, il file viene aperto in teams.</span><span class="sxs-lookup"><span data-stu-id="8203d-123">By default, the file opens in Teams.</span></span> <span data-ttu-id="8203d-124">Talvolta, il collegamento di condivisione potrebbe non essere stato convertito in un'anteprima del file per il momento in cui un utente invia il messaggio.</span><span class="sxs-lookup"><span data-stu-id="8203d-124">Sometimes, the sharing link may not have converted to a file preview by the time a user sends the message.</span></span> <span data-ttu-id="8203d-125">L'anteprima del file verrà generata dal sistema, ma in questo scenario il collegamento di condivisione non verrà ridotto solo al nome del file.</span><span class="sxs-lookup"><span data-stu-id="8203d-125">The file preview will be generated by the system, but in this scenario, the sharing link won't be shortened to the only the file name.</span></span>

<span data-ttu-id="8203d-126">Quando gli utenti condividono un file in una chat o un canale, viene avvisato se alcuni o tutti i destinatari non hanno l'autorizzazione per visualizzare il file.</span><span class="sxs-lookup"><span data-stu-id="8203d-126">When users share a file in a chat or channel, they're notified whether some or all recipients don't have permission to view the file.</span></span> <span data-ttu-id="8203d-127">Possono modificare le autorizzazioni per il file prima di condividerlo facendo clic sulla freccia accanto all'anteprima del file che ora viene visualizzata nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="8203d-127">They can change the permissions on the file before they share it by clicking the arrow next to the file preview that now appears in the message.</span></span>

![Screenshot della notifica se i destinatari non dispongono delle autorizzazioni](media/share-files-permissions.png)

### <a name="copy-a-sharing-link-in-teams"></a><span data-ttu-id="8203d-129">Copiare un collegamento di condivisione in teams</span><span class="sxs-lookup"><span data-stu-id="8203d-129">Copy a sharing link in Teams</span></span>

<span data-ttu-id="8203d-130">Gli utenti possono copiare un collegamento di condivisione di SharePoint e modificare le autorizzazioni di condivisione proprio come in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8203d-130">Users can copy a SharePoint sharing link and change sharing permissions just like they do across Microsoft 365.</span></span> <span data-ttu-id="8203d-131">Possono consentire l'accesso a tutti gli utenti dell'organizzazione, agli utenti con accesso esistente o a persone specifiche.</span><span class="sxs-lookup"><span data-stu-id="8203d-131">They can give access to anyone, people in your organization, people with existing access, or specific people.</span></span> <span data-ttu-id="8203d-132">L'autorizzazione predefinita del collegamento è uguale al set di autorizzazioni predefinito a livello dell'organizzazione, a meno che le autorizzazioni a livello di sito di SharePoint non lo sostituiscano.</span><span class="sxs-lookup"><span data-stu-id="8203d-132">The default permission of the link is the same as the default permission set at the organization level unless SharePoint site level permissions override it.</span></span>

## <a name="configure-sharing-in-onedrive-and-sharepoint"></a><span data-ttu-id="8203d-133">Configurare la condivisione in OneDrive e SharePoint</span><span class="sxs-lookup"><span data-stu-id="8203d-133">Configure sharing in OneDrive and SharePoint</span></span>

<span data-ttu-id="8203d-134">Per altre informazioni sulla condivisione di file in OneDrive e SharePoint, tra cui la configurazione della condivisione e la modalità di attivazione e disattivazione della condivisione, vedere:</span><span class="sxs-lookup"><span data-stu-id="8203d-134">For more information about sharing files in OneDrive and SharePoint, including how to configure sharing and how to turn sharing on and off, see:</span></span>

- <span data-ttu-id="8203d-135">[Panoramica della condivisione esterna](https://docs.microsoft.com/sharepoint/external-sharing-overview) : descrive cosa succede quando gli utenti condividono, a seconda di cosa stanno condividendo e con chi.</span><span class="sxs-lookup"><span data-stu-id="8203d-135">[External sharing overview](https://docs.microsoft.com/sharepoint/external-sharing-overview) - describes what happens when users share, depending on what they're sharing and with whom.</span></span>

- <span data-ttu-id="8203d-136">[Gestire le impostazioni di condivisione](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) : descrive in che modo gli amministratori globali e di SharePoint possono modificare le impostazioni di condivisione a livello di organizzazione per SharePoint e OneDrive.</span><span class="sxs-lookup"><span data-stu-id="8203d-136">[Manage sharing settings](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) - describes how global and SharePoint admins can change their organization-level sharing settings for SharePoint and OneDrive.</span></span>

- <span data-ttu-id="8203d-137">[Attivare o disattivare la condivisione esterna per un sito](https://docs.microsoft.com/sharepoint/change-external-sharing-site) : descrive in che modo gli amministratori globali e di SharePoint possono attivare o disattivare la condivisione esterna per un sito.</span><span class="sxs-lookup"><span data-stu-id="8203d-137">[Turn external sharing on or off for a site](https://docs.microsoft.com/sharepoint/change-external-sharing-site) – describes how global and SharePoint admins can turn external sharing on or off for a site.</span></span>

- <span data-ttu-id="8203d-138">[Modificare il tipo di collegamento predefinito per un sito](https://docs.microsoft.com/sharepoint/change-default-sharing-link) -descrive come impostare il tipo di collegamento predefinito in modo che sia più restrittivo.</span><span class="sxs-lookup"><span data-stu-id="8203d-138">[Change the default link type for a site](https://docs.microsoft.com/sharepoint/change-default-sharing-link) - describes how to set the default link type so that it's more restrictive.</span></span>

## <a name="more-information"></a><span data-ttu-id="8203d-139">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="8203d-139">More information</span></span>

- [<span data-ttu-id="8203d-140">Come interagire con SharePoint Online e OneDrive for business con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8203d-140">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>](sharepoint-onedrive-interact.md)

- [<span data-ttu-id="8203d-141">SharePoint e teams: meglio insieme</span><span class="sxs-lookup"><span data-stu-id="8203d-141">SharePoint and Teams: better together</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)

- [<span data-ttu-id="8203d-142">Condividere file e cartelle di OneDrive</span><span class="sxs-lookup"><span data-stu-id="8203d-142">Share OneDrive files and folders</span></span>](https://support.office.com/article/Share-OneDrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07#OS_Type=OneDrive_-_Business)

- [<span data-ttu-id="8203d-143">Condividere file o cartelle di SharePoint</span><span class="sxs-lookup"><span data-stu-id="8203d-143">Share SharePoint files or folders</span></span>](https://support.office.com/article/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c)

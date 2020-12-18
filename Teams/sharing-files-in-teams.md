---
title: Condividere file in Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: haagaraw
audience: admin
search.appverid: MET150
description: Informazioni sull'esperienza di condivisione di file in Microsoft Teams.
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 98935f7d8629e22b733b12f3f046ccb7af36b396
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138352"
---
# <a name="sharing-files-in-microsoft-teams"></a><span data-ttu-id="b4ec0-103">Condividere file in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b4ec0-103">Sharing files in Microsoft Teams</span></span>

<span data-ttu-id="b4ec0-104">In Microsoft Teams, gli utenti possono condividere contenuti con altri utenti di Teams all'interno e all'esterno della propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b4ec0-104">In Microsoft Teams, users can share content with other Teams users within and outside their organization.</span></span> <span data-ttu-id="b4ec0-105">La condivisione in Teams si basa sulle impostazioni configurate in SharePoint e OneDrive, quindi qualunque cosa sia stata configurata per SharePoint e OneDrive controllerà anche la condivisione in Teams.</span><span class="sxs-lookup"><span data-stu-id="b4ec0-105">Sharing in Teams is based on the settings configured in SharePoint and OneDrive, so whatever you set up for SharePoint and OneDrive will control sharing in Teams as well.</span></span>

## <a name="overview"></a><span data-ttu-id="b4ec0-106">Panoramica</span><span class="sxs-lookup"><span data-stu-id="b4ec0-106">Overview</span></span>

<span data-ttu-id="b4ec0-107">Gli utenti possono condividere file da OneDrive, da team e siti a cui hanno accesso e dal proprio computer.</span><span class="sxs-lookup"><span data-stu-id="b4ec0-107">Users can share files from OneDrive, from teams and sites they have access to, and from their computer.</span></span> <span data-ttu-id="b4ec0-108">Per condividere un file, gli utenti possono eseguire le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="b4ec0-108">To share a file, users can do the following:</span></span>

- <span data-ttu-id="b4ec0-109">In un canale, fare click su **Allega** (l’icona a forma di graffetta), selezionare **Recenti**, **Sfoglia team e canali**, **OneDrive** o **Carica dal computer locale**, quindi scegliere i file che si desidera condividere.</span><span class="sxs-lookup"><span data-stu-id="b4ec0-109">In a channel, click **Attach** (the paperclip icon), select **Recent**, **Browse Teams and Channels**, **OneDrive**, or **Upload from my computer**, and then choose the file they want to share.</span></span> <br> 
    <span data-ttu-id="b4ec0-110">![Screenshot che mostra la condivisione di un file da un canale](media/share-files-channel.png)</span><span class="sxs-lookup"><span data-stu-id="b4ec0-110">![Screenshot showing sharing a file from a channel](media/share-files-channel.png)</span></span>
- <span data-ttu-id="b4ec0-111">In un chat, fare click su **Allega** (l’icona a forma di graffetta), selezionare **OneDrive** o **Carica dal computer locale**, quindi scegliere i file che si desidera condividere.</span><span class="sxs-lookup"><span data-stu-id="b4ec0-111">In a chat, click **Attach** (the paperclip icon), select  or **OneDrive** or **Upload from my computer**, and then choose the file they want to share.</span></span> <br>
    <span data-ttu-id="b4ec0-112">![Screenshot che mostra la condivisione di un file da una chat](media/share-files-chat.png)</span><span class="sxs-lookup"><span data-stu-id="b4ec0-112">![Screenshot showing sharing a file from a chat](media/share-files-chat.png)</span></span>
- <span data-ttu-id="b4ec0-113">Copia e incolla il link di condivisione nella casella di composizione.</span><span class="sxs-lookup"><span data-stu-id="b4ec0-113">Copy and paste the sharing link in the compose box.</span></span><br>
    <span data-ttu-id="b4ec0-114">![Screenshot che mostra l'anteprima del file nella casella di composizione](media/share-files-link.png)</span><span class="sxs-lookup"><span data-stu-id="b4ec0-114">![Screenshot showing file preview in the compose box](media/share-files-link.png)</span></span>

### <a name="what-you-need-to-know-about-the-file-sharing-experience"></a><span data-ttu-id="b4ec0-115">Quello che c’è sapere sull'esperienza di condivisione dei file</span><span class="sxs-lookup"><span data-stu-id="b4ec0-115">What you need to know about the file sharing experience</span></span>

### <a name="permissions-of-shared-files-and-sharing-links"></a><span data-ttu-id="b4ec0-116">Autorizzazioni di file condivisi e collegamenti di condivisione</span><span class="sxs-lookup"><span data-stu-id="b4ec0-116">Permissions of shared files and sharing links</span></span>

<span data-ttu-id="b4ec0-117">Quando gli utenti condividono un file sfogliandolo in OneDrive o nei team e nei canali, a tutti i destinatari viene concesso l'accesso insieme all’[autorizzazione predefinita impostata a livello di organizzazione](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span><span class="sxs-lookup"><span data-stu-id="b4ec0-117">When users share a file by browsing to it in OneDrive or teams and channels, all recipients are granted access along with the [default permission that's set at the organization level](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span></span>

<span data-ttu-id="b4ec0-118">Quando un utente copia e incolla un collegamento di condivisione, le autorizzazioni impostate su quel collegamento di condivisione vengono rispettate e l'URL di SharePoint viene abbreviato col nome del file.</span><span class="sxs-lookup"><span data-stu-id="b4ec0-118">When a user copies and pastes a sharing link, the permissions set on that sharing link are honored and the SharePoint URL is shortened to the file name.</span></span> <span data-ttu-id="b4ec0-119">In altre parole, Teams usa solo il nome del file per collegarsi a un file.</span><span class="sxs-lookup"><span data-stu-id="b4ec0-119">In other words, Teams uses just the file name to link to a file.</span></span>

<span data-ttu-id="b4ec0-120">Quando gli utenti condividono un file direttamente da Teams, possono impostare chi può accedere al file proprio come fanno in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b4ec0-120">When users share a file from within Teams, they can set who can access the file just like they do across Microsoft 365.</span></span> <span data-ttu-id="b4ec0-121">Possono concedere l'accesso a chiunque, persone all’interno dell’organizzazione, persone con accesso esistente o persone specifiche (che possono includere le persone in una chat 1:1, chat di gruppo o canale).</span><span class="sxs-lookup"><span data-stu-id="b4ec0-121">They can give access to anyone, people in your organization, people with existing access, or specific people (which can include the people in a 1:1 chat, group chat, or channel).</span></span>  <span data-ttu-id="b4ec0-122">Quando un file viene condiviso, l'anteprima del file è disponibile nel messaggio, insieme a tutte le azioni sui file come **Apri online**, **Scarica**, e **Copia link**.</span><span class="sxs-lookup"><span data-stu-id="b4ec0-122">When a file is shared, the file preview is available in the message, along with all file actions such as **Open online**, **Download**, and **Copy link**.</span></span> <span data-ttu-id="b4ec0-123">Per impostazione predefinita, il file si apre in Teams.</span><span class="sxs-lookup"><span data-stu-id="b4ec0-123">By default, the file opens in Teams.</span></span> <span data-ttu-id="b4ec0-124">A volte, il collegamento di condivisione potrebbe non essere stato convertito in un'anteprima del file nel momento in cui un utente invia il messaggio.</span><span class="sxs-lookup"><span data-stu-id="b4ec0-124">Sometimes, the sharing link may not have converted to a file preview by the time a user sends the message.</span></span> <span data-ttu-id="b4ec0-125">L'anteprima del file verrà generata dal sistema, ma in questo scenario il collegamento di condivisione non verrà abbreviato col solo nome del file.</span><span class="sxs-lookup"><span data-stu-id="b4ec0-125">The file preview will be generated by the system, but in this scenario, the sharing link won't be shortened to the only the file name.</span></span>

<span data-ttu-id="b4ec0-126">Quando gli utenti condividono un file in una chat o in un canale, vengono avvisati se alcuni o tutti i destinatari non sono autorizzati a visualizzare il file.</span><span class="sxs-lookup"><span data-stu-id="b4ec0-126">When users share a file in a chat or channel, they're notified whether some or all recipients don't have permission to view the file.</span></span> <span data-ttu-id="b4ec0-127">Possono modificare le autorizzazioni sul file prima di condividerlo facendo clic sulla freccia accanto all'anteprima del file che ora appare nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="b4ec0-127">They can change the permissions on the file before they share it by clicking the arrow next to the file preview that now appears in the message.</span></span>

![Screenshot della notifica se i destinatari non dispongono delle autorizzazioni](media/share-files-permissions.png)

### <a name="copy-a-sharing-link-in-teams"></a><span data-ttu-id="b4ec0-129">Copiare un collegamento di condivisione in Teams</span><span class="sxs-lookup"><span data-stu-id="b4ec0-129">Copy a sharing link in Teams</span></span>

<span data-ttu-id="b4ec0-130">Gli utenti possono copiare un collegamento di condivisione di SharePoint e modificare le autorizzazioni di condivisione proprio come fanno in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b4ec0-130">Users can copy a SharePoint sharing link and change sharing permissions just like they do across Microsoft 365.</span></span> <span data-ttu-id="b4ec0-131">Possono concedere l'accesso a chiunque, persone all’interno dell’organizzazione, persone con accesso esistente o persone specifiche.</span><span class="sxs-lookup"><span data-stu-id="b4ec0-131">They can give access to anyone, people in your organization, people with existing access, or specific people.</span></span> <span data-ttu-id="b4ec0-132">L'autorizzazione predefinita del collegamento è la stessa dell'autorizzazione predefinita impostata a livello di organizzazione, a meno che le autorizzazioni a livello di sito di SharePoint non la sovrascrivano.</span><span class="sxs-lookup"><span data-stu-id="b4ec0-132">The default permission of the link is the same as the default permission set at the organization level unless SharePoint site level permissions override it.</span></span>

## <a name="configure-sharing-in-onedrive-and-sharepoint"></a><span data-ttu-id="b4ec0-133">Configurare la condivisione in OneDrive e SharePoint</span><span class="sxs-lookup"><span data-stu-id="b4ec0-133">Configure sharing in OneDrive and SharePoint</span></span>

<span data-ttu-id="b4ec0-134">Per ulteriori informazioni sulla condivisione di file in OneDrive e SharePoint, incluso come configurare la condivisione e come attivare e disattivare la condivisione, vedere:</span><span class="sxs-lookup"><span data-stu-id="b4ec0-134">For more information about sharing files in OneDrive and SharePoint, including how to configure sharing and how to turn sharing on and off, see:</span></span>

- <span data-ttu-id="b4ec0-135">[Panoramica condivisione esterna](https://docs.microsoft.com/sharepoint/external-sharing-overview) - descrive cosa accade quando gli utenti condividono in base a cosa viene condiviso e con chi.</span><span class="sxs-lookup"><span data-stu-id="b4ec0-135">[External sharing overview](https://docs.microsoft.com/sharepoint/external-sharing-overview) - describes what happens when users share, depending on what they're sharing and with whom.</span></span>

- <span data-ttu-id="b4ec0-136">[Gestire le impostazioni di condivisione](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) - descrive come gli amministratori globali e di SharePoint possono modificare le impostazioni di condivisione a livello di organizzazione per SharePoint e OneDrive.</span><span class="sxs-lookup"><span data-stu-id="b4ec0-136">[Manage sharing settings](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) - describes how global and SharePoint admins can change their organization-level sharing settings for SharePoint and OneDrive.</span></span>

- <span data-ttu-id="b4ec0-137">[Attivare o disattivare la condivisione esterna per un sito](https://docs.microsoft.com/sharepoint/change-external-sharing-site) – descrive come gli amministratori globali e di SharePoint possono attivare o disattivare la condivisione esterna per un sito.</span><span class="sxs-lookup"><span data-stu-id="b4ec0-137">[Turn external sharing on or off for a site](https://docs.microsoft.com/sharepoint/change-external-sharing-site) – describes how global and SharePoint admins can turn external sharing on or off for a site.</span></span>

- <span data-ttu-id="b4ec0-138">[Cambiare tipo di collegamento predefinito per un sito](https://docs.microsoft.com/sharepoint/change-default-sharing-link) - descrive come impostare il tipo di collegamento predefinito in modo che sia più restrittivo.</span><span class="sxs-lookup"><span data-stu-id="b4ec0-138">[Change the default link type for a site](https://docs.microsoft.com/sharepoint/change-default-sharing-link) - describes how to set the default link type so that it's more restrictive.</span></span>

## <a name="more-information"></a><span data-ttu-id="b4ec0-139">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="b4ec0-139">More information</span></span>

- [<span data-ttu-id="b4ec0-140">Modalità di interazione di SharePoint Online e OneDrive for Business con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b4ec0-140">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>](sharepoint-onedrive-interact.md)

- [<span data-ttu-id="b4ec0-141">SharePoint e Teams: migliori insieme</span><span class="sxs-lookup"><span data-stu-id="b4ec0-141">SharePoint and Teams: better together</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)

- [<span data-ttu-id="b4ec0-142">Condividere file e cartelle di OneDrive</span><span class="sxs-lookup"><span data-stu-id="b4ec0-142">Share OneDrive files and folders</span></span>](https://support.office.com/article/Share-OneDrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07#OS_Type=OneDrive_-_Business)

- [<span data-ttu-id="b4ec0-143">Condividere file o cartelle di SharePoint</span><span class="sxs-lookup"><span data-stu-id="b4ec0-143">Share SharePoint files or folders</span></span>](https://support.office.com/article/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c)

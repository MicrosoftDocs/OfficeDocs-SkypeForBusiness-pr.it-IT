---
title: Condivisione di file e cartelle in Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: haagaraw
audience: admin
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
description: Informazioni sull'esperienza di condivisione di file e cartelle in Microsoft Teams.
ms.openlocfilehash: 5b6847c42f13701e289b2efaad4a5489351f339b
ms.sourcegitcommit: b68a7b5100fc2b47ae81f465d48d1ac2348c1744
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2021
ms.locfileid: "49795777"
---
# <a name="sharing-files-in-microsoft-teams"></a><span data-ttu-id="0fc99-103">Condividere file in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0fc99-103">Sharing files in Microsoft Teams</span></span>

<span data-ttu-id="0fc99-104">In Microsoft Teams, gli utenti possono condividere contenuti con altri utenti di Teams all'interno e all'esterno della propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0fc99-104">In Microsoft Teams, users can share content with other Teams users within and outside their organization.</span></span> <span data-ttu-id="0fc99-105">La condivisione di file e cartelle in Teams si basa sulle impostazioni configurate in SharePoint e OneDrive, quindi qualsiasi impostazione configurata per SharePoint e OneDrive influirà anche sulla condivisione in Teams.</span><span class="sxs-lookup"><span data-stu-id="0fc99-105">Sharing files and folders in Teams is based on the settings configured in SharePoint and OneDrive, so whatever you set up for SharePoint and OneDrive will affect sharing in Teams as well.</span></span>

## <a name="overview"></a><span data-ttu-id="0fc99-106">Panoramica</span><span class="sxs-lookup"><span data-stu-id="0fc99-106">Overview</span></span>

<span data-ttu-id="0fc99-107">Gli utenti possono condividere file da OneDrive, da team e siti a cui hanno accesso e dal proprio computer.</span><span class="sxs-lookup"><span data-stu-id="0fc99-107">Users can share files from OneDrive, from teams and sites they have access to, and from their computer.</span></span> <span data-ttu-id="0fc99-108">Per condividere un file, gli utenti possono eseguire le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="0fc99-108">To share a file, users can do the following:</span></span>

- <span data-ttu-id="0fc99-p103">In un canale, fare click su **Allega** (l’icona a forma di graffetta), selezionare **Recenti**, **Sfoglia team e canali**, **OneDrive** o **Carica dal computer locale**, quindi scegliere i file che si desidera condividere.</span><span class="sxs-lookup"><span data-stu-id="0fc99-p103">In a channel, click **Attach** (the paperclip icon), select **Recent**, **Browse Teams and Channels**, **OneDrive**, or **Upload from my computer**, and then choose the file they want to share. </span></span><br> 
    <span data-ttu-id="0fc99-110">![Screenshot che mostra la condivisione di un file da un canale](media/share-files-channel.png)</span><span class="sxs-lookup"><span data-stu-id="0fc99-110">![Screenshot showing sharing a file from a channel](media/share-files-channel.png)</span></span>
- <span data-ttu-id="0fc99-p104">In un chat, fare click su **Allega** (l’icona a forma di graffetta), selezionare **OneDrive** o **Carica dal computer locale**, quindi scegliere i file che si desidera condividere.</span><span class="sxs-lookup"><span data-stu-id="0fc99-p104">In a chat, click **Attach** (the paperclip icon), select  or **OneDrive** or **Upload from my computer**, and then choose the file they want to share. </span></span><br>
    <span data-ttu-id="0fc99-112">![Screenshot che mostra la condivisione di un file da una chat](media/share-files-chat.png)</span><span class="sxs-lookup"><span data-stu-id="0fc99-112">![Screenshot showing sharing a file from a chat](media/share-files-chat.png)</span></span>
- <span data-ttu-id="0fc99-113">Copia e incolla il link di condivisione nella casella di composizione.</span><span class="sxs-lookup"><span data-stu-id="0fc99-113">Copy and paste the sharing link in the compose box.</span></span><br>
    <span data-ttu-id="0fc99-114">![Screenshot che mostra l'anteprima del file nella casella di composizione](media/share-files-link.png)</span><span class="sxs-lookup"><span data-stu-id="0fc99-114">![Screenshot showing file preview in the compose box](media/share-files-link.png)</span></span>

### <a name="permissions-of-shared-files-and-sharing-links"></a><span data-ttu-id="0fc99-115">Autorizzazioni di file condivisi e collegamenti di condivisione</span><span class="sxs-lookup"><span data-stu-id="0fc99-115">Permissions of shared files and sharing links</span></span>

<span data-ttu-id="0fc99-116">Quando gli utenti condividono un file direttamente da Teams, possono impostare chi può accedere al file proprio come fanno in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0fc99-116">When users share a file from within Teams, they can set who can access the file just like they do across Microsoft 365.</span></span> <span data-ttu-id="0fc99-117">Possono concedere l'accesso a chiunque, persone all’interno dell’organizzazione, persone con accesso esistente o persone specifiche (che possono includere le persone in una chat 1:1, chat di gruppo o canale).</span><span class="sxs-lookup"><span data-stu-id="0fc99-117">They can give access to anyone, people in your organization, people with existing access, or specific people (which can include the people in a 1:1 chat, group chat, or channel).</span></span>  <span data-ttu-id="0fc99-118">Quando un file viene condiviso, l'anteprima del file è disponibile nel messaggio, insieme a tutte le azioni sui file come **Apri online**, **Scarica**, e **Copia link**.</span><span class="sxs-lookup"><span data-stu-id="0fc99-118">When a file is shared, the file preview is available in the message, along with all file actions such as **Open online**, **Download**, and **Copy link**.</span></span> <span data-ttu-id="0fc99-119">Per impostazione predefinita, il file si apre in Teams.</span><span class="sxs-lookup"><span data-stu-id="0fc99-119">By default, the file opens in Teams.</span></span>

<span data-ttu-id="0fc99-120">Quando gli utenti condividono un file in una chat o in un canale, vengono avvisati se alcuni o tutti i destinatari non sono autorizzati a visualizzare il file.</span><span class="sxs-lookup"><span data-stu-id="0fc99-120">When users share a file in a chat or channel, they're notified whether some or all recipients don't have permission to view the file.</span></span> <span data-ttu-id="0fc99-121">Possono modificare le autorizzazioni sul file prima di condividerlo facendo clic sulla freccia accanto all'anteprima del file che ora appare nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="0fc99-121">They can change the permissions on the file before they share it by clicking the arrow next to the file preview that now appears in the message.</span></span>

![Screenshot della notifica se i destinatari non dispongono delle autorizzazioni](media/share-files-permissions.png)

## <a name="related-topics"></a><span data-ttu-id="0fc99-123">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="0fc99-123">Related topics</span></span>

[<span data-ttu-id="0fc99-124">Modalità di interazione di SharePoint Online e OneDrive for Business con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0fc99-124">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>](sharepoint-onedrive-interact.md)

[<span data-ttu-id="0fc99-125">Modificare il tipo di collegamento predefinito per un sito</span><span class="sxs-lookup"><span data-stu-id="0fc99-125">Change the default link type for a site</span></span>](https://docs.microsoft.com/sharepoint/change-default-sharing-link)

[<span data-ttu-id="0fc99-126">Collaborare con guest in un team</span><span class="sxs-lookup"><span data-stu-id="0fc99-126">Collaborate with guests in a team</span></span>](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)
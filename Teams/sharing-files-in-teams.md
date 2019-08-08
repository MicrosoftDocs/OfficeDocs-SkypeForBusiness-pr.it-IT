---
title: Condivisione di file in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/08/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
search.appverid: MET150
description: Microsoft teams USA le impostazioni di OneDrive e SharePoint per controllare la condivisione.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0d9f2060c7b87d58820cf0d90dd8e4dc556297f1
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243160"
---
# <a name="sharing-files-in-microsoft-teams"></a><span data-ttu-id="c20c5-103">Condivisione di file in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c20c5-103">Sharing files in Microsoft Teams</span></span>

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-article.md)]

<span data-ttu-id="c20c5-104">Le funzionalità di condivisione di file in team consentono agli utenti di condividere contenuti con altri utenti di teams nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c20c5-104">The file sharing features in Teams let users share content with other Teams users in their organization.</span></span> <span data-ttu-id="c20c5-105">La condivisione in teams si basa sulle impostazioni configurate in SharePoint e OneDrive, quindi qualsiasi configurazione per SharePoint e OneDrive controllerà la condivisione anche in teams.</span><span class="sxs-lookup"><span data-stu-id="c20c5-105">Sharing in Teams is based on the settings configured in SharePoint and OneDrive, so whatever you set up for SharePoint and OneDrive will control sharing in Teams as well.</span></span>
<span data-ttu-id="c20c5-106">![Diagramma che indica il funzionamento della condivisione file tra team e OneDrive for business e SharePoint](media/sharing-files-in-teams-image1.png)</span><span class="sxs-lookup"><span data-stu-id="c20c5-106">![Diagram indicating how file sharing works between Teams and OneDrive for Business and SharePoint](media/sharing-files-in-teams-image1.png)</span></span>

<span data-ttu-id="c20c5-107">Condivisione teams consente agli utenti di eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c20c5-107">Teams sharing lets users do the following:</span></span>

- <span data-ttu-id="c20c5-108">Condividere file da OneDrive.</span><span class="sxs-lookup"><span data-stu-id="c20c5-108">Share files from OneDrive.</span></span>

- <span data-ttu-id="c20c5-109">Impostare le autorizzazioni per i file che si vuole condividere con altri utenti.</span><span class="sxs-lookup"><span data-stu-id="c20c5-109">Set permissions for files they want to share with others.</span></span>

- <span data-ttu-id="c20c5-110">Condividere file tra team.</span><span class="sxs-lookup"><span data-stu-id="c20c5-110">Share files across Teams.</span></span>

- <span data-ttu-id="c20c5-111">Condividere file dall'elenco dei file di recente accesso (in genere, questi sono i file che gli utenti sono più interessati alla condivisione).</span><span class="sxs-lookup"><span data-stu-id="c20c5-111">Share files from their list of recently accessed files (typically, these are the files users are most interested in sharing).</span></span>

- <span data-ttu-id="c20c5-112">Rimanere in teams quando si fa clic sul nome di un file per aprire un file.</span><span class="sxs-lookup"><span data-stu-id="c20c5-112">Stay within Teams when they click a file name to open a file.</span></span>

<span data-ttu-id="c20c5-113">Teams accorcia gli URL di SharePoint e gli URL del browser lunghi che puntano a un file.</span><span class="sxs-lookup"><span data-stu-id="c20c5-113">Teams shortens long SharePoint URLS and browser URLS that point to a file.</span></span> <span data-ttu-id="c20c5-114">Teams USA solo il nome del file per creare un collegamento a un file.</span><span class="sxs-lookup"><span data-stu-id="c20c5-114">Teams uses just the file name to link to a file.</span></span> <span data-ttu-id="c20c5-115">Inoltre, l'opzione **Ottieni collegamento** è stata cambiata in **copia collegamento** per eliminare qualsiasi confusione che gli utenti potrebbero avere per consentire ad altri di accedere a un file.</span><span class="sxs-lookup"><span data-stu-id="c20c5-115">Additionally, the **Get link** option has been changed to **Copy link** to eliminate any confusion that users might have about giving others access to a file.</span></span>

## <a name="configure-sharing-in-onedrive-and-sharepoint"></a><span data-ttu-id="c20c5-116">Configurare la condivisione in OneDrive e SharePoint</span><span class="sxs-lookup"><span data-stu-id="c20c5-116">Configure sharing in OneDrive and SharePoint</span></span>

<span data-ttu-id="c20c5-117">Per altre informazioni sulla condivisione di file in OneDrive e SharePoint, tra cui la configurazione della condivisione e la modalità di attivazione e disattivazione della condivisione, vedere:</span><span class="sxs-lookup"><span data-stu-id="c20c5-117">For more information about sharing files in OneDrive and SharePoint, including how to configure sharing and how to turn sharing on and off, see:</span></span>

- <span data-ttu-id="c20c5-118">[Panoramica della condivisione esterna](https://docs.microsoft.com/sharepoint/external-sharing-overview) : descrive cosa succede quando gli utenti condividono, a seconda di cosa stanno condividendo e con chi.</span><span class="sxs-lookup"><span data-stu-id="c20c5-118">[External sharing overview](https://docs.microsoft.com/sharepoint/external-sharing-overview) - describes what happens when users share, depending on what they're sharing and with whom.</span></span>

- <span data-ttu-id="c20c5-119">[Attivare o disattivare la condivisione esterna](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) : descrive in che modo gli amministratori globali e di SharePoint possono modificare le impostazioni di condivisione a livello di organizzazione per SharePoint e OneDrive.</span><span class="sxs-lookup"><span data-stu-id="c20c5-119">[Turn external sharing on or off](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) - describes how global and SharePoint admins can change their organization-level sharing settings for SharePoint and OneDrive.</span></span>

- <span data-ttu-id="c20c5-120">[Modificare la condivisione esterna per un sito](https://docs.microsoft.com/sharepoint/change-external-sharing-site) : descrive in che modo gli amministratori globali e di SharePoint possono attivare o disattivare la condivisione esterna per un sito.</span><span class="sxs-lookup"><span data-stu-id="c20c5-120">[Change external sharing for a site](https://docs.microsoft.com/sharepoint/change-external-sharing-site) – describes how global and SharePoint admins can turn external sharing on or off for a site.</span></span>

- <span data-ttu-id="c20c5-121">[Modificare il tipo di collegamento predefinito quando gli utenti ottengono collegamenti per la condivisione](https://docs.microsoft.com/sharepoint/change-default-sharing-link) : descrive come impostare il tipo di collegamento predefinito in modo che sia più restrittivo.</span><span class="sxs-lookup"><span data-stu-id="c20c5-121">[Change the default link type when users get links for sharing](https://docs.microsoft.com/sharepoint/change-default-sharing-link) - describes how to set the default link type so that it is more restrictive.</span></span>

## <a name="more-information"></a><span data-ttu-id="c20c5-122">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="c20c5-122">More information</span></span>

- [<span data-ttu-id="c20c5-123">Come interagire con SharePoint Online e OneDrive for business con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c20c5-123">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>](sharepoint-onedrive-interact.md)

- <span data-ttu-id="c20c5-124">[SharePoint e teams: meglio insieme](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span><span class="sxs-lookup"><span data-stu-id="c20c5-124">[SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

- [<span data-ttu-id="c20c5-125">Condividere file e cartelle di OneDrive</span><span class="sxs-lookup"><span data-stu-id="c20c5-125">Share OneDrive files and folders</span></span>](https://support.office.com/article/Share-OneDrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07#OS_Type=OneDrive_-_Business)

- [<span data-ttu-id="c20c5-126">Condividere file o cartelle di SharePoint</span><span class="sxs-lookup"><span data-stu-id="c20c5-126">Share SharePoint files or folders</span></span>](https://support.office.com/article/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c)


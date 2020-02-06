---
title: Espansione delle impostazioni per Lync Server Lite
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
ROBOTS: NOINDEX, NOFOLLOW
description: 'Per modificare le proprietà di un sito esistente, eseguire le operazioni seguenti:'
ms.openlocfilehash: a8240030bd05ae865cb54343a460c8be414546a3
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798293"
---
# <a name="lync-server-site-settings-expander"></a><span data-ttu-id="7c5c5-103">Espansione delle impostazioni per Lync Server Lite</span><span class="sxs-lookup"><span data-stu-id="7c5c5-103">Lync Server Site Settings Expander</span></span>

<span data-ttu-id="7c5c5-104">Per modificare le proprietà di un sito esistente, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7c5c5-104">To edit the properties of an existing site, do the following:</span></span>



## <a name="site-properties"></a><span data-ttu-id="7c5c5-105">Proprietà del sito</span><span class="sxs-lookup"><span data-stu-id="7c5c5-105">Site properties</span></span>

<span data-ttu-id="7c5c5-106">In proprietà sito è possibile modificare o modificare il nome del sito (obbligatorio), la descrizione (facoltativa), la città (facoltativa), lo stato/provincia (facoltativo) e il codice paese/area geografica (facoltativo).</span><span class="sxs-lookup"><span data-stu-id="7c5c5-106">In site properties, you can change or modify the site Name (required), Description (optional), City (optional), State/Province (optional), and the Country/Region Code (optional).</span></span>

<span data-ttu-id="7c5c5-107">Per informazioni dettagliate sulle proprietà del sito, vedere [aggiungere siti di succursale alla topologia](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).</span><span class="sxs-lookup"><span data-stu-id="7c5c5-107">For details about site properties, see [Add Branch Sites to Your Topology](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).</span></span>

## <a name="federation-route-properties"></a><span data-ttu-id="7c5c5-108">Proprietà route federative</span><span class="sxs-lookup"><span data-stu-id="7c5c5-108">Federation Route properties</span></span>

<span data-ttu-id="7c5c5-109">Per impostare un'assegnazione della route Federation del sito, è prima necessario che la Federazione sia abilitata in un server perimetrale o in un pool di Edge Server.</span><span class="sxs-lookup"><span data-stu-id="7c5c5-109">To set a site federation route assignment, you must first have federation enabled on an Edge Server or an Edge Server pool.</span></span> <span data-ttu-id="7c5c5-110">Se la Federazione non è abilitata in un server perimetrale o in un pool, le impostazioni di assegnazione della route federativo per il sito non saranno disponibili per la modifica.</span><span class="sxs-lookup"><span data-stu-id="7c5c5-110">If federation is not enabled on an Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>

<span data-ttu-id="7c5c5-111">Se è stata configurata l'impostazione federativo in Edge Server o pool, selezionare **Abilita** a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="7c5c5-111">If the federation setting at the Edge Server or pool has been configured, select **Enable** at the site level.</span></span> <span data-ttu-id="7c5c5-112">Selezionare quindi un bordo o un Director dall'elenco a discesa per impostare la route federativo.</span><span class="sxs-lookup"><span data-stu-id="7c5c5-112">Then select an Edge or a Director from the drop-down list to set as the federation route.</span></span>

> [!CAUTION]
> <span data-ttu-id="7c5c5-113">Questa impostazione avrà effetto su tutti i siti.</span><span class="sxs-lookup"><span data-stu-id="7c5c5-113">This setting will affect all sites.</span></span> <span data-ttu-id="7c5c5-114">Verificare che l'impostazione che si sta configurando in questo sito sia appropriata per tutti i siti.</span><span class="sxs-lookup"><span data-stu-id="7c5c5-114">Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>

## <a name="see-also"></a><span data-ttu-id="7c5c5-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c5c5-115">See also</span></span>

<span data-ttu-id="7c5c5-116">Per informazioni dettagliate, vedere [topologie per l'accesso degli utenti esterni](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).</span><span class="sxs-lookup"><span data-stu-id="7c5c5-116">For details, see [Topologies for External User Access](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).</span></span>



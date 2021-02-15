---
title: Espansione delle impostazioni del sito di Lync Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
description: 'Per modificare le proprietà di un sito esistente, eseguire le operazioni seguenti:'
ms.openlocfilehash: acfd7e312dbde97e847a9b97d9730a6d0b3488da
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832916"
---
# <a name="lync-server-site-settings-expander"></a><span data-ttu-id="fb409-103">Espansione delle impostazioni del sito di Lync Server</span><span class="sxs-lookup"><span data-stu-id="fb409-103">Lync Server Site Settings Expander</span></span>

<span data-ttu-id="fb409-104">Per modificare le proprietà di un sito esistente, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fb409-104">To edit the properties of an existing site, do the following:</span></span>



## <a name="site-properties"></a><span data-ttu-id="fb409-105">Proprietà del sito</span><span class="sxs-lookup"><span data-stu-id="fb409-105">Site properties</span></span>

<span data-ttu-id="fb409-106">Nelle proprietà del sito è possibile cambiare o modificare il nome del sito (obbligatorio), la descrizione (facoltativa), la città (facoltativa), la provincia (facoltativa) e il codice paese/area geografica (facoltativo).</span><span class="sxs-lookup"><span data-stu-id="fb409-106">In site properties, you can change or modify the site Name (required), Description (optional), City (optional), State/Province (optional), and the Country/Region Code (optional).</span></span>

<span data-ttu-id="fb409-107">Per informazioni dettagliate sulle proprietà di un sito, vedere [Add Branch Sites to Your Topology](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).</span><span class="sxs-lookup"><span data-stu-id="fb409-107">For details about site properties, see [Add Branch Sites to Your Topology](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).</span></span>

## <a name="federation-route-properties"></a><span data-ttu-id="fb409-108">Proprietà della route di federazione</span><span class="sxs-lookup"><span data-stu-id="fb409-108">Federation Route properties</span></span>

<span data-ttu-id="fb409-p101">Per impostare un'assegnazione di route di federazione per il sito, è necessario innanzitutto che in un server perimetrale o in un pool di server perimetrali sia abilitata la federazione. In caso contrario, le impostazioni di assegnazione della route di federazione per il sito non saranno disponibili per la modifica.</span><span class="sxs-lookup"><span data-stu-id="fb409-p101">To set a site federation route assignment, you must first have federation enabled on an Edge Server or an Edge Server pool. If federation is not enabled on an Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>

<span data-ttu-id="fb409-p102">Se l'impostazione di federazione è stata configurata nel server perimetrale o nel pool di server perimetrali, selezionare **Abilita** a livello di sito. Selezionare quindi nell'elenco a discesa un server perimetrale o un server Director da impostare come route di federazione.</span><span class="sxs-lookup"><span data-stu-id="fb409-p102">If the federation setting at the Edge Server or pool has been configured, select **Enable** at the site level. Then select an Edge or a Director from the drop-down list to set as the federation route.</span></span>

> [!CAUTION]
> <span data-ttu-id="fb409-p103">Questa impostazione avrà effetto su tutti i siti. Accertarsi quindi che l'impostazione da configurare per questo sito sia appropriata per tutti i siti.</span><span class="sxs-lookup"><span data-stu-id="fb409-p103">This setting will affect all sites. Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>

## <a name="see-also"></a><span data-ttu-id="fb409-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb409-115">See also</span></span>

<span data-ttu-id="fb409-116">Per informazioni dettagliate, vedere [Topologies for External User Access](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).</span><span class="sxs-lookup"><span data-stu-id="fb409-116">For details, see [Topologies for External User Access](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).</span></span>



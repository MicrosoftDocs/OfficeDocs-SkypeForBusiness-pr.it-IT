---
title: Espansione delle impostazioni della route di federazione
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FederationRouteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 22aa11b8-80ba-4c6a-9396-d11166903066
ROBOTS: NOINDEX, NOFOLLOW
description: Per impostare un'assegnazione di route di federazione per il sito, è necessario innanzitutto che nell'Edge Server o nel pool Edge Server sia abilitata la federazione. In caso contrario, le impostazioni di assegnazione della route di federazione per il sito non saranno disponibili per la modifica.
ms.openlocfilehash: 9e453eae2ca44b0e6f406aa6767bc44b741bd3b6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819466"
---
# <a name="federation-route-settings-expander"></a><span data-ttu-id="73d8a-104">Espansione delle impostazioni della route di federazione</span><span class="sxs-lookup"><span data-stu-id="73d8a-104">Federation Route Settings Expander</span></span>
 
<span data-ttu-id="73d8a-p102">Per impostare un'assegnazione di route di federazione per il sito, è necessario innanzitutto che nell'Edge Server o nel pool Edge Server sia abilitata la federazione. In caso contrario, le impostazioni di assegnazione della route di federazione per il sito non saranno disponibili per la modifica.</span><span class="sxs-lookup"><span data-stu-id="73d8a-p102">To set a site federation route assignment, you must first have federation enabled on the Edge Server or Edge Server pool. If federation is not enabled on the Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>

<span data-ttu-id="73d8a-107">Se l'impostazione di federazione nel server perimetrale o nel pool è stata configurata, sarà possibile configurare le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="73d8a-107">If the federation setting at the Edge Server or pool has been configured, you can configure the following options:</span></span> 
  
- <span data-ttu-id="73d8a-108">**Consenti assegnazioni di route di federazione a tutti i siti** Questa impostazione avrà effetto su tutti i siti.</span><span class="sxs-lookup"><span data-stu-id="73d8a-108">**Allow federation route assignments to all sites** This setting will affect all sites.</span></span> <span data-ttu-id="73d8a-109">Accertarsi quindi che l'impostazione da configurare per questo sito sia appropriata per tutti i siti.</span><span class="sxs-lookup"><span data-stu-id="73d8a-109">Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>
    
- <span data-ttu-id="73d8a-110">**Abilita federazione SIP** Selezionare questa opzione per abilitare una route di federazione SIP e quindi selezionare un Director o un pool di server perimetrali come route di Federazione.</span><span class="sxs-lookup"><span data-stu-id="73d8a-110">**Enable SIP federation** Select this option to enable a SIP federation route, and then select a Director or Edge pool as the federation route.</span></span>
    
- <span data-ttu-id="73d8a-111">**Abilitare la Federazione XMPP** Selezionare questa opzione per abilitare una route di federazione XMPP e quindi selezionare un Director o un pool di server perimetrali come route di Federazione.</span><span class="sxs-lookup"><span data-stu-id="73d8a-111">**Enable XMPP federation** Select this option to enable an XMPP federation route, and then select a Director or Edge pool as the federation route.</span></span>
- 
  > [!NOTE]
  > <span data-ttu-id="73d8a-112">I gateway e i proxy XMPP sono disponibili in Skype for Business Server 2015 ma non sono più supportati in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="73d8a-112">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="73d8a-113">Per ulteriori informazioni, vedere [migrazione della Federazione XMPP](../../../../SfBServer2019/migration/migrating-xmpp-federation.md) .</span><span class="sxs-lookup"><span data-stu-id="73d8a-113">See [Migrating XMPP federation](../../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span>
    


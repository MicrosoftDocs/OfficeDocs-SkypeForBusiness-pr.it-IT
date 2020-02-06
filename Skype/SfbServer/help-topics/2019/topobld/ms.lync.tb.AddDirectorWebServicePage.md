---
title: Aggiungere il servizio Web Director
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
ROBOTS: NOINDEX, NOFOLLOW
description: L'URL di base è l'identità dei servizi Web per l'URL, meno il https://. Ad esempio, se l'URL completo per i servizi Web del pool è https://pool01.contoso.net, l'URL di base è pool01.contoso.NET.
ms.openlocfilehash: df8f6d88e57be2abd3c4a5081188f6e22849da0f
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796555"
---
# <a name="add-director-web-service"></a><span data-ttu-id="591d7-104">Aggiungere il servizio Web Director</span><span class="sxs-lookup"><span data-stu-id="591d7-104">Add Director Web Service</span></span>
 
<span data-ttu-id="591d7-105">L'URL di base è l'identità dei servizi Web per l'URL, meno il https://.</span><span class="sxs-lookup"><span data-stu-id="591d7-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="591d7-106">Ad esempio, se l'URL completo per i servizi Web del pool è https://pool01.contoso.net, l'URL di base è pool01.contoso.NET.</span><span class="sxs-lookup"><span data-stu-id="591d7-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="591d7-107">Non è possibile eseguire l'override del nome di dominio completo (FQDN) del pool di servizi Web interni se si sta distribuendo solo un singolo amministratore.</span><span class="sxs-lookup"><span data-stu-id="591d7-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) if you are deploying only a single Director.</span></span> <span data-ttu-id="591d7-108">Se si configura un bilanciamento del carico DNS (Domain Name System) per pool di amministratori, è possibile specificare un URL di base interno diverso (che deve essere diverso dall'FQDN del pool e potrebbe essere, ad esempio, l'URL\<\>di base interno).</span><span class="sxs-lookup"><span data-stu-id="591d7-108">If you are configuring a Domain Name System (DNS) load balancing for pool of Directors, you can specify a different internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="591d7-109">Puoi specificare un URL di base esterno diverso dall'URL di base interno per distinguere la denominazione dei domini.</span><span class="sxs-lookup"><span data-stu-id="591d7-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="591d7-110">Ad esempio, il dominio interno è contoso.net, ma il nome di dominio esterno è contoso.com.</span><span class="sxs-lookup"><span data-stu-id="591d7-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="591d7-111">Definiresti l'URL della base esterna usando il nome di dominio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="591d7-111">You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="591d7-112">Questo è importante per i server proxy inversi per una distribuzione di Edge.</span><span class="sxs-lookup"><span data-stu-id="591d7-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="591d7-113">Il nome di dominio dell'URL di base esterno deve essere uguale al nome di dominio dell'FQDN del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="591d7-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> 
  


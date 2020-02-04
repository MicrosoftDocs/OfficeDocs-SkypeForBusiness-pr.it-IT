---
title: Aggiungere servizi Web di Front End
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: L'URL di base è l'identità dei servizi Web per l'URL, meno il https://. Ad esempio, se l'URL completo per i servizi Web del pool è https://pool01.contoso.net, l'URL di base è pool01.contoso.NET.
ms.openlocfilehash: 10749cc746cf1f3d039a89fd351be6de77eafaee
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698201"
---
# <a name="add-front-end-web-services"></a><span data-ttu-id="04faf-104">Aggiungere servizi Web di Front End</span><span class="sxs-lookup"><span data-stu-id="04faf-104">Add Front End Web Services</span></span>
 
<span data-ttu-id="04faf-105">L'URL di base è l'identità dei servizi Web per l'URL, meno il https://.</span><span class="sxs-lookup"><span data-stu-id="04faf-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="04faf-106">Ad esempio, se l'URL completo per i servizi Web del pool è https://pool01.contoso.net, l'URL di base è pool01.contoso.NET.</span><span class="sxs-lookup"><span data-stu-id="04faf-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="04faf-107">Non è possibile eseguire l'override del nome di dominio completo del pool di servizi Web interni per un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="04faf-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition server.</span></span> <span data-ttu-id="04faf-108">Se si sta configurando il bilanciamento del carico DNS (Domain Name System) per un pool Enterprise Edition Front-\<end, è possibile specificare un URL di base interno diverso, che deve essere diverso dall'FQDN del pool, ad esempio l'\>URL di base interno.</span><span class="sxs-lookup"><span data-stu-id="04faf-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL, which must be different from the pool FQDN (for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="04faf-109">Puoi specificare un URL di base esterno diverso dall'URL di base interno per distinguere la denominazione dei domini.</span><span class="sxs-lookup"><span data-stu-id="04faf-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="04faf-110">Ad esempio, il dominio interno è contoso.net, ma il nome di dominio esterno è contoso.com.</span><span class="sxs-lookup"><span data-stu-id="04faf-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="04faf-111">Definiresti l'URL della base esterna usando il nome di dominio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="04faf-111">You would define the external base URL using the contoso.com domain name.</span></span> <span data-ttu-id="04faf-112">Questo è importante per i server proxy inversi per una distribuzione di Edge.</span><span class="sxs-lookup"><span data-stu-id="04faf-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="04faf-113">Il nome di dominio dell'URL di base esterno deve essere uguale al nome di dominio dell'FQDN del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="04faf-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="04faf-114">La messaggistica istantanea e la presenza richiedono l'accesso HTTP al pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="04faf-114">Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  


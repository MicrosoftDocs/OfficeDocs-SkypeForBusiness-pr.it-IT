---
title: Aggiungere servizi Web di Front End Server (2010)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: L'URL di base è l'identità dei servizi Web per l'URL meno https://. Ad esempio, se l'URL completo per i servizi Web del pool è https://pool01.contoso.net , l'URL di base è pool01.contoso.NET.
ms.openlocfilehash: d87bb3716a19f59f2614194d79dfedaf544964e1
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217957"
---
# <a name="add-front-end-web-services-2010"></a><span data-ttu-id="7f381-104">Aggiungere servizi Web di Front End Server (2010)</span><span class="sxs-lookup"><span data-stu-id="7f381-104">Add Front End Web Services 2010</span></span>
 
<span data-ttu-id="7f381-105">L'URL di base è l'identità dei servizi Web per l'URL meno https://.</span><span class="sxs-lookup"><span data-stu-id="7f381-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="7f381-106">Ad esempio, se l'URL completo per i servizi Web del pool è https://pool01.contoso.net , l'URL di base è pool01.contoso.NET.</span><span class="sxs-lookup"><span data-stu-id="7f381-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="7f381-107">Non è possibile eseguire l'override del nome di dominio completo (FQDN) del pool di servizi Web interni per un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="7f381-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition Server.</span></span> <span data-ttu-id="7f381-108">Se si sta configurando il bilanciamento del carico DNS (Domain Name System) per un pool Enterprise Edition front end, è possibile specificare un URL di base interno diverso (che deve essere diverso dall'FQDN del pool e che potrebbe essere, ad esempio, Internal- \<your base URL\> ).</span><span class="sxs-lookup"><span data-stu-id="7f381-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL (which must be different than the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="7f381-109">È possibile specificare un URL di base esterno che sia diverso dall'URL di base interno per differenziare la denominazione dei domini.</span><span class="sxs-lookup"><span data-stu-id="7f381-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="7f381-110">Il dominio interno ad esempio è contoso.net, mentre il nome di dominio esterno è contoso.com.</span><span class="sxs-lookup"><span data-stu-id="7f381-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="7f381-111">È possibile definire l'URL di base esterno utilizzando il nome di dominio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="7f381-111">You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="7f381-112">Questo è importante per i server proxy inversi per una distribuzione di server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="7f381-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="7f381-113">Il nome di dominio dell'URL di base esterno deve essere lo stesso del nome di dominio dell'FQDN del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="7f381-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="7f381-114">Per la messaggistica istantanea e la presenza è necessario l'accesso HTTP al pool Front End.</span><span class="sxs-lookup"><span data-stu-id="7f381-114">Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  


---
title: Aggiungere il servizio Web del Director
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
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: L'URL di base è l'identità dei servizi Web per l'URL meno https://. Ad esempio, se l'URL completo per i servizi Web del pool è https://pool01.contoso.net , l'URL di base è pool01.contoso.NET.
ms.openlocfilehash: 5d965eb591afca8d7154d8fd12af741ddaf65084
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219467"
---
# <a name="add-director-web-service"></a><span data-ttu-id="6baf3-104">Aggiungere il servizio Web del Director</span><span class="sxs-lookup"><span data-stu-id="6baf3-104">Add Director Web Service</span></span>
 
<span data-ttu-id="6baf3-105">L'URL di base è l'identità dei servizi Web per l'URL meno https://.</span><span class="sxs-lookup"><span data-stu-id="6baf3-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="6baf3-106">Ad esempio, se l'URL completo per i servizi Web del pool è https://pool01.contoso.net , l'URL di base è pool01.contoso.NET.</span><span class="sxs-lookup"><span data-stu-id="6baf3-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="6baf3-107">Non è possibile sostituire il nome di dominio completo (FQDN) del pool di servizi Web interno se si sta distribuendo solo un singolo Director.</span><span class="sxs-lookup"><span data-stu-id="6baf3-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) if you are deploying only a single Director.</span></span> <span data-ttu-id="6baf3-108">Se si sta configurando un bilanciamento del carico DNS (Domain Name System) per il pool di amministratori, è possibile specificare un URL di base interno diverso (che deve essere diverso dall'FQDN del pool e che potrebbe essere, ad esempio, Internal- \<your base URL\> ).</span><span class="sxs-lookup"><span data-stu-id="6baf3-108">If you are configuring a Domain Name System (DNS) load balancing for pool of Directors, you can specify a different internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="6baf3-p104">È possibile specificare un URL di base esterno che sia diverso dall'URL di base interno per differenziare la denominazione dei domini. Il dominio interno ad esempio è contoso.net, mentre il nome di dominio esterno è contoso.com. È possibile definire l'URL di base esterno utilizzando il nome di dominio contoso.com. Questo è importante per i server proxy inversi per una distribuzione di server perimetrali. Il nome di dominio dell'URL di base esterno deve corrispondere al nome di dominio dell'FQDN del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="6baf3-p104">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming. For example, your internal domain is contoso.net, but your external domain name is contoso.com. You would define the external base URL by using the contoso.com domain name. This is important for reverse proxy servers for an edge deployment. The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> 
  


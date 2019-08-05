---
title: Stima dell'uso delle voci e del traffico per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 621b08fb-f894-4d91-ac38-e443401b098b
description: È possibile usare la metrica seguente per stimare il traffico degli utenti in ogni sito e il numero di porte necessarie per supportare il traffico.
ms.openlocfilehash: 09c3e638d25225376b95afd60bdd6d3c311c1f5a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187916"
---
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server"></a><span data-ttu-id="f54f1-103">Stima dell'uso delle voci e del traffico per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f54f1-103">Estimating voice usage and traffic for Skype for Business Server</span></span>
 
<span data-ttu-id="f54f1-104">È possibile usare la metrica seguente per stimare il traffico degli utenti in ogni sito e il numero di porte necessarie per supportare il traffico.</span><span class="sxs-lookup"><span data-stu-id="f54f1-104">You can use the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>
  
> <span data-ttu-id="f54f1-105">Per il **traffico leggero** (una chiamata PSTN per utente per ora), figura 15 utenti per ogni porta.</span><span class="sxs-lookup"><span data-stu-id="f54f1-105">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>
> 
> <span data-ttu-id="f54f1-106">Per il **traffico medio** (2 chiamate PSTN per utente per ora), figura 10 utenti per ogni porta.</span><span class="sxs-lookup"><span data-stu-id="f54f1-106">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>
> 
> <span data-ttu-id="f54f1-107">Per **traffico intenso** (3 o più chiamate PSTN per utente per ora), figura 5 utenti per ogni porta.</span><span class="sxs-lookup"><span data-stu-id="f54f1-107">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>
    
<span data-ttu-id="f54f1-108">Il numero di porte determina a sua volta il numero di server di mediazione e gateway che saranno necessari.</span><span class="sxs-lookup"><span data-stu-id="f54f1-108">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="f54f1-109">I gateway PSTN (Public Switched Telephone Network) che la maggior parte delle organizzazioni considerano la distribuzione di intervalli di dimensioni da 2 porte fino a un numero di porte di 960.</span><span class="sxs-lookup"><span data-stu-id="f54f1-109">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="f54f1-110">Ci sono anche gateway più grandi, ma questi sono usati principalmente dai provider di servizi di telefonia.</span><span class="sxs-lookup"><span data-stu-id="f54f1-110">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>
  
<span data-ttu-id="f54f1-111">Ad esempio, un'organizzazione con gli utenti di 10.000 e il traffico medio richiederebbe porte 1000.</span><span class="sxs-lookup"><span data-stu-id="f54f1-111">For example, an organization with 10,000 users and medium traffic would require 1000 ports.</span></span> <span data-ttu-id="f54f1-112">Il numero di gateway necessari sarebbe uguale al numero totale di porte richieste come determinato dalla capacità totale dei gateway.</span><span class="sxs-lookup"><span data-stu-id="f54f1-112">The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>
  


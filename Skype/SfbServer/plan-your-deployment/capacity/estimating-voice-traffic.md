---
title: Stima dell'utilizzo e del traffico vocali per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 621b08fb-f894-4d91-ac38-e443401b098b
description: È possibile utilizzare la metrica seguente per stimare il traffico degli utenti in ogni sito e il numero di porte necessarie per supportare tale traffico.
ms.openlocfilehash: c631361a7ef6d4706632f59366adac3384a6d255
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827686"
---
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server"></a><span data-ttu-id="0b0ed-103">Stima dell'utilizzo e del traffico vocali per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0b0ed-103">Estimating voice usage and traffic for Skype for Business Server</span></span>
 
<span data-ttu-id="0b0ed-104">È possibile utilizzare la metrica seguente per stimare il traffico degli utenti in ogni sito e il numero di porte necessarie per supportare tale traffico.</span><span class="sxs-lookup"><span data-stu-id="0b0ed-104">You can use the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>
  
> <span data-ttu-id="0b0ed-105">Per un livello di **traffico leggero** (una chiamata PSTN per utente all'ora) considerare 15 utenti per porta.</span><span class="sxs-lookup"><span data-stu-id="0b0ed-105">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>
> 
> <span data-ttu-id="0b0ed-106">Per un livello di **traffico medio** (2 chiamate PSTN per utente all'ora) considerare 10 utenti per porta.</span><span class="sxs-lookup"><span data-stu-id="0b0ed-106">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>
> 
> <span data-ttu-id="0b0ed-107">Per un livello di **traffico pesante** (3 chiamate PSTN o più per utente all'ora) considerare 5 utenti per porta.</span><span class="sxs-lookup"><span data-stu-id="0b0ed-107">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>
    
<span data-ttu-id="0b0ed-108">Il numero di porte a sua volta determina il numero di Mediation Server e gateway che saranno necessari.</span><span class="sxs-lookup"><span data-stu-id="0b0ed-108">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="0b0ed-109">I gateway PSTN (Public Switched Telephone Network) distribuiti nella maggior parte delle organizzazioni variano in dimensione da 2 a 960 porte.</span><span class="sxs-lookup"><span data-stu-id="0b0ed-109">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="0b0ed-110">Sono disponibili anche gateway più grandi, ma vengono utilizzati principalmente dai provider di servizi di telefonia.</span><span class="sxs-lookup"><span data-stu-id="0b0ed-110">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>
  
<span data-ttu-id="0b0ed-p102">Un'organizzazione con 10.000 utenti e traffico medio, ad esempio, necessiterebbe di 1000 porte. Il numero di gateway richiesti sarebbe uguale al numero totale di porte necessarie determinato in base alla capacità totale dei gateway.</span><span class="sxs-lookup"><span data-stu-id="0b0ed-p102">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>
  


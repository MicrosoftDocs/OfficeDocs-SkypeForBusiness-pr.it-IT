---
title: Ottenere il log di integrazione
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: "Riepilogo: informazioni sull'operazione Get Integration log, che fa parte dell'API dati per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 58be983ff3b282c94a4b42619a6c37c6270afcb5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186944"
---
# <a name="get-integration-log"></a><span data-ttu-id="acd68-104">Ottenere il log di integrazione</span><span class="sxs-lookup"><span data-stu-id="acd68-104">Get Integration Log</span></span>
 
<span data-ttu-id="acd68-105">**Riepilogo:** Informazioni sull'operazione Get Integration log, che fa parte dell'API dati per il dashboard della qualità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="acd68-105">**Summary:** Learn about the Get Integration Log operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="acd68-106">Call Quality dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="acd68-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="acd68-107">L'operazione Get Integration log fa parte dell'API Data per il dashboard qualità chiamata</span><span class="sxs-lookup"><span data-stu-id="acd68-107">The Get Integration Log operation is part of the Data API for Call Quality Dashboard</span></span>
  
## <a name="get-integration-log"></a><span data-ttu-id="acd68-108">Ottenere il log di integrazione</span><span class="sxs-lookup"><span data-stu-id="acd68-108">Get Integration Log</span></span>

<span data-ttu-id="acd68-109">Get Integration log Operation restituisce un elenco delle voci di log che descrivono le attività nell'elaborazione dei cubi QoE.</span><span class="sxs-lookup"><span data-stu-id="acd68-109">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>
  
<span data-ttu-id="acd68-110">Questa operazione è disabilitata per impostazione predefinita per motivi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="acd68-110">This operation is disabled by default for security reasons.</span></span> <span data-ttu-id="acd68-111">Quando disabilitata, restituisce una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="acd68-111">When disabled, it returns an empty string.</span></span> <span data-ttu-id="acd68-112">Per abilitare questa operazione, gli amministratori devono configurare l'applicazione Web host Web. config per l'API dati.</span><span class="sxs-lookup"><span data-stu-id="acd68-112">To enable this operation, administrators need to configure the web.config for Data API's host web application.</span></span>
  

|<span data-ttu-id="acd68-113">Metodo</span><span class="sxs-lookup"><span data-stu-id="acd68-113">Method</span></span>|<span data-ttu-id="acd68-114">**URI di richiesta**</span><span class="sxs-lookup"><span data-stu-id="acd68-114">**Request URI**</span></span>|<span data-ttu-id="acd68-115">**Versione HTTP**</span><span class="sxs-lookup"><span data-stu-id="acd68-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="acd68-116">Ottieni</span><span class="sxs-lookup"><span data-stu-id="acd68-116">GET</span></span>  <br/> |<span data-ttu-id="acd68-117">/QoEDataService/IntegrationLog\<portale\>https://</span><span class="sxs-lookup"><span data-stu-id="acd68-117">https://\<portal\>/QoEDataService/IntegrationLog</span></span>  <br/> |<span data-ttu-id="acd68-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="acd68-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="acd68-119">**Parametri URI** -None.</span><span class="sxs-lookup"><span data-stu-id="acd68-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="acd68-120">**Richiedi intestazioni** -nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="acd68-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="acd68-121">**Richiedi corpo** -nessuno.</span><span class="sxs-lookup"><span data-stu-id="acd68-121">**Request Body** - None.</span></span>
  
 <span data-ttu-id="acd68-122">**Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="acd68-122">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="acd68-123">**Codice di stato** : un'operazione riuscita restituisce il codice di stato 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="acd68-123">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="acd68-124">**Intestazioni di risposta** -nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="acd68-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="acd68-125">**Corpo risposta** : di seguito è riportata una struttura di esempio delle voci di log.</span><span class="sxs-lookup"><span data-stu-id="acd68-125">**Response Body** - Below is a sample structure of log entries.</span></span>
  
```
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```



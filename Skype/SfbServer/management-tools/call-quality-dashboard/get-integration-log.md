---
title: Get Integration Log
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: "Riepilogo: informazioni sull'operazione Get Integration Log, che fa parte dell'API dei dati per call quality dashboard. Call Quality Dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 69827fa9f3fd3f56843a41867b029a071799ba66
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832596"
---
# <a name="get-integration-log"></a><span data-ttu-id="d9171-104">Get Integration Log</span><span class="sxs-lookup"><span data-stu-id="d9171-104">Get Integration Log</span></span>
 
<span data-ttu-id="d9171-105">**Riepilogo:** Informazioni sull'operazione Get Integration Log, che fa parte dell'API dati per call quality dashboard.</span><span class="sxs-lookup"><span data-stu-id="d9171-105">**Summary:** Learn about the Get Integration Log operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="d9171-106">Call Quality Dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d9171-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="d9171-107">L'operazione Get Integration Log fa parte dell'API dei dati per call quality dashboard</span><span class="sxs-lookup"><span data-stu-id="d9171-107">The Get Integration Log operation is part of the Data API for Call Quality Dashboard</span></span>
  
## <a name="get-integration-log"></a><span data-ttu-id="d9171-108">Get Integration Log</span><span class="sxs-lookup"><span data-stu-id="d9171-108">Get Integration Log</span></span>

<span data-ttu-id="d9171-109">L'operazione Get Integration Log restituisce un elenco di voci di registro che descrivono le attività nell'elaborazione del cubo QoE.</span><span class="sxs-lookup"><span data-stu-id="d9171-109">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>
  
<span data-ttu-id="d9171-110">Questa operazione è disabilitata per impostazione predefinita per motivi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d9171-110">This operation is disabled by default for security reasons.</span></span> <span data-ttu-id="d9171-111">Se disabilitata, restituisce una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="d9171-111">When disabled, it returns an empty string.</span></span> <span data-ttu-id="d9171-112">Per abilitare questa operazione, gli amministratori devono configurare il web.config per l'applicazione Web host dell'API dei dati.</span><span class="sxs-lookup"><span data-stu-id="d9171-112">To enable this operation, administrators need to configure the web.config for Data API's host web application.</span></span>
  

|<span data-ttu-id="d9171-113">Metodo</span><span class="sxs-lookup"><span data-stu-id="d9171-113">Method</span></span>|<span data-ttu-id="d9171-114">**URI richiesta**</span><span class="sxs-lookup"><span data-stu-id="d9171-114">**Request URI**</span></span>|<span data-ttu-id="d9171-115">**Versione HTTP**</span><span class="sxs-lookup"><span data-stu-id="d9171-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d9171-116">GET</span><span class="sxs-lookup"><span data-stu-id="d9171-116">GET</span></span>  <br/> |<span data-ttu-id="d9171-117">https:// \<portal\> /QoEDataService/IntegrationLog</span><span class="sxs-lookup"><span data-stu-id="d9171-117">https://\<portal\>/QoEDataService/IntegrationLog</span></span>  <br/> |<span data-ttu-id="d9171-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="d9171-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="d9171-119">**Parametri URI** - Nessuno.</span><span class="sxs-lookup"><span data-stu-id="d9171-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="d9171-120">**Intestazioni richiesta** - Nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="d9171-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="d9171-121">**Corpo della richiesta** - Nessuno.</span><span class="sxs-lookup"><span data-stu-id="d9171-121">**Request Body** - None.</span></span>
  
 <span data-ttu-id="d9171-122">**Risposta:** la risposta include un codice di stato HTTP e un set di intestazioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="d9171-122">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="d9171-123">**Codice di stato:** un'operazione riuscita restituisce il codice di stato 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="d9171-123">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="d9171-124">**Intestazioni risposta** - Nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="d9171-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="d9171-125">**Corpo della risposta:** di seguito è riportata una struttura di esempio di voci di registro.</span><span class="sxs-lookup"><span data-stu-id="d9171-125">**Response Body** - Below is a sample structure of log entries.</span></span>
  
```json
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```



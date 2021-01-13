---
title: Get Last Integration Data
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
ms.assetid: e7967dd9-0d6a-4a80-8b59-b8fc2e5615f8
description: "Riepilogo: informazioni sull'operazione Get last Integration data, che fa parte dell'API dei dati per il dashboard per la qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: c40041e41e04d2bdc62a9eb9fa1eb699697a5b3d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832516"
---
# <a name="get-last-integration-data"></a><span data-ttu-id="94b33-104">Get Last Integration Data</span><span class="sxs-lookup"><span data-stu-id="94b33-104">Get Last Integration Data</span></span>
 
<span data-ttu-id="94b33-105">**Riepilogo:** Informazioni sull'operazione Get last Integration data, che fa parte dell'API Data per il dashboard qualità chiamata.</span><span class="sxs-lookup"><span data-stu-id="94b33-105">**Summary:** Learn about the Get Last Integration Data operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="94b33-106">Call Quality dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="94b33-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="94b33-107">L'operazione Get last Integration data fa parte dell'API Data per il dashboard qualità chiamata.</span><span class="sxs-lookup"><span data-stu-id="94b33-107">The Get Last Integration Data operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-last-integration-data"></a><span data-ttu-id="94b33-108">Get Last Integration Data</span><span class="sxs-lookup"><span data-stu-id="94b33-108">Get Last Integration Data</span></span>

<span data-ttu-id="94b33-109">Get last Integration data Operation restituisce l'elenco degli ultimi 5 esito positivo/negativo dell'archiviazione e dell'elaborazione del cubo.</span><span class="sxs-lookup"><span data-stu-id="94b33-109">Get Last Integration Data operation returns the list of last 5 success/failure of archiving and cube processing.</span></span>
  
<span data-ttu-id="94b33-110">Questa funzionalità è disabilitata per impostazione predefinita e deve essere abilitata configurando l'API dei dati.</span><span class="sxs-lookup"><span data-stu-id="94b33-110">This feature is disabled by default and it needs to be enabled by configuring the Data API.</span></span>
  

|<span data-ttu-id="94b33-111">**Metodo**</span><span class="sxs-lookup"><span data-stu-id="94b33-111">**Method**</span></span>|<span data-ttu-id="94b33-112">**URI della richiesta**</span><span class="sxs-lookup"><span data-stu-id="94b33-112">**Request URI**</span></span>|<span data-ttu-id="94b33-113">**Versione HTTP**</span><span class="sxs-lookup"><span data-stu-id="94b33-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="94b33-114">GET</span><span class="sxs-lookup"><span data-stu-id="94b33-114">GET</span></span>  <br/> |<span data-ttu-id="94b33-115">https:// \<portal\> /QoEDataService/IntegrationLog/status</span><span class="sxs-lookup"><span data-stu-id="94b33-115">https://\<portal\>/QoEDataService/IntegrationLog/Status</span></span>  <br/> |<span data-ttu-id="94b33-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="94b33-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="94b33-117">**Parametri URI** -None.</span><span class="sxs-lookup"><span data-stu-id="94b33-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="94b33-118">**Intestazioni richieste** -nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="94b33-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="94b33-119">**Corpo richiesta** -nessuno.</span><span class="sxs-lookup"><span data-stu-id="94b33-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="94b33-120">**Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="94b33-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="94b33-121">**Codice di stato** -un'operazione completata restituisce il codice di stato 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="94b33-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="94b33-122">**Intestazioni di risposta** -Nessun intestazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="94b33-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="94b33-123">**Corpo di risposta** -di seguito è riportato lo stato di un registro di esempio.</span><span class="sxs-lookup"><span data-stu-id="94b33-123">**Response Body** - Below is a sample log status.</span></span>
  
```json
{
"LastSuccessIntegrations": ["01/18/2015 10:30:13",
"01/18/2015 10:28:29",
"01/17/2015 15:15:17",
"01/17/2015 15:00:17",
"01/17/2015 14:45:13"],
"LastSuccessCubeProcessings": ["01/17/2015 15:16:40",
"01/17/2015 15:01:41",
"01/17/2015 14:47:19",
"01/17/2015 14:31:40",
"01/17/2015 14:17:01"],
"LastFailedIntegrations":  ,
"LastFailedCubeProcessings": ["01/18/2015 10:30:58",
"01/18/2015 10:29:28",
"01/17/2015 10:02:20",
"01/15/2015 20:01:56",
"01/15/2015 19:45:50"],
"LastDataIntegrationStart": null,
"LastCubeProcessingStart": "01/18/2015 10:30:16"
}
```

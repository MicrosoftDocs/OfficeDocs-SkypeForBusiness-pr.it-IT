---
title: API dati per Call Quality Dashboard (Call Quality Dashboard) in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: "Riepilogo: informazioni sull'API rata per il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: f74f581a3d46ba7cf75daf92df5ade16dab510d0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186974"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="55afe-104">API dati per Call Quality Dashboard (Call Quality Dashboard) in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="55afe-104">Data API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="55afe-105">**Riepilogo:** Informazioni sull'API rata per il dashboard qualità chiamata.</span><span class="sxs-lookup"><span data-stu-id="55afe-105">**Summary:** Learn about the Rata API for Call Quality Dashboard.</span></span> <span data-ttu-id="55afe-106">Call Quality dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="55afe-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="55afe-107">L'API dati offre accesso a livello di codice per Call Quality dashboard per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="55afe-107">The Data API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="data-api-for-call-quality-dashboard"></a><span data-ttu-id="55afe-108">API dati per dashboard qualità chiamata</span><span class="sxs-lookup"><span data-stu-id="55afe-108">Data API for Call Quality Dashboard</span></span>

<span data-ttu-id="55afe-109">L'API dati offre un'interfaccia di query al cubo QoE.</span><span class="sxs-lookup"><span data-stu-id="55afe-109">The Data API offers a query interface to the QoE Cube.</span></span> <span data-ttu-id="55afe-110">L'API dati è un'API REST per l'uso di database multidimensionali che fornisce metriche QoE aggregate basate su dimensioni e filtri specificati.</span><span class="sxs-lookup"><span data-stu-id="55afe-110">The Data API is a REST API for working with multi-dimensional database that provides aggregated QoE metrics based on specified dimensions and filters.</span></span>
  
<span data-ttu-id="55afe-111">Le operazioni REST sono incluse nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="55afe-111">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="55afe-112">**Operazione**</span><span class="sxs-lookup"><span data-stu-id="55afe-112">**Operation**</span></span>|<span data-ttu-id="55afe-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="55afe-113">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="55afe-114">Ottieni cubo</span><span class="sxs-lookup"><span data-stu-id="55afe-114">Get Cube</span></span>](get-cube.md) <br/> |<span data-ttu-id="55afe-115">Ottenere l'elenco delle dimensioni e delle misure disponibili.</span><span class="sxs-lookup"><span data-stu-id="55afe-115">Get the list of available dimensions and measurements.</span></span>  <br/> |
|[<span data-ttu-id="55afe-116">Ottenere i membri della dimensione</span><span class="sxs-lookup"><span data-stu-id="55afe-116">Get Dimension Members</span></span>](get-dimension-members.md) <br/> |<span data-ttu-id="55afe-117">L'operazione get Members Dimension restituisce l'elenco dei membri di una dimensione specifica.</span><span class="sxs-lookup"><span data-stu-id="55afe-117">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="55afe-118">È anche possibile filtrare l'elenco dei membri e ottenere un sottoinsieme, per ridurre il costo del bonifico bancario.</span><span class="sxs-lookup"><span data-stu-id="55afe-118">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>  <br/> |
|[<span data-ttu-id="55afe-119">Esegui query</span><span class="sxs-lookup"><span data-stu-id="55afe-119">Run Query</span></span>](run-query.md) <br/> |<span data-ttu-id="55afe-120">L'operazione Esegui query offre la possibilità di eseguire una query sul cubo in base a dimensioni, misure e filtri specificati e restituire i dati.</span><span class="sxs-lookup"><span data-stu-id="55afe-120">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>  <br/> |
|[<span data-ttu-id="55afe-121">Cancellare la cache</span><span class="sxs-lookup"><span data-stu-id="55afe-121">Clear Cache</span></span>](clear-cache.md) <br/> |<span data-ttu-id="55afe-122">Cancella operazione cache Elimina la cache sul server per query e dati.</span><span class="sxs-lookup"><span data-stu-id="55afe-122">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="55afe-123">In questo modo verrà reimpostata la cache e in seguito verranno riprodotti nuovi dati dal cubo QoE per le nuove richieste.</span><span class="sxs-lookup"><span data-stu-id="55afe-123">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>  <br/> |
|[<span data-ttu-id="55afe-124">Ottenere il log di integrazione</span><span class="sxs-lookup"><span data-stu-id="55afe-124">Get Integration Log</span></span>](get-integration-log.md) <br/> |<span data-ttu-id="55afe-125">Get Integration log Operation restituisce un elenco delle voci di log che descrivono le attività nell'elaborazione dei cubi QoE.</span><span class="sxs-lookup"><span data-stu-id="55afe-125">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>  <br/> |
|[<span data-ttu-id="55afe-126">Ottenere gli ultimi dati di integrazione</span><span class="sxs-lookup"><span data-stu-id="55afe-126">Get Last Integration Data</span></span>](get-last-integration-data.md) <br/> |<span data-ttu-id="55afe-127">Ottenere gli ultimi dati di integrazione dal cubo.</span><span class="sxs-lookup"><span data-stu-id="55afe-127">Get the last integration data from the cube.</span></span>  <br/> |
   
 <span data-ttu-id="55afe-128">**Supporto CORS (Cross-Origin Resource Sharing) per API dati**</span><span class="sxs-lookup"><span data-stu-id="55afe-128">**Cross-Origin Resource Sharing (CORS) Support for Data API**</span></span>
  
<span data-ttu-id="55afe-129">L'API dei dati supporta la condivisione delle risorse CORS (Cross-Origin Resource Sharing).</span><span class="sxs-lookup"><span data-stu-id="55afe-129">Data API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="55afe-130">CORS è una caratteristica HTTP che consente a un'applicazione Web in uso in un dominio di accedere alle risorse in un altro dominio.</span><span class="sxs-lookup"><span data-stu-id="55afe-130">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="55afe-131">I Web browser implementano una restrizione [](https://www.w3.org/Security/wiki/Same_Origin_Policy) di sicurezza nota come criterio di origine della stessa origine che impedisce la chiamata delle API in un dominio diverso da una pagina Web.</span><span class="sxs-lookup"><span data-stu-id="55afe-131">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="55afe-132">CORS offre un modo sicuro per consentire a un dominio (il dominio di origine) di chiamare le API in un altro dominio.</span><span class="sxs-lookup"><span data-stu-id="55afe-132">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="55afe-133">Vedere la [specifica CORS](https://www.w3.org/TR/cors/) per informazioni dettagliate su CORS.</span><span class="sxs-lookup"><span data-stu-id="55afe-133">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="55afe-134">**Abilitazione di CORS for Data API**</span><span class="sxs-lookup"><span data-stu-id="55afe-134">**Enabling CORS for Data API**</span></span>
  
 <span data-ttu-id="55afe-135">Di seguito è riportato un Estratto di data API Web. config, che mostra due domini elencati nelle impostazioni delle applicazioni di corsTrustedOrigin.</span><span class="sxs-lookup"><span data-stu-id="55afe-135">The following is an excerpt of Data API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="55afe-136">Tutte le richieste effettuate dagli script caricati da questi server sono attendibili dall'API dati.</span><span class="sxs-lookup"><span data-stu-id="55afe-136">All requests made by the scripts loaded from these servers are trusted by Data API.</span></span>
  
<span data-ttu-id="55afe-137">Ricordarsi di includere l'esatto protocollo, il nome host e la porta (se presenti).</span><span class="sxs-lookup"><span data-stu-id="55afe-137">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="55afe-138">Non inserire alcun carattere barra (/) alla fine.</span><span class="sxs-lookup"><span data-stu-id="55afe-138">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="55afe-139">È possibile specificare più voci separandoli con una virgola.</span><span class="sxs-lookup"><span data-stu-id="55afe-139">Multiple entries can be specified by separating with commas.</span></span>
  
```
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```



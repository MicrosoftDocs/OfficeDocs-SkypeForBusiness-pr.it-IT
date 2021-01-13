---
title: API dei dati per Call Quality Dashboard (CQD) in Skype for Business Server
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
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: "Riepilogo: informazioni sull'API dei dati per il dashboard per la qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 367aa1bf1103863fff37fbcd4f8d9fa379de7c1d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832696"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="a0cd7-104">API dei dati per Call Quality Dashboard (CQD) in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a0cd7-104">Data API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="a0cd7-105">**Riepilogo:** Informazioni sull'API dei dati per il dashboard qualità chiamata.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-105">**Summary:** Learn about the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="a0cd7-106">Call Quality dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="a0cd7-107">L'API Data fornisce l'accesso programmatico per il dashboard qualità chiamata per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-107">The Data API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="data-api-for-call-quality-dashboard"></a><span data-ttu-id="a0cd7-108">API dei dati per il dashboard qualità chiamata</span><span class="sxs-lookup"><span data-stu-id="a0cd7-108">Data API for Call Quality Dashboard</span></span>

<span data-ttu-id="a0cd7-109">L'API Data offre un'interfaccia di query al cubo QoE.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-109">The Data API offers a query interface to the QoE Cube.</span></span> <span data-ttu-id="a0cd7-110">L'API dei dati è un'API REST per l'utilizzo di database multidimensionali che fornisce metriche QoE aggregate in base alle dimensioni e ai filtri specificati.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-110">The Data API is a REST API for working with multi-dimensional database that provides aggregated QoE metrics based on specified dimensions and filters.</span></span>
  
<span data-ttu-id="a0cd7-111">Le operazioni REST sono incluse nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-111">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="a0cd7-112">**Operazione**</span><span class="sxs-lookup"><span data-stu-id="a0cd7-112">**Operation**</span></span>|<span data-ttu-id="a0cd7-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="a0cd7-113">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="a0cd7-114">Get Cube</span><span class="sxs-lookup"><span data-stu-id="a0cd7-114">Get Cube</span></span>](get-cube.md) <br/> |<span data-ttu-id="a0cd7-115">Ottenere l'elenco delle dimensioni e delle misure disponibili.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-115">Get the list of available dimensions and measurements.</span></span>  <br/> |
|[<span data-ttu-id="a0cd7-116">Get Dimension Members</span><span class="sxs-lookup"><span data-stu-id="a0cd7-116">Get Dimension Members</span></span>](get-dimension-members.md) <br/> |<span data-ttu-id="a0cd7-117">Get Dimension members Operation restituisce l'elenco dei membri di una dimensione specifica.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-117">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="a0cd7-118">È inoltre possibile filtrare l'elenco dei membri e ottenere un sottoinsieme, per ridurre il costo di trasferimento dei cavi.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-118">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>  <br/> |
|[<span data-ttu-id="a0cd7-119">Run Query</span><span class="sxs-lookup"><span data-stu-id="a0cd7-119">Run Query</span></span>](run-query.md) <br/> |<span data-ttu-id="a0cd7-120">L'operazione Esegui query consente di eseguire una query sul cubo in base alle dimensioni, alle misure e ai filtri specificati e di restituire i dati.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-120">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>  <br/> |
|[<span data-ttu-id="a0cd7-121">Clear Cache</span><span class="sxs-lookup"><span data-stu-id="a0cd7-121">Clear Cache</span></span>](clear-cache.md) <br/> |<span data-ttu-id="a0cd7-122">Cancella operazione cache Elimina la cache sul server per le query e i dati.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-122">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="a0cd7-123">In questo modo verrà ripristinata la cache e verranno riportati i dati da un cubo QoE dopo per nuove richieste.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-123">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>  <br/> |
|[<span data-ttu-id="a0cd7-124">Get Integration Log</span><span class="sxs-lookup"><span data-stu-id="a0cd7-124">Get Integration Log</span></span>](get-integration-log.md) <br/> |<span data-ttu-id="a0cd7-125">Get Integration log Operation restituisce un elenco di voci di registro che descrivono le attività nell'elaborazione del cubo QoE.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-125">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>  <br/> |
|[<span data-ttu-id="a0cd7-126">Get Last Integration Data</span><span class="sxs-lookup"><span data-stu-id="a0cd7-126">Get Last Integration Data</span></span>](get-last-integration-data.md) <br/> |<span data-ttu-id="a0cd7-127">Recuperare i dati dell'ultima integrazione dal cubo.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-127">Get the last integration data from the cube.</span></span>  <br/> |
   
 <span data-ttu-id="a0cd7-128">**Supporto per la condivisione delle risorse di CORS (Cross-Origin Resource) per API dei dati**</span><span class="sxs-lookup"><span data-stu-id="a0cd7-128">**Cross-Origin Resource Sharing (CORS) Support for Data API**</span></span>
  
<span data-ttu-id="a0cd7-129">API dei dati supporta la condivisione delle risorse tra origini (CORS).</span><span class="sxs-lookup"><span data-stu-id="a0cd7-129">Data API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="a0cd7-130">CORS è una funzionalità HTTP che consente a un'applicazione Web in esecuzione in un dominio di accedere alle risorse in un altro dominio.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-130">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="a0cd7-131">I Web browser implementano una restrizione di sicurezza nota come criterio di origine dello stesso [criterio](https://www.w3.org/Security/wiki/Same_Origin_Policy) di origine che impedisce la chiamata delle API in un dominio diverso da una pagina Web.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-131">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="a0cd7-132">CORS fornisce un modo sicuro per consentire a un dominio (il dominio di origine) di chiamare API in un altro dominio.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-132">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="a0cd7-133">Per informazioni dettagliate su CORS, vedere la [specifica di CORS](https://www.w3.org/TR/cors/) .</span><span class="sxs-lookup"><span data-stu-id="a0cd7-133">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="a0cd7-134">**Abilitazione di CORS per API dei dati**</span><span class="sxs-lookup"><span data-stu-id="a0cd7-134">**Enabling CORS for Data API**</span></span>
  
 <span data-ttu-id="a0cd7-135">Di seguito è riportato un Estratto di data API web.config, che mostra due domini elencati nelle impostazioni delle applicazioni di corsTrustedOrigin.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-135">The following is an excerpt of Data API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="a0cd7-136">Tutte le richieste eseguite dagli script caricati da questi server sono considerate attendibili dall'API dei dati.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-136">All requests made by the scripts loaded from these servers are trusted by Data API.</span></span>
  
<span data-ttu-id="a0cd7-137">Tenere presente che il protocollo, il nome host e la porta (se presenti) sono esatte.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-137">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="a0cd7-138">Non inserire alcun carattere barra (/) alla fine.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-138">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="a0cd7-139">È possibile specificare più voci separando le virgole.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-139">Multiple entries can be specified by separating with commas.</span></span>
  
```xml
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```



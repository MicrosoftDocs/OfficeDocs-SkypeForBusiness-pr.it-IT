---
title: Repository API for Call Quality Dashboard (CQD) in Skype for Business Server
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
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: "Riepilogo: informazioni sull'API repository per call quality dashboard. Call Quality Dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 982ec0932f0a57958e1929a6ae2413ada0b5c9fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803126"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="4a353-104">Repository API for Call Quality Dashboard (CQD) in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4a353-104">Repository API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="4a353-105">**Riepilogo:** Informazioni sull'API repository per call quality dashboard.</span><span class="sxs-lookup"><span data-stu-id="4a353-105">**Summary:** Learn about the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="4a353-106">Call Quality Dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4a353-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="4a353-107">L'API repository fornisce l'accesso programmatico per call quality dashboard per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4a353-107">The Repository API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="repository-api-for-call-quality-dashboard"></a><span data-ttu-id="4a353-108">API di repository per call quality dashboard</span><span class="sxs-lookup"><span data-stu-id="4a353-108">Repository API for Call Quality Dashboard</span></span>

<span data-ttu-id="4a353-109">L'API repository offre un'interfaccia di accesso ai dati per il database repository.</span><span class="sxs-lookup"><span data-stu-id="4a353-109">Repository API offers a data access interface to repository database.</span></span> <span data-ttu-id="4a353-110">Il repository consente di organizzare il contenuto in una struttura ad albero o in un grafico in modo che gli utenti possano raggrupparli nel modo più opportuno per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="4a353-110">The repository allows the contents to be organized in a tree or graph structure such that users can group them in the ways that make sense to the users.</span></span> <span data-ttu-id="4a353-111">L'archivio supporta due tipi generali di utenti: utente di sistema, ovvero un utente predefinito che rappresenta il repository, e utenti normali che rappresentano gli utenti autorizzati del repository.</span><span class="sxs-lookup"><span data-stu-id="4a353-111">The repository supports two general types of users: system user, which is a built-in user representing the repository, and regular users that represent the authorized users of the repository.</span></span>
  
<span data-ttu-id="4a353-112">L'API repository è costituita da tre servizi generali:</span><span class="sxs-lookup"><span data-stu-id="4a353-112">Repository API consists of three general services:</span></span> 
  
- <span data-ttu-id="4a353-113">[Servizio utente per CQD-](user-service.md) per l'accesso agli utenti.</span><span class="sxs-lookup"><span data-stu-id="4a353-113">[User Service for CQD](user-service.md) - for accessing Users.</span></span>
    
- <span data-ttu-id="4a353-114">[Item Service for Call Quality Dashboard (CQD)](item-service.md) - Per accedere agli elementi e ai contenuti archiviati in Elementi.</span><span class="sxs-lookup"><span data-stu-id="4a353-114">[Item Service for Call Quality Dashboard (CQD)](item-service.md) - for accessing Items and the contents stored in Items.</span></span>
    
- <span data-ttu-id="4a353-115">[Servizio impostazioni utente per call quality dashboard (CQD)](user-settings-service.md) - per l'accesso alle impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="4a353-115">[User Settings Service for Call Quality Dashboard (CQD)](user-settings-service.md) - for accessing User Settings.</span></span>
    
<span data-ttu-id="4a353-116">Call Quality Dashboard usa l'API Repository per gestire le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4a353-116">Call Quality Dashboard uses Repository API to manage the following information:</span></span> 
  
- <span data-ttu-id="4a353-117">**User:** rappresentazione degli utenti che hanno accesso al repository.</span><span class="sxs-lookup"><span data-stu-id="4a353-117">**User** - representation of Users who have access to the repository.</span></span>
    
- <span data-ttu-id="4a353-118">**Report:** contiene un elenco di query, archiviate come contenuto negli elementi del repository.</span><span class="sxs-lookup"><span data-stu-id="4a353-118">**Report** - contains a list of Queries, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="4a353-119">**Query:** usata per recuperare i dati dall'API dei dati, archiviati come contenuto negli elementi del repository.</span><span class="sxs-lookup"><span data-stu-id="4a353-119">**Query** - used to retrieve data from Data API, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="4a353-120">**Impostazione utente:** descrive un comportamento facoltativo dell'applicazione per l'utente.</span><span class="sxs-lookup"><span data-stu-id="4a353-120">**User Setting** - describes an optional application behavior for the user.</span></span>
    
  <span data-ttu-id="4a353-121">**Supporto cors (Cross-Origin Resource Sharing) per l'API repository**</span><span class="sxs-lookup"><span data-stu-id="4a353-121">**Cross-Origin Resource Sharing (CORS) Support for Repository API**</span></span>
  
<span data-ttu-id="4a353-122">L'API repository supporta cors (Cross-Origin Resource Sharing).</span><span class="sxs-lookup"><span data-stu-id="4a353-122">Repository API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="4a353-123">CORS è una funzionalità HTTP che consente a un'applicazione Web in esecuzione in un dominio di accedere alle risorse in un altro dominio.</span><span class="sxs-lookup"><span data-stu-id="4a353-123">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="4a353-124">I Web browser implementano [](https://www.w3.org/Security/wiki/Same_Origin_Policy) una restrizione di sicurezza nota come criterio di stessa origine che impedisce a una pagina Web di chiamare API in un dominio diverso.</span><span class="sxs-lookup"><span data-stu-id="4a353-124">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="4a353-125">CORS offre un modo sicuro per consentire a un dominio (il dominio di origine) di chiamare le API in un altro dominio.</span><span class="sxs-lookup"><span data-stu-id="4a353-125">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="4a353-126">Per informazioni [dettagliate](https://www.w3.org/TR/cors/) su CORS, vedere la specifica CORS.</span><span class="sxs-lookup"><span data-stu-id="4a353-126">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="4a353-127">**Abilitazione dell'API CORS per repository**</span><span class="sxs-lookup"><span data-stu-id="4a353-127">**Enabling CORS for Repository API**</span></span>
  
 <span data-ttu-id="4a353-128">Di seguito è riportato un estratto di Repository API web.config, che mostra due domini elencati nelle impostazioni dell'applicazione corsTrustedOrigin.</span><span class="sxs-lookup"><span data-stu-id="4a353-128">The following is an excerpt of Repository API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="4a353-129">Tutte le richieste effettuate dagli script caricati da questi server sono attendibili dall'API repository.</span><span class="sxs-lookup"><span data-stu-id="4a353-129">All requests made by the scripts loaded from these servers are trusted by Repository API.</span></span>
  
<span data-ttu-id="4a353-130">Ricordarsi di includere il protocollo esatto, il nome host e la porta (se presenti).</span><span class="sxs-lookup"><span data-stu-id="4a353-130">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="4a353-131">Non inserire alcun carattere barra (/) alla fine.</span><span class="sxs-lookup"><span data-stu-id="4a353-131">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="4a353-132">È possibile specificare più voci separandole con una virgola.</span><span class="sxs-lookup"><span data-stu-id="4a353-132">Multiple entries can be specified by separating with commas.</span></span>
  
```xml
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```



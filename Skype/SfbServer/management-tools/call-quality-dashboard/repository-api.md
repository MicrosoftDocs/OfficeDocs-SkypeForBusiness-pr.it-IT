---
title: API del repository per Call Quality Dashboard (CQD) in Skype for Business Server
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
description: "Riepilogo: informazioni sull'API del repository per il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 982ec0932f0a57958e1929a6ae2413ada0b5c9fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803126"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="cd550-104">API del repository per Call Quality Dashboard (CQD) in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="cd550-104">Repository API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="cd550-105">**Riepilogo:** Informazioni sull'API del repository per il dashboard qualità chiamata.</span><span class="sxs-lookup"><span data-stu-id="cd550-105">**Summary:** Learn about the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="cd550-106">Call Quality dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="cd550-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="cd550-107">L'API del repository fornisce l'accesso programmatico per il dashboard sulla qualità delle chiamate per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="cd550-107">The Repository API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="repository-api-for-call-quality-dashboard"></a><span data-ttu-id="cd550-108">API del repository per il dashboard per la qualità delle chiamate</span><span class="sxs-lookup"><span data-stu-id="cd550-108">Repository API for Call Quality Dashboard</span></span>

<span data-ttu-id="cd550-109">L'API del repository offre un'interfaccia di accesso ai dati per il database repository.</span><span class="sxs-lookup"><span data-stu-id="cd550-109">Repository API offers a data access interface to repository database.</span></span> <span data-ttu-id="cd550-110">L'archivio consente di organizzare il contenuto in una struttura ad albero o grafico in modo che gli utenti possano raggrupparli in modo da avere un senso per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="cd550-110">The repository allows the contents to be organized in a tree or graph structure such that users can group them in the ways that make sense to the users.</span></span> <span data-ttu-id="cd550-111">L'archivio supporta due tipi generali di utenti: l'utente di sistema, che è un utente incorporato che rappresenta l'archivio, e gli utenti regolari che rappresentano gli utenti autorizzati del repository.</span><span class="sxs-lookup"><span data-stu-id="cd550-111">The repository supports two general types of users: system user, which is a built-in user representing the repository, and regular users that represent the authorized users of the repository.</span></span>
  
<span data-ttu-id="cd550-112">API del repository è costituito da tre servizi generali:</span><span class="sxs-lookup"><span data-stu-id="cd550-112">Repository API consists of three general services:</span></span> 
  
- <span data-ttu-id="cd550-113">[Servizio utente per CQD](user-service.md) -per l'accesso agli utenti.</span><span class="sxs-lookup"><span data-stu-id="cd550-113">[User Service for CQD](user-service.md) - for accessing Users.</span></span>
    
- <span data-ttu-id="cd550-114">[Servizio elementi per il dashboard per la qualità delle chiamate (CQD)](item-service.md) -per accedere agli elementi e ai contenuti archiviati negli elementi.</span><span class="sxs-lookup"><span data-stu-id="cd550-114">[Item Service for Call Quality Dashboard (CQD)](item-service.md) - for accessing Items and the contents stored in Items.</span></span>
    
- <span data-ttu-id="cd550-115">[User Settings Service for Call Quality Dashboard (CQD)](user-settings-service.md) -per accedere alle impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="cd550-115">[User Settings Service for Call Quality Dashboard (CQD)](user-settings-service.md) - for accessing User Settings.</span></span>
    
<span data-ttu-id="cd550-116">Call Quality dashboard utilizza l'API del repository per gestire le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cd550-116">Call Quality Dashboard uses Repository API to manage the following information:</span></span> 
  
- <span data-ttu-id="cd550-117">Rappresentazione **utente** degli utenti che dispongono dell'accesso all'archivio.</span><span class="sxs-lookup"><span data-stu-id="cd550-117">**User** - representation of Users who have access to the repository.</span></span>
    
- <span data-ttu-id="cd550-118">**Report** : contiene un elenco di query, memorizzate come contenuto negli elementi del repository.</span><span class="sxs-lookup"><span data-stu-id="cd550-118">**Report** - contains a list of Queries, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="cd550-119">**Query** -utilizzata per recuperare i dati dall'API dei dati, archiviati come contenuto negli elementi del repository.</span><span class="sxs-lookup"><span data-stu-id="cd550-119">**Query** - used to retrieve data from Data API, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="cd550-120">**Impostazione utente** -descrive un comportamento facoltativo dell'applicazione per l'utente.</span><span class="sxs-lookup"><span data-stu-id="cd550-120">**User Setting** - describes an optional application behavior for the user.</span></span>
    
  <span data-ttu-id="cd550-121">**Supporto per la condivisione delle risorse tra origini (CORS) per l'API del repository**</span><span class="sxs-lookup"><span data-stu-id="cd550-121">**Cross-Origin Resource Sharing (CORS) Support for Repository API**</span></span>
  
<span data-ttu-id="cd550-122">L'API del repository supporta la condivisione delle risorse tra origini (CORS).</span><span class="sxs-lookup"><span data-stu-id="cd550-122">Repository API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="cd550-123">CORS è una funzionalità HTTP che consente a un'applicazione Web in esecuzione in un dominio di accedere alle risorse in un altro dominio.</span><span class="sxs-lookup"><span data-stu-id="cd550-123">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="cd550-124">I Web browser implementano una restrizione di sicurezza nota come criterio di origine dello stesso [criterio](https://www.w3.org/Security/wiki/Same_Origin_Policy) di origine che impedisce la chiamata delle API in un dominio diverso da una pagina Web.</span><span class="sxs-lookup"><span data-stu-id="cd550-124">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="cd550-125">CORS fornisce un modo sicuro per consentire a un dominio (il dominio di origine) di chiamare API in un altro dominio.</span><span class="sxs-lookup"><span data-stu-id="cd550-125">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="cd550-126">Per informazioni dettagliate su CORS, vedere la [specifica di CORS](https://www.w3.org/TR/cors/) .</span><span class="sxs-lookup"><span data-stu-id="cd550-126">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="cd550-127">**Abilitazione di CORS per l'API del repository**</span><span class="sxs-lookup"><span data-stu-id="cd550-127">**Enabling CORS for Repository API**</span></span>
  
 <span data-ttu-id="cd550-128">Di seguito è riportato un estratto dell'API del repository web.config, che mostra due domini elencati nelle impostazioni delle applicazioni di corsTrustedOrigin.</span><span class="sxs-lookup"><span data-stu-id="cd550-128">The following is an excerpt of Repository API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="cd550-129">Tutte le richieste eseguite dagli script caricati da questi server sono considerate attendibili dall'API del repository.</span><span class="sxs-lookup"><span data-stu-id="cd550-129">All requests made by the scripts loaded from these servers are trusted by Repository API.</span></span>
  
<span data-ttu-id="cd550-130">Tenere presente che il protocollo, il nome host e la porta (se presenti) sono esatte.</span><span class="sxs-lookup"><span data-stu-id="cd550-130">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="cd550-131">Non inserire alcun carattere barra (/) alla fine.</span><span class="sxs-lookup"><span data-stu-id="cd550-131">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="cd550-132">È possibile specificare più voci separando le virgole.</span><span class="sxs-lookup"><span data-stu-id="cd550-132">Multiple entries can be specified by separating with commas.</span></span>
  
```xml
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```



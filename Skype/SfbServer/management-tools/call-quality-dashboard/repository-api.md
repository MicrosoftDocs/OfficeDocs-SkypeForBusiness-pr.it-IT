---
title: API del repository per Call Quality Dashboard (Call Quality Dashboard) in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: "Riepilogo: informazioni sull'API del repository per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: a027cc7402bad7524343391f9bf7039dd077a46c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816695"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="22259-104">API del repository per Call Quality Dashboard (Call Quality Dashboard) in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="22259-104">Repository API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="22259-105">**Riepilogo:** Informazioni sull'API del repository per il dashboard della qualità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="22259-105">**Summary:** Learn about the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="22259-106">Call Quality dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="22259-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="22259-107">L'API del repository offre accesso a livello di codice per Call Quality dashboard per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="22259-107">The Repository API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="repository-api-for-call-quality-dashboard"></a><span data-ttu-id="22259-108">API del repository per dashboard qualità chiamata</span><span class="sxs-lookup"><span data-stu-id="22259-108">Repository API for Call Quality Dashboard</span></span>

<span data-ttu-id="22259-109">API del repository offre un'interfaccia di accesso ai dati per il database repository.</span><span class="sxs-lookup"><span data-stu-id="22259-109">Repository API offers a data access interface to repository database.</span></span> <span data-ttu-id="22259-110">Il repository consente di organizzare il contenuto in una struttura ad albero o a grafico in modo che gli utenti possano raggrupparli in modo che abbiano senso per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="22259-110">The repository allows the contents to be organized in a tree or graph structure such that users can group them in the ways that make sense to the users.</span></span> <span data-ttu-id="22259-111">Il repository supporta due tipi generali di utenti: l'utente di sistema, che è un utente predefinito che rappresenta il repository e gli utenti regolari che rappresentano gli utenti autorizzati del repository.</span><span class="sxs-lookup"><span data-stu-id="22259-111">The repository supports two general types of users: system user, which is a built-in user representing the repository, and regular users that represent the authorized users of the repository.</span></span>
  
<span data-ttu-id="22259-112">L'API del repository è costituita da tre servizi generali:</span><span class="sxs-lookup"><span data-stu-id="22259-112">Repository API consists of three general services:</span></span> 
  
- <span data-ttu-id="22259-113">[Servizio utente per Call Quality dashboard](user-service.md) -per l'accesso agli utenti.</span><span class="sxs-lookup"><span data-stu-id="22259-113">[User Service for CQD](user-service.md) - for accessing Users.</span></span>
    
- <span data-ttu-id="22259-114">[Item Service per Call Quality Dashboard (Call Quality Dashboard)](item-service.md) -per l'accesso agli elementi e il contenuto archiviato in elementi.</span><span class="sxs-lookup"><span data-stu-id="22259-114">[Item Service for Call Quality Dashboard (CQD)](item-service.md) - for accessing Items and the contents stored in Items.</span></span>
    
- <span data-ttu-id="22259-115">[Servizio impostazioni utente per Call Quality Dashboard (Call Quality Dashboard)](user-settings-service.md) -per l'accesso alle impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="22259-115">[User Settings Service for Call Quality Dashboard (CQD)](user-settings-service.md) - for accessing User Settings.</span></span>
    
<span data-ttu-id="22259-116">Call Quality dashboard usa l'API del repository per gestire le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="22259-116">Call Quality Dashboard uses Repository API to manage the following information:</span></span> 
  
- <span data-ttu-id="22259-117">Rappresentazione **utente** degli utenti che hanno accesso al repository.</span><span class="sxs-lookup"><span data-stu-id="22259-117">**User** - representation of Users who have access to the repository.</span></span>
    
- <span data-ttu-id="22259-118">**Report** : contiene un elenco di query, archiviate come contenuto negli elementi del repository.</span><span class="sxs-lookup"><span data-stu-id="22259-118">**Report** - contains a list of Queries, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="22259-119">**Query** : consente di recuperare dati dall'API dati, archiviati come contenuto in elementi del repository.</span><span class="sxs-lookup"><span data-stu-id="22259-119">**Query** - used to retrieve data from Data API, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="22259-120">**Impostazione utente** : descrive un comportamento facoltativo dell'applicazione per l'utente.</span><span class="sxs-lookup"><span data-stu-id="22259-120">**User Setting** - describes an optional application behavior for the user.</span></span>
    
  <span data-ttu-id="22259-121">**Supporto CORS (Cross-Origin Resource Sharing) per l'API del repository**</span><span class="sxs-lookup"><span data-stu-id="22259-121">**Cross-Origin Resource Sharing (CORS) Support for Repository API**</span></span>
  
<span data-ttu-id="22259-122">L'API del repository supporta la condivisione delle risorse CORS (Cross-Origin Resource Sharing).</span><span class="sxs-lookup"><span data-stu-id="22259-122">Repository API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="22259-123">CORS è una caratteristica HTTP che consente a un'applicazione Web in uso in un dominio di accedere alle risorse in un altro dominio.</span><span class="sxs-lookup"><span data-stu-id="22259-123">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="22259-124">I Web browser implementano una restrizione di sicurezza nota come criterio di origine [della stessa origine](https://www.w3.org/Security/wiki/Same_Origin_Policy) che impedisce la chiamata delle API in un dominio diverso da una pagina Web.</span><span class="sxs-lookup"><span data-stu-id="22259-124">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="22259-125">CORS offre un modo sicuro per consentire a un dominio (il dominio di origine) di chiamare le API in un altro dominio.</span><span class="sxs-lookup"><span data-stu-id="22259-125">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="22259-126">Vedere la [specifica CORS](https://www.w3.org/TR/cors/) per informazioni dettagliate su CORS.</span><span class="sxs-lookup"><span data-stu-id="22259-126">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="22259-127">**Abilitazione di CORS per l'API del repository**</span><span class="sxs-lookup"><span data-stu-id="22259-127">**Enabling CORS for Repository API**</span></span>
  
 <span data-ttu-id="22259-128">Di seguito è riportato un Estratto di Web. config API del repository che mostra due domini elencati nelle impostazioni delle applicazioni di corsTrustedOrigin.</span><span class="sxs-lookup"><span data-stu-id="22259-128">The following is an excerpt of Repository API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="22259-129">Tutte le richieste effettuate dagli script caricati da questi server sono attendibili dall'API del repository.</span><span class="sxs-lookup"><span data-stu-id="22259-129">All requests made by the scripts loaded from these servers are trusted by Repository API.</span></span>
  
<span data-ttu-id="22259-130">Ricordarsi di includere l'esatto protocollo, il nome host e la porta (se presenti).</span><span class="sxs-lookup"><span data-stu-id="22259-130">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="22259-131">Non inserire alcun carattere barra (/) alla fine.</span><span class="sxs-lookup"><span data-stu-id="22259-131">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="22259-132">È possibile specificare più voci separandoli con una virgola.</span><span class="sxs-lookup"><span data-stu-id="22259-132">Multiple entries can be specified by separating with commas.</span></span>
  
```
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```



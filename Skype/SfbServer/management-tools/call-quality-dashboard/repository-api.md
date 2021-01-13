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
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>API del repository per Call Quality Dashboard (CQD) in Skype for Business Server
 
**Riepilogo:** Informazioni sull'API del repository per il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server.
  
L'API del repository fornisce l'accesso programmatico per il dashboard sulla qualità delle chiamate per Skype for Business Server.
  
## <a name="repository-api-for-call-quality-dashboard"></a>API del repository per il dashboard per la qualità delle chiamate

L'API del repository offre un'interfaccia di accesso ai dati per il database repository. L'archivio consente di organizzare il contenuto in una struttura ad albero o grafico in modo che gli utenti possano raggrupparli in modo da avere un senso per gli utenti. L'archivio supporta due tipi generali di utenti: l'utente di sistema, che è un utente incorporato che rappresenta l'archivio, e gli utenti regolari che rappresentano gli utenti autorizzati del repository.
  
API del repository è costituito da tre servizi generali: 
  
- [Servizio utente per CQD](user-service.md) -per l'accesso agli utenti.
    
- [Servizio elementi per il dashboard per la qualità delle chiamate (CQD)](item-service.md) -per accedere agli elementi e ai contenuti archiviati negli elementi.
    
- [User Settings Service for Call Quality Dashboard (CQD)](user-settings-service.md) -per accedere alle impostazioni utente.
    
Call Quality dashboard utilizza l'API del repository per gestire le informazioni seguenti: 
  
- Rappresentazione **utente** degli utenti che dispongono dell'accesso all'archivio.
    
- **Report** : contiene un elenco di query, memorizzate come contenuto negli elementi del repository.
    
- **Query** -utilizzata per recuperare i dati dall'API dei dati, archiviati come contenuto negli elementi del repository.
    
- **Impostazione utente** -descrive un comportamento facoltativo dell'applicazione per l'utente.
    
  **Supporto per la condivisione delle risorse tra origini (CORS) per l'API del repository**
  
L'API del repository supporta la condivisione delle risorse tra origini (CORS). CORS è una funzionalità HTTP che consente a un'applicazione Web in esecuzione in un dominio di accedere alle risorse in un altro dominio. I Web browser implementano una restrizione di sicurezza nota come criterio di origine dello stesso [criterio](https://www.w3.org/Security/wiki/Same_Origin_Policy) di origine che impedisce la chiamata delle API in un dominio diverso da una pagina Web. CORS fornisce un modo sicuro per consentire a un dominio (il dominio di origine) di chiamare API in un altro dominio. Per informazioni dettagliate su CORS, vedere la [specifica di CORS](https://www.w3.org/TR/cors/) .
  
 **Abilitazione di CORS per l'API del repository**
  
 Di seguito è riportato un estratto dell'API del repository web.config, che mostra due domini elencati nelle impostazioni delle applicazioni di corsTrustedOrigin. Tutte le richieste eseguite dagli script caricati da questi server sono considerate attendibili dall'API del repository.
  
Tenere presente che il protocollo, il nome host e la porta (se presenti) sono esatte. Non inserire alcun carattere barra (/) alla fine. È possibile specificare più voci separando le virgole.
  
```xml
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```



---
title: API del repository per Call Quality Dashboard (Call Quality Dashboard) in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: "Riepilogo: informazioni sull'API del repository per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 723b7a9340737e3f1cec47112b33ff1175597cd0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186872"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>API del repository per Call Quality Dashboard (Call Quality Dashboard) in Skype for Business Server
 
**Riepilogo:** Informazioni sull'API del repository per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server.
  
L'API del repository offre accesso a livello di codice per Call Quality dashboard per Skype for Business Server.
  
## <a name="repository-api-for-call-quality-dashboard"></a>API del repository per dashboard qualità chiamata

API del repository offre un'interfaccia di accesso ai dati per il database repository. Il repository consente di organizzare il contenuto in una struttura ad albero o a grafico in modo che gli utenti possano raggrupparli in modo che abbiano senso per gli utenti. Il repository supporta due tipi generali di utenti: l'utente di sistema, che è un utente predefinito che rappresenta il repository e gli utenti regolari che rappresentano gli utenti autorizzati del repository.
  
L'API del repository è costituita da tre servizi generali: 
  
- [Servizio utente per Call Quality dashboard](user-service.md) -per l'accesso agli utenti.
    
- [Item Service per Call Quality Dashboard (Call Quality Dashboard)](item-service.md) -per l'accesso agli elementi e il contenuto archiviato in elementi.
    
- [Servizio impostazioni utente per Call Quality Dashboard (Call Quality Dashboard)](user-settings-service.md) -per l'accesso alle impostazioni utente.
    
Call Quality dashboard usa l'API del repository per gestire le informazioni seguenti: 
  
- Rappresentazione **utente** degli utenti che hanno accesso al repository.
    
- **Report** : contiene un elenco di query, archiviate come contenuto negli elementi del repository.
    
- **Query** : consente di recuperare dati dall'API dati, archiviati come contenuto in elementi del repository.
    
- **Impostazione utente** : descrive un comportamento facoltativo dell'applicazione per l'utente.
    
  **Supporto CORS (Cross-Origin Resource Sharing) per l'API del repository**
  
L'API del repository supporta la condivisione delle risorse CORS (Cross-Origin Resource Sharing). CORS è una caratteristica HTTP che consente a un'applicazione Web in uso in un dominio di accedere alle risorse in un altro dominio. I Web browser implementano una restrizione [](https://www.w3.org/Security/wiki/Same_Origin_Policy) di sicurezza nota come criterio di origine della stessa origine che impedisce la chiamata delle API in un dominio diverso da una pagina Web. CORS offre un modo sicuro per consentire a un dominio (il dominio di origine) di chiamare le API in un altro dominio. Vedere la [specifica CORS](https://www.w3.org/TR/cors/) per informazioni dettagliate su CORS.
  
 **Abilitazione di CORS per l'API del repository**
  
 Di seguito è riportato un Estratto di Web. config API del repository che mostra due domini elencati nelle impostazioni delle applicazioni di corsTrustedOrigin. Tutte le richieste effettuate dagli script caricati da questi server sono attendibili dall'API del repository.
  
Ricordarsi di includere l'esatto protocollo, il nome host e la porta (se presenti). Non inserire alcun carattere barra (/) alla fine. È possibile specificare più voci separandoli con una virgola.
  
```
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```



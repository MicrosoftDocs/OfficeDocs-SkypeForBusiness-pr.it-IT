---
title: Framework di sicurezza per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: In questa sezione viene fornita una panoramica degli elementi fondamentali che formano il framework di sicurezza per Skype for Business Server. La comprensione del modo in cui questi elementi funzionano insieme è essenziale per prendere decisioni informate sulla protezione della distribuzione Skype for Business Server particolare.
ms.openlocfilehash: a0f6513f86d7416f546c6a744fc1b40df7c7137a18dae5d76fcf18166a4f2eb1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54337714"
---
# <a name="security-framework-for-skype-for-business-server"></a>Framework di sicurezza per Skype for Business Server
 
In questa sezione viene fornita una panoramica degli elementi fondamentali che formano il framework di sicurezza per Skype for Business Server. La comprensione del modo in cui questi elementi funzionano insieme è essenziale per prendere decisioni informate sulla protezione della distribuzione Skype for Business Server particolare.
  
Gli elementi sono i seguenti:
  
- Servizi di dominio Active Directory (AD-DS) fornisce un singolo archivio back-end attendibile per gli account utente e le risorse di rete.
    
- Role-Based controllo di accesso (RBAC) consente di delegare le attività amministrative mantenendo standard elevati per la sicurezza.
    
- L'infrastruttura a chiave pubblica (PKI) utilizza i certificati emessi da autorità di certificazione attendibili (CA) per autenticare i server e garantire l'integrità dei dati.
    
- Transport Layer Security (TLS), HTTPS su SSL (HTTPS) e Mutual TLS (MTLS) consentono l'autenticazione degli endpoint e la crittografia della messaggistica istantanea. I flussi di condivisione di audio, video e applicazioni punto a punto sono crittografati mediante Secure Real-Time Transport Protocol (SRTP).
    
- Protocolli standard di settore per l'autenticazione degli utenti, laddove possibile.
    
- Windows PowerShell fornisce funzionalità di sicurezza abilitate per impostazione predefinita, in modo che gli utenti non possano eseguire facilmente o involontariamente script.
    
Questi elementi di sicurezza fondamentali lavorano insieme per definire utenti, server, connessioni e operazioni attendibili per garantire una base sicura per Skype for Business Server.
  
## <a name="in-this-section"></a>Contenuto della sezione

Negli argomenti di questa sezione viene descritto il funzionamento di ognuno di questi elementi fondamentali per migliorare la sicurezza dell'Skype for Business Server aziendale.
  
- [Servizi di dominio Active Directory per Skype for Business Server](active-directory-domain-services.md)
    
- [Controllo dell'accesso basato sui ruoli (RBAC) per Skype for Business Server](role-based-access-control-rbac.md)
    
- [Infrastruttura a chiave pubblica per Skype for Business Server](public-key-infrastructure-for-skype.md)
    
- [TLS e MTLS per Skype for Business Server](tls-and-mtls.md)
    
- [Crittografia per Skype for Business Server](encryption.md)
    
- [Autenticazione utente e client per Skype for Business Server](user-and-client-authentication.md)
    
- [Windows PowerShell e Skype for Business Server di gestione](management-tools.md)
    


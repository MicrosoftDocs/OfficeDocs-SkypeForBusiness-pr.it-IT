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
description: In questa sezione viene fornita una panoramica degli elementi fondamentali che formano il Framework di sicurezza per Skype for Business Server. Comprendere il modo in cui questi elementi interagiscono è essenziale per prendere decisioni informate sulla protezione della distribuzione di Skype for Business Server in particolare.
ms.openlocfilehash: 94d2ffac30e029ab6631557a69d6da3ec108657f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832096"
---
# <a name="security-framework-for-skype-for-business-server"></a>Framework di sicurezza per Skype for Business Server
 
In questa sezione viene fornita una panoramica degli elementi fondamentali che formano il Framework di sicurezza per Skype for Business Server. Comprendere il modo in cui questi elementi interagiscono è essenziale per prendere decisioni informate sulla protezione della distribuzione di Skype for Business Server in particolare.
  
Gli elementi sono i seguenti:
  
- Servizi di dominio Active Directory (AD-DS) fornisce un singolo archivio back-end attendibile per gli account utente e le risorse di rete.
    
- Role-Based controllo di accesso (RBAC) consente di delegare le attività amministrative mantenendo standard elevati per la sicurezza.
    
- L'infrastruttura a chiave pubblica (PKI) utilizza i certificati emessi da autorità di certificazione (CAs) attendibili per autenticare i server e garantire l'integrità dei dati.
    
- Transport Layer Security (TLS), HTTPS su SSL (HTTPS) e Mutual TLS (MTLS) consentono l'autenticazione degli endpoint e la crittografia della messaggistica istantanea. I flussi di condivisione di audio, video e applicazioni punto a punto sono crittografati mediante Secure Real-Time Transport Protocol (SRTP).
    
- Protocolli standard di settore per l'autenticazione degli utenti, laddove possibile.
    
- Windows PowerShell fornisce funzionalità di sicurezza abilitate per impostazione predefinita, in modo che gli utenti non possano eseguire facilmente o involontariamente script.
    
Questi elementi di sicurezza fondamentali interagiscono per definire utenti, server, connessioni e operazioni attendibili per garantire una base sicura per Skype for Business Server.
  
## <a name="in-this-section"></a>Contenuto della sezione

Negli argomenti di questa sezione viene descritto il funzionamento di ognuno di questi elementi fondamentali per migliorare la sicurezza dell'infrastruttura di Skype for Business Server.
  
- [Servizi di dominio Active Directory per Skype for Business Server](active-directory-domain-services.md)
    
- [Controllo dell'accesso basato sui ruoli (RBAC) per Skype for Business Server](role-based-access-control-rbac.md)
    
- [Infrastruttura a chiave pubblica per Skype for Business Server](public-key-infrastructure-for-skype.md)
    
- [TLS e MTLS per Skype for Business Server](tls-and-mtls.md)
    
- [Crittografia per Skype for Business Server](encryption.md)
    
- [Autenticazione utente e client per Skype for Business Server](user-and-client-authentication.md)
    
- [Strumenti di gestione di Windows PowerShell e Skype for Business Server](management-tools.md)
    


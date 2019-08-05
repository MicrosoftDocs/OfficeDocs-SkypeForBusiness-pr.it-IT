---
title: Framework di sicurezza per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: Questa sezione offre una panoramica degli elementi fondamentali che costituiscono il Framework di sicurezza per Skype for Business Server. È essenziale comprendere il modo in cui questi elementi collaborano per prendere decisioni informate su come proteggere la distribuzione di Skype for Business Server in particolare.
ms.openlocfilehash: 8b82b09a8220139abe62ac4503ad8a7eddc28e99
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194883"
---
# <a name="security-framework-for-skype-for-business-server"></a>Framework di sicurezza per Skype for Business Server
 
Questa sezione offre una panoramica degli elementi fondamentali che costituiscono il Framework di sicurezza per Skype for Business Server. È essenziale comprendere il modo in cui questi elementi collaborano per prendere decisioni informate su come proteggere la distribuzione di Skype for Business Server in particolare.
  
Questi elementi sono i seguenti:
  
- Active Directory Domain Services (AD DS) offre un unico repository back-end attendibile per gli account utente e le risorse di rete.
    
- Controllo di accesso basato sui ruoli (RBAC) consente di delegare le attività amministrative mantenendo standard elevati per la sicurezza.
    
- Infrastruttura a chiave pubblica (PKI) USA i certificati emessi da autorità di certificazione (CAs) attendibili per autenticare i server e garantire l'integrità dei dati.
    
- Transport Layer Security (TLS), HTTPS su SSL (HTTPS) e TLS reciproche (MTLS) abilitano l'autenticazione dell'endpoint e la crittografia della messaggistica istantanea (IM). I flussi audio, video e di condivisione delle applicazioni Point-to-Point vengono crittografati usando il protocollo SRTP (Secure Real-Time Transport Protocol).
    
- Protocolli standard del settore per l'autenticazione dell'utente, ove possibile.
    
- Windows PowerShell offre funzionalità di sicurezza abilitate per impostazione predefinita in modo che gli utenti non possano eseguire facilmente o inconsapevolmente gli script.
    
Questi elementi di sicurezza fondamentali collaborano per definire utenti, server, connessioni e operazioni attendibili per garantire un fondamento sicuro per Skype for Business Server.
  
## <a name="in-this-section"></a>In questa sezione

Gli argomenti di questa sezione descrivono il funzionamento di ognuno di questi elementi fondamentali per migliorare la sicurezza dell'infrastruttura di Skype for Business Server.
  
- [Servizi di dominio Active Directory per Skype for Business Server](active-directory-domain-services.md)
    
- [Controllo di accesso basato sui ruoli (RBAC) per Skype for Business Server](role-based-access-control-rbac.md)
    
- [Infrastruttura a chiave pubblica per Skype for Business Server](public-key-infrastructure-for-skype.md)
    
- [TLS e MTLS per Skype for Business Server](tls-and-mtls.md)
    
- [Crittografia per Skype for Business Server](encryption.md)
    
- [Autenticazione utente e client per Skype for Business Server](user-and-client-authentication.md)
    
- [Strumenti di gestione di Windows PowerShell e Skype for Business Server](management-tools.md)
    


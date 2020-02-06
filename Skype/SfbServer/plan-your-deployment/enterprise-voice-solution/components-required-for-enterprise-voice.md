---
title: Componenti necessari per VoIP aziendale in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: Riepilogo dei componenti di VoIP aziendale in Skype for Business Server.
ms.openlocfilehash: a2e32e2301a404afd06038d438fbb62a13235d65
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803106"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a>Componenti necessari per VoIP aziendale in Skype for Business Server
 
Riepilogo dei componenti di VoIP aziendale in Skype for Business Server.
  
Per distribuire VoIP aziendale, nella topologia sono necessari i componenti seguenti. 
  
- Uno o più server di mediazione, che traducono la segnalazione e, in alcune configurazioni, elementi multimediali tra il server Skype for business, l'infrastruttura VoIP aziendale e un gateway PSTN (Public Switched Telephone Network) o un protocollo di avvio della sessione (SIP) trunk. I Mediation Server sono il componente più importante della distribuzione di VoIP aziendale. Per altre informazioni, Vedi [Componente Mediation Server in Skype for Business Server](mediation-server.md).
    
    I server di mediazione possono essere collocati con Front End Server o installati come server autonomi.
    
- Componenti di connettività PSTN, che possono includere trunk SIP o gateway PSTN. Per altre informazioni, Vedi [componenti di connettività PSTN in Skype for Business Server](pstn-connectivity.md).
    
- Edge Server, che consente di usare le funzionalità vocali aziendali dagli utenti quando si trovano al di fuori del firewall dell'organizzazione. 
    
    Il servizio Access Edge offre una segnalazione SIP per le chiamate degli utenti di Skype for business che si trovano al di fuori del firewall dell'organizzazione. L'A/V Edge Services consente l'attraversamento multimediale di NAT e firewall. Un chiamante che usa un client Unified Communications (UC) all'esterno del firewall aziendale si basa sul servizio A/V Edge sia per le singole che per le conferenze telefoniche.
    
    Il servizio di autenticazione A/V è collocato e fornisce servizi di autenticazione per il servizio A/V Edge. Gli utenti esterni che tentano di connettersi al servizio a/V Edge richiedono un token di autenticazione fornito dal servizio di autenticazione A/V prima che le chiamate possano passare.
    
- Inoltre, alcuni componenti Enterprise Voice vengono eseguiti nei server front-end. Per informazioni dettagliate su questi componenti, vedere [componenti VoIP di front end server per Skype for Business Server](front-end-server-voip.md)
    


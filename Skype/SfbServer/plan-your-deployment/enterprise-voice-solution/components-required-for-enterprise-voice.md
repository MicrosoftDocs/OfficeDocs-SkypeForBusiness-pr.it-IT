---
title: Componenti necessari per VoIP aziendale in Skype for Business Server
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: Riepilogo dei componenti VoIP aziendale in Skype for Business Server.
ms.openlocfilehash: 1a7f13cc171af44ecbd0f48706ec12d882e50b33
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825826"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a>Componenti necessari per VoIP aziendale in Skype for Business Server
 
Riepilogo dei componenti VoIP aziendale in Skype for Business Server.
  
Per distribuire VoIP aziendale, nella topologia sono necessari i componenti seguenti. 
  
- Uno o più Mediation Server, che traducono la segnalazione e, in alcune configurazioni, i supporti tra Skype for Business Server interno, l'infrastruttura VoIP aziendale e un gateway PSTN (Public Switched Telephone Network) o un trunk SIP (Session Initiation Protocol). I Mediation Server sono il componente più importante nella distribuzione VoIP aziendale distribuzione. Per ulteriori informazioni, vedere [componente Mediation Server in Skype for Business Server.](mediation-server.md)
    
    I Mediation Server possono essere collocati con Front End Server o installati come server autonomi.
    
- Componenti di connettività PSTN, che possono includere trunk SIP o gateway PSTN. Per ulteriori informazioni, vedere [Componenti di connettività PSTN in Skype for Business Server.](pstn-connectivity.md)
    
- Server perimetrali, che consentono l'utilizzo VoIP aziendale funzionalità da parte degli utenti quando si trova all'esterno del firewall dell'organizzazione. 
    
    Il servizio Access Edge fornisce la segnalazione SIP per le chiamate provenienti da utenti di Skype for Business esterni al firewall dell'organizzazione. Il servizio A/V Edge consente l'attraversamento del contenuto multimediale in NAT e nei firewall. Un chiamante che utilizza un client per le comunicazioni unificate dall'esterno del firewall aziendale utilizza il servizio A/V Edge per singole chiamate e conferenze telefoniche.
    
    Il servizio di autenticazione A/V si trova nella stessa posizione del servizio A/V Edge e offre servizi di autenticazione per questo servizio. Gli utenti esterni che tentano di connettersi al servizio A/V Edge devono disporre di un token di autenticazione fornito dal servizio di autenticazione A/V prima di poter effettuare le proprie chiamate.
    
- Alcuni componenti di VoIP aziendale inoltre vengono eseguiti nei Front End Server. Per informazioni dettagliate su questi componenti, vedere [Componenti VoIP](front-end-server-voip.md) di Front End Server per Skype for Business Server
    


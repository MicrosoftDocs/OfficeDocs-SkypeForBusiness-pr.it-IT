---
title: Componenti necessari per VoIP aziendale in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: Riepilogo dei componenti VoIP aziendale in Skype for Business Server.
ms.openlocfilehash: 0dcc7578ee427fe6bf37f2bbde48c09ff32d62e7
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60855423"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a>Componenti necessari per VoIP aziendale in Skype for Business Server
 
Riepilogo dei componenti VoIP aziendale in Skype for Business Server.
  
Per distribuire VoIP aziendale, nella topologia sono necessari i componenti seguenti. 
  
- Uno o più Mediation Server, che traducono la segnalazione e, in alcune configurazioni, i supporti tra il Skype for Business Server interno, l'infrastruttura VoIP aziendale e un gateway PSTN (Public Switched Telephone Network) o un trunk SIP (Session Initiation Protocol). I Mediation Server sono il componente più importante nella distribuzione VoIP aziendale distribuzione. Per ulteriori informazioni, vedere [Componente Mediation Server in Skype for Business Server](mediation-server.md).
    
    I Mediation Server possono essere collocati con Front End Server o installati come server autonomi.
    
- Componenti di connettività PSTN, che possono includere trunk SIP o gateway PSTN. Per ulteriori informazioni, vedere [Componenti di connettività PSTN in Skype for Business Server](pstn-connectivity.md).
    
- Server perimetrali, che consente l'VoIP aziendale degli utenti quando si trova all'esterno del firewall dell'organizzazione. 
    
    Il servizio Access Edge fornisce la segnalazione SIP per le chiamate Skype for Business utenti esterni al firewall dell'organizzazione. Il servizio A/V Edge consente l'attraversamento del contenuto multimediale in NAT e nei firewall. Un chiamante che utilizza un client per le comunicazioni unificate dall'esterno del firewall aziendale utilizza il servizio A/V Edge per singole chiamate e conferenze telefoniche.
    
    Il servizio di autenticazione A/V si trova nella stessa posizione del servizio A/V Edge e offre servizi di autenticazione per questo servizio. Gli utenti esterni che tentano di connettersi al servizio A/V Edge devono disporre di un token di autenticazione fornito dal servizio di autenticazione A/V prima di poter effettuare le proprie chiamate.
    
- Inoltre, alcuni componenti VoIP aziendale vengono eseguiti nei Front End Server. Per informazioni dettagliate su questi componenti, vedere [Front End Server VoIP components for Skype for Business Server](front-end-server-voip.md)
    


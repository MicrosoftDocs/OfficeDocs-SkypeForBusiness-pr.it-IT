---
title: Componenti di connettività PSTN in Skype for Business Server
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
ms.assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
description: Informazioni sul trunking SIP e sui gateway PSTN per VoIP aziendale in Skype for Business Server.
ms.openlocfilehash: 6261b95906699777e62c025889d23e03d381f09d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813536"
---
# <a name="pstn-connectivity-components-in-skype-for-business-server"></a>Componenti di connettività PSTN in Skype for Business Server
 
Informazioni sul trunking SIP e sui gateway PSTN per VoIP aziendale in Skype for Business Server.
  
Una soluzione VoIP di livello aziendale deve essere in grado di garantire le chiamate da e verso la rete PSTN (Public Switched Telephone Network) senza alcun decadimento della qualità del servizio (QoS). Gli utenti non devono inoltre preoccuparsi della tecnologia sottostante quando effettuano e ricevono chiamate. Dal punto di vista dell'utente, una chiamata tra l'infrastruttura VoIP aziendale e la rete PSTN deve risultare del tutto analoga a qualsiasi altra sessione SIP.
  
Per le connessioni PSTN, è possibile distribuire un trunk SIP o un gateway PSTN (con un sistema PBX, noto anche come collegamento SIP diretto o senza PBX).
  
## <a name="sip-trunking"></a>Trunking SIP

Come alternativa all'utilizzo di gateway PSTN, è possibile connettere la soluzione VoIP aziendale alla rete PSTN tramite trunking SIP. Il trunking SIP consente gli scenari seguenti:
  
- Un utente aziendale interno o esterno al firewall aziendale può effettuare una chiamata locale o interurbana tramite un numero compatibile con E.164, che viene terminata nella rete PSTN come servizio del provider di servizi corrispondente.
    
- Qualsiasi sottoscrittore PSTN può contattare un utente aziendale interno o esterno al firewall aziendale componendo un numero DID (Direct Inward Dialing) associato a tale utente.
    
Per l'utilizzo di questa soluzione di distribuzione è necessario un provider di servizi di trunking SIP. 
  
## <a name="pstn-gateways"></a>Gateway PSTN

I gateway PSTN sono dispositivi di terze parti che convertono i segnali e i contenuti multimediali tra l'infrastruttura VoIP aziendale e una rete PSTN o un PBX. I gateway PSTN operano con Mediation Server per presentare una chiamata PSTN o PBX a un client VoIP aziendale. Mediation Server presenta inoltre le chiamate da client VoIP aziendale al gateway PSTN per il routing alla rete PSTN o al PBX. Per un elenco di partner che collaborano con Microsoft per fornire dispositivi che funzionano con Skype for Business Server, vedere  [il sito Web Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836). 
  
## <a name="private-branch-exchanges"></a>Centralini

 Se si dispone di un'infrastruttura vocale esistente che utilizza un sistema PBX (Private Branch Exchange), è possibile utilizzare il PBX con VoIP aziendale.
  
Gli scenari di integrazione tra VoIP aziendale e PBX supportati sono i seguenti:
  
- IP-PBX che supporta Media Bypass, con un server Mediation Server.
    
- IP-PBX che richiede un gateway PSTN autonomo.
    
- PBX TDM (Time Division Multiplexing), con un gateway PSTN autonomo.
    
> [!NOTE]
> Media Bypass non funziona con tutti i gateway PSTN, i sistemi IP-PBX e i servizi SBC. Microsoft ha testato una serie di gateway PSTN e SBCs con partner certificati e ha eseguito alcuni test con i sistemi IP-PBX Cisco. Il bypass multimediale è supportato solo con i prodotti e le versioni elencati nel [programma Unified Communications Open Interoperability Program-Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406). 
  
Per informazioni dettagliate sui partner che offrono soluzioni VoIP aziendale, vedere il [sito Web Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836).
  
Per informazioni dettagliate sui partner che offrono soluzioni hardware VoIP aziendale, tra cui i gateway PSTN, vedere il [sito Web Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836).
  


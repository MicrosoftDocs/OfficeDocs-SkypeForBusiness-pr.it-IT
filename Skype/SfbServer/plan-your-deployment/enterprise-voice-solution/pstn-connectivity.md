---
title: Componenti di connettività PSTN in Skype for Business Server
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
ms.assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
description: Informazioni sul trunking SIP e i gateway PSTN per VoIP aziendale in Skype for Business Server.
ms.openlocfilehash: 443f5425beeed5b032968837ac56ce3a26468cdc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802536"
---
# <a name="pstn-connectivity-components-in-skype-for-business-server"></a>Componenti di connettività PSTN in Skype for Business Server
 
Informazioni sul trunking SIP e i gateway PSTN per VoIP aziendale in Skype for Business Server.
  
Una soluzione VoIP di livello aziendale deve prevedere le chiamate da e verso la rete PSTN (Public Switched Telephone Network) senza alcun calo di qualità del servizio (QoS). Inoltre, gli utenti non devono essere consapevoli della tecnologia sottostante quando effettuano e ricevono chiamate. Dal punto di vista dell'utente, una chiamata tra l'infrastruttura VoIP aziendale e la rete PSTN dovrebbe sembrare solo un'altra sessione SIP.
  
Per le connessioni PSTN, è possibile distribuire un trunk SIP o un gateway PSTN (con un PBX, noto anche come collegamento SIP diretto o senza PBX).
  
## <a name="sip-trunking"></a>Trunking SIP

In alternativa all'uso di gateway PSTN, è possibile connettere la soluzione VoIP aziendale alla rete PSTN usando il trunking SIP. Il trunking SIP consente gli scenari seguenti:
  
- Un utente aziendale all'interno o all'esterno del firewall aziendale può effettuare una chiamata locale o interurbana specificata da un numero conforme E. 164 che viene terminato sulla rete PSTN come servizio del provider di servizi corrispondente.
    
- Qualsiasi abbonato PSTN può contattare un utente aziendale all'interno o all'esterno del firewall aziendale componendo un numero DID (Direct inwarded Dialing) associato all'utente aziendale.
    
L'uso di questa soluzione di distribuzione richiede un provider di servizi di trunking SIP. 
  
## <a name="pstn-gateways"></a>Gateway PSTN

I gateway PSTN sono dispositivi di terze parti che traducono segnali e elementi multimediali tra l'infrastruttura VoIP aziendale e una rete PSTN o PBX. I gateway PSTN collaborano con il Mediation Server per presentare una chiamata PSTN o PBX a un client VoIP aziendale. Il Mediation Server presenta anche le chiamate dei client VoIP aziendale al gateway PSTN per il routing alla rete PSTN o PBX. Per un elenco dei partner che collaborano con Microsoft per la fornitura di dispositivi compatibili con Skype for Business Server, vedere [il sito Web Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836). 
  
## <a name="private-branch-exchanges"></a>Scambi di branch privati

 Se si ha un'infrastruttura vocale esistente che usa un PBX (Private Branch Exchange), è possibile usare il PBX con VoIP aziendale.
  
Gli scenari di integrazione Voice-PBX supportati di Enterprise sono i seguenti:
  
- IP-PBX che supporta il bypass multimediale, con un Mediation Server.
    
- IP-PBX che richiede un gateway PSTN autonomo.
    
- PBX TDM (Time Division Multiplexing) con un gateway PSTN autonomo.
    
> [!NOTE]
> Il bypass multimediale non si interagisce con ogni gateway PSTN, IP-PBX e SBC. Microsoft ha testato un set di gateway PSTN e SBCs con partner certificati e ha eseguito alcuni test con Cisco IP-PBX. Il bypass multimediale è supportato solo con i prodotti e le versioni elencati in [Unified Communications Open Interoperability Program-Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406). 
  
Per informazioni dettagliate sui partner che offrono soluzioni VoIP aziendale, vedere il [sito Web Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836).
  
Per informazioni dettagliate sui partner che offrono soluzioni hardware VoIP aziendale, inclusi i gateway PSTN, vedere il [sito Web Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836).
  


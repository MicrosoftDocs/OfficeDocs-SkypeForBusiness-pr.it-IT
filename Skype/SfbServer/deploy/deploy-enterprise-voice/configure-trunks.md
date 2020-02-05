---
title: Configurare Trunks in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 'Riepilogo: informazioni su come configurare un trunk tra un Mediation Server e i peer per VoIP aziendale in Skype for Business Server.'
ms.openlocfilehash: eb2cf3042fe4e0d1a7c840fb31c583b18289bb7b
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768069"
---
# <a name="configure-trunks-in-skype-for-business-server"></a>Configurare Trunks in Skype for Business Server
 
**Riepilogo:** Informazioni su come configurare un trunk tra un Mediation Server e i peer per VoIP aziendale in Skype for Business Server.
  
Come parte della distribuzione VoIP aziendale, è possibile configurare un trunk tra un Mediation Server e uno o più dei peer seguenti per consentire la connettività PSTN (Public Switched Telephone Network) per i client e i dispositivi VoIP aziendali nell'organizzazione:
  
- Connessione trunk SIP a un provider di servizi di telefonia Internet (ITSP)
    
- Gateway PSTN
    
- PBX (Private Branch Exchange)
    
Per altre informazioni, Vedi [pianificare la connettività PSTN in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).
  
La funzionalità di Skype for Business Server supporta più associazioni tra gateway e Mediation Server. Queste associazioni vengono effettuate definendo un trunk, che è un'associazione logica tra un pool di Mediation Server e un gateway PSTN (Public Switched Telephone Network), Session Border Controller (SBC) o IP-PBX. Usare il generatore di topologie per associare i gateway ai server di mediazione (ovvero Trunks).
  
- Per assegnare o rimuovere un trunk in Skype for Business Server, è necessario prima di tutto definire un trunk in Generatore di topologie. Un trunk è costituito dall'associazione seguente: Mediation Server Fully Qualified Domain Name (FQDN), la porta di ascolto di Mediation Server, il nome di dominio completo del gateway e la porta di ascolto del gateway.
    
- Per configurare più Trunks, è possibile creare più associazioni tra lo stesso gateway e il Mediation Server. In questo modo è disponibile un'ulteriore resilienza dell'infrastruttura VoIP aziendale, che risulta particolarmente utile negli scenari di interoperabilità del PBX (Private Branch Exchange). 
    
Quando viene definito un trunk, deve essere associato a una route. Per associare un trunk a una route, è possibile definire un nome semplice per il trunk in Generatore di topologia. Questo nome semplice viene usato come nome del trunk nel pannello di controllo di Skype for Business Server, dove Trunks può essere associato alle route. Il nome del trunk semplice viene usato come nome del gateway da Skype for Business Server Management Shell. 
  
```powershell
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

L'amministratore deve selezionare un trunk predefinito associato a un Mediation Server. In Generatore di topologie fare clic con il pulsante destro del mouse sul server di mediazione associato e quindi scegliere **Proprietà**. Specificare il gateway predefinito per il Mediation Server. 
  


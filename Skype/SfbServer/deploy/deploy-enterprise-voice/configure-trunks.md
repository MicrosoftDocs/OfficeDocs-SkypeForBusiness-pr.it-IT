---
title: Configurare i trunk in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 'Riepilogo: informazioni su come configurare un trunk tra un Mediation Server e i peer per VoIP aziendale in Skype for Business Server.'
ms.openlocfilehash: 128be18c31802787c173c8d180de80f5ae5a64fb
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60748892"
---
# <a name="configure-trunks-in-skype-for-business-server"></a>Configurare i trunk in Skype for Business Server
 
**Riepilogo:** Informazioni su come configurare un trunk tra un Mediation Server e i peer per VoIP aziendale in Skype for Business Server.
  
Nell'ambito della distribuzione di VoIP aziendale, è possibile configurare un trunk tra un Mediation Server e uno o più dei peer seguenti per fornire connettività PSTN (Public Switched Telephone Network) per i client e i dispositivi VoIP aziendale nell'organizzazione:
  
- Connessione con trunk SIP a un provider di servizi di telefonia Internet (ITSP)
    
- Gateway PSTN
    
- Centralino (PBX)
    
Per ulteriori informazioni, vedere [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).
  
Skype for Business Server supporta più associazioni tra gateway e Mediation Server. Queste associazioni vengono effettuate definendo un trunk, ovvero un'associazione logica tra un pool Mediation Server e un gateway PSTN (Public Switched Telephone Network), session border controller (SBC) o IP-PBX. Utilizzare generatore di topologie per associare gateway a Mediation Server, ovvero trunk.
  
- Per assegnare o rimuovere un trunk in Skype for Business Server, è innanzitutto necessario definire un trunk in Generatore di topologie. Un trunk è costituito dalla seguente associazione: nome di dominio completo (FQDN) di Mediation Server, porta di attesa mediation server, FQDN gateway e porta di attesa del gateway.
    
- Per configurare più trunk, è possibile creare più associazioni tra lo stesso gateway e il Mediation Server. In questo modo si garantisce una maggiore resilienza all'infrastruttura VoIP aziendale, particolarmente utile in scenari di interoperabilità PBX (Private Branch Exchange). 
    
Dopo essere stato definito, il trunk deve essere associato a una route. Per associare un trunk a una route, è necessario definire un nome semplice per il trunk in Generatore di topologie. Questo nome semplice viene utilizzato come nome trunk nel Pannello Skype for Business Server, dove i trunk possono essere associati alle route. Il nome del trunk semplice viene utilizzato come nome del gateway da Skype for Business Server Management Shell. 
  
```powershell
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

L'amministratore deve selezionare un trunk predefinito associato a un Mediation Server. In Generatore di topologie fare clic con il pulsante destro del mouse sul Mediation Server associato e quindi scegliere **Proprietà**. Specificare il gateway predefinito per il Mediation Server. 
  


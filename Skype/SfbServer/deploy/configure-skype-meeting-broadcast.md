---
title: Configurare la distribuzione locale per Skype meeting broadcast
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: 'Riepilogo: informazioni sui passaggi che è necessario eseguire per configurare Skype meeting broadcast per la distribuzione ibrida di Skype for Business Server locale.'
ms.openlocfilehash: bd87c64dd1e54c8092186a3e233557ebd11eec77
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234584"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>Configurare la distribuzione locale per Skype meeting broadcast
 
**Riepilogo:** Informazioni sui passaggi che è necessario eseguire per configurare Skype meeting broadcast per la distribuzione ibrida di Skype for Business Server locale.
  
Skype meeting broadcast è un servizio online che fa parte di Office 365. Se si usa Skype for Business Server locale e si vuole usare Skype meeting broadcast nell'ambiente, è necessario seguire la procedura di configurazione in questo argomento. Prima di iniziare, l'ambiente deve essere configurato per l'ibrido con Skype for business online. Per altre informazioni, Vedi [pianificare la connettività ibrida tra Skype for Business Server e Skype for business online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) e [distribuire la connettività ibrida tra Skype for Business Server e Skype for business online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>Configurare l'ambiente ibrido per Skype meeting broadcast

Per preparare l'ambiente per Skype meeting broadcast è necessario eseguire le operazioni seguenti:
  
- Configurare la Federazione con le risorse di Skype for business online
    
- Configurare i domini federati SIP
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>Configurare la Federazione con le risorse di Skype for business online

Per abilitare la Federazione con le risorse di Skype for business online, è necessario configurare l'accesso esterno per un provider federato SIP. Per eseguire questa operazione, usare il pannello di controllo di Skype for Business Server seguire questa procedura:
  
1. Avviare il pannello di controllo di Skype for Business Server e selezionare **accesso esterno** a sinistra.
    
2. Selezionare **provider federati SIP** e fare clic su **nuovo**.
    
3. Configurare il nuovo provider con le impostazioni seguenti:
    
|||
|:-----|:-----|
|**Abilitare le comunicazioni con questo provider:** <br/> |Selezionato  <br/> |
|**Nome provider:** <br/> |LyncOnlineResources  <br/> |
|**Access Edge Services (FQDN):** <br/> |sipfed.resources.lync.com  <br/> |
|**Livello di verifica predefinito:** <br/> |Consentire agli utenti di comunicare con tutti tramite questo provider.  <br/> |
   
Puoi anche abilitare la Federazione con le risorse di Skype for business online eseguendo il cmdlet seguente in Skype for Business Server Management Shell:
  
```
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>Configurare i domini federati SIP

È quindi necessario aggiungere domini federati SIP all'elenco di domini consentiti. Ripetere questi passaggi per ogni dominio elencato, creando 4 nuovi domini federati SIP. Questi domini includono sono per i centri dati regionali usati in Skype for business online.
  
1. Avviare il pannello di controllo di Skype for Business Server e selezionare **accesso esterno** a sinistra.
    
2. Selezionare **domini federati SIP** e fare clic su **nuovo**.
    
3. Per il **nome di dominio (o FQDN):** immettere il dominio, ripetendo questa procedura per ognuno dei domini seguenti:
    
   - noammeetings.lync.com
    
   - emeameetings.lync.com
    
   - apacmeetings.lync.com
    
   - resources.lync.com
    
È anche possibile configurare l'accesso esterno per i domini federati SIP eseguendo i cmdlet seguenti in Skype for Business Server Management Shell:
  
```
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

Dopo aver completato questi passaggi di configurazione, è possibile iniziare a usare Skype meeting broadcast nella distribuzione. Per altre informazioni su Skype meeting broadcast, vedere [cos'è un Skype meeting broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) e [Guida per gli amministratori di Skype meeting broadcast](https://go.microsoft.com/fwlink/?LinkId=617075).
  


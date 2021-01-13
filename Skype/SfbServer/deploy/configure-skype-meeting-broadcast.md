---
title: Configurare la distribuzione locale per Skype meeting broadcast
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: 'Riepilogo: informazioni sui passaggi che è necessario eseguire per configurare Skype meeting broadcast per la distribuzione ibrida di Skype for Business Server locale.'
ms.openlocfilehash: c016d60b416c7b6d935b15718f3f1a10f439b9ab
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820706"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>Configurare la distribuzione locale per Skype meeting broadcast
 
**Riepilogo:** Informazioni sui passaggi che è necessario eseguire per configurare Skype meeting broadcast per la distribuzione ibrida di Skype for Business Server locale.
  
Skype meeting broadcast è un servizio online che fa parte di Office 365. Se si esegue Skype for Business Server in locale e si desidera utilizzare Skype meeting broadcast nell'ambiente in uso, è necessario seguire la procedura di configurazione descritta in questo argomento. Prima di iniziare, è necessario configurare l'ambiente per l'ibrido con Skype for business online. Per ulteriori informazioni, vedere [pianificare la connettività ibrida tra Skype for Business Server e Skype for business online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) e [distribuire la connettività ibrida tra Skype for Business Server e Skype for business online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>Configurare l'ambiente ibrido per Skype meeting broadcast

Per preparare l'ambiente per Skype meeting broadcast, è necessario eseguire le operazioni seguenti:
  
- Configurare la Federazione con le risorse di Skype for business online
    
- Configurare i domini federati SIP
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>Configurare la Federazione con le risorse di Skype for business online

Per abilitare la Federazione con le risorse di Skype for business online, è necessario configurare l'accesso esterno per un provider federato SIP. Per eseguire questa operazione utilizzando il pannello di controllo di Skype for Business Server, eseguire la procedura seguente:
  
1. Avviare il pannello di controllo di Skype for Business Server e selezionare **accesso esterno** a sinistra.
    
2. Selezionare **provider federati SIP** e fare clic su **nuovo**.
    
3. Configurare il nuovo provider con le impostazioni seguenti:
    
|||
|:-----|:-----|
|**Abilitare le comunicazioni con questo provider:** <br/> |Opzione selezionata  <br/> |
|**Nome provider:** <br/> |LyncOnlineResources  <br/> |
|**Servizio Access Edge (FQDN):** <br/> |sipfed.resources.lync.com  <br/> |
|**Livello di verifica predefinito** <br/> |Consenti agli utenti di comunicare con tutti quelli che utilizzano questo provider.  <br/> |
   
È inoltre possibile abilitare la Federazione con le risorse di Skype for business online eseguendo il cmdlet seguente in Skype for Business Server Management Shell:
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>Configurare i domini federati SIP

Successivamente, è necessario aggiungere i domini federati SIP all'elenco dei domini consentiti. Ripetere questi passaggi per ognuno dei domini elencati, creando 4 nuovi domini federati SIP. Questi domini includono sono per i data center regionali usati in Skype for business online.
  
1. Avviare il pannello di controllo di Skype for Business Server e selezionare **accesso esterno** a sinistra.
    
2. Selezionare **domini federati SIP** e fare clic su **nuovo**.
    
3. Per il **nome di dominio (o FQDN):** immettere il dominio, ripetendo questa procedura per ognuno dei domini seguenti:
    
   - noammeetings.lync.com
    
   - emeameetings.lync.com
    
   - apacmeetings.lync.com
    
   - resources.lync.com
    
È inoltre possibile configurare l'accesso esterno per i domini federati SIP eseguendo i cmdlet seguenti in Skype for Business Server Management Shell:
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

Dopo aver completato questi passaggi di configurazione, è possibile iniziare a usare Skype meeting broadcast nella distribuzione. Per ulteriori informazioni su Skype meeting broadcast, vedere [che cos'è un Skype meeting broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) e [Skype meeting broadcast admin guide](https://go.microsoft.com/fwlink/?LinkId=617075).
  


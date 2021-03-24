---
title: Configurare la distribuzione locale per Skype Meeting Broadcast
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
description: 'Riepilogo: informazioni sui passaggi da eseguire per configurare Skype Meeting Broadcast per la distribuzione ibrida di Skype for Business Server locale.'
ms.openlocfilehash: b70272ee90146bdac87264acf0c7673b8def05c2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103692"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>Configurare la distribuzione locale per Skype Meeting Broadcast
 
**Riepilogo:** Informazioni sui passaggi da eseguire per configurare Skype Meeting Broadcast per la distribuzione ibrida di Skype for Business Server locale.
  
Skype Meeting Broadcast è un servizio online che fa parte di Office 365. Se si esegue Skype for Business Server in locale e si desidera utilizzare Skype Meeting Broadcast nel proprio ambiente, è necessario seguire i passaggi di configurazione descritti in questo argomento. Prima di iniziare, l'ambiente deve essere configurato per la distribuzione ibrida con Skype for Business online. Per ulteriori informazioni, vedere Pianificare la connettività ibrida tra [Skype for Business Server](../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) e Skype for Business online e Distribuire la connettività ibrida tra Skype for Business Server e Skype for Business [online.](../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>Configurare l'ambiente ibrido per Skype Meeting Broadcast

Dovrai eseguire le operazioni seguenti per preparare l'ambiente per Skype Meeting Broadcast:
  
- Configurare la federazione con le risorse di Skype for Business Online
    
- Configurare i domini federati SIP
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>Configurare la federazione con le risorse di Skype for Business Online

Per abilitare la federazione con le risorse di Skype for Business Online, è necessario configurare l'accesso esterno per un provider federato SIP. Per eseguire questa operazione utilizzando il Pannello di controllo di Skype for Business Server, attenersi alla seguente procedura:
  
1. Avviare il Pannello di controllo di Skype for Business Server e selezionare **Accesso esterno** a sinistra.
    
2. Selezionare **Provider federati SIP e** fare clic su **Nuovo.**
    
3. Configurare il nuovo provider con le impostazioni seguenti:
    
|||
|:-----|:-----|
|**Abilita comunicazioni con questo provider:** <br/> |Opzione selezionata  <br/> |
|**Nome provider:** <br/> |LyncOnlineResources  <br/> |
|**Servizio Access Edge (FQDN):** <br/> |sipfed.resources.lync.com  <br/> |
|**Livello di verifica predefinito** <br/> |Consenti agli utenti di comunicare con tutti gli utenti che usano questo provider.  <br/> |
   
È inoltre possibile abilitare la federazione con le risorse di Skype for Business Online eseguendo il cmdlet seguente in Skype for Business Server Management Shell:
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>Configurare i domini federati SIP

Successivamente, è necessario aggiungere domini federati SIP all'elenco dei domini consentiti. Ripetere questi passaggi per ognuno dei domini elencati, creando 4 nuovi domini federati SIP. Questi domini includono i data center regionali usati in Skype for Business online.
  
1. Avviare il Pannello di controllo di Skype for Business Server e selezionare **Accesso esterno** a sinistra.
    
2. Selezionare **Domini federati SIP e** fare clic su **Nuovo.**
    
3. Per **nome di dominio (o FQDN):** immettere il dominio, ripetendo questa procedura per ognuno dei domini seguenti:
    
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

Dopo aver completato questi passaggi di configurazione, puoi iniziare a usare Skype Meeting Broadcast nella distribuzione. Per altre informazioni su Skype Meeting Broadcast, vedi [Che cos'è Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) e Guida all'amministratore [di Skype Meeting Broadcast.](../../SfbOnline/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md)

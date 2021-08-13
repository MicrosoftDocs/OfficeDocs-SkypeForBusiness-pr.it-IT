---
title: Configurare la distribuzione locale per Riunione Skype Broadcast
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
description: 'Riepilogo: informazioni sui passaggi da eseguire per configurare Riunione Skype Broadcast per la distribuzione ibrida Skype for Business Server locale.'
ms.openlocfilehash: 6cab2ed4fbb5cb2992b970d5a960bbc0ad2e10af2184588aa6c938e9811d2a50
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54304488"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>Configurare la distribuzione locale per Riunione Skype Broadcast
 
**Riepilogo:** Informazioni sui passaggi da eseguire per configurare Riunione Skype broadcast per la distribuzione ibrida Skype for Business Server locale.
  
Riunione Skype Broadcast è un servizio online che fa parte di Office 365. Se si esegue Skype for Business Server locale e si desidera usare Riunione Skype Broadcast nell'ambiente, è necessario seguire i passaggi di configurazione descritti in questo argomento. Prima di iniziare, l'ambiente deve essere configurato per la distribuzione ibrida con Skype for Business Online. Per ulteriori informazioni, vedere [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) e Deploy hybrid connectivity between Skype for Business Server and Skype for Business [Online.](../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>Configurare l'ambiente ibrido per Riunione Skype Broadcast

Dovrai eseguire le operazioni seguenti per preparare l'ambiente per Riunione Skype Broadcast:
  
- Configurare la federazione con Skype for Business online
    
- Configurare i domini federati SIP
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>Configurare la federazione con Skype for Business online

Per abilitare la federazione con Skype for Business online, è necessario configurare l'accesso esterno per un provider federato SIP. Per eseguire questa operazione utilizzando il Pannello Skype for Business Server di controllo, attenersi alla seguente procedura:
  
1. Avviare il Skype for Business Server di controllo e selezionare **Accesso esterno** a sinistra.
    
2. Selezionare **Provider federati SIP e** fare clic su **Nuovo.**
    
3. Configurare il nuovo provider con le impostazioni seguenti:
    
|||
|:-----|:-----|
|**Abilita comunicazioni con questo provider:** <br/> |Selezionato  <br/> |
|**Nome provider:** <br/> |LyncOnlineResources  <br/> |
|**Servizio Access Edge (FQDN):** <br/> |sipfed.resources.lync.com  <br/> |
|**Livello di verifica predefinito** <br/> |Consenti agli utenti di comunicare con tutti gli utenti che usano questo provider.  <br/> |
   
È inoltre possibile abilitare la federazione con Skype for Business online eseguendo il cmdlet seguente in Skype for Business Server Management Shell:
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>Configurare i domini federati SIP

Successivamente, è necessario aggiungere domini federati SIP all'elenco dei domini consentiti. Ripetere questi passaggi per ognuno dei domini elencati, creando 4 nuovi domini federati SIP. Questi domini includono i data center regionali utilizzati in Skype for Business Online.
  
1. Avviare il Skype for Business Server di controllo e selezionare **Accesso esterno** a sinistra.
    
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

Dopo aver completato questi passaggi di configurazione, puoi iniziare a usare Riunione Skype Broadcast nella distribuzione. Per ulteriori informazioni su Riunione Skype Broadcast, vedere [What is a Riunione Skype Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) e Riunione Skype Broadcast Admin [Guide](../../SfbOnline/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md).

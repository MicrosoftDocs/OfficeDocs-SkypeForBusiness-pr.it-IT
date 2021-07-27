---
title: Configurare Skype for Business ibrido
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: "Riepilogo: informazioni su come configurare l'interoperabilità tra la distribuzione locale e Teams."
ms.openlocfilehash: 5593dce3bef26e2b3f528618d88e4f87e1996596
ms.sourcegitcommit: 3f1635d1915561798ea764c3e33d7db55f7e49da
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2021
ms.locfileid: "53574131"
---
# <a name="configure-skype-for-business-hybrid"></a>Configurare Skype for Business ibrido

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Per configurare Skype for Business ibrido, è necessario:

- [Configurare il servizio Edge locale per la federazione con Teams](#configure-your-on-premises-edge-service-to-federate-with-teams).
- [Configurare l'ambiente locale in modo che ritieni attendibile Teams e abilitare lo spazio di indirizzi SIP condiviso.](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams)
- [Abilitare lo spazio di indirizzi SIP condiviso nell'Teams organizzazione](#enable-shared-sip-address-space-in-your-organization).

Se si dispone Exchange locale, è possibile configurare OAuth tra l'Exchange locale e gli ambienti online. Per ulteriori informazioni, vedere [Manage server-to-server authentication in Skype for Business Server](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md) e Plan to integrate Skype for Business and [Exchange](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support). 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-teams"></a>Configurare il servizio Edge locale per la federazione con Teams

La federazione consente agli utenti della distribuzione locale di comunicare con Teams utenti dell'organizzazione. Per configurare la federazione, eseguire il cmdlet seguente in Skype for Business Server Management Shell:
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

Se il valore '-EnablePartnerDiscovery' è impostato su $True, Skype for Business Server utilizzerà i record DNS per cercare di individuare i domini partner non elencati nell'elenco AllowedDomains. Se il valore è impostato su $False , Skype for Business Server solo i domini trovati nell'elenco AllowedDomains. Questo parametro è obbligatorio se si utilizza il routing del servizio DNS.

> [!NOTE]
> Per ulteriori informazioni sull'abilitazione della federazione tra gli utenti della distribuzione di Skype for Business locale e gli utenti di un'organizzazione di Microsoft 365, vedere [Configuring federation support for a Microsoft 365 customer in Skype for Business Server](../../SfbServer/manage/federation-and-external-access/federation-support/configuring-federation-support.md).


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams"></a>Configurare l'ambiente locale per abilitare lo spazio di indirizzi SIP condiviso con Teams

È inoltre necessario configurare l'ambiente locale in modo che ritieni attendibile Teams e abilitare lo spazio di indirizzi SIP condiviso. Questa configurazione significa Teams possono ospitare account utente per lo stesso set di domini SIP dell'ambiente locale e i messaggi possono essere instradati tra gli utenti ospitati in locale e online. Configurare un provider di hosting con ProxyFqdn=sipfed.online.lync.com come descritto di seguito.

Verificare innanzitutto se si dispone già di un provider di hosting con ProxyFqdn=sipfed.online.lync.com. Se ne esiste uno, rimuoverlo utilizzando il comando seguente in Skype for Business Server Management Shell:

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

Creare quindi un nuovo provider di hosting utilizzando il cmdlet New-CsHostingProvider seguente: 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a>Abilitare lo spazio di indirizzi SIP condiviso nell'organizzazione
  
Oltre alla modifica apportata nella distribuzione locale, è necessario apportare la modifica corrispondente nell'organizzazione di Teams per l'attivazione dello spazio di indirizzi SIP condiviso con la distribuzione locale.  

Per abilitare lo spazio di indirizzi SIP condiviso nell'organizzazione, stabilire una sessione remota di PowerShell con Teams ed eseguire il cmdlet seguente:
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> L'attributo SharedSipAddressSpace deve rimanere "True" finché il passaggio online non è definitivo e nessun utente rimane in locale. 
  
Per stabilire una sessione remota di PowerShell con Teams, è innanzitutto necessario installare il modulo [Teams PowerShell.](/microsoftteams/teams-powershell-install) Il Teams PowerShell sostituisce il modulo Skype per Busines Online Connector, che è stato ritirato.
  
Dopo aver installato il modulo, è possibile stabilire una sessione remota con i cmdlet seguenti:
   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

Per ulteriori informazioni su come stabilire una sessione remota di PowerShell con Teams e su come usare il modulo powershell di Teams, vedere [Set up your computer for Windows PowerShell](../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  


## <a name="see-also"></a>Vedere anche

[New-CsHostingProvider](/powershell/module/skype/new-cshostingprovider?view=skype-ps)

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
description: "Riepilogo: informazioni su come configurare l'interoperabilità tra la distribuzione locale e Skype for Business online."
ms.openlocfilehash: e2af514ef1a10d652abae7bdd39a923dc52e1c4a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118945"
---
# <a name="configure-skype-for-business-hybrid"></a>Configurare Skype for Business ibrido

Per configurare Skype for Business ibrido, è necessario:

- [Configurare il servizio Edge locale per la federazione con Microsoft 365 o Office 365.](#configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365)
- [Configurare l'ambiente locale per considerare attendibile Microsoft 365 o Office 365](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365)e abilitare lo spazio di indirizzi SIP condiviso.
- [Abilitare lo spazio di indirizzi SIP condiviso nell'organizzazione di Microsoft 365 o Office 365.](#enable-shared-sip-address-space-in-your-organization)

Si noti che se si dispone di Exchange locale, è possibile configurare OAuth tra gli ambienti Exchange locale e Skype for Business online. Per ulteriori informazioni, vedere Gestire l'autenticazione [da server a server in Skype for Business Server](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md) e Pianificare l'integrazione di Skype for Business ed [Exchange.](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365"></a>Configurare il servizio Edge locale per la federazione con Microsoft 365 o Office 365

La federazione consente agli utenti della distribuzione locale di comunicare con gli utenti di Microsoft 365 o Office 365 nell'organizzazione. Per configurare la federazione, eseguire il cmdlet seguente in Skype for Business Server Management Shell:
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

Se il valore '-EnablePartnerDiscovery' è impostato su $True, Skype for Business Server utilizzerà i record DNS per cercare di individuare i domini partner non elencati nell'elenco AllowedDomains. Se il valore è impostato su $False , Skype for Business Server si federatirà solo con i domini trovati nell'elenco AllowedDomains. Questo parametro è obbligatorio se si utilizza il routing del servizio DNS.

> [!NOTE]
> Per ulteriori informazioni sull'abilitazione della federazione tra gli utenti della distribuzione locale di Skype for Business e gli utenti di un'organizzazione Skype for Business Online, vedere [Configuring federation support for a Skype for Business Online customer in Skype for Business Server.](../../SfbServer/manage/federation-and-external-access/federation-support/configuring-federation-support.md)


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365"></a>Configurare l'ambiente locale per abilitare lo spazio di indirizzi SIP condiviso con Microsoft 365 o Office 365

È inoltre necessario configurare l'ambiente locale per considerare attendibile Microsoft 365 o Office 365 e abilitare lo spazio di indirizzi SIP condiviso. Ciò significa che Microsoft 365 o Office 365 può ospitare potenzialmente account utente per lo stesso set di domini SIP dell'ambiente locale e i messaggi possono essere instradati tra gli utenti ospitati in locale e online.  A tale scopo, configurare un provider di hosting con ProxyFqdn=sipfed.online.lync.com come descritto di seguito.

Verificare innanzitutto se si dispone già di un provider di hosting con ProxyFqdn=sipfed.online.lync.com. Se ne esiste uno, rimuoverlo utilizzando il comando seguente:

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

Creare quindi un nuovo provider di hosting, utilizzare il cmdlet New-CsHostingProvider seguente: 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a>Abilitare lo spazio di indirizzi SIP condiviso nell'organizzazione
  
Oltre alla modifica apportata nella distribuzione locale, è necessario apportare la modifica corrispondente nell'organizzazione di Microsoft 365 o Office 365 per rendere abilitato lo spazio di indirizzi SIP condiviso con la distribuzione locale.  

Per abilitare lo spazio di indirizzi SIP condiviso nell'organizzazione, stabilire una sessione remota di PowerShell con Skype for Business online, quindi eseguire il cmdlet seguente:
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> L'attributo SharedSipAddressSpace deve rimanere "True" finché il passaggio online non è definitivo e nessun utente rimane in locale. 
  
Per stabilire una sessione remota di PowerShell con Teams o Skype for Business online, è innanzitutto necessario installare il modulo [PowerShell di Teams.](/microsoftteams/teams-powershell-install)
  
Dopo aver installato il modulo, è possibile stabilire una sessione remota con i cmdlet seguenti:
   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

Per altre informazioni su come stabilire una sessione remota di PowerShell con Skype for Business online e su come usare il modulo Connettore Skype for Business online, vedi Configurare il computer per [Windows PowerShell](../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  


## <a name="see-also"></a>Vedere anche

[New-CsHostingProvider](/powershell/module/skype/new-cshostingprovider?view=skype-ps)
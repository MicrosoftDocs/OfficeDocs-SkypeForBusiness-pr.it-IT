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
description: "Riepilogo: informazioni su come configurare l'interoperabilità tra la distribuzione locale e Skype for business online."
ms.openlocfilehash: ccf140b62cdbad11605c99fe1cb0cc66aa1ee4dd
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780105"
---
# <a name="configure-skype-for-business-hybrid"></a>Configurare Skype for Business ibrido

Per configurare Skype for Business ibrido, è necessario:

- [Configurare il servizio perimetrale locale per la Federazione con Office 365 o un'altra organizzazione](#configure-your-on-premises-edge-service-to-federate-with-office-365-or-another-organization).
- [Configurare l'ambiente locale in modo che consideri attendibile office 365 e che venga abilitato lo spazio degli indirizzi SIP condiviso con office 365](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365).
- [Abilitare lo spazio degli indirizzi SIP condiviso nell'organizzazione di Office 365](#enable-shared-sip-address-space-in-your-office-365-organization).

Si noti che, se si dispone di Exchange locale, è possibile configurare OAuth tra gli ambienti Exchange locale e Skype for business online. Per ulteriori informazioni, vedere [gestire l'autenticazione da server a server in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) e [pianificare l'integrazione di Skype for business ed Exchange](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support). 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-office-365-or-another-organization"></a>Configurare il servizio perimetrale locale per la Federazione con Office 365 o un'altra organizzazione

La federazione consente agli utenti della distribuzione locale di comunicare con gli utenti di Microsoft 365 o Office 365 nell'organizzazione. Per configurare la Federazione, eseguire il seguente cmdlet in Skype for Business Server Management Shell:
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

Se il valore di '-EnablePartnerDiscovery ' è impostato su $True, Skype for Business Server utilizzerà i record DNS per cercare di individuare i domini dei partner non elencati nell'elenco AllowedDomains. Se il valore è impostato su $False, in Skype for Business Server la federazione verrà associata solo ai domini trovati nell'elenco AllowedDomains. Questo parametro è obbligatorio se si utilizza il routing del servizio DNS.

> [!NOTE]
> Per ulteriori informazioni sull'abilitazione della Federazione tra gli utenti della distribuzione di Skype for business locale e gli utenti di un'organizzazione di Skype for business online, vedere [Configuring Federation support for a Skype for business online Customer in Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support).


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365"></a>Configurare l'ambiente locale per abilitare lo spazio degli indirizzi SIP condiviso con Office 365

È inoltre necessario configurare l'ambiente locale per considerare attendibile Office 365 e abilitare lo spazio degli indirizzi SIP condiviso con Office 365. Questo significa che Office 365 può ospitare account utente per lo stesso gruppo di domini SIP dell'ambiente locale e i messaggi possono essere instradati tra gli utenti ospitati in locale e online.  A tale scopo, configurare un provider di hosting con ProxyFqdn = sipfed. online. Lync. com come descritto di seguito.

In primo luogo, controllare se si dispone già di un provider di hosting con ProxyFqdn = sipfed. online. Lync. com. Se esiste, rimuoverlo utilizzando il comando seguente:

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

Creare quindi un nuovo provider di hosting, utilizzare il cmdlet New-CsHostingProvider come indicato di seguito: 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-office-365-organization"></a>Abilitare lo spazio degli indirizzi SIP condiviso nell'organizzazione di Office 365
  
Oltre alla modifica apportata nella distribuzione locale, è necessario apportare le modifiche corrispondenti nell'organizzazione di Office 365 per abilitare lo spazio degli indirizzi SIP condiviso con la distribuzione locale.  

Per abilitare lo spazio degli indirizzi SIP condiviso nell'organizzazione di Office 365, stabilire una sessione remota di PowerShell con Skype for business online e quindi eseguire il cmdlet seguente:
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> L'attributo SharedSipAddressSpace deve rimanere "true" fino a quando lo spostamento in linea è finale e nessuno degli utenti rimane in locale. 
  
Per creare una sessione di PowerShell remota con team o Skype for business online, è necessario prima di tutto installare il modulo del connettore di Skype for business online per Windows PowerShell, che è possibile ottenere [qui](https://go.microsoft.com/fwlink/p/?LinkId=391911).
  
Dopo aver installato il modulo, è possibile stabilire una sessione remota con i cmdlet seguenti:
  
```PowerShell
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

Per ulteriori informazioni su come stabilire una sessione remota di PowerShell con Skype for business online e su come usare il modulo connettore di Skype for business online, vedere [configurare il computer per Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  


## <a name="see-also"></a>Vedere anche

[New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

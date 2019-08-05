---
title: Configurare Skype for business Hybrid
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
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
ms.openlocfilehash: 59f5f752e7a6d9fa4047e736f1a988819525955e
ms.sourcegitcommit: 1336f6c182043016c42660d5f21632d82febb658
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2019
ms.locfileid: "36185525"
---
# <a name="configure-skype-for-business-hybrid"></a>Configurare Skype for business Hybrid

Per configurare Skype for business Hybrid, è necessario:

- [Configurare il servizio di ambiente locale per la Federazione con Office 365](#configure-your-on-premises-edge-service-to-federate-with-office-365).
- [Configurare l'ambiente locale per considerare attendibile office 365 e abilitare lo spazio di indirizzi SIP condiviso con office 365](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365).
- [Abilitare lo spazio di indirizzi SIP condiviso nel tenant di Office 365](#enable-shared-sip-address-space-in-your-office-365-tenant).

Tieni presente che se hai Exchange locale, potresti voler configurare OAuth tra gli ambienti Exchange locale e Skype for business online. Per altre informazioni, Vedi [gestire l'autenticazione da server a server in Skype for Business Server](https://docs.microsoft.com/en-us/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) e [pianificare l'integrazione di Skype for business e Exchange](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support). 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-office-365"></a>Configurare il servizio Edge locale per la Federazione con Office 365

La federazione consente agli utenti della distribuzione locale di comunicare con gli utenti di Office 365 nell'organizzazione. Per configurare la Federazione, eseguire il cmdlet seguente in Skype for Business Server Management Shell:
  
```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```

Se il valore "-EnablePartnerDiscovery" è impostato su 1, Skype for Business Server userà i record DNS per cercare di individuare i domini partner non elencati nell'elenco di AllowedDomains. Se il valore è impostato su 0, Skype for Business Server verrà federato solo con i domini trovati nell'elenco AllowedDomains. Questo parametro è obbligatorio se si utilizza il routing del servizio DNS.



## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365"></a>Configurare l'ambiente locale per abilitare lo spazio di indirizzi SIP condiviso con Office 365

È inoltre necessario configurare l'ambiente locale per considerare attendibile Office 365 e abilitare lo spazio di indirizzi SIP condiviso con Office 365. Questo significa che Office 365 può potenzialmente ospitare account utente per lo stesso set di domini SIP dell'ambiente locale e i messaggi possono essere instradati tra utenti ospitati in locale e online.  A tale scopo, configurare un provider di hosting con ProxyFqdn = sipfed. online. Lync. com come descritto di seguito.

Prima di tutto, controlla se hai già un provider di hosting con ProxyFqdn = sipfed. online. Lync. com. Se uno esiste, rimuoverlo usando il comando seguente:

```
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

Crea quindi un nuovo provider di hosting, usa il cmdlet New-CsHostingProvider come segue: 

```
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-office-365-tenant"></a>Abilitare lo spazio di indirizzi SIP condiviso nel tenant di Office 365
  
Oltre alla modifica apportata nella distribuzione locale, è necessario apportare la modifica corrispondente nel tenant di Office 365 per abilitare lo spazio di indirizzi SIP condiviso con la distribuzione locale.  

Per abilitare lo spazio di indirizzi SIP condiviso nel tenant di Office 365, stabilire una sessione remota di PowerShell con Skype for business online e quindi eseguire il cmdlet seguente:
  
```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> L'attributo SharedSipAddressSpace deve rimanere "vero" finché il passaggio a online non è definitivo e gli utenti non rimangono in locale. 
  
Per stabilire una sessione remota di PowerShell con teams o Skype for business online, è necessario prima di tutto installare il modulo Connector di Skype for business online per Windows PowerShell, che è possibile ottenere [qui](https://go.microsoft.com/fwlink/p/?LinkId=391911).
  
Dopo aver installato il modulo, è possibile stabilire una sessione remota con i cmdlet seguenti:
  
```
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

Per altre informazioni su come stabilire una sessione remota di PowerShell con Skype for business online e come usare il modulo connettore di Skype for business online, vedere [configurare il computer per Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  


## <a name="see-also"></a>Vedere anche

[New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)


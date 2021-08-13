---
title: Teams tastiera del telefono
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
description: Informazioni su come configurare la tastiera del telefono nel client Teams in modo che gli utenti possano accedere alla funzionalità PSTN (Public Switched Telephone Network).
ms.openlocfilehash: 848e52859be3b2339e1e1968631c6d55fc7a8df79dc3a691fd47e9613f7f583d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344315"
---
# <a name="dial-pad-configuration"></a>Configurazione della tastiera del telefono

Nel client Teams, la tastiera del telefono consente agli utenti di accedere alla funzionalità PSTN (Public Switched Telephone Network). La tastiera del telefono è disponibile per gli utenti con una licenza Sistema telefonico, purché siano configurati correttamente. Per visualizzare la tastiera del telefono, sono necessari tutti i criteri seguenti:

- L'utente ha una licenza Sistema telefonico ("MCOEV")
- L'utente ha un piano per chiamate Microsoft o è abilitato per il routing diretto
- L'utente VoIP aziendale abilitato
- L'utente è disponibile online e non Skype for Business locale
- L'utente ha Teams dei criteri di chiamata abilitati

Le sezioni seguenti descrivono come usare PowerShell per controllare i criteri. Nella maggior parte dei casi, è necessario esaminare varie proprietà nell'output del cmdlet Get-CsOnlineUser. Gli esempi presuppongono $user sia l'indirizzo UPN o sip dell'utente.

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a>L'utente ha una licenza Sistema telefonico ("MCOEV")

È necessario assicurarsi che il piano assegnato per l'utente mostra l'attributo **CapabilityStatus** impostato su Abilitato e il piano di funzionalità impostato su **MCOEV** (Sistema telefonico licenza). Potrebbero essere visualizzati MCOEV, MCOEV1 e così via. Tutti sono accettabili, purché il piano di funzionalità inizi con MCOEV.

Per verificare che gli attributi siano impostati correttamente, usare il comando seguente:

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

L'output sarà simile al seguente. È necessario controllare solo gli **attributi CapabilityStatus** e **Capability Plan:**

```
<Plan SubscribedPlanId="2f9eda01-4630-4a5c-bdb3-cf195f22d240"  
   ServiceInstance="MicrosoftCommunicationsOnline/NOAM-0M-DMT" 
   CapabilityStatus="Enabled"  
   AssignedTimestamp="2020-04-21T18:31:13Z" 
   ServicePlanId="4828c8ec-dc2e-4779-b502-87ac9ce28ab7" 
   xmlns="http://schemas.microsoft.com/online/directoryservices/change/2008/11"> 
  <Capability> 
     <Capability Plan="MCOEV" 
     xmlns="http://schemas.microsoft.com/online/MCO/2009/01"/> 
  </Capability>
</Plan>
```


## <a name="user-has-microsoft-calling-plan-or-is-enabled-for-direct-routing"></a>L'utente ha microsoft Calling Plan OR abilitato per il routing diretto

**Se l'utente ha Un** piano per chiamate Microsoft, è necessario verificare che l'attributo **CapabilityStatus** sia impostato su Abilitato e che il piano di funzionalità sia impostato **su MCOPSTN.** Potrebbero essere visualizzati MCOPSTN1, MCOPSTN2 e così via. Tutti sono accettabili, purché il piano di funzionalità inizi con MCOPSTN.

Per controllare gli attributi, usare il comando seguente:

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

L'output sarà simile al seguente. È necessario controllare solo gli **attributi CapabilityStatus** e **Capability Plan:**

```  
<Plan SubscribedPlanId="71d1258e-a4e6-443f-884e-0f3d6f644bb1" 
ServiceInstance="MicrosoftCommunicationsOnline/NOAM-0M-DMT" 
CapabilityStatus="Enabled"    
AssignedTimestamp="2018-09-18T18:41:42Z" 
ServicePlanId="5a10155d-f5c1-411a-a8ec-e99aae125390" 
xmlns="http://schemas.microsoft.com/online/directoryservices/change/2008/11">
 <Capability>
    <Capability Plan="MCOPSTN2" 
    xmlns="http://schemas.microsoft.com/online/MCO/2009/01" />
 </Capability>
</Plan>
  ```

**Se l'utente è abilitato per il routing diretto,** all'utente deve essere assegnato un valore non Null per OnlineVoiceRoutingPolicy. Per controllare l'attributo, usare il comando seguente:
  
```
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy 
```

L'output deve avere un valore non Null, ad esempio:

```
OnlineVoiceRoutingPolicy
------------------------
Test_Policy
```

## <a name="user-has-enterprise-voice-enabled"></a>L'utente VoIP aziendale abilitato

Per verificare se l'utente VoIP aziendale abilitato, usare il comando seguente:

```
Get-CsOnlineUser -Identity $user|Select EnterpriseVoiceEnabled
```

L'output dovrebbe essere simile al seguente:

```
EnterpriseVoiceEnabled
----------------------
                  True

```
 
## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a>L'utente è disponibile online e non Skype for Business locale

Per assicurarsi che l'utente sia ospitato online e non in Skype for Business locale, RegistrarPool non deve essere Null e HostingProvider deve contenere un valore che inizia con "sipfed.online".  Per controllare i valori, usare il comando seguente:

```
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

L'output dovrebbe essere simile al seguente:

```
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a>L'utente ha Teams dei criteri di chiamata abilitati

TeamsCallingPolicy effettivo dell'utente deve avere AllowPrivateCalling impostato su true.  Per impostazione predefinita, gli utenti ereditano i criteri globali, che hanno AllowPrivateCallingPolicy impostato su true per impostazione predefinita.

Per ottenere TeamsCallingPolicy per un utente e verificare che AllowPrivateCalling sia impostato su true, usare il comando seguente:

```
if (($p=(get-csonlineuser -Identity $user).TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity global} else {get-csteamscallingpolicy -Identity $p}
```

L'output dovrebbe essere simile al seguente:

```
Identity                   : Global
Description                :
AllowPrivateCalling        : True
AllowWebPSTNCalling        : True
AllowVoicemail             : UserOverride
AllowCallGroups            : True
AllowDelegation            : True
AllowCallForwardingToUser  : True
AllowCallForwardingToPhone : True
PreventTollBypass          : False
BusyOnBusyEnabledType      : Disabled
MusicOnHoldEnabledType     : Enabled
``` 

## <a name="additional-notes"></a>Note aggiuntive

-   Potrebbe essere necessario riavviare il client Teams dopo aver apportato una di queste modifiche alla configurazione.

-   Se di recente è stato aggiornato uno dei criteri indicati sopra, potrebbe essere necessario attendere alcune ore prima che il client riceva le nuove impostazioni.

-   Se la tastiera del telefono non è ancora visualizzata, verificare se è presente un errore di provisioning usando il comando seguente:

  ```
  Get-CsOnlineUser -Identity $user|Select McoValidationError
  ```

-    Se sono state più di 24 ore e il problema persiste, contattare il supporto tecnico.



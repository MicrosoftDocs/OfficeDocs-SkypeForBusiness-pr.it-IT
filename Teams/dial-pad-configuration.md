---
title: Configurazione della tastiera del telefono di Teams
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
description: Informazioni su come configurare la tastiera del telefono nel client di Teams in modo che gli utenti possano accedere alla funzionalità PSTN (Public Switched Telephone Network).
ms.openlocfilehash: 44fcbb766cadaa4b31aa065fae80fdcd48c5453f
ms.sourcegitcommit: a94a267c421a78587b0dbbea5fa167aad2882e9b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "45012417"
---
# <a name="dial-pad-configuration"></a>Configurazione della tastiera del telefono

Nel client di Teams, la tastiera del telefono consente agli utenti di accedere alla funzionalità PSTN (Public Switched Telephone Network). La tastiera del telefono è disponibile per gli utenti con licenza Sistema telefonico, a condizione che siano configurati correttamente. Per visualizzare la tastiera del telefono sono tutti necessari i criteri seguenti:

- L'utente ha una licenza Sistema telefonico ("MCOEV") abilitata
- L'utente ha un Piano per chiamate Microsoft o è abilitato per l'instradamento diretto
- L'utente ha VoIP aziendale abilitato
- L'utente è ospitata online e non in Skype for Business locale
- L'utente ha abilitato i criteri di chiamata di Teams

Le sezioni seguenti descrivono come usare PowerShell per controllare i criteri. Nella maggior parte dei casi, è necessario esaminare varie proprietà nell'output del cmdlet Get-CsOnlineUser. Gli esempi $user che si tratta dell'UPN o dell'indirizzo SIP dell'utente.

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a>L'utente ha una licenza Sistema telefonico ("MCOEV") abilitata

È necessario assicurarsi che il piano assegnato per l'utente mostra l'attributo **CapabilityStatus impostato** su Abilitato e il piano capacità impostato su **MCOEV** (licenza Sistema telefonico). Potrebbero essere visualizzati MCOEV, MCOEV1 e così via. Tutto è accettabile, a meno che il piano di capacità inizi con MCOEV.

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


## <a name="user-has-microsoft-calling-plan-or-is-enabled-for-direct-routing"></a>L'utente ha un Piano per chiamate Microsoft OR abilitato per l'instradamento diretto

**Se l'utente** ha un Piano per chiamate Microsoft, è necessario verificare che l'attributo **CapabilityStatus** sia impostato su Enabled e che Capability Plan sia impostato su **MCOPSTN.** Potrebbero essere visualizzati MCOPSTN1, MCOPSTN2 e così via. Tutti sono accettabili, a meno che il piano di capacità inizi con MCOPSTN.

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

## <a name="user-has-enterprise-voice-enabled"></a>L'utente ha VoIP aziendale abilitato

Per verificare se l'utente ha VoIP aziendale abilitato, usare il comando seguente:

```
Get-CsOnlineUser -Identity $user|Select EnterpriseVoiceEnabled
```

L'output dovrebbe essere simile al seguente:

```
EnterpriseVoiceEnabled
----------------------
                  True

```
 
## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a>L'utente è ospitata online e non in Skype for Business locale

Per garantire che l'utente sia ospitato online e non in Skype for Business locale, RegistrarPool non deve essere Null e HostingProvider deve contenere un valore che inizia con "sipfed.online".  Per controllare i valori, usare il comando seguente:

```
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

L'output dovrebbe essere simile al seguente:

```
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a>L'utente ha abilitato i criteri di chiamata di Teams

TeamsCallingPolicy effettivo dell'utente deve avere AllowPrivateCalling impostato su true.  Per impostazione predefinita, gli utenti ereditano il criterio globale, per cui AllowPrivateCallingPolicy è impostato su true per impostazione predefinita.

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

-   Potrebbe essere necessario riavviare il client di Teams dopo aver apportato le modifiche alla configurazione.

-   Se di recente è stato aggiornato uno dei criteri precedenti, potrebbe essere necessario attendere alcune ore perché il client riceva le nuove impostazioni.

-   Se ancora non vedi la tastiera del telefono, verifica se si verifica un errore di provisioning usando il comando seguente:

  ```
  Get-CsOnlineUser -Identity $user|Select McoValidationError
  ```

-    Se dopo più di 24 ore il problema persiste, contattare il supporto.



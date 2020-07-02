---
title: Configurazione del tastierino vocale di Teams
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
description: Informazioni su come configurare la tastiera del telefono nel client teams in modo che gli utenti possano accedere alle funzionalità PSTN (Public Switched Telephone Network).
ms.openlocfilehash: 44fcbb766cadaa4b31aa065fae80fdcd48c5453f
ms.sourcegitcommit: a94a267c421a78587b0dbbea5fa167aad2882e9b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "45012417"
---
# <a name="dial-pad-configuration"></a>Configurazione del tastierino vocale

Nel client teams, la tastiera del telefono consente agli utenti di accedere alle funzionalità PSTN (Public Switched Telephone Network). La tastiera del telefono è disponibile per gli utenti con una licenza di sistema telefonico, purché siano configurati correttamente. I criteri seguenti sono tutti necessari per visualizzare la tastiera del telefono:

- L'utente ha una licenza per il sistema telefonico abilitato ("MCOEV")
- L'utente ha un piano di chiamata Microsoft o è abilitato per il routing diretto
- L'utente ha abilitato VoIP aziendale
- L'utente è ospitato online e non in Skype for business in locale
- L'utente ha attivato i criteri per le chiamate dei team

Nelle sezioni seguenti viene descritto come usare PowerShell per controllare i criteri. Nella maggior parte dei casi, è necessario esaminare varie proprietà nell'output del cmdlet Get-CsOnlineUser. Gli esempi presuppongono che $user sia l'indirizzo UPN o SIP dell'utente.

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a>L'utente ha una licenza per il sistema telefonico abilitato ("MCOEV")

Devi verificare che il piano assegnato per l'utente mostri l' **attributo CapabilityStatus impostato su Enabled** e il **piano di funzionalità impostato su MCOEV** (licenza per il sistema telefonico). Potresti vedere MCOEV, MCOEV1 e così via. Tutti sono accettabili, purché il piano di funzionalità inizi con MCOEV.

Per verificare che gli attributi siano impostati correttamente, usare il comando seguente:

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

L'output avrà un aspetto simile al seguente. È necessario controllare solo gli attributi **CapabilityStatus** e **Plan Capability** :

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


## <a name="user-has-microsoft-calling-plan-or-is-enabled-for-direct-routing"></a>L'utente ha un piano di chiamata Microsoft o è abilitato per il routing diretto

**Se l'utente ha un piano di chiamata Microsoft**, devi assicurarti che l' **attributo CapabilityStatus sia impostato su Enabled**e che il **piano di funzionalità sia impostato su MCOPSTN**. Potresti vedere MCOPSTN1, MCOPSTN2 e così via. Tutti sono accettabili, purché il piano di funzionalità inizi con MCOPSTN.

Per controllare gli attributi, usare il comando seguente:

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

L'output avrà un aspetto simile al seguente. È necessario controllare solo gli attributi **CapabilityStatus** e **Plan Capability** :

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

**Se l'utente è abilitato per il routing diretto**, all'utente deve essere assegnato un valore non null per OnlineVoiceRoutingPolicy. Per controllare l'attributo, usare il comando seguente:
  
```
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy 
```

L'output deve avere un valore diverso da null, ad esempio:

```
OnlineVoiceRoutingPolicy
------------------------
Test_Policy
```

## <a name="user-has-enterprise-voice-enabled"></a>L'utente ha abilitato VoIP aziendale

Per verificare se l'utente ha abilitato VoIP aziendale, usare il comando seguente:

```
Get-CsOnlineUser -Identity $user|Select EnterpriseVoiceEnabled
```

L'output dovrebbe essere simile al seguente:

```
EnterpriseVoiceEnabled
----------------------
                  True

```
 
## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a>L'utente è ospitato online e non in Skype for business in locale

Per assicurarti che l'utente sia ospitato online e non in Skype for business in locale, RegistrarPool non deve essere null e provider dihosting deve contenere un valore che inizia con "sipfed. online".  Per controllare i valori, usare il comando seguente:

```
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

L'output deve essere simile a:

```
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a>L'utente ha attivato i criteri per le chiamate dei team

Il TeamsCallingPolicy effettivo dell'utente deve avere AllowPrivateCalling impostato su true.  Per impostazione predefinita, gli utenti ereditano il criterio globale, che ha AllowPrivateCallingPolicy impostato su true per impostazione predefinita.

Per ottenere il TeamsCallingPolicy per un utente e verificare che AllowPrivateCalling sia impostato su true, usare il comando seguente:

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

-   Potrebbe essere necessario riavviare il client teams dopo aver apportato queste modifiche alla configurazione.

-   Se di recente è stato aggiornato uno dei criteri descritti sopra, potrebbe essere necessario attendere qualche ora prima che il client riceva le nuove impostazioni.

-   Se la tastiera non è ancora visibile, verificare se è presente un errore di provisioning tramite il comando seguente:

  ```
  Get-CsOnlineUser -Identity $user|Select McoValidationError
  ```

-    Se sono state visualizzate più di 24 ore e si verificano ancora problemi, contattare il supporto.



---
title: Teams configurazione della tastiera del telefono
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Informazioni su come configurare la tastiera del client Teams in modo che gli utenti possano accedere alla funzionalità PSTN (Public Switched Telephone Network).
ms.openlocfilehash: 6aa5edf8f57574fa08a224541772c1f9e662f9ca
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676154"
---
# <a name="dial-pad-configuration"></a>Configurazione della tastiera del telefono

Nel client Teams la tastiera consente agli utenti di accedere alla funzionalità PSTN (Public Switched Telephone Network). La tastiera del telefono è disponibile per gli utenti con una licenza di Sistema telefonico, purché siano configurati correttamente. Per visualizzare la tastiera del telefono sono tutti necessari i criteri seguenti:

- L'utente dispone di una licenza di Sistema telefonico ("MCOEV") abilitata
- L'utente ha un piano per chiamate Microsoft, Connessione con operatore o è abilitato per il routing diretto
- L'utente ha abilitato VoIP aziendale
- L'utente è ospitato online e non in Skype for Business locale
- L'utente ha abilitato i criteri per le chiamate Teams

Le sezioni seguenti descrivono come usare PowerShell per verificare i criteri. Nella maggior parte dei casi, è necessario esaminare varie proprietà nell'output del cmdlet Get-CsOnlineUser. Gli esempi presuppongono $user sia l'indirizzo UPN che l'indirizzo SIP dell'utente.

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a>L'utente dispone di una licenza di Sistema telefonico ("MCOEV") abilitata

Assicurarsi che il piano assegnato per l'utente mostri **l'attributo CapabilityStatus impostato su Enabled** e il **Capability impostato su MCOEV** (Sistema telefonico licenza). Potrebbe essere visualizzato MCOEV, MCOEV1 e così via. Tutto è accettabile, purché la funzionalità inizi con MCOEV.

Per verificare che gli attributi siano impostati correttamente, utilizzare il comando seguente:

```PowerShell
(Get-CsOnlineUser -Identity $user).AssignedPlan
```

L'output sarà simile al seguente. È sufficiente controllare gli attributi **CapabilityStatus** e **Capability** :

```PowerShell
AssignedTimestamp   Capability      CapabilityStatus ServiceInstance                          ServicePlanId
-----------------   ----------      ---------------- ---------------                          -------------
07-02-2020 12:28:48 MCOEV           Enabled          MicrosoftCommunicationsOnline/NOAM-4A-S7 4828c8ec-dc2e-4779-b502-...
07-02-2020 12:28:48 Teams           Enabled          TeamspaceAPI/NA001                       57ff2da0-773e-42df-b2af-...
```

## <a name="user-has-microsoft-calling-plan-operator-connect-or-is-enabled-for-direct-routing"></a>L'utente ha un piano per le chiamate Microsoft, Connessione con operatore OR è abilitato per il routing diretto

**Se l'utente ha un piano per chiamate Microsoft**, verifica che **l'attributo CapabilityStatus sia impostato su Enabled** e che **l'opzione Capability sia impostata su MCOPSTN**. È possibile che vengano visualizzati MCOPSTN1, MCOPSTN2 e così via. Tutto è accettabile, purché la funzionalità inizi con MCOPSTN.

Per controllare gli attributi, usare il comando seguente:

```PowerShell
(Get-CsOnlineUser -Identity $user).AssignedPlan
```

L'output sarà simile al seguente. È sufficiente controllare gli attributi **CapabilityStatus** e **Capability** :

```PowerShell
AssignedTimestamp   Capability      CapabilityStatus ServiceInstance                          ServicePlanId
-----------------   ----------      ---------------- ---------------                          -------------
07-02-2020 12:28:48 MCOEV           Enabled          MicrosoftCommunicationsOnline/NOAM-4A-S7 4828c8ec-dc2e-4779-b502-...
07-02-2020 12:28:48 MCOPSTN2        Enabled          MicrosoftCommunicationsOnline/NOAM-4A-S7 5a10155d-f5c1-411a-a8ec-...
07-02-2020 12:28:48 Teams           Enabled          TeamspaceAPI/NA001                       57ff2da0-773e-42df-b2af-...
```

**Se l'utente è abilitato per Connessione con operatore**, l'utente deve avere un valore non Null per TeamsCarrierEmergencyCallRoutingPolicy. Per controllare l'attributo, utilizzare il comando seguente:

```PowerShell
Get-CsOnlineUser -Identity $user|Select TeamsCarrierEmergencyCallRoutingPolicy
```

L'output deve avere un valore non Null, ad esempio:

```PowerShell
TeamsCarrierEmergencyCallRoutingPolicy
--------------------------------------
Synergy_98d1a5cb-d3e6-4306-885e-69a95f2da5c3
```

**Se l'utente è abilitato per il routing diretto**, all'utente deve essere assegnato un valore non Null per OnlineVoiceRoutingPolicy. Per controllare l'attributo, utilizzare il comando seguente:

```PowerShell
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy
```

L'output deve avere un valore non Null, ad esempio:

```PowerShell
OnlineVoiceRoutingPolicy
------------------------
Test_Policy
```

## <a name="user-has-enterprise-voice-enabled"></a>L'utente ha abilitato VoIP aziendale

Per verificare se l'utente ha VoIP aziendale abilitato, usare il comando seguente:

```PowerShell
Get-CsOnlineUser -Identity $user|Select EnterpriseVoiceEnabled
```

L'output dovrebbe essere simile al seguente:

```PowerShell
EnterpriseVoiceEnabled
----------------------
                  True
```

## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a>L'utente è ospitato online e non in Skype for Business locale

Per assicurarsi che l'utente sia ospitato online e non in Skype for Business locale, RegistrarPool non deve essere Null e HostingProvider deve contenere un valore che inizia con "sipfed.online".  Per controllare i valori, usare il comando seguente:

```PowerShell
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

L'output dovrebbe essere simile a:

```PowerShell
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a>L'utente ha abilitato i criteri per le chiamate Teams

TeamsCallingPolicy efficace dell'utente deve avere AllowPrivateCalling impostato su true.  Per impostazione predefinita, gli utenti ereditano il criterio globale, che ha AllowPrivateCallingPolicy impostato su true per impostazione predefinita.

Per ottenere TeamsCallingPolicy per un utente e verificare che AllowPrivateCalling sia impostato su true, usare il comando seguente:

```PowerShell
if (($p=Get-CsUserPolicyAssignment -Identity $user -PolicyType TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity Global} else {Get-CsTeamsCallingPolicy -Identity $p.PolicyName}
```

L'output dovrebbe essere simile al seguente:

```PowerShell
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

- Potrebbe essere necessario riavviare il client Teams dopo aver apportato una di queste modifiche alla configurazione.

- Se di recente è stato aggiornato uno dei criteri precedenti, potrebbe essere necessario attendere alcune ore prima che il client riceva le nuove impostazioni.

- Se la tastiera del telefono continua a non essere visualizzata, verifica se si è verificato un errore di provisioning usando il comando seguente:

  ```PowerShell
  Get-CsOnlineUser -Identity $user|Select UserValidationErrors
  ```

- Se i problemi persistono da più di 24 ore, contatta il supporto tecnico.

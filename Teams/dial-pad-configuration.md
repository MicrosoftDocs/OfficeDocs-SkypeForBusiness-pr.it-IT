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
# <a name="dial-pad-configuration"></a><span data-ttu-id="be846-103">Configurazione della tastiera del telefono</span><span class="sxs-lookup"><span data-stu-id="be846-103">Dial pad configuration</span></span>

<span data-ttu-id="be846-104">Nel client di Teams, la tastiera del telefono consente agli utenti di accedere alla funzionalità PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="be846-104">In the Teams client, the dial pad enables users to access Public Switched Telephone Network (PSTN) functionality.</span></span> <span data-ttu-id="be846-105">La tastiera del telefono è disponibile per gli utenti con licenza Sistema telefonico, a condizione che siano configurati correttamente.</span><span class="sxs-lookup"><span data-stu-id="be846-105">The dial pad is available for users with a Phone System license, provided they are configured properly.</span></span> <span data-ttu-id="be846-106">Per visualizzare la tastiera del telefono sono tutti necessari i criteri seguenti:</span><span class="sxs-lookup"><span data-stu-id="be846-106">The following criteria are all required for the dial pad to show:</span></span>

- <span data-ttu-id="be846-107">L'utente ha una licenza Sistema telefonico ("MCOEV") abilitata</span><span class="sxs-lookup"><span data-stu-id="be846-107">User has an enabled Phone System (“MCOEV”) license</span></span>
- <span data-ttu-id="be846-108">L'utente ha un Piano per chiamate Microsoft o è abilitato per l'instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="be846-108">User has Microsoft Calling Plan or is enabled for Direct Routing</span></span>
- <span data-ttu-id="be846-109">L'utente ha VoIP aziendale abilitato</span><span class="sxs-lookup"><span data-stu-id="be846-109">User has Enterprise Voice enabled</span></span>
- <span data-ttu-id="be846-110">L'utente è ospitata online e non in Skype for Business locale</span><span class="sxs-lookup"><span data-stu-id="be846-110">User is homed online and not in Skype for Business on premises</span></span>
- <span data-ttu-id="be846-111">L'utente ha abilitato i criteri di chiamata di Teams</span><span class="sxs-lookup"><span data-stu-id="be846-111">User has Teams Calling Policy enabled</span></span>

<span data-ttu-id="be846-112">Le sezioni seguenti descrivono come usare PowerShell per controllare i criteri.</span><span class="sxs-lookup"><span data-stu-id="be846-112">The following sections describe how to use PowerShell to check the criteria.</span></span> <span data-ttu-id="be846-113">Nella maggior parte dei casi, è necessario esaminare varie proprietà nell'output del cmdlet Get-CsOnlineUser.</span><span class="sxs-lookup"><span data-stu-id="be846-113">In most cases, you need to look at various properties in the output of the Get-CsOnlineUser cmdlet.</span></span> <span data-ttu-id="be846-114">Gli esempi $user che si tratta dell'UPN o dell'indirizzo SIP dell'utente.</span><span class="sxs-lookup"><span data-stu-id="be846-114">Examples assume $user is either the UPN or sip address of the user.</span></span>

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a><span data-ttu-id="be846-115">L'utente ha una licenza Sistema telefonico ("MCOEV") abilitata</span><span class="sxs-lookup"><span data-stu-id="be846-115">User has an enabled Phone System (“MCOEV”) license</span></span>

<span data-ttu-id="be846-116">È necessario assicurarsi che il piano assegnato per l'utente mostra l'attributo **CapabilityStatus impostato** su Abilitato e il piano capacità impostato su **MCOEV** (licenza Sistema telefonico).</span><span class="sxs-lookup"><span data-stu-id="be846-116">You must ensure that the assigned plan for the user shows the **CapabilityStatus attribute set to Enabled** and the **Capability Plan set to MCOEV** (Phone System license).</span></span> <span data-ttu-id="be846-117">Potrebbero essere visualizzati MCOEV, MCOEV1 e così via.</span><span class="sxs-lookup"><span data-stu-id="be846-117">You might see MCOEV, MCOEV1, and so on.</span></span> <span data-ttu-id="be846-118">Tutto è accettabile, a meno che il piano di capacità inizi con MCOEV.</span><span class="sxs-lookup"><span data-stu-id="be846-118">All are acceptable--as long as the Capability Plan starts with MCOEV.</span></span>

<span data-ttu-id="be846-119">Per verificare che gli attributi siano impostati correttamente, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="be846-119">To check that the attributes are set correctly, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

<span data-ttu-id="be846-120">L'output sarà simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="be846-120">The output will look like the following.</span></span> <span data-ttu-id="be846-121">È necessario controllare solo gli **attributi CapabilityStatus** e **Capability Plan:**</span><span class="sxs-lookup"><span data-stu-id="be846-121">You only need to check the **CapabilityStatus** and the **Capability Plan** attributes:</span></span>

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


## <a name="user-has-microsoft-calling-plan-or-is-enabled-for-direct-routing"></a><span data-ttu-id="be846-122">L'utente ha un Piano per chiamate Microsoft OR abilitato per l'instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="be846-122">User has Microsoft Calling Plan OR is enabled for Direct Routing</span></span>

<span data-ttu-id="be846-123">**Se l'utente** ha un Piano per chiamate Microsoft, è necessario verificare che l'attributo **CapabilityStatus** sia impostato su Enabled e che Capability Plan sia impostato su **MCOPSTN.**</span><span class="sxs-lookup"><span data-stu-id="be846-123">**If the user has Microsoft Calling Plan**, you must ensure that the **CapabilityStatus attribute is set to Enabled**, and that the **Capability Plan is set to MCOPSTN**.</span></span> <span data-ttu-id="be846-124">Potrebbero essere visualizzati MCOPSTN1, MCOPSTN2 e così via.</span><span class="sxs-lookup"><span data-stu-id="be846-124">You might see MCOPSTN1, MCOPSTN2, and so on.</span></span> <span data-ttu-id="be846-125">Tutti sono accettabili, a meno che il piano di capacità inizi con MCOPSTN.</span><span class="sxs-lookup"><span data-stu-id="be846-125">All are acceptable--as long as the Capability Plan starts with MCOPSTN.</span></span>

<span data-ttu-id="be846-126">Per controllare gli attributi, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="be846-126">To check the attributes, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

<span data-ttu-id="be846-127">L'output sarà simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="be846-127">The output will look like the following.</span></span> <span data-ttu-id="be846-128">È necessario controllare solo gli **attributi CapabilityStatus** e **Capability Plan:**</span><span class="sxs-lookup"><span data-stu-id="be846-128">You only need to check the **CapabilityStatus** and the **Capability Plan** attributes:</span></span>

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

<span data-ttu-id="be846-129">**Se l'utente è abilitato per il routing diretto,** all'utente deve essere assegnato un valore non Null per OnlineVoiceRoutingPolicy.</span><span class="sxs-lookup"><span data-stu-id="be846-129">**If the user is enabled for Direct Routing**, the user must be assigned a non-null value for OnlineVoiceRoutingPolicy.</span></span> <span data-ttu-id="be846-130">Per controllare l'attributo, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="be846-130">To check the attribute, use the following command:</span></span>
  
```
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy 
```

<span data-ttu-id="be846-131">L'output deve avere un valore non Null, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="be846-131">The output should have a non-null value, for example:</span></span>

```
OnlineVoiceRoutingPolicy
------------------------
Test_Policy
```

## <a name="user-has-enterprise-voice-enabled"></a><span data-ttu-id="be846-132">L'utente ha VoIP aziendale abilitato</span><span class="sxs-lookup"><span data-stu-id="be846-132">User has Enterprise Voice enabled</span></span>

<span data-ttu-id="be846-133">Per verificare se l'utente ha VoIP aziendale abilitato, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="be846-133">To check if the user has Enterprise Voice enabled, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|Select EnterpriseVoiceEnabled
```

<span data-ttu-id="be846-134">L'output dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="be846-134">The output should look like:</span></span>

```
EnterpriseVoiceEnabled
----------------------
                  True

```
 
## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a><span data-ttu-id="be846-135">L'utente è ospitata online e non in Skype for Business locale</span><span class="sxs-lookup"><span data-stu-id="be846-135">User is homed online and not in Skype for Business on premises</span></span>

<span data-ttu-id="be846-136">Per garantire che l'utente sia ospitato online e non in Skype for Business locale, RegistrarPool non deve essere Null e HostingProvider deve contenere un valore che inizia con "sipfed.online".</span><span class="sxs-lookup"><span data-stu-id="be846-136">To ensure the user is homed online and not in Skype for Business on premises, the RegistrarPool must not be null and the HostingProvider must contain a value that starts with “sipfed.online.”</span></span>  <span data-ttu-id="be846-137">Per controllare i valori, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="be846-137">To check the values, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

<span data-ttu-id="be846-138">L'output dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="be846-138">The output should be similar to:</span></span>

```
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a><span data-ttu-id="be846-139">L'utente ha abilitato i criteri di chiamata di Teams</span><span class="sxs-lookup"><span data-stu-id="be846-139">User has Teams Calling Policy enabled</span></span>

<span data-ttu-id="be846-140">TeamsCallingPolicy effettivo dell'utente deve avere AllowPrivateCalling impostato su true.</span><span class="sxs-lookup"><span data-stu-id="be846-140">The user’s effective TeamsCallingPolicy must have AllowPrivateCalling set to true.</span></span>  <span data-ttu-id="be846-141">Per impostazione predefinita, gli utenti ereditano il criterio globale, per cui AllowPrivateCallingPolicy è impostato su true per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="be846-141">By default, users inherit the global policy, which has AllowPrivateCallingPolicy set to true by default.</span></span>

<span data-ttu-id="be846-142">Per ottenere TeamsCallingPolicy per un utente e verificare che AllowPrivateCalling sia impostato su true, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="be846-142">To get the TeamsCallingPolicy for a user and to check that AllowPrivateCalling is set to true, use the following command:</span></span>

```
if (($p=(get-csonlineuser -Identity $user).TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity global} else {get-csteamscallingpolicy -Identity $p}
```

<span data-ttu-id="be846-143">L'output dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="be846-143">The output should look like:</span></span>

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

## <a name="additional-notes"></a><span data-ttu-id="be846-144">Note aggiuntive</span><span class="sxs-lookup"><span data-stu-id="be846-144">Additional notes</span></span>

-   <span data-ttu-id="be846-145">Potrebbe essere necessario riavviare il client di Teams dopo aver apportato le modifiche alla configurazione.</span><span class="sxs-lookup"><span data-stu-id="be846-145">You may need to restart the Teams client after making any of these configuration changes.</span></span>

-   <span data-ttu-id="be846-146">Se di recente è stato aggiornato uno dei criteri precedenti, potrebbe essere necessario attendere alcune ore perché il client riceva le nuove impostazioni.</span><span class="sxs-lookup"><span data-stu-id="be846-146">If you recently updated any of the above criteria, you may need to wait a few hours for the client to receive the new settings.</span></span>

-   <span data-ttu-id="be846-147">Se ancora non vedi la tastiera del telefono, verifica se si verifica un errore di provisioning usando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="be846-147">If you still don’t see the dial pad, check if there is a provisioning error by using the following command:</span></span>

  ```
  Get-CsOnlineUser -Identity $user|Select McoValidationError
  ```

-    <span data-ttu-id="be846-148">Se dopo più di 24 ore il problema persiste, contattare il supporto.</span><span class="sxs-lookup"><span data-stu-id="be846-148">If it has been more than 24 hours and you are still seeing problems, contact Support.</span></span>



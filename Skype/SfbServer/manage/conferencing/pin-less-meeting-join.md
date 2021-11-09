---
title: Configurare la partecipazione alle riunioni senza PIN in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: "Riepilogo: informazioni su come configurare l'opzione di partecipazione alle riunioni senza PIN in Skype for Business Server."
ms.openlocfilehash: 13af671edaa9ab8853e0390d43c62b6576bed4e2
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60861363"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a>Configurare la partecipazione alle riunioni senza PIN in Skype for Business Server
 
**Riepilogo:** Informazioni su come configurare l'opzione di partecipazione alle riunioni senza PIN in Skype for Business Server.
  
Quando un chiamante con accesso esterno tenta di partecipare a una riunione, il servizio Conference Operatore automatico (CAA) posiziona il chiamante in una penna di attesa diversa dal &#x2014; sala di attesa se un relatore non è già in una chiamata e il chiamante di accesso esterno non ha immesso un PIN di leader. L'opzione di partecipazione alla riunione senza PIN consente ai chiamanti con accesso esterno di partecipare a una riunione senza immettere un PIN di leader anche se sono la prima persona di una chiamata. 
  
Quando si configura questa funzionalità, tenere presente quanto segue:
  
- Si applica solo alle riunioni private.
    
- Consente ai chiamanti PSTN di rimanere in riunioni private senza la presenza di utenti autenticati.
    
- Dopo la modifica, l'impostazione si applica a tutte le riunioni private esistenti e nuove.
    
- Può essere abilitato sia nel sito dell'organizzatore che a livello globale.
    
- Le opzioni per gli utenti che possono ignorare la sala di attesa possono essere impostate per una delle opzioni seguenti: 
    
  - **Tutti gli utenti dell'organizzazione con chiamanti possono accedere direttamente**
    
  - **Chiunque (senza restrizioni) con chiamanti ottiene direttamente** (questa è l'impostazione predefinita).
    
- Se configurato per abilitare l'aggiunta senza PIN, il servizio CAA richiede comunque un PIN leader. Gli utenti possono partecipare alla riunione indipendentemente dal fatto che sia stato immesso o meno un PIN. Tuttavia, mantenendo la possibilità di immettere un PIN di leader, un chiamante esterno può autenticarsi come leader e gestire la riunione, se necessario.
    
## <a name="configure-pin-less-meeting-join"></a>Configurare la partecipazione alle riunioni senza PIN

Per abilitare la partecipazione alle riunioni senza PIN per gli utenti, utilizzare il cmdlet [Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) con il parametro AllowAnonymousPstnActivation come segue:
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

Ad esempio, il comando seguente abilita la partecipazione alle riunioni senza PIN per il sito Redmond:
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

Per motivi di sicurezza, quando l'accesso alle riunioni senza PIN è attivato, è possibile limitare la composizione degli utenti anonimi assicurandosi che ConferencingPolicy sia impostato come segue:
  
```PowerShell
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

Per ulteriori informazioni, vedere [Set-CsConferencingPolicy.](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)

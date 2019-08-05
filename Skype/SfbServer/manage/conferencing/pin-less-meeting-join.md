---
title: Configurare l'aggiunta di una riunione senza PIN in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: "Riepilogo: informazioni su come configurare l'opzione di partecipazione alla riunione senza PIN in Skype for Business Server."
ms.openlocfilehash: ecd1d2bf184dd6b9e1ff78e16c2ca1eb8da73ef9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188945"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a>Configurare l'aggiunta di una riunione senza PIN in Skype for Business Server
 
**Riepilogo:** Informazioni su come configurare l'opzione di partecipazione alla riunione senza PIN in Skype for Business Server.
  
Quando un chiamante di chiamata in ingresso tenta di partecipare a una riunione, il servizio di conferenza automatica (CAA) colloca il chiamante in una penna di attesa diversa da quella della sala di &#x2014; se un relatore non è già in una chiamata e il chiamante non ha inserito il PIN di una direttrice. L'opzione di join per riunioni con PIN meno consente ai chiamanti di accesso esterno di partecipare a una riunione senza immettere un PIN di riferimento, anche se è la prima persona che effettua una chiamata. 
  
Quando si configura questa funzionalità, tieni presente quanto segue:
  
- Si applica solo alle riunioni private.
    
- Consente ai chiamanti PSTN di rimanere in riunioni private senza la presenza di utenti autenticati.
    
- Dopo aver modificato l'impostazione, viene applicata a tutte le riunioni private esistenti e nuove.
    
- Può essere abilitato sia nel sito dell'organizzatore che a livello globale.
    
- Le opzioni per chi può bypassare la sala d'attesa possono essere impostate per una delle seguenti operazioni: 
    
  - **Tutti gli utenti dell'organizzazione con i chiamanti entrano direttamente**
    
  - **Tutti gli utenti (nessuna restrizione) con i chiamanti entrano direttamente** Questa è l'impostazione predefinita.
    
- Quando è configurato per abilitare l'aggiunta di PIN, il servizio CAA richiede ancora un PIN iniziale. Gli utenti possono partecipare alla riunione indipendentemente dal fatto che venga immesso o meno un PIN. Tuttavia, il mantenimento della possibilità di immettere un PIN di riferimento consente a un chiamante di effettuare l'autenticazione come leader e di gestire la riunione, se necessario.
    
## <a name="configure-pin-less-meeting-join"></a>Configurare l'aggiunta di una riunione senza PIN

Per abilitare l'aggiunta di una riunione senza PIN per gli utenti, usare il cmdlet [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) con il parametro AllowAnonymousPstnActivation come indicato di seguito:
  
```
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

Ad esempio, con il comando seguente viene abilitato il join di riunione senza PIN per il sito Redmond:
  
```
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

Per motivi di sicurezza, quando è attivata la partecipazione alla riunione senza PIN, è consigliabile limitare l'accesso degli utenti anonimi garantendo che ConferencingPolicy sia impostato come segue:
  
```
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

Per altre informazioni, vedere [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
  


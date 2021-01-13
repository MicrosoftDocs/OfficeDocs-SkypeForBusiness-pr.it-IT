---
title: Configurare il join di riunioni senza PIN in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: "Riepilogo: informazioni su come configurare l'opzione di partecipazione alle riunioni senza PIN in Skype for Business Server."
ms.openlocfilehash: 794bf13d92857a18254f903a1c5dcca98d0a1ec0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827986"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a>Configurare il join di riunioni senza PIN in Skype for Business Server
 
**Riepilogo:** Informazioni su come configurare l'opzione di partecipazione alle riunioni senza PIN in Skype for Business Server.
  
Quando un chiamante di accesso esterno tenta di partecipare a una riunione, il servizio operatore automatico di conferenza inserisce il chiamante in una penna che è diversa dalla lobby &#x2014; se un relatore non è già su una chiamata e il chiamante di accesso esterno non è stato immesso in un PIN della direttrice. L'opzione di partecipazione alle riunioni con PIN meno consente ai chiamanti di accesso esterno di partecipare a una riunione senza immettere un PIN della direttrice anche se è la prima persona di una chiamata. 
  
Quando si configura questa funzionalità, tenere presente quanto segue:
  
- Si applica solo alle riunioni private.
    
- Consente ai chiamanti PSTN di rimanere in riunioni private senza la presenza di utenti autenticati.
    
- Dopo la modifica dell'impostazione, si applica a tutte le riunioni private esistenti e nuove.
    
- Può essere abilitato sia nel sito dell'organizzatore sia a livello globale.
    
- Le opzioni per gli utenti che possono ignorare la lobby possono essere impostate per una delle seguenti operazioni: 
    
  - **Tutti gli utenti dell'organizzazione con i chiamanti si rifanno direttamente**
    
  - **Tutti gli utenti (nessuna restrizione) con i chiamanti ottengono direttamente** (questa è l'impostazione predefinita).
    
- Quando viene configurato per abilitare l'aggiunta senza PIN, il servizio CAA richiede ancora un PIN di direttrice. Gli utenti possono partecipare alla riunione indipendentemente dal fatto che un PIN venga immesso. Tuttavia, mantenere la possibilità di immettere un PIN di direttrice consente a un chiamante di effettuare l'autenticazione come leader e di gestire la riunione, se necessario.
    
## <a name="configure-pin-less-meeting-join"></a>Configurare l'aggiunta di riunioni senza PIN

Per abilitare la partecipazione alle riunioni senza PIN per gli utenti, utilizzare il cmdlet [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) con il parametro AllowAnonymousPstnActivation, come indicato di seguito:
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

Ad esempio, il comando seguente consente di abilitare l'aggiunta di riunioni senza PIN per il sito Redmond:
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

Per motivi di sicurezza, quando il PIN-less meeting join è attivato, è possibile che si desideri limitare l'accesso degli utenti anonimi assicurando che il ConferencingPolicy sia impostato come indicato di seguito:
  
```PowerShell
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

Per ulteriori informazioni, vedere [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
  


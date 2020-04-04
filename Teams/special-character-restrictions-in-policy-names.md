---
title: Restrizioni per i caratteri speciali nei criteri di Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policies.naming.error
- seo-marvel-mar2020
description: Informazioni sui problemi relativi ai caratteri speciali nei nomi dei criteri e sulle operazioni che è possibile eseguire per risolvere il problema.
ms.openlocfilehash: c6e41e19467f01252049c7fdc54745bcee3109d9
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140839"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>Quali sono le restrizioni dei caratteri speciali nei criteri di Teams?

**Non è possibile creare o modificare criteri (per la messaggistica, le riunioni e così via) che hanno un carattere speciale nel nome nell'interfaccia di amministrazione di Microsoft teams**. 

Se il nome di un criterio contiene caratteri speciali, sarà limitato a gestire questi criteri nell'interfaccia di amministrazione di Microsoft teams. **Di conseguenza, consigliamo vivamente che i nomi dei criteri non includano caratteri speciali**. 

I nomi dei criteri creati con PowerShell per le riunioni e la messaggistica in team possono avere caratteri speciali, ad esempio @, #, $. Tuttavia, se si vuole apportare modifiche ai criteri nell'interfaccia di amministrazione di Microsoft teams, non sarà possibile. 

Se si dispone di un criterio con caratteri speciali, sarà necessario modificare i criteri usando Windows PowerShell (per sempre) o creare un nuovo criterio nell'interfaccia di amministrazione di Microsoft teams con le stesse impostazioni dei vecchi criteri e assegnarlo allo stesso gruppo di utenti.

## <a name="to-remove-special-characters"></a>Per rimuovere caratteri speciali

**Passaggio 1: creare una connessione remota con PowerShell.** 
Se non è ancora stato [configurato, configurare il computer per Windows PowerShell](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) .
```PowerShell
 Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


**Passaggio 2: ottenere le impostazioni per i vecchi criteri e acquisire l'output.**

> [!NOTE]
> Questo esempio è per i criteri di [messaggistica](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) .  La procedura è la stessa per altri tipi di criteri, ma è necessario usare il cmdlet corretto. 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


**Passaggio 3: creare un nuovo criterio.**

Puoi creare il nuovo criterio con la stessa impostazione usando l'interfaccia di amministrazione di Microsoft teams o PowerShell.

In questo modo verrà creato un nuovo criterio, ma sarà necessario aggiungere le impostazioni corrette visualizzando [set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) e quindi eseguendolo:

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**Passaggio 4: assegnare il criterio.**
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
Per altre informazioni su questo cmdlet, vedere [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) .

**Passaggio 5-eliminare i vecchi criteri.**

Questo eliminerà il vecchio criterio con i caratteri speciali.
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
Per altre informazioni su questo cmdlet, vedere [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) .

Se il comando ha esito positivo, l'operazione è completata. Se il comando precedente restituisce un errore, è perché il criterio precedente viene assegnato agli utenti, quindi è necessario eseguire per rimuovere tutti gli utenti assegnati dal criterio:

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:
    
  - [Perché è necessario usare Office 365 PowerShell?](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Modi migliori per gestire Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre numerosi vantaggi in termini di velocità, semplicità e produttività solo con l'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti:
    
  - [Introduzione a Windows Powershell e Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Uso di Windows PowerShell per gestire Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Il modulo di Windows PowerShell per Skype for business online consente di creare una sessione remota di Windows PowerShell che si connette a Skype for business online e Microsoft teams. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  


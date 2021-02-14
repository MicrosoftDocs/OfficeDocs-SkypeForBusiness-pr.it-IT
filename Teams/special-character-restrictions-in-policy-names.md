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
description: Informazioni sui problemi relativi ai caratteri speciali nei nomi dei criteri e su cosa è possibile fare per risolverli.
ms.openlocfilehash: 899cffa45bc5ec7a36339e89e3cb97e35e6e4507
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814715"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>Quali sono le limitazioni relative ai caratteri speciali nei criteri di Teams?

Non è possibile creare o modificare i criteri **(per messaggistica,** riunioni e così via) che hanno un carattere speciale nel nome nell'interfaccia di amministrazione di Microsoft Teams. 

Se un nome di criterio contiene caratteri speciali, la gestione di questi criteri sarà limitata nell'interfaccia di amministrazione di Microsoft Teams. **Di conseguenza, è consigliabile che i nomi dei criteri non includano caratteri speciali.** 

I nomi dei criteri creati con PowerShell per le riunioni e la messaggistica in Teams possono contenere caratteri speciali come @,#,$. Tuttavia, se si vogliono apportare modifiche ai criteri nell'interfaccia di amministrazione di Microsoft Teams, non sarà possibile. 

Se si ha un criterio con caratteri speciali, sarà necessario modificare il criterio usando Windows PowerShell (sempre) o creare un nuovo criterio nell'interfaccia di amministrazione di Microsoft Teams con le stesse impostazioni del vecchio criterio e assegnarlo allo stesso gruppo di utenti.

## <a name="to-remove-special-characters"></a>Per rimuovere i caratteri speciali

**Passaggio 1 - Effettuare una connessione remota con PowerShell.**
> [!NOTE]
> Skype for Business Online Connector fa attualmente parte del più recente modulo PowerShell di Teams.
>
> Se si usa la versione pubblica più recente di [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)non è necessario installare Skype for Business Online Connector.

```PowerShell
 Import-Module -Name MicrosoftTeams
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


**Passaggio 2: ottenere le impostazioni per il criterio precedente e acquisire l'output.**

> [!NOTE]
> Questo esempio si tratta di un [criterio di messaggistica.](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps)  I passaggi sono gli stessi per altri tipi di criteri, ma è necessario usare il cmdlet corretto. 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


**Passaggio 3 - Creare un nuovo criterio.**

È possibile creare il nuovo criterio con la stessa impostazione usando l'interfaccia di amministrazione di Microsoft Teams o PowerShell.

Eseguendo questa operazione verrà creato automaticamente un nuovo criterio, ma sarà necessario aggiungere le impostazioni corrette facendo clic su [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) e quindi eseguendolo:

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**Passaggio 4- Assegnare i criteri.**
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
Per altre informazioni su questo cmdlet, [vedere Grant-CsTeamsMessagingPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps)

**Passaggio 5: eliminare i criteri vecchi.**

Il vecchio criterio con i caratteri speciali verrà eliminato.
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
Per altre [informazioni su questo cmdlet, vedere Remove-CsTeamsMessagingPolicy.](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps)

Se il comando ha esito positivo, la procedura è completata. Se il comando precedente restituisce un errore, il problema è dovuto al fatto che il vecchio criterio è assegnato agli utenti, quindi è necessario eseguirlo per rimuovere tutti gli utenti assegnati dal criterio:

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 usando un unico punto di amministrazione che consente di semplificare il lavoro quotidiano quando si hanno più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere i seguenti argomenti:
    
  - [Perché è necessario usare PowerShell di Office 365?](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Modi migliori per gestire Microsoft 365 o Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell presenta molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti:
    
  - [Introduzione a Windows Powershell e Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Uso di Windows PowerShell per gestire Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Il Windows PowerShell per Skype for Business online consente di creare una sessione Windows PowerShell remota che si connette a Skype for Business Online e Microsoft Teams. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  


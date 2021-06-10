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
description: Vedere quali problemi si verificano con caratteri speciali nei nomi dei criteri e cosa è possibile fare per risolverli.
ms.openlocfilehash: 15df8b64f423d1ee20df6e230e4a9cdbebcb56db
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116984"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>Quali sono le restrizioni speciali per i caratteri nei Teams criteri?

Non è possibile creare o modificare criteri (per messaggistica, riunioni e così via) con un carattere speciale nel nome **nell'Microsoft Teams di amministrazione.** 

Se il nome di un criterio contiene caratteri speciali, la gestione di questi criteri sarà limitata nell'interfaccia Microsoft Teams di amministrazione. **Di conseguenza, è consigliabile che i nomi dei criteri non includano caratteri speciali.** 

I nomi dei criteri creati con PowerShell per le riunioni e la messaggistica Teams possono contenere caratteri speciali come @,#,$. Tuttavia, se si vogliono apportare modifiche ai criteri nell'interfaccia di amministrazione di Microsoft Teams, non sarà possibile. 

Se si hanno criteri con caratteri speciali, è necessario modificare il criterio usando Windows PowerShell (sempre) o creare un nuovo criterio nell'interfaccia di amministrazione di Microsoft Teams con le stesse impostazioni del criterio precedente e assegnarlo allo stesso gruppo di utenti.

## <a name="to-remove-special-characters"></a>Per rimuovere caratteri speciali

**Passaggio 1 - Stabilire una connessione remota con PowerShell.**
> [!NOTE]
> Skype for Business Online Connector fa attualmente parte della versione più Teams modulo di PowerShell.
>
> Se si usa la versione pubblica più [recente Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)non è necessario installare Skype for Business Online Connector.

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```


**Passaggio 2: ottenere le impostazioni per il criterio precedente e acquisire l'output.**

> [!NOTE]
> Questo esempio è per i criteri [di](/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) messaggistica.  La procedura sarebbe la stessa per altri tipi di criteri, ma è necessario usare il cmdlet corretto. 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


**Passaggio 3- Creare un nuovo criterio.**

È possibile creare il nuovo criterio con la stessa impostazione usando l'interfaccia di amministrazione Microsoft Teams o PowerShell.

Se si esegue questa operazione, verrà creato automaticamente un nuovo criterio, ma sarà necessario aggiungere le impostazioni corrette facendo clic su [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) e quindi eseguendolo:

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**Passaggio 4 - Assegnare il criterio.**
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
Per altre informazioni su questo cmdlet, vedere [Grant-CsTeamsMessagingPolicy.](/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps)

**Passaggio 5- Eliminare il criterio precedente.**

Il criterio precedente verrà eliminato con i caratteri speciali.
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
Per altre informazioni su questo cmdlet, vedere [Remove-CsTeamsMessagingPolicy.](/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps)

Se il comando ha esito positivo, il comando è completato. Se il comando precedente restituisce un errore, il criterio precedente è assegnato agli utenti, quindi è necessario eseguire per rimuovere tutti gli utenti assegnati dal criterio:

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 usando un unico punto di amministrazione che consente di semplificare il lavoro quotidiano quando si hanno più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:
    
  - [Perché è necessario usare Office 365 PowerShell?](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso dell'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti:
    
  - [Introduzione a Windows Powershell e Skype for Business online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    [Uso di Windows PowerShell per gestire Skype for Business online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    > [!NOTE]
    > Il Windows PowerShell per Skype for Business Online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business Online e Microsoft Teams. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)

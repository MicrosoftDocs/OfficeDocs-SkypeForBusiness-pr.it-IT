---
title: Spostare le directory conferenze
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Prima di rimuovere un pool, è necessario eseguire la procedura seguente per ogni directory conferenze nel pool legacy.
ms.openlocfilehash: 8a25b955ae769a712750ff08325b3fa29538be8a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752498"
---
# <a name="move-conference-directories"></a>Spostare le directory conferenze

Prima di rimuovere il pool, è necessario eseguire la procedura seguente per ogni directory conferenze nel pool legacy.
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a>Per spostare una directory conferenze in Skype for Business Server 2019

1. Aprire la shell di gestione di Skype for Business Server.
    
2. Per ottenere l'identità delle directory conferenze nell'organizzazione, eseguire il comando riportato di seguito:
    
   ```PowerShell
   Get-CsConferenceDirectory
   ```

    Il comando precedente restituisce tutte le directory conferenze nell'organizzazione. Per questo motivo, è possibile che si desideri limitare i risultati al pool di cui è stata eseguita la rimozione. Ad esempio, se si sta rimuovendo il pool con il nome di dominio completo (FQDN) pool01.contoso.net, utilizzare questo comando per limitare i dati restituiti alle directory conferenze del pool:
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    Questo comando restituisce solo le directory conferenze in cui la proprietà ServiceID contiene il nome di dominio completo pool01.contoso.net.
    
3. Per spostare le directory conferenze, eseguire il comando riportato di seguito per ogni directory conferenze nel pool:
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    Ad esempio, per spostare la directory conferenze 3, utilizzare questo comando, specificando un pool di Skype for Business Server 2019 come TargetPool:
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    Se si desidera spostare tutte le directory conferenze in un pool, utilizzare un comando simile al seguente:
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

Scaricare la [disinstallazione di Microsoft legacy e rimuovere i ruoli del server](https://go.microsoft.com/fwlink/p/?linkId=246227) per istruzioni dettagliate sulla rimozione delle autorizzazioni dei pool legacy.
  
Quando si spostano le directory conferenze, è possibile che venga visualizzato l'errore seguente:
  
```console
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

Questo errore si verifica in genere quando Skype for Business Server Management Shell richiede un set aggiornato di autorizzazioni di Active Directory per completare un'attività. Per risolvere il problema, chiudere l'istanza corrente di Management Shell, quindi aprire una nuova istanza di Shell ed eseguire di nuovo il comando per spostare la directory conferenze.
  


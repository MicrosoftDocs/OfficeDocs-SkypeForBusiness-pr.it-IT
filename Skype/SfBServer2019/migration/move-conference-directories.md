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
ms.localizationpriority: medium
description: Prima di rimuovere un pool, è necessario eseguire la procedura seguente per ogni directory conferenze nel pool legacy.
ms.openlocfilehash: 5d4333f74c1d45e57e45c66c8de6f3e279cee01f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596150"
---
# <a name="move-conference-directories"></a>Spostare le directory conferenze

Prima di rimuovere un pool, è necessario eseguire la procedura seguente per ogni directory conferenze nel pool legacy.
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a>Per spostare una directory conferenze Skype for Business Server 2019

1. Aprire la Skype for Business Server Management Shell.
    
2. Per ottenere l'identità delle directory conferenze nell'organizzazione, eseguire il comando seguente:
    
   ```PowerShell
   Get-CsConferenceDirectory
   ```

    Il comando precedente restituisce tutte le directory conferenze dell'organizzazione. Per questo, potrebbe essere necessario limitare i risultati al pool in fase di rimozione. Ad esempio, se si sta decommissionando il pool con il nome di dominio completo (FQDN) pool01.contoso.net, utilizzare questo comando per limitare i dati restituiti alle directory conferenze da tale pool:
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    Questo comando restituisce solo le directory conferenze in cui la proprietà ServiceID contiene il nome di dominio completo pool01.contoso.net.
    
3. Per spostare le directory conferenze, eseguire il comando seguente per ogni directory conferenze del pool:
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    Ad esempio, per spostare la directory conferenze 3, utilizzare questo comando, specificando un pool Skype for Business Server 2019 come TargetPool:
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    Se si desidera spostare tutte le directory conferenze in un pool, utilizzare un comando simile al seguente:
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

Download [Uninstalling Microsoft legacy and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227) per istruzioni complete e dettagliate sulla rimozione dei pool legacy.
  
Durante lo spostamento delle directory conferenze, è possibile che si verifichi l'errore seguente:
  
```console
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

Questo errore si verifica in genere quando Skype for Business Server Management Shell richiede un set aggiornato di autorizzazioni di Active Directory per completare un'attività. Per risolvere il problema, chiudere l'istanza corrente di Management Shell, quindi aprire una nuova istanza della shell ed eseguire di nuovo il comando per spostare la directory conferenze.
  


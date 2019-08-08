---
title: Spostare le directory conferenze
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Prima di rimuovere un pool, è necessario eseguire la procedura seguente per ogni directory di conferenza nel pool legacy.
ms.openlocfilehash: cc989e752e69db31f338b493c403b8b8d4c252cc
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238081"
---
# <a name="move-conference-directories"></a>Spostare le directory conferenze

Prima di rimuovere un pool, è necessario eseguire la procedura seguente per ogni directory di conferenza nel pool legacy.
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a>Per trasferire una directory di conferenza in Skype for Business Server 2019

1. Aprire Skype for Business Server Management Shell.
    
2. Per ottenere l'identità delle directory conferenza nell'organizzazione, eseguire il comando seguente:
    
   ```
   Get-CsConferenceDirectory
   ```

    Il comando precedente restituisce tutte le directory conferenza dell'organizzazione. Per questo motivo, potresti voler limitare i risultati al pool da rimuovere. Se ad esempio si sta disattivando il pool con il nome di dominio completo (FQDN) pool01.contoso.net, usare questo comando per limitare i dati restituiti alle directory della conferenza da tale pool:
    
   ```
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    Questo comando restituisce solo le directory della conferenza in cui la proprietà ServiceID contiene il nome FQDN pool01.contoso.net.
    
3. Per trasferire le directory conferenza, eseguire il comando seguente per ogni directory di conferenza nel pool:
    
   ```
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    Ad esempio, per trasferire la directory della conferenza 3, usare questo comando specificando un pool di Skype for Business Server 2019 come TargetPool:
    
   ```
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    Se si desidera trasferire tutte le directory conferenza in un pool, usare un comando simile al seguente:
    
   ```
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

Scaricare la procedura dettagliata per la disinstallazione di [Microsoft legacy e la rimozione dei ruoli del server](https://go.microsoft.com/fwlink/p/?linkId=246227) per istruzioni dettagliate su come rimuovere i pool legacy.
  
Quando si spostano le directory conferenza, è possibile che venga visualizzato il seguente messaggio di errore:
  
```
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

Questo errore si verifica in genere quando Skype for Business Server Management Shell richiede un set aggiornato di autorizzazioni di Active Directory per completare un'attività. Per risolvere il problema, chiudere l'istanza corrente di Management Shell, quindi aprire una nuova istanza della shell ed eseguire di nuovo il comando per passare alla directory della conferenza.
  


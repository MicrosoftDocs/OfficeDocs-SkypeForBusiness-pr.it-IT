---
title: Patch o aggiornare un server back-end o un server Standard Edition in Skype for Business Server
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
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 'Riepilogo: informazioni su come installare un aggiornamento o una patch su un server back-end in Skype for Business Server.'
ms.openlocfilehash: 3e5e0cda1604f3144e853cfa3bf7bcc45e7d0c2f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826306"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a>Patch o aggiornare un server back-end o un server Standard Edition in Skype for Business Server
 
**Riepilogo:** Informazioni su come installare un aggiornamento o una patch su un server back-end in Skype for Business Server.
  
In questo argomento viene descritto come installare un aggiornamento in un server di back-end Enterprise Edition o in un server Standard Edition.
  
Se un server back-end è inverso verso il basso per almeno 30 minuti mentre lo si sta aggiornando, gli utenti possono accedere alla modalità di resilienza. Al termine dell'aggiornamento e i server back-end sono di nuovo connessi con i Front End Server nel pool, gli utenti vengono restituiti alla funzionalità completa. Se l'aggiornamento richiede meno di 30 minuti, gli utenti non saranno coinvolti.
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a>Per aggiornare un server back-end o un server Standard Edition

1. Eseguire l'accesso al server da aggiornare come membro del ruolo CsAdministrator.
    
2. Scaricare l'aggiornamento ed estrarlo nel disco rigido locale.
    
3. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business** e quindi su **Skype for Business Server Management Shell**.
    
4. Interrompere i servizi di Skype for Business Server. Nella riga di comando digitare il comando seguente:
    
    ```PowerShell
    Stop-CsWindowsService
    ```

5. Arrestare il servizio World Wide Web. Nella riga di comando digitare:
    
    ```PowerShell
    net stop w3svc
   ```

6. Chiudere tutte le finestre di Windows Management Shell di Skype for Business Server.
    
7. Installare l'aggiornamento.
    
8. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business** e quindi su **Skype for Business Server Management Shell**.
    
9. Arrestare di nuovo i servizi di Skype for Business Server per individuare gli assembly Global Assembly Cache (GAC)-d. Nella riga di comando digitare:
    
    ```PowerShell
    Stop-CsWindowsService
    ```

10. Riavviare il servizio World Wide Web. Nella riga di comando digitare:
    
    ```PowerShell
    net start w3svc
    ```

11. Applicare le modifiche apportate ai database di SQL Server eseguendo una delle operazioni seguenti:
    
    - Se si tratta di un server back-end Enterprise Edition e non sono presenti database collocati nel server, ad esempio i database di archiviazione o di monitoraggio, digitare quanto segue nella riga di comando:
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - Se si tratta di un server back-end Enterprise Edition e sono presenti database collocati nel server, digitare quanto segue nella riga di comando:
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - Se si tratta di un server Standard Edition, digitare quanto segue nella riga di comando:
    
    ```PowerShell
    Install-CsDatabase -Update -LocalDatabases

    ```

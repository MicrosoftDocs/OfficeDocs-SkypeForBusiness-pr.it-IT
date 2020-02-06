---
title: Patch o aggiornamento di un server di back-end o di un server Standard Edition in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 'Riepilogo: informazioni su come installare un aggiornamento o una patch in un server back-end in Skype for Business Server.'
ms.openlocfilehash: 62c7a0c2e0c958e9f3e6c566d9e73a35d1dd945a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817097"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a>Patch o aggiornamento di un server di back-end o di un server Standard Edition in Skype for Business Server
 
**Riepilogo:** Informazioni su come installare un aggiornamento o una patch in un server back-end in Skype for Business Server.
  
Questo argomento spiega come installare un aggiornamento in un server back-end Enterprise Edition o in un server Standard Edition.
  
Se un server di back-end è in calo per almeno 30 minuti durante l'aggiornamento, gli utenti possono passare alla modalità resilienza. Al termine dell'aggiornamento e i server back-end sono di nuovo connessi con i server front-end nel pool, gli utenti vengono restituiti alla funzionalità completa. Se l'aggiornamento richiede meno di 30 minuti, gli utenti non saranno interessati.
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a>Per aggiornare un server back-end o un server Standard Edition

1. Accedere al server da aggiornare come membro del ruolo CsAdministrator.
    
2. Scaricare l'aggiornamento ed estrarlo nel disco rigido locale.
    
3. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business**e quindi su **Skype for Business Server Management Shell**.
    
4. Interrompere i servizi di Skype for Business Server. Nella riga di comando digitare:
    
    ```PowerShell
    Stop-CsWindowsService
    ```

5. Arrestare il servizio World Wide Web. Nella riga di comando digitare:
    
    ```PowerShell
    net stop w3svc
   ```

6. Chiudere tutte le finestre di Windows Management Shell di Skype for Business Server.
    
7. Installare l'aggiornamento.
    
8. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business**e quindi su **Skype for Business Server Management Shell**.
    
9. Interrompi di nuovo i servizi di Skype for Business Server per intercettare assembly della cache globale degli assembly (GAC)-d. Nella riga di comando digitare:
    
    ```PowerShell
    Stop-CsWindowsService
    ```

10. Riavviare il servizio World Wide Web. Nella riga di comando digitare:
    
    ```PowerShell
    net start w3svc
    ```

11. Applicare le modifiche apportate ai database di SQL Server eseguendo una delle operazioni seguenti:
    
    - Se si tratta di un server back-end Enterprise Edition e non sono presenti database collocati nel server, ad esempio l'archiviazione o il monitoraggio dei database, digitare quanto segue nella riga di comando:
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - Se si tratta di un server back-end Enterprise Edition e in questo server sono presenti database collocati, digitare quanto segue nella riga di comando:
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - Se si tratta di un server Standard Edition, digitare quanto segue nella riga di comando:
    
    ```PowerShell
    Install-CsDatabase -Update -LocalDatabases

    ```

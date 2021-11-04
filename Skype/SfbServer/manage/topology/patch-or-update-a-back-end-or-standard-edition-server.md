---
title: Applicare patch o aggiornare un server back-end o edizione Standard server in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 'Riepilogo: informazioni su come installare un aggiornamento o una patch in un server back-end in Skype for Business Server.'
ms.openlocfilehash: 6c2a03358f5fc5f1253f65d1ff2bc202871da678
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60737782"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a>Applicare patch o aggiornare un server back-end o edizione Standard server in Skype for Business Server
 
**Riepilogo:** Informazioni su come installare un aggiornamento o una patch in un server back-end in Skype for Business Server.
  
In questo argomento viene illustrato come installare un aggiornamento in un server edizione Enterprise back-end o edizione Standard server.
  
Se un server back-end non è disponibile per almeno 30 minuti durante l'aggiornamento, gli utenti possono passare alla modalità resilienza. Al termine dell'aggiornamento e i server back-end si sono nuovamente connessi ai Front End Server nel pool, gli utenti vengono restituiti alla funzionalità completa. Se l'aggiornamento richiede meno di 30 minuti, gli utenti non ne saranno interessati.
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a>Per aggiornare un server back-end o edizione Standard server

1. Eseguire l'accesso al server da aggiornare come membro del ruolo CsAdministrator.
    
2. Scaricare l'aggiornamento ed estrarlo nel disco rigido locale.
    
3. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business** e quindi fare clic su Skype for Business Server **Management Shell**..
    
4. Arrestare Skype for Business Server servizi. Nella riga di comando digitare il comando seguente:
    
    ```PowerShell
    Stop-CsWindowsService
    ```

5. Arrestare il servizio World Wide Web. Nella riga di comando digitare:
    
    ```PowerShell
    net stop w3svc
   ```

6. Chiudere tutte Skype for Business Server Management Shell.
    
7. Installare l'aggiornamento.
    
8. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business** e quindi fare clic su Skype for Business Server **Management Shell.**
    
9. Arrestare Skype for Business Server servizi per intercettare gli assembly -d della Global Assembly Cache (GAC). Nella riga di comando digitare:
    
    ```PowerShell
    Stop-CsWindowsService
    ```

10. Riavviare il servizio World Wide Web. Nella riga di comando digitare:
    
    ```PowerShell
    net start w3svc
    ```

11. Applicare le modifiche apportate ai SQL Server database eseguendo una delle operazioni seguenti:
    
    - Se si tratta di un edizione Enterprise back-end server e non sono presenti database collocati nel server, ad esempio database di archiviazione o di monitoraggio, digitare quanto segue nella riga di comando:
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - Se si tratta di edizione Enterprise server back-end e sono presenti database collocati nel server, digitare quanto segue in una riga di comando:
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - Se si tratta di un server edizione Standard, digitare quanto segue in una riga di comando:
    
    ```PowerShell
    Install-CsDatabase -Update -LocalDatabases

    ```

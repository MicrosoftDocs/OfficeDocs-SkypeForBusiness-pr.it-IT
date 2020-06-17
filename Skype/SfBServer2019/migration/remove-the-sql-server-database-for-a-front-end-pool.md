---
title: Rimuovere il database di SQL Server per un pool Front End
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
description: Dopo la rimozione di un pool Front end o la riconfigurazione del pool per l'utilizzo di un database diverso, è possibile rimuovere i database di SQL Server che ospitano i dati del pool. Utilizzare le procedure seguenti per rimuovere le definizioni da generatore di topologie, quindi rimuovere il database e i file di registro dal server di database.
ms.openlocfilehash: 9047486708b92c07e6ec099fce43ec4c708fa900
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753408"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>Rimuovere il database di SQL Server per un pool Front End

Dopo la rimozione di un pool Front end o la riconfigurazione del pool per l'utilizzo di un database diverso, è possibile rimuovere i database di SQL Server che ospitano i dati del pool. Utilizzare le procedure seguenti per rimuovere le definizioni da generatore di topologie, quindi rimuovere il database e i file di registro dal server di database.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Per rimuovere il database di SQL Server tramite Generatore di topologie

1. Dal front end server di Skype for Business Server 2019, aprire Generatore di topologie e scaricare la topologia esistente. 
    
2. In Generatore di topologie, passare a **componenti condivisi** e quindi a **SQL Server Store**, fare clic con il pulsante destro del mouse sull'istanza di SQL Server associata al pool Front End rimosso o riconfigurato, quindi fare clic su **Elimina**.
    
3. Pubblicare la topologia, quindi verificare lo stato della replica. 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>Per rimuovere i database dell'utente e dell'applicazione da SQL Server

1. Per rimuovere i database di SQL Server, è necessario essere membri del gruppo sysadmins di SQL Server per SQL Server in cui si stanno rimuovendo i file di database. 
    
2. Aprire Skype for Business Server Management Shell.
    
3. Per rimuovere il database dall'archivio utenti del pool, digitare:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Dove _\<FQDN\>_ è il nome di dominio completo (FQDN) del server di database e _\<instance\>_ è l'istanza di database denominata, se ne è stata definita una. 
    
4. Per rimuovere il database dall'archivio applicazioni del pool, digitare:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Dove _\<FQDN\>_ è il nome di dominio completo del server di database e _\<instance\>_ è l'istanza di database denominata, se ne è stata definita una. 
    
5. Quando il cmdlet **Uninstall-CsDatabase** richiede di confermare le azioni, leggere le informazioni e quindi premere Y (o invio) per continuare oppure N e quindi immettere se si desidera arrestare il cmdlet (in caso di errori). 
    


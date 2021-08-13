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
description: Dopo aver rimosso un pool Front End o aver riconfigurato il pool per l'utilizzo di un database diverso, è possibile rimuovere i database SQL Server che ospitavano i dati del pool. Utilizzare le procedure seguenti per rimuovere le definizioni da Generatore di topologie e quindi rimuovere i file di database e di registro dal server di database.
ms.openlocfilehash: 01a28beabb85aa7cda25043680537f519872d58654dee5418f03ae9f5f702a19
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340322"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>Rimuovere il database di SQL Server per un pool Front End

Dopo aver rimosso un pool Front End o aver riconfigurato il pool per l'utilizzo di un database diverso, è possibile rimuovere i database SQL Server che ospitavano i dati del pool. Utilizzare le procedure seguenti per rimuovere le definizioni da Generatore di topologie e quindi rimuovere i file di database e di registro dal server di database.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Per rimuovere il database SQL Server utilizzando Generatore di topologie

1. Dal Front End Server Skype for Business Server 2019 aprire Generatore di topologie e scaricare la topologia esistente. 
    
2. In Generatore di topologie  passare a Componenti condivisi e quindi **SQL Server Archivi,** fare clic con il pulsante destro del mouse sull'istanza di SQL Server associata al pool Front End rimosso o riconfigurato e quindi scegliere **Elimina.**
    
3. Pubblicare la topologia, quindi verificare lo stato della replica. 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>Per rimuovere i database di utenti e applicazioni dal server SQL server

1. Per rimuovere i database nel server SQL, è necessario essere membri del gruppo sysadmins di SQL Server per il server SQL in cui si desidera rimuovere i file di database. 
    
2. Aprire Skype for Business Server Management Shell.
    
3. Per rimuovere il database dall'archivio utenti del pool, digitare:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Dove è il nome di dominio completo (FQDN) del server di database e è l'istanza di database denominata, ovvero se ne è  _\<FQDN\>_  _\<instance\>_ stata definita una. 
    
4. Per rimuovere il database dall'archivio applicazioni del pool, digitare:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Dove è il nome di dominio completo del server di database e è l'istanza di database denominata, ovvero  _\<FQDN\>_ se ne è stata definita  _\<instance\>_ una. 
    
5. Quando il cmdlet **Uninstall-CsDataBase** richiede di confermare le azioni, leggere le informazioni e quindi premere Y (o INVIO) per procedere oppure premere N e quindi INVIO se si desidera arrestare il cmdlet (in caso di errori). 
    


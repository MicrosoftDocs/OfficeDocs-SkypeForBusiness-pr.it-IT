---
title: Rimuovere il database di SQL Server per un server di archiviazione
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
description: Dopo aver rimosso un server di archiviazione, è possibile rimuovere SQL Server database che ospitavano i dati del pool. Utilizzare le procedure seguenti per rimuovere le definizioni da Generatore di topologie e quindi rimuovere i file di database e di registro dal server di database.
ms.openlocfilehash: 3b0b41944941cd6984dec72c52405a1bce63fd8bff87e14cfd94fc723e262d49
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54279564"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a>Rimuovere il database di SQL Server per un server di archiviazione

Dopo aver rimosso un server di archiviazione, è possibile rimuovere SQL Server database che ospitavano i dati del pool. Utilizzare le procedure seguenti per rimuovere le definizioni da Generatore di topologie e quindi rimuovere i file di database e di registro dal server di database.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Per rimuovere il database SQL Server utilizzando Generatore di topologie

1. Nel Front End Server Skype for Business Server 2019 aprire Generatore di topologie.
    
2. In Generatore di topologie  passare a Componenti condivisi e quindi **SQL Server Archivi,** fare clic con il pulsante destro del mouse sull'istanza di SQL Server associata al server di archiviazione rimosso o riconfigurato e quindi scegliere **Elimina**.
    
3. Pubblicare la topologia, quindi verificare lo stato della replica. 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>Per rimuovere i file di database da SQL Server

1. Per rimuovere i database contenuti nell'istanza di SQL Server, è necessario essere membri del gruppo sysadmins di SQL Server per l'istanza di SQL Server da cui si desidera rimuovere i file di database. 
    
2. Aprire la Skype for Business Server Management Shell.
    
3. Nella riga di comando digitare quanto segue:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Dove è il nome di dominio completo (FQDN) del server di database e è l'istanza di database denominata, ovvero se ne è  _\<FQDN\>_  _\<instance\>_ stata definita una. 
    
4. Quando il cmdlet **Uninstall-CsDataBase** richiede di confermare le azioni, leggere le informazioni e quindi premere Y (o INVIO) per procedere oppure premere N e quindi INVIO se si desidera arrestare il cmdlet (in caso di errori). 
    


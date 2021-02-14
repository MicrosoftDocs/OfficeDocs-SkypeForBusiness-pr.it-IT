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
description: Dopo aver rimosso un server di archiviazione, è possibile rimuovere SQL Server database che ospitavano i dati del pool. Utilizzare le procedure seguenti per rimuovere le definizioni dal Generatore di topologie e quindi rimuovere i file di database e di registro dal server di database.
ms.openlocfilehash: f8a08b7ea73fa954726bdef986e5a28919c90ceb
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753308"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a>Rimuovere il database di SQL Server per un server di archiviazione

Dopo aver rimosso un server di archiviazione, è possibile rimuovere SQL Server database che ospitavano i dati del pool. Utilizzare le procedure seguenti per rimuovere le definizioni dal Generatore di topologie e quindi rimuovere i file di database e di registro dal server di database.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Per rimuovere il database SQL Server utilizzando Generatore di topologie

1. Nel Front End Server di Skype for Business Server 2019 aprire Generatore di topologie.
    
2. In Generatore di topologie  passare a Componenti condivisi e quindi **SQL Server Archivi,** fare clic con il pulsante destro del mouse sull'istanza di SQL Server associata al server di archiviazione rimosso o riconfigurato e quindi scegliere **Elimina.**
    
3. Pubblicare la topologia, quindi verificare lo stato della replica. 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>Per rimuovere i file di database da SQL Server

1. Per rimuovere i database contenuti nell'istanza di SQL Server, è necessario essere membri del gruppo sysadmins di SQL Server per l'istanza di SQL Server da cui si desidera rimuovere i file di database. 
    
2. Aprire Skype for Business Server Management Shell.
    
3. Nella riga di comando digitare quanto segue:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Dove è il nome di dominio completo (FQDN) del server di database ed è l'istanza di database denominata, ovvero se ne è  _\<FQDN\>_  _\<instance\>_ stata definita una. 
    
4. Quando il cmdlet **Uninstall-CsDataBase** richiede di confermare le azioni, leggere le informazioni e quindi premere Y (o INVIO) per continuare oppure premere N e invio se si desidera arrestare il cmdlet (se sono presenti errori). 
    


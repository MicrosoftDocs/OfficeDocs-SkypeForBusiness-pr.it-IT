---
title: Rimuovere il database di SQL Server per un server di monitoraggio
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
description: Dopo aver rimosso un Monitoring Server, è possibile rimuovere SQL Server database che ospitavano i dati del server. Utilizzare le procedure seguenti per rimuovere le definizioni da Generatore di topologie e quindi rimuovere i file di database e di registro dal server di database.
ms.openlocfilehash: cadb24e2dcbe88e643c234dd8559d07406e5566e3e7eea0e33eec796cd98cf52
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54280391"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a>Rimuovere il database di SQL Server per un server di monitoraggio

Dopo aver rimosso un Monitoring Server, è possibile rimuovere SQL Server database che ospitavano i dati del server. Utilizzare le procedure seguenti per rimuovere le definizioni da Generatore di topologie e quindi rimuovere i file di database e di registro dal server di database.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Per rimuovere il database SQL Server utilizzando Generatore di topologie

1. Nel Front End Server Skype for Business Server 2019 aprire Generatore di topologie.
    
2. In Generatore di topologie  passare a Componenti condivisi e quindi **SQL Server Archivi,** fare clic con il pulsante destro del mouse sull'istanza di SQL Server associata al Monitoring Server rimosso o riconfigurato e quindi scegliere **Elimina.**
    
3. Pubblicare la topologia, quindi verificare lo stato della replica.
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>Per rimuovere i file di database da SQL Server

1. Per rimuovere i database dal server basato su SQL Server, è necessario essere un membro del gruppo sysadmins nel server SQL Server in cui vengono rimossi i file di database.
    
2. Aprire la Skype for Business Server Management Shell.
    
3. Nella riga di comando digitare quanto segue:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Dove  _\<FQDN\>_ è il nome di dominio completo (FQDN) del server di database ed è  _\<instance\>_ l'istanza di database denominata facoltativa. 
    
4. Quando il cmdlet **Uninstall-CsDataBase** richiede di confermare le azioni, leggere le informazioni e quindi premere Y (o INVIO) per procedere oppure premere N e quindi INVIO se si desidera arrestare il cmdlet (in caso di errori). 
    


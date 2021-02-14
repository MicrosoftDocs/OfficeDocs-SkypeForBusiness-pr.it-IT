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
description: Dopo aver rimosso un Monitoring Server, è possibile rimuovere SQL Server database che ospitavano i dati del server. Utilizzare le procedure seguenti per rimuovere le definizioni dal Generatore di topologie e quindi rimuovere i file di database e di registro dal server di database.
ms.openlocfilehash: 829e55175c9b9c85582aafe996bbbee0afdffa62
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753328"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a>Rimuovere il database di SQL Server per un server di monitoraggio

Dopo aver rimosso un Monitoring Server, è possibile rimuovere SQL Server database che ospitavano i dati del server. Utilizzare le procedure seguenti per rimuovere le definizioni dal Generatore di topologie e quindi rimuovere i file di database e di registro dal server di database.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Per rimuovere il database SQL Server utilizzando Generatore di topologie

1. Nel Front End Server di Skype for Business Server 2019 aprire Generatore di topologie.
    
2. In Generatore di topologie  passare a Componenti condivisi e quindi **SQL Server Archivi,** fare clic con il pulsante destro del mouse sull'istanza di SQL Server associata al Monitoring Server rimosso o riconfigurato e quindi scegliere **Elimina.**
    
3. Pubblicare la topologia, quindi verificare lo stato della replica.
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>Per rimuovere i file di database da SQL Server

1. Per rimuovere i database dal server basato su SQL Server, è necessario essere un membro del gruppo sysadmins nel server SQL Server in cui vengono rimossi i file di database.
    
2. Aprire Skype for Business Server Management Shell.
    
3. Nella riga di comando digitare quanto segue:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Dove è il nome di dominio completo (FQDN) del server di database ed  _\<FQDN\>_ è l'istanza di database denominata  _\<instance\>_ facoltativa. 
    
4. Quando il cmdlet **Uninstall-CsDataBase** richiede di confermare le azioni, leggere le informazioni e quindi premere Y (o INVIO) per continuare oppure premere N e invio se si desidera arrestare il cmdlet (se sono presenti errori). 
    


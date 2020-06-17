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
description: Dopo aver rimosso un Monitoring Server, è possibile rimuovere i database di SQL Server in cui sono stati ospitati i dati del server. Utilizzare le procedure seguenti per rimuovere le definizioni da generatore di topologie, quindi rimuovere il database e i file di registro dal server di database.
ms.openlocfilehash: 829e55175c9b9c85582aafe996bbbee0afdffa62
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753328"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a>Rimuovere il database di SQL Server per un server di monitoraggio

Dopo aver rimosso un Monitoring Server, è possibile rimuovere i database di SQL Server in cui sono stati ospitati i dati del server. Utilizzare le procedure seguenti per rimuovere le definizioni da generatore di topologie, quindi rimuovere il database e i file di registro dal server di database.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Per rimuovere il database di SQL Server tramite Generatore di topologie

1. Nel server front end di Skype for Business Server 2019 aprire Generatore di topologie.
    
2. In Generatore di topologie, passare a **componenti condivisi** e quindi a **SQL Server Store**, fare clic con il pulsante destro del mouse sull'istanza di SQL Server associata al Monitoring Server rimosso o riconfigurato, quindi fare clic su **Elimina**.
    
3. Pubblicare la topologia, quindi verificare lo stato della replica.
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>Per rimuovere i file di database da SQL Server

1. Per rimuovere i database dal server basato su SQL Server, è necessario essere un membro del gruppo sysadmins nel server SQL Server in cui vengono rimossi i file di database.
    
2. Aprire la shell di gestione di Skype for Business Server.
    
3. Nella riga di comando digitare quanto segue:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Dove _\<FQDN\>_ è il nome di dominio completo (FQDN) del server di database e _\<instance\>_ è l'istanza di database denominata facoltativa. 
    
4. Quando il cmdlet **Uninstall-CsDatabase** richiede di confermare le azioni, leggere le informazioni e quindi premere Y (o invio) per continuare oppure N e quindi immettere se si desidera arrestare il cmdlet (in caso di errori). 
    


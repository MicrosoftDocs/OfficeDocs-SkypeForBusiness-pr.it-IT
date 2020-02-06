---
title: Rimuovere il database di SQL Server per un server di monitoraggio
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Dopo aver rimosso un server di monitoraggio, è possibile rimuovere i database di SQL Server che ospitavano i dati del server. Usare le procedure seguenti per rimuovere le definizioni da generatore di topologie e quindi rimuovere il database e i file di log dal server di database.
ms.openlocfilehash: 275c69f2c35428bcff2d12799cad3fbc129abc23
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812824"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a>Rimuovere il database di SQL Server per un server di monitoraggio

Dopo aver rimosso un server di monitoraggio, è possibile rimuovere i database di SQL Server che ospitavano i dati del server. Usare le procedure seguenti per rimuovere le definizioni da generatore di topologie e quindi rimuovere il database e i file di log dal server di database.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Per rimuovere il database di SQL Server tramite Generatore di topologie

1. Nel server front-end di Skype for Business Server 2019 aprire Generatore di topologia.
    
2. In Generatore di topologie passare a **componenti condivisi** e quindi **archiviare SQL Server**, fare clic con il pulsante destro del mouse sull'istanza di SQL Server associata al server di monitoraggio rimosso o riconfigurato e quindi scegliere **Elimina**.
    
3. Pubblicare la topologia e quindi controllare lo stato della replica.
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>Per rimuovere i file di database da SQL Server

1. Per rimuovere i database nel server basato su SQL Server, è necessario essere membri del gruppo sysadmin di SQL Server per il server SQL Server in cui si stanno rimuovendo i file di database.
    
2. Aprire Skype for Business Server Management Shell.
    
3. Nella riga di comando digitare quanto segue:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Dove _ \<FQDN\> _ è il nome di dominio completo (FQDN) del server di database e _ \<instance\> _ è l'istanza di database denominata facoltativa. 
    
4. Quando il cmdlet **Uninstall-CsDatabase** richiede di confermare le azioni, leggere le informazioni e quindi premere Y (o invio) per procedere oppure premere N e quindi immettere se si vuole arrestare il cmdlet (in caso di errori). 
    


---
title: Rimuovere il database di SQL Server per un server di archiviazione
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Dopo aver rimosso un server di archiviazione, è possibile rimuovere i database di SQL Server che ospitavano i dati del pool. Usare le procedure seguenti per rimuovere le definizioni da generatore di topologie e quindi rimuovere il database e i file di log dal server di database.
ms.openlocfilehash: ab76c8ebc629206827be0a4c0a5477eff54a0923
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36241815"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a>Rimuovere il database di SQL Server per un server di archiviazione

Dopo aver rimosso un server di archiviazione, è possibile rimuovere i database di SQL Server che ospitavano i dati del pool. Usare le procedure seguenti per rimuovere le definizioni da generatore di topologie e quindi rimuovere il database e i file di log dal server di database.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Per rimuovere il database di SQL Server tramite Generatore di topologie

1. Nel server front-end di Skype for Business Server 2019 aprire Generatore di topologia.
    
2. In Generatore di topologie passare a **componenti condivisi** e quindi **archiviare SQL Server**, fare clic con il pulsante destro del mouse sull'istanza di SQL Server associata al server di archiviazione rimosso o riconfigurato e quindi scegliere **Elimina**.
    
3. Pubblicare la topologia e quindi controllare lo stato della replica. 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>Per rimuovere i file di database da SQL Server

1. Per rimuovere i database di SQL Server, è necessario essere membri del gruppo sysadmin di SQL Server per SQL Server in cui si stanno rimuovendo i file di database. 
    
2. Aprire Skype for Business Server Management Shell.
    
3. Nella riga di comando digitare quanto segue:
    
   ```
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Dove _ \<FQDN\> _ è il nome di dominio completo (FQDN) del server di database e _ \<instance\> _ è l'istanza di database denominata, ovvero se ne è stata definita una. 
    
4. Quando il cmdlet **Uninstall-CsDatabase** richiede di confermare le azioni, leggere le informazioni e quindi premere Y (o invio) per procedere oppure premere N e quindi immettere se si vuole arrestare il cmdlet (in caso di errori). 
    


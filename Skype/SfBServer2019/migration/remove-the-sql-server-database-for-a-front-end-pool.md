---
title: Rimuovere il database di SQL Server per un pool Front End
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Dopo aver rimosso un pool Front-end o aver riconfigurato il pool per l'uso di un database diverso, è possibile rimuovere i database di SQL Server che ospitavano i dati del pool. Usare le procedure seguenti per rimuovere le definizioni da generatore di topologie e quindi rimuovere il database e i file di log dal server di database.
ms.openlocfilehash: f26cf1f93abb8538c068a4ab2d6f81c9c36d759d
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40989091"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>Rimuovere il database di SQL Server per un pool Front End

Dopo aver rimosso un pool Front-end o aver riconfigurato il pool per l'uso di un database diverso, è possibile rimuovere i database di SQL Server che ospitavano i dati del pool. Usare le procedure seguenti per rimuovere le definizioni da generatore di topologie e quindi rimuovere il database e i file di log dal server di database.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Per rimuovere il database di SQL Server tramite Generatore di topologie

1. Dal server front-end di Skype for Business Server 2019 aprire Generatore di topologie e scaricare la topologia esistente. 
    
2. In Generatore di topologie passare a **componenti condivisi** e quindi **archiviare SQL Server**, fare clic con il pulsante destro del mouse sull'istanza di SQL Server associata al pool di front-end rimosso o riconfigurato e quindi scegliere **Elimina**.
    
3. Pubblicare la topologia e quindi controllare lo stato della replica. 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>Per rimuovere i database di utenti e applicazioni da SQL Server

1. Per rimuovere i database di SQL Server, è necessario essere membri del gruppo sysadmin di SQL Server per SQL Server in cui si stanno rimuovendo i file di database. 
    
2. Aprire Skype for Business Server Management Shell.
    
3. Per rimuovere il database per l'archivio utenti del pool, digitare:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Dove _ \<FQDN\> _ è il nome di dominio completo (FQDN) del server di database e _ \<instance\> _ è l'istanza di database denominata, ovvero se ne è stata definita una. 
    
4. Per rimuovere il database per l'archivio delle applicazioni del pool, digitare:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Dove _ \<FQDN\> _ è il nome di dominio completo del server di database e _ \<instance\> _ è l'istanza di database denominata, ovvero se ne è stata definita una. 
    
5. Quando il cmdlet **Uninstall-CsDatabase** richiede di confermare le azioni, leggere le informazioni e quindi premere Y (o invio) per procedere oppure premere N e quindi immettere se si vuole arrestare il cmdlet (in caso di errori). 
    


---
title: Rimuovere il database di SQL Server per un pool Front End
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
description: Dopo aver rimosso un pool Front-end o aver riconfigurato il pool per l'uso di un database diverso, è possibile rimuovere i database di SQL Server che ospitavano i dati del pool. Usare le procedure seguenti per rimuovere le definizioni da generatore di topologie e quindi rimuovere il database e i file di log dal server di database.
ms.openlocfilehash: 8644760f9f3a18f737fcccd80e20eb091efe2f4b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812854"
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
    


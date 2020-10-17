---
title: Rimuovere il database di SQL Server per un server di archiviazione
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for an Archiving server
ms:assetid: 6e8a1fcd-ed09-43b0-82c9-60e7ce116a01
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688087(v=OCS.15)
ms:contentKeyID: 49733686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fab9cefc3fff51267426fd26263f9e2ec20a85ee
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518103"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a>Rimuovere il database di SQL Server per un server di archiviazione

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-04_

Dopo aver rimosso un server di archiviazione di Microsoft Lync Server 2010, è possibile rimuovere i database di SQL Server che ospitano i dati del pool. Utilizzare le procedure seguenti per rimuovere le definizioni da generatore di topologie, quindi rimuovere il database e i file di registro dal server di database.

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Per rimuovere il database di SQL Server tramite Generatore di topologie

1.  Nel server front-end Lync Server 2013 aprire Generatore di topologie.

2.  In Generatore di topologie, passare a **componenti condivisi** e quindi a **SQL Server Store**, fare clic con il pulsante destro del mouse sull'istanza di SQL Server associata al server di archiviazione rimosso o riconfigurato, quindi fare clic su **Elimina**.

3.  Pubblicare la topologia, quindi verificare lo stato della replica.

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a>Per rimuovere i file di database da SQL Server

1.  Per rimuovere i database contenuti nell'istanza di SQL Server, è necessario essere membri del gruppo sysadmins di SQL Server per l'istanza di SQL Server da cui si desidera rimuovere i file di database.

2.  Aprire Lync Server Management Shell.

3.  Nella riga di comando digitare quanto segue:
    
        Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    Dove \<FQDN\> è il nome di dominio completo (FQDN) del server di database e \<instance\> è l'istanza di database denominata, se ne è stata definita una.

4.  Quando il cmdlet **Uninstall-CsDataBase** richiede di confermare le azioni, leggere le informazioni e quindi premere **S** (o INVIO) per procedere oppure **N** e quindi INVIO per arrestare il cmdlet (in caso di errori).

</div>

</div>

<span> </span>

</div>

</div>

</div>


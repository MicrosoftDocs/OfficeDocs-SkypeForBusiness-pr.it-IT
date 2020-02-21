---
title: Rimuovere il database di SQL Server per un pool Front End
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for a Front End pool
ms:assetid: 6bb932df-3ed7-49b6-ae17-61e4c6a5fe82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688084(v=OCS.15)
ms:contentKeyID: 49733681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a69972d355ad2870445af14ccfeb097f1d8a6dcb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189399"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>Rimuovere il database di SQL Server per un pool Front End

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-04_

Dopo la rimozione di un pool Front End di Microsoft Lync Server 2010 o la riconfigurazione del pool per l'utilizzo di un database diverso, è possibile rimuovere i database di SQL Server che ospitano i dati del pool. Utilizzare le procedure seguenti per rimuovere le definizioni da generatore di topologie, quindi rimuovere il database e i file di registro dal server di database.

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Per rimuovere il database di SQL Server tramite Generatore di topologie

1.  Dal front end server Lync Server 2013 aprire Generatore di topologie e scaricare la topologia esistente.

2.  In Generatore di topologie, passare a **componenti condivisi** e quindi a **SQL Server Store**, fare clic con il pulsante destro del mouse sull'istanza di SQL Server associata al pool Front End rimosso o riconfigurato, quindi fare clic su **Elimina**.

3.  Pubblicare la topologia, quindi verificare lo stato della replica.

</div>

<div>

## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>Per rimuovere i database degli utenti e delle applicazioni da SQL Server

1.  Per rimuovere i database in SQL Server, è necessario essere un membro del gruppo sysadmins di SQL Server per il server SQL Server in cui si desidera rimuovere i file di database.

2.  Aprire Lync Server Management Shell

3.  Per rimuovere il database dall'archivio utenti del pool, digitare:
    
        Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    Dove \<FQDN\> è il nome di dominio completo (FQDN) del server di database e \<instance\> è l'istanza di database denominata, se ne è stata definita una.

4.  Per rimuovere il database dall'archivio applicazioni del pool, digitare:
    
        Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    Dove \<FQDN\> è il nome di dominio completo del server di \<database\> e instance è l'istanza di database denominata, se ne è stata definita una.

5.  Quando il cmdlet **Uninstall-CsDataBase** richiede di confermare le azioni, leggere le informazioni e quindi premere **S** (o INVIO) per procedere oppure **N** e quindi INVIO per arrestare il cmdlet (in caso di errori).

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Rimuovere il database di SQL Server per un pool Front End
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove the SQL Server database for a Front End pool
ms:assetid: 6bb932df-3ed7-49b6-ae17-61e4c6a5fe82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688084(v=OCS.15)
ms:contentKeyID: 49733681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6dcbe9bcab20438d02fe489666f9b4c0c0f6d0b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979646"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>Rimuovere il database di SQL Server per un pool Front End

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-04_

Dopo aver rimosso un pool di front end di Microsoft Lync Server 2010 o aver riconfigurato il pool per l'uso di un database diverso, è possibile rimuovere i database di SQL Server che ospitavano i dati del pool. Usare le procedure seguenti per rimuovere le definizioni da generatore di topologie e quindi rimuovere il database e i file di log dal server di database.

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Per rimuovere il database di SQL Server tramite Generatore di topologie

1.  Dal server front-end di Lync Server 2013 aprire Generatore di topologia e scaricare la topologia esistente.

2.  In Generatore di topologie passare a **componenti condivisi** e quindi **archiviare SQL Server**, fare clic con il pulsante destro del mouse sull'istanza di SQL Server associata al pool di front-end rimosso o riconfigurato e quindi scegliere **Elimina**.

3.  Pubblicare la topologia e quindi controllare lo stato della replica.

</div>

<div>

## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>Per rimuovere i database di utenti e applicazioni da SQL Server

1.  Per rimuovere i database di SQL Server, è necessario essere membri del gruppo sysadmin di SQL Server per SQL Server in cui si stanno rimuovendo i file di database.

2.  Aprire Lync Server Management Shell

3.  Per rimuovere il database per l'archivio utenti del pool, digitare:
    
        Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    Dove \<FQDN\> è il nome di dominio completo (FQDN) del server di database e \<instance\> è l'istanza di database denominata, ovvero se ne è stata definita una.

4.  Per rimuovere il database per l'archivio delle applicazioni del pool, digitare:
    
        Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    Dove \<FQDN\> è il nome di dominio completo del server di \<database\> e instance è l'istanza di database denominata, ovvero se ne è stata definita una.

5.  Quando il cmdlet **Uninstall-CsDatabase** richiede di confermare le azioni, leggere le informazioni e quindi premere **Y** (o premere INVIO) per procedere oppure premere **N** e quindi immettere se si vuole interrompere il cmdlet (ovvero, in caso di errori).

</div>

</div>

<span> </span>

</div>

</div>

</div>


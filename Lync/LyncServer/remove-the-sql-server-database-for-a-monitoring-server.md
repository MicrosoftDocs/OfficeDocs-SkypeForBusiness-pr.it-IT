---
title: Rimuovere il database di SQL Server per un server di monitoraggio
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for a Monitoring server
ms:assetid: aed5e394-d63e-4ad4-af40-f12d3a044344
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721848(v=OCS.15)
ms:contentKeyID: 49733781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f877f7d8d1ade4d260ed137f52046c21f29cf11
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726986"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a>Rimuovere il database di SQL Server per un server di monitoraggio

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-04_

Dopo aver rimosso un server di monitoraggio di Microsoft Lync Server 2010, è possibile rimuovere i database di SQL Server che ospitavano i dati del server. Usare le procedure seguenti per rimuovere le definizioni da generatore di topologie e quindi rimuovere il database e i file di log dal server di database.

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Per rimuovere il database di SQL Server tramite Generatore di topologie

1.  Nel server front-end di Lync Server 2013 aprire Generatore di topologia.

2.  In Generatore di topologie passare a **componenti condivisi** e quindi **archiviare SQL Server**, fare clic con il pulsante destro del mouse sull'istanza di SQL Server associata al server di monitoraggio rimosso o riconfigurato e quindi scegliere **Elimina**.

3.  Pubblicare la topologia e quindi controllare lo stato della replica.

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a>Per rimuovere i file di database da SQL Server

1.  Per rimuovere i database nel server basato su SQL Server, è necessario essere membri del gruppo sysadmin di SQL Server per il server SQL Server in cui si stanno rimuovendo i file di database.

2.  Aprire Lync Server Management Shell.

3.  Nella riga di comando digitare quanto segue:
    
        Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    Dove \<FQDN\> è il nome di dominio completo (FQDN) del server di database e \<instance\> è l'istanza di database denominata facoltativa.

4.  Quando il cmdlet **Uninstall-CsDatabase** richiede di confermare le azioni, leggere le informazioni e quindi premere **Y** (o premere INVIO) per procedere oppure premere **N** e quindi immettere se si vuole interrompere il cmdlet (ovvero, in caso di errori).

</div>

</div>

<span> </span>

</div>

</div>

</div>


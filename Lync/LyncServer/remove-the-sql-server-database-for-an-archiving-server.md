---
title: Rimuovere il database di SQL Server per un server di archiviazione
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove the SQL Server database for an Archiving server
ms:assetid: 6e8a1fcd-ed09-43b0-82c9-60e7ce116a01
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688087(v=OCS.15)
ms:contentKeyID: 49733686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a0794d751ae0c469539971d4b29685e2971d865
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979029"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-an-archiving-server"></a><span data-ttu-id="5a332-102">Rimuovere il database di SQL Server per un server di archiviazione</span><span class="sxs-lookup"><span data-stu-id="5a332-102">Remove the SQL Server database for an Archiving server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a332-103">_**Argomento Ultima modifica:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="5a332-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="5a332-104">Dopo aver rimosso un server di archiviazione di Microsoft Lync Server 2010, è possibile rimuovere i database di SQL Server che ospitavano i dati del pool.</span><span class="sxs-lookup"><span data-stu-id="5a332-104">After you remove a Microsoft Lync Server 2010 Archiving Server, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="5a332-105">Usare le procedure seguenti per rimuovere le definizioni da generatore di topologie e quindi rimuovere il database e i file di log dal server di database.</span><span class="sxs-lookup"><span data-stu-id="5a332-105">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="5a332-106">Per rimuovere il database di SQL Server tramite Generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="5a332-106">To remove the SQL Server database using Topology Builder</span></span>

1.  <span data-ttu-id="5a332-107">Nel server front-end di Lync Server 2013 aprire Generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="5a332-107">On the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="5a332-108">In Generatore di topologie passare a **componenti condivisi** e quindi **archiviare SQL Server**, fare clic con il pulsante destro del mouse sull'istanza di SQL Server associata al server di archiviazione rimosso o riconfigurato e quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="5a332-108">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Archiving Server, and then click **Delete**.</span></span>

3.  <span data-ttu-id="5a332-109">Pubblicare la topologia e quindi controllare lo stato della replica.</span><span class="sxs-lookup"><span data-stu-id="5a332-109">Publish the topology, and then check replication status.</span></span>

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="5a332-110">Per rimuovere i file di database da SQL Server</span><span class="sxs-lookup"><span data-stu-id="5a332-110">To remove the database files from the SQL Server</span></span>

1.  <span data-ttu-id="5a332-111">Per rimuovere i database di SQL Server, è necessario essere membri del gruppo sysadmin di SQL Server per SQL Server in cui si stanno rimuovendo i file di database.</span><span class="sxs-lookup"><span data-stu-id="5a332-111">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span>

2.  <span data-ttu-id="5a332-112">Aprire Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5a332-112">Open the Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="5a332-113">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="5a332-113">At the command line, type the following:</span></span>
    
        Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="5a332-114">Dove \<FQDN\> è il nome di dominio completo (FQDN) del server di database e \<instance\> è l'istanza di database denominata, ovvero se ne è stata definita una.</span><span class="sxs-lookup"><span data-stu-id="5a332-114">Where \<FQDN\> is the fully qualified domain name (FQDN) of the database server, and \<instance\> is the named database instance (that is, if one was defined).</span></span>

4.  <span data-ttu-id="5a332-115">Quando il cmdlet **Uninstall-CsDatabase** richiede di confermare le azioni, leggere le informazioni e quindi premere **Y** (o premere INVIO) per procedere oppure premere **N** e quindi immettere se si vuole interrompere il cmdlet (ovvero, in caso di errori).</span><span class="sxs-lookup"><span data-stu-id="5a332-115">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press **Y** (or press Enter) to proceed, or press **N** and then Enter if you want to stop the cmdlet (that is, in case there errors).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


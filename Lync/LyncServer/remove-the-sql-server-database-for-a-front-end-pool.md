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
ms.openlocfilehash: 853b52c6f6a06d05f106114ab6b59ebc52129fc3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727146"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a><span data-ttu-id="611ed-102">Rimuovere il database di SQL Server per un pool Front End</span><span class="sxs-lookup"><span data-stu-id="611ed-102">Remove the SQL Server database for a Front End pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="611ed-103">_**Argomento Ultima modifica:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="611ed-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="611ed-104">Dopo aver rimosso un pool di front end di Microsoft Lync Server 2010 o aver riconfigurato il pool per l'uso di un database diverso, è possibile rimuovere i database di SQL Server che ospitavano i dati del pool.</span><span class="sxs-lookup"><span data-stu-id="611ed-104">After you remove a Microsoft Lync Server 2010 Front End pool or reconfigure the pool to use a different database, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="611ed-105">Usare le procedure seguenti per rimuovere le definizioni da generatore di topologie e quindi rimuovere il database e i file di log dal server di database.</span><span class="sxs-lookup"><span data-stu-id="611ed-105">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="611ed-106">Per rimuovere il database di SQL Server tramite Generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="611ed-106">To remove the SQL Server database using Topology Builder</span></span>

1.  <span data-ttu-id="611ed-107">Dal server front-end di Lync Server 2013 aprire Generatore di topologia e scaricare la topologia esistente.</span><span class="sxs-lookup"><span data-stu-id="611ed-107">From the Lync Server 2013 Front End Server, open Topology Builder and download the existing topology.</span></span>

2.  <span data-ttu-id="611ed-108">In Generatore di topologie passare a **componenti condivisi** e quindi **archiviare SQL Server**, fare clic con il pulsante destro del mouse sull'istanza di SQL Server associata al pool di front-end rimosso o riconfigurato e quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="611ed-108">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Front End pool, and then click **Delete**.</span></span>

3.  <span data-ttu-id="611ed-109">Pubblicare la topologia e quindi controllare lo stato della replica.</span><span class="sxs-lookup"><span data-stu-id="611ed-109">Publish the topology, and then check the replication status.</span></span>

</div>

<div>

## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a><span data-ttu-id="611ed-110">Per rimuovere i database di utenti e applicazioni da SQL Server</span><span class="sxs-lookup"><span data-stu-id="611ed-110">To remove user and application databases from the SQL Server</span></span>

1.  <span data-ttu-id="611ed-111">Per rimuovere i database di SQL Server, è necessario essere membri del gruppo sysadmin di SQL Server per SQL Server in cui si stanno rimuovendo i file di database.</span><span class="sxs-lookup"><span data-stu-id="611ed-111">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span>

2.  <span data-ttu-id="611ed-112">Aprire Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="611ed-112">Open Lync Server Management Shell</span></span>

3.  <span data-ttu-id="611ed-113">Per rimuovere il database per l'archivio utenti del pool, digitare:</span><span class="sxs-lookup"><span data-stu-id="611ed-113">To remove the database for the pool user store, type:</span></span>
    
        Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="611ed-114">Dove \<FQDN\> è il nome di dominio completo (FQDN) del server di database e \<instance\> è l'istanza di database denominata, ovvero se ne è stata definita una.</span><span class="sxs-lookup"><span data-stu-id="611ed-114">Where \<FQDN\> is the fully qualified domain name (FQDN) of the database server, and \<instance\> is the named database instance (that is, if one was defined).</span></span>

4.  <span data-ttu-id="611ed-115">Per rimuovere il database per l'archivio delle applicazioni del pool, digitare:</span><span class="sxs-lookup"><span data-stu-id="611ed-115">To remove the database for the pool application store, type:</span></span>
    
        Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="611ed-116">Dove \<FQDN\> è il nome di dominio completo del server di \<database\> e instance è l'istanza di database denominata, ovvero se ne è stata definita una.</span><span class="sxs-lookup"><span data-stu-id="611ed-116">Where \<FQDN\> is the FQDN of the database server, and \<instance\> is the named database instance (that is, if one was defined).</span></span>

5.  <span data-ttu-id="611ed-117">Quando il cmdlet **Uninstall-CsDatabase** richiede di confermare le azioni, leggere le informazioni e quindi premere **Y** (o premere INVIO) per procedere oppure premere **N** e quindi immettere se si vuole interrompere il cmdlet (ovvero, in caso di errori).</span><span class="sxs-lookup"><span data-stu-id="611ed-117">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press **Y** (or press Enter) to proceed, or press **N** and then Enter if you want to stop the cmdlet (that is, in case there errors).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


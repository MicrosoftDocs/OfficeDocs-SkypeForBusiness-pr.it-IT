---
title: Rimuovere il database di SQL Server per un Monitoring Server
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
ms.openlocfilehash: 5485f957bf0f172b52db602fba84819f493bc817
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008852"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a><span data-ttu-id="6f32b-102">Rimuovere il database di SQL Server per un Monitoring Server</span><span class="sxs-lookup"><span data-stu-id="6f32b-102">Remove the SQL Server database for a Monitoring server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f32b-103">_**Ultimo argomento modificato:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="6f32b-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="6f32b-104">Dopo aver rimosso un server di monitoraggio di Microsoft Lync Server 2010, è possibile rimuovere i database di SQL Server in cui sono stati ospitati i dati del server.</span><span class="sxs-lookup"><span data-stu-id="6f32b-104">After you remove a Microsoft Lync Server 2010 Monitoring Server, you can remove the SQL Server databases that hosted the server data.</span></span> <span data-ttu-id="6f32b-105">Utilizzare le procedure seguenti per rimuovere le definizioni da generatore di topologie, quindi rimuovere il database e i file di registro dal server di database.</span><span class="sxs-lookup"><span data-stu-id="6f32b-105">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="6f32b-106">Per rimuovere il database di SQL Server tramite Generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="6f32b-106">To remove the SQL Server database using Topology Builder</span></span>

1.  <span data-ttu-id="6f32b-107">Nel server front-end Lync Server 2013 aprire Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="6f32b-107">On the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="6f32b-108">In Generatore di topologie, passare a **componenti condivisi** e quindi a **SQL Server Store**, fare clic con il pulsante destro del mouse sull'istanza di SQL Server associata al Monitoring Server rimosso o riconfigurato, quindi fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="6f32b-108">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Monitoring Server, and then click **Delete**.</span></span>

3.  <span data-ttu-id="6f32b-109">Pubblicare la topologia, quindi verificare lo stato della replica.</span><span class="sxs-lookup"><span data-stu-id="6f32b-109">Publish the topology, and then check replication status.</span></span>

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="6f32b-110">Per rimuovere i file di database da SQL Server</span><span class="sxs-lookup"><span data-stu-id="6f32b-110">To remove the database files from the SQL Server</span></span>

1.  <span data-ttu-id="6f32b-111">Per rimuovere i database dal server basato su SQL Server, è necessario essere un membro del gruppo sysadmins nel server SQL Server in cui vengono rimossi i file di database.</span><span class="sxs-lookup"><span data-stu-id="6f32b-111">To remove the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmins group for the SQL Server server where you are removing the database files.</span></span>

2.  <span data-ttu-id="6f32b-112">Aprire Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="6f32b-112">Open the Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="6f32b-113">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="6f32b-113">At the command line, type the following:</span></span>
    
        Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="6f32b-114">Dove \<FQDN\> è il nome di dominio completo (FQDN) del server di database e \<instance\> è l'istanza di database denominata facoltativa.</span><span class="sxs-lookup"><span data-stu-id="6f32b-114">Where \<FQDN\> is the fully qualified domain name (FQDN) of the database server, and \<instance\> is the optional named database instance.</span></span>

4.  <span data-ttu-id="6f32b-115">Quando il cmdlet **Uninstall-CsDataBase** richiede di confermare le azioni, leggere le informazioni e quindi premere **S** (o INVIO) per procedere oppure **N** e quindi INVIO per arrestare il cmdlet (in caso di errori).</span><span class="sxs-lookup"><span data-stu-id="6f32b-115">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press **Y** (or press Enter) to proceed, or press **N** and then Enter if you want to stop the cmdlet (that is, in case there errors).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


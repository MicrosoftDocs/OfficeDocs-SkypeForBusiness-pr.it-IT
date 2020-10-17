---
title: 'Lync Server 2013: preparazione per il ripristino di Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing to restore Lync Server
ms:assetid: 857e4e02-908e-433a-96c6-be1795a9cb61
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202179(v=OCS.15)
ms:contentKeyID: 51541490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f31354ee87cdf7df5efdb6c4e2accf3758829c1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506833"
---
# <a name="preparing-to-restore-lync-server-2013"></a><span data-ttu-id="ea3db-102">Preparazione per il ripristino di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea3db-102">Preparing to restore Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea3db-103">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="ea3db-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="ea3db-104">Prima di iniziare a ripristinare server e database dopo un errore, è necessario determinare gli aspetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea3db-104">Before you begin restoring servers and databases after a failure, you need to determine the following:</span></span>

  - <span data-ttu-id="ea3db-105">Che cosa deve essere ripristinato.</span><span class="sxs-lookup"><span data-stu-id="ea3db-105">What needs to be restored.</span></span>

  - <span data-ttu-id="ea3db-106">L'hardware, il software, i dati e gli strumenti necessari per il ripristino.</span><span class="sxs-lookup"><span data-stu-id="ea3db-106">The hardware, software, data, and tools you need for restoration.</span></span>

<div>

## <a name="determining-what-to-restore"></a><span data-ttu-id="ea3db-107">Determinazione dei componenti da ripristinare</span><span class="sxs-lookup"><span data-stu-id="ea3db-107">Determining What to Restore</span></span>

<span data-ttu-id="ea3db-108">In questo argomento viene descritto come ripristinare le interruzioni di Lync Server che si verificano a livello del server, del pool o dell'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="ea3db-108">This topic describes how to restore Lync Server outages that occur at the server, pool, or Central Management store level.</span></span> <span data-ttu-id="ea3db-109">Se l'archivio di gestione centrale ha esito negativo, la distribuzione di Lync Server continua a funzionare, ma non è possibile apportare modifiche alla configurazione.</span><span class="sxs-lookup"><span data-stu-id="ea3db-109">If the Central Management store fails, your Lync Server deployment continues to function, but you cannot make any configuration changes.</span></span> <span data-ttu-id="ea3db-110">In caso di errore di un server back-end o Standard Edition, il pool di utenti smette di funzionare.</span><span class="sxs-lookup"><span data-stu-id="ea3db-110">If a Back End Server or Standard Edition server fails, the user pool stops functioning.</span></span> <span data-ttu-id="ea3db-111">In caso di errore di qualsiasi altro server, la gravità dell'errore dipende dal ruolo del server e dal fatto che il server ospiti uno o più database.</span><span class="sxs-lookup"><span data-stu-id="ea3db-111">If any other server fails, the magnitude of the failure depends on the server role the server is running and whether the server hosts one or more databases.</span></span>

### <a name="what-to-restore"></a><span data-ttu-id="ea3db-112">Componenti da ripristinare</span><span class="sxs-lookup"><span data-stu-id="ea3db-112">What to Restore</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ea3db-113">In caso di errore di</span><span class="sxs-lookup"><span data-stu-id="ea3db-113">If this failed</span></span></th>
<th><span data-ttu-id="ea3db-114">Vedere questa sezione:</span><span class="sxs-lookup"><span data-stu-id="ea3db-114">See this section:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea3db-115">Server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="ea3db-115">Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="ea3db-116"><a href="lync-server-2013-restoring-a-standard-edition-server.md">Ripristino di un server Standard Edition in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ea3db-116"><a href="lync-server-2013-restoring-a-standard-edition-server.md">Restoring a Standard Edition server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea3db-117">Archivio di gestione centrale</span><span class="sxs-lookup"><span data-stu-id="ea3db-117">Central Management store</span></span></p></td>
<td><p><span data-ttu-id="ea3db-118"><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Ripristino del server che ospita l'archivio di gestione centrale in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ea3db-118"><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Restoring the server hosting the Central Management store in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea3db-119">Back-end Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="ea3db-119">Enterprise Edition Back End</span></span></p></td>
<td><p><span data-ttu-id="ea3db-120"><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Ripristino di un server back-end Enterprise Edition in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ea3db-120"><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restoring an Enterprise Edition Back End Server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea3db-121">Server primario di back-end con mirroring Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="ea3db-121">Enterprise Edition Mirrored Back End Primary Server</span></span></p></td>
<td><p><span data-ttu-id="ea3db-122"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Ripristino di un server back-end Enterprise Edition con mirroring in Lync Server 2013-Primary</a></span><span class="sxs-lookup"><span data-stu-id="ea3db-122"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea3db-123">Server secondario di back-end con mirroring Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="ea3db-123">Enterprise Edition Mirrored Back End Secondary Server</span></span></p></td>
<td><p><span data-ttu-id="ea3db-124"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Ripristino di un server back-end Enterprise Edition con mirroring in Lync Server 2013-mirror</a></span><span class="sxs-lookup"><span data-stu-id="ea3db-124"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea3db-125">Qualsiasi server Enterprise Edition che esegue un ruolo del server, ad esempio front end server, server perimetrale, Director, Mediation Server o Persistent Chat Server.</span><span class="sxs-lookup"><span data-stu-id="ea3db-125">Any Enterprise Edition server running a server role, such as a Front End Server, Edge Server, Director, Mediation Server,.or Persistent Chat Server.</span></span></p></td>
<td><p><span data-ttu-id="ea3db-126"><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Ripristino di un server membro Enterprise Edition in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ea3db-126"><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restoring an Enterprise Edition member server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea3db-127">Un intero pool di Lync Server</span><span class="sxs-lookup"><span data-stu-id="ea3db-127">An entire Lync Server pool</span></span></p></td>
<td><p><span data-ttu-id="ea3db-128"><a href="lync-server-2013-restoring-a-lync-server-pool.md">Ripristino di un pool di Lync Server in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ea3db-128"><a href="lync-server-2013-restoring-a-lync-server-pool.md">Restoring a Lync Server pool in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea3db-129">Archivio file Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="ea3db-129">Enterprise Edition File Store</span></span></p></td>
<td><p><span data-ttu-id="ea3db-130"><a href="lync-server-2013-restoring-a-file-store.md">Ripristino di un archivio file in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ea3db-130"><a href="lync-server-2013-restoring-a-file-store.md">Restoring a file store in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea3db-131">Un database di monitoraggio autonomo o un database di archiviazione</span><span class="sxs-lookup"><span data-stu-id="ea3db-131">A standalone Monitoring database or Archiving database</span></span></p></td>
<td><p><span data-ttu-id="ea3db-132"><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Ripristino dei dati di monitoraggio o archiviazione in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ea3db-132"><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Restoring monitoring or archiving data in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea3db-133">Un database di chat persistente autonomo</span><span class="sxs-lookup"><span data-stu-id="ea3db-133">A stand-alone Persistent Chat database</span></span></p></td>
<td><p><span data-ttu-id="ea3db-134"><a href="lync-server-2013-restoring-persistent-chat-data.md">Ripristino dei dati di chat persistente in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ea3db-134"><a href="lync-server-2013-restoring-persistent-chat-data.md">Restoring Persistent Chat data in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="gathering-hardware-software-and-tools"></a><span data-ttu-id="ea3db-135">Raccolta di hardware, software e strumenti</span><span class="sxs-lookup"><span data-stu-id="ea3db-135">Gathering Hardware, Software, and Tools</span></span>

<span data-ttu-id="ea3db-136">Quando si ripristina un server, è necessario iniziare con un computer nuovo o pulito.</span><span class="sxs-lookup"><span data-stu-id="ea3db-136">When you restore a server, you need to start with a new or clean computer.</span></span> <span data-ttu-id="ea3db-137">È inoltre necessario che siano disponibili i seguenti componenti hardware e software:</span><span class="sxs-lookup"><span data-stu-id="ea3db-137">Additionally, you must have the following hardware and software available:</span></span>

  - <span data-ttu-id="ea3db-138">Un server nuovo o pulito con lo stesso nome di dominio completo (FQDN) del server in cui si è verificato l'errore.</span><span class="sxs-lookup"><span data-stu-id="ea3db-138">A clean or new server with the same fully qualified domain name (FQDN) as the server that failed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ea3db-139">Quando si installa il sistema operativo, assicurarsi che l'account del computer non venga eliminato in servizi di dominio Active Directory e verificare che le autorizzazioni di gruppo per l'account vengano conservate.</span><span class="sxs-lookup"><span data-stu-id="ea3db-139">When you install the operating system, make sure that you do not delete the computer account in Active Directory Domain Services, and verify that the group permissions for the account are retained.</span></span>

    
    </div>

  - <span data-ttu-id="ea3db-140">Software di installazione per il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="ea3db-140">Installation software for the operating system.</span></span> <span data-ttu-id="ea3db-141">Per installare il sistema operativo, è possibile utilizzare le procedure di distribuzione del server e le configurazioni stabilite dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ea3db-141">To install the operating system, use the server deployment procedures and configurations established by your organization.</span></span> <span data-ttu-id="ea3db-142">Quando si ripristina il servizio, è necessario che queste procedure e i requisiti di configurazione siano disponibili.</span><span class="sxs-lookup"><span data-stu-id="ea3db-142">You should have these procedures and configuration requirements available when you restore service.</span></span>

  - <span data-ttu-id="ea3db-143">Software di installazione per SQL Server 2012 o SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="ea3db-143">Installation software for SQL Server 2012 or SQL Server 2008 R2.</span></span> <span data-ttu-id="ea3db-144">Per installare un server di database, utilizzare la versione appropriata di SQL Server, nonché le configurazioni e le procedure di distribuzione del server di database stabilite dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ea3db-144">To install a database server, use the appropriate version of SQL Server and the database server deployment procedures and configurations established by your organization.</span></span> <span data-ttu-id="ea3db-145">Quando si ripristina il servizio, è necessario che queste procedure e i requisiti di configurazione siano disponibili.</span><span class="sxs-lookup"><span data-stu-id="ea3db-145">You should have these procedures and configuration requirements available when you restore service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ea3db-146">La distribuzione guidata di Lync Server installa automaticamente SQL Server 2012 Express in ogni server Standard Edition e in qualsiasi altro server Lync Server quando è installato un archivio di configurazione locale, a meno che non sia stato preinstallato SQL Server 2012 o SQL Server 2008 R2 sul server.</span><span class="sxs-lookup"><span data-stu-id="ea3db-146">The Lync Server Deployment Wizard automatically installs SQL Server 2012 Express on each Standard Edition server and on any other Lync Server server when a local configuration store is installed, unless you have preinstalled SQL Server 2012 or SQL Server 2008 R2 on the server.</span></span>

    
    </div>

  - <span data-ttu-id="ea3db-147">Software per l'acquisizione di immagini di sistema.</span><span class="sxs-lookup"><span data-stu-id="ea3db-147">Software for taking system images.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="ea3db-148">È consigliabile acquisire una copia di immagine del sistema dopo l'installazione del sistema operativo e di SQL Server e prima di iniziare il ripristino, in modo che sia possibile utilizzare questa immagine come punto di rollback in caso di problemi durante il ripristino.</span><span class="sxs-lookup"><span data-stu-id="ea3db-148">We recommend that you take an image copy of the system after you install the operating system and SQL Server, and before you start restoration, so that you can use this image as a rollback point in case something goes wrong during restoration.</span></span>

    
    </div>

  - <span data-ttu-id="ea3db-149">Software di installazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ea3db-149">Lync Server 2013 installation software.</span></span> <span data-ttu-id="ea3db-150">La distribuzione guidata di Lync Server si trova nella cartella di installazione di Lync Server o nel file multimediale all' \\ installazione di \\ amd64 \\Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="ea3db-150">The Lync Server Deployment Wizard is located in the Lync Server installation folder or media at \\setup\\amd64\\Setup.exe.</span></span>

<span data-ttu-id="ea3db-151">Durante il ripristino, vengono utilizzati gli strumenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea3db-151">During restoration, you use the following tools:</span></span>

  - <span data-ttu-id="ea3db-152">Cmdlet di Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="ea3db-152">Lync Server Management Shell cmdlets</span></span>

  - <span data-ttu-id="ea3db-153">Import-CsUserData</span><span class="sxs-lookup"><span data-stu-id="ea3db-153">Import-CsUserData</span></span>

  - <span data-ttu-id="ea3db-154">Strumenti per il ripristino delle cartelle di Windows</span><span class="sxs-lookup"><span data-stu-id="ea3db-154">Tools for restoring Windows folders</span></span>

  - <span data-ttu-id="ea3db-155">Strumento di generazione topologia</span><span class="sxs-lookup"><span data-stu-id="ea3db-155">Topology Builder</span></span>

  - <span data-ttu-id="ea3db-156">Utilità di database di SQL Server, ad esempio SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ea3db-156">SQL Server database utilities, such as SQL Server Management Studio</span></span>

</div>

<div>

## <a name="preparing-to-restore-a-server"></a><span data-ttu-id="ea3db-157">Preparazione al ripristino di un server</span><span class="sxs-lookup"><span data-stu-id="ea3db-157">Preparing to Restore a Server</span></span>

<span data-ttu-id="ea3db-158">Prima di ripristinare il server, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea3db-158">Before you restore the server, you must perform the following steps:</span></span>

1.  <span data-ttu-id="ea3db-159">Installare il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="ea3db-159">Install the operating system.</span></span>

2.  <span data-ttu-id="ea3db-160">Se il server è un server di back-end, installare SQL Server 2012 o SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="ea3db-160">If the server is a Back End Server, install SQL Server 2012 or SQL Server 2008 R2.</span></span>

3.  <span data-ttu-id="ea3db-161">Ripristinare o registrare nuovamente i certificati.</span><span class="sxs-lookup"><span data-stu-id="ea3db-161">Restore or reenroll your certificates.</span></span> <span data-ttu-id="ea3db-162">Per informazioni dettagliate sui certificati, vedere "requisiti di backup aggiuntivi" in [requisiti di backup e ripristino in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span><span class="sxs-lookup"><span data-stu-id="ea3db-162">For details about certificates, see "Additional Backup Requirements" in [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span></span>

4.  <span data-ttu-id="ea3db-163">Acquisire un'immagine del sistema prima di iniziare il ripristino da utilizzare come punto di rollback, in caso di problemi durante il ripristino.</span><span class="sxs-lookup"><span data-stu-id="ea3db-163">Take an image of the system before starting restoration to use as a rollback point, in case something goes wrong during restoration.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ea3db-164">La distribuzione guidata di Lync Server e i cmdlet descritti nelle procedure illustrate in questo argomento e gli argomenti correlati, impostare tutti gli elenchi di controllo di accesso (ACL) necessari.</span><span class="sxs-lookup"><span data-stu-id="ea3db-164">The Lync Server Deployment Wizard and cmdlets described in the procedures in this topic, and related topics, set all required access control lists (ACLs).</span></span>



</div>

<span data-ttu-id="ea3db-165">Verificare che l'hardware e il software necessari per i componenti che si intende ripristinare siano disponibili prima di iniziare il ripristino.</span><span class="sxs-lookup"><span data-stu-id="ea3db-165">Verify that the hardware and the software that you need for the components that you plan to restore are available before you start restoration.</span></span> <span data-ttu-id="ea3db-166">Dopo aver installato il sistema operativo e SQL Server, la maggior parte delle operazioni delle procedure di ripristino seguenti può essere eseguita in modalità remota.</span><span class="sxs-lookup"><span data-stu-id="ea3db-166">After you install the operating system and SQL Server, most of the steps in the following restoration procedures can be run remotely.</span></span> <span data-ttu-id="ea3db-167">Le eccezioni sono segnalate nelle procedure.</span><span class="sxs-lookup"><span data-stu-id="ea3db-167">The exceptions are noted in the procedures.</span></span>

<span data-ttu-id="ea3db-168">È inoltre necessario disporre del piano di backup e ripristino dell'organizzazione e delle informazioni dell'ultimo backup, ad esempio le informazioni contenute nei fogli di lavoro di questo documento (per informazioni dettagliate, vedere [backup and Restoration Worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)), disponibile prima di iniziare il ripristino.</span><span class="sxs-lookup"><span data-stu-id="ea3db-168">You should also have your organization's backup and restoration plan and the information from your last backup, such as the information in the worksheets in this document (for details, see [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)), available before you begin restoration.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


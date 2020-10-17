---
title: 'Lync Server 2013: backup dei dati di base e delle impostazioni'
description: 'Lync Server 2013: backup dei dati di base e delle impostazioni.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up core data and settings
ms:assetid: 278bc95a-7b8d-4e01-a872-a844830459de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202170(v=OCS.15)
ms:contentKeyID: 51541452
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 637eeb950a3b8380f6e756f46a5083f51b5d7e1f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543742"
---
# <a name="backing-up-core-data-and-settings-in-lync-server-2013"></a><span data-ttu-id="5a2a4-103">Backup dei dati di base e delle impostazioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a2a4-103">Backing up core data and settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a2a4-104">_**Ultimo argomento modificato:** 2014-04-23_</span><span class="sxs-lookup"><span data-stu-id="5a2a4-104">_**Topic Last Modified:** 2014-04-23_</span></span>

<span data-ttu-id="5a2a4-105">Nelle procedure seguenti vengono utilizzati i cmdlet di Lync Server Management Shell per creare file di backup per le impostazioni e i dati per i servizi di base.</span><span class="sxs-lookup"><span data-stu-id="5a2a4-105">The following procedures use Lync Server Management Shell cmdlets to create backup files for settings and data for core services.</span></span> <span data-ttu-id="5a2a4-106">Per informazioni dettagliate sugli strumenti utilizzati in questa sezione, incluso il percorso in cui si trovano, vedere [backup and Restoration requirements in Lync Server 2013: Tools and Permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="5a2a4-106">For details about the tools used in this section, including where they are located, see [Backup and restoration requirements in Lync Server 2013: tools and permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span></span> <span data-ttu-id="5a2a4-107">Per informazioni dettagliate sul backup dei dati di archiviazione e di monitoraggio, vedere [backing up Archiving and Monitoring Databases in Lync Server 2013](lync-server-2013-backing-up-archiving-and-monitoring-databases.md).</span><span class="sxs-lookup"><span data-stu-id="5a2a4-107">For details about backing up Archiving and Monitoring data, see [Backing up Archiving and Monitoring databases in Lync Server 2013](lync-server-2013-backing-up-archiving-and-monitoring-databases.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5a2a4-108">Il passaggio in questa sezione per eseguire il backup dell'archivio di gestione centrale include le impostazioni e la configurazione per l'archiviazione e il monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="5a2a4-108">The step in this section to back up the Central Management store includes the settings and configuration for Archiving and Monitoring.</span></span>



</div>

<span data-ttu-id="5a2a4-109">È possibile eseguire i cmdlet descritti in questa sezione localmente o da postazione remota.</span><span class="sxs-lookup"><span data-stu-id="5a2a4-109">You can run the cmdlets described in this section locally or remotely.</span></span>

<div>

## <a name="to-back-up-core-data-and-settings"></a><span data-ttu-id="5a2a4-110">Per eseguire il backup dei dati e delle impostazioni di base</span><span class="sxs-lookup"><span data-stu-id="5a2a4-110">To back up core data and settings</span></span>

1.  <span data-ttu-id="5a2a4-111">Eseguire l'accesso a un computer della distribuzione interna utilizzando un account utente membro del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="5a2a4-111">From a user account that is a member of the RTCUniversalServerAdmins group, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5a2a4-112">Per archiviare i backup creati nei passaggi seguenti, creare una nuova cartella condivisa e aggiornare il percorso utilizzato come riferimento da **$Backup** sostituendolo con la nuova cartella condivisa.</span><span class="sxs-lookup"><span data-stu-id="5a2a4-112">To store the backups you create in the following steps, create a new shared folder and update the path referenced by **$Backup** to the new shared folder.</span></span>

3.  <span data-ttu-id="5a2a4-113">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="5a2a4-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="5a2a4-114">Eseguire il backup del file di configurazione dell'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="5a2a4-114">Back up the Central Management store configuration file.</span></span> <span data-ttu-id="5a2a4-115">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="5a2a4-115">At the command line, type the following:</span></span>
    
        Export-CsConfiguration -FileName <path and file name for backup>
    
    <span data-ttu-id="5a2a4-116">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5a2a4-116">For example:</span></span>
    
        Export-CsConfiguration -FileName "C:\Config.zip"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5a2a4-117">In questo passaggio vengono esportate in un file la topologia, i criteri e le impostazioni di configurazione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5a2a4-117">This step exports your Lync Server topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="5a2a4-118">Non sono richieste altre operazioni per il backup dei dati della topologia.</span><span class="sxs-lookup"><span data-stu-id="5a2a4-118">No other step is required to backup topology data.</span></span>

    
    </div>

5.  <span data-ttu-id="5a2a4-119">Copiare il file di configurazione dell'archivio di gestione centrale di cui è stato eseguito il backup in $Backup \\ .</span><span class="sxs-lookup"><span data-stu-id="5a2a4-119">Copy the backed-up Central Management store configuration file to $Backup\\.</span></span>

6.  <span data-ttu-id="5a2a4-p104">Eseguire il backup dei dati del servizio Informazioni percorso. Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="5a2a4-p104">Back up Location Information service data. At the command line, type the following:</span></span>
    
        Export-CsLisConfiguration -FileName <path and file name for backup>
    
    <span data-ttu-id="5a2a4-122">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5a2a4-122">For example:</span></span>
    
        Export-CsLisConfiguration -FileName "C:\E911Config.zip"

7.  <span data-ttu-id="5a2a4-123">Copiare il file di configurazione del servizio informazioni percorso di cui è stato eseguito il backup in $Backup \\ .</span><span class="sxs-lookup"><span data-stu-id="5a2a4-123">Copy the backed-up Location Information service configuration file to $Backup\\.</span></span>

8.  <span data-ttu-id="5a2a4-124">Eseguire il backup dei dati degli utenti su ogni database back-end di un pool Front end e di ogni server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="5a2a4-124">Back up user data on every back-end database of a Front End pool and every Standard Edition server.</span></span> <span data-ttu-id="5a2a4-125">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="5a2a4-125">At the command line, type the following:</span></span>
    
        Export-CsUserData -PoolFQDN <Fqdn> -FileName <String>
    
    <span data-ttu-id="5a2a4-126">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5a2a4-126">For example:</span></span>
    
        Export-CsUserData -PoolFQDN "atl-cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserData.zip"

9.  <span data-ttu-id="5a2a4-127">Copiare il file dell'utente di cui è stato eseguito il backup in $Backup \\ .</span><span class="sxs-lookup"><span data-stu-id="5a2a4-127">Copy the backed up user file to $Backup\\.</span></span>

10. <span data-ttu-id="5a2a4-128">In ogni pool che esegue l'applicazione Response Group eseguire il backup della configurazione di Response Group.</span><span class="sxs-lookup"><span data-stu-id="5a2a4-128">On every pool that runs the Response Group application, back up the Response Group configuration.</span></span> <span data-ttu-id="5a2a4-129">Eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a2a4-129">Do the following:</span></span>
    
    1.  <span data-ttu-id="5a2a4-130">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="5a2a4-130">At the command line, type:</span></span>
        
            Export-CsRgsConfiguration -Source "service:ApplicationServer:<pool FQDN>" -FileName <path and file name for backup>
        
        <span data-ttu-id="5a2a4-131">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5a2a4-131">For example:</span></span>
        
            Export-CsRgsConfiguration -Source ApplicationServer:pool01.contoso.com -FileName C:\RgsConfiguration.zip

11. <span data-ttu-id="5a2a4-132">Copiare il file di configurazione di Response Group di cui è stato eseguito il backup su $Backup \\ .</span><span class="sxs-lookup"><span data-stu-id="5a2a4-132">Copy the backed up Response Group configuration file to $Backup\\.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


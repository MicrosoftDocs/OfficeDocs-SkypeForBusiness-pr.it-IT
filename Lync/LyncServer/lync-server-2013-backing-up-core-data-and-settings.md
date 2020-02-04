---
title: 'Lync Server 2013: backup dei dati e delle impostazioni di base'
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
ms.openlocfilehash: 4185c02bc85077b0f68ca76d83fd48203e0e5fd9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727916"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-core-data-and-settings-in-lync-server-2013"></a><span data-ttu-id="998ee-102">Backup dei dati e delle impostazioni di base in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="998ee-102">Backing up core data and settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="998ee-103">_**Argomento Ultima modifica:** 2014-04-23_</span><span class="sxs-lookup"><span data-stu-id="998ee-103">_**Topic Last Modified:** 2014-04-23_</span></span>

<span data-ttu-id="998ee-104">Le procedure seguenti usano i cmdlet di Lync Server Management Shell per creare file di backup per le impostazioni e i dati per i servizi principali.</span><span class="sxs-lookup"><span data-stu-id="998ee-104">The following procedures use Lync Server Management Shell cmdlets to create backup files for settings and data for core services.</span></span> <span data-ttu-id="998ee-105">Per informazioni dettagliate sugli strumenti usati in questa sezione, inclusi i casi in cui si trovano, vedere [requisiti di backup e ripristino in Lync Server 2013: strumenti e autorizzazioni](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="998ee-105">For details about the tools used in this section, including where they are located, see [Backup and restoration requirements in Lync Server 2013: tools and permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span></span> <span data-ttu-id="998ee-106">Per informazioni dettagliate su come eseguire il backup dei dati di archiviazione e monitoraggio, vedere [backup di archiviazione e monitoraggio di database in Lync Server 2013](lync-server-2013-backing-up-archiving-and-monitoring-databases.md).</span><span class="sxs-lookup"><span data-stu-id="998ee-106">For details about backing up Archiving and Monitoring data, see [Backing up Archiving and Monitoring databases in Lync Server 2013](lync-server-2013-backing-up-archiving-and-monitoring-databases.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="998ee-107">Il passaggio in questa sezione per eseguire il backup di Central Management Store include le impostazioni e la configurazione per l'archiviazione e il monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="998ee-107">The step in this section to back up the Central Management store includes the settings and configuration for Archiving and Monitoring.</span></span>



</div>

<span data-ttu-id="998ee-108">È possibile eseguire i cmdlet descritti in questa sezione localmente o in remoto.</span><span class="sxs-lookup"><span data-stu-id="998ee-108">You can run the cmdlets described in this section locally or remotely.</span></span>

<div>

## <a name="to-back-up-core-data-and-settings"></a><span data-ttu-id="998ee-109">Per eseguire il backup dei dati e delle impostazioni principali</span><span class="sxs-lookup"><span data-stu-id="998ee-109">To back up core data and settings</span></span>

1.  <span data-ttu-id="998ee-110">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="998ee-110">From a user account that is a member of the RTCUniversalServerAdmins group, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="998ee-111">Per archiviare i backup creati nei passaggi seguenti, creare una nuova cartella condivisa e aggiornare il percorso a cui fa riferimento **$backup** alla nuova cartella condivisa.</span><span class="sxs-lookup"><span data-stu-id="998ee-111">To store the backups you create in the following steps, create a new shared folder and update the path referenced by **$Backup** to the new shared folder.</span></span>

3.  <span data-ttu-id="998ee-112">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="998ee-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="998ee-113">Eseguire il backup del file di configurazione di Central Management store.</span><span class="sxs-lookup"><span data-stu-id="998ee-113">Back up the Central Management store configuration file.</span></span> <span data-ttu-id="998ee-114">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="998ee-114">At the command line, type the following:</span></span>
    
        Export-CsConfiguration -FileName <path and file name for backup>
    
    <span data-ttu-id="998ee-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="998ee-115">For example:</span></span>
    
        Export-CsConfiguration -FileName "C:\Config.zip"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="998ee-116">Questo passaggio Esporta la topologia, i criteri e le impostazioni di configurazione di Lync Server in un file.</span><span class="sxs-lookup"><span data-stu-id="998ee-116">This step exports your Lync Server topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="998ee-117">Nessun altro passaggio è necessario per eseguire il backup dei dati della topologia.</span><span class="sxs-lookup"><span data-stu-id="998ee-117">No other step is required to backup topology data.</span></span>

    
    </div>

5.  <span data-ttu-id="998ee-118">Copiare il file di configurazione dell'archivio di gestione centralizzato di cui\\è stato eseguito il backup in $backup.</span><span class="sxs-lookup"><span data-stu-id="998ee-118">Copy the backed-up Central Management store configuration file to $Backup\\.</span></span>

6.  <span data-ttu-id="998ee-119">Eseguire il backup dei dati del servizio informazioni sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="998ee-119">Back up Location Information service data.</span></span> <span data-ttu-id="998ee-120">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="998ee-120">At the command line, type the following:</span></span>
    
        Export-CsLisConfiguration -FileName <path and file name for backup>
    
    <span data-ttu-id="998ee-121">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="998ee-121">For example:</span></span>
    
        Export-CsLisConfiguration -FileName "C:\E911Config.zip"

7.  <span data-ttu-id="998ee-122">Copiare il file di configurazione del servizio informazioni posizione di cui è stato\\eseguito il backup in $backup.</span><span class="sxs-lookup"><span data-stu-id="998ee-122">Copy the backed-up Location Information service configuration file to $Backup\\.</span></span>

8.  <span data-ttu-id="998ee-123">Eseguire il backup dei dati degli utenti in tutti i database back-end di un pool Front-end e di ogni server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="998ee-123">Back up user data on every back-end database of a Front End pool and every Standard Edition server.</span></span> <span data-ttu-id="998ee-124">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="998ee-124">At the command line, type the following:</span></span>
    
        Export-CsUserData -PoolFQDN <Fqdn> -FileName <String>
    
    <span data-ttu-id="998ee-125">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="998ee-125">For example:</span></span>
    
        Export-CsUserData -PoolFQDN "atl-cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserData.zip"

9.  <span data-ttu-id="998ee-126">Copiare il file utente di cui è stato eseguito\\il backup in $backup.</span><span class="sxs-lookup"><span data-stu-id="998ee-126">Copy the backed up user file to $Backup\\.</span></span>

10. <span data-ttu-id="998ee-127">In tutti i pool che esegue l'applicazione Response Group, eseguire il backup della configurazione del gruppo di risposte.</span><span class="sxs-lookup"><span data-stu-id="998ee-127">On every pool that runs the Response Group application, back up the Response Group configuration.</span></span> <span data-ttu-id="998ee-128">Effettuare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="998ee-128">Do the following:</span></span>
    
    1.  <span data-ttu-id="998ee-129">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="998ee-129">At the command line, type:</span></span>
        
            Export-CsRgsConfiguration -Source "service:ApplicationServer:<pool FQDN>" -FileName <path and file name for backup>
        
        <span data-ttu-id="998ee-130">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="998ee-130">For example:</span></span>
        
            Export-CsRgsConfiguration -Source ApplicationServer:pool01.contoso.com -FileName C:\RgsConfiguration.zip

11. <span data-ttu-id="998ee-131">Copiare il file di configurazione del gruppo di risposta di cui\\è stato eseguito il backup in $backup.</span><span class="sxs-lookup"><span data-stu-id="998ee-131">Copy the backed up Response Group configuration file to $Backup\\.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


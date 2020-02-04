---
title: 'Lync Server 2013: Gestire gli annunci durante il ripristino di emergenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage announcements during disaster recovery
ms:assetid: c33e51ea-421f-42d2-826b-b73968f6bd5b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721874(v=OCS.15)
ms:contentKeyID: 49733807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfc987ea579bef4e2b02c8da210efe9a707c5900
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733426"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-announcements-during-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="30d0b-102">Gestire gli annunci durante il ripristino di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30d0b-102">Manage announcements during disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30d0b-103">_**Argomento Ultima modifica:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="30d0b-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="30d0b-104">Lync Server 2013 supporta gli annunci per le chiamate a numeri non assegnati durante le interruzioni.</span><span class="sxs-lookup"><span data-stu-id="30d0b-104">Lync Server 2013 supports announcements for calls to unassigned numbers during outages.</span></span> <span data-ttu-id="30d0b-105">Il ripristino della funzionalità di annuncio durante un'interruzione è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="30d0b-105">Restoring announcement functionality during an outage is optional.</span></span> <span data-ttu-id="30d0b-106">Se si sceglie di ripristinare gli annunci durante un'interruzione, è necessario ricreare la configurazione dell'annuncio nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="30d0b-106">If you choose to restore announcements during an outage, you need recreate your announcement configuration in the backup pool.</span></span> <span data-ttu-id="30d0b-107">Questa sezione descrive le operazioni da eseguire se si sceglie di ripristinare gli annunci durante il ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="30d0b-107">This section describes what you need to do if you choose to restore announcements during disaster recovery.</span></span>

<span data-ttu-id="30d0b-108">Questa sezione si applica agli intervalli di numeri non assegnati che usano l'applicazione annuncio.</span><span class="sxs-lookup"><span data-stu-id="30d0b-108">This section applies to unassigned number ranges that use the Announcement application.</span></span> <span data-ttu-id="30d0b-109">Questa sezione non si applica agli intervalli di numeri non assegnati che usano l'operatore automatico di messaggistica UNIFICAta di Exchange.</span><span class="sxs-lookup"><span data-stu-id="30d0b-109">This section does not apply to unassigned number ranges that use Exchange Unified Messaging (UM) Auto Attendant.</span></span>

<div>

## <a name="before-an-outage"></a><span data-ttu-id="30d0b-110">Prima di un'interruzione</span><span class="sxs-lookup"><span data-stu-id="30d0b-110">Before an Outage</span></span>

<span data-ttu-id="30d0b-111">Indipendentemente dal fatto che si scelga di usare gli annunci durante le interruzioni, è consigliabile eseguire backup distinti di tutti i file audio personalizzati configurati per l'applicazione di annuncio.</span><span class="sxs-lookup"><span data-stu-id="30d0b-111">Regardless of whether you choose to use announcements during outages, you should take separate backups of any customized audio files that you configured for the Announcement application.</span></span> <span data-ttu-id="30d0b-112">Non viene eseguito il backup degli annunci personalizzati come parte del processo di ripristino di emergenza di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="30d0b-112">Customized announcements are not backed up as part of the Lync Server disaster recovery process.</span></span> <span data-ttu-id="30d0b-113">Se non si accettano backup separati dei file e i file caricati nel server o nel pool sono danneggiati, danneggiati o eliminati, i file andranno perduti.</span><span class="sxs-lookup"><span data-stu-id="30d0b-113">If you do not take separate backups of the files and the files that you uploaded to the server or pool are damaged, corrupted, or erased, the files will be lost.</span></span>

<span data-ttu-id="30d0b-114">Se non si dispone di copie di backup di file audio personalizzati e i file audio originali non sono più disponibili, è possibile trovare i file audio configurati per un'applicazione di annuncio cercando nell'archivio file del server o del pool in cui si trovavano originariamente importato i file.</span><span class="sxs-lookup"><span data-stu-id="30d0b-114">If you do not have backup copies of customized audio files, and the original audio files are no longer available, you can find the audio files that you configured for an Announcement application by looking in the File Store for the server or pool where you originally imported the files.</span></span> <span data-ttu-id="30d0b-115">È possibile copiare tutti i file audio configurati per l'applicazione di annuncio dall'archivio file.</span><span class="sxs-lookup"><span data-stu-id="30d0b-115">You can copy all the audio files that you configured for the Announcement application from the File Store.</span></span>

<span data-ttu-id="30d0b-116">**Per copiare i file audio dall'archivio file**</span><span class="sxs-lookup"><span data-stu-id="30d0b-116">**To copy audio files from the file store**</span></span>

1.  <span data-ttu-id="30d0b-117">Nella riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="30d0b-117">At the command line, run:</span></span>
    
        Xcopy <Source: Pool Announcement Service File Store path> <Destination>
    
    <span data-ttu-id="30d0b-118">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="30d0b-118">For example:</span></span>
    
        Xcopy "<Pool File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS" "<Destination: Backup location>"
    
    <span data-ttu-id="30d0b-119">Dove X-ApplicationServer-X si riferisce all'ID servizio del server applicazioni del pool, ad esempio 1-ApplicationServer-1 ")</span><span class="sxs-lookup"><span data-stu-id="30d0b-119">Where X-ApplicationServer-X refers to the service ID of the Application Server of the pool (for example, 1-ApplicationServer-1")</span></span>


</div>

<div>

## <a name="during-an-outage"></a><span data-ttu-id="30d0b-120">Durante un'interruzione</span><span class="sxs-lookup"><span data-stu-id="30d0b-120">During an Outage</span></span>

<span data-ttu-id="30d0b-121">Per usare l'applicazione di annuncio durante un'interruzione, è necessario ricreare la configurazione dell'annuncio nel pool di backup eseguendo le attività descritte in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="30d0b-121">To use the Announcement application during an outage, you need to recreate the announcement configuration in the backup pool by performing the tasks described in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="30d0b-122">È consigliabile eseguire queste attività dopo aver eseguito il failover nel pool di backup, perché non appena si esegue il passaggio 2, il pool di backup assume la proprietà degli intervalli di numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="30d0b-122">We recommend that you perform these tasks after you fail over to the backup pool, because as soon as you perform step 2, the backup pool takes ownership of the unassigned number ranges.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="30d0b-123">Questi passaggi non sono necessari per gli intervalli di numeri che usano un numero di telefono dell'operatore automatico di Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="30d0b-123">These steps are not required for number ranges that use an Exchange UM Auto Attendant phone number.</span></span>



</div>

<span data-ttu-id="30d0b-124">**Per ricreare la configurazione dell'annuncio nel pool di backup**</span><span class="sxs-lookup"><span data-stu-id="30d0b-124">**To recreate the announcement configuration in the backup pool**</span></span>

1.  <span data-ttu-id="30d0b-125">Per ricreare gli annunci distribuiti nel pool principale nel pool di backup, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="30d0b-125">Recreate the announcements that you deployed in the primary pool in the backup pool by doing the following:</span></span>
    
    1.  <span data-ttu-id="30d0b-126">Importare i file audio usati nel pool principale nel pool di backup usando il cmdlet **Import-CsAnnouncementFile** e specificando il pool di backup per il parametro Parent.</span><span class="sxs-lookup"><span data-stu-id="30d0b-126">Import any audio files used in the primary pool to the backup pool by using the **Import-CsAnnouncementFile** cmdlet and specifying the backup pool for the Parent parameter.</span></span>
    
    2.  <span data-ttu-id="30d0b-127">Ricreare ogni annuncio usando il cmdlet **New-CsAnnouncement** e specificando il pool di backup per il parametro Parent.</span><span class="sxs-lookup"><span data-stu-id="30d0b-127">Recreate each announcement by using the **New-CsAnnouncement** cmdlet and specifying the backup pool for the Parent parameter.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="30d0b-128">Per informazioni dettagliate sull'uso di questi parametri per creare annunci nel pool di backup, vedere <A href="lync-server-2013-create-an-announcement.md">creare un annuncio in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="30d0b-128">For details about using these parameters to create announcements in the backup pool, see <A href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="30d0b-129">Dopo che tutti gli annunci vengono ricreati nel pool di backup, reindirizza tutti gli intervalli di numeri non assegnati che usano gli annunci nel pool principale per gli annunci ricreati nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="30d0b-129">After all announcements are recreated in the backup pool, redirect all the unassigned number ranges that use announcements in the primary pool to the recreated announcements in the backup pool.</span></span>
    
    <span data-ttu-id="30d0b-130">Per ogni intervallo di numeri non assegnati che usa un annuncio nel pool principale, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="30d0b-130">For each unassigned number range that uses an announcement in the primary pool, run the following:</span></span>
    
        Set-CsUnassignedNumber -Identity "<name of number range>" -AnnouncementService "<FQDN of backup pool>" -AnnouncementName "<announcement name in backup pool>"

</div>

<div>

## <a name="after-the-outage"></a><span data-ttu-id="30d0b-131">Dopo l'interruzione</span><span class="sxs-lookup"><span data-stu-id="30d0b-131">After the Outage</span></span>

<span data-ttu-id="30d0b-132">Quando il pool primario diventa disponibile, è necessario reindirizzare gli intervalli di numeri non assegnati modificati per l'interruzione di nuovo nel pool principale.</span><span class="sxs-lookup"><span data-stu-id="30d0b-132">When the primary pool becomes available, you need to redirect the unassigned number ranges that you changed for the outage back to the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="30d0b-133">Questi passaggi non sono necessari per gli intervalli di numeri che usano un numero di telefono dell'operatore automatico di Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="30d0b-133">These steps are not required for number ranges that use an Exchange UM Auto Attendant phone number.</span></span>



</div>

<span data-ttu-id="30d0b-134">**Per ripristinare gli annunci nel pool principale**</span><span class="sxs-lookup"><span data-stu-id="30d0b-134">**To restore announcements in the primary pool**</span></span>

1.  <span data-ttu-id="30d0b-135">Se si dovesse ricompilare il pool principale durante il ripristino, è necessario ricreare gli annunci nel pool principale importando i file audio e creando annunci, proprio come nel pool di backup, ad eccezione del fatto che si specifica il pool principale per l'elemento padre parametro.</span><span class="sxs-lookup"><span data-stu-id="30d0b-135">If you had to rebuild the primary pool during the recovery, you need to recreate the announcements in the primary pool by importing the audio files and creating announcements, just as you did in the backup pool, except that you specify the primary pool for the Parent parameter.</span></span> <span data-ttu-id="30d0b-136">Per informazioni dettagliate, vedere "durante un'interruzione" più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="30d0b-136">For details, see "During an Outage" earlier in this topic.</span></span>

2.  <span data-ttu-id="30d0b-137">Per ogni intervallo di numeri non assegnati modificato per l'interruzione, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="30d0b-137">For each unassigned number range that you changed for the outage, run the following:</span></span>
    
        Set-CsUnassignedNumber [-Identity "<name of number range>"] -AnnouncementService "<FQDN of primary pool>" -AnnouncementName "<announcement name in primary pool>"

3.  <span data-ttu-id="30d0b-138">Facoltativamente, rimuovere gli annunci ricreati nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="30d0b-138">Optionally, remove the announcements that you recreated in the backup pool.</span></span> <span data-ttu-id="30d0b-139">Ottenere un elenco di annunci per l'applicazione di annuncio del pool di backup.</span><span class="sxs-lookup"><span data-stu-id="30d0b-139">Get a list of announcements for the backup pool Announcement application.</span></span> <span data-ttu-id="30d0b-140">Nella riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="30d0b-140">At the command line, run:</span></span>
    
        Get-CsAnnouncement -Identity "<Service:service ID>"
    
    <span data-ttu-id="30d0b-141">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="30d0b-141">For example:</span></span>
    
        Get-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com
    
    <span data-ttu-id="30d0b-142">Nell'elenco risultante individuare gli annunci che si desidera rimuovere e copiare i GUID.</span><span class="sxs-lookup"><span data-stu-id="30d0b-142">In the resulting list, locate the announcements you want to remove and copy the GUIDs.</span></span> <span data-ttu-id="30d0b-143">Per ogni annuncio che si vuole rimuovere, eseguire:</span><span class="sxs-lookup"><span data-stu-id="30d0b-143">For each announcement you want to remove, run:</span></span>
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
    
    <span data-ttu-id="30d0b-144">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="30d0b-144">For example:</span></span>
    
        Remove-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"


</div>

</div>

<span> </span>

</div>

</div>

</div>


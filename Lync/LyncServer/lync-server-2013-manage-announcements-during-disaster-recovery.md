---
title: 'Lync Server 2013: gestire gli annunci durante il ripristino di emergenza'
description: 'Lync Server 2013: gestire gli annunci durante il ripristino di emergenza.'
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
ms.openlocfilehash: d85dfcd15c9c3650bafafa6fa7702e19ac9c4f7d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550632"
---
# <a name="manage-announcements-during-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="ff7d1-103">Gestire gli annunci durante il ripristino di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff7d1-103">Manage announcements during disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff7d1-104">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="ff7d1-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="ff7d1-105">Lync Server 2013 supporta gli annunci per le chiamate ai numeri non assegnati durante le interruzioni.</span><span class="sxs-lookup"><span data-stu-id="ff7d1-105">Lync Server 2013 supports announcements for calls to unassigned numbers during outages.</span></span> <span data-ttu-id="ff7d1-106">Il ripristino della funzionalità degli annunci durante un'interruzione dei servizi è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ff7d1-106">Restoring announcement functionality during an outage is optional.</span></span> <span data-ttu-id="ff7d1-107">Se si sceglie di ripristinare gli annunci durante un'interruzione dei servizi, è necessario ricreare la configurazione degli annunci nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="ff7d1-107">If you choose to restore announcements during an outage, you need recreate your announcement configuration in the backup pool.</span></span> <span data-ttu-id="ff7d1-108">In questa sezione vengono descritte le operazioni da eseguire se si sceglie di ripristinare gli annunci durante il ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="ff7d1-108">This section describes what you need to do if you choose to restore announcements during disaster recovery.</span></span>

<span data-ttu-id="ff7d1-109">Questa sezione si applica agli intervalli di numeri non assegnati in cui viene utilizzata l'applicazione annuncio.</span><span class="sxs-lookup"><span data-stu-id="ff7d1-109">This section applies to unassigned number ranges that use the Announcement application.</span></span> <span data-ttu-id="ff7d1-110">Questa sezione non si applica agli intervalli di numeri non assegnati che utilizzano l'operatore automatico di messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="ff7d1-110">This section does not apply to unassigned number ranges that use Exchange Unified Messaging (UM) Auto Attendant.</span></span>

<div>

## <a name="before-an-outage"></a><span data-ttu-id="ff7d1-111">Prima di un'interruzione dei servizi</span><span class="sxs-lookup"><span data-stu-id="ff7d1-111">Before an Outage</span></span>

<span data-ttu-id="ff7d1-112">Indipendentemente dal fatto che si decida di utilizzare gli annunci durante le interruzioni, è consigliabile eseguire backup separati dei file audio personalizzati configurati per l'applicazione annuncio.</span><span class="sxs-lookup"><span data-stu-id="ff7d1-112">Regardless of whether you choose to use announcements during outages, you should take separate backups of any customized audio files that you configured for the Announcement application.</span></span> <span data-ttu-id="ff7d1-113">Gli annunci personalizzati non vengono sottoposti a backup come parte del processo di ripristino di emergenza di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ff7d1-113">Customized announcements are not backed up as part of the Lync Server disaster recovery process.</span></span> <span data-ttu-id="ff7d1-114">I file andranno perduti se non si eseguono backup separati e le copie caricate nel server o nel pool vengono danneggiate o cancellate.</span><span class="sxs-lookup"><span data-stu-id="ff7d1-114">If you do not take separate backups of the files and the files that you uploaded to the server or pool are damaged, corrupted, or erased, the files will be lost.</span></span>

<span data-ttu-id="ff7d1-115">Se non si dispone di copie di backup dei file audio personalizzati e i file audio originali non sono più disponibili, è possibile trovare i file audio configurati per un'applicazione annuncio cercando nell'archivio file il server o il pool in cui sono stati originariamente importati i file.</span><span class="sxs-lookup"><span data-stu-id="ff7d1-115">If you do not have backup copies of customized audio files, and the original audio files are no longer available, you can find the audio files that you configured for an Announcement application by looking in the File Store for the server or pool where you originally imported the files.</span></span> <span data-ttu-id="ff7d1-116">È possibile copiare tutti i file audio configurati per l'applicazione annuncio dall'archivio file.</span><span class="sxs-lookup"><span data-stu-id="ff7d1-116">You can copy all the audio files that you configured for the Announcement application from the File Store.</span></span>

<span data-ttu-id="ff7d1-117">**Per copiare i file audio dall'archivio file**</span><span class="sxs-lookup"><span data-stu-id="ff7d1-117">**To copy audio files from the file store**</span></span>

1.  <span data-ttu-id="ff7d1-118">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="ff7d1-118">At the command line, run:</span></span>
    
        Xcopy <Source: Pool Announcement Service File Store path> <Destination>
    
    <span data-ttu-id="ff7d1-119">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ff7d1-119">For example:</span></span>
    
        Xcopy "<Pool File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS" "<Destination: Backup location>"
    
    <span data-ttu-id="ff7d1-120">Dove X-ApplicationServer-X indica l'ID servizio del server applicazioni del pool, ad esempio 1-ApplicationServer-1.</span><span class="sxs-lookup"><span data-stu-id="ff7d1-120">Where X-ApplicationServer-X refers to the service ID of the Application Server of the pool (for example, 1-ApplicationServer-1")</span></span>


</div>

<div>

## <a name="during-an-outage"></a><span data-ttu-id="ff7d1-121">Durante un'interruzione dei servizi</span><span class="sxs-lookup"><span data-stu-id="ff7d1-121">During an Outage</span></span>

<span data-ttu-id="ff7d1-122">Per utilizzare l'applicazione annuncio durante un'interruzione, è necessario ricreare la configurazione degli annunci nel pool di backup eseguendo le attività descritte in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="ff7d1-122">To use the Announcement application during an outage, you need to recreate the announcement configuration in the backup pool by performing the tasks described in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ff7d1-123">È consigliabile eseguire queste attività dopo il failover al pool di backup, poiché nel momento in cui si esegue il passaggio 2, il pool di backup assume la proprietà degli intervalli di numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="ff7d1-123">We recommend that you perform these tasks after you fail over to the backup pool, because as soon as you perform step 2, the backup pool takes ownership of the unassigned number ranges.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="ff7d1-124">Queste operazioni non sono necessarie per gli intervalli di numeri in cui viene utilizzato un numero di telefono di Operatore automatico di Messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="ff7d1-124">These steps are not required for number ranges that use an Exchange UM Auto Attendant phone number.</span></span>



</div>

<span data-ttu-id="ff7d1-125">**Per ricreare la configurazione degli annunci nel pool di backup**</span><span class="sxs-lookup"><span data-stu-id="ff7d1-125">**To recreate the announcement configuration in the backup pool**</span></span>

1.  <span data-ttu-id="ff7d1-126">Eseguire le operazioni seguenti per ricreare nel pool di backup gli annunci distribuiti nel pool principale:</span><span class="sxs-lookup"><span data-stu-id="ff7d1-126">Recreate the announcements that you deployed in the primary pool in the backup pool by doing the following:</span></span>
    
    1.  <span data-ttu-id="ff7d1-127">Importare nel pool di backup i file audio utilizzati nel pool principale utilizzando il cmdlet **Import-CsAnnouncementFile** e specificando il pool di backup per il parametro Parent.</span><span class="sxs-lookup"><span data-stu-id="ff7d1-127">Import any audio files used in the primary pool to the backup pool by using the **Import-CsAnnouncementFile** cmdlet and specifying the backup pool for the Parent parameter.</span></span>
    
    2.  <span data-ttu-id="ff7d1-128">Ricreare ogni annuncio utilizzando il cmdlet **New-CsAnnouncement** e specificando il pool di backup per il parametro Parent.</span><span class="sxs-lookup"><span data-stu-id="ff7d1-128">Recreate each announcement by using the **New-CsAnnouncement** cmdlet and specifying the backup pool for the Parent parameter.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ff7d1-129">Per informazioni dettagliate sull'utilizzo di questi parametri per creare annunci nel pool di backup, vedere <A href="lync-server-2013-create-an-announcement.md">creare un annuncio in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ff7d1-129">For details about using these parameters to create announcements in the backup pool, see <A href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="ff7d1-130">Dopo aver ricreato tutti gli annunci nel pool di backup, reindirizzare agli annunci ricreati nel pool di backup tutti gli intervalli di numeri non assegnati in cui vengono utilizzati gli annunci nel pool principale.</span><span class="sxs-lookup"><span data-stu-id="ff7d1-130">After all announcements are recreated in the backup pool, redirect all the unassigned number ranges that use announcements in the primary pool to the recreated announcements in the backup pool.</span></span>
    
    <span data-ttu-id="ff7d1-131">Eseguire il comando seguente per ogni intervallo di numeri non assegnati in cui viene utilizzato un annuncio nel pool principale:</span><span class="sxs-lookup"><span data-stu-id="ff7d1-131">For each unassigned number range that uses an announcement in the primary pool, run the following:</span></span>
    
        Set-CsUnassignedNumber -Identity "<name of number range>" -AnnouncementService "<FQDN of backup pool>" -AnnouncementName "<announcement name in backup pool>"

</div>

<div>

## <a name="after-the-outage"></a><span data-ttu-id="ff7d1-132">Dopo l'interruzione dei servizi</span><span class="sxs-lookup"><span data-stu-id="ff7d1-132">After the Outage</span></span>

<span data-ttu-id="ff7d1-133">Quando diventa disponibile il pool principale, è necessario reindirizzare gli intervalli di numeri non assegnati modificati per l'interruzione dei servizi di nuovo al pool principale.</span><span class="sxs-lookup"><span data-stu-id="ff7d1-133">When the primary pool becomes available, you need to redirect the unassigned number ranges that you changed for the outage back to the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ff7d1-134">Queste operazioni non sono necessarie per gli intervalli di numeri in cui viene utilizzato un numero di telefono di Operatore automatico di Messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="ff7d1-134">These steps are not required for number ranges that use an Exchange UM Auto Attendant phone number.</span></span>



</div>

<span data-ttu-id="ff7d1-135">**Per ripristinare gli annunci nel pool principale**</span><span class="sxs-lookup"><span data-stu-id="ff7d1-135">**To restore announcements in the primary pool**</span></span>

1.  <span data-ttu-id="ff7d1-p105">Se è stato necessario rigenerare il pool principale durante il ripristino, sarà necessario ricreare gli annunci nel pool principale importando i file audio e creando gli annunci, esattamente come per il pool di backup ma specificando in questo caso il pool principale per il parametro Parent. Per informazioni dettagliate, vedere la sezione "Durante un'interruzione dei servizi" più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="ff7d1-p105">If you had to rebuild the primary pool during the recovery, you need to recreate the announcements in the primary pool by importing the audio files and creating announcements, just as you did in the backup pool, except that you specify the primary pool for the Parent parameter. For details, see "During an Outage" earlier in this topic.</span></span>

2.  <span data-ttu-id="ff7d1-138">Eseguire il comando seguente per ogni intervallo di numeri non assegnati modificato per l'interruzione dei servizi:</span><span class="sxs-lookup"><span data-stu-id="ff7d1-138">For each unassigned number range that you changed for the outage, run the following:</span></span>
    
        Set-CsUnassignedNumber [-Identity "<name of number range>"] -AnnouncementService "<FQDN of primary pool>" -AnnouncementName "<announcement name in primary pool>"

3.  <span data-ttu-id="ff7d1-139">Facoltativamente, rimuovere gli annunci ricreati nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="ff7d1-139">Optionally, remove the announcements that you recreated in the backup pool.</span></span> <span data-ttu-id="ff7d1-140">Ottenere un elenco di annunci per l'applicazione annuncio del pool di backup.</span><span class="sxs-lookup"><span data-stu-id="ff7d1-140">Get a list of announcements for the backup pool Announcement application.</span></span> <span data-ttu-id="ff7d1-141">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="ff7d1-141">At the command line, run:</span></span>
    
        Get-CsAnnouncement -Identity "<Service:service ID>"
    
    <span data-ttu-id="ff7d1-142">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ff7d1-142">For example:</span></span>
    
        Get-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com
    
    <span data-ttu-id="ff7d1-p107">Nell'elenco ottenuto individuare gli annunci che si desidera rimuovere e copiare i GUID. Eseguire il comando seguente per ogni annuncio che si desidera rimuovere:</span><span class="sxs-lookup"><span data-stu-id="ff7d1-p107">In the resulting list, locate the announcements you want to remove and copy the GUIDs. For each announcement you want to remove, run:</span></span>
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
    
    <span data-ttu-id="ff7d1-145">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ff7d1-145">For example:</span></span>
    
        Remove-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"


</div>

</div>

<span> </span>

</div>

</div>

</div>


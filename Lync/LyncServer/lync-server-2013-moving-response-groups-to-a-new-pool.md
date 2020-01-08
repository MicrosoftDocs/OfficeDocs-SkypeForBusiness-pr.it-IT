---
title: 'Lync Server 2013: spostamento di Response Group in un nuovo pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Moving response groups to a new pool
ms:assetid: da0db765-41e5-430b-b5a7-5418ec5ff2a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205298(v=OCS.15)
ms:contentKeyID: 48185538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e682ce99826cd5b9f2812c358e1028bfb491ddef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978303"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-response-groups-to-a-new-pool-in-lync-server-2013"></a><span data-ttu-id="f890b-102">Spostamento di gruppi di risposte in un nuovo pool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f890b-102">Moving response groups to a new pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f890b-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f890b-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f890b-104">Lync Server 2013 introduce un nuovo supporto per i cmdlet per lo spostamento di gruppi di risposte da un pool a un altro, anche quando il nome di dominio completo (FQDN) è diverso.</span><span class="sxs-lookup"><span data-stu-id="f890b-104">Lync Server 2013 introduces new cmdlet support for moving response groups from one pool to another pool, even when the fully qualified domain name (FQDN) is different.</span></span>

<span data-ttu-id="f890b-105">Seguire i passaggi descritti nella procedura seguente per trasferire i gruppi di risposte da un pool Front-end a un altro pool Front-end con un nome di dominio completo diverso.</span><span class="sxs-lookup"><span data-stu-id="f890b-105">Use the steps in the following procedure to move response groups from one Front End pool to another Front End pool with a different FQDN.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f890b-106">In un ambiente di coesistenza è possibile trasferire i gruppi di risposte solo tra&nbsp;i pool Front End di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f890b-106">In a coexistence environment, you can move response groups only between Lync Server 2013&nbsp;Front End pools.</span></span>



</div>

<div>

## <a name="to-move-response-groups-to-a-pool-with-a-different-fqdn"></a><span data-ttu-id="f890b-107">Per trasferire i gruppi di risposte in un pool con un nome di dominio completo diverso</span><span class="sxs-lookup"><span data-stu-id="f890b-107">To move response groups to a pool with a different FQDN</span></span>

1.  <span data-ttu-id="f890b-108">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f890b-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f890b-109">Esportare i gruppi di risposte nel pool di origine.</span><span class="sxs-lookup"><span data-stu-id="f890b-109">Export the response groups in the source pool.</span></span> <span data-ttu-id="f890b-110">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="f890b-110">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source FQDN>" -FileName "<export file name>"
    
    <span data-ttu-id="f890b-111">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f890b-111">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -FileName "C:\RgsExportSource.zip"
    
    <span data-ttu-id="f890b-112">Per rimuovere i gruppi di risposte dal pool di origine durante l'esportazione, includere il parametro – RemoveExportedConfiguration.</span><span class="sxs-lookup"><span data-stu-id="f890b-112">To remove the response groups from the source pool during the export, include the –RemoveExportedConfiguration parameter.</span></span> <span data-ttu-id="f890b-113">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f890b-113">For example:</span></span>
    
        Export-CsRgsConfiguration -Source ApplicationServer:source.contoso.com -FileName "C:\RgsExportSource.zip" -RemoveExportedConfiguration

3.  <span data-ttu-id="f890b-114">Importare i Response Groups nel pool di destinazione e assegnare il pool di destinazione come nuovo proprietario.</span><span class="sxs-lookup"><span data-stu-id="f890b-114">Import the response groups to the destination pool and assign the destination pool as the new owner.</span></span> <span data-ttu-id="f890b-115">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="f890b-115">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<destination pool>" -FileName "<export file name>" -OverwriteOwner
    
    <span data-ttu-id="f890b-116">Se si vuole anche copiare le impostazioni a livello di Response Group Application dal pool di origine al pool di destinazione, includere il parametro – ReplaceExistingRgsSettings.</span><span class="sxs-lookup"><span data-stu-id="f890b-116">If you also want to copy the Response Group application-level settings from the source pool to the destination pool, include the –ReplaceExistingRgsSettings parameter.</span></span> <span data-ttu-id="f890b-117">Puoi definire solo un set di impostazioni a livello di applicazione per ogni pool.</span><span class="sxs-lookup"><span data-stu-id="f890b-117">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="f890b-118">Se si copiano le impostazioni a livello di applicazione dal pool di origine al pool di destinazione, le impostazioni del pool di origine sostituiscono le impostazioni per il pool di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f890b-118">If you copy the application-level settings from the source pool to the destination pool, the settings from the source pool replace the settings for the destination pool.</span></span> <span data-ttu-id="f890b-119">Se le impostazioni a livello di applicazione non vengono copiate dal pool di origine, le impostazioni esistenti del pool di destinazione si applicano ai gruppi di risposta importati.</span><span class="sxs-lookup"><span data-stu-id="f890b-119">If you do not copy the application-level settings from the source pool, the existing settings from the destination pool apply to the imported response groups.</span></span>
    
    <span data-ttu-id="f890b-120">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f890b-120">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:destination.contoso.com" -FileName "C:\RgsExportSource.zip" -OverwriteOwner -ReplaceExistingRgsSettings
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f890b-121">Le impostazioni a livello di applicazione includono la configurazione predefinita per la musica in blocco, il file audio predefinito per la musica in blocco, il periodo di risponderia dell'agente e la configurazione del contesto delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="f890b-121">Application-level settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="f890b-122">Per visualizzare queste impostazioni di configurazione, eseguire il cmdlet <STRONG>Get-CsRgsConfiguration</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="f890b-122">To view these configuration settings, run the <STRONG>Get-CsRgsConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="f890b-123">Per informazioni dettagliate su questo cmdlet, vedere <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</A>.</span><span class="sxs-lookup"><span data-stu-id="f890b-123">For details about this cmdlet, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="f890b-124">Verificare che l'importazione abbia avuto esito positivo visualizzando la configurazione del gruppo di risposta importato eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f890b-124">Verify that the import was successful by displaying the imported response group configuration by doing the following:</span></span>
    
      - <span data-ttu-id="f890b-125">Verificare che tutti i flussi di lavoro siano stati importati.</span><span class="sxs-lookup"><span data-stu-id="f890b-125">Verify that all the workflows were imported.</span></span> <span data-ttu-id="f890b-126">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f890b-126">At the command line, type the following:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="f890b-127">Verificare che tutte le code siano state importate.</span><span class="sxs-lookup"><span data-stu-id="f890b-127">Verify that all the queues were imported.</span></span> <span data-ttu-id="f890b-128">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f890b-128">At the command line, type the following:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="f890b-129">Verificare che tutti i gruppi di agenti siano stati importati.</span><span class="sxs-lookup"><span data-stu-id="f890b-129">Verify that all the agent groups were imported.</span></span> <span data-ttu-id="f890b-130">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f890b-130">At the command line, type the following:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="f890b-131">Verificare che tutte le ore di attività siano state importate.</span><span class="sxs-lookup"><span data-stu-id="f890b-131">Verify that all the hours of business were imported.</span></span> <span data-ttu-id="f890b-132">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f890b-132">At the command line, type the following:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<destination pool FQDN>" 
    
      - <span data-ttu-id="f890b-133">Verificare che siano stati importati tutti i set di festività.</span><span class="sxs-lookup"><span data-stu-id="f890b-133">Verify that all the holiday sets were imported.</span></span> <span data-ttu-id="f890b-134">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f890b-134">At the command line, type the following:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<destination pool FQDN>" 

5.  <span data-ttu-id="f890b-135">Verificare che l'importazione abbia avuto successo effettuando una chiamata a uno dei gruppi di risposta e verificando che la chiamata sia gestita correttamente.</span><span class="sxs-lookup"><span data-stu-id="f890b-135">Verify that the import was successful by placing a call to one of the response groups and verifying that the call is handled correctly.</span></span>

6.  <span data-ttu-id="f890b-136">Richiedere agli agenti che sono membri di gruppi di agenti formali di accedere ai gruppi di agenti nel pool di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f890b-136">Request agents who are members of formal agent groups to sign in to their agent groups in the destination pool.</span></span>

7.  <span data-ttu-id="f890b-137">Se i gruppi di risposte non sono stati rimossi in precedenza dal pool di origine, rimuovere i gruppi di risposte dal pool di origine.</span><span class="sxs-lookup"><span data-stu-id="f890b-137">If you did not previously remove response groups from the source pool, remove the response groups from the source pool.</span></span> <span data-ttu-id="f890b-138">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="f890b-138">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source pool FQDN> -RemoveExportedConfiguration -FileName "<temporary export file name>"
    
    <span data-ttu-id="f890b-139">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f890b-139">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -RemoveExportedConfiguration -FileName "C:\TempRGsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>


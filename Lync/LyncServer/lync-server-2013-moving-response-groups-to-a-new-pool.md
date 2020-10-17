---
title: 'Lync Server 2013: spostamento di Response Group in un nuovo pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving response groups to a new pool
ms:assetid: da0db765-41e5-430b-b5a7-5418ec5ff2a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205298(v=OCS.15)
ms:contentKeyID: 48185538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6b0af841385bff8b11d46dd24793de5cdcf81da
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507103"
---
# <a name="moving-response-groups-to-a-new-pool-in-lync-server-2013"></a><span data-ttu-id="13c2b-102">Spostamento di Response Group in un nuovo pool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13c2b-102">Moving response groups to a new pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13c2b-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="13c2b-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="13c2b-104">Lync Server 2013 introduce un nuovo supporto per i cmdlet per lo spostamento di Response Group da un pool a un altro, anche quando il nome di dominio completo (FQDN) è diverso.</span><span class="sxs-lookup"><span data-stu-id="13c2b-104">Lync Server 2013 introduces new cmdlet support for moving response groups from one pool to another pool, even when the fully qualified domain name (FQDN) is different.</span></span>

<span data-ttu-id="13c2b-105">Utilizzare i passaggi della procedura seguente per spostare i Response Group da un pool Front end a un altro pool Front end con un nome di dominio completo diverso.</span><span class="sxs-lookup"><span data-stu-id="13c2b-105">Use the steps in the following procedure to move response groups from one Front End pool to another Front End pool with a different FQDN.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="13c2b-106">In un ambiente di coesistenza, è possibile spostare i Response Group solo tra i pool Front End di Lync Server 2013 &nbsp; .</span><span class="sxs-lookup"><span data-stu-id="13c2b-106">In a coexistence environment, you can move response groups only between Lync Server 2013&nbsp;Front End pools.</span></span>



</div>

<div>

## <a name="to-move-response-groups-to-a-pool-with-a-different-fqdn"></a><span data-ttu-id="13c2b-107">Per spostare i Response Group in un pool con un nome di dominio completo diverso</span><span class="sxs-lookup"><span data-stu-id="13c2b-107">To move response groups to a pool with a different FQDN</span></span>

1.  <span data-ttu-id="13c2b-108">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="13c2b-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="13c2b-109">Esportare i Response Group nel pool di origine.</span><span class="sxs-lookup"><span data-stu-id="13c2b-109">Export the response groups in the source pool.</span></span> <span data-ttu-id="13c2b-110">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="13c2b-110">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source FQDN>" -FileName "<export file name>"
    
    <span data-ttu-id="13c2b-111">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="13c2b-111">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -FileName "C:\RgsExportSource.zip"
    
    <span data-ttu-id="13c2b-112">Per rimuovere i Response Group dal pool di origine durante l'esportazione, includere il parametro – RemoveExportedConfiguration.</span><span class="sxs-lookup"><span data-stu-id="13c2b-112">To remove the response groups from the source pool during the export, include the –RemoveExportedConfiguration parameter.</span></span> <span data-ttu-id="13c2b-113">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="13c2b-113">For example:</span></span>
    
        Export-CsRgsConfiguration -Source ApplicationServer:source.contoso.com -FileName "C:\RgsExportSource.zip" -RemoveExportedConfiguration

3.  <span data-ttu-id="13c2b-114">Importare i Response Group nel pool di destinazione e assegnare il pool di destinazione come nuovo proprietario.</span><span class="sxs-lookup"><span data-stu-id="13c2b-114">Import the response groups to the destination pool and assign the destination pool as the new owner.</span></span> <span data-ttu-id="13c2b-115">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="13c2b-115">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<destination pool>" -FileName "<export file name>" -OverwriteOwner
    
    <span data-ttu-id="13c2b-116">Se si desidera copiare anche le impostazioni a livello di applicazione di Response Group dal pool di origine al pool di destinazione, includere il parametro – ReplaceExistingRgsSettings.</span><span class="sxs-lookup"><span data-stu-id="13c2b-116">If you also want to copy the Response Group application-level settings from the source pool to the destination pool, include the –ReplaceExistingRgsSettings parameter.</span></span> <span data-ttu-id="13c2b-117">È possibile definire solo un set di impostazioni a livello di applicazione per ogni pool.</span><span class="sxs-lookup"><span data-stu-id="13c2b-117">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="13c2b-118">Se si copiano le impostazioni a livello di applicazione dal pool di origine al pool di destinazione, le impostazioni del pool di origine sostituiscono quelle del pool di destinazione.</span><span class="sxs-lookup"><span data-stu-id="13c2b-118">If you copy the application-level settings from the source pool to the destination pool, the settings from the source pool replace the settings for the destination pool.</span></span> <span data-ttu-id="13c2b-119">Se le impostazioni a livello di applicazione non vengono copiate dal pool di origine, le impostazioni esistenti del pool di destinazione verranno applicate ai Response Group importati.</span><span class="sxs-lookup"><span data-stu-id="13c2b-119">If you do not copy the application-level settings from the source pool, the existing settings from the destination pool apply to the imported response groups.</span></span>
    
    <span data-ttu-id="13c2b-120">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="13c2b-120">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:destination.contoso.com" -FileName "C:\RgsExportSource.zip" -OverwriteOwner -ReplaceExistingRgsSettings
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="13c2b-121">Le impostazioni a livello di applicazione includono la configurazione predefinita per la musica di attesa, il file audio predefinito per la musica in attesa, il periodo di richiamata dell'agente e la configurazione del contesto delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="13c2b-121">Application-level settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="13c2b-122">Per visualizzare queste impostazioni di configurazione, eseguire il cmdlet <STRONG>Get-CsRgsConfiguration</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="13c2b-122">To view these configuration settings, run the <STRONG>Get-CsRgsConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="13c2b-123">Per informazioni dettagliate su questo cmdlet, vedere <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</A>.</span><span class="sxs-lookup"><span data-stu-id="13c2b-123">For details about this cmdlet, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="13c2b-124">Verificare che l'importazione abbia avuto esito positivo visualizzando la configurazione di Response Group importata eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="13c2b-124">Verify that the import was successful by displaying the imported response group configuration by doing the following:</span></span>
    
      - <span data-ttu-id="13c2b-125">Verificare che tutti i flussi di lavoro siano stati importati.</span><span class="sxs-lookup"><span data-stu-id="13c2b-125">Verify that all the workflows were imported.</span></span> <span data-ttu-id="13c2b-126">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="13c2b-126">At the command line, type the following:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="13c2b-127">Verificare che tutte le code siano state importate.</span><span class="sxs-lookup"><span data-stu-id="13c2b-127">Verify that all the queues were imported.</span></span> <span data-ttu-id="13c2b-128">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="13c2b-128">At the command line, type the following:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="13c2b-129">Verificare che tutti i gruppi di agenti siano stati importati.</span><span class="sxs-lookup"><span data-stu-id="13c2b-129">Verify that all the agent groups were imported.</span></span> <span data-ttu-id="13c2b-130">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="13c2b-130">At the command line, type the following:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="13c2b-131">Verificare che tutte le ore di attività siano state importate.</span><span class="sxs-lookup"><span data-stu-id="13c2b-131">Verify that all the hours of business were imported.</span></span> <span data-ttu-id="13c2b-132">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="13c2b-132">At the command line, type the following:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<destination pool FQDN>" 
    
      - <span data-ttu-id="13c2b-133">Verificare che tutti i set di festività siano stati importati.</span><span class="sxs-lookup"><span data-stu-id="13c2b-133">Verify that all the holiday sets were imported.</span></span> <span data-ttu-id="13c2b-134">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="13c2b-134">At the command line, type the following:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<destination pool FQDN>" 

5.  <span data-ttu-id="13c2b-135">Verificare che l'importazione abbia avuto esito positivo effettuando una chiamata a uno dei Response Group e verificando che la chiamata venga gestita correttamente.</span><span class="sxs-lookup"><span data-stu-id="13c2b-135">Verify that the import was successful by placing a call to one of the response groups and verifying that the call is handled correctly.</span></span>

6.  <span data-ttu-id="13c2b-136">Richiedere agli agenti che sono membri di gruppi di agenti formali di accedere ai rispettivi gruppi di agenti nel pool di destinazione.</span><span class="sxs-lookup"><span data-stu-id="13c2b-136">Request agents who are members of formal agent groups to sign in to their agent groups in the destination pool.</span></span>

7.  <span data-ttu-id="13c2b-137">Se i Response Group non sono stati precedentemente rimossi dal pool di origine, rimuovere i Response Group dal pool di origine.</span><span class="sxs-lookup"><span data-stu-id="13c2b-137">If you did not previously remove response groups from the source pool, remove the response groups from the source pool.</span></span> <span data-ttu-id="13c2b-138">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="13c2b-138">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source pool FQDN> -RemoveExportedConfiguration -FileName "<temporary export file name>"
    
    <span data-ttu-id="13c2b-139">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="13c2b-139">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -RemoveExportedConfiguration -FileName "C:\TempRGsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>


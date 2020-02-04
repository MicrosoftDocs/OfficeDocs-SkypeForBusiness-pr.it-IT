---
title: 'Lync Server 2013: utilizzo di stop per il servizio di registrazione centralizzato'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Stop for the Centralized Logging Service
ms:assetid: 09ac093e-8f30-4874-84b4-12548ac8c898
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687964(v=OCS.15)
ms:contentKeyID: 49733549
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 621d7c02530fea62b1601c1db755292c8f819a6e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743966"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-stop-for-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="8cb4c-102">Uso di stop per il servizio di registrazione centralizzato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8cb4c-102">Using Stop for the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8cb4c-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="8cb4c-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="8cb4c-104">È possibile interrompere una sessione di registrazione corrente con il cmdlet Stop-CsClsLogging.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-104">You can stop a currently running logging session with the Stop-CsClsLogging cmdlet.</span></span> <span data-ttu-id="8cb4c-105">In genere, non ci sono molte situazioni in cui è necessario interrompere una sessione di registrazione.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-105">Generally, there aren’t many situations in which you would need to stop a logging session.</span></span> <span data-ttu-id="8cb4c-106">Ad esempio, è possibile cercare registri e modificare le configurazioni senza prima di tutto necessario interrompere la registrazione.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-106">For example, you can search logs and change configurations without first needing to stop logging.</span></span> <span data-ttu-id="8cb4c-107">Se sono in uso due scenari, ad esempio AlwaysOn e UserReplicator, ed è necessario raccogliere informazioni correlate all'autenticazione, è necessario interrompere uno degli altri scenari (in un ambito globale, di un sito, di un pool o un computer) prima di iniziare a eseguire Scenario di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-107">If you have two scenarios running, for example AlwaysOn and UserReplicator, and you need to collect information related to Authentication, you will need to stop one of the other scenarios (at a global, site, pool or computer scope) before you can start running to Authentication scenario.</span></span> <span data-ttu-id="8cb4c-108">Per informazioni dettagliate, vedere [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging).</span><span class="sxs-lookup"><span data-stu-id="8cb4c-108">For details, see [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8cb4c-109">Per determinare gli scenari che è possibile eseguire in una distribuzione, un pool o un computer specifico, è necessario tenere presente che si è limitati a eseguire due scenari <STRONG>per ogni computer</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-109">When determining what scenarios you can run on a given deployment, pool or computer, you need to remember that you are limited to running two scenarios <STRONG>per computer</STRONG>.</span></span> <span data-ttu-id="8cb4c-110">Se si esegue la registrazione di attività in un pool, è consigliabile trattare un pool come singola entità.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-110">If you are logging activity on a pool, you should treat a pool as a single entity.</span></span> <span data-ttu-id="8cb4c-111">Nella maggior parte dei casi, non avrebbe senso eseguire scenari diversi in ogni computer in un pool.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-111">In most cases, it would not make sense to run different scenarios on each computer in a pool.</span></span> <span data-ttu-id="8cb4c-112">È consigliabile esaminare il problema di cui si stanno raccogliendo i dati e pensare allo scenario più appropriato in un dato computer nella distribuzione complessiva.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-112">It does make sense to look at the problem that you are collecting data about and think about what scenario makes the most sense on a given computer in the overall deployment.</span></span> <span data-ttu-id="8cb4c-113">Se, ad esempio, consideriamo lo scenario UserReplicator, il valore dell'uso di UserReplicator in un server perimetrale o in un pool di Edge sarà molto scarso.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-113">For example, if you consider the UserReplicator scenario, there would be very little value in running UserReplicator on an Edge Server or Edge pool.</span></span><BR><span data-ttu-id="8cb4c-114">Dopo aver compreso il problema e l'ambito dell'impatto, è consigliabile scegliere quali scenari eseguire in quali computer e pool.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-114">After you understand the problem and the scope of the impact, you should make careful choices about what scenarios to run on which computers and pools.</span></span> <span data-ttu-id="8cb4c-115">Anche se lo scenario AlwaysOn ha un significato per un'applicazione di ambito esteso, poiché raccoglie informazioni su un'ampia gamma di provider, gli scenari specifici hanno solo valore dell'applicazione in computer o pool specifici.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-115">While the AlwaysOn scenario makes sense for a wide scope application because it collects information on a wide variety of providers, specific scenarios only have application value on specific computers or pools.</span></span> <span data-ttu-id="8cb4c-116">È inoltre necessario prestare attenzione quando si avvia una sessione di registrazione in modo casuale senza prima capire il valore di uno scenario specifico.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-116">Also, you should take caution when randomly starting up a logging session without first understanding the value of a given scenario.</span></span> <span data-ttu-id="8cb4c-117">Se si usa lo scenario errato oppure se si usa uno scenario appropriato per l'attività e si applica lo scenario nell'ambito errato (globale, sito, pool o computer), è possibile ottenere dati discutibili che non sono molto utili, come se non fosse stato eseguito affatto lo scenario.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-117">If you use the wrong scenario, or if you use a scenario that is appropriate for the task and you apply the scenario at the wrong scope (be it global, site, pool, or computer), you can get questionable data that is not very useful—as if you didn't run the scenario at all.</span></span>



</div>

<span data-ttu-id="8cb4c-118">Per controllare le funzioni del servizio di registrazione centralizzato tramite Lync Server Management Shell, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator (RBAC) o di un ruolo RBAC personalizzato che contiene uno di questi due gruppi.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-118">To control the Centralized Logging Service functions by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="8cb4c-119">Per restituire un elenco di tutti i ruoli RBAC a cui è stato assegnato questo cmdlet (inclusi eventuali ruoli RBAC personalizzati creati manualmente), eseguire il comando seguente da Lync Server Management Shell o dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8cb4c-119">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="8cb4c-120">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8cb4c-120">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>

## <a name="to-stop-a-currently-running-centralized-logging-service-session"></a><span data-ttu-id="8cb4c-121">Per interrompere una sessione di servizio di registrazione centralizzata attualmente in uso</span><span class="sxs-lookup"><span data-stu-id="8cb4c-121">To stop a currently running Centralized Logging Service session</span></span>

1.  <span data-ttu-id="8cb4c-122">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="8cb4c-123">Eseguire una query sul servizio di registrazione centralizzata per individuare gli scenari in esecuzione digitando quanto segue:</span><span class="sxs-lookup"><span data-stu-id="8cb4c-123">Query the Centralized Logging Service to find out what scenarios are currently running by typing the following:</span></span>
    
        Show-CsClsLogging
    
    <span data-ttu-id="8cb4c-124">![Console di Windows PowerShell dopo la chiamata a Show-CsCl](images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "Console di Windows PowerShell dopo la chiamata a Show-CsCl")</span><span class="sxs-lookup"><span data-stu-id="8cb4c-124">![Windows PowerShell console after calling Show-CsCl](images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "Windows PowerShell console after calling Show-CsCl")</span></span>
    
    <span data-ttu-id="8cb4c-125">Il risultato di Show-CsClsLogging è un riepilogo degli scenari in uso e l'ambito in cui sono in uso.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-125">The result of Show-CsClsLogging is a summary of the scenarios that are running and what scope they are running in.</span></span> <span data-ttu-id="8cb4c-126">Per informazioni dettagliate, vedere [Mostra-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging).</span><span class="sxs-lookup"><span data-stu-id="8cb4c-126">For details, see [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging).</span></span>

3.  <span data-ttu-id="8cb4c-127">Per interrompere una sessione di registrazione attualmente in uso con uno scenario specifico, digitare:</span><span class="sxs-lookup"><span data-stu-id="8cb4c-127">To stop a currently running logging session with a specific scenario, type:</span></span>
    
        Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
    
    <span data-ttu-id="8cb4c-128">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8cb4c-128">For example:</span></span>
    
        Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
    
    <span data-ttu-id="8cb4c-129">Questo comando interrompe la registrazione con lo scenario UserReplicatior in pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-129">This command will stop logging with the UserReplicatior scenario on pool01.contoso.net.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8cb4c-130">I log creati durante questa sessione di registrazione usando lo scenario UserReplicator non vengono eliminati.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-130">Logs created during this logging session using the UserReplicator scenario are not deleted.</span></span> <span data-ttu-id="8cb4c-131">La registrazione è ancora disponibile per l'esecuzione delle ricerche sull'uso del comando Cerca-CsClsLogging.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-131">The logging is still available for you to execute searches against using the Search-CsClsLogging command.</span></span> <span data-ttu-id="8cb4c-132">Per informazioni dettagliate, vedere <A href="https://docs.microsoft.com/powershell/module/skype/Search-CsClsLogging">Ricerca-CsClsLogging</A>.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-132">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Search-CsClsLogging">Search-CsClsLogging</A>.</span></span>

    
    </div>

<span data-ttu-id="8cb4c-133">Agendo come comando complementare per Start-CsClsLogging, il cmdlet Stop-CsClsLogging termina la sessione di registrazione, definita da scenari, e mantiene i registri creati dalla sessione di registrazione.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-133">Acting as the companion command to Start-CsClsLogging, the Stop-CsClsLogging cmdlet ends the logging session, defined by scenarios, and retains the logs created by the logging session.</span></span> <span data-ttu-id="8cb4c-134">È possibile eseguire due scenari in un computer specifico in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-134">You can run two scenarios on a given computer at any time.</span></span> <span data-ttu-id="8cb4c-135">Il metodo di interruzione di uno scenario per raccogliere informazioni con un altro scenario è un'attività comune che è possibile eseguire durante la maggior parte dei problemi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-135">The method of stopping one scenario to gather information using another scenario is a common task that you can perform during most workload troubleshooting.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8cb4c-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8cb4c-136">See Also</span></span>


[<span data-ttu-id="8cb4c-137">Uso di Start per il servizio di registrazione centralizzato per acquisire i registri in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8cb4c-137">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</span></span>](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)  


[<span data-ttu-id="8cb4c-138">Panoramica del servizio di registrazione centralizzato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8cb4c-138">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[<span data-ttu-id="8cb4c-139">Mostra-CsClsLogging</span><span class="sxs-lookup"><span data-stu-id="8cb4c-139">Show-CsClsLogging</span></span>](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging)  
[<span data-ttu-id="8cb4c-140">Start-CsClsLogging</span><span class="sxs-lookup"><span data-stu-id="8cb4c-140">Start-CsClsLogging</span></span>](https://docs.microsoft.com/powershell/module/skype/Start-CsClsLogging)  
[<span data-ttu-id="8cb4c-141">Stop-CsClsLogging</span><span class="sxs-lookup"><span data-stu-id="8cb4c-141">Stop-CsClsLogging</span></span>](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


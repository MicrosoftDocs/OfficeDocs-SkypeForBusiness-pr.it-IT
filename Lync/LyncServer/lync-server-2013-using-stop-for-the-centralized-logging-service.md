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
ms.openlocfilehash: f9f1c662081b5a92d53f0658859d9fdee1a038d2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-stop-for-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="9d662-102">Utilizzo di stop per il servizio di registrazione centralizzato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9d662-102">Using Stop for the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d662-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="9d662-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="9d662-104">Il cmdlet Stop-CsClsLogging consente di interrompere una sessione di registrazione in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9d662-104">You can stop a currently running logging session with the Stop-CsClsLogging cmdlet.</span></span> <span data-ttu-id="9d662-105">In generale, le situazioni in cui può essere necessario interrompere una sessione di registrazione non sono molte.</span><span class="sxs-lookup"><span data-stu-id="9d662-105">Generally, there aren’t many situations in which you would need to stop a logging session.</span></span> <span data-ttu-id="9d662-106">Ad esempio, è possibile eseguire ricerche nei log e modificare configurazioni senza bisogno di interrompere la registrazione.</span><span class="sxs-lookup"><span data-stu-id="9d662-106">For example, you can search logs and change configurations without first needing to stop logging.</span></span> <span data-ttu-id="9d662-107">Se sono in esecuzione due scenari, ad esempio AlwaysOn e UserReplicator, ed è necessario raccogliere informazioni relative all'autenticazione, per poter avviare lo scenario Authentication sarà necessario interrompere uno dei due scenari, a livello globale, di pool o di sito.</span><span class="sxs-lookup"><span data-stu-id="9d662-107">If you have two scenarios running, for example AlwaysOn and UserReplicator, and you need to collect information related to Authentication, you will need to stop one of the other scenarios (at a global, site, pool or computer scope) before you can start running to Authentication scenario.</span></span> <span data-ttu-id="9d662-108">Per informazioni dettagliate, vedere [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging).</span><span class="sxs-lookup"><span data-stu-id="9d662-108">For details, see [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9d662-109">Nella determinazione degli scenari da eseguire in un dato pool, computer o distribuzione, tenere presente che l'esecuzione è limitata a due scenari <STRONG>per computer</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="9d662-109">When determining what scenarios you can run on a given deployment, pool or computer, you need to remember that you are limited to running two scenarios <STRONG>per computer</STRONG>.</span></span> <span data-ttu-id="9d662-110">Se si stanno registrando le attività in un pool, è consigliabile trattare il pool come una singola entità.</span><span class="sxs-lookup"><span data-stu-id="9d662-110">If you are logging activity on a pool, you should treat a pool as a single entity.</span></span> <span data-ttu-id="9d662-111">Nella maggior parte dei casi l'esecuzione di scenari diversi in ogni computer di un pool non ha senso.</span><span class="sxs-lookup"><span data-stu-id="9d662-111">In most cases, it would not make sense to run different scenarios on each computer in a pool.</span></span> <span data-ttu-id="9d662-112">È invece opportuno esaminare il problema su cui si stanno raccogliendo dati e stabilire quale scenario abbia più senso in un determinato computer nella distribuzione complessiva.</span><span class="sxs-lookup"><span data-stu-id="9d662-112">It does make sense to look at the problem that you are collecting data about and think about what scenario makes the most sense on a given computer in the overall deployment.</span></span> <span data-ttu-id="9d662-113">Ad esempio, se si considera lo scenario UserReplicator, è necessario che l'esecuzione di UserReplicator in un server perimetrale o in un pool perimetrale sia molto scarsa.</span><span class="sxs-lookup"><span data-stu-id="9d662-113">For example, if you consider the UserReplicator scenario, there would be very little value in running UserReplicator on an Edge Server or Edge pool.</span></span><BR><span data-ttu-id="9d662-p103">Una volta compresi il problema e l'ambito dell'impatto, andranno effettuate scelte attente sugli scenari da eseguire e sui computer e pool ai quali applicarli. Mentre lo scenario AlwaysOn è adatto all'applicazione su vasta scala, in quanto raccoglie informazioni su un'ampia gamma di provider, gli scenari specifici risultano utili solo se applicati a specifici computer o pool. È inoltre necessaria attenzione quando si avvia una sessione di registrazione scelta a caso senza prima comprendere il valore di un dato scenario. Se si utilizza lo scenario sbagliato, oppure si sceglie uno scenario appropriato per l'attività, ma lo si applica all'ambito sbagliato (a livello globale, di sito, di pool o di computer), si possono ottenere dati dubbi e non molto utili, come se non si fosse eseguito affatto lo scenario.</span><span class="sxs-lookup"><span data-stu-id="9d662-p103">After you understand the problem and the scope of the impact, you should make careful choices about what scenarios to run on which computers and pools. While the AlwaysOn scenario makes sense for a wide scope application because it collects information on a wide variety of providers, specific scenarios only have application value on specific computers or pools. Also, you should take caution when randomly starting up a logging session without first understanding the value of a given scenario. If you use the wrong scenario, or if you use a scenario that is appropriate for the task and you apply the scenario at the wrong scope (be it global, site, pool, or computer), you can get questionable data that is not very useful—as if you didn't run the scenario at all.</span></span>



</div>

<span data-ttu-id="9d662-118">Per controllare le funzioni del servizio di registrazione centralizzato utilizzando Lync Server Management Shell, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator (RBAC) o di un ruolo RBAC personalizzato contenente uno di questi due gruppi.</span><span class="sxs-lookup"><span data-stu-id="9d662-118">To control the Centralized Logging Service functions by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="9d662-119">Per restituire un elenco di tutti i ruoli RBAC a cui è stato assegnato questo cmdlet (inclusi eventuali ruoli RBAC personalizzati creati autonomamente), eseguire il comando seguente da Lync Server Management Shell o dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9d662-119">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="9d662-120">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="9d662-120">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>

## <a name="to-stop-a-currently-running-centralized-logging-service-session"></a><span data-ttu-id="9d662-121">Per arrestare una sessione di servizio di registrazione centralizzata attualmente in esecuzione</span><span class="sxs-lookup"><span data-stu-id="9d662-121">To stop a currently running Centralized Logging Service session</span></span>

1.  <span data-ttu-id="9d662-122">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="9d662-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="9d662-123">Eseguire una query sul servizio di registrazione centralizzato per individuare gli scenari attualmente in esecuzione digitando quanto segue:</span><span class="sxs-lookup"><span data-stu-id="9d662-123">Query the Centralized Logging Service to find out what scenarios are currently running by typing the following:</span></span>
    
        Show-CsClsLogging
    
    <span data-ttu-id="9d662-124">![Console di Windows PowerShell dopo aver chiamato Show-CsCl](images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "Console di Windows PowerShell dopo aver chiamato Show-CsCl")</span><span class="sxs-lookup"><span data-stu-id="9d662-124">![Windows PowerShell console after calling Show-CsCl](images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "Windows PowerShell console after calling Show-CsCl")</span></span>
    
    <span data-ttu-id="9d662-125">Il risultato di Show-CsClsLogging è un riepilogo degli scenari in esecuzione e dei relativi ambiti di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9d662-125">The result of Show-CsClsLogging is a summary of the scenarios that are running and what scope they are running in.</span></span> <span data-ttu-id="9d662-126">Per informazioni dettagliate, vedere [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging).</span><span class="sxs-lookup"><span data-stu-id="9d662-126">For details, see [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging).</span></span>

3.  <span data-ttu-id="9d662-127">Per interrompere una sessione di registrazione in esecuzione con uno scenario specifico, digitare:</span><span class="sxs-lookup"><span data-stu-id="9d662-127">To stop a currently running logging session with a specific scenario, type:</span></span>
    
        Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
    
    <span data-ttu-id="9d662-128">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="9d662-128">For example:</span></span>
    
        Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
    
    <span data-ttu-id="9d662-129">Questo comando interromperà la registrazione con lo scenario UserReplicatior in pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="9d662-129">This command will stop logging with the UserReplicatior scenario on pool01.contoso.net.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9d662-130">I log creati nel corso di questa sessione di registrazione utilizzando lo scenario UserReplicator non vengono eliminati.</span><span class="sxs-lookup"><span data-stu-id="9d662-130">Logs created during this logging session using the UserReplicator scenario are not deleted.</span></span> <span data-ttu-id="9d662-131">La registrazione resta disponibile per l'esecuzione di ricerche mediante il comando Search-CsClsLogging.</span><span class="sxs-lookup"><span data-stu-id="9d662-131">The logging is still available for you to execute searches against using the Search-CsClsLogging command.</span></span> <span data-ttu-id="9d662-132">Per informazioni dettagliate, vedere <A href="https://docs.microsoft.com/powershell/module/skype/Search-CsClsLogging">Search-CsClsLogging</A>.</span><span class="sxs-lookup"><span data-stu-id="9d662-132">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Search-CsClsLogging">Search-CsClsLogging</A>.</span></span>

    
    </div>

<span data-ttu-id="9d662-p107">Il cmdlet Stop-CsClsLogging funge da comando complementare a Start-CsClsLogging e interrompe la sessione di registrazione, definita dagli scenari, conservando i log creati. È possibile eseguire un totale di due scenari su un dato computer in qualsiasi momento. L'interruzione di uno scenario per raccogliere informazioni utilizzando uno scenario diverso è un'attività comune, utile nella maggior parte delle procedure di risoluzione dei problemi relativi ai carichi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9d662-p107">Acting as the companion command to Start-CsClsLogging, the Stop-CsClsLogging cmdlet ends the logging session, defined by scenarios, and retains the logs created by the logging session. You can run two scenarios on a given computer at any time. The method of stopping one scenario to gather information using another scenario is a common task that you can perform during most workload troubleshooting.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9d662-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d662-136">See Also</span></span>


[<span data-ttu-id="9d662-137">Utilizzo di Start per il servizio di registrazione centralizzato per l'acquisizione dei log in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9d662-137">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</span></span>](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)  


[<span data-ttu-id="9d662-138">Panoramica del servizio di registrazione centralizzato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9d662-138">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[<span data-ttu-id="9d662-139">Show-CsClsLogging</span><span class="sxs-lookup"><span data-stu-id="9d662-139">Show-CsClsLogging</span></span>](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging)  
[<span data-ttu-id="9d662-140">Start-CsClsLogging</span><span class="sxs-lookup"><span data-stu-id="9d662-140">Start-CsClsLogging</span></span>](https://docs.microsoft.com/powershell/module/skype/Start-CsClsLogging)  
[<span data-ttu-id="9d662-141">Stop-CsClsLogging</span><span class="sxs-lookup"><span data-stu-id="9d662-141">Stop-CsClsLogging</span></span>](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


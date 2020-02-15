---
title: 'Lync Server 2013: installazione dei Lync Server 2013 Management Pack'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: nstalling the Lync Server 2013 management packs
ms:assetid: b800d4ab-fdc8-4c72-a76a-b78932779fe3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205202(v=OCS.15)
ms:contentKeyID: 48185233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2324d166ab43153cf37b71500da438e6db6b4b4f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029517"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-management-packs"></a><span data-ttu-id="7bc14-102">Installazione dei Management Pack di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7bc14-102">Installing the Lync Server 2013 management packs</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7bc14-103">_**Ultimo argomento modificato:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="7bc14-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="7bc14-104">Da solo, System Center Operations Manager è in grado di monitorare solo una piccola parte del sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="7bc14-104">By itself, System Center Operations Manager has the ability to monitor only a small portion of the Windows operating system.</span></span> <span data-ttu-id="7bc14-105">Tuttavia, è possibile estendere le funzionalità di System Center Operations Manager installando Management Pack, software che determina quali elementi possono essere monitorati dal System Center Operations Manager, includendo il monitoraggio e il modo in cui devono essere monitorati gli avvisi. attivata e segnalata.</span><span class="sxs-lookup"><span data-stu-id="7bc14-105">However, you can extend the capabilities of System Center Operations Manager by installing management packs, software that dictates which items System Center Operations Manager can monitor, including how those items should be monitored and how alerts should be triggered and reported.</span></span> <span data-ttu-id="7bc14-106">Microsoft Lync Server 2013 include due Management Pack di System Center Operations Manager che forniscono le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="7bc14-106">Microsoft Lync Server 2013 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

  - <span data-ttu-id="7bc14-107">Il componente e User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) tiene traccia dei problemi di Lync Server registrati nei registri eventi, registrati dai contatori delle prestazioni o registrati nei record dettagli chiamata (CDR) o nella qualità di esperienza (QoE) database.</span><span class="sxs-lookup"><span data-stu-id="7bc14-107">The Component and User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) tracks Lync Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDR) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="7bc14-108">Per i problemi critici, System Center Operations Manager può essere configurato per informare immediatamente gli amministratori tramite messaggi di posta elettronica, messaggi istantanei o SMS (Short Message Service).</span><span class="sxs-lookup"><span data-stu-id="7bc14-108">For critical problems, System Center Operations Manager can be configured to immediately notify administrators via email, instant message, or Short Message Service (SMS) messaging.</span></span> <span data-ttu-id="7bc14-109">La tecnologia SMS viene utilizzata per inviare messaggi di testo da un dispositivo mobile a un altro.</span><span class="sxs-lookup"><span data-stu-id="7bc14-109">SMS is the technology used to send text messages from one mobile device to another.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7bc14-110">Per ulteriori informazioni sulla configurazione della notifica di Operations Manager, vedere Configuring Notification in <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?linkid=268785</A>the TechNet Library at.</span><span class="sxs-lookup"><span data-stu-id="7bc14-110">For more information on configuring Operations Manager notification, see Configuring Notification in the TechNet Library at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?linkid=268785</A>.</span></span>

    
    </div>

  - <span data-ttu-id="7bc14-111">Il Active Monitoring Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) verifica in modo proattivo i componenti chiave di Lync Server, ad esempio l'accesso al sistema, lo scambio di messaggi istantanei o la chiamata a un telefono che si trova sul telefono pubblico a commutazione rete (PSTN).</span><span class="sxs-lookup"><span data-stu-id="7bc14-111">The Active Monitoring Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) proactively tests key Lync Server components such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="7bc14-112">Questi test vengono eseguiti utilizzando i cmdlet per le transazioni sintetiche di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7bc14-112">These tests are conducted using the Lync Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="7bc14-113">Il cmdlet **Test-CsIM** ad esempio viene utilizzato per simulare una conversazione istantanea tra due utenti di test.</span><span class="sxs-lookup"><span data-stu-id="7bc14-113">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="7bc14-114">Se questa conversazione simulata ha esito negativo, verrà generato un avviso.</span><span class="sxs-lookup"><span data-stu-id="7bc14-114">If this simulated messaging conversation fails an alert will be generated.</span></span>

<span data-ttu-id="7bc14-115">I due Management Pack inclusi in Lync Server 2013 includono un numero elevato di miglioramenti rispetto ai Management Pack utilizzati con Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="7bc14-115">The two management packs included with Lync Server 2013 include a large number of enhancements over the management packs used with Microsoft Lync Server 2010.</span></span> <span data-ttu-id="7bc14-116">Ad esempio, il Lync Server 2013 Component Management Pack non è limitato al monitoraggio di Lync Server stesso.</span><span class="sxs-lookup"><span data-stu-id="7bc14-116">For example, the Lync Server 2013 Component Management Pack is not limited to monitoring Lync Server itself.</span></span> <span data-ttu-id="7bc14-117">Oltre a monitorare i registri eventi e i contatori delle prestazioni per Lync Server, il Management Pack del componente può anche tenere conto delle prestazioni e inviare avvisi per gli elementi cruciali, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="7bc14-117">In addition to monitoring event logs and performance counters for Lync Server, the Component Management pack can also track the performance of, and issue alerts for, crucial items such as:</span></span>

  - <span data-ttu-id="7bc14-118">**Gli avvisi di Internet Information Services (IIS)**   verranno emessi se Internet Information Services non è in linea.</span><span class="sxs-lookup"><span data-stu-id="7bc14-118">**Internet Information Services (IIS)**   Alerts will be issued if Internet Information Services goes offline.</span></span> <span data-ttu-id="7bc14-119">Questo è importante perché i servizi Web di Lync Server si basano su IIS.</span><span class="sxs-lookup"><span data-stu-id="7bc14-119">This is important, because the Lync Server web services rely on IIS.</span></span>

  - <span data-ttu-id="7bc14-120">**Gli avvisi sull'utilizzo**   dei processi verranno emessi se le risorse di sistema, ad esempio la memoria disponibile, cominciano a funzionare in basso.</span><span class="sxs-lookup"><span data-stu-id="7bc14-120">**Process usage**   Alerts will be issued if system resources (such as available memory) begin to run low.</span></span> <span data-ttu-id="7bc14-121">Questi avvisi verranno emessi anche se Lync Server non è responsabile dell'utilizzo del sistema elevato.</span><span class="sxs-lookup"><span data-stu-id="7bc14-121">These alerts will be issued even if Lync Server is not responsible for the high system usage.</span></span>

  - <span data-ttu-id="7bc14-122">**Eventi di errore del computer gli**   avvisi verranno emessi in caso di un problema hardware o software che minacci la redditività di un server.</span><span class="sxs-lookup"><span data-stu-id="7bc14-122">**Computer failure events**   Alerts will be issued in case of a hardware or software issue that threatens the viability of a server.</span></span> <span data-ttu-id="7bc14-123">Ad esempio, gli amministratori di Lync Server riceveranno una notifica se un server sembra rischiare di riscontrare un errore del disco rigido.</span><span class="sxs-lookup"><span data-stu-id="7bc14-123">For example, Lync Server administrators will be notified if a server appears to be in danger of experiencing a hard disk failure.</span></span>

<span data-ttu-id="7bc14-124">I nuovi Management Pack inoltre offrono funzionalità di segnalazione avanzate.</span><span class="sxs-lookup"><span data-stu-id="7bc14-124">The new management packs also feature enhanced reporting.</span></span> <span data-ttu-id="7bc14-125">I nuovi rapporti per Lync Server 2013 includono:</span><span class="sxs-lookup"><span data-stu-id="7bc14-125">New reports for Lync Server 2013 include:</span></span>

  - <span data-ttu-id="7bc14-126">**End to end scenario availability report**   questo rapporto descrive in dettaglio la disponibilità/tempo di uptime per i servizi chiave di Lync Server, ad esempio la registrazione o la presenza.</span><span class="sxs-lookup"><span data-stu-id="7bc14-126">**End to End Scenario Availability Report**   This report details the availability/uptime for key Lync Server services such as registration or presence.</span></span>

  - <span data-ttu-id="7bc14-127">**Rapporto capacità utilizzando**   le informazioni sui contatori delle prestazioni, in questo report vengono visualizzate le tendenze per i componenti di sistema, ad esempio la disponibilità della memoria e l'utilizzo</span><span class="sxs-lookup"><span data-stu-id="7bc14-127">**Capacity Report**   Using performance counter information, this report shows trends for system components such as memory availability and processor usage.</span></span>

  - <span data-ttu-id="7bc14-128">**Report componente in**   questo report sono elencati i generatori di avvisi principali raggruppati in base al componente Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7bc14-128">**Component Report**   This report lists the top alert generators grouped by Lync Server component.</span></span>

<span data-ttu-id="7bc14-129">Oltre a questi rapporti predefiniti, i Management Pack per Lync Server 2013 segnalano automaticamente gli avvisi per l'affidabilità delle chiamate (metriche misurate tramite registrazione dettagli chiamata) e gli Stati QoE (metriche misurate in base alla qualità dell'esperienza).</span><span class="sxs-lookup"><span data-stu-id="7bc14-129">In addition to these predesigned reports, the management packs for Lync Server 2013 automatically report alerts for both Call Reliability (metrics measured by Call Detail Recording) and QoE states (metrics measured by Quality of Experience).</span></span> <span data-ttu-id="7bc14-130">Se è stata abilitata la registrazione dettagli chiamata, è possibile esaminare gli avvisi relativi all'affidabilità delle chiamate eseguendo la procedura seguente dalla console di System Center Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="7bc14-130">If you have enabled Call Detail Recording, you can review Call Reliability alerts by completing the following procedure from the System Center Operations Manager console:</span></span>

  - <span data-ttu-id="7bc14-131">Espandere **Monitoring**, **Microsoft Lync Server 2013 Health** e **Call Reliability and Media Quality** e quindi fare clic su **Call Reliability**.</span><span class="sxs-lookup"><span data-stu-id="7bc14-131">Expand **Monitoring**, expand **Microsoft Lync Server 2013 Health**, expand **Call Reliability and Media Quality**, and then click **Call Reliability**.</span></span>

<span data-ttu-id="7bc14-132">Per visualizzare gli avvisi relativi alla qualità delle esperienze, eseguire questa procedura dalla console di System Center Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="7bc14-132">To view Quality of Experience alerts, complete this procedure from the System Center Operations Manager console:</span></span>

  - <span data-ttu-id="7bc14-133">Espandere **Monitoring**, **Microsoft Lync Server 2013 Health**, **Call Reliability and Media Quality** e quindi **Media Quality**.</span><span class="sxs-lookup"><span data-stu-id="7bc14-133">Expand **Monitoring**, expand **Microsoft Lync Server 2013 Health**, expand **Call Reliability and Media Quality**, and then expand **Media Quality**.</span></span>

<span data-ttu-id="7bc14-134">I Management Pack per Lync Server 2013 ora utilizzano l'individuazione a livello di computer invece del meccanismo di individuazione centrale utilizzato in Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="7bc14-134">The management packs for Lync Server 2013 now use machine-level discovery instead of the central discovery mechanism used in Microsoft Lync Server 2010.</span></span> <span data-ttu-id="7bc14-135">Questo significa che ogni agente del centro di sistema si riscoprirà e ne riferirà la presenza al server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="7bc14-135">This means that each System Center agent essentially discovers itself and reports its existence to the Central Management Server.</span></span> <span data-ttu-id="7bc14-136">L'utilizzo dell'individuazione a livello di computer semplifica l'amministrazione dell'infrastruttura del centro di sistema e consente anche diverse versioni dei Management Pack di Lync Server (ad esempio, Management Pack per Lync Server 2010 e Management Pack per Lync Server 2013) coesistere.</span><span class="sxs-lookup"><span data-stu-id="7bc14-136">Using machine-level discovery simplifies administration of your System Center infrastructure and also allows different versions of the Lync Server management packs (for example, management packs for Lync Server 2010 and management packs for Lync Server 2013) to coexist.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


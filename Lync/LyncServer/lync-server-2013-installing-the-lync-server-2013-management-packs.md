---
title: 'Lync Server 2013: installazione di Lync Server 2013 Management Pack'
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
ms.openlocfilehash: ffc102eccdbaa941e2691df88899c0cc01348838
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-management-packs"></a><span data-ttu-id="86161-102">Installazione dei Management Pack di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86161-102">Installing the Lync Server 2013 management packs</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86161-103">_**Argomento Ultima modifica:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="86161-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="86161-104">Di per sé, System Center Operations Manager è in grado di monitorare solo una piccola parte del sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="86161-104">By itself, System Center Operations Manager has the ability to monitor only a small portion of the Windows operating system.</span></span> <span data-ttu-id="86161-105">È tuttavia possibile estendere le funzionalità di System Center Operations Manager installando Management Pack, un software che detta gli elementi che System Center Operations Manager può monitorare, incluso il monitoraggio degli elementi e la modalità di visualizzazione degli avvisi attivato e segnalato.</span><span class="sxs-lookup"><span data-stu-id="86161-105">However, you can extend the capabilities of System Center Operations Manager by installing management packs, software that dictates which items System Center Operations Manager can monitor, including how those items should be monitored and how alerts should be triggered and reported.</span></span> <span data-ttu-id="86161-106">Microsoft Lync Server 2013 include due Management Pack di System Center Operations Manager che fornisce le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="86161-106">Microsoft Lync Server 2013 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

  - <span data-ttu-id="86161-107">Il componente e User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) tiene traccia dei problemi di Lync Server registrati nei registri eventi, registrati da contatori delle prestazioni oppure registrati nei record dettagli chiamata (CDR) o nella qualità dell'esperienza (QoE) database.</span><span class="sxs-lookup"><span data-stu-id="86161-107">The Component and User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) tracks Lync Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDR) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="86161-108">Per problemi critici, System Center Operations Manager può essere configurato per informare immediatamente gli amministratori tramite posta elettronica, messaggio istantaneo o messaggistica SMS (Short Message Service).</span><span class="sxs-lookup"><span data-stu-id="86161-108">For critical problems, System Center Operations Manager can be configured to immediately notify administrators via email, instant message, or Short Message Service (SMS) messaging.</span></span> <span data-ttu-id="86161-109">SMS è la tecnologia usata per inviare SMS da un dispositivo mobile a un altro.</span><span class="sxs-lookup"><span data-stu-id="86161-109">SMS is the technology used to send text messages from one mobile device to another.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="86161-110">Per altre informazioni sulla configurazione della notifica di Operations Manager, vedere Configurazione della notifica in TechNet <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?linkid=268785</A>Library at.</span><span class="sxs-lookup"><span data-stu-id="86161-110">For more information on configuring Operations Manager notification, see Configuring Notification in the TechNet Library at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?linkid=268785</A>.</span></span>

    
    </div>

  - <span data-ttu-id="86161-111">Il Active Monitoring Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) verifica in modo proattivo i componenti principali di Lync Server, ad esempio l'accesso al sistema, lo scambio di messaggi istantanei o l'esecuzione di chiamate a un telefono che si trova nel telefono con commutazioni pubbliche rete (PSTN).</span><span class="sxs-lookup"><span data-stu-id="86161-111">The Active Monitoring Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) proactively tests key Lync Server components such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="86161-112">Questi test vengono eseguiti usando i cmdlet di transazione sintetica di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="86161-112">These tests are conducted using the Lync Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="86161-113">Ad esempio, il cmdlet **Test-CsIM** viene usato per simulare una conversazione di messaggistica istantanea tra una coppia di utenti di test.</span><span class="sxs-lookup"><span data-stu-id="86161-113">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="86161-114">Se la conversazione di messaggistica simulata non riesce, verrà generato un avviso.</span><span class="sxs-lookup"><span data-stu-id="86161-114">If this simulated messaging conversation fails an alert will be generated.</span></span>

<span data-ttu-id="86161-115">I due Management Pack inclusi in Lync Server 2013 includono un numero elevato di miglioramenti nei Management Pack usati con Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="86161-115">The two management packs included with Lync Server 2013 include a large number of enhancements over the management packs used with Microsoft Lync Server 2010.</span></span> <span data-ttu-id="86161-116">Ad esempio, il pacchetto di gestione dei componenti di Lync Server 2013 non si limita a monitorare Lync Server stesso.</span><span class="sxs-lookup"><span data-stu-id="86161-116">For example, the Lync Server 2013 Component Management Pack is not limited to monitoring Lync Server itself.</span></span> <span data-ttu-id="86161-117">Oltre a monitorare i registri eventi e i contatori delle prestazioni per Lync Server, il Management Pack del componente può anche tenere traccia delle prestazioni e inviare avvisi per elementi cruciali, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="86161-117">In addition to monitoring event logs and performance counters for Lync Server, the Component Management pack can also track the performance of, and issue alerts for, crucial items such as:</span></span>

  - <span data-ttu-id="86161-118">**Gli avvisi di Internet Information Services (IIS)**   verranno emessi se Internet Information Services è offline.</span><span class="sxs-lookup"><span data-stu-id="86161-118">**Internet Information Services (IIS)**   Alerts will be issued if Internet Information Services goes offline.</span></span> <span data-ttu-id="86161-119">Questo è importante perché i servizi Web di Lync Server si basano su IIS.</span><span class="sxs-lookup"><span data-stu-id="86161-119">This is important, because the Lync Server web services rely on IIS.</span></span>

  - <span data-ttu-id="86161-120">\*\*\*\*   Gli avvisi per l'uso del processo verranno emessi se le risorse di sistema, ad esempio la memoria disponibile, iniziano a funzionare in basso.</span><span class="sxs-lookup"><span data-stu-id="86161-120">**Process usage**   Alerts will be issued if system resources (such as available memory) begin to run low.</span></span> <span data-ttu-id="86161-121">Questi avvisi verranno emessi anche se Lync Server non è responsabile dell'uso elevato del sistema.</span><span class="sxs-lookup"><span data-stu-id="86161-121">These alerts will be issued even if Lync Server is not responsible for the high system usage.</span></span>

  - <span data-ttu-id="86161-122">**Gli avvisi sugli eventi**   di errore del computer verranno emessi in caso di problemi hardware o software che minacciano la redditività di un server.</span><span class="sxs-lookup"><span data-stu-id="86161-122">**Computer failure events**   Alerts will be issued in case of a hardware or software issue that threatens the viability of a server.</span></span> <span data-ttu-id="86161-123">Ad esempio, gli amministratori di Lync Server verranno informati se un server sembra essere in pericolo di un errore del disco rigido.</span><span class="sxs-lookup"><span data-stu-id="86161-123">For example, Lync Server administrators will be notified if a server appears to be in danger of experiencing a hard disk failure.</span></span>

<span data-ttu-id="86161-124">I nuovi Management Pack includono anche report avanzati.</span><span class="sxs-lookup"><span data-stu-id="86161-124">The new management packs also feature enhanced reporting.</span></span> <span data-ttu-id="86161-125">I nuovi report per Lync Server 2013 includono:</span><span class="sxs-lookup"><span data-stu-id="86161-125">New reports for Lync Server 2013 include:</span></span>

  - <span data-ttu-id="86161-126">**Report disponibilità scenario finale**   questo report descrive in dettaglio la disponibilità/uptime dei servizi principali di Lync Server, ad esempio registrazione o presenza.</span><span class="sxs-lookup"><span data-stu-id="86161-126">**End to End Scenario Availability Report**   This report details the availability/uptime for key Lync Server services such as registration or presence.</span></span>

  - <span data-ttu-id="86161-127">**Report capacità con**   le informazioni sui contatori delle prestazioni, questo report Mostra le tendenze per i componenti di sistema, ad esempio la disponibilità della memoria e l'uso del processore</span><span class="sxs-lookup"><span data-stu-id="86161-127">**Capacity Report**   Using performance counter information, this report shows trends for system components such as memory availability and processor usage.</span></span>

  - <span data-ttu-id="86161-128">**Report componente questo**   report elenca i generatori di avvisi principali raggruppati in base al componente Lync Server.</span><span class="sxs-lookup"><span data-stu-id="86161-128">**Component Report**   This report lists the top alert generators grouped by Lync Server component.</span></span>

<span data-ttu-id="86161-129">Oltre a questi report predefiniti, i Management Pack per Lync Server 2013 segnalano automaticamente gli avvisi sia per l'affidabilità delle chiamate (metriche misurate in base alla registrazione dei dettagli delle chiamate) che per gli Stati QoE (metriche misurate in base alla qualità dell'esperienza).</span><span class="sxs-lookup"><span data-stu-id="86161-129">In addition to these predesigned reports, the management packs for Lync Server 2013 automatically report alerts for both Call Reliability (metrics measured by Call Detail Recording) and QoE states (metrics measured by Quality of Experience).</span></span> <span data-ttu-id="86161-130">Se è stata abilitata la registrazione dei dettagli delle chiamate, è possibile esaminare gli avvisi di affidabilità delle chiamate completando la procedura seguente dalla console di System Center Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="86161-130">If you have enabled Call Detail Recording, you can review Call Reliability alerts by completing the following procedure from the System Center Operations Manager console:</span></span>

  - <span data-ttu-id="86161-131">Espandi **monitoraggio**, Espandi **Microsoft Lync Server 2013 Health**, Espandi l' **affidabilità delle chiamate e la qualità degli elementi multimediali**e quindi fai clic su **affidabilità chiamata**.</span><span class="sxs-lookup"><span data-stu-id="86161-131">Expand **Monitoring**, expand **Microsoft Lync Server 2013 Health**, expand **Call Reliability and Media Quality**, and then click **Call Reliability**.</span></span>

<span data-ttu-id="86161-132">Per visualizzare gli avvisi relativi alla qualità dell'esperienza, eseguire questa procedura dalla console di System Center Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="86161-132">To view Quality of Experience alerts, complete this procedure from the System Center Operations Manager console:</span></span>

  - <span data-ttu-id="86161-133">Espandi **monitoraggio**, Espandi **Microsoft Lync Server 2013 Health**, Espandi l' **affidabilità delle chiamate e la qualità degli elementi multimediali**e quindi Espandi **qualità multimediale**.</span><span class="sxs-lookup"><span data-stu-id="86161-133">Expand **Monitoring**, expand **Microsoft Lync Server 2013 Health**, expand **Call Reliability and Media Quality**, and then expand **Media Quality**.</span></span>

<span data-ttu-id="86161-134">I Management Pack per Lync Server 2013 ora usano l'individuazione a livello di computer anziché il meccanismo di individuazione centralizzato usato in Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="86161-134">The management packs for Lync Server 2013 now use machine-level discovery instead of the central discovery mechanism used in Microsoft Lync Server 2010.</span></span> <span data-ttu-id="86161-135">Questo significa che ogni agente del centro di sistema si rivela in sostanza e ne segnala l'esistenza al server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="86161-135">This means that each System Center agent essentially discovers itself and reports its existence to the Central Management Server.</span></span> <span data-ttu-id="86161-136">L'uso dell'individuazione a livello di computer semplifica l'amministrazione dell'infrastruttura del centro di sistema e consente anche diverse versioni di Lync Server Management Pack, ad esempio Management Pack per Lync Server 2010 e Management Pack per Lync Server 2013, per coesistere.</span><span class="sxs-lookup"><span data-stu-id="86161-136">Using machine-level discovery simplifies administration of your System Center infrastructure and also allows different versions of the Lync Server management packs (for example, management packs for Lync Server 2010 and management packs for Lync Server 2013) to coexist.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


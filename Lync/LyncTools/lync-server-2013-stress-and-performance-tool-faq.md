---
title: Domande frequenti su Lync Server 2013 stress and Performance Tool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Stress and Performance Tool FAQ
ms:assetid: a5aff705-320c-4916-8094-23046b2a1b18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945600(v=OCS.15)
ms:contentKeyID: 51541426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 590453f6270ebcd2beebbb26b8035f9e33cc2cd7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-stress-and-performance-tool-faq"></a><span data-ttu-id="96634-102">Domande frequenti su Lync Server 2013 stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="96634-102">Lync Server 2013 Stress and Performance Tool FAQ</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96634-103">_**Ultimo argomento modificato:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="96634-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<div>

## <a name="frequently-asked-questions"></a><span data-ttu-id="96634-104">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="96634-104">Frequently Asked Questions</span></span>

<span data-ttu-id="96634-105">Di seguito sono riportate alcune domande frequenti sullo strumento Lync Server 2013 stress and performance.</span><span class="sxs-lookup"><span data-stu-id="96634-105">Here are some frequently asked questions about the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="can-i-run-lyncperftoolexe-in-production"></a><span data-ttu-id="96634-106">È possibile eseguire LyncPerfTool. exe in produzione?</span><span class="sxs-lookup"><span data-stu-id="96634-106">Can I run LyncPerfTool.exe in production?</span></span>

<span data-ttu-id="96634-107">Non è consigliabile.</span><span class="sxs-lookup"><span data-stu-id="96634-107">We do not recommend this.</span></span> <span data-ttu-id="96634-108">Questo strumento avrà un impatto sulle prestazioni del server, sulla sicurezza e sull'esperienza utente.</span><span class="sxs-lookup"><span data-stu-id="96634-108">This tool will impact server performance, security, and user experience.</span></span>

</div>

<div>

## <a name="i-am-logging-on-my-users-for-the-first-time-why-are-the-servers-running-at-such-high-load"></a><span data-ttu-id="96634-109">La prima volta che si accede ai miei utenti.</span><span class="sxs-lookup"><span data-stu-id="96634-109">I am logging on my users for the first time.</span></span> <span data-ttu-id="96634-110">Perché i server sono in esecuzione a un carico così elevato?</span><span class="sxs-lookup"><span data-stu-id="96634-110">Why are the servers running at such high load?</span></span>

<span data-ttu-id="96634-111">La prima volta che si esegue l'accesso agli utenti, sono presenti operazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="96634-111">The first time the users log on, there are additional operations that occur.</span></span> <span data-ttu-id="96634-112">Di conseguenza, le prestazioni sul server back-end di Microsoft SQL Server verranno danneggiate.</span><span class="sxs-lookup"><span data-stu-id="96634-112">As a result, the performance on the Microsoft SQL Server Back End Server will be degraded.</span></span> <span data-ttu-id="96634-113">È consigliabile eseguire un test breve che accede a tutti gli utenti e quindi riavviare i client prima di misurare i risultati.</span><span class="sxs-lookup"><span data-stu-id="96634-113">We recommend that you run a short test that logs on all of the users, and then restart the clients before you measure results.</span></span> <span data-ttu-id="96634-114">Non sono supportate più di 12 sessioni di accesso utente simultanee al secondo, ma ciò dipende dalla configurazione hardware.</span><span class="sxs-lookup"><span data-stu-id="96634-114">We do not support more than 12 concurrent user logon sessions per second, but this depends on your hardware configuration.</span></span>

</div>

<div>

## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a><span data-ttu-id="96634-115">I client esauriscono la memoria.</span><span class="sxs-lookup"><span data-stu-id="96634-115">My clients are running out of memory.</span></span> <span data-ttu-id="96634-116">Cosa si può fare?</span><span class="sxs-lookup"><span data-stu-id="96634-116">What should I do?</span></span>

<span data-ttu-id="96634-117">Se i client esauriscono la memoria, è necessario ridurre il numero di utenti per computer.</span><span class="sxs-lookup"><span data-stu-id="96634-117">If your clients are running out of memory, you need to reduce the number of users per computer.</span></span>

</div>

<div>

## <a name="my-clients-are-at-100-percent-cpu-all-the-time-what-should-i-do"></a><span data-ttu-id="96634-118">I client sono al 100 percento della CPU per tutto il tempo.</span><span class="sxs-lookup"><span data-stu-id="96634-118">My clients are at 100 percent CPU all the time.</span></span> <span data-ttu-id="96634-119">Cosa si può fare?</span><span class="sxs-lookup"><span data-stu-id="96634-119">What should I do?</span></span>

<span data-ttu-id="96634-120">Se i client sono in esecuzione con CPU molto alta dopo che tutti gli utenti hanno effettuato l'accesso, è necessario ridurre il numero di utenti per computer.</span><span class="sxs-lookup"><span data-stu-id="96634-120">If your clients are running with very high CPU after all the users have logged on, you need to reduce the number of users per computer.</span></span> <span data-ttu-id="96634-121">Gli alti picchi di CPU sono accettabili, ma se sono sostenuti, è necessario ridurre il carico.</span><span class="sxs-lookup"><span data-stu-id="96634-121">High CPU spikes are acceptable, but if it is sustained, you need to reduce the load.</span></span>

</div>

<div>

## <a name="can-i-run-the-tool-on-the-server-itself"></a><span data-ttu-id="96634-122">È possibile eseguire lo strumento nel server stesso?</span><span class="sxs-lookup"><span data-stu-id="96634-122">Can I run the tool on the server itself?</span></span>

<span data-ttu-id="96634-123">No.</span><span class="sxs-lookup"><span data-stu-id="96634-123">No.</span></span> <span data-ttu-id="96634-124">Questo scenario non è supportato e potrebbe avere esito negativo a causa di una mancata corrispondenza binaria.</span><span class="sxs-lookup"><span data-stu-id="96634-124">This scenario is not supported and may fail due to a binary mismatch.</span></span> <span data-ttu-id="96634-125">Inoltre, poiché il punto è misurare il consumo di risorse sul server, l'esecuzione dello strumento consentirebbe di eseguire il rendering delle misurazioni insignificanti.</span><span class="sxs-lookup"><span data-stu-id="96634-125">Also, because the point is to measure resource consumption on the server, running the tool there would render the measurements meaningless.</span></span>

</div>

<div>

## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a><span data-ttu-id="96634-126">È possibile eseguire LyncPerfTool. exe su un server virtuale o su Microsoft Hyper-V Server 2008/2012?</span><span class="sxs-lookup"><span data-stu-id="96634-126">Can I run LyncPerfTool.exe on a Virtual Server or on Microsoft Hyper-V Server 2008/2012?</span></span>

<span data-ttu-id="96634-127">Sì.</span><span class="sxs-lookup"><span data-stu-id="96634-127">Yes.</span></span>

</div>

<div>

## <a name="what-does-mpop-mean"></a><span data-ttu-id="96634-128">Cosa significa MPOP?</span><span class="sxs-lookup"><span data-stu-id="96634-128">What does MPOP mean?</span></span>

<span data-ttu-id="96634-129">MPOP è sinonimo di più punti di presenza.</span><span class="sxs-lookup"><span data-stu-id="96634-129">MPOP stands for multiple points of presence.</span></span> <span data-ttu-id="96634-130">Si intende simulare lo scenario in cui gli utenti accedono a Lync 2013 da più computer.</span><span class="sxs-lookup"><span data-stu-id="96634-130">It is meant to simulate the scenario where users are logged on to Lync 2013 from multiple machines.</span></span> <span data-ttu-id="96634-131">Si noti che in LyncPerfTool. exe ogni endpoint utilizza il profilo predefinito, ovvero che il profilo non è suddiviso tra i due punti di presenza.</span><span class="sxs-lookup"><span data-stu-id="96634-131">Note that in LyncPerfTool.exe, each endpoint uses the default profile (that is, the profile is not split between the two points of presence).</span></span>

</div>

<div>

## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a><span data-ttu-id="96634-132">Sono stati avviati LyncPerfTool. exe ma non è stato avviato alcun evento.</span><span class="sxs-lookup"><span data-stu-id="96634-132">I started LyncPerfTool.exe but nothing is happening.</span></span> <span data-ttu-id="96634-133">Per quale motivo?</span><span class="sxs-lookup"><span data-stu-id="96634-133">What’s going on?</span></span>

<span data-ttu-id="96634-134">Controllare il contatore totale degli endpoint attivi sui client per verificare se gli utenti si connettono.</span><span class="sxs-lookup"><span data-stu-id="96634-134">Check the Total Active Endpoints counter on the clients to see if the users are connecting.</span></span> <span data-ttu-id="96634-135">Se gli utenti non si connettono, verificare la configurazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="96634-135">If users are not connecting, verify your Lync Server 2013 configuration.</span></span> <span data-ttu-id="96634-136">Questo problema si verifica in genere perché il nome del server, il prefisso dell'utente o la password non è corretta.</span><span class="sxs-lookup"><span data-stu-id="96634-136">This issue usually occurs because the server name, the user prefix, or the password is incorrect.</span></span> <span data-ttu-id="96634-137">Si noti che i client esterni devono specificare il proxy di accesso come valore TargetServer.</span><span class="sxs-lookup"><span data-stu-id="96634-137">Note that external clients should specify the Access Proxy as the TargetServer value.</span></span> <span data-ttu-id="96634-138">Verificare la porta nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="96634-138">Verify the port in the configuration file.</span></span>

</div>

<div>

## <a name="how-do-i-know-something-is-happening"></a><span data-ttu-id="96634-139">Come si fa a sapere che sta accadendo qualcosa?</span><span class="sxs-lookup"><span data-stu-id="96634-139">How do I know something is happening?</span></span>

<span data-ttu-id="96634-140">I vari contatori delle prestazioni di LyncPerfTool indicano se gli utenti si connettono e eseguono azioni.</span><span class="sxs-lookup"><span data-stu-id="96634-140">The various LyncPerfTool performance counters indicate whether or not users are connecting and performing actions.</span></span> <span data-ttu-id="96634-141">Tuttavia, un modo semplice per effettuare la verifica consiste nell'accedere a uno degli account utilizzando Lync 2013 ed eseguire l'azione desiderata.</span><span class="sxs-lookup"><span data-stu-id="96634-141">However, an easy way to check is to log on to one of the accounts by using Lync 2013 and performing the action you want.</span></span>

</div>

<div>

## <a name="i-have-live-communications-server-2007-r2-capacity-planning-tools-andor-lync-server-2010-installed-is-that-ok"></a><span data-ttu-id="96634-142">Sono stati installati gli strumenti di pianificazione della capacità di Live Communications Server 2007 R2 e/o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="96634-142">I have Live Communications Server 2007 R2 Capacity Planning Tools and/or Lync Server 2010 installed.</span></span> <span data-ttu-id="96634-143">È tutto OK?</span><span class="sxs-lookup"><span data-stu-id="96634-143">Is that OK?</span></span>

<span data-ttu-id="96634-144">No.</span><span class="sxs-lookup"><span data-stu-id="96634-144">No.</span></span> <span data-ttu-id="96634-145">Sono presenti problemi di interoperabilità ed è necessario disinstallare tutte le versioni precedenti del prodotto.</span><span class="sxs-lookup"><span data-stu-id="96634-145">There are interoperability issues, and you must uninstall all previous versions of this product.</span></span>

</div>

<div>

## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a><span data-ttu-id="96634-146">Gli strumenti di stress e prestazioni configurano la topologia del server delle informazioni di chiamata CAA?</span><span class="sxs-lookup"><span data-stu-id="96634-146">Will the Stress and Performance tools set up the CAA Call Information server topology?</span></span>

<span data-ttu-id="96634-147">No.</span><span class="sxs-lookup"><span data-stu-id="96634-147">No.</span></span> <span data-ttu-id="96634-148">Gli strumenti creano solo gli utenti, i contatti e le liste di distribuzione e simulano il carico dell'utente.</span><span class="sxs-lookup"><span data-stu-id="96634-148">The tools only create users, contacts, and distribution lists, and simulate user load.</span></span>

</div>

<div>

## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a><span data-ttu-id="96634-149">Qual è il numero massimo di utenti supportati dagli strumenti?</span><span class="sxs-lookup"><span data-stu-id="96634-149">What is the maximum number of users that the tools support?</span></span>

<span data-ttu-id="96634-150">È stato creato un totale di 80.000 utenti e sono stati eseguiti test per un totale di 30.000 utenti, utilizzando questi strumenti.</span><span class="sxs-lookup"><span data-stu-id="96634-150">We have created up to a total of 80,000 users and executed tests totaling 30,000 users, using these tools.</span></span> <span data-ttu-id="96634-151">È consigliabile disporre di un massimo di 120.000 utenti, anche se le limitazioni tecniche consentono un valore superiore, a seconda dell'hardware del server e del client.</span><span class="sxs-lookup"><span data-stu-id="96634-151">We suggest a maximum of 120,000 users, although the technical limitations allow for a higher value, depending on the client and server hardware available.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


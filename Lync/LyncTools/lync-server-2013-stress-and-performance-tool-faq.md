---
title: Domande frequenti su Lync Server 2013 stress and Performance Tool
description: Domande frequenti su Lync Server 2013 stress and Performance Tool.
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
ms.openlocfilehash: 716325390bc33df209be3bdc67ed8b6cd7d1ec30
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573542"
---
# <a name="lync-server-2013-stress-and-performance-tool-faq"></a><span data-ttu-id="62ebd-103">Domande frequenti su Lync Server 2013 stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="62ebd-103">Lync Server 2013 Stress and Performance Tool FAQ</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62ebd-104">_**Ultimo argomento modificato:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="62ebd-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<div>

## <a name="frequently-asked-questions"></a><span data-ttu-id="62ebd-105">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="62ebd-105">Frequently Asked Questions</span></span>

<span data-ttu-id="62ebd-106">Di seguito sono riportate alcune domande frequenti sullo strumento Lync Server 2013 stress and performance.</span><span class="sxs-lookup"><span data-stu-id="62ebd-106">Here are some frequently asked questions about the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="can-i-run-lyncperftoolexe-in-production"></a><span data-ttu-id="62ebd-107">È possibile eseguire LyncPerfTool.exe in produzione?</span><span class="sxs-lookup"><span data-stu-id="62ebd-107">Can I run LyncPerfTool.exe in production?</span></span>

<span data-ttu-id="62ebd-108">Non è consigliabile.</span><span class="sxs-lookup"><span data-stu-id="62ebd-108">We do not recommend this.</span></span> <span data-ttu-id="62ebd-109">Questo strumento avrà un impatto sulle prestazioni del server, sulla sicurezza e sull'esperienza utente.</span><span class="sxs-lookup"><span data-stu-id="62ebd-109">This tool will impact server performance, security, and user experience.</span></span>

</div>

<div>

## <a name="i-am-logging-on-my-users-for-the-first-time-why-are-the-servers-running-at-such-high-load"></a><span data-ttu-id="62ebd-110">La prima volta che si accede ai miei utenti.</span><span class="sxs-lookup"><span data-stu-id="62ebd-110">I am logging on my users for the first time.</span></span> <span data-ttu-id="62ebd-111">Perché i server sono in esecuzione a un carico così elevato?</span><span class="sxs-lookup"><span data-stu-id="62ebd-111">Why are the servers running at such high load?</span></span>

<span data-ttu-id="62ebd-112">La prima volta che si esegue l'accesso agli utenti, sono presenti operazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="62ebd-112">The first time the users log on, there are additional operations that occur.</span></span> <span data-ttu-id="62ebd-113">Di conseguenza, le prestazioni sul server back-end di Microsoft SQL Server verranno danneggiate.</span><span class="sxs-lookup"><span data-stu-id="62ebd-113">As a result, the performance on the Microsoft SQL Server Back End Server will be degraded.</span></span> <span data-ttu-id="62ebd-114">È consigliabile eseguire un test breve che accede a tutti gli utenti e quindi riavviare i client prima di misurare i risultati.</span><span class="sxs-lookup"><span data-stu-id="62ebd-114">We recommend that you run a short test that logs on all of the users, and then restart the clients before you measure results.</span></span> <span data-ttu-id="62ebd-115">Non sono supportate più di 12 sessioni di accesso utente simultanee al secondo, ma ciò dipende dalla configurazione hardware.</span><span class="sxs-lookup"><span data-stu-id="62ebd-115">We do not support more than 12 concurrent user logon sessions per second, but this depends on your hardware configuration.</span></span>

</div>

<div>

## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a><span data-ttu-id="62ebd-116">I client esauriscono la memoria.</span><span class="sxs-lookup"><span data-stu-id="62ebd-116">My clients are running out of memory.</span></span> <span data-ttu-id="62ebd-117">Cosa si può fare?</span><span class="sxs-lookup"><span data-stu-id="62ebd-117">What should I do?</span></span>

<span data-ttu-id="62ebd-118">Se i client esauriscono la memoria, è necessario ridurre il numero di utenti per computer.</span><span class="sxs-lookup"><span data-stu-id="62ebd-118">If your clients are running out of memory, you need to reduce the number of users per computer.</span></span>

</div>

<div>

## <a name="my-clients-are-at-100-percent-cpu-all-the-time-what-should-i-do"></a><span data-ttu-id="62ebd-119">I client sono al 100 percento della CPU per tutto il tempo.</span><span class="sxs-lookup"><span data-stu-id="62ebd-119">My clients are at 100 percent CPU all the time.</span></span> <span data-ttu-id="62ebd-120">Cosa si può fare?</span><span class="sxs-lookup"><span data-stu-id="62ebd-120">What should I do?</span></span>

<span data-ttu-id="62ebd-121">Se i client sono in esecuzione con CPU molto alta dopo che tutti gli utenti hanno effettuato l'accesso, è necessario ridurre il numero di utenti per computer.</span><span class="sxs-lookup"><span data-stu-id="62ebd-121">If your clients are running with very high CPU after all the users have logged on, you need to reduce the number of users per computer.</span></span> <span data-ttu-id="62ebd-122">Gli alti picchi di CPU sono accettabili, ma se sono sostenuti, è necessario ridurre il carico.</span><span class="sxs-lookup"><span data-stu-id="62ebd-122">High CPU spikes are acceptable, but if it is sustained, you need to reduce the load.</span></span>

</div>

<div>

## <a name="can-i-run-the-tool-on-the-server-itself"></a><span data-ttu-id="62ebd-123">È possibile eseguire lo strumento nel server stesso?</span><span class="sxs-lookup"><span data-stu-id="62ebd-123">Can I run the tool on the server itself?</span></span>

<span data-ttu-id="62ebd-124">No.</span><span class="sxs-lookup"><span data-stu-id="62ebd-124">No.</span></span> <span data-ttu-id="62ebd-125">Questo scenario non è supportato e potrebbe avere esito negativo a causa di una mancata corrispondenza binaria.</span><span class="sxs-lookup"><span data-stu-id="62ebd-125">This scenario is not supported and may fail due to a binary mismatch.</span></span> <span data-ttu-id="62ebd-126">Inoltre, poiché il punto è misurare il consumo di risorse sul server, l'esecuzione dello strumento consentirebbe di eseguire il rendering delle misurazioni insignificanti.</span><span class="sxs-lookup"><span data-stu-id="62ebd-126">Also, because the point is to measure resource consumption on the server, running the tool there would render the measurements meaningless.</span></span>

</div>

<div>

## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a><span data-ttu-id="62ebd-127">È possibile eseguire LyncPerfTool.exe su un server virtuale o su Microsoft Hyper-V Server 2008/2012?</span><span class="sxs-lookup"><span data-stu-id="62ebd-127">Can I run LyncPerfTool.exe on a Virtual Server or on Microsoft Hyper-V Server 2008/2012?</span></span>

<span data-ttu-id="62ebd-128">Sì.</span><span class="sxs-lookup"><span data-stu-id="62ebd-128">Yes.</span></span>

</div>

<div>

## <a name="what-does-mpop-mean"></a><span data-ttu-id="62ebd-129">Cosa significa MPOP?</span><span class="sxs-lookup"><span data-stu-id="62ebd-129">What does MPOP mean?</span></span>

<span data-ttu-id="62ebd-130">MPOP è sinonimo di più punti di presenza.</span><span class="sxs-lookup"><span data-stu-id="62ebd-130">MPOP stands for multiple points of presence.</span></span> <span data-ttu-id="62ebd-131">Si intende simulare lo scenario in cui gli utenti accedono a Lync 2013 da più computer.</span><span class="sxs-lookup"><span data-stu-id="62ebd-131">It is meant to simulate the scenario where users are logged on to Lync 2013 from multiple machines.</span></span> <span data-ttu-id="62ebd-132">Si noti che in LyncPerfTool.exe, ogni endpoint utilizza il profilo predefinito, ovvero il profilo non è suddiviso tra i due punti di presenza.</span><span class="sxs-lookup"><span data-stu-id="62ebd-132">Note that in LyncPerfTool.exe, each endpoint uses the default profile (that is, the profile is not split between the two points of presence).</span></span>

</div>

<div>

## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a><span data-ttu-id="62ebd-133">Ho cominciato LyncPerfTool.exe ma non succede nulla.</span><span class="sxs-lookup"><span data-stu-id="62ebd-133">I started LyncPerfTool.exe but nothing is happening.</span></span> <span data-ttu-id="62ebd-134">Per quale motivo?</span><span class="sxs-lookup"><span data-stu-id="62ebd-134">What’s going on?</span></span>

<span data-ttu-id="62ebd-135">Controllare il contatore totale degli endpoint attivi sui client per verificare se gli utenti si connettono.</span><span class="sxs-lookup"><span data-stu-id="62ebd-135">Check the Total Active Endpoints counter on the clients to see if the users are connecting.</span></span> <span data-ttu-id="62ebd-136">Se gli utenti non si connettono, verificare la configurazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="62ebd-136">If users are not connecting, verify your Lync Server 2013 configuration.</span></span> <span data-ttu-id="62ebd-137">Questo problema si verifica in genere perché il nome del server, il prefisso dell'utente o la password non è corretta.</span><span class="sxs-lookup"><span data-stu-id="62ebd-137">This issue usually occurs because the server name, the user prefix, or the password is incorrect.</span></span> <span data-ttu-id="62ebd-138">Si noti che i client esterni devono specificare il proxy di accesso come valore TargetServer.</span><span class="sxs-lookup"><span data-stu-id="62ebd-138">Note that external clients should specify the Access Proxy as the TargetServer value.</span></span> <span data-ttu-id="62ebd-139">Verificare la porta nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="62ebd-139">Verify the port in the configuration file.</span></span>

</div>

<div>

## <a name="how-do-i-know-something-is-happening"></a><span data-ttu-id="62ebd-140">Come si fa a sapere che sta accadendo qualcosa?</span><span class="sxs-lookup"><span data-stu-id="62ebd-140">How do I know something is happening?</span></span>

<span data-ttu-id="62ebd-141">I vari contatori delle prestazioni di LyncPerfTool indicano se gli utenti si connettono e eseguono azioni.</span><span class="sxs-lookup"><span data-stu-id="62ebd-141">The various LyncPerfTool performance counters indicate whether or not users are connecting and performing actions.</span></span> <span data-ttu-id="62ebd-142">Tuttavia, un modo semplice per effettuare la verifica consiste nell'accedere a uno degli account utilizzando Lync 2013 ed eseguire l'azione desiderata.</span><span class="sxs-lookup"><span data-stu-id="62ebd-142">However, an easy way to check is to log on to one of the accounts by using Lync 2013 and performing the action you want.</span></span>

</div>

<div>

## <a name="i-have-live-communications-server-2007-r2-capacity-planning-tools-andor-lync-server-2010-installed-is-that-ok"></a><span data-ttu-id="62ebd-143">Sono stati installati gli strumenti di pianificazione della capacità di Live Communications Server 2007 R2 e/o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="62ebd-143">I have Live Communications Server 2007 R2 Capacity Planning Tools and/or Lync Server 2010 installed.</span></span> <span data-ttu-id="62ebd-144">È tutto OK?</span><span class="sxs-lookup"><span data-stu-id="62ebd-144">Is that OK?</span></span>

<span data-ttu-id="62ebd-145">No.</span><span class="sxs-lookup"><span data-stu-id="62ebd-145">No.</span></span> <span data-ttu-id="62ebd-146">Sono presenti problemi di interoperabilità ed è necessario disinstallare tutte le versioni precedenti del prodotto.</span><span class="sxs-lookup"><span data-stu-id="62ebd-146">There are interoperability issues, and you must uninstall all previous versions of this product.</span></span>

</div>

<div>

## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a><span data-ttu-id="62ebd-147">Gli strumenti di stress e prestazioni configurano la topologia del server delle informazioni di chiamata CAA?</span><span class="sxs-lookup"><span data-stu-id="62ebd-147">Will the Stress and Performance tools set up the CAA Call Information server topology?</span></span>

<span data-ttu-id="62ebd-148">No.</span><span class="sxs-lookup"><span data-stu-id="62ebd-148">No.</span></span> <span data-ttu-id="62ebd-149">Gli strumenti creano solo gli utenti, i contatti e le liste di distribuzione e simulano il carico dell'utente.</span><span class="sxs-lookup"><span data-stu-id="62ebd-149">The tools only create users, contacts, and distribution lists, and simulate user load.</span></span>

</div>

<div>

## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a><span data-ttu-id="62ebd-150">Qual è il numero massimo di utenti supportati dagli strumenti?</span><span class="sxs-lookup"><span data-stu-id="62ebd-150">What is the maximum number of users that the tools support?</span></span>

<span data-ttu-id="62ebd-151">È stato creato un totale di 80.000 utenti e sono stati eseguiti test per un totale di 30.000 utenti, utilizzando questi strumenti.</span><span class="sxs-lookup"><span data-stu-id="62ebd-151">We have created up to a total of 80,000 users and executed tests totaling 30,000 users, using these tools.</span></span> <span data-ttu-id="62ebd-152">È consigliabile disporre di un massimo di 120.000 utenti, anche se le limitazioni tecniche consentono un valore superiore, a seconda dell'hardware del server e del client.</span><span class="sxs-lookup"><span data-stu-id="62ebd-152">We suggest a maximum of 120,000 users, although the technical limitations allow for a higher value, depending on the client and server hardware available.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


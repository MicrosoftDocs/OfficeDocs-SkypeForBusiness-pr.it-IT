---
title: 'Lync Server 2013: monitoraggio del sistema operativo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring operating system
ms:assetid: 72406d3e-54c8-4796-8d6d-2144a5b6f030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720918(v=OCS.15)
ms:contentKeyID: 63969617
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5bd837bab2ca4323dd0fb2f4d29b31d653d37c8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047698"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-operating-system-in-lync-server-2013"></a><span data-ttu-id="3f392-102">Monitoraggio del sistema operativo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f392-102">Monitoring operating system in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f392-103">_**Ultimo argomento modificato:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="3f392-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="3f392-104">È necessario monitorare le prestazioni di tutti i server e i componenti del Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3f392-104">You must monitor the performance of all servers and components in the Lync Server 2013.</span></span> <span data-ttu-id="3f392-105">Ovviamente, uno dei componenti più importanti è il sistema operativo stesso.</span><span class="sxs-lookup"><span data-stu-id="3f392-105">Obviously, one of the most important components is the operating system itself.</span></span> <span data-ttu-id="3f392-106">Lync Server 2013 supporta le edizioni x64 di:</span><span class="sxs-lookup"><span data-stu-id="3f392-106">Lync Server 2013 supports x64 editions of:</span></span>

  - <span data-ttu-id="3f392-107">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="3f392-107">Windows Server 2008 R2</span></span>

  - <span data-ttu-id="3f392-108">Windows Server 2012 e Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="3f392-108">Windows Server 2012 and Windows Server 2012 R2</span></span>

<span data-ttu-id="3f392-109">Il modo più trasparente per monitorare un sistema operativo consiste nell'utilizzare il Management Pack del sistema operativo Windows Server.</span><span class="sxs-lookup"><span data-stu-id="3f392-109">The most transparent way to monitor an operating system is by using Windows Server Operating System Management Pack.</span></span> <span data-ttu-id="3f392-110">Sono disponibili le nozioni fondamentali di monitoraggio, quali prestazioni, integrità e disponibilità per i computer che eseguono Windows Server 2012, Windows Server 2012 R2 e Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="3f392-110">It provides the fundamental monitoring basics, such as performance, health, and availability for computers that are running Windows Server 2012, Windows Server 2012 R2, and Windows Server 2008 R2.</span></span>

<span data-ttu-id="3f392-111">Rilevando, avvertendo e rispondendo automaticamente a eventi importanti e indicatori di prestazioni, questi Management Pack riducono i tempi di risoluzione dei problemi e aumentano la disponibilità complessiva e le prestazioni di sistemi che eseguono Windows Server sistemi operativi.</span><span class="sxs-lookup"><span data-stu-id="3f392-111">By detecting, alerting, and automatically responding to important events and performance indicators, these management packs reduce resolution times for issues and increase the overall availability and performance of systems that are running the Windows Server operating systems.</span></span>

<span data-ttu-id="3f392-112">Oltre ai Management Pack di Windows Server rilevanti per System Center Operations Manager, è possibile utilizzare le risorse e gli strumenti di sistema seguenti per monitorare l'integrità del sistema operativo, a seconda della versione del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="3f392-112">Apart from relevant Windows Server management packs for System Center Operations Manager, the following system tools and resources can be used to monitor the health of the operating system (depending on the operating system version).</span></span>

<div>

## <a name="windows-server2008r2"></a><span data-ttu-id="3f392-113">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="3f392-113">Windows Server 2008 R2</span></span>

<span data-ttu-id="3f392-114">Windows Server 2008 R2 include le funzionalità e gli strumenti aggiuntivi seguenti che consentono agli amministratori di eseguire il monitoraggio e la gestione di base del sistema operativo:</span><span class="sxs-lookup"><span data-stu-id="3f392-114">Windows Server 2008 R2 includes the following additional features and tools to help administrators with basic operating system monitoring and management:</span></span>

  - <span data-ttu-id="3f392-115">**Monitor risorse di Windows** è uno strumento potente per comprendere le modalità di utilizzo delle risorse di sistema da parte dei processi e dei servizi.</span><span class="sxs-lookup"><span data-stu-id="3f392-115">**Windows Resource Monitor** is a powerful tool for understanding how system resources are used by processes and services.</span></span> <span data-ttu-id="3f392-116">Oltre a monitorare l'utilizzo delle risorse in tempo reale, un monitor delle risorse consente di analizzare i processi non rispondenti, identificare le applicazioni che utilizzano i file e controllare i processi e i servizi.</span><span class="sxs-lookup"><span data-stu-id="3f392-116">In addition to monitoring resource usage in real time, a Resource Monitor can help analyze unresponsive processes, identify which applications are using files, and control processes and services.</span></span>

  - <span data-ttu-id="3f392-117">Il **componente di analisi dell'affidabilità** è un agente in-box che fornisce informazioni dettagliate sull'utilizzo e l'affidabilità del sistema.</span><span class="sxs-lookup"><span data-stu-id="3f392-117">**Reliability Analysis Component** is an in-box agent that provides detailed experience information on system usage and reliability.</span></span> <span data-ttu-id="3f392-118">Queste informazioni vengono esposte tramite un'interfaccia WMI per renderlo disponibile per il consumo da parte dei sistemi di lettori portatili.</span><span class="sxs-lookup"><span data-stu-id="3f392-118">This information is exposed through a WMI interface to make it available for consumption by Portable Readers Systems.</span></span> <span data-ttu-id="3f392-119">Esponendo il componente di analisi dell'affidabilità tramite un'interfaccia WMI, gli sviluppatori possono monitorare e analizzare le applicazioni, aumentando l'affidabilità e le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="3f392-119">By exposing Reliability Analysis Component through a WMI interface, developers can monitor and analyze applications, increasing reliability and performance.</span></span>

  - <span data-ttu-id="3f392-120">**Windows Server 2008 R2** utilizza il componente di analisi dell'affidabilità incorporato per calcolare un indice di affidabilità, in cui vengono fornite informazioni sull'utilizzo e sulla stabilità generali del sistema nel tempo.</span><span class="sxs-lookup"><span data-stu-id="3f392-120">**Windows Server 2008 R2** uses the built-in Reliability Analysis Component to calculate a reliability index, which provides information about overall system usage and stability over time.</span></span> <span data-ttu-id="3f392-121">Il componente di analisi dell'affidabilità tiene anche conto di eventuali modifiche importanti al sistema che potrebbero influire sulla stabilità, ad esempio gli aggiornamenti di Windows e le installazioni di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="3f392-121">The Reliability Analysis Component also keeps track of any important changes to the system that are likely to influence stability, such as Windows updates and application installations.</span></span>

</div>

<div>

## <a name="windows-server2008-windows-reliability-and-performance-monitor"></a><span data-ttu-id="3f392-122">Monitoraggio affidabilità e prestazioni di Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="3f392-122">Windows Server 2008 Windows Reliability and Performance Monitor</span></span>

<span data-ttu-id="3f392-123">Monitoraggio affidabilità e prestazioni di Windows è uno snap-in MMC che combina la funzionalità dei precedenti strumenti autonomi, tra cui registri delle prestazioni e avvisi, Server Performance Advisor e monitor di sistema.</span><span class="sxs-lookup"><span data-stu-id="3f392-123">Windows Reliability and Performance Monitor is an MMC Snap-in that combines the functionality of previous stand-alone tools including Performance Logs and Alerts, Server Performance Advisor, and System Monitor.</span></span> <span data-ttu-id="3f392-124">Offre un'interfaccia grafica per la personalizzazione della raccolta di dati di prestazioni e delle sessioni di traccia degli eventi.</span><span class="sxs-lookup"><span data-stu-id="3f392-124">It provides a graphical interface for customizing performance data collection and Event Trace Sessions.</span></span>

<span data-ttu-id="3f392-125">Include inoltre il monitoraggio dell'affidabilità, uno snap-in MMC che consente di tenere traccia delle modifiche apportate al sistema e le confronta con le modifiche apportate alla stabilità del sistema e fornisce una visualizzazione grafica della relazione.</span><span class="sxs-lookup"><span data-stu-id="3f392-125">It also includes Reliability Monitor, an MMC Snap-in that tracks changes to the system and compares them to changes in system stability, and it provides a graphical view of their relationship.</span></span>

</div>

<div>

## <a name="windows-reliability-and-performance-monitor"></a><span data-ttu-id="3f392-126">Monitoraggio affidabilità e prestazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="3f392-126">Windows Reliability and Performance Monitor</span></span>

<span data-ttu-id="3f392-127">Mentre Monitoraggio affidabilità e prestazioni di Windows combinano le funzionalità di alcuni strumenti precedenti, come i registri di prestazioni e gli avvisi, e il monitor di sistema e il Server Performance Advisor, fornisce anche alcune nuove funzionalità a Windows Server 2008 e Windows Server 2008 R2, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3f392-127">While Windows Reliability and Performance Monitor combine functionalities of some former stand-alone tools such as Performance Logs and Alerts, and System Monitor and Server Performance Advisor, it also provides some new functionality to Windows Server 2008 and Windows Server 2008 R2, such as the following:</span></span>

  - <span data-ttu-id="3f392-128">Insiemi di agenti di raccolta dati</span><span class="sxs-lookup"><span data-stu-id="3f392-128">Data Collector Sets</span></span>

  - <span data-ttu-id="3f392-129">Visualizzazione risorse</span><span class="sxs-lookup"><span data-stu-id="3f392-129">Resource View</span></span>

  - <span data-ttu-id="3f392-130">Monitoraggio affidabilità</span><span class="sxs-lookup"><span data-stu-id="3f392-130">Reliability Monitor</span></span>

  - <span data-ttu-id="3f392-131">Procedure guidate e modelli per la creazione di registri</span><span class="sxs-lookup"><span data-stu-id="3f392-131">Wizards and templates for creating logs</span></span>

<span data-ttu-id="3f392-132">Set di agenti di **raccolta dati** raggruppa i collezionisti di dati in elementi riutilizzabili per l'utilizzo con diversi scenari di monitoraggio delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="3f392-132">**Data Collector Set** groups data collectors into reusable elements for use with different performance monitoring scenarios.</span></span> <span data-ttu-id="3f392-133">Dopo che un gruppo di collezionisti di dati è archiviato come set di agenti di raccolta dati, le operazioni come la pianificazione possono essere applicate a tutto il set tramite una singola modifica della proprietà. Monitoraggio affidabilità e prestazioni di Windows include modelli set di agenti di raccolta dati predefiniti che consentono agli amministratori di sistema di raccogliere immediatamente dati sulle prestazioni specifici di un ruolo del server o di uno scenario di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="3f392-133">After a group of data collectors are stored as a Data Collector Set, operations such as scheduling can be applied to the whole set through a single property change.Windows Reliability and Performance Monitor includes default Data Collector Set templates to help system administrators begin immediately collecting performance data that is specific to a server role or monitoring scenario.</span></span>

<span data-ttu-id="3f392-134">La Home page di monitoraggio affidabilità e prestazioni di Windows è la nuova schermata di **visualizzazione delle risorse** , che fornisce una panoramica grafica in tempo reale di utilizzo della CPU, del disco, della rete e della memoria.</span><span class="sxs-lookup"><span data-stu-id="3f392-134">The home page of Windows Reliability and Performance Monitor is the new **Resource View** screen, which provides a real-time graphical overview of CPU, disk, network, and memory usage.</span></span> <span data-ttu-id="3f392-135">Espandendo ognuno di questi elementi monitorati, gli amministratori di sistema possono identificare i processi che utilizzano le risorse.</span><span class="sxs-lookup"><span data-stu-id="3f392-135">By expanding each of these monitored elements, system administrators can identify which processes are using which resources.</span></span> <span data-ttu-id="3f392-136">Nelle versioni precedenti di Windows, in tempo reale, i dati specifici dei processi erano disponibili solo in formato limitato in Task Manager.</span><span class="sxs-lookup"><span data-stu-id="3f392-136">In earlier versions of Windows, this real-time, process-specific data was available only in limited form in Task Manager.</span></span>

<span data-ttu-id="3f392-137">**Monitor di affidabilità** calcola un indice di stabilità del sistema che indica se i problemi imprevisti riducono l'affidabilità del sistema.</span><span class="sxs-lookup"><span data-stu-id="3f392-137">**Reliability Monitor** calculates a System Stability Index that reflects whether unexpected issues reduced the reliability of the system.</span></span> <span data-ttu-id="3f392-138">Un grafico dell'indice di stabilità nel tempo identifica rapidamente le date in cui si sono verificati problemi.</span><span class="sxs-lookup"><span data-stu-id="3f392-138">A graph of the Stability Index over time quickly identifies dates when issues began to occur.</span></span> <span data-ttu-id="3f392-139">Il rapporto di stabilità del sistema associato fornisce informazioni dettagliate per la risoluzione dei problemi relativi alla causa di un'affidabilità ridotta.</span><span class="sxs-lookup"><span data-stu-id="3f392-139">The accompanying System Stability Report provides details to help troubleshoot the cause of reduced reliability.</span></span> <span data-ttu-id="3f392-140">Visualizzando le modifiche apportate al sistema (installazione o rimozione di applicazioni, aggiornamenti per il sistema operativo o addizione o modifica dei driver) affiancati da errori (errori di applicazioni, arresti anomali del sistema operativo o errori hardware), una strategia per la risoluzione dei problemi può essere sviluppata rapidamente.</span><span class="sxs-lookup"><span data-stu-id="3f392-140">By viewing changes to the system (installation or removal of applications, updates to the operating system, or addition or modification of drivers) side by side with failures (application failures, operating system crashes, or hardware failures), a strategy for addressing the issues can be developed quickly.</span></span>

<span data-ttu-id="3f392-141">L'aggiunta di contatori ai file di registro e la pianificazione dell'avvio, dell'interruzione e della durata possono ora essere eseguite tramite un' **interfaccia della procedura guidata**.</span><span class="sxs-lookup"><span data-stu-id="3f392-141">Adding counters to log files and scheduling their start, stop, and duration can now be performed through a **Wizard interface**.</span></span> <span data-ttu-id="3f392-142">Inoltre, il salvataggio di questa configurazione come modello consente agli amministratori di sistema di raccogliere lo stesso registro su altri computer senza ripetere la selezione e i processi di pianificazione dell'agente di raccolta dati.</span><span class="sxs-lookup"><span data-stu-id="3f392-142">In addition, saving this configuration as a template enables system administrators to collect the same log on other computers without repeating the data collector selection and scheduling processes.</span></span> <span data-ttu-id="3f392-143">Le funzionalità di avvisi e registri delle prestazioni sono state integrate in Monitoraggio affidabilità e prestazioni di Windows per l'utilizzo con qualsiasi insieme agenti di raccolta dati.</span><span class="sxs-lookup"><span data-stu-id="3f392-143">Performance Logs and Alerts features were incorporated into the Windows Reliability and Performance Monitor for use with any Data Collector Set.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


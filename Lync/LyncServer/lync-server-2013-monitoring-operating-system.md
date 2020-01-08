---
title: 'Lync Server 2013: monitoraggio del sistema operativo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring operating system
ms:assetid: 72406d3e-54c8-4796-8d6d-2144a5b6f030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720918(v=OCS.15)
ms:contentKeyID: 63969617
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2f8124afcf2d1acbde3518ff625d528d6e34a3e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981992"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-operating-system-in-lync-server-2013"></a><span data-ttu-id="63010-102">Monitoraggio del sistema operativo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63010-102">Monitoring operating system in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63010-103">_**Argomento Ultima modifica:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="63010-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="63010-104">È necessario monitorare le prestazioni di tutti i server e i componenti di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="63010-104">You must monitor the performance of all servers and components in the Lync Server 2013.</span></span> <span data-ttu-id="63010-105">Uno dei componenti più importanti, naturalmente, è il sistema operativo stesso.</span><span class="sxs-lookup"><span data-stu-id="63010-105">Obviously, one of the most important components is the operating system itself.</span></span> <span data-ttu-id="63010-106">Lync Server 2013 supporta le edizioni x64 di:</span><span class="sxs-lookup"><span data-stu-id="63010-106">Lync Server 2013 supports x64 editions of:</span></span>

  - <span data-ttu-id="63010-107">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="63010-107">Windows Server 2008 R2</span></span>

  - <span data-ttu-id="63010-108">Windows Server 2012 e Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="63010-108">Windows Server 2012 and Windows Server 2012 R2</span></span>

<span data-ttu-id="63010-109">Il modo più trasparente per monitorare un sistema operativo consiste nell'usare il Management Pack del sistema operativo Windows Server.</span><span class="sxs-lookup"><span data-stu-id="63010-109">The most transparent way to monitor an operating system is by using Windows Server Operating System Management Pack.</span></span> <span data-ttu-id="63010-110">Fornisce le nozioni fondamentali per il monitoraggio, ad esempio prestazioni, integrità e disponibilità per i computer che eseguono Windows Server 2012, Windows Server 2012 R2 e Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="63010-110">It provides the fundamental monitoring basics, such as performance, health, and availability for computers that are running Windows Server 2012, Windows Server 2012 R2, and Windows Server 2008 R2.</span></span>

<span data-ttu-id="63010-111">Individuando, avvisando e rispondendo automaticamente agli eventi importanti e agli indicatori di prestazioni, questi Management Pack riducono i tempi di risoluzione per i problemi e aumentano la disponibilità complessiva e le prestazioni dei sistemi che esegue Windows Server sistemi operativi.</span><span class="sxs-lookup"><span data-stu-id="63010-111">By detecting, alerting, and automatically responding to important events and performance indicators, these management packs reduce resolution times for issues and increase the overall availability and performance of systems that are running the Windows Server operating systems.</span></span>

<span data-ttu-id="63010-112">Oltre a rilevanti Windows Server Management Pack per System Center Operations Manager, è possibile usare gli strumenti e le risorse di sistema seguenti per monitorare l'integrità del sistema operativo (a seconda della versione del sistema operativo).</span><span class="sxs-lookup"><span data-stu-id="63010-112">Apart from relevant Windows Server management packs for System Center Operations Manager, the following system tools and resources can be used to monitor the health of the operating system (depending on the operating system version).</span></span>

<div>

## <a name="windows-server2008r2"></a><span data-ttu-id="63010-113">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="63010-113">Windows Server 2008 R2</span></span>

<span data-ttu-id="63010-114">Windows Server 2008 R2 include le caratteristiche e gli strumenti aggiuntivi seguenti per aiutare gli amministratori con il monitoraggio e la gestione dei sistemi operativi di base:</span><span class="sxs-lookup"><span data-stu-id="63010-114">Windows Server 2008 R2 includes the following additional features and tools to help administrators with basic operating system monitoring and management:</span></span>

  - <span data-ttu-id="63010-p103">**Monitoraggio risorse** è uno strumento avanzato che consente di comprendere in modo approfondito l'utilizzo delle risorse di sistema da parte dei processi e dei servizi. Oltre a effettuare il monitoraggio dell'utilizzo delle risorse in tempo reale, Monitoraggio risorse consente di analizzare i processi che non rispondono, identificare le applicazioni che utilizzano file e controllare processi e servizi.</span><span class="sxs-lookup"><span data-stu-id="63010-p103">**Windows Resource Monitor** is a powerful tool for understanding how system resources are used by processes and services. In addition to monitoring resource usage in real time, a Resource Monitor can help analyze unresponsive processes, identify which applications are using files, and control processes and services.</span></span>

  - <span data-ttu-id="63010-p104">**Componente di analisi dell'affidabilità** è un agente incorporato che fornisce informazioni dettagliate sull'esperienza relative all'utilizzo del sistema e all'affidabilità. Queste informazioni vengono esposte tramite un'interfaccia di Strumentazione gestione Windows (WMI), rendendole disponibili per l'utilizzo da parte di sistemi per lettori portatili. L'esposizione del Componente di analisi dell'affidabilità tramite un'interfaccia WMI consente agli sviluppatori di monitorare e analizzare le applicazioni, aumentando affidabilità e prestazioni.</span><span class="sxs-lookup"><span data-stu-id="63010-p104">**Reliability Analysis Component** is an in-box agent that provides detailed experience information on system usage and reliability. This information is exposed through a WMI interface to make it available for consumption by Portable Readers Systems. By exposing Reliability Analysis Component through a WMI interface, developers can monitor and analyze applications, increasing reliability and performance.</span></span>

  - <span data-ttu-id="63010-120">**Windows Server 2008 R2** usa il componente di analisi di affidabilità predefinito per calcolare un indice di affidabilità, che fornisce informazioni sull'uso e la stabilità complessive del sistema nel tempo.</span><span class="sxs-lookup"><span data-stu-id="63010-120">**Windows Server 2008 R2** uses the built-in Reliability Analysis Component to calculate a reliability index, which provides information about overall system usage and stability over time.</span></span> <span data-ttu-id="63010-121">The Reliability Analysis Component also keeps track of any important changes to the system that are likely to influence stability, such as Windows updates and application installations.</span><span class="sxs-lookup"><span data-stu-id="63010-121">The Reliability Analysis Component also keeps track of any important changes to the system that are likely to influence stability, such as Windows updates and application installations.</span></span>

</div>

<div>

## <a name="windows-server2008-windows-reliability-and-performance-monitor"></a><span data-ttu-id="63010-122">Monitoraggio affidabilità e prestazioni di Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="63010-122">Windows Server 2008 Windows Reliability and Performance Monitor</span></span>

<span data-ttu-id="63010-p106">Le funzionalità Monitoraggio affidabilità e Monitoraggio prestazioni di Windows costituiscono uno snap-in MMC (Microsoft Management Console) nel quale sono combinate le funzionalità di strumenti autonomi precedenti, tra cui Avvisi e registri di prestazioni, Server Performance Advisor (SPA) e Monitor di sistema. Lo snap-in è provvisto di un'interfaccia grafica per la personalizzazione di insiemi di dati sulle prestazioni e di sessioni di traccia degli eventi.</span><span class="sxs-lookup"><span data-stu-id="63010-p106">Windows Reliability and Performance Monitor is an MMC Snap-in that combines the functionality of previous stand-alone tools including Performance Logs and Alerts, Server Performance Advisor, and System Monitor. It provides a graphical interface for customizing performance data collection and Event Trace Sessions.</span></span>

<span data-ttu-id="63010-125">È inoltre incluso Monitoraggio affidabilità, uno snap-in MMC che consente di tenere traccia delle modifiche apportate al sistema e di confrontarle con le variazioni in termini di stabilità del sistema in una visualizzazione grafica delle relative relazioni.</span><span class="sxs-lookup"><span data-stu-id="63010-125">It also includes Reliability Monitor, an MMC Snap-in that tracks changes to the system and compares them to changes in system stability, and it provides a graphical view of their relationship.</span></span>

</div>

<div>

## <a name="windows-reliability-and-performance-monitor"></a><span data-ttu-id="63010-126">Monitoraggio affidabilità e Monitoraggio prestazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="63010-126">Windows Reliability and Performance Monitor</span></span>

<span data-ttu-id="63010-127">L'affidabilità e il monitoraggio delle prestazioni di Windows combinano le funzionalità di alcuni ex strumenti autonomi come i registri delle prestazioni e gli avvisi, oltre a un monitor di sistema e a un Server Performance Advisor, ma offre anche alcune nuove caratteristiche di Windows Server 2008 e Windows Server 2008 R2, ad esempio il seguente:</span><span class="sxs-lookup"><span data-stu-id="63010-127">While Windows Reliability and Performance Monitor combine functionalities of some former stand-alone tools such as Performance Logs and Alerts, and System Monitor and Server Performance Advisor, it also provides some new functionality to Windows Server 2008 and Windows Server 2008 R2, such as the following:</span></span>

  - <span data-ttu-id="63010-128">Insiemi agenti di raccolta dati</span><span class="sxs-lookup"><span data-stu-id="63010-128">Data Collector Sets</span></span>

  - <span data-ttu-id="63010-129">Visualizzazione risorse</span><span class="sxs-lookup"><span data-stu-id="63010-129">Resource View</span></span>

  - <span data-ttu-id="63010-130">Monitoraggio affidabilità</span><span class="sxs-lookup"><span data-stu-id="63010-130">Reliability Monitor</span></span>

  - <span data-ttu-id="63010-131">Creazioni guidate e modelli per la creazione di registri</span><span class="sxs-lookup"><span data-stu-id="63010-131">Wizards and templates for creating logs</span></span>

<span data-ttu-id="63010-p107">**Insieme agenti di raccolta dati** raggruppa gli agenti di raccolta dati in elementi riutilizzabili per l'utilizzo in scenari diversi di monitoraggio delle prestazioni. Dopo l'archiviazione di un gruppo di agenti di raccolta dati come Insieme agenti di raccolta dati, è possibile eseguire operazioni come ad esempio la pianificazione sull'intero insieme modificando una sola proprietà. Sono inclusi anche modelli di insieme agenti di raccolta dati che consentono agli amministratori di sistema di cominciare a raccogliere immediatamente i dati delle prestazioni specifici di un ruolo di server o di uno scenario di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="63010-p107">**Data Collector Set** groups data collectors into reusable elements for use with different performance monitoring scenarios. After a group of data collectors are stored as a Data Collector Set, operations such as scheduling can be applied to the whole set through a single property change.Windows Reliability and Performance Monitor includes default Data Collector Set templates to help system administrators begin immediately collecting performance data that is specific to a server role or monitoring scenario.</span></span>

<span data-ttu-id="63010-p108">La pagina iniziale di Monitoraggio affidabilità e Monitoraggio prestazioni di Windows è la nuova schermata di \*\* Visualizzazione risorse\*\* che offre una panoramica grafica in tempo reale dell'utilizzo della CPU, del disco, della rete e della memoria. Espandendo ognuno di questi elementi monitorati, gli amministratori di sistema possono identificare quali processi vengono utilizzati dalle singole risorse. Nelle versioni precedenti di Windows, i dati in tempo reale specifici di un processo sono disponibili soltanto in modo limitato in Gestione attività.</span><span class="sxs-lookup"><span data-stu-id="63010-p108">The home page of Windows Reliability and Performance Monitor is the new **Resource View** screen, which provides a real-time graphical overview of CPU, disk, network, and memory usage. By expanding each of these monitored elements, system administrators can identify which processes are using which resources. In earlier versions of Windows, this real-time, process-specific data was available only in limited form in Task Manager.</span></span>

<span data-ttu-id="63010-p109">In **Monitoraggio affidabilità** viene calcolato un indice di stabilità del sistema che indica se eventuali problemi imprevisti hanno ridotto l'affidabilità del sistema. In un grafico dell'indice di stabilità del sistema nel tempo vengono identificate rapidamente le date in cui i problemi hanno iniziato a verificarsi. Nel relativo Rapporto stabilità sistema vengono riportati i dettagli per risolvere la causa principale della riduzione dell'affidabilità. La visualizzazione delle modifiche del sistema, ad esempio l'installazione o la rimozione delle applicazioni, gli aggiornamenti al sistema operativo oppure l'aggiunta o la modifica di driver, affiancata agli errori, ad esempio gli errori delle applicazioni, gli arresti anomali del sistema operativo o gli errori hardware, consente di sviluppare rapidamente una strategia per risolvere i problemi.</span><span class="sxs-lookup"><span data-stu-id="63010-p109">**Reliability Monitor** calculates a System Stability Index that reflects whether unexpected issues reduced the reliability of the system. A graph of the Stability Index over time quickly identifies dates when issues began to occur. The accompanying System Stability Report provides details to help troubleshoot the cause of reduced reliability. By viewing changes to the system (installation or removal of applications, updates to the operating system, or addition or modification of drivers) side by side with failures (application failures, operating system crashes, or hardware failures), a strategy for addressing the issues can be developed quickly.</span></span>

<span data-ttu-id="63010-p110">È possibile ora aggiungere contatori ai file di registro e pianificarne l'avvio, l'interruzione e la durata tramite un'**interfaccia della creazione guidata**. È inoltre possibile salvare questa configurazione come modello per la raccolta dello stesso registro su computer successivi senza ripetere la selezione dell'agente di raccolta dati e pianificare i processi. In Monitoraggio affidabilità e Monitoraggio prestazioni di Windows sono state incorporate le funzionalità Avvisi e registri di prestazioni per l'utilizzo con qualsiasi insieme agenti di raccolta dati.</span><span class="sxs-lookup"><span data-stu-id="63010-p110">Adding counters to log files and scheduling their start, stop, and duration can now be performed through a **Wizard interface**. In addition, saving this configuration as a template enables system administrators to collect the same log on other computers without repeating the data collector selection and scheduling processes. Performance Logs and Alerts features were incorporated into the Windows Reliability and Performance Monitor for use with any Data Collector Set.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Panoramica di Best Practices Analyzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Best Practices Analyzer
ms:assetid: c5fcaa05-eb1c-4092-90ad-177b127e795b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591349(v=OCS.15)
ms:contentKeyID: 48185364
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a11cebfe1b8344bcad0385bbe17bb26277c498c1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153286"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="6eaea-102">Panoramica di Best Practices Analyzer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eaea-102">Overview of Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6eaea-103">_**Ultimo argomento modificato:** 2012-09-19_</span><span class="sxs-lookup"><span data-stu-id="6eaea-103">_**Topic Last Modified:** 2012-09-19_</span></span>

<span data-ttu-id="6eaea-104">È possibile utilizzare Lync Server 2013, Best Practices Analyzer per identificare e risolvere i problemi relativi alla distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6eaea-104">You can use Lync Server 2013, Best Practices Analyzer to identify and resolve problems with your Lync Server 2013 deployment.</span></span> <span data-ttu-id="6eaea-105">Lync Server 2013, Best Practices Analyzer raccoglie le informazioni di configurazione dai componenti di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6eaea-105">The Lync Server 2013, Best Practices Analyzer gathers configuration information from Lync Server 2013 components.</span></span>

<span data-ttu-id="6eaea-106">Con l'accesso di rete appropriato, l'Analizzatore procedure consigliate può esaminare i server che eseguono servizi di dominio Active Directory, la messaggistica unificata di Exchange Server e Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6eaea-106">With the proper network access, the Best Practices Analyzer can examine servers running Active Directory Domain Services, Exchange Server Unified Messaging (UM), and Lync Server 2013.</span></span> <span data-ttu-id="6eaea-107">È possibile utilizzare Best Practices Analyzer per eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6eaea-107">You can use Best Practices Analyzer to do the following:</span></span>

  - <span data-ttu-id="6eaea-108">Eseguire preventivamente controlli per verificare che la configurazione sia impostata secondo le procedure consigliate.</span><span class="sxs-lookup"><span data-stu-id="6eaea-108">Proactively perform checks, verifying that the configuration is set according to recommended best practices.</span></span>

  - <span data-ttu-id="6eaea-109">Rileva automaticamente gli aggiornamenti necessari per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6eaea-109">Automatically detect required updates to Lync Server 2013.</span></span>

  - <span data-ttu-id="6eaea-110">Generare un elenco di problemi, ad esempio impostazioni di configurazione non ottimali, opzioni non supportate, aggiornamenti mancanti o procedure non consigliate.</span><span class="sxs-lookup"><span data-stu-id="6eaea-110">Generate a list of issues, such as suboptimal configuration settings, unsupported options, missing updates, or practices that we do not recommend.</span></span>

  - <span data-ttu-id="6eaea-111">Individuare e risolvere facilmente problemi specifici.</span><span class="sxs-lookup"><span data-stu-id="6eaea-111">Help you troubleshoot and fix specific problems.</span></span>

<span data-ttu-id="6eaea-112">Best Practices Analyzer presenta le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="6eaea-112">Best Practices Analyzer provides the following features:</span></span>

  - <span data-ttu-id="6eaea-113">Prerequisiti di installazione minimi.</span><span class="sxs-lookup"><span data-stu-id="6eaea-113">Minimal installation prerequisites.</span></span>

  - <span data-ttu-id="6eaea-114">Documentazione online sui problemi segnalati, inclusi suggerimenti per la soluzione.</span><span class="sxs-lookup"><span data-stu-id="6eaea-114">Online documentation about reported issues, including troubleshooting tips.</span></span>

  - <span data-ttu-id="6eaea-115">Informazioni di configurazione che è possibile salvare per un utilizzo successivo.</span><span class="sxs-lookup"><span data-stu-id="6eaea-115">Configuration information that you can save for later review.</span></span>

  - <span data-ttu-id="6eaea-116">Tecnologia di punta per l'analisi del sistema.</span><span class="sxs-lookup"><span data-stu-id="6eaea-116">State-of-the-art system analysis.</span></span>

<span data-ttu-id="6eaea-117">Best Practices Analyzer utilizza un set di file di configurazione XML per determinare le informazioni da raccogliere dall'ambiente Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6eaea-117">Best Practices Analyzer uses a set of XML configuration files to determine the information to gather from your Lync Server 2013 environment.</span></span> <span data-ttu-id="6eaea-118">Oltre a verificare Servizi di dominio Active Directory, questo strumento consente anche di controllare origini come il Registro di sistema di Windows Server e le impostazioni in Strumentazione gestione Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="6eaea-118">In addition to checking Active Directory Domain Services, it checks sources such as the Windows Server operating system registry and settings in Windows Management Instrumentation (WMI).</span></span>

<span data-ttu-id="6eaea-119">Best Practices Analyzer confronta i dati raccolti con un set di regole predefinite per le impostazioni e le configurazioni delle distribuzioni di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6eaea-119">Best Practices Analyzer compares the data it gathers with a set of predefined rules for the settings and configurations of Lync Server 2013 deployments.</span></span>

<span data-ttu-id="6eaea-120">Dopo aver confrontato i dati raccolti con le regole predefinite, lo strumento segnala gli eventuali problemi.</span><span class="sxs-lookup"><span data-stu-id="6eaea-120">After comparing the collected data with the predefined rules, the tool reports issues.</span></span> <span data-ttu-id="6eaea-121">Per tutti i problemi segnalati, Best Practices Analyzer fornisce informazioni su ciò che è stato trovato nell'ambiente analizzato di Lync Server 2013 e la configurazione consigliata.</span><span class="sxs-lookup"><span data-stu-id="6eaea-121">For every issue that it reports, Best Practices Analyzer provides information about what was found in the scanned Lync Server 2013 environment and the recommended configuration.</span></span> <span data-ttu-id="6eaea-122">In Best Practices Analyzer vengono forniti inoltre collegamenti a informazioni dettagliate sui problemi specifici.</span><span class="sxs-lookup"><span data-stu-id="6eaea-122">Best Practices Analyzer also provides links to more detailed information about the specific issues.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6eaea-123">Lync Server 2013, Best Practices Analyzer raccoglie le informazioni di configurazione solo dai componenti di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6eaea-123">The Lync Server 2013, Best Practices Analyzer gathers configuration information only from Lync Server 2013 components.</span></span> <span data-ttu-id="6eaea-124">Per analizzare gli ambienti con versioni precedenti, è possibile utilizzare le versioni precedenti dello strumento.</span><span class="sxs-lookup"><span data-stu-id="6eaea-124">You can use the previous versions of the tool to scan previous environments.</span></span> <span data-ttu-id="6eaea-125">Per ulteriori informazioni, vedere <A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">requisiti per l'esecuzione di Best Practices Analyzer in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="6eaea-125">For details, see <A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">Requirements for running Best Practices Analyzer in Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>


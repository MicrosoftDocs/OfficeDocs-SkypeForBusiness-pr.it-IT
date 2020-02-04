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
ms.openlocfilehash: 53e63bf6063803364a679a3cc0724ec1cbeae1a2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755600"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="f607f-102">Panoramica dell'analizzatore delle procedure consigliate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f607f-102">Overview of Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f607f-103">_**Argomento Ultima modifica:** 2012-09-19_</span><span class="sxs-lookup"><span data-stu-id="f607f-103">_**Topic Last Modified:** 2012-09-19_</span></span>

<span data-ttu-id="f607f-104">È possibile usare Lync Server 2013, Best Practices Analyzer per identificare e risolvere i problemi relativi alla distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f607f-104">You can use Lync Server 2013, Best Practices Analyzer to identify and resolve problems with your Lync Server 2013 deployment.</span></span> <span data-ttu-id="f607f-105">Lync Server 2013, Best Practices Analyzer raccoglie le informazioni di configurazione dai componenti di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f607f-105">The Lync Server 2013, Best Practices Analyzer gathers configuration information from Lync Server 2013 components.</span></span>

<span data-ttu-id="f607f-106">Con l'accesso corretto alla rete, l'analizzatore delle procedure consigliate può esaminare i server che esegue servizi di dominio Active Directory, messaggistica UNIFICAta di Exchange Server e Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f607f-106">With the proper network access, the Best Practices Analyzer can examine servers running Active Directory Domain Services, Exchange Server Unified Messaging (UM), and Lync Server 2013.</span></span> <span data-ttu-id="f607f-107">È possibile usare Best Practices Analyzer per eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f607f-107">You can use Best Practices Analyzer to do the following:</span></span>

  - <span data-ttu-id="f607f-108">Eseguire i controlli in modo proattivo, verificando che la configurazione sia impostata in base alle procedure consigliate.</span><span class="sxs-lookup"><span data-stu-id="f607f-108">Proactively perform checks, verifying that the configuration is set according to recommended best practices.</span></span>

  - <span data-ttu-id="f607f-109">Rileva automaticamente gli aggiornamenti necessari a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f607f-109">Automatically detect required updates to Lync Server 2013.</span></span>

  - <span data-ttu-id="f607f-110">Genera un elenco di problemi, ad esempio le impostazioni di configurazione non ottimali, le opzioni non supportate, gli aggiornamenti mancanti o le procedure che sconsigliamo.</span><span class="sxs-lookup"><span data-stu-id="f607f-110">Generate a list of issues, such as suboptimal configuration settings, unsupported options, missing updates, or practices that we do not recommend.</span></span>

  - <span data-ttu-id="f607f-111">Informazioni su come risolvere i problemi specifici.</span><span class="sxs-lookup"><span data-stu-id="f607f-111">Help you troubleshoot and fix specific problems.</span></span>

<span data-ttu-id="f607f-112">Analizzatore procedure consigliate offre le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="f607f-112">Best Practices Analyzer provides the following features:</span></span>

  - <span data-ttu-id="f607f-113">Prerequisiti di installazione minimi.</span><span class="sxs-lookup"><span data-stu-id="f607f-113">Minimal installation prerequisites.</span></span>

  - <span data-ttu-id="f607f-114">Documentazione online sui problemi segnalati, inclusi suggerimenti per la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="f607f-114">Online documentation about reported issues, including troubleshooting tips.</span></span>

  - <span data-ttu-id="f607f-115">Informazioni sulla configurazione che è possibile salvare per la revisione successiva.</span><span class="sxs-lookup"><span data-stu-id="f607f-115">Configuration information that you can save for later review.</span></span>

  - <span data-ttu-id="f607f-116">Analisi del sistema all'avanguardia.</span><span class="sxs-lookup"><span data-stu-id="f607f-116">State-of-the-art system analysis.</span></span>

<span data-ttu-id="f607f-117">Best Practices Analyzer usa un set di file di configurazione XML per determinare le informazioni da raccogliere dall'ambiente Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f607f-117">Best Practices Analyzer uses a set of XML configuration files to determine the information to gather from your Lync Server 2013 environment.</span></span> <span data-ttu-id="f607f-118">Oltre a controllare i servizi di dominio Active Directory, controlla le origini, ad esempio il registro di sistema operativo Windows Server e le impostazioni in Strumentazione gestione Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="f607f-118">In addition to checking Active Directory Domain Services, it checks sources such as the Windows Server operating system registry and settings in Windows Management Instrumentation (WMI).</span></span>

<span data-ttu-id="f607f-119">Analizzatore procedure consigliate Confronta i dati raccolti con un set di regole predefinite per le impostazioni e le configurazioni delle distribuzioni di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f607f-119">Best Practices Analyzer compares the data it gathers with a set of predefined rules for the settings and configurations of Lync Server 2013 deployments.</span></span>

<span data-ttu-id="f607f-120">Dopo aver confrontato i dati raccolti con le regole predefinite, lo strumento segnala i problemi.</span><span class="sxs-lookup"><span data-stu-id="f607f-120">After comparing the collected data with the predefined rules, the tool reports issues.</span></span> <span data-ttu-id="f607f-121">Per ogni problema che segnala, Best Practices Analyzer fornisce informazioni su ciò che è stato trovato nell'ambiente di Lync Server 2013 digitalizzato e la configurazione consigliata.</span><span class="sxs-lookup"><span data-stu-id="f607f-121">For every issue that it reports, Best Practices Analyzer provides information about what was found in the scanned Lync Server 2013 environment and the recommended configuration.</span></span> <span data-ttu-id="f607f-122">Best Practices Analyzer offre anche collegamenti a informazioni più dettagliate sui problemi specifici.</span><span class="sxs-lookup"><span data-stu-id="f607f-122">Best Practices Analyzer also provides links to more detailed information about the specific issues.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f607f-123">Lync Server 2013, Best Practices Analyzer raccoglie le informazioni di configurazione solo dai componenti di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f607f-123">The Lync Server 2013, Best Practices Analyzer gathers configuration information only from Lync Server 2013 components.</span></span> <span data-ttu-id="f607f-124">È possibile usare le versioni precedenti dello strumento per analizzare gli ambienti precedenti.</span><span class="sxs-lookup"><span data-stu-id="f607f-124">You can use the previous versions of the tool to scan previous environments.</span></span> <span data-ttu-id="f607f-125">Per informazioni dettagliate, vedere <A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">requisiti per l'uso di Best Practices Analyzer in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f607f-125">For details, see <A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">Requirements for running Best Practices Analyzer in Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>


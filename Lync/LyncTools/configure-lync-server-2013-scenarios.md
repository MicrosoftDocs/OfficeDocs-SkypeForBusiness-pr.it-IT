---
title: Configurare gli scenari di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Lync Server 2013 Scenarios
ms:assetid: 6705346b-1512-4af3-85e4-64dfa6ee6f80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945596(v=OCS.15)
ms:contentKeyID: 51541420
ms.date: 12/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93ad7a3be8b69c956b1cca0f1d1554a5fa288f17
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975978"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-scenarios"></a><span data-ttu-id="529e2-102">Configurare gli scenari di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="529e2-102">Configure Lync Server 2013 Scenarios</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="529e2-103">_**Argomento Ultima modifica:** 2016-12-28_</span><span class="sxs-lookup"><span data-stu-id="529e2-103">_**Topic Last Modified:** 2016-12-28_</span></span>

<span data-ttu-id="529e2-104">Per eseguire lo strumento di gestione dello stress e delle prestazioni di Lync Server 2013 (LyncPerfTool), la topologia di Lync Server 2013 deve essere prima configurata per gli scenari che verranno eseguiti.</span><span class="sxs-lookup"><span data-stu-id="529e2-104">To run the Lync Server 2013 Stress and Performance Tool (LyncPerfTool), the Lync Server 2013 topology must first be configured for the scenarios that will be executed.</span></span> <span data-ttu-id="529e2-105">Se Lync Server 2013 non è configurato o è configurato in modo non corretto, nella maggior parte dei casi non verrà eseguita la simulazione di caricamento.</span><span class="sxs-lookup"><span data-stu-id="529e2-105">If Lync Server 2013 is not configured or is configured incorrectly, load simulation will fail in most cases.</span></span> <span data-ttu-id="529e2-106">Con lo strumento di gestione dello stress e delle prestazioni di Lync Server 2013 sono stati forniti gli script di Lync Server Management Shell e i file di risorse di base che è possibile usare come punto di partenza per la configurazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="529e2-106">With the Lync Server 2013 Stress and Performance Tool, we have provided example Lync Server Management Shell scripts and basic resource files that can be used as a starting point for configuring Lync Server 2013.</span></span> <span data-ttu-id="529e2-107">Questo argomento descrive gli esempi di Windows PowerShell forniti.</span><span class="sxs-lookup"><span data-stu-id="529e2-107">This topic describes the Windows PowerShell examples provided.</span></span> <span data-ttu-id="529e2-108">Si noti che non è l'obiettivo di questo argomento descrivere come configurare Lync Server 2013 in generale.</span><span class="sxs-lookup"><span data-stu-id="529e2-108">Note that it is not the goal of this topic to describe how to configure Lync Server 2013 in general.</span></span> <span data-ttu-id="529e2-109">Per informazioni dettagliate sull'uso di Windows PowerShell in Lync Server 2013, vedere la documentazione di Lync Server Management <https://technet.microsoft.com/en-us/library/gg398474.aspx>shell all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="529e2-109">For details about working with Windows PowerShell in Lync Server 2013, see the Lync Server Management Shell documentation at <https://technet.microsoft.com/en-us/library/gg398474.aspx>.</span></span>

<div>

## <a name="about-running-lync-server-management-shell-scripts"></a><span data-ttu-id="529e2-110">Informazioni sull'uso degli script di Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="529e2-110">About Running Lync Server Management Shell Scripts</span></span>

<span data-ttu-id="529e2-111">Sono stati forniti gli script di Lync Server Management Shell che possono essere usati in preparazione per l'uso della simulazione di caricamento.</span><span class="sxs-lookup"><span data-stu-id="529e2-111">We have provided example Lync Server Management Shell scripts that may be used in preparation for running load simulation.</span></span> <span data-ttu-id="529e2-112">Poiché gli script sono destinati alla simulazione del carico, sono semplici e permissivi e pertanto potrebbero non essere appropriati per la produzione.</span><span class="sxs-lookup"><span data-stu-id="529e2-112">Because the scripts are intended for load simulation, they are simple and permissive, and therefore may not be appropriate for production.</span></span> <span data-ttu-id="529e2-113">Tutti gli script sono esempi e devono essere rivisti e, in alcuni casi, modificati per riflettere la topologia.</span><span class="sxs-lookup"><span data-stu-id="529e2-113">All scripts are examples and must be reviewed, and, in some cases, modified to reflect your topology.</span></span> <span data-ttu-id="529e2-114">Come minimo, ci aspettiamo che lo scenario di Response Group Service (RGS) debba essere modificato per specificare gli agenti assegnati ai gruppi di agenti.</span><span class="sxs-lookup"><span data-stu-id="529e2-114">At a minimum, we expect that the Response Group Service (RGS) scenario would need to be modified to specify the agents that are assigned to the agent groups.</span></span> <span data-ttu-id="529e2-115">Tuttavia, hai la possibilità di non simulare questo carico.</span><span class="sxs-lookup"><span data-stu-id="529e2-115">However, you have the option to not simulate this load.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="529e2-116">Fare attenzione a rivedendo e capendo gli esempi forniti.</span><span class="sxs-lookup"><span data-stu-id="529e2-116">Take care in reviewing and understanding the examples provided.</span></span> <span data-ttu-id="529e2-117">Gli script sovrascriveranno le impostazioni esistenti nella topologia.</span><span class="sxs-lookup"><span data-stu-id="529e2-117">Scripts will overwrite any existing settings in the topology.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="529e2-118">Per informazioni dettagliate sull'uso di Windows PowerShell e Lync Server Management Shell, vedere il Blog di Lync Server 2013 di <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A>Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="529e2-118">For details about using Windows PowerShell and the Lync Server Management Shell, see the Lync Server 2013 Windows PowerShell Blog at <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A>.</span></span>



</div>

</div>

<div>

## <a name="stress-and-performance-tool-client-version-monikers"></a><span data-ttu-id="529e2-119">Moniker della versione client dello strumento stress e prestazioni</span><span class="sxs-lookup"><span data-stu-id="529e2-119">Stress and Performance Tool Client Version Monikers</span></span>

<span data-ttu-id="529e2-120">Potrebbe essere necessario configurare i criteri di controllo della versione client se sono state modificate le impostazioni dei valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="529e2-120">You may need to configure the Client Version Check policy if you have changed the settings from the default values.</span></span> <span data-ttu-id="529e2-121">Per informazioni dettagliate, vedere la pagina relativa alla <https://technet.microsoft.com/en-us/library/gg412832(v=ocs.15).aspx>configurazione delle versioni client supportate.</span><span class="sxs-lookup"><span data-stu-id="529e2-121">For details, see “Configuring supported client versions” at <https://technet.microsoft.com/en-us/library/gg412832(v=ocs.15).aspx>.</span></span> <span data-ttu-id="529e2-122">Lo strumento di monitoraggio dello stress e delle prestazioni di Lync Server 2013 usa le versioni seguenti dell'agente utente per impostazione predefinita durante la comunicazione con Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="529e2-122">The Lync Server 2013 Stress and Performance Tool uses the following User Agent Versions by default when communicating with Lync Server 2013:</span></span>

  - <span data-ttu-id="529e2-123">LSPT/15.0.0.0 (strumento per lo stress e le prestazioni di Lync Server 2013)</span><span class="sxs-lookup"><span data-stu-id="529e2-123">LSPT/15.0.0.0 (Lync Server 2013 Stress and Performance Tool)</span></span>

  - <span data-ttu-id="529e2-124">OCPHONE/.0.522</span><span class="sxs-lookup"><span data-stu-id="529e2-124">OCPHONE/.0.522</span></span>

<span data-ttu-id="529e2-125">Questi sono per il client Mobility (UCWA) in LyncPerfTool:</span><span class="sxs-lookup"><span data-stu-id="529e2-125">These are for the Mobility (UCWA) client in LyncPerfTool:</span></span>

  - <span data-ttu-id="529e2-126">Strumento Perf UCWA/conferenza Web</span><span class="sxs-lookup"><span data-stu-id="529e2-126">Ucwa Perf Tool/Web Conference</span></span>

  - <span data-ttu-id="529e2-127">Strumento Perf UCWA/mobile</span><span class="sxs-lookup"><span data-stu-id="529e2-127">Ucwa Perf Tool/Mobile</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Configurare gli scenari di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Lync Server 2013 Scenarios
ms:assetid: 6705346b-1512-4af3-85e4-64dfa6ee6f80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945596(v=OCS.15)
ms:contentKeyID: 51541420
ms.date: 12/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d108cc3a2c49c40eb04c9039c83689fb8c5abf4c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499943"
---
# <a name="configure-lync-server-2013-scenarios"></a><span data-ttu-id="7e2b5-102">Configurare gli scenari di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e2b5-102">Configure Lync Server 2013 Scenarios</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e2b5-103">_**Ultimo argomento modificato:** 2016-12-28_</span><span class="sxs-lookup"><span data-stu-id="7e2b5-103">_**Topic Last Modified:** 2016-12-28_</span></span>

<span data-ttu-id="7e2b5-104">Per eseguire lo strumento di gestione dello stress e delle prestazioni di Lync Server 2013 (LyncPerfTool), è innanzitutto necessario configurare la topologia di Lync Server 2013 per gli scenari che verranno eseguiti.</span><span class="sxs-lookup"><span data-stu-id="7e2b5-104">To run the Lync Server 2013 Stress and Performance Tool (LyncPerfTool), the Lync Server 2013 topology must first be configured for the scenarios that will be executed.</span></span> <span data-ttu-id="7e2b5-105">Se Lync Server 2013 non è configurato o non è configurato in modo errato, nella maggior parte dei casi la simulazione del caricamento avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="7e2b5-105">If Lync Server 2013 is not configured or is configured incorrectly, load simulation will fail in most cases.</span></span> <span data-ttu-id="7e2b5-106">Con lo strumento Lync Server 2013 stress and performance sono stati forniti esempi di script Lync Server Management Shell e file di risorse di base che è possibile utilizzare come punto di partenza per la configurazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7e2b5-106">With the Lync Server 2013 Stress and Performance Tool, we have provided example Lync Server Management Shell scripts and basic resource files that can be used as a starting point for configuring Lync Server 2013.</span></span> <span data-ttu-id="7e2b5-107">In questo argomento vengono descritti gli esempi di Windows PowerShell forniti.</span><span class="sxs-lookup"><span data-stu-id="7e2b5-107">This topic describes the Windows PowerShell examples provided.</span></span> <span data-ttu-id="7e2b5-108">Si noti che non è l'obiettivo di questo argomento descrivere la modalità di configurazione di Lync Server 2013 in generale.</span><span class="sxs-lookup"><span data-stu-id="7e2b5-108">Note that it is not the goal of this topic to describe how to configure Lync Server 2013 in general.</span></span> <span data-ttu-id="7e2b5-109">Per informazioni dettagliate sull'utilizzo di Windows PowerShell in Lync Server 2013, vedere la documentazione di Lync Server Management Shell all'indirizzo <https://technet.microsoft.com/library/gg398474.aspx> .</span><span class="sxs-lookup"><span data-stu-id="7e2b5-109">For details about working with Windows PowerShell in Lync Server 2013, see the Lync Server Management Shell documentation at <https://technet.microsoft.com/library/gg398474.aspx>.</span></span>

<div>

## <a name="about-running-lync-server-management-shell-scripts"></a><span data-ttu-id="7e2b5-110">Informazioni sull'esecuzione di script di Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="7e2b5-110">About Running Lync Server Management Shell Scripts</span></span>

<span data-ttu-id="7e2b5-111">Sono stati forniti script di Lync Server Management Shell che possono essere utilizzati in preparazione per l'esecuzione di simulazione del carico.</span><span class="sxs-lookup"><span data-stu-id="7e2b5-111">We have provided example Lync Server Management Shell scripts that may be used in preparation for running load simulation.</span></span> <span data-ttu-id="7e2b5-112">Poiché gli script sono destinati alla simulazione del carico, sono semplici e permissivi e pertanto potrebbero non essere appropriati per la produzione.</span><span class="sxs-lookup"><span data-stu-id="7e2b5-112">Because the scripts are intended for load simulation, they are simple and permissive, and therefore may not be appropriate for production.</span></span> <span data-ttu-id="7e2b5-113">Tutti gli script sono esempi e devono essere esaminati e, in alcuni casi, modificati per riflettere la topologia.</span><span class="sxs-lookup"><span data-stu-id="7e2b5-113">All scripts are examples and must be reviewed, and, in some cases, modified to reflect your topology.</span></span> <span data-ttu-id="7e2b5-114">Come minimo, si prevede che lo scenario del servizio Response Group (RGS) debba essere modificato in modo da specificare gli agenti assegnati ai gruppi di agenti.</span><span class="sxs-lookup"><span data-stu-id="7e2b5-114">At a minimum, we expect that the Response Group Service (RGS) scenario would need to be modified to specify the agents that are assigned to the agent groups.</span></span> <span data-ttu-id="7e2b5-115">Tuttavia, si ha la possibilità di non simulare questo carico.</span><span class="sxs-lookup"><span data-stu-id="7e2b5-115">However, you have the option to not simulate this load.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="7e2b5-116">Fare attenzione a esaminare e comprendere gli esempi forniti.</span><span class="sxs-lookup"><span data-stu-id="7e2b5-116">Take care in reviewing and understanding the examples provided.</span></span> <span data-ttu-id="7e2b5-117">Gli script sovrascrivono le impostazioni esistenti nella topologia.</span><span class="sxs-lookup"><span data-stu-id="7e2b5-117">Scripts will overwrite any existing settings in the topology.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="7e2b5-118">Per informazioni dettagliate sull'utilizzo di Windows PowerShell e Lync Server Management Shell, vedere il Blog di Lync Server 2013 Windows PowerShell all'indirizzo <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A> .</span><span class="sxs-lookup"><span data-stu-id="7e2b5-118">For details about using Windows PowerShell and the Lync Server Management Shell, see the Lync Server 2013 Windows PowerShell Blog at <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A>.</span></span>



</div>

</div>

<div>

## <a name="stress-and-performance-tool-client-version-monikers"></a><span data-ttu-id="7e2b5-119">Moniker versione client dello strumento di stress e prestazioni</span><span class="sxs-lookup"><span data-stu-id="7e2b5-119">Stress and Performance Tool Client Version Monikers</span></span>

<span data-ttu-id="7e2b5-120">Potrebbe essere necessario configurare i criteri di controllo della versione client se sono state modificate le impostazioni dai valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="7e2b5-120">You may need to configure the Client Version Check policy if you have changed the settings from the default values.</span></span> <span data-ttu-id="7e2b5-121">Per informazioni dettagliate, vedere la sezione relativa alla configurazione delle versioni client supportate all'indirizzo <https://technet.microsoft.com/library/gg412832(v=ocs.15).aspx> .</span><span class="sxs-lookup"><span data-stu-id="7e2b5-121">For details, see “Configuring supported client versions” at <https://technet.microsoft.com/library/gg412832(v=ocs.15).aspx>.</span></span> <span data-ttu-id="7e2b5-122">Lo strumento Lync Server 2013 stress and performance utilizza le seguenti versioni di agente utente per impostazione predefinita durante la comunicazione con Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="7e2b5-122">The Lync Server 2013 Stress and Performance Tool uses the following User Agent Versions by default when communicating with Lync Server 2013:</span></span>

  - <span data-ttu-id="7e2b5-123">LSPT/15.0.0.0 (strumento di stress e prestazioni di Lync Server 2013)</span><span class="sxs-lookup"><span data-stu-id="7e2b5-123">LSPT/15.0.0.0 (Lync Server 2013 Stress and Performance Tool)</span></span>

  - <span data-ttu-id="7e2b5-124">OCPHONE/.0.522</span><span class="sxs-lookup"><span data-stu-id="7e2b5-124">OCPHONE/.0.522</span></span>

<span data-ttu-id="7e2b5-125">Si tratta del client per dispositivi mobili (UCWA) in LyncPerfTool:</span><span class="sxs-lookup"><span data-stu-id="7e2b5-125">These are for the Mobility (UCWA) client in LyncPerfTool:</span></span>

  - <span data-ttu-id="7e2b5-126">UCWA Perf Tool/Web Conference</span><span class="sxs-lookup"><span data-stu-id="7e2b5-126">Ucwa Perf Tool/Web Conference</span></span>

  - <span data-ttu-id="7e2b5-127">UCWA Perf Tool/mobile</span><span class="sxs-lookup"><span data-stu-id="7e2b5-127">Ucwa Perf Tool/Mobile</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


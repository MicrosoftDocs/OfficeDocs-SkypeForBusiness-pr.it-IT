---
title: Scenari di prestazioni per lo strumento Di stress e prestazioni di Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: Attività da eseguire per configurare Skype for Business Server 2015 per eseguire test di carico e prestazioni, utilizzando lo strumento Stress and Performance.
ms.openlocfilehash: e0a3cc3767cf7652bda9bfacb14ced6632e32d87
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105372"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="da172-103">Scenari di prestazioni per lo strumento Di stress e prestazioni di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="da172-103">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="da172-104">Attività da eseguire per configurare Skype for Business Server 2015 per eseguire test di carico e prestazioni, utilizzando lo strumento Stress and Performance.</span><span class="sxs-lookup"><span data-stu-id="da172-104">Tasks you'll need to do to configure Skype for Business Server 2015 to do performance and load-testing, using the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="da172-105">Per eseguire lo strumento Di stress e prestazioni di Skype for Business Server 2015 (LyncPerfTool), la topologia di Skype for Business Server 2015 deve prima essere configurata per gli scenari pertinenti.</span><span class="sxs-lookup"><span data-stu-id="da172-105">To run the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool), the Skype for Business Server 2015 topology must first be configured for scenarios relevant to you.</span></span> <span data-ttu-id="da172-106">Se Skype for Business Server 2015 non è configurato o non è configurato correttamente, è molto probabile che la simulazione del carico non riesca.</span><span class="sxs-lookup"><span data-stu-id="da172-106">If Skype for Business Server 2015 isn't configured, or is configured incorrectly, your load simulation is very likely to fail.</span></span> <span data-ttu-id="da172-107">Con lo strumento Di stress e prestazioni di Skype for Business Server 2015, stiamo fornendo script di Skype for Business Server Management Shell di esempio e file di risorse di base come parte del [download dello strumento.](https://www.microsoft.com/download/details.aspx?id=50367)</span><span class="sxs-lookup"><span data-stu-id="da172-107">With the Skype for Business Server 2015 Stress and Performance Tool, we're providing example Skype for Business Server Management Shell scripts and basic resource files as part of the [tool download](https://www.microsoft.com/download/details.aspx?id=50367).</span></span> <span data-ttu-id="da172-108">Questi possono essere usati come punto di partenza per configurare la distribuzione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="da172-108">These can be used as a starting point for configuring your Skype for Business Server deployment.</span></span> <span data-ttu-id="da172-109">In questo articolo vengono descritti Windows PowerShell esempi forniti.</span><span class="sxs-lookup"><span data-stu-id="da172-109">This article describes the Windows PowerShell examples provided.</span></span>
  
> [!NOTE]
> <span data-ttu-id="da172-110">Questo argomento non ti aiuterà a descrivere come configurare Skype for Business Server 2015 in generale, abbiamo altri argomenti relativi alla pianificazione e alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="da172-110">This topic won't help you describe how to configure Skype for Business Server 2015 generally, we have other Planning and Deployment topics for that.</span></span> <span data-ttu-id="da172-111">Per informazioni dettagliate sull'Windows PowerShell in Skype for Business Server 2015, vedere la documentazione di Skype for Business Server Management Shell all'indirizzo Insert introduction HERE.</span><span class="sxs-lookup"><span data-stu-id="da172-111">For details about working with Windows PowerShell in Skype for Business Server 2015, see the Skype for Business Server Management Shell documentation at Insert introduction HERE.</span></span> 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a><span data-ttu-id="da172-112">Informazioni sull'esecuzione degli script di Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="da172-112">About running Skype for Business Server management shell scripts</span></span>

<span data-ttu-id="da172-113">Microsoft fornisce script di PowerShell di esempio che è possibile usare per preparare le simulazioni di carico.</span><span class="sxs-lookup"><span data-stu-id="da172-113">We're providing sample PowerShell scripts you can use to prepare for your load simulations.</span></span> <span data-ttu-id="da172-114">Poiché questi script sono destinati alla simulazione del carico, è possibile trovarli semplici e permissivi.</span><span class="sxs-lookup"><span data-stu-id="da172-114">Because these scripts are intended for load simulation, you'll find them to be simple and permissive.</span></span> <span data-ttu-id="da172-115">Potrebbe non essere appropriato per l'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="da172-115">That may not be appropriate for your production environment.</span></span> <span data-ttu-id="da172-116">Anche in questo caso si sottolinea che questi script sono esempi, è necessario esaminarli e in molti casi apportare modifiche rilevanti per l'ambiente prima di poterli utilizzare in modo pratico.</span><span class="sxs-lookup"><span data-stu-id="da172-116">Again we stress that these scripts are samples, you'll need to review them and in many cases make changes relevant to your environment before being able to make practical use of them.</span></span> <span data-ttu-id="da172-117">Come minimo, ci si aspetterebbe che sia necessario modificare lo script RSG (Response Service Group) con la topologia in mente (per specificare gli agenti assegnati ai gruppi di agenti).</span><span class="sxs-lookup"><span data-stu-id="da172-117">At a minimum, we'd expect you'd need to modify the Response Service Group (RSG) script with your topology in mind (to specify the agents assigned to the agent groups).</span></span> <span data-ttu-id="da172-118">Ma non è necessario eseguir, se non è necessario.</span><span class="sxs-lookup"><span data-stu-id="da172-118">But you don't have to run that, if you don't need to.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="da172-119">Si prega di fare attenzione a rivedere e comprendere questi esempi.</span><span class="sxs-lookup"><span data-stu-id="da172-119">Please take care in reviewing and understanding these samples.</span></span> <span data-ttu-id="da172-120">Durante l'esecuzione degli script verranno sovrascritte tutte le impostazioni esistenti nella topologia.</span><span class="sxs-lookup"><span data-stu-id="da172-120">Scripts will overwrite any existing settings in the topology when run.</span></span> 
  
## <a name="stress-and-performance-tool-client-version-names"></a><span data-ttu-id="da172-121">Nomi delle versioni client dello Strumento stress e prestazioni</span><span class="sxs-lookup"><span data-stu-id="da172-121">Stress and Performance Tool client version names</span></span>

<span data-ttu-id="da172-122">Potrebbe essere necessario configurare il criterio Controllo versione client se in precedenza sono state modificate le impostazioni rispetto ai valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="da172-122">You might need to configure the Client Version Check policy if you've previously changed the settings from the default values.</span></span> <span data-ttu-id="da172-123">In caso di dubbi, consultare la documentazione relativa al controllo [della versione client](/previous-versions/office/lync-server-2013/lync-server-2013-view-client-version-policy-rules).</span><span class="sxs-lookup"><span data-stu-id="da172-123">If you're unsure about this, check the [Client Version Check documentation](/previous-versions/office/lync-server-2013/lync-server-2013-view-client-version-policy-rules).</span></span>
  
<span data-ttu-id="da172-124">Lo strumento Stress and Performance usa per impostazione predefinita le seguenti versioni dell'agente utente quando comunica con Skype for Business Server 2015:</span><span class="sxs-lookup"><span data-stu-id="da172-124">The Stress and Performance Tool uses the following User Agent versions by default when communicating with Skype for Business Server 2015:</span></span>
  
- <span data-ttu-id="da172-125">LSPT/15.0.0.0 (Strumento stress e prestazioni di Skype for Business Server 2015)</span><span class="sxs-lookup"><span data-stu-id="da172-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span></span>
    
- <span data-ttu-id="da172-126">OCPHONE/.0.522</span><span class="sxs-lookup"><span data-stu-id="da172-126">OCPHONE/.0.522</span></span>
    
<span data-ttu-id="da172-127">Per il client per dispositivi mobili (UCWA) in LyncPerfTool:</span><span class="sxs-lookup"><span data-stu-id="da172-127">For the Mobility (UCWA) client in LyncPerfTool:</span></span>
  
- <span data-ttu-id="da172-128">UCWA Perf Tool/Web Conference</span><span class="sxs-lookup"><span data-stu-id="da172-128">UCWA Perf Tool/Web Conference</span></span>
    
- <span data-ttu-id="da172-129">UCWA Perf Tool/Mobile</span><span class="sxs-lookup"><span data-stu-id="da172-129">UCWA Perf Tool/Mobile</span></span>

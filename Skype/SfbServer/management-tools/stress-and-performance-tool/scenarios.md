---
title: Scenari di prestazioni per lo strumento Skype for Business Server 2015 Stress and Performance
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
description: Attività da eseguire per configurare Skype for Business Server 2015 per eseguire test delle prestazioni e del carico, utilizzando lo strumento Stress and Performance.
ms.openlocfilehash: 3edc945f09ef5b2c7c6ecdefcbc66166f0945aec
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814706"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="8d436-103">Scenari di prestazioni per lo strumento Skype for Business Server 2015 Stress and Performance</span><span class="sxs-lookup"><span data-stu-id="8d436-103">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="8d436-104">Attività da eseguire per configurare Skype for Business Server 2015 per eseguire test delle prestazioni e del carico, utilizzando lo strumento Stress and Performance.</span><span class="sxs-lookup"><span data-stu-id="8d436-104">Tasks you'll need to do to configure Skype for Business Server 2015 to do performance and load-testing, using the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="8d436-105">Per eseguire lo strumento Skype for Business Server 2015 Stress and Performance (LyncPerfTool), la topologia di Skype for Business Server 2015 deve prima essere configurata per gli scenari pertinenti.</span><span class="sxs-lookup"><span data-stu-id="8d436-105">To run the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool), the Skype for Business Server 2015 topology must first be configured for scenarios relevant to you.</span></span> <span data-ttu-id="8d436-106">Se Skype for Business Server 2015 non è configurato o non è configurato correttamente, è molto probabile che la simulazione del carico non riesca.</span><span class="sxs-lookup"><span data-stu-id="8d436-106">If Skype for Business Server 2015 isn't configured, or is configured incorrectly, your load simulation is very likely to fail.</span></span> <span data-ttu-id="8d436-107">Con lo strumento Skype for Business Server 2015 Stress and Performance, stiamo fornendo script di esempio di Skype for Business Server Management Shell e file di risorse di base come parte del [download dello strumento.](https://www.microsoft.com/download/details.aspx?id=50367)</span><span class="sxs-lookup"><span data-stu-id="8d436-107">With the Skype for Business Server 2015 Stress and Performance Tool, we're providing example Skype for Business Server Management Shell scripts and basic resource files as part of the [tool download](https://www.microsoft.com/download/details.aspx?id=50367).</span></span> <span data-ttu-id="8d436-108">Questi possono essere usati come punto di partenza per configurare la distribuzione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8d436-108">These can be used as a starting point for configuring your Skype for Business Server deployment.</span></span> <span data-ttu-id="8d436-109">In questo articolo vengono descritti Windows PowerShell esempi forniti.</span><span class="sxs-lookup"><span data-stu-id="8d436-109">This article describes the Windows PowerShell examples provided.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8d436-110">In questo argomento non viene descritto come configurare Skype for Business Server 2015 in generale, sono disponibili altri argomenti relativi alla pianificazione e alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8d436-110">This topic won't help you describe how to configure Skype for Business Server 2015 generally, we have other Planning and Deployment topics for that.</span></span> <span data-ttu-id="8d436-111">Per informazioni dettagliate sull'Windows PowerShell in Skype for Business Server 2015, vedere la documentazione di Skype for Business Server Management Shell in Insert introduction HERE.</span><span class="sxs-lookup"><span data-stu-id="8d436-111">For details about working with Windows PowerShell in Skype for Business Server 2015, see the Skype for Business Server Management Shell documentation at Insert introduction HERE.</span></span> 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a><span data-ttu-id="8d436-112">Informazioni sull'esecuzione degli script di Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="8d436-112">About running Skype for Business Server management shell scripts</span></span>

<span data-ttu-id="8d436-113">Microsoft fornisce script di PowerShell di esempio che è possibile usare per preparare le simulazioni di carico.</span><span class="sxs-lookup"><span data-stu-id="8d436-113">We're providing sample PowerShell scripts you can use to prepare for your load simulations.</span></span> <span data-ttu-id="8d436-114">Poiché questi script sono destinati alla simulazione del carico, saranno semplici e permissivi.</span><span class="sxs-lookup"><span data-stu-id="8d436-114">Because these scripts are intended for load simulation, you'll find them to be simple and permissive.</span></span> <span data-ttu-id="8d436-115">Potrebbe non essere appropriato per l'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="8d436-115">That may not be appropriate for your production environment.</span></span> <span data-ttu-id="8d436-116">Anche in questo caso si sottolinea che questi script sono esempi, è necessario esaminarli e in molti casi apportare modifiche rilevanti per il proprio ambiente prima di poterli utilizzare in modo pratico.</span><span class="sxs-lookup"><span data-stu-id="8d436-116">Again we stress that these scripts are samples, you'll need to review them and in many cases make changes relevant to your environment before being able to make practical use of them.</span></span> <span data-ttu-id="8d436-117">Come minimo, ci si aspetterebbe che sia necessario modificare lo script di Response Service Group (RSG) con la topologia in considerazione (per specificare gli agenti assegnati ai gruppi di agenti).</span><span class="sxs-lookup"><span data-stu-id="8d436-117">At a minimum, we'd expect you'd need to modify the Response Service Group (RSG) script with your topology in mind (to specify the agents assigned to the agent groups).</span></span> <span data-ttu-id="8d436-118">Ma non è necessario eseguire questa, se non è necessario.</span><span class="sxs-lookup"><span data-stu-id="8d436-118">But you don't have to run that, if you don't need to.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="8d436-119">Si prega di esaminare e comprendere questi esempi.</span><span class="sxs-lookup"><span data-stu-id="8d436-119">Please take care in reviewing and understanding these samples.</span></span> <span data-ttu-id="8d436-120">Durante l'esecuzione, gli script sovrascriveranno le impostazioni esistenti nella topologia.</span><span class="sxs-lookup"><span data-stu-id="8d436-120">Scripts will overwrite any existing settings in the topology when run.</span></span> 
  
## <a name="stress-and-performance-tool-client-version-names"></a><span data-ttu-id="8d436-121">Nomi delle versioni client dello Strumento stress e prestazioni</span><span class="sxs-lookup"><span data-stu-id="8d436-121">Stress and Performance Tool client version names</span></span>

<span data-ttu-id="8d436-122">Potrebbe essere necessario configurare il criterio Controllo versione client se in precedenza sono state modificate le impostazioni rispetto ai valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="8d436-122">You might need to configure the Client Version Check policy if you've previously changed the settings from the default values.</span></span> <span data-ttu-id="8d436-123">In caso di dubbi, consultare la documentazione relativa al controllo [della versione client.](https://msdn.microsoft.com/vsto/jj923060)</span><span class="sxs-lookup"><span data-stu-id="8d436-123">If you're unsure about this, check the [Client Version Check documentation](https://msdn.microsoft.com/vsto/jj923060).</span></span>
  
<span data-ttu-id="8d436-124">Lo strumento Stress and Performance usa le seguenti versioni agente utente per impostazione predefinita quando comunica con Skype for Business Server 2015:</span><span class="sxs-lookup"><span data-stu-id="8d436-124">The Stress and Performance Tool uses the following User Agent versions by default when communicating with Skype for Business Server 2015:</span></span>
  
- <span data-ttu-id="8d436-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span><span class="sxs-lookup"><span data-stu-id="8d436-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span></span>
    
- <span data-ttu-id="8d436-126">OCPHONE/.0.522</span><span class="sxs-lookup"><span data-stu-id="8d436-126">OCPHONE/.0.522</span></span>
    
<span data-ttu-id="8d436-127">Per il client per dispositivi mobili (UCWA) in LyncPerfTool:</span><span class="sxs-lookup"><span data-stu-id="8d436-127">For the Mobility (UCWA) client in LyncPerfTool:</span></span>
  
- <span data-ttu-id="8d436-128">Strumento UCWA Perf/Conferenza Web</span><span class="sxs-lookup"><span data-stu-id="8d436-128">UCWA Perf Tool/Web Conference</span></span>
    
- <span data-ttu-id="8d436-129">UCWA Perf Tool/Mobile</span><span class="sxs-lookup"><span data-stu-id="8d436-129">UCWA Perf Tool/Mobile</span></span>
    


---
title: Scenari di prestazioni per lo strumento di stress e prestazioni di Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Attività che è necessario eseguire per configurare Skype for Business Server 2015 per eseguire le prestazioni e i test di carico, utilizzando lo strumento stress and performance.
ms.openlocfilehash: 5531627ab7d5072d32dfcf60fed41eac47f5373f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983851"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="2e87f-103">Scenari di prestazioni per lo strumento di stress e prestazioni di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2e87f-103">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="2e87f-104">Attività che è necessario eseguire per configurare Skype for Business Server 2015 per eseguire le prestazioni e i test di carico, utilizzando lo strumento stress and performance.</span><span class="sxs-lookup"><span data-stu-id="2e87f-104">Tasks you'll need to do to configure Skype for Business Server 2015 to do performance and load-testing, using the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="2e87f-105">Per eseguire lo strumento di gestione dello stress e delle prestazioni di Skype for Business Server 2015 (LyncPerfTool), è innanzitutto necessario configurare la topologia di Skype for Business Server 2015 per gli scenari rilevanti per l'utente.</span><span class="sxs-lookup"><span data-stu-id="2e87f-105">To run the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool), the Skype for Business Server 2015 topology must first be configured for scenarios relevant to you.</span></span> <span data-ttu-id="2e87f-106">Se Skype for Business Server 2015 non è configurato o è configurato in modo errato, è probabile che la simulazione di carico abbia esito negativo.</span><span class="sxs-lookup"><span data-stu-id="2e87f-106">If Skype for Business Server 2015 isn't configured, or is configured incorrectly, your load simulation is very likely to fail.</span></span> <span data-ttu-id="2e87f-107">Con lo strumento per lo stress e le prestazioni di Skype for Business Server 2015, vengono fornite esempi di script di gestione della shell di Skype for Business Server e file di risorse di base come parte del [download dello strumento](https://www.microsoft.com/download/details.aspx?id=50367).</span><span class="sxs-lookup"><span data-stu-id="2e87f-107">With the Skype for Business Server 2015 Stress and Performance Tool, we're providing example Skype for Business Server Management Shell scripts and basic resource files as part of the [tool download](https://www.microsoft.com/download/details.aspx?id=50367).</span></span> <span data-ttu-id="2e87f-108">Questi possono essere utilizzati come punto di partenza per la configurazione della distribuzione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2e87f-108">These can be used as a starting point for configuring your Skype for Business Server deployment.</span></span> <span data-ttu-id="2e87f-109">In questo articolo vengono descritti gli esempi di Windows PowerShell forniti.</span><span class="sxs-lookup"><span data-stu-id="2e87f-109">This article describes the Windows PowerShell examples provided.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2e87f-110">In questo argomento non viene descritto come configurare Skype for Business Server 2015 in genere, sono disponibili altri argomenti per la pianificazione e la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="2e87f-110">This topic won't help you describe how to configure Skype for Business Server 2015 generally, we have other Planning and Deployment topics for that.</span></span> <span data-ttu-id="2e87f-111">Per informazioni dettagliate sull'utilizzo di Windows PowerShell in Skype for Business Server 2015, vedere la documentazione su Skype for Business Server Management Shell all'articolo Introduzione qui.</span><span class="sxs-lookup"><span data-stu-id="2e87f-111">For details about working with Windows PowerShell in Skype for Business Server 2015, see the Skype for Business Server Management Shell documentation at Insert introduction HERE.</span></span> 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a><span data-ttu-id="2e87f-112">Informazioni sull'esecuzione degli script di Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="2e87f-112">About running Skype for Business Server management shell scripts</span></span>

<span data-ttu-id="2e87f-113">Vengono fornite esempi di script PowerShell che è possibile utilizzare per preparare le simulazioni di carico.</span><span class="sxs-lookup"><span data-stu-id="2e87f-113">We're providing sample PowerShell scripts you can use to prepare for your load simulations.</span></span> <span data-ttu-id="2e87f-114">Poiché questi script sono destinati alla simulazione del carico, è possibile trovarli come semplici e permissivi.</span><span class="sxs-lookup"><span data-stu-id="2e87f-114">Because these scripts are intended for load simulation, you'll find them to be simple and permissive.</span></span> <span data-ttu-id="2e87f-115">Potrebbe non essere appropriato per l'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="2e87f-115">That may not be appropriate for your production environment.</span></span> <span data-ttu-id="2e87f-116">Anche in questo caso viene sottolineato che questi script sono campioni, è necessario esaminarli e, in molti casi, apportare modifiche rilevanti all'ambiente prima di essere in grado di utilizzarli in modo pratico.</span><span class="sxs-lookup"><span data-stu-id="2e87f-116">Again we stress that these scripts are samples, you'll need to review them and in many cases make changes relevant to your environment before being able to make practical use of them.</span></span> <span data-ttu-id="2e87f-117">Come minimo, è prevedibile che sia necessario modificare lo script di Response Service Group (RSG) con la topologia in mente (per specificare gli agenti assegnati ai gruppi di agenti).</span><span class="sxs-lookup"><span data-stu-id="2e87f-117">At a minimum, we'd expect you'd need to modify the Response Service Group (RSG) script with your topology in mind (to specify the agents assigned to the agent groups).</span></span> <span data-ttu-id="2e87f-118">Tuttavia, non è necessario eseguirlo, se non si ha necessità di farlo.</span><span class="sxs-lookup"><span data-stu-id="2e87f-118">But you don't have to run that, if you don't need to.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="2e87f-119">Fare attenzione a controllare e comprendere questi esempi.</span><span class="sxs-lookup"><span data-stu-id="2e87f-119">Please take care in reviewing and understanding these samples.</span></span> <span data-ttu-id="2e87f-120">Gli script sovrascrivono le impostazioni esistenti nella topologia quando vengono eseguite.</span><span class="sxs-lookup"><span data-stu-id="2e87f-120">Scripts will overwrite any existing settings in the topology when run.</span></span> 
  
## <a name="stress-and-performance-tool-client-version-names"></a><span data-ttu-id="2e87f-121">Nomi delle versioni client dello strumento di stress e prestazioni</span><span class="sxs-lookup"><span data-stu-id="2e87f-121">Stress and Performance Tool client version names</span></span>

<span data-ttu-id="2e87f-122">Potrebbe essere necessario configurare i criteri di controllo della versione client se le impostazioni sono state modificate in precedenza dai valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="2e87f-122">You might need to configure the Client Version Check policy if you've previously changed the settings from the default values.</span></span> <span data-ttu-id="2e87f-123">In caso di dubbi, vedere la [documentazione relativa alla verifica della versione client](https://msdn.microsoft.com/vsto/jj923060).</span><span class="sxs-lookup"><span data-stu-id="2e87f-123">If you're unsure about this, check the [Client Version Check documentation](https://msdn.microsoft.com/vsto/jj923060).</span></span>
  
<span data-ttu-id="2e87f-124">Lo strumento stress and performance utilizza le seguenti versioni di agente utente per impostazione predefinita durante la comunicazione con Skype for Business Server 2015:</span><span class="sxs-lookup"><span data-stu-id="2e87f-124">The Stress and Performance Tool uses the following User Agent versions by default when communicating with Skype for Business Server 2015:</span></span>
  
- <span data-ttu-id="2e87f-125">LSPT/15.0.0.0 (strumento di stress e prestazioni di Skype for Business Server 2015)</span><span class="sxs-lookup"><span data-stu-id="2e87f-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span></span>
    
- <span data-ttu-id="2e87f-126">OCPHONE/.0.522</span><span class="sxs-lookup"><span data-stu-id="2e87f-126">OCPHONE/.0.522</span></span>
    
<span data-ttu-id="2e87f-127">Per il client Mobility (UCWA) in LyncPerfTool:</span><span class="sxs-lookup"><span data-stu-id="2e87f-127">For the Mobility (UCWA) client in LyncPerfTool:</span></span>
  
- <span data-ttu-id="2e87f-128">UCWA Perf Tool/Web Conference</span><span class="sxs-lookup"><span data-stu-id="2e87f-128">UCWA Perf Tool/Web Conference</span></span>
    
- <span data-ttu-id="2e87f-129">UCWA Perf Tool/mobile</span><span class="sxs-lookup"><span data-stu-id="2e87f-129">UCWA Perf Tool/Mobile</span></span>
    


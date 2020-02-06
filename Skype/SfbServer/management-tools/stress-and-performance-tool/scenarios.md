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
description: Attività che è necessario eseguire per configurare Skype for Business Server 2015 per eseguire prestazioni e test di carico, usando lo strumento stress e prestazioni.
ms.openlocfilehash: 343378d0b0d763d8a290e8d1e930a64c5d114bdb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803876"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="8ae98-103">Scenari di prestazioni per lo strumento di stress e prestazioni di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8ae98-103">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="8ae98-104">Attività che è necessario eseguire per configurare Skype for Business Server 2015 per eseguire prestazioni e test di carico, usando lo strumento stress e prestazioni.</span><span class="sxs-lookup"><span data-stu-id="8ae98-104">Tasks you'll need to do to configure Skype for Business Server 2015 to do performance and load-testing, using the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="8ae98-105">Per eseguire lo strumento di stress e prestazioni di Skype for Business Server 2015 (LyncPerfTool), la topologia di Skype for Business Server 2015 deve prima essere configurata per gli scenari rilevanti.</span><span class="sxs-lookup"><span data-stu-id="8ae98-105">To run the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool), the Skype for Business Server 2015 topology must first be configured for scenarios relevant to you.</span></span> <span data-ttu-id="8ae98-106">Se Skype for Business Server 2015 non è configurato o è configurato in modo errato, è probabile che la simulazione di caricamento non riesca.</span><span class="sxs-lookup"><span data-stu-id="8ae98-106">If Skype for Business Server 2015 isn't configured, or is configured incorrectly, your load simulation is very likely to fail.</span></span> <span data-ttu-id="8ae98-107">Con lo strumento di stress e prestazioni di Skype for Business Server 2015, stiamo fornendo gli script di Skype for Business Server Management Shell di esempio e i file di risorse di base come parte del [download dello strumento](https://www.microsoft.com/download/details.aspx?id=50367).</span><span class="sxs-lookup"><span data-stu-id="8ae98-107">With the Skype for Business Server 2015 Stress and Performance Tool, we're providing example Skype for Business Server Management Shell scripts and basic resource files as part of the [tool download](https://www.microsoft.com/download/details.aspx?id=50367).</span></span> <span data-ttu-id="8ae98-108">Questi possono essere usati come punto di partenza per configurare la distribuzione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8ae98-108">These can be used as a starting point for configuring your Skype for Business Server deployment.</span></span> <span data-ttu-id="8ae98-109">In questo articolo vengono illustrati gli esempi di Windows PowerShell forniti.</span><span class="sxs-lookup"><span data-stu-id="8ae98-109">This article describes the Windows PowerShell examples provided.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8ae98-110">Questo argomento non ti aiuterà a descrivere come configurare Skype for Business Server 2015 in generale, abbiamo altri argomenti per la pianificazione e la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8ae98-110">This topic won't help you describe how to configure Skype for Business Server 2015 generally, we have other Planning and Deployment topics for that.</span></span> <span data-ttu-id="8ae98-111">Per informazioni dettagliate sull'uso di Windows PowerShell in Skype for Business Server 2015, vedere la documentazione di Skype for Business Server Management Shell in Inserisci introduzione qui.</span><span class="sxs-lookup"><span data-stu-id="8ae98-111">For details about working with Windows PowerShell in Skype for Business Server 2015, see the Skype for Business Server Management Shell documentation at Insert introduction HERE.</span></span> 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a><span data-ttu-id="8ae98-112">Informazioni sull'uso degli script di Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="8ae98-112">About running Skype for Business Server management shell scripts</span></span>

<span data-ttu-id="8ae98-113">Stiamo fornendo script di PowerShell di esempio che puoi usare per preparare le simulazioni di caricamento.</span><span class="sxs-lookup"><span data-stu-id="8ae98-113">We're providing sample PowerShell scripts you can use to prepare for your load simulations.</span></span> <span data-ttu-id="8ae98-114">Dato che questi script sono destinati alla simulazione del carico, li troverai semplici e permissivi.</span><span class="sxs-lookup"><span data-stu-id="8ae98-114">Because these scripts are intended for load simulation, you'll find them to be simple and permissive.</span></span> <span data-ttu-id="8ae98-115">Potrebbe non essere appropriato per l'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="8ae98-115">That may not be appropriate for your production environment.</span></span> <span data-ttu-id="8ae98-116">Ancora una volta sottolineiamo che questi script sono esempi, è necessario rivederli e in molti casi apportare modifiche rilevanti per l'ambiente prima di poterlo usare in modo pratico.</span><span class="sxs-lookup"><span data-stu-id="8ae98-116">Again we stress that these scripts are samples, you'll need to review them and in many cases make changes relevant to your environment before being able to make practical use of them.</span></span> <span data-ttu-id="8ae98-117">Come minimo, ci aspettiamo che tu debba modificare lo script RSG (Response Service Group) con la topologia in mente (per specificare gli agenti assegnati ai gruppi di agenti).</span><span class="sxs-lookup"><span data-stu-id="8ae98-117">At a minimum, we'd expect you'd need to modify the Response Service Group (RSG) script with your topology in mind (to specify the agents assigned to the agent groups).</span></span> <span data-ttu-id="8ae98-118">Ma non devi eseguire questa funzione, se non è necessario.</span><span class="sxs-lookup"><span data-stu-id="8ae98-118">But you don't have to run that, if you don't need to.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="8ae98-119">Prestare particolare attenzione a rivedere e comprendere questi esempi.</span><span class="sxs-lookup"><span data-stu-id="8ae98-119">Please take care in reviewing and understanding these samples.</span></span> <span data-ttu-id="8ae98-120">Gli script sovrascriveranno le impostazioni esistenti nella topologia quando verranno eseguite.</span><span class="sxs-lookup"><span data-stu-id="8ae98-120">Scripts will overwrite any existing settings in the topology when run.</span></span> 
  
## <a name="stress-and-performance-tool-client-version-names"></a><span data-ttu-id="8ae98-121">Nomi di versione client dello strumento stress e prestazioni</span><span class="sxs-lookup"><span data-stu-id="8ae98-121">Stress and Performance Tool client version names</span></span>

<span data-ttu-id="8ae98-122">Potrebbe essere necessario configurare i criteri di controllo della versione client se in precedenza sono state modificate le impostazioni dei valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="8ae98-122">You might need to configure the Client Version Check policy if you've previously changed the settings from the default values.</span></span> <span data-ttu-id="8ae98-123">In caso di dubbi, verificare la [documentazione relativa alla verifica della versione client](https://msdn.microsoft.com/en-us/vsto/jj923060).</span><span class="sxs-lookup"><span data-stu-id="8ae98-123">If you're unsure about this, check the [Client Version Check documentation](https://msdn.microsoft.com/en-us/vsto/jj923060).</span></span>
  
<span data-ttu-id="8ae98-124">Lo strumento sollecitazione e prestazioni usa le versioni seguenti dell'agente utente per impostazione predefinita durante la comunicazione con Skype for Business Server 2015:</span><span class="sxs-lookup"><span data-stu-id="8ae98-124">The Stress and Performance Tool uses the following User Agent versions by default when communicating with Skype for Business Server 2015:</span></span>
  
- <span data-ttu-id="8ae98-125">LSPT/15.0.0.0 (strumento di stress e prestazioni di Skype for Business Server 2015)</span><span class="sxs-lookup"><span data-stu-id="8ae98-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span></span>
    
- <span data-ttu-id="8ae98-126">OCPHONE/.0.522</span><span class="sxs-lookup"><span data-stu-id="8ae98-126">OCPHONE/.0.522</span></span>
    
<span data-ttu-id="8ae98-127">Per il client Mobility (UCWA) in LyncPerfTool:</span><span class="sxs-lookup"><span data-stu-id="8ae98-127">For the Mobility (UCWA) client in LyncPerfTool:</span></span>
  
- <span data-ttu-id="8ae98-128">Strumento Perf UCWA/conferenza Web</span><span class="sxs-lookup"><span data-stu-id="8ae98-128">UCWA Perf Tool/Web Conference</span></span>
    
- <span data-ttu-id="8ae98-129">Strumento Perf UCWA/mobile</span><span class="sxs-lookup"><span data-stu-id="8ae98-129">UCWA Perf Tool/Mobile</span></span>
    


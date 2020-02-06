---
title: Strumento di stress e prestazioni di Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 4/6/2016
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: Lo strumento di stress e prestazioni di Skype for Business Server 2015 viene usato durante la pianificazione della capacità e l'ottimizzazione delle prestazioni in ambienti non di produzione o di test.
ms.openlocfilehash: efc3ed6cc7f24acc5fda7a7ae2ae818df5b43393
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816155"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="e91f5-103">Strumento di stress e prestazioni di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e91f5-103">Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="e91f5-104">Lo strumento di stress e prestazioni di Skype for Business Server 2015 viene usato durante la pianificazione della capacità e l'ottimizzazione delle prestazioni in ambienti non di produzione o di test.</span><span class="sxs-lookup"><span data-stu-id="e91f5-104">The Skype for Business Server 2015 Stress and Performance Tool is used during capacity planning and performance tuning in non-production or test environments.</span></span>
  
<span data-ttu-id="e91f5-105">Lo strumento di stress e prestazioni di Skype for Business Server 2015 include strumenti che faciliteranno la pianificazione della capacità per Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e91f5-105">The Skype for Business Server 2015 Stress and Performance Tool includes tools that will simplify your capacity planning for Skype for Business Server 2015.</span></span> <span data-ttu-id="e91f5-106">Lo strumento di stress e prestazioni di Skype for Business Server 2015 ti aiuterà a:</span><span class="sxs-lookup"><span data-stu-id="e91f5-106">The Skype for Business Server 2015 Stress and Performance Tool will help you to:</span></span>
  
- <span data-ttu-id="e91f5-107">Semplificare la pianificazione hardware per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e91f5-107">Simplify your hardware planning for Skype for Business Server</span></span>
    
- <span data-ttu-id="e91f5-108">Offrire maggiori informazioni e procedure consigliate per l'ottimizzazione delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="e91f5-108">Give you increased knowledge and best practices for performance tuning</span></span>
    
- <span data-ttu-id="e91f5-109">Misurare le prestazioni delle distribuzioni di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e91f5-109">Measure the performance of your Skype for Business Server deployments</span></span>
    
<span data-ttu-id="e91f5-110">In genere si usa questo strumento dopo aver usato lo [strumento di pianificazione di Skype for Business server 2015](../../management-tools/planning-tool/planning-tool.md) per progettare la topologia e perfezionare la topologia con il [calcolatore di pianificazione della capacità di Skype for Business Server 2015](../../management-tools/capacity-planning-calculator.md).</span><span class="sxs-lookup"><span data-stu-id="e91f5-110">You would typically use this tool after you use the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md) to design the topology, and refining the topology with the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="e91f5-111">Questo strumento non verrà aggiornato per Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e91f5-111">This tool will not be updated for Skype for Business Server 2019.</span></span>
  
## <a name="tests"></a><span data-ttu-id="e91f5-112">Test</span><span class="sxs-lookup"><span data-stu-id="e91f5-112">Tests</span></span>

<span data-ttu-id="e91f5-113">Lo strumento di stress e prestazioni può simulare questi tipi di caricamento degli utenti:</span><span class="sxs-lookup"><span data-stu-id="e91f5-113">The Stress and Performance Tool can simulate these types of user load:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e91f5-114">Messaggistica istantanea (IM) e presenza</span><span class="sxs-lookup"><span data-stu-id="e91f5-114">Instant Messaging (IM) and presence</span></span>  <br/> |<span data-ttu-id="e91f5-115">Audioconferenza</span><span class="sxs-lookup"><span data-stu-id="e91f5-115">Audio conferencing</span></span>  <br/> |
|<span data-ttu-id="e91f5-116">Condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="e91f5-116">Application sharing</span></span>  <br/> |<span data-ttu-id="e91f5-117">Voice over IP (VoIP), inclusa la simulazione PTSN (Public Switched Telephone Network)</span><span class="sxs-lookup"><span data-stu-id="e91f5-117">Voice over IP (VoIP), including public switched telephone network (PTSN) simulation</span></span>  <br/> |
|<span data-ttu-id="e91f5-118">Servizi di conferenza client di Web Access</span><span class="sxs-lookup"><span data-stu-id="e91f5-118">Web Access Client conferencing</span></span>  <br/> |<span data-ttu-id="e91f5-119">Operatore automatico conferenza</span><span class="sxs-lookup"><span data-stu-id="e91f5-119">Conference auto attendant</span></span>  <br/> |
|<span data-ttu-id="e91f5-120">Response Group</span><span class="sxs-lookup"><span data-stu-id="e91f5-120">Response Groups</span></span>  <br/> |<span data-ttu-id="e91f5-121">Espansione della lista di distribuzione</span><span class="sxs-lookup"><span data-stu-id="e91f5-121">Distribution list expansion</span></span>  <br/> |
|<span data-ttu-id="e91f5-122">Query di download e Rubrica per la Rubrica</span><span class="sxs-lookup"><span data-stu-id="e91f5-122">Address book download and address book query</span></span>  <br/> |<span data-ttu-id="e91f5-123">Chiamate avanzate di 911 (E911) e profilo posizione (dial plan)</span><span class="sxs-lookup"><span data-stu-id="e91f5-123">Enhanced 911 (E911) calls and location profile (dial plan)</span></span>  <br/> |
|<span data-ttu-id="e91f5-124">MultiView</span><span class="sxs-lookup"><span data-stu-id="e91f5-124">MultiView</span></span>  <br/> |<span data-ttu-id="e91f5-125">Collaborazione dati</span><span class="sxs-lookup"><span data-stu-id="e91f5-125">Data collaboration</span></span>  <br/> |
|<span data-ttu-id="e91f5-126">Mobilità</span><span class="sxs-lookup"><span data-stu-id="e91f5-126">Mobility</span></span>  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="e91f5-127">Applicazioni e file inclusi nello strumento per lo stress e le prestazioni di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e91f5-127">Applications and files included with the Skype for Business Server 2015 Stress and Performance Tool</span></span>

<span data-ttu-id="e91f5-128">Queste applicazioni fanno parte dello strumento di stress e prestazioni di Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="e91f5-128">These applications are a part of the Skype for Business Server Stress and Performance Tool:</span></span>
  
|<span data-ttu-id="e91f5-129">**Strumento**</span><span class="sxs-lookup"><span data-stu-id="e91f5-129">**Tool**</span></span>|<span data-ttu-id="e91f5-130">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="e91f5-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e91f5-131">UserProvisioningTool. exe</span><span class="sxs-lookup"><span data-stu-id="e91f5-131">UserProvisioningTool.exe</span></span>  <br/> |<span data-ttu-id="e91f5-132">Questo strumento viene usato per creare utenti e contatti.</span><span class="sxs-lookup"><span data-stu-id="e91f5-132">This tool is used to create users and contacts.</span></span>  <br/> |
|<span data-ttu-id="e91f5-133">UserProfileGenerator. exe</span><span class="sxs-lookup"><span data-stu-id="e91f5-133">UserProfileGenerator.exe</span></span>  <br/> |<span data-ttu-id="e91f5-134">Consente di configurare le caratteristiche del carico utente che si sta simulando.</span><span class="sxs-lookup"><span data-stu-id="e91f5-134">Used to configure the characteristics of the user load you're simulating.</span></span>  <br/> |
|<span data-ttu-id="e91f5-135">LyncPerfTool. exe</span><span class="sxs-lookup"><span data-stu-id="e91f5-135">LyncPerfTool.exe</span></span>  <br/> |<span data-ttu-id="e91f5-136">Strumento che simula il caricamento dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e91f5-136">The tool that simulates user load.</span></span>  <br/> |
|<span data-ttu-id="e91f5-137">Default. TMX</span><span class="sxs-lookup"><span data-stu-id="e91f5-137">Default.tmx</span></span>  <br/> |<span data-ttu-id="e91f5-138">Necessario per usare lo strumento di registrazione di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e91f5-138">Required to use the Skype for Business Server 2015 Logging Tool.</span></span>  <br/> |
|<span data-ttu-id="e91f5-139">Esempi di script di provisioning</span><span class="sxs-lookup"><span data-stu-id="e91f5-139">Provisioning script examples</span></span>  <br/> |<span data-ttu-id="e91f5-140">Consente di configurare la topologia per l'utilizzo di test di carico, in base a scenari specifici.</span><span class="sxs-lookup"><span data-stu-id="e91f5-140">Used to configure the topology for running load tests, based on specific scenarios.</span></span> <span data-ttu-id="e91f5-141">È probabile che sia necessario modificarle per renderle rilevanti per l'ambiente specifico.</span><span class="sxs-lookup"><span data-stu-id="e91f5-141">You'll likely need to modify them to make them relevant for your particular environment.</span></span>  <br/> |
   
## <a name="topics-in-this-section"></a><span data-ttu-id="e91f5-142">Argomenti in questa sezione</span><span class="sxs-lookup"><span data-stu-id="e91f5-142">Topics in this section</span></span>

<span data-ttu-id="e91f5-143">Per altre informazioni, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="e91f5-143">You should review the following articles if you need to know more:</span></span>
  
- [<span data-ttu-id="e91f5-144">Prerequisiti e configurazione per lo strumento di stress e prestazioni di Skype for busines</span><span class="sxs-lookup"><span data-stu-id="e91f5-144">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>](prerequisites-and-setup.md)
    
- [<span data-ttu-id="e91f5-145">Scenari di prestazioni per lo strumento di stress e prestazioni di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e91f5-145">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](scenarios.md)
    
  - [<span data-ttu-id="e91f5-146">Provisioning della topologia per l'esecuzione del caricamento in scenari di stress e prestazioni</span><span class="sxs-lookup"><span data-stu-id="e91f5-146">Provisioning the topology to run load in Stress and Performance scenarios</span></span>](provisioning-the-topology-to-run-load.md)
    
  - [<span data-ttu-id="e91f5-147">Configurazione dei criteri per lo strumento di stress e prestazioni di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e91f5-147">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](configuring-policies.md)
    
- [<span data-ttu-id="e91f5-148">Uso dello strumento di stress e prestazioni di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e91f5-148">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>](using-the-tool.md)
    
- [<span data-ttu-id="e91f5-149">Domande frequenti per lo strumento di stress e prestazioni di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e91f5-149">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](faq.md)
    


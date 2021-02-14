---
title: Skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Lo strumento Skype for Business Server 2015 Stress and Performance viene utilizzato durante la pianificazione della capacità e l'ottimizzazione delle prestazioni in ambienti non di produzione o di test.
ms.openlocfilehash: 551e4e5f985fc18439a4f277685034e86c7cdfb6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814926"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="7949c-103">Skype for Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="7949c-103">Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="7949c-104">Lo strumento Skype for Business Server 2015 Stress and Performance viene utilizzato durante la pianificazione della capacità e l'ottimizzazione delle prestazioni in ambienti non di produzione o di test.</span><span class="sxs-lookup"><span data-stu-id="7949c-104">The Skype for Business Server 2015 Stress and Performance Tool is used during capacity planning and performance tuning in non-production or test environments.</span></span>
  
<span data-ttu-id="7949c-105">Lo strumento Skype for Business Server 2015 Stress and Performance include strumenti che semplificano la pianificazione della capacità per Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7949c-105">The Skype for Business Server 2015 Stress and Performance Tool includes tools that will simplify your capacity planning for Skype for Business Server 2015.</span></span> <span data-ttu-id="7949c-106">Lo strumento Skype for Business Server 2015 Stress and Performance consente di:</span><span class="sxs-lookup"><span data-stu-id="7949c-106">The Skype for Business Server 2015 Stress and Performance Tool will help you to:</span></span>
  
- <span data-ttu-id="7949c-107">Semplificare la pianificazione dell'hardware per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7949c-107">Simplify your hardware planning for Skype for Business Server</span></span>
    
- <span data-ttu-id="7949c-108">Offrire maggiori conoscenze e procedure consigliate per l'ottimizzazione delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="7949c-108">Give you increased knowledge and best practices for performance tuning</span></span>
    
- <span data-ttu-id="7949c-109">Misurare le prestazioni delle distribuzioni di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7949c-109">Measure the performance of your Skype for Business Server deployments</span></span>
    
<span data-ttu-id="7949c-110">Questo strumento viene in genere utilizzato dopo aver utilizzato lo strumento di pianificazione di [Skype for Business Server 2015](../../management-tools/planning-tool/planning-tool.md) per progettare la topologia e perfezionando la topologia con lo strumento di calcolo della pianificazione della capacità di Skype for Business Server [2015.](../../management-tools/capacity-planning-calculator.md)</span><span class="sxs-lookup"><span data-stu-id="7949c-110">You would typically use this tool after you use the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md) to design the topology, and refining the topology with the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="7949c-111">Questo strumento non verrà aggiornato per Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7949c-111">This tool will not be updated for Skype for Business Server 2019.</span></span>
  
## <a name="tests"></a><span data-ttu-id="7949c-112">Test</span><span class="sxs-lookup"><span data-stu-id="7949c-112">Tests</span></span>

<span data-ttu-id="7949c-113">Lo strumento Stress and Performance può simulare questi tipi di carico utente:</span><span class="sxs-lookup"><span data-stu-id="7949c-113">The Stress and Performance Tool can simulate these types of user load:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="7949c-114">Messaggistica istantanea e presenza</span><span class="sxs-lookup"><span data-stu-id="7949c-114">Instant Messaging (IM) and presence</span></span>  <br/> |<span data-ttu-id="7949c-115">Audioconferenza</span><span class="sxs-lookup"><span data-stu-id="7949c-115">Audio conferencing</span></span>  <br/> |
|<span data-ttu-id="7949c-116">Condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="7949c-116">Application sharing</span></span>  <br/> |<span data-ttu-id="7949c-117">Voice over IP (VoIP), inclusa la simulazione PTSN (Public Switched Telephone Network)</span><span class="sxs-lookup"><span data-stu-id="7949c-117">Voice over IP (VoIP), including public switched telephone network (PTSN) simulation</span></span>  <br/> |
|<span data-ttu-id="7949c-118">Web Access Client Conferencing</span><span class="sxs-lookup"><span data-stu-id="7949c-118">Web Access Client conferencing</span></span>  <br/> |<span data-ttu-id="7949c-119">Operatore automatico conferenza</span><span class="sxs-lookup"><span data-stu-id="7949c-119">Conference auto attendant</span></span>  <br/> |
|<span data-ttu-id="7949c-120">Response Group</span><span class="sxs-lookup"><span data-stu-id="7949c-120">Response Groups</span></span>  <br/> |<span data-ttu-id="7949c-121">Espansione delle liste di distribuzione</span><span class="sxs-lookup"><span data-stu-id="7949c-121">Distribution list expansion</span></span>  <br/> |
|<span data-ttu-id="7949c-122">Query per il download e la rubrica della rubrica</span><span class="sxs-lookup"><span data-stu-id="7949c-122">Address book download and address book query</span></span>  <br/> |<span data-ttu-id="7949c-123">Chiamate enhanced 911 (E911) e profilo località (dial plan)</span><span class="sxs-lookup"><span data-stu-id="7949c-123">Enhanced 911 (E911) calls and location profile (dial plan)</span></span>  <br/> |
|<span data-ttu-id="7949c-124">MultiView</span><span class="sxs-lookup"><span data-stu-id="7949c-124">MultiView</span></span>  <br/> |<span data-ttu-id="7949c-125">Collaborazione dati</span><span class="sxs-lookup"><span data-stu-id="7949c-125">Data collaboration</span></span>  <br/> |
|<span data-ttu-id="7949c-126">Mobilità</span><span class="sxs-lookup"><span data-stu-id="7949c-126">Mobility</span></span>  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="7949c-127">Applicazioni e file inclusi in Skype for Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="7949c-127">Applications and files included with the Skype for Business Server 2015 Stress and Performance Tool</span></span>

<span data-ttu-id="7949c-128">Queste applicazioni fanno parte dello strumento Skype for Business Server Stress and Performance:</span><span class="sxs-lookup"><span data-stu-id="7949c-128">These applications are a part of the Skype for Business Server Stress and Performance Tool:</span></span>
  
|<span data-ttu-id="7949c-129">**Strumento**</span><span class="sxs-lookup"><span data-stu-id="7949c-129">**Tool**</span></span>|<span data-ttu-id="7949c-130">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="7949c-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7949c-131">UserProvisioningTool.exe</span><span class="sxs-lookup"><span data-stu-id="7949c-131">UserProvisioningTool.exe</span></span>  <br/> |<span data-ttu-id="7949c-132">Questo strumento viene utilizzato per creare utenti e contatti.</span><span class="sxs-lookup"><span data-stu-id="7949c-132">This tool is used to create users and contacts.</span></span>  <br/> |
|<span data-ttu-id="7949c-133">UserProfileGenerator.exe</span><span class="sxs-lookup"><span data-stu-id="7949c-133">UserProfileGenerator.exe</span></span>  <br/> |<span data-ttu-id="7949c-134">Usato per configurare le caratteristiche del carico utente che si sta simulando.</span><span class="sxs-lookup"><span data-stu-id="7949c-134">Used to configure the characteristics of the user load you're simulating.</span></span>  <br/> |
|<span data-ttu-id="7949c-135">LyncPerfTool.exe</span><span class="sxs-lookup"><span data-stu-id="7949c-135">LyncPerfTool.exe</span></span>  <br/> |<span data-ttu-id="7949c-136">Strumento che simula il carico utente.</span><span class="sxs-lookup"><span data-stu-id="7949c-136">The tool that simulates user load.</span></span>  <br/> |
|<span data-ttu-id="7949c-137">Default.tmx</span><span class="sxs-lookup"><span data-stu-id="7949c-137">Default.tmx</span></span>  <br/> |<span data-ttu-id="7949c-138">Necessario per usare lo strumento di registrazione di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7949c-138">Required to use the Skype for Business Server 2015 Logging Tool.</span></span>  <br/> |
|<span data-ttu-id="7949c-139">Esempi di script di provisioning</span><span class="sxs-lookup"><span data-stu-id="7949c-139">Provisioning script examples</span></span>  <br/> |<span data-ttu-id="7949c-140">Utilizzato per configurare la topologia per l'esecuzione di test di carico, in base a scenari specifici.</span><span class="sxs-lookup"><span data-stu-id="7949c-140">Used to configure the topology for running load tests, based on specific scenarios.</span></span> <span data-ttu-id="7949c-141">È probabile che sia necessario modificarli per renderli rilevanti per il proprio ambiente specifico.</span><span class="sxs-lookup"><span data-stu-id="7949c-141">You'll likely need to modify them to make them relevant for your particular environment.</span></span>  <br/> |
   
## <a name="topics-in-this-section"></a><span data-ttu-id="7949c-142">Argomenti di questa sezione</span><span class="sxs-lookup"><span data-stu-id="7949c-142">Topics in this section</span></span>

<span data-ttu-id="7949c-143">Per saperne di più, consultare gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="7949c-143">You should review the following articles if you need to know more:</span></span>
  
- [<span data-ttu-id="7949c-144">Prerequisiti e configurazione dello strumento Skype for Busines Stress and Performance</span><span class="sxs-lookup"><span data-stu-id="7949c-144">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>](prerequisites-and-setup.md)
    
- [<span data-ttu-id="7949c-145">Scenari di prestazioni per lo strumento Skype for Business Server 2015 Stress and Performance</span><span class="sxs-lookup"><span data-stu-id="7949c-145">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](scenarios.md)
    
  - [<span data-ttu-id="7949c-146">Provisioning della topologia per l'esecuzione del carico in scenari di stress e prestazioni</span><span class="sxs-lookup"><span data-stu-id="7949c-146">Provisioning the topology to run load in Stress and Performance scenarios</span></span>](provisioning-the-topology-to-run-load.md)
    
  - [<span data-ttu-id="7949c-147">Configurazione dei criteri per lo strumento Skype for Business Server 2015 Stress and Performance</span><span class="sxs-lookup"><span data-stu-id="7949c-147">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](configuring-policies.md)
    
- [<span data-ttu-id="7949c-148">Uso dello strumento Skype for Business Server 2015 Stress and Performance</span><span class="sxs-lookup"><span data-stu-id="7949c-148">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>](using-the-tool.md)
    
- [<span data-ttu-id="7949c-149">Domande frequenti su Skype for Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="7949c-149">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](faq.md)
    


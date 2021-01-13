---
title: Strumento per lo stress e le prestazioni di Skype for Business Server 2015
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
description: Lo strumento di gestione dello stress e delle prestazioni di Skype for Business Server 2015 viene utilizzato durante la pianificazione della capacità e l'ottimizzazione delle prestazioni in ambienti non di produzione o di testing.
ms.openlocfilehash: 551e4e5f985fc18439a4f277685034e86c7cdfb6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814926"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="dacac-103">Strumento per lo stress e le prestazioni di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="dacac-103">Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="dacac-104">Lo strumento di gestione dello stress e delle prestazioni di Skype for Business Server 2015 viene utilizzato durante la pianificazione della capacità e l'ottimizzazione delle prestazioni in ambienti non di produzione o di testing.</span><span class="sxs-lookup"><span data-stu-id="dacac-104">The Skype for Business Server 2015 Stress and Performance Tool is used during capacity planning and performance tuning in non-production or test environments.</span></span>
  
<span data-ttu-id="dacac-105">Lo strumento per lo stress e le prestazioni di Skype for Business Server 2015 include strumenti che semplificano la pianificazione della capacità per Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="dacac-105">The Skype for Business Server 2015 Stress and Performance Tool includes tools that will simplify your capacity planning for Skype for Business Server 2015.</span></span> <span data-ttu-id="dacac-106">Lo strumento di supporto per la sollecitazione e le prestazioni di Skype for Business Server 2015 consente di:</span><span class="sxs-lookup"><span data-stu-id="dacac-106">The Skype for Business Server 2015 Stress and Performance Tool will help you to:</span></span>
  
- <span data-ttu-id="dacac-107">Semplificare la pianificazione dell'hardware per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dacac-107">Simplify your hardware planning for Skype for Business Server</span></span>
    
- <span data-ttu-id="dacac-108">Offrire maggiori informazioni e procedure consigliate per l'ottimizzazione delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="dacac-108">Give you increased knowledge and best practices for performance tuning</span></span>
    
- <span data-ttu-id="dacac-109">Misurare le prestazioni delle distribuzioni di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dacac-109">Measure the performance of your Skype for Business Server deployments</span></span>
    
<span data-ttu-id="dacac-110">Questo strumento viene in genere utilizzato dopo aver utilizzato lo [strumento di pianificazione di Skype for Business server 2015](../../management-tools/planning-tool/planning-tool.md) per progettare la topologia e perfezionare la topologia con il [calcolatore di pianificazione della capacità di Skype for Business Server 2015](../../management-tools/capacity-planning-calculator.md).</span><span class="sxs-lookup"><span data-stu-id="dacac-110">You would typically use this tool after you use the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md) to design the topology, and refining the topology with the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="dacac-111">Questo strumento non verrà aggiornato per Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="dacac-111">This tool will not be updated for Skype for Business Server 2019.</span></span>
  
## <a name="tests"></a><span data-ttu-id="dacac-112">Test</span><span class="sxs-lookup"><span data-stu-id="dacac-112">Tests</span></span>

<span data-ttu-id="dacac-113">Lo strumento stress and performance è in grado di simulare questi tipi di carico utente:</span><span class="sxs-lookup"><span data-stu-id="dacac-113">The Stress and Performance Tool can simulate these types of user load:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="dacac-114">Messaggistica istantanea (IM) e presenza</span><span class="sxs-lookup"><span data-stu-id="dacac-114">Instant Messaging (IM) and presence</span></span>  <br/> |<span data-ttu-id="dacac-115">Audioconferenza</span><span class="sxs-lookup"><span data-stu-id="dacac-115">Audio conferencing</span></span>  <br/> |
|<span data-ttu-id="dacac-116">Condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="dacac-116">Application sharing</span></span>  <br/> |<span data-ttu-id="dacac-117">VoIP (Voice over IP), inclusa la simulazione PTSN (Public Switched Telephone Network)</span><span class="sxs-lookup"><span data-stu-id="dacac-117">Voice over IP (VoIP), including public switched telephone network (PTSN) simulation</span></span>  <br/> |
|<span data-ttu-id="dacac-118">Servizi di conferenza client di accesso Web</span><span class="sxs-lookup"><span data-stu-id="dacac-118">Web Access Client conferencing</span></span>  <br/> |<span data-ttu-id="dacac-119">Operatore automatico conferenza</span><span class="sxs-lookup"><span data-stu-id="dacac-119">Conference auto attendant</span></span>  <br/> |
|<span data-ttu-id="dacac-120">Response Group</span><span class="sxs-lookup"><span data-stu-id="dacac-120">Response Groups</span></span>  <br/> |<span data-ttu-id="dacac-121">Espansione della lista di distribuzione</span><span class="sxs-lookup"><span data-stu-id="dacac-121">Distribution list expansion</span></span>  <br/> |
|<span data-ttu-id="dacac-122">Download della Rubrica e query della Rubrica</span><span class="sxs-lookup"><span data-stu-id="dacac-122">Address book download and address book query</span></span>  <br/> |<span data-ttu-id="dacac-123">Chiamate e profili delle posizioni migliorati di 911 (E911) (dial plan)</span><span class="sxs-lookup"><span data-stu-id="dacac-123">Enhanced 911 (E911) calls and location profile (dial plan)</span></span>  <br/> |
|<span data-ttu-id="dacac-124">MultiView</span><span class="sxs-lookup"><span data-stu-id="dacac-124">MultiView</span></span>  <br/> |<span data-ttu-id="dacac-125">Collaborazione dati</span><span class="sxs-lookup"><span data-stu-id="dacac-125">Data collaboration</span></span>  <br/> |
|<span data-ttu-id="dacac-126">Mobilità</span><span class="sxs-lookup"><span data-stu-id="dacac-126">Mobility</span></span>  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="dacac-127">Applicazioni e file forniti con lo strumento di stress e prestazioni di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="dacac-127">Applications and files included with the Skype for Business Server 2015 Stress and Performance Tool</span></span>

<span data-ttu-id="dacac-128">Queste applicazioni fanno parte dello strumento per lo stress e le prestazioni di Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="dacac-128">These applications are a part of the Skype for Business Server Stress and Performance Tool:</span></span>
  
|<span data-ttu-id="dacac-129">**Strumento**</span><span class="sxs-lookup"><span data-stu-id="dacac-129">**Tool**</span></span>|<span data-ttu-id="dacac-130">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="dacac-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dacac-131">UserProvisioningTool.exe</span><span class="sxs-lookup"><span data-stu-id="dacac-131">UserProvisioningTool.exe</span></span>  <br/> |<span data-ttu-id="dacac-132">Questo strumento viene utilizzato per creare utenti e contatti.</span><span class="sxs-lookup"><span data-stu-id="dacac-132">This tool is used to create users and contacts.</span></span>  <br/> |
|<span data-ttu-id="dacac-133">UserProfileGenerator.exe</span><span class="sxs-lookup"><span data-stu-id="dacac-133">UserProfileGenerator.exe</span></span>  <br/> |<span data-ttu-id="dacac-134">Utilizzato per configurare le caratteristiche del carico utente che si sta simulando.</span><span class="sxs-lookup"><span data-stu-id="dacac-134">Used to configure the characteristics of the user load you're simulating.</span></span>  <br/> |
|<span data-ttu-id="dacac-135">LyncPerfTool.exe</span><span class="sxs-lookup"><span data-stu-id="dacac-135">LyncPerfTool.exe</span></span>  <br/> |<span data-ttu-id="dacac-136">Strumento che simula il caricamento dell'utente.</span><span class="sxs-lookup"><span data-stu-id="dacac-136">The tool that simulates user load.</span></span>  <br/> |
|<span data-ttu-id="dacac-137">Default. TMX</span><span class="sxs-lookup"><span data-stu-id="dacac-137">Default.tmx</span></span>  <br/> |<span data-ttu-id="dacac-138">Necessario per utilizzare lo strumento di registrazione di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="dacac-138">Required to use the Skype for Business Server 2015 Logging Tool.</span></span>  <br/> |
|<span data-ttu-id="dacac-139">Esempi di script di provisioning</span><span class="sxs-lookup"><span data-stu-id="dacac-139">Provisioning script examples</span></span>  <br/> |<span data-ttu-id="dacac-140">Utilizzato per configurare la topologia per l'esecuzione di test di carico, in base a scenari specifici.</span><span class="sxs-lookup"><span data-stu-id="dacac-140">Used to configure the topology for running load tests, based on specific scenarios.</span></span> <span data-ttu-id="dacac-141">È probabile che sia necessario modificarli per renderli rilevanti per l'ambiente specifico.</span><span class="sxs-lookup"><span data-stu-id="dacac-141">You'll likely need to modify them to make them relevant for your particular environment.</span></span>  <br/> |
   
## <a name="topics-in-this-section"></a><span data-ttu-id="dacac-142">Argomenti in questa sezione</span><span class="sxs-lookup"><span data-stu-id="dacac-142">Topics in this section</span></span>

<span data-ttu-id="dacac-143">Per ulteriori informazioni, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="dacac-143">You should review the following articles if you need to know more:</span></span>
  
- [<span data-ttu-id="dacac-144">Prerequisiti e configurazione per lo strumento di stress e prestazioni di Skype for busines</span><span class="sxs-lookup"><span data-stu-id="dacac-144">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>](prerequisites-and-setup.md)
    
- [<span data-ttu-id="dacac-145">Scenari di prestazioni per lo strumento di stress e prestazioni di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="dacac-145">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](scenarios.md)
    
  - [<span data-ttu-id="dacac-146">Provisioning della topologia per l'esecuzione del carico negli scenari di stress e prestazioni</span><span class="sxs-lookup"><span data-stu-id="dacac-146">Provisioning the topology to run load in Stress and Performance scenarios</span></span>](provisioning-the-topology-to-run-load.md)
    
  - [<span data-ttu-id="dacac-147">Configurazione dei criteri per lo strumento di stress e prestazioni di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="dacac-147">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](configuring-policies.md)
    
- [<span data-ttu-id="dacac-148">Utilizzo dello strumento di sollecito e prestazioni di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="dacac-148">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>](using-the-tool.md)
    
- [<span data-ttu-id="dacac-149">Domande frequenti sullo strumento di stress e prestazioni di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="dacac-149">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](faq.md)
    


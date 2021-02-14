---
title: Verificare la coesistenza del pool pilota con il pool legacy
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Processo per verificare la coesistenza del pool pilota con il pool legacy.
ms.openlocfilehash: e9fe944c03c88aad2ca2b40f0e995842363e7a85
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751658"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="004c4-103">Verificare la coesistenza del pool pilota con il pool legacy</span><span class="sxs-lookup"><span data-stu-id="004c4-103">Verify pilot pool coexistence with legacy pool</span></span>

 <span data-ttu-id="004c4-104">**In questo articolo**</span><span class="sxs-lookup"><span data-stu-id="004c4-104">**In this article**</span></span>
  
[<span data-ttu-id="004c4-105">Verificare che i servizi di Skype for Business Server 2019 siano stati avviati</span><span class="sxs-lookup"><span data-stu-id="004c4-105">Verify that Skype for Business Server 2019 services have started</span></span>](#sectionSection0)
  
[<span data-ttu-id="004c4-106">Aprire il Pannello di controllo di Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="004c4-106">Open the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection1)
  
[<span data-ttu-id="004c4-107">Non tentare di aprire la topologia nel Generatore di topologie legacy</span><span class="sxs-lookup"><span data-stu-id="004c4-107">Don't attempt to open the topology in the legacy Topology Builder</span></span>](#sectionSection2)
  
<span data-ttu-id="004c4-108">Dopo aver distribuito il pool pilota, è necessario verificare la coesistenza dei due pool utilizzando gli strumenti di amministrazione per visualizzare le informazioni dei pool.</span><span class="sxs-lookup"><span data-stu-id="004c4-108">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="004c4-109">Per i pool di Skype for Business Server 2019 e i pool legacy, è necessario utilizzare il Pannello di controllo di Skype for Business Server 2019 e gli strumenti di Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="004c4-109">For the Skype for Business Server 2019 pools and legacy pools, you must use the Skype for Business Server 2019 Control Panel and Topology Builder tools.</span></span> 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a><span data-ttu-id="004c4-110">Verificare che i servizi di Skype for Business Server 2019 siano stati avviati</span><span class="sxs-lookup"><span data-stu-id="004c4-110">Verify that Skype for Business Server 2019 services have started</span></span>
<span data-ttu-id="004c4-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="004c4-111"><a name="sectionSection0"> </a></span></span>

1. <span data-ttu-id="004c4-112">Dal Front End Server di Skype for Business Server 2019, accedere all'applet Strumenti di amministrazione\Servizi.</span><span class="sxs-lookup"><span data-stu-id="004c4-112">From the Skype for Business Server 2019 Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="004c4-113">Verificare che i servizi seguenti siano in esecuzione nel Front End Server:</span><span class="sxs-lookup"><span data-stu-id="004c4-113">Verify that the following services are running on the Front End Server:</span></span>

    - <span data-ttu-id="004c4-114">Agente del servizio di registrazione centralizzato</span><span class="sxs-lookup"><span data-stu-id="004c4-114">Centralized Logging Service Agent</span></span>
    - <span data-ttu-id="004c4-115">Condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="004c4-115">Application Sharing</span></span>
    - <span data-ttu-id="004c4-116">Servizio test audio</span><span class="sxs-lookup"><span data-stu-id="004c4-116">Audio Test Service</span></span>
    - <span data-ttu-id="004c4-117">Audio/videoconferenze</span><span class="sxs-lookup"><span data-stu-id="004c4-117">Audio/Video Conferencing</span></span>
    - <span data-ttu-id="004c4-118">Parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="004c4-118">Call Park</span></span>
    - <span data-ttu-id="004c4-119">Annuncio conferenza</span><span class="sxs-lookup"><span data-stu-id="004c4-119">Conferencing Announcement</span></span>
    - <span data-ttu-id="004c4-120">Operatore Conferenza</span><span class="sxs-lookup"><span data-stu-id="004c4-120">Conferencing Attendant</span></span>
    - <span data-ttu-id="004c4-121">Front-End</span><span class="sxs-lookup"><span data-stu-id="004c4-121">Front-End</span></span>
    - <span data-ttu-id="004c4-122">Servizi di conferenza di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="004c4-122">IM Conferencing</span></span>
    - <span data-ttu-id="004c4-123">Mediation</span><span class="sxs-lookup"><span data-stu-id="004c4-123">Mediation</span></span>
    - <span data-ttu-id="004c4-124">Agente Replicator</span><span class="sxs-lookup"><span data-stu-id="004c4-124">Replica Replicator Agent</span></span>
    - <span data-ttu-id="004c4-125">Response Group</span><span class="sxs-lookup"><span data-stu-id="004c4-125">Response Group</span></span>
    - <span data-ttu-id="004c4-126">Conferenze Web</span><span class="sxs-lookup"><span data-stu-id="004c4-126">Web Conferencing</span></span>
    - <span data-ttu-id="004c4-127">Gateway di conversione XMPP</span><span class="sxs-lookup"><span data-stu-id="004c4-127">XMPP Translating Gateway</span></span>

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="004c4-128">Aprire il Pannello di controllo di Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="004c4-128">Open the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="004c4-129"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="004c4-129"><a name="sectionSection1"> </a></span></span>

<span data-ttu-id="004c4-130">Dal Front End Server nella distribuzione di Skype for Business Server 2019, aprire il Pannello di controllo di Skype for Business Server 2019 e selezionare il pool legacy.</span><span class="sxs-lookup"><span data-stu-id="004c4-130">From the Front End Server in your Skype for Business Server 2019 deployment, open the Skype for Business Server 2019 Control Panel and select the legacy pool.</span></span> <span data-ttu-id="004c4-131">Ripetere la procedura per aprire il pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="004c4-131">Repeat the procedure to open the Skype for Business Server 2019 pool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="004c4-132">In Skype for Business Server 2019, è necessario aggiornare Silverlight a Silverlight versione 5 prima di usare il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="004c4-132">On Skype for Business Server 2019, you must upgrade Silverlight to Silverlight version 5 prior to using the Skype for Business Server Control Panel.</span></span> 
  
<span data-ttu-id="004c4-133">Questa topologia ora include i ruoli del server Legacy e Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="004c4-133">This topology now includes legacy and Skype for Business Server 2019 server roles.</span></span> 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a><span data-ttu-id="004c4-134">Non tentare di aprire la topologia nel Generatore di topologie legacy</span><span class="sxs-lookup"><span data-stu-id="004c4-134">Don't attempt to open the topology in the legacy Topology Builder</span></span>
<span data-ttu-id="004c4-135"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="004c4-135"><a name="sectionSection2"> </a></span></span>

<span data-ttu-id="004c4-136">La topologia può essere visualizzata solo tramite Generatore di topologie di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="004c4-136">The topology can only be viewed using Skype for Business Server 2019 Topology Builder.</span></span> <span data-ttu-id="004c4-137">Il Generatore di topologie di Skype for Business Server 2019 deve essere utilizzato per creare pool sia per Skype for Business Server 2019 che per l'installazione legacy.</span><span class="sxs-lookup"><span data-stu-id="004c4-137">The Skype for Business Server 2019 Topology Builder must be used to create pools for both Skype for Business Server 2019 and the legacy install.</span></span>

  


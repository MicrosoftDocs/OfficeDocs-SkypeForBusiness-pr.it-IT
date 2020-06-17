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
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="9dabe-103">Verificare la coesistenza del pool pilota con il pool legacy</span><span class="sxs-lookup"><span data-stu-id="9dabe-103">Verify pilot pool coexistence with legacy pool</span></span>

 <span data-ttu-id="9dabe-104">**In questo articolo**</span><span class="sxs-lookup"><span data-stu-id="9dabe-104">**In this article**</span></span>
  
[<span data-ttu-id="9dabe-105">Verificare che i servizi di Skype for Business Server 2019 siano stati avviati</span><span class="sxs-lookup"><span data-stu-id="9dabe-105">Verify that Skype for Business Server 2019 services have started</span></span>](#sectionSection0)
  
[<span data-ttu-id="9dabe-106">Aprire il pannello di controllo di Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="9dabe-106">Open the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection1)
  
[<span data-ttu-id="9dabe-107">Non tentare di aprire la topologia nel generatore di topologie legacy</span><span class="sxs-lookup"><span data-stu-id="9dabe-107">Don't attempt to open the topology in the legacy Topology Builder</span></span>](#sectionSection2)
  
<span data-ttu-id="9dabe-108">Dopo aver distribuito il pool pilota, è necessario verificare la coesistenza dei due pool utilizzando gli strumenti di amministrazione per visualizzare le informazioni dei pool.</span><span class="sxs-lookup"><span data-stu-id="9dabe-108">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="9dabe-109">Per i pool e i pool legacy di Skype for Business Server 2019, è necessario utilizzare il pannello di controllo di Skype for Business Server 2019 e gli strumenti del generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="9dabe-109">For the Skype for Business Server 2019 pools and legacy pools, you must use the Skype for Business Server 2019 Control Panel and Topology Builder tools.</span></span> 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a><span data-ttu-id="9dabe-110">Verificare che i servizi di Skype for Business Server 2019 siano stati avviati</span><span class="sxs-lookup"><span data-stu-id="9dabe-110">Verify that Skype for Business Server 2019 services have started</span></span>
<span data-ttu-id="9dabe-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="9dabe-111"><a name="sectionSection0"> </a></span></span>

1. <span data-ttu-id="9dabe-112">Dal server front end di Skype for Business Server 2019 passare all'applet Amministrazione\servizi. amministrativa.</span><span class="sxs-lookup"><span data-stu-id="9dabe-112">From the Skype for Business Server 2019 Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="9dabe-113">Verificare che i servizi seguenti siano in esecuzione nel Front End Server:</span><span class="sxs-lookup"><span data-stu-id="9dabe-113">Verify that the following services are running on the Front End Server:</span></span>

    - <span data-ttu-id="9dabe-114">Agente del servizio di registrazione centralizzato</span><span class="sxs-lookup"><span data-stu-id="9dabe-114">Centralized Logging Service Agent</span></span>
    - <span data-ttu-id="9dabe-115">Condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="9dabe-115">Application Sharing</span></span>
    - <span data-ttu-id="9dabe-116">Servizio di test audio</span><span class="sxs-lookup"><span data-stu-id="9dabe-116">Audio Test Service</span></span>
    - <span data-ttu-id="9dabe-117">Audio/videoconferenze</span><span class="sxs-lookup"><span data-stu-id="9dabe-117">Audio/Video Conferencing</span></span>
    - <span data-ttu-id="9dabe-118">Parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="9dabe-118">Call Park</span></span>
    - <span data-ttu-id="9dabe-119">Annuncio per conferenze</span><span class="sxs-lookup"><span data-stu-id="9dabe-119">Conferencing Announcement</span></span>
    - <span data-ttu-id="9dabe-120">Operatore Conferenza</span><span class="sxs-lookup"><span data-stu-id="9dabe-120">Conferencing Attendant</span></span>
    - <span data-ttu-id="9dabe-121">Front-End</span><span class="sxs-lookup"><span data-stu-id="9dabe-121">Front-End</span></span>
    - <span data-ttu-id="9dabe-122">Conferenze di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="9dabe-122">IM Conferencing</span></span>
    - <span data-ttu-id="9dabe-123">Mediation</span><span class="sxs-lookup"><span data-stu-id="9dabe-123">Mediation</span></span>
    - <span data-ttu-id="9dabe-124">Agente Replicator replica</span><span class="sxs-lookup"><span data-stu-id="9dabe-124">Replica Replicator Agent</span></span>
    - <span data-ttu-id="9dabe-125">Response Group</span><span class="sxs-lookup"><span data-stu-id="9dabe-125">Response Group</span></span>
    - <span data-ttu-id="9dabe-126">Web Conferencing</span><span class="sxs-lookup"><span data-stu-id="9dabe-126">Web Conferencing</span></span>
    - <span data-ttu-id="9dabe-127">Gateway di traduzione XMPP</span><span class="sxs-lookup"><span data-stu-id="9dabe-127">XMPP Translating Gateway</span></span>

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="9dabe-128">Aprire il pannello di controllo di Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="9dabe-128">Open the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="9dabe-129"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="9dabe-129"><a name="sectionSection1"> </a></span></span>

<span data-ttu-id="9dabe-130">Dal front end server della distribuzione di Skype for Business Server 2019, aprire il pannello di controllo di Skype for Business Server 2019 e selezionare il pool legacy.</span><span class="sxs-lookup"><span data-stu-id="9dabe-130">From the Front End Server in your Skype for Business Server 2019 deployment, open the Skype for Business Server 2019 Control Panel and select the legacy pool.</span></span> <span data-ttu-id="9dabe-131">Ripetere la procedura per aprire il pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="9dabe-131">Repeat the procedure to open the Skype for Business Server 2019 pool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9dabe-132">In Skype for Business Server 2019, è necessario eseguire l'aggiornamento a Silverlight versione 5 prima di utilizzare il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9dabe-132">On Skype for Business Server 2019, you must upgrade Silverlight to Silverlight version 5 prior to using the Skype for Business Server Control Panel.</span></span> 
  
<span data-ttu-id="9dabe-133">Questa topologia ora include i ruoli del server legacy e Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="9dabe-133">This topology now includes legacy and Skype for Business Server 2019 server roles.</span></span> 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a><span data-ttu-id="9dabe-134">Non tentare di aprire la topologia nel generatore di topologie legacy</span><span class="sxs-lookup"><span data-stu-id="9dabe-134">Don't attempt to open the topology in the legacy Topology Builder</span></span>
<span data-ttu-id="9dabe-135"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="9dabe-135"><a name="sectionSection2"> </a></span></span>

<span data-ttu-id="9dabe-136">La topologia può essere visualizzata solo utilizzando il generatore di topologie di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="9dabe-136">The topology can only be viewed using Skype for Business Server 2019 Topology Builder.</span></span> <span data-ttu-id="9dabe-137">Il generatore di topologie di Skype for Business Server 2019 deve essere utilizzato per creare pool sia per Skype for Business Server 2019 che per l'installazione legacy.</span><span class="sxs-lookup"><span data-stu-id="9dabe-137">The Skype for Business Server 2019 Topology Builder must be used to create pools for both Skype for Business Server 2019 and the legacy install.</span></span>

  


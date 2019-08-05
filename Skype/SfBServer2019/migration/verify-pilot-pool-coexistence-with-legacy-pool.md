---
title: Verificare la coesistenza del pool pilota con il pool legacy
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Processo per verificare la coesistenza del pool pilota con il pool legacy.
ms.openlocfilehash: b41a1f24786fdf807f9c9c1d5854e397654fdadb
ms.sourcegitcommit: c554b09527817dc3e06b10509f6668b42ccc5cb9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/17/2019
ms.locfileid: "36196041"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="17c61-103">Verificare la coesistenza del pool pilota con il pool legacy</span><span class="sxs-lookup"><span data-stu-id="17c61-103">Verify pilot pool coexistence with legacy pool</span></span>

 <span data-ttu-id="17c61-104">**In questo articolo**</span><span class="sxs-lookup"><span data-stu-id="17c61-104">**In this article**</span></span>
  
[<span data-ttu-id="17c61-105">Verificare che i servizi di Skype for Business Server 2019 siano stati avviati</span><span class="sxs-lookup"><span data-stu-id="17c61-105">Verify that Skype for Business Server 2019 services have started</span></span>](#sectionSection0)
  
[<span data-ttu-id="17c61-106">Aprire il pannello di controllo di Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="17c61-106">Open the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection1)
  
[<span data-ttu-id="17c61-107">Non provare ad aprire la topologia nel generatore di topologia legacy</span><span class="sxs-lookup"><span data-stu-id="17c61-107">Don't attempt to open the topology in the legacy Topology Builder</span></span>](#sectionSection2)
  
<span data-ttu-id="17c61-108">Dopo la distribuzione del pool pilota, è necessario verificare la coesistenza dei due pool usando gli strumenti di amministrazione per visualizzare le informazioni sul pool.</span><span class="sxs-lookup"><span data-stu-id="17c61-108">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="17c61-109">Per i pool di 2019 e i pool legacy di Skype for Business Server, è necessario usare gli strumenti pannello di controllo e generatore di topologia di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="17c61-109">For the Skype for Business Server 2019 pools and legacy pools, you must use the Skype for Business Server 2019 Control Panel and Topology Builder tools.</span></span> 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a><span data-ttu-id="17c61-110">Verificare che i servizi di Skype for Business Server 2019 siano stati avviati</span><span class="sxs-lookup"><span data-stu-id="17c61-110">Verify that Skype for Business Server 2019 services have started</span></span>
<span data-ttu-id="17c61-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="17c61-111"></span></span>

1. <span data-ttu-id="17c61-112">Dal server front-end di Skype for Business Server 2019 passare all'applet Tools\Services amministrativa.</span><span class="sxs-lookup"><span data-stu-id="17c61-112">From the Skype for Business Server 2019 Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="17c61-113">Verificare che i servizi seguenti siano in uso nel server front-end:</span><span class="sxs-lookup"><span data-stu-id="17c61-113">Verify that the following services are running on the Front End Server:</span></span>

    - <span data-ttu-id="17c61-114">Agente del servizio di registrazione centralizzato</span><span class="sxs-lookup"><span data-stu-id="17c61-114">Centralized Logging Service Agent</span></span>
    - <span data-ttu-id="17c61-115">Condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="17c61-115">Application Sharing</span></span>
    - <span data-ttu-id="17c61-116">Servizio test audio</span><span class="sxs-lookup"><span data-stu-id="17c61-116">Audio Test Service</span></span>
    - <span data-ttu-id="17c61-117">Conferenze audio/video</span><span class="sxs-lookup"><span data-stu-id="17c61-117">Audio/Video Conferencing</span></span>
    - <span data-ttu-id="17c61-118">Parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="17c61-118">Call Park</span></span>
    - <span data-ttu-id="17c61-119">Annuncio conferenza</span><span class="sxs-lookup"><span data-stu-id="17c61-119">Conferencing Announcement</span></span>
    - <span data-ttu-id="17c61-120">Assistente conferenza</span><span class="sxs-lookup"><span data-stu-id="17c61-120">Conferencing Attendant</span></span>
    - <span data-ttu-id="17c61-121">Front-end</span><span class="sxs-lookup"><span data-stu-id="17c61-121">Front-End</span></span>
    - <span data-ttu-id="17c61-122">Conferenza di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="17c61-122">IM Conferencing</span></span>
    - <span data-ttu-id="17c61-123">Pubblicitari</span><span class="sxs-lookup"><span data-stu-id="17c61-123">Mediation</span></span>
    - <span data-ttu-id="17c61-124">Agente Replicator replica</span><span class="sxs-lookup"><span data-stu-id="17c61-124">Replica Replicator Agent</span></span>
    - <span data-ttu-id="17c61-125">Response Group</span><span class="sxs-lookup"><span data-stu-id="17c61-125">Response Group</span></span>
    - <span data-ttu-id="17c61-126">Web Conferencing</span><span class="sxs-lookup"><span data-stu-id="17c61-126">Web Conferencing</span></span>
    - <span data-ttu-id="17c61-127">Gateway di traduzione XMPP</span><span class="sxs-lookup"><span data-stu-id="17c61-127">XMPP Translating Gateway</span></span>

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="17c61-128">Aprire il pannello di controllo di Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="17c61-128">Open the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="17c61-129"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="17c61-129"></span></span>

<span data-ttu-id="17c61-130">Dal server front-end della distribuzione di Skype for Business Server 2019 aprire il pannello di controllo di Skype for Business Server 2019 e selezionare il pool legacy.</span><span class="sxs-lookup"><span data-stu-id="17c61-130">From the Front End Server in your Skype for Business Server 2019 deployment, open the Skype for Business Server 2019 Control Panel and select the legacy pool.</span></span> <span data-ttu-id="17c61-131">Ripetere la procedura per aprire il pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="17c61-131">Repeat the procedure to open the Skype for Business Server 2019 pool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="17c61-132">In Skype for Business Server 2019 è necessario eseguire l'aggiornamento a Silverlight versione 5 prima di usare il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="17c61-132">On Skype for Business Server 2019, you must upgrade Silverlight to Silverlight version 5 prior to using the Skype for Business Server Control Panel.</span></span> 
  
<span data-ttu-id="17c61-133">Questa topologia include ora i ruoli server legacy e Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="17c61-133">This topology now includes legacy and Skype for Business Server 2019 server roles.</span></span> 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a><span data-ttu-id="17c61-134">Non provare ad aprire la topologia nel generatore di topologia legacy</span><span class="sxs-lookup"><span data-stu-id="17c61-134">Don't attempt to open the topology in the legacy Topology Builder</span></span>
<span data-ttu-id="17c61-135"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="17c61-135"></span></span>

<span data-ttu-id="17c61-136">La topologia può essere visualizzata solo con il generatore di topologia di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="17c61-136">The topology can only be viewed using Skype for Business Server 2019 Topology Builder.</span></span> <span data-ttu-id="17c61-137">Il generatore di topologia di Skype for Business Server 2019 deve essere usato per creare pool sia per Skype for Business Server 2019 che per l'installazione legacy.</span><span class="sxs-lookup"><span data-stu-id="17c61-137">The Skype for Business Server 2019 Topology Builder must be used to create pools for both Skype for Business Server 2019 and the legacy install.</span></span>

  


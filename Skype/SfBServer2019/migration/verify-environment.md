---
title: Verificare l'ambiente legacy
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Prima di distribuire Skype for Business Server 2019 in uno stato di coesistenza, è necessario verificare che i servizi legacy siano stati configurati e avviati. È importante identificare i servizi e le caratteristiche principali presenti nell'ambiente legacy, prima di distribuire un pool pilota di Skype for Business Server 2019. Prima di distribuire Microsoft Skype for Business Server 2019 XMPP in uno stato di coesistenza con una distribuzione XMPP legacy, è necessario verificare che i servizi XMPP legacy siano stati configurati e avviati e identificare il partner federato della configurazione XMPP legacy supporto.
ms.openlocfilehash: 34c9ecbc4fe9863c09b2648145ff46c1628ef655
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812694"
---
# <a name="verify-the-legacy-environment"></a><span data-ttu-id="b35cc-105">Verificare l'ambiente legacy</span><span class="sxs-lookup"><span data-stu-id="b35cc-105">Verify the legacy environment</span></span>

<span data-ttu-id="b35cc-106">Prima di distribuire Skype for Business Server 2019 in uno stato di coesistenza, è necessario verificare che i servizi legacy siano stati configurati e avviati.</span><span class="sxs-lookup"><span data-stu-id="b35cc-106">Before deploying Skype for Business Server 2019 in a coexistence state, you need to verify that legacy services have been configured and started.</span></span> <span data-ttu-id="b35cc-107">È importante identificare i servizi e le caratteristiche principali presenti nell'ambiente legacy prima della distribuzione di un pool pilota di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b35cc-107">It is important to identify key services and features that exist in your legacy environment prior to deploying a Skype for Business Server 2019 pilot pool.</span></span> <span data-ttu-id="b35cc-108">Prima di distribuire Microsoft Skype for Business Server 2019 XMPP in uno stato di coesistenza con una distribuzione XMPP legacy, è necessario verificare che i servizi XMPP legacy siano stati configurati e avviati e identificare il partner federativo legacy XMPP la configurazione sta supportando.</span><span class="sxs-lookup"><span data-stu-id="b35cc-108">Before deploying Microsoft Skype for Business Server 2019 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify that the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="b35cc-109">La verifica della distribuzione legacy comporta le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b35cc-109">Verifying your legacy deployment entails the following:</span></span>
  
- <span data-ttu-id="b35cc-110">Verificare che i servizi legacy vengano avviati</span><span class="sxs-lookup"><span data-stu-id="b35cc-110">Verifying that the legacy services are started</span></span>
    
- <span data-ttu-id="b35cc-111">Revisione della topologia e degli utenti</span><span class="sxs-lookup"><span data-stu-id="b35cc-111">Reviewing the topology and users</span></span>
    
- <span data-ttu-id="b35cc-112">Verifica delle impostazioni della Federazione e del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="b35cc-112">Verifying the federation and Edge server settings</span></span>
    
- <span data-ttu-id="b35cc-113">Verificare i servizi XMPP e i partner federati</span><span class="sxs-lookup"><span data-stu-id="b35cc-113">Verifying XMPP services and federated partners</span></span>
    
## <a name="verify-that-legacy-services-are-started"></a><span data-ttu-id="b35cc-114">Verificare che i servizi legacy siano avviati</span><span class="sxs-lookup"><span data-stu-id="b35cc-114">Verify that legacy services are started</span></span>

1. <span data-ttu-id="b35cc-115">Dal server front-end legacy passare all'applet Tools\Services amministrativa.</span><span class="sxs-lookup"><span data-stu-id="b35cc-115">From the legacy Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="b35cc-116">Verificare che i servizi seguenti siano in uso nel server front-end:</span><span class="sxs-lookup"><span data-stu-id="b35cc-116">Verify that the following services are running on the Front End Server:</span></span>
    
     ![Elenco dei servizi in esecuzione nel server Front End](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a><span data-ttu-id="b35cc-118">Esaminare la topologia legacy nel pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b35cc-118">Review the legacy topology in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="b35cc-119">Accedere al server front-end con un account che sia un membro del gruppo RTCUniversalServerAdmins o un membro del ruolo di amministratore di CsAdministrator o CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="b35cc-119">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="b35cc-120">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b35cc-120">Open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="b35cc-121">Selezionare **topologia**.</span><span class="sxs-lookup"><span data-stu-id="b35cc-121">Select **Topology**.</span></span> <span data-ttu-id="b35cc-122">Verificare che i vari server della distribuzione legacy siano elencati.</span><span class="sxs-lookup"><span data-stu-id="b35cc-122">Verify that the various servers in your legacy deployment are listed.</span></span>
    
     ![Pagina topologia pannello di controllo](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a><span data-ttu-id="b35cc-124">Rivedere gli utenti legacy nel pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b35cc-124">Review legacy users in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="b35cc-125">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b35cc-125">Open the Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="b35cc-126">Selezionare **utenti**e quindi fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="b35cc-126">Select **Users**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="b35cc-127">Verificare che la colonna del **pool di registrazione** punti al pool legacy per ogni utente elencato.</span><span class="sxs-lookup"><span data-stu-id="b35cc-127">Verify that the **Registrar Pool** column points to the legacy pool for each user listed.</span></span> 
    
     ![Elenco degli utenti del pannello di controllo](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a><span data-ttu-id="b35cc-129">Verificare le impostazioni di Edge e federazioni legacy</span><span class="sxs-lookup"><span data-stu-id="b35cc-129">Verify legacy Edge and federation settings</span></span>

1. <span data-ttu-id="b35cc-130">Avviare Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="b35cc-130">Start Topology Builder.</span></span>
    
2. <span data-ttu-id="b35cc-131">Selezionare **Scarica topologia dalla distribuzione esistente**.</span><span class="sxs-lookup"><span data-stu-id="b35cc-131">Select **Download Topology from existing deployment**.</span></span>
    
3. <span data-ttu-id="b35cc-132">Scegliere un nome file e salvare la topologia con il tipo di file default. tbxml.</span><span class="sxs-lookup"><span data-stu-id="b35cc-132">Choose a file name, and save the topology with the default .tbxml file type.</span></span>
    
4. <span data-ttu-id="b35cc-133">Espandere il nodo installazioni legacy per rivelare i vari ruoli del server nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="b35cc-133">Expand the legacy installs node to reveal the various server roles in the deployment.</span></span>
    
5. <span data-ttu-id="b35cc-134">Selezionare il nodo del sito e verificare che sia impostato un valore di **assegnazione della route federativo del sito** .</span><span class="sxs-lookup"><span data-stu-id="b35cc-134">Select the site node and verify that a **Site federation route assignment** value is set.</span></span> 
    
     ![Generatore di topologie - Route federazione sito](../media/migration_lyncserver_w14_federation.jpg)
  
6. <span data-ttu-id="b35cc-136">Selezionare il pool di front end del server Standard Edition o Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="b35cc-136">Select the Standard Edition Server or Enterprise Edition front end pool.</span></span> <span data-ttu-id="b35cc-137">Determinare se un pool di bordi è stato configurato per elementi multimediali al di sotto delle **associazioni**.</span><span class="sxs-lookup"><span data-stu-id="b35cc-137">Determine whether an Edge pool has been configured for media below **Associations**.</span></span> 
    
     ![Generatore di topologie con server e pool](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. <span data-ttu-id="b35cc-139">Selezionare il pool di bordi e identificare se un pool di hop successivo è configurato sotto la **selezione dell'hop successivo**.</span><span class="sxs-lookup"><span data-stu-id="b35cc-139">Select the Edge pool and identify whether a Next hop pool is configured below **Next hop selection**.</span></span>
    
     ![Generatore di topologie - Selezione hop successivo](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a><span data-ttu-id="b35cc-141">Verificare la configurazione legacy del partner federato XMPP</span><span class="sxs-lookup"><span data-stu-id="b35cc-141">Verify legacy XMPP federated partner Configuration</span></span>

1. <span data-ttu-id="b35cc-142">Dal server XMPP legacy passare all'applet Tools\Services amministrativa.</span><span class="sxs-lookup"><span data-stu-id="b35cc-142">From the legacy XMPP server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="b35cc-143">Verificare che il servizio gateway XMPP di Office Communications Server sia stato avviato.</span><span class="sxs-lookup"><span data-stu-id="b35cc-143">Verify that the Office Communications Server XMPP Gateway service is started.</span></span> 
    
     ![Servizio gateway XMPP di Office Communications Server](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  


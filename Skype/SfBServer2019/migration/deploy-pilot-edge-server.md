---
title: Distribuire Edge Server pilota
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
description: In questo argomento vengono evidenziate le impostazioni di configurazione di cui tenere conto prima di distribuire il server perimetrale di Skype for Business Server 2019. I processi di distribuzione e configurazione per Skype for Business Server 2019 sono molto simili a Skype for Business Server 2015. In questa sezione vengono evidenziati solo i punti chiave di cui è consigliabile tenere conto nell'ambito della distribuzione del pool pilota. Per la procedura dettagliata, vedere Deploying External User Access in Skype for Business Server 2019 nella documentazione relativa alla distribuzione, in cui viene descritto il processo di distribuzione e vengono fornite anche informazioni di configurazione per l'accesso degli utenti esterni.
ms.openlocfilehash: 00c371b917f2649dba9011fbbce6162b153822d1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752868"
---
# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="869b1-106">Distribuire Edge Server pilota</span><span class="sxs-lookup"><span data-stu-id="869b1-106">Deploy pilot Edge Server</span></span>

<span data-ttu-id="869b1-107">In questo argomento vengono evidenziate le impostazioni di configurazione di cui tenere conto prima di distribuire il server perimetrale di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="869b1-107">This topic highlights configuration settings you should be aware of before deploying your Skype for Business Server 2019 Edge Server.</span></span> <span data-ttu-id="869b1-108">I processi di distribuzione e configurazione per Skype for Business Server 2019 sono molto simili a Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="869b1-108">The deployment and configuration processes for Skype for Business Server 2019 are very similar to Skype for Business Server 2015.</span></span> <span data-ttu-id="869b1-109">In questa sezione vengono evidenziati solo i punti chiave di cui è consigliabile tenere conto nell'ambito della distribuzione del pool pilota.</span><span class="sxs-lookup"><span data-stu-id="869b1-109">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
<span data-ttu-id="869b1-110">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span><span class="sxs-lookup"><span data-stu-id="869b1-110">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="869b1-111">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span><span class="sxs-lookup"><span data-stu-id="869b1-111">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span> 
  
### <a name="to-define-an-edge-pool"></a><span data-ttu-id="869b1-112">Per definire un pool di server perimetrali</span><span class="sxs-lookup"><span data-stu-id="869b1-112">To define an Edge Pool</span></span>

1. <span data-ttu-id="869b1-113">Accedere al computer in cui è installato Generatore di topologie come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="869b1-113">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="869b1-114">Accedere al nodo Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="869b1-114">Navigate to the Skype for Business Server 2019 node.</span></span> <span data-ttu-id="869b1-115">Fare clic con il pulsante destro del mouse su **Pool di server perimetrali** e scegliere **Nuovo pool di server perimetrali**.</span><span class="sxs-lookup"><span data-stu-id="869b1-115">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
     ![Finestra di dialogo definire il nuovo pool di server perimetrali](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. <span data-ttu-id="869b1-117">Un pool di server perimetrali può essere un **Pool di più computer** o un **Pool computer singolo**.</span><span class="sxs-lookup"><span data-stu-id="869b1-117">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
     ![Finestra di dialogo definire l'FQDN del pool di server perimetrali](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. <span data-ttu-id="869b1-119">Nella pagina **Selezionare funzionalità** non abilitare la federazione o la federazione XMPP.</span><span class="sxs-lookup"><span data-stu-id="869b1-119">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="869b1-120">La Federazione e la Federazione XMPP sono entrambe instradate al server perimetrale legacy.</span><span class="sxs-lookup"><span data-stu-id="869b1-120">Federation and XMPP federation are both currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="869b1-121">Queste funzionalità verranno configurate in una fase successiva della migrazione.</span><span class="sxs-lookup"><span data-stu-id="869b1-121">These features will be configured in a later phase of migration.</span></span> 

  
5. <span data-ttu-id="869b1-122">Continuare a completare le pagine seguenti della procedura guidata: **FQDN esterni**, **definire l'indirizzo IP interno**e **definire l'indirizzo IP esterno**.</span><span class="sxs-lookup"><span data-stu-id="869b1-122">Continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>
    
6. <span data-ttu-id="869b1-123">Nella pagina **definire il server dell'hop successivo** selezionare il Director per l'hop successivo del pool perimetrale legacy.</span><span class="sxs-lookup"><span data-stu-id="869b1-123">On the **Define the next hop server** page, select the Director for the next hop of the legacy Edge pool.</span></span> 
    
     ![Finestra di dialogo definire l'hop successivo](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. <span data-ttu-id="869b1-125">Nella pagina **associa gruppi front-end o pool di Mediation** non associare un pool a questo pool di server perimetrali in questo momento.</span><span class="sxs-lookup"><span data-stu-id="869b1-125">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="869b1-126">Il traffico multimediale esterno è attualmente instradato attraverso il server perimetrale legacy.</span><span class="sxs-lookup"><span data-stu-id="869b1-126">External media traffic is currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="869b1-127">Questa impostazione verrà configurata in una fase successiva della migrazione.</span><span class="sxs-lookup"><span data-stu-id="869b1-127">This setting will be configured in a later phase of migration.</span></span> 
    
     ![Finestra di dialogo Associa pool Front End](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. <span data-ttu-id="869b1-129">Fare clic su **fine**e quindi **pubblicare** la topologia.</span><span class="sxs-lookup"><span data-stu-id="869b1-129">Click **Finish**, and then **Publish** the topology.</span></span> 
    
9. <span data-ttu-id="869b1-130">Attenersi alla procedura descritta nella documentazione relativa alla distribuzione per installare i file nel nuovo server perimetrale, configurare i certificati e avviare i servizi.</span><span class="sxs-lookup"><span data-stu-id="869b1-130">Follow the steps in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span> 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
<span data-ttu-id="869b1-131">È molto importante seguire le linee guida negli argomenti della documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="869b1-131">It's very important that you follow the guidelines in the topics in the Deployment documentation.</span></span> <span data-ttu-id="869b1-132">In questa sezione vengono fornite solo indicazioni sulle impostazioni di configurazione durante la fase di installazione di questi ruoli server.</span><span class="sxs-lookup"><span data-stu-id="869b1-132">This section merely provided some guidance on configuration settings when installing these server roles.</span></span> 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
<span data-ttu-id="869b1-133">È ora necessario disporre di un server perimetrale legacy distribuito in parallelo con una distribuzione di server perimetrale di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="869b1-133">You should now have a legacy Edge Server deployed in parallel with a Skype for Business Server 2019 Edge server deployment.</span></span> <span data-ttu-id="869b1-134">Prima di passare alla fase successiva, verificare che entrambe le distribuzioni funzionino correttamente, che i servizi siano stati avviati e che sia possibile amministrare ogni distribuzione.</span><span class="sxs-lookup"><span data-stu-id="869b1-134">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span> 
  


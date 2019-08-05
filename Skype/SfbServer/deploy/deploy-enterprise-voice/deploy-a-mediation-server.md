---
title: Distribuire un Mediation Server in Generatore di topologia in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: 'Riepilogo: informazioni su come definire e distribuire un Mediation Server in Generatore di topologie in Skype for Business Server.'
ms.openlocfilehash: 61b90bb874d96579d975a1672238a7427350a5dc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190088"
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="77d5c-103">Distribuire un Mediation Server in Generatore di topologia in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="77d5c-103">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="77d5c-104">**Riepilogo:** Informazioni su come definire e distribuire un Mediation Server in Generatore di topologia in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="77d5c-104">**Summary:** Learn how to define and deploy a Mediation Server in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="77d5c-105">Il carico di lavoro VoIP aziendale, i servizi di conferenza telefonica con accesso esterno e le applicazioni vocali avanzate di Enterprise (Response Group Application, Call Park application, Call ammissioni Control (CAC) e così via) sono disponibili nei pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="77d5c-105">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="77d5c-106">La funzionalità di Mediation Server è integrata nel server front-end.</span><span class="sxs-lookup"><span data-stu-id="77d5c-106">The functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="77d5c-107">Un server di mediazione autonomo separato non è necessario.</span><span class="sxs-lookup"><span data-stu-id="77d5c-107">A separate stand-alone Mediation Server is not necessary.</span></span> 
  
<span data-ttu-id="77d5c-108">L'unica eccezione è la configurazione di un trunk SIP per la connessione a un controller di bordo della sessione per un provider di servizi di telefonia Internet.</span><span class="sxs-lookup"><span data-stu-id="77d5c-108">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="77d5c-109">Per connettere l'infrastruttura VoIP aziendale al provider trunk SIP, è necessario distribuire un server di mediazione separato.</span><span class="sxs-lookup"><span data-stu-id="77d5c-109">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>
  
<span data-ttu-id="77d5c-110">La connessione tra Skype for Business Server (un Mediation Server collocato in un pool Front-end o un Mediation Server autonomo) e un gateway viene definito come associazione logica denominata trunk.</span><span class="sxs-lookup"><span data-stu-id="77d5c-110">The connection between Skype for Business Server (either a Mediation Server collocated on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a trunk.</span></span> <span data-ttu-id="77d5c-111">Gli argomenti di questa sezione descrivono come definire un trunk e come distribuire un Mediation Server autonomo, se ci si connette a un trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="77d5c-111">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>
  
## <a name="define-a-mediation-server-in-topology-builder"></a><span data-ttu-id="77d5c-112">Definire un Mediation Server in Generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="77d5c-112">Define a Mediation Server in Topology Builder</span></span>

<span data-ttu-id="77d5c-113">È possibile aggiungere Mediation Server come ruolo collocato in un pool Front-end oppure definire un pool di Mediation Server autonomo distinto.</span><span class="sxs-lookup"><span data-stu-id="77d5c-113">You can add Mediation Server as a collocated role on a Front End pool, or define a separate standalone Mediation Server pool.</span></span>
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a><span data-ttu-id="77d5c-114">Per aggiungere un Mediation Server a un pool Front-End</span><span class="sxs-lookup"><span data-stu-id="77d5c-114">To add a Mediation Server to a Front End pool</span></span>

1. <span data-ttu-id="77d5c-115">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for Business Server 2015**e quindi su **Skype for Business Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="77d5c-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="77d5c-116">Nell'albero della console di generatore di topologia espandere il nome del sito per il quale si desidera definire un pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="77d5c-116">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Front End pool.</span></span>
    
3. <span data-ttu-id="77d5c-117">Nell'albero della console fare clic con il pulsante destro del mouse sul tipo di pool Front-end desiderato e quindi scegliere **nuovo pool Front-end.**..</span><span class="sxs-lookup"><span data-stu-id="77d5c-117">In the console tree, right-click the type of Front End pool you want, and then click **New Front End pool..**.</span></span>
    
4. <span data-ttu-id="77d5c-118">Spostarsi tra la procedura guidata **Definisci nuovo pool di front end** fino a raggiungere la pagina **Selezione ruoli server collocati** .</span><span class="sxs-lookup"><span data-stu-id="77d5c-118">Navigate through the **Define New Front End Pool** wizard until you reach the **Select collocated server roles** page.</span></span>
    
5. <span data-ttu-id="77d5c-119">In **Seleziona ruoli server collocati selezionare**l'opzione **collocazione Mediation Server**.</span><span class="sxs-lookup"><span data-stu-id="77d5c-119">In **Select collocated server roles**, check the option **Collocate Mediation Server**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="77d5c-120">Se il tipo di pool Front-End selezionato è Enterprise Edition, il componente Mediation Server verrà installato in tutti i server front-end del pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="77d5c-120">If the type of Front End pool you selected is the Enterprise Edition, then the Mediation Server component will be installed on all the Front End Servers of that Front End pool.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="77d5c-121">Il **pool di hop successivo** usato dal Mediation Server sarà il pool Front-end in cui è installato il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="77d5c-121">The **Next hop pool** used by the Mediation Server will be the Front End pool where the Mediation Server is collocated on.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="77d5c-122">Il **pool di Edge** usato da Mediation Server sarà lo stesso pool di Edge associato al pool Front-end in cui è installato il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="77d5c-122">The **Edge pool** used by the Mediation Server will be the same Edge pool associated with the Front End pool where the Mediation Server is collocated on.</span></span>
  
6. <span data-ttu-id="77d5c-123">Fare clic su **Imposta predefinito** per usare questo pool Front-end per instradare le chiamate alla rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="77d5c-123">Click **Make Default** to use this Front End pool to route calls to the PSTN.</span></span>
    
7. <span data-ttu-id="77d5c-124">Al termine, fare clic su **fine** per associare uno o più peer al pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="77d5c-124">Click **Finish** when you are finished associating one or more peers to the Front End pool.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="77d5c-125">Prima di procedere con il passaggio successivo nel processo di distribuzione di VoIP aziendale, verificare che il pool di Mediation Server (ad esempio il pool Front end con il componente Mediation Server) usi i nomi di dominio completi specificati.</span><span class="sxs-lookup"><span data-stu-id="77d5c-125">Before you proceed to the next step in the Enterprise Voice deployment process, make sure that the Mediation Server pool (i.e. Front End pool with the Mediation Server component collocated) is using the FQDNs that you specified.</span></span> 
  
8. <span data-ttu-id="77d5c-126">Fare clic con il pulsante destro del mouse sul nodo **di Skype for Business Server 2015** e quindi scegliere **Pubblica topologia**.</span><span class="sxs-lookup"><span data-stu-id="77d5c-126">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
### <a name="to-add-a-standalone-mediation-server"></a><span data-ttu-id="77d5c-127">Per aggiungere un Mediation Server autonomo</span><span class="sxs-lookup"><span data-stu-id="77d5c-127">To add a standalone Mediation Server</span></span>

1. <span data-ttu-id="77d5c-128">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for Business Server 2015**e quindi su **Skype for Business Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="77d5c-128">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="77d5c-129">Nell'albero della console di generatore di topologia espandere il nome del sito per il quale si desidera definire un Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="77d5c-129">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Mediation Server.</span></span>
    
3. <span data-ttu-id="77d5c-130">Nell'albero della console fare clic con il pulsante destro del mouse sul nodo **pool** di mediazione e quindi scegliere **pool di Mediation Server**.</span><span class="sxs-lookup"><span data-stu-id="77d5c-130">In the console tree, right-click the **Mediation pools** node, and then click **Mediation Server pool**.</span></span>
    
4. <span data-ttu-id="77d5c-131">In **Definisci nuovo pool**di mediazione digitare il nome di dominio completo (FQDN) del pool di Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="77d5c-131">In **Define New Mediation Pool**, type the Mediation Server pool fully qualified domain name (FQDN).</span></span>
    
5. <span data-ttu-id="77d5c-132">Eseguire quindi una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="77d5c-132">Next, do one of the following:</span></span>
    
   - <span data-ttu-id="77d5c-133">Se si vuole distribuire più server di mediazione nel pool per ottenere una disponibilità elevata, selezionare **più pool di computer**.</span><span class="sxs-lookup"><span data-stu-id="77d5c-133">If you want to deploy multiple Mediation Servers in the pool to provide high availability, then select **Multiple computer pool**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="77d5c-134">È necessario eseguire la [distribuzione](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) per supportare i pool di Mediation Server con più server di mediazione.</span><span class="sxs-lookup"><span data-stu-id="77d5c-134">You must [deploy](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) to support Mediation Server pools that have multiple Mediation Servers.</span></span>
  
   - <span data-ttu-id="77d5c-135">Se si vuole distribuire un solo Mediation Server nel pool perché non è necessaria una disponibilità elevata, selezionare **Single computer pool**.</span><span class="sxs-lookup"><span data-stu-id="77d5c-135">If you want to deploy only one Mediation Server in the pool because you do not require high availability, then select **Single computer pool**.</span></span> <span data-ttu-id="77d5c-136">Ignorare il passaggio seguente.</span><span class="sxs-lookup"><span data-stu-id="77d5c-136">Skip the following step.</span></span>
    
6. <span data-ttu-id="77d5c-137">Se nel passaggio precedente è stato selezionato **più pool di computer** , nell'elemento Definisci **i computer in questo pool** fare clic su **FQDN computer**, digitare il nome di dominio completo di ogni server nel pool e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="77d5c-137">If you selected **Multiple computer pool** in the previous step, on the **Define the computers in this pool** item, click **Computer FQDN**, type the FQDN of each server in the pool, and then click **Add**.</span></span> <span data-ttu-id="77d5c-138">Ripetere questo passaggio per tutti gli altri Mediation Server che si vuole aggiungere al pool.</span><span class="sxs-lookup"><span data-stu-id="77d5c-138">Repeat this step for all other Mediation Servers that you want to add to the pool.</span></span> <span data-ttu-id="77d5c-139">Dopo aver definito tutti i computer nel pool, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="77d5c-139">When you have defined all the computers in the pool, click **Next**.</span></span>
    
7. <span data-ttu-id="77d5c-140">Nella pagina **selezionare l'hop successivo** fare clic su **pool hop successivo**, fare clic sul nome di dominio completo del pool Front-end che utilizzerà questo pool di Mediation Server e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="77d5c-140">On the **Select the next hop** page, click **Next hop pool**, click the FQDN of the Front End pool that will use this Mediation Server pool, and then click **Next**.</span></span>
    
8. <span data-ttu-id="77d5c-141">Nella pagina **selezionare un server perimetrale** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="77d5c-141">On the **Select an Edge Server** page, do one of the following:</span></span>
    
   - <span data-ttu-id="77d5c-142">Se si vuole consentire la connettività PSTN agli utenti esterni abilitati per VoIP aziendale, in **selezionare pool Edge usato da questo Mediation Server**fare clic sul nome di dominio completo del pool di Edge Server che utilizzerà questo pool di Mediation Server per consentire la connettività PSTN Gli utenti esterni e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="77d5c-142">If you want to provide PSTN connectivity to external users enabled for Enterprise Voice, under **Select Edge Pool used by this Mediation Server**, click the FQDN of the Edge Server pool that will use this Mediation Server pool to provide PSTN connectivity to those external users, and then click **Next**.</span></span>
    
   - <span data-ttu-id="77d5c-143">Se non si prevede di abilitare gli utenti esterni per VoIP aziendale o se non si vuole concedere connettività PSTN agli utenti quando si trovano all'esterno della rete interna, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="77d5c-143">If you do not plan to enable external users for Enterprise Voice, or if you do not want to provide PSTN connectivity to users when they are outside the internal network, click **Next**.</span></span>
    
9. <span data-ttu-id="77d5c-144">Fare clic con il pulsante destro del mouse sul nodo **di Skype for Business Server 2015** e quindi scegliere **Pubblica topologia**.</span><span class="sxs-lookup"><span data-stu-id="77d5c-144">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
## <a name="define-the-mediation-server-listening-ports"></a><span data-ttu-id="77d5c-145">Definire le porte di ascolto di Mediation Server</span><span class="sxs-lookup"><span data-stu-id="77d5c-145">Define the Mediation Server Listening Ports</span></span>

<span data-ttu-id="77d5c-146">Seguire i passaggi descritti in questo argomento per usare generatore di topologie per definire le porte in attesa un server di mediazione o un pool accetteranno le connessioni in ingresso da un peer del gateway.</span><span class="sxs-lookup"><span data-stu-id="77d5c-146">Follow the steps in this topic to use Topology Builder to define the listening ports a Mediation Server or pool will accept incoming connections from a gateway peer.</span></span>
  
### <a name="to-modify-the-mediation-server-listening-ports"></a><span data-ttu-id="77d5c-147">Per modificare le porte di ascolto di Mediation Server</span><span class="sxs-lookup"><span data-stu-id="77d5c-147">To Modify the Mediation Server Listening Ports</span></span>

1. <span data-ttu-id="77d5c-148">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for Business Server 2015**e quindi su **Skype for Business Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="77d5c-148">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="77d5c-149">Nell'albero della console di generatore di topologia espandere il nodo **pool** di mediazione e fare clic con il pulsante destro del mouse sul server di mediazione creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="77d5c-149">In Topology Builder, in the console tree, expand the **Mediation pools** node, and right-click the Mediation Server previously created.</span></span>
    
3. <span data-ttu-id="77d5c-150">Per impostazione predefinita, le porte di ascolto SIP sul Mediation Server sono 5070 per il traffico TLS da Skype for Business Server e 5067 per il traffico TLS da peer (ad esempio gateway, sistemi PBX o SBCs).</span><span class="sxs-lookup"><span data-stu-id="77d5c-150">By default, the SIP listening ports on the Mediation Server are 5070 for TLS traffic from Skype for Business Server, and 5067 for TLS traffic from peers (such as gateways, PBXes, or SBCs).</span></span> <span data-ttu-id="77d5c-151">La porta TCP è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="77d5c-151">TCP port is disabled by default.</span></span> <span data-ttu-id="77d5c-152">È necessario abilitare la porta TCP se sono presenti gateway che non supportano TLS.</span><span class="sxs-lookup"><span data-stu-id="77d5c-152">You must enable TCP port if you have gateways that do not support TLS.</span></span>
    
4. <span data-ttu-id="77d5c-153">Specificare l'intervallo di porte di ascolto TLS o TCP desiderato il server di mediazione accetterà le connessioni in ingresso dai gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="77d5c-153">Specify the desired TLS or TCP listening port range the Mediation Server will accept incoming connections from PSTN gateways.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="77d5c-154">L'immissione di un intervallo di porte TCP non è necessaria se l'abilitazione della **porta TCP** non è selezionata.</span><span class="sxs-lookup"><span data-stu-id="77d5c-154">Entering a TCP port range is not required if **Enable TCP port** is not checked.</span></span> <span data-ttu-id="77d5c-155">Questa impostazione è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="77d5c-155">This setting is optional.</span></span>
  


---
title: Configurare le route federative e il traffico multimediale
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Federation è una relazione di trust tra due o più domini SIP che consente agli utenti di organizzazioni separate di comunicare tra loro attraverso i confini della rete. Dopo la migrazione al pool pilota, è necessario eseguire la transizione dalla Route federativo delle versioni precedenti dei server Edge alla route federativo dei server Edge di Skype for Business Server 2019.
ms.openlocfilehash: 6b76932c8b988dbed61cba1470f32a51f6585536
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195023"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="aff33-104">Configurare le route federative e il traffico multimediale</span><span class="sxs-lookup"><span data-stu-id="aff33-104">Configure federation routes and media traffic</span></span>

<span data-ttu-id="aff33-105">Federation è una relazione di trust tra due o più domini SIP che consente agli utenti di organizzazioni separate di comunicare tra loro attraverso i confini della rete.</span><span class="sxs-lookup"><span data-stu-id="aff33-105">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="aff33-106">Dopo la migrazione al pool pilota, è necessario eseguire la transizione dalla Route federativo della versione precedente di Edge Server alla route federativo di Skype for Business Server 2019 Edge Servers.</span><span class="sxs-lookup"><span data-stu-id="aff33-106">After you migrate to your pilot pool, you need to transition from the federation route of your previous version's Edge Servers to the federation route of your Skype for Business Server 2019 Edge Servers.</span></span>
  
<span data-ttu-id="aff33-107">Usare le procedure seguenti per eseguire la transizione della route federativa e della route del traffico multimediale da Edge Server e Director della versione precedente al server Edge di Skype for Business Server 2019 per una distribuzione a sito singolo.</span><span class="sxs-lookup"><span data-stu-id="aff33-107">Use the following procedures to transition the federation route and the media traffic route from your previous version's Edge Server and Director to your Skype for Business Server 2019 Edge Server, for a single-site deployment.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="aff33-108">Se si modifica la route della Federazione e il traffico multimediale, è necessario pianificare l'inattività di manutenzione per Skype for Business Server 2019 e i server Edge versione precedente.</span><span class="sxs-lookup"><span data-stu-id="aff33-108">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Skype for Business Server 2019 and previous version Edge Servers.</span></span> <span data-ttu-id="aff33-109">L'intero processo di transizione significa anche che l'accesso federato non sarà disponibile per la durata dell'interruzione.</span><span class="sxs-lookup"><span data-stu-id="aff33-109">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="aff33-110">È consigliabile pianificare i tempi di inattività per un periodo di tempo in cui si prevede un'attività utente minima.</span><span class="sxs-lookup"><span data-stu-id="aff33-110">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="aff33-111">Dovresti anche dare una notifica sufficiente agli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="aff33-111">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="aff33-112">Pianificare di conseguenza questa interruzione e impostare le aspettative appropriate all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="aff33-112">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="aff33-113">Se il server perimetrale legacy è configurato per l'uso dello stesso nome di dominio completo per il servizio Access Edge, Web Conferencing Edge service e il servizio A/V Edge, le procedure descritte in questa sezione non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="aff33-113">If your legacy Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="aff33-114">Se i servizi Edge legacy sono configurati in modo da usare lo stesso nome di dominio completo, è necessario prima eseguire la migrazione di tutti gli utenti, quindi rimuovere il server Edge versioni precedenti prima di abilitare la Federazione in Skype for Business Server 2019 Edge Server.</span><span class="sxs-lookup"><span data-stu-id="aff33-114">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users, then decommission the previous versions Edge Server before enabling federation on the Skype for Business Server 2019 Edge Server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="aff33-115">Se la Federazione XMPP viene instradata tramite un server Edge di Skype for Business Server 2019, gli utenti della versione precedente non saranno in grado di comunicare con il partner federato XMPP finché tutti gli utenti non sono stati spostati in Skype for Business Server 2019, i criteri XMPP e i certificati sono stati configurati, il partner federato XMPP è stato configurato in Skype for Business Server 2019 e, infine, le voci DNS sono state aggiornate.</span><span class="sxs-lookup"><span data-stu-id="aff33-115">If your XMPP federation is routed through a Skype for Business Server 2019 Edge Server, users on the previous version will not be able to communicate with the XMPP federated partner until all users have been moved to Skype for Business Server 2019, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Skype for Business Server 2019, and, lastly, the DNS entries have been updated.</span></span> 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a><span data-ttu-id="aff33-116">Per rimuovere l'associazione di federazione legacy dai siti di Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="aff33-116">To remove the legacy federation association from Skype for Business Server 2019 sites</span></span>

1. <span data-ttu-id="aff33-117">Nel server front end di Skype for Business Server 2019 aprire la topologia esistente in Generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="aff33-117">On the Skype for Business Server 2019 Front End server, open the existing topology in Topology Builder.</span></span> 
    
2. <span data-ttu-id="aff33-118">Nel riquadro sinistro passare al nodo del sito, che si trova direttamente sotto **Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="aff33-118">In the left pane, navigate to the site node, which is located directly below **Skype for Business Server**.</span></span>
    
3. <span data-ttu-id="aff33-119">Fare clic con il pulsante destro del mouse sul sito e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="aff33-119">Right-click the site, and then click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="aff33-120">Nel riquadro sinistro selezionare **Route federativo**.</span><span class="sxs-lookup"><span data-stu-id="aff33-120">In the left pane, select **Federation route**.</span></span> 
    
5. <span data-ttu-id="aff33-121">In **assegnazione della route federativo di sito**deselezionare la casella di controllo **Abilita federazione SIP** per disabilitare la route federativo nell'ambiente legacy.</span><span class="sxs-lookup"><span data-stu-id="aff33-121">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy environment.</span></span> 
  
6. <span data-ttu-id="aff33-122">Fare clic su **OK** per chiudere la pagina Modifica proprietà.</span><span class="sxs-lookup"><span data-stu-id="aff33-122">Click **OK** to close the Edit Properties page.</span></span> 
    
7. <span data-ttu-id="aff33-123">In **Generatore**di topologie selezionare il nodo principale **di Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="aff33-123">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span>
    
8. <span data-ttu-id="aff33-124">Nel menu **azione** fare clic su **Pubblica topologia**.</span><span class="sxs-lookup"><span data-stu-id="aff33-124">From the **Action** menu, click **Publish Topology**.</span></span>
    
9. <span data-ttu-id="aff33-125">Fare clic su **Avanti** per completare il processo di pubblicazione e quindi fare clic su **fine** quando il processo di pubblicazione è stato completato.</span><span class="sxs-lookup"><span data-stu-id="aff33-125">Click **Next** to complete the publishing process, and then click **Finish** when the publishing process has completed.</span></span> 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="aff33-126">Per configurare il server perimetrale legacy come server perimetrale non federativo</span><span class="sxs-lookup"><span data-stu-id="aff33-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1. <span data-ttu-id="aff33-127">Nel riquadro sinistro passare al nodo di installazione legacy e quindi al nodo Pool di **bordi** .</span><span class="sxs-lookup"><span data-stu-id="aff33-127">In the left pane, navigate to the legacy install node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="aff33-128">Fare clic con il pulsante destro del mouse sul server perimetrale e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="aff33-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="aff33-129">Selezionare **generale** nel riquadro sinistro.</span><span class="sxs-lookup"><span data-stu-id="aff33-129">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="aff33-130">Deselezionare la casella di controllo **Abilita federazione per questo pool di bordi (porta 5061)** e scegliere **OK** per chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="aff33-130">Clear the **Enable federation for this Edge pool (port 5061)** check box and select **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="aff33-131">Scegliere **Pubblica topologia**dal menu **azione** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="aff33-131">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="aff33-132">Al termine della **pubblicazione guidata** , fare clic su **fine** per chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="aff33-132">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="aff33-133">Verificare che la Federazione per il server perimetrale legacy sia disabilitata in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="aff33-133">Verify that federation for the legacy Edge server is disabled in Topology Builder.</span></span>
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a><span data-ttu-id="aff33-134">Per configurare i certificati nel server perimetrale legacy</span><span class="sxs-lookup"><span data-stu-id="aff33-134">To configure certificates on the legacy Edge Server</span></span>

1. <span data-ttu-id="aff33-135">Esportare il certificato del proxy di accesso esterno, con la chiave privata, dal server perimetrale legacy.</span><span class="sxs-lookup"><span data-stu-id="aff33-135">Export the external Access Proxy certificate, with the private key, from the legacy Edge Server.</span></span> 
    
2. <span data-ttu-id="aff33-136">In Skype for Business Server 2019 Edge Server e importare il certificato esterno del proxy di accesso dal passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="aff33-136">On the Skype for Business Server 2019 Edge Server, and import the Access Proxy external certificate from the previous step.</span></span>
    
3. <span data-ttu-id="aff33-137">Assegnare il certificato esterno del proxy di accesso all'interfaccia esterna di Skype for Business Server 2019 dell'Edge Server.</span><span class="sxs-lookup"><span data-stu-id="aff33-137">Assign the Access Proxy external certificate to the Skype for Business Server 2019 external interface of the Edge Server.</span></span>
    
4. <span data-ttu-id="aff33-138">Il certificato di interfaccia interno di Skype for Business Server 2019 Edge Server deve essere richiesto da una CA attendibile e assegnato.</span><span class="sxs-lookup"><span data-stu-id="aff33-138">The internal interface certificate of the Skype for Business Server 2019 Edge Server should be requested from a trusted CA and assigned.</span></span> 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="aff33-139">Per modificare la route federativo della versione precedente in uso di Skype for Business Server 2019 Edge Server</span><span class="sxs-lookup"><span data-stu-id="aff33-139">To change the previous version's federation route to use Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="aff33-140">Nel riquadro sinistro di generatore di topologia passare al nodo di **Skype for Business Server 2019** e quindi al nodo **pool di bordi** .</span><span class="sxs-lookup"><span data-stu-id="aff33-140">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="aff33-141">Fare clic con il pulsante destro del mouse sul server perimetrale e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="aff33-141">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="aff33-142">Selezionare **generale** nel riquadro sinistro.</span><span class="sxs-lookup"><span data-stu-id="aff33-142">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="aff33-143">Selezionare la casella di controllo **Abilita federazione per questo pool di bordi (porta 5061)** e quindi fare clic su **OK** per chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="aff33-143">Select the check box for **Enable federation for this Edge pool (port 5061)**, and then click **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="aff33-144">Scegliere **Pubblica topologia**dal menu **azione** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="aff33-144">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="aff33-145">Al termine della **pubblicazione guidata** , fare clic su **fine** per chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="aff33-145">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="aff33-146">Verificare che **Federation (porta 5061)** sia impostato su **Enabled** in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="aff33-146">Verify that **Federation (port 5061)** is set to **Enabled** in Topology Builder.</span></span>
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a><span data-ttu-id="aff33-147">Per aggiornare l'hop successivo della Federazione di Skype for Business Server 2019 Edge Server</span><span class="sxs-lookup"><span data-stu-id="aff33-147">To update Skype for Business Server 2019 Edge Server federation next hop</span></span>

1. <span data-ttu-id="aff33-148">Nel riquadro sinistro di generatore di topologia passare al nodo di **Skype for Business Server 2019** e quindi al nodo **pool di bordi** .</span><span class="sxs-lookup"><span data-stu-id="aff33-148">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="aff33-149">Espandere il nodo, fare clic con il pulsante destro del mouse sul server perimetrale elencato e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="aff33-149">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
3. <span data-ttu-id="aff33-150">Nella pagina **generale** , in **selezione hop successivo**, selezionare nell'elenco a discesa il pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="aff33-150">On the **General** page, under **Next hop selection**, select from the drop-down list the Skype for Business Server 2019 pool.</span></span>
  
4. <span data-ttu-id="aff33-151">Fare clic su **OK** per chiudere la pagina Modifica proprietà.</span><span class="sxs-lookup"><span data-stu-id="aff33-151">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="aff33-152">In **Generatore**di topologie selezionare il nodo principale **di Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="aff33-152">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
6. <span data-ttu-id="aff33-153">Nel menu **azione** fare clic su **Pubblica topologia** e completare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="aff33-153">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span> 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a><span data-ttu-id="aff33-154">Per configurare il percorso multimediale in uscita di Skype for Business Server 2019 Edge Server</span><span class="sxs-lookup"><span data-stu-id="aff33-154">To configure Skype for Business Server 2019 Edge Server outbound media path</span></span>

1. <span data-ttu-id="aff33-155">In Generatore di topologie, nel riquadro sinistro, passare al nodo **Skype for Business Server 2019** e quindi al pool sotto i **server front end Standard Edition** o i **pool Front-End di Enterprise Edition**.</span><span class="sxs-lookup"><span data-stu-id="aff33-155">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>
    
2. <span data-ttu-id="aff33-156">Fare clic con il pulsante destro del mouse sul pool e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="aff33-156">Right-click the pool, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="aff33-157">Nella sezione **associazioni** selezionare la casella **di controllo Associa pool Edge (per componenti multimediali)** .</span><span class="sxs-lookup"><span data-stu-id="aff33-157">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span> 
  
4. <span data-ttu-id="aff33-158">Nella casella a discesa selezionare il server Edge di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="aff33-158">From the drop-down box, select the Skype for Business Server 2019 Edge Server.</span></span>
    
5. <span data-ttu-id="aff33-159">Fare clic su **OK** per chiudere la pagina **modifica proprietà** .</span><span class="sxs-lookup"><span data-stu-id="aff33-159">Click **OK** to close the **Edit Properties** page.</span></span> 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a><span data-ttu-id="aff33-160">Per attivare la Federazione di Skype for Business Server 2019 Edge Server</span><span class="sxs-lookup"><span data-stu-id="aff33-160">To turn on Skype for Business Server 2019 Edge Server federation</span></span>

1. <span data-ttu-id="aff33-161">Nel riquadro sinistro di generatore di topologia passare al nodo di **Skype for Business Server 2019** e quindi al nodo **pool di bordi** .</span><span class="sxs-lookup"><span data-stu-id="aff33-161">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="aff33-162">Espandere il nodo, fare clic con il pulsante destro del mouse sul server perimetrale elencato e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="aff33-162">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="aff33-163">La Federazione può essere abilitata solo per un singolo pool di Edge.</span><span class="sxs-lookup"><span data-stu-id="aff33-163">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="aff33-164">Se si hanno più pool di bordi, selezionarne uno da usare come pool di bordi federativi.</span><span class="sxs-lookup"><span data-stu-id="aff33-164">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span> 
  
3. <span data-ttu-id="aff33-165">Nella pagina **generale** verificare che la casella **di controllo Abilita federazione per questo pool di bordi (porta 5061)** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="aff33-165">On the **General** page, verify that the **Enable federation for this Edge pool (Port 5061)** check box is selected.</span></span> 
  
4. <span data-ttu-id="aff33-166">Fare clic su **OK** per chiudere la pagina Modifica proprietà.</span><span class="sxs-lookup"><span data-stu-id="aff33-166">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="aff33-167">Passare al nodo del sito.</span><span class="sxs-lookup"><span data-stu-id="aff33-167">Navigate to the site node.</span></span> 
    
6. <span data-ttu-id="aff33-168">Fare clic con il pulsante destro del mouse sul sito e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="aff33-168">Right-click the site, and then click **Edit Properties**.</span></span>
    
7. <span data-ttu-id="aff33-169">Nel riquadro sinistro fare clic su **Route federativo**.</span><span class="sxs-lookup"><span data-stu-id="aff33-169">In the left pane, click **Federation route**.</span></span>
    
8. <span data-ttu-id="aff33-170">In **assegnazione della route federativo di sito**selezionare **Abilita federazione SIP**e quindi nell'elenco selezionare il server Edge di Skype for Business Server 2019 elencato.</span><span class="sxs-lookup"><span data-stu-id="aff33-170">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Skype for Business Server 2019 Edge Server listed.</span></span> 
  
9. <span data-ttu-id="aff33-171">Fare clic su **OK** per chiudere la pagina **modifica proprietà** .</span><span class="sxs-lookup"><span data-stu-id="aff33-171">Click **OK** to close the **Edit Properties** page.</span></span> 
    
     <span data-ttu-id="aff33-172">Per le distribuzioni multisito, completare questa procedura in ogni sito.</span><span class="sxs-lookup"><span data-stu-id="aff33-172">For multi-site deployments, complete this procedure at each site.</span></span> 
    
## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="aff33-173">Per pubblicare le modifiche alla configurazione di Edge Server</span><span class="sxs-lookup"><span data-stu-id="aff33-173">To publish Edge Server configuration changes</span></span>

1. <span data-ttu-id="aff33-174">In **Generatore**di topologie selezionare il nodo principale **di Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="aff33-174">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
2. <span data-ttu-id="aff33-175">Nel menu **azione** selezionare **Pubblica topologia** e completare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="aff33-175">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span> 
    
3. <span data-ttu-id="aff33-176">Attendere che la replica di Active Directory si verifichi in tutti i pool della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="aff33-176">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="aff33-177">Potrebbe essere visualizzato il messaggio seguente: **Avviso: la topologia contiene più di un server perimetrale federato. Questo problema può verificarsi durante la migrazione a una versione più recente del prodotto. In questo caso, un solo server perimetrale verrebbe usato attivamente per la Federazione. Verificare che il record SRV DNS esterno punti al server perimetrale corretto. Se si vuole distribuire più Edge Server federativo in modo che sia attivo contemporaneamente, ovvero non uno scenario di migrazione, verificare che tutti i partner federati utilizzino Skype for Business Server. Verificare che il record SRV DNS esterno elenchi tutti i server perimetrali abilitati alla Federazione.**</span><span class="sxs-lookup"><span data-stu-id="aff33-177">You may see the following message: **Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Skype for Business Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.**</span></span> <span data-ttu-id="aff33-178">Questo avviso è previsto e può essere ignorato in modo sicuro.</span><span class="sxs-lookup"><span data-stu-id="aff33-178">This warning is expected and can be safely ignored.</span></span> 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="aff33-179">Per configurare Skype for Business Server 2019 Edge Server</span><span class="sxs-lookup"><span data-stu-id="aff33-179">To configure Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="aff33-180">Porta tutti i server Edge di Skype for Business Server 2019 online.</span><span class="sxs-lookup"><span data-stu-id="aff33-180">Bring all of the Skype for Business Server 2019 Edge Servers online.</span></span> 
    
2. <span data-ttu-id="aff33-181">Aggiornare le regole di routing del firewall esterno o le impostazioni di bilanciamento del carico hardware per inviare il traffico SIP per l'accesso esterno (in genere la porta 443) e la Federazione (in genere la porta 5061) a Skype for Business Server 2019 Edge Server, invece del server perimetrale legacy.</span><span class="sxs-lookup"><span data-stu-id="aff33-181">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Skype for Business Server 2019 Edge Server, instead of the legacy Edge Server.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="aff33-182">Se non si dispone di un servizio di bilanciamento del carico hardware, è necessario aggiornare il record DNS per la Federazione per risolverlo nel nuovo server di Access Edge di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="aff33-182">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Skype for Business Server Access Edge server.</span></span> <span data-ttu-id="aff33-183">Per eseguire questa operazione con interruzioni minime, ridurre il valore di TLL per l'FQDN di Access Edge di Skype for Business Server esterno, in modo che quando il DNS viene aggiornato per puntare al nuovo Edge di Access di Skype for Business Server, la Federazione e l'accesso remoto verranno aggiornati rapidamente.</span><span class="sxs-lookup"><span data-stu-id="aff33-183">To accomplish this with minimal disruption, reduce the TLL value for the external Skype for Business Server Access Edge FQDN so that when DNS is updated to point to the new Skype for Business Server Access Edge, federation and remote access will be updated quickly.</span></span> 
  
3. <span data-ttu-id="aff33-184">Arrestare il **bordo di accesso di Skype for Business Server** da ogni computer Edge Server.</span><span class="sxs-lookup"><span data-stu-id="aff33-184">Stop the **Skype for Business Server Access Edge** from each Edge Server computer.</span></span> 
    
4. <span data-ttu-id="aff33-185">Da ogni computer legacy Edge Server aprire l'applet **Servizi** dagli strumenti di **Amministrazione**.</span><span class="sxs-lookup"><span data-stu-id="aff33-185">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>
    
5. <span data-ttu-id="aff33-186">Nell'elenco servizi individuare **Edge Access per Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="aff33-186">In the services list, find **Skype for Business Server Access Edge**.</span></span>
    
6. <span data-ttu-id="aff33-187">Fare clic con il pulsante destro del mouse sul nome \*\*\*\* dei servizi e quindi scegliere Interrompi per arrestare il servizio.</span><span class="sxs-lookup"><span data-stu-id="aff33-187">Right-click the services name, and then select **Stop** to stop the service.</span></span> 
    
7. <span data-ttu-id="aff33-188">Impostare il tipo di avvio \*\*\*\* su Disabled.</span><span class="sxs-lookup"><span data-stu-id="aff33-188">Set the Startup type to **Disabled**.</span></span> 
    
8. <span data-ttu-id="aff33-189">Fare clic su **OK** per chiudere la finestra **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="aff33-189">Click **OK** to close the **Properties** window.</span></span> 
    


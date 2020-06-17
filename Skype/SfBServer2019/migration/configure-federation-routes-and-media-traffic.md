---
title: Configurare le route di federazione e il traffico multimediale
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
description: La federazione è una relazione di trust tra due o più domini SIP che consente a utenti di organizzazioni distinte di comunicare attraverso i confini della rete. Dopo aver eseguito la migrazione al pool pilota, è necessario eseguire la transizione dalla route di Federazione dei server perimetrali delle versioni precedenti alla route di Federazione dei server perimetrali di Skype for Business Server 2019.
ms.openlocfilehash: 2fafe991b8d09a477d084bdf2081d240e4830589
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754036"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="9720a-104">Configurare le route di federazione e il traffico multimediale</span><span class="sxs-lookup"><span data-stu-id="9720a-104">Configure federation routes and media traffic</span></span>

<span data-ttu-id="9720a-105">La federazione è una relazione di trust tra due o più domini SIP che consente a utenti di organizzazioni distinte di comunicare attraverso i confini della rete.</span><span class="sxs-lookup"><span data-stu-id="9720a-105">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="9720a-106">Dopo aver eseguito la migrazione al pool pilota, è necessario eseguire la transizione dalla route di Federazione dei server perimetrali della versione precedente alla route di Federazione dei server perimetrali di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="9720a-106">After you migrate to your pilot pool, you need to transition from the federation route of your previous version's Edge Servers to the federation route of your Skype for Business Server 2019 Edge Servers.</span></span>
  
<span data-ttu-id="9720a-107">Utilizzare le procedure seguenti per eseguire la transizione della route di Federazione e della route del traffico multimediale dal server perimetrale e dal Director della versione precedente al server perimetrale di Skype for Business Server 2019 per una distribuzione a sito singolo.</span><span class="sxs-lookup"><span data-stu-id="9720a-107">Use the following procedures to transition the federation route and the media traffic route from your previous version's Edge Server and Director to your Skype for Business Server 2019 Edge Server, for a single-site deployment.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9720a-108">La modifica della route di Federazione e della route del traffico multimediale richiede la pianificazione di tempi di inattività di manutenzione per i server Edge di Skype for Business Server 2019 e versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="9720a-108">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Skype for Business Server 2019 and previous version Edge Servers.</span></span> <span data-ttu-id="9720a-109">Il processo di transizione completo implica anche che l'accesso federato non sarà disponibile per l'intera durata dell'interruzione dei servizi.</span><span class="sxs-lookup"><span data-stu-id="9720a-109">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="9720a-110">È consigliabile pianificare l'interruzione dei servizi in un lasso di tempo in cui si prevede un'attività minima da parte degli utenti.</span><span class="sxs-lookup"><span data-stu-id="9720a-110">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="9720a-111">È inoltre consigliabile inviare notifica agli utenti con sufficiente anticipo.</span><span class="sxs-lookup"><span data-stu-id="9720a-111">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="9720a-112">Pianificare adeguatamente l'interruzione dei servizi e fare in modo che le aspettative dell'organizzazione siano appropriate.</span><span class="sxs-lookup"><span data-stu-id="9720a-112">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="9720a-113">Se il server perimetrale legacy è configurato in modo da utilizzare lo stesso nome di dominio completo per il servizio Access Edge, il servizio Web Conferencing Edge e il servizio A/V Edge, le procedure descritte in questa sezione non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="9720a-113">If your legacy Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="9720a-114">Se i servizi perimetrali legacy sono configurati per l'utilizzo dello stesso FQDN, è necessario prima eseguire la migrazione di tutti gli utenti, quindi rimuovere il server perimetrale versioni precedenti prima di abilitare la Federazione sul server perimetrale di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="9720a-114">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users, then decommission the previous versions Edge Server before enabling federation on the Skype for Business Server 2019 Edge Server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="9720a-115">Se la Federazione XMPP viene instradata attraverso un server perimetrale di Skype for Business Server 2019, gli utenti della versione precedente non potranno comunicare con il partner federato XMPP finché tutti gli utenti non sono stati spostati in Skype for Business Server 2019, sono stati configurati i criteri e i certificati XMPP, il partner federato XMPP è stato configurato su Skype for Business Server 2019 e, infine, le voci DNS sono state aggiornate.</span><span class="sxs-lookup"><span data-stu-id="9720a-115">If your XMPP federation is routed through a Skype for Business Server 2019 Edge Server, users on the previous version will not be able to communicate with the XMPP federated partner until all users have been moved to Skype for Business Server 2019, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Skype for Business Server 2019, and, lastly, the DNS entries have been updated.</span></span> 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a><span data-ttu-id="9720a-116">Per rimuovere l'associazione di federazione legacy dai siti di Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="9720a-116">To remove the legacy federation association from Skype for Business Server 2019 sites</span></span>

1. <span data-ttu-id="9720a-117">Nel server front end di Skype for Business Server 2019 aprire la topologia esistente in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="9720a-117">On the Skype for Business Server 2019 Front End server, open the existing topology in Topology Builder.</span></span> 
    
2. <span data-ttu-id="9720a-118">Nel riquadro sinistro, passare al nodo del sito, che si trova direttamente sotto **Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="9720a-118">In the left pane, navigate to the site node, which is located directly below **Skype for Business Server**.</span></span>
    
3. <span data-ttu-id="9720a-119">Fare clic con il pulsante destro del mouse sul sito e quindi scegliere  \*\*Modifica proprietà \*\*.</span><span class="sxs-lookup"><span data-stu-id="9720a-119">Right-click the site, and then click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="9720a-120">Nel riquadro sinistro, selezionare **Route di federazione**.</span><span class="sxs-lookup"><span data-stu-id="9720a-120">In the left pane, select **Federation route**.</span></span> 
    
5. <span data-ttu-id="9720a-121">In **Assegnazione route federazione sito**deselezionare la casella di controllo **Abilita federazione SIP** per disabilitare la route di federazione tramite l'ambiente legacy.</span><span class="sxs-lookup"><span data-stu-id="9720a-121">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy environment.</span></span> 
  
6. <span data-ttu-id="9720a-122">Fare clic su  **OK** per chiudere la pagina Modifica proprietà.</span><span class="sxs-lookup"><span data-stu-id="9720a-122">Click **OK** to close the Edit Properties page.</span></span> 
    
7. <span data-ttu-id="9720a-123">In **Generatore di topologie**selezionare il nodo principale **di Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="9720a-123">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span>
    
8. <span data-ttu-id="9720a-124">Scegliere **Pubblica topologia** dal menu **Azione**.</span><span class="sxs-lookup"><span data-stu-id="9720a-124">From the **Action** menu, click **Publish Topology**.</span></span>
    
9. <span data-ttu-id="9720a-125">Fare clic su **Avanti** per completare il processo di pubblicazione e quindi fare clic su **fine** al termine del processo di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="9720a-125">Click **Next** to complete the publishing process, and then click **Finish** when the publishing process has completed.</span></span> 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="9720a-126">Per configurare il server perimetrale legacy come server perimetrale non federato</span><span class="sxs-lookup"><span data-stu-id="9720a-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1. <span data-ttu-id="9720a-127">Nel riquadro sinistro passare al nodo installazione legacy e quindi al nodo **pool di server perimetrali** .</span><span class="sxs-lookup"><span data-stu-id="9720a-127">In the left pane, navigate to the legacy install node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="9720a-128">Fare clic con il pulsante destro del mouse sul server perimetrale e quindi scegliere **Modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="9720a-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="9720a-129">Selezionare **Generale** nel riquadro sinistro.</span><span class="sxs-lookup"><span data-stu-id="9720a-129">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="9720a-130">Deselezionare la casella di controllo **Abilita federazione per questo pool di server perimetrali (porta 5061)** e selezionare **OK** per chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="9720a-130">Clear the **Enable federation for this Edge pool (port 5061)** check box and select **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="9720a-131">Scegliere **Pubblica topologia** dal menu **Azione** e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="9720a-131">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="9720a-132">Al termine della **Pubblicazione guidata** fare clic su **Fine** per chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="9720a-132">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="9720a-133">Verificare che la Federazione per il server perimetrale legacy sia disabilitata in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="9720a-133">Verify that federation for the legacy Edge server is disabled in Topology Builder.</span></span>
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a><span data-ttu-id="9720a-134">Per configurare i certificati nel server perimetrale legacy</span><span class="sxs-lookup"><span data-stu-id="9720a-134">To configure certificates on the legacy Edge Server</span></span>

1. <span data-ttu-id="9720a-135">Esportare il certificato del proxy di accesso esterno con la chiave privata dal server perimetrale legacy.</span><span class="sxs-lookup"><span data-stu-id="9720a-135">Export the external Access Proxy certificate, with the private key, from the legacy Edge Server.</span></span> 
    
2. <span data-ttu-id="9720a-136">Sul server perimetrale di Skype for Business Server 2019 e importare il certificato esterno del proxy di accesso dal passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="9720a-136">On the Skype for Business Server 2019 Edge Server, and import the Access Proxy external certificate from the previous step.</span></span>
    
3. <span data-ttu-id="9720a-137">Assegnare il certificato esterno del proxy di accesso all'interfaccia esterna di Skype for Business Server 2019 del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="9720a-137">Assign the Access Proxy external certificate to the Skype for Business Server 2019 external interface of the Edge Server.</span></span>
    
4. <span data-ttu-id="9720a-138">Il certificato dell'interfaccia interna del server perimetrale Skype for Business Server 2019 deve essere richiesto da un'autorità di certificazione attendibile e assegnato.</span><span class="sxs-lookup"><span data-stu-id="9720a-138">The internal interface certificate of the Skype for Business Server 2019 Edge Server should be requested from a trusted CA and assigned.</span></span> 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="9720a-139">Per modificare la route di Federazione della versione precedente per l'utilizzo del server perimetrale di Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="9720a-139">To change the previous version's federation route to use Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="9720a-140">In Generatore di topologie, nel riquadro sinistro, passare al nodo di **Skype for Business Server 2019** e quindi al nodo **pool di Edge** .</span><span class="sxs-lookup"><span data-stu-id="9720a-140">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="9720a-141">Fare clic con il pulsante destro del mouse sul server perimetrale e quindi scegliere **Modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="9720a-141">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="9720a-142">Selezionare **Generale** nel riquadro sinistro.</span><span class="sxs-lookup"><span data-stu-id="9720a-142">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="9720a-143">Selezionare la casella di controllo **Abilita federazione per questo pool di server perimetrali (porta 5061)** e quindi fare clic su **OK** per chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="9720a-143">Select the check box for **Enable federation for this Edge pool (port 5061)**, and then click **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="9720a-144">Scegliere **Pubblica topologia** dal menu **Azione** e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="9720a-144">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="9720a-145">Al termine della **Pubblicazione guidata** fare clic su **Fine** per chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="9720a-145">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="9720a-146">Verificare che la **Federazione (porta 5061)** sia impostata su **attivata** in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="9720a-146">Verify that **Federation (port 5061)** is set to **Enabled** in Topology Builder.</span></span>
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a><span data-ttu-id="9720a-147">Per aggiornare l'hop successivo di Federazione del server Edge di Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="9720a-147">To update Skype for Business Server 2019 Edge Server federation next hop</span></span>

1. <span data-ttu-id="9720a-148">In Generatore di topologie, nel riquadro sinistro, passare al nodo di **Skype for Business Server 2019** e quindi al nodo **pool di Edge** .</span><span class="sxs-lookup"><span data-stu-id="9720a-148">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="9720a-149">Espandere il nodo, fare clic con il pulsante destro del mouse sul server perimetrale elencato e quindi scegliere  \*\*Modifica proprietà \*\*.</span><span class="sxs-lookup"><span data-stu-id="9720a-149">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
3. <span data-ttu-id="9720a-150">In **selezione hop successivo**nella pagina **generale** selezionare dall'elenco a discesa il pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="9720a-150">On the **General** page, under **Next hop selection**, select from the drop-down list the Skype for Business Server 2019 pool.</span></span>
  
4. <span data-ttu-id="9720a-151">Fare clic su  **OK** per chiudere la pagina Modifica proprietà.</span><span class="sxs-lookup"><span data-stu-id="9720a-151">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="9720a-152">In **Generatore di topologie**selezionare il nodo principale **di Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="9720a-152">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
6. <span data-ttu-id="9720a-153">Scegliere **Pubblica topologia** dal menu **Azione** e completare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="9720a-153">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span> 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a><span data-ttu-id="9720a-154">Per configurare il percorso multimediale in uscita di Skype for Business Server 2019 Edge Server</span><span class="sxs-lookup"><span data-stu-id="9720a-154">To configure Skype for Business Server 2019 Edge Server outbound media path</span></span>

1. <span data-ttu-id="9720a-155">In Generatore di topologie, nel riquadro sinistro, passare al nodo **Skype for Business Server 2019** e quindi al pool al di sotto di **Standard Edition Front End Server** o **pool Enterprise Edition front end**.</span><span class="sxs-lookup"><span data-stu-id="9720a-155">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>
    
2. <span data-ttu-id="9720a-156">Fare clic con il pulsante destro del mouse sul pool e quindi scegliere  \*\*Modifica proprietà \*\*.</span><span class="sxs-lookup"><span data-stu-id="9720a-156">Right-click the pool, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="9720a-157">Nella sezione  \*\*Associazioni \*\* selezionare la casella di controllo  \*\*Associa pool di server perimetrali (per componenti multimediali) \*\*.</span><span class="sxs-lookup"><span data-stu-id="9720a-157">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span> 
  
4. <span data-ttu-id="9720a-158">Nella casella a discesa selezionare il server perimetrale di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="9720a-158">From the drop-down box, select the Skype for Business Server 2019 Edge Server.</span></span>
    
5. <span data-ttu-id="9720a-159">Fare clic su  \*\*OK \*\* per chiudere la pagina  \*\*Modifica proprietà \*\*.</span><span class="sxs-lookup"><span data-stu-id="9720a-159">Click **OK** to close the **Edit Properties** page.</span></span> 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a><span data-ttu-id="9720a-160">Per abilitare la Federazione del server perimetrale di Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="9720a-160">To turn on Skype for Business Server 2019 Edge Server federation</span></span>

1. <span data-ttu-id="9720a-161">In Generatore di topologie, nel riquadro sinistro, passare al nodo di **Skype for Business Server 2019** e quindi al nodo **pool di Edge** .</span><span class="sxs-lookup"><span data-stu-id="9720a-161">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="9720a-162">Espandere il nodo, fare clic con il pulsante destro del mouse sul server perimetrale elencato e quindi scegliere  \*\*Modifica proprietà \*\*.</span><span class="sxs-lookup"><span data-stu-id="9720a-162">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="9720a-163">La Federazione può essere abilitata solo per un singolo pool di server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="9720a-163">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="9720a-164">In presenza di più pool di server perimetrali, selezionarne uno da utilizzare come pool di server perimetrali federati.</span><span class="sxs-lookup"><span data-stu-id="9720a-164">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span> 
  
3. <span data-ttu-id="9720a-165">Nella pagina **generale** verificare che sia selezionata la casella **di controllo Abilita federazione per il pool di server perimetrali (porta 5061)** .</span><span class="sxs-lookup"><span data-stu-id="9720a-165">On the **General** page, verify that the **Enable federation for this Edge pool (Port 5061)** check box is selected.</span></span> 
  
4. <span data-ttu-id="9720a-166">Fare clic su  **OK** per chiudere la pagina Modifica proprietà.</span><span class="sxs-lookup"><span data-stu-id="9720a-166">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="9720a-167">Passare al nodo del sito.</span><span class="sxs-lookup"><span data-stu-id="9720a-167">Navigate to the site node.</span></span> 
    
6. <span data-ttu-id="9720a-168">Fare clic con il pulsante destro del mouse sul sito e quindi scegliere  \*\*Modifica proprietà \*\*.</span><span class="sxs-lookup"><span data-stu-id="9720a-168">Right-click the site, and then click **Edit Properties**.</span></span>
    
7. <span data-ttu-id="9720a-169">Nel riquadro sinistro fare clic su  \*\*Route di federazione \*\*.</span><span class="sxs-lookup"><span data-stu-id="9720a-169">In the left pane, click **Federation route**.</span></span>
    
8. <span data-ttu-id="9720a-170">In **Assegnazione route federazione sito**selezionare **Abilita federazione SIP**e quindi selezionare il server perimetrale di Skype for Business Server 2019 nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="9720a-170">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Skype for Business Server 2019 Edge Server listed.</span></span> 
  
9. <span data-ttu-id="9720a-171">Fare clic su  \*\*OK \*\* per chiudere la pagina  \*\*Modifica proprietà \*\*.</span><span class="sxs-lookup"><span data-stu-id="9720a-171">Click **OK** to close the **Edit Properties** page.</span></span> 
    
     <span data-ttu-id="9720a-172">Nel caso di distribuzioni multisito, eseguire questa procedura in ogni sito.</span><span class="sxs-lookup"><span data-stu-id="9720a-172">For multi-site deployments, complete this procedure at each site.</span></span> 
    
## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="9720a-173">Per pubblicare le modifiche di configurazione del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9720a-173">To publish Edge Server configuration changes</span></span>

1. <span data-ttu-id="9720a-174">In **Generatore di topologie**selezionare il nodo principale **di Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="9720a-174">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
2. <span data-ttu-id="9720a-175">Scegliere **Pubblica topologia** dal menu **Azione** e completare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="9720a-175">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span> 
    
3. <span data-ttu-id="9720a-176">Attendere il completamento della replica di Active Directory in tutti i pool della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="9720a-176">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9720a-177">È possibile che venga visualizzato il messaggio seguente: **Avviso: la topologia contiene più server perimetrali federati. Ciò può verificarsi durante la migrazione a una versione più recente del prodotto. In tal caso, solo un server perimetrale verrebbe utilizzato attivamente per la Federazione. Verificare che il record SRV DNS esterno punti al server perimetrale corretto. Se si desidera distribuire più server perimetrale federativo affinché siano attivi contemporaneamente, ovvero non uno scenario di migrazione, verificare che tutti i partner federati utilizzino Skype for Business Server. Verificare che il record SRV DNS esterno elenchi tutti i server perimetrali abilitati per la Federazione.**</span><span class="sxs-lookup"><span data-stu-id="9720a-177">You may see the following message: **Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Skype for Business Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.**</span></span> <span data-ttu-id="9720a-178">Si tratta di un avviso previsto che può essere tranquillamente ignorato.</span><span class="sxs-lookup"><span data-stu-id="9720a-178">This warning is expected and can be safely ignored.</span></span> 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="9720a-179">Per configurare il server perimetrale di Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="9720a-179">To configure Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="9720a-180">Portare online tutti i server Edge di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="9720a-180">Bring all of the Skype for Business Server 2019 Edge Servers online.</span></span> 
    
2. <span data-ttu-id="9720a-181">Aggiornare le regole di routing del firewall esterno o le impostazioni del servizio di bilanciamento del carico hardware in modo da inviare il traffico SIP per l'accesso esterno (in genere la porta 443) e la Federazione (in genere la porta 5061) al server perimetrale di Skype for Business Server 2019, anziché al server perimetrale legacy.</span><span class="sxs-lookup"><span data-stu-id="9720a-181">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Skype for Business Server 2019 Edge Server, instead of the legacy Edge Server.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9720a-182">Se non si dispone di un dispositivo di bilanciamento del carico hardware, è necessario aggiornare il record DNS a per la Federazione per risolvere il nuovo server Access Edge di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9720a-182">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Skype for Business Server Access Edge server.</span></span> <span data-ttu-id="9720a-183">Per ottenere questo risultato con interruzioni minime, ridurre il valore TLL per l'FQDN del server di accesso esterno di Skype for business, in modo che quando DNS viene aggiornato per puntare al nuovo Edge di accesso di Skype for Business Server, la Federazione e l'accesso remoto vengano aggiornati rapidamente.</span><span class="sxs-lookup"><span data-stu-id="9720a-183">To accomplish this with minimal disruption, reduce the TLL value for the external Skype for Business Server Access Edge FQDN so that when DNS is updated to point to the new Skype for Business Server Access Edge, federation and remote access will be updated quickly.</span></span> 
  
3. <span data-ttu-id="9720a-184">Arrestare il **server perimetrale di accesso di Skype for business** da ogni computer server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="9720a-184">Stop the **Skype for Business Server Access Edge** from each Edge Server computer.</span></span> 
    
4. <span data-ttu-id="9720a-185">Da ogni computer server perimetrale legacy, aprire l'applet **Servizi** dagli **strumenti di amministrazione**.</span><span class="sxs-lookup"><span data-stu-id="9720a-185">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>
    
5. <span data-ttu-id="9720a-186">Nell'elenco dei servizi, trova **Access Edge di Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="9720a-186">In the services list, find **Skype for Business Server Access Edge**.</span></span>
    
6. <span data-ttu-id="9720a-187">Fare clic con il pulsante destro del mouse sul nome del servizio e quindi scegliere **Arresta** per arrestarlo.</span><span class="sxs-lookup"><span data-stu-id="9720a-187">Right-click the services name, and then select **Stop** to stop the service.</span></span> 
    
7. <span data-ttu-id="9720a-188">Impostare il tipo di avvio su **Disabilitato**.</span><span class="sxs-lookup"><span data-stu-id="9720a-188">Set the Startup type to **Disabled**.</span></span> 
    
8. <span data-ttu-id="9720a-189">Fare clic su  \*\*OK \*\* per chiudere la finestra \*\*Proprietà \*\*.</span><span class="sxs-lookup"><span data-stu-id="9720a-189">Click **OK** to close the **Properties** window.</span></span> 
    


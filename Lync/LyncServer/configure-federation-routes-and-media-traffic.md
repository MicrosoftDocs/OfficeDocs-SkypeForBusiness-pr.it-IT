---
title: Configurare le route di federazione e il traffico multimediale
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: 8b2f5f81-a955-4ad1-ad74-397322ff9521
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688121(v=OCS.15)
ms:contentKeyID: 49733720
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b07e0bfe62fe6d09521d1f9d5dc2d84aa975d5e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503353"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="98c3e-102">Configurare le route di federazione e il traffico multimediale</span><span class="sxs-lookup"><span data-stu-id="98c3e-102">Configure federation routes and media traffic</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98c3e-103">_**Ultimo argomento modificato:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="98c3e-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="98c3e-104">La federazione è una relazione di trust tra due o più domini SIP che consente a utenti di organizzazioni distinte di comunicare attraverso i confini della rete.</span><span class="sxs-lookup"><span data-stu-id="98c3e-104">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="98c3e-105">Dopo aver eseguito la migrazione al pool pilota di Lync Server 2013, è necessario eseguire la transizione dalla route di Federazione dei server perimetrali di Lync Server 2010 alla route di Federazione dei server perimetrali di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="98c3e-105">After you migrate to your Lync Server 2013 pilot pool, you need to transition from the federation route of your Lync Server 2010 Edge Servers to the federation route of your Lync Server 2013 Edge Servers.</span></span>

<span data-ttu-id="98c3e-106">Utilizzare le procedure seguenti per la transizione della route di Federazione e della route del traffico multimediale dal server perimetrale e dal Director di Lync Server 2010 al server perimetrale di Lync Server 2013, per una distribuzione a sito singolo.</span><span class="sxs-lookup"><span data-stu-id="98c3e-106">Use the following procedures to transition the federation route and the media traffic route from your Lync Server 2010 Edge Server and Director to your Lync Server 2013 Edge Server, for a single-site deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="98c3e-107">La modifica della route di Federazione e della route del traffico multimediale richiede la pianificazione di tempi di inattività di manutenzione per i server perimetrali di Lync Server 2013 e Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="98c3e-107">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Lync Server 2013 and Lync Server 2010 Edge Servers.</span></span> <span data-ttu-id="98c3e-108">Il processo di transizione completo implica anche che l'accesso federato non sarà disponibile per l'intera durata dell'interruzione dei servizi.</span><span class="sxs-lookup"><span data-stu-id="98c3e-108">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="98c3e-109">È consigliabile pianificare l'interruzione dei servizi in un lasso di tempo in cui si prevede un'attività minima da parte degli utenti.</span><span class="sxs-lookup"><span data-stu-id="98c3e-109">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="98c3e-110">È inoltre consigliabile inviare notifica agli utenti con sufficiente anticipo.</span><span class="sxs-lookup"><span data-stu-id="98c3e-110">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="98c3e-111">Pianificare adeguatamente l'interruzione dei servizi e fare in modo che le aspettative dell'organizzazione siano appropriate.</span><span class="sxs-lookup"><span data-stu-id="98c3e-111">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="98c3e-112">Se il server perimetrale Lync Server 2010 legacy è configurato per utilizzare lo stesso nome di dominio completo per il servizio Access Edge, il servizio Web Conferencing Edge e il servizio A/V Edge, le procedure descritte in questa sezione non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="98c3e-112">If your legacy Lync Server 2010 Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="98c3e-113">Se i servizi perimetrali legacy sono configurati per l'utilizzo dello stesso FQDN, è necessario prima eseguire la migrazione di tutti gli utenti da Lync Server 2010 a Lync Server 2013, quindi rimuovere il server perimetrale di Lync Server 2010 prima di abilitare la Federazione sul server perimetrale di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="98c3e-113">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users from Lync Server 2010 to Lync Server 2013, then decommission the Lync Server 2010 Edge Server before enabling federation on the Lync Server 2013 Edge Server.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="98c3e-114">Se la Federazione XMPP viene instradata attraverso un server perimetrale di Lync Server 2013, gli utenti di Lync Server 2010 legacy non saranno in grado di comunicare con il partner federato XMPP finché tutti gli utenti non sono stati spostati in Lync Server 2013, sono stati configurati i criteri e i certificati XMPP, il partner federato XMPP è stato configurato su Lync Server 2013 e infine le voci DNS sono state aggiornate</span><span class="sxs-lookup"><span data-stu-id="98c3e-114">If your XMPP federation is routed through a Lync Server 2013 Edge Server, legacy Lync Server 2010 users will not be able to communicate with the XMPP federated partner until all users have been moved to Lync Server 2013, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Lync Server 2013, and lastly the DNS entries have been updated.</span></span>



</div>

<div>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a><span data-ttu-id="98c3e-115">Per rimuovere l'associazione di federazione legacy dai siti di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98c3e-115">To remove the legacy federation association from Lync Server 2013 sites</span></span>

1.  <span data-ttu-id="98c3e-116">Nel server front end di Lync Server 2013 aprire la topologia esistente in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="98c3e-116">On the Lync Server 2013 Front End server, open the existing topology in Topology Builder.</span></span>

2.  <span data-ttu-id="98c3e-117">Nel riquadro sinistro, passare la nodo del sito direttamente sotto **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="98c3e-117">In the left pane, navigate to the site node, which is located directly below **Lync Server**.</span></span>

3.  <span data-ttu-id="98c3e-118">Fare clic con il pulsante destro del mouse sul sito e quindi scegliere \*\*Modifica proprietà \*\*.</span><span class="sxs-lookup"><span data-stu-id="98c3e-118">Right-click the site and then click **Edit Properties**.</span></span>

4.  <span data-ttu-id="98c3e-119">Nel riquadro sinistro, selezionare **Route di federazione**.</span><span class="sxs-lookup"><span data-stu-id="98c3e-119">In the left pane, select **Federation route**.</span></span>

5.  <span data-ttu-id="98c3e-120">In **Assegnazione route federazione sito**deselezionare la casella di controllo **Abilita federazione SIP** per disabilitare la route di federazione tramite l'ambiente legacy di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="98c3e-120">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy Lync Server 2010 environment.</span></span>
    
    <span data-ttu-id="98c3e-121">![Finestra di dialogo Modifica proprietà, pagina Route di Federazione](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "Finestra di dialogo Modifica proprietà, pagina Route di Federazione")</span><span class="sxs-lookup"><span data-stu-id="98c3e-121">![Edit Properties dialog, Federation route page](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "Edit Properties dialog, Federation route page")</span></span>

6.  <span data-ttu-id="98c3e-122">Fare clic su  **OK** per chiudere la pagina Modifica proprietà.</span><span class="sxs-lookup"><span data-stu-id="98c3e-122">Click **OK** to close the Edit Properties page.</span></span>

7.  <span data-ttu-id="98c3e-123">In **Generatore di topologie** selezionare il nodo di primo livello **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="98c3e-123">From **Topology Builder**, select the top node **Lync Server**.</span></span>

8.  <span data-ttu-id="98c3e-124">Scegliere **Pubblica topologia** dal menu **Azione**.</span><span class="sxs-lookup"><span data-stu-id="98c3e-124">From the **Action** menu, click **Publish Topology**.</span></span>

9.  <span data-ttu-id="98c3e-125">Fare clic su **Avanti** per completare il processo di pubblicazione e quindi fare clic su **Fine** al termine del processo.</span><span class="sxs-lookup"><span data-stu-id="98c3e-125">Click **Next** to complete the publishing process and then click **Finish** when the publishing process has completed.</span></span>

</div>

<div>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="98c3e-126">Per configurare il server perimetrale legacy come server perimetrale non federato</span><span class="sxs-lookup"><span data-stu-id="98c3e-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1.  <span data-ttu-id="98c3e-127">Nel riquadro sinistro, passare al nodo **Lync Server 2010** e quindi al nodo **Pool di server perimetrali**.</span><span class="sxs-lookup"><span data-stu-id="98c3e-127">In the left pane, navigate to the **Lync Server 2010** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="98c3e-128">Fare clic con il pulsante destro del mouse sul server perimetrale e quindi scegliere **Modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="98c3e-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="98c3e-129">Selezionare **Generale** nel riquadro sinistro.</span><span class="sxs-lookup"><span data-stu-id="98c3e-129">Select **General** in the left pane.</span></span>

4.  <span data-ttu-id="98c3e-130">Deselezionare la casella di controllo **Abilita federazione per pool di server perimetrali (porta 5061)** e fare clic su **OK** per chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="98c3e-130">Clear the **Enable federation for this Edge pool (port 5061)** check box entry and select **OK** to close the page.</span></span>
    
    <span data-ttu-id="98c3e-131">![Modifica proprietà, generale, deseleziona Abilita federazione](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "Modifica proprietà, generale, deseleziona Abilita federazione")</span><span class="sxs-lookup"><span data-stu-id="98c3e-131">![Edit Properties, General, clear Enable federation](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "Edit Properties, General, clear Enable federation")</span></span>

5.  <span data-ttu-id="98c3e-132">Scegliere **Pubblica topologia** dal menu **Azione** e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="98c3e-132">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

6.  <span data-ttu-id="98c3e-133">Al termine della **Pubblicazione guidata** fare clic su **Fine** per chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="98c3e-133">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

7.  <span data-ttu-id="98c3e-134">Verificare che la federazione del server perimetrale legacy sia disabilitata.</span><span class="sxs-lookup"><span data-stu-id="98c3e-134">Verify federation for the legacy Edge server is disabled.</span></span>
    
    <span data-ttu-id="98c3e-135">![Generatore di topologie, pool di server perimetrali, Federazione disabilitata](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "Generatore di topologie, pool di server perimetrali, Federazione disabilitata")</span><span class="sxs-lookup"><span data-stu-id="98c3e-135">![Topology Builder, Edge pool, federation disabled](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "Topology Builder, Edge pool, federation disabled")</span></span>

</div>

<div>

## <a name="to-configure-certificates-on-the-lync-server-2010-edge-server"></a><span data-ttu-id="98c3e-136">Per configurare i certificati nel server perimetrale di Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="98c3e-136">To configure certificates on the Lync Server 2010 Edge Server</span></span>

1.  <span data-ttu-id="98c3e-137">Esportare il certificato del proxy di accesso esterno con la chiave privata dal server perimetrale Lync Server 2010 legacy.</span><span class="sxs-lookup"><span data-stu-id="98c3e-137">Export the external Access Proxy certificate, with the private key, from the legacy Lync Server 2010 Edge Server.</span></span>

2.  <span data-ttu-id="98c3e-138">Nel server perimetrale di Lync Server 2013 importare il certificato esterno del proxy di accesso dal passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="98c3e-138">On the Lync Server 2013 Edge Server, import the Access Proxy external certificate from the previous step.</span></span>

3.  <span data-ttu-id="98c3e-139">Assegnare il certificato esterno del proxy di accesso all'interfaccia esterna di Lync Server 2013 del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="98c3e-139">Assign the Access Proxy external certificate to the Lync Server 2013 external interface of the Edge Server.</span></span>

4.  <span data-ttu-id="98c3e-140">Il certificato dell'interfaccia interna del server perimetrale di Lync Server 2013 deve essere richiesto da un'autorità di certificazione attendibile e assegnato.</span><span class="sxs-lookup"><span data-stu-id="98c3e-140">The internal interface certificate of the Lync Server 2013 Edge Server should be requested from a trusted CA and assigned.</span></span>

</div>

<div>

## <a name="to-change-lync-server-2010-federation-route-to-use-lync-server-2013-edge-server"></a><span data-ttu-id="98c3e-141">Per modificare la route di federazione di Lync Server 2010 per l'uso del server perimetrale di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98c3e-141">To change Lync Server 2010 federation route to use Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="98c3e-142">Nel riquadro sinistro del Generatore di topologie, passare al nodo \*\*Lync Server 2013 \*\* e quindi al nodo **Pool di server perimetrali**.</span><span class="sxs-lookup"><span data-stu-id="98c3e-142">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="98c3e-143">Fare clic con il pulsante destro del mouse sul server perimetrale e quindi scegliere **Modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="98c3e-143">Right-click the Edge server, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="98c3e-144">Selezionare **Generale** nel riquadro sinistro.</span><span class="sxs-lookup"><span data-stu-id="98c3e-144">Select **General** in the left pane.</span></span>

4.  <span data-ttu-id="98c3e-145">Selezionare la casella di controllo **Abilita federazione per pool di server perimetrali (porta 5061)** e quindi fare clic su **OK** per chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="98c3e-145">Select the check box entry for **Enable federation for this Edge pool (port 5061)** and then click **OK** to close the page.</span></span>
    
    <span data-ttu-id="98c3e-146">![Finestra di dialogo Modifica proprietà, pagina generale](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Finestra di dialogo Modifica proprietà, pagina generale")</span><span class="sxs-lookup"><span data-stu-id="98c3e-146">![Edit Properties dialog, General page](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Edit Properties dialog, General page")</span></span>

5.  <span data-ttu-id="98c3e-147">Scegliere **Pubblica topologia** dal menu **Azione** e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="98c3e-147">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

6.  <span data-ttu-id="98c3e-148">Al termine della **Pubblicazione guidata** fare clic su **Fine** per chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="98c3e-148">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

7.  <span data-ttu-id="98c3e-149">Verificare che **Federazione (porta 5061)** sia impostata su **Abilitata**.</span><span class="sxs-lookup"><span data-stu-id="98c3e-149">Verify **Federation (port 5061)** is set to **Enabled**.</span></span>
    
    <span data-ttu-id="98c3e-150">![Generatore di topologie, pool di server perimetrali, Federazione abilitata](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "Generatore di topologie, pool di server perimetrali, Federazione abilitata")</span><span class="sxs-lookup"><span data-stu-id="98c3e-150">![Topology Builder, Edge pool, Federation enabled](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "Topology Builder, Edge pool, Federation enabled")</span></span>

</div>

<div>

## <a name="to-update-lync-server-2013-edge-server-federation-next-hop"></a><span data-ttu-id="98c3e-151">Per aggiornare l'hop successivo di federazione del server perimetrale di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98c3e-151">To update Lync Server 2013 Edge Server federation next hop</span></span>

1.  <span data-ttu-id="98c3e-152">Nel riquadro sinistro del Generatore di topologie, passare al nodo \*\*Lync Server 2013 \*\* e quindi al nodo **Pool di server perimetrali**.</span><span class="sxs-lookup"><span data-stu-id="98c3e-152">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="98c3e-153">Espandere il nodo, fare clic con il pulsante destro del mouse sul server perimetrale elencato e quindi scegliere  \*\*Modifica proprietà \*\*.</span><span class="sxs-lookup"><span data-stu-id="98c3e-153">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="98c3e-154">In **selezione hop successivo**nella pagina **generale** selezionare nell'elenco a discesa il pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="98c3e-154">On the **General** page, under **Next hop selection**, select from the drop-down list the Lync Server 2013  pool.</span></span>
    
    <span data-ttu-id="98c3e-155">![Finestra di dialogo Modifica proprietà, pagina hop successivo](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "Finestra di dialogo Modifica proprietà, pagina hop successivo")</span><span class="sxs-lookup"><span data-stu-id="98c3e-155">![Edit Properties dialog, Next hop page](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "Edit Properties dialog, Next hop page")</span></span>

4.  <span data-ttu-id="98c3e-156">Fare clic su  **OK** per chiudere la pagina Modifica proprietà.</span><span class="sxs-lookup"><span data-stu-id="98c3e-156">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="98c3e-157">In **Generatore di topologie**selezionare il nodo di primo livello **Lync Server** .</span><span class="sxs-lookup"><span data-stu-id="98c3e-157">From **Topology Builder**, select the top node **Lync Server** .</span></span>

6.  <span data-ttu-id="98c3e-158">Scegliere **Pubblica topologia** dal menu **Azione** e completare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="98c3e-158">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a><span data-ttu-id="98c3e-159">Per configurare il percorso del contenuto multimediale in uscita dei server perimetrali Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98c3e-159">To configure Lync Server 2013 Edge Server outbound media path</span></span>

1.  <span data-ttu-id="98c3e-160">In Generatore di topologie, nel riquadro sinistro, passare al nodo **Lync Server 2013** e quindi al pool al di sotto di **Standard Edition Front End Server** o **pool Enterprise Edition front end**.</span><span class="sxs-lookup"><span data-stu-id="98c3e-160">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>

2.  <span data-ttu-id="98c3e-161">Fare clic con il pulsante destro del mouse sul pool e quindi scegliere  \*\*Modifica proprietà \*\*.</span><span class="sxs-lookup"><span data-stu-id="98c3e-161">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="98c3e-162">Nella sezione  \*\*Associazioni \*\* selezionare la casella di controllo  \*\*Associa pool di server perimetrali (per componenti multimediali) \*\*.</span><span class="sxs-lookup"><span data-stu-id="98c3e-162">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span>
    
    <span data-ttu-id="98c3e-163">![Modifica proprietà, generale, associa pool di server perimetrali](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "Modifica proprietà, generale, associa pool di server perimetrali")</span><span class="sxs-lookup"><span data-stu-id="98c3e-163">![Edit Properties, General, Associate Edge pool](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "Edit Properties, General, Associate Edge pool")</span></span>

4.  <span data-ttu-id="98c3e-164">Nella casella a discesa selezionare il server perimetrale di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="98c3e-164">From the drop down box, select the Lync Server 2013 Edge Server.</span></span>

5.  <span data-ttu-id="98c3e-165">Fare clic su  \*\*OK \*\* per chiudere la pagina  \*\*Modifica proprietà \*\*.</span><span class="sxs-lookup"><span data-stu-id="98c3e-165">Click **OK** to close the **Edit Properties** page.</span></span>

</div>

<div>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a><span data-ttu-id="98c3e-166">Per abilitare la federazione del server perimetrale di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98c3e-166">To turn on Lync Server 2013 Edge Server federation</span></span>

1.  <span data-ttu-id="98c3e-167">Nel riquadro sinistro del Generatore di topologie, passare al nodo \*\*Lync Server 2013 \*\* e quindi al nodo **Pool di server perimetrali**.</span><span class="sxs-lookup"><span data-stu-id="98c3e-167">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="98c3e-168">Espandere il nodo, fare clic con il pulsante destro del mouse sul server perimetrale elencato e quindi scegliere  \*\*Modifica proprietà \*\*.</span><span class="sxs-lookup"><span data-stu-id="98c3e-168">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="98c3e-169">La Federazione può essere abilitata solo per un singolo pool di server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="98c3e-169">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="98c3e-170">In presenza di più pool di server perimetrali, selezionarne uno da utilizzare come pool di server perimetrali federati.</span><span class="sxs-lookup"><span data-stu-id="98c3e-170">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span>

    
    </div>

3.  <span data-ttu-id="98c3e-171">Nella pagina **Generale** verificare che l'impostazione **Abilita federazione per pool di server perimetrali (porta 5061)** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="98c3e-171">On the **General** page, verify the **Enable federation for this Edge pool (Port 5061)** setting is checked.</span></span>
    
    <span data-ttu-id="98c3e-172">![Finestra di dialogo Modifica proprietà, pagina generale](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Finestra di dialogo Modifica proprietà, pagina generale")</span><span class="sxs-lookup"><span data-stu-id="98c3e-172">![Edit Properties dialog, General page](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Edit Properties dialog, General page")</span></span>

4.  <span data-ttu-id="98c3e-173">Fare clic su  **OK** per chiudere la pagina Modifica proprietà.</span><span class="sxs-lookup"><span data-stu-id="98c3e-173">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="98c3e-174">Passare quindi al nodo del sito.</span><span class="sxs-lookup"><span data-stu-id="98c3e-174">Next, navigate to the site node.</span></span>

6.  <span data-ttu-id="98c3e-175">Fare clic con il pulsante destro del mouse sul sito e quindi scegliere  \*\*Modifica proprietà \*\*.</span><span class="sxs-lookup"><span data-stu-id="98c3e-175">Right-click the site, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="98c3e-176">Nel riquadro sinistro fare clic su  \*\*Route di federazione \*\*.</span><span class="sxs-lookup"><span data-stu-id="98c3e-176">In the left pane, click **Federation route**.</span></span>

8.  <span data-ttu-id="98c3e-177">In **Assegnazione route federazione sito**selezionare **Abilita federazione SIP**e quindi nell'elenco selezionare il server perimetrale di Lync Server 2013 elencato.</span><span class="sxs-lookup"><span data-stu-id="98c3e-177">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Lync Server 2013 Edge Server listed.</span></span>
    
    <span data-ttu-id="98c3e-178">![Modifica proprietà, pagina Route di Federazione](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "Modifica proprietà, pagina Route di Federazione")</span><span class="sxs-lookup"><span data-stu-id="98c3e-178">![Edit Properties, Federation route page](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "Edit Properties, Federation route page")</span></span>

9.  <span data-ttu-id="98c3e-179">Fare clic su  \*\*OK \*\* per chiudere la pagina  \*\*Modifica proprietà \*\*.</span><span class="sxs-lookup"><span data-stu-id="98c3e-179">Click **OK** to close the **Edit Properties** page.</span></span>
    
    <span data-ttu-id="98c3e-180">Nel caso di distribuzioni multisito, eseguire questa procedura in ogni sito.</span><span class="sxs-lookup"><span data-stu-id="98c3e-180">For multi-site deployments, complete this procedure at each site.</span></span>

</div>

<div>

## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="98c3e-181">Per pubblicare le modifiche di configurazione del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="98c3e-181">To publish Edge Server configuration changes</span></span>

1.  <span data-ttu-id="98c3e-182">In **Generatore di topologie**selezionare il nodo di primo livello **Lync Server** .</span><span class="sxs-lookup"><span data-stu-id="98c3e-182">From **Topology Builder**, select the top node **Lync Server** .</span></span>

2.  <span data-ttu-id="98c3e-183">Scegliere **Pubblica topologia** dal menu **Azione** e completare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="98c3e-183">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

3.  <span data-ttu-id="98c3e-184">Attendere il completamento della replica di Active Directory in tutti i pool della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="98c3e-184">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="98c3e-185">Potrebbe essere visualizzato il messaggio seguente:</span><span class="sxs-lookup"><span data-stu-id="98c3e-185">You may see the following message:</span></span><BR><span data-ttu-id="98c3e-186"><STRONG>Avviso: la topologia contiene più di un server perimetrale federato. Questa situazione può verificarsi durante la migrazione a una versione successiva del prodotto. In questo caso, per la federazione viene utilizzato attivamente un solo server perimetrale. Verificare che il record SRV DNS punti al server perimetrale corretto. Se si desidera distribuire più server perimetrali federati in modo che siano attivi contemporaneamente (ovvero non in uno scenario di migrazione), verificare che tutti i partner federati utilizzino Lync Server e che il record SRV DNS esterno elenchi tutti i server perimetrali abilitati per la federazione</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="98c3e-186"><STRONG>Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Lync Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.</STRONG></span></span><BR><span data-ttu-id="98c3e-187">Si tratta di un avviso previsto che può essere tranquillamente ignorato.</span><span class="sxs-lookup"><span data-stu-id="98c3e-187">This warning is expected and can be safely ignored.</span></span>

    
    </div>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server"></a><span data-ttu-id="98c3e-188">Per configurare il server perimetrale Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98c3e-188">To configure Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="98c3e-189">Portare online tutti i server perimetrali di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="98c3e-189">Bring all of the Lync Server 2013 Edge Servers online.</span></span>

2.  <span data-ttu-id="98c3e-190">Aggiornare le regole di routing del firewall esterno o le impostazioni del servizio di bilanciamento del carico hardware in modo da inviare il traffico SIP per l'accesso esterno (in genere la porta 443) e la Federazione (in genere la porta 5061) al server perimetrale di Lync Server 2013, anziché al server perimetrale legacy.</span><span class="sxs-lookup"><span data-stu-id="98c3e-190">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Lync Server 2013 Edge Server, instead of the legacy Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="98c3e-p105">Se non si dispone di un servizio di bilanciamento del carico hardware, è necessario aggiornare il record A DNS per la federazione in modo che venga risolto nel nuovo server Access Edge Server di Lync Server. Per eseguire questa operazione causando una minima interruzione del servizio, ridurre il valore TLL per l'FQDN Access Edge di Lync Server esterno in modo che se il DNS viene aggiornato per puntare al nuovo Access Edge Server di Lync Server, la federazione e l'accesso remoto vengano aggiornati rapidamente.</span><span class="sxs-lookup"><span data-stu-id="98c3e-p105">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Lync Server Access Edge server. To accomplish this with minimum disruption, reduce the TLL value for the external Lync Server Access Edge FQDN so that when DNS is updated to point to the new Lync Server Access Edge, federation and remote access will be updated quickly.</span></span>

    
    </div>

3.  <span data-ttu-id="98c3e-193">Successivamente, arrestare **Lync Server Access Edge** da ogni computer server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="98c3e-193">Next, stop the **Lync Server Access Edge** from each Edge Server computer.</span></span>

4.  <span data-ttu-id="98c3e-194">Da ogni computer server perimetrale legacy, aprire l'applet **Servizi** dagli **strumenti di amministrazione**.</span><span class="sxs-lookup"><span data-stu-id="98c3e-194">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>

5.  <span data-ttu-id="98c3e-195">Nell'elenco di servizi, individuare **Lync Server Access Edge**.</span><span class="sxs-lookup"><span data-stu-id="98c3e-195">In the services list, find **Lync Server Access Edge**.</span></span>

6.  <span data-ttu-id="98c3e-196">Fare clic con il pulsante destro del mouse sul nome del servizio e quindi scegliere **Arresta** per arrestarlo.</span><span class="sxs-lookup"><span data-stu-id="98c3e-196">Right-click the services name, and then select **Stop** to stop the service.</span></span>

7.  <span data-ttu-id="98c3e-197">Impostare il tipo di avvio su **Disabilitato**.</span><span class="sxs-lookup"><span data-stu-id="98c3e-197">Set the Startup type to **Disabled**.</span></span>

8.  <span data-ttu-id="98c3e-198">Fare clic su  \*\*OK \*\* per chiudere la finestra \*\*Proprietà \*\*.</span><span class="sxs-lookup"><span data-stu-id="98c3e-198">Click **OK** to close the **Properties** window.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Configurare le route di federazione e il traffico multimediale
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure federation routes and media traffic
ms:assetid: 8b2f5f81-a955-4ad1-ad74-397322ff9521
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688121(v=OCS.15)
ms:contentKeyID: 49733720
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed16ac6b8aceea6828b600ce18da8b9a72827846
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980812"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="c7650-102">Configurare le route di federazione e il traffico multimediale</span><span class="sxs-lookup"><span data-stu-id="c7650-102">Configure federation routes and media traffic</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7650-103">_**Argomento Ultima modifica:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="c7650-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="c7650-104">Federation è una relazione di trust tra due o più domini SIP che consente agli utenti di organizzazioni separate di comunicare tra loro attraverso i confini della rete.</span><span class="sxs-lookup"><span data-stu-id="c7650-104">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="c7650-105">Dopo la migrazione al pool di piloti di Lync Server 2013, è necessario eseguire la transizione dalla Route federativo di Lync Server 2010 Edge Server alla route federativo di Lync Server 2013 Edge Servers.</span><span class="sxs-lookup"><span data-stu-id="c7650-105">After you migrate to your Lync Server 2013 pilot pool, you need to transition from the federation route of your Lync Server 2010 Edge Servers to the federation route of your Lync Server 2013 Edge Servers.</span></span>

<span data-ttu-id="c7650-106">Usare le procedure seguenti per eseguire la transizione della route federativa e della route del traffico multimediale da Lync Server 2010 Edge Server e Director a Lync Server 2013 Edge Server per una distribuzione a sito singolo.</span><span class="sxs-lookup"><span data-stu-id="c7650-106">Use the following procedures to transition the federation route and the media traffic route from your Lync Server 2010 Edge Server and Director to your Lync Server 2013 Edge Server, for a single-site deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c7650-107">Per modificare la route della Federazione e il traffico multimediale, è necessario pianificare l'inattività della manutenzione per Lync Server 2013 e Lync Server 2010 Edge Server.</span><span class="sxs-lookup"><span data-stu-id="c7650-107">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Lync Server 2013 and Lync Server 2010 Edge Servers.</span></span> <span data-ttu-id="c7650-108">L'intero processo di transizione significa anche che l'accesso federato non sarà disponibile per la durata dell'interruzione.</span><span class="sxs-lookup"><span data-stu-id="c7650-108">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="c7650-109">È consigliabile pianificare i tempi di inattività per un periodo di tempo in cui si prevede un'attività utente minima.</span><span class="sxs-lookup"><span data-stu-id="c7650-109">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="c7650-110">Dovresti anche dare una notifica sufficiente agli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="c7650-110">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="c7650-111">Pianificare di conseguenza questa interruzione e impostare le aspettative appropriate all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c7650-111">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c7650-112">Se il server perimetrale di Lync Server 2010 è configurato per l'uso dello stesso nome di dominio completo per il servizio Access Edge, Web Conferencing Edge Services e il servizio A/V Edge, le procedure descritte in questa sezione non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="c7650-112">If your legacy Lync Server 2010 Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="c7650-113">Se i servizi Edge legacy sono configurati in modo da usare lo stesso nome di dominio completo, è necessario prima eseguire la migrazione di tutti gli utenti da Lync Server 2010 a Lync Server 2013, quindi rimuovere la Commissione dal server Edge di Lync Server 2010 prima di abilitare la Federazione in Lync Server 2013 Edge Server.</span><span class="sxs-lookup"><span data-stu-id="c7650-113">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users from Lync Server 2010 to Lync Server 2013, then decommission the Lync Server 2010 Edge Server before enabling federation on the Lync Server 2013 Edge Server.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c7650-114">Se la Federazione XMPP viene instradata tramite un server perimetrale di Lync Server 2013, gli utenti legacy di Lync Server 2010 non saranno in grado di comunicare con il partner federato XMPP finché tutti gli utenti non sono stati spostati in Lync Server 2013, i criteri e i certificati XMPP sono stati configurato, il partner federato XMPP è stato configurato in Lync Server 2013 e infine le voci DNS sono state aggiornate.</span><span class="sxs-lookup"><span data-stu-id="c7650-114">If your XMPP federation is routed through a Lync Server 2013 Edge Server, legacy Lync Server 2010 users will not be able to communicate with the XMPP federated partner until all users have been moved to Lync Server 2013, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Lync Server 2013, and lastly the DNS entries have been updated.</span></span>



</div>

<div>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a><span data-ttu-id="c7650-115">Per rimuovere l'associazione federativa Legacy dai siti di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7650-115">To remove the legacy federation association from Lync Server 2013 sites</span></span>

1.  <span data-ttu-id="c7650-116">Nel server front-end di Lync Server 2013 aprire la topologia esistente in Generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="c7650-116">On the Lync Server 2013 Front End server, open the existing topology in Topology Builder.</span></span>

2.  <span data-ttu-id="c7650-117">Nel riquadro sinistro passare al nodo del sito, che si trova direttamente sotto **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="c7650-117">In the left pane, navigate to the site node, which is located directly below **Lync Server**.</span></span>

3.  <span data-ttu-id="c7650-118">Fare clic con il pulsante destro del mouse sul sito e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="c7650-118">Right-click the site and then click **Edit Properties**.</span></span>

4.  <span data-ttu-id="c7650-119">Nel riquadro sinistro selezionare **Route federativo**.</span><span class="sxs-lookup"><span data-stu-id="c7650-119">In the left pane, select **Federation route**.</span></span>

5.  <span data-ttu-id="c7650-120">In **assegnazione della route federativo di sito**deselezionare la casella di controllo **Abilita federazione SIP** per disabilitare la route federativo nell'ambiente legacy di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c7650-120">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy Lync Server 2010 environment.</span></span>
    
    <span data-ttu-id="c7650-121">Finestra ![di dialogo Modifica proprietà, pagina Route federativo pagina](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "modifica proprietà, Route federativo")</span><span class="sxs-lookup"><span data-stu-id="c7650-121">![Edit Properties dialog, Federation route page](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "Edit Properties dialog, Federation route page")</span></span>

6.  <span data-ttu-id="c7650-122">Fare clic su **OK** per chiudere la pagina Modifica proprietà.</span><span class="sxs-lookup"><span data-stu-id="c7650-122">Click **OK** to close the Edit Properties page.</span></span>

7.  <span data-ttu-id="c7650-123">In **Generatore di topologie**selezionare il primo nodo **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="c7650-123">From **Topology Builder**, select the top node **Lync Server**.</span></span>

8.  <span data-ttu-id="c7650-124">Nel menu **azione** fare clic su **Pubblica topologia**.</span><span class="sxs-lookup"><span data-stu-id="c7650-124">From the **Action** menu, click **Publish Topology**.</span></span>

9.  <span data-ttu-id="c7650-125">Fare clic su **Avanti** per completare il processo di pubblicazione e quindi fare clic su **fine** quando il processo di pubblicazione è stato completato.</span><span class="sxs-lookup"><span data-stu-id="c7650-125">Click **Next** to complete the publishing process and then click **Finish** when the publishing process has completed.</span></span>

</div>

<div>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="c7650-126">Per configurare il server perimetrale legacy come server perimetrale non federativo</span><span class="sxs-lookup"><span data-stu-id="c7650-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1.  <span data-ttu-id="c7650-127">Nel riquadro sinistro passare al nodo **Lync Server 2010** e quindi al nodo **pool di bordi** .</span><span class="sxs-lookup"><span data-stu-id="c7650-127">In the left pane, navigate to the **Lync Server 2010** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="c7650-128">Fare clic con il pulsante destro del mouse sul server perimetrale e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="c7650-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="c7650-129">Selezionare **generale** nel riquadro sinistro.</span><span class="sxs-lookup"><span data-stu-id="c7650-129">Select **General** in the left pane.</span></span>

4.  <span data-ttu-id="c7650-130">Deselezionare la casella di controllo **Abilita federazione per questo pool di bordi (porta 5061)** e scegliere **OK** per chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c7650-130">Clear the **Enable federation for this Edge pool (port 5061)** check box entry and select **OK** to close the page.</span></span>
    
    <span data-ttu-id="c7650-131">![Modificare le proprietà, generale, deselezionare Abilita](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "proprietà modifica Federazione, generale, Cancella Abilita federazione")</span><span class="sxs-lookup"><span data-stu-id="c7650-131">![Edit Properties, General, clear Enable federation](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "Edit Properties, General, clear Enable federation")</span></span>

5.  <span data-ttu-id="c7650-132">Scegliere **Pubblica topologia**dal menu **azione** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c7650-132">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

6.  <span data-ttu-id="c7650-133">Al termine della **pubblicazione guidata** , fare clic su **fine** per chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="c7650-133">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

7.  <span data-ttu-id="c7650-134">Verificare che la Federazione per il server perimetrale legacy sia disabilitata.</span><span class="sxs-lookup"><span data-stu-id="c7650-134">Verify federation for the legacy Edge server is disabled.</span></span>
    
    <span data-ttu-id="c7650-135">![Generatore di topologia, pool di bordi, generatore di topologia disabilitato federativo](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg ", pool Edge, Federazione disabilitata")</span><span class="sxs-lookup"><span data-stu-id="c7650-135">![Topology Builder, Edge pool, federation disabled](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "Topology Builder, Edge pool, federation disabled")</span></span>

</div>

<div>

## <a name="to-configure-certificates-on-the-lync-server-2010-edge-server"></a><span data-ttu-id="c7650-136">Per configurare i certificati nel server perimetrale di Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="c7650-136">To configure certificates on the Lync Server 2010 Edge Server</span></span>

1.  <span data-ttu-id="c7650-137">Esportare il certificato proxy di accesso esterno, con la chiave privata, dal server perimetrale Lync Server 2010 legacy.</span><span class="sxs-lookup"><span data-stu-id="c7650-137">Export the external Access Proxy certificate, with the private key, from the legacy Lync Server 2010 Edge Server.</span></span>

2.  <span data-ttu-id="c7650-138">Nel server Edge di Lync Server 2013 importare il certificato esterno del proxy di accesso dal passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="c7650-138">On the Lync Server 2013 Edge Server, import the Access Proxy external certificate from the previous step.</span></span>

3.  <span data-ttu-id="c7650-139">Assegnare il certificato esterno del proxy di accesso all'interfaccia esterna di Lync Server 2013 dell'Edge Server.</span><span class="sxs-lookup"><span data-stu-id="c7650-139">Assign the Access Proxy external certificate to the Lync Server 2013 external interface of the Edge Server.</span></span>

4.  <span data-ttu-id="c7650-140">Il certificato di interfaccia interno del server Edge di Lync Server 2013 deve essere richiesto da una CA attendibile e assegnato.</span><span class="sxs-lookup"><span data-stu-id="c7650-140">The internal interface certificate of the Lync Server 2013 Edge Server should be requested from a trusted CA and assigned.</span></span>

</div>

<div>

## <a name="to-change-lync-server-2010-federation-route-to-use-lync-server-2013-edge-server"></a><span data-ttu-id="c7650-141">Per modificare la route federativo di Lync Server 2010 per l'uso di Lync Server 2013 Edge Server</span><span class="sxs-lookup"><span data-stu-id="c7650-141">To change Lync Server 2010 federation route to use Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="c7650-142">Nel riquadro sinistro di generatore di topologia passare al nodo **Lync Server 2013** e quindi al nodo Pool di **bordi** .</span><span class="sxs-lookup"><span data-stu-id="c7650-142">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="c7650-143">Fare clic con il pulsante destro del mouse sul server perimetrale e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="c7650-143">Right-click the Edge server, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="c7650-144">Selezionare **generale** nel riquadro sinistro.</span><span class="sxs-lookup"><span data-stu-id="c7650-144">Select **General** in the left pane.</span></span>

4.  <span data-ttu-id="c7650-145">Selezionare la voce della casella di controllo per **abilitare la Federazione per questo pool di bordi (porta 5061)** e quindi fare clic su **OK** per chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c7650-145">Select the check box entry for **Enable federation for this Edge pool (port 5061)** and then click **OK** to close the page.</span></span>
    
    <span data-ttu-id="c7650-146">![Finestra di dialogo Modifica proprietà,](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "finestra di dialogo Modifica proprietà") generale pagina generale</span><span class="sxs-lookup"><span data-stu-id="c7650-146">![Edit Properties dialog, General page](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Edit Properties dialog, General page")</span></span>

5.  <span data-ttu-id="c7650-147">Scegliere **Pubblica topologia**dal menu **azione** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c7650-147">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

6.  <span data-ttu-id="c7650-148">Al termine della **pubblicazione guidata** , fare clic su **fine** per chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="c7650-148">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

7.  <span data-ttu-id="c7650-149">Verifica **Federazione (la porta 5061)** è impostata su **Enabled**.</span><span class="sxs-lookup"><span data-stu-id="c7650-149">Verify **Federation (port 5061)** is set to **Enabled**.</span></span>
    
    <span data-ttu-id="c7650-150">![Generatore di topologia, pool di bordi,](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "Generatore di topologie abilitato alla Federazione, pool Edge, Federazione abilitata")</span><span class="sxs-lookup"><span data-stu-id="c7650-150">![Topology Builder, Edge pool, Federation enabled](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "Topology Builder, Edge pool, Federation enabled")</span></span>

</div>

<div>

## <a name="to-update-lync-server-2013-edge-server-federation-next-hop"></a><span data-ttu-id="c7650-151">Per aggiornare Lync Server 2013 Edge Server Federation next hop</span><span class="sxs-lookup"><span data-stu-id="c7650-151">To update Lync Server 2013 Edge Server federation next hop</span></span>

1.  <span data-ttu-id="c7650-152">Nel riquadro sinistro di generatore di topologia passare al nodo **Lync Server 2013** e quindi al nodo Pool di **bordi** .</span><span class="sxs-lookup"><span data-stu-id="c7650-152">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="c7650-153">Espandere il nodo, fare clic con il pulsante destro del mouse sul server perimetrale elencato e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="c7650-153">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="c7650-154">Nella pagina **generale** , in **selezione hop successivo**, selezionare nell'elenco a discesa il pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c7650-154">On the **General** page, under **Next hop selection**, select from the drop-down list the Lync Server 2013  pool.</span></span>
    
    <span data-ttu-id="c7650-155">Finestra ![di dialogo Modifica proprietà, pagina hop successiva]pagina(images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "modifica proprietà, pagina hop successivo")</span><span class="sxs-lookup"><span data-stu-id="c7650-155">![Edit Properties dialog, Next hop page](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "Edit Properties dialog, Next hop page")</span></span>

4.  <span data-ttu-id="c7650-156">Fare clic su **OK** per chiudere la pagina Modifica proprietà.</span><span class="sxs-lookup"><span data-stu-id="c7650-156">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="c7650-157">In **Generatore di topologie**selezionare il primo nodo **Lync Server** .</span><span class="sxs-lookup"><span data-stu-id="c7650-157">From **Topology Builder**, select the top node **Lync Server** .</span></span>

6.  <span data-ttu-id="c7650-158">Nel menu **azione** fare clic su **Pubblica topologia** e completare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="c7650-158">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a><span data-ttu-id="c7650-159">Per configurare il percorso multimediale in uscita di Lync Server 2013 Edge Server</span><span class="sxs-lookup"><span data-stu-id="c7650-159">To configure Lync Server 2013 Edge Server outbound media path</span></span>

1.  <span data-ttu-id="c7650-160">In Generatore di topologie, nel riquadro sinistro, passare al nodo **Lync Server 2013** e quindi al pool sotto i **server front end Standard Edition** o i **pool Front End di Enterprise Edition**.</span><span class="sxs-lookup"><span data-stu-id="c7650-160">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>

2.  <span data-ttu-id="c7650-161">Fare clic con il pulsante destro del mouse sul pool e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="c7650-161">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="c7650-162">Nella sezione **associazioni** selezionare la casella **di controllo Associa pool Edge (per componenti multimediali)** .</span><span class="sxs-lookup"><span data-stu-id="c7650-162">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span>
    
    <span data-ttu-id="c7650-163">Proprietà ![modifica, generale, associa proprietà modifica pool Edge](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg ", generale, pool Edge associato")</span><span class="sxs-lookup"><span data-stu-id="c7650-163">![Edit Properties, General, Associate Edge pool](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "Edit Properties, General, Associate Edge pool")</span></span>

4.  <span data-ttu-id="c7650-164">Nella casella a discesa selezionare il server Edge di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c7650-164">From the drop down box, select the Lync Server 2013 Edge Server.</span></span>

5.  <span data-ttu-id="c7650-165">Fare clic su **OK** per chiudere la pagina **modifica proprietà** .</span><span class="sxs-lookup"><span data-stu-id="c7650-165">Click **OK** to close the **Edit Properties** page.</span></span>

</div>

<div>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a><span data-ttu-id="c7650-166">Per attivare Lync Server 2013 Edge Server Federation</span><span class="sxs-lookup"><span data-stu-id="c7650-166">To turn on Lync Server 2013 Edge Server federation</span></span>

1.  <span data-ttu-id="c7650-167">Nel riquadro sinistro di generatore di topologia passare al nodo **Lync Server 2013** e quindi al nodo Pool di **bordi** .</span><span class="sxs-lookup"><span data-stu-id="c7650-167">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="c7650-168">Espandere il nodo, fare clic con il pulsante destro del mouse sul server perimetrale elencato e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="c7650-168">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c7650-169">La Federazione può essere abilitata solo per un singolo pool di Edge.</span><span class="sxs-lookup"><span data-stu-id="c7650-169">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="c7650-170">Se si hanno più pool di bordi, selezionarne uno da usare come pool di bordi federativi.</span><span class="sxs-lookup"><span data-stu-id="c7650-170">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span>

    
    </div>

3.  <span data-ttu-id="c7650-171">Nella pagina **generale** verificare che l'impostazione **Abilita federazione per questo pool di Edge (porta 5061)** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="c7650-171">On the **General** page, verify the **Enable federation for this Edge pool (Port 5061)** setting is checked.</span></span>
    
    <span data-ttu-id="c7650-172">![Finestra di dialogo Modifica proprietà,](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "finestra di dialogo Modifica proprietà") generale pagina generale</span><span class="sxs-lookup"><span data-stu-id="c7650-172">![Edit Properties dialog, General page](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Edit Properties dialog, General page")</span></span>

4.  <span data-ttu-id="c7650-173">Fare clic su **OK** per chiudere la pagina Modifica proprietà.</span><span class="sxs-lookup"><span data-stu-id="c7650-173">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="c7650-174">Passare quindi al nodo del sito.</span><span class="sxs-lookup"><span data-stu-id="c7650-174">Next, navigate to the site node.</span></span>

6.  <span data-ttu-id="c7650-175">Fare clic con il pulsante destro del mouse sul sito e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="c7650-175">Right-click the site, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="c7650-176">Nel riquadro sinistro fare clic su **Route federativo**.</span><span class="sxs-lookup"><span data-stu-id="c7650-176">In the left pane, click **Federation route**.</span></span>

8.  <span data-ttu-id="c7650-177">In **assegnazione percorso federativo di sito**selezionare **Abilita federazione SIP**e quindi nell'elenco selezionare il server Edge di Lync Server 2013 elencato.</span><span class="sxs-lookup"><span data-stu-id="c7650-177">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Lync Server 2013 Edge Server listed.</span></span>
    
    <span data-ttu-id="c7650-178">Modificare le proprietà, le proprietà della ![pagina Route federativo](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg ", la pagina della route federativo")</span><span class="sxs-lookup"><span data-stu-id="c7650-178">![Edit Properties, Federation route page](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "Edit Properties, Federation route page")</span></span>

9.  <span data-ttu-id="c7650-179">Fare clic su **OK** per chiudere la pagina **modifica proprietà** .</span><span class="sxs-lookup"><span data-stu-id="c7650-179">Click **OK** to close the **Edit Properties** page.</span></span>
    
    <span data-ttu-id="c7650-180">Per le distribuzioni multisito, completare questa procedura in ogni sito.</span><span class="sxs-lookup"><span data-stu-id="c7650-180">For multi-site deployments, complete this procedure at each site.</span></span>

</div>

<div>

## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="c7650-181">Per pubblicare le modifiche alla configurazione di Edge Server</span><span class="sxs-lookup"><span data-stu-id="c7650-181">To publish Edge Server configuration changes</span></span>

1.  <span data-ttu-id="c7650-182">In **Generatore di topologie**selezionare il primo nodo **Lync Server** .</span><span class="sxs-lookup"><span data-stu-id="c7650-182">From **Topology Builder**, select the top node **Lync Server** .</span></span>

2.  <span data-ttu-id="c7650-183">Nel menu **azione** selezionare **Pubblica topologia** e completare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="c7650-183">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

3.  <span data-ttu-id="c7650-184">Attendere che la replica di Active Directory si verifichi in tutti i pool della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c7650-184">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c7650-185">Potrebbe essere visualizzato il messaggio seguente:</span><span class="sxs-lookup"><span data-stu-id="c7650-185">You may see the following message:</span></span><BR><span data-ttu-id="c7650-186"><STRONG>Avviso: la topologia contiene più di un server perimetrale federato. Questo problema può verificarsi durante la migrazione a una versione più recente del prodotto. In questo caso, un solo server perimetrale verrebbe usato attivamente per la Federazione. Verificare che il record SRV DNS esterno punti al server perimetrale corretto. Se si vuole distribuire più Edge Server federativo in modo che sia attivo contemporaneamente, ovvero non uno scenario di migrazione, verificare che tutti i partner federati utilizzino Lync Server. Verificare che il record SRV DNS esterno elenchi tutti i server perimetrali abilitati alla Federazione.</STRONG></span><span class="sxs-lookup"><span data-stu-id="c7650-186"><STRONG>Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Lync Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.</STRONG></span></span><BR><span data-ttu-id="c7650-187">Questo avviso è previsto e può essere ignorato in modo sicuro.</span><span class="sxs-lookup"><span data-stu-id="c7650-187">This warning is expected and can be safely ignored.</span></span>

    
    </div>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server"></a><span data-ttu-id="c7650-188">Per configurare Lync Server 2013 Edge Server</span><span class="sxs-lookup"><span data-stu-id="c7650-188">To configure Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="c7650-189">Riunire tutti i server Edge di Lync Server 2013 online.</span><span class="sxs-lookup"><span data-stu-id="c7650-189">Bring all of the Lync Server 2013 Edge Servers online.</span></span>

2.  <span data-ttu-id="c7650-190">Aggiornare le regole di routing del firewall esterno o le impostazioni di bilanciamento del carico hardware per inviare il traffico SIP per l'accesso esterno (in genere la porta 443) e la Federazione (in genere la porta 5061) nel server perimetrale di Lync Server 2013, invece che nel server perimetrale legacy.</span><span class="sxs-lookup"><span data-stu-id="c7650-190">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Lync Server 2013 Edge Server, instead of the legacy Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c7650-191">Se non si dispone di un servizio di bilanciamento del carico hardware, è necessario aggiornare il record DNS per la Federazione per risolverlo nel nuovo server di Access Edge di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c7650-191">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Lync Server Access Edge server.</span></span> <span data-ttu-id="c7650-192">Per eseguire questa operazione con un minimo di interruzioni, ridurre il valore di TLL per l'FQDN di Access Edge di Lync Server esterno, in modo che quando il DNS viene aggiornato per posizionare il puntatore sul nuovo bordo di accesso di Lync Server, la Federazione e l'accesso remoto verranno aggiornati rapidamente.</span><span class="sxs-lookup"><span data-stu-id="c7650-192">To accomplish this with minimum disruption, reduce the TLL value for the external Lync Server Access Edge FQDN so that when DNS is updated to point to the new Lync Server Access Edge, federation and remote access will be updated quickly.</span></span>

    
    </div>

3.  <span data-ttu-id="c7650-193">Arrestare quindi il **bordo di accesso di Lync Server** da ogni computer Edge Server.</span><span class="sxs-lookup"><span data-stu-id="c7650-193">Next, stop the **Lync Server Access Edge** from each Edge Server computer.</span></span>

4.  <span data-ttu-id="c7650-194">Da ogni computer legacy Edge Server aprire l'applet **Servizi** dagli strumenti di **Amministrazione**.</span><span class="sxs-lookup"><span data-stu-id="c7650-194">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>

5.  <span data-ttu-id="c7650-195">Nell'elenco servizi individuare **Edge Access di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="c7650-195">In the services list, find **Lync Server Access Edge**.</span></span>

6.  <span data-ttu-id="c7650-196">Fare clic con il pulsante destro del mouse sul nome dei servizi e quindi scegliere **Interrompi** per arrestare il servizio.</span><span class="sxs-lookup"><span data-stu-id="c7650-196">Right-click the services name, and then select **Stop** to stop the service.</span></span>

7.  <span data-ttu-id="c7650-197">Impostare il tipo di avvio su **disabled**.</span><span class="sxs-lookup"><span data-stu-id="c7650-197">Set the Startup type to **Disabled**.</span></span>

8.  <span data-ttu-id="c7650-198">Fare clic su **OK** per chiudere la finestra **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="c7650-198">Click **OK** to close the **Properties** window.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


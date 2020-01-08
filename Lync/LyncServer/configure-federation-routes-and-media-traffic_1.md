---
title: Configurare le route di federazione e il traffico multimediale
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure federation routes and media traffic
ms:assetid: ed6cb922-7863-453a-adce-2ce0ba761d74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721925(v=OCS.15)
ms:contentKeyID: 49733860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4542ae02cc72dfbac05dfa982e2fbda7f2924919
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982590"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="a0920-102">Configurare le route di federazione e il traffico multimediale</span><span class="sxs-lookup"><span data-stu-id="a0920-102">Configure federation routes and media traffic</span></span>

 


<span data-ttu-id="a0920-103">Federation è una relazione di trust tra due o più domini SIP che consente agli utenti di organizzazioni separate di comunicare tra loro attraverso i confini della rete.</span><span class="sxs-lookup"><span data-stu-id="a0920-103">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="a0920-104">Dopo la migrazione al pool di piloti di Lync Server 2013, è necessario passare dalla Route federativo di Microsoft Office Communications Server 2007 R2 Edge Server alla route federativo di Lync Server 2013 Edge Servers.</span><span class="sxs-lookup"><span data-stu-id="a0920-104">After you migrate to your Lync Server 2013 pilot pool, you need to transition from the federation route of your Microsoft Office Communications Server 2007 R2 Edge Servers to the federation route of your Lync Server 2013 Edge Servers.</span></span>

<span data-ttu-id="a0920-105">Usare le procedure seguenti per eseguire la transizione della route federativa e della route del traffico multimediale da Office Communications Server 2007 R2 Edge Server e Director a Lync Server 2013 Edge Server per una distribuzione a sito singolo.</span><span class="sxs-lookup"><span data-stu-id="a0920-105">Use the procedures that follow to transition the federation route and the media traffic route from your Office Communications Server 2007 R2 Edge Server and Director to your Lync Server 2013 Edge Server, for a single-site deployment.</span></span>


> [!IMPORTANT]  
> <span data-ttu-id="a0920-106">Per modificare la route della Federazione e il traffico multimediale, è necessario pianificare l'inattività della manutenzione per Lync Server 2013 e Office Communications Server 2007 R2 Edge Servers.</span><span class="sxs-lookup"><span data-stu-id="a0920-106">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Lync Server 2013 and Office Communications Server 2007 R2 Edge Servers.</span></span> <span data-ttu-id="a0920-107">L'intero processo di transizione significa anche che l'accesso federato non sarà disponibile per la durata dell'interruzione.</span><span class="sxs-lookup"><span data-stu-id="a0920-107">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="a0920-108">È consigliabile pianificare i tempi di inattività per un periodo di tempo in cui si prevede un'attività utente minima.</span><span class="sxs-lookup"><span data-stu-id="a0920-108">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="a0920-109">Dovresti anche dare una notifica sufficiente agli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="a0920-109">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="a0920-110">Pianificare di conseguenza questa interruzione e impostare le aspettative appropriate all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a0920-110">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span>




> [!IMPORTANT]  
> <span data-ttu-id="a0920-111">Se l'legacy Office Communications Server 2007 R2 Edge Server è configurato per l'uso dello stesso nome di dominio completo per il servizio Access Edge, Web Conferencing Edge Services e il servizio A/V Edge, le procedure descritte in questa sezione per la transizione dell'impostazione della Federazione a un server perimetrale di Lync Server 2013 non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="a0920-111">If your legacy Office Communications Server 2007 R2 Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section to transition the federation setting to a Lync Server 2013 Edge Server are not supported.</span></span> <span data-ttu-id="a0920-112">Se i servizi Edge legacy sono configurati in modo da usare lo stesso nome di dominio completo, è necessario prima eseguire la migrazione di tutti gli utenti da Office Communications Server 2007 R2 a Lync Server 2013, quindi rimuovere la Commissione da Office Communications Server 2007 R2 Edge Server prima di abilitare la Federazione Server Edge di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a0920-112">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users from Office Communications Server 2007 R2 to Lync Server 2013, then decommission the Office Communications Server 2007 R2 Edge Server before enabling federation on the Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="a0920-113">Per informazioni dettagliate, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0920-113">For details, see the following topics:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="a0920-114"><A href="move-remaining-users-to-lync-server-2013_1.md">Spostare gli utenti rimanenti in Lync Server 2013</A></span><span class="sxs-lookup"><span data-stu-id="a0920-114"><A href="move-remaining-users-to-lync-server-2013_1.md">Move remaining users to Lync Server 2013</A></span></span></P>
> <LI>
> <P><span data-ttu-id="a0920-115">"Rimuovere server e ruoli server" in<A href="http://go.microsoft.com/fwlink/p/?linkid=268790">http://go.microsoft.com/fwlink/p/?LinkId=268790</A></span><span class="sxs-lookup"><span data-stu-id="a0920-115">"Remove Servers and Server Roles" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268790">http://go.microsoft.com/fwlink/p/?LinkId=268790</A></span></span></P></LI></UL>




> [!IMPORTANT]  
> <span data-ttu-id="a0920-116">Se la Federazione XMPP viene instradata tramite un server perimetrale di Lync Server 2013, gli utenti legacy di Office Communications Server 2007 R2 non saranno in grado di comunicare con il partner federato XMPP finché tutti gli utenti non sono stati spostati in Lync Server 2013, in criteri XMPP e i certificati sono stati configurati, il partner federato XMPP è stato configurato in Lync Server 2013 e infine le voci DNS sono state aggiornate.</span><span class="sxs-lookup"><span data-stu-id="a0920-116">If your XMPP federation is routed through a Lync Server 2013 Edge Server, legacy Office Communications Server 2007 R2 users will not be able to communicate with the XMPP federated partner until all users have been moved to Lync Server 2013, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Lync Server 2013, and lastly the DNS entries have been updated.</span></span>



<span data-ttu-id="a0920-117">Per pubblicare, abilitare o disabilitare correttamente una topologia durante l'aggiunta o la rimozione di un ruolo del server, è necessario avere effettuato l'accesso come utente membro dei gruppi RTCUniversalServerAdmins e Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="a0920-117">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="a0920-118">È anche possibile delegare i diritti utente appropriati e le autorizzazioni per l'aggiunta di ruoli del server.</span><span class="sxs-lookup"><span data-stu-id="a0920-118">It is also possible to delegate the proper user rights and permissions for adding server roles.</span></span> <span data-ttu-id="a0920-119">Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync server 2013](lync-server-2013-delegate-setup-permissions.md) nella documentazione sulla distribuzione di server Standard Edition o Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="a0920-119">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="a0920-120">Per altre modifiche alla configurazione, è necessaria solo l'appartenenza al gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="a0920-120">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a><span data-ttu-id="a0920-121">Per rimuovere l'associazione federativa Legacy dai siti di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0920-121">To remove the legacy federation association from Lync Server 2013 sites</span></span>

1.  <span data-ttu-id="a0920-122">Aprire la topologia del pool di Pilot usando generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="a0920-122">Open the pilot pool topology using Topology Builder.</span></span>

2.  <span data-ttu-id="a0920-123">Nel riquadro sinistro passare al nodo del sito.</span><span class="sxs-lookup"><span data-stu-id="a0920-123">In the left pane, navigate to the site node.</span></span>

3.  <span data-ttu-id="a0920-124">Fare clic con il pulsante destro del mouse sul sito e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a0920-124">Right-click the site, and then click **Edit Properties**.</span></span>

4.  <span data-ttu-id="a0920-125">Selezionare **Route federativo** nel riquadro sinistro.</span><span class="sxs-lookup"><span data-stu-id="a0920-125">Select **Federation route** in the left pane.</span></span>

5.  <span data-ttu-id="a0920-126">In assegnazione della route federativo di sito deselezionare la casella di controllo accanto a **Consenti federazione SIP** per disabilitare la route federativo tramite **BackCompatSite**.</span><span class="sxs-lookup"><span data-stu-id="a0920-126">Under Site federation route assignment, clear the check box next to **Enable SIP federation** to disable the federation route through the **BackCompatSite**.</span></span>
    
    <span data-ttu-id="a0920-127">Finestra ![di dialogo Modifica proprietà, Route federativo](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "modifica proprietà, Route federativo")</span><span class="sxs-lookup"><span data-stu-id="a0920-127">![Edit Properties dialog, Federation route](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Edit Properties dialog, Federation route")</span></span>

6.  <span data-ttu-id="a0920-128">Fare clic su **OK** per chiudere la pagina Modifica proprietà.</span><span class="sxs-lookup"><span data-stu-id="a0920-128">Click **OK** to close the Edit Properties page.</span></span>

7.  <span data-ttu-id="a0920-129">In **Generatore di topologie**selezionare il primo nodo **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a0920-129">From **Topology Builder**, select the top node **Lync Server**.</span></span>

8.  <span data-ttu-id="a0920-130">Nel menu **azione** fare clic su **Pubblica topologia** e completare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="a0920-130">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="a0920-131">Per configurare il server perimetrale legacy come server perimetrale non federativo</span><span class="sxs-lookup"><span data-stu-id="a0920-131">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1.  <span data-ttu-id="a0920-132">Da **Generatore di topologie**, dal menu **azione** fare clic su **Unisci topologia di Office Communications Server 2007 R2**.</span><span class="sxs-lookup"><span data-stu-id="a0920-132">From **Topology Builder**, from the **Action** menu click **Merge Office Communications Server 2007 R2 Topology**.</span></span>

2.  <span data-ttu-id="a0920-133">Fare clic su **Avanti** per continuare.</span><span class="sxs-lookup"><span data-stu-id="a0920-133">Click **Next** to continue.</span></span>

3.  <span data-ttu-id="a0920-134">Nella **configurazione specifica bordo**selezionare il nome di **dominio completo interno del server perimetrale** attualmente configurato per la Federazione e quindi fare clic su **Cambia**.</span><span class="sxs-lookup"><span data-stu-id="a0920-134">On the **Specify Edge Setup**, select the **Edge Server Internal FQDN** that is currently configured for federation, and then click **Change**.</span></span>
    
    <span data-ttu-id="a0920-135">![Unire la topologia ocs 2007 R2, specificare]la(images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "topologia merge OCS 2007 R2, specificare la configurazione di Edge")</span><span class="sxs-lookup"><span data-stu-id="a0920-135">![Merge OCS 2007 R2 Topology, Specify Edge Setup](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Merge OCS 2007 R2 Topology, Specify Edge Setup")</span></span>

4.  <span data-ttu-id="a0920-136">Fare clic su **Avanti** e accettare le impostazioni predefinite fino a raggiungere la pagina **specifica bordi esterni** :</span><span class="sxs-lookup"><span data-stu-id="a0920-136">Click **Next** and accept the default settings until you get to the **Specify External Edge** page:</span></span>
    
    <span data-ttu-id="a0920-137">![Generatore di topologia specificare]il(images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "Generatore di topologia") della pagina perimetrale esterno</span><span class="sxs-lookup"><span data-stu-id="a0920-137">![Topology Builder Specify External Edge page](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "Topology Builder Specify External Edge page")</span></span>

5.  <span data-ttu-id="a0920-138">In **specifica bordo esterno**deselezionare la casella **di controllo questo pool di bordi viene usato per la Federazione e la connettività di messaggistica istantanea pubblica** .</span><span class="sxs-lookup"><span data-stu-id="a0920-138">In **Specify External Edge**, clear the **This Edge pool is used for federation and public IM connectivity** check box.</span></span> <span data-ttu-id="a0920-139">Verrà rimosso l'associazione di federazione con BackCompatSite.</span><span class="sxs-lookup"><span data-stu-id="a0920-139">This will remove the federation association with the BackCompatSite.</span></span>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a0920-140">Questo passaggio è importante.</span><span class="sxs-lookup"><span data-stu-id="a0920-140">This step is important.</span></span> <span data-ttu-id="a0920-141">Devi deselezionare questa opzione per rimuovere l'associazione di federazione legacy.</span><span class="sxs-lookup"><span data-stu-id="a0920-141">You must clear this option to remove the legacy federation association.</span></span>



6.  <span data-ttu-id="a0920-142">Fare clic su **Avanti** e accettare le impostazioni predefinite delle pagine rimanenti della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="a0920-142">Click **Next** and accept the default settings of the remaining pages of the wizard.</span></span>

7.  <span data-ttu-id="a0920-143">In **Riepilogo**, fare clic su **Avanti** per iniziare a unire le topologie.</span><span class="sxs-lookup"><span data-stu-id="a0920-143">In **Summary**, click **Next** to begin merging the topologies.</span></span>

8.  <span data-ttu-id="a0920-144">Nella colonna **stato** verificare che il valore sia **successo**e quindi fare clic su **fine** per chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="a0920-144">In the **Status** column, verify that the value is **Success**, and then click **Finish** to close the wizard.</span></span>

9.  <span data-ttu-id="a0920-145">Scegliere **Pubblica topologia**dal menu **azione** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a0920-145">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

10. <span data-ttu-id="a0920-146">Al termine della **pubblicazione guidata** , fare clic su **fine** per chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="a0920-146">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>
    
    <span data-ttu-id="a0920-147">![Generatore di topologia con il sito visualizzato dopo]il(images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Generatore di topologia Unione con il sito visualizzato dopo l'Unione")</span><span class="sxs-lookup"><span data-stu-id="a0920-147">![Topology Builder with site displayed after merge](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Topology Builder with site displayed after merge")</span></span>
    
    <span data-ttu-id="a0920-148">Come illustrato nella figura precedente, la **federazione SIP** situata in **assegnazione Route federativo di sito** è impostata su **disabled**.</span><span class="sxs-lookup"><span data-stu-id="a0920-148">As shown in the previous figure, the **SIP federation** located under **Site federation route assignment** is set to **Disabled**.</span></span>

## <a name="to-configure-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="a0920-149">Per configurare i certificati nel server perimetrale di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0920-149">To configure certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="a0920-150">Esportare il certificato proxy di accesso esterno, con la chiave privata, dal server perimetrale legacy di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a0920-150">Export the external Access Proxy certificate, with the private key, from the legacy Office Communications Server 2007 R2 Edge Server.</span></span>

2.  <span data-ttu-id="a0920-151">Nel server Edge di Lync Server 2013 importare il certificato esterno del proxy di accesso dal passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="a0920-151">On the Lync Server 2013 Edge Server, import the Access Proxy external certificate from the previous step.</span></span>

3.  <span data-ttu-id="a0920-152">Assegnare il certificato esterno del proxy di accesso all'interfaccia esterna di Lync Server 2013 dell'Edge Server.</span><span class="sxs-lookup"><span data-stu-id="a0920-152">Assign the Access Proxy external certificate to the Lync Server 2013 external interface of the Edge Server.</span></span>

4.  <span data-ttu-id="a0920-153">Il certificato di interfaccia interno del server Edge di Lync Server 2013 non deve essere modificato.</span><span class="sxs-lookup"><span data-stu-id="a0920-153">The internal interface certificate of the Lync Server 2013 Edge Server should not be changed.</span></span>

## <a name="to-change-office-communications-server-2007-r2-federation-route-to-use-lync-server-2013-edge-server"></a><span data-ttu-id="a0920-154">Per modificare la route Federation di Office Communications Server 2007 R2 per l'uso di Lync Server 2013 Edge Server</span><span class="sxs-lookup"><span data-stu-id="a0920-154">To change Office Communications Server 2007 R2 federation route to use Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="a0920-155">Nel server Office Communications Server 2007 R2 Standard Edition o front end server aprire lo strumento di amministrazione di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a0920-155">On the Office Communications Server 2007 R2 Standard Edition server or Front End Server, open the Office Communications Server 2007 R2 Administrative tool.</span></span>

2.  <span data-ttu-id="a0920-156">Nel riquadro sinistro espandere il nodo superiore e quindi fare clic con il pulsante destro del mouse sul nodo della **foresta** .</span><span class="sxs-lookup"><span data-stu-id="a0920-156">In the left pane, expand the top node, and then right-click the **Forest** node.</span></span> <span data-ttu-id="a0920-157">Selezionare **Proprietà**e quindi fare clic su **proprietà globali**.</span><span class="sxs-lookup"><span data-stu-id="a0920-157">Select **Properties**, and then click **Global Properties**.</span></span>

3.  <span data-ttu-id="a0920-158">Fare clic sulla scheda **Federazione** .</span><span class="sxs-lookup"><span data-stu-id="a0920-158">Click the **Federation** tab.</span></span>

4.  <span data-ttu-id="a0920-159">Selezionare la casella di controllo per abilitare la Federazione e la connettività per messaggistica istantanea pubblica.</span><span class="sxs-lookup"><span data-stu-id="a0920-159">Select the check box to enable federation and Public IM connectivity.</span></span>

5.  <span data-ttu-id="a0920-160">Immettere il nome di dominio completo di Lync Server 2013 Edge Server e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a0920-160">Enter the FQDN of the Lync Server 2013 Edge Server, and then click **OK**.</span></span>
    
    <span data-ttu-id="a0920-161">![Proprietà globali OCS, scheda Federazione](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "proprietà globali OCS, scheda Federazione")</span><span class="sxs-lookup"><span data-stu-id="a0920-161">![OCS Global Properties, Federation tab](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "OCS Global Properties, Federation tab")</span></span>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a><span data-ttu-id="a0920-162">Per attivare Lync Server 2013 Edge Server Federation</span><span class="sxs-lookup"><span data-stu-id="a0920-162">To turn on Lync Server 2013 Edge Server federation</span></span>

1.  <span data-ttu-id="a0920-163">Nel riquadro sinistro di generatore di topologia passare al nodo **pool di bordi** di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a0920-163">From Topology Builder, in the left pane, navigate to the Lync Server 2013 **Edge pools** node.</span></span>

2.  <span data-ttu-id="a0920-164">Espandere il nodo, fare clic con il pulsante destro del mouse sul server perimetrale elencato e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a0920-164">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="a0920-165">La Federazione può essere abilitata solo per un singolo pool di Edge.</span><span class="sxs-lookup"><span data-stu-id="a0920-165">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="a0920-166">Se si hanno più pool di bordi, selezionarne uno da usare come pool di bordi federativi.</span><span class="sxs-lookup"><span data-stu-id="a0920-166">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span>



3.  <span data-ttu-id="a0920-167">Nella pagina **generale** selezionare la casella **di controllo Abilita federazione per questo pool di bordi (porta 5061)** .</span><span class="sxs-lookup"><span data-stu-id="a0920-167">On the **General** page, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
    <span data-ttu-id="a0920-168">![Modificare le proprietà, generale, abilitare]le proprietà di modifica della federazione(images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "di Edge, generale, Enable Edge Federation")</span><span class="sxs-lookup"><span data-stu-id="a0920-168">![Edit Properties, General, Enable Edge Federation](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "Edit Properties, General, Enable Edge Federation")</span></span>

4.  <span data-ttu-id="a0920-169">Fare clic su **OK** per chiudere la pagina Modifica proprietà.</span><span class="sxs-lookup"><span data-stu-id="a0920-169">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="a0920-170">Passare quindi al nodo del sito.</span><span class="sxs-lookup"><span data-stu-id="a0920-170">Next, navigate to the site node.</span></span>

6.  <span data-ttu-id="a0920-171">Fare clic con il pulsante destro del mouse sul sito e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a0920-171">Right-click the site, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="a0920-172">Nel riquadro sinistro fare clic su **Route federativo**.</span><span class="sxs-lookup"><span data-stu-id="a0920-172">In the left pane, click **Federation route**.</span></span>

8.  <span data-ttu-id="a0920-173">In **assegnazione percorso federativo di sito**selezionare **Abilita federazione SIP**e quindi nell'elenco selezionare il server Edge di Lync Server 2013 elencato.</span><span class="sxs-lookup"><span data-stu-id="a0920-173">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Lync Server 2013 Edge Server listed.</span></span>

9.  <span data-ttu-id="a0920-174">Fare clic su **OK** per chiudere la pagina **modifica proprietà** .</span><span class="sxs-lookup"><span data-stu-id="a0920-174">Click **OK** to close the **Edit Properties** page.</span></span>
    
    <span data-ttu-id="a0920-175">Proprietà ![modifica, generale, associa proprietà modifica pool Edge](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg ", generale, pool Edge associato")</span><span class="sxs-lookup"><span data-stu-id="a0920-175">![Edit Properties, General, Associate Edge pool](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Edit Properties, General, Associate Edge pool")</span></span>
    
    <span data-ttu-id="a0920-176">Per le distribuzioni multisito, completare questa procedura in ogni sito.</span><span class="sxs-lookup"><span data-stu-id="a0920-176">For multi-site deployments, complete this procedure at each site.</span></span>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a><span data-ttu-id="a0920-177">Per configurare il percorso multimediale in uscita di Lync Server 2013 Edge Server</span><span class="sxs-lookup"><span data-stu-id="a0920-177">To configure Lync Server 2013 Edge Server outbound media path</span></span>

1.  <span data-ttu-id="a0920-178">Da **Generatore di topologie**, passare al pool di Lync Server 2013 sotto i **server front end Standard Edition** o i **pool Front end Enterprise Edition**.</span><span class="sxs-lookup"><span data-stu-id="a0920-178">From **Topology Builder**, navigate to the Lync Server 2013 pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>

2.  <span data-ttu-id="a0920-179">Fare clic con il pulsante destro del mouse sul pool e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a0920-179">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="a0920-180">Nella sezione **associazioni** selezionare la casella **di controllo Associa pool Edge (per componenti multimediali)** .</span><span class="sxs-lookup"><span data-stu-id="a0920-180">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span>

4.  <span data-ttu-id="a0920-181">Nella casella a discesa selezionare il server Edge di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a0920-181">From the drop down box, select the Lync Server 2013 Edge Server.</span></span>
    
    <span data-ttu-id="a0920-182">![Finestra di dialogo Modifica proprietà,](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "finestra di dialogo Associa proprietà modifica") bordo pool</span><span class="sxs-lookup"><span data-stu-id="a0920-182">![Edit Properties dialog, Associate Edge Pool](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Edit Properties dialog, Associate Edge Pool")</span></span>

5.  <span data-ttu-id="a0920-183">Fare clic su **OK** per chiudere la pagina **modifica proprietà** .</span><span class="sxs-lookup"><span data-stu-id="a0920-183">Click **OK** to close the **Edit Properties** page.</span></span>

## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="a0920-184">Per pubblicare le modifiche alla configurazione di Edge Server</span><span class="sxs-lookup"><span data-stu-id="a0920-184">To publish Edge Server configuration changes</span></span>

1.  <span data-ttu-id="a0920-185">In **Generatore di topologie**selezionare il primo nodo **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a0920-185">From **Topology Builder**, select the top node **Lync Server**.</span></span>

2.  <span data-ttu-id="a0920-186">Nel menu **azione** selezionare **Pubblica topologia** e completare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="a0920-186">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

3.  <span data-ttu-id="a0920-187">Attendere che la replica di Active Directory si verifichi in tutti i pool della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="a0920-187">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="a0920-188">Potrebbe essere visualizzato il messaggio seguente:</span><span class="sxs-lookup"><span data-stu-id="a0920-188">You may see the following message:</span></span><BR><span data-ttu-id="a0920-189"><STRONG>Avviso: la topologia contiene più di un server perimetrale federato. Questo problema può verificarsi durante la migrazione a una versione più recente del prodotto. In questo caso, un solo server perimetrale verrebbe usato attivamente per la Federazione. Verificare che il record SRV DNS esterno punti al server perimetrale corretto. Se si vuole distribuire più Edge Server federativo in modo che sia attivo contemporaneamente, ovvero non uno scenario di migrazione, verificare che tutti i partner federati utilizzino Office Communications Server 2007 R2 o Lync Server. Verificare che il record SRV DNS esterno elenchi tutti i server perimetrali abilitati alla Federazione.</STRONG></span><span class="sxs-lookup"><span data-stu-id="a0920-189"><STRONG>Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Office Communications Server 2007 R2 or Lync Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.</STRONG></span></span><BR><span data-ttu-id="a0920-190">Questo avviso è previsto e può essere ignorato in modo sicuro.</span><span class="sxs-lookup"><span data-stu-id="a0920-190">This warning is expected and can be safely ignored.</span></span>



## <a name="to-verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="a0920-191">Per verificare la Federazione e l'accesso remoto per gli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="a0920-191">To verify federation and remote access for external users</span></span>

1.  <span data-ttu-id="a0920-192">Dal server front-end di Lync Server 2013 aprire Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="a0920-192">From the Lync Server 2013 Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="a0920-193">Per verificare lo stato di Federazione e accesso remoto, nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="a0920-193">To verify the status of federation and remote access, from the command line, type the following:</span></span>
    
        Get-CsAccessEdgeConfiguration

3.  <span data-ttu-id="a0920-194">Per abilitare la Federazione e l'accesso remoto, digitare quanto segue dalla riga di comando:</span><span class="sxs-lookup"><span data-stu-id="a0920-194">To enable federation and remote access, from the command line, type the following:</span></span>
    
        Set-CsAccessEdgeConfiguration
    
    <span data-ttu-id="a0920-195">Per altre informazioni su questi cmdlet, vedere gli argomenti seguenti: [Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg398574\(v=ocs.15\)) e [Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg413017\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="a0920-195">For more information on these cmdlets, see the following topics: [Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg398574\(v=ocs.15\)) and [Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg413017\(v=ocs.15\)).</span></span>

4.  <span data-ttu-id="a0920-196">Attendere che la replica sia stata completata prima di portare i server Edge di Lync Server 2013 online e verificare la Federazione e l'accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="a0920-196">Wait until replication has completed before bringing the Lync Server 2013 Edge servers online, and testing federation and external access.</span></span>

## <a name="to-configure-lync-server-2013-edge-server"></a><span data-ttu-id="a0920-197">Per configurare Lync Server 2013 Edge Server</span><span class="sxs-lookup"><span data-stu-id="a0920-197">To configure Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="a0920-198">Riunire tutti i server Edge di Lync Server 2013 online.</span><span class="sxs-lookup"><span data-stu-id="a0920-198">Bring all of the Lync Server 2013 Edge Servers online.</span></span>

2.  <span data-ttu-id="a0920-199">Aggiornare le regole di routing del firewall esterno o le impostazioni di bilanciamento del carico hardware per inviare il traffico SIP per l'accesso esterno (in genere la porta 443) e la Federazione (in genere la porta 5061) nel server perimetrale di Lync Server 2013, invece che nel server perimetrale legacy.</span><span class="sxs-lookup"><span data-stu-id="a0920-199">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Lync Server 2013 Edge Server, instead of the legacy Edge Server.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="a0920-200">Se non si dispone di un servizio di bilanciamento del carico hardware, è necessario aggiornare il record DNS per la Federazione per risolvere il nuovo server di Access Edge di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a0920-200">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve the new Lync Server Access Edge server.</span></span> <span data-ttu-id="a0920-201">Per eseguire questa operazione con un'interruzione minima, ridurre il valore TTL per l'FQDN di Access Edge di Lync Server esterno, in modo che quando il DNS viene aggiornato per posizionare il puntatore sul nuovo server di Access Edge di Lync Server, la Federazione e l'accesso remoto verranno aggiornati rapidamente.</span><span class="sxs-lookup"><span data-stu-id="a0920-201">To accomplish this with minimum disruption, reduce the TTL value for the external Lync Server Access Edge FQDN so that when DNS is updated to point to the new Lync Server Access Edge server, federation and remote access will be updated quickly.</span></span>



3.  <span data-ttu-id="a0920-202">Arrestare quindi il **bordo di accesso di Lync Server** da ogni computer Edge Server.</span><span class="sxs-lookup"><span data-stu-id="a0920-202">Next, stop the **Lync Server Access Edge** from each Edge Server computer.</span></span>

4.  <span data-ttu-id="a0920-203">Da ogni computer legacy Edge Server aprire l'applet **Servizi** dagli strumenti di **Amministrazione**.</span><span class="sxs-lookup"><span data-stu-id="a0920-203">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>

5.  <span data-ttu-id="a0920-204">Nell'elenco servizi individuare **Edge Access di Office Communications Server**.</span><span class="sxs-lookup"><span data-stu-id="a0920-204">In the services list, find **Office Communications Server Access Edge**.</span></span>

6.  <span data-ttu-id="a0920-205">Fare clic con il pulsante destro del mouse sul nome dei servizi e quindi scegliere **Interrompi** per arrestare il servizio.</span><span class="sxs-lookup"><span data-stu-id="a0920-205">Right-click the services name, and then select **Stop** to stop the service.</span></span>

7.  <span data-ttu-id="a0920-206">Impostare il tipo di avvio su **disabled**.</span><span class="sxs-lookup"><span data-stu-id="a0920-206">Set the Startup type to **Disabled**.</span></span>

8.  <span data-ttu-id="a0920-207">Fare clic su **OK** per chiudere la finestra **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="a0920-207">Click **OK** to close the **Properties** window.</span></span>

## <a name="to-test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="a0920-208">Per testare la connettività degli utenti esterni e dell'accesso esterno</span><span class="sxs-lookup"><span data-stu-id="a0920-208">To Test Connectivity of External Users and External access</span></span>

  - <span data-ttu-id="a0920-209">Utenti di almeno un dominio federato, un utente interno in Lync Server 2013 e un utente in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a0920-209">Users from at least one federated domain, an internal user on Lync Server 2013 and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="a0920-210">Test di messaggistica istantanea (IM), presenza, audio/video (A/V) e condivisione desktop.</span><span class="sxs-lookup"><span data-stu-id="a0920-210">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>

  - <span data-ttu-id="a0920-211">Utenti di ogni provider di servizi di messaggistica istantanea pubblico supportato dall'organizzazione (e per il quale è stato completato il provisioning) che comunica con un utente in Lync Server 2013 e un utente in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a0920-211">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Lync Server 2013 and a user on Office Communications Server 2007 R2.</span></span>

  - <span data-ttu-id="a0920-212">Verificare che gli utenti anonimi siano in grado di partecipare a conferenze.</span><span class="sxs-lookup"><span data-stu-id="a0920-212">Verify anonymous users are able to join conferences.</span></span>

  - <span data-ttu-id="a0920-213">Un utente ospitato in Office Communications Server 2007 R2 che usa l'accesso degli utenti remoti (accedendo a Office Communications Server 2007 R2 dall'esterno della Intranet ma senza VPN) con un utente in Lync Server 2013 e un utente in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a0920-213">A user hosted on Office Communications Server 2007 R2 using remote user access (logging into Office Communications Server 2007 R2 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="a0920-214">Test di messaggistica istantanea, presenza, A/V e condivisione desktop.</span><span class="sxs-lookup"><span data-stu-id="a0920-214">Test IM, presence, A/V, and desktop sharing.</span></span>

  - <span data-ttu-id="a0920-215">Un utente ospitato in Lync Server 2013 che usa l'accesso degli utenti remoti (accedendo a Lync Server 2013 dall'esterno della Intranet ma senza VPN) con un utente in Lync Server 2013 e un utente in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a0920-215">A user hosted on Lync Server 2013 using remote user access (logging into Lync Server 2013 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="a0920-216">Test di messaggistica istantanea, presenza, A/V e condivisione desktop.</span><span class="sxs-lookup"><span data-stu-id="a0920-216">Test IM, presence, A/V, and desktop sharing.</span></span>


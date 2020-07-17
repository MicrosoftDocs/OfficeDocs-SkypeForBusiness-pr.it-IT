---
title: Configurare le route di federazione e il traffico multimediale
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: ed6cb922-7863-453a-adce-2ce0ba761d74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721925(v=OCS.15)
ms:contentKeyID: 49733860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d6af77188809b092050629c1b74cdab8b20a2cc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754962"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="1df76-102">Configurare le route di federazione e il traffico multimediale</span><span class="sxs-lookup"><span data-stu-id="1df76-102">Configure federation routes and media traffic</span></span>

 


<span data-ttu-id="1df76-103">La federazione è una relazione di trust tra due o più domini SIP che consente a utenti di organizzazioni distinte di comunicare attraverso i confini della rete.</span><span class="sxs-lookup"><span data-stu-id="1df76-103">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="1df76-104">Dopo aver eseguito la migrazione al pool pilota di Lync Server 2013, è necessario eseguire la transizione dalla route di Federazione dei server perimetrali di Microsoft Office Communications Server 2007 R2 alla route di Federazione dei server perimetrali di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1df76-104">After you migrate to your Lync Server 2013 pilot pool, you need to transition from the federation route of your Microsoft Office Communications Server 2007 R2 Edge Servers to the federation route of your Lync Server 2013 Edge Servers.</span></span>

<span data-ttu-id="1df76-105">Utilizzare le procedure seguenti per la transizione della route di Federazione e della route del traffico multimediale dal server perimetrale e dal Director di Office Communications Server 2007 R2 al server perimetrale di Lync Server 2013, per una distribuzione a sito singolo.</span><span class="sxs-lookup"><span data-stu-id="1df76-105">Use the procedures that follow to transition the federation route and the media traffic route from your Office Communications Server 2007 R2 Edge Server and Director to your Lync Server 2013 Edge Server, for a single-site deployment.</span></span>


> [!IMPORTANT]  
> <span data-ttu-id="1df76-106">La modifica della route di Federazione e della route del traffico multimediale richiede la pianificazione di tempi di inattività di manutenzione per i server perimetrali di Lync Server 2013 e Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="1df76-106">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Lync Server 2013 and Office Communications Server 2007 R2 Edge Servers.</span></span> <span data-ttu-id="1df76-107">Il processo di transizione completo implica anche che l'accesso federato non sarà disponibile per l'intera durata dell'interruzione dei servizi.</span><span class="sxs-lookup"><span data-stu-id="1df76-107">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="1df76-108">È consigliabile pianificare l'interruzione dei servizi in un lasso di tempo in cui si prevede un'attività minima da parte degli utenti.</span><span class="sxs-lookup"><span data-stu-id="1df76-108">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="1df76-109">È inoltre consigliabile inviare notifica agli utenti con sufficiente anticipo.</span><span class="sxs-lookup"><span data-stu-id="1df76-109">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="1df76-110">Pianificare adeguatamente l'interruzione dei servizi e fare in modo che le aspettative dell'organizzazione siano appropriate.</span><span class="sxs-lookup"><span data-stu-id="1df76-110">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span>




> [!IMPORTANT]  
> <span data-ttu-id="1df76-111">Se il server perimetrale Office Communications Server 2007 R2 legacy è configurato in modo da utilizzare lo stesso FQDN per il servizio Access Edge, il servizio Web Conferencing Edge e il servizio A/V Edge, le procedure descritte in questa sezione per la transizione dell'impostazione di federazione a un server perimetrale di Lync Server 2013 non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="1df76-111">If your legacy Office Communications Server 2007 R2 Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section to transition the federation setting to a Lync Server 2013 Edge Server are not supported.</span></span> <span data-ttu-id="1df76-112">Se i servizi perimetrali legacy sono configurati per l'utilizzo dello stesso FQDN, è necessario prima eseguire la migrazione di tutti gli utenti da Office Communications Server 2007 R2 a Lync Server 2013, quindi rimuovere il server perimetrale di Office Communications Server 2007 R2 prima di abilitare la Federazione sul server perimetrale di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1df76-112">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users from Office Communications Server 2007 R2 to Lync Server 2013, then decommission the Office Communications Server 2007 R2 Edge Server before enabling federation on the Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="1df76-113">Per informazioni dettagliate, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="1df76-113">For details, see the following topics:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="1df76-114"><A href="move-remaining-users-to-lync-server-2013_1.md">Spostare gli utenti rimanenti in Lync Server 2013</A></span><span class="sxs-lookup"><span data-stu-id="1df76-114"><A href="move-remaining-users-to-lync-server-2013_1.md">Move remaining users to Lync Server 2013</A></span></span></P>
> <LI>
> <P><span data-ttu-id="1df76-115">"Rimozione di server e ruoli del server" all'indirizzo<A href="https://go.microsoft.com/fwlink/p/?linkid=268790">https://go.microsoft.com/fwlink/p/?LinkId=268790</A></span><span class="sxs-lookup"><span data-stu-id="1df76-115">"Remove Servers and Server Roles" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268790">https://go.microsoft.com/fwlink/p/?LinkId=268790</A></span></span></P></LI></UL>




> [!IMPORTANT]  
> <span data-ttu-id="1df76-116">Se la Federazione XMPP viene instradata attraverso un server perimetrale di Lync Server 2013, gli utenti di Office Communications Server 2007 R2 legacy non saranno in grado di comunicare con il partner federato XMPP finché tutti gli utenti non sono stati spostati in Lync Server 2013, sono stati configurati i criteri e i certificati XMPP, il partner federato XMPP è stato configurato su Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1df76-116">If your XMPP federation is routed through a Lync Server 2013 Edge Server, legacy Office Communications Server 2007 R2 users will not be able to communicate with the XMPP federated partner until all users have been moved to Lync Server 2013, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Lync Server 2013, and lastly the DNS entries have been updated.</span></span>



<span data-ttu-id="1df76-117">Per pubblicare, abilitare o disabilitare correttamente una topologia quando si aggiunge o si rimuove un ruolo del server, è necessario aver eseguito l'accesso come utente membro dei gruppi RTCUniversalServerAdmins e Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="1df76-117">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="1df76-118">È inoltre possibile delegare le autorizzazioni e i diritti utente appropriati per l'aggiunta di ruoli del server.</span><span class="sxs-lookup"><span data-stu-id="1df76-118">It is also possible to delegate the proper user rights and permissions for adding server roles.</span></span> <span data-ttu-id="1df76-119">Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync server 2013](lync-server-2013-delegate-setup-permissions.md) nella documentazione relativa alla distribuzione di server Standard Edition o Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="1df76-119">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="1df76-120">Per poter apportare altre modifiche alla configurazione, è necessaria solo l'appartenenza al gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="1df76-120">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a><span data-ttu-id="1df76-121">Per rimuovere l'associazione di federazione legacy dai siti di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1df76-121">To remove the legacy federation association from Lync Server 2013 sites</span></span>

1.  <span data-ttu-id="1df76-122">Aprire la topologia pool pilota utilizzando Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="1df76-122">Open the pilot pool topology using Topology Builder.</span></span>

2.  <span data-ttu-id="1df76-123">Nel riquadro sinistro passare al nodo del sito.</span><span class="sxs-lookup"><span data-stu-id="1df76-123">In the left pane, navigate to the site node.</span></span>

3.  <span data-ttu-id="1df76-124">Fare clic con il pulsante destro del mouse sul sito e quindi scegliere  \*\*Modifica proprietà \*\*.</span><span class="sxs-lookup"><span data-stu-id="1df76-124">Right-click the site, and then click **Edit Properties**.</span></span>

4.  <span data-ttu-id="1df76-125">Selezionare **Route di federazione** nel riquadro sinistro.</span><span class="sxs-lookup"><span data-stu-id="1df76-125">Select **Federation route** in the left pane.</span></span>

5.  <span data-ttu-id="1df76-126">In Assegnazione route federazione sito deselezionare la casella di controllo accanto a **Abilita federazione SIP** per disabilitare la route di federazione tramite **BackCompatSite**.</span><span class="sxs-lookup"><span data-stu-id="1df76-126">Under Site federation route assignment, clear the check box next to **Enable SIP federation** to disable the federation route through the **BackCompatSite**.</span></span>
    
    <span data-ttu-id="1df76-127">![Finestra di dialogo Modifica proprietà, route di Federazione](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Finestra di dialogo Modifica proprietà, route di Federazione")</span><span class="sxs-lookup"><span data-stu-id="1df76-127">![Edit Properties dialog, Federation route](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Edit Properties dialog, Federation route")</span></span>

6.  <span data-ttu-id="1df76-128">Fare clic su  **OK** per chiudere la pagina Modifica proprietà.</span><span class="sxs-lookup"><span data-stu-id="1df76-128">Click **OK** to close the Edit Properties page.</span></span>

7.  <span data-ttu-id="1df76-129">In **Generatore di topologie** selezionare il nodo di primo livello **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="1df76-129">From **Topology Builder**, select the top node **Lync Server**.</span></span>

8.  <span data-ttu-id="1df76-130">Nel menu **Azione** fare clic su **Pubblica topologia** e quindi completare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="1df76-130">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="1df76-131">Per configurare il server perimetrale legacy come server perimetrale non federato</span><span class="sxs-lookup"><span data-stu-id="1df76-131">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1.  <span data-ttu-id="1df76-132">In **Generatore di tipologie** scegliere **Unisci la topologia Office Communications Server 2007 R2** dal menu **Azione**.</span><span class="sxs-lookup"><span data-stu-id="1df76-132">From **Topology Builder**, from the **Action** menu click **Merge Office Communications Server 2007 R2 Topology**.</span></span>

2.  <span data-ttu-id="1df76-133">Fare clic su **Avanti** per continuare.</span><span class="sxs-lookup"><span data-stu-id="1df76-133">Click **Next** to continue.</span></span>

3.  <span data-ttu-id="1df76-134">In **Specificare installazione server perimetrale** selezionare il nome **FQDN interno del server perimetrale** attualmente configurato per la federazione e quindi fare clic su **Cambia**.</span><span class="sxs-lookup"><span data-stu-id="1df76-134">On the **Specify Edge Setup**, select the **Edge Server Internal FQDN** that is currently configured for federation, and then click **Change**.</span></span>
    
    <span data-ttu-id="1df76-135">![Unire la topologia OCS 2007 R2, specificare l'installazione del server perimetrale](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Unire la topologia OCS 2007 R2, specificare l'installazione del server perimetrale")</span><span class="sxs-lookup"><span data-stu-id="1df76-135">![Merge OCS 2007 R2 Topology, Specify Edge Setup](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Merge OCS 2007 R2 Topology, Specify Edge Setup")</span></span>

4.  <span data-ttu-id="1df76-136">Fare clic su **Avanti** e accettare le impostazioni predefinite finché non viene visualizzata la pagina **Specificare il perimetro esterno**:</span><span class="sxs-lookup"><span data-stu-id="1df76-136">Click **Next** and accept the default settings until you get to the **Specify External Edge** page:</span></span>
    
    <span data-ttu-id="1df76-137">![Generatore di topologie specificare la pagina perimetro esterno](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "Generatore di topologie specificare la pagina perimetro esterno")</span><span class="sxs-lookup"><span data-stu-id="1df76-137">![Topology Builder Specify External Edge page](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "Topology Builder Specify External Edge page")</span></span>

5.  <span data-ttu-id="1df76-p105">In **Specificare il perimetro esterno** deselezionare la casella di controllo **Questo pool di server perimetrali è utilizzato per la federazione e la connettività di messaggistica istantanea pubblica**. In questo modo verrà rimossa l'associazione di federazione con BackCompatSite.</span><span class="sxs-lookup"><span data-stu-id="1df76-p105">In **Specify External Edge**, clear the **This Edge pool is used for federation and public IM connectivity** check box. This will remove the federation association with the BackCompatSite.</span></span>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1df76-p106">Questo passaggio è importante. È necessario deselezionare questa opzione per rimuovere l'associazione di federazione legacy.</span><span class="sxs-lookup"><span data-stu-id="1df76-p106">This step is important. You must clear this option to remove the legacy federation association.</span></span>



6.  <span data-ttu-id="1df76-142">Fare clic su **Avanti** e accettare le impostazioni predefinite delle pagine rimanenti della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="1df76-142">Click **Next** and accept the default settings of the remaining pages of the wizard.</span></span>

7.  <span data-ttu-id="1df76-143">In **Riepilogo** fare clic su **Avanti** per iniziare a unire le topologie.</span><span class="sxs-lookup"><span data-stu-id="1df76-143">In **Summary**, click **Next** to begin merging the topologies.</span></span>

8.  <span data-ttu-id="1df76-144">Nella colonna **stato** verificare che il valore sia **esito positivo**e quindi fare clic su **fine** per chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="1df76-144">In the **Status** column, verify that the value is **Success**, and then click **Finish** to close the wizard.</span></span>

9.  <span data-ttu-id="1df76-145">Scegliere **Pubblica topologia** dal menu **Azione** e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1df76-145">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

10. <span data-ttu-id="1df76-146">Al termine della **Pubblicazione guidata** fare clic su **Fine** per chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="1df76-146">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>
    
    <span data-ttu-id="1df76-147">![Generatore di topologie con sito visualizzato dopo l'Unione](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Generatore di topologie con sito visualizzato dopo l'Unione")</span><span class="sxs-lookup"><span data-stu-id="1df76-147">![Topology Builder with site displayed after merge](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Topology Builder with site displayed after merge")</span></span>
    
    <span data-ttu-id="1df76-148">Come illustrato nella figura precedente, la **federazione SIP** presente in **Assegnazione route federazione sito** è impostata su **Disabilitata**.</span><span class="sxs-lookup"><span data-stu-id="1df76-148">As shown in the previous figure, the **SIP federation** located under **Site federation route assignment** is set to **Disabled**.</span></span>

## <a name="to-configure-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="1df76-149">Per configurare i certificati nel server perimetrale Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1df76-149">To configure certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="1df76-150">Esportare il certificato del proxy di accesso esterno, con la chiave privata, dal server perimetrale Office Communications Server 2007 R2 legacy.</span><span class="sxs-lookup"><span data-stu-id="1df76-150">Export the external Access Proxy certificate, with the private key, from the legacy Office Communications Server 2007 R2 Edge Server.</span></span>

2.  <span data-ttu-id="1df76-151">Nel server perimetrale di Lync Server 2013 importare il certificato esterno del proxy di accesso dal passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="1df76-151">On the Lync Server 2013 Edge Server, import the Access Proxy external certificate from the previous step.</span></span>

3.  <span data-ttu-id="1df76-152">Assegnare il certificato esterno del proxy di accesso all'interfaccia esterna di Lync Server 2013 del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="1df76-152">Assign the Access Proxy external certificate to the Lync Server 2013 external interface of the Edge Server.</span></span>

4.  <span data-ttu-id="1df76-153">Il certificato dell'interfaccia interna del server perimetrale di Lync Server 2013 non deve essere modificato.</span><span class="sxs-lookup"><span data-stu-id="1df76-153">The internal interface certificate of the Lync Server 2013 Edge Server should not be changed.</span></span>

## <a name="to-change-office-communications-server-2007-r2-federation-route-to-use-lync-server-2013-edge-server"></a><span data-ttu-id="1df76-154">Per modificare la route di federazione di Office Communications Server 2007 R2 per l'utilizzo del server perimetrale Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1df76-154">To change Office Communications Server 2007 R2 federation route to use Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="1df76-155">Nel server Office Communications Server 2007 R2 Standard Edition o front end server aprire lo strumento di amministrazione di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="1df76-155">On the Office Communications Server 2007 R2 Standard Edition server or Front End Server, open the Office Communications Server 2007 R2 Administrative tool.</span></span>

2.  <span data-ttu-id="1df76-p107">Nel riquadro sinistro espandere il nodo superiore e quindi fare clic con il pulsante destro del mouse sul nodo **Foresta**. Scegliere **Proprietà** e quindi fare clic su **Proprietà globali**.</span><span class="sxs-lookup"><span data-stu-id="1df76-p107">In the left pane, expand the top node, and then right-click the **Forest** node. Select **Properties**, and then click **Global Properties**.</span></span>

3.  <span data-ttu-id="1df76-158">Fare clic sulla scheda **Federazione**.</span><span class="sxs-lookup"><span data-stu-id="1df76-158">Click the **Federation** tab.</span></span>

4.  <span data-ttu-id="1df76-159">Selezionare la casella di controllo per abilitare la federazione e la connettività per messaggistica istantanea pubblica.</span><span class="sxs-lookup"><span data-stu-id="1df76-159">Select the check box to enable federation and Public IM connectivity.</span></span>

5.  <span data-ttu-id="1df76-160">Immettere il nome di dominio completo del server perimetrale di Lync Server 2013 e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="1df76-160">Enter the FQDN of the Lync Server 2013 Edge Server, and then click **OK**.</span></span>
    
    <span data-ttu-id="1df76-161">![Proprietà globali di OCS, scheda Federazione](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "Proprietà globali di OCS, scheda Federazione")</span><span class="sxs-lookup"><span data-stu-id="1df76-161">![OCS Global Properties, Federation tab](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "OCS Global Properties, Federation tab")</span></span>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a><span data-ttu-id="1df76-162">Per abilitare la federazione del server perimetrale di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1df76-162">To turn on Lync Server 2013 Edge Server federation</span></span>

1.  <span data-ttu-id="1df76-163">In Generatore di topologie, nel riquadro sinistro, passare al nodo Pool di server **perimetrali** di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="1df76-163">From Topology Builder, in the left pane, navigate to the Lync Server 2013 **Edge pools** node.</span></span>

2.  <span data-ttu-id="1df76-164">Espandere il nodo, fare clic con il pulsante destro del mouse sul server perimetrale elencato e quindi scegliere  \*\*Modifica proprietà \*\*.</span><span class="sxs-lookup"><span data-stu-id="1df76-164">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="1df76-165">La Federazione può essere abilitata solo per un singolo pool di server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="1df76-165">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="1df76-166">In presenza di più pool di server perimetrali, selezionarne uno da utilizzare come pool di server perimetrali federati.</span><span class="sxs-lookup"><span data-stu-id="1df76-166">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span>



3.  <span data-ttu-id="1df76-167">Nella pagina **Generale** selezionare la casella di controllo **Abilita federazione per pool di server perimetrali (porta 5061)**.</span><span class="sxs-lookup"><span data-stu-id="1df76-167">On the **General** page, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
    <span data-ttu-id="1df76-168">![Modifica proprietà, generale, Abilita federazione Edge](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "Modifica proprietà, generale, Abilita federazione Edge")</span><span class="sxs-lookup"><span data-stu-id="1df76-168">![Edit Properties, General, Enable Edge Federation](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "Edit Properties, General, Enable Edge Federation")</span></span>

4.  <span data-ttu-id="1df76-169">Fare clic su  **OK** per chiudere la pagina Modifica proprietà.</span><span class="sxs-lookup"><span data-stu-id="1df76-169">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="1df76-170">Passare quindi al nodo del sito.</span><span class="sxs-lookup"><span data-stu-id="1df76-170">Next, navigate to the site node.</span></span>

6.  <span data-ttu-id="1df76-171">Fare clic con il pulsante destro del mouse sul sito e quindi scegliere  \*\*Modifica proprietà \*\*.</span><span class="sxs-lookup"><span data-stu-id="1df76-171">Right-click the site, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="1df76-172">Nel riquadro sinistro fare clic su  \*\*Route di federazione \*\*.</span><span class="sxs-lookup"><span data-stu-id="1df76-172">In the left pane, click **Federation route**.</span></span>

8.  <span data-ttu-id="1df76-173">In **Assegnazione route federazione sito**selezionare **Abilita federazione SIP**e quindi nell'elenco selezionare il server perimetrale di Lync Server 2013 elencato.</span><span class="sxs-lookup"><span data-stu-id="1df76-173">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Lync Server 2013 Edge Server listed.</span></span>

9.  <span data-ttu-id="1df76-174">Fare clic su  \*\*OK \*\* per chiudere la pagina  \*\*Modifica proprietà \*\*.</span><span class="sxs-lookup"><span data-stu-id="1df76-174">Click **OK** to close the **Edit Properties** page.</span></span>
    
    <span data-ttu-id="1df76-175">![Modifica proprietà, generale, associa pool di server perimetrali](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Modifica proprietà, generale, associa pool di server perimetrali")</span><span class="sxs-lookup"><span data-stu-id="1df76-175">![Edit Properties, General, Associate Edge pool](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Edit Properties, General, Associate Edge pool")</span></span>
    
    <span data-ttu-id="1df76-176">Nel caso di distribuzioni multisito, eseguire questa procedura in ogni sito.</span><span class="sxs-lookup"><span data-stu-id="1df76-176">For multi-site deployments, complete this procedure at each site.</span></span>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a><span data-ttu-id="1df76-177">Per configurare il percorso del contenuto multimediale in uscita dei server perimetrali Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1df76-177">To configure Lync Server 2013 Edge Server outbound media path</span></span>

1.  <span data-ttu-id="1df76-178">In **Generatore di topologie**passare al pool di Lync Server 2013 al di sotto di **Standard Edition Front End Server** o **pool Enterprise Edition front end**.</span><span class="sxs-lookup"><span data-stu-id="1df76-178">From **Topology Builder**, navigate to the Lync Server 2013 pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>

2.  <span data-ttu-id="1df76-179">Fare clic con il pulsante destro del mouse sul pool e quindi scegliere  \*\*Modifica proprietà \*\*.</span><span class="sxs-lookup"><span data-stu-id="1df76-179">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="1df76-180">Nella sezione  \*\*Associazioni \*\* selezionare la casella di controllo  \*\*Associa pool di server perimetrali (per componenti multimediali) \*\*.</span><span class="sxs-lookup"><span data-stu-id="1df76-180">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span>

4.  <span data-ttu-id="1df76-181">Nella casella a discesa selezionare il server perimetrale di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1df76-181">From the drop down box, select the Lync Server 2013 Edge Server.</span></span>
    
    <span data-ttu-id="1df76-182">![Finestra di dialogo Modifica proprietà, associa pool di server perimetrali](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Finestra di dialogo Modifica proprietà, associa pool di server perimetrali")</span><span class="sxs-lookup"><span data-stu-id="1df76-182">![Edit Properties dialog, Associate Edge Pool](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Edit Properties dialog, Associate Edge Pool")</span></span>

5.  <span data-ttu-id="1df76-183">Fare clic su **OK** per chiudere la pagina **Modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="1df76-183">Click **OK** to close the **Edit Properties** page.</span></span>

## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="1df76-184">Per pubblicare le modifiche di configurazione del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="1df76-184">To publish Edge Server configuration changes</span></span>

1.  <span data-ttu-id="1df76-185">In **Generatore di topologie** selezionare il nodo principale **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="1df76-185">From **Topology Builder**, select the top node **Lync Server**.</span></span>

2.  <span data-ttu-id="1df76-186">Scegliere **Pubblica topologia** dal menu **Azione** e quindi completare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="1df76-186">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

3.  <span data-ttu-id="1df76-187">Attendere il completamento della replica di Active Directory in tutti i pool della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="1df76-187">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="1df76-188">Potrebbe essere visualizzato il messaggio seguente:</span><span class="sxs-lookup"><span data-stu-id="1df76-188">You may see the following message:</span></span><BR><span data-ttu-id="1df76-189"><STRONG>Avviso: la topologia contiene più di un server perimetrale federato. Questa situazione può verificarsi durante la migrazione a una versione successiva del prodotto. In questo caso, per la federazione viene utilizzato attivamente un solo server perimetrale. Verificare che il record SRV DNS punti al server perimetrale corretto. Se si desidera distribuire più server perimetrali federati in modo che siano attivi contemporaneamente (ovvero non in uno scenario di migrazione), verificare che tutti i partner federati utilizzino Office Communications Server 2007 R2 o versione successiva e che il record SRV DNS esterno elenchi tutti i server perimetrali abilitati per la federazione.</STRONG></span><span class="sxs-lookup"><span data-stu-id="1df76-189"><STRONG>Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Office Communications Server 2007 R2 or Lync Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.</STRONG></span></span><BR><span data-ttu-id="1df76-190">Si tratta di un avviso previsto che può essere tranquillamente ignorato.</span><span class="sxs-lookup"><span data-stu-id="1df76-190">This warning is expected and can be safely ignored.</span></span>



## <a name="to-verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="1df76-191">Per verificare la federazione e l'accesso remoto per gli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="1df76-191">To verify federation and remote access for external users</span></span>

1.  <span data-ttu-id="1df76-192">Dal front end server Lync Server 2013 aprire Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="1df76-192">From the Lync Server 2013 Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="1df76-193">Per verificare lo stato della federazione e dell'accesso remoto, digitare dalla riga di comando quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1df76-193">To verify the status of federation and remote access, from the command line, type the following:</span></span>
    
        Get-CsAccessEdgeConfiguration

3.  <span data-ttu-id="1df76-194">Per abilitare la federazione e l'accesso remoto, digitare dalla riga di comando quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1df76-194">To enable federation and remote access, from the command line, type the following:</span></span>
    
        Set-CsAccessEdgeConfiguration
    
    <span data-ttu-id="1df76-195">Per ulteriori informazioni su questi cmdlet, vedere i seguenti argomenti: [Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg398574\(v=ocs.15\)) e [Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg413017\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="1df76-195">For more information on these cmdlets, see the following topics: [Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg398574\(v=ocs.15\)) and [Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg413017\(v=ocs.15\)).</span></span>

4.  <span data-ttu-id="1df76-196">Attendere che la replica sia stata completata prima di portare i server perimetrali di Lync Server 2013 online e verificare la Federazione e l'accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="1df76-196">Wait until replication has completed before bringing the Lync Server 2013 Edge servers online, and testing federation and external access.</span></span>

## <a name="to-configure-lync-server-2013-edge-server"></a><span data-ttu-id="1df76-197">Per configurare il server perimetrale Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1df76-197">To configure Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="1df76-198">Portare online tutti i server perimetrali di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1df76-198">Bring all of the Lync Server 2013 Edge Servers online.</span></span>

2.  <span data-ttu-id="1df76-199">Aggiornare le regole di routing del firewall esterno o le impostazioni del servizio di bilanciamento del carico hardware in modo da inviare il traffico SIP per l'accesso esterno (in genere la porta 443) e la Federazione (in genere la porta 5061) al server perimetrale di Lync Server 2013, anziché al server perimetrale legacy.</span><span class="sxs-lookup"><span data-stu-id="1df76-199">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Lync Server 2013 Edge Server, instead of the legacy Edge Server.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="1df76-p109">Se non si dispone di un servizio di bilanciamento del carico hardware, è necessario aggiornare il record DNS A per la federazione in modo che rimandi al nuovo server Lync Server Access Edge. Per eseguire questa operazione con il minimo impatto sul servizio, ridurre il valore TTL dell'FQDN del Lync Server Access Edge esterno in modo che quando il DNS viene aggiornato per puntare al nuovo server Lync Server Access Edge, la federazione e l'accesso remoto vengono aggiornati rapidamente.</span><span class="sxs-lookup"><span data-stu-id="1df76-p109">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve the new Lync Server Access Edge server. To accomplish this with minimum disruption, reduce the TTL value for the external Lync Server Access Edge FQDN so that when DNS is updated to point to the new Lync Server Access Edge server, federation and remote access will be updated quickly.</span></span>



3.  <span data-ttu-id="1df76-202">Successivamente, arrestare **Lync Server Access Edge** da ogni computer server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="1df76-202">Next, stop the **Lync Server Access Edge** from each Edge Server computer.</span></span>

4.  <span data-ttu-id="1df76-203">Da ogni computer server perimetrale legacy, aprire l'applet **Servizi** dagli **strumenti di amministrazione**.</span><span class="sxs-lookup"><span data-stu-id="1df76-203">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>

5.  <span data-ttu-id="1df76-204">Individuare **Office Communications Server Access Edge** tra i servizi elencati.</span><span class="sxs-lookup"><span data-stu-id="1df76-204">In the services list, find **Office Communications Server Access Edge**.</span></span>

6.  <span data-ttu-id="1df76-205">Fare clic con il pulsante destro del mouse sul nome del servizio e quindi scegliere **Arresta** per arrestare il servizio.</span><span class="sxs-lookup"><span data-stu-id="1df76-205">Right-click the services name, and then select **Stop** to stop the service.</span></span>

7.  <span data-ttu-id="1df76-206">Impostare il tipo di avvio su **Disabilitato**.</span><span class="sxs-lookup"><span data-stu-id="1df76-206">Set the Startup type to **Disabled**.</span></span>

8.  <span data-ttu-id="1df76-207">Fare clic su **OK** per chiudere la finestra **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="1df76-207">Click **OK** to close the **Properties** window.</span></span>

## <a name="to-test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="1df76-208">Per testare la connettività degli utenti esterni e dell'accesso esterno</span><span class="sxs-lookup"><span data-stu-id="1df76-208">To Test Connectivity of External Users and External access</span></span>

  - <span data-ttu-id="1df76-209">Utenti provenienti da almeno un dominio federato, un utente interno in Lync Server 2013 e un utente in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="1df76-209">Users from at least one federated domain, an internal user on Lync Server 2013 and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="1df76-210">Testare la messaggistica istantanea, il traffico audio/video e la condivisione del desktop.</span><span class="sxs-lookup"><span data-stu-id="1df76-210">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>

  - <span data-ttu-id="1df76-211">Utenti di ogni provider di servizi di messaggistica istantanea supportato dall'organizzazione (e per i quali è stato completato il provisioning) che comunicano con un utente in Lync Server 2013 e un utente in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="1df76-211">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Lync Server 2013 and a user on Office Communications Server 2007 R2.</span></span>

  - <span data-ttu-id="1df76-212">Verificare che gli utenti anonimi siano in grado di partecipare alle conferenze.</span><span class="sxs-lookup"><span data-stu-id="1df76-212">Verify anonymous users are able to join conferences.</span></span>

  - <span data-ttu-id="1df76-213">Un utente ospitato in Office Communications Server 2007 R2 utilizzando l'accesso utente remoto (connessione a Office Communications Server 2007 R2 dall'esterno della rete Intranet ma senza VPN) con un utente in Lync Server 2013 e un utente in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="1df76-213">A user hosted on Office Communications Server 2007 R2 using remote user access (logging into Office Communications Server 2007 R2 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="1df76-214">Testare la messaggistica istantanea, la presenza, il traffico audio/video e la condivisione del desktop.</span><span class="sxs-lookup"><span data-stu-id="1df76-214">Test IM, presence, A/V, and desktop sharing.</span></span>

  - <span data-ttu-id="1df76-215">Un utente ospitato in Lync Server 2013 utilizzando l'accesso degli utenti remoti (accedendo a Lync Server 2013 dall'esterno della rete Intranet ma senza VPN) con un utente in Lync Server 2013 e un utente in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="1df76-215">A user hosted on Lync Server 2013 using remote user access (logging into Lync Server 2013 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="1df76-216">Testare la messaggistica istantanea, la presenza, il traffico audio/video e la condivisione del desktop.</span><span class="sxs-lookup"><span data-stu-id="1df76-216">Test IM, presence, A/V, and desktop sharing.</span></span>


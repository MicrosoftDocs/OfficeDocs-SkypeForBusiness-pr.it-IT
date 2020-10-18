---
title: 'Lync Server 2013: definire la topologia perimetrale'
description: 'Lync Server 2013: definire la topologia perimetrale.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define your edge topology
ms:assetid: 787b23f1-8fa0-4c37-abf2-c516c5dd66f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398591(v=OCS.15)
ms:contentKeyID: 48184562
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd4aa16ca23d24f0edd92189216030ef926fc841
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572942"
---
# <a name="define-your-edge-topology-in-lync-server-2013"></a><span data-ttu-id="a2380-103">Definire la topologia perimetrale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2380-103">Define your edge topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2380-104">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="a2380-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="a2380-105">Per poter distribuire il server perimetrale, è necessario utilizzare Generatore di topologie per creare la topologia ed è necessario configurare almeno un pool Front End interno o un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="a2380-105">You must use Topology Builder to build your topology and you must set up at least one internal Front End pool or Standard Edition server before you can deploy your Edge Server.</span></span> <span data-ttu-id="a2380-106">Utilizzare la procedura seguente per definire la topologia perimetrale per un singolo server perimetrale e quindi utilizzare le procedure descritte in [pubblicare la topologia in Lync server 2013](lync-server-2013-publish-your-topology.md) ed [esportare la topologia di Lync Server 2013 e copiarla su supporto esterno per l'installazione perimetrale](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) per pubblicare la topologia e renderla disponibile per il server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="a2380-106">Use the following procedure to define the edge topology for a single Edge Server, and then use the procedures in [Publish your topology in Lync Server 2013](lync-server-2013-publish-your-topology.md) and [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) to publish the topology and make it available to your Edge Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a2380-p102">Per l'interfaccia perimetrale interna e per quella esterna è necessario utilizzare lo stesso tipo di bilanciamento del carico. Non è possibile utilizzare il bilanciamento del carico DNS in un'interfaccia perimetrale e il bilanciamento del carico hardware nell'altra.</span><span class="sxs-lookup"><span data-stu-id="a2380-p102">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>



</div>

<span data-ttu-id="a2380-109">Per pubblicare, abilitare o disabilitare correttamente una topologia quando si aggiunge o rimuove un ruolo del server, è necessario aver effettuato l'accesso come membro dei gruppi RTCUniversalServerAdmins e Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="a2380-109">To successfully publish, enable, or disable a topology when adding or removing a server role, you must be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="a2380-110">È anche possibile concedere le autorizzazioni e i diritti di amministratore necessari per l'aggiunta di ruoli del server a un account utente.</span><span class="sxs-lookup"><span data-stu-id="a2380-110">You can also grant the administrator rights and permissions required for adding server roles to a user account.</span></span> <span data-ttu-id="a2380-111">Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync server 2013](lync-server-2013-delegate-setup-permissions.md) nella documentazione relativa alla distribuzione di server Standard Edition o Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="a2380-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="a2380-112">Per altre modifiche di configurazione, è necessaria solo l'appartenenza al gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="a2380-112">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<span data-ttu-id="a2380-113">Se la topologia perimetrale è stata definita durante la definizione e la pubblicazione della topologia interna e non sono richieste modifiche alla topologia perimetrale creata in precedenza, non è necessario definirla e pubblicarla di nuovo.</span><span class="sxs-lookup"><span data-stu-id="a2380-113">If you defined your edge topology when you defined and published your internal topology, and no changes are required to the edge topology that you previously defined, you do not need to do define it and publish it again.</span></span> <span data-ttu-id="a2380-114">Utilizzare la procedura seguente solo se è necessario apportare modifiche alla topologia perimetrale.</span><span class="sxs-lookup"><span data-stu-id="a2380-114">Use the following procedure only if you need to make changes to your edge topology.</span></span> <span data-ttu-id="a2380-115">È necessario rendere disponibile la topologia precedentemente definita e pubblicata ai server perimetrali, eseguendo la procedura descritta in [esportare la topologia di Lync Server 2013 e copiarla su supporto esterno per l'installazione perimetrale](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span><span class="sxs-lookup"><span data-stu-id="a2380-115">You must make the previously defined and published topology available to your Edge Servers, which you do by using the procedure in [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a2380-116">Non è possibile eseguire Generatore di topologie da un server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="a2380-116">You cannot run Topology Builder from an Edge Server.</span></span> <span data-ttu-id="a2380-117">È necessario eseguirlo dal front end server o server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="a2380-117">You must run it from your Front End Server or Standard Edition servers.</span></span>



</div>

<span data-ttu-id="a2380-118">Il processo per la definizione della topologia del server perimetrale viene effettuato in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="a2380-118">The process to define your Edge Server topology is done in Topology Builder.</span></span> <span data-ttu-id="a2380-119">In seguito sono elencati i tre tipi principali di topologie dei server perimetrali che è possibile pianificare e configurare:</span><span class="sxs-lookup"><span data-stu-id="a2380-119">The three primary types of Edge Server topologies that you plan and configure are listed below:</span></span>

  - <span data-ttu-id="a2380-120">Per definire la topologia per un singolo server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a2380-120">To define the Topology for a Single Edge Server</span></span>

  - <span data-ttu-id="a2380-121">Per definire la topologia per un pool di server perimetrali con bilanciamento del carico</span><span class="sxs-lookup"><span data-stu-id="a2380-121">To define the Topology for a Load Balanced Edge Server Pool</span></span>

  - <span data-ttu-id="a2380-122">Per definire la topologia per un pool di server perimetrali con bilanciamento del carico hardware</span><span class="sxs-lookup"><span data-stu-id="a2380-122">To define the Topology for a Hardware Load Balanced Edge Pool</span></span>

<div>

## <a name="to-define-the-topology-for-a-single-edge-server"></a><span data-ttu-id="a2380-123">Per definire la topologia per un singolo server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a2380-123">To define the topology for a single Edge Server</span></span>

1.  <span data-ttu-id="a2380-124">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.</span><span class="sxs-lookup"><span data-stu-id="a2380-124">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="a2380-125">Nell'albero della console espandere il sito in cui si desidera distribuire un server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="a2380-125">In the console tree, expand the site in which you want to deploy an Edge Server.</span></span>

3.  <span data-ttu-id="a2380-126">Fare clic con il pulsante destro del mouse su pool **Edge**e quindi scegliere **nuovo pool di server perimetrali**.</span><span class="sxs-lookup"><span data-stu-id="a2380-126">Right-click **Edge pools**, and then click **New Edge Pool**.</span></span>

4.  <span data-ttu-id="a2380-127">In **Definire il nuovo pool di server perimetrali** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a2380-127">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="a2380-128">In **Definire l'FQDN del pool di server perimetrali** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2380-128">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="a2380-129">In **FQDN pool** digitare il nome di dominio completo (FQDN) dell'interfaccia interna per il server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="a2380-129">In **Pool FQDN**, type the fully qualified domain name (FQDN) of the internal interface for the Edge Server.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="a2380-130">Il nome specificato deve essere uguale al nome computer configurato nel server.</span><span class="sxs-lookup"><span data-stu-id="a2380-130">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="a2380-131">Per impostazione predefinita, il nome di un computer non aggiunto a un dominio è un nome breve e non un FQDN.</span><span class="sxs-lookup"><span data-stu-id="a2380-131">By default the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="a2380-132">Generatore di topologie utilizza gli FQDN e non i nomi brevi.</span><span class="sxs-lookup"><span data-stu-id="a2380-132">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="a2380-133">Pertanto, è necessario configurare un suffisso DNS sul nome del computer da distribuire come server perimetrale non aggiunto a un dominio.</span><span class="sxs-lookup"><span data-stu-id="a2380-133">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="a2380-134">Utilizzare solo caratteri standard, ovvero A-Z, a-z, 0-9 e trattini, per assegnare FQDN dei server Lync Server, dei server perimetrali e dei pool.</span><span class="sxs-lookup"><span data-stu-id="a2380-134">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="a2380-135">Non utilizzare caratteri Unicode o di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="a2380-135">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="a2380-136">La presenza di caratteri non standard in un FQDN è spesso non supportata da DNS esterni e CA pubbliche (quando l'FQDN deve essere assegnato al nome soggetto nel certificato).</span><span class="sxs-lookup"><span data-stu-id="a2380-136">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="a2380-137">Per informazioni dettagliate sull'aggiunta di un suffisso DNS a un nome computer, vedere <A href="lync-server-2013-configure-dns-for-edge-support.md">configure DNS for Edge support in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a2380-137">For details about adding a DNS suffix to a computer name, see <A href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</A>.</span></span>

        
        </div>
    
      - <span data-ttu-id="a2380-138">Fare clic su **Pool computer singolo** e quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a2380-138">Click **Single computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="a2380-139">In **Selezionare funzionalità** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2380-139">In **Select features**, do the following:</span></span>
    
      - <span data-ttu-id="a2380-140">Se si prevede di utilizzare un singolo FQDN e indirizzo IP per il servizio di accesso SIP, il servizio Web Conferencing di Lync Server 2013 e i servizi A/V Edge, selezionare la casella di controllo **utilizza un singolo FQDN e indirizzo IP** .</span><span class="sxs-lookup"><span data-stu-id="a2380-140">If you plan to use a single FQDN and IP address for the SIP Access service, Lync Server 2013 Web Conferencing service, and A/V Edge services, select the **Use a single FQDN and IP Address** check box.</span></span>
    
      - <span data-ttu-id="a2380-141">Se si prevede di abilitare la federazione, selezionare la casella di controllo **Abilita la federazione per questo pool di server perimetrali (porta 5061)**.</span><span class="sxs-lookup"><span data-stu-id="a2380-141">If you plan to enable federation select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a2380-p108">È possibile selezionare questa opzione, ma è possibile pubblicare esternamente per la federazione solo un pool di server perimetrali o un server perimetrale nell'organizzazione. Tutto l'accesso da parte di utenti federati, inclusi gli utenti di messaggistica istantanea pubblica, passa per lo stesso pool di server perimetrali o singolo server perimetrale. Se, ad esempio, la distribuzione include un pool di server perimetrali o un singolo server perimetrale distribuito a New York e uno distribuito a Londra e si abilita il supporto per la federazione nel pool di server perimetrali o nel server perimetrale di New York, il traffico dei segnali per gli utenti federati passerà per il pool di server perimetrali o il singolo server perimetrale di New York. Ciò vale anche per le comunicazioni con gli utenti di Londra, anche se un utente interno di Londra che chiami un utente federato di Londra utilizzerà il pool o il server perimetrale di Londra per il traffico audio/video.</span><span class="sxs-lookup"><span data-stu-id="a2380-p108">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation. All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server. For example, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server. This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="a2380-146">Se si prevede di supportare il protocollo XMPP per la distribuzione, selezionare la casella di controllo **Abilita la federazione XMPP (porta 5269)**</span><span class="sxs-lookup"><span data-stu-id="a2380-146">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="a2380-147">In **Selezionare le opzioni IP** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2380-147">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="a2380-148">**Abilita IPv4 su interfaccia interna**: selezionare questa casella di controllo se si desidera applicare un indirizzo IPv4 all'interfaccia interna del server perimetrale o del pool perimetrale</span><span class="sxs-lookup"><span data-stu-id="a2380-148">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="a2380-149">**Abilita IPv6 su interfaccia interna**: selezionare questa casella di controllo se si desidera applicare un indirizzo IPv6 all'interfaccia interna del server perimetrale o del pool perimetrale</span><span class="sxs-lookup"><span data-stu-id="a2380-149">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="a2380-150">**Abilita IPv4 su interfaccia esterna**: selezionare questa casella di controllo se si desidera applicare un indirizzo IPv4 all'interfaccia esterna del server perimetrale o del pool perimetrale</span><span class="sxs-lookup"><span data-stu-id="a2380-150">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="a2380-151">**Abilita IPv6 su interfaccia esterna**: selezionare questa casella di controllo se si desidera applicare un indirizzo IPv6 all'interfaccia esterna del server perimetrale o del pool perimetrale</span><span class="sxs-lookup"><span data-stu-id="a2380-151">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <span data-ttu-id="a2380-152">È inoltre possibile configurare il server perimetrale o il pool perimetrale per l'utilizzo di un indirizzo di conversione indirizzo di rete per gli indirizzi IP esterni.</span><span class="sxs-lookup"><span data-stu-id="a2380-152">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="a2380-153">A tale scopo, selezionando la casella di controllo **l'indirizzo IP esterno del pool di server perimetrali viene convertito da NAT**.</span><span class="sxs-lookup"><span data-stu-id="a2380-153">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>

8.  <span data-ttu-id="a2380-154">In **FQDN esterni** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2380-154">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="a2380-155">Se in **Selezionare funzionalità** si è scelto di utilizzare un singolo FQDN e indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Edge, digitare l'FQDN esterno in **Accesso SIP**.</span><span class="sxs-lookup"><span data-stu-id="a2380-155">If in **Select features** you chose to use a single FQDN and IP address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a2380-p110">Se si sceglie di selezionare questa opzione, è necessario specificare un numero di porta diverso per ogni servizio Edge (impostazioni di porta consigliate: 5061 per il servizio Access Edge, 444 per il servizio Web Conferencing Edge e 443 per il servizio A/V Edge). Selezionando questa opzione, è possibile evitare possibili problemi di connettività e semplificare la configurazione, in quanto è quindi possibile utilizzare lo stesso numero di porta, ad esempio 443, per i tre servizi.</span><span class="sxs-lookup"><span data-stu-id="a2380-p110">If you choose this option, you must specify a different port number for each of the edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service). Selecting this option can help prevent potential connectivity issues, and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="a2380-158">Se in **Selezionare funzionalità** non si è scelto di utilizzare un singolo FQDN e indirizzo IP, digitare gli FQDN esterni per **Accesso SIP**, **Web Conferencing** e **Audio/Video**, mantenendo le porte predefinite.</span><span class="sxs-lookup"><span data-stu-id="a2380-158">If in **Select features** you did not chose to use a single FQDN and IP Address, type the External FQDNs for **SIP Access**, **Web Conferencing** and **Audio Video**, keeping the default ports.</span></span>

9.  <span data-ttu-id="a2380-159">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a2380-159">Click **Next**.</span></span>

10. <span data-ttu-id="a2380-p111">In **Definire l'indirizzo IP interno**, digitare l'indirizzo IP del server perimetrale in **Indirizzo IPv4 interno** e **Indirizzo IPv6 interno**, a seconda dei propri requisiti. Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a2380-p111">In **Define the Internal IP address**, type the IP address of your Edge Server in **Internal IPv4 address** and **Internal IPv6 address** as is appropriate for your requirements. Click **Next**.</span></span>

11. <span data-ttu-id="a2380-162">In **Definire l'indirizzo IP esterno** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2380-162">In **Define the External IP address**, do the following:</span></span>
    
      - <span data-ttu-id="a2380-163">Se si è scelto di utilizzare un singolo FQDN e indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Edge, digitare l'indirizzo IPv4 esterno del server perimetrale in **Accesso SIP** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a2380-163">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 address of the Edge Server in **SIP Access**, and then, click **Next**.</span></span>
    
      - <span data-ttu-id="a2380-164">Se si è scelto di utilizzare indirizzi IPv6, digitare l'indirizzo IPv6 esterno del server perimetrale in **Accesso SIP**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a2380-164">If you chose to use IPv6 addresses, type the external IPv6 address of the Edge Server in **SIP Access**, and then, click **Next**.</span></span>
    
      - <span data-ttu-id="a2380-165">Se non si è scelto di utilizzare un singolo FQDN e indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Edge, digitare gli indirizzi IPv4 esterni del server perimetrale in **Accesso SIP**, **Web Conferencing** e **A/V Conferencing** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a2380-165">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 addresses of the Edge Server in **SIP Access**, **Web Conferencing**, and **A/V Conferencing**, and then click **Next**.</span></span>
    
      - <span data-ttu-id="a2380-166">Se si è scelto di utilizzare indirizzi IPv6 ma non si è scelto di utilizzare un singolo FQDN e indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Edge, digitare gli indirizzi IPv6 esterni del server perimetrale in **Accesso SIP**, **Web Conferencing** e **A/V Conferencing** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a2380-166">If you chose to use IPv6 addresses and did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 addresses of the Edge Server in **SIP Access**, **Web Conferencing**, and **A/V Conferencing**, and then click **Next**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a2380-167">Se non è stato scelto di abilitare e assegnare gli indirizzi IPv6, questa finestra di dialogo non viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="a2380-167">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

        
        </div>

12. <span data-ttu-id="a2380-p112">Se si è scelto di utilizzare NAT, viene visualizzata una finestra di dialogo. In **Indirizzo IPv4 pubblico per il servizio A/V Edge** digitare l'indirizzo IPv4 pubblico da convertire tramite NAT e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a2380-p112">If you chose to use NAT, a dialog box appears. In **Public IPv4 address for the A/V Edge service**, type the public IPv4 address to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a2380-170">Tale indirizzo deve corrispondere all'indirizzo IP esterno del servizio A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="a2380-170">This should be the external IP address of the A/V Edge service.</span></span>

    
    </div>

13. <span data-ttu-id="a2380-p113">Se si è scelto di utilizzare NAT e indirizzi IPv6, viene visualizzata una finestra di dialogo. In **Indirizzo IPv6 pubblico per il servizio A/V Edge** digitare l'indirizzo IPv6 pubblico da convertire tramite NAT e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a2380-p113">If you chose to use NAT and IPv6 addresses, a dialog box appears. In **Public IPv6 address for the A/V Edge service**, type the public IPv6 address to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a2380-173">Tale indirizzo deve corrispondere all'indirizzo IP esterno del servizio A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="a2380-173">This should be the external IP address of the A/V Edge service.</span></span>

    
    </div>

14. <span data-ttu-id="a2380-p114">In **Pool hop successivo** in **Definire l'hop successivo** selezionare il nome del pool interno, che può essere un pool Front End o un pool Standard Edition. In alternativa, se la distribuzione include un server Director, selezionare il nome di questo server e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a2380-p114">In **Define the next hop**, in **Next hop pool**, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool. Or, if your deployment includes a Director, select the Director. Then, click **Next**.</span></span>

15. <span data-ttu-id="a2380-177">In **Associare pool Front End** specificare uno o più pool interni, che possono includere pool Front End e server Standard Edition, da associare a questo server perimetrale, selezionando i nomi dei pool interni che utilizzeranno il server perimetrale per la comunicazione con gli utenti esterni supportati.</span><span class="sxs-lookup"><span data-stu-id="a2380-177">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pools that are to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a2380-p115">È possibile associare solo un pool di server perimetrali o un singolo server perimetrale con carico bilanciato a ogni pool interno per il traffico audio/video. Se è già stato associato un pool interno a un pool di server perimetrali o a un server perimetrale, viene visualizzato un avviso che indica che al pool interno è già associato un pool di server perimetrali o un server perimetrale. Se si seleziona un pool già associato a un altro server perimetrale, l'associazione verrà modificata.</span><span class="sxs-lookup"><span data-stu-id="a2380-p115">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic. If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server. If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

16. <span data-ttu-id="a2380-181">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="a2380-181">Click **Finish**.</span></span>

17. <span data-ttu-id="a2380-182">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="a2380-182">Publish your topology.</span></span>

</div>

<div>

## <a name="to-define-the-topology-for-a-dns-load-balanced-edge-server-pool"></a><span data-ttu-id="a2380-183">Per definire la topologia per un pool di server perimetrali con bilanciamento del carico DNS</span><span class="sxs-lookup"><span data-stu-id="a2380-183">To define the topology for a DNS load balanced Edge Server pool</span></span>

1.  <span data-ttu-id="a2380-184">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.</span><span class="sxs-lookup"><span data-stu-id="a2380-184">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="a2380-185">Nell'albero della console espandere il sito in cui si desidera distribuire i server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="a2380-185">In the console tree, expand the site in which you want to deploy Edge Servers.</span></span>

3.  <span data-ttu-id="a2380-186">Fare clic con il pulsante destro del mouse su **Pool di server perimetrali** e quindi scegliere **Nuovo pool di server perimetrali**.</span><span class="sxs-lookup"><span data-stu-id="a2380-186">Right-click **Edge Pools**, and then click **New Edge Pool**.</span></span>

4.  <span data-ttu-id="a2380-187">In **Definire il nuovo pool di server perimetrali** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a2380-187">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="a2380-188">In **Definire l'FQDN del pool di server perimetrali** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2380-188">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="a2380-189">In **Pool FQDN** digitare il nome di dominio completo (FQDN) della connessione interna del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="a2380-189">In **Pool FQDN**, type the fully qualified domain name (FQDN) for the internal connection of the Edge pool.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="a2380-190">Il nome specificato per il pool deve essere il nome del pool di server perimetrali interno.</span><span class="sxs-lookup"><span data-stu-id="a2380-190">The name you specify for the pool must be the internal edge pool name.</span></span> <span data-ttu-id="a2380-191">Questo deve essere definito come FQDN.</span><span class="sxs-lookup"><span data-stu-id="a2380-191">This must be defined as a FQDN.</span></span> <span data-ttu-id="a2380-192">Generatore di topologie utilizza gli FQDN e non i nomi brevi.</span><span class="sxs-lookup"><span data-stu-id="a2380-192">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="a2380-193">Utilizzare solo caratteri standard, ovvero A-Z, a-z, 0-9 e trattini, per assegnare FQDN dei server Lync Server, dei server perimetrali e dei pool.</span><span class="sxs-lookup"><span data-stu-id="a2380-193">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="a2380-194">Non utilizzare caratteri Unicode o di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="a2380-194">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="a2380-195">La presenza di caratteri non standard in un FQDN è spesso non supportata da DNS esterni e CA pubbliche (quando l'FQDN deve essere assegnato al nome soggetto nel certificato).</span><span class="sxs-lookup"><span data-stu-id="a2380-195">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span>

        
        </div>
    
      - <span data-ttu-id="a2380-196">Fare clic su **Pool di più computer** e quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a2380-196">Click **Multiple computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="a2380-197">In **Selezionare funzionalità** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2380-197">In **Select features**, do the following:</span></span>
    
      - <span data-ttu-id="a2380-198">Se si prevede di utilizzare un singolo FQDN e indirizzo IP per l'accesso SIP, il servizio Web Conferencing di Lync Server 2013 e i servizi A/V Edge, selezionare la casella di controllo **utilizza un singolo FQDN e indirizzo IP** .</span><span class="sxs-lookup"><span data-stu-id="a2380-198">If you plan to use a single FQDN and IP address for the SIP access, Lync Server 2013 Web Conferencing service and A/V Edge services, select the **Use a single FQDN and IP Address** check box.</span></span>
    
      - <span data-ttu-id="a2380-p117">Se si prevede di abilitare la federazione, selezionare la casella di controllo **Abilita la federazione per questo pool di server perimetrali (porta 5061)**. Fare clic su **Avanti**</span><span class="sxs-lookup"><span data-stu-id="a2380-p117">If you plan to enable federation, select the **Enable federation for this Edge pool (Port 5061)** check box. Click **Next**</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a2380-p118">È possibile selezionare questa opzione, ma è possibile pubblicare esternamente per la federazione solo un pool di server perimetrali o un server perimetrale nell'organizzazione. Tutto l'accesso da parte di utenti federati, inclusi gli utenti di messaggistica istantanea pubblica, passa per lo stesso pool di server perimetrali o singolo server perimetrale. Se, ad esempio, la distribuzione include un pool di server perimetrali o un singolo server perimetrale distribuito a New York e uno distribuito a Londra e si abilita il supporto per la federazione nel pool di server perimetrali o nel server perimetrale di New York, il traffico dei segnali per gli utenti federati passerà per il pool di server perimetrali o il singolo server perimetrale di New York. Ciò vale anche per le comunicazioni con gli utenti di Londra, anche se un utente interno di Londra che chiama un utente federato di Londra utilizzerà il pool o il server perimetrale di Londra per il traffico audio/video.</span><span class="sxs-lookup"><span data-stu-id="a2380-p118">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation. All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server. For instance, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server. This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="a2380-205">Se si prevede di supportare il protocollo XMPP per la distribuzione, selezionare la casella di controllo **Abilita la federazione XMPP (porta 5269)**</span><span class="sxs-lookup"><span data-stu-id="a2380-205">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="a2380-206">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a2380-206">Click **Next**.</span></span>

8.  <span data-ttu-id="a2380-207">In **Selezionare le opzioni IP** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2380-207">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="a2380-208">**Abilita IPv4 su interfaccia interna**: selezionare questa casella di controllo se si desidera applicare un indirizzo IPv4 all'interfaccia interna del server perimetrale o del pool perimetrale</span><span class="sxs-lookup"><span data-stu-id="a2380-208">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="a2380-209">**Abilita IPv6 su interfaccia interna**: selezionare questa casella di controllo se si desidera applicare un indirizzo IPv6 all'interfaccia interna del server perimetrale o del pool perimetrale</span><span class="sxs-lookup"><span data-stu-id="a2380-209">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="a2380-210">**Abilita IPv4 su interfaccia esterna**: selezionare questa casella di controllo se si desidera applicare un indirizzo IPv4 all'interfaccia esterna del server perimetrale o del pool perimetrale</span><span class="sxs-lookup"><span data-stu-id="a2380-210">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="a2380-211">**Abilita IPv6 su interfaccia esterna**: selezionare questa casella di controllo se si desidera applicare un indirizzo IPv6 all'interfaccia esterna del server perimetrale o del pool perimetrale</span><span class="sxs-lookup"><span data-stu-id="a2380-211">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <span data-ttu-id="a2380-212">È inoltre possibile configurare il server perimetrale o il pool perimetrale per l'utilizzo di un indirizzo di conversione indirizzo di rete per gli indirizzi IP esterni.</span><span class="sxs-lookup"><span data-stu-id="a2380-212">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="a2380-213">A tale scopo, selezionando la casella di controllo **l'indirizzo IP esterno del pool di server perimetrali viene convertito da NAT**.</span><span class="sxs-lookup"><span data-stu-id="a2380-213">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>

9.  <span data-ttu-id="a2380-214">In **FQDN esterni** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2380-214">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="a2380-215">Se in **Selezionare funzionalità** si è scelto di utilizzare un singolo FQDN e indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Edge, digitare l'FQDN esterno in **Accesso SIP**.</span><span class="sxs-lookup"><span data-stu-id="a2380-215">If in **Select features** you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a2380-p120">Se si sceglie di selezionare questa opzione, è necessario specificare un numero di porta diverso per ogni servizio Edge (impostazioni di porta consigliate: 5061 per il servizio Access Edge, 444 per il servizio Web Conferencing Edge e 443 per il servizio A/V Edge). Selezionando questa opzione, è possibile evitare possibili problemi di connettività e semplificare la configurazione, in quanto è quindi possibile utilizzare lo stesso numero di porta, ad esempio 443, per i tre servizi.</span><span class="sxs-lookup"><span data-stu-id="a2380-p120">If you choose this option, you must specify a different port number for each of the Edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service). By selecting this option, you can help prevent potential connectivity issues and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="a2380-p121">Se in **Selezionare funzionalità** non si è scelto di utilizzare un singolo FQDN e indirizzo IP, digitare l'FQDN scelto per il lato pubblico del pool di server perimetrali in **Accesso SIP**. In **Web Conferencing** digitare l'FQDN scelto per il lato pubblico del pool di server perimetrali. In **Audio/Video** digitare l'FQDN scelto per il lato pubblico del pool di server perimetrali. Utilizzare le porte predefinite.</span><span class="sxs-lookup"><span data-stu-id="a2380-p121">If in **Select features** you did not chose to use a single FQDN and IP Address, type the FQDN that you have chosen for your public facing side of the edge pool for in **SIP Access**. In **Web Conferencing**, type the FQDN you have chosen for your public facing side of the Edge pool. In **Audio/Video**, type the FQDN you have chosen for your public facing side of the Edge pool. Use the default ports.</span></span>

10. <span data-ttu-id="a2380-222">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a2380-222">Click **Next**.</span></span>

11. <span data-ttu-id="a2380-223">In **Definire i computer nel pool corrente** fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a2380-223">In **Define the computers in this pool**, click **Add**.</span></span>

12. <span data-ttu-id="a2380-224">In **Indirizzo IP e FQDN interni** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2380-224">In **Internal FQDN and IP address**, do the following:</span></span>
    
      - <span data-ttu-id="a2380-225">In **Indirizzo IPv4 interno**, digitare l'indirizzo IPv4 e l'**Indirizzo IPv6 interno**, a seconda dei propri requisiti, del primo server perimetrale che si desidera creare nel pool.</span><span class="sxs-lookup"><span data-stu-id="a2380-225">In **Internal IPv4 address**, type the IPv4 address and **Internal IPv6 address** as is appropriate for your requirements for the first Edge Server that you want to create in this pool.</span></span>
    
      - <span data-ttu-id="a2380-226">In **FQDN interno** digitare l'FQDN del primo server perimetrale che si desidera creare nel pool.</span><span class="sxs-lookup"><span data-stu-id="a2380-226">In **Internal FQDN**, type the FQDN of the first Edge Server that you want to create in this pool.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a2380-227">Il nome specificato deve essere uguale al nome computer configurato nel server.</span><span class="sxs-lookup"><span data-stu-id="a2380-227">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="a2380-228">Per impostazione predefinita, il nome di un computer non aggiunto a un dominio è un nome breve e non un FQDN.</span><span class="sxs-lookup"><span data-stu-id="a2380-228">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="a2380-229">Generatore di topologie utilizza gli FQDN e non i nomi brevi.</span><span class="sxs-lookup"><span data-stu-id="a2380-229">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="a2380-230">Pertanto, è necessario configurare un suffisso DNS sul nome del computer da distribuire come server perimetrale non aggiunto a un dominio.</span><span class="sxs-lookup"><span data-stu-id="a2380-230">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="a2380-231">Utilizzare solo caratteri standard, ovvero A-Z, a-z, 0-9 e trattini, per assegnare FQDN dei server Lync Server, dei server perimetrali, dei pool e degli array.</span><span class="sxs-lookup"><span data-stu-id="a2380-231">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, pools, and arrays.</span></span> <span data-ttu-id="a2380-232">Non utilizzare caratteri Unicode o di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="a2380-232">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="a2380-233">La presenza di caratteri non standard in un FQDN è spesso non supportata da DNS esterni e CA pubbliche (quando l'FQDN deve essere assegnato al nome soggetto nel certificato).</span><span class="sxs-lookup"><span data-stu-id="a2380-233">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="a2380-234">Per informazioni dettagliate sull'aggiunta di un suffisso DNS a un nome computer, vedere <A href="lync-server-2013-configure-dns-for-edge-support.md">configure DNS for Edge support in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a2380-234">For details about adding a DNS suffix to a computer name, see <A href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</A>.</span></span>

        
        </div>

13. <span data-ttu-id="a2380-235">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a2380-235">Click **Next**.</span></span>

14. <span data-ttu-id="a2380-236">In **Definire l'indirizzo IP esterno** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2380-236">In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="a2380-237">Se si è scelto di utilizzare un singolo FQDN e indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Edge, digitare l'indirizzo IP esterno del server perimetrale in **Accesso SIP**.</span><span class="sxs-lookup"><span data-stu-id="a2380-237">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IP address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="a2380-p123">Se non si è scelto di utilizzare un singolo FQDN e indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Conferencing, digitare l'indirizzo IP scelto per il lato pubblico di questo server del pool di server perimetrali in **Accesso SIP**. In **Web Conferencing** digitare l'indirizzo IP scelto per il lato pubblico di questo server del pool di server perimetrali. In **A/V Conferencing** digitare l'indirizzo IP scelto per il lato pubblico di questo server del pool di server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="a2380-p123">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IP address that you have chosen for your public facing side of this Edge pool server for **SIP Access**. In **Web Conferencing**, type the IP address that you have chosen for your public facing side of this Edge pool server. In **A/V Conferencing**, type the IP address you have chosen for your public facing side of this Edge pool server.</span></span>

15. <span data-ttu-id="a2380-241">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a2380-241">Click **Next**.</span></span>

16. <span data-ttu-id="a2380-242">Se è stato scelto di abilitare gli indirizzi IPv6, in **Definire l'indirizzo IP esterno** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2380-242">If you chose to enable IPv6 addresses, In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="a2380-243">Se si è scelto di utilizzare un singolo FQDN e indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Edge, digitare l'indirizzo IPv6 esterno del server perimetrale in **Accesso SIP**.</span><span class="sxs-lookup"><span data-stu-id="a2380-243">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="a2380-p124">Se non si è scelto di utilizzare un singolo FQDN e indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Conferencing, digitare l'indirizzo IPv6 scelto per il lato pubblico di questo server del pool di server perimetrali in **Accesso SIP**. In **Web Conferencing** digitare l'indirizzo IPv6 scelto per il lato pubblico di questo server del pool di server perimetrali. In **A/V Conferencing** digitare l'indirizzo IPv6 scelto per il lato pubblico di questo server del pool di server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="a2380-p124">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IPv6 address that you have chosen for your public facing side of this Edge pool server for **SIP Access**. In **Web Conferencing**, type the IPv6 address that you have chosen for your public facing side of this Edge pool server. In **A/V Conferencing**, type the IPv6 address you have chosen for your public facing side of this Edge pool server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a2380-247">Se non è stato scelto di abilitare e assegnare gli indirizzi IPv6, questa finestra di dialogo non viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="a2380-247">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

    
    </div>

17. <span data-ttu-id="a2380-248">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="a2380-248">Click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a2380-249">Il primo server perimetrale creato nel pool verrà ora visualizzato nella finestra di dialogo <STRONG>Definire i computer nel pool corrente</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="a2380-249">You will now see the first Edge Server you created in your pool in the <STRONG>Define the computers in this pool</STRONG> dialog box.</span></span>

    
    </div>

18. <span data-ttu-id="a2380-250">In **Definire i computer nel pool corrente** fare clic su **Aggiungi** e quindi ripetere i passaggi da 11 a 14 per il secondo server perimetrale che si desidera aggiungere al pool di server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="a2380-250">In **Define the computers in this pool**, click **Add**, and then repeat steps 11 through 14 for the second Edge Server that you want to add to you Edge pool.</span></span>

19. <span data-ttu-id="a2380-251">Dopo aver ripetuto i passaggi da 11 a 14, fare clic su **Avanti** in **Definire i computer nel pool corrente**.</span><span class="sxs-lookup"><span data-stu-id="a2380-251">After you repeat steps 11 through 14, click **Next** in **Define the computers in this pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a2380-252">A questo punto, è possibile visualizzare entrambi i server perimetrali nel pool.</span><span class="sxs-lookup"><span data-stu-id="a2380-252">At this point, you can see both of the Edge Servers in your pool.</span></span>

    
    </div>

20. <span data-ttu-id="a2380-p125">Se si è scelto di utilizzare NAT, viene visualizzata una finestra di dialogo. In **Indirizzo IP pubblico** digitare l'indirizzo IPv4 o IPv6 pubblico (come appropriato) da convertire tramite NAT e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a2380-p125">If you chose to use NAT, a dialog box appears. In **Public IP address**, type the public IPv4 and IPv6 (as appropriate) addresses to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a2380-255">Tale indirizzo deve corrispondere all'indirizzo IP esterno di A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="a2380-255">This should be the external IP Address of the A/V Edge.</span></span>

    
    </div>

21. <span data-ttu-id="a2380-p126">Nell'elenco **Pool hop successivo** in **Definire l'hop successivo** selezionare il nome del pool interno, che può essere un pool Front End o un pool Standard Edition. In alternativa, se la distribuzione include un server Director, selezionare il nome di questo server e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a2380-p126">In **Define the next hop**, in the **Next hop pool** list, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool. Or, if your deployment includes a Director, select the name of the Director. Then, click **Next**.</span></span>

22. <span data-ttu-id="a2380-259">In **Associare pool Front End** specificare uno o più pool interni, che possono includere pool Front End e server Standard Edition, da associare a questo server perimetrale, selezionando i nomi dei pool interni che utilizzeranno il server perimetrale per la comunicazione con gli utenti esterni supportati.</span><span class="sxs-lookup"><span data-stu-id="a2380-259">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pool(s) that is to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a2380-p127">È possibile associare solo un pool di server perimetrali o un singolo server perimetrale con carico bilanciato a ogni pool interno per il traffico audio/video. Se è già stato associato un pool interno a un pool di server perimetrali o a un server perimetrale, viene visualizzato un avviso che indica che al pool interno è già associato un pool di server perimetrali o un server perimetrale. Se si seleziona un pool già associato a un altro server perimetrale, l'associazione verrà modificata.</span><span class="sxs-lookup"><span data-stu-id="a2380-p127">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic. If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server. If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

23. <span data-ttu-id="a2380-263">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="a2380-263">Click **Finish**.</span></span>

24. <span data-ttu-id="a2380-264">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="a2380-264">Publish your topology.</span></span>

</div>

<div>

## <a name="to-define-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a><span data-ttu-id="a2380-265">Per definire la topologia per un pool di server perimetrali con bilanciamento del carico hardware</span><span class="sxs-lookup"><span data-stu-id="a2380-265">To define the topology for a hardware load balanced Edge Server pool</span></span>

1.  <span data-ttu-id="a2380-266">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.</span><span class="sxs-lookup"><span data-stu-id="a2380-266">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="a2380-267">Nell'albero della console espandere il sito in cui si desidera distribuire i server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="a2380-267">In the console tree, expand the site in which you want to deploy Edge Servers.</span></span>

3.  <span data-ttu-id="a2380-268">Fare clic con il pulsante destro del mouse su **pool di server perimetrali**e quindi scegliere **nuovo pool Edge**.</span><span class="sxs-lookup"><span data-stu-id="a2380-268">Right-click **Edge Pools**, and then select **New Edge Pool**.</span></span>

4.  <span data-ttu-id="a2380-269">In **Definire il nuovo pool di server perimetrali** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a2380-269">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="a2380-270">In **Definire l'FQDN del pool di server perimetrali** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2380-270">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="a2380-271">In **FQDN** digitare il nome di dominio completo (FQDN) scelto per il lato interno del pool di server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="a2380-271">In **FQDN**, type the fully qualified domain name (FQDN) you have chosen for the internal side of the Edge pool.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="a2380-272">Il nome specificato per il pool deve essere il nome del pool di server perimetrali interno.</span><span class="sxs-lookup"><span data-stu-id="a2380-272">The name you specify for the pool must be the internal edge pool name.</span></span> <span data-ttu-id="a2380-273">Questo deve essere definito come FQDN.</span><span class="sxs-lookup"><span data-stu-id="a2380-273">This must be defined as a FQDN.</span></span> <span data-ttu-id="a2380-274">Generatore di topologie utilizza gli FQDN e non i nomi brevi.</span><span class="sxs-lookup"><span data-stu-id="a2380-274">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="a2380-275">Utilizzare solo caratteri standard, ovvero A-Z, a-z, 0-9 e trattini, per assegnare FQDN dei server Lync Server, dei server perimetrali e dei pool.</span><span class="sxs-lookup"><span data-stu-id="a2380-275">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="a2380-276">Non utilizzare caratteri Unicode o di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="a2380-276">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="a2380-277">La presenza di caratteri non standard in un FQDN è spesso non supportata da DNS esterni e CA pubbliche (quando l'FQDN deve essere assegnato al nome soggetto nel certificato).</span><span class="sxs-lookup"><span data-stu-id="a2380-277">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span>

        
        </div>
    
    <!-- end list -->
    
      - <span data-ttu-id="a2380-278">Fare clic su **pool di più computer**e quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a2380-278">Click **Multiple computer pool**, and then **Next**.</span></span>

6.  <span data-ttu-id="a2380-279">In **Selezionare funzionalità** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2380-279">In **Select features** do the following:</span></span>
    
      - <span data-ttu-id="a2380-280">Se si prevede di utilizzare un singolo FQDN e indirizzo IP per il servizio di accesso SIP, il servizio Web Conferencing di Lync Server e il servizio A/V Edge, selezionare la casella di controllo **utilizza un solo fqdn & indirizzo IP** .</span><span class="sxs-lookup"><span data-stu-id="a2380-280">If you plan to use a single FQDN and IP address for the SIP access service, Lync Server Web Conferencing service, and A/V Edge service, select the **Use a single FQDN & IP Address** check box.</span></span>
    
      - <span data-ttu-id="a2380-281">Se si prevede di abilitare la federazione, selezionare la casella di controllo **Abilita federazione per pool di server perimetrali (porta 5061)**.</span><span class="sxs-lookup"><span data-stu-id="a2380-281">If you plan to enable federation, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a2380-p129">È possibile selezionare questa opzione, ma è possibile pubblicare esternamente per la federazione solo un pool di server perimetrali o un server perimetrale nell'organizzazione. Tutto l'accesso da parte di utenti federati, inclusi gli utenti di messaggistica istantanea pubblica, passa per lo stesso pool di server perimetrali o singolo server perimetrale. Se, ad esempio, la distribuzione include un pool di server perimetrali o un singolo server perimetrale distribuito a New York e uno distribuito a Londra e si abilita il supporto per la federazione nel pool di server perimetrali o nel server perimetrale di New York, il traffico dei segnali per gli utenti federati passerà per il pool di server perimetrali o il singolo server perimetrale di New York. Ciò vale anche per le comunicazioni con gli utenti di Londra, anche se un utente interno di Londra che chiami un utente federato di Londra utilizzerà il pool o il server perimetrale di Londra per il traffico audio/video.</span><span class="sxs-lookup"><span data-stu-id="a2380-p129">You can select this option, but only one Edge pool or Edge Server in your organization may be published externally for federation. All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server. For instance, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server. This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="a2380-286">Se si prevede di supportare il protocollo XMPP per la distribuzione, selezionare la casella di controllo **Abilita la federazione XMPP (porta 5269)**</span><span class="sxs-lookup"><span data-stu-id="a2380-286">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="a2380-287">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a2380-287">Click **Next**.</span></span>

8.  <span data-ttu-id="a2380-288">In **Selezionare le opzioni IP** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2380-288">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="a2380-289">**Abilita IPv4 su interfaccia interna**: selezionare questa casella di controllo se si desidera applicare un indirizzo IPv4 all'interfaccia interna del server perimetrale o del pool perimetrale</span><span class="sxs-lookup"><span data-stu-id="a2380-289">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="a2380-290">**Abilita IPv6 su interfaccia interna**: selezionare questa casella di controllo se si desidera applicare un indirizzo IPv6 all'interfaccia interna del server perimetrale o del pool perimetrale</span><span class="sxs-lookup"><span data-stu-id="a2380-290">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="a2380-291">**Abilita IPv4 su interfaccia esterna**: selezionare questa casella di controllo se si desidera applicare un indirizzo IPv4 all'interfaccia esterna del server perimetrale o del pool perimetrale</span><span class="sxs-lookup"><span data-stu-id="a2380-291">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="a2380-292">**Abilita IPv6 su interfaccia esterna**: selezionare questa casella di controllo se si desidera applicare un indirizzo IPv6 all'interfaccia esterna del server perimetrale o del pool perimetrale</span><span class="sxs-lookup"><span data-stu-id="a2380-292">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a2380-p130"><STRONG>Non</STRONG> selezionare la casella di controllo <STRONG>L'indirizzo IP esterno del pool di server perimetrali è convertito da NAT</STRONG>. Network Address Translation (NAT) non è supportato quando si utilizza il bilanciamento del carico di rete hardware.</span><span class="sxs-lookup"><span data-stu-id="a2380-p130"><STRONG>Do Not</STRONG> select the <STRONG>The external IP address of the Edge pool is translated by NAT</STRONG> check box. Network address translation (NAT) is not supported when you are using hardware load balancing.</span></span>

    
    </div>

9.  <span data-ttu-id="a2380-295">In **FQDN esterni** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2380-295">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="a2380-296">Se in **Selezionare funzionalità** si è scelto di utilizzare un singolo FQDN e indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Edge, digitare l'FQDN esterno in **Accesso SIP**.</span><span class="sxs-lookup"><span data-stu-id="a2380-296">If in **Select features** you chose to use a single FQDN and IP address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a2380-p131">Se si sceglie di selezionare questa opzione, è necessario specificare un numero di porta diverso per ogni servizio Edge (impostazioni di porta consigliate: 5061 per il servizio Access Edge, 444 per il servizio Web Conferencing Edge e 443 per il servizio A/V Edge). Selezionando questa opzione, è possibile evitare possibili problemi di connettività e semplificare la configurazione, in quanto è quindi possibile utilizzare lo stesso numero di porta, ad esempio 443, per i tre servizi.</span><span class="sxs-lookup"><span data-stu-id="a2380-p131">If you choose to select this option, you must specify a different port number for each of the Edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service). By selecting this option, you can help prevent potential connectivity issues and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="a2380-p132">Se in **Selezionare funzionalità** non si è scelto di utilizzare un singolo FQDN e indirizzo IP, digitare l'FQDN scelto per il lato pubblico del pool di server perimetrali in **Accesso SIP**. In **Web Conferencing** digitare l'FQDN scelto per il lato pubblico del pool di server perimetrali. In **Audio/Video** digitare l'FQDN scelto per il lato pubblico del pool di server perimetrali. Utilizzare le porte predefinite.</span><span class="sxs-lookup"><span data-stu-id="a2380-p132">If in **Select features** you did not chose to use a single FQDN and IP address, type the FQDN that you have chosen for your public facing side of the edge pool for in **SIP Access**. In **Web Conferencing**, type the FQDN you have chosen for your public facing side of the Edge pool. In **Audio/Video**, type the FQDN you have chosen for your public facing side of the Edge pool. Use the default ports.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a2380-303">Questi saranno gli FQDN IP virtuali (VIP) del lato pubblico per il pool.</span><span class="sxs-lookup"><span data-stu-id="a2380-303">These will be the publicly facing virtual IP (VIP) FQDNs for the pool.</span></span>

        
        </div>

10. <span data-ttu-id="a2380-304">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a2380-304">Click **Next**.</span></span>

11. <span data-ttu-id="a2380-305">In **Definire i computer nel pool corrente** fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a2380-305">In **Define the computers in this pool**, click **Add**.</span></span>

12. <span data-ttu-id="a2380-306">In **Definire l'indirizzo IP esterno** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2380-306">In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="a2380-307">Se si è scelto di utilizzare un singolo FQDN e indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Edge, digitare l'indirizzo IPv4 esterno del server perimetrale in **Accesso SIP** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a2380-307">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 address of the Edge Server in **SIP Access**.external IP address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="a2380-p133">Se non si è scelto di utilizzare un singolo FQDN e indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Conferencing, digitare l'indirizzo IP scelto per il lato pubblico di questo server del pool di server perimetrali in **Accesso SIP**. In **Web Conferencing** digitare l'indirizzo IP scelto per il lato pubblico di questo server del pool di server perimetrali. In **A/V Conferencing** digitare l'indirizzo IP scelto per il lato pubblico di questo server del pool di server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="a2380-p133">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IP address that you have chosen for your public facing side of this Edge pool server for **SIP Access**. In **Web Conferencing**, type the IP address that you have chosen for your public facing side of this Edge pool server. In **A/V Conferencing**, type the IP address you have chosen for your public facing side of this Edge pool server.</span></span>

13. <span data-ttu-id="a2380-311">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a2380-311">Click **Next**.</span></span>

14. <span data-ttu-id="a2380-312">Se è stato scelto di abilitare gli indirizzi IPv6, in **Definire l'indirizzo IP esterno** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2380-312">If you chose to enable IPv6 addresses, In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="a2380-313">Se si è scelto di utilizzare un singolo FQDN e indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Edge, digitare l'indirizzo IPv6 esterno del server perimetrale in **Accesso SIP**.</span><span class="sxs-lookup"><span data-stu-id="a2380-313">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="a2380-p134">Se non si è scelto di utilizzare un singolo FQDN e indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Conferencing, digitare l'indirizzo IPv6 scelto per il lato pubblico di questo server del pool di server perimetrali in **Accesso SIP**. In **Web Conferencing** digitare l'indirizzo IPv6 scelto per il lato pubblico di questo server del pool di server perimetrali. In **A/V Conferencing** digitare l'indirizzo IPv6 scelto per il lato pubblico di questo server del pool di server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="a2380-p134">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IPv6 address that you have chosen for your public facing side of this Edge pool server for **SIP Access**. In **Web Conferencing**, type the IPv6 address that you have chosen for your public facing side of this Edge pool server. In **A/V Conferencing**, type the IPv6 address you have chosen for your public facing side of this Edge pool server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a2380-317">Se non è stato scelto di abilitare e assegnare gli indirizzi IPv6, questa finestra di dialogo non viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="a2380-317">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

    
    </div>

15. <span data-ttu-id="a2380-318">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="a2380-318">Click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a2380-319">Il primo server perimetrale creato nel pool verrà ora visualizzato nella finestra di dialogo <STRONG>Definire i computer nel pool corrente</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="a2380-319">You will now see the first Edge Server you created in your pool in the <STRONG>Define the computers in this pool</STRONG> dialog box.</span></span>

    
    </div>

16. <span data-ttu-id="a2380-320">In **Definire i computer nel pool corrente** fare clic su **Aggiungi** e quindi ripetere i passaggi da 11 a 14 per il secondo server perimetrale che si desidera aggiungere al pool di server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="a2380-320">In **Define the computers in this pool**, click **Add**, and then repeat steps 11 through 14 for the second Edge Server that you want to add to your Edge pool.</span></span>

17. <span data-ttu-id="a2380-321">Dopo aver ripetuto i passaggi da 11 a 14, fare clic su **Avanti** in **Definire i computer nel pool corrente**.</span><span class="sxs-lookup"><span data-stu-id="a2380-321">After you repeat steps 11 through 14, click **Next** in **Define the computers in this pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a2380-322">A questo punto, è possibile visualizzare entrambi i server perimetrali nel pool.</span><span class="sxs-lookup"><span data-stu-id="a2380-322">At this point, you can see both of the Edge Servers in your pool.</span></span>

    
    </div>

18. <span data-ttu-id="a2380-p135">Nell'elenco **Pool hop successivo** in **Definire l'hop successivo** selezionare il nome del pool interno, che può essere un pool Front End o un pool Standard Edition. In alternativa, se la distribuzione include un server Director, selezionare il nome di questo server e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a2380-p135">In **Define the next hop**, in the **Next hop pool** list, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool. Or, if your deployment includes a Director, select the name of the Director. Then, click **Next**.</span></span>

19. <span data-ttu-id="a2380-326">In **Associare pool Front End** specificare uno o più pool interni, che possono includere pool Front End e server Standard Edition, da associare a questo server perimetrale, selezionando i nomi dei pool interni che utilizzeranno il server perimetrale per la comunicazione con gli utenti esterni supportati.</span><span class="sxs-lookup"><span data-stu-id="a2380-326">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pool(s) that is to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a2380-p136">È possibile associare solo un pool di server perimetrali o un singolo server perimetrale con carico bilanciato a ogni pool interno per il traffico audio/video. Se è già stato associato un pool interno a un pool di server perimetrali o a un server perimetrale, viene visualizzato un avviso che indica che al pool interno è già associato un pool di server perimetrali o un server perimetrale. Se si seleziona un pool già associato a un altro server perimetrale, l'associazione verrà modificata.</span><span class="sxs-lookup"><span data-stu-id="a2380-p136">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic. If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server. If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

20. <span data-ttu-id="a2380-330">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="a2380-330">Click **Finish**.</span></span>

21. <span data-ttu-id="a2380-331">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="a2380-331">Publish your topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


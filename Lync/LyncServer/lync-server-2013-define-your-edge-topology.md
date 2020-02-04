---
title: 'Lync Server 2013: Definire la topologia perimetrale'
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
ms.openlocfilehash: 4a04dca4b935caf8f07546babd2c53f65fff4e89
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763940"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-your-edge-topology-in-lync-server-2013"></a><span data-ttu-id="cf79f-102">Definire la topologia perimetrale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf79f-102">Define your edge topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf79f-103">_**Argomento Ultima modifica:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="cf79f-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="cf79f-104">Per creare la topologia, è necessario usare generatore di topologia e configurare almeno un pool di front-end interno o un server Standard Edition prima di poter distribuire il server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="cf79f-104">You must use Topology Builder to build your topology and you must set up at least one internal Front End pool or Standard Edition server before you can deploy your Edge Server.</span></span> <span data-ttu-id="cf79f-105">Usare la procedura seguente per definire la topologia di Edge per un singolo Edge Server e quindi usare le procedure descritte in [pubblicare la topologia in Lync server 2013](lync-server-2013-publish-your-topology.md) ed [esportare la topologia di Lync Server 2013 e copiarla in elementi multimediali esterni per l'installazione di Edge](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) per pubblicare la topologia e renderla disponibile per il server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="cf79f-105">Use the following procedure to define the edge topology for a single Edge Server, and then use the procedures in [Publish your topology in Lync Server 2013](lync-server-2013-publish-your-topology.md) and [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) to publish the topology and make it available to your Edge Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cf79f-106">L'interfaccia perimetrale interna e l'interfaccia perimetrale esterna devono usare lo stesso tipo di bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="cf79f-106">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="cf79f-107">Non è possibile usare il bilanciamento del carico DNS in un'interfaccia perimetrale e il bilanciamento del carico hardware nell'altra.</span><span class="sxs-lookup"><span data-stu-id="cf79f-107">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>



</div>

<span data-ttu-id="cf79f-108">Per pubblicare, abilitare o disabilitare correttamente una topologia durante l'aggiunta o la rimozione di un ruolo del server, è necessario avere effettuato l'accesso come utente membro dei gruppi RTCUniversalServerAdmins e Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="cf79f-108">To successfully publish, enable, or disable a topology when adding or removing a server role, you must be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="cf79f-109">È anche possibile concedere i diritti di amministratore e le autorizzazioni necessarie per l'aggiunta di ruoli del server a un account utente.</span><span class="sxs-lookup"><span data-stu-id="cf79f-109">You can also grant the administrator rights and permissions required for adding server roles to a user account.</span></span> <span data-ttu-id="cf79f-110">Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync server 2013](lync-server-2013-delegate-setup-permissions.md) nella documentazione sulla distribuzione di server Standard Edition o Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="cf79f-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="cf79f-111">Per altre modifiche alla configurazione, è necessaria solo l'appartenenza al gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="cf79f-111">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<span data-ttu-id="cf79f-112">Se è stata definita la topologia di Edge quando è stata definita e pubblicata la topologia interna e non sono necessarie modifiche alla topologia perimetrale definita in precedenza, non è necessario definirla e pubblicarla di nuovo.</span><span class="sxs-lookup"><span data-stu-id="cf79f-112">If you defined your edge topology when you defined and published your internal topology, and no changes are required to the edge topology that you previously defined, you do not need to do define it and publish it again.</span></span> <span data-ttu-id="cf79f-113">Usare la procedura seguente solo se è necessario apportare modifiche alla topologia di Edge.</span><span class="sxs-lookup"><span data-stu-id="cf79f-113">Use the following procedure only if you need to make changes to your edge topology.</span></span> <span data-ttu-id="cf79f-114">Per usare la topologia definita e pubblicata in precedenza per gli Edge Server, è necessario eseguire la procedura descritta in [esportare la topologia di Lync Server 2013 e copiarla in elementi multimediali esterni per l'installazione di Edge](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span><span class="sxs-lookup"><span data-stu-id="cf79f-114">You must make the previously defined and published topology available to your Edge Servers, which you do by using the procedure in [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cf79f-115">Non è possibile eseguire Generatore di topologia da un server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="cf79f-115">You cannot run Topology Builder from an Edge Server.</span></span> <span data-ttu-id="cf79f-116">È necessario eseguirlo dal server front-end o da server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="cf79f-116">You must run it from your Front End Server or Standard Edition servers.</span></span>



</div>

<span data-ttu-id="cf79f-117">Il processo per definire la topologia di Edge Server viene eseguito in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="cf79f-117">The process to define your Edge Server topology is done in Topology Builder.</span></span> <span data-ttu-id="cf79f-118">Di seguito sono elencati i tre tipi principali di topologie di Edge Server che si prevede di pianificare e configurare:</span><span class="sxs-lookup"><span data-stu-id="cf79f-118">The three primary types of Edge Server topologies that you plan and configure are listed below:</span></span>

  - <span data-ttu-id="cf79f-119">Per definire la topologia di un singolo Edge Server</span><span class="sxs-lookup"><span data-stu-id="cf79f-119">To define the Topology for a Single Edge Server</span></span>

  - <span data-ttu-id="cf79f-120">Per definire la topologia di un pool di Edge Server con bilanciamento del carico</span><span class="sxs-lookup"><span data-stu-id="cf79f-120">To define the Topology for a Load Balanced Edge Server Pool</span></span>

  - <span data-ttu-id="cf79f-121">Per definire la topologia di un pool di Edge con bilanciamento del carico hardware</span><span class="sxs-lookup"><span data-stu-id="cf79f-121">To define the Topology for a Hardware Load Balanced Edge Pool</span></span>

<div>

## <a name="to-define-the-topology-for-a-single-edge-server"></a><span data-ttu-id="cf79f-122">Per definire la topologia di un singolo Edge Server</span><span class="sxs-lookup"><span data-stu-id="cf79f-122">To define the topology for a single Edge Server</span></span>

1.  <span data-ttu-id="cf79f-123">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-123">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="cf79f-124">Nell'albero della console espandere il sito in cui si vuole distribuire un server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="cf79f-124">In the console tree, expand the site in which you want to deploy an Edge Server.</span></span>

3.  <span data-ttu-id="cf79f-125">Fare clic con il pulsante destro del mouse su pool **Edge**e quindi scegliere **nuovo pool di bordi**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-125">Right-click **Edge pools**, and then click **New Edge Pool**.</span></span>

4.  <span data-ttu-id="cf79f-126">In **definire il nuovo pool di bordi**fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-126">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="cf79f-127">In **definire il nome di dominio completo del pool Edge**eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf79f-127">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="cf79f-128">In **FQDN del pool**Digitare il nome di dominio completo (FQDN) dell'interfaccia interna per il server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="cf79f-128">In **Pool FQDN**, type the fully qualified domain name (FQDN) of the internal interface for the Edge Server.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="cf79f-129">Il nome specificato deve essere uguale al nome del computer configurato nel server.</span><span class="sxs-lookup"><span data-stu-id="cf79f-129">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="cf79f-130">Per impostazione predefinita, il nome del computer di un computer che non è associato a un dominio è un nome breve, non un FQDN.</span><span class="sxs-lookup"><span data-stu-id="cf79f-130">By default the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="cf79f-131">Generatore di topologie usa gli FQDN e non i nomi brevi.</span><span class="sxs-lookup"><span data-stu-id="cf79f-131">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="cf79f-132">Devi quindi configurare un suffisso DNS sul nome del computer da distribuire come server perimetrale che non è associato a un dominio.</span><span class="sxs-lookup"><span data-stu-id="cf79f-132">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="cf79f-133">Usare solo caratteri standard (tra cui A-Z, a-z, 0-9 e segni meno) durante l'assegnazione di nomi di dominio completi di Lync Server, Edge Server e pool.</span><span class="sxs-lookup"><span data-stu-id="cf79f-133">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="cf79f-134">Non usare caratteri Unicode o carattere di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="cf79f-134">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="cf79f-135">I caratteri non standard di un nome di dominio completo spesso non sono supportati dal DNS esterno e dalle CA pubbliche (quando il nome di dominio completo deve essere assegnato a SN nel certificato).</span><span class="sxs-lookup"><span data-stu-id="cf79f-135">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="cf79f-136">Per informazioni dettagliate sull'aggiunta di un suffisso DNS a un nome di computer, vedere <A href="lync-server-2013-configure-dns-for-edge-support.md">configurare il supporto DNS per Edge in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="cf79f-136">For details about adding a DNS suffix to a computer name, see <A href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</A>.</span></span>

        
        </div>
    
      - <span data-ttu-id="cf79f-137">Fare clic su **pool di computer singolo**e quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-137">Click **Single computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="cf79f-138">In **Seleziona funzionalità**eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf79f-138">In **Select features**, do the following:</span></span>
    
      - <span data-ttu-id="cf79f-139">Se si prevede di usare un solo FQDN e un indirizzo IP per il servizio di accesso SIP, il servizio di conferenza Web di Lync Server 2013 e i servizi A/V Edge, selezionare la casella di controllo **Usa un solo nome di dominio completo e indirizzo IP** .</span><span class="sxs-lookup"><span data-stu-id="cf79f-139">If you plan to use a single FQDN and IP address for the SIP Access service, Lync Server 2013 Web Conferencing service, and A/V Edge services, select the **Use a single FQDN and IP Address** check box.</span></span>
    
      - <span data-ttu-id="cf79f-140">Se si prevede di abilitare la Federazione, selezionare la casella **di controllo Abilita federazione per questo pool di bordi (porta 5061)** .</span><span class="sxs-lookup"><span data-stu-id="cf79f-140">If you plan to enable federation select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="cf79f-141">È possibile selezionare questa opzione, ma è possibile pubblicare esternamente per la Federazione solo un pool di Edge o un server perimetrale dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cf79f-141">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation.</span></span> <span data-ttu-id="cf79f-142">Tutti gli accessi da parte di utenti federati, inclusi gli utenti di messaggistica istantanea pubblica, passano attraverso lo stesso pool di Edge o un singolo Edge Server.</span><span class="sxs-lookup"><span data-stu-id="cf79f-142">All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server.</span></span> <span data-ttu-id="cf79f-143">Ad esempio, se la distribuzione include un pool di Edge o un server perimetrale distribuito in New York e uno distribuito a Londra e si Abilita il supporto federativo per il pool Edge di New York o un singolo Edge Server, il traffico di segnale per gli utenti federati passerà attraverso New York Edge pool o Single Edge Server.</span><span class="sxs-lookup"><span data-stu-id="cf79f-143">For example, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server.</span></span> <span data-ttu-id="cf79f-144">Ciò avviene persino per le comunicazioni con gli utenti di Londra, anche se un utente interno di Londra che chiama un utente federato di Londra utilizza il pool o il server perimetrale di Londra per il traffico A/V.</span><span class="sxs-lookup"><span data-stu-id="cf79f-144">This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="cf79f-145">Se si prevede di supportare il protocollo XMPP (Extensible Messaging and Presence Protocol) per la distribuzione, selezionare la casella di controllo **Abilita federazione XMPP (porta 5269)**</span><span class="sxs-lookup"><span data-stu-id="cf79f-145">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="cf79f-146">In **Seleziona opzioni IP**eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf79f-146">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="cf79f-147">**Abilitare IPv4 sull'interfaccia interna**: selezionare la casella di controllo se si vuole applicare un indirizzo IPv4 all'interfaccia interna del server perimetrale o del pool Edge</span><span class="sxs-lookup"><span data-stu-id="cf79f-147">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="cf79f-148">**Abilitare IPv6 sull'interfaccia interna**: selezionare la casella di controllo se si vuole applicare un indirizzo IPv6 all'interfaccia interna del server perimetrale o del pool Edge</span><span class="sxs-lookup"><span data-stu-id="cf79f-148">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="cf79f-149">**Abilitare IPv4 sull'interfaccia esterna**: selezionare la casella di controllo se si vuole applicare un indirizzo IPv4 all'interfaccia esterna del server perimetrale o del pool Edge</span><span class="sxs-lookup"><span data-stu-id="cf79f-149">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="cf79f-150">**Abilitare IPv6 sull'interfaccia esterna**: selezionare la casella di controllo se si vuole applicare un indirizzo IPv6 all'interfaccia esterna del server perimetrale o del pool Edge</span><span class="sxs-lookup"><span data-stu-id="cf79f-150">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <span data-ttu-id="cf79f-151">È anche possibile configurare l'Edge Server o il pool di Edge in uso di un indirizzo di rete per gli indirizzi IP esterni.</span><span class="sxs-lookup"><span data-stu-id="cf79f-151">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="cf79f-152">A tale scopo, seleziona la casella di controllo **l'indirizzo IP esterno di questo pool di bordi viene tradotto da NAT**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-152">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>

8.  <span data-ttu-id="cf79f-153">In **FQDN esterni**eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf79f-153">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="cf79f-154">Se in **Seleziona funzionalità** si è scelto di usare un singolo FQDN e un indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio a/V Edge, digitare il nome di dominio completo esterno in **Access SIP**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-154">If in **Select features** you chose to use a single FQDN and IP address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="cf79f-155">Se si sceglie questa opzione, è necessario specificare un numero di porta diverso per ogni servizio Edge (impostazioni di porta consigliate: 5061 per Access Edge service, 444 per Web Conferencing Edge service e 443 per un/V Edge service).</span><span class="sxs-lookup"><span data-stu-id="cf79f-155">If you choose this option, you must specify a different port number for each of the edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service).</span></span> <span data-ttu-id="cf79f-156">Se si seleziona questa opzione, è possibile evitare potenziali problemi di connettività e semplificare la configurazione perché è quindi possibile usare lo stesso numero di porta, ad esempio 443, per tutti e tre i servizi.</span><span class="sxs-lookup"><span data-stu-id="cf79f-156">Selecting this option can help prevent potential connectivity issues, and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="cf79f-157">Se in **Seleziona funzionalità** non si è scelto di usare un singolo nome di dominio completo e un indirizzo IP, digitare gli FQDN esterni per l' **accesso SIP**, le **conferenze Web** e il **video audio**, mantenendo le porte predefinite.</span><span class="sxs-lookup"><span data-stu-id="cf79f-157">If in **Select features** you did not chose to use a single FQDN and IP Address, type the External FQDNs for **SIP Access**, **Web Conferencing** and **Audio Video**, keeping the default ports.</span></span>

9.  <span data-ttu-id="cf79f-158">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-158">Click **Next**.</span></span>

10. <span data-ttu-id="cf79f-159">In **definire l'indirizzo IP interno**Digitare l'indirizzo IP del server perimetrale nell'indirizzo **IPv4 interno** e l' **indirizzo IPv6 interno** , come appropriato per i requisiti.</span><span class="sxs-lookup"><span data-stu-id="cf79f-159">In **Define the Internal IP address**, type the IP address of your Edge Server in **Internal IPv4 address** and **Internal IPv6 address** as is appropriate for your requirements.</span></span> <span data-ttu-id="cf79f-160">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-160">Click **Next**.</span></span>

11. <span data-ttu-id="cf79f-161">In **definire l'indirizzo IP esterno**eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf79f-161">In **Define the External IP address**, do the following:</span></span>
    
      - <span data-ttu-id="cf79f-162">Se si è scelto di usare un singolo FQDN e un indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Edge, digitare l'indirizzo IPv4 esterno del server perimetrale in **Access SIP**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-162">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 address of the Edge Server in **SIP Access**, and then, click **Next**.</span></span>
    
      - <span data-ttu-id="cf79f-163">Se si è scelto di usare gli indirizzi IPv6, digitare l'indirizzo IPv6 esterno dell'Edge Server in **Access SIP**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-163">If you chose to use IPv6 addresses, type the external IPv6 address of the Edge Server in **SIP Access**, and then, click **Next**.</span></span>
    
      - <span data-ttu-id="cf79f-164">Se non si è scelto di usare un singolo FQDN e un indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Edge, digitare gli indirizzi IPv4 esterni dell'Edge Server in **Access SIP**, servizi di **conferenza Web**e **conferenze a/v**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-164">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 addresses of the Edge Server in **SIP Access**, **Web Conferencing**, and **A/V Conferencing**, and then click **Next**.</span></span>
    
      - <span data-ttu-id="cf79f-165">Se si è scelto di usare gli indirizzi IPv6 e non si è scelto di usare un singolo FQDN e un indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Edge, digitare gli indirizzi IPv6 esterni dell'Edge Server in **Access SIP**, servizi di **conferenza Web**e **conferenze a/v**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-165">If you chose to use IPv6 addresses and did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 addresses of the Edge Server in **SIP Access**, **Web Conferencing**, and **A/V Conferencing**, and then click **Next**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="cf79f-166">Se non si è scelto di abilitare e assegnare l'indirizzo IPv6, la finestra di dialogo non verrà visualizzata.</span><span class="sxs-lookup"><span data-stu-id="cf79f-166">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

        
        </div>

12. <span data-ttu-id="cf79f-167">Se si è scelto di usare NAT, viene visualizzata una finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="cf79f-167">If you chose to use NAT, a dialog box appears.</span></span> <span data-ttu-id="cf79f-168">Nell' **indirizzo IPv4 pubblico per il servizio a/V Edge**Digitare l'indirizzo IPv4 pubblico da tradurre tramite NAT e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-168">In **Public IPv4 address for the A/V Edge service**, type the public IPv4 address to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cf79f-169">Dovrebbe essere l'indirizzo IP esterno del servizio A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="cf79f-169">This should be the external IP address of the A/V Edge service.</span></span>

    
    </div>

13. <span data-ttu-id="cf79f-170">Se si è scelto di usare gli indirizzi NAT e IPv6, viene visualizzata una finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="cf79f-170">If you chose to use NAT and IPv6 addresses, a dialog box appears.</span></span> <span data-ttu-id="cf79f-171">Nell' **indirizzo IPv6 pubblico per il servizio a/V Edge**Digitare l'indirizzo IPv6 pubblico da tradurre tramite NAT e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-171">In **Public IPv6 address for the A/V Edge service**, type the public IPv6 address to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cf79f-172">Dovrebbe essere l'indirizzo IP esterno del servizio A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="cf79f-172">This should be the external IP address of the A/V Edge service.</span></span>

    
    </div>

14. <span data-ttu-id="cf79f-173">In **Definisci l'hop successivo**, nel **pool hop successivo**, selezionare il nome del pool interno, che può essere un pool Front-end o un pool Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="cf79f-173">In **Define the next hop**, in **Next hop pool**, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool.</span></span> <span data-ttu-id="cf79f-174">In alternativa, se la distribuzione include un amministratore, selezionare il Director.</span><span class="sxs-lookup"><span data-stu-id="cf79f-174">Or, if your deployment includes a Director, select the Director.</span></span> <span data-ttu-id="cf79f-175">Quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-175">Then, click **Next**.</span></span>

15. <span data-ttu-id="cf79f-176">In **Associa pool Front End**specificare uno o più pool interni, che possono includere i pool Front-end e i server Standard Edition, da associare a questo Edge Server, selezionando i nomi dei pool interni che devono usare questo Edge Server per la comunicazione con utenti esterni supportati.</span><span class="sxs-lookup"><span data-stu-id="cf79f-176">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pools that are to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cf79f-177">Solo un pool di Edge con bilanciamento del carico o un singolo Edge Server può essere associato a ogni pool interno per il traffico A/V.</span><span class="sxs-lookup"><span data-stu-id="cf79f-177">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic.</span></span> <span data-ttu-id="cf79f-178">Se si dispone già di un pool interno associato a un pool di Edge o un server perimetrale, viene visualizzato un avviso che indica che il pool interno è già associato a un pool di Edge o a un server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="cf79f-178">If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server.</span></span> <span data-ttu-id="cf79f-179">Se si seleziona un pool già associato a un altro Edge Server, l'associazione verrà modificata.</span><span class="sxs-lookup"><span data-stu-id="cf79f-179">If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

16. <span data-ttu-id="cf79f-180">Fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-180">Click **Finish**.</span></span>

17. <span data-ttu-id="cf79f-181">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="cf79f-181">Publish your topology.</span></span>

</div>

<div>

## <a name="to-define-the-topology-for-a-dns-load-balanced-edge-server-pool"></a><span data-ttu-id="cf79f-182">Per definire la topologia di un pool di server Edge con bilanciamento del carico DNS</span><span class="sxs-lookup"><span data-stu-id="cf79f-182">To define the topology for a DNS load balanced Edge Server pool</span></span>

1.  <span data-ttu-id="cf79f-183">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-183">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="cf79f-184">Nell'albero della console espandere il sito in cui si vogliono distribuire i server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="cf79f-184">In the console tree, expand the site in which you want to deploy Edge Servers.</span></span>

3.  <span data-ttu-id="cf79f-185">Fare clic con il pulsante destro del mouse su pool **Edge**e quindi scegliere **nuovo pool di bordi**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-185">Right-click **Edge Pools**, and then click **New Edge Pool**.</span></span>

4.  <span data-ttu-id="cf79f-186">In **definire il nuovo pool di bordi**fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-186">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="cf79f-187">In **definire il nome di dominio completo del pool Edge**eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf79f-187">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="cf79f-188">In **FQDN del pool**Digitare il nome di dominio completo (FQDN) per la connessione interna del pool di bordi.</span><span class="sxs-lookup"><span data-stu-id="cf79f-188">In **Pool FQDN**, type the fully qualified domain name (FQDN) for the internal connection of the Edge pool.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="cf79f-189">Il nome specificato per il pool deve essere il nome del pool di Edge interno.</span><span class="sxs-lookup"><span data-stu-id="cf79f-189">The name you specify for the pool must be the internal edge pool name.</span></span> <span data-ttu-id="cf79f-190">Questa operazione deve essere definita come FQDN.</span><span class="sxs-lookup"><span data-stu-id="cf79f-190">This must be defined as a FQDN.</span></span> <span data-ttu-id="cf79f-191">Generatore di topologie usa gli FQDN e non i nomi brevi.</span><span class="sxs-lookup"><span data-stu-id="cf79f-191">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="cf79f-192">Usare solo caratteri standard (tra cui A-Z, a-z, 0-9 e segni meno) durante l'assegnazione di nomi di dominio completi di Lync Server, Edge Server e pool.</span><span class="sxs-lookup"><span data-stu-id="cf79f-192">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="cf79f-193">Non usare caratteri Unicode o carattere di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="cf79f-193">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="cf79f-194">I caratteri non standard di un nome di dominio completo spesso non sono supportati dal DNS esterno e dalle CA pubbliche (quando il nome di dominio completo deve essere assegnato a SN nel certificato).</span><span class="sxs-lookup"><span data-stu-id="cf79f-194">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span>

        
        </div>
    
      - <span data-ttu-id="cf79f-195">Fare clic su **pool di computer multipli**e quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-195">Click **Multiple computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="cf79f-196">In **Seleziona funzionalità**eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf79f-196">In **Select features**, do the following:</span></span>
    
      - <span data-ttu-id="cf79f-197">Se si prevede di usare un solo FQDN e un indirizzo IP per l'accesso SIP, il servizio Web Conferencing di Lync Server 2013 e un/V Edge Services, selezionare la casella di controllo **Usa un solo nome di dominio completo e indirizzo IP** .</span><span class="sxs-lookup"><span data-stu-id="cf79f-197">If you plan to use a single FQDN and IP address for the SIP access, Lync Server 2013 Web Conferencing service and A/V Edge services, select the **Use a single FQDN and IP Address** check box.</span></span>
    
      - <span data-ttu-id="cf79f-198">Se si prevede di abilitare la Federazione, selezionare la casella **di controllo Abilita federazione per questo pool di bordi (porta 5061)** .</span><span class="sxs-lookup"><span data-stu-id="cf79f-198">If you plan to enable federation, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span> <span data-ttu-id="cf79f-199">Fare clic su **Avanti**</span><span class="sxs-lookup"><span data-stu-id="cf79f-199">Click **Next**</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="cf79f-200">È possibile selezionare questa opzione, ma è possibile pubblicare esternamente per la Federazione solo un pool di Edge o un server perimetrale dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cf79f-200">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation.</span></span> <span data-ttu-id="cf79f-201">Tutti gli accessi da parte di utenti federati, inclusi gli utenti di messaggistica istantanea pubblica, passano attraverso lo stesso pool di Edge o un singolo Edge Server.</span><span class="sxs-lookup"><span data-stu-id="cf79f-201">All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server.</span></span> <span data-ttu-id="cf79f-202">Se ad esempio nella distribuzione è incluso un pool di server perimetrali o un singolo server perimetrale distribuito a New York e uno distribuito a Londra e si abilita il supporto della federazione per il pool di server perimetrali o il singolo server perimetrale di New York, il traffico di segnalazione per gli utenti federati passerà attraverso tale pool o server.</span><span class="sxs-lookup"><span data-stu-id="cf79f-202">For instance, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server.</span></span> <span data-ttu-id="cf79f-203">Ciò avviene persino per le comunicazioni con gli utenti di Londra, anche se un utente interno di Londra che chiama un utente federato di Londra utilizza il pool o il server perimetrale di Londra per il traffico A/V.</span><span class="sxs-lookup"><span data-stu-id="cf79f-203">This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="cf79f-204">Se si prevede di supportare il protocollo XMPP (Extensible Messaging and Presence Protocol) per la distribuzione, selezionare la casella di controllo **Abilita federazione XMPP (porta 5269)**</span><span class="sxs-lookup"><span data-stu-id="cf79f-204">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="cf79f-205">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-205">Click **Next**.</span></span>

8.  <span data-ttu-id="cf79f-206">In **Seleziona opzioni IP**eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf79f-206">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="cf79f-207">**Abilitare IPv4 sull'interfaccia interna**: selezionare la casella di controllo se si vuole applicare un indirizzo IPv4 all'interfaccia interna del server perimetrale o del pool Edge</span><span class="sxs-lookup"><span data-stu-id="cf79f-207">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="cf79f-208">**Abilitare IPv6 sull'interfaccia interna**: selezionare la casella di controllo se si vuole applicare un indirizzo IPv6 all'interfaccia interna del server perimetrale o del pool Edge</span><span class="sxs-lookup"><span data-stu-id="cf79f-208">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="cf79f-209">**Abilitare IPv4 sull'interfaccia esterna**: selezionare la casella di controllo se si vuole applicare un indirizzo IPv4 all'interfaccia esterna del server perimetrale o del pool Edge</span><span class="sxs-lookup"><span data-stu-id="cf79f-209">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="cf79f-210">**Abilitare IPv6 sull'interfaccia esterna**: selezionare la casella di controllo se si vuole applicare un indirizzo IPv6 all'interfaccia esterna del server perimetrale o del pool Edge</span><span class="sxs-lookup"><span data-stu-id="cf79f-210">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <span data-ttu-id="cf79f-211">È anche possibile configurare l'Edge Server o il pool di Edge in uso di un indirizzo di rete per gli indirizzi IP esterni.</span><span class="sxs-lookup"><span data-stu-id="cf79f-211">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="cf79f-212">A tale scopo, seleziona la casella di controllo **l'indirizzo IP esterno di questo pool di bordi viene tradotto da NAT**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-212">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>

9.  <span data-ttu-id="cf79f-213">In **FQDN esterni**eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf79f-213">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="cf79f-214">Se in **Seleziona funzionalità** si è scelto di usare un singolo FQDN e un indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio a/V Edge, digitare il nome di dominio completo esterno in **Access SIP**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-214">If in **Select features** you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="cf79f-215">Se si sceglie questa opzione, è necessario specificare un numero di porta diverso per ogni servizio Edge (impostazioni di porta consigliate: 5061 per Access Edge service, 444 per Web Conferencing Edge service e 443 per un/V Edge service).</span><span class="sxs-lookup"><span data-stu-id="cf79f-215">If you choose this option, you must specify a different port number for each of the Edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service).</span></span> <span data-ttu-id="cf79f-216">Selezionando questa opzione, è possibile evitare potenziali problemi di connettività e semplificare la configurazione perché è quindi possibile usare lo stesso numero di porta, ad esempio 443, per tutti e tre i servizi.</span><span class="sxs-lookup"><span data-stu-id="cf79f-216">By selecting this option, you can help prevent potential connectivity issues and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="cf79f-217">Se in **Seleziona funzionalità** non si è scelto di usare un singolo nome di dominio completo e indirizzo IP, digitare il nome di dominio completo scelto per il lato pubblico del pool di Edge per l' **accesso SIP**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-217">If in **Select features** you did not chose to use a single FQDN and IP Address, type the FQDN that you have chosen for your public facing side of the edge pool for in **SIP Access**.</span></span> <span data-ttu-id="cf79f-218">In **Web Conferencing**Digitare il nome di dominio completo scelto per il lato pubblico del pool di Edge.</span><span class="sxs-lookup"><span data-stu-id="cf79f-218">In **Web Conferencing**, type the FQDN you have chosen for your public facing side of the Edge pool.</span></span> <span data-ttu-id="cf79f-219">In **audio/video**Digitare il nome di dominio completo scelto per il lato pubblico del pool di bordi.</span><span class="sxs-lookup"><span data-stu-id="cf79f-219">In **Audio/Video**, type the FQDN you have chosen for your public facing side of the Edge pool.</span></span> <span data-ttu-id="cf79f-220">Usare le porte predefinite.</span><span class="sxs-lookup"><span data-stu-id="cf79f-220">Use the default ports.</span></span>

10. <span data-ttu-id="cf79f-221">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-221">Click **Next**.</span></span>

11. <span data-ttu-id="cf79f-222">In **definire i computer in questo pool**fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-222">In **Define the computers in this pool**, click **Add**.</span></span>

12. <span data-ttu-id="cf79f-223">In **FQDN interno e indirizzo IP**eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf79f-223">In **Internal FQDN and IP address**, do the following:</span></span>
    
      - <span data-ttu-id="cf79f-224">Nell' **indirizzo IPv4 interno**Digitare l'indirizzo IPv4 e l' **indirizzo IPv6 interno** come appropriato per i requisiti per il primo Edge Server che si vuole creare nel pool.</span><span class="sxs-lookup"><span data-stu-id="cf79f-224">In **Internal IPv4 address**, type the IPv4 address and **Internal IPv6 address** as is appropriate for your requirements for the first Edge Server that you want to create in this pool.</span></span>
    
      - <span data-ttu-id="cf79f-225">In **FQDN interno**Digitare il nome di dominio completo del primo Edge Server che si vuole creare nel pool.</span><span class="sxs-lookup"><span data-stu-id="cf79f-225">In **Internal FQDN**, type the FQDN of the first Edge Server that you want to create in this pool.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="cf79f-226">Il nome specificato deve essere uguale al nome del computer configurato nel server.</span><span class="sxs-lookup"><span data-stu-id="cf79f-226">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="cf79f-227">Per impostazione predefinita, il nome di un computer non aggiunto a un dominio è un nome breve e non un FQDN.</span><span class="sxs-lookup"><span data-stu-id="cf79f-227">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="cf79f-228">Generatore di topologie usa gli FQDN e non i nomi brevi.</span><span class="sxs-lookup"><span data-stu-id="cf79f-228">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="cf79f-229">Devi quindi configurare un suffisso DNS sul nome del computer da distribuire come server perimetrale che non è associato a un dominio.</span><span class="sxs-lookup"><span data-stu-id="cf79f-229">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="cf79f-230">Usare solo caratteri standard (tra cui A-Z, a-z, 0-9 e segni meno) durante l'assegnazione di nomi di dominio completi di Lync Server, Edge Server, pool e matrici.</span><span class="sxs-lookup"><span data-stu-id="cf79f-230">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, pools, and arrays.</span></span> <span data-ttu-id="cf79f-231">Non usare caratteri Unicode o carattere di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="cf79f-231">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="cf79f-232">I caratteri non standard di un nome di dominio completo spesso non sono supportati dal DNS esterno e dalle CA pubbliche (quando il nome di dominio completo deve essere assegnato a SN nel certificato).</span><span class="sxs-lookup"><span data-stu-id="cf79f-232">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="cf79f-233">Per informazioni dettagliate sull'aggiunta di un suffisso DNS a un nome di computer, vedere <A href="lync-server-2013-configure-dns-for-edge-support.md">configurare il supporto DNS per Edge in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="cf79f-233">For details about adding a DNS suffix to a computer name, see <A href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</A>.</span></span>

        
        </div>

13. <span data-ttu-id="cf79f-234">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-234">Click **Next**.</span></span>

14. <span data-ttu-id="cf79f-235">In **definire gli indirizzi IP esterni**eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf79f-235">In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="cf79f-236">Se si è scelto di usare un singolo FQDN e un indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Edge, digitare l'indirizzo IP esterno dell'Edge Server in **Access SIP**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-236">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IP address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="cf79f-237">Se non si è scelto di usare un singolo FQDN e un indirizzo IP per l'accesso SIP, il servizio di conferenza Web e il servizio di conferenza telefonica A/V, digitare l'indirizzo IP scelto per il lato pubblico di questo server Edge pool per l' **accesso SIP**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-237">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IP address that you have chosen for your public facing side of this Edge pool server for **SIP Access**.</span></span> <span data-ttu-id="cf79f-238">In **Web Conferencing**Digitare l'indirizzo IP scelto per il lato pubblico di questo server Edge pool.</span><span class="sxs-lookup"><span data-stu-id="cf79f-238">In **Web Conferencing**, type the IP address that you have chosen for your public facing side of this Edge pool server.</span></span> <span data-ttu-id="cf79f-239">In **conferenze telefoniche a/V**Digitare l'indirizzo IP scelto per il lato pubblico di questo server Edge pool.</span><span class="sxs-lookup"><span data-stu-id="cf79f-239">In **A/V Conferencing**, type the IP address you have chosen for your public facing side of this Edge pool server.</span></span>

15. <span data-ttu-id="cf79f-240">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-240">Click **Next**.</span></span>

16. <span data-ttu-id="cf79f-241">Se si è scelto di abilitare gli indirizzi IPv6, in **definire gli indirizzi IP esterni**eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf79f-241">If you chose to enable IPv6 addresses, In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="cf79f-242">Se si è scelto di usare un singolo FQDN e un indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Edge, digitare l'indirizzo IPv6 esterno dell'Edge Server in **Access SIP**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-242">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="cf79f-243">Se non si è scelto di usare un singolo FQDN e un indirizzo IP per l'accesso SIP, il servizio di conferenza Web e il servizio di conferenza telefonica A/V, digitare l'indirizzo IPv6 scelto per il lato pubblico di questo server Edge pool per l' **accesso SIP**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-243">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IPv6 address that you have chosen for your public facing side of this Edge pool server for **SIP Access**.</span></span> <span data-ttu-id="cf79f-244">In servizi di **conferenza Web**Digitare l'indirizzo IPv6 scelto per il lato pubblico di questo server Edge pool.</span><span class="sxs-lookup"><span data-stu-id="cf79f-244">In **Web Conferencing**, type the IPv6 address that you have chosen for your public facing side of this Edge pool server.</span></span> <span data-ttu-id="cf79f-245">In **conferenze telefoniche a/V**Digitare l'indirizzo IPv6 scelto per il lato pubblico di questo server Edge pool.</span><span class="sxs-lookup"><span data-stu-id="cf79f-245">In **A/V Conferencing**, type the IPv6 address you have chosen for your public facing side of this Edge pool server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cf79f-246">Se non si è scelto di abilitare e assegnare l'indirizzo IPv6, la finestra di dialogo non verrà visualizzata.</span><span class="sxs-lookup"><span data-stu-id="cf79f-246">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

    
    </div>

17. <span data-ttu-id="cf79f-247">Fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-247">Click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cf79f-248">Si vedrà ora il primo server perimetrale creato nel pool nella finestra di dialogo <STRONG>Definisci computer in questo pool</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="cf79f-248">You will now see the first Edge Server you created in your pool in the <STRONG>Define the computers in this pool</STRONG> dialog box.</span></span>

    
    </div>

18. <span data-ttu-id="cf79f-249">In **definire i computer in questo pool**fare clic su **Aggiungi**e quindi ripetere i passaggi da 11 a 14 per il secondo Edge Server che si vuole aggiungere al pool di Edge.</span><span class="sxs-lookup"><span data-stu-id="cf79f-249">In **Define the computers in this pool**, click **Add**, and then repeat steps 11 through 14 for the second Edge Server that you want to add to you Edge pool.</span></span>

19. <span data-ttu-id="cf79f-250">Dopo aver ripetuto i passaggi da 11 a 14, fare clic su **Avanti** in **Definisci i computer in questo pool**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-250">After you repeat steps 11 through 14, click **Next** in **Define the computers in this pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cf79f-251">A questo punto, è possibile visualizzare entrambi i server perimetrali nel pool.</span><span class="sxs-lookup"><span data-stu-id="cf79f-251">At this point, you can see both of the Edge Servers in your pool.</span></span>

    
    </div>

20. <span data-ttu-id="cf79f-252">Se si è scelto di usare NAT, viene visualizzata una finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="cf79f-252">If you chose to use NAT, a dialog box appears.</span></span> <span data-ttu-id="cf79f-253">In **indirizzo IP pubblico**Digitare gli indirizzi IPv4 e IPv6 (in base alle esigenze) pubblici da tradurre tramite NAT e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-253">In **Public IP address**, type the public IPv4 and IPv6 (as appropriate) addresses to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cf79f-254">Dovrebbe essere l'indirizzo IP esterno del bordo A/V.</span><span class="sxs-lookup"><span data-stu-id="cf79f-254">This should be the external IP Address of the A/V Edge.</span></span>

    
    </div>

21. <span data-ttu-id="cf79f-255">In **Definisci l'hop successivo**, nell'elenco del **pool hop successivo** , selezionare il nome del pool interno, che può essere un pool di front-end o un pool di Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="cf79f-255">In **Define the next hop**, in the **Next hop pool** list, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool.</span></span> <span data-ttu-id="cf79f-256">In alternativa, se la distribuzione include un amministratore, selezionare il nome del direttore.</span><span class="sxs-lookup"><span data-stu-id="cf79f-256">Or, if your deployment includes a Director, select the name of the Director.</span></span> <span data-ttu-id="cf79f-257">Quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-257">Then, click **Next**.</span></span>

22. <span data-ttu-id="cf79f-258">In **Associa pool Front End**specificare uno o più pool interni, che possono includere i pool Front-end e i server Standard Edition, da associare a questo Edge Server, selezionando i nomi dei pool interni che devono usare questo Edge Server per la comunicazione con utenti esterni supportati.</span><span class="sxs-lookup"><span data-stu-id="cf79f-258">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pool(s) that is to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cf79f-259">Solo un pool di Edge con bilanciamento del carico o un singolo Edge Server può essere associato a ogni pool interno per il traffico A/V.</span><span class="sxs-lookup"><span data-stu-id="cf79f-259">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic.</span></span> <span data-ttu-id="cf79f-260">Se si dispone già di un pool interno associato a un pool di Edge o un server perimetrale, viene visualizzato un avviso che indica che il pool interno è già associato a un pool di Edge o a un server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="cf79f-260">If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server.</span></span> <span data-ttu-id="cf79f-261">Se si seleziona un pool già associato a un altro Edge Server, l'associazione verrà modificata.</span><span class="sxs-lookup"><span data-stu-id="cf79f-261">If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

23. <span data-ttu-id="cf79f-262">Fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-262">Click **Finish**.</span></span>

24. <span data-ttu-id="cf79f-263">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="cf79f-263">Publish your topology.</span></span>

</div>

<div>

## <a name="to-define-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a><span data-ttu-id="cf79f-264">Per definire la topologia di un pool di server Edge con bilanciamento del carico hardware</span><span class="sxs-lookup"><span data-stu-id="cf79f-264">To define the topology for a hardware load balanced Edge Server pool</span></span>

1.  <span data-ttu-id="cf79f-265">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-265">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="cf79f-266">Nell'albero della console espandere il sito in cui si vogliono distribuire i server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="cf79f-266">In the console tree, expand the site in which you want to deploy Edge Servers.</span></span>

3.  <span data-ttu-id="cf79f-267">Fare clic con il pulsante destro del mouse su **pool di bordi**e quindi scegliere **nuovo pool di bordi**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-267">Right-click **Edge Pools**, and then select **New Edge Pool**.</span></span>

4.  <span data-ttu-id="cf79f-268">In **definire il nuovo pool di bordi**fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-268">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="cf79f-269">In **definire il nome di dominio completo del pool Edge**eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf79f-269">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="cf79f-270">In **FQDN**Digitare il nome di dominio completo (FQDN) scelto per il lato interno del pool di bordi.</span><span class="sxs-lookup"><span data-stu-id="cf79f-270">In **FQDN**, type the fully qualified domain name (FQDN) you have chosen for the internal side of the Edge pool.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="cf79f-271">Il nome specificato per il pool deve essere il nome del pool di Edge interno.</span><span class="sxs-lookup"><span data-stu-id="cf79f-271">The name you specify for the pool must be the internal edge pool name.</span></span> <span data-ttu-id="cf79f-272">Questa operazione deve essere definita come FQDN.</span><span class="sxs-lookup"><span data-stu-id="cf79f-272">This must be defined as a FQDN.</span></span> <span data-ttu-id="cf79f-273">Generatore di topologie usa gli FQDN e non i nomi brevi.</span><span class="sxs-lookup"><span data-stu-id="cf79f-273">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="cf79f-274">Usare solo caratteri standard (tra cui A-Z, a-z, 0-9 e segni meno) durante l'assegnazione di nomi di dominio completi di Lync Server, Edge Server e pool.</span><span class="sxs-lookup"><span data-stu-id="cf79f-274">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="cf79f-275">Non usare caratteri Unicode o carattere di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="cf79f-275">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="cf79f-276">I caratteri non standard di un nome di dominio completo spesso non sono supportati dal DNS esterno e dalle CA pubbliche (quando il nome di dominio completo deve essere assegnato a SN nel certificato).</span><span class="sxs-lookup"><span data-stu-id="cf79f-276">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span>

        
        </div>
    
    <!-- end list -->
    
      - <span data-ttu-id="cf79f-277">Fare clic su **pool di computer multipli**e quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-277">Click **Multiple computer pool**, and then **Next**.</span></span>

6.  <span data-ttu-id="cf79f-278">In **Seleziona funzionalità** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf79f-278">In **Select features** do the following:</span></span>
    
      - <span data-ttu-id="cf79f-279">Se si prevede di usare un solo nome di dominio completo e un indirizzo IP per il servizio di accesso SIP, Lync Server Web Conferencing Service e A/V Edge Services, selezionare la casella **di controllo Usa un solo nome fqdn & indirizzo IP** .</span><span class="sxs-lookup"><span data-stu-id="cf79f-279">If you plan to use a single FQDN and IP address for the SIP access service, Lync Server Web Conferencing service, and A/V Edge service, select the **Use a single FQDN & IP Address** check box.</span></span>
    
      - <span data-ttu-id="cf79f-280">Se si prevede di abilitare la Federazione, selezionare la casella **di controllo Abilita federazione per questo pool di bordi (porta 5061)** .</span><span class="sxs-lookup"><span data-stu-id="cf79f-280">If you plan to enable federation, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="cf79f-281">Puoi selezionare questa opzione, ma solo un bordo o un server perimetrale nell'organizzazione può essere pubblicato esternamente per la Federazione.</span><span class="sxs-lookup"><span data-stu-id="cf79f-281">You can select this option, but only one Edge pool or Edge Server in your organization may be published externally for federation.</span></span> <span data-ttu-id="cf79f-282">Tutti gli accessi da parte di utenti federati, inclusi gli utenti di messaggistica istantanea pubblica, passano attraverso lo stesso pool di Edge o un singolo Edge Server.</span><span class="sxs-lookup"><span data-stu-id="cf79f-282">All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server.</span></span> <span data-ttu-id="cf79f-283">Se ad esempio nella distribuzione è incluso un pool di server perimetrali o un singolo server perimetrale distribuito a New York e uno distribuito a Londra e si abilita il supporto della federazione per il pool di server perimetrali o il singolo server perimetrale di New York, il traffico di segnalazione per gli utenti federati passerà attraverso tale pool o server.</span><span class="sxs-lookup"><span data-stu-id="cf79f-283">For instance, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server.</span></span> <span data-ttu-id="cf79f-284">Ciò avviene persino per le comunicazioni con gli utenti di Londra, anche se un utente interno di Londra che chiama un utente federato di Londra utilizza il pool o il server perimetrale di Londra per il traffico A/V.</span><span class="sxs-lookup"><span data-stu-id="cf79f-284">This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="cf79f-285">Se si prevede di supportare il protocollo XMPP (Extensible Messaging and Presence Protocol) per la distribuzione, selezionare la casella di controllo **Abilita federazione XMPP (porta 5269)**</span><span class="sxs-lookup"><span data-stu-id="cf79f-285">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="cf79f-286">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-286">Click **Next**.</span></span>

8.  <span data-ttu-id="cf79f-287">In **Seleziona opzioni IP**eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf79f-287">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="cf79f-288">**Abilitare IPv4 sull'interfaccia interna**: selezionare la casella di controllo se si vuole applicare un indirizzo IPv4 all'interfaccia interna del server perimetrale o del pool Edge</span><span class="sxs-lookup"><span data-stu-id="cf79f-288">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="cf79f-289">**Abilitare IPv6 sull'interfaccia interna**: selezionare la casella di controllo se si vuole applicare un indirizzo IPv6 all'interfaccia interna del server perimetrale o del pool Edge</span><span class="sxs-lookup"><span data-stu-id="cf79f-289">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="cf79f-290">**Abilitare IPv4 sull'interfaccia esterna**: selezionare la casella di controllo se si vuole applicare un indirizzo IPv4 all'interfaccia esterna del server perimetrale o del pool Edge</span><span class="sxs-lookup"><span data-stu-id="cf79f-290">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="cf79f-291">**Abilitare IPv6 sull'interfaccia esterna**: selezionare la casella di controllo se si vuole applicare un indirizzo IPv6 all'interfaccia esterna del server perimetrale o del pool Edge</span><span class="sxs-lookup"><span data-stu-id="cf79f-291">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="cf79f-292"><STRONG>Non selezionare la</STRONG> casella di controllo <STRONG>l'indirizzo IP esterno del pool di Edge viene tradotto da NAT</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="cf79f-292"><STRONG>Do Not</STRONG> select the <STRONG>The external IP address of the Edge pool is translated by NAT</STRONG> check box.</span></span> <span data-ttu-id="cf79f-293">NAT (Network Address Translation) non è supportato quando si usa il bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="cf79f-293">Network address translation (NAT) is not supported when you are using hardware load balancing.</span></span>

    
    </div>

9.  <span data-ttu-id="cf79f-294">In **FQDN esterni**eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf79f-294">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="cf79f-295">Se in **Seleziona funzionalità** si è scelto di usare un singolo FQDN e un indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio a/V Edge, digitare il nome di dominio completo esterno in **Access SIP**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-295">If in **Select features** you chose to use a single FQDN and IP address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="cf79f-296">Se si sceglie di selezionare questa opzione, è necessario specificare un numero di porta diverso per ogni servizio Edge (impostazioni di porta consigliate: 5061 per Access Edge service, 444 per Web Conferencing Edge service e 443 per un/V Edge Server).</span><span class="sxs-lookup"><span data-stu-id="cf79f-296">If you choose to select this option, you must specify a different port number for each of the Edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service).</span></span> <span data-ttu-id="cf79f-297">Selezionando questa opzione, è possibile evitare potenziali problemi di connettività e semplificare la configurazione perché è quindi possibile usare lo stesso numero di porta, ad esempio 443, per tutti e tre i servizi.</span><span class="sxs-lookup"><span data-stu-id="cf79f-297">By selecting this option, you can help prevent potential connectivity issues and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="cf79f-298">Se in **Seleziona funzionalità** non si è scelto di usare un singolo nome di dominio completo e indirizzo IP, digitare il nome di dominio completo scelto per il lato pubblico del pool di Edge per l' **accesso SIP**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-298">If in **Select features** you did not chose to use a single FQDN and IP address, type the FQDN that you have chosen for your public facing side of the edge pool for in **SIP Access**.</span></span> <span data-ttu-id="cf79f-299">In **Web Conferencing**Digitare il nome di dominio completo scelto per il lato pubblico del pool di Edge.</span><span class="sxs-lookup"><span data-stu-id="cf79f-299">In **Web Conferencing**, type the FQDN you have chosen for your public facing side of the Edge pool.</span></span> <span data-ttu-id="cf79f-300">In **audio/video**Digitare il nome di dominio completo scelto per il lato pubblico del pool di bordi.</span><span class="sxs-lookup"><span data-stu-id="cf79f-300">In **Audio/Video**, type the FQDN you have chosen for your public facing side of the Edge pool.</span></span> <span data-ttu-id="cf79f-301">Usare le porte predefinite.</span><span class="sxs-lookup"><span data-stu-id="cf79f-301">Use the default ports.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="cf79f-302">Questi saranno gli FQDN di Virtual IP (VIP) pubblicamente di fronte per il pool.</span><span class="sxs-lookup"><span data-stu-id="cf79f-302">These will be the publicly facing virtual IP (VIP) FQDNs for the pool.</span></span>

        
        </div>

10. <span data-ttu-id="cf79f-303">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-303">Click **Next**.</span></span>

11. <span data-ttu-id="cf79f-304">In **definire i computer in questo pool**fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-304">In **Define the computers in this pool**, click **Add**.</span></span>

12. <span data-ttu-id="cf79f-305">In **definire gli indirizzi IP esterni**eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf79f-305">In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="cf79f-306">Se si è scelto di usare un singolo FQDN e un indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Edge, digitare l'indirizzo IPv4 esterno dell'Edge Server in **Access**SIP. indirizzo IP esterno dell'Edge Server in **Access SIP**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-306">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 address of the Edge Server in **SIP Access**.external IP address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="cf79f-307">Se non si è scelto di usare un singolo FQDN e un indirizzo IP per l'accesso SIP, il servizio di conferenza Web e il servizio di conferenza telefonica A/V, digitare l'indirizzo IP scelto per il lato pubblico di questo server Edge pool per l' **accesso SIP**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-307">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IP address that you have chosen for your public facing side of this Edge pool server for **SIP Access**.</span></span> <span data-ttu-id="cf79f-308">In **Web Conferencing**Digitare l'indirizzo IP scelto per il lato pubblico di questo server Edge pool.</span><span class="sxs-lookup"><span data-stu-id="cf79f-308">In **Web Conferencing**, type the IP address that you have chosen for your public facing side of this Edge pool server.</span></span> <span data-ttu-id="cf79f-309">In **conferenze telefoniche a/V**Digitare l'indirizzo IP scelto per il lato pubblico di questo server Edge pool.</span><span class="sxs-lookup"><span data-stu-id="cf79f-309">In **A/V Conferencing**, type the IP address you have chosen for your public facing side of this Edge pool server.</span></span>

13. <span data-ttu-id="cf79f-310">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-310">Click **Next**.</span></span>

14. <span data-ttu-id="cf79f-311">Se si è scelto di abilitare gli indirizzi IPv6, in **definire gli indirizzi IP esterni**eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf79f-311">If you chose to enable IPv6 addresses, In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="cf79f-312">Se si è scelto di usare un singolo FQDN e un indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Edge, digitare l'indirizzo IPv6 esterno dell'Edge Server in **Access SIP**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-312">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="cf79f-313">Se non si è scelto di usare un singolo FQDN e un indirizzo IP per l'accesso SIP, il servizio di conferenza Web e il servizio di conferenza telefonica A/V, digitare l'indirizzo IPv6 scelto per il lato pubblico di questo server Edge pool per l' **accesso SIP**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-313">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IPv6 address that you have chosen for your public facing side of this Edge pool server for **SIP Access**.</span></span> <span data-ttu-id="cf79f-314">In servizi di **conferenza Web**Digitare l'indirizzo IPv6 scelto per il lato pubblico di questo server Edge pool.</span><span class="sxs-lookup"><span data-stu-id="cf79f-314">In **Web Conferencing**, type the IPv6 address that you have chosen for your public facing side of this Edge pool server.</span></span> <span data-ttu-id="cf79f-315">In **conferenze telefoniche a/V**Digitare l'indirizzo IPv6 scelto per il lato pubblico di questo server Edge pool.</span><span class="sxs-lookup"><span data-stu-id="cf79f-315">In **A/V Conferencing**, type the IPv6 address you have chosen for your public facing side of this Edge pool server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cf79f-316">Se non si è scelto di abilitare e assegnare l'indirizzo IPv6, la finestra di dialogo non verrà visualizzata.</span><span class="sxs-lookup"><span data-stu-id="cf79f-316">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

    
    </div>

15. <span data-ttu-id="cf79f-317">Fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-317">Click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cf79f-318">Si vedrà ora il primo server perimetrale creato nel pool nella finestra di dialogo <STRONG>Definisci computer in questo pool</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="cf79f-318">You will now see the first Edge Server you created in your pool in the <STRONG>Define the computers in this pool</STRONG> dialog box.</span></span>

    
    </div>

16. <span data-ttu-id="cf79f-319">In **definire i computer in questo pool**fare clic su **Aggiungi**e quindi ripetere i passaggi da 11 a 14 per il secondo Edge Server che si vuole aggiungere al pool di Edge.</span><span class="sxs-lookup"><span data-stu-id="cf79f-319">In **Define the computers in this pool**, click **Add**, and then repeat steps 11 through 14 for the second Edge Server that you want to add to your Edge pool.</span></span>

17. <span data-ttu-id="cf79f-320">Dopo aver ripetuto i passaggi da 11 a 14, fare clic su **Avanti** in **Definisci i computer in questo pool**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-320">After you repeat steps 11 through 14, click **Next** in **Define the computers in this pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cf79f-321">A questo punto, è possibile visualizzare entrambi i server perimetrali nel pool.</span><span class="sxs-lookup"><span data-stu-id="cf79f-321">At this point, you can see both of the Edge Servers in your pool.</span></span>

    
    </div>

18. <span data-ttu-id="cf79f-322">In **Definisci l'hop successivo**, nell'elenco del **pool hop successivo** , selezionare il nome del pool interno, che può essere un pool di front-end o un pool di Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="cf79f-322">In **Define the next hop**, in the **Next hop pool** list, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool.</span></span> <span data-ttu-id="cf79f-323">In alternativa, se la distribuzione include un amministratore, selezionare il nome del direttore.</span><span class="sxs-lookup"><span data-stu-id="cf79f-323">Or, if your deployment includes a Director, select the name of the Director.</span></span> <span data-ttu-id="cf79f-324">Quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-324">Then, click **Next**.</span></span>

19. <span data-ttu-id="cf79f-325">In **Associa pool Front End**specificare uno o più pool interni, che possono includere i pool Front-end e i server Standard Edition, da associare a questo Edge Server, selezionando i nomi dei pool interni che devono usare questo Edge Server per la comunicazione con utenti esterni supportati.</span><span class="sxs-lookup"><span data-stu-id="cf79f-325">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pool(s) that is to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cf79f-326">Solo un pool di Edge con bilanciamento del carico o un singolo Edge Server può essere associato a ogni pool interno per il traffico A/V.</span><span class="sxs-lookup"><span data-stu-id="cf79f-326">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic.</span></span> <span data-ttu-id="cf79f-327">Se si dispone già di un pool interno associato a un pool di Edge o un server perimetrale, viene visualizzato un avviso che indica che il pool interno è già associato a un pool di Edge o a un server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="cf79f-327">If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server.</span></span> <span data-ttu-id="cf79f-328">Se si seleziona un pool già associato a un altro Edge Server, l'associazione verrà modificata.</span><span class="sxs-lookup"><span data-stu-id="cf79f-328">If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

20. <span data-ttu-id="cf79f-329">Fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="cf79f-329">Click **Finish**.</span></span>

21. <span data-ttu-id="cf79f-330">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="cf79f-330">Publish your topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


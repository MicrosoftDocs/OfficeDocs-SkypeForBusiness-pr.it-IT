---
title: 'Lync Server 2013: definire un Mediation Server in Generatore di topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a Mediation Server in Topology Builder
ms:assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398391(v=OCS.15)
ms:contentKeyID: 48184217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f1356217b9effe3f2282f6931b601e84aa46770
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984240"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-mediation-server-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="69442-102">Definire un Mediation Server in Generatore di topologia in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69442-102">Define a Mediation Server in Topology Builder in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69442-103">_**Argomento Ultima modifica:** 2013-03-25_</span><span class="sxs-lookup"><span data-stu-id="69442-103">_**Topic Last Modified:** 2013-03-25_</span></span>

<span data-ttu-id="69442-104">Seguire la procedura descritta in questo argomento per usare generatore di topologia per definire un Mediation Server autonomo o un pool collocato con un pool Front-end in un sito per il quale non è stato distribuito in precedenza Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="69442-104">Follow the steps in this topic to use Topology Builder to define a stand-alone Mediation Server or a pool collocated with a Front End pool at a site for which you did not previously deploy Enterprise Voice.</span></span>

<span data-ttu-id="69442-105">Puoi definire una topologia usando un account che è un membro del gruppo Administrators.</span><span class="sxs-lookup"><span data-stu-id="69442-105">You can define a topology using an account that is a member of the Administrators group.</span></span>

<div>

## <a name="define-mediation-server-collocated-to-a-front-end-pool"></a><span data-ttu-id="69442-106">Definire Mediation Server collocato in un pool Front-End</span><span class="sxs-lookup"><span data-stu-id="69442-106">Define Mediation Server collocated to a Front End pool</span></span>

<span data-ttu-id="69442-107">Seguire la procedura descritta in questo argomento per usare generatore di topologia per definire un Mediation Server collocato in un pool Front-end in un sito in cui Enterprise Voice non è stato distribuito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="69442-107">Follow the steps in this topic to use Topology Builder to define a Mediation Server collocated to a Front End pool in a site where Enterprise Voice has not been previously deployed.</span></span>

<div>

## <a name="to-add-a-mediation-server-to-a-front-end-pool"></a><span data-ttu-id="69442-108">Per aggiungere un Mediation Server a un pool Front-End</span><span class="sxs-lookup"><span data-stu-id="69442-108">To Add a Mediation Server to a Front End pool</span></span>

1.  <span data-ttu-id="69442-109">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="69442-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="69442-110">Nell'albero della console di generatore di topologia espandere il nome del sito per il quale si desidera definire un pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="69442-110">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Front End pool.</span></span>

3.  <span data-ttu-id="69442-111">Nell'albero della console fare clic con il pulsante destro del mouse sul tipo di pool Front-end desiderato e quindi scegliere **nuovo pool Front-end.**..</span><span class="sxs-lookup"><span data-stu-id="69442-111">In the console tree, right-click the type of Front End pool you want, and then click **New Front End pool..**.</span></span>

4.  <span data-ttu-id="69442-112">Spostarsi tra la procedura guidata **Definisci nuovo pool di front end** fino a raggiungere la pagina **Selezione ruoli server collocati** .</span><span class="sxs-lookup"><span data-stu-id="69442-112">Navigate through the **Define New Front End Pool** wizard until you reach the **Select collocated server roles** page.</span></span>

5.  <span data-ttu-id="69442-113">In **Seleziona ruoli server collocati selezionare**l'opzione **collocazione Mediation Server**.</span><span class="sxs-lookup"><span data-stu-id="69442-113">In **Select collocated server roles**, check the option **Collocate Mediation Server**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="69442-114">Se il tipo di pool Front-End selezionato è Enterprise Edition, il componente Mediation Server verrà installato in tutti i server front-end del pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="69442-114">If the type of Front End pool you selected is the Enterprise Edition, then the Mediation Server component will be installed on all the Front End Servers of that Front End pool.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="69442-115">Il <STRONG>pool di hop successivo</STRONG> usato dal Mediation Server sarà il pool Front-end in cui è installato il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="69442-115">The <STRONG>Next hop pool</STRONG> used by the Mediation Server will be the Front End pool where the Mediation Server is collocated on.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="69442-116">Il <STRONG>pool di Edge</STRONG> usato da Mediation Server sarà lo stesso pool di Edge associato al pool Front-end in cui è installato il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="69442-116">The <STRONG>Edge pool</STRONG> used by the Mediation Server will be the same Edge pool associated with the Front End pool where the Mediation Server is collocated on.</span></span></P></LI></UL>

    
    </div>

6.  <span data-ttu-id="69442-117">Fare clic su **Imposta predefinito** per usare questo pool Front-end per instradare le chiamate da Microsoft Office Communications Server 2007 R2 alla rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="69442-117">Click **Make Default** to use this Front End pool to route calls from Microsoft Office Communications Server 2007 R2 to the PSTN.</span></span>

7.  <span data-ttu-id="69442-118">Al termine, fare clic su **fine** per associare uno o più peer al pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="69442-118">Click **Finish** when you are finished associating one or more peers to the Front End pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="69442-119">Prima di procedere con il passaggio successivo nel processo di distribuzione di VoIP aziendale, verificare che il pool di Mediation Server (ad esempio il pool Front end con il componente Mediation Server) usi i nomi di dominio completi specificati.</span><span class="sxs-lookup"><span data-stu-id="69442-119">Before you proceed to the next step in the Enterprise Voice deployment process, make sure that the Mediation Server pool (i.e. Front End pool with the Mediation Server component collocated) is using the FQDNs that you specified.</span></span>

    
    </div>

8.  <span data-ttu-id="69442-120">Seguire quindi le procedure descritte in [pubblicare la topologia in Lync server 2013](lync-server-2013-publish-the-topology.md) nella documentazione della Guida alla distribuzione per aggiungere il Mediation Server alla topologia prima di procedere con il passaggio successivo della modifica delle porte di ascolto del server di mediazione, se necessario.</span><span class="sxs-lookup"><span data-stu-id="69442-120">Next, follow the procedures in [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment Guide documentation to add the Mediation Server to your topology before proceeding to the next step of modifying the listening ports of the Mediation Server if needed.</span></span> <span data-ttu-id="69442-121">È necessario pubblicare la topologia ogni volta che si usa generatore di topologie per definire o modificare la topologia.</span><span class="sxs-lookup"><span data-stu-id="69442-121">You must publish your topology each time you use Topology Builder to define or modify your topology.</span></span>

</div>

</div>

<div>

## <a name="define-stand-alone-mediation-server"></a><span data-ttu-id="69442-122">Definire Mediation Server autonomo</span><span class="sxs-lookup"><span data-stu-id="69442-122">Define stand-alone Mediation Server</span></span>

<span data-ttu-id="69442-123">Seguire i passaggi descritti in questo argomento per usare generatore di topologia per definire un server di mediazione autonomo o un pool in un sito in cui Enterprise Voice non è stato distribuito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="69442-123">Follow the steps in this topic to use Topology Builder to define a stand-alone Mediation Server or pool at a site where Enterprise Voice has not been previously deployed.</span></span>

<span data-ttu-id="69442-124">Se sono già stati distribuiti server di mediazione collocati in pool Front-end in questo sito, è possibile ignorare questa sezione e [installare i file per Mediation Server in Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md) prima di procedere alla [configurazione dei trunk in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span><span class="sxs-lookup"><span data-stu-id="69442-124">If you already deployed Mediation Servers collocated to Front End pools at this site, you can skip this section and [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) before proceeding to [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="69442-125">In questa sezione si presuppone che sia già stato configurato almeno un pool Front-End, come descritto in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">definire e configurare un pool Front end o un server Standard Edition in Lync server 2013</A> e <A href="lync-server-2013-publish-the-topology.md">pubblicare la topologia in Lync Server 2013</A> nella documentazione della Guida alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="69442-125">This section assumes that you have already setup at least one Front End pool, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment Guide documentation.</span></span>



</div>

<div>

## <a name="to-add-a-mediation-server"></a><span data-ttu-id="69442-126">Per aggiungere un Mediation Server</span><span class="sxs-lookup"><span data-stu-id="69442-126">To Add a Mediation Server</span></span>

1.  <span data-ttu-id="69442-127">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="69442-127">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="69442-128">Nell'albero della console di generatore di topologia espandere il nome del sito per il quale si desidera definire un Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="69442-128">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Mediation Server.</span></span>

3.  <span data-ttu-id="69442-129">Nell'albero della console fare clic con il pulsante destro del mouse sul nodo **pool di mediazione** e quindi scegliere **pool di Mediation Server**.</span><span class="sxs-lookup"><span data-stu-id="69442-129">In the console tree, right-click the **Mediation pools** node, and then click **Mediation Server pool**.</span></span>

4.  <span data-ttu-id="69442-130">In **Definisci nuovo pool di mediazione**Digitare il nome di dominio completo (FQDN) del pool di Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="69442-130">In **Define New Mediation Pool**, type the Mediation Server pool fully qualified domain name (FQDN).</span></span>

5.  <span data-ttu-id="69442-131">Eseguire quindi una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="69442-131">Next, do one of the following:</span></span>
    
      - <span data-ttu-id="69442-132">Se si vuole distribuire più server di mediazione nel pool per ottenere una disponibilità elevata, selezionare **più pool di computer**.</span><span class="sxs-lookup"><span data-stu-id="69442-132">If you want to deploy multiple Mediation Servers in the pool to provide high availability, then select **Multiple computer pool**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="69442-133">È necessario distribuire il bilanciamento del carico DNS per supportare i pool di Mediation Server con più server di mediazione.</span><span class="sxs-lookup"><span data-stu-id="69442-133">You must deploy DNS load balancing to support Mediation Server pools that have multiple Mediation Servers.</span></span> <span data-ttu-id="69442-134">Per informazioni dettagliate, vedere la sezione Utilizzo di bilanciamento del carico DNS nei pool di Mediation Server del <A href="lync-server-2013-dns-load-balancing.md">bilanciamento del carico DNS in Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="69442-134">For details, see the Using DNS Load Balancing on Mediation Server Pools section of <A href="lync-server-2013-dns-load-balancing.md">DNS load balancing in Lync Server 2013</A> in the Planning documentation.</span></span>

        
        </div>
    
      - <span data-ttu-id="69442-135">Se si vuole distribuire un solo Mediation Server nel pool perché non è necessaria una disponibilità elevata, selezionare **Single computer pool**.</span><span class="sxs-lookup"><span data-stu-id="69442-135">If you want to deploy only one Mediation Server in the pool because you do not require high availability, then select **Single computer pool**.</span></span> <span data-ttu-id="69442-136">Ignorare il passaggio seguente.</span><span class="sxs-lookup"><span data-stu-id="69442-136">Skip the following step.</span></span>

6.  <span data-ttu-id="69442-137">Se nel passaggio precedente è stato selezionato **più pool di computer** , nell' **elemento Definisci i computer in questo pool** fare clic su **FQDN computer**, digitare il nome di dominio completo di ogni server nel pool e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="69442-137">If you selected **Multiple computer pool** in the previous step, on the **Define the computers in this pool** item, click **Computer FQDN**, type the FQDN of each server in the pool, and then click **Add**.</span></span> <span data-ttu-id="69442-138">Ripetere questo passaggio per tutti gli altri Mediation Server che si vuole aggiungere al pool.</span><span class="sxs-lookup"><span data-stu-id="69442-138">Repeat this step for all other Mediation Servers that you want to add to the pool.</span></span> <span data-ttu-id="69442-139">Dopo aver definito tutti i computer nel pool, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="69442-139">When you have defined all the computers in the pool, click **Next**.</span></span>

7.  <span data-ttu-id="69442-140">Nella pagina **selezionare l'hop successivo** fare clic su **pool hop successivo**, fare clic sul nome di dominio completo del pool Front-end che utilizzerà questo pool di Mediation Server e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="69442-140">On the **Select the next hop** page, click **Next hop pool**, click the FQDN of the Front End pool that will use this Mediation Server pool, and then click **Next**.</span></span>

8.  <span data-ttu-id="69442-141">Nella pagina **selezionare un server perimetrale** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="69442-141">On the **Select an Edge Server** page, do one of the following:</span></span>
    
      - <span data-ttu-id="69442-142">Se si vuole consentire la connettività PSTN agli utenti esterni abilitati per VoIP aziendale, in **selezionare pool Edge usato da questo Mediation Server**fare clic sul nome di dominio completo del pool di Edge Server che utilizzerà questo pool di Mediation Server per consentire la connettività PSTN a tali utenti esterni e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="69442-142">If you want to provide PSTN connectivity to external users enabled for Enterprise Voice, under **Select Edge Pool used by this Mediation Server**, click the FQDN of the Edge Server pool that will use this Mediation Server pool to provide PSTN connectivity to those external users, and then click **Next**.</span></span>
    
      - <span data-ttu-id="69442-143">Se non si prevede di abilitare gli utenti esterni per VoIP aziendale o se non si vuole concedere connettività PSTN agli utenti quando si trovano all'esterno della rete interna, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="69442-143">If you do not plan to enable external users for Enterprise Voice, or if you do not want to provide PSTN connectivity to users when they are outside the internal network, click **Next**.</span></span>

9.  <span data-ttu-id="69442-144">Seguire quindi le procedure descritte in [pubblicare la topologia in Lync server 2013](lync-server-2013-publish-the-topology.md) nella documentazione relativa alla distribuzione per aggiungere il Mediation Server alla topologia.</span><span class="sxs-lookup"><span data-stu-id="69442-144">Next, follow the procedures in [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation to add the Mediation Server to the topology.</span></span> <span data-ttu-id="69442-145">È necessario pubblicare la topologia ogni volta che si usa generatore di topologie per creare o modificare la topologia in modo che i dati possano essere usati per installare i file per i server che esegue Lync Server.</span><span class="sxs-lookup"><span data-stu-id="69442-145">You must publish your topology each time you use Topology Builder to build or modify your topology so that the data can be used to install the files for servers that are running Lync Server.</span></span> <span data-ttu-id="69442-146">Continuare con i passaggi successivi per modificare le porte di ascolto nel server Mediation, se necessario.</span><span class="sxs-lookup"><span data-stu-id="69442-146">Then continue to the next steps to modify the listening ports on the Mediation Server, if necessary.</span></span>

</div>

</div>

<div>

## <a name="define-the-mediation-server-listening-ports"></a><span data-ttu-id="69442-147">Definire le porte di ascolto di Mediation Server</span><span class="sxs-lookup"><span data-stu-id="69442-147">Define the Mediation Server Listening Ports</span></span>

<span data-ttu-id="69442-148">Seguire i passaggi descritti in questo argomento per usare generatore di topologie per definire le porte in attesa un server di mediazione o un pool accetteranno le connessioni in ingresso da un peer del gateway.</span><span class="sxs-lookup"><span data-stu-id="69442-148">Follow the steps in this topic to use Topology Builder to define the listening ports a Mediation Server or pool will accept incoming connections from a gateway peer.</span></span>

<div>

## <a name="to-modify-the-mediation-server-listening-ports"></a><span data-ttu-id="69442-149">Per modificare le porte di ascolto di Mediation Server</span><span class="sxs-lookup"><span data-stu-id="69442-149">To Modify the Mediation Server Listening Ports</span></span>

1.  <span data-ttu-id="69442-150">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="69442-150">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="69442-151">Nell'albero della console di generatore di topologia espandere il nodo **pool di mediazione** e fare clic con il pulsante destro del mouse sul server di mediazione creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="69442-151">In Topology Builder, in the console tree, expand the **Mediation pools** node, and right-click the Mediation Server previously created.</span></span>

3.  <span data-ttu-id="69442-152">Per impostazione predefinita, le porte di ascolto SIP sul Mediation Server sono 5070 per il traffico TLS da Lync Server, 5067 per il traffico TLS da peer (gateway, sistemi PBX o SBCs).</span><span class="sxs-lookup"><span data-stu-id="69442-152">By default, the SIP listening ports on the Mediation Server are 5070 for TLS traffic from Lync Server, 5067 for TLS traffic from peers (gateways, PBXes, or SBCs).</span></span> <span data-ttu-id="69442-153">La porta TCP è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="69442-153">TCP port is disabled by default.</span></span> <span data-ttu-id="69442-154">È necessario abilitare la porta TCP se sono presenti gateway che non supportano TLS.</span><span class="sxs-lookup"><span data-stu-id="69442-154">You must enable TCP port if you have gateways that do not support TLS.</span></span>

4.  <span data-ttu-id="69442-155">Specificare l'intervallo di porte di ascolto TLS o TCP desiderato il server di mediazione accetterà le connessioni in ingresso dai gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="69442-155">Specify the desired TLS or TCP listening port range the Mediation Server will accept incoming connections from PSTN gateways.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="69442-156">L'immissione di un intervallo di porte TCP non è necessaria se l' <STRONG>Abilitazione della porta TCP</STRONG> non è selezionata.</span><span class="sxs-lookup"><span data-stu-id="69442-156">Entering a TCP port range is not required if <STRONG>Enable TCP port</STRONG> is not checked.</span></span> <span data-ttu-id="69442-157">Questa impostazione è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="69442-157">This setting is optional.</span></span>

    
    </div>

<span data-ttu-id="69442-158">Definire quindi [un gateway in Generatore di topologia in Lync server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md) e installare i file in ogni Mediation Server nel pool seguendo le procedure descritte in [installare i file per Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="69442-158">Next, [Define a gateway in Topology Builder in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md) and install the files on each Mediation Server in the pool by following the procedures in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md).</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


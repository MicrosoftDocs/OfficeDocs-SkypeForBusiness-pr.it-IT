---
title: 'Lync Server 2013: Configurare DNS per il bilanciamento del carico'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS for load balancing
ms:assetid: 1b2e8414-8676-4872-8ecf-ea07196f74de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398251(v=OCS.15)
ms:contentKeyID: 48183540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5b68bf226c71d65835791577ab9a45f18b2a10e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758354"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-load-balancing-in-lync-server-2013"></a><span data-ttu-id="4f00d-102">Configurare DNS per il bilanciamento del carico in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f00d-102">Configure DNS for load balancing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f00d-103">_**Argomento Ultima modifica:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="4f00d-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="4f00d-104">Per completare correttamente questa procedura, è necessario avere effettuato l'accesso al server o al dominio come membro del gruppo Domain Admins o di un membro del gruppo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="4f00d-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="4f00d-105">Il bilanciamento del carico DNS (Domain Name System) bilancia il traffico di rete univoco per Lync Server 2013, ad esempio il traffico SIP e il traffico multimediale.</span><span class="sxs-lookup"><span data-stu-id="4f00d-105">Domain Name System (DNS) Load Balancing balances the network traffic that is unique to Lync Server 2013, such as SIP traffic and media traffic.</span></span> <span data-ttu-id="4f00d-106">Il bilanciamento del carico DNS è supportato per i pool Front-End, i pool di bordi, i pool di direttori e i pool di mediazione autonomi.</span><span class="sxs-lookup"><span data-stu-id="4f00d-106">DNS load balancing is supported for Front End pools, Edge pools, Director pools, and stand-alone Mediation pools.</span></span> <span data-ttu-id="4f00d-107">Un pool configurato per l'uso del bilanciamento del carico DNS deve avere due nomi di dominio completi (FQDN) definiti: l'FQDN del pool normale usato dal bilanciamento del carico DNS (ad esempio, pool1.contoso.com) e che viene risolto nell'IPs fisico dei server nel pool e un altro nome di dominio completo per i servizi Web del pool, ad esempio web1.contoso.net, che viene risolto nell'indirizzo IP virtuale del pool.</span><span class="sxs-lookup"><span data-stu-id="4f00d-107">A pool that is configured to use DNS load balancing must have two fully qualified domain names (FQDNs) defined: the regular pool FQDN that is used by DNS load balancing (for example, pool1.contoso.com) and that resolves to the physical IPs of the servers in the pool, and another FQDN for the pool’s Web Services (for example, web1.contoso.net), which resolves to the virtual IP address of the pool.</span></span> <span data-ttu-id="4f00d-108">Per informazioni dettagliate sul bilanciamento del carico DNS, vedere [bilanciamento del carico DNS in Lync Server 2013](lync-server-2013-dns-load-balancing.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="4f00d-108">For details about DNS Load Balancing, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) in the Planning documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4f00d-109">Il bilanciamento del carico hardware è ancora necessario per il traffico HTTPS da client a server.</span><span class="sxs-lookup"><span data-stu-id="4f00d-109">Hardware load balancing is still required for client to server HTTPS traffic.</span></span>



</div>

<span data-ttu-id="4f00d-110">Per poter usare il bilanciamento del carico DNS, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4f00d-110">Before you can use DNS load balancing, you must do the following:</span></span>

1.  <span data-ttu-id="4f00d-111">Eseguire l'override del nome FQDN del pool di servizi Web interni.</span><span class="sxs-lookup"><span data-stu-id="4f00d-111">Override the internal Web Services pool FQDN.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="4f00d-112">Se decidi di ignorare i servizi Web interni con un nome di dominio completo definito autonomamente, ogni nome di dominio completo deve essere univoco da qualsiasi altro pool di front-end, Director o pool di Director.</span><span class="sxs-lookup"><span data-stu-id="4f00d-112">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

2.  <span data-ttu-id="4f00d-113">Creare record host DNS per risolvere il nome di dominio completo del pool agli indirizzi IP di tutti i server del pool.</span><span class="sxs-lookup"><span data-stu-id="4f00d-113">Create DNS A host records to resolve the pool FQDN to the IP addresses of all the servers in the pool.</span></span>

3.  <span data-ttu-id="4f00d-114">Abilitare la randomizzazione degli indirizzi IP o, per Windows Server DNS, abilitare Round Robin.</span><span class="sxs-lookup"><span data-stu-id="4f00d-114">Enable IP Address randomization or, for Windows Server DNS, enable round robin.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4f00d-115">Il Round Robin deve essere abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4f00d-115">Round robin should be enabled by default.</span></span>

    
    </div>

<div>

## <a name="to-override-internal-web-services-fqdn"></a><span data-ttu-id="4f00d-116">Per ignorare l'FQDN dei servizi Web interni</span><span class="sxs-lookup"><span data-stu-id="4f00d-116">To override internal Web services FQDN</span></span>

1.  <span data-ttu-id="4f00d-117">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4f00d-117">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="4f00d-118">Nell'albero della console espandere il nodo Pool di front end di Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="4f00d-118">From the console tree, expand the Enterprise Edition Front End pools node.</span></span>

3.  <span data-ttu-id="4f00d-119">Fare clic con il pulsante destro del mouse sul pool, scegliere **modifica proprietà**e quindi fare clic su **servizi Web**.</span><span class="sxs-lookup"><span data-stu-id="4f00d-119">Right-click the pool, click **Edit Properties**, and then click **Web Services**.</span></span>

4.  <span data-ttu-id="4f00d-120">Sotto **servizi Web interni**selezionare la casella di controllo **Sostituisci FQDN** .</span><span class="sxs-lookup"><span data-stu-id="4f00d-120">Below **Internal web services**, select the **Override FQDN** check box.</span></span>

5.  <span data-ttu-id="4f00d-121">Digitare il nome di dominio completo del pool che viene risolto negli indirizzi IP fisici dei server nel pool.</span><span class="sxs-lookup"><span data-stu-id="4f00d-121">Type the pool FQDN that resolves to the physical IP addresses of the servers in the pool.</span></span>

6.  <span data-ttu-id="4f00d-122">Sotto **servizi Web esterni**Digitare il nome di dominio completo del pool esterno che viene risolto negli indirizzi IP virtuali del pool e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4f00d-122">Below **External web services**, type the external pool FQDN that resolves to the virtual IP addresses of the pool, and then click **OK**.</span></span>

7.  <span data-ttu-id="4f00d-123">Nell'albero della console fare clic su **Lync Server 2013**e quindi, nel riquadro **azioni** , fare clic su **Pubblica topologia**.</span><span class="sxs-lookup"><span data-stu-id="4f00d-123">From the console tree, click **Lync Server 2013**, and then in the **Actions** pane, click **Publish Topology**.</span></span>

</div>

<div>

## <a name="to-create-dns-host-a-records-for-all-internal-pool-servers"></a><span data-ttu-id="4f00d-124">Per creare record host DNS (A) per tutti i server di pool interni</span><span class="sxs-lookup"><span data-stu-id="4f00d-124">To create DNS Host (A) Records for all internal pool servers</span></span>

1.  <span data-ttu-id="4f00d-125">Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **strumenti di amministrazione**e quindi fare clic su **DNS**.</span><span class="sxs-lookup"><span data-stu-id="4f00d-125">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="4f00d-126">In **gestore DNS**fare clic sul server DNS che gestisce i record per espanderlo.</span><span class="sxs-lookup"><span data-stu-id="4f00d-126">In **DNS Manager**, click the DNS Server that manages your records to expand it.</span></span>

3.  <span data-ttu-id="4f00d-127">Fare clic su **Inoltra aree di ricerca** per espanderlo.</span><span class="sxs-lookup"><span data-stu-id="4f00d-127">Click **Forward Lookup Zones** to expand it.</span></span>

4.  <span data-ttu-id="4f00d-128">Fare clic con il pulsante destro del mouse sul dominio DNS a cui è necessario aggiungere i record e quindi scegliere **nuovo host (a o AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="4f00d-128">Right-click the DNS domain that you need to add records to, and then click **New Host (A or AAAA)**.</span></span>

5.  <span data-ttu-id="4f00d-129">Nella casella **nome** Digitare il nome del record host (il nome del dominio verrà accodato automaticamente).</span><span class="sxs-lookup"><span data-stu-id="4f00d-129">In the **Name** box, type the name of the host record (the domain name will be automatically appended).</span></span>

6.  <span data-ttu-id="4f00d-130">Nella casella indirizzo IP digitare l'indirizzo IP del server front-end individuale e quindi selezionare **Crea record puntatore associato (PTR)** o **consentire a qualsiasi utente autenticato di aggiornare i record DNS con lo stesso nome proprietario**, se applicabile.</span><span class="sxs-lookup"><span data-stu-id="4f00d-130">In the IP Address box, type the IP address of the individual Front End Server and then select **Create associated pointer (PTR) record** or **Allow any authenticated user to update DNS records with the same owner name**, if applicable.</span></span>

7.  <span data-ttu-id="4f00d-131">Continuare a creare record per tutti i server front-end membri che parteciperanno al bilanciamento del carico DNS.</span><span class="sxs-lookup"><span data-stu-id="4f00d-131">Continue creating records for all member Front End Servers that will participate in DNS Load Balancing.</span></span>
    
    <span data-ttu-id="4f00d-132">Ad esempio, se si ha un pool denominato pool1.contoso.com e tre server front-end, si creeranno le voci DNS seguenti:</span><span class="sxs-lookup"><span data-stu-id="4f00d-132">For example, if you had a pool named pool1.contoso.com and three Front End Servers, you would create the following DNS entries:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="4f00d-133">FQDN</span><span class="sxs-lookup"><span data-stu-id="4f00d-133">FQDN</span></span></th>
    <th><span data-ttu-id="4f00d-134">Tipo</span><span class="sxs-lookup"><span data-stu-id="4f00d-134">Type</span></span></th>
    <th><span data-ttu-id="4f00d-135">Dati</span><span class="sxs-lookup"><span data-stu-id="4f00d-135">Data</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="4f00d-136">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4f00d-136">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="4f00d-137">Host (A)</span><span class="sxs-lookup"><span data-stu-id="4f00d-137">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="4f00d-138">192.168.1.1</span><span class="sxs-lookup"><span data-stu-id="4f00d-138">192.168.1.1</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="4f00d-139">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4f00d-139">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="4f00d-140">Host (A)</span><span class="sxs-lookup"><span data-stu-id="4f00d-140">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="4f00d-141">192.168.1.2</span><span class="sxs-lookup"><span data-stu-id="4f00d-141">192.168.1.2</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="4f00d-142">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4f00d-142">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="4f00d-143">Host (A)</span><span class="sxs-lookup"><span data-stu-id="4f00d-143">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="4f00d-144">192.168.1.3</span><span class="sxs-lookup"><span data-stu-id="4f00d-144">192.168.1.3</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="4f00d-145">Per informazioni dettagliate sulla creazione di record host DNS (A), vedere [configurare i record host DNS per Lync Server 2013](lync-server-2013-configure-dns-host-records.md).</span><span class="sxs-lookup"><span data-stu-id="4f00d-145">For details about creating DNS Host (A) records, see [Configure DNS Host records for Lync Server 2013](lync-server-2013-configure-dns-host-records.md).</span></span>

</div>

<div>

## <a name="to-enable-round-robin-for-windows-server"></a><span data-ttu-id="4f00d-146">Per abilitare Round Robin per Windows Server</span><span class="sxs-lookup"><span data-stu-id="4f00d-146">To enable round robin for Windows Server</span></span>

1.  <span data-ttu-id="4f00d-147">Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **strumenti di amministrazione**e quindi fare clic su **DNS**.</span><span class="sxs-lookup"><span data-stu-id="4f00d-147">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="4f00d-148">Espandere **DNS**, fare clic con il pulsante destro del mouse sul server DNS che si vuole configurare e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="4f00d-148">Expand **DNS**, right-click the DNS server you want to configure, and then click **Properties**.</span></span>

3.  <span data-ttu-id="4f00d-149">Fare clic sulla scheda **Avanzate** , selezionare **Abilita Round Robin** e **abilitare l'ordinamento per netmask**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4f00d-149">Click the **Advanced** tab, select **Enable round robin** and **Enable netmask ordering**, and then click **OK**.</span></span>
    
    <span data-ttu-id="4f00d-150">![Finestra di dialogo del round robin DNS](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "Finestra di dialogo del round robin DNS")</span><span class="sxs-lookup"><span data-stu-id="4f00d-150">![DNS Round Robin dialog box](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "DNS Round Robin dialog box")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4f00d-151">Questa caratteristica deve essere abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4f00d-151">This feature should be enabled by default.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4f00d-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f00d-152">See Also</span></span>


[<span data-ttu-id="4f00d-153">Bilanciamento del carico DNS in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f00d-153">DNS load balancing in Lync Server 2013</span></span>](lync-server-2013-dns-load-balancing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


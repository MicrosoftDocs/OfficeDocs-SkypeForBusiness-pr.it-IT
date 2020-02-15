---
title: 'Lync Server 2013: configurare DNS per il bilanciamento del carico'
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
ms.openlocfilehash: 797a788649edab99852cfec9f83423075b14f742
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-load-balancing-in-lync-server-2013"></a><span data-ttu-id="10aa2-102">Configurare il DNS per il bilanciamento del carico in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10aa2-102">Configure DNS for load balancing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10aa2-103">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="10aa2-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="10aa2-104">Per eseguire correttamente questa procedura, è necessario connettersi al server o al dominio almeno come membro del gruppo Domain Admins o DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="10aa2-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="10aa2-105">Il bilanciamento del carico DNS (Domain Name System) bilancia il traffico di rete univoco per Lync Server 2013, ad esempio il traffico SIP e il traffico multimediale.</span><span class="sxs-lookup"><span data-stu-id="10aa2-105">Domain Name System (DNS) Load Balancing balances the network traffic that is unique to Lync Server 2013, such as SIP traffic and media traffic.</span></span> <span data-ttu-id="10aa2-106">Il bilanciamento del carico DNS è supportato per pool Front End, pool di server perimetrali, pool di server Director e pool Mediation Server autonomi.</span><span class="sxs-lookup"><span data-stu-id="10aa2-106">DNS load balancing is supported for Front End pools, Edge pools, Director pools, and stand-alone Mediation pools.</span></span> <span data-ttu-id="10aa2-107">Un pool configurato per l'utilizzo del bilanciamento del carico DNS deve disporre di due nomi di dominio completi (FQDN) definiti: il nome FQDN del pool normale utilizzato dal bilanciamento del carico DNS (ad esempio, pool1.contoso.com) e che viene risolto negli indirizzi IP fisici dei server del pool. e un altro nome di dominio completo per i servizi Web del pool (ad esempio, web1.contoso.net), che viene risolto nell'indirizzo IP virtuale del pool.</span><span class="sxs-lookup"><span data-stu-id="10aa2-107">A pool that is configured to use DNS load balancing must have two fully qualified domain names (FQDNs) defined: the regular pool FQDN that is used by DNS load balancing (for example, pool1.contoso.com) and that resolves to the physical IPs of the servers in the pool, and another FQDN for the pool’s Web Services (for example, web1.contoso.net), which resolves to the virtual IP address of the pool.</span></span> <span data-ttu-id="10aa2-108">Per informazioni dettagliate sul bilanciamento del carico DNS, vedere [DNS Load Balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="10aa2-108">For details about DNS Load Balancing, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) in the Planning documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="10aa2-109">Per il traffico HTTPS da client a server è ancora necessario utilizzare il bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="10aa2-109">Hardware load balancing is still required for client to server HTTPS traffic.</span></span>



</div>

<span data-ttu-id="10aa2-110">Prima di poter utilizzare il bilanciamento del carico DNS, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="10aa2-110">Before you can use DNS load balancing, you must do the following:</span></span>

1.  <span data-ttu-id="10aa2-111">Eseguire l'override del nome FQDN del pool di servizi Web interni.</span><span class="sxs-lookup"><span data-stu-id="10aa2-111">Override the internal Web Services pool FQDN.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="10aa2-112">Se si decide di sostituire i servizi Web interni con un FQDN autodefinito, ogni FQDN deve essere univoco da qualsiasi altro pool Front End, Director o pool di server Director.</span><span class="sxs-lookup"><span data-stu-id="10aa2-112">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

2.  <span data-ttu-id="10aa2-113">Creare record host A DNS per risolvere l'FQDN del pool negli indirizzi IP di tutti i server inclusi nel pool.</span><span class="sxs-lookup"><span data-stu-id="10aa2-113">Create DNS A host records to resolve the pool FQDN to the IP addresses of all the servers in the pool.</span></span>

3.  <span data-ttu-id="10aa2-114">Abilitare la sequenza casuale degli indirizzi IP oppure, per DNS di Windows Server, abilitare il round robin.</span><span class="sxs-lookup"><span data-stu-id="10aa2-114">Enable IP Address randomization or, for Windows Server DNS, enable round robin.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="10aa2-115">Il round robin è abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="10aa2-115">Round robin should be enabled by default.</span></span>

    
    </div>

<div>

## <a name="to-override-internal-web-services-fqdn"></a><span data-ttu-id="10aa2-116">Per sostituire l'FQDN dei servizi Web interni</span><span class="sxs-lookup"><span data-stu-id="10aa2-116">To override internal Web services FQDN</span></span>

1.  <span data-ttu-id="10aa2-117">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.</span><span class="sxs-lookup"><span data-stu-id="10aa2-117">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="10aa2-118">Nell'albero della console espandere il nodo Pool Enterprise Edition Front End.</span><span class="sxs-lookup"><span data-stu-id="10aa2-118">From the console tree, expand the Enterprise Edition Front End pools node.</span></span>

3.  <span data-ttu-id="10aa2-119">Fare clic con il pulsante destro del mouse sul pool, scegliere **Modifica proprietà** e quindi fare clic su **Servizi Web**.</span><span class="sxs-lookup"><span data-stu-id="10aa2-119">Right-click the pool, click **Edit Properties**, and then click **Web Services**.</span></span>

4.  <span data-ttu-id="10aa2-120">Sotto **Servizi Web interni** selezionare la casella di controllo **Sostituisci FQDN**.</span><span class="sxs-lookup"><span data-stu-id="10aa2-120">Below **Internal web services**, select the **Override FQDN** check box.</span></span>

5.  <span data-ttu-id="10aa2-121">Digitare l'FQDN del pool che viene risolto negli indirizzi IP fisici dei server del pool.</span><span class="sxs-lookup"><span data-stu-id="10aa2-121">Type the pool FQDN that resolves to the physical IP addresses of the servers in the pool.</span></span>

6.  <span data-ttu-id="10aa2-122">Sotto **Servizi Web esterni** digitare l'FQDN del pool esterno che viene risolto negli indirizzi IP virtuali del pool e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="10aa2-122">Below **External web services**, type the external pool FQDN that resolves to the virtual IP addresses of the pool, and then click **OK**.</span></span>

7.  <span data-ttu-id="10aa2-123">Nell'albero della console fare clic su **Lync Server 2013**e quindi nel riquadro **Azioni** fare clic su **Pubblica topologia**.</span><span class="sxs-lookup"><span data-stu-id="10aa2-123">From the console tree, click **Lync Server 2013**, and then in the **Actions** pane, click **Publish Topology**.</span></span>

</div>

<div>

## <a name="to-create-dns-host-a-records-for-all-internal-pool-servers"></a><span data-ttu-id="10aa2-124">Per creare i record host (A) DNS per tutti i server del pool interno</span><span class="sxs-lookup"><span data-stu-id="10aa2-124">To create DNS Host (A) Records for all internal pool servers</span></span>

1.  <span data-ttu-id="10aa2-125">Fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Strumenti di amministrazione** e quindi **DNS**.</span><span class="sxs-lookup"><span data-stu-id="10aa2-125">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="10aa2-126">In **Gestore DNS** fare clic sul server DNS che gestisce i record per espanderlo.</span><span class="sxs-lookup"><span data-stu-id="10aa2-126">In **DNS Manager**, click the DNS Server that manages your records to expand it.</span></span>

3.  <span data-ttu-id="10aa2-127">Fare clic sulla voce **Zone di ricerca diretta** per espanderla.</span><span class="sxs-lookup"><span data-stu-id="10aa2-127">Click **Forward Lookup Zones** to expand it.</span></span>

4.  <span data-ttu-id="10aa2-128">Fare clic con il pulsante destro del mouse sul dominio DNS a cui aggiungere i record e quindi scegliere **Nuovo host (A o AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="10aa2-128">Right-click the DNS domain that you need to add records to, and then click **New Host (A or AAAA)**.</span></span>

5.  <span data-ttu-id="10aa2-129">Nella casella **nome** Digitare il nome del record host (il nome di dominio verrà automaticamente accodato).</span><span class="sxs-lookup"><span data-stu-id="10aa2-129">In the **Name** box, type the name of the host record (the domain name will be automatically appended).</span></span>

6.  <span data-ttu-id="10aa2-130">Nella casella Indirizzo IP digitare l'indirizzo IP del singolo Front End Server e quindi selezionare **Crea record puntatore (PTR) associato** o **Consenti a tutti gli utenti autenticati di aggiornare i record DNS con lo stesso nome proprietario**, se applicabile.</span><span class="sxs-lookup"><span data-stu-id="10aa2-130">In the IP Address box, type the IP address of the individual Front End Server and then select **Create associated pointer (PTR) record** or **Allow any authenticated user to update DNS records with the same owner name**, if applicable.</span></span>

7.  <span data-ttu-id="10aa2-131">Continuare a creare i record per tutti i Front End Server membri che parteciperanno al bilanciamento del carico DNS.</span><span class="sxs-lookup"><span data-stu-id="10aa2-131">Continue creating records for all member Front End Servers that will participate in DNS Load Balancing.</span></span>
    
    <span data-ttu-id="10aa2-132">Se ad esempio si dispone di un pool denominato pool1.contoso.com e di tre Front End Server, sarà necessario creare le voci DNS seguenti:</span><span class="sxs-lookup"><span data-stu-id="10aa2-132">For example, if you had a pool named pool1.contoso.com and three Front End Servers, you would create the following DNS entries:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="10aa2-133">FQDN</span><span class="sxs-lookup"><span data-stu-id="10aa2-133">FQDN</span></span></th>
    <th><span data-ttu-id="10aa2-134">Tipo</span><span class="sxs-lookup"><span data-stu-id="10aa2-134">Type</span></span></th>
    <th><span data-ttu-id="10aa2-135">Dati</span><span class="sxs-lookup"><span data-stu-id="10aa2-135">Data</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="10aa2-136">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="10aa2-136">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="10aa2-137">Host (A)</span><span class="sxs-lookup"><span data-stu-id="10aa2-137">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="10aa2-138">192.168.1.1</span><span class="sxs-lookup"><span data-stu-id="10aa2-138">192.168.1.1</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="10aa2-139">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="10aa2-139">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="10aa2-140">Host (A)</span><span class="sxs-lookup"><span data-stu-id="10aa2-140">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="10aa2-141">192.168.1.2</span><span class="sxs-lookup"><span data-stu-id="10aa2-141">192.168.1.2</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="10aa2-142">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="10aa2-142">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="10aa2-143">Host (A)</span><span class="sxs-lookup"><span data-stu-id="10aa2-143">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="10aa2-144">192.168.1.3</span><span class="sxs-lookup"><span data-stu-id="10aa2-144">192.168.1.3</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="10aa2-145">Per informazioni dettagliate sulla creazione di record host DNS (A), vedere [configure DNS Host Records for Lync Server 2013](lync-server-2013-configure-dns-host-records.md).</span><span class="sxs-lookup"><span data-stu-id="10aa2-145">For details about creating DNS Host (A) records, see [Configure DNS Host records for Lync Server 2013](lync-server-2013-configure-dns-host-records.md).</span></span>

</div>

<div>

## <a name="to-enable-round-robin-for-windows-server"></a><span data-ttu-id="10aa2-146">Per abilitare il round robin per Windows Server</span><span class="sxs-lookup"><span data-stu-id="10aa2-146">To enable round robin for Windows Server</span></span>

1.  <span data-ttu-id="10aa2-147">Fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Strumenti di amministrazione** e quindi **DNS**.</span><span class="sxs-lookup"><span data-stu-id="10aa2-147">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="10aa2-148">Espandere **DNS**, fare clic con il pulsante destro del mouse sul server DNS che si desidera configurare e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="10aa2-148">Expand **DNS**, right-click the DNS server you want to configure, and then click **Properties**.</span></span>

3.  <span data-ttu-id="10aa2-149">Fare clic sulla scheda **Avanzate**, selezionare **Attiva round robin** e \*\*Attiva ordinamento netmask \*\* e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="10aa2-149">Click the **Advanced** tab, select **Enable round robin** and **Enable netmask ordering**, and then click **OK**.</span></span>
    
    <span data-ttu-id="10aa2-150">![Finestra di dialogo Round Robin DNS](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "Finestra di dialogo Round Robin DNS")</span><span class="sxs-lookup"><span data-stu-id="10aa2-150">![DNS Round Robin dialog box](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "DNS Round Robin dialog box")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="10aa2-151">Questa funzionalità è abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="10aa2-151">This feature should be enabled by default.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="10aa2-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10aa2-152">See Also</span></span>


[<span data-ttu-id="10aa2-153">Bilanciamento del carico DNS in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10aa2-153">DNS load balancing in Lync Server 2013</span></span>](lync-server-2013-dns-load-balancing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


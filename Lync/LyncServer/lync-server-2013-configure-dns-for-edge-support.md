---
title: 'Lync Server 2013: configurare DNS per il supporto di Edge'
description: 'Lync Server 2013: configurare DNS per il supporto di Edge.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS for edge support
ms:assetid: 955493e6-aa29-424d-bb81-1ef87b3b15e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398756(v=OCS.15)
ms:contentKeyID: 48184894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 706f4915adda58dbb72b8dd8921e0cc612833718
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555892"
---
# <a name="configure-dns-for-edge-support-in-lync-server-2013"></a><span data-ttu-id="38d8c-103">Configurare DNS per il supporto Edge in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38d8c-103">Configure DNS for edge support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38d8c-104">_**Ultimo argomento modificato:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="38d8c-104">_**Topic Last Modified:** 2013-02-15_</span></span>

<span data-ttu-id="38d8c-105">È necessario configurare record DNS (Domain Name System) per le interfacce perimetrali interne ed esterne, incluse le interfacce di server perimetrali e proxy inversi.</span><span class="sxs-lookup"><span data-stu-id="38d8c-105">You must configure Domain Name System (DNS) records for internal and external edge interfaces, including both Edge Server and reverse proxy interfaces.</span></span> <span data-ttu-id="38d8c-106">Per impostazione predefinita, i server perimetrali non vengono aggiunti a un dominio e non avranno un nome di dominio completo (Fully Qualified Domain Name).</span><span class="sxs-lookup"><span data-stu-id="38d8c-106">By default, Edge Servers are not joined to a domain and will not have a fully qualified domain name (fully qualified domain name).</span></span> <span data-ttu-id="38d8c-107">Il server perimetrale è denominato solo dal nome breve (computer) e non da un nome di dominio completo.</span><span class="sxs-lookup"><span data-stu-id="38d8c-107">The Edge Server is only referred to by the short (machine) name, not a fully qualified domain name.</span></span> <span data-ttu-id="38d8c-108">Tuttavia, il generatore di topologie utilizza FQDN e non nomi brevi.</span><span class="sxs-lookup"><span data-stu-id="38d8c-108">However, Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="38d8c-109">Il nome del server perimetrale deve corrispondere all'FQDN utilizzato dal generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="38d8c-109">The name of the Edge Server must match the FQDN used by Topology Builder.</span></span> <span data-ttu-id="38d8c-110">A tale scopo, è possibile definire un suffisso DNS che, se combinato con il nome del computer, comporta l'FQDN previsto.</span><span class="sxs-lookup"><span data-stu-id="38d8c-110">To do this, you define a DNS suffix that, when combined with the machine name, results in the expected FQDN.</span></span> <span data-ttu-id="38d8c-111">Utilizzare la procedura seguente in "per aggiungere il suffisso DNS al nome del computer nel server perimetrale che non è aggiunto a un dominio" per aggiungere il suffisso DNS al nome del computer.</span><span class="sxs-lookup"><span data-stu-id="38d8c-111">Use the following procedure in “To add the DNS suffix to the computer name on and Edge Server that is not joined to a domain” to add the DNS suffix to the computer name.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="38d8c-112">Per impostazione predefinita, il DNS utilizza un algoritmo round robin per ruotare l'ordine dei dati del record di risorse restituiti nelle risposte di query in cui sono presenti più record di risorse dello stesso tipo per un nome di dominio DNS sottoposto a query.</span><span class="sxs-lookup"><span data-stu-id="38d8c-112">By default, DNS uses a round robin algorithm to rotate the order of resource record data returned in query answers where multiple resource records of the same type exist for a queried DNS domain name.</span></span> <span data-ttu-id="38d8c-113">Il bilanciamento del carico DNS di Lync Server 2013 dipende dal Round Robin DNS come parte del meccanismo di bilanciamento del carico DNS.</span><span class="sxs-lookup"><span data-stu-id="38d8c-113">Lync Server 2013 DNS load balancing, depends on DNS round-robin as a part of the DNS Load Balancing mechanism.</span></span> <span data-ttu-id="38d8c-114">Verificare che l'impostazione Round Robin non sia stata disattivata.</span><span class="sxs-lookup"><span data-stu-id="38d8c-114">Verify that round-robin setting has not been disabled.</span></span> <span data-ttu-id="38d8c-115">Se si utilizza un server DNS che non esegue un sistema operativo Windows, verificare che l'ordinamento dei record di risorse Round Robin sia abilitato.</span><span class="sxs-lookup"><span data-stu-id="38d8c-115">If you are using a DNS server that is not running a Windows operating system, verify that round-robin resource record ordering is enabled.</span></span>



</div>

<span data-ttu-id="38d8c-116">Utilizzare le procedure seguenti in "**per creare un record DNS SRV**" per creare e verificare ogni record DNS SRV.</span><span class="sxs-lookup"><span data-stu-id="38d8c-116">Use the following procedures in “**To create a DNS SRV record**” to create and verify each DNS SRV record.</span></span> <span data-ttu-id="38d8c-117">Utilizzare la procedura descritta in "**per creare un record a DNS**" per definire i record DNS necessari per l'accesso degli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="38d8c-117">Use the procedure in “**To create a DNS A record**” to define the DNS A records required for external user access.</span></span> <span data-ttu-id="38d8c-118">Per verificare che i record siano configurati e funzionino correttamente, vedere la sezione relativa**alla verifica di un record DNS**in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="38d8c-118">To confirm that the records are configured and working correctly, see “**To verify a DNS record**” in this topic.</span></span> <span data-ttu-id="38d8c-119">Per informazioni dettagliate su ogni record necessario per supportare l'accesso degli utenti esterni, vedere [determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38d8c-119">For details about each record required to support external user access, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<div>

## <a name="to-add-the-dns-suffix-to-the-computer-name-on-an-edge-server-that-is-not-joined-to-a-domain"></a><span data-ttu-id="38d8c-120">Per aggiungere un suffisso DNS al nome del computer in un server perimetrale che non fa parte di un dominio</span><span class="sxs-lookup"><span data-stu-id="38d8c-120">To add the DNS suffix to the computer name on an Edge Server that is not joined to a domain</span></span>

1.  <span data-ttu-id="38d8c-121">Nel computer fare clic sul pulsante **Start**, fare clic con il pulsante destro del mouse su **Computer** e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="38d8c-121">On the computer, click **Start**, right-click **Computer**, and then click **Properties**.</span></span>

2.  <span data-ttu-id="38d8c-122">In **Impostazioni relative a nome computer, dominio e gruppo di lavoro** fare clic su **Cambia impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="38d8c-122">Under **Computer name, domain, and workgroup settings**, click **Change settings**.</span></span>

3.  <span data-ttu-id="38d8c-123">Nella scheda **Nome computer** fare clic su **Cambia**.</span><span class="sxs-lookup"><span data-stu-id="38d8c-123">On the **Computer Name** tab, click **Change**.</span></span>

4.  <span data-ttu-id="38d8c-124">In **Cambiamenti dominio/nome computer** fare clic su **Altro**.</span><span class="sxs-lookup"><span data-stu-id="38d8c-124">In **Computer Name/Domain Changes**, click **More**.</span></span>

5.  <span data-ttu-id="38d8c-125">In **Suffisso DNS e nome NetBIOS del computer** digitare il nome del dominio interno (ad esempio corp.contoso.com) in **Suffisso DNS primario del computer** e quindi fare clic su **OK** tre volte.</span><span class="sxs-lookup"><span data-stu-id="38d8c-125">In **DNS Suffix and NetBIOS Computer Name**, in **Primary DNS suffix of this computer**, type the name of your internal domain (for example, corp.contoso.com), and then click **OK** three times.</span></span>

6.  <span data-ttu-id="38d8c-126">Riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="38d8c-126">Restart the computer.</span></span>

</div>

<div>

## <a name="to-create-a-dns-srv-record"></a><span data-ttu-id="38d8c-127">Per creare un record SRV DNS</span><span class="sxs-lookup"><span data-stu-id="38d8c-127">To create a DNS SRV record</span></span>

1.  <span data-ttu-id="38d8c-128">Nel server DNS appropriato fare clic sul pulsante **Start**, scegliere **Pannello di controllo**, **Strumenti di amministrazione** e quindi **DNS**.</span><span class="sxs-lookup"><span data-stu-id="38d8c-128">On the appropriate DNS server, click **Start**, click **Control Panel**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="38d8c-129">È necessario configurare DNS in modo che vi siano: 1) voci DNS esterne per le ricerche DNS esterne da parte degli utenti remoti e dei partner federati; 2) le voci per le ricerche DNS per l'utilizzo da parte dei server perimetrali all'interno della rete (noto anche come DMZ, area demilitarizzata e subnet schermata), inclusi i record per i server interni che eseguono Lync Server 2013; e 3) le voci DNS interne per le ricerche eseguite dai client e dai server interni che eseguono Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="38d8c-129">You need to configure DNS so that there are: 1) external DNS entries for external DNS lookups by remote users and federated partners; 2) entries for DNS lookups for use by the Edge Servers within the perimeter network (also known as DMZ, demilitarized zone, and screened subnet), including A records for the internal servers running Lync Server 2013; and 3) internal DNS entries for lookups by the internal clients and servers running Lync Server 2013.</span></span>

    
    </div>

2.  <span data-ttu-id="38d8c-130">Nell'albero della console per il dominio SIP espandere **zone di ricerca diretta**e quindi fare clic con il pulsante destro del mouse sul dominio in cui è installato Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="38d8c-130">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the domain where Lync Server 2013 is installed.</span></span>

3.  <span data-ttu-id="38d8c-131">Scegliere **Altri nuovi record**.</span><span class="sxs-lookup"><span data-stu-id="38d8c-131">Click **Other New Records**.</span></span>

4.  <span data-ttu-id="38d8c-132">In **Selezionare tipo di record di risorsa** digitare **Posizione servizio (SRV)** e quindi su fare clic su **Crea record**.</span><span class="sxs-lookup"><span data-stu-id="38d8c-132">In **Select a resource record type**, type **Service Location (SRV)**, and then click **Create Record**.</span></span>

5.  <span data-ttu-id="38d8c-133">Specificare tutte le informazioni necessarie per il record SRV DNS.</span><span class="sxs-lookup"><span data-stu-id="38d8c-133">Provide all required information for the DNS SRV record.</span></span>

</div>

<div>

## <a name="to-create-a-dns-a-record"></a><span data-ttu-id="38d8c-134">Per creare un record A DNS</span><span class="sxs-lookup"><span data-stu-id="38d8c-134">To create a DNS A record</span></span>

1.  <span data-ttu-id="38d8c-135">Nel server DNS fare clic sul pulsante **Start**, scegliere **Pannello di controllo**, **Strumenti di amministrazione** e quindi **DNS**.</span><span class="sxs-lookup"><span data-stu-id="38d8c-135">On the DNS server, click **Start**, click **Control Panel**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="38d8c-136">Nell'albero della console per il dominio SIP espandere **zone di ricerca diretta**e quindi fare clic con il pulsante destro del mouse sul dominio in cui è installato Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="38d8c-136">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 is installed.</span></span>

3.  <span data-ttu-id="38d8c-137">Scegliere **Nuovo host (A o AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="38d8c-137">Click **New Host (A)**.</span></span>

4.  <span data-ttu-id="38d8c-138">Specificare tutte le informazioni necessarie per il record SRV DNS.</span><span class="sxs-lookup"><span data-stu-id="38d8c-138">Provide all required information for the DNS SRV record.</span></span>

</div>

<div>

## <a name="to-verify-a-dns-record"></a><span data-ttu-id="38d8c-139">Per verificare un record DNS</span><span class="sxs-lookup"><span data-stu-id="38d8c-139">To verify a DNS record</span></span>

1.  <span data-ttu-id="38d8c-140">Accedere a un computer client nel dominio.</span><span class="sxs-lookup"><span data-stu-id="38d8c-140">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="38d8c-141">Fare clic sul pulsante **Start** e quindi scegliere **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="38d8c-141">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="38d8c-142">Al prompt dei comandi eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="38d8c-142">At the command prompt, run the following command:</span></span>
    
        nslookup <FQDN edge interface>

4.  <span data-ttu-id="38d8c-143">Verificare che la risposta ricevuta venga risolta nell'indirizzo IP appropriato per l'FQDN.</span><span class="sxs-lookup"><span data-stu-id="38d8c-143">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="38d8c-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38d8c-144">See Also</span></span>


[<span data-ttu-id="38d8c-145">Creare un record DNS SRV per l'integrazione con la messaggistica unificata di Exchange ospitata</span><span class="sxs-lookup"><span data-stu-id="38d8c-145">Create a DNS SRV record for integration with hosted Exchange UM</span></span>](lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md)  


[<span data-ttu-id="38d8c-146">Determinare i requisiti DNS per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38d8c-146">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


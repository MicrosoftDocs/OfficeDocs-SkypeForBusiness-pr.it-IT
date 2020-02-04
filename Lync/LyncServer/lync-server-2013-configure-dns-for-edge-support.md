---
title: 'Lync Server 2013: Configurare DNS per il supporto dei componenti perimetrali'
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
ms.openlocfilehash: c905c8fff7a67b26a7df8d2c741ce0a16fddce6c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757900"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-edge-support-in-lync-server-2013"></a><span data-ttu-id="37596-102">Configurare DNS per il supporto dei componenti perimetrali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37596-102">Configure DNS for edge support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37596-103">_**Argomento Ultima modifica:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="37596-103">_**Topic Last Modified:** 2013-02-15_</span></span>

<span data-ttu-id="37596-104">È necessario configurare i record DNS (Domain Name System) per le interfacce di Edge interne ed esterne, tra cui le interfacce Edge Server e proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="37596-104">You must configure Domain Name System (DNS) records for internal and external edge interfaces, including both Edge Server and reverse proxy interfaces.</span></span> <span data-ttu-id="37596-105">Per impostazione predefinita, i server perimetrali non vengono uniti a un dominio e non avranno un nome di dominio completo (nome di dominio completo).</span><span class="sxs-lookup"><span data-stu-id="37596-105">By default, Edge Servers are not joined to a domain and will not have a fully qualified domain name (fully qualified domain name).</span></span> <span data-ttu-id="37596-106">Il server perimetrale viene indicato solo dal nome short (computer), non da un nome di dominio completo.</span><span class="sxs-lookup"><span data-stu-id="37596-106">The Edge Server is only referred to by the short (machine) name, not a fully qualified domain name.</span></span> <span data-ttu-id="37596-107">Tuttavia, generatore di topologie usa nomi di dominio completi, non brevi.</span><span class="sxs-lookup"><span data-stu-id="37596-107">However, Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="37596-108">Il nome del server perimetrale deve corrispondere all'FQDN usato da generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="37596-108">The name of the Edge Server must match the FQDN used by Topology Builder.</span></span> <span data-ttu-id="37596-109">A questo scopo, devi definire un suffisso DNS che, se combinato con il nome del computer, restituisce l'FQDN previsto.</span><span class="sxs-lookup"><span data-stu-id="37596-109">To do this, you define a DNS suffix that, when combined with the machine name, results in the expected FQDN.</span></span> <span data-ttu-id="37596-110">Usare la procedura seguente in "per aggiungere il suffisso DNS al nome del computer in e Edge Server che non è stato aggiunto a un dominio" per aggiungere il suffisso DNS al nome del computer.</span><span class="sxs-lookup"><span data-stu-id="37596-110">Use the following procedure in “To add the DNS suffix to the computer name on and Edge Server that is not joined to a domain” to add the DNS suffix to the computer name.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="37596-111">Per impostazione predefinita, il DNS usa un algoritmo round robin per ruotare l'ordine dei dati del record di risorse restituiti nelle risposte alle query in cui sono presenti più record di risorse dello stesso tipo per un nome di dominio DNS interrogato.</span><span class="sxs-lookup"><span data-stu-id="37596-111">By default, DNS uses a round robin algorithm to rotate the order of resource record data returned in query answers where multiple resource records of the same type exist for a queried DNS domain name.</span></span> <span data-ttu-id="37596-112">Il bilanciamento del carico DNS di Lync Server 2013 dipende dal DNS round-robin come parte del meccanismo di bilanciamento del carico DNS.</span><span class="sxs-lookup"><span data-stu-id="37596-112">Lync Server 2013 DNS load balancing, depends on DNS round-robin as a part of the DNS Load Balancing mechanism.</span></span> <span data-ttu-id="37596-113">Verificare che l'impostazione Round Robin non sia stata disattivata.</span><span class="sxs-lookup"><span data-stu-id="37596-113">Verify that round-robin setting has not been disabled.</span></span> <span data-ttu-id="37596-114">Se si usa un server DNS che non esegue un sistema operativo Windows, verificare che l'ordinamento dei record di risorse Round Robin sia abilitato.</span><span class="sxs-lookup"><span data-stu-id="37596-114">If you are using a DNS server that is not running a Windows operating system, verify that round-robin resource record ordering is enabled.</span></span>



</div>

<span data-ttu-id="37596-115">Usare le procedure seguenti in "**per creare un record SRV DNS**" per creare e verificare ogni record SRV DNS.</span><span class="sxs-lookup"><span data-stu-id="37596-115">Use the following procedures in “**To create a DNS SRV record**” to create and verify each DNS SRV record.</span></span> <span data-ttu-id="37596-116">Usare la procedura descritta in "**per creare un record DNS**" per definire i record DNS necessari per l'accesso degli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="37596-116">Use the procedure in “**To create a DNS A record**” to define the DNS A records required for external user access.</span></span> <span data-ttu-id="37596-117">Per verificare che i record siano configurati e funzioni correttamente, vedere la sezione relativa**alla verifica di un record DNS**in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="37596-117">To confirm that the records are configured and working correctly, see “**To verify a DNS record**” in this topic.</span></span> <span data-ttu-id="37596-118">Per informazioni dettagliate su ogni record necessario per supportare l'accesso degli utenti esterni, vedere [determinare i requisiti DNS per Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37596-118">For details about each record required to support external user access, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<div>

## <a name="to-add-the-dns-suffix-to-the-computer-name-on-an-edge-server-that-is-not-joined-to-a-domain"></a><span data-ttu-id="37596-119">Per aggiungere il suffisso DNS al nome del computer in un server perimetrale che non è stato aggiunto a un dominio</span><span class="sxs-lookup"><span data-stu-id="37596-119">To add the DNS suffix to the computer name on an Edge Server that is not joined to a domain</span></span>

1.  <span data-ttu-id="37596-120">Nel computer fare clic su **Start**, fare clic con il pulsante destro del mouse su **computer**e quindi scegliere **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="37596-120">On the computer, click **Start**, right-click **Computer**, and then click **Properties**.</span></span>

2.  <span data-ttu-id="37596-121">In **Impostazioni nome computer, dominio e gruppo**di lavoro fare clic su **Cambia impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="37596-121">Under **Computer name, domain, and workgroup settings**, click **Change settings**.</span></span>

3.  <span data-ttu-id="37596-122">Nella scheda **nome computer** fare clic su **Cambia**.</span><span class="sxs-lookup"><span data-stu-id="37596-122">On the **Computer Name** tab, click **Change**.</span></span>

4.  <span data-ttu-id="37596-123">In **nome computer/Domain Changes**fare clic su **altro**.</span><span class="sxs-lookup"><span data-stu-id="37596-123">In **Computer Name/Domain Changes**, click **More**.</span></span>

5.  <span data-ttu-id="37596-124">In **suffisso DNS e nome computer NetBIOS**, in **suffisso DNS primario del computer**, digitare il nome del dominio interno, ad esempio Corp.contoso.com, e quindi fare clic su **OK** tre volte.</span><span class="sxs-lookup"><span data-stu-id="37596-124">In **DNS Suffix and NetBIOS Computer Name**, in **Primary DNS suffix of this computer**, type the name of your internal domain (for example, corp.contoso.com), and then click **OK** three times.</span></span>

6.  <span data-ttu-id="37596-125">Riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="37596-125">Restart the computer.</span></span>

</div>

<div>

## <a name="to-create-a-dns-srv-record"></a><span data-ttu-id="37596-126">Per creare un record SRV DNS</span><span class="sxs-lookup"><span data-stu-id="37596-126">To create a DNS SRV record</span></span>

1.  <span data-ttu-id="37596-127">Nel server DNS appropriato fare clic sul pulsante **Start**, scegliere **Pannello di controllo**, strumenti di **Amministrazione**e quindi fare clic su **DNS**.</span><span class="sxs-lookup"><span data-stu-id="37596-127">On the appropriate DNS server, click **Start**, click **Control Panel**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="37596-128">È necessario configurare il DNS in modo che siano presenti: 1) voci DNS esterne per le ricerche DNS esterne da parte di utenti remoti e partner federati; 2) le voci per le ricerche DNS per l'uso da parte di Edge Server all'interno della rete perimetrale (nota anche come DMZ, zona demilitarizzata e subnet schermata), inclusi i record per i server interni che usano Lync Server 2013; e 3) voci DNS interne per le ricerche dei client e dei server interni che utilizzano Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="37596-128">You need to configure DNS so that there are: 1) external DNS entries for external DNS lookups by remote users and federated partners; 2) entries for DNS lookups for use by the Edge Servers within the perimeter network (also known as DMZ, demilitarized zone, and screened subnet), including A records for the internal servers running Lync Server 2013; and 3) internal DNS entries for lookups by the internal clients and servers running Lync Server 2013.</span></span>

    
    </div>

2.  <span data-ttu-id="37596-129">Nell'albero della console per il dominio SIP espandere **aree di ricerca in avanti**e quindi fare clic con il pulsante destro del mouse sul dominio in cui è installato Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="37596-129">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the domain where Lync Server 2013 is installed.</span></span>

3.  <span data-ttu-id="37596-130">Fare clic su **altri nuovi record**.</span><span class="sxs-lookup"><span data-stu-id="37596-130">Click **Other New Records**.</span></span>

4.  <span data-ttu-id="37596-131">In **selezionare un tipo di record di risorse**digitare **posizione servizio (SRV)** e quindi fare clic su **Crea record**.</span><span class="sxs-lookup"><span data-stu-id="37596-131">In **Select a resource record type**, type **Service Location (SRV)**, and then click **Create Record**.</span></span>

5.  <span data-ttu-id="37596-132">Fornisci tutte le informazioni necessarie per il record SRV DNS.</span><span class="sxs-lookup"><span data-stu-id="37596-132">Provide all required information for the DNS SRV record.</span></span>

</div>

<div>

## <a name="to-create-a-dns-a-record"></a><span data-ttu-id="37596-133">Per creare un record DNS</span><span class="sxs-lookup"><span data-stu-id="37596-133">To create a DNS A record</span></span>

1.  <span data-ttu-id="37596-134">Nel server DNS fare clic sul pulsante **Start**, scegliere **Pannello di controllo**, strumenti di **Amministrazione**e quindi fare clic su **DNS**.</span><span class="sxs-lookup"><span data-stu-id="37596-134">On the DNS server, click **Start**, click **Control Panel**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="37596-135">Nell'albero della console per il dominio SIP espandere **aree di ricerca in avanti**e quindi fare clic con il pulsante destro del mouse sul dominio in cui è installato Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="37596-135">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 is installed.</span></span>

3.  <span data-ttu-id="37596-136">Fare clic su **nuovo host (A)**.</span><span class="sxs-lookup"><span data-stu-id="37596-136">Click **New Host (A)**.</span></span>

4.  <span data-ttu-id="37596-137">Fornisci tutte le informazioni necessarie per il record SRV DNS.</span><span class="sxs-lookup"><span data-stu-id="37596-137">Provide all required information for the DNS SRV record.</span></span>

</div>

<div>

## <a name="to-verify-a-dns-record"></a><span data-ttu-id="37596-138">Per verificare un record DNS</span><span class="sxs-lookup"><span data-stu-id="37596-138">To verify a DNS record</span></span>

1.  <span data-ttu-id="37596-139">Accedere a un computer client nel dominio.</span><span class="sxs-lookup"><span data-stu-id="37596-139">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="37596-140">Fare clic sul pulsante **Start**e quindi su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="37596-140">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="37596-141">Al prompt dei comandi eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="37596-141">At the command prompt, run the following command:</span></span>
    
        nslookup <FQDN edge interface>

4.  <span data-ttu-id="37596-142">Verificare di ricevere una risposta che venga risolta nell'indirizzo IP appropriato per il nome di dominio completo.</span><span class="sxs-lookup"><span data-stu-id="37596-142">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="37596-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="37596-143">See Also</span></span>


[<span data-ttu-id="37596-144">Creare un Record DNS SRV per l'integrazione con la messaggistica unificata di Exchange ospitata</span><span class="sxs-lookup"><span data-stu-id="37596-144">Create a DNS SRV record for integration with hosted Exchange UM</span></span>](lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md)  


[<span data-ttu-id="37596-145">Determinare i requisiti di DNS per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37596-145">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


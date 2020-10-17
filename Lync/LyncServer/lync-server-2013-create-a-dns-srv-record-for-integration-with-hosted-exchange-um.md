---
title: Creare un record DNS SRV per l'integrazione con la messaggistica unificata di Exchange ospitata
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a DNS SRV record for integration with hosted Exchange UM
ms:assetid: 8ea590ae-58ea-4ca5-9853-e0708b3ea760
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh500728(v=OCS.15)
ms:contentKeyID: 48184770
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac215b5a0ba42ff031962e656e72fb355a808bf4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507473"
---
# <a name="create-a-dns-srv-record-for-integration-with-hosted-exchange-um"></a><span data-ttu-id="8d23a-102">Creare un record DNS SRV per l'integrazione con la messaggistica unificata di Exchange ospitata</span><span class="sxs-lookup"><span data-stu-id="8d23a-102">Create a DNS SRV record for integration with hosted Exchange UM</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d23a-103">_**Ultimo argomento modificato:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="8d23a-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="8d23a-104">In questo argomento viene descritto come configurare il record DNS (Domain Name System) SRV necessario per un server perimetrale di Lync Server 2013 per il routing a un servizio di Exchange ospitato, ad esempio Microsoft Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8d23a-104">This topic describes how to configure the Domain Name System (DNS) SRV record that is required for a Lync Server 2013 Edge Server to route to a hosted Exchange service such as Microsoft Exchange Online.</span></span>

<div>

## <a name="to-create-an-external-dns-srv-record-for-the-hosted-exchange-service"></a><span data-ttu-id="8d23a-105">Per creare un record DNS SRV esterno per il servizio di Exchange ospitato</span><span class="sxs-lookup"><span data-stu-id="8d23a-105">To create an external DNS SRV record for the hosted Exchange service</span></span>

1.  <span data-ttu-id="8d23a-106">Accedere al DNS esterno come membro del gruppo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="8d23a-106">Log on to the external DNS server as a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="8d23a-107">Fare clic sul pulsante **Start**, scegliere **Strumenti di amministrazione** e quindi **DNS**.</span><span class="sxs-lookup"><span data-stu-id="8d23a-107">Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="8d23a-108">Nell'albero della console per il dominio SIP espandere **zone di ricerca diretta**e selezionare il dominio SIP in cui verrà installato Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8d23a-108">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and select the SIP domain in which Lync Server 2013 will be installed.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="8d23a-p101">È necessario creare il record DNS SRV nel dominio SIP in cui Lync Server è o verrà installato. Quando si crea il record SRV, l'FQDN utilizzato per il campo Host che offre questo servizio deve essere l'FQDN esterno del pool di server perimetrali. Ad esempio, se l'FQDN esterno del pool di server perimetrali è edge01.contoso.net, immettere tale valore. Deve inoltre trovarsi nello stesso dominio del record DNS degli host (A).</span><span class="sxs-lookup"><span data-stu-id="8d23a-p101">You must create the DNS SRV record in the SIP domain in which Lync Server is or will be installed. When you create the SRV record, the FQDN used for the Host offering this service field must be the external FQDN of the Edge pool. For example, if the external FQDN of your Edge pool is edge01.contoso.net, enter that value. This must also be in the same domain as the DNS Hosts (A) record.</span></span>

    
    </div>

4.  <span data-ttu-id="8d23a-113">Fare clic con il pulsante destro del mouse sul dominio selezionato e quindi scegliere **Altri nuovi record**.</span><span class="sxs-lookup"><span data-stu-id="8d23a-113">Right-click the selected domain, and then click **Other New Records**.</span></span>

5.  <span data-ttu-id="8d23a-114">In **Tipo record di risorse** fare clic su **Posizione servizio (SRV)**, quindi su **Crea record**.</span><span class="sxs-lookup"><span data-stu-id="8d23a-114">In **Resource Record Type**, click **Service Location (SRV)**, and then click **Create Record**.</span></span>

6.  <span data-ttu-id="8d23a-115">In **nuovo record di risorse**fare clic su **servizio**e quindi digitare \*\* \_ sipfederationtls\*\*.</span><span class="sxs-lookup"><span data-stu-id="8d23a-115">In **New Resource Record**, click **Service**, and then type **\_sipfederationtls**.</span></span>

7.  <span data-ttu-id="8d23a-116">Fare clic su **protocollo**e quindi digitare \*\* \_ TCP\*\*.</span><span class="sxs-lookup"><span data-stu-id="8d23a-116">Click **Protocol**, and then type **\_tcp**.</span></span>

8.  <span data-ttu-id="8d23a-117">Fare clic su **Numero porta** e quindi digitare **5061**.</span><span class="sxs-lookup"><span data-stu-id="8d23a-117">Click **Port Number**, and then type **5061**.</span></span>

9.  <span data-ttu-id="8d23a-118">Fare clic su **host che offre questo servizio**e quindi digitare il nome di dominio completo (FQDN) del pool di Edge di lync Server 2013 che consente di accedere al sistema lync Server 2013 per i client esterni attendibili.</span><span class="sxs-lookup"><span data-stu-id="8d23a-118">Click **Host offering this service**, and then type the fully qualified domain name (FQDN) of the Lync Server 2013 Edge pool that provides access to your Lync Server 2013 system for trusted external clients.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="8d23a-119">È inoltre necessario configurare il dominio come autorevole e accettato nelle impostazioni di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8d23a-119">The domain must also be set up as an authoritative, accepted domain in your Exchange Online settings.</span></span> <span data-ttu-id="8d23a-120">Per informazioni dettagliate, vedere Create Accepted Domains at <A href="https://go.microsoft.com/fwlink/p/?linkid=229762">https://go.microsoft.com/fwlink/p/?linkId=229762</A> .</span><span class="sxs-lookup"><span data-stu-id="8d23a-120">For details, see Create Accepted Domains at <A href="https://go.microsoft.com/fwlink/p/?linkid=229762">https://go.microsoft.com/fwlink/p/?linkId=229762</A>.</span></span>

    
    </div>

10. <span data-ttu-id="8d23a-121">Scegliere **OK**, quindi su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="8d23a-121">Click **OK**, and then click **Done**.</span></span>

</div>

<div>

## <a name="to-verify-that-the-dns-srv-record-was-created-successfully"></a><span data-ttu-id="8d23a-122">Per verificare che il record DNS SRV sia stato creato correttamente</span><span class="sxs-lookup"><span data-stu-id="8d23a-122">To verify that the DNS SRV record was created successfully</span></span>

1.  <span data-ttu-id="8d23a-123">Accedere a un computer client nel dominio.</span><span class="sxs-lookup"><span data-stu-id="8d23a-123">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="8d23a-124">Fare clic sul pulsante **Start** e quindi scegliere **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="8d23a-124">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="8d23a-125">Al prompt dei comandi eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="8d23a-125">At the command prompt, run the following command:</span></span>
    
        nslookup <FQDN Lync Edge Pool>

4.  <span data-ttu-id="8d23a-126">Verificare che la risposta ricevuta venga risolta nell'indirizzo IP appropriato per l'FQDN.</span><span class="sxs-lookup"><span data-stu-id="8d23a-126">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8d23a-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d23a-127">See Also</span></span>


[<span data-ttu-id="8d23a-128">Creare record DNS per i server proxy inversi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d23a-128">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


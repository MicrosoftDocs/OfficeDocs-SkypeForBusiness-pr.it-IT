---
title: 'Lync Server 2013: Creare e verificare record DNS SRV'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create and verify DNS SRV records
ms:assetid: 86888c7e-1401-458f-9a7b-08ac726deeec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398680(v=OCS.15)
ms:contentKeyID: 48184714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a539b58abbad323aaf7c7343b40eabb49d04d91
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982012"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-and-verify-dns-srv-records-in-lync-server-2013"></a><span data-ttu-id="0911e-102">Creare e verificare record DNS SRV in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0911e-102">Create and verify DNS SRV records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0911e-103">_**Argomento Ultima modifica:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="0911e-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="0911e-104">Per completare correttamente questa procedura, è necessario avere effettuato l'accesso al server o al dominio come membro del gruppo Domain Admins o di un membro del gruppo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="0911e-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="0911e-105">Questo argomento descrive come configurare i record DNS (Domain Name System) necessari per la creazione nelle distribuzioni di Lync Server 2013 e quelle necessarie per l'accesso automatico del client.</span><span class="sxs-lookup"><span data-stu-id="0911e-105">This topic describes how to configure the Domain Name System (DNS) records that you are required to create in Lync Server 2013 deployments and those required for automatic client sign in.</span></span> <span data-ttu-id="0911e-106">Quando si crea un pool Front-End, il programma di installazione crea oggetti e impostazioni di Active Directory per il pool, incluso il nome di dominio completo (FQDN) del pool.</span><span class="sxs-lookup"><span data-stu-id="0911e-106">When you create a Front End pool, Setup creates Active Directory objects and settings for the pool, including the pool fully qualified domain name (FQDN).</span></span> <span data-ttu-id="0911e-107">Gli oggetti e le impostazioni simili vengono creati per un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="0911e-107">Similar objects and settings are created for a Standard Edition server.</span></span> <span data-ttu-id="0911e-108">Per consentire ai client di connettersi al pool o al server Standard Edition, il nome di dominio completo del pool o del server Standard Edition deve essere registrato in DNS.</span><span class="sxs-lookup"><span data-stu-id="0911e-108">For clients to be able to connect to the pool or Standard Edition server, the FQDN of the pool or Standard Edition server must be registered in DNS.</span></span> <span data-ttu-id="0911e-109">È necessario creare record SRV DNS nel DNS interno per ogni dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="0911e-109">You must create DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="0911e-110">Questa procedura presuppone che il DNS interno disponga di aree per i domini utente SIP.</span><span class="sxs-lookup"><span data-stu-id="0911e-110">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<div>

## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="0911e-111">Per configurare un record SRV DNS</span><span class="sxs-lookup"><span data-stu-id="0911e-111">To configure a DNS SRV record</span></span>

1.  <span data-ttu-id="0911e-112">Nel server DNS fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi fare clic su **DNS**.</span><span class="sxs-lookup"><span data-stu-id="0911e-112">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="0911e-113">Nell'albero della console per il dominio SIP espandere **aree di ricerca in avanti**e quindi fare clic con il pulsante destro del mouse sul dominio SIP in cui verrà installato Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0911e-113">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the SIP domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="0911e-114">Fare clic su **altri nuovi record**.</span><span class="sxs-lookup"><span data-stu-id="0911e-114">Click **Other New Records**.</span></span>

4.  <span data-ttu-id="0911e-115">In **selezionare un tipo di record delle risorse**fare clic su **posizione servizio (SRV)** e quindi su **Crea record**.</span><span class="sxs-lookup"><span data-stu-id="0911e-115">In **Select a resource record type**, click **Service Location (SRV)**, and then click **Create Record**.</span></span>

5.  <span data-ttu-id="0911e-116">Fare clic su **servizio**e quindi digitare \*\* \_sipinternaltls\*\*.</span><span class="sxs-lookup"><span data-stu-id="0911e-116">Click **Service**, and then type **\_sipinternaltls**.</span></span>

6.  <span data-ttu-id="0911e-117">Fare clic su **protocollo**e quindi digitare \*\* \_TCP\*\*.</span><span class="sxs-lookup"><span data-stu-id="0911e-117">Click **Protocol**, and then type **\_tcp**.</span></span>

7.  <span data-ttu-id="0911e-118">Fare clic su **numero di porta**e quindi digitare **5061**.</span><span class="sxs-lookup"><span data-stu-id="0911e-118">Click **Port Number**, and then type **5061**.</span></span>

8.  <span data-ttu-id="0911e-119">Fare clic su **host che offre questo servizio**e quindi digitare il nome di dominio completo del pool o del server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="0911e-119">Click **Host offering this service**, and then type the FQDN of the pool or Standard Edition server.</span></span>

9.  <span data-ttu-id="0911e-120">Fare clic su **OK**e quindi su **fine**.</span><span class="sxs-lookup"><span data-stu-id="0911e-120">Click **OK**, and then click **Done**.</span></span>

</div>

<div>

## <a name="to-verify-the-creation-of-a-dns-srv-record"></a><span data-ttu-id="0911e-121">Per verificare la creazione di un record SRV DNS</span><span class="sxs-lookup"><span data-stu-id="0911e-121">To verify the creation of a DNS SRV record</span></span>

1.  <span data-ttu-id="0911e-122">Accedere a un computer client nel dominio con un account membro del gruppo Authenticated Users o con autorizzazioni equivalenti.</span><span class="sxs-lookup"><span data-stu-id="0911e-122">Log on to a client computer in the domain with an account that is a member of the Authenticated Users group or has equivalent permissions.</span></span>

2.  <span data-ttu-id="0911e-123">Fare clic sul pulsante **Start**e quindi su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="0911e-123">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="0911e-124">Nella casella **Apri** Digitare **cmd**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0911e-124">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="0911e-125">Al prompt dei comandi digitare **nslookup**e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="0911e-125">At the command prompt, type **nslookup**, and then press ENTER.</span></span>

5.  <span data-ttu-id="0911e-126">Digitare **set type = srv**e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="0911e-126">Type **set type=srv**, and then press ENTER.</span></span>

6.  <span data-ttu-id="0911e-127">Digitare \*\* \_sipinternaltls.\_ tcp.contoso.com\*\*e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="0911e-127">Type **\_sipinternaltls.\_tcp.contoso.com**, and then press ENTER.</span></span> <span data-ttu-id="0911e-128">L'output visualizzato per il record TLS (Transport Layer Security) è il seguente:</span><span class="sxs-lookup"><span data-stu-id="0911e-128">The output displayed for the Transport Layer Security (TLS) record is as follows:</span></span>
    
    <span data-ttu-id="0911e-129">Server: \<DNS server\>. contoso.com</span><span class="sxs-lookup"><span data-stu-id="0911e-129">Server: \<dns server\>.contoso.com</span></span>
    
    <span data-ttu-id="0911e-130">Indirizzo: \<indirizzo IP del server DNS\></span><span class="sxs-lookup"><span data-stu-id="0911e-130">Address: \<IP address of DNS server\></span></span>
    
    <span data-ttu-id="0911e-131">Risposta non autorevole:</span><span class="sxs-lookup"><span data-stu-id="0911e-131">Non-authoritative answer:</span></span>
    
    <span data-ttu-id="0911e-132">\_sipinternaltls. \_posizione del servizio SRV di TCP.contoso.com:</span><span class="sxs-lookup"><span data-stu-id="0911e-132">\_sipinternaltls.\_tcp.contoso.com SRV service location:</span></span>
    
    <span data-ttu-id="0911e-133">Priority = 0</span><span class="sxs-lookup"><span data-stu-id="0911e-133">priority = 0</span></span>
    
    <span data-ttu-id="0911e-134">Peso = 0</span><span class="sxs-lookup"><span data-stu-id="0911e-134">weight = 0</span></span>
    
    <span data-ttu-id="0911e-135">porta = 5061</span><span class="sxs-lookup"><span data-stu-id="0911e-135">port = 5061</span></span>
    
    <span data-ttu-id="0911e-136">svr hostname = poolname.contoso.com (o Standard Edition Server A record)</span><span class="sxs-lookup"><span data-stu-id="0911e-136">svr hostname = poolname.contoso.com (or Standard Edition server A record)</span></span>
    
    <span data-ttu-id="0911e-137">Indirizzo Internet poolname.contoso.com = \<indirizzo IP virtuale del bilanciamento del\> carico o \<dell'indirizzo IP di un singolo server Enterprise Edition per i pool con un solo server\> Enterprise o \<un indirizzo IP del server Standard Edition\></span><span class="sxs-lookup"><span data-stu-id="0911e-137">poolname.contoso.com internet address = \<virtual IP Address of the load balancer\> or \<IP address of a single Enterprise Edition server for pools with only one Enterprise Edition server\> or \<IP address of the Standard Edition server\></span></span>

7.  <span data-ttu-id="0911e-138">Al termine, al prompt dei comandi digitare **Exit**e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="0911e-138">When you are finished, at the command prompt, type **exit**, and then press ENTER.</span></span>

</div>

<div>

## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="0911e-139">Per verificare che il nome di dominio completo del pool Front-end o del server Standard Edition possa essere risolto</span><span class="sxs-lookup"><span data-stu-id="0911e-139">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1.  <span data-ttu-id="0911e-140">Accedere a un computer client nel dominio.</span><span class="sxs-lookup"><span data-stu-id="0911e-140">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="0911e-141">Fare clic sul pulsante **Start**e quindi su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="0911e-141">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="0911e-142">Nella casella **Apri** Digitare **cmd**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0911e-142">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="0911e-143">Al prompt dei comandi digitare il nome di dominio completo **nslookup** \<del pool\> di \<front end o il nome di\>dominio completo del server Standard Edition, quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="0911e-143">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="0911e-144">Verificare di ricevere una risposta che venga risolta nell'indirizzo IP appropriato per il nome di dominio completo.</span><span class="sxs-lookup"><span data-stu-id="0911e-144">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


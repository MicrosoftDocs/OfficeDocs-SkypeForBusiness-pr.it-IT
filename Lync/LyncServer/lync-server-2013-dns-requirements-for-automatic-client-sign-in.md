---
title: "Lync Server 2013: requisiti DNS per l'accesso automatico dei client"
description: "Lync Server 2013: requisiti DNS per l'accesso automatico dei client."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for automatic client sign-in
ms:assetid: 3bcd4bb3-a022-4ffa-b005-1a95ad2b1796
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425884(v=OCS.15)
ms:contentKeyID: 48183873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2247c955e0a563a22fb5d0ec20735291a836cdfc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574372"
---
# <a name="dns-requirements-for-automatic-client-sign-in-in-lync-server-2013"></a><span data-ttu-id="3b66a-103">Requisiti DNS per l'accesso automatico dei client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b66a-103">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b66a-104">_**Ultimo argomento modificato:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="3b66a-104">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="3b66a-105">In questa sezione vengono descritti i record DNS (Domain Name System) necessari per l'accesso client automatico.</span><span class="sxs-lookup"><span data-stu-id="3b66a-105">This section explains the Domain Name System (DNS) records that are required for automatic client sign-in.</span></span> <span data-ttu-id="3b66a-106">Quando si distribuiscono i Server Standard o i pool Front End, è possibile configurare i client per l'utilizzo dell'individuazione automatica in modo da accedere al Server Standard o al pool Front End appropriato.</span><span class="sxs-lookup"><span data-stu-id="3b66a-106">When you deploy your Standard Edition servers or Front End pools, you can configure your clients to use automatic discovery to sign in to the appropriate Standard Edition server or Front End pool.</span></span> <span data-ttu-id="3b66a-107">Se si prevede di richiedere ai client di connettersi manualmente a Lync Server 2013, è possibile ignorare questo argomento.</span><span class="sxs-lookup"><span data-stu-id="3b66a-107">If you plan to require your clients to connect manually to Lync Server 2013, you can skip this topic.</span></span>

<span data-ttu-id="3b66a-108">Per supportare l'accesso automatico dei client, è necessario:</span><span class="sxs-lookup"><span data-stu-id="3b66a-108">To support automatic client sign-in, you must:</span></span>

  - <span data-ttu-id="3b66a-p102">Designare un solo server o un pool per la distribuzione e l'autenticazione delle richieste di accesso dei client. A tale scopo, è possibile designare un server o un pool disponibile nell'organizzazione che ospita gli utenti oppure un server o un pool dedicato che non ospita alcun utente. Per garantire la disponibilità elevata, è consigliabile designare un pool Front End per questa funzione.</span><span class="sxs-lookup"><span data-stu-id="3b66a-p102">Designate a single server or pool to distribute and authenticate client sign-in requests. This can be an existing server or pool in your organization that hosts users, or you can designate a dedicated server or pool for this purpose that hosts no users. For high availability, we recommend that you designate a Front End pool for this function.</span></span>

  - <span data-ttu-id="3b66a-112">Creare un record SRV DNS interno per supportare l'accesso automatico dei client per questo server o pool.</span><span class="sxs-lookup"><span data-stu-id="3b66a-112">Create an internal DNS SRV record to support automatic client sign-in for this server or pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3b66a-p103">Nei requisiti dei record riportati di seguito il dominio SIP fa riferimento alla parte host degli URI SIP assegnati agli utenti. Se ad esempio gli URI SIP sono nel formato \*@contoso.com, contoso.com è il dominio SIP. Il dominio SIP è spesso diverso dal dominio Active Directory interno. Un'organizzazione può supportare anche più domini SIP.</span><span class="sxs-lookup"><span data-stu-id="3b66a-p103">In the following record requirements, SIP domain refers to the host portion of the SIP URIs assigned to users. For example, if SIP URIs are of the form \*@contoso.com, contoso.com is the SIP domain. The SIP domain is often different from the internal Active Directory domain. An organization can also support multiple SIP domains.</span></span>

    
    </div>

<span data-ttu-id="3b66a-117">Per abilitare la configurazione automatica per i client, è necessario creare un record SRV DNS interno che esegua il mapping tra uno dei record seguenti e il nome di dominio completo (FQDN) del pool Front end o del server Standard Edition che distribuisce le richieste di accesso dai client Lync:</span><span class="sxs-lookup"><span data-stu-id="3b66a-117">To enable automatic configuration for your clients, you must create an internal DNS SRV record that maps one of the following records to the fully qualified domain name (FQDN) of the Front End pool or Standard Edition server that distributes sign-in requests from Lync clients:</span></span>

  - <span data-ttu-id="3b66a-118">\_sipinternaltls. \_ TCP.\<domain\></span><span class="sxs-lookup"><span data-stu-id="3b66a-118">\_sipinternaltls.\_tcp.\<domain\></span></span> <span data-ttu-id="3b66a-119">-per le connessioni TLS interne</span><span class="sxs-lookup"><span data-stu-id="3b66a-119">- for internal TLS connections</span></span>

<span data-ttu-id="3b66a-120">È sufficiente creare un unico record SRV per il pool Front End o il server Standard Edition che distribuirà le richieste di accesso.</span><span class="sxs-lookup"><span data-stu-id="3b66a-120">You only need to create a single SRV record for the Front End pool or Standard Edition server or that will distribute sign-in requests.</span></span>

<span data-ttu-id="3b66a-121">Nella tabella riportata di seguito vengono illustrati alcuni record di esempio necessari per la società fittizia Contoso, che supporta i domini SIP contoso.com e retail.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3b66a-121">The following table shows some example records required for the fictitious company Contoso, which supports SIP domains of contoso.com and retail.contoso.com.</span></span>

### <a name="example-of-dns-records-required-for-automatic-client-sign-in-with-multiple-sip-domains"></a><span data-ttu-id="3b66a-122">Esempio di record DNS obbligatori per l'accesso automatico dei client con più domini SIP</span><span class="sxs-lookup"><span data-stu-id="3b66a-122">Example of DNS Records Required for Automatic Client Sign-in with Multiple SIP Domains</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3b66a-123">FQDN del pool Front End utilizzato per distribuire le richieste di accesso</span><span class="sxs-lookup"><span data-stu-id="3b66a-123">FQDN of Front End pool used to distribute sign-in requests</span></span></th>
<th><span data-ttu-id="3b66a-124">Dominio SIP</span><span class="sxs-lookup"><span data-stu-id="3b66a-124">SIP domain</span></span></th>
<th><span data-ttu-id="3b66a-125">Record SRV DNS</span><span class="sxs-lookup"><span data-stu-id="3b66a-125">DNS SRV record</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b66a-126">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b66a-126">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="3b66a-127">contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b66a-127">contoso.com</span></span></p></td>
<td><p><span data-ttu-id="3b66a-128">Record SRV per il dominio _sipinternaltls._tcp.contoso.com tramite la porta 5061 associata a pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b66a-128">An SRV record for _sipinternaltls._tcp.contoso.com domain over port 5061 that maps to pool01.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b66a-129">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b66a-129">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="3b66a-130">retail.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b66a-130">retail.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="3b66a-131">Record SRV per il dominio _sipinternaltls._tcp.retail.contoso.com tramite la porta 5061 associata a pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b66a-131">An SRV record for _sipinternaltls._tcp.retail.contoso.com domain over port 5061 that maps to pool01.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="3b66a-132">Per impostazione predefinita, le query per i record DNS seguono la rigida corrispondenza dei nomi di dominio tra il dominio del nome utente e il record SRV.</span><span class="sxs-lookup"><span data-stu-id="3b66a-132">By default, queries for DNS records adhere to strict domain name matching between the domain in the user name and the SRV record.</span></span> <span data-ttu-id="3b66a-133">Se si desidera che le query DNS del client utilizzino invece la corrispondenza dei suffissi, è possibile configurare il criterio di gruppo DisableStrictDNSNaming.</span><span class="sxs-lookup"><span data-stu-id="3b66a-133">If you prefer that client DNS queries use suffix matching instead, you can configure the DisableStrictDNSNaming Group Policy.</span></span> <span data-ttu-id="3b66a-134">Per informazioni dettagliate, vedere <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and Devices in Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="3b66a-134">For details, see <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and devices in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="example-of-the-certificates-and-dns-records-required-for-automatic-client-sign-in"></a><span data-ttu-id="3b66a-135">Esempio dei certificati e dei record DNS obbligatori per l'accesso automatico dei client</span><span class="sxs-lookup"><span data-stu-id="3b66a-135">Example of the Certificates and DNS Records Required for Automatic Client Sign-In</span></span>

<span data-ttu-id="3b66a-p106">In questo esempio vengono utilizzati gli stessi nomi di esempio della tabella precedente. L'organizzazione Contoso supporta i domini SIP contoso.com e retail.contoso.com e tutti i relativi utenti dispongono di un URI SIP in uno dei formati seguenti:</span><span class="sxs-lookup"><span data-stu-id="3b66a-p106">This example uses the same example names in the preceding table. The Contoso organization supports the SIP domains of contoso.com and retail.contoso.com, and all of its users have a SIP URI in one of the following forms:</span></span>

  - <span data-ttu-id="3b66a-138">\<user\>@retail. contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b66a-138">\<user\>@retail.contoso.com</span></span>

  - <span data-ttu-id="3b66a-139">\<user\>@contoso. com</span><span class="sxs-lookup"><span data-stu-id="3b66a-139">\<user\>@contoso.com</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


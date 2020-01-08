---
title: "Lync Server 2013: requisiti DNS per l'accesso automatico al client"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for automatic client sign-in
ms:assetid: 3bcd4bb3-a022-4ffa-b005-1a95ad2b1796
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425884(v=OCS.15)
ms:contentKeyID: 48183873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: afd8ac315222a5582bde9802c22ab7b4911ddfe3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985046"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-automatic-client-sign-in-in-lync-server-2013"></a><span data-ttu-id="de2ae-102">Requisiti DNS per l'accesso automatico client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de2ae-102">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de2ae-103">_**Argomento Ultima modifica:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="de2ae-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="de2ae-104">Questa sezione illustra i record DNS (Domain Name System) necessari per l'accesso automatico client.</span><span class="sxs-lookup"><span data-stu-id="de2ae-104">This section explains the Domain Name System (DNS) records that are required for automatic client sign-in.</span></span> <span data-ttu-id="de2ae-105">Quando si distribuiscono i server standard o i pool Front-End, è possibile configurare i client per l'uso dell'individuazione automatica per accedere al server standard o al pool Front-end appropriato.</span><span class="sxs-lookup"><span data-stu-id="de2ae-105">When you deploy your Standard Edition servers or Front End pools, you can configure your clients to use automatic discovery to sign in to the appropriate Standard Edition server or Front End pool.</span></span> <span data-ttu-id="de2ae-106">Se si prevede di richiedere la connessione manuale dei client a Lync Server 2013, è possibile ignorare questo argomento.</span><span class="sxs-lookup"><span data-stu-id="de2ae-106">If you plan to require your clients to connect manually to Lync Server 2013, you can skip this topic.</span></span>

<span data-ttu-id="de2ae-107">Per supportare l'accesso automatico al client, è necessario:</span><span class="sxs-lookup"><span data-stu-id="de2ae-107">To support automatic client sign-in, you must:</span></span>

  - <span data-ttu-id="de2ae-108">Designa un singolo server o pool per la distribuzione e l'autenticazione delle richieste di accesso client.</span><span class="sxs-lookup"><span data-stu-id="de2ae-108">Designate a single server or pool to distribute and authenticate client sign-in requests.</span></span> <span data-ttu-id="de2ae-109">Può trattarsi di un server o di un pool esistente nell'organizzazione che ospita gli utenti oppure è possibile designare un server o un pool dedicato per questo scopo che non ospita utenti.</span><span class="sxs-lookup"><span data-stu-id="de2ae-109">This can be an existing server or pool in your organization that hosts users, or you can designate a dedicated server or pool for this purpose that hosts no users.</span></span> <span data-ttu-id="de2ae-110">Per una disponibilità elevata, è consigliabile designare un pool Front-end per questa funzione.</span><span class="sxs-lookup"><span data-stu-id="de2ae-110">For high availability, we recommend that you designate a Front End pool for this function.</span></span>

  - <span data-ttu-id="de2ae-111">Creare un record SRV DNS interno per supportare l'accesso automatico al client per questo server o pool.</span><span class="sxs-lookup"><span data-stu-id="de2ae-111">Create an internal DNS SRV record to support automatic client sign-in for this server or pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="de2ae-112">Nei requisiti di record seguenti, il dominio SIP si riferisce alla parte ospitante degli URI SIP assegnati agli utenti.</span><span class="sxs-lookup"><span data-stu-id="de2ae-112">In the following record requirements, SIP domain refers to the host portion of the SIP URIs assigned to users.</span></span> <span data-ttu-id="de2ae-113">Ad esempio, se gli URI SIP hanno il formato \* @contoso. com, contoso.com è il dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="de2ae-113">For example, if SIP URIs are of the form \*@contoso.com, contoso.com is the SIP domain.</span></span> <span data-ttu-id="de2ae-114">Il dominio SIP è spesso diverso dal dominio Active Directory interno.</span><span class="sxs-lookup"><span data-stu-id="de2ae-114">The SIP domain is often different from the internal Active Directory domain.</span></span> <span data-ttu-id="de2ae-115">Un'organizzazione può anche supportare più domini SIP.</span><span class="sxs-lookup"><span data-stu-id="de2ae-115">An organization can also support multiple SIP domains.</span></span>

    
    </div>

<span data-ttu-id="de2ae-116">Per abilitare la configurazione automatica per i client, è necessario creare un record SRV DNS interno che esegue il mapping di uno dei record seguenti al nome di dominio completo (FQDN) del pool Front-end o del server Standard Edition che distribuisce le richieste di accesso da Lync client</span><span class="sxs-lookup"><span data-stu-id="de2ae-116">To enable automatic configuration for your clients, you must create an internal DNS SRV record that maps one of the following records to the fully qualified domain name (FQDN) of the Front End pool or Standard Edition server that distributes sign-in requests from Lync clients:</span></span>

  - <span data-ttu-id="de2ae-117">\_sipinternaltls. \_TCP. \<domain\> -per le connessioni TLS interne</span><span class="sxs-lookup"><span data-stu-id="de2ae-117">\_sipinternaltls.\_tcp.\<domain\> - for internal TLS connections</span></span>

<span data-ttu-id="de2ae-118">È sufficiente creare un singolo record SRV per il pool Front-end o per il server Standard Edition o per distribuire le richieste di accesso.</span><span class="sxs-lookup"><span data-stu-id="de2ae-118">You only need to create a single SRV record for the Front End pool or Standard Edition server or that will distribute sign-in requests.</span></span>

<span data-ttu-id="de2ae-119">Nella tabella seguente sono riportati alcuni esempi di record necessari per la società fittizia Contoso, che supporta i domini SIP di contoso.com e retail.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="de2ae-119">The following table shows some example records required for the fictitious company Contoso, which supports SIP domains of contoso.com and retail.contoso.com.</span></span>

### <a name="example-of-dns-records-required-for-automatic-client-sign-in-with-multiple-sip-domains"></a><span data-ttu-id="de2ae-120">Esempio di record DNS necessari per l'accesso automatico al client con più domini SIP</span><span class="sxs-lookup"><span data-stu-id="de2ae-120">Example of DNS Records Required for Automatic Client Sign-in with Multiple SIP Domains</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="de2ae-121">FQDN del pool Front End usato per distribuire le richieste di accesso</span><span class="sxs-lookup"><span data-stu-id="de2ae-121">FQDN of Front End pool used to distribute sign-in requests</span></span></th>
<th><span data-ttu-id="de2ae-122">Dominio SIP</span><span class="sxs-lookup"><span data-stu-id="de2ae-122">SIP domain</span></span></th>
<th><span data-ttu-id="de2ae-123">Record SRV DNS</span><span class="sxs-lookup"><span data-stu-id="de2ae-123">DNS SRV record</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="de2ae-124">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="de2ae-124">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="de2ae-125">contoso.com</span><span class="sxs-lookup"><span data-stu-id="de2ae-125">contoso.com</span></span></p></td>
<td><p><span data-ttu-id="de2ae-126">Record SRV per il dominio _sipinternaltls. _tcp. contoso. com sulla porta 5061 che esegue il mapping a pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="de2ae-126">An SRV record for _sipinternaltls._tcp.contoso.com domain over port 5061 that maps to pool01.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de2ae-127">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="de2ae-127">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="de2ae-128">retail.contoso.com</span><span class="sxs-lookup"><span data-stu-id="de2ae-128">retail.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="de2ae-129">Record SRV per il dominio _sipinternaltls. _tcp. retail. contoso. com sulla porta 5061 mappata a pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="de2ae-129">An SRV record for _sipinternaltls._tcp.retail.contoso.com domain over port 5061 that maps to pool01.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="de2ae-130">Per impostazione predefinita, le query per i record DNS si applicano a una corrispondenza di nomi di dominio rigorosa tra il dominio nel nome utente e il record SRV.</span><span class="sxs-lookup"><span data-stu-id="de2ae-130">By default, queries for DNS records adhere to strict domain name matching between the domain in the user name and the SRV record.</span></span> <span data-ttu-id="de2ae-131">Se si preferisce che le query DNS client usino invece la corrispondenza dei suffissi, è possibile configurare i criteri di gruppo di DisableStrictDNSNaming.</span><span class="sxs-lookup"><span data-stu-id="de2ae-131">If you prefer that client DNS queries use suffix matching instead, you can configure the DisableStrictDNSNaming Group Policy.</span></span> <span data-ttu-id="de2ae-132">Per informazioni dettagliate, vedere <A href="lync-server-2013-planning-for-clients-and-devices.md">pianificazione di client e dispositivi in Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="de2ae-132">For details, see <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and devices in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="example-of-the-certificates-and-dns-records-required-for-automatic-client-sign-in"></a><span data-ttu-id="de2ae-133">Esempio di certificati e record DNS necessari per l'accesso automatico al client</span><span class="sxs-lookup"><span data-stu-id="de2ae-133">Example of the Certificates and DNS Records Required for Automatic Client Sign-In</span></span>

<span data-ttu-id="de2ae-134">Questo esempio usa gli stessi nomi di esempio nella tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="de2ae-134">This example uses the same example names in the preceding table.</span></span> <span data-ttu-id="de2ae-135">L'organizzazione Contoso supporta i domini SIP di contoso.com e retail.contoso.com e tutti gli utenti hanno un URI SIP in uno dei moduli seguenti:</span><span class="sxs-lookup"><span data-stu-id="de2ae-135">The Contoso organization supports the SIP domains of contoso.com and retail.contoso.com, and all of its users have a SIP URI in one of the following forms:</span></span>

  - <span data-ttu-id="de2ae-136">\<User\>@retail. contoso.com</span><span class="sxs-lookup"><span data-stu-id="de2ae-136">\<user\>@retail.contoso.com</span></span>

  - <span data-ttu-id="de2ae-137">\<User\>@contoso. com</span><span class="sxs-lookup"><span data-stu-id="de2ae-137">\<user\>@contoso.com</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


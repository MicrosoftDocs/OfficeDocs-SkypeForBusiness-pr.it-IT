---
title: "Lync Server 2013: linee guida per l'integrazione della messaggistica unificata locale"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Guidelines for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 829ac017-6907-40f9-be22-787a28eae0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398656(v=OCS.15)
ms:contentKeyID: 48184681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1be763250edf7222b900aef88665b3e360e8125c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006222"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="guidelines-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="c94cd-102">Linee guida per l'integrazione della messaggistica unificata locale e di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c94cd-102">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c94cd-103">_**Ultimo argomento modificato:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="c94cd-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="c94cd-104">Di seguito sono riportate le linee guida e le procedure consigliate da considerare quando si distribuisce VoIP aziendale:</span><span class="sxs-lookup"><span data-stu-id="c94cd-104">The following are guidelines and best practices to consider when you deploy Enterprise Voice:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c94cd-105">La messaggistica unificata di Exchange supporta IPv6 solo se si utilizza anche UCMA 4.</span><span class="sxs-lookup"><span data-stu-id="c94cd-105">Exchange Unified Messaging (UM) supports IPv6 only if you are also using UCMA 4.</span></span>



</div>

  - <span data-ttu-id="c94cd-106">Distribuire un server di Lync Server 2013 Standard Edition o un pool Front end.</span><span class="sxs-lookup"><span data-stu-id="c94cd-106">Deploy a Lync Server 2013 Standard Edition server or a Front End pool.</span></span> <span data-ttu-id="c94cd-107">Per informazioni dettagliate sull'installazione, vedere [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c94cd-107">For details about installation, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="c94cd-108">Collaborare con gli amministratori di Exchange per verificare le attività che verranno eseguite da ognuno al fine di assicurare un'integrazione agevole e corretta.</span><span class="sxs-lookup"><span data-stu-id="c94cd-108">Work with Exchange administrators to confirm which tasks each of you will perform to assure a smooth and successful integration.</span></span>

  - <span data-ttu-id="c94cd-109">Distribuire i ruoli del server cassette postali di Exchange in ogni foresta di messaggistica unificata di Exchange in cui si desidera abilitare gli utenti per la messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="c94cd-109">Deploy the Exchange Mailbox server roles in each Exchange Unified Messaging (UM) forest where you want to enable users for Exchange UM.</span></span> <span data-ttu-id="c94cd-110">Per informazioni dettagliate sull'installazione dei ruoli del server Exchange, vedere la documentazione di Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c94cd-110">For details about installing Exchange server roles, see the Microsoft Exchange Server 2013 documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c94cd-111">Quando la messaggistica unificata di Exchange è installata, è configurata per l'utilizzo di un certificato autofirmato.</span><span class="sxs-lookup"><span data-stu-id="c94cd-111">When Exchange Unified Messaging (UM) is installed, it is configured to use a self-signed certificate.</span></span><BR><span data-ttu-id="c94cd-112">Il certificato autofirmato, tuttavia, non consente a Lync Server 2013 e alla messaggistica unificata di Exchange di essere attendibili tra loro, per questo motivo è necessario richiedere un certificato distinto da un'autorità di certificazione attendibile per entrambi i server.</span><span class="sxs-lookup"><span data-stu-id="c94cd-112">The self-signed certificate, however, does not enable Lync Server 2013 and Exchange UM to trust each other, which is why it is necessary to request a separate certificate from a certification authority that both servers trust.</span></span>

    
    </div>

  - <span data-ttu-id="c94cd-113">Se Lync Server 2013 e la messaggistica unificata di Exchange sono installati in foreste diverse, configurare ogni foresta di Exchange affinché consideri attendibile la foresta Lync Server 2013 e la foresta Lync Server 2013 per considerare attendibile ogni foresta di Exchange.</span><span class="sxs-lookup"><span data-stu-id="c94cd-113">If Lync Server 2013 and Exchange UM are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest and the Lync Server 2013 forest to trust each Exchange forest.</span></span> <span data-ttu-id="c94cd-114">Inoltre, impostare le impostazioni di messaggistica unificata di Exchange degli utenti sugli oggetti utente nella foresta di Lync Server 2013, in genere tramite uno script o uno strumento tra foreste, ad esempio Identity Lifecycle Manager (ILM).</span><span class="sxs-lookup"><span data-stu-id="c94cd-114">Also, set the users’ Exchange UM settings on the user objects in the Lync Server 2013 forest, typically by using a script or a cross-forest tool, such as Identity Lifecycle Manager (ILM).</span></span>

  - <span data-ttu-id="c94cd-115">Se necessario, installare Exchange Management Console per gestire i server di messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="c94cd-115">If necessary, install the Exchange Management Console to manage your Unified Messaging servers.</span></span>

  - <span data-ttu-id="c94cd-116">Ottenere numeri di telefono validi per Outlook Voice Access e l'operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="c94cd-116">Obtain valid phone numbers for Outlook Voice Access and auto attendant.</span></span>

  - <span data-ttu-id="c94cd-117">Se si utilizza una versione della messaggistica unificata di Exchange in precedenza rispetto a Microsoft Exchange Server 2010 Service Pack 1 (SP1), i nomi di coordinate per i dial plan di messaggistica unificata di Exchange e dial plan VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="c94cd-117">If you are using a version of Exchange UM earlier than Microsoft Exchange Server 2010 Service Pack 1 (SP1), coordinate names for Exchange UM SIP URI dial plans and Enterprise Voice dial plans.</span></span>

<div>

## <a name="deploying-redundant-exchange-um-servers"></a><span data-ttu-id="c94cd-118">Distribuzione di server di messaggistica unificata di Exchange ridondanti</span><span class="sxs-lookup"><span data-stu-id="c94cd-118">Deploying Redundant Exchange UM Servers</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c94cd-119">Si consiglia di distribuire almeno due server su cui è in esecuzione il servizio di messaggistica unificata di Exchange per ogni dial plan di messaggistica unificata SIP di Exchange che viene configurato per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c94cd-119">We recommend that you deploy a minimum of two servers on which Exchange UM services is running for each Exchange UM SIP URI dial plan that you configure for your organization.</span></span> <span data-ttu-id="c94cd-120">Oltre a fornire la capacità espansa, la distribuzione di server ridondanti garantisce una disponibilità elevata.</span><span class="sxs-lookup"><span data-stu-id="c94cd-120">In addition to providing expanded capacity, deploying redundant servers provides high availability.</span></span> <span data-ttu-id="c94cd-121">In caso di errore del server, Lync Server 2013 può essere configurato per eseguire il failover su un altro server.</span><span class="sxs-lookup"><span data-stu-id="c94cd-121">In the event of an server failure, Lync Server 2013 can be configured to fail over to another server.</span></span>



</div>

<span data-ttu-id="c94cd-122">Le configurazioni di esempio seguenti garantiscono resilienza della messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="c94cd-122">The following example configurations provide Exchange UM resiliency.</span></span>

<span data-ttu-id="c94cd-123">**Esempio 1: resilienza della messaggistica unificata di Exchange**</span><span class="sxs-lookup"><span data-stu-id="c94cd-123">**Example 1: Exchange UM Resiliency**</span></span>

<span data-ttu-id="c94cd-124">![Esempio di messaggistica unificata di Exchange 1](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Esempio di messaggistica unificata di Exchange 1")</span><span class="sxs-lookup"><span data-stu-id="c94cd-124">![Exchange UM Example 1](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Exchange UM Example 1")</span></span>

<span data-ttu-id="c94cd-125">Nell'esempio 1 i server di messaggistica unificata di Exchange 1 e 2 sono abilitati nel data center di Tukwila e i server di messaggistica unificata di Exchange 3 e 4 sono abilitati nel data center di Dublino.</span><span class="sxs-lookup"><span data-stu-id="c94cd-125">In Example 1, Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center.</span></span> <span data-ttu-id="c94cd-126">In caso di un'interruzione della messaggistica unificata di Exchange in Tukwila, i record DNS (Domain Name System) per i server 1 e 2 devono essere configurati in modo che puntino rispettivamente ai server 3 e 4.</span><span class="sxs-lookup"><span data-stu-id="c94cd-126">In the event of an Exchange UM outage in Tukwila, the Domain Name System (DNS) A records for servers 1 and 2 should be configured to point to servers 3 and 4, respectively.</span></span> <span data-ttu-id="c94cd-127">In caso di un'interruzione della messaggistica unificata di Exchange a Dublino, i record A DNS per i server 3 e 4 devono essere configurati in modo che puntino rispettivamente ai server 1 e 2.</span><span class="sxs-lookup"><span data-stu-id="c94cd-127">In the event of an Exchange UM outage in Dublin, the DNS A records for servers 3 and 4 should be configured to point to servers 1 and 2, respectively.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c94cd-128">Per l'esempio 1, è anche necessario assegnare uno dei certificati seguenti in ogni server di messaggistica unificata di Exchange:</span><span class="sxs-lookup"><span data-stu-id="c94cd-128">For Example 1, you should also assign one of following certificate on each Exchange UM server:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="c94cd-129">Utilizzare un certificato con un carattere jolly nel nome alternativo del soggetto.</span><span class="sxs-lookup"><span data-stu-id="c94cd-129">Use a certificate with a wildcard in the Subject Alternative Name (SAN).</span></span></P>
> <LI>
> <P><span data-ttu-id="c94cd-130">Inserire il nome di dominio completo (FQDN) di ognuno dei quattro server di messaggistica unificata di Exchange nel SAN.</span><span class="sxs-lookup"><span data-stu-id="c94cd-130">Put the fully qualified domain name (FQDN) of each of the four Exchange UM servers in the SAN.</span></span></P></LI></UL>



</div>

<span data-ttu-id="c94cd-131">**Esempio 2: resilienza della messaggistica unificata di Exchange**</span><span class="sxs-lookup"><span data-stu-id="c94cd-131">**Example 2: Exchange UM Resiliency**</span></span>

<span data-ttu-id="c94cd-132">![Esempio di messaggistica unificata di Exchange 2](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Esempio di messaggistica unificata di Exchange 2")</span><span class="sxs-lookup"><span data-stu-id="c94cd-132">![Exchange UM Example 2](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Exchange UM Example 2")</span></span>

<span data-ttu-id="c94cd-p106">Nell'esempio 2, in condizioni operative standard, i server di messaggistica unificata di Exchange 1 e 2 sono abilitati nel data center di Tukwila e i server di messaggistica unificata di Exchange 3 e 4 sono abilitati nel data center di Dublino. Tutti e quattro i server sono inclusi nel dial plan URI SIP degli utenti Tukwila, tuttavia, i server 3 e 4 sono disabilitati. In caso di interruzione della messaggistica unificata di Exchange a Tukwila, ad esempio, i server 1 e 2 di messaggistica unificata di Exchange devono essere disabilitati e i server 3 e 4 di messaggistica unificata di Exchange devono essere abilitati in modo che il traffico di messaggistica unificata di Exchange di Tukwila venga instradato ai server di Dublino.</span><span class="sxs-lookup"><span data-stu-id="c94cd-p106">In Example 2, under ordinary operating conditions Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center. All four servers are included in the Tukwila users' SIP URI dial plan; however, servers 3 and 4 are disabled. In the event of an Exchange UM outage in Tukwila, for example, Exchange UM servers 1 and 2 should be disabled and Exchange UM servers 3 and 4 should be enabled so the Tukwila Exchange UM traffic will be routed to the servers in Dublin.</span></span>

<span data-ttu-id="c94cd-136">Per informazioni dettagliate su come abilitare o disabilitare la messaggistica unificata in Exchange 2013, vedere la sezione relativa alla messaggistica unificata di Exchange [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372)2013 con Lync Server all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="c94cd-136">For details about how to enable or disable Unified Messaging on Exchange 2013, see “Integrate Exchange 2013 UM with Lync Server” at [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372).</span></span>

<span data-ttu-id="c94cd-137">Per informazioni dettagliate su come abilitare o disabilitare la messaggistica unificata in Microsoft Exchange Server 2010, vedere:</span><span class="sxs-lookup"><span data-stu-id="c94cd-137">For details about how to enable or disable Unified Messaging on Microsoft Exchange Server 2010, see:</span></span>

  - <span data-ttu-id="c94cd-138">"Abilita messaggistica unificata su Exchange 2010" all' [http://go.microsoft.com/fwlink/p/?LinkId=204418](http://go.microsoft.com/fwlink/p/?linkid=204418)indirizzo.</span><span class="sxs-lookup"><span data-stu-id="c94cd-138">"Enable Unified Messaging on Exchange 2010" at [http://go.microsoft.com/fwlink/p/?LinkId=204418](http://go.microsoft.com/fwlink/p/?linkid=204418).</span></span>

  - <span data-ttu-id="c94cd-139">"Disabilitare la messaggistica unificata su Exchange 2010" [http://go.microsoft.com/fwlink/p/?LinkId=204416](http://go.microsoft.com/fwlink/p/?linkid=204416)all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="c94cd-139">"Disable Unified Messaging on Exchange 2010" at [http://go.microsoft.com/fwlink/p/?LinkId=204416](http://go.microsoft.com/fwlink/p/?linkid=204416).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c94cd-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c94cd-140">See Also</span></span>


[<span data-ttu-id="c94cd-141">Processo di distribuzione per l'integrazione della messaggistica unificata locale e di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c94cd-141">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


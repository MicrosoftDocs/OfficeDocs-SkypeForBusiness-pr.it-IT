---
title: "Lync Server 2013: Linee guida per l'integrazione della messaggistica unificata locale"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Guidelines for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 829ac017-6907-40f9-be22-787a28eae0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398656(v=OCS.15)
ms:contentKeyID: 48184681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15973bf2055339e375e4aecc7cfd1f61ac205dbb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980742"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="guidelines-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="bd7db-102">Linee guida per l'integrazione della messaggistica unificata locale con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd7db-102">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd7db-103">_**Argomento Ultima modifica:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="bd7db-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="bd7db-104">Di seguito sono riportate le linee guida e le procedure consigliate per la distribuzione di VoIP aziendale:</span><span class="sxs-lookup"><span data-stu-id="bd7db-104">The following are guidelines and best practices to consider when you deploy Enterprise Voice:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bd7db-105">La messaggistica unificata di Exchange supporta IPv6 solo se si usa anche UCMA 4.</span><span class="sxs-lookup"><span data-stu-id="bd7db-105">Exchange Unified Messaging (UM) supports IPv6 only if you are also using UCMA 4.</span></span>



</div>

  - <span data-ttu-id="bd7db-106">Distribuire un server di Lync Server 2013 Standard Edition o un pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="bd7db-106">Deploy a Lync Server 2013 Standard Edition server or a Front End pool.</span></span> <span data-ttu-id="bd7db-107">Per informazioni dettagliate sull'installazione, vedere [distribuzione di Lync Server 2013](lync-server-2013-deploying-lync-server.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="bd7db-107">For details about installation, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="bd7db-108">Collaborare con gli amministratori di Exchange per confermare le attività che ognuno di voi eseguirà per garantire un'integrazione corretta e efficace.</span><span class="sxs-lookup"><span data-stu-id="bd7db-108">Work with Exchange administrators to confirm which tasks each of you will perform to assure a smooth and successful integration.</span></span>

  - <span data-ttu-id="bd7db-109">Distribuire i ruoli del server cassette postali di Exchange in ogni foresta di messaggistica unificata di Exchange in cui si vuole abilitare gli utenti per la messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="bd7db-109">Deploy the Exchange Mailbox server roles in each Exchange Unified Messaging (UM) forest where you want to enable users for Exchange UM.</span></span> <span data-ttu-id="bd7db-110">Per informazioni dettagliate sull'installazione dei ruoli di Exchange Server, vedere la documentazione di Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bd7db-110">For details about installing Exchange server roles, see the Microsoft Exchange Server 2013 documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="bd7db-111">Quando è installata la messaggistica unificata di Exchange, è configurata per l'uso di un certificato autofirmato.</span><span class="sxs-lookup"><span data-stu-id="bd7db-111">When Exchange Unified Messaging (UM) is installed, it is configured to use a self-signed certificate.</span></span><BR><span data-ttu-id="bd7db-112">Il certificato autofirmato, tuttavia, non consente a Lync Server 2013 e alla messaggistica unificata di Exchange di considerarsi attendibili, per cui è necessario richiedere un certificato distinto da un'autorità di certificazione attendibile per entrambi i server.</span><span class="sxs-lookup"><span data-stu-id="bd7db-112">The self-signed certificate, however, does not enable Lync Server 2013 and Exchange UM to trust each other, which is why it is necessary to request a separate certificate from a certification authority that both servers trust.</span></span>

    
    </div>

  - <span data-ttu-id="bd7db-113">Se Lync Server 2013 e la messaggistica unificata di Exchange sono installati in foreste diverse, configurare ogni foresta di Exchange per considerare attendibile la foresta Lync Server 2013 e la foresta di Lync Server 2013 per considerare attendibile ogni foresta di Exchange.</span><span class="sxs-lookup"><span data-stu-id="bd7db-113">If Lync Server 2013 and Exchange UM are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest and the Lync Server 2013 forest to trust each Exchange forest.</span></span> <span data-ttu-id="bd7db-114">Inoltre, imposta le impostazioni di messaggistica unificata di Exchange degli utenti negli oggetti utente nella foresta di Lync Server 2013, in genere usando uno script o uno strumento tra insiemi di strutture, ad esempio ILM (Identity Lifecycle Manager).</span><span class="sxs-lookup"><span data-stu-id="bd7db-114">Also, set the users’ Exchange UM settings on the user objects in the Lync Server 2013 forest, typically by using a script or a cross-forest tool, such as Identity Lifecycle Manager (ILM).</span></span>

  - <span data-ttu-id="bd7db-115">Se necessario, installare Exchange Management Console per gestire i server di messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="bd7db-115">If necessary, install the Exchange Management Console to manage your Unified Messaging servers.</span></span>

  - <span data-ttu-id="bd7db-116">Ottenere i numeri di telefono validi per Outlook Voice Access e l'operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="bd7db-116">Obtain valid phone numbers for Outlook Voice Access and auto attendant.</span></span>

  - <span data-ttu-id="bd7db-117">Se si usa una versione di messaggistica unificata di Exchange precedente a Microsoft Exchange Server 2010 Service Pack 1 (SP1), i nomi delle coordinate per i dial plan di messaggistica unificata di Exchange UM e i piani per le chiamate vocali aziendali.</span><span class="sxs-lookup"><span data-stu-id="bd7db-117">If you are using a version of Exchange UM earlier than Microsoft Exchange Server 2010 Service Pack 1 (SP1), coordinate names for Exchange UM SIP URI dial plans and Enterprise Voice dial plans.</span></span>

<div>

## <a name="deploying-redundant-exchange-um-servers"></a><span data-ttu-id="bd7db-118">Distribuzione di server Messaggistica unificata di Exchange ridondanti</span><span class="sxs-lookup"><span data-stu-id="bd7db-118">Deploying Redundant Exchange UM Servers</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bd7db-119">È consigliabile distribuire un minimo di due server in cui i servizi di messaggistica unificata di Exchange sono in esecuzione per ogni dial plan di messaggistica unificata di Exchange che si configura per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="bd7db-119">We recommend that you deploy a minimum of two servers on which Exchange UM services is running for each Exchange UM SIP URI dial plan that you configure for your organization.</span></span> <span data-ttu-id="bd7db-120">Oltre a fornire capacità espansa, la distribuzione di server ridondanti offre una disponibilità elevata.</span><span class="sxs-lookup"><span data-stu-id="bd7db-120">In addition to providing expanded capacity, deploying redundant servers provides high availability.</span></span> <span data-ttu-id="bd7db-121">In caso di errore del server, Lync Server 2013 può essere configurato per il failover su un altro server.</span><span class="sxs-lookup"><span data-stu-id="bd7db-121">In the event of an server failure, Lync Server 2013 can be configured to fail over to another server.</span></span>



</div>

<span data-ttu-id="bd7db-122">Le configurazioni di esempio seguenti garantiscono la resilienza della messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="bd7db-122">The following example configurations provide Exchange UM resiliency.</span></span>

<span data-ttu-id="bd7db-123">**Esempio 1: resilienza della messaggistica unificata di Exchange**</span><span class="sxs-lookup"><span data-stu-id="bd7db-123">**Example 1: Exchange UM Resiliency**</span></span>

<span data-ttu-id="bd7db-124">![Esempio di messaggistica unificata di Exchange 1](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "esempio di um Exchange 1")</span><span class="sxs-lookup"><span data-stu-id="bd7db-124">![Exchange UM Example 1](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Exchange UM Example 1")</span></span>

<span data-ttu-id="bd7db-125">Nell'esempio 1 i server di messaggistica unificata di Exchange 1 e 2 sono abilitati nel centro dati di Tukwila e i server di messaggistica unificata di Exchange 3 e 4 sono abilitati nel Data Center di Dublino.</span><span class="sxs-lookup"><span data-stu-id="bd7db-125">In Example 1, Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center.</span></span> <span data-ttu-id="bd7db-126">In caso di interruzione della messaggistica unificata di Exchange in Tukwila, il DNS (Domain Name System) record per i server 1 e 2 deve essere configurato in modo che punti rispettivamente ai server 3 e 4.</span><span class="sxs-lookup"><span data-stu-id="bd7db-126">In the event of an Exchange UM outage in Tukwila, the Domain Name System (DNS) A records for servers 1 and 2 should be configured to point to servers 3 and 4, respectively.</span></span> <span data-ttu-id="bd7db-127">In caso di interruzione della messaggistica unificata di Exchange in Dublin, è necessario configurare i record DNS per i server 3 e 4 in modo che puntino rispettivamente ai server 1 e 2.</span><span class="sxs-lookup"><span data-stu-id="bd7db-127">In the event of an Exchange UM outage in Dublin, the DNS A records for servers 3 and 4 should be configured to point to servers 1 and 2, respectively.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bd7db-128">Ad esempio 1, devi anche assegnare uno dei seguenti certificati in ogni server Messaggistica unificata di Exchange:</span><span class="sxs-lookup"><span data-stu-id="bd7db-128">For Example 1, you should also assign one of following certificate on each Exchange UM server:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="bd7db-129">Usare un certificato con un carattere jolly nel nome alternativo soggetto (SAN).</span><span class="sxs-lookup"><span data-stu-id="bd7db-129">Use a certificate with a wildcard in the Subject Alternative Name (SAN).</span></span></P>
> <LI>
> <P><span data-ttu-id="bd7db-130">Inserire il nome di dominio completo (FQDN) di ognuno dei quattro server di messaggistica unificata di Exchange nella SAN.</span><span class="sxs-lookup"><span data-stu-id="bd7db-130">Put the fully qualified domain name (FQDN) of each of the four Exchange UM servers in the SAN.</span></span></P></LI></UL>



</div>

<span data-ttu-id="bd7db-131">**Esempio 2: resilienza della messaggistica unificata di Exchange**</span><span class="sxs-lookup"><span data-stu-id="bd7db-131">**Example 2: Exchange UM Resiliency**</span></span>

<span data-ttu-id="bd7db-132">![Esempio di messaggistica unificata di Exchange 2](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "esempio di um") di Exchange 2</span><span class="sxs-lookup"><span data-stu-id="bd7db-132">![Exchange UM Example 2](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Exchange UM Example 2")</span></span>

<span data-ttu-id="bd7db-133">Nell'esempio 2, in condizioni operative ordinarie i server Messaggistica unificata di Exchange 1 e 2 sono abilitati nel centro dati Tukwila e i server di messaggistica unificata di Exchange 3 e 4 sono abilitati nel Data Center di Dublino.</span><span class="sxs-lookup"><span data-stu-id="bd7db-133">In Example 2, under ordinary operating conditions Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center.</span></span> <span data-ttu-id="bd7db-134">Tutti e quattro i server sono inclusi nel dial plan URI SIP degli utenti di Tukwila; Tuttavia, i server 3 e 4 sono disabilitati.</span><span class="sxs-lookup"><span data-stu-id="bd7db-134">All four servers are included in the Tukwila users' SIP URI dial plan; however, servers 3 and 4 are disabled.</span></span> <span data-ttu-id="bd7db-135">In caso di interruzione della messaggistica unificata di Exchange in Tukwila, ad esempio, i server di messaggistica unificata di Exchange 1 e 2 devono essere disabilitati e i server di messaggistica unificata di Exchange 3 e 4 devono essere abilitati in modo che il traffico di messaggistica unificata di Exchange venga Tukwila ai server di Dublino.</span><span class="sxs-lookup"><span data-stu-id="bd7db-135">In the event of an Exchange UM outage in Tukwila, for example, Exchange UM servers 1 and 2 should be disabled and Exchange UM servers 3 and 4 should be enabled so the Tukwila Exchange UM traffic will be routed to the servers in Dublin.</span></span>

<span data-ttu-id="bd7db-136">Per informazioni dettagliate su come abilitare o disabilitare la messaggistica unificata in Exchange 2013, vedere "integrare la messaggistica unificata di Exchange 2013 [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372)con Lync Server" all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="bd7db-136">For details about how to enable or disable Unified Messaging on Exchange 2013, see “Integrate Exchange 2013 UM with Lync Server” at [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372).</span></span>

<span data-ttu-id="bd7db-137">Per informazioni dettagliate su come abilitare o disabilitare la messaggistica unificata in Microsoft Exchange Server 2010, vedere:</span><span class="sxs-lookup"><span data-stu-id="bd7db-137">For details about how to enable or disable Unified Messaging on Microsoft Exchange Server 2010, see:</span></span>

  - <span data-ttu-id="bd7db-138">"Abilita la messaggistica unificata su Exchange 2010" [http://go.microsoft.com/fwlink/p/?LinkId=204418](http://go.microsoft.com/fwlink/p/?linkid=204418)at.</span><span class="sxs-lookup"><span data-stu-id="bd7db-138">"Enable Unified Messaging on Exchange 2010" at [http://go.microsoft.com/fwlink/p/?LinkId=204418](http://go.microsoft.com/fwlink/p/?linkid=204418).</span></span>

  - <span data-ttu-id="bd7db-139">"Disabilitare la messaggistica unificata su Exchange 2010" [http://go.microsoft.com/fwlink/p/?LinkId=204416](http://go.microsoft.com/fwlink/p/?linkid=204416)in.</span><span class="sxs-lookup"><span data-stu-id="bd7db-139">"Disable Unified Messaging on Exchange 2010" at [http://go.microsoft.com/fwlink/p/?LinkId=204416](http://go.microsoft.com/fwlink/p/?linkid=204416).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bd7db-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd7db-140">See Also</span></span>


[<span data-ttu-id="bd7db-141">Processo di distribuzione per l'integrazione della messaggistica unificata locale con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd7db-141">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


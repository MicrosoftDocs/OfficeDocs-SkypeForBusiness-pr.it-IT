---
title: "Lync Server 2013: Configurazione della messaggistica unificata in Microsoft Exchange Server per l'interazione con Lync Server"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013
ms:assetid: 058da9c4-23af-4ddb-9f63-70133a8aafc6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398106(v=OCS.15)
ms:contentKeyID: 48183289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 461d822862e837879f1feb2d3f980b816aae5280
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981871"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-unified-messaging-on-microsoft-exchange-server-to-work-with-lync-server-2013"></a><span data-ttu-id="f5c98-102">Configurazione della messaggistica unificata in Microsoft Exchange Server per l'interazione con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5c98-102">Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5c98-103">_**Argomento Ultima modifica:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="f5c98-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f5c98-104">Se si vuole usare la messaggistica unificata di Exchange (UM) per fornire risposte alle chiamate, Outlook Voice Access o servizi di operatore automatico per gli utenti di VoIP aziendale, leggere la <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">pianificazione per l'integrazione della messaggistica unificata di Exchange in Lync Server 2013</A> nella documentazione di pianificazione e quindi seguire le istruzioni in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="f5c98-104">If you want to use Exchange Unified Messaging (UM) to provide call answering, Outlook Voice Access, or auto-attendant services for Enterprise Voice users, read <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">Planning for Exchange Unified Messaging integration in Lync Server 2013</A> in the Planning documentation, and then follow the instructions in this section.</span></span>



</div>

<span data-ttu-id="f5c98-105">Per configurare la messaggistica UNIFICAta di Exchange per l'utilizzo di Enterprise Voice, è necessario eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="f5c98-105">To configure Exchange Unified Messaging (UM) to work with Enterprise Voice, you’ll need to perform the following tasks:</span></span>

  - <span data-ttu-id="f5c98-106">Configurare i certificati nel server che gestisce i servizi di messaggistica UNIFICAta di Exchange</span><span class="sxs-lookup"><span data-stu-id="f5c98-106">Configure certificates on the server running Exchange Unified Messaging (UM) services</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f5c98-107">Aggiungere tutti i server di accesso client e cassette postali a tutti i dial plan URI SIP di messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="f5c98-107">Add all Client Access and Mailbox servers to all UM SIP URI dial plans.</span></span> <span data-ttu-id="f5c98-108">In caso contrario, il routing delle chiamate in uscita non funziona come previsto.</span><span class="sxs-lookup"><span data-stu-id="f5c98-108">If not, outbound call routing won’t work as expected.</span></span>

    
    </div>

  - <span data-ttu-id="f5c98-109">Creare uno o più piani di dial URI SIP di messaggistica unificata, insieme ai numeri di telefono di accesso del Sottoscrittore, in base alle esigenze e quindi creare corrispondenti piani di chiamata di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f5c98-109">Create one or more UM SIP URI dial plans, along with the subscriber access phone numbers, as needed, and then create corresponding Lync Server dial plans.</span></span>

  - <span data-ttu-id="f5c98-110">USA lo script **exchucutil. ps1** per:</span><span class="sxs-lookup"><span data-stu-id="f5c98-110">Use the **exchucutil.ps1** script to:</span></span>
    
      - <span data-ttu-id="f5c98-111">Creare gateway IP di messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="f5c98-111">Create UM IP gateways.</span></span>
    
      - <span data-ttu-id="f5c98-112">Creare gruppi di risposta di messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="f5c98-112">Create UM hunt groups.</span></span>
    
      - <span data-ttu-id="f5c98-113">Concedere l'autorizzazione Lync Server 2013 per la lettura degli oggetti servizi di dominio Active Directory di messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="f5c98-113">Grant Lync Server 2013 permission to read UM Active Directory Domain Services objects.</span></span>

  - <span data-ttu-id="f5c98-114">Creare un oggetto operatore automatico di messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="f5c98-114">Create a UM auto-attendant object.</span></span>

  - <span data-ttu-id="f5c98-115">Creare un oggetto di accesso del Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="f5c98-115">Create a subscriber access object.</span></span>

  - <span data-ttu-id="f5c98-116">Crea un URI SIP per ogni utente e associa gli utenti a un dial plan di URI SIP di messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="f5c98-116">Create a SIP URI for each user and associating users with a UM SIP URI dial plan.</span></span>

<div>

## <a name="requirements-and-recommendations"></a><span data-ttu-id="f5c98-117">Requisiti e suggerimenti</span><span class="sxs-lookup"><span data-stu-id="f5c98-117">Requirements and Recommendations</span></span>

<span data-ttu-id="f5c98-118">Prima di iniziare, la documentazione in questa sezione presuppone che siano stati distribuiti i ruoli di Exchange 2013 seguenti: accesso client e cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="f5c98-118">Before you begin, the documentation in this section assumes that you have deployed the following Exchange 2013 roles: Client Access and Mailbox.</span></span> <span data-ttu-id="f5c98-119">In Microsoft Exchange Server 2013 la messaggistica unificata di Exchange viene eseguita come servizio in questi server.</span><span class="sxs-lookup"><span data-stu-id="f5c98-119">In Microsoft Exchange Server 2013, Exchange UM runs as a service on these servers.</span></span>

<span data-ttu-id="f5c98-120">Per informazioni dettagliate sulla distribuzione di Exchange 2013, vedere la raccolta di Exchange 2013 TechNet all'indirizzo[http://go.microsoft.com/fwlink/p/?LinkId=266637](http://go.microsoft.com/fwlink/p/?linkid=266637)</span><span class="sxs-lookup"><span data-stu-id="f5c98-120">For details about deploying Exchange 2013, see the Exchange 2013 TechNet Library at [http://go.microsoft.com/fwlink/p/?LinkId=266637](http://go.microsoft.com/fwlink/p/?linkid=266637)</span></span>

<span data-ttu-id="f5c98-121">Tenere inoltre presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f5c98-121">Also note the following:</span></span>

  - <span data-ttu-id="f5c98-122">Se la messaggistica unificata di Exchange è installata in più foreste, è necessario eseguire la procedura di integrazione di Exchange Server per ogni foresta di messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="f5c98-122">If Exchange UM is installed in multiple forests, the Exchange Server integration steps must be performed for each UM forest.</span></span> <span data-ttu-id="f5c98-123">Ogni foresta di messaggistica unificata deve inoltre essere configurata per considerare attendibile la foresta in cui è distribuito Lync Server 2013 e la foresta in cui è distribuito Lync Server 2013 deve essere configurata in modo da considerare attendibile ogni foresta di messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="f5c98-123">In addition, each UM forest must be configured to trust the forest in which Lync Server 2013 is deployed, and the forest in which Lync Server 2013 is deployed must be configured to trust each UM forest.</span></span>

  - <span data-ttu-id="f5c98-124">I passaggi di integrazione vengono eseguiti nei ruoli del server Exchange in cui sono in esecuzione i servizi di messaggistica unificata e nel server che esegue Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5c98-124">Integration steps are performed on both the Exchange Server roles where Unified Messaging services are running, and on the server running Lync Server 2013.</span></span> <span data-ttu-id="f5c98-125">È consigliabile eseguire i passaggi di integrazione della messaggistica unificata di Exchange Server prima di eseguire i passaggi di integrazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5c98-125">You should perform the Exchange Server Unified Messaging integration steps before you perform the Lync Server 2013 integration steps.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f5c98-126">Per scoprire quali passaggi di integrazione vengono eseguiti in quali server e per quali ruoli di amministratore, vedere <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">processo di distribuzione per l'integrazione di messaggistica unificata locale e Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f5c98-126">To see which integration steps are performed on which servers and by which administrator roles, see <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</A>.</span></span>

    
    </div>

<span data-ttu-id="f5c98-127">Gli strumenti seguenti devono essere disponibili in ogni server che gestisce la messaggistica unificata di Exchange:</span><span class="sxs-lookup"><span data-stu-id="f5c98-127">The following tools must be available on each server running Exchange UM:</span></span>

  - <span data-ttu-id="f5c98-128">Exchange Management Shell</span><span class="sxs-lookup"><span data-stu-id="f5c98-128">Exchange Management Shell</span></span>

  - <span data-ttu-id="f5c98-129">Lo script **exchucutil. ps1**, che esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="f5c98-129">The script **exchucutil.ps1**, which performs the following tasks:</span></span>
    
      - <span data-ttu-id="f5c98-130">Crea un gateway IP di messaggistica unificata per ogni Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5c98-130">Creates a UM IP gateway for each Lync Server 2013.</span></span>
    
      - <span data-ttu-id="f5c98-131">Crea un gruppo di ricerca per ogni gateway.</span><span class="sxs-lookup"><span data-stu-id="f5c98-131">Creates a hunt group for each gateway.</span></span> <span data-ttu-id="f5c98-132">L'identificatore pilota di ogni gruppo di ricerca specifica il dial plan URI SIP di messaggistica unificata usato dal pool Front-end o dal server Standard Edition associato al gateway.</span><span class="sxs-lookup"><span data-stu-id="f5c98-132">The pilot identifier of each hunt group specifies the UM SIP URI dial plan used by the Front End pool or Standard Edition server that is associated with the gateway.</span></span>
    
      - <span data-ttu-id="f5c98-133">Concede l'autorizzazione Lync Server 2013 per la lettura degli oggetti della messaggistica unificata di Exchange in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f5c98-133">Grants Lync Server 2013 permission to read Exchange UM objects in Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f5c98-134">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="f5c98-134">In This Section</span></span>

  - [<span data-ttu-id="f5c98-135">Configurare i certificati nel server in cui è in uso la messaggistica unificata di Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="f5c98-135">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</span></span>](lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md)

  - [<span data-ttu-id="f5c98-136">Configurare la messaggistica unificata in Microsoft Exchange per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5c98-136">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</span></span>](lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


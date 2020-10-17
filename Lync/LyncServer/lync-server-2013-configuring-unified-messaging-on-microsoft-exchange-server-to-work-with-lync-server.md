---
title: "Lync Server 2013: configurazione della messaggistica unificata in Microsoft Exchange Server per l'utilizzo con Lync Server"
description: "Lync Server 2013: configurazione della messaggistica unificata in Microsoft Exchange Server per l'utilizzo con Lync Server."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013
ms:assetid: 058da9c4-23af-4ddb-9f63-70133a8aafc6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398106(v=OCS.15)
ms:contentKeyID: 48183289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53c303f0ae659536aafcbdfcd829ed236e35a0ba
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548242"
---
# <a name="configuring-unified-messaging-on-microsoft-exchange-server-to-work-with-lync-server-2013"></a><span data-ttu-id="f8409-103">Configurazione della messaggistica unificata in Microsoft Exchange Server per l'utilizzo con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8409-103">Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8409-104">_**Ultimo argomento modificato:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="f8409-104">_**Topic Last Modified:** 2012-10-11_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f8409-105">Se si desidera utilizzare la messaggistica unificata di Exchange per fornire i servizi di risponditore automatico, Outlook Voice Access o operatori automatici per gli utenti di VoIP aziendale, leggere <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">pianificazione per l'integrazione della messaggistica unificata di Exchange in Lync Server 2013</A> nella documentazione relativa alla pianificazione e quindi seguire le istruzioni riportate in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="f8409-105">If you want to use Exchange Unified Messaging (UM) to provide call answering, Outlook Voice Access, or auto-attendant services for Enterprise Voice users, read <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">Planning for Exchange Unified Messaging integration in Lync Server 2013</A> in the Planning documentation, and then follow the instructions in this section.</span></span>



</div>

<span data-ttu-id="f8409-106">Per configurare la messaggistica unificata di Exchange in modo che funzioni con VoIP aziendale, è necessario eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="f8409-106">To configure Exchange Unified Messaging (UM) to work with Enterprise Voice, you’ll need to perform the following tasks:</span></span>

  - <span data-ttu-id="f8409-107">Configurare i certificati nel server che esegue i servizi di messaggistica unificata di Exchange</span><span class="sxs-lookup"><span data-stu-id="f8409-107">Configure certificates on the server running Exchange Unified Messaging (UM) services</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f8409-108">Aggiungere tutti i server Accesso client e cassette postali a tutti i dial plan URI SIP di messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="f8409-108">Add all Client Access and Mailbox servers to all UM SIP URI dial plans.</span></span> <span data-ttu-id="f8409-109">In caso contrario, il routing delle chiamate in uscita non funzionerà come previsto.</span><span class="sxs-lookup"><span data-stu-id="f8409-109">If not, outbound call routing won’t work as expected.</span></span>

    
    </div>

  - <span data-ttu-id="f8409-110">Creare uno o più dial plan URI SIP di messaggistica unificata, insieme ai numeri di telefono di accesso del Sottoscrittore, in base alle esigenze e quindi creare i dial plan di Lync Server corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="f8409-110">Create one or more UM SIP URI dial plans, along with the subscriber access phone numbers, as needed, and then create corresponding Lync Server dial plans.</span></span>

  - <span data-ttu-id="f8409-111">Utilizzare lo script **exchucutil.ps1** per:</span><span class="sxs-lookup"><span data-stu-id="f8409-111">Use the **exchucutil.ps1** script to:</span></span>
    
      - <span data-ttu-id="f8409-112">Creare gateway IP di messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="f8409-112">Create UM IP gateways.</span></span>
    
      - <span data-ttu-id="f8409-113">Creare gruppi di risposta di messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="f8409-113">Create UM hunt groups.</span></span>
    
      - <span data-ttu-id="f8409-114">Concedere l'autorizzazione Lync Server 2013 per leggere gli oggetti di servizi di dominio Active Directory di messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="f8409-114">Grant Lync Server 2013 permission to read UM Active Directory Domain Services objects.</span></span>

  - <span data-ttu-id="f8409-115">Creare un oggetto operatore automatico di messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="f8409-115">Create a UM auto-attendant object.</span></span>

  - <span data-ttu-id="f8409-116">Creare un oggetto di accesso sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="f8409-116">Create a subscriber access object.</span></span>

  - <span data-ttu-id="f8409-117">Creare un URI SIP per ogni utente e associare gli utenti a un dial plan URI SIP di messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="f8409-117">Create a SIP URI for each user and associating users with a UM SIP URI dial plan.</span></span>

<div>

## <a name="requirements-and-recommendations"></a><span data-ttu-id="f8409-118">Requisiti e raccomandazioni</span><span class="sxs-lookup"><span data-stu-id="f8409-118">Requirements and Recommendations</span></span>

<span data-ttu-id="f8409-119">Prima di iniziare, la documentazione in questa sezione presuppone che siano stati distribuiti i ruoli di Exchange 2013 seguenti: accesso client e cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="f8409-119">Before you begin, the documentation in this section assumes that you have deployed the following Exchange 2013 roles: Client Access and Mailbox.</span></span> <span data-ttu-id="f8409-120">In Microsoft Exchange Server 2013, la messaggistica unificata di Exchange viene eseguita come servizio su questi server.</span><span class="sxs-lookup"><span data-stu-id="f8409-120">In Microsoft Exchange Server 2013, Exchange UM runs as a service on these servers.</span></span>

<span data-ttu-id="f8409-121">Per informazioni dettagliate sulla distribuzione di Exchange 2013, vedere la libreria TechNet di Exchange 2013 all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=266637](https://go.microsoft.com/fwlink/p/?linkid=266637)</span><span class="sxs-lookup"><span data-stu-id="f8409-121">For details about deploying Exchange 2013, see the Exchange 2013 TechNet Library at [https://go.microsoft.com/fwlink/p/?LinkId=266637](https://go.microsoft.com/fwlink/p/?linkid=266637)</span></span>

<span data-ttu-id="f8409-122">Tenere inoltre presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f8409-122">Also note the following:</span></span>

  - <span data-ttu-id="f8409-123">Se la messaggistica unificata di Exchange è installata in più foreste, è necessario eseguire i passaggi di integrazione di Exchange Server per ogni foresta di messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="f8409-123">If Exchange UM is installed in multiple forests, the Exchange Server integration steps must be performed for each UM forest.</span></span> <span data-ttu-id="f8409-124">Ogni foresta di messaggistica unificata, inoltre, deve essere configurata per considerare attendibile la foresta in cui è distribuito Lync Server 2013 e la foresta in cui è distribuito Lync Server 2013 deve essere configurata in modo da considerare attendibile ogni foresta di messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="f8409-124">In addition, each UM forest must be configured to trust the forest in which Lync Server 2013 is deployed, and the forest in which Lync Server 2013 is deployed must be configured to trust each UM forest.</span></span>

  - <span data-ttu-id="f8409-125">I passaggi di integrazione vengono eseguiti sui ruoli del server Exchange in cui sono in esecuzione i servizi di messaggistica unificata e sul server che esegue Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f8409-125">Integration steps are performed on both the Exchange Server roles where Unified Messaging services are running, and on the server running Lync Server 2013.</span></span> <span data-ttu-id="f8409-126">È consigliabile eseguire i passaggi di integrazione della messaggistica unificata di Exchange Server prima di eseguire i passaggi di integrazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f8409-126">You should perform the Exchange Server Unified Messaging integration steps before you perform the Lync Server 2013 integration steps.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f8409-127">Per sapere quali passaggi di integrazione vengono eseguiti nei server e in base ai quali i ruoli di amministratore, vedere <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">processo di distribuzione per l'integrazione della messaggistica unificata locale e Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f8409-127">To see which integration steps are performed on which servers and by which administrator roles, see <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</A>.</span></span>

    
    </div>

<span data-ttu-id="f8409-128">Gli strumenti seguenti devono essere disponibili in ogni server che esegue la messaggistica unificata di Exchange:</span><span class="sxs-lookup"><span data-stu-id="f8409-128">The following tools must be available on each server running Exchange UM:</span></span>

  - <span data-ttu-id="f8409-129">Exchange Management Shell</span><span class="sxs-lookup"><span data-stu-id="f8409-129">Exchange Management Shell</span></span>

  - <span data-ttu-id="f8409-130">Script **exchucutil.ps1**, che consente di eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="f8409-130">The script **exchucutil.ps1**, which performs the following tasks:</span></span>
    
      - <span data-ttu-id="f8409-131">Crea un gateway IP di messaggistica unificata per ogni Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f8409-131">Creates a UM IP gateway for each Lync Server 2013.</span></span>
    
      - <span data-ttu-id="f8409-132">Creazione di un gruppo di risposta per ogni gateway.</span><span class="sxs-lookup"><span data-stu-id="f8409-132">Creates a hunt group for each gateway.</span></span> <span data-ttu-id="f8409-133">L'identificatore pilota di ogni gruppo di risposta specifica il dial plan URI SIP di messaggistica unificata utilizzato dal pool Front end o dal server Standard Edition associato al gateway.</span><span class="sxs-lookup"><span data-stu-id="f8409-133">The pilot identifier of each hunt group specifies the UM SIP URI dial plan used by the Front End pool or Standard Edition server that is associated with the gateway.</span></span>
    
      - <span data-ttu-id="f8409-134">Concede all'autorizzazione Lync Server 2013 la lettura degli oggetti di messaggistica unificata di Exchange in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f8409-134">Grants Lync Server 2013 permission to read Exchange UM objects in Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f8409-135">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="f8409-135">In This Section</span></span>

  - [<span data-ttu-id="f8409-136">Configurare i certificati nel server che esegue la messaggistica unificata di Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="f8409-136">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</span></span>](lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md)

  - [<span data-ttu-id="f8409-137">Configurare la messaggistica unificata in Microsoft Exchange per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8409-137">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</span></span>](lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


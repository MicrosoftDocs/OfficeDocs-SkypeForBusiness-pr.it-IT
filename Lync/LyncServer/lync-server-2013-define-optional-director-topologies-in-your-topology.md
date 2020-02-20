---
title: 'Lync Server 2013: definire topologie di Director opzionali nella topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define optional Director topologies in your topology
ms:assetid: 8e9a659d-23b0-401d-b296-59c7df414d49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398717(v=OCS.15)
ms:contentKeyID: 48184808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a07bf43552066260d55c8f5461a091d41732e46c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154338"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-optional-director-topologies-in-your-topology-for-lync-server-2013"></a><span data-ttu-id="55f16-102">Definire topologie Director opzionali nella topologia per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55f16-102">Define optional Director topologies in your topology for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55f16-103">_**Ultimo argomento modificato:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="55f16-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="55f16-104">I direttori di Lync Server 2013 possono essere server a istanza singola oppure possono essere installati come pool di più direttori con bilanciamento del carico per una maggiore disponibilità e capacità.</span><span class="sxs-lookup"><span data-stu-id="55f16-104">Lync Server 2013 Directors can be single-instance servers or they can be installed as a load-balanced pool of multiple Directors for higher availability and capacity.</span></span> <span data-ttu-id="55f16-105">Sono supportati sia il bilanciamento del carico hardware sia il bilanciamento del carico DNS (Domain Name System).</span><span class="sxs-lookup"><span data-stu-id="55f16-105">Both hardware load balancing and Domain Name System (DNS) load balancing are supported.</span></span> <span data-ttu-id="55f16-106">In questo argomento viene descritto come configurare il bilanciamento del carico DNS per i pool di server Director.</span><span class="sxs-lookup"><span data-stu-id="55f16-106">This topic explains how to configure DNS load balancing for Director pools.</span></span>

<span data-ttu-id="55f16-107">Per pubblicare, abilitare o disabilitare correttamente una topologia quando si aggiunge o si rimuove un ruolo server, è necessario accedere come utente membro dei gruppi **RTCUniversalServerAdmins** e **Domain Admins**.</span><span class="sxs-lookup"><span data-stu-id="55f16-107">To successfully publish, enable, or disable a topology when you add or remove a server role, you should be logged on as a user who is a member of the **RTCUniversalServerAdmins** and **Domain Admins** groups.</span></span> <span data-ttu-id="55f16-108">È anche possibile delegare i diritti e le autorizzazioni di amministratore appropriate per l'aggiunta dei ruoli server.</span><span class="sxs-lookup"><span data-stu-id="55f16-108">You can also delegate the proper administrator rights and permissions for adding server roles.</span></span> <span data-ttu-id="55f16-109">Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync server 2013](lync-server-2013-delegate-setup-permissions.md) nella documentazione relativa alla distribuzione di server Standard Edition o Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="55f16-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="55f16-110">Per poter apportare altre modifiche alla configurazione, è richiesta solo l'appartenenza al gruppo **RTCUniversalServerAdmins**.</span><span class="sxs-lookup"><span data-stu-id="55f16-110">For other configuration changes, only membership in the **RTCUniversalServerAdmins** group is required.</span></span>

<span data-ttu-id="55f16-111">In questo argomento vengono descritti i passaggi necessari per definire e pubblicare la topologia per le due topologie del Director:</span><span class="sxs-lookup"><span data-stu-id="55f16-111">This topic describes the steps to define and publish the topology for the two Director topologies:</span></span>

  - <span data-ttu-id="55f16-112">Per definire il Director (istanza singola)</span><span class="sxs-lookup"><span data-stu-id="55f16-112">To define the Director (single instance)</span></span>

  - <span data-ttu-id="55f16-113">Per definire il Director (più pool di server Director)</span><span class="sxs-lookup"><span data-stu-id="55f16-113">To define the Director (multiple Director pool)</span></span>

<div>

## <a name="to-define-the-director-single-instance"></a><span data-ttu-id="55f16-114">Per definire il Director (istanza singola)</span><span class="sxs-lookup"><span data-stu-id="55f16-114">To define the Director (single instance)</span></span>

1.  <span data-ttu-id="55f16-115">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.</span><span class="sxs-lookup"><span data-stu-id="55f16-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="55f16-116">Nella pagina di benvenuto fare clic su **Scarica topologia dalla distribuzione esistente**.</span><span class="sxs-lookup"><span data-stu-id="55f16-116">On the welcome page, click **Download Topology from Existing Deployment**.</span></span>

3.  <span data-ttu-id="55f16-117">Nella finestra di dialogo **Salva topologia con nome** digitare il nome e il percorso della copia locale della topologia esistente e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="55f16-117">In the **Save Topology As** dialog box, type the name and location of the local copy of the existing topology, and then click **Save**.</span></span>

4.  <span data-ttu-id="55f16-118">Espandere il sito in cui si intende aggiungere il Director, fare clic con il pulsante destro del mouse su **Pool di server Director** e quindi fare clic su **Nuovo pool di server Director**.</span><span class="sxs-lookup"><span data-stu-id="55f16-118">Expand the site in which you plan to add the Director, right-click **Director pools**, and then click **New Director Pool**.</span></span>

5.  <span data-ttu-id="55f16-119">Nella finestra di dialogo **Definire l'FQDN del pool di server Director** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="55f16-119">In the **Define the Director pool FQDN** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="55f16-120">In **FQDN pool** digitare l'FQDN del pool di server Director.</span><span class="sxs-lookup"><span data-stu-id="55f16-120">In **Pool FQDN**, type the FQDN for the Director pool.</span></span>
    
      - <span data-ttu-id="55f16-121">Fare clic su **Pool computer singolo** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="55f16-121">Click **Single computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="55f16-122">Nella finestra di dialogo **Definire condivisione file** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="55f16-122">In the **Define the file share** dialog box, do one of the following:</span></span>
    
    1.  <span data-ttu-id="55f16-123">Per utilizzare una condivisione file esistente, fare clic su **Utilizza condivisione file definita in precedenza**, selezionare una condivisione file nell'elenco e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="55f16-123">To use an existing file share, click **Use a previously defined file share**, select a file share from the list, and then click **Next**.</span></span>
    
    2.  <span data-ttu-id="55f16-124">Per creare una nuova condivisione file, fare clic su **Definisci nuova condivisione file**, digitare l'FQDN del percorso della condivisione file in **FQDN file server**, digitare il nome della condivisione in **Condivisione file** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="55f16-124">To create a new file share, click **Define a new file share**, type the FQDN for the location of the file share in **File Server FQDN**, type the name of the share in **File Share**, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="55f16-125">La condivisione file specificata o creata in questo passaggio deve esistere o essere creata prima della pubblicazione della topologia.</span><span class="sxs-lookup"><span data-stu-id="55f16-125">The file share that you specify or create in this step must exist or be created prior to publishing the topology.</span></span><BR><span data-ttu-id="55f16-126">La condivisione file assegnata a un Director in realtà non viene utilizzata, pertanto è possibile assegnare la condivisione file di qualsiasi pool all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="55f16-126">The file share assigned to a Director is not actually used, so you can assign the file share of any pool in the organization.</span></span>

    
    </div>

7.  <span data-ttu-id="55f16-127">Nella finestra di dialogo **Specificare l'URL dei servizi Web**, in **URL di base esterno** specificare l'FQDN per i server Director e quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="55f16-127">In the **Specify the Web Services URL** dialog box, in **External Base URL**, specify the FQDN for the Directors, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="55f16-128">Il nome deve essere risolvibile dai server DNS Internet e puntare all'indirizzo IP pubblico del proxy inverso, che resta in attesa delle richieste HTTP/HTTPS a tale URL e le trasmette tramite proxy alla directory virtuale dei servizi Web esterni in tale Director.</span><span class="sxs-lookup"><span data-stu-id="55f16-128">The name must be resolvable from Internet DNS servers and point to the public IP address of the reverse proxy, which listens for HTTP/HTTPS requests to that URL and proxies them to the external Web Services virtual directory on that Director.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="55f16-129">Se si dispone di più di un pool Front end o front end server, l'FQDN dei servizi Web esterni deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="55f16-129">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="55f16-130">Ad esempio, se si definisce l'FQDN dei servizi Web esterni di un front end server come <STRONG>pool01.contoso.com</STRONG>, non è possibile utilizzare <STRONG>pool01.contoso.com</STRONG> per un altro pool Front end o front end server.</span><span class="sxs-lookup"><span data-stu-id="55f16-130">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="55f16-131">Se si sta distribuendo anche Director, l'FQDN dei servizi Web esterni definiti per qualsiasi server Director o di server Director deve essere univoco da qualsiasi altro pool di Director o Director, nonché da qualsiasi pool Front end o front-end.</span><span class="sxs-lookup"><span data-stu-id="55f16-131">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="55f16-132">Se si decide di sostituire i servizi Web interni con un FQDN autodefinito, ogni FQDN deve essere univoco da qualsiasi altro pool Front End, Director o pool di server Director.</span><span class="sxs-lookup"><span data-stu-id="55f16-132">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

8.  <span data-ttu-id="55f16-133">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="55f16-133">Publish the topology.</span></span>

</div>

<div>

## <a name="to-define-the-director-multiple-director-pool"></a><span data-ttu-id="55f16-134">Per definire il Director (pool di più server Director)</span><span class="sxs-lookup"><span data-stu-id="55f16-134">To define the Director (multiple Director pool)</span></span>

1.  <span data-ttu-id="55f16-135">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.</span><span class="sxs-lookup"><span data-stu-id="55f16-135">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="55f16-136">Nella pagina di benvenuto fare clic su **Scarica topologia dalla distribuzione esistente**.</span><span class="sxs-lookup"><span data-stu-id="55f16-136">On the welcome page, click **Download Topology from Existing Deployment**.</span></span>

3.  <span data-ttu-id="55f16-137">Nella finestra di dialogo **Salva topologia con nome** digitare il nome e il percorso della copia locale della topologia esistente e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="55f16-137">In the **Save Topology As** dialog box, type the name and location of the local copy of the existing topology, and then click **Save**.</span></span>

4.  <span data-ttu-id="55f16-138">Espandere il sito in cui si intende aggiungere il Director, fare clic con il pulsante destro del mouse su **Pool di server Director** e quindi fare clic su **Nuovo pool di server Director**.</span><span class="sxs-lookup"><span data-stu-id="55f16-138">Expand the site in which you plan to add the Director, right-click **Director pools**, and then click **New Director Pool**.</span></span>

5.  <span data-ttu-id="55f16-139">Nella finestra di dialogo **Definire l'FQDN del pool di server Director** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="55f16-139">In the **Define the Director pool FQDN** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="55f16-140">In **FQDN pool** digitare l'FQDN del pool di server Director.</span><span class="sxs-lookup"><span data-stu-id="55f16-140">In **Pool FQDN**, type the FQDN for the Director pool.</span></span>
    
      - <span data-ttu-id="55f16-141">Fare clic su **Pool di più computer** e quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="55f16-141">Click **Multiple computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="55f16-142">Nella finestra di dialogo **Definire i computer nel pool corrente** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="55f16-142">In the **Define the computers in this pool** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="55f16-143">Specificare l'FQDN del computer del primo membro del pool e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="55f16-143">Specify the computer FQDN of the first pool member, and then click **Add**.</span></span>
    
      - <span data-ttu-id="55f16-p104">Ripetere il passaggio precedente per ogni computer da aggiungere. Al termine, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="55f16-p104">Repeat the previous step for each computer that you want to add. When you are finished, click **Next**.</span></span>

7.  <span data-ttu-id="55f16-146">Nella finestra di dialogo **Definire condivisione file** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="55f16-146">In the **Define the file share** dialog box, do one of the following:</span></span>
    
      - <span data-ttu-id="55f16-147">Per utilizzare una condivisione file esistente, fare clic su **Utilizza condivisione file definita in precedenza**, selezionare una condivisione file nell'elenco e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="55f16-147">To use an existing file share, click **Use a previously defined file share**, select a file share from the list, and then click **Next**.</span></span>
    
      - <span data-ttu-id="55f16-148">Per creare una nuova condivisione file, fare clic su **Definisci nuova condivisione file**, digitare l'FQDN del percorso della condivisione file in **FQDN file server**, digitare il nome della condivisione in **Condivisione file** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="55f16-148">To create a new file share, click **Define a new file share**, type the FQDN for the location of the file share in **File Server FQDN**, type the name of the share in **File Share**, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="55f16-149">La condivisione file specificata o creata in questo passaggio deve esistere o essere creata prima della pubblicazione della topologia.</span><span class="sxs-lookup"><span data-stu-id="55f16-149">The file share that you specify or create in this step must exist or be created prior to publishing the topology.</span></span><BR><span data-ttu-id="55f16-150">La condivisione file assegnata a un Director in realtà non viene utilizzata, pertanto è possibile assegnare la condivisione file di qualsiasi pool all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="55f16-150">The file share assigned to a Director is not actually used, so you can assign the file share of any pool in the organization.</span></span>

    
    </div>

8.  <span data-ttu-id="55f16-151">Nella finestra di dialogo **Specificare l'URL dei servizi Web**, in **URL di base esterno**, specificare l'FQDN dei Director e quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="55f16-151">In the **Specify the Web Services URL** dialog box, in **External Base URL**, specify the FQDN for the Directors, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="55f16-152">Il nome deve essere risolvibile dai server DNS Internet e puntare all'indirizzo IP pubblico del proxy inverso che è in attesa delle richieste HTTP/HTTPS inviate a tale URL e le trasmette mediante proxy alla directory virtuale dei Servizi Web esterni su tale pool di server Director.</span><span class="sxs-lookup"><span data-stu-id="55f16-152">The name must be resolvable from Internet DNS servers and point to the public IP address of the reverse proxy, which listens for HTTP/HTTPS requests sent to that URL and proxies them to the external Web Services virtual directory on that Director pool.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="55f16-153">Se si dispone di più di un pool Front end o front end server, l'FQDN dei servizi Web esterni deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="55f16-153">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="55f16-154">Ad esempio, se si definisce l'FQDN dei servizi Web esterni di un front end server come <STRONG>pool01.contoso.com</STRONG>, non è possibile utilizzare <STRONG>pool01.contoso.com</STRONG> per un altro pool Front end o front end server.</span><span class="sxs-lookup"><span data-stu-id="55f16-154">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="55f16-155">Se si sta distribuendo anche Director, l'FQDN dei servizi Web esterni definiti per qualsiasi server Director o di server Director deve essere univoco da qualsiasi altro pool di Director o Director, nonché da qualsiasi pool Front end o front-end.</span><span class="sxs-lookup"><span data-stu-id="55f16-155">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="55f16-156">Se si decide di sostituire i servizi Web interni con un FQDN autodefinito, ogni FQDN deve essere univoco da qualsiasi altro pool Front End, Director o pool di server Director.</span><span class="sxs-lookup"><span data-stu-id="55f16-156">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

9.  <span data-ttu-id="55f16-157">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="55f16-157">Publish the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


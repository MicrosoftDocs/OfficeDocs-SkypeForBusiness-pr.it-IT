---
title: 'Lync Server 2013: Definire topologie con server Director facoltativi nella topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define optional Director topologies in your topology
ms:assetid: 8e9a659d-23b0-401d-b296-59c7df414d49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398717(v=OCS.15)
ms:contentKeyID: 48184808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 524259226b44d68367b631c2b7cef5513e0770e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985041"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-optional-director-topologies-in-your-topology-for-lync-server-2013"></a><span data-ttu-id="1404f-102">Definire topologie con server Director facoltativi nella topologia per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1404f-102">Define optional Director topologies in your topology for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1404f-103">_**Argomento Ultima modifica:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="1404f-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="1404f-104">Gli amministratori di Lync Server 2013 possono essere server a istanza singola oppure possono essere installati come pool di più direttori con bilanciamento del carico per una maggiore disponibilità e capacità.</span><span class="sxs-lookup"><span data-stu-id="1404f-104">Lync Server 2013 Directors can be single-instance servers or they can be installed as a load-balanced pool of multiple Directors for higher availability and capacity.</span></span> <span data-ttu-id="1404f-105">Sono supportati sia il bilanciamento del carico hardware che il bilanciamento del carico DNS (Domain Name System).</span><span class="sxs-lookup"><span data-stu-id="1404f-105">Both hardware load balancing and Domain Name System (DNS) load balancing are supported.</span></span> <span data-ttu-id="1404f-106">Questo argomento spiega come configurare il bilanciamento del carico DNS per i pool di Director.</span><span class="sxs-lookup"><span data-stu-id="1404f-106">This topic explains how to configure DNS load balancing for Director pools.</span></span>

<span data-ttu-id="1404f-107">Per pubblicare, abilitare o disabilitare correttamente una topologia quando si aggiunge o si rimuove un ruolo del server, è necessario essere connessi come utenti membri dei gruppi **RTCUniversalServerAdmins** e **Domain Admins** .</span><span class="sxs-lookup"><span data-stu-id="1404f-107">To successfully publish, enable, or disable a topology when you add or remove a server role, you should be logged on as a user who is a member of the **RTCUniversalServerAdmins** and **Domain Admins** groups.</span></span> <span data-ttu-id="1404f-108">È anche possibile delegare i diritti e le autorizzazioni di amministratore appropriati per l'aggiunta di ruoli server.</span><span class="sxs-lookup"><span data-stu-id="1404f-108">You can also delegate the proper administrator rights and permissions for adding server roles.</span></span> <span data-ttu-id="1404f-109">Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync server 2013](lync-server-2013-delegate-setup-permissions.md) nella documentazione sulla distribuzione di server Standard Edition o Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="1404f-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="1404f-110">Per altre modifiche alla configurazione, è necessaria solo l'appartenenza al gruppo **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="1404f-110">For other configuration changes, only membership in the **RTCUniversalServerAdmins** group is required.</span></span>

<span data-ttu-id="1404f-111">In questo argomento vengono illustrati i passaggi per definire e pubblicare la topologia per le due topologie di Director:</span><span class="sxs-lookup"><span data-stu-id="1404f-111">This topic describes the steps to define and publish the topology for the two Director topologies:</span></span>

  - <span data-ttu-id="1404f-112">Per definire il Director (istanza singola)</span><span class="sxs-lookup"><span data-stu-id="1404f-112">To define the Director (single instance)</span></span>

  - <span data-ttu-id="1404f-113">Per definire il Director (pool di più direttori)</span><span class="sxs-lookup"><span data-stu-id="1404f-113">To define the Director (multiple Director pool)</span></span>

<div>

## <a name="to-define-the-director-single-instance"></a><span data-ttu-id="1404f-114">Per definire il Director (istanza singola)</span><span class="sxs-lookup"><span data-stu-id="1404f-114">To define the Director (single instance)</span></span>

1.  <span data-ttu-id="1404f-115">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="1404f-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="1404f-116">Nella pagina di benvenuto fare clic su **Scarica topologia da distribuzione esistente**.</span><span class="sxs-lookup"><span data-stu-id="1404f-116">On the welcome page, click **Download Topology from Existing Deployment**.</span></span>

3.  <span data-ttu-id="1404f-117">Nella finestra di dialogo **Salva topologia come** Digitare il nome e il percorso della copia locale della topologia esistente e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1404f-117">In the **Save Topology As** dialog box, type the name and location of the local copy of the existing topology, and then click **Save**.</span></span>

4.  <span data-ttu-id="1404f-118">Espandere il sito in cui si prevede di aggiungere il Director, fare clic con il pulsante destro del mouse su pool di **Director**e quindi scegliere **nuovo pool di Director**.</span><span class="sxs-lookup"><span data-stu-id="1404f-118">Expand the site in which you plan to add the Director, right-click **Director pools**, and then click **New Director Pool**.</span></span>

5.  <span data-ttu-id="1404f-119">Nella finestra di dialogo **Definisci il nome di dominio completo del pool di Director** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1404f-119">In the **Define the Director pool FQDN** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="1404f-120">In **FQDN del pool**Digitare il nome di dominio completo per il pool di Director.</span><span class="sxs-lookup"><span data-stu-id="1404f-120">In **Pool FQDN**, type the FQDN for the Director pool.</span></span>
    
      - <span data-ttu-id="1404f-121">Fare clic su **pool di computer singolo**e quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1404f-121">Click **Single computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="1404f-122">Nella finestra di dialogo **Definisci la condivisione file** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1404f-122">In the **Define the file share** dialog box, do one of the following:</span></span>
    
    1.  <span data-ttu-id="1404f-123">Per usare una condivisione file esistente, fare clic su **Usa una condivisione file definita in precedenza**, selezionare una condivisione file dall'elenco e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1404f-123">To use an existing file share, click **Use a previously defined file share**, select a file share from the list, and then click **Next**.</span></span>
    
    2.  <span data-ttu-id="1404f-124">Per creare una nuova condivisione di file, fare clic su **Definisci una nuova condivisione file**, digitare il nome di dominio completo relativo alla posizione della condivisione file nell' **FQDN del file server**, digitare la condivisione in **condivisione file**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1404f-124">To create a new file share, click **Define a new file share**, type the FQDN for the location of the file share in **File Server FQDN**, type the name of the share in **File Share**, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1404f-125">La condivisione di file specificata o creata in questo passaggio deve esistere o crearsi prima di pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="1404f-125">The file share that you specify or create in this step must exist or be created prior to publishing the topology.</span></span><BR><span data-ttu-id="1404f-126">La condivisione file assegnata a un amministratore non viene effettivamente usata, quindi è possibile assegnare la condivisione file di qualsiasi pool nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1404f-126">The file share assigned to a Director is not actually used, so you can assign the file share of any pool in the organization.</span></span>

    
    </div>

7.  <span data-ttu-id="1404f-127">Nella finestra di dialogo **specifica URL servizi Web** , in **URL di base esterno**, specificare il nome di dominio completo per gli amministratori e quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="1404f-127">In the **Specify the Web Services URL** dialog box, in **External Base URL**, specify the FQDN for the Directors, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1404f-128">Il nome deve essere risolvibile dai server DNS Internet e posizionare il puntatore sull'indirizzo IP pubblico del proxy inverso, che ascolta le richieste HTTP/HTTPS per l'URL e li delega alla directory virtuale dei servizi Web esterni in tale Director.</span><span class="sxs-lookup"><span data-stu-id="1404f-128">The name must be resolvable from Internet DNS servers and point to the public IP address of the reverse proxy, which listens for HTTP/HTTPS requests to that URL and proxies them to the external Web Services virtual directory on that Director.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="1404f-129">Se si hanno più di un pool Front end o un server front-end, l'FQDN dei servizi Web esterni deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="1404f-129">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="1404f-130">Se ad esempio si definisce il nome di dominio completo dei servizi Web esterni di un front end server come <STRONG>pool01.contoso.com</STRONG>, non è possibile usare <STRONG>pool01.contoso.com</STRONG> per un altro pool Front-end o front end server.</span><span class="sxs-lookup"><span data-stu-id="1404f-130">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="1404f-131">Se si sta distribuendo anche Directors, l'FQDN dei servizi Web esterni definiti per qualsiasi pool di Director o Director deve essere univoco da qualsiasi altro pool di Director o Director, nonché da qualsiasi pool Front-end o front end server.</span><span class="sxs-lookup"><span data-stu-id="1404f-131">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="1404f-132">Se decidi di ignorare i servizi Web interni con un nome di dominio completo definito autonomamente, ogni nome di dominio completo deve essere univoco da qualsiasi altro pool di front-end, Director o pool di Director.</span><span class="sxs-lookup"><span data-stu-id="1404f-132">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

8.  <span data-ttu-id="1404f-133">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="1404f-133">Publish the topology.</span></span>

</div>

<div>

## <a name="to-define-the-director-multiple-director-pool"></a><span data-ttu-id="1404f-134">Per definire il Director (pool di più direttori)</span><span class="sxs-lookup"><span data-stu-id="1404f-134">To define the Director (multiple Director pool)</span></span>

1.  <span data-ttu-id="1404f-135">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="1404f-135">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="1404f-136">Nella pagina di benvenuto fare clic su **Scarica topologia da distribuzione esistente**.</span><span class="sxs-lookup"><span data-stu-id="1404f-136">On the welcome page, click **Download Topology from Existing Deployment**.</span></span>

3.  <span data-ttu-id="1404f-137">Nella finestra di dialogo **Salva topologia come** Digitare il nome e il percorso della copia locale della topologia esistente e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1404f-137">In the **Save Topology As** dialog box, type the name and location of the local copy of the existing topology, and then click **Save**.</span></span>

4.  <span data-ttu-id="1404f-138">Espandere il sito in cui si prevede di aggiungere il Director, fare clic con il pulsante destro del mouse su pool di **Director**e quindi scegliere **nuovo pool di Director**.</span><span class="sxs-lookup"><span data-stu-id="1404f-138">Expand the site in which you plan to add the Director, right-click **Director pools**, and then click **New Director Pool**.</span></span>

5.  <span data-ttu-id="1404f-139">Nella finestra di dialogo **Definisci il nome di dominio completo del pool di Director** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1404f-139">In the **Define the Director pool FQDN** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="1404f-140">In **FQDN del pool**Digitare il nome di dominio completo per il pool di Director.</span><span class="sxs-lookup"><span data-stu-id="1404f-140">In **Pool FQDN**, type the FQDN for the Director pool.</span></span>
    
      - <span data-ttu-id="1404f-141">Fare clic su **pool di computer multipli**e quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1404f-141">Click **Multiple computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="1404f-142">Nella finestra di dialogo **Definisci i computer in questo pool** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1404f-142">In the **Define the computers in this pool** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="1404f-143">Specificare il nome di dominio completo del computer del primo membro del pool e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="1404f-143">Specify the computer FQDN of the first pool member, and then click **Add**.</span></span>
    
      - <span data-ttu-id="1404f-144">Ripetere il passaggio precedente per ogni computer che si vuole aggiungere.</span><span class="sxs-lookup"><span data-stu-id="1404f-144">Repeat the previous step for each computer that you want to add.</span></span> <span data-ttu-id="1404f-145">Al termine, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1404f-145">When you are finished, click **Next**.</span></span>

7.  <span data-ttu-id="1404f-146">Nella finestra di dialogo **Definisci la condivisione file** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1404f-146">In the **Define the file share** dialog box, do one of the following:</span></span>
    
      - <span data-ttu-id="1404f-147">Per usare una condivisione file esistente, fare clic su **Usa una condivisione file definita in precedenza**, selezionare una condivisione file dall'elenco e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1404f-147">To use an existing file share, click **Use a previously defined file share**, select a file share from the list, and then click **Next**.</span></span>
    
      - <span data-ttu-id="1404f-148">Per creare una nuova condivisione di file, fare clic su **Definisci una nuova condivisione file**, digitare il nome di dominio completo relativo alla posizione della condivisione file nell' **FQDN del file server**, digitare la condivisione in **condivisione file**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1404f-148">To create a new file share, click **Define a new file share**, type the FQDN for the location of the file share in **File Server FQDN**, type the name of the share in **File Share**, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1404f-149">La condivisione di file specificata o creata in questo passaggio deve esistere o crearsi prima di pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="1404f-149">The file share that you specify or create in this step must exist or be created prior to publishing the topology.</span></span><BR><span data-ttu-id="1404f-150">La condivisione file assegnata a un amministratore non viene effettivamente usata, quindi è possibile assegnare la condivisione file di qualsiasi pool nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1404f-150">The file share assigned to a Director is not actually used, so you can assign the file share of any pool in the organization.</span></span>

    
    </div>

8.  <span data-ttu-id="1404f-151">Nella finestra di dialogo **specifica URL servizi Web** , in **URL di base esterno**, specificare il nome di dominio completo per gli amministratori e quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="1404f-151">In the **Specify the Web Services URL** dialog box, in **External Base URL**, specify the FQDN for the Directors, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1404f-152">Il nome deve essere risolvibile dai server DNS Internet e posizionare il puntatore sull'indirizzo IP pubblico del proxy inverso, che attende le richieste HTTP/HTTPS inviate all'URL e le delega alla directory virtuale dei servizi Web esterni nel pool di Director.</span><span class="sxs-lookup"><span data-stu-id="1404f-152">The name must be resolvable from Internet DNS servers and point to the public IP address of the reverse proxy, which listens for HTTP/HTTPS requests sent to that URL and proxies them to the external Web Services virtual directory on that Director pool.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="1404f-153">Se si hanno più di un pool Front end o un server front-end, l'FQDN dei servizi Web esterni deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="1404f-153">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="1404f-154">Se ad esempio si definisce il nome di dominio completo dei servizi Web esterni di un front end server come <STRONG>pool01.contoso.com</STRONG>, non è possibile usare <STRONG>pool01.contoso.com</STRONG> per un altro pool Front-end o front end server.</span><span class="sxs-lookup"><span data-stu-id="1404f-154">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="1404f-155">Se si sta distribuendo anche Directors, l'FQDN dei servizi Web esterni definiti per qualsiasi pool di Director o Director deve essere univoco da qualsiasi altro pool di Director o Director, nonché da qualsiasi pool Front-end o front end server.</span><span class="sxs-lookup"><span data-stu-id="1404f-155">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="1404f-156">Se decidi di ignorare i servizi Web interni con un nome di dominio completo definito autonomamente, ogni nome di dominio completo deve essere univoco da qualsiasi altro pool di front-end, Director o pool di Director.</span><span class="sxs-lookup"><span data-stu-id="1404f-156">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

9.  <span data-ttu-id="1404f-157">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="1404f-157">Publish the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


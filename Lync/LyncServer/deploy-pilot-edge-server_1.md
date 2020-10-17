---
title: Distribuire Edge Server pilota
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: 11a59c48-0a53-4de1-83ed-875f850febd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204682(v=OCS.15)
ms:contentKeyID: 48183446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27b7cf106cb8c65f01a1c1935ff98a8f9d428b27
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502933"
---
# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="6b744-102">Distribuire Edge Server pilota</span><span class="sxs-lookup"><span data-stu-id="6b744-102">Deploy pilot Edge Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b744-103">_**Ultimo argomento modificato:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="6b744-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="6b744-104">In questo argomento vengono evidenziate le impostazioni di configurazione di cui tenere conto prima di distribuire il server perimetrale di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6b744-104">This topic highlights configuration settings you should be aware of prior to deploying your Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="6b744-105">In questa sezione vengono evidenziati solo i punti chiave di cui è consigliabile tenere conto nell'ambito della distribuzione del pool di server perimetrali pilota.</span><span class="sxs-lookup"><span data-stu-id="6b744-105">This section only highlights key points you should consider as part of your pilot Edge pool deployment.</span></span> <span data-ttu-id="6b744-106">Per la procedura dettagliata, vedere [Deploying External User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) nella documentazione relativa alla distribuzione, in cui viene descritto il processo di distribuzione e vengono fornite anche informazioni di configurazione per l'accesso degli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="6b744-106">For detailed steps, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.</span></span>

<span data-ttu-id="6b744-p102">Man mano che si va avanti nella procedura guidata **Definisci pool di server perimetrali**, esaminare le impostazioni di configurazione chiave illustrate nei passaggi seguenti. Si noti che sono visualizzate solo alcune pagine della procedura guidata **Definisci pool di server perimetrali**.</span><span class="sxs-lookup"><span data-stu-id="6b744-p102">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps. Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span>

<span data-ttu-id="6b744-109">**Definire un pool di server perimetrali**</span><span class="sxs-lookup"><span data-stu-id="6b744-109">**Define an Edge Pool**</span></span>

1.  <span data-ttu-id="6b744-110">Aprire la topologia pool pilota utilizzando Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="6b744-110">Open the pilot pool topology using Topology Builder.</span></span>

2.  <span data-ttu-id="6b744-111">Passare al nodo Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6b744-111">Navigate to the Lync Server 2013 node.</span></span> <span data-ttu-id="6b744-112">Fare clic con il pulsante destro del mouse su **Pool di server perimetrali** e scegliere **Nuovo pool di server perimetrali**.</span><span class="sxs-lookup"><span data-stu-id="6b744-112">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
    <span data-ttu-id="6b744-113">![Finestra di dialogo definire il nuovo pool di server perimetrali](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Finestra di dialogo definire il nuovo pool di server perimetrali")</span><span class="sxs-lookup"><span data-stu-id="6b744-113">![Define the New Edge Pool dialog box](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Define the New Edge Pool dialog box")</span></span>

3.  <span data-ttu-id="6b744-114">Un pool di server perimetrali può essere un **Pool di più computer** o un **Pool computer singolo**.</span><span class="sxs-lookup"><span data-stu-id="6b744-114">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
    <span data-ttu-id="6b744-115">![Finestra di dialogo definire l'FQDN del pool di server perimetrali](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Finestra di dialogo definire l'FQDN del pool di server perimetrali")</span><span class="sxs-lookup"><span data-stu-id="6b744-115">![Define the Edge Pool FQDN dialog box](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Define the Edge Pool FQDN dialog box")</span></span>

4.  <span data-ttu-id="6b744-116">Nella pagina **Selezionare funzionalità** non abilitare la federazione o la federazione XMPP.</span><span class="sxs-lookup"><span data-stu-id="6b744-116">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="6b744-117">La Federazione e la Federazione XMPP sono attualmente instradate attraverso il server perimetrale Office Communications Server 2007 R2 legacy.</span><span class="sxs-lookup"><span data-stu-id="6b744-117">Federation and XMPP federation are currently routed through the legacy Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="6b744-118">Queste funzionalità verranno configurate in una fase successiva della migrazione.</span><span class="sxs-lookup"><span data-stu-id="6b744-118">These features will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="6b744-119">![Finestra di dialogo Seleziona funzionalità.](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Finestra di dialogo Seleziona funzionalità.")</span><span class="sxs-lookup"><span data-stu-id="6b744-119">![Select Features dialog box](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Select Features dialog box")</span></span>

5.  <span data-ttu-id="6b744-120">Successivamente, completare le pagine seguenti della procedura guidata: **Selezionare le opzioni IP**, **FQDN esterni**, **Definire l'indirizzo IP interno** e **Definire l'indirizzo IP esterno**.</span><span class="sxs-lookup"><span data-stu-id="6b744-120">Next, continue completing the following wizard pages: **Select IP options**, **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>

6.  <span data-ttu-id="6b744-121">Nella pagina **definire l'hop successivo** selezionare il Director per l'hop successivo del pool di Edge di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6b744-121">On the **Define the next hop** page, select the Director for the next hop of the Lync Server 2013 Edge pool.</span></span>
    
    <span data-ttu-id="6b744-122">![Finestra di dialogo Definisci nuovo pool di server perimetrali, elenco pool hop successivo](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Finestra di dialogo Definisci nuovo pool di server perimetrali, elenco pool hop successivo")</span><span class="sxs-lookup"><span data-stu-id="6b744-122">![Define New Edge Pool dialog, Next hop pool list](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Define New Edge Pool dialog, Next hop pool list")</span></span>

7.  <span data-ttu-id="6b744-123">Nella pagina **Associa pool Front End** non associare un pool al pool di server perimetrali in questo momento.</span><span class="sxs-lookup"><span data-stu-id="6b744-123">On the **Associate Front End pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="6b744-124">Il traffico multimediale esterno è attualmente instradato attraverso il server perimetrale Office Communications Server 2007 R2 legacy.</span><span class="sxs-lookup"><span data-stu-id="6b744-124">External media traffic is currently routed through the legacy Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="6b744-125">Questa impostazione verrà configurata in una fase successiva della migrazione.</span><span class="sxs-lookup"><span data-stu-id="6b744-125">This setting will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="6b744-126">![Finestra di dialogo Definisci nuovo pool di server perimetrali](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Finestra di dialogo Definisci nuovo pool di server perimetrali")</span><span class="sxs-lookup"><span data-stu-id="6b744-126">![Define New Edge Pool dialog](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Define New Edge Pool dialog")</span></span>

8.  <span data-ttu-id="6b744-127">Fare clic su **Fine** e quindi su **Pubblica** per pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="6b744-127">Click **Finish** and then **Publish** the topology.</span></span>

9.  <span data-ttu-id="6b744-128">Seguire la procedura descritta in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) nella documentazione relativa alla distribuzione per installare i file nel nuovo server perimetrale, configurare i certificati e avviare i servizi.</span><span class="sxs-lookup"><span data-stu-id="6b744-128">Follow the steps in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span>

<span data-ttu-id="6b744-129">È molto importante seguire le linee guida illustrate negli argomenti relativi alla [distribuzione di accesso utente esterno in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="6b744-129">It’s very important that you follow the guidelines in the topics [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="6b744-130">In questa sezione vengono fornite solo indicazioni sulle impostazioni di configurazione durante la fase di installazione di questi ruoli server.</span><span class="sxs-lookup"><span data-stu-id="6b744-130">This section merely provided some guidance on configuration settings when installing these server roles.</span></span>

<span data-ttu-id="6b744-131">È ora necessario disporre di una distribuzione di Office Communications Server 2007 R2 server perimetrale legacy, indicata dalla presenza di BackCompatSite, in parallelo con una distribuzione di Lync Server 2013 Edge Server.</span><span class="sxs-lookup"><span data-stu-id="6b744-131">You should now have a legacy Office Communications Server 2007 R2 Edge server deployment, indicated by the presence of the BackCompatSite, in parallel with a Lync Server 2013 Edge server deployment.</span></span> <span data-ttu-id="6b744-132">La Federazione è configurata per l'utilizzo del Director di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="6b744-132">Federation is configured to use the Office Communications Server 2007 R2 Director.</span></span> <span data-ttu-id="6b744-133">Prima di passare alla fase successiva, verificare che entrambe le distribuzioni funzionino correttamente, che i servizi siano stati avviati e che sia possibile amministrare ogni distribuzione.</span><span class="sxs-lookup"><span data-stu-id="6b744-133">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span>

<span data-ttu-id="6b744-134">![Generatore di topologie che mostra il server perimetrale OCS](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Generatore di topologie che mostra il server perimetrale OCS")</span><span class="sxs-lookup"><span data-stu-id="6b744-134">![Topology Builder showing OCS Edge Server](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Topology Builder showing OCS Edge Server")</span></span>

</div>

<span> </span>

</div>

</div>

</div>


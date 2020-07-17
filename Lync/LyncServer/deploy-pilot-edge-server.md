---
title: Distribuire Edge Server pilota
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: dab345c0-8577-4c11-ac73-fe8b2a75f4cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205306(v=OCS.15)
ms:contentKeyID: 48185559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ba616f6a5ce86e0f94c3b52afd60aaba34b7635
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751268"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="8ebe3-102">Distribuire Edge Server pilota</span><span class="sxs-lookup"><span data-stu-id="8ebe3-102">Deploy pilot Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ebe3-103">_**Ultimo argomento modificato:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="8ebe3-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="8ebe3-104">In questo argomento vengono evidenziate le impostazioni di configurazione di cui tenere conto prima di distribuire il server perimetrale di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ebe3-104">This topic highlights configuration settings you should be aware of prior to deploying your Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="8ebe3-105">I processi di distribuzione e configurazione per Lync Server 2013 sono molto simili a Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ebe3-105">The deployment and configuration processes for Lync Server 2013 are very similar to Lync Server 2010.</span></span> <span data-ttu-id="8ebe3-106">In questa sezione vengono evidenziati solo i punti chiave di cui è consigliabile tenere conto nell'ambito della distribuzione del pool pilota.</span><span class="sxs-lookup"><span data-stu-id="8ebe3-106">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="8ebe3-107">Per la procedura dettagliata, vedere [Deploying External User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) nella documentazione relativa alla distribuzione, in cui viene descritto il processo di distribuzione e vengono fornite anche informazioni di configurazione per l'accesso degli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="8ebe3-107">For detailed steps, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.</span></span>

<span data-ttu-id="8ebe3-p102">Man mano che si va avanti nella procedura guidata **Definisci pool di server perimetrali**, esaminare le impostazioni di configurazione chiave illustrate nei passaggi seguenti. Si noti che sono visualizzate solo alcune pagine della procedura guidata **Definisci pool di server perimetrali**.</span><span class="sxs-lookup"><span data-stu-id="8ebe3-p102">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps. Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span>

<span data-ttu-id="8ebe3-110">**Definire un pool di server perimetrali**</span><span class="sxs-lookup"><span data-stu-id="8ebe3-110">**Define an Edge Pool**</span></span>

1.  <span data-ttu-id="8ebe3-111">Accedere al computer in cui è installato Generatore di topologie come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="8ebe3-111">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="8ebe3-112">Passare al nodo Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ebe3-112">Navigate to the Lync Server 2013 node.</span></span> <span data-ttu-id="8ebe3-113">Fare clic con il pulsante destro del mouse su **Pool di server perimetrali** e scegliere **Nuovo pool di server perimetrali**.</span><span class="sxs-lookup"><span data-stu-id="8ebe3-113">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
    <span data-ttu-id="8ebe3-114">![Finestra di dialogo definire il nuovo pool di server perimetrali](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Finestra di dialogo definire il nuovo pool di server perimetrali")</span><span class="sxs-lookup"><span data-stu-id="8ebe3-114">![Define the New Edge Pool dialog box](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Define the New Edge Pool dialog box")</span></span>

3.  <span data-ttu-id="8ebe3-115">Un pool di server perimetrali può essere un **Pool di più computer** o un **Pool computer singolo**.</span><span class="sxs-lookup"><span data-stu-id="8ebe3-115">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
    <span data-ttu-id="8ebe3-116">![Finestra di dialogo definire l'FQDN del pool di server perimetrali](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Finestra di dialogo definire l'FQDN del pool di server perimetrali")</span><span class="sxs-lookup"><span data-stu-id="8ebe3-116">![Define the Edge Pool FQDN dialog box](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Define the Edge Pool FQDN dialog box")</span></span>

4.  <span data-ttu-id="8ebe3-117">Nella pagina **Selezionare funzionalità** non abilitare la federazione o la federazione XMPP.</span><span class="sxs-lookup"><span data-stu-id="8ebe3-117">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="8ebe3-118">La Federazione e la Federazione XMPP sono entrambe instradate al server perimetrale di Lync Server 2010 legacy.</span><span class="sxs-lookup"><span data-stu-id="8ebe3-118">Federation and XMPP federation are both currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="8ebe3-119">Queste funzionalità verranno configurate in una fase successiva della migrazione.</span><span class="sxs-lookup"><span data-stu-id="8ebe3-119">These features will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="8ebe3-120">![Finestra di dialogo Seleziona funzionalità.](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Finestra di dialogo Seleziona funzionalità.")</span><span class="sxs-lookup"><span data-stu-id="8ebe3-120">![Select Features dialog box](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Select Features dialog box")</span></span>

5.  <span data-ttu-id="8ebe3-121">Successivamente, continuare a completare le pagine seguenti della procedura guidata: **FQDN esterni**, **definire l'indirizzo IP interno**e **definire l'indirizzo IP esterno**.</span><span class="sxs-lookup"><span data-stu-id="8ebe3-121">Next, continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>

6.  <span data-ttu-id="8ebe3-122">Nella pagina **definire l'hop successivo** selezionare il Director per l'hop successivo del pool di Edge di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ebe3-122">On the **Define the next hop** page, select the Director for the next hop of the Lync Server 2010 Edge pool.</span></span>
    
    <span data-ttu-id="8ebe3-123">![Finestra di dialogo definire l'hop successivo](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Finestra di dialogo definire l'hop successivo")</span><span class="sxs-lookup"><span data-stu-id="8ebe3-123">![Define the Next Hop dialog box](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Define the Next Hop dialog box")</span></span>

7.  <span data-ttu-id="8ebe3-124">Nella pagina **associa gruppi front-end o pool di Mediation** non associare un pool a questo pool di server perimetrali in questo momento.</span><span class="sxs-lookup"><span data-stu-id="8ebe3-124">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="8ebe3-125">Il traffico multimediale esterno è attualmente instradato attraverso il server perimetrale di Lync Server 2010 legacy.</span><span class="sxs-lookup"><span data-stu-id="8ebe3-125">External media traffic is currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="8ebe3-126">Questa impostazione verrà configurata in una fase successiva della migrazione.</span><span class="sxs-lookup"><span data-stu-id="8ebe3-126">This setting will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="8ebe3-127">![Finestra di dialogo Associa pool Front End](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Finestra di dialogo Associa pool Front End")</span><span class="sxs-lookup"><span data-stu-id="8ebe3-127">![Associate Front End Pools dialog box](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Associate Front End Pools dialog box")</span></span>

8.  <span data-ttu-id="8ebe3-128">Fare clic su **Fine** e quindi su **Pubblica** per pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="8ebe3-128">Click **Finish** and then **Publish** the topology.</span></span>

9.  <span data-ttu-id="8ebe3-129">Seguire la procedura descritta in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) nella documentazione relativa alla distribuzione per installare i file nel nuovo server perimetrale, configurare i certificati e avviare i servizi.</span><span class="sxs-lookup"><span data-stu-id="8ebe3-129">Follow the steps in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span>

<span data-ttu-id="8ebe3-130">È molto importante seguire le linee guida illustrate negli argomenti relativi alla [distribuzione di accesso utente esterno in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8ebe3-130">It’s very important that you follow the guidelines in the topics [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="8ebe3-131">In questa sezione vengono fornite solo indicazioni sulle impostazioni di configurazione durante la fase di installazione di questi ruoli server.</span><span class="sxs-lookup"><span data-stu-id="8ebe3-131">This section merely provided some guidance on configuration settings when installing these server roles.</span></span>

<span data-ttu-id="8ebe3-132">È ora necessario disporre di un server perimetrale di Lync Server 2010 legacy distribuito in parallelo con una distribuzione di Lync Server 2013 Edge Server.</span><span class="sxs-lookup"><span data-stu-id="8ebe3-132">You should now have a legacy Lync Server 2010 Edge Server deployed in parallel with a Lync Server 2013 Edge server deployment.</span></span> <span data-ttu-id="8ebe3-133">Prima di passare alla fase successiva, verificare che entrambe le distribuzioni funzionino correttamente, che i servizi siano stati avviati e che sia possibile amministrare ogni distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8ebe3-133">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


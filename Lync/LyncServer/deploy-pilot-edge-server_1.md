---
title: Distribuire Edge Server pilota
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: 11a59c48-0a53-4de1-83ed-875f850febd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204682(v=OCS.15)
ms:contentKeyID: 48183446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 686973f9334b9bf376a2e56c52f3306cf243c0eb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724026"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="379b7-102">Distribuire Edge Server pilota</span><span class="sxs-lookup"><span data-stu-id="379b7-102">Deploy pilot Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="379b7-103">_**Argomento Ultima modifica:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="379b7-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="379b7-104">Questo argomento evidenzia le impostazioni di configurazione da tenere presenti prima della distribuzione del server Edge di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="379b7-104">This topic highlights configuration settings you should be aware of prior to deploying your Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="379b7-105">Questa sezione evidenzia solo i punti chiave da considerare come parte della distribuzione del pool di Edge pilota.</span><span class="sxs-lookup"><span data-stu-id="379b7-105">This section only highlights key points you should consider as part of your pilot Edge pool deployment.</span></span> <span data-ttu-id="379b7-106">Per la procedura dettagliata, vedere [distribuzione dell'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) nella documentazione relativa alla distribuzione, che descrive il processo di distribuzione e fornisce anche informazioni sulla configurazione per l'accesso degli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="379b7-106">For detailed steps, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.</span></span>

<span data-ttu-id="379b7-107">Mentre ci si sposta nella procedura guidata **Definisci nuovo pool Edge** , rivedere le impostazioni di configurazione chiave illustrate nella procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="379b7-107">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="379b7-108">Tieni presente che vengono visualizzate solo alcune pagine della procedura guidata **Definisci nuovo pool di Edge** .</span><span class="sxs-lookup"><span data-stu-id="379b7-108">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span>

<span data-ttu-id="379b7-109">**Definire un pool di bordi**</span><span class="sxs-lookup"><span data-stu-id="379b7-109">**Define an Edge Pool**</span></span>

1.  <span data-ttu-id="379b7-110">Aprire la topologia del pool di Pilot usando generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="379b7-110">Open the pilot pool topology using Topology Builder.</span></span>

2.  <span data-ttu-id="379b7-111">Passare al nodo Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="379b7-111">Navigate to the Lync Server 2013 node.</span></span> <span data-ttu-id="379b7-112">Fare clic con il pulsante destro del mouse su pool **Edge**e scegliere **nuovo pool di bordi**.</span><span class="sxs-lookup"><span data-stu-id="379b7-112">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
    <span data-ttu-id="379b7-113">![Finestra di dialogo Definire il nuovo pool di server perimetrali](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Finestra di dialogo Definire il nuovo pool di server perimetrali")</span><span class="sxs-lookup"><span data-stu-id="379b7-113">![Define the New Edge Pool dialog box](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Define the New Edge Pool dialog box")</span></span>

3.  <span data-ttu-id="379b7-114">Un pool di Edge può essere un pool di **computer multipli** o un pool di **computer singolo**.</span><span class="sxs-lookup"><span data-stu-id="379b7-114">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
    <span data-ttu-id="379b7-115">![Finestra di dialogo Definire l'FQDN del pool di server perimetrali](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Finestra di dialogo Definire l'FQDN del pool di server perimetrali")</span><span class="sxs-lookup"><span data-stu-id="379b7-115">![Define the Edge Pool FQDN dialog box](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Define the Edge Pool FQDN dialog box")</span></span>

4.  <span data-ttu-id="379b7-116">Nella pagina **Seleziona funzionalità** non abilitare la Federazione o la Federazione XMPP.</span><span class="sxs-lookup"><span data-stu-id="379b7-116">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="379b7-117">Federazione e Federazione XMPP sono attualmente instradati attraverso il server perimetrale legacy di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="379b7-117">Federation and XMPP federation are currently routed through the legacy Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="379b7-118">Queste caratteristiche verranno configurate in una fase successiva della migrazione.</span><span class="sxs-lookup"><span data-stu-id="379b7-118">These features will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="379b7-119">![Finestra di dialogo Selezionare funzionalità](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Finestra di dialogo Selezionare funzionalità")</span><span class="sxs-lookup"><span data-stu-id="379b7-119">![Select Features dialog box](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Select Features dialog box")</span></span>

5.  <span data-ttu-id="379b7-120">Continuare quindi a completare le pagine della procedura guidata seguenti: **selezionare opzioni IP**, nomi di **dominio completi esterni**, **definire l'indirizzo IP interno**e **definire l'indirizzo IP esterno**.</span><span class="sxs-lookup"><span data-stu-id="379b7-120">Next, continue completing the following wizard pages: **Select IP options**, **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>

6.  <span data-ttu-id="379b7-121">Nella pagina **Definisci l'hop successivo** selezionare il Director per l'hop successivo del pool di Edge di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="379b7-121">On the **Define the next hop** page, select the Director for the next hop of the Lync Server 2013 Edge pool.</span></span>
    
    <span data-ttu-id="379b7-122">![Finestra di dialogo Definisci pool di server perimetrali - Elenco Pool hop successivo](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Finestra di dialogo Definisci pool di server perimetrali - Elenco Pool hop successivo")</span><span class="sxs-lookup"><span data-stu-id="379b7-122">![Define New Edge Pool dialog, Next hop pool list](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Define New Edge Pool dialog, Next hop pool list")</span></span>

7.  <span data-ttu-id="379b7-123">Nella pagina **Associa pool Front-End** non associare un pool a questo pool di Edge in questo momento.</span><span class="sxs-lookup"><span data-stu-id="379b7-123">On the **Associate Front End pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="379b7-124">Il traffico multimediale esterno è attualmente instradato attraverso il server perimetrale legacy di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="379b7-124">External media traffic is currently routed through the legacy Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="379b7-125">Questa impostazione verrà configurata in una fase successiva della migrazione.</span><span class="sxs-lookup"><span data-stu-id="379b7-125">This setting will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="379b7-126">![Finestra di dialogo Definisci pool di server perimetrali](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Finestra di dialogo Definisci pool di server perimetrali")</span><span class="sxs-lookup"><span data-stu-id="379b7-126">![Define New Edge Pool dialog](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Define New Edge Pool dialog")</span></span>

8.  <span data-ttu-id="379b7-127">Fare clic su **fine** e quindi **pubblicare** la topologia.</span><span class="sxs-lookup"><span data-stu-id="379b7-127">Click **Finish** and then **Publish** the topology.</span></span>

9.  <span data-ttu-id="379b7-128">Seguire la procedura descritta in [installare Edge Server per Lync Server 2013](lync-server-2013-install-edge-servers.md) nella documentazione relativa alla distribuzione per installare i file nel nuovo Edge Server, configurare i certificati e avviare i servizi.</span><span class="sxs-lookup"><span data-stu-id="379b7-128">Follow the steps in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span>

<span data-ttu-id="379b7-129">È molto importante seguire le linee guida degli argomenti relativi alla [distribuzione dell'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="379b7-129">It’s very important that you follow the guidelines in the topics [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="379b7-130">Questa sezione ha semplicemente fornito alcune indicazioni sulle impostazioni di configurazione durante l'installazione di questi ruoli del server.</span><span class="sxs-lookup"><span data-stu-id="379b7-130">This section merely provided some guidance on configuration settings when installing these server roles.</span></span>

<span data-ttu-id="379b7-131">Ora dovresti avere una distribuzione legacy di Office Communications Server 2007 R2 Edge Server, indicata dalla presenza di BackCompatSite, in parallelo con una distribuzione di Lync Server 2013 Edge Server.</span><span class="sxs-lookup"><span data-stu-id="379b7-131">You should now have a legacy Office Communications Server 2007 R2 Edge server deployment, indicated by the presence of the BackCompatSite, in parallel with a Lync Server 2013 Edge server deployment.</span></span> <span data-ttu-id="379b7-132">La Federazione è configurata per l'uso di Office Communications Server 2007 R2 Director.</span><span class="sxs-lookup"><span data-stu-id="379b7-132">Federation is configured to use the Office Communications Server 2007 R2 Director.</span></span> <span data-ttu-id="379b7-133">Verificare che entrambe le distribuzioni vengano eseguite correttamente, i servizi vengano avviati ed è possibile amministrare ogni distribuzione prima di passare alla fase successiva.</span><span class="sxs-lookup"><span data-stu-id="379b7-133">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span>

<span data-ttu-id="379b7-134">![Generatore di topologie con server perimetrale OCS](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Generatore di topologie con server perimetrale OCS")</span><span class="sxs-lookup"><span data-stu-id="379b7-134">![Topology Builder showing OCS Edge Server](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Topology Builder showing OCS Edge Server")</span></span>

</div>

<span> </span>

</div>

</div>

</div>


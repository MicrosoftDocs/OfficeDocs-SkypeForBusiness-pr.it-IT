---
title: Distribuire Edge Server pilota
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: dab345c0-8577-4c11-ac73-fe8b2a75f4cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205306(v=OCS.15)
ms:contentKeyID: 48185559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc9f88d731873a16535e80eb0726aec8335e447b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="e1f6d-102">Distribuire Edge Server pilota</span><span class="sxs-lookup"><span data-stu-id="e1f6d-102">Deploy pilot Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1f6d-103">_**Argomento Ultima modifica:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="e1f6d-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="e1f6d-104">Questo argomento evidenzia le impostazioni di configurazione da tenere presenti prima della distribuzione del server Edge di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e1f6d-104">This topic highlights configuration settings you should be aware of prior to deploying your Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="e1f6d-105">I processi di distribuzione e configurazione per Lync Server 2013 sono molto simili a Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e1f6d-105">The deployment and configuration processes for Lync Server 2013 are very similar to Lync Server 2010.</span></span> <span data-ttu-id="e1f6d-106">Questa sezione evidenzia solo i punti chiave da tenere in considerazione nell'ambito della distribuzione del pool pilota.</span><span class="sxs-lookup"><span data-stu-id="e1f6d-106">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="e1f6d-107">Per la procedura dettagliata, vedere [distribuzione dell'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) nella documentazione relativa alla distribuzione, che descrive il processo di distribuzione e fornisce anche informazioni sulla configurazione per l'accesso degli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="e1f6d-107">For detailed steps, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.</span></span>

<span data-ttu-id="e1f6d-108">Mentre ci si sposta nella procedura guidata **Definisci nuovo pool Edge** , rivedere le impostazioni di configurazione chiave illustrate nella procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="e1f6d-108">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="e1f6d-109">Tieni presente che vengono visualizzate solo alcune pagine della procedura guidata **Definisci nuovo pool di Edge** .</span><span class="sxs-lookup"><span data-stu-id="e1f6d-109">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span>

<span data-ttu-id="e1f6d-110">**Definire un pool di bordi**</span><span class="sxs-lookup"><span data-stu-id="e1f6d-110">**Define an Edge Pool**</span></span>

1.  <span data-ttu-id="e1f6d-111">Accedere al computer in cui è installato Generatore di topologia come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="e1f6d-111">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="e1f6d-112">Passare al nodo Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e1f6d-112">Navigate to the Lync Server 2013 node.</span></span> <span data-ttu-id="e1f6d-113">Fare clic con il pulsante destro del mouse su pool **Edge**e scegliere **nuovo pool di bordi**.</span><span class="sxs-lookup"><span data-stu-id="e1f6d-113">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
    <span data-ttu-id="e1f6d-114">![Finestra di dialogo Definire il nuovo pool di server perimetrali](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Finestra di dialogo Definire il nuovo pool di server perimetrali")</span><span class="sxs-lookup"><span data-stu-id="e1f6d-114">![Define the New Edge Pool dialog box](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Define the New Edge Pool dialog box")</span></span>

3.  <span data-ttu-id="e1f6d-115">Un pool di Edge può essere un pool di **computer multipli** o un pool di **computer singolo**.</span><span class="sxs-lookup"><span data-stu-id="e1f6d-115">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
    <span data-ttu-id="e1f6d-116">![Finestra di dialogo Definire l'FQDN del pool di server perimetrali](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Finestra di dialogo Definire l'FQDN del pool di server perimetrali")</span><span class="sxs-lookup"><span data-stu-id="e1f6d-116">![Define the Edge Pool FQDN dialog box](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Define the Edge Pool FQDN dialog box")</span></span>

4.  <span data-ttu-id="e1f6d-117">Nella pagina **Seleziona funzionalità** non abilitare la Federazione o la Federazione XMPP.</span><span class="sxs-lookup"><span data-stu-id="e1f6d-117">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="e1f6d-118">Federazione e Federazione XMPP sono entrambi attualmente instradati attraverso il server perimetrale Lync Server 2010 legacy.</span><span class="sxs-lookup"><span data-stu-id="e1f6d-118">Federation and XMPP federation are both currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="e1f6d-119">Queste caratteristiche verranno configurate in una fase successiva della migrazione.</span><span class="sxs-lookup"><span data-stu-id="e1f6d-119">These features will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="e1f6d-120">![Finestra di dialogo Selezionare funzionalità](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Finestra di dialogo Selezionare funzionalità")</span><span class="sxs-lookup"><span data-stu-id="e1f6d-120">![Select Features dialog box](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Select Features dialog box")</span></span>

5.  <span data-ttu-id="e1f6d-121">Continuare quindi a completare le pagine della procedura guidata seguenti: **FQDN esterni**, **definire l'indirizzo IP interno**e **definire l'indirizzo IP esterno**.</span><span class="sxs-lookup"><span data-stu-id="e1f6d-121">Next, continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>

6.  <span data-ttu-id="e1f6d-122">Nella pagina **Definisci l'hop successivo** selezionare il Director per l'hop successivo del pool di Edge di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e1f6d-122">On the **Define the next hop** page, select the Director for the next hop of the Lync Server 2010 Edge pool.</span></span>
    
    <span data-ttu-id="e1f6d-123">![Finestra di dialogo Definire l'hop successivo](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Finestra di dialogo Definire l'hop successivo")</span><span class="sxs-lookup"><span data-stu-id="e1f6d-123">![Define the Next Hop dialog box](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Define the Next Hop dialog box")</span></span>

7.  <span data-ttu-id="e1f6d-124">Nella pagina **Associa pool di mediazione o front-end** non associare un pool a questo pool di Edge in questo momento.</span><span class="sxs-lookup"><span data-stu-id="e1f6d-124">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="e1f6d-125">Il traffico multimediale esterno è attualmente instradato attraverso il server perimetrale Lync Server 2010 legacy.</span><span class="sxs-lookup"><span data-stu-id="e1f6d-125">External media traffic is currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="e1f6d-126">Questa impostazione verrà configurata in una fase successiva della migrazione.</span><span class="sxs-lookup"><span data-stu-id="e1f6d-126">This setting will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="e1f6d-127">![Finestra di dialogo Associare pool Front End](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Finestra di dialogo Associare pool Front End")</span><span class="sxs-lookup"><span data-stu-id="e1f6d-127">![Associate Front End Pools dialog box](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Associate Front End Pools dialog box")</span></span>

8.  <span data-ttu-id="e1f6d-128">Fare clic su **fine** e quindi **pubblicare** la topologia.</span><span class="sxs-lookup"><span data-stu-id="e1f6d-128">Click **Finish** and then **Publish** the topology.</span></span>

9.  <span data-ttu-id="e1f6d-129">Seguire la procedura descritta in [installare Edge Server per Lync Server 2013](lync-server-2013-install-edge-servers.md) nella documentazione relativa alla distribuzione per installare i file nel nuovo Edge Server, configurare i certificati e avviare i servizi.</span><span class="sxs-lookup"><span data-stu-id="e1f6d-129">Follow the steps in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span>

<span data-ttu-id="e1f6d-130">È molto importante seguire le linee guida degli argomenti relativi alla [distribuzione dell'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e1f6d-130">It’s very important that you follow the guidelines in the topics [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="e1f6d-131">Questa sezione ha semplicemente fornito alcune indicazioni sulle impostazioni di configurazione durante l'installazione di questi ruoli del server.</span><span class="sxs-lookup"><span data-stu-id="e1f6d-131">This section merely provided some guidance on configuration settings when installing these server roles.</span></span>

<span data-ttu-id="e1f6d-132">Ora dovresti avere un server perimetrale Lync Server 2010 distribuito in parallelo con una distribuzione di Lync Server 2013 Edge Server.</span><span class="sxs-lookup"><span data-stu-id="e1f6d-132">You should now have a legacy Lync Server 2010 Edge Server deployed in parallel with a Lync Server 2013 Edge server deployment.</span></span> <span data-ttu-id="e1f6d-133">Verificare che entrambe le distribuzioni vengano eseguite correttamente, i servizi vengano avviati ed è possibile amministrare ogni distribuzione prima di passare alla fase successiva.</span><span class="sxs-lookup"><span data-stu-id="e1f6d-133">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


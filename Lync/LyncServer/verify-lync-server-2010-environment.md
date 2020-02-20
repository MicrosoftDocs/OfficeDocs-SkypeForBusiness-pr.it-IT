---
title: Verificare l'ambiente Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify Lync Server 2010 environment
ms:assetid: bfc7c620-556a-43cd-b1ed-2c268ec2b5cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205231(v=OCS.15)
ms:contentKeyID: 48185301
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a162c51dabf88231edc7fb5a5f5372a9f29d8687
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147879"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-lync-server-2010-environment"></a><span data-ttu-id="340ff-102">Verificare l'ambiente Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="340ff-102">Verify Lync Server 2010 environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="340ff-103">_**Ultimo argomento modificato:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="340ff-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="340ff-104">Prima di distribuire Lync Server 2013 in uno stato di coesistenza con Lync Server 2010, è necessario verificare che i servizi di Lync Server 2010 siano stati configurati e avviati.</span><span class="sxs-lookup"><span data-stu-id="340ff-104">Before deploying Lync Server 2013 in a coexistence state with Lync Server 2010, you need to verify that Lync Server 2010 services have been configured and started.</span></span> <span data-ttu-id="340ff-105">È importante identificare i servizi e le funzionalità principali presenti nell'ambiente legacy, prima di distribuire un pool pilota di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="340ff-105">It is important to identify key services and features that exist in your legacy environment, prior to deploying a Lync Server 2013 pilot pool.</span></span> <span data-ttu-id="340ff-106">Prima di distribuire Microsoft Lync Server 2013 XMPP in uno stato di coesistenza con una distribuzione XMPP legacy, è necessario verificare che i servizi XMPP legacy siano stati configurati e avviati e identificare quale partner federato supporta la configurazione di XMPP legacy.</span><span class="sxs-lookup"><span data-stu-id="340ff-106">Before deploying Microsoft Lync Server 2013 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="340ff-107">La verifica della distribuzione di Lync Server 2010 legacy comporta quanto segue:</span><span class="sxs-lookup"><span data-stu-id="340ff-107">Verifying your legacy Lync Server 2010 deployment entails the following:</span></span>

  - <span data-ttu-id="340ff-108">Verificare che i servizi di Lync Server 2010 siano stati avviati</span><span class="sxs-lookup"><span data-stu-id="340ff-108">Verifying the Lync Server 2010 services are started</span></span>

  - <span data-ttu-id="340ff-109">Revisione della topologia e degli utenti in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="340ff-109">Reviewing the topology and users in Lync Server 2010.</span></span>

  - <span data-ttu-id="340ff-110">Verificare le impostazioni di federazione e server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="340ff-110">Verifying the federation and Edge server settings.</span></span>

  - <span data-ttu-id="340ff-111">Verificare i servizi e i partner federati XMPP.</span><span class="sxs-lookup"><span data-stu-id="340ff-111">Verifying XMPP services and federated partners.</span></span>

<span data-ttu-id="340ff-112">**Verificare che i servizi Lync Server 2010 siano stati avviati**</span><span class="sxs-lookup"><span data-stu-id="340ff-112">**Verify Lync Server 2010 Services are started**</span></span>

1.  <span data-ttu-id="340ff-113">Dal front end server di Lync Server 2010 passare all'applet servizi di amministrazione\\degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="340ff-113">From the Lync Server 2010 Front End Server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="340ff-114">Verificare che i servizi seguenti siano in esecuzione nel Front End Server:</span><span class="sxs-lookup"><span data-stu-id="340ff-114">Verify that the following services are running on the Front End Server:</span></span>
    
    <span data-ttu-id="340ff-115">![Elenco dei servizi in esecuzione nel front end server](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "Elenco dei servizi in esecuzione nel front end server")</span><span class="sxs-lookup"><span data-stu-id="340ff-115">![List of services running on Front End Server](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "List of services running on Front End Server")</span></span>

<span data-ttu-id="340ff-116">**Esaminare la topologia di Lync Server 2010 nel pannello di controllo di Lync Server**</span><span class="sxs-lookup"><span data-stu-id="340ff-116">**Review the Lync Server 2010 topology in Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="340ff-117">Eseguire l'accesso al Front End Server con un account membro del gruppo RTCUniversalServerAdmins oppure membro del ruolo amministrativo CsAdministrator o CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="340ff-117">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="340ff-118">Aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="340ff-118">Open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="340ff-119">Selezionare **Topologia**.</span><span class="sxs-lookup"><span data-stu-id="340ff-119">Select **Topology**.</span></span> <span data-ttu-id="340ff-120">Verificare che siano elencati i vari server della distribuzione di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="340ff-120">Verify that the various servers in your Lync Server 2010 deployment are listed.</span></span>
    
    <span data-ttu-id="340ff-121">![Pagina della topologia del pannello di controllo di Lync Server 2010](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Pagina della topologia del pannello di controllo di Lync Server 2010")</span><span class="sxs-lookup"><span data-stu-id="340ff-121">![Lync Server 2010 Control Panel topology page](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Lync Server 2010 Control Panel topology page")</span></span>

<span data-ttu-id="340ff-122">**Per esaminare gli utenti di Lync Server 2010 nel pannello di controllo di Lync Server**</span><span class="sxs-lookup"><span data-stu-id="340ff-122">**To review Lync Server 2010 users in Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="340ff-123">Aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="340ff-123">Open the Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="340ff-124">Selezionare **Utenti** e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="340ff-124">Select **Users** and then click **Find**.</span></span>

3.  <span data-ttu-id="340ff-125">Verificare che la colonna **pool di registrazione** punti al pool Lync Server 2010 per ogni utente elencato.</span><span class="sxs-lookup"><span data-stu-id="340ff-125">Verify that the **Registrar Pool** column points to the Lync Server 2010 pool for each user listed.</span></span>
    
    <span data-ttu-id="340ff-126">![Pannello di controllo di Lync Server 2010 che elenca gli utenti](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Pannello di controllo di Lync Server 2010 che elenca gli utenti")</span><span class="sxs-lookup"><span data-stu-id="340ff-126">![Lync Server 2010 Control Panel listing users](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Lync Server 2010 Control Panel listing users")</span></span>

<span data-ttu-id="340ff-127">**Per verificare le impostazioni di Federazione e Edge di Lync Server 2010**</span><span class="sxs-lookup"><span data-stu-id="340ff-127">**To verify Lync Server 2010 Edge and Federation Settings**</span></span>

1.  <span data-ttu-id="340ff-128">Avviare Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="340ff-128">Start Topology Builder.</span></span>

2.  <span data-ttu-id="340ff-129">Selezionare **Scarica topologia dalla distribuzione esistente**.</span><span class="sxs-lookup"><span data-stu-id="340ff-129">Select **Download Topology from existing deployment**.</span></span>

3.  <span data-ttu-id="340ff-130">Scegliere un nome di file e salvare la topologia come tipo di file predefinito, ovvero con l'estensione tbxml.</span><span class="sxs-lookup"><span data-stu-id="340ff-130">Choose a file name and save the topology with the default .tbxml file type.</span></span>

4.  <span data-ttu-id="340ff-131">Espandere il nodo Lync Server 2010 per rivelare i diversi ruoli del server nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="340ff-131">Expand the Lync Server 2010 node to reveal the various server roles in the deployment.</span></span>

5.  <span data-ttu-id="340ff-132">Selezionare il nodo del sito e verificare se è impostato un valore **Assegnazione route federazione sito**.</span><span class="sxs-lookup"><span data-stu-id="340ff-132">Select the site node and verify if a **Site federation route assignment** value is set.</span></span>
    
    <span data-ttu-id="340ff-133">![Generatore di topologie, route di Federazione del sito](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Generatore di topologie, route di Federazione del sito")</span><span class="sxs-lookup"><span data-stu-id="340ff-133">![Topology Builder, Site Federation Route](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Topology Builder, Site Federation Route")</span></span>

6.  <span data-ttu-id="340ff-p103">Selezionare quindi lo Standard Edition Front End Server o il pool Enterprise Edition Front End. Determinare se è stato configurato un pool di server perimetrali (per componenti multimediali) in **Associazioni**.</span><span class="sxs-lookup"><span data-stu-id="340ff-p103">Next, select the Standard Edition Server or Enterprise Edition front end pool. Determine if an Edge pool has been configured for Media below **Associations**.</span></span>
    
    <span data-ttu-id="340ff-136">![Generatore di topologie che Mostra server e pool](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Generatore di topologie che Mostra server e pool")</span><span class="sxs-lookup"><span data-stu-id="340ff-136">![Topology Builder showing servers and pools](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Topology Builder showing servers and pools")</span></span>

7.  <span data-ttu-id="340ff-137">Selezionare infine il pool di server perimetrali e identificare se è configurato un pool hop successivo in **Selezione hop successivo**.</span><span class="sxs-lookup"><span data-stu-id="340ff-137">Finally, select the Edge pool and identify if a Next hop pool is configured below **Next hop selection**.</span></span>
    
    <span data-ttu-id="340ff-138">![Generatore di topologie, selezione dell'hop successivo](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Generatore di topologie, selezione dell'hop successivo")</span><span class="sxs-lookup"><span data-stu-id="340ff-138">![Topology Builder, Next hop selection](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Topology Builder, Next hop selection")</span></span>

<span data-ttu-id="340ff-139">**Verificare la configurazione del partner federato XMPP legacy**</span><span class="sxs-lookup"><span data-stu-id="340ff-139">**Verify legacy XMPP Federated Partner Configuration**</span></span>

1.  <span data-ttu-id="340ff-140">Dal server XMPP legacy, accedere all'applet servizi di amministrazione\\degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="340ff-140">From the legacy XMPP server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="340ff-141">Verificare che il servizio Office Communications Server XMPP Gateway sia stato avviato.</span><span class="sxs-lookup"><span data-stu-id="340ff-141">Verify that the Office Communications Server XMPP Gateway service is started.</span></span>
    
    <span data-ttu-id="340ff-142">![Servizio gateway XMPP di Office Communications Server](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Servizio gateway XMPP di Office Communications Server")</span><span class="sxs-lookup"><span data-stu-id="340ff-142">![Office Communications Server XMPP Gateway Service](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP Gateway Service")</span></span>

</div>

<span> </span>

</div>

</div>

</div>


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
ms.openlocfilehash: 2a871955f53515491ed09ece5e5da21ef7a9fef8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730916"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-lync-server-2010-environment"></a><span data-ttu-id="53b93-102">Verificare l'ambiente Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="53b93-102">Verify Lync Server 2010 environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53b93-103">_**Argomento Ultima modifica:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="53b93-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="53b93-104">Prima di distribuire Lync Server 2013 in uno stato di coesistenza con Lync Server 2010, è necessario verificare che i servizi di Lync Server 2010 siano stati configurati e avviati.</span><span class="sxs-lookup"><span data-stu-id="53b93-104">Before deploying Lync Server 2013 in a coexistence state with Lync Server 2010, you need to verify that Lync Server 2010 services have been configured and started.</span></span> <span data-ttu-id="53b93-105">È importante identificare i servizi e le caratteristiche principali presenti nell'ambiente legacy, prima di distribuire un pool di piloti di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53b93-105">It is important to identify key services and features that exist in your legacy environment, prior to deploying a Lync Server 2013 pilot pool.</span></span> <span data-ttu-id="53b93-106">Prima di distribuire Microsoft Lync Server 2013 XMPP in uno stato di coesistenza con una distribuzione XMPP legacy, è necessario verificare che i servizi XMPP legacy siano stati configurati e avviati e identificare il partner federativo supportato dalla configurazione XMPP legacy.</span><span class="sxs-lookup"><span data-stu-id="53b93-106">Before deploying Microsoft Lync Server 2013 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="53b93-107">Per verificare la distribuzione legacy di Lync Server 2010, è richiesto quanto segue:</span><span class="sxs-lookup"><span data-stu-id="53b93-107">Verifying your legacy Lync Server 2010 deployment entails the following:</span></span>

  - <span data-ttu-id="53b93-108">La verifica dei servizi di Lync Server 2010 viene avviata</span><span class="sxs-lookup"><span data-stu-id="53b93-108">Verifying the Lync Server 2010 services are started</span></span>

  - <span data-ttu-id="53b93-109">Revisione della topologia e degli utenti in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="53b93-109">Reviewing the topology and users in Lync Server 2010.</span></span>

  - <span data-ttu-id="53b93-110">Verificare le impostazioni della Federazione e del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="53b93-110">Verifying the federation and Edge server settings.</span></span>

  - <span data-ttu-id="53b93-111">Verificare i servizi XMPP e i partner federati.</span><span class="sxs-lookup"><span data-stu-id="53b93-111">Verifying XMPP services and federated partners.</span></span>

<span data-ttu-id="53b93-112">**Verificare che i servizi di Lync Server 2010 siano avviati**</span><span class="sxs-lookup"><span data-stu-id="53b93-112">**Verify Lync Server 2010 Services are started**</span></span>

1.  <span data-ttu-id="53b93-113">Dal server front-end di Lync Server 2010 passare all'applet strumenti\\di amministrazione di servizi.</span><span class="sxs-lookup"><span data-stu-id="53b93-113">From the Lync Server 2010 Front End Server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="53b93-114">Verificare che i servizi seguenti siano in uso nel server front-end:</span><span class="sxs-lookup"><span data-stu-id="53b93-114">Verify that the following services are running on the Front End Server:</span></span>
    
    <span data-ttu-id="53b93-115">![Elenco dei servizi in esecuzione nel server Front End](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "Elenco dei servizi in esecuzione nel server Front End")</span><span class="sxs-lookup"><span data-stu-id="53b93-115">![List of services running on Front End Server](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "List of services running on Front End Server")</span></span>

<span data-ttu-id="53b93-116">**Esaminare la topologia di Lync Server 2010 nel pannello di controllo di Lync Server**</span><span class="sxs-lookup"><span data-stu-id="53b93-116">**Review the Lync Server 2010 topology in Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="53b93-117">Accedere al server front-end con un account che sia un membro del gruppo RTCUniversalServerAdmins o un membro del ruolo di amministratore di CsAdministrator o CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="53b93-117">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="53b93-118">Aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="53b93-118">Open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="53b93-119">Selezionare **topologia**.</span><span class="sxs-lookup"><span data-stu-id="53b93-119">Select **Topology**.</span></span> <span data-ttu-id="53b93-120">Verificare che siano elencati i vari server della distribuzione di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="53b93-120">Verify that the various servers in your Lync Server 2010 deployment are listed.</span></span>
    
    <span data-ttu-id="53b93-121">![Pagina della topologia del Pannello di controllo di Lync Server 2010](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Pagina della topologia del Pannello di controllo di Lync Server 2010")</span><span class="sxs-lookup"><span data-stu-id="53b93-121">![Lync Server 2010 Control Panel topology page](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Lync Server 2010 Control Panel topology page")</span></span>

<span data-ttu-id="53b93-122">**Per esaminare gli utenti di Lync Server 2010 nel pannello di controllo di Lync Server**</span><span class="sxs-lookup"><span data-stu-id="53b93-122">**To review Lync Server 2010 users in Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="53b93-123">Aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="53b93-123">Open the Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="53b93-124">Selezionare **utenti** e quindi fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="53b93-124">Select **Users** and then click **Find**.</span></span>

3.  <span data-ttu-id="53b93-125">Verificare che la colonna del **pool di registrazione** punti al pool di Lync Server 2010 per ogni utente elencato.</span><span class="sxs-lookup"><span data-stu-id="53b93-125">Verify that the **Registrar Pool** column points to the Lync Server 2010 pool for each user listed.</span></span>
    
    <span data-ttu-id="53b93-126">![Elenco utenti nel Pannello di controllo di Lync Server 2010](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Elenco utenti nel Pannello di controllo di Lync Server 2010")</span><span class="sxs-lookup"><span data-stu-id="53b93-126">![Lync Server 2010 Control Panel listing users](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Lync Server 2010 Control Panel listing users")</span></span>

<span data-ttu-id="53b93-127">**Per verificare le impostazioni di Edge e federativo di Lync Server 2010**</span><span class="sxs-lookup"><span data-stu-id="53b93-127">**To verify Lync Server 2010 Edge and Federation Settings**</span></span>

1.  <span data-ttu-id="53b93-128">Avviare Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="53b93-128">Start Topology Builder.</span></span>

2.  <span data-ttu-id="53b93-129">Selezionare **Scarica topologia dalla distribuzione esistente**.</span><span class="sxs-lookup"><span data-stu-id="53b93-129">Select **Download Topology from existing deployment**.</span></span>

3.  <span data-ttu-id="53b93-130">Scegliere un nome file e salvare la topologia con il tipo di file default. tbxml.</span><span class="sxs-lookup"><span data-stu-id="53b93-130">Choose a file name and save the topology with the default .tbxml file type.</span></span>

4.  <span data-ttu-id="53b93-131">Espandere il nodo Lync Server 2010 per rivelare i vari ruoli del server nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="53b93-131">Expand the Lync Server 2010 node to reveal the various server roles in the deployment.</span></span>

5.  <span data-ttu-id="53b93-132">Selezionare il nodo del sito e verificare se è impostato un valore di **assegnazione della route federativo del sito** .</span><span class="sxs-lookup"><span data-stu-id="53b93-132">Select the site node and verify if a **Site federation route assignment** value is set.</span></span>
    
    <span data-ttu-id="53b93-133">![Generatore di topologie - Route federazione sito](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Generatore di topologie - Route federazione sito")</span><span class="sxs-lookup"><span data-stu-id="53b93-133">![Topology Builder, Site Federation Route](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Topology Builder, Site Federation Route")</span></span>

6.  <span data-ttu-id="53b93-134">Selezionare quindi il pool di front end del server Standard Edition o Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="53b93-134">Next, select the Standard Edition Server or Enterprise Edition front end pool.</span></span> <span data-ttu-id="53b93-135">Determinare se un pool di bordi è stato configurato per elementi multimediali al di sotto delle **associazioni**.</span><span class="sxs-lookup"><span data-stu-id="53b93-135">Determine if an Edge pool has been configured for Media below **Associations**.</span></span>
    
    <span data-ttu-id="53b93-136">![Generatore di topologie con server e pool](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Generatore di topologie con server e pool")</span><span class="sxs-lookup"><span data-stu-id="53b93-136">![Topology Builder showing servers and pools](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Topology Builder showing servers and pools")</span></span>

7.  <span data-ttu-id="53b93-137">Infine, seleziona il pool di bordi e identifica se un pool di hop successivo è configurato sotto la **selezione dell'hop successivo**.</span><span class="sxs-lookup"><span data-stu-id="53b93-137">Finally, select the Edge pool and identify if a Next hop pool is configured below **Next hop selection**.</span></span>
    
    <span data-ttu-id="53b93-138">![Generatore di topologie - Selezione hop successivo](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Generatore di topologie - Selezione hop successivo")</span><span class="sxs-lookup"><span data-stu-id="53b93-138">![Topology Builder, Next hop selection](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Topology Builder, Next hop selection")</span></span>

<span data-ttu-id="53b93-139">**Verificare la configurazione legacy del partner federato XMPP**</span><span class="sxs-lookup"><span data-stu-id="53b93-139">**Verify legacy XMPP Federated Partner Configuration**</span></span>

1.  <span data-ttu-id="53b93-140">Dal server XMPP legacy, passare all'applet strumenti\\di amministrazione di servizi.</span><span class="sxs-lookup"><span data-stu-id="53b93-140">From the legacy XMPP server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="53b93-141">Verificare che il servizio gateway XMPP di Office Communications Server sia stato avviato.</span><span class="sxs-lookup"><span data-stu-id="53b93-141">Verify that the Office Communications Server XMPP Gateway service is started.</span></span>
    
    <span data-ttu-id="53b93-142">![Servizio gateway XMPP di Office Communications Server](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Servizio gateway XMPP di Office Communications Server")</span><span class="sxs-lookup"><span data-stu-id="53b93-142">![Office Communications Server XMPP Gateway Service](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP Gateway Service")</span></span>

</div>

<span> </span>

</div>

</div>

</div>


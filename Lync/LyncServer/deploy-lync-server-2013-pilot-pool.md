---
title: Distribuire Lync Server 2013 Pilot pool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: a81aba1e-e636-434b-8c56-4150435bb55d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205144(v=OCS.15)
ms:contentKeyID: 48185028
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93fb3c5062cc1f817d3de7b869f57600178ad454
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974534"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="d06a4-102">Distribuire Lync Server 2013 Pilot pool</span><span class="sxs-lookup"><span data-stu-id="d06a4-102">Deploy Lync Server 2013 pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d06a4-103">_**Argomento Ultima modifica:** 2013-11-22_</span><span class="sxs-lookup"><span data-stu-id="d06a4-103">_**Topic Last Modified:** 2013-11-22_</span></span>

<span data-ttu-id="d06a4-104">Uno dei primi passaggi necessari per la migrazione a Lync Server 2013 consiste nel distribuire un pool pilota.</span><span class="sxs-lookup"><span data-stu-id="d06a4-104">One of the first steps required for migration to Lync Server 2013 is to deploy a pilot pool.</span></span> <span data-ttu-id="d06a4-105">Il pool di piloti è il punto in cui è possibile testare la coesistenza di Lync Server 2013 con la distribuzione di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="d06a4-105">The pilot pool is where you test coexistence of Lync Server 2013 with your Lync Server 2010 deployment.</span></span> <span data-ttu-id="d06a4-106">La coesistenza è uno stato temporaneo che dura fino a quando non si sono spostati tutti gli utenti e i pool in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d06a4-106">Coexistence is a temporary state that lasts until you have moved all users and pools to Lync Server 2013.</span></span>

<span data-ttu-id="d06a4-107">Quando si distribuisce un pool pilota, si usa la procedura guidata Definisci nuovo pool di front-end.</span><span class="sxs-lookup"><span data-stu-id="d06a4-107">When you deploy a pilot pool, you use the Define New Front End Pool wizard.</span></span> <span data-ttu-id="d06a4-108">È consigliabile distribuire le stesse funzionalità e i carichi di lavoro nel pool di piloti di Lync Server 2013 nel pool di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="d06a4-108">You should deploy the same features and workloads in your Lync Server 2013 pilot pool that you have in your Lync Server 2010 pool.</span></span> <span data-ttu-id="d06a4-109">Se si è distribuito server di archiviazione, server di monitoraggio o System Center Operations Manager per l'archiviazione o il monitoraggio dell'ambiente Lync Server 2010 e si vuole continuare l'archiviazione o il monitoraggio durante la migrazione, è necessario distribuirli anche funzionalità nell'ambiente pilota.</span><span class="sxs-lookup"><span data-stu-id="d06a4-109">If you deployed Archiving Server, Monitoring Server, or System Center Operations Manager for archiving or monitoring your Lync Server 2010 environment, and you want to continue archiving or monitoring throughout the migration, you need to also deploy these features in your pilot environment.</span></span> <span data-ttu-id="d06a4-110">La versione distribuita per archiviare o monitorare l'ambiente Lync Server 2010 non acquisisce i dati nell'ambiente Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d06a4-110">The version you deployed to archive or monitor your Lync Server 2010 environment will not capture data in your Lync Server 2013 environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d06a4-111">La procedura seguente illustra le caratteristiche e le impostazioni da tenere in considerazione nell'ambito del processo di distribuzione del pool pilota globale.</span><span class="sxs-lookup"><span data-stu-id="d06a4-111">The following procedure discusses features and settings you should consider as part of your overall pilot pool deployment process.</span></span> <span data-ttu-id="d06a4-112">Questa sezione evidenzia solo i punti chiave da tenere in considerazione nell'ambito della distribuzione del pool pilota.</span><span class="sxs-lookup"><span data-stu-id="d06a4-112">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="d06a4-113">Per la procedura dettagliata, vedere la guida alla distribuzione di <A href="lync-server-2013-deploying-lync-server.md">Lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="d06a4-113">For detailed steps, refer to the <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> deployment guide.</span></span>



</div>

<span data-ttu-id="d06a4-114">**Per distribuire un pool di piloti di Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="d06a4-114">**To deploy a Lync Server 2013 pilot pool**</span></span>

1.  <span data-ttu-id="d06a4-115">Accedere al computer in cui è installato Generatore di topologia come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="d06a4-115">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="d06a4-116">Espandere l'albero fino a raggiungere i pool di front end di **Lync Server 2013** **Enterprise Edition**.</span><span class="sxs-lookup"><span data-stu-id="d06a4-116">Expand the tree until you reach **Lync Server 2013** **Enterprise Edition Front End pools**.</span></span>

3.  <span data-ttu-id="d06a4-117">Fare clic con il pulsante destro del mouse su pool **front-end Enterprise Edition**e scegliere **nuovo pool Front-End**.</span><span class="sxs-lookup"><span data-stu-id="d06a4-117">Right click **Enterprise Edition Front End pools**, and select **New Front End Pool**.</span></span>
    
    <span data-ttu-id="d06a4-118">![](images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "Sottomenu selezione") pool server Builder topologia</span><span class="sxs-lookup"><span data-stu-id="d06a4-118">![Topology Builder Server pool selection submenu](images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "Topology Builder Server pool selection submenu")</span></span>

4.  <span data-ttu-id="d06a4-119">Immettere il nome di dominio completo del pool.</span><span class="sxs-lookup"><span data-stu-id="d06a4-119">Enter the pool FQDN.</span></span> <span data-ttu-id="d06a4-120">Quando si definisce il pool pilota, è possibile scegliere di distribuire un pool di front-end Enterprise Edition o un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="d06a4-120">When you define your pilot pool, you can choose to deploy an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="d06a4-121">Lync Server 2013 non richiede che le caratteristiche del pool pilota corrispondano a quelle distribuite nel pool legacy.</span><span class="sxs-lookup"><span data-stu-id="d06a4-121">Lync Server 2013 does not require that your pilot pool features match what was deployed in your legacy pool.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="d06a4-122">Il nome di dominio completo (FQDN) del pool o del server definito per il pool pilota deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="d06a4-122">The pool or server fully qualified domain name (FQDN) that you define for the pilot pool must be unique.</span></span> <span data-ttu-id="d06a4-123">Non può corrispondere al nome del pool di Lync Server 2010 attualmente distribuito o di qualsiasi altro server attualmente distribuito.</span><span class="sxs-lookup"><span data-stu-id="d06a4-123">It cannot match the name of the currently deployed Lync Server 2010 pool, or any other servers currently deployed.</span></span>

    
    </div>
    
    <span data-ttu-id="d06a4-124">![Definire la nuova procedura guidata pool di front end Wizard FQDN](images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "")</span><span class="sxs-lookup"><span data-stu-id="d06a4-124">![Define New Front End Pool Wizard FQDN page](images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "Define New Front End Pool Wizard FQDN page")</span></span>

5.  <span data-ttu-id="d06a4-125">Nella pagina **selezionare le caratteristiche** selezionare le caselle di controllo relative alle caratteristiche desiderate in questo pool di front-end.</span><span class="sxs-lookup"><span data-stu-id="d06a4-125">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="d06a4-126">Ad esempio, se si stanno distribuendo solo le funzionalità di messaggistica istantanea e presenza, è necessario selezionare la casella di controllo conferenza per consentire la messaggistica istantanea a più parti, ma non selezionare le caselle di controllo per le conferenze telefoniche con accesso esterno, VoIP aziendale o di ammissione alle chiamate. perché rappresentano funzionalità di conferenza vocale, video e collaborative.</span><span class="sxs-lookup"><span data-stu-id="d06a4-126">For example, if you are deploying only instant messaging (IM) and presence features, you would select the Conferencing check box to allow multiparty IM, but would not select the Dial-in (PSTN) conferencing, Enterprise Voice, or Call Admission Control check boxes, because they represent voice, video, and collaborative conferencing features.</span></span> <span data-ttu-id="d06a4-127">Per altre informazioni sulla selezione di funzionalità, vedere [definire e configurare un pool Front end o un server Standard Edition in Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d06a4-127">For additional information on selecting features, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.</span></span>
    
    <span data-ttu-id="d06a4-128">![Pool di front-end selezionare le caratteristiche pagina](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "pool di front end per selezionare le caratteristiche")</span><span class="sxs-lookup"><span data-stu-id="d06a4-128">![Front End Pool Select features page](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Front End Pool Select features page")</span></span>

6.  <span data-ttu-id="d06a4-129">Nella pagina **Selezione ruoli server collocati** è consigliabile collocare il Mediation Server in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d06a4-129">On the **Select collocated server roles** page, we recommend you collocate the Mediation Server in Lync Server 2013.</span></span> <span data-ttu-id="d06a4-130">Quando si unisce una topologia legacy a Lync Server 2013, è necessario prima di tutto collocare il server di mediazione Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="d06a4-130">When merging a legacy topology with Lync Server 2013, we require that you first collocate the Lync Server 2010 Mediation Server.</span></span> <span data-ttu-id="d06a4-131">Dopo l'Unione delle topologie e la configurazione di Lync Server 2013 Mediation Server, è possibile decidere se conservare il Mediation Server collocato o modificarlo in un server autonomo quando si sposta il ruolo di Mediation Server in Lync Server 2013 più avanti nella distribuzione processo.</span><span class="sxs-lookup"><span data-stu-id="d06a4-131">After merging the topologies and configuring the Lync Server 2013 Mediation Server, you can decide whether to keep the collocated Mediation Server, or change it to a stand-alone server when you move the Mediation Server role to Lync Server 2013 later in the deployment process.</span></span>
    
    <span data-ttu-id="d06a4-132">![Pool di front-end selezionare ruoli server collocati pagina](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "pool Front-End selezionare la pagina ruoli server collocati")</span><span class="sxs-lookup"><span data-stu-id="d06a4-132">![Front End Pool Select collocated server roles page](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Front End Pool Select collocated server roles page")</span></span>

7.  <span data-ttu-id="d06a4-133">Nella pagina **associa i ruoli del server con questa pagina del pool Front-End** , durante la distribuzione del pool pilota, non scegliere l'opzione **Abilita un pool di bordi da usare per il componente multimediale di questo pool di front-end** .</span><span class="sxs-lookup"><span data-stu-id="d06a4-133">On the **Associate server roles with this Front End pool** page, during pilot pool deployment, do not choose the **Enable an Edge pool to be used by the media component of this Front End pool** option.</span></span> <span data-ttu-id="d06a4-134">Si tratta di una caratteristica che verrà abilitata e riportata online in una fase successiva della migrazione.</span><span class="sxs-lookup"><span data-stu-id="d06a4-134">This is a feature you will enable and bring online in a later phase of migration.</span></span> <span data-ttu-id="d06a4-135">Mantieni questa impostazione deselezionata per il momento.</span><span class="sxs-lookup"><span data-stu-id="d06a4-135">Keep this setting cleared for now.</span></span>
    
    <span data-ttu-id="d06a4-136">![Associare ruoli del server con]i ruoli del server associato alla pagina del pool Front End(images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "con la pagina del pool Front-End")</span><span class="sxs-lookup"><span data-stu-id="d06a4-136">![Associate server roles with Front End pool page](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Associate server roles with Front End pool page")</span></span>

8.  <span data-ttu-id="d06a4-137">Nella pagina **selezionare un server di Office Web Apps** fare clic su **nuovo**e specificare il nome di dominio completo del server applicazioni.</span><span class="sxs-lookup"><span data-stu-id="d06a4-137">On the **Select an Office Web Apps Server** page, click **New**, and specify the FQDN of the application server.</span></span>
    
    <span data-ttu-id="d06a4-138">![Definire le nuove proprietà FQDN del server Office Web Apps](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "definire le nuove proprietà FQDN del server Office Web Apps")</span><span class="sxs-lookup"><span data-stu-id="d06a4-138">![Define New Office Web Apps Server FQDN properties](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Define New Office Web Apps Server FQDN properties")</span></span>

9.  <span data-ttu-id="d06a4-139">Nella pagina **Definisci archiviazione SQL Server Store** , quando si definisce l'archivio di SQL Server per l'archiviazione e il monitoraggio di Lync Server, selezionare l'istanza di SQL Server creata in precedenza per lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d06a4-139">On the **Define the Archiving SQL Server store** page, when defining the SQL Server store for both Lync Server Archiving and Monitoring, select the SQL Server instance created earlier for Lync Server 2013.</span></span>
    
    <span data-ttu-id="d06a4-140">![Definire la pagina archiviazione di SQL Server Store](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "definire la pagina archiviazione di SQL Server Store")</span><span class="sxs-lookup"><span data-stu-id="d06a4-140">![Define Archiving SQL Server store page](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Define Archiving SQL Server store page")</span></span>

10. <span data-ttu-id="d06a4-141">Per pubblicare la topologia, fare clic con il pulsante destro del mouse sul nodo **Lync Server** e quindi scegliere **Pubblica topologia**.</span><span class="sxs-lookup"><span data-stu-id="d06a4-141">To publish your topology, right-click the **Lync Server** node, and then click **Publish Topology**.</span></span>
    
    <span data-ttu-id="d06a4-142">![Generatore]di topologia con un generatore di topologia configurato che(images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "Visualizza una topologia configurata")</span><span class="sxs-lookup"><span data-stu-id="d06a4-142">![Topology Builder displaying a configured topology](images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "Topology Builder displaying a configured topology")</span></span>

11. <span data-ttu-id="d06a4-143">Al termine del processo di pubblicazione, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="d06a4-143">When the publish process has completed, click **Finish**.</span></span>

<span data-ttu-id="d06a4-144">Per installare una copia locale dell'archivio di configurazione e avviare i servizi necessari, vedere [configurazione dei server front-end e dei pool Front end per Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d06a4-144">To install a local copy of the configuration store and start the required services, see [Setting up Front End Servers and Front End pools for Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.</span></span>


</div>

<span> </span>

</div>

</div>

</div>


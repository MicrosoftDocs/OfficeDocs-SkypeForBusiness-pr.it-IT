---
title: Distribuire il pool pilota di Lync Server 2013
description: Distribuire il pool pilota di Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: a81aba1e-e636-434b-8c56-4150435bb55d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205144(v=OCS.15)
ms:contentKeyID: 48185028
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a599cee1719f773ebbf3cf5a71405aa9b7259261
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550792"
---
# <a name="deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="e0d6e-103">Distribuire il pool pilota di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0d6e-103">Deploy Lync Server 2013 pilot pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0d6e-104">_**Ultimo argomento modificato:** 2013-11-22_</span><span class="sxs-lookup"><span data-stu-id="e0d6e-104">_**Topic Last Modified:** 2013-11-22_</span></span>

<span data-ttu-id="e0d6e-105">Uno dei primi passaggi necessari per la migrazione a Lync Server 2013 è la distribuzione di un pool pilota.</span><span class="sxs-lookup"><span data-stu-id="e0d6e-105">One of the first steps required for migration to Lync Server 2013 is to deploy a pilot pool.</span></span> <span data-ttu-id="e0d6e-106">Il pool pilota è il punto in cui è possibile testare la coesistenza di Lync Server 2013 con la distribuzione di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e0d6e-106">The pilot pool is where you test coexistence of Lync Server 2013 with your Lync Server 2010 deployment.</span></span> <span data-ttu-id="e0d6e-107">La coesistenza è uno stato temporaneo che dura fino a quando non sono stati spostati tutti gli utenti e i pool in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e0d6e-107">Coexistence is a temporary state that lasts until you have moved all users and pools to Lync Server 2013.</span></span>

<span data-ttu-id="e0d6e-108">Quando si distribuisce un pool pilota, utilizzare la procedura guidata Definisci nuovo pool Front End.</span><span class="sxs-lookup"><span data-stu-id="e0d6e-108">When you deploy a pilot pool, you use the Define New Front End Pool wizard.</span></span> <span data-ttu-id="e0d6e-109">È consigliabile distribuire le stesse caratteristiche e i carichi di lavoro nel pool pilota di Lync Server 2013 che è presente nel pool di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e0d6e-109">You should deploy the same features and workloads in your Lync Server 2013 pilot pool that you have in your Lync Server 2010 pool.</span></span> <span data-ttu-id="e0d6e-110">Se è stato distribuito il server di archiviazione, il Monitoring Server o System Center Operations Manager per l'archiviazione o il monitoraggio dell'ambiente Lync Server 2010 e si desidera continuare l'archiviazione o il monitoraggio durante la migrazione, è necessario distribuire queste funzionalità anche nell'ambiente pilota.</span><span class="sxs-lookup"><span data-stu-id="e0d6e-110">If you deployed Archiving Server, Monitoring Server, or System Center Operations Manager for archiving or monitoring your Lync Server 2010 environment, and you want to continue archiving or monitoring throughout the migration, you need to also deploy these features in your pilot environment.</span></span> <span data-ttu-id="e0d6e-111">La versione distribuita per archiviare o monitorare l'ambiente Lync Server 2010 non acquisisce i dati nell'ambiente Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e0d6e-111">The version you deployed to archive or monitor your Lync Server 2010 environment will not capture data in your Lync Server 2013 environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e0d6e-112">Nella procedura riportata di seguito vengono illustrate le funzionalità e le impostazioni che è necessario considerare come parte del processo complessivo di distribuzione del pool pilota.</span><span class="sxs-lookup"><span data-stu-id="e0d6e-112">The following procedure discusses features and settings you should consider as part of your overall pilot pool deployment process.</span></span> <span data-ttu-id="e0d6e-113">In questa sezione vengono evidenziati solo i punti chiave di cui è consigliabile tenere conto nell'ambito della distribuzione del pool pilota.</span><span class="sxs-lookup"><span data-stu-id="e0d6e-113">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="e0d6e-114">Per la procedura dettagliata, vedere la guida alla distribuzione di <A href="lync-server-2013-deploying-lync-server.md">Lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="e0d6e-114">For detailed steps, refer to the <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> deployment guide.</span></span>



</div>

<span data-ttu-id="e0d6e-115">**Per distribuire un pool pilota di Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="e0d6e-115">**To deploy a Lync Server 2013 pilot pool**</span></span>

1.  <span data-ttu-id="e0d6e-116">Accedere al computer in cui è installato Generatore di topologie come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="e0d6e-116">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="e0d6e-117">Espandere l'albero fino a raggiungere i **pool Front End**di **Lync Server 2013** Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="e0d6e-117">Expand the tree until you reach **Lync Server 2013** **Enterprise Edition Front End pools**.</span></span>

3.  <span data-ttu-id="e0d6e-118">Fare clic con il pulsante destro del mouse su **Pool Enterprise Edition Front End** e scegliere **Nuovo pool Front End**.</span><span class="sxs-lookup"><span data-stu-id="e0d6e-118">Right click **Enterprise Edition Front End pools**, and select **New Front End Pool**.</span></span>
    
    <span data-ttu-id="e0d6e-119">![Sottomenu della selezione del pool di server generatore di topologie](images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "Sottomenu della selezione del pool di server generatore di topologie")</span><span class="sxs-lookup"><span data-stu-id="e0d6e-119">![Topology Builder Server pool selection submenu](images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "Topology Builder Server pool selection submenu")</span></span>

4.  <span data-ttu-id="e0d6e-120">Immettere l'FQDN del pool.</span><span class="sxs-lookup"><span data-stu-id="e0d6e-120">Enter the pool FQDN.</span></span> <span data-ttu-id="e0d6e-121">Quando si definisce il pool pilota, è possibile scegliere di distribuire un pool Enterprise Edition front end o un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e0d6e-121">When you define your pilot pool, you can choose to deploy an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="e0d6e-122">Lync Server 2013 non richiede che le funzionalità del pool pilota corrispondano a quelle distribuite nel pool legacy.</span><span class="sxs-lookup"><span data-stu-id="e0d6e-122">Lync Server 2013 does not require that your pilot pool features match what was deployed in your legacy pool.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="e0d6e-123">Il nome di dominio completo (FQDN) del pool o del server definito per il pool pilota deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="e0d6e-123">The pool or server fully qualified domain name (FQDN) that you define for the pilot pool must be unique.</span></span> <span data-ttu-id="e0d6e-124">Non può corrispondere al nome del pool di Lync Server 2010 attualmente distribuito o a qualsiasi altro server attualmente distribuito.</span><span class="sxs-lookup"><span data-stu-id="e0d6e-124">It cannot match the name of the currently deployed Lync Server 2010 pool, or any other servers currently deployed.</span></span>

    
    </div>
    
    <span data-ttu-id="e0d6e-125">![Pagina di definizione del nuovo FQDN del pool di front end Wizard](images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "Pagina di definizione del nuovo FQDN del pool di front end Wizard")</span><span class="sxs-lookup"><span data-stu-id="e0d6e-125">![Define New Front End Pool Wizard FQDN page](images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "Define New Front End Pool Wizard FQDN page")</span></span>

5.  <span data-ttu-id="e0d6e-126">Nella pagina **Selezionare funzionalità** selezionare le caselle di controllo relative alle funzionalità che si desidera distribuire in questo pool Front End.</span><span class="sxs-lookup"><span data-stu-id="e0d6e-126">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="e0d6e-127">Se ad esempio si distribuiscono solo le funzionalità di Messaggistica istantanea e presenza, si selezionerà la casella di controllo per il servizio di conferenza in modo da consentire sessioni IM tra più utenti, ma non quelle relative a funzionalità per conferenze vocali, video e collaborative come Conferenza con accesso esterno (PSTN), VoIP aziendale o Controllo di ammissione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="e0d6e-127">For example, if you are deploying only instant messaging (IM) and presence features, you would select the Conferencing check box to allow multiparty IM, but would not select the Dial-in (PSTN) conferencing, Enterprise Voice, or Call Admission Control check boxes, because they represent voice, video, and collaborative conferencing features.</span></span> <span data-ttu-id="e0d6e-128">Per ulteriori informazioni sulla selezione di funzionalità, vedere [define and Configure a front end pool or Standard Edition server in Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e0d6e-128">For additional information on selecting features, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.</span></span>
    
    <span data-ttu-id="e0d6e-129">![Pagina di selezione delle funzionalità del pool Front End](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Pagina di selezione delle funzionalità del pool Front End")</span><span class="sxs-lookup"><span data-stu-id="e0d6e-129">![Front End Pool Select features page](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Front End Pool Select features page")</span></span>

6.  <span data-ttu-id="e0d6e-130">Nella pagina **Selezione ruoli server collocati** , è consigliabile collocare il Mediation Server in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e0d6e-130">On the **Select collocated server roles** page, we recommend you collocate the Mediation Server in Lync Server 2013.</span></span> <span data-ttu-id="e0d6e-131">Quando si esegue l'Unione di una topologia legacy con Lync Server 2013, è necessario innanzitutto collocare Lync Server 2010 Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="e0d6e-131">When merging a legacy topology with Lync Server 2013, we require that you first collocate the Lync Server 2010 Mediation Server.</span></span> <span data-ttu-id="e0d6e-132">Dopo l'Unione delle topologie e la configurazione di Lync Server 2013 Mediation Server, è possibile decidere se mantenere il Mediation Server collocato o modificarlo in un server autonomo quando si sposta il ruolo Mediation Server in Lync Server 2013 più avanti nel processo di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e0d6e-132">After merging the topologies and configuring the Lync Server 2013 Mediation Server, you can decide whether to keep the collocated Mediation Server, or change it to a stand-alone server when you move the Mediation Server role to Lync Server 2013 later in the deployment process.</span></span>
    
    <span data-ttu-id="e0d6e-133">![Pagina di selezione dei ruoli server collocati nel pool Front End](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Pagina di selezione dei ruoli server collocati nel pool Front End")</span><span class="sxs-lookup"><span data-stu-id="e0d6e-133">![Front End Pool Select collocated server roles page](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Front End Pool Select collocated server roles page")</span></span>

7.  <span data-ttu-id="e0d6e-p108">Nella pagina **Associare ruoli server al pool Front End** non scegliere l'opzione **Abilita un pool di server perimetrali utilizzato dal componente multimediale di questo pool Front End** durante la distribuzione del pool pilota. Questa funzionalità verrà abilitata e portata online in una fase successiva della migrazione, pertanto mantenere deselezionata questa opzione per ora.</span><span class="sxs-lookup"><span data-stu-id="e0d6e-p108">On the **Associate server roles with this Front End pool** page, during pilot pool deployment, do not choose the **Enable an Edge pool to be used by the media component of this Front End pool** option. This is a feature you will enable and bring online in a later phase of migration. Keep this setting cleared for now.</span></span>
    
    <span data-ttu-id="e0d6e-137">![Associare i ruoli del server alla pagina del pool Front End](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Associare i ruoli del server alla pagina del pool Front End")</span><span class="sxs-lookup"><span data-stu-id="e0d6e-137">![Associate server roles with Front End pool page](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Associate server roles with Front End pool page")</span></span>

8.  <span data-ttu-id="e0d6e-138">Nella pagina **Selezionare un server Office Web Apps** fare clic su **Nuovo** e specificare l'FQDN del server applicazioni.</span><span class="sxs-lookup"><span data-stu-id="e0d6e-138">On the **Select an Office Web Apps Server** page, click **New**, and specify the FQDN of the application server.</span></span>
    
    <span data-ttu-id="e0d6e-139">![Definire nuove proprietà FQDN del server Office Web Apps](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Definire nuove proprietà FQDN del server Office Web Apps")</span><span class="sxs-lookup"><span data-stu-id="e0d6e-139">![Define New Office Web Apps Server FQDN properties](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Define New Office Web Apps Server FQDN properties")</span></span>

9.  <span data-ttu-id="e0d6e-140">Nella pagina **definire l'archivio SQL Server di archiviazione** , quando si definisce l'archivio SQL Server per l'archiviazione e il monitoraggio di Lync Server, selezionare l'istanza di SQL Server creata in precedenza per lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e0d6e-140">On the **Define the Archiving SQL Server store** page, when defining the SQL Server store for both Lync Server Archiving and Monitoring, select the SQL Server instance created earlier for Lync Server 2013.</span></span>
    
    <span data-ttu-id="e0d6e-141">![Pagina per la definizione dell'archivio SQL Server di archiviazione](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Pagina per la definizione dell'archivio SQL Server di archiviazione")</span><span class="sxs-lookup"><span data-stu-id="e0d6e-141">![Define Archiving SQL Server store page](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Define Archiving SQL Server store page")</span></span>

10. <span data-ttu-id="e0d6e-142">Per pubblicare la topologia, fare clic con il pulsante destro del mouse sul nodo **Lync Server** e quindi scegliere **Pubblica topologia**.</span><span class="sxs-lookup"><span data-stu-id="e0d6e-142">To publish your topology, right-click the **Lync Server** node, and then click **Publish Topology**.</span></span>
    
    <span data-ttu-id="e0d6e-143">![Generatore di topologie che visualizza una topologia configurata](images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "Generatore di topologie che visualizza una topologia configurata")</span><span class="sxs-lookup"><span data-stu-id="e0d6e-143">![Topology Builder displaying a configured topology](images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "Topology Builder displaying a configured topology")</span></span>

11. <span data-ttu-id="e0d6e-144">Al termine del processo di pubblicazione, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="e0d6e-144">When the publish process has completed, click **Finish**.</span></span>

<span data-ttu-id="e0d6e-145">Per installare una copia locale dell'archivio di configurazione e avviare i servizi richiesti, vedere [Setting up front end servers and front end pools for Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e0d6e-145">To install a local copy of the configuration store and start the required services, see [Setting up Front End Servers and Front End pools for Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.</span></span>


</div>

<span> </span>

</div>

</div>

</div>


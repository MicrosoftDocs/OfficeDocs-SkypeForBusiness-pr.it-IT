---
title: Distribuire Lync Server 2013 Pilot pool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: 19c27053-8b21-401f-ad91-75c2dd355e91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204718(v=OCS.15)
ms:contentKeyID: 48183539
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5e9068ca3ff5a2827991869598a2066473cc5af
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981022"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="f9b1d-102">Distribuire Lync Server 2013 Pilot pool</span><span class="sxs-lookup"><span data-stu-id="f9b1d-102">Deploy Lync Server 2013 pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9b1d-103">_**Argomento Ultima modifica:** 2013-11-22_</span><span class="sxs-lookup"><span data-stu-id="f9b1d-103">_**Topic Last Modified:** 2013-11-22_</span></span>

<span data-ttu-id="f9b1d-104">Uno dei primi passaggi necessari per la migrazione a Lync Server 2013 consiste nel distribuire un pool pilota.</span><span class="sxs-lookup"><span data-stu-id="f9b1d-104">One of the first steps required for migration to Lync Server 2013 is to deploy a pilot pool.</span></span> <span data-ttu-id="f9b1d-105">Il pool di piloti è il punto in cui è possibile testare la coesistenza di Lync Server 2013 con la distribuzione di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f9b1d-105">The pilot pool is where you test coexistence of Lync Server 2013 with your Office Communications Server 2007 R2 deployment.</span></span> <span data-ttu-id="f9b1d-106">La coesistenza è uno stato temporaneo che dura fino a quando non si sono spostati tutti gli utenti e i pool in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f9b1d-106">Coexistence is a temporary state that lasts until you have moved all users and pools to Lync Server 2013.</span></span>

<span data-ttu-id="f9b1d-107">Quando si distribuisce un pool pilota, si usa la procedura guidata Definisci nuovo pool di front-end.</span><span class="sxs-lookup"><span data-stu-id="f9b1d-107">When you deploy a pilot pool, you use the Define New Front End Pool wizard.</span></span> <span data-ttu-id="f9b1d-108">È consigliabile distribuire le stesse funzionalità e i carichi di lavoro nel pool di piloti di Lync Server 2013 nel pool di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f9b1d-108">You should deploy the same features and workloads in your Lync Server 2013 pilot pool that you have in your Office Communications Server 2007 R2 pool.</span></span> <span data-ttu-id="f9b1d-109">Se si è distribuito server di archiviazione, server di monitoraggio o System Center Operations Manager per l'archiviazione o il monitoraggio dell'ambiente Office Communications Server 2007 R2 e si vuole continuare l'archiviazione o il monitoraggio durante la migrazione, è necessario distribuire anche queste funzionalità nell'ambiente pilota.</span><span class="sxs-lookup"><span data-stu-id="f9b1d-109">If you deployed Archiving Server, Monitoring Server, or System Center Operations Manager for archiving or monitoring your Office Communications Server 2007 R2 environment, and you want to continue archiving or monitoring throughout the migration, you need to also deploy these features in your pilot environment.</span></span> <span data-ttu-id="f9b1d-110">La versione distribuita per archiviare o monitorare l'ambiente Office Communications Server 2007 R2 non acquisisce i dati nell'ambiente Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f9b1d-110">The version you deployed to archive or monitor your Office Communications Server 2007 R2 environment will not capture data in your Lync Server 2013 environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f9b1d-111">La procedura seguente illustra le caratteristiche e le impostazioni da tenere in considerazione nell'ambito del processo di distribuzione del pool pilota globale.</span><span class="sxs-lookup"><span data-stu-id="f9b1d-111">The following procedure discusses features and settings you should consider as part of your overall pilot pool deployment process.</span></span> <span data-ttu-id="f9b1d-112">Questa sezione evidenzia solo i punti chiave da tenere in considerazione nell'ambito della distribuzione del pool pilota.</span><span class="sxs-lookup"><span data-stu-id="f9b1d-112">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="f9b1d-113">Per la procedura dettagliata, vedere la guida alla distribuzione di <A href="lync-server-2013-deploying-lync-server.md">Lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="f9b1d-113">For detailed steps, refer to the <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> deployment guide.</span></span>



</div>

<span data-ttu-id="f9b1d-114">**Per distribuire un pool di piloti di Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="f9b1d-114">**To deploy a Lync Server 2013 pilot pool**</span></span>

1.  <span data-ttu-id="f9b1d-115">Accedere al computer in cui è installato Generatore di topologia come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="f9b1d-115">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="f9b1d-116">Aprire Generatore di topologie e scegliere di creare una nuova topologia.</span><span class="sxs-lookup"><span data-stu-id="f9b1d-116">Open Topology Builder and choose to create a new topology.</span></span>

3.  <span data-ttu-id="f9b1d-117">Immettere il dominio SIP principale.</span><span class="sxs-lookup"><span data-stu-id="f9b1d-117">Enter the primary SIP domain.</span></span>
    
    <span data-ttu-id="f9b1d-118">![Creare una nuova topologia, definire la pagina del dominio principale](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "creare una nuova topologia, definire la pagina del dominio principale")</span><span class="sxs-lookup"><span data-stu-id="f9b1d-118">![Create New Topology, Define primary domain page](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "Create New Topology, Define primary domain page")</span></span>

4.  <span data-ttu-id="f9b1d-119">Continuare a completare la procedura guidata fino a raggiungere la procedura guidata **Definisci il nuovo pool Front-End** .</span><span class="sxs-lookup"><span data-stu-id="f9b1d-119">Continue completing the wizard until you reach the **Define the New Front End pool** wizard.</span></span> <span data-ttu-id="f9b1d-120">Fare clic su Avanti.</span><span class="sxs-lookup"><span data-stu-id="f9b1d-120">Click Next.</span></span>

5.  <span data-ttu-id="f9b1d-121">Immettere il nome di dominio completo del pool.</span><span class="sxs-lookup"><span data-stu-id="f9b1d-121">Enter the pool FQDN.</span></span> <span data-ttu-id="f9b1d-122">Quando si definisce il pool pilota, è possibile scegliere di distribuire un pool di front-end Enterprise Edition o un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f9b1d-122">When you define your pilot pool, you can choose to deploy an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="f9b1d-123">Lync Server 2013 non richiede che le caratteristiche del pool pilota corrispondano a quelle distribuite nel pool legacy.</span><span class="sxs-lookup"><span data-stu-id="f9b1d-123">Lync Server 2013 does not require that your pilot pool features match what was deployed in your legacy pool.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="f9b1d-124">Il nome di dominio completo (FQDN) del pool o del server definito per il pool pilota deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="f9b1d-124">The pool or server fully qualified domain name (FQDN) that you define for the pilot pool must be unique.</span></span> <span data-ttu-id="f9b1d-125">Non può corrispondere al nome del pool di Office Communications Server 2007 R2 attualmente distribuito o di qualsiasi altro server attualmente distribuito.</span><span class="sxs-lookup"><span data-stu-id="f9b1d-125">It cannot match the name of the currently deployed Office Communications Server 2007 R2 pool, or any other servers currently deployed.</span></span>

    
    </div>
    
    <span data-ttu-id="f9b1d-126">![Definire la pagina FQDN del pool di front-end](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "definire la pagina FQDN del pool Front-End")</span><span class="sxs-lookup"><span data-stu-id="f9b1d-126">![Define the Front End pool FQDN page](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "Define the Front End pool FQDN page")</span></span>

6.  <span data-ttu-id="f9b1d-127">Definire il computer che verrà aggiunto al pool.</span><span class="sxs-lookup"><span data-stu-id="f9b1d-127">Define the computer that will be added to the pool.</span></span>
    
    <span data-ttu-id="f9b1d-128">![Definire la finestra di dialogo nuovo pool Front End](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "")</span><span class="sxs-lookup"><span data-stu-id="f9b1d-128">![Define New Front End Pool dialog](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "Define New Front End Pool dialog")</span></span>

7.  <span data-ttu-id="f9b1d-129">Nella pagina **selezionare le caratteristiche** selezionare le caselle di controllo relative alle caratteristiche desiderate in questo pool di front-end.</span><span class="sxs-lookup"><span data-stu-id="f9b1d-129">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="f9b1d-130">Ad esempio, se si stanno distribuendo solo le funzionalità di messaggistica istantanea e presenza, è necessario selezionare la casella di controllo conferenza per consentire la messaggistica istantanea a più parti, ma non selezionare le caselle di controllo per le conferenze telefoniche con accesso esterno, VoIP aziendale o di ammissione alle chiamate. perché rappresentano funzionalità di conferenza vocale, video e collaborative.</span><span class="sxs-lookup"><span data-stu-id="f9b1d-130">For example, if you are deploying only instant messaging (IM) and presence features, you would select the Conferencing check box to allow multiparty IM, but would not select the Dial-in (PSTN) conferencing, Enterprise Voice, or Call Admission Control check boxes, because they represent voice, video, and collaborative conferencing features.</span></span> <span data-ttu-id="f9b1d-131">Per altre informazioni sulla selezione di funzionalità, vedere [definire e configurare un pool Front end o un server Standard Edition in Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="f9b1d-131">For additional information on selecting features, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.</span></span>
    
    <span data-ttu-id="f9b1d-132">![Pool di front-end selezionare le caratteristiche pagina](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "pool di front end per selezionare le caratteristiche")</span><span class="sxs-lookup"><span data-stu-id="f9b1d-132">![Front End Pool Select features page](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Front End Pool Select features page")</span></span>

8.  <span data-ttu-id="f9b1d-133">Nella pagina **Selezione ruoli server collocati** è consigliabile collocare il Mediation Server in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f9b1d-133">On the **Select collocated server roles** page, we recommend you collocate the Mediation Server in Lync Server 2013.</span></span> <span data-ttu-id="f9b1d-134">Quando si unisce una topologia legacy a Lync Server 2013, è necessario prima di tutto collocare Office Communications Server 2007 R2 Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="f9b1d-134">When merging a legacy topology with Lync Server 2013, we require that you first collocate the Office Communications Server 2007 R2 Mediation Server.</span></span> <span data-ttu-id="f9b1d-135">Dopo l'Unione delle topologie e la configurazione di Lync Server 2013 Mediation Server, è possibile decidere se conservare il Mediation Server collocato o modificarlo in un server autonomo quando si sposta il ruolo di Mediation Server in Lync Server 2013 più avanti nella distribuzione processo.</span><span class="sxs-lookup"><span data-stu-id="f9b1d-135">After merging the topologies and configuring the Lync Server 2013 Mediation Server, you can decide whether to keep the collocated Mediation Server, or change it to a stand-alone server when you move the Mediation Server role to Lync Server 2013 later in the deployment process.</span></span>
    
    <span data-ttu-id="f9b1d-136">![Pool di front-end selezionare ruoli server collocati pagina](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "pool Front-End selezionare la pagina ruoli server collocati")</span><span class="sxs-lookup"><span data-stu-id="f9b1d-136">![Front End Pool Select collocated server roles page](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Front End Pool Select collocated server roles page")</span></span>

9.  <span data-ttu-id="f9b1d-137">Nella pagina **associa i ruoli del server con questa pagina del pool Front-End** , durante la distribuzione del pool pilota, non scegliere l'opzione **Abilita un pool di bordi da usare per il componente multimediale di questo pool di front-end** .</span><span class="sxs-lookup"><span data-stu-id="f9b1d-137">On the **Associate server roles with this Front End pool** page, during pilot pool deployment, do not choose the **Enable an Edge pool to be used by the media component of this Front End pool** option.</span></span> <span data-ttu-id="f9b1d-138">Si tratta di una caratteristica che verrà abilitata e riportata online in una fase successiva della migrazione.</span><span class="sxs-lookup"><span data-stu-id="f9b1d-138">This is a feature you will enable and bring online in a later phase of migration.</span></span> <span data-ttu-id="f9b1d-139">Mantieni questa impostazione deselezionata per il momento.</span><span class="sxs-lookup"><span data-stu-id="f9b1d-139">Keep this setting cleared for now.</span></span>
    
    <span data-ttu-id="f9b1d-140">![Associare ruoli del server con]i ruoli del server associato alla pagina del pool Front End(images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "con la pagina del pool Front-End")</span><span class="sxs-lookup"><span data-stu-id="f9b1d-140">![Associate server roles with Front End pool page](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Associate server roles with Front End pool page")</span></span>

10. <span data-ttu-id="f9b1d-141">Nella pagina **selezionare un server di Office Web Apps** fare clic su **nuovo**e specificare il nome di dominio completo del server applicazioni.</span><span class="sxs-lookup"><span data-stu-id="f9b1d-141">On the **Select an Office Web Apps Server** page, click **New**, and specify the FQDN of the application server.</span></span>
    
    <span data-ttu-id="f9b1d-142">![Definire le nuove proprietà FQDN del server Office Web Apps](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "definire le nuove proprietà FQDN del server Office Web Apps")</span><span class="sxs-lookup"><span data-stu-id="f9b1d-142">![Define New Office Web Apps Server FQDN properties](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Define New Office Web Apps Server FQDN properties")</span></span>

11. <span data-ttu-id="f9b1d-143">Nella pagina **Definisci archiviazione SQL Server Store** selezionare l'istanza di SQL Server creata in precedenza per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f9b1d-143">On the **Define the Archiving SQL Server store** page, select the SQL Server instance created earlier for Lync Server 2013.</span></span>
    
    <span data-ttu-id="f9b1d-144">![Definire la pagina archiviazione di SQL Server Store](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "definire la pagina archiviazione di SQL Server Store")</span><span class="sxs-lookup"><span data-stu-id="f9b1d-144">![Define Archiving SQL Server store page](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Define Archiving SQL Server store page")</span></span>

12. <span data-ttu-id="f9b1d-145">Nella pagina **Definisci il monitoraggio di SQL Server Store** selezionare l'istanza di SQL Server creata in precedenza per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f9b1d-145">On the **Define the Monitoring SQL Server store** page, select the SQL Server instance created earlier for Lync Server 2013.</span></span> <span data-ttu-id="f9b1d-146">Fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="f9b1d-146">Click **Finish**.</span></span>

13. <span data-ttu-id="f9b1d-147">Dal nodo superiore di generatore di topologie fare clic con il pulsante destro del mouse su **Lync Server** e scegliere **modifica proprietà.**</span><span class="sxs-lookup"><span data-stu-id="f9b1d-147">From the top node of Topology Builder, right click **Lync Server** and click **Edit Properties.**</span></span> <span data-ttu-id="f9b1d-148">Fare clic su **URL semplici**.</span><span class="sxs-lookup"><span data-stu-id="f9b1d-148">Click **Simple URLs**.</span></span>

14. <span data-ttu-id="f9b1d-149">Aggiornare l' **URL di accesso amministrativo**.</span><span class="sxs-lookup"><span data-stu-id="f9b1d-149">Update the **Administrative access URL**.</span></span>
    
    <span data-ttu-id="f9b1d-150">Proprietà ![modifica, pagina URL semplici](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "modifica proprietà, pagina URL semplici")</span><span class="sxs-lookup"><span data-stu-id="f9b1d-150">![Edit Properties, Simple URLs page](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "Edit Properties, Simple URLs page")</span></span>
    
    <span data-ttu-id="f9b1d-151">Per altre informazioni sugli URL semplici, vedere l'argomento [modificare o configurare gli URL semplici in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="f9b1d-151">For additional information on Simple URLs, see the topic [Edit or configure simple URLs in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) in the Deployment documentation.</span></span>

15. <span data-ttu-id="f9b1d-152">Dalle **proprietà modifica**fare clic su **server di gestione centrale**.</span><span class="sxs-lookup"><span data-stu-id="f9b1d-152">From the **Edit Properties**, click **Central Management Server**.</span></span>

16. <span data-ttu-id="f9b1d-153">Nell'elenco a discesa selezionare il pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f9b1d-153">From the drop-down list, select the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="f9b1d-154">Proprietà ![modifica, pagina server di gestione centrale](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "modifica proprietà, pagina server di gestione centrale")</span><span class="sxs-lookup"><span data-stu-id="f9b1d-154">![Edit Properties, Central Management Server page](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "Edit Properties, Central Management Server page")</span></span>

17. <span data-ttu-id="f9b1d-155">Fare clic su OK per chiudere **la pagina Modifica proprietà** .</span><span class="sxs-lookup"><span data-stu-id="f9b1d-155">Click OK to close **the Edit Properties** page.</span></span>

18. <span data-ttu-id="f9b1d-156">Scegliere **Pubblica topologia**dal menu **azione** .</span><span class="sxs-lookup"><span data-stu-id="f9b1d-156">From the **Action** menu, select **Publish Topology**.</span></span>

19. <span data-ttu-id="f9b1d-157">Al termine del processo di pubblicazione, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="f9b1d-157">When the publish process has completed, click **Finish**.</span></span>

20. <span data-ttu-id="f9b1d-158">Tornando alla distribuzione guidata di Lync Server 2013, fare clic su **Installa o aggiorna Lync Server System**.</span><span class="sxs-lookup"><span data-stu-id="f9b1d-158">Returning to the Lync Server 2013 Deployment Wizard, click **Install or Update Lync Server System**.</span></span>
    
    <span data-ttu-id="f9b1d-159">Distribuzione guidata Lync Server ![2013 distribuzione guidata]di lync server(images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "2013")</span><span class="sxs-lookup"><span data-stu-id="f9b1d-159">![Lync Server 2013 Deployment Wizard](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Lync Server 2013 Deployment Wizard")</span></span>

<span data-ttu-id="f9b1d-160">Per installare una copia locale dell'archivio di configurazione e avviare i servizi necessari, vedere [configurazione dei server front-end e dei pool Front end per Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="f9b1d-160">To install a local copy of the configuration store and start the required services, see [Setting up Front End Servers and Front End pools for Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.</span></span>


</div>

<span> </span>

</div>

</div>

</div>


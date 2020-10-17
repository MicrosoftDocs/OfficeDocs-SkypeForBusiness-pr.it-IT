---
title: Distribuire il pool pilota di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: 19c27053-8b21-401f-ad91-75c2dd355e91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204718(v=OCS.15)
ms:contentKeyID: 48183539
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3df30b2aa45fe9519d724f904e8b375bed794042
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502958"
---
# <a name="deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="40e7e-102">Distribuire il pool pilota di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40e7e-102">Deploy Lync Server 2013 pilot pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40e7e-103">_**Ultimo argomento modificato:** 2013-11-22_</span><span class="sxs-lookup"><span data-stu-id="40e7e-103">_**Topic Last Modified:** 2013-11-22_</span></span>

<span data-ttu-id="40e7e-104">Uno dei primi passaggi necessari per la migrazione a Lync Server 2013 è la distribuzione di un pool pilota.</span><span class="sxs-lookup"><span data-stu-id="40e7e-104">One of the first steps required for migration to Lync Server 2013 is to deploy a pilot pool.</span></span> <span data-ttu-id="40e7e-105">Il pool pilota è il luogo in cui è possibile testare la coesistenza di Lync Server 2013 con la distribuzione di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="40e7e-105">The pilot pool is where you test coexistence of Lync Server 2013 with your Office Communications Server 2007 R2 deployment.</span></span> <span data-ttu-id="40e7e-106">La coesistenza è uno stato temporaneo che dura fino a quando non sono stati spostati tutti gli utenti e i pool in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="40e7e-106">Coexistence is a temporary state that lasts until you have moved all users and pools to Lync Server 2013.</span></span>

<span data-ttu-id="40e7e-107">Quando si distribuisce un pool pilota, utilizzare la procedura guidata Definisci nuovo pool Front End.</span><span class="sxs-lookup"><span data-stu-id="40e7e-107">When you deploy a pilot pool, you use the Define New Front End Pool wizard.</span></span> <span data-ttu-id="40e7e-108">È consigliabile distribuire le stesse caratteristiche e i carichi di lavoro nel pool pilota di Lync Server 2013 che è presente nel pool di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="40e7e-108">You should deploy the same features and workloads in your Lync Server 2013 pilot pool that you have in your Office Communications Server 2007 R2 pool.</span></span> <span data-ttu-id="40e7e-109">Se è stato distribuito il server di archiviazione, il Monitoring Server o System Center Operations Manager per l'archiviazione o il monitoraggio dell'ambiente Office Communications Server 2007 R2 e si desidera continuare l'archiviazione o il monitoraggio durante la migrazione, è necessario distribuire queste funzionalità anche nell'ambiente pilota.</span><span class="sxs-lookup"><span data-stu-id="40e7e-109">If you deployed Archiving Server, Monitoring Server, or System Center Operations Manager for archiving or monitoring your Office Communications Server 2007 R2 environment, and you want to continue archiving or monitoring throughout the migration, you need to also deploy these features in your pilot environment.</span></span> <span data-ttu-id="40e7e-110">La versione distribuita per archiviare o monitorare l'ambiente Office Communications Server 2007 R2 non acquisisce i dati nell'ambiente Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="40e7e-110">The version you deployed to archive or monitor your Office Communications Server 2007 R2 environment will not capture data in your Lync Server 2013 environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="40e7e-111">Nella procedura riportata di seguito vengono illustrate le funzionalità e le impostazioni che è necessario considerare come parte del processo complessivo di distribuzione del pool pilota.</span><span class="sxs-lookup"><span data-stu-id="40e7e-111">The following procedure discusses features and settings you should consider as part of your overall pilot pool deployment process.</span></span> <span data-ttu-id="40e7e-112">In questa sezione vengono evidenziati solo i punti chiave di cui è consigliabile tenere conto nell'ambito della distribuzione del pool pilota.</span><span class="sxs-lookup"><span data-stu-id="40e7e-112">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="40e7e-113">Per la procedura dettagliata, vedere la guida alla distribuzione di <A href="lync-server-2013-deploying-lync-server.md">Lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="40e7e-113">For detailed steps, refer to the <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> deployment guide.</span></span>



</div>

<span data-ttu-id="40e7e-114">**Per distribuire un pool pilota di Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="40e7e-114">**To deploy a Lync Server 2013 pilot pool**</span></span>

1.  <span data-ttu-id="40e7e-115">Accedere al computer in cui è installato Generatore di topologie come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="40e7e-115">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="40e7e-116">Aprire il Generatore di topologie e scegliere di creare una nuova topologia.</span><span class="sxs-lookup"><span data-stu-id="40e7e-116">Open Topology Builder and choose to create a new topology.</span></span>

3.  <span data-ttu-id="40e7e-117">Specificare il domino SIP primario.</span><span class="sxs-lookup"><span data-stu-id="40e7e-117">Enter the primary SIP domain.</span></span>
    
    <span data-ttu-id="40e7e-118">![Creare una nuova topologia, definire la pagina del dominio principale](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "Creare una nuova topologia, definire la pagina del dominio principale")</span><span class="sxs-lookup"><span data-stu-id="40e7e-118">![Create New Topology, Define primary domain page](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "Create New Topology, Define primary domain page")</span></span>

4.  <span data-ttu-id="40e7e-119">Continuare a eseguire la procedura guidata fino alla pagina **Definire il nuovo pool Front End**.</span><span class="sxs-lookup"><span data-stu-id="40e7e-119">Continue completing the wizard until you reach the **Define the New Front End pool** wizard.</span></span> <span data-ttu-id="40e7e-120">Fare clic su Avanti.</span><span class="sxs-lookup"><span data-stu-id="40e7e-120">Click Next.</span></span>

5.  <span data-ttu-id="40e7e-121">Immettere l'FQDN del pool.</span><span class="sxs-lookup"><span data-stu-id="40e7e-121">Enter the pool FQDN.</span></span> <span data-ttu-id="40e7e-122">Quando si definisce il pool pilota, è possibile scegliere di distribuire un pool Enterprise Edition front end o un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="40e7e-122">When you define your pilot pool, you can choose to deploy an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="40e7e-123">Lync Server 2013 non richiede che le funzionalità del pool pilota corrispondano a quelle distribuite nel pool legacy.</span><span class="sxs-lookup"><span data-stu-id="40e7e-123">Lync Server 2013 does not require that your pilot pool features match what was deployed in your legacy pool.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="40e7e-124">Il nome di dominio completo (FQDN) del pool o del server definito per il pool pilota deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="40e7e-124">The pool or server fully qualified domain name (FQDN) that you define for the pilot pool must be unique.</span></span> <span data-ttu-id="40e7e-125">Non può corrispondere al nome del pool di Office Communications Server 2007 R2 correntemente distribuito o di qualsiasi altro server attualmente distribuito.</span><span class="sxs-lookup"><span data-stu-id="40e7e-125">It cannot match the name of the currently deployed Office Communications Server 2007 R2 pool, or any other servers currently deployed.</span></span>

    
    </div>
    
    <span data-ttu-id="40e7e-126">![Definire la pagina FQDN del pool Front End](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "Definire la pagina FQDN del pool Front End")</span><span class="sxs-lookup"><span data-stu-id="40e7e-126">![Define the Front End pool FQDN page](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "Define the Front End pool FQDN page")</span></span>

6.  <span data-ttu-id="40e7e-127">Definire il computer che verrà aggiunto al pool.</span><span class="sxs-lookup"><span data-stu-id="40e7e-127">Define the computer that will be added to the pool.</span></span>
    
    <span data-ttu-id="40e7e-128">![Definire una nuova finestra di dialogo del pool Front End](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "Definire una nuova finestra di dialogo del pool Front End")</span><span class="sxs-lookup"><span data-stu-id="40e7e-128">![Define New Front End Pool dialog](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "Define New Front End Pool dialog")</span></span>

7.  <span data-ttu-id="40e7e-129">Nella pagina **Selezionare funzionalità** selezionare le caselle di controllo relative alle funzionalità che si desidera distribuire in questo pool Front End.</span><span class="sxs-lookup"><span data-stu-id="40e7e-129">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="40e7e-130">Se ad esempio si distribuiscono solo le funzionalità di Messaggistica istantanea e presenza, si selezionerà la casella di controllo per il servizio di conferenza in modo da consentire sessioni IM tra più utenti, ma non quelle relative a funzionalità per conferenze vocali, video e collaborative come Conferenza con accesso esterno (PSTN), VoIP aziendale o Controllo di ammissione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="40e7e-130">For example, if you are deploying only instant messaging (IM) and presence features, you would select the Conferencing check box to allow multiparty IM, but would not select the Dial-in (PSTN) conferencing, Enterprise Voice, or Call Admission Control check boxes, because they represent voice, video, and collaborative conferencing features.</span></span> <span data-ttu-id="40e7e-131">Per ulteriori informazioni sulla selezione di funzionalità, vedere [define and Configure a front end pool or Standard Edition server in Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="40e7e-131">For additional information on selecting features, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.</span></span>
    
    <span data-ttu-id="40e7e-132">![Pagina di selezione delle funzionalità del pool Front End](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Pagina di selezione delle funzionalità del pool Front End")</span><span class="sxs-lookup"><span data-stu-id="40e7e-132">![Front End Pool Select features page](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Front End Pool Select features page")</span></span>

8.  <span data-ttu-id="40e7e-133">Nella pagina **Selezione ruoli server collocati** , è consigliabile collocare il Mediation Server in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="40e7e-133">On the **Select collocated server roles** page, we recommend you collocate the Mediation Server in Lync Server 2013.</span></span> <span data-ttu-id="40e7e-134">Durante l'Unione di una topologia legacy con Lync Server 2013, è necessario innanzitutto collocare Office Communications Server 2007 R2 Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="40e7e-134">When merging a legacy topology with Lync Server 2013, we require that you first collocate the Office Communications Server 2007 R2 Mediation Server.</span></span> <span data-ttu-id="40e7e-135">Dopo l'Unione delle topologie e la configurazione di Lync Server 2013 Mediation Server, è possibile decidere se mantenere il Mediation Server collocato o modificarlo in un server autonomo quando si sposta il ruolo Mediation Server in Lync Server 2013 più avanti nel processo di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="40e7e-135">After merging the topologies and configuring the Lync Server 2013 Mediation Server, you can decide whether to keep the collocated Mediation Server, or change it to a stand-alone server when you move the Mediation Server role to Lync Server 2013 later in the deployment process.</span></span>
    
    <span data-ttu-id="40e7e-136">![Pagina di selezione dei ruoli server collocati nel pool Front End](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Pagina di selezione dei ruoli server collocati nel pool Front End")</span><span class="sxs-lookup"><span data-stu-id="40e7e-136">![Front End Pool Select collocated server roles page](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Front End Pool Select collocated server roles page")</span></span>

9.  <span data-ttu-id="40e7e-p109">Nella pagina **Associare ruoli server al pool Front End** non scegliere l'opzione **Abilita un pool di server perimetrali utilizzato dal componente multimediale di questo pool Front End** durante la distribuzione del pool pilota. Questa funzionalità verrà abilitata e portata online in una fase successiva della migrazione, pertanto mantenere deselezionata questa opzione per ora.</span><span class="sxs-lookup"><span data-stu-id="40e7e-p109">On the **Associate server roles with this Front End pool** page, during pilot pool deployment, do not choose the **Enable an Edge pool to be used by the media component of this Front End pool** option. This is a feature you will enable and bring online in a later phase of migration. Keep this setting cleared for now.</span></span>
    
    <span data-ttu-id="40e7e-140">![Associare i ruoli del server alla pagina del pool Front End](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Associare i ruoli del server alla pagina del pool Front End")</span><span class="sxs-lookup"><span data-stu-id="40e7e-140">![Associate server roles with Front End pool page](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Associate server roles with Front End pool page")</span></span>

10. <span data-ttu-id="40e7e-141">Nella pagina **Selezionare un server Office Web Apps** fare clic su **Nuovo** e specificare l'FQDN del server applicazioni.</span><span class="sxs-lookup"><span data-stu-id="40e7e-141">On the **Select an Office Web Apps Server** page, click **New**, and specify the FQDN of the application server.</span></span>
    
    <span data-ttu-id="40e7e-142">![Definire nuove proprietà FQDN del server Office Web Apps](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Definire nuove proprietà FQDN del server Office Web Apps")</span><span class="sxs-lookup"><span data-stu-id="40e7e-142">![Define New Office Web Apps Server FQDN properties](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Define New Office Web Apps Server FQDN properties")</span></span>

11. <span data-ttu-id="40e7e-143">Nella pagina **definire l'archivio SQL Server di archiviazione** selezionare l'istanza di SQL Server creata in precedenza per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="40e7e-143">On the **Define the Archiving SQL Server store** page, select the SQL Server instance created earlier for Lync Server 2013.</span></span>
    
    <span data-ttu-id="40e7e-144">![Pagina per la definizione dell'archivio SQL Server di archiviazione](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Pagina per la definizione dell'archivio SQL Server di archiviazione")</span><span class="sxs-lookup"><span data-stu-id="40e7e-144">![Define Archiving SQL Server store page](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Define Archiving SQL Server store page")</span></span>

12. <span data-ttu-id="40e7e-145">Nella pagina **definire l'archivio SQL Server di monitoraggio** selezionare l'istanza di SQL Server creata in precedenza per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="40e7e-145">On the **Define the Monitoring SQL Server store** page, select the SQL Server instance created earlier for Lync Server 2013.</span></span> <span data-ttu-id="40e7e-146">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="40e7e-146">Click **Finish**.</span></span>

13. <span data-ttu-id="40e7e-p111">Nel nodo principale del Generatore di topologie fare clic con il pulsante destro del mouse su **Lync Server** e scegliere **Modifica proprietà.** Fare clic su **URL semplici**.</span><span class="sxs-lookup"><span data-stu-id="40e7e-p111">From the top node of Topology Builder, right click **Lync Server** and click **Edit Properties.** Click **Simple URLs**.</span></span>

14. <span data-ttu-id="40e7e-149">Aggiornare l'**URL di accesso amministrativo**.</span><span class="sxs-lookup"><span data-stu-id="40e7e-149">Update the **Administrative access URL**.</span></span>
    
    <span data-ttu-id="40e7e-150">![Modifica proprietà, pagina URL semplici](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "Modifica proprietà, pagina URL semplici")</span><span class="sxs-lookup"><span data-stu-id="40e7e-150">![Edit Properties, Simple URLs page](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "Edit Properties, Simple URLs page")</span></span>
    
    <span data-ttu-id="40e7e-151">Per ulteriori informazioni sugli URL semplici, vedere l'argomento [Edit or Configure Simple URLs in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="40e7e-151">For additional information on Simple URLs, see the topic [Edit or configure simple URLs in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) in the Deployment documentation.</span></span>

15. <span data-ttu-id="40e7e-152">In **Modifica proprietà** fare clic su **Server di gestione centrale**.</span><span class="sxs-lookup"><span data-stu-id="40e7e-152">From the **Edit Properties**, click **Central Management Server**.</span></span>

16. <span data-ttu-id="40e7e-153">Nell'elenco a discesa selezionare il pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="40e7e-153">From the drop-down list, select the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="40e7e-154">![Modifica proprietà, pagina server di gestione centrale](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "Modifica proprietà, pagina server di gestione centrale")</span><span class="sxs-lookup"><span data-stu-id="40e7e-154">![Edit Properties, Central Management Server page](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "Edit Properties, Central Management Server page")</span></span>

17. <span data-ttu-id="40e7e-155">Fare clic su OK per chiudere la pagina **Modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="40e7e-155">Click OK to close **the Edit Properties** page.</span></span>

18. <span data-ttu-id="40e7e-156">Nel menu **Azione** scegliere **Pubblica topologia**.</span><span class="sxs-lookup"><span data-stu-id="40e7e-156">From the **Action** menu, select **Publish Topology**.</span></span>

19. <span data-ttu-id="40e7e-157">Al termine del processo di pubblicazione, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="40e7e-157">When the publish process has completed, click **Finish**.</span></span>

20. <span data-ttu-id="40e7e-158">Tornando alla distribuzione guidata di Lync Server 2013, fare clic su **Installa o aggiorna il sistema Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="40e7e-158">Returning to the Lync Server 2013 Deployment Wizard, click **Install or Update Lync Server System**.</span></span>
    
    <span data-ttu-id="40e7e-159">![Distribuzione guidata di Lync Server 2013](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Distribuzione guidata di Lync Server 2013")</span><span class="sxs-lookup"><span data-stu-id="40e7e-159">![Lync Server 2013 Deployment Wizard](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Lync Server 2013 Deployment Wizard")</span></span>

<span data-ttu-id="40e7e-160">Per installare una copia locale dell'archivio di configurazione e avviare i servizi richiesti, vedere [Setting up front end servers and front end pools for Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="40e7e-160">To install a local copy of the configuration store and start the required services, see [Setting up Front End Servers and Front End pools for Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.</span></span>


</div>

<span> </span>

</div>

</div>

</div>


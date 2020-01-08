---
title: 'Lync Server 2013: Esecuzione della preparazione dello schema'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Running schema preparation
ms:assetid: 9d02bdb1-ff29-417a-bcce-b068b31207d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412729(v=OCS.15)
ms:contentKeyID: 48184911
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b743e5ef93b14279f5f2f16cb70241617a0c8f0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981408"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-active-directory-schema-preparation-in-lync-server-2013"></a><span data-ttu-id="70f23-102">Esecuzione della preparazione dello schema in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70f23-102">Running Active Directory schema preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70f23-103">_**Argomento Ultima modifica:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="70f23-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="70f23-104">È possibile usare i cmdlet setup o Lync Server Management Shell per preparare lo schema Active Directory.</span><span class="sxs-lookup"><span data-stu-id="70f23-104">You can use Setup or Lync Server Management Shell cmdlets to prepare the Active Directory schema.</span></span> <span data-ttu-id="70f23-105">Il cmdlet che estende lo schema di Active Directory è **Install-CsAdServerSchema**.</span><span class="sxs-lookup"><span data-stu-id="70f23-105">The cmdlet that extends the Active Directory schema is **Install-CsAdServerSchema**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="70f23-106">Il cmdlet di preparazione dello schema (<STRONG>Install-CsAdServerSchema</STRONG>) deve accedere al master schema, che richiede che il servizio Registro di sistema remoto sia in uso e che la chiave del registro di sistema remota sia abilitata.</span><span class="sxs-lookup"><span data-stu-id="70f23-106">The schema preparation cmdlet (<STRONG>Install-CsAdServerSchema</STRONG>) must access the schema master, which requires that the remote registry service is running and that the remote registry key is enabled.</span></span> <span data-ttu-id="70f23-107">Se il servizio Registro di sistema remoto non può essere abilitato nello schema master, è possibile eseguire il cmdlet localmente nello schema master.</span><span class="sxs-lookup"><span data-stu-id="70f23-107">If the remote registry service cannot be enabled on the schema master, you can run the cmdlet locally on the schema master.</span></span> <span data-ttu-id="70f23-108">Per informazioni dettagliate sull'accesso remoto del registro di sistema, vedere l'articolo 314837 della Microsoft Knowledge Base "come gestire l'accesso remoto al <A href="http://go.microsoft.com/fwlink/p/?linkid=125769">http://go.microsoft.com/fwlink/p/?linkId=125769</A>registro di sistema".</span><span class="sxs-lookup"><span data-stu-id="70f23-108">For details about registry remote access, see Microsoft Knowledge Base article 314837, "How to Manage Remote Access to the Registry," at <A href="http://go.microsoft.com/fwlink/p/?linkid=125769">http://go.microsoft.com/fwlink/p/?linkId=125769</A>.</span></span>



</div>

<span data-ttu-id="70f23-109">Dopo aver completato la preparazione dello schema, verificare manualmente che la partizione dello schema sia stata replicata prima di procedere con la preparazione della foresta.</span><span class="sxs-lookup"><span data-stu-id="70f23-109">After you complete schema preparation, manually verify that the schema partition has been replicated before proceeding to forest preparation.</span></span> <span data-ttu-id="70f23-110">Per informazioni dettagliate, vedere [Verifica della replica dello schema di Active Directory in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span><span class="sxs-lookup"><span data-stu-id="70f23-110">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

<div>

## <a name="to-use-setup-to-prepare-the-schema-of-the-current-forest"></a><span data-ttu-id="70f23-111">Per usare la configurazione per preparare lo schema della foresta corrente</span><span class="sxs-lookup"><span data-stu-id="70f23-111">To use Setup to prepare the schema of the current forest</span></span>

1.  <span data-ttu-id="70f23-112">Accedere a un server della foresta come membro del gruppo amministratori schema e con i diritti di amministratore dello schema.</span><span class="sxs-lookup"><span data-stu-id="70f23-112">Log on to a server in your forest as a member of the Schema Admins group and with administrator rights on the schema master.</span></span>

2.  <span data-ttu-id="70f23-113">Nella cartella di installazione o nel supporto di Lync Server 2013 eseguire Setup. exe per avviare la distribuzione guidata.</span><span class="sxs-lookup"><span data-stu-id="70f23-113">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Deployment Wizard.</span></span>

3.  <span data-ttu-id="70f23-114">Se viene richiesto di installare Microsoft Visual C++ ridistribuibile, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="70f23-114">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>

4.  <span data-ttu-id="70f23-115">Nella finestra di dialogo configurazione di Lync Server 2013 viene richiesto di installare i file di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="70f23-115">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="70f23-116">Scegliere il percorso predefinito o **passare** a una posizione a scelta e quindi fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="70f23-116">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>

5.  <span data-ttu-id="70f23-117">Nella pagina Contratto di licenza selezionare **Accetto i termini del contratto di licenza**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="70f23-117">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span>

6.  <span data-ttu-id="70f23-118">Il programma di installazione installa i componenti principali di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="70f23-118">The installer installs the Lync Server Core Components.</span></span>

7.  <span data-ttu-id="70f23-119">Quando la distribuzione guidata è pronta, fare clic su **prepara Active Directory**e quindi attendere che venga determinato lo stato di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="70f23-119">When the Deployment Wizard is ready, click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

8.  <span data-ttu-id="70f23-120">Al **passaggio 1: preparare lo schema**, fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="70f23-120">At **Step 1: Prepare Schema**, click **Run**.</span></span>

9.  <span data-ttu-id="70f23-121">Nella pagina **Prepara schema** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="70f23-121">On the **Prepare Schema** page, click **Next**.</span></span>

10. <span data-ttu-id="70f23-122">Nella pagina **Esecuzione comandi in corso** cercare il messaggio **Stato attività: Completata** e quindi fare clic su **Visualizza registro**.</span><span class="sxs-lookup"><span data-stu-id="70f23-122">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

11. <span data-ttu-id="70f23-123">Nella colonna **azione** espandere **schema Prep**, cercare il \*\* \<\> \*\* risultato dell'esecuzione di successo alla fine di ogni attività per verificare che la preparazione dello schema sia stata completata correttamente, chiudere il log e quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="70f23-123">Under the **Action** column, expand **Schema Prep**, look for the **\<Success\>** Execution Result at the end of each task to verify that schema preparation completed successfully, close the log, and then click **Finish**.</span></span>

12. <span data-ttu-id="70f23-124">Attendere che la replica di Active Directory completi o forzi la replica.</span><span class="sxs-lookup"><span data-stu-id="70f23-124">Wait for Active Directory replication to complete or force replication.</span></span>

13. <span data-ttu-id="70f23-125">Verificare manualmente che lo schema cambi replicato in tutti gli altri controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="70f23-125">Manually verify that the schema changes replicated to all other domain controllers.</span></span> <span data-ttu-id="70f23-126">Per informazioni dettagliate, vedere [Verifica della replica dello schema di Active Directory in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span><span class="sxs-lookup"><span data-stu-id="70f23-126">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-schema-of-the-current-forest"></a><span data-ttu-id="70f23-127">Per usare i cmdlet per preparare lo schema della foresta corrente</span><span class="sxs-lookup"><span data-stu-id="70f23-127">To use cmdlets to prepare the schema of the current forest</span></span>

1.  <span data-ttu-id="70f23-128">Accedere a un computer della foresta come membro del gruppo amministratori schema e con i diritti di amministratore dello schema.</span><span class="sxs-lookup"><span data-stu-id="70f23-128">Log on to a computer in the forest as a member of the Schema Admins group and with administrator rights on the schema master.</span></span>

2.  <span data-ttu-id="70f23-129">Installare i componenti di base di Lync Server nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="70f23-129">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="70f23-130">Nella cartella di installazione o nel supporto di Lync Server 2013 eseguire Setup. exe per avviare la distribuzione guidata di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="70f23-130">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="70f23-131">Se viene richiesto di installare Microsoft Visual C++ ridistribuibile, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="70f23-131">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="70f23-132">Nella finestra di dialogo configurazione di Lync Server 2013 viene richiesto di installare i file di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="70f23-132">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="70f23-133">Scegliere il percorso predefinito o **passare** a una posizione a scelta e quindi fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="70f23-133">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="70f23-134">Nella pagina Contratto di licenza selezionare **Accetto i termini del contratto di licenza**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="70f23-134">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="70f23-135">Il programma di installazione installa i componenti principali di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="70f23-135">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="70f23-136">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="70f23-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="70f23-137">Eseguire</span><span class="sxs-lookup"><span data-stu-id="70f23-137">Run:</span></span>
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    <span data-ttu-id="70f23-138">Se non specifichi il parametro ldf, il valore predefinito è il percorso di installazione di Lync Server 2013 che viene letto dal registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="70f23-138">If you do not specify the Ldf parameter, the default value is the Lync Server 2013 installation path that is read from the registry.</span></span>
    
    <span data-ttu-id="70f23-139">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="70f23-139">For example:</span></span>
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  <span data-ttu-id="70f23-140">Usa il cmdlet seguente per verificare che la preparazione dello schema sia stata eseguita fino al completamento.</span><span class="sxs-lookup"><span data-stu-id="70f23-140">Use the following cmdlet to verify that schema preparation ran to completion.</span></span>
    
        Get-CsAdServerSchema 
    
    <span data-ttu-id="70f23-141">Questo cmdlet restituisce un valore di **stato\_\_della\_versione dello schema corrente** se la preparazione dello schema ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="70f23-141">This cmdlet returns a value of **SCHEMA\_VERSION\_STATE\_CURRENT** if schema preparation was successful.</span></span>

6.  <span data-ttu-id="70f23-142">Attendere che la replica di Active Directory completi o forzi la replica.</span><span class="sxs-lookup"><span data-stu-id="70f23-142">Wait for Active Directory replication to complete or force replication.</span></span>

7.  <span data-ttu-id="70f23-143">Verificare manualmente che lo schema cambi replicato in tutti gli altri controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="70f23-143">Manually verify that the schema changes replicated to all other domain controllers.</span></span> <span data-ttu-id="70f23-144">Per informazioni dettagliate, vedere [Verifica della replica dello schema di Active Directory in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span><span class="sxs-lookup"><span data-stu-id="70f23-144">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="70f23-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70f23-145">See Also</span></span>


[<span data-ttu-id="70f23-146">Verifica della replica dello schema in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70f23-146">Verifying Active Directory schema replication in Lync Server 2013</span></span>](lync-server-2013-verifying-schema-replication.md)  


[<span data-ttu-id="70f23-147">Preparazione dello schema di Active Directory in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70f23-147">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


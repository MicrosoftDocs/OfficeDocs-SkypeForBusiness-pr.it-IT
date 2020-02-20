---
title: 'Lync Server 2013: esecuzione della preparazione dello schema'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running schema preparation
ms:assetid: 9d02bdb1-ff29-417a-bcce-b068b31207d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412729(v=OCS.15)
ms:contentKeyID: 48184911
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8336bdb881570c40900600c1eda3c3c17ffb614
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144452"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="running-active-directory-schema-preparation-in-lync-server-2013"></a><span data-ttu-id="4d9c0-102">Esecuzione della preparazione dello schema di Active Directory in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d9c0-102">Running Active Directory schema preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d9c0-103">_**Ultimo argomento modificato:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="4d9c0-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="4d9c0-104">È possibile utilizzare i cmdlet setup o Lync Server Management Shell per preparare lo schema di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4d9c0-104">You can use Setup or Lync Server Management Shell cmdlets to prepare the Active Directory schema.</span></span> <span data-ttu-id="4d9c0-105">Il cmdlet che estende lo schema di Active Directory è **Install-CsAdServerSchema**.</span><span class="sxs-lookup"><span data-stu-id="4d9c0-105">The cmdlet that extends the Active Directory schema is **Install-CsAdServerSchema**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4d9c0-106">Il cmdlet di preparazione dello schema (<STRONG>Install-CsAdServerSchema</STRONG>) deve accedere al master dello schema, che richiede che il servizio Registro di sistema remoto sia in esecuzione e che la chiave del registro di sistema remota sia abilitata.</span><span class="sxs-lookup"><span data-stu-id="4d9c0-106">The schema preparation cmdlet (<STRONG>Install-CsAdServerSchema</STRONG>) must access the schema master, which requires that the remote registry service is running and that the remote registry key is enabled.</span></span> <span data-ttu-id="4d9c0-107">Se il servizio Registro di sistema remoto non può essere abilitato sul master schema, è possibile eseguire il cmdlet localmente nel master schema.</span><span class="sxs-lookup"><span data-stu-id="4d9c0-107">If the remote registry service cannot be enabled on the schema master, you can run the cmdlet locally on the schema master.</span></span> <span data-ttu-id="4d9c0-108">Per informazioni dettagliate sull'accesso remoto al registro di sistema, vedere l'articolo 314837 della Microsoft Knowledge Base "come gestire l'accesso remoto al <A href="https://go.microsoft.com/fwlink/p/?linkid=125769">https://go.microsoft.com/fwlink/p/?linkId=125769</A>registro di sistema" all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="4d9c0-108">For details about registry remote access, see Microsoft Knowledge Base article 314837, "How to Manage Remote Access to the Registry," at <A href="https://go.microsoft.com/fwlink/p/?linkid=125769">https://go.microsoft.com/fwlink/p/?linkId=125769</A>.</span></span>



</div>

<span data-ttu-id="4d9c0-109">Dopo aver completato la preparazione dello schema, verificare manualmente che la partizione dello schema sia stata replicata prima di procedere alla preparazione della foresta.</span><span class="sxs-lookup"><span data-stu-id="4d9c0-109">After you complete schema preparation, manually verify that the schema partition has been replicated before proceeding to forest preparation.</span></span> <span data-ttu-id="4d9c0-110">Per informazioni dettagliate, vedere [Verifying Active Directory schema Replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span><span class="sxs-lookup"><span data-stu-id="4d9c0-110">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

<div>

## <a name="to-use-setup-to-prepare-the-schema-of-the-current-forest"></a><span data-ttu-id="4d9c0-111">Per utilizzare il programma di installazione per preparare lo schema della foresta corrente</span><span class="sxs-lookup"><span data-stu-id="4d9c0-111">To use Setup to prepare the schema of the current forest</span></span>

1.  <span data-ttu-id="4d9c0-112">Accedere a un server nella foresta come membro del gruppo Schema Admins e con diritti di amministratore per il master schema.</span><span class="sxs-lookup"><span data-stu-id="4d9c0-112">Log on to a server in your forest as a member of the Schema Admins group and with administrator rights on the schema master.</span></span>

2.  <span data-ttu-id="4d9c0-113">Dalla cartella o dal supporto di installazione di Lync Server 2013, eseguire Setup. exe per avviare la distribuzione guidata.</span><span class="sxs-lookup"><span data-stu-id="4d9c0-113">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Deployment Wizard.</span></span>

3.  <span data-ttu-id="4d9c0-114">Se viene chiesto di installare Microsoft Visual C++ Redistributable, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="4d9c0-114">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>

4.  <span data-ttu-id="4d9c0-115">Nella finestra di dialogo installazione di Lync Server 2013 viene visualizzata una richiesta di installazione dei file di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4d9c0-115">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="4d9c0-116">Scegliere il percorso predefinito o **Sfoglia** per selezionare il percorso desiderato e quindi fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="4d9c0-116">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>

5.  <span data-ttu-id="4d9c0-117">Nella pagina Contratto di Licenza selezionare **Accetto i termini del Contratto di Licenza** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4d9c0-117">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span>

6.  <span data-ttu-id="4d9c0-118">Il programma di installazione installa i componenti di base di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4d9c0-118">The installer installs the Lync Server Core Components.</span></span>

7.  <span data-ttu-id="4d9c0-119">Quando la distribuzione guidata è pronta, fare clic su **prepara Active Directory**e quindi attendere che venga determinato lo stato della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="4d9c0-119">When the Deployment Wizard is ready, click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

8.  <span data-ttu-id="4d9c0-120">Al **passaggio 1: preparare lo schema**, fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="4d9c0-120">At **Step 1: Prepare Schema**, click **Run**.</span></span>

9.  <span data-ttu-id="4d9c0-121">Nella pagina **Prepara schema** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4d9c0-121">On the **Prepare Schema** page, click **Next**.</span></span>

10. <span data-ttu-id="4d9c0-122">Nella pagina **Esecuzione comandi in corso** ricercare **Stato attività: Operazione completata** e quindi fare clic su **Visualizza registro**.</span><span class="sxs-lookup"><span data-stu-id="4d9c0-122">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

11. <span data-ttu-id="4d9c0-123">Nella colonna **azione** espandere **preparazione schema**, cercare il \*\*\*\* \*\* \<risultato dell'esecuzione di\> esito positivo\*\* alla fine di ogni attività per verificare che la preparazione dello schema sia stata completata correttamente, chiudere il registro e quindi fare clic su fine.</span><span class="sxs-lookup"><span data-stu-id="4d9c0-123">Under the **Action** column, expand **Schema Prep**, look for the **\<Success\>** Execution Result at the end of each task to verify that schema preparation completed successfully, close the log, and then click **Finish**.</span></span>

12. <span data-ttu-id="4d9c0-124">Attendere il completamento della replica di Active Directory o forzare la replica.</span><span class="sxs-lookup"><span data-stu-id="4d9c0-124">Wait for Active Directory replication to complete or force replication.</span></span>

13. <span data-ttu-id="4d9c0-125">Verificare manualmente che le modifiche allo schema siano state replicate in tutti gli altri controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="4d9c0-125">Manually verify that the schema changes replicated to all other domain controllers.</span></span> <span data-ttu-id="4d9c0-126">Per informazioni dettagliate, vedere [Verifying Active Directory schema Replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span><span class="sxs-lookup"><span data-stu-id="4d9c0-126">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-schema-of-the-current-forest"></a><span data-ttu-id="4d9c0-127">Per utilizzare i cmdlet per preparare lo schema della foresta corrente</span><span class="sxs-lookup"><span data-stu-id="4d9c0-127">To use cmdlets to prepare the schema of the current forest</span></span>

1.  <span data-ttu-id="4d9c0-128">Accedere a un computer nella foresta con un account membro del gruppo Schema Admins e con diritti di amministratore per il master schema.</span><span class="sxs-lookup"><span data-stu-id="4d9c0-128">Log on to a computer in the forest as a member of the Schema Admins group and with administrator rights on the schema master.</span></span>

2.  <span data-ttu-id="4d9c0-129">Installare i componenti di base di Lync Server come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="4d9c0-129">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="4d9c0-130">Dalla cartella o dal supporto di installazione di Lync Server 2013, eseguire Setup. exe per avviare la distribuzione guidata di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4d9c0-130">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="4d9c0-131">Se viene chiesto di installare Microsoft Visual C++ Redistributable, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="4d9c0-131">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="4d9c0-132">Nella finestra di dialogo installazione di Lync Server 2013 viene visualizzata una richiesta di installazione dei file di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4d9c0-132">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="4d9c0-133">Scegliere il percorso predefinito o **Sfoglia** per selezionare il percorso desiderato e quindi fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="4d9c0-133">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="4d9c0-134">Nella pagina Contratto di Licenza selezionare **Accetto i termini del Contratto di Licenza** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4d9c0-134">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="4d9c0-135">Il programma di installazione installa i componenti di base di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4d9c0-135">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="4d9c0-136">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="4d9c0-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="4d9c0-137">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="4d9c0-137">Run:</span></span>
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    <span data-ttu-id="4d9c0-138">Se non si specifica il parametro ldf, il valore predefinito è il percorso di installazione di Lync Server 2013 che viene letto dal registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="4d9c0-138">If you do not specify the Ldf parameter, the default value is the Lync Server 2013 installation path that is read from the registry.</span></span>
    
    <span data-ttu-id="4d9c0-139">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4d9c0-139">For example:</span></span>
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  <span data-ttu-id="4d9c0-140">Utilizzare il cmdlet seguente per verificare la corretta esecuzione della preparazione dello schema.</span><span class="sxs-lookup"><span data-stu-id="4d9c0-140">Use the following cmdlet to verify that schema preparation ran to completion.</span></span>
    
        Get-CsAdServerSchema 
    
    <span data-ttu-id="4d9c0-141">Questo cmdlet restituisce il valore dello **stato\_\_della\_versione dello schema corrente** se la preparazione dello schema ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="4d9c0-141">This cmdlet returns a value of **SCHEMA\_VERSION\_STATE\_CURRENT** if schema preparation was successful.</span></span>

6.  <span data-ttu-id="4d9c0-142">Attendere il completamento della replica di Active Directory o forzare la replica.</span><span class="sxs-lookup"><span data-stu-id="4d9c0-142">Wait for Active Directory replication to complete or force replication.</span></span>

7.  <span data-ttu-id="4d9c0-143">Verificare manualmente che le modifiche allo schema siano state replicate in tutti gli altri controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="4d9c0-143">Manually verify that the schema changes replicated to all other domain controllers.</span></span> <span data-ttu-id="4d9c0-144">Per informazioni dettagliate, vedere [Verifying Active Directory schema Replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span><span class="sxs-lookup"><span data-stu-id="4d9c0-144">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4d9c0-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d9c0-145">See Also</span></span>


[<span data-ttu-id="4d9c0-146">Verifica della replica dello schema di Active Directory in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d9c0-146">Verifying Active Directory schema replication in Lync Server 2013</span></span>](lync-server-2013-verifying-schema-replication.md)  


[<span data-ttu-id="4d9c0-147">Preparazione dello schema di Active Directory in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d9c0-147">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


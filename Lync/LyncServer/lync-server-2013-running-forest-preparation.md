---
title: 'Lync Server 2013: esecuzione della preparazione della foresta'
description: 'Lync Server 2013: esecuzione della preparazione della foresta.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running forest preparation
ms:assetid: 9d62f7be-bcfe-421d-8d8a-225567102a35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412732(v=OCS.15)
ms:contentKeyID: 48184991
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad3ef2d7583d541701d6606946ca1df1bbd8cf23
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577762"
---
# <a name="running-forest-preparation-for-lync-server-2013"></a><span data-ttu-id="72fb6-103">Esecuzione della preparazione della foresta per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72fb6-103">Running forest preparation for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72fb6-104">_**Ultimo argomento modificato:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="72fb6-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="72fb6-105">È possibile utilizzare i cmdlet setup o Lync Server Management Shell per preparare la foresta.</span><span class="sxs-lookup"><span data-stu-id="72fb6-105">You can use Setup or Lync Server Management Shell cmdlets to prepare the forest.</span></span> <span data-ttu-id="72fb6-106">Il cmdlet che prepara la foresta è **Enable-CsAdForest**.</span><span class="sxs-lookup"><span data-stu-id="72fb6-106">The cmdlet that prepares the forest is **Enable-CsAdForest**.</span></span>

<span data-ttu-id="72fb6-107">Dopo aver preparato la foresta, è necessario verificare che le impostazioni globali siano state replicate prima di eseguire la preparazione del dominio.</span><span class="sxs-lookup"><span data-stu-id="72fb6-107">After you prepare the forest, you must verify that global settings have been replicated before running domain preparation.</span></span>

<div>

## <a name="to-use-setup-to-prepare-the-forest"></a><span data-ttu-id="72fb6-108">Per utilizzare il programma di installazione per preparare la foresta</span><span class="sxs-lookup"><span data-stu-id="72fb6-108">To use Setup to prepare the forest</span></span>

1.  <span data-ttu-id="72fb6-109">Accedere a un computer aggiunto a un dominio come membro del gruppo Enterprise Admins per il dominio radice della foresta.</span><span class="sxs-lookup"><span data-stu-id="72fb6-109">Log on to a computer that is joined to a domain as a member of the Enterprise Admins group for the forest root domain.</span></span>

2.  <span data-ttu-id="72fb6-110">Dalla cartella o dal supporto di installazione di Lync Server 2013, eseguire Setup.exe per avviare la distribuzione guidata.</span><span class="sxs-lookup"><span data-stu-id="72fb6-110">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Deployment Wizard.</span></span>

3.  <span data-ttu-id="72fb6-111">Fare clic su **Prepara Active Directory** e quindi attendere che venga determinato lo stato della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="72fb6-111">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

4.  <span data-ttu-id="72fb6-112">Al **passaggio 3: preparare la foresta corrente**, fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="72fb6-112">At **Step 3: Prepare Current Forest**, click **Run**.</span></span>

5.  <span data-ttu-id="72fb6-113">Nella pagina **Prepara foresta** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="72fb6-113">On the **Prepare Forest** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="72fb6-114">La preparazione della foresta consente di scegliere dove collocare i gruppi universali per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="72fb6-114">Forest Preparation allows you to choose where to place the Universal Groups for Lync Server 2013.</span></span> <span data-ttu-id="72fb6-115">Selezionare una posizione coerente con i requisiti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="72fb6-115">Choose a location that is consistent with the requirements of your organization.</span></span>

    
    </div>

6.  <span data-ttu-id="72fb6-116">Nella pagina **Esecuzione comandi in corso** ricercare **Stato attività: Operazione completata** e quindi fare clic su **Visualizza registro**.</span><span class="sxs-lookup"><span data-stu-id="72fb6-116">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

7.  <span data-ttu-id="72fb6-117">Nella colonna **azione** espandere **Preparazione foresta**, cercare il **\<Success\>** risultato dell'esecuzione alla fine di ogni attività per verificare che la preparazione della foresta sia stata completata correttamente, chiudere il registro e quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="72fb6-117">Under the **Action** column, expand **Forest Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that forest preparation completed successfully, close the log, and then click **Finish**.</span></span>

8.  <span data-ttu-id="72fb6-p103">Attendere il completamento della replica di Active Directory oppure forzare la replica in tutti i controller di dominio elencati nello snap-in **Siti e servizi di Active Directory** per il controller di dominio della radice della foresta prima di eseguire la preparazione del dominio. Forzare la replica tra i controller di dominio in tutti i siti di Active Directory perché la replica all'interno dei siti venga eseguita entro pochi minuti.</span><span class="sxs-lookup"><span data-stu-id="72fb6-p103">Wait for Active Directory replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation. Force replication between the domain controllers in all Active Directory sites to cause replication within the sites to occur within minutes.</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-forest"></a><span data-ttu-id="72fb6-120">Per utilizzare i cmdlet per la preparazione della foresta</span><span class="sxs-lookup"><span data-stu-id="72fb6-120">To use cmdlets to prepare the forest</span></span>

1.  <span data-ttu-id="72fb6-121">Accedere a un computer che fa parte di un dominio come membro del gruppo Domain Admins nel dominio radice della foresta.</span><span class="sxs-lookup"><span data-stu-id="72fb6-121">Log on to a computer that is joined to a domain as a member of the Domain Admins group in the forest root domain.</span></span>

2.  <span data-ttu-id="72fb6-122">Installare i componenti di base di Lync Server come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="72fb6-122">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="72fb6-123">Dalla cartella o dal supporto di installazione di Lync Server 2013, eseguire Setup.exe per avviare la distribuzione guidata di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="72fb6-123">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="72fb6-124">Se viene chiesto di installare Microsoft Visual C++ Redistributable, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="72fb6-124">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="72fb6-125">Nella finestra di dialogo installazione di Lync Server 2013 viene visualizzata una richiesta di installazione dei file di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="72fb6-125">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="72fb6-126">Scegliere il percorso predefinito o **Sfoglia** per selezionare il percorso desiderato e quindi fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="72fb6-126">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="72fb6-127">Nella pagina Contratto di Licenza selezionare **Accetto i termini del Contratto di Licenza** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="72fb6-127">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="72fb6-128">Il programma di installazione installa i componenti di base di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="72fb6-128">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="72fb6-129">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="72fb6-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="72fb6-130">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="72fb6-130">Run:</span></span>
    
        Enable-CsAdForest [-GroupDomain <FQDN of the domain in which to create the universal groups>]
    
    <span data-ttu-id="72fb6-131">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="72fb6-131">For example:</span></span>
    
        Enable-CsAdForest -GroupDomain domain1.contoso.com 
    
    <span data-ttu-id="72fb6-p106">Se non si specifica il parametro GroupDomain, il valore predefinito è il dominio locale. Se i gruppi universali sono stati creati in precedenza in un dominio che non è quello predefinito, è necessario specificare il parametro GroupDomain in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="72fb6-p106">If you do not specify the GroupDomain parameter, the default value is the local domain. If universal groups were created previously in a domain that is not the default domain, you must specify the GroupDomain parameter explicitly.</span></span>

5.  <span data-ttu-id="72fb6-134">Attendere il completamento della replica di Active Directory oppure forzare la replica in tutti i controller di dominio elencati nello snap-in **Siti e servizi di Active Directory** per il controller del dominio radice della foresta, prima di eseguire la preparazione del dominio.</span><span class="sxs-lookup"><span data-stu-id="72fb6-134">Wait for Active Directory replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span>

6.  <span data-ttu-id="72fb6-135">Verificare che la preparazione della foresta abbia avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="72fb6-135">Verify that forest preparation was successful.</span></span> <span data-ttu-id="72fb6-136">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="72fb6-136">Run:</span></span>
    
        Get-CsAdForest 
    
    <span data-ttu-id="72fb6-137">Questo cmdlet restituisce un valore di \*\* \_ stato LC \_ FORESTSETTINGS \_ pronto\*\* se la preparazione della foresta ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="72fb6-137">This cmdlet returns a value of **LC\_FORESTSETTINGS\_STATE\_READY** if forest preparation was successful.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="72fb6-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72fb6-138">See Also</span></span>


[<span data-ttu-id="72fb6-139">Utilizzo dei cmdlet per annullare la preparazione della foresta per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72fb6-139">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)  


[<span data-ttu-id="72fb6-140">Preparazione della foresta per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72fb6-140">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Esecuzione della preparazione della foresta'
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
ms.openlocfilehash: 129926afe17f946a2ea32d7c67fdea89fab32a54
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732817"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-forest-preparation-for-lync-server-2013"></a><span data-ttu-id="24f41-102">Esecuzione della preparazione della foresta per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24f41-102">Running forest preparation for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24f41-103">_**Argomento Ultima modifica:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="24f41-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="24f41-104">È possibile usare i cmdlet setup o Lync Server Management Shell per preparare la foresta.</span><span class="sxs-lookup"><span data-stu-id="24f41-104">You can use Setup or Lync Server Management Shell cmdlets to prepare the forest.</span></span> <span data-ttu-id="24f41-105">Il cmdlet che prepara la foresta è **Enable-CsAdForest**.</span><span class="sxs-lookup"><span data-stu-id="24f41-105">The cmdlet that prepares the forest is **Enable-CsAdForest**.</span></span>

<span data-ttu-id="24f41-106">Dopo aver preparato la foresta, è necessario verificare che le impostazioni globali siano state replicate prima di eseguire la preparazione del dominio.</span><span class="sxs-lookup"><span data-stu-id="24f41-106">After you prepare the forest, you must verify that global settings have been replicated before running domain preparation.</span></span>

<div>

## <a name="to-use-setup-to-prepare-the-forest"></a><span data-ttu-id="24f41-107">Per usare la configurazione per preparare la foresta</span><span class="sxs-lookup"><span data-stu-id="24f41-107">To use Setup to prepare the forest</span></span>

1.  <span data-ttu-id="24f41-108">Accedere a un computer collegato a un dominio come membro del gruppo amministratori aziendali per il dominio radice della foresta.</span><span class="sxs-lookup"><span data-stu-id="24f41-108">Log on to a computer that is joined to a domain as a member of the Enterprise Admins group for the forest root domain.</span></span>

2.  <span data-ttu-id="24f41-109">Nella cartella di installazione o nel supporto di Lync Server 2013 eseguire Setup. exe per avviare la distribuzione guidata.</span><span class="sxs-lookup"><span data-stu-id="24f41-109">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Deployment Wizard.</span></span>

3.  <span data-ttu-id="24f41-110">Fare clic su **Prepara Active Directory** e quindi attendere che venga determinato lo stato della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="24f41-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

4.  <span data-ttu-id="24f41-111">Al **passaggio 3: preparare la foresta corrente**, fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="24f41-111">At **Step 3: Prepare Current Forest**, click **Run**.</span></span>

5.  <span data-ttu-id="24f41-112">Nella pagina **Preparazione foresta** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="24f41-112">On the **Prepare Forest** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="24f41-113">La preparazione della foresta consente di scegliere dove posizionare i gruppi universali per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="24f41-113">Forest Preparation allows you to choose where to place the Universal Groups for Lync Server 2013.</span></span> <span data-ttu-id="24f41-114">Scegliere una posizione conforme ai requisiti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="24f41-114">Choose a location that is consistent with the requirements of your organization.</span></span>

    
    </div>

6.  <span data-ttu-id="24f41-115">Nella pagina **Esecuzione comandi in corso** ricercare **Stato attività: Operazione completata** e quindi fare clic su **Visualizza registro**.</span><span class="sxs-lookup"><span data-stu-id="24f41-115">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

7.  <span data-ttu-id="24f41-116">Nella colonna **Action** espandere **Forest Prep**cercare un \*\* \<\> \*\* risultato di esecuzione di successo alla fine di ogni attività per verificare che la preparazione della foresta sia stata completata correttamente, chiudere il log e quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="24f41-116">Under the **Action** column, expand **Forest Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that forest preparation completed successfully, close the log, and then click **Finish**.</span></span>

8.  <span data-ttu-id="24f41-117">Attendere il completamento della replica di Active Directory oppure forzare la replica a tutti i controller di dominio elencati nello snap-in **siti e servizi di Active Directory** per il controller di dominio radice della foresta, prima di eseguire la preparazione del dominio.</span><span class="sxs-lookup"><span data-stu-id="24f41-117">Wait for Active Directory replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span> <span data-ttu-id="24f41-118">Forzare la replica tra i controller di dominio in tutti i siti di Active Directory per provocare la replica nei siti in pochi minuti.</span><span class="sxs-lookup"><span data-stu-id="24f41-118">Force replication between the domain controllers in all Active Directory sites to cause replication within the sites to occur within minutes.</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-forest"></a><span data-ttu-id="24f41-119">Per usare i cmdlet per preparare la foresta</span><span class="sxs-lookup"><span data-stu-id="24f41-119">To use cmdlets to prepare the forest</span></span>

1.  <span data-ttu-id="24f41-120">Accedere a un computer collegato a un dominio come membro del gruppo Domain Admins nel dominio radice della foresta.</span><span class="sxs-lookup"><span data-stu-id="24f41-120">Log on to a computer that is joined to a domain as a member of the Domain Admins group in the forest root domain.</span></span>

2.  <span data-ttu-id="24f41-121">Installare i componenti di base di Lync Server nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="24f41-121">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="24f41-122">Nella cartella di installazione o nel supporto di Lync Server 2013 eseguire Setup. exe per avviare la distribuzione guidata di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="24f41-122">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="24f41-123">Se viene richiesto di installare Microsoft Visual C++ ridistribuibile, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="24f41-123">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="24f41-124">Nella finestra di dialogo configurazione di Lync Server 2013 viene richiesto di installare i file di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="24f41-124">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="24f41-125">Scegliere il percorso predefinito o **passare** a una posizione a scelta e quindi fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="24f41-125">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="24f41-126">Nella pagina Contratto di licenza selezionare **Accetto i termini del contratto di licenza**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="24f41-126">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="24f41-127">Il programma di installazione installa i componenti principali di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="24f41-127">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="24f41-128">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="24f41-128">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="24f41-129">Eseguire</span><span class="sxs-lookup"><span data-stu-id="24f41-129">Run:</span></span>
    
        Enable-CsAdForest [-GroupDomain <FQDN of the domain in which to create the universal groups>]
    
    <span data-ttu-id="24f41-130">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="24f41-130">For example:</span></span>
    
        Enable-CsAdForest -GroupDomain domain1.contoso.com 
    
    <span data-ttu-id="24f41-131">Se non specifichi il parametro GroupDomain, il valore predefinito è il dominio locale.</span><span class="sxs-lookup"><span data-stu-id="24f41-131">If you do not specify the GroupDomain parameter, the default value is the local domain.</span></span> <span data-ttu-id="24f41-132">Se i gruppi universali sono stati creati in precedenza in un dominio che non è il dominio predefinito, è necessario specificare in modo esplicito il parametro GroupDomain.</span><span class="sxs-lookup"><span data-stu-id="24f41-132">If universal groups were created previously in a domain that is not the default domain, you must specify the GroupDomain parameter explicitly.</span></span>

5.  <span data-ttu-id="24f41-133">Attendere il completamento della replica di Active Directory oppure forzare la replica a tutti i controller di dominio elencati nello snap-in **siti e servizi di Active Directory** per il controller di dominio radice della foresta, prima di eseguire la preparazione del dominio.</span><span class="sxs-lookup"><span data-stu-id="24f41-133">Wait for Active Directory replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span>

6.  <span data-ttu-id="24f41-134">Verificare che la preparazione della foresta sia riuscita.</span><span class="sxs-lookup"><span data-stu-id="24f41-134">Verify that forest preparation was successful.</span></span> <span data-ttu-id="24f41-135">Eseguire</span><span class="sxs-lookup"><span data-stu-id="24f41-135">Run:</span></span>
    
        Get-CsAdForest 
    
    <span data-ttu-id="24f41-136">Questo cmdlet restituisce il valore di **LC\_FORESTSETTINGS\_stato\_pronto** se la preparazione della foresta è riuscita.</span><span class="sxs-lookup"><span data-stu-id="24f41-136">This cmdlet returns a value of **LC\_FORESTSETTINGS\_STATE\_READY** if forest preparation was successful.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="24f41-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24f41-137">See Also</span></span>


[<span data-ttu-id="24f41-138">Utilizzo dei cmdlet per annullare la preparazione della foresta per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24f41-138">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)  


[<span data-ttu-id="24f41-139">Preparazione della foresta per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24f41-139">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


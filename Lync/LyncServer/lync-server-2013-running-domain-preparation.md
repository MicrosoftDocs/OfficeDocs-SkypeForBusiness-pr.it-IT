---
title: 'Lync Server 2013: esecuzione della preparazione del dominio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running domain preparation
ms:assetid: 95dab800-1f2c-4506-b36c-99986643b149
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398761(v=OCS.15)
ms:contentKeyID: 48184847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 960a3664bb7b629a9d66b375d072f826ed9e2738
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050768"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-domain-preparation-for-lync-server-2013"></a><span data-ttu-id="4a861-102">Esecuzione della preparazione del dominio per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a861-102">Running domain preparation for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a861-103">_**Ultimo argomento modificato:** 2013-04-16_</span><span class="sxs-lookup"><span data-stu-id="4a861-103">_**Topic Last Modified:** 2013-04-16_</span></span>

<span data-ttu-id="4a861-104">È possibile utilizzare i cmdlet setup o Lync Server Management Shell per preparare i domini.</span><span class="sxs-lookup"><span data-stu-id="4a861-104">You can use Setup or Lync Server Management Shell cmdlets to prepare domains.</span></span> <span data-ttu-id="4a861-105">Il cmdlet che prepara un dominio è **Enable-CsAdDomain**.</span><span class="sxs-lookup"><span data-stu-id="4a861-105">The cmdlet that prepares a domain is **Enable-CsAdDomain**.</span></span>

<span data-ttu-id="4a861-106">La preparazione del dominio è il passaggio finale nella preparazione di servizi di dominio Active Directory per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4a861-106">Domain preparation is the final step in preparing Active Directory Domain Services for Lync Server 2013.</span></span>

<div>

## <a name="to-use-setup-to-prepare-domains"></a><span data-ttu-id="4a861-107">Per utilizzare il programma di installazione per preparare i domini</span><span class="sxs-lookup"><span data-stu-id="4a861-107">To use Setup to prepare domains</span></span>

1.  <span data-ttu-id="4a861-108">Eseguire l'accesso a un server del dominio come membro del gruppo Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="4a861-108">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="4a861-109">Dalla cartella o dal supporto di installazione di Lync Server 2013, eseguire Setup. exe per avviare la distribuzione guidata di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4a861-109">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>

3.  <span data-ttu-id="4a861-110">Fare clic su **Prepara Active Directory** e quindi attendere che venga determinato lo stato della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="4a861-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

4.  <span data-ttu-id="4a861-111">Al **Passaggio 5: Preparazione del dominio corrente**, fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="4a861-111">At **Step 5: Prepare Current Domain**, click **Run**.</span></span>

5.  <span data-ttu-id="4a861-112">Nella pagina **Prepara dominio** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4a861-112">On the **Prepare Domain** page, click **Next**.</span></span>

6.  <span data-ttu-id="4a861-113">Nella pagina **Esecuzione comandi in corso** ricercare **Stato attività: Operazione completata** e quindi fare clic su **Visualizza registro**.</span><span class="sxs-lookup"><span data-stu-id="4a861-113">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

7.  <span data-ttu-id="4a861-114">Nella colonna **azione** espandere **preparazione dominio**, \*\* \<\> cercare il risultato dell'esecuzione finale\*\* alla fine di ogni attività per verificare che la preparazione del dominio sia stata completata correttamente, chiudere il registro e quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="4a861-114">Under the **Action** column, expand **Domain Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that domain preparation completed successfully, close the log, and then click **Finish**.</span></span>

8.  <span data-ttu-id="4a861-115">Attendere che la replica di Active Directory venga completata o forzare la replica in tutti i controller di dominio elencati nello snap-in siti e servizi di Active Directory per il controller di dominio radice della foresta.</span><span class="sxs-lookup"><span data-stu-id="4a861-115">Wait for Active Directory replication to complete or force replication to all the domain controllers listed in the Active Directory Sites and Services snap-in for the forest root domain controller.</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-domain"></a><span data-ttu-id="4a861-116">Per utilizzare i cmdlet per preparare il dominio</span><span class="sxs-lookup"><span data-stu-id="4a861-116">To use cmdlets to prepare the domain</span></span>

1.  <span data-ttu-id="4a861-117">Eseguire l'accesso a un server del dominio come membro del gruppo Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="4a861-117">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="4a861-118">Installare i componenti di base di Lync Server come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="4a861-118">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="4a861-119">Dalla cartella o dal supporto di installazione di Lync Server 2013, eseguire Setup. exe per avviare la distribuzione guidata di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4a861-119">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="4a861-120">Se viene chiesto di installare Microsoft Visual C++ Redistributable, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="4a861-120">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="4a861-121">Nella finestra di dialogo installazione di Lync Server 2013 viene visualizzata una richiesta di installazione dei file di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4a861-121">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="4a861-122">Scegliere il percorso predefinito o **Sfoglia** per selezionare il percorso desiderato e quindi fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="4a861-122">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="4a861-123">Nella pagina Contratto di Licenza selezionare **Accetto i termini del Contratto di Licenza** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a861-123">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="4a861-124">Il programma di installazione installa i componenti di base di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4a861-124">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="4a861-125">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="4a861-125">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="4a861-126">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="4a861-126">Run:</span></span>
    
        Enable-CsAdDomain [-Domain <DomainFQDN>] 
    
    <span data-ttu-id="4a861-127">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4a861-127">For example:</span></span>
    
        Enable-CsAdDomain -Domain domain1.contoso.net 
    
    <span data-ttu-id="4a861-128">Se non si specifica il parametro Domain, per impostazione predefinita verrà utilizzato il dominio locale.</span><span class="sxs-lookup"><span data-stu-id="4a861-128">If you do not specify the Domain parameter, the default is the local domain.</span></span>

5.  <span data-ttu-id="4a861-129">Verificare che la preparazione del dominio abbia avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="4a861-129">Verify that domain preparation was successful.</span></span> <span data-ttu-id="4a861-130">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="4a861-130">Run:</span></span>
    
        Get-CsAdDomain [-Domain <Domain FQDN>] [-DomainController <Domain controller FQDN>] [-GlobalCatalog <Global catalog server FQDN>] [-GlobalSettingsDomainController <Domain controller FQDN where global settings are stored>] 
    
    <span data-ttu-id="4a861-131">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4a861-131">For example:</span></span>
    
        Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4a861-132">Il parametro GlobalSettingsDomainController consente di indicare dove vengono archiviate le impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="4a861-132">The parameter GlobalSettingsDomainController allows you to indicate where global settings are stored.</span></span> <span data-ttu-id="4a861-133">Se le impostazioni vengono archiviate nel contenitore di sistema (tipica delle distribuzioni di aggiornamento che non hanno eseguito la migrazione delle impostazioni globali nel contenitore di configurazione), è necessario definire un controller di dominio nella radice della foresta di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4a861-133">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global settings migrated to the Configuration container), you define a domain controller in the root of your Active Directory forest.</span></span> <span data-ttu-id="4a861-134">Se invece le impostazioni globali sono incluse nel contenitore Configuration, come avviene in genere con le distribuzioni nuove o di aggiornamento per cui è stata eseguita la migrazione delle impostazioni nel contenitore Configuration, definire un controller di dominio nella foresta.</span><span class="sxs-lookup"><span data-stu-id="4a861-134">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="4a861-135">Se non si specifica questo parametro, il cmdlet presuppone che le impostazioni siano archiviate nel contenitore di configurazione e si riferisca a qualsiasi controller&nbsp;di dominio in ad DS.</span><span class="sxs-lookup"><span data-stu-id="4a861-135">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in AD&nbsp;DS.</span></span>

    
    </div>
    
    <span data-ttu-id="4a861-136">Se non si specifica il parametro **Domain** , il valore predefinito è il dominio locale.</span><span class="sxs-lookup"><span data-stu-id="4a861-136">If you do not specify the **Domain** parameter, the default is the local domain.</span></span>
    
    <span data-ttu-id="4a861-137">Questo cmdlet restituisce un valore di **stato\_\_LC\_DOMAINSETTINGS pronto** se la preparazione del dominio ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="4a861-137">This cmdlet returns a value of **LC\_DOMAINSETTINGS\_STATE\_READY** if domain preparation was successful.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4a861-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a861-138">See Also</span></span>


[<span data-ttu-id="4a861-139">Utilizzo dei cmdlet per annullare la preparazione del dominio per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a861-139">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)  


[<span data-ttu-id="4a861-140">Preparazione dei domini per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a861-140">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


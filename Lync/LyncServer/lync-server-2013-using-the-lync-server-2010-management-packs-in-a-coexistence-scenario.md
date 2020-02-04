---
title: Uso dei Management Pack di Lync Server 2010 in uno scenario di coesistenza
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Server 2010 management packs in a coexistence scenario
ms:assetid: 8b792503-bd88-47fe-9d97-b071e8d429a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205078(v=OCS.15)
ms:contentKeyID: 48184772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 264cd8f1495840eb6dd86879f279110cd4de4784
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743886"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-lync-server-2010-management-packs-in-a-coexistence-scenario"></a><span data-ttu-id="cd946-102">Uso dei Management Pack di Lync Server 2010 in uno scenario di coesistenza</span><span class="sxs-lookup"><span data-stu-id="cd946-102">Using the Lync Server 2010 management packs in a coexistence scenario</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd946-103">_**Argomento Ultima modifica:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="cd946-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="cd946-104">Molti clienti adottano un programma di implementazione all'interno delle aziende in cui gli utenti vengono progressivamente migrati da Microsoft Lync Server 2010 a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cd946-104">Many customers adopt a rollout program inside of their enterprises in which users are progressively migrated from Microsoft Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="cd946-105">Gli amministratori di queste aziende si preoccuperanno del monitoraggio di entrambe le versioni di Lync Server per garantire che tutti gli utenti finali possano ottenere la migliore esperienza di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="cd946-105">The administrators at these companies will care about monitoring both versions of Lync Server to help ensure that all of their end users are getting the best possible communication experience.</span></span> <span data-ttu-id="cd946-106">Per questo scenario, il Management Pack di Lync Server 2013 supporta un percorso di migrazione affiancato con Lync Server 2010 Management Pack.</span><span class="sxs-lookup"><span data-stu-id="cd946-106">For this scenario, the Lync Server 2013 Management Pack supports a side-by-side migration path with the Lync Server 2010 Management Pack.</span></span>

<span data-ttu-id="cd946-107">In Lync Server 2010 i computer Lync Server sono stati scoperti tramite il documento di topologia archiviato con l'Central Management store.</span><span class="sxs-lookup"><span data-stu-id="cd946-107">In the Lync Server 2010, Lync Server computers were discovered through the topology document stored with the Central Management store.</span></span> <span data-ttu-id="cd946-108">In questa configurazione un singolo computer segnala l'esistenza di tutti gli altri computer Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cd946-108">In this configuration, a single computer would report the existence of all the other Lync Server computers.</span></span>

<span data-ttu-id="cd946-109">I Management Pack per Lync Server 2013 ora usano l'individuazione a livello di computer anziché il meccanismo di individuazione centralizzato usato in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="cd946-109">The management packs for Lync Server 2013 now use machine-level discovery instead of the central discovery mechanism that was used in Lync Server 2010.</span></span> <span data-ttu-id="cd946-110">Questo significa che ogni agente del centro di sistema si rivela essenzialmente e ne segnala l'esistenza a System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="cd946-110">This means that each System Center agent essentially discovers itself and reports its existence to System Center Operations Manager.</span></span> <span data-ttu-id="cd946-111">L'uso dell'individuazione a livello di computer semplifica l'amministrazione dell'infrastruttura del centro di sistema e consente anche versioni diverse di Lync Server Management Pack, ad esempio Management Pack per Lync Server 2010 e Management Pack per Lync Server 2013. per convivere più facilmente.</span><span class="sxs-lookup"><span data-stu-id="cd946-111">Using machine-level discovery simplifies administration of your System Center infrastructure and also enables different versions of the Lync Server management packs (for example, management packs for Lync Server 2010 and management packs for Lync Server 2013) to coexist more easily.</span></span>

<span data-ttu-id="cd946-112">Per supportare la migrazione, è necessario aggiornare il monitoraggio esistente di Lync Server 2010 per evitare lacune nella copertura.</span><span class="sxs-lookup"><span data-stu-id="cd946-112">To support this migration, you will first need to upgrade your existing Lync Server 2010 monitoring to avoid gaps in coverage.</span></span> <span data-ttu-id="cd946-113">A questo scopo, è necessario eleggere un computer Lync Server 2010 esistente per il servizio dello script di individuazione centralizzato per Lync Server 2010 prima di eseguire l'aggiornamento di Central Management store a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cd946-113">To do this, elect an existing Lync Server 2010 computer to service the Central Discovery script for the Lync Server 2010 before upgrading your Central Management store to Lync Server 2013.</span></span> <span data-ttu-id="cd946-114">Si tratta di un processo in quattro passaggi:</span><span class="sxs-lookup"><span data-stu-id="cd946-114">This is a four-step process:</span></span>

1.  <span data-ttu-id="cd946-115">Aggiornare i Management Pack di Lync Server 2010 all'aggiornamento cumulativo 7.</span><span class="sxs-lookup"><span data-stu-id="cd946-115">Upgrade the Lync Server 2010 Management Packs to Cumulative Update 7.</span></span>

2.  <span data-ttu-id="cd946-116">Indicare a un computer Lync Server 2010 di eseguire lo script di individuazione centralizzato.</span><span class="sxs-lookup"><span data-stu-id="cd946-116">Instruct a Lync Server 2010 computer to run the Central Discovery script.</span></span>

3.  <span data-ttu-id="cd946-117">Eseguire l'override del candidato di individuazione centralizzato nel Management Pack di Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="cd946-117">Override the Central Discovery Candidate in the Microsoft Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="cd946-118">Verificare che il nuovo candidato di individuazione centrale sia stato individuato.</span><span class="sxs-lookup"><span data-stu-id="cd946-118">Verify that the new Central Discovery Candidate has been discovered.</span></span>

<div>

## <a name="instructing-a-lync-server-2010-computer-to-run-the-central-discovery-script"></a><span data-ttu-id="cd946-119">Istruzione di un computer Lync Server 2010 per l'esecuzione dello script di individuazione centralizzato</span><span class="sxs-lookup"><span data-stu-id="cd946-119">Instructing a Lync Server 2010 Computer to Run the Central Discovery script</span></span>

<span data-ttu-id="cd946-120">Per nominare un computer dell'archivio di gestione non centrale, ad esempio un server front end di Lync Server, per gestire l'individuazione centralizzata, è necessario creare la chiave del registro di sistema seguente nel server dell'archivio di gestione non centrale:</span><span class="sxs-lookup"><span data-stu-id="cd946-120">To nominate a non-Central Management store computer (for example, a Lync Server Front End) server to handle central discovery, you will need to create the following registry key on the non-Central Management store server:</span></span>

<span data-ttu-id="cd946-121">HKLM\\software\\Microsoft\\Real-Time Communications\\Health\\CentralDiscoveryCandidate</span><span class="sxs-lookup"><span data-stu-id="cd946-121">HKLM\\Software\\Microsoft\\Real-Time Communications\\Health\\CentralDiscoveryCandidate</span></span>

<span data-ttu-id="cd946-122">Per creare questa chiave del registro di sistema, è possibile completare la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="cd946-122">You can create this registry key by completing the following procedure:</span></span>

1.  <span data-ttu-id="cd946-123">Fare clic sul pulsante **Start** e quindi su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="cd946-123">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="cd946-124">Nella finestra di dialogo **Esegui** Digitare **Regedit** e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="cd946-124">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="cd946-125">In Editor del registro di **sistema\_espandere\_HKEY computer locale**, espandere il **software**, espandere **Microsoft**e quindi espandere **comunicazioni in tempo reale**.</span><span class="sxs-lookup"><span data-stu-id="cd946-125">In Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Microsoft**, and then expand **Real-Time Communications**.</span></span>

4.  <span data-ttu-id="cd946-126">Fare clic con il pulsante destro del mouse su **integrità**, scegliere **nuovo**e quindi fare clic su **chiave**.</span><span class="sxs-lookup"><span data-stu-id="cd946-126">Right-click **Health**, click **New**, and then click **Key**.</span></span> <span data-ttu-id="cd946-127">Se il codice di **integrità** non esiste, fare clic con il pulsante destro del mouse su **comunicazioni in tempo reale**, scegliere **nuovo**e quindi fare clic su **chiave**.</span><span class="sxs-lookup"><span data-stu-id="cd946-127">If the **Health** key does not exist, then right-click **Real-Time Communications**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="cd946-128">Quando viene creata la nuova chiave, digitare integrità e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="cd946-128">When the new key is created, type Health, and then press ENTER.</span></span>
    
    <span data-ttu-id="cd946-129">Dopo aver creato la nuova chiave, digitare **CentralDiscoveryCandidate** e quindi premere INVIO per rinominare la chiave.</span><span class="sxs-lookup"><span data-stu-id="cd946-129">After the new key has been created, type **CentralDiscoveryCandidate** and then press ENTER to rename the key.</span></span>

<span data-ttu-id="cd946-130">Il computer può richiedere diverse ore per raccogliere la modifica.</span><span class="sxs-lookup"><span data-stu-id="cd946-130">It may take the computer several hours to pick up this change.</span></span> <span data-ttu-id="cd946-131">Per rendere effettive le modifiche, interrompere e riavviare il servizio agente di integrità.</span><span class="sxs-lookup"><span data-stu-id="cd946-131">To make the change take effect immediately, stop and then restart the Health Agent service.</span></span> <span data-ttu-id="cd946-132">Per riavviare il servizio Agente integrità, eseguire la procedura seguente nel computer Lync Server 2010:</span><span class="sxs-lookup"><span data-stu-id="cd946-132">To restart the Health Agent service, complete the following procedure on the Lync Server 2010 computer:</span></span>

1.  <span data-ttu-id="cd946-133">Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Accessori**, fare clic con il pulsante destro del mouse su **prompt dei comandi**e quindi scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="cd946-133">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="cd946-134">Nella finestra della console digitare il comando seguente e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="cd946-134">In the console window, type the following command and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="cd946-135">Verrà visualizzato un messaggio che indica che "il servizio di gestione del centro di sistema si arresta", seguito da un secondo messaggio che informa che il servizio è stato interrotto.</span><span class="sxs-lookup"><span data-stu-id="cd946-135">You will see a message that states "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped.</span></span> <span data-ttu-id="cd946-136">Dopo l'interruzione del servizio, è possibile riavviarlo digitando il comando seguente e premendo INVIO:</span><span class="sxs-lookup"><span data-stu-id="cd946-136">After the service has stopped, you can restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="overriding-the-central-discovery-candidate-in-the-lync-server-2010-management-pack"></a><span data-ttu-id="cd946-137">Override del candidato di individuazione centralizzato nel Management Pack di Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="cd946-137">Overriding the Central Discovery Candidate in the Lync Server 2010 Management Pack</span></span>

<span data-ttu-id="cd946-138">Dopo aver indicato a un computer Lync Server 2010 di segnalare i computer di Lync Server 2010, è necessario informare anche il Management Pack di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="cd946-138">After instructing a Lync Server 2010 computer to report on Lync Server 2010 computers, you will need to inform the Lync Server 2010 Management Pack about this change as well.</span></span> <span data-ttu-id="cd946-139">A tale scopo, è necessario creare un override nel Management Pack.</span><span class="sxs-lookup"><span data-stu-id="cd946-139">To do this, you will need to create an override in the Management Pack.</span></span> <span data-ttu-id="cd946-140">Questa operazione può essere eseguita completando la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="cd946-140">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="cd946-141">Nella console di Operations Manager fare clic su **creazione**.</span><span class="sxs-lookup"><span data-stu-id="cd946-141">In the Operations Manager console, click **Authoring**.</span></span>

2.  <span data-ttu-id="cd946-142">Nella scheda Creazione espandere **oggetti Management Pack**, fare clic su **individuazioni**oggetti e quindi fare clic su **ambito**.</span><span class="sxs-lookup"><span data-stu-id="cd946-142">On the Authoring tab, expand **Management Pack Objects**, click **Object Discoveries**, and then click **Scope**.</span></span>

3.  <span data-ttu-id="cd946-143">Nella finestra di dialogo **ambito Management Pack Objects** selezionare l'elemento con il **candidato di individuazione** di destinazione LS e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="cd946-143">In the **Scope Management Pack Objects** dialog box, select the item with the Target **LS Discovery Candidate** and then click **OK**.</span></span> <span data-ttu-id="cd946-144">Si noti che il candidato per l'individuazione LS verrà visualizzato solo se è stato installato il Management Pack di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="cd946-144">Note that LS Discovery Candidate will appear only if you have installed the Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="cd946-145">Nella console di Operations Manager fare clic con il pulsante destro del mouse su **candida scoperta**, scegliere **sostituzioni**, scegliere **Sostituisci individuazione oggetti**e quindi fare clic su **per tutti gli oggetti della classe: LS Discovery candidate**.</span><span class="sxs-lookup"><span data-stu-id="cd946-145">In the Operations Manager console, right-click **LS Discovery Candidate**, point to **Overrides**, point to **Override the Object Discovery**, and then click **For all objects of class: LS Discovery Candidate**.</span></span>

5.  <span data-ttu-id="cd946-146">Nella finestra di dialogo **Sostituisci proprietà** selezionare la casella di controllo **Sostituisci** accanto al **nome completo di Watchernode di individuazione centrale**dei parametri.</span><span class="sxs-lookup"><span data-stu-id="cd946-146">In the **Override Properties** dialog box, select the **Override** check box next to the parameter **Central Discovery WatcherNode Fqdn**.</span></span> <span data-ttu-id="cd946-147">Digitare il nome di dominio completo del computer Lync Server 2010 nelle caselle **valore di override** e **valore effettivo** .</span><span class="sxs-lookup"><span data-stu-id="cd946-147">Type the fully qualified domain name of the Lync Server 2010 computer in the **Override Value** and **Effective Value** boxes.</span></span> <span data-ttu-id="cd946-148">Selezionare la casella di controllo **imposta** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="cd946-148">Select the **Enforced** check box and click **OK**.</span></span>

<span data-ttu-id="cd946-149">Dopo aver creato l'override, è necessario riavviare il servizio integrità nel server di gestione radice.</span><span class="sxs-lookup"><span data-stu-id="cd946-149">After you have created the override, you need to restart the health service on the Root Management Server.</span></span> <span data-ttu-id="cd946-150">Per riavviare il servizio integrità, completare la procedura seguente nel server di gestione radice:</span><span class="sxs-lookup"><span data-stu-id="cd946-150">To restart the health service, complete the following procedure on the Root Management Server:</span></span>

1.  <span data-ttu-id="cd946-151">Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Accessori**, fare clic con il pulsante destro del mouse su **prompt dei comandi**e quindi scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="cd946-151">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="cd946-152">Nella finestra della console digitare il comando seguente e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="cd946-152">In the console window, type the following command, and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="cd946-153">Verrà visualizzato un messaggio che indica che "il servizio di gestione di System Center si arresta", seguito da un secondo messaggio che indica che il servizio è stato interrotto.</span><span class="sxs-lookup"><span data-stu-id="cd946-153">You will see a message stating that "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped.</span></span> <span data-ttu-id="cd946-154">Dopo l'interruzione del servizio, è possibile riavviarlo digitando il comando seguente e premendo INVIO:</span><span class="sxs-lookup"><span data-stu-id="cd946-154">After the service has stopped, you can then restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="verifying-that-the-new-central-discovery-candidate-was-discovered"></a><span data-ttu-id="cd946-155">Verificare che il nuovo candidato di individuazione centrale sia stato individuato</span><span class="sxs-lookup"><span data-stu-id="cd946-155">Verifying that the New Central Discovery Candidate Was Discovered</span></span>

<span data-ttu-id="cd946-156">Il passaggio finale prima dell'aggiornamento di Central Management store consiste nel verificare che il nuovo candidato di individuazione centrale sia stato individuato dal Management Pack di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="cd946-156">The final step before upgrading Central Management store is to make sure that the new central discovery candidate was discovered by the Lync Server 2010 Management Pack.</span></span> <span data-ttu-id="cd946-157">A questo scopo, aprire la console di Operations Manager e quindi fare clic su monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="cd946-157">To do this, open the Operations Manager console and then click Monitoring.</span></span> <span data-ttu-id="cd946-158">Nella scheda Monitoraggio espandere **Microsoft Lync Server 2010 Health**, espandere **individuazione topologia**e quindi fare clic su **visualizzazione stato individuazione**.</span><span class="sxs-lookup"><span data-stu-id="cd946-158">On the Monitoring tab, expand **Microsoft Lync Server 2010 Health**, expand **Topology Discovery**, and then click **Discovery State View**.</span></span> <span data-ttu-id="cd946-159">Verificare che una riga nella visualizzazione contenga un **percorso** che elenchi il nome di dominio completo del candidato di individuazione centrale.</span><span class="sxs-lookup"><span data-stu-id="cd946-159">Verify that a row in the display has a **Path** that lists the fully qualified domain name of the central discovery candidate.</span></span> <span data-ttu-id="cd946-160">Dovresti anche verificare che lo stato del computer sia segnalato come **integro**.</span><span class="sxs-lookup"><span data-stu-id="cd946-160">You should also verify that the computer state is reported as **Healthy**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


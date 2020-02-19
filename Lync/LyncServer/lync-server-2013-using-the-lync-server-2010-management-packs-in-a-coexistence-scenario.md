---
title: Utilizzo dei Management Pack di Lync Server 2010 in uno scenario di coesistenza
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
ms.openlocfilehash: cc198abe47d76abae2ae49f426ac433c29129790
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138607"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-the-lync-server-2010-management-packs-in-a-coexistence-scenario"></a><span data-ttu-id="b2f61-102">Utilizzo dei Management Pack di Lync Server 2010 in uno scenario di coesistenza</span><span class="sxs-lookup"><span data-stu-id="b2f61-102">Using the Lync Server 2010 management packs in a coexistence scenario</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2f61-103">_**Ultimo argomento modificato:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="b2f61-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="b2f61-104">Molti clienti adottano un programma di implementazione all'interno delle proprie aziende in cui gli utenti vengono progressivamente migrati da Microsoft Lync Server 2010 a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2f61-104">Many customers adopt a rollout program inside of their enterprises in which users are progressively migrated from Microsoft Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="b2f61-105">Gli amministratori di queste società si preoccuperanno del monitoraggio di entrambe le versioni di Lync Server per garantire che tutti gli utenti finali possano ottenere la migliore esperienza di comunicazione possibile.</span><span class="sxs-lookup"><span data-stu-id="b2f61-105">The administrators at these companies will care about monitoring both versions of Lync Server to help ensure that all of their end users are getting the best possible communication experience.</span></span> <span data-ttu-id="b2f61-106">Per questo scenario, il Management Pack di Lync Server 2013 supporta un percorso di migrazione affiancato con Lync Server 2010 Management Pack.</span><span class="sxs-lookup"><span data-stu-id="b2f61-106">For this scenario, the Lync Server 2013 Management Pack supports a side-by-side migration path with the Lync Server 2010 Management Pack.</span></span>

<span data-ttu-id="b2f61-107">In Lync Server 2010, i computer Lync Server sono stati individuati tramite il documento della topologia archiviato con l'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="b2f61-107">In the Lync Server 2010, Lync Server computers were discovered through the topology document stored with the Central Management store.</span></span> <span data-ttu-id="b2f61-108">In questa configurazione, un singolo computer segnala l'esistenza di tutti gli altri computer Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b2f61-108">In this configuration, a single computer would report the existence of all the other Lync Server computers.</span></span>

<span data-ttu-id="b2f61-109">I Management Pack per Lync Server 2013 ora utilizzano l'individuazione a livello di computer invece del meccanismo di individuazione centrale utilizzato in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="b2f61-109">The management packs for Lync Server 2013 now use machine-level discovery instead of the central discovery mechanism that was used in Lync Server 2010.</span></span> <span data-ttu-id="b2f61-110">Ciò significa che ogni agente System Center individua se stesso e segnala la sua esistenza a System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="b2f61-110">This means that each System Center agent essentially discovers itself and reports its existence to System Center Operations Manager.</span></span> <span data-ttu-id="b2f61-111">L'utilizzo dell'individuazione a livello di computer semplifica l'amministrazione dell'infrastruttura del centro di sistema e consente anche diverse versioni dei Management Pack di Lync Server (ad esempio, Management Pack per Lync Server 2010 e Management Pack per Lync Server 2013) coesistere più facilmente.</span><span class="sxs-lookup"><span data-stu-id="b2f61-111">Using machine-level discovery simplifies administration of your System Center infrastructure and also enables different versions of the Lync Server management packs (for example, management packs for Lync Server 2010 and management packs for Lync Server 2013) to coexist more easily.</span></span>

<span data-ttu-id="b2f61-112">Per supportare la migrazione, è necessario prima di tutto aggiornare il monitoraggio di Lync Server 2010 esistente per evitare lacune nella copertura.</span><span class="sxs-lookup"><span data-stu-id="b2f61-112">To support this migration, you will first need to upgrade your existing Lync Server 2010 monitoring to avoid gaps in coverage.</span></span> <span data-ttu-id="b2f61-113">A tale scopo, eleggere un computer Lync Server 2010 esistente per il servizio dello script di individuazione centrale per Lync Server 2010 prima di eseguire l'aggiornamento dell'archivio di gestione centrale a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2f61-113">To do this, elect an existing Lync Server 2010 computer to service the Central Discovery script for the Lync Server 2010 before upgrading your Central Management store to Lync Server 2013.</span></span> <span data-ttu-id="b2f61-114">Questo processo si articola in quattro passaggi:</span><span class="sxs-lookup"><span data-stu-id="b2f61-114">This is a four-step process:</span></span>

1.  <span data-ttu-id="b2f61-115">Eseguire l'aggiornamento dei Management Pack di Lync Server 2010 all'aggiornamento cumulativo 7.</span><span class="sxs-lookup"><span data-stu-id="b2f61-115">Upgrade the Lync Server 2010 Management Packs to Cumulative Update 7.</span></span>

2.  <span data-ttu-id="b2f61-116">Indicare a un computer Lync Server 2010 di eseguire lo script di individuazione centrale.</span><span class="sxs-lookup"><span data-stu-id="b2f61-116">Instruct a Lync Server 2010 computer to run the Central Discovery script.</span></span>

3.  <span data-ttu-id="b2f61-117">Eseguire l'override del candidato di individuazione centrale in Microsoft Lync Server 2010 Management Pack.</span><span class="sxs-lookup"><span data-stu-id="b2f61-117">Override the Central Discovery Candidate in the Microsoft Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="b2f61-118">Verificare che il nuovo candidato di individuazione centrale sia stato individuato.</span><span class="sxs-lookup"><span data-stu-id="b2f61-118">Verify that the new Central Discovery Candidate has been discovered.</span></span>

<div>

## <a name="instructing-a-lync-server-2010-computer-to-run-the-central-discovery-script"></a><span data-ttu-id="b2f61-119">Impostazione di un computer Lync Server 2010 per l'esecuzione dello script di individuazione centrale</span><span class="sxs-lookup"><span data-stu-id="b2f61-119">Instructing a Lync Server 2010 Computer to Run the Central Discovery script</span></span>

<span data-ttu-id="b2f61-120">Per nominare un computer dell'archivio di gestione non centrale, ad esempio un server Lync Server front end, per gestire l'individuazione centrale, è necessario creare la seguente chiave del registro di sistema nel server di gestione non centrale:</span><span class="sxs-lookup"><span data-stu-id="b2f61-120">To nominate a non-Central Management store computer (for example, a Lync Server Front End) server to handle central discovery, you will need to create the following registry key on the non-Central Management store server:</span></span>

<span data-ttu-id="b2f61-121">HKLM\\software\\Microsoft\\Real-Time Communications\\Health\\CentralDiscoveryCandidate</span><span class="sxs-lookup"><span data-stu-id="b2f61-121">HKLM\\Software\\Microsoft\\Real-Time Communications\\Health\\CentralDiscoveryCandidate</span></span>

<span data-ttu-id="b2f61-122">È possibile creare questa chiave del Registro di sistema completando la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="b2f61-122">You can create this registry key by completing the following procedure:</span></span>

1.  <span data-ttu-id="b2f61-123">Fare clic sul pulsante **Start**, quindi scegliere **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="b2f61-123">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="b2f61-124">Nella finestra di dialogo **Esegui** digitare **regedit** e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="b2f61-124">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="b2f61-125">In Editor del registro di **sistema\_espandere\_HKEY computer locale**, espandere **software**, espandere **Microsoft**e quindi espandere **comunicazioni in tempo reale**.</span><span class="sxs-lookup"><span data-stu-id="b2f61-125">In Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Microsoft**, and then expand **Real-Time Communications**.</span></span>

4.  <span data-ttu-id="b2f61-p105">Fare clic con il pulsante destro del mouse su **Health**, scegliere **Nuovo** e quindi **Chiave**. Se la chiave **Health** non esiste, fare clic con il pulsante destro del mouse su **Real-Time Communications**, scegliere **Nuovo** e quindi **Chiave**. Dopo aver creato la nuova chiave, digitare Health e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="b2f61-p105">Right-click **Health**, click **New**, and then click **Key**. If the **Health** key does not exist, then right-click **Real-Time Communications**, point to **New**, and then click **Key**. When the new key is created, type Health, and then press ENTER.</span></span>
    
    <span data-ttu-id="b2f61-129">Dopo aver creato la nuova chiave, digitare **CentralDiscoveryCandidate** e quindi premere INVIO per rinominarla.</span><span class="sxs-lookup"><span data-stu-id="b2f61-129">After the new key has been created, type **CentralDiscoveryCandidate** and then press ENTER to rename the key.</span></span>

<span data-ttu-id="b2f61-130">L'acquisizione di questa modifica da parte del computer può richiedere diverse ore.</span><span class="sxs-lookup"><span data-stu-id="b2f61-130">It may take the computer several hours to pick up this change.</span></span> <span data-ttu-id="b2f61-131">Per fare in modo che la modifica venga applicata immediatamente, arrestare e quindi riavviare il servizio Agente integrità.</span><span class="sxs-lookup"><span data-stu-id="b2f61-131">To make the change take effect immediately, stop and then restart the Health Agent service.</span></span> <span data-ttu-id="b2f61-132">Per riavviare il servizio agente di integrità, eseguire la procedura seguente nel computer Lync Server 2010:</span><span class="sxs-lookup"><span data-stu-id="b2f61-132">To restart the Health Agent service, complete the following procedure on the Lync Server 2010 computer:</span></span>

1.  <span data-ttu-id="b2f61-133">Fare clic su **Start**, scegliere **Tutti i programmi** e **Accessori**, fare clic con il pulsante destro del mouse su **Prompt dei comandi** e quindi scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="b2f61-133">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="b2f61-134">Nella finestra della console digitare il comando seguente e premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="b2f61-134">In the console window, type the following command and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="b2f61-p107">Verrà visualizzato un messaggio indicante che il servizio System Center Management è in fase di arresto, seguito da un secondo messaggio di conferma dell'avvenuto arresto. Dopo che il servizio è stato arrestato, è possibile riavviarlo digitando il comando seguente e premendo INVIO:</span><span class="sxs-lookup"><span data-stu-id="b2f61-p107">You will see a message that states "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped. After the service has stopped, you can restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="overriding-the-central-discovery-candidate-in-the-lync-server-2010-management-pack"></a><span data-ttu-id="b2f61-137">Sostituzione del candidato di individuazione centrale in Lync Server 2010 Management Pack</span><span class="sxs-lookup"><span data-stu-id="b2f61-137">Overriding the Central Discovery Candidate in the Lync Server 2010 Management Pack</span></span>

<span data-ttu-id="b2f61-138">Dopo aver insegnato a un computer Lync Server 2010 a segnalare i computer Lync Server 2010, è necessario informare anche il Management Pack di Lync Server 2010 su questa modifica.</span><span class="sxs-lookup"><span data-stu-id="b2f61-138">After instructing a Lync Server 2010 computer to report on Lync Server 2010 computers, you will need to inform the Lync Server 2010 Management Pack about this change as well.</span></span> <span data-ttu-id="b2f61-139">A tale scopo, sarà necessario creare una sostituzione in Management Pack.</span><span class="sxs-lookup"><span data-stu-id="b2f61-139">To do this, you will need to create an override in the Management Pack.</span></span> <span data-ttu-id="b2f61-140">A tale scopo, effettuare la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="b2f61-140">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="b2f61-141">Nella console di Operations Manager fare clic su **Creazione e modifica**.</span><span class="sxs-lookup"><span data-stu-id="b2f61-141">In the Operations Manager console, click **Authoring**.</span></span>

2.  <span data-ttu-id="b2f61-142">Nella scheda Creazione e modifica espandere **Oggetti Management Pack**, fare clic su **Individuazioni oggetti** e quindi fare clic su **Ambito**.</span><span class="sxs-lookup"><span data-stu-id="b2f61-142">On the Authoring tab, expand **Management Pack Objects**, click **Object Discoveries**, and then click **Scope**.</span></span>

3.  <span data-ttu-id="b2f61-143">Nella finestra di dialogo **Crea ambito oggetti Management Pack in base a destinazioni** selezionare l'elemento con destinazione il **candidato di individuazione LS** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b2f61-143">In the **Scope Management Pack Objects** dialog box, select the item with the Target **LS Discovery Candidate** and then click **OK**.</span></span> <span data-ttu-id="b2f61-144">Si noti che il candidato di individuazione LS verrà visualizzato solo se è stato installato il Management Pack di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="b2f61-144">Note that LS Discovery Candidate will appear only if you have installed the Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="b2f61-145">Nella console di Operations Manager fare clic con il pulsante destro del mouse sul **candidato individuazione LS**, scegliere **Sostituzione**, **Sostituzione individuazione oggetto** e fare clic su **Per tutti gli oggetti della classe: candidato individuazione LS**.</span><span class="sxs-lookup"><span data-stu-id="b2f61-145">In the Operations Manager console, right-click **LS Discovery Candidate**, point to **Overrides**, point to **Override the Object Discovery**, and then click **For all objects of class: LS Discovery Candidate**.</span></span>

5.  <span data-ttu-id="b2f61-146">Nella finestra di dialogo **Proprietà di sostituzione** selezionare la casella di controllo **Sostituzione** accanto al parametro **FQDN WatcherNode individuazione centrale**.</span><span class="sxs-lookup"><span data-stu-id="b2f61-146">In the **Override Properties** dialog box, select the **Override** check box next to the parameter **Central Discovery WatcherNode Fqdn**.</span></span> <span data-ttu-id="b2f61-147">Digitare il nome di dominio completo del computer Lync Server 2010 nelle caselle **valore di sostituzione** e **valore effettivo** .</span><span class="sxs-lookup"><span data-stu-id="b2f61-147">Type the fully qualified domain name of the Lync Server 2010 computer in the **Override Value** and **Effective Value** boxes.</span></span> <span data-ttu-id="b2f61-148">Selezionare la casella di controllo **Imposto** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b2f61-148">Select the **Enforced** check box and click **OK**.</span></span>

<span data-ttu-id="b2f61-p111">Dopo aver creato la sostituzione, è necessario riavviare il servizio di integrità nel server di gestione radice. Per riavviare il servizio di integrità, completare la procedura seguente nel server di gestione radice:</span><span class="sxs-lookup"><span data-stu-id="b2f61-p111">After you have created the override, you need to restart the health service on the Root Management Server. To restart the health service, complete the following procedure on the Root Management Server:</span></span>

1.  <span data-ttu-id="b2f61-151">Fare clic su **Start**, scegliere **Tutti i programmi** e **Accessori**, fare clic con il pulsante destro del mouse su **Prompt dei comandi** e quindi scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="b2f61-151">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="b2f61-152">Nella finestra della console digitare il comando seguente e premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="b2f61-152">In the console window, type the following command, and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="b2f61-p112">Verrà visualizzato un messaggio indicante che il servizio System Center Management è in fase di arresto, seguito da un secondo messaggio di conferma dell'avvenuto arresto. Dopo che il servizio è stato arrestato, è possibile riavviarlo digitando il comando seguente e premendo INVIO:</span><span class="sxs-lookup"><span data-stu-id="b2f61-p112">You will see a message stating that "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped. After the service has stopped, you can then restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="verifying-that-the-new-central-discovery-candidate-was-discovered"></a><span data-ttu-id="b2f61-155">Verifica dell'individuazione del nuovo candidato di individuazione centrale</span><span class="sxs-lookup"><span data-stu-id="b2f61-155">Verifying that the New Central Discovery Candidate Was Discovered</span></span>

<span data-ttu-id="b2f61-156">Il passaggio finale prima dell'aggiornamento dell'archivio di gestione centrale consiste nel verificare che il nuovo candidato di individuazione centrale sia stato individuato dal Management Pack di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="b2f61-156">The final step before upgrading Central Management store is to make sure that the new central discovery candidate was discovered by the Lync Server 2010 Management Pack.</span></span> <span data-ttu-id="b2f61-157">A tale scopo, aprire la console di Operations Manager  e quindi fare clic su Monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="b2f61-157">To do this, open the Operations Manager console and then click Monitoring.</span></span> <span data-ttu-id="b2f61-158">Nella scheda Monitoraggio espandere **Integrità Microsoft Lync Server 2010**, **Individuazione topologia** e quindi la **vista dello stato di individuazione**.</span><span class="sxs-lookup"><span data-stu-id="b2f61-158">On the Monitoring tab, expand **Microsoft Lync Server 2010 Health**, expand **Topology Discovery**, and then click **Discovery State View**.</span></span> <span data-ttu-id="b2f61-159">Verificare che una riga nella vista presenti un **percorso** indicante il nome di dominio completo del candidato di individuazione centrale.</span><span class="sxs-lookup"><span data-stu-id="b2f61-159">Verify that a row in the display has a **Path** that lists the fully qualified domain name of the central discovery candidate.</span></span> <span data-ttu-id="b2f61-160">È inoltre necessario verificare che lo stato del computer risulti **integro**.</span><span class="sxs-lookup"><span data-stu-id="b2f61-160">You should also verify that the computer state is reported as **Healthy**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


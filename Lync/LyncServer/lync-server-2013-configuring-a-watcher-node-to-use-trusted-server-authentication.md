---
title: Configurazione di un nodo Watcher per l'uso dell'autenticazione trusted server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a watcher node to use Trusted Server authentication
ms:assetid: 42d879ac-aa90-4ed6-b5e2-1e208711672a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204852(v=OCS.15)
ms:contentKeyID: 48184017
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6634fa55424190d2e0a05aece38d88977d2f6bca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-use-trusted-server-authentication"></a><span data-ttu-id="f33d8-102">Configurazione di un nodo Watcher in Lync Server 2013 per l'uso dell'autenticazione server attendibile</span><span class="sxs-lookup"><span data-stu-id="f33d8-102">Configuring a watcher node in Lync Server 2013 to use Trusted Server authentication</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f33d8-103">_**Argomento Ultima modifica:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="f33d8-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="f33d8-104">Se il computer del nodo Watcher si trova all'interno della rete perimetrale, l'autenticazione basata su server attendibile può ridurre notevolmente le imposte amministrative per il mantenimento di un singolo certificato anziché di numerose password degli account utente.</span><span class="sxs-lookup"><span data-stu-id="f33d8-104">If your watcher node computer lies inside the perimeter network, using Trusted Server authentication can greatly reduce administration taxes to maintaining a single certificate rather than numerous user account passwords.</span></span>

<span data-ttu-id="f33d8-105">Il primo passaggio della configurazione dell'autenticazione del server attendibile consiste nel creare un pool di applicazioni attendibili per ospitare il computer del nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="f33d8-105">The first step in configuring Trusted Server authentication is to create a trusted application pool to host the watcher node computer.</span></span> <span data-ttu-id="f33d8-106">Dopo aver creato il pool di applicazioni attendibili, è necessario configurare le transazioni sintetiche nel nodo Watcher per l'esecuzione come applicazione attendibile.</span><span class="sxs-lookup"><span data-stu-id="f33d8-106">After the trusted application pool has been created, you must then configure synthetic transactions on that watcher node to run as a trusted application.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="f33d8-107">Un'applicazione attendibile è un'applicazione a cui viene assegnato lo stato attendibile per l'esecuzione come parte di Lync Server 2013, ma questa non è una parte incorporata del prodotto.</span><span class="sxs-lookup"><span data-stu-id="f33d8-107">A trusted application is an application that is given trusted status to run as part of Lync Server 2013, but that is not a built-in part of the product.</span></span> <span data-ttu-id="f33d8-108">Lo stato attendibile indica che l'applicazione non verrà contestata per l'autenticazione ogni volta che viene eseguita.</span><span class="sxs-lookup"><span data-stu-id="f33d8-108">Trusted status means that the application will not be challenged for authentication each time it runs.</span></span>



</div>

<span data-ttu-id="f33d8-109">Per creare un pool di applicazioni attendibili, aprire Lync Server 2013 Management Shell ed eseguire un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="f33d8-109">To create a trusted application pool, open the Lync Server 2013 Management Shell and run a command similar to this:</span></span>

    New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond

<div>


> [!NOTE]
> <span data-ttu-id="f33d8-110">Per informazioni dettagliate sui parametri usati nel comando precedente, digitare quanto segue al prompt di Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="f33d8-110">For details about the parameters used in the preceding command, type the following at the Lync Server Management Shell prompt:</span></span><BR><span data-ttu-id="f33d8-111">Get-Help New-CsTrustedApplicationPool-Full | più</span><span class="sxs-lookup"><span data-stu-id="f33d8-111">Get-Help New-CsTrustedApplicationPool -Full | more</span></span>



</div>

<span data-ttu-id="f33d8-112">Dopo aver creato il pool di applicazioni attendibili, configurare il computer del nodo Watcher per eseguire transazioni sintetiche come applicazione attendibile.</span><span class="sxs-lookup"><span data-stu-id="f33d8-112">After creating the trusted application pool, configure the watcher node computer to run synthetic transactions as a trusted application.</span></span> <span data-ttu-id="f33d8-113">Questa operazione viene eseguita usando il cmdlet **New-CsTrustedApplication** e un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="f33d8-113">This is done by using the **New-CsTrustedApplication** cmdlet and a command similar to this:</span></span>

    New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061

<span data-ttu-id="f33d8-114">Quando il comando precedente viene completato e l'applicazione attendibile è stata creata, eseguire Enable-CsTopology per verificare che le modifiche abbiano effetto:</span><span class="sxs-lookup"><span data-stu-id="f33d8-114">When the preceding command completes and the trusted application has been created, run Enable-CsTopology to make sure that the changes take effect:</span></span>

    Enable-CsTopology

<span data-ttu-id="f33d8-115">Dopo aver eseguito Enable-CsTopology, è consigliabile riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="f33d8-115">After running Enable-CsTopology, we recommend that you restart the computer.</span></span>

<span data-ttu-id="f33d8-116">Per verificare che sia stata creata la nuova applicazione attendibile, digitare quanto segue al prompt di Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="f33d8-116">To verify that the new trusted application has been created, type the following at the Lync Server Management Shell prompt:</span></span>

    Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"

<div>

## <a name="configuring-a-default-certificate-on-the-watcher-node"></a><span data-ttu-id="f33d8-117">Configurazione di un certificato predefinito nel nodo Watcher</span><span class="sxs-lookup"><span data-stu-id="f33d8-117">Configuring a Default Certificate on the Watcher Node</span></span>

<span data-ttu-id="f33d8-118">Ogni nodo Watcher deve avere un certificato predefinito assegnato tramite la distribuzione guidata di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f33d8-118">Each watcher node must have a Default certificate assigned by using the Lync Server Deployment Wizard.</span></span>

<span data-ttu-id="f33d8-119">**Per assegnare un certificato predefinito**</span><span class="sxs-lookup"><span data-stu-id="f33d8-119">**To assign a Default certificate**</span></span>

1.  <span data-ttu-id="f33d8-120">Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Lync Server**e quindi fare clic su **distribuzione guidata Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="f33d8-120">Click **Start**, click **All Programs**, click **Lync Server**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="f33d8-121">Nella distribuzione guidata di Lync Server fare clic su **Installa o aggiorna Lync Server System** , quindi fare clic su **Esegui** sotto la richiesta di titolo **, installa o assegna certificato**.</span><span class="sxs-lookup"><span data-stu-id="f33d8-121">In the Lync Server Deployment Wizard, click **Install or Update Lync Server System** and then click **Run** under the heading **Request, Install, or Assign Certificate**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="f33d8-122">Se il pulsante <STRONG>Esegui</STRONG> è disabilitato, potrebbe essere necessario fare prima clic su <STRONG>Esegui</STRONG> in <STRONG>Installa archivio configurazione locale</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="f33d8-122">If the <STRONG>Run</STRONG> button is disabled, you may need to first click <STRONG>Run</STRONG> under <STRONG>Install Local Configuration Store</STRONG>.</span></span>

    
    </div>

3.  <span data-ttu-id="f33d8-123">Esegui una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f33d8-123">Do one of the following:</span></span>
    
      - <span data-ttu-id="f33d8-124">Se si dispone già di un certificato che può essere usato come certificato predefinito, fare clic su **predefinito** nella procedura guidata certificato e quindi fare clic su **assegna**.</span><span class="sxs-lookup"><span data-stu-id="f33d8-124">If you already have a certificate that can be used as the Default certificate, click **Default** in the Certificate wizard and then click **Assign**.</span></span> <span data-ttu-id="f33d8-125">Seguire i passaggi della procedura guidata assegnazione certificati per assegnare il certificato.</span><span class="sxs-lookup"><span data-stu-id="f33d8-125">Follow the steps in the Certificate Assignment wizard to assign that certificate.</span></span>
    
      - <span data-ttu-id="f33d8-126">Se è necessario richiedere un certificato per l'uso del certificato predefinito, fare clic su **Richiedi** e quindi seguire i passaggi della richiesta guidata certificato per richiedere tale certificato.</span><span class="sxs-lookup"><span data-stu-id="f33d8-126">If you need to request a certificate for use the Default certificate, click **Request** and then follow the steps in the Certificate Request wizard to request that certificate.</span></span> <span data-ttu-id="f33d8-127">Se si usano i valori predefiniti per il certificato del server Web, si ottiene un certificato che è possibile assegnare come certificato predefinito.</span><span class="sxs-lookup"><span data-stu-id="f33d8-127">If you use the default values for the Web Server certificate, you get a certificate that you can assign as the Default certificate.</span></span>

</div>

<div>

## <a name="installing-and-configuring-a-watcher-node"></a><span data-ttu-id="f33d8-128">Installazione e configurazione di un nodo Watcher</span><span class="sxs-lookup"><span data-stu-id="f33d8-128">Installing and Configuring a Watcher Node</span></span>

<span data-ttu-id="f33d8-129">Dopo aver riavviato il computer del nodo Watcher e configurato un certificato, è necessario eseguire il file WatcherNode. msi.</span><span class="sxs-lookup"><span data-stu-id="f33d8-129">After you have restarted the watcher node computer and configured a certificate, you need to run the file Watchernode.msi.</span></span> <span data-ttu-id="f33d8-130">È necessario eseguire WatcherNode. msi in un computer in cui sono installati sia i file dell'agente Operations Manager che i componenti principali di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f33d8-130">(You must run Watchernode.msi on a computer where both the Operations Manager agent files and the Lync Server 2013 core components are installed.)</span></span>

<span data-ttu-id="f33d8-131">**Per installare e configurare un nodo Watcher**</span><span class="sxs-lookup"><span data-stu-id="f33d8-131">**To install and configure a watcher node**</span></span>

1.  <span data-ttu-id="f33d8-132">Aprire Lync Server Management Shell facendo clic sul pulsante **Start**, scegliendo **tutti i programmi**, facendo clic su **Lync Server**e quindi su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f33d8-132">Open the Lync Server Management Shell by clicking **Start**, clicking **All Programs**, clicking **Lync Server**, and then clicking **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f33d8-133">In Lync Server Management Shell digitare il comando seguente e quindi premere INVIO (specificare il percorso effettivo della copia di WatcherNode. msi):</span><span class="sxs-lookup"><span data-stu-id="f33d8-133">In the Lync Server Management Shell, type the following command and then press ENTER (specify the actual path to your copy of Watchernode.msi):</span></span>
    
        C:\Tools\Watchernode.msi Authentication=TrustedServer
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="f33d8-134">È anche possibile eseguire WatcherNode. msi da una finestra di comando.</span><span class="sxs-lookup"><span data-stu-id="f33d8-134">You can also run Watchernode.msi from a command window.</span></span> <span data-ttu-id="f33d8-135">Per aprire una finestra di comando, fare clic su <STRONG>Start</STRONG>, fare clic con il pulsante destro del mouse su <STRONG>prompt dei comandi</STRONG>e quindi scegliere <STRONG>Esegui come amministratore</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="f33d8-135">To open a command window, click <STRONG>Start</STRONG>, right-click <STRONG>Command Prompt</STRONG>, and then click <STRONG>Run as administrator</STRONG>.</span></span> <span data-ttu-id="f33d8-136">Quando viene visualizzata la finestra di comando, digitare lo stesso comando precedente.</span><span class="sxs-lookup"><span data-stu-id="f33d8-136">When the command window opens, type the same preceding command.</span></span>

    
    </div>

<span data-ttu-id="f33d8-137">Tieni presente che la coppia nome/valore nel comando precedente Authentication = TrustedServer fa distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="f33d8-137">Note that the name/value pair in the preceding command Authentication=TrustedServer is case-sensitive.</span></span> <span data-ttu-id="f33d8-138">È necessario digitarlo esattamente come illustrato.</span><span class="sxs-lookup"><span data-stu-id="f33d8-138">You must type it exactly as shown.</span></span> <span data-ttu-id="f33d8-139">Il comando seguente non riesce perché non usa l'involucro lettera corretto:</span><span class="sxs-lookup"><span data-stu-id="f33d8-139">The following command fails because it does not use the correct letter casing:</span></span>

<span data-ttu-id="f33d8-140">C:\\strumenti\\di autenticazione WatcherNode. msi = TrustedServer</span><span class="sxs-lookup"><span data-stu-id="f33d8-140">C:\\Tools\\Watchernode.msi authentication=trustedserver</span></span>

<span data-ttu-id="f33d8-141">Puoi usare la modalità TrustedServer solo con i computer che si trovano all'interno della rete perimetrale.</span><span class="sxs-lookup"><span data-stu-id="f33d8-141">You can use TrustedServer mode only with computers that are located within the perimeter network.</span></span> <span data-ttu-id="f33d8-142">Quando un nodo Watcher viene eseguito in modalità TrustedServer, gli amministratori non devono gestire le password degli utenti di test nel computer.</span><span class="sxs-lookup"><span data-stu-id="f33d8-142">When a watcher node is running in TrustedServer mode, administrators do not have to maintain test user passwords on the computer.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


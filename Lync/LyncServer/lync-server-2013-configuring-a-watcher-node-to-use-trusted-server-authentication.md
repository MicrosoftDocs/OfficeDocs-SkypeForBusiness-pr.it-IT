---
title: Configurazione di un nodo Watcher per l'utilizzo dell'autenticazione del server attendibile
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to use Trusted Server authentication
ms:assetid: 42d879ac-aa90-4ed6-b5e2-1e208711672a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204852(v=OCS.15)
ms:contentKeyID: 48184017
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ba69980f97e901703f51f71729c661821e70e61
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037396"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-use-trusted-server-authentication"></a><span data-ttu-id="719fa-102">Configurazione di un nodo Watcher in Lync Server 2013 per l'utilizzo dell'autenticazione server attendibile</span><span class="sxs-lookup"><span data-stu-id="719fa-102">Configuring a watcher node in Lync Server 2013 to use Trusted Server authentication</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="719fa-103">_**Ultimo argomento modificato:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="719fa-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="719fa-104">Se il computer del nodo Watcher si trova all'interno della rete perimetrale, l'uso dell'autenticazione Server attendibile può ridurre notevolmente le attività di amministrazione richieste dal momento che implica il mantenimento di un singolo certificato anziché di numerose password per i vari account utente.</span><span class="sxs-lookup"><span data-stu-id="719fa-104">If your watcher node computer lies inside the perimeter network, using Trusted Server authentication can greatly reduce administration taxes to maintaining a single certificate rather than numerous user account passwords.</span></span>

<span data-ttu-id="719fa-p101">Il primo passaggio per la configurazione dell'autenticazione Server attendibile consiste nel creare un pool di applicazioni attendibili in cui ospitare il computer del nodo Watcher. Dopo aver creato il pool, è necessario configurare l'esecuzione delle transazioni sintetiche sul nodo Watcher come applicazione attendibile.</span><span class="sxs-lookup"><span data-stu-id="719fa-p101">The first step in configuring Trusted Server authentication is to create a trusted application pool to host the watcher node computer. After the trusted application pool has been created, you must then configure synthetic transactions on that watcher node to run as a trusted application.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="719fa-107">Un'applicazione attendibile è un'applicazione a cui viene assegnato lo stato attendibile per l'esecuzione come parte di Lync Server 2013, ma non si tratta di una parte incorporata del prodotto.</span><span class="sxs-lookup"><span data-stu-id="719fa-107">A trusted application is an application that is given trusted status to run as part of Lync Server 2013, but that is not a built-in part of the product.</span></span> <span data-ttu-id="719fa-108">Lo stato attendibile indica che all'applicazione non verrà richiesta l'autenticazione a ogni esecuzione.</span><span class="sxs-lookup"><span data-stu-id="719fa-108">Trusted status means that the application will not be challenged for authentication each time it runs.</span></span>



</div>

<span data-ttu-id="719fa-109">Per creare un pool di applicazioni attendibili, aprire Lync Server 2013 Management Shell ed eseguire un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="719fa-109">To create a trusted application pool, open the Lync Server 2013 Management Shell and run a command similar to this:</span></span>

    New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond

<div>


> [!NOTE]
> <span data-ttu-id="719fa-110">Per informazioni dettagliate sui parametri utilizzati nel comando precedente, al prompt dei comandi di Lync Server Management Shell digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="719fa-110">For details about the parameters used in the preceding command, type the following at the Lync Server Management Shell prompt:</span></span><BR><span data-ttu-id="719fa-111">Get-Help New-CsTrustedApplicationPool -Full | more</span><span class="sxs-lookup"><span data-stu-id="719fa-111">Get-Help New-CsTrustedApplicationPool -Full | more</span></span>



</div>

<span data-ttu-id="719fa-112">Dopo aver creato il pool di applicazioni attendibili, configurare il computer del nodo Watcher per l'esecuzione delle transazioni sintetiche come applicazione attendibile.</span><span class="sxs-lookup"><span data-stu-id="719fa-112">After creating the trusted application pool, configure the watcher node computer to run synthetic transactions as a trusted application.</span></span> <span data-ttu-id="719fa-113">A tale scopo, utilizzare il cmdlet **New-CsTrustedApplication** e un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="719fa-113">This is done by using the **New-CsTrustedApplication** cmdlet and a command similar to this:</span></span>

    New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061

<span data-ttu-id="719fa-114">Al termine del comando precedente e della creazione dell'applicazione attendibile, eseguire Enable-CsTopology per in modo che le modifiche diventino effettive:</span><span class="sxs-lookup"><span data-stu-id="719fa-114">When the preceding command completes and the trusted application has been created, run Enable-CsTopology to make sure that the changes take effect:</span></span>

    Enable-CsTopology

<span data-ttu-id="719fa-115">Dopo aver eseguito Enable-CsTopology, si consiglia di riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="719fa-115">After running Enable-CsTopology, we recommend that you restart the computer.</span></span>

<span data-ttu-id="719fa-116">Per verificare che la nuova applicazione attendibile sia stata creata, digitare quanto segue al prompt dei comandi di Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="719fa-116">To verify that the new trusted application has been created, type the following at the Lync Server Management Shell prompt:</span></span>

    Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"

<div>

## <a name="configuring-a-default-certificate-on-the-watcher-node"></a><span data-ttu-id="719fa-117">Configurazione di un certificato predefinito sul nodo Watcher</span><span class="sxs-lookup"><span data-stu-id="719fa-117">Configuring a Default Certificate on the Watcher Node</span></span>

<span data-ttu-id="719fa-118">Ogni nodo Watcher deve disporre di un certificato predefinito assegnato tramite la distribuzione guidata di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="719fa-118">Each watcher node must have a Default certificate assigned by using the Lync Server Deployment Wizard.</span></span>

<span data-ttu-id="719fa-119">**Per assegnare un certificato predefinito**</span><span class="sxs-lookup"><span data-stu-id="719fa-119">**To assign a Default certificate**</span></span>

1.  <span data-ttu-id="719fa-120">Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Lync Server**e quindi **distribuzione guidata di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="719fa-120">Click **Start**, click **All Programs**, click **Lync Server**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="719fa-121">Nella distribuzione guidata di Lync Server, fare clic su **Installa o aggiorna il sistema Lync Server** , quindi fare clic su **Esegui** nell'intestazione **richiesta, installazione o assegnazione**di un certificato.</span><span class="sxs-lookup"><span data-stu-id="719fa-121">In the Lync Server Deployment Wizard, click **Install or Update Lync Server System** and then click **Run** under the heading **Request, Install, or Assign Certificate**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="719fa-122">Se il pulsante <STRONG>Esegui</STRONG> è disabilitato, può essere necessario prima fare clic su <STRONG>Esegui</STRONG> al di sotto di <STRONG>Installazione dell'archivio di configurazione locale</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="719fa-122">If the <STRONG>Run</STRONG> button is disabled, you may need to first click <STRONG>Run</STRONG> under <STRONG>Install Local Configuration Store</STRONG>.</span></span>

    
    </div>

3.  <span data-ttu-id="719fa-123">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="719fa-123">Do one of the following:</span></span>
    
      - <span data-ttu-id="719fa-p104">Se è già disponibile un certificato da poter utilizzare come predefinito, fare clic su **Predefinito** nella Configurazione guidata certificati e quindi fare clic su **Assegna**. Seguire i passaggi indicati nella procedura guidata Assegnazione certificato per assegnarlo.</span><span class="sxs-lookup"><span data-stu-id="719fa-p104">If you already have a certificate that can be used as the Default certificate, click **Default** in the Certificate wizard and then click **Assign**. Follow the steps in the Certificate Assignment wizard to assign that certificate.</span></span>
    
      - <span data-ttu-id="719fa-p105">Se è necessario richiedere un certificato da utilizzare come predefinito, fare clic su **Richiesta** e quindi seguire i passaggi indicati dalla procedura guidata Richiesta di certificato. Se si utilizzano i valori predefiniti per il certificato del server Web, si ottiene un certificato che può essere assegnato come predefinito.</span><span class="sxs-lookup"><span data-stu-id="719fa-p105">If you need to request a certificate for use the Default certificate, click **Request** and then follow the steps in the Certificate Request wizard to request that certificate. If you use the default values for the Web Server certificate, you get a certificate that you can assign as the Default certificate.</span></span>

</div>

<div>

## <a name="installing-and-configuring-a-watcher-node"></a><span data-ttu-id="719fa-128">Installazione e configurazione di un nodo Watcher</span><span class="sxs-lookup"><span data-stu-id="719fa-128">Installing and Configuring a Watcher Node</span></span>

<span data-ttu-id="719fa-129">Dopo aver riavviato il computer del nodo Watcher e aver configurato un certificato, è necessario eseguire il file Watchernode.msi.</span><span class="sxs-lookup"><span data-stu-id="719fa-129">After you have restarted the watcher node computer and configured a certificate, you need to run the file Watchernode.msi.</span></span> <span data-ttu-id="719fa-130">È necessario eseguire WatcherNode. msi in un computer in cui sono installati entrambi i file dell'agente di Operations Manager e i componenti di base di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="719fa-130">(You must run Watchernode.msi on a computer where both the Operations Manager agent files and the Lync Server 2013 core components are installed.)</span></span>

<span data-ttu-id="719fa-131">**Per installare e configurare un nodo Watcher**</span><span class="sxs-lookup"><span data-stu-id="719fa-131">**To install and configure a watcher node**</span></span>

1.  <span data-ttu-id="719fa-132">Aprire Lync Server Management Shell facendo clic sul pulsante **Start**, scegliendo **tutti i programmi**, **Lync Server**e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="719fa-132">Open the Lync Server Management Shell by clicking **Start**, clicking **All Programs**, clicking **Lync Server**, and then clicking **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="719fa-133">In Lync Server Management Shell, digitare il comando seguente e quindi premere INVIO (specificare il percorso effettivo della copia di WatcherNode. msi):</span><span class="sxs-lookup"><span data-stu-id="719fa-133">In the Lync Server Management Shell, type the following command and then press ENTER (specify the actual path to your copy of Watchernode.msi):</span></span>
    
        C:\Tools\Watchernode.msi Authentication=TrustedServer
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="719fa-p107">È anche possibile eseguire Watchernode.msi da una finestra di comando. Per aprire una finestra di comando, fare clic sul pulsante <STRONG>Start</STRONG>, fare clic con il pulsante destro del mouse su <STRONG>Prompt dei comandi</STRONG> e quindi scegliere <STRONG>Esegui come amministratore</STRONG>. Quando viene visualizzata la finestra di comando, digitare lo stesso comando precedente.</span><span class="sxs-lookup"><span data-stu-id="719fa-p107">You can also run Watchernode.msi from a command window. To open a command window, click <STRONG>Start</STRONG>, right-click <STRONG>Command Prompt</STRONG>, and then click <STRONG>Run as administrator</STRONG>. When the command window opens, type the same preceding command.</span></span>

    
    </div>

<span data-ttu-id="719fa-p108">Si noti che la coppia nome/valore del comando precedente Authentication=TrustedServer presenta la distinzione tra maiuscole e minuscole. Digitarla esattamente come mostrato. Il comando seguente non riesce in quanto non utilizza la corretta distinzione tra maiuscole e minuscole per le lettere:</span><span class="sxs-lookup"><span data-stu-id="719fa-p108">Note that the name/value pair in the preceding command Authentication=TrustedServer is case-sensitive. You must type it exactly as shown. The following command fails because it does not use the correct letter casing:</span></span>

<span data-ttu-id="719fa-140">C:\\Tools\\WatcherNode. msi Authentication = TrustedServer</span><span class="sxs-lookup"><span data-stu-id="719fa-140">C:\\Tools\\Watchernode.msi authentication=trustedserver</span></span>

<span data-ttu-id="719fa-p109">È possibile utilizzare la modalità TrustedServer solo con i computer situati all'interno della rete perimetrale. Quando un nodo viene eseguito in modalità TrustedServer, gli amministratori non devono mantenere le password di prova degli utenti sul computer.</span><span class="sxs-lookup"><span data-stu-id="719fa-p109">You can use TrustedServer mode only with computers that are located within the perimeter network. When a watcher node is running in TrustedServer mode, administrators do not have to maintain test user passwords on the computer.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: "Lync Server 2013: configurazione di un nodo Watcher per l'uso dell'autenticazione delle credenziali"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a watcher node to use credential authentication
ms:assetid: 032e33f3-9483-42e6-a33c-347eb6779597
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204632(v=OCS.15)
ms:contentKeyID: 48183255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3746042e0fbf6c7342dd19085f563440b26bb0a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980110"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-use-credential-authentication-in-lync-server-2013"></a><span data-ttu-id="ba93c-102">Configurazione di un nodo Watcher per l'uso dell'autenticazione delle credenziali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba93c-102">Configuring a watcher node to use credential authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba93c-103">_**Argomento Ultima modifica:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="ba93c-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="ba93c-104">Se il computer del nodo Watcher si trova all'esterno della rete perimetrale, è necessario seguire una procedura leggermente diversa per configurare il nodo Watcher in modo da eseguire transazioni sintetiche.</span><span class="sxs-lookup"><span data-stu-id="ba93c-104">If your watcher node computer lies outside the perimeter network, then you must follow a slightly different procedure in order to configure that watcher node to run synthetic transactions.</span></span> <span data-ttu-id="ba93c-105">In particolare, non è consigliabile creare un pool di applicazioni attendibili e un'applicazione attendibile ed è necessario installare un certificato che consenta al nodo Watcher di inviare avvisi a un computer all'interno della rete perimetrale.</span><span class="sxs-lookup"><span data-stu-id="ba93c-105">Specifically, you should not create a trusted application pool and a trusted application, and you must install a certificate that enables the watcher node to send alerts to a computer inside the perimeter network.</span></span> <span data-ttu-id="ba93c-106">Ciò significa che dovrai completare due attività separate:</span><span class="sxs-lookup"><span data-stu-id="ba93c-106">This means that you will need to complete two separate tasks:</span></span>

  - <span data-ttu-id="ba93c-107">Aggiornare l'appartenenza al gruppo di amministratori di sola lettura locale RTC del computer</span><span class="sxs-lookup"><span data-stu-id="ba93c-107">Update the membership in the computer's RTC Local Read-only Administrators Group</span></span>

  - <span data-ttu-id="ba93c-108">Installare i file di configurazione del nodo Watcher</span><span class="sxs-lookup"><span data-stu-id="ba93c-108">Install the watcher node configuration files</span></span>

<div>

## <a name="updating-membership-in-the-rtc-local-read-only-administrators-group"></a><span data-ttu-id="ba93c-109">Aggiornamento dell'appartenenza al gruppo di amministratori di sola lettura RTC Local</span><span class="sxs-lookup"><span data-stu-id="ba93c-109">Updating Membership in the RTC Local Read-Only Administrators Group</span></span>

<span data-ttu-id="ba93c-110">Se il nodo Watcher si trova all'esterno della rete perimetrale, è necessario aggiungere l'account del servizio di rete al gruppo amministratori locali di sola lettura RTC nel computer del nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="ba93c-110">If your watcher node lies outside the perimeter network, you must add the Network Service account to the RTC Local Read-only Administrators group on the watcher node computer.</span></span> <span data-ttu-id="ba93c-111">A questo scopo, completare la procedura seguente nel nodo Watcher:</span><span class="sxs-lookup"><span data-stu-id="ba93c-111">To do this, complete the following procedure on the watcher node:</span></span>

1.  <span data-ttu-id="ba93c-112">Fare clic su **Start**, fare clic con il pulsante destro del mouse su **computer**e quindi scegliere **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="ba93c-112">Click **Start**, right-click **Computer**, and then click **Manage**.</span></span>

2.  <span data-ttu-id="ba93c-113">In Server Manager espandere **configurazione**, espandere **utenti e gruppi locali**e quindi fare clic su **gruppi**.</span><span class="sxs-lookup"><span data-stu-id="ba93c-113">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="ba93c-114">Nel riquadro gruppi fare doppio clic su **amministratori locali di sola lettura RTC**.</span><span class="sxs-lookup"><span data-stu-id="ba93c-114">In the Groups pane, double-click **RTC Local Read-only Administrators**.</span></span>

4.  <span data-ttu-id="ba93c-115">Nella finestra di dialogo **Proprietà amministratori locali di sola lettura RTC** fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="ba93c-115">In the **RTC Local Read-only Administrators Properties** dialog box, click **Add**.</span></span>

5.  <span data-ttu-id="ba93c-116">Nella finestra di dialogo **Seleziona utenti, computer, account di servizio o gruppi** fare clic su **percorsi**.</span><span class="sxs-lookup"><span data-stu-id="ba93c-116">In the **Select Users, Computers, Service Accounts, or Groups** dialog box, click **Locations**.</span></span>

6.  <span data-ttu-id="ba93c-117">Nella finestra di dialogo **posizioni** selezionare il nome del computer del nodo Watcher e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ba93c-117">In the **Locations** dialog box, select the name of the watcher node computer, and then click **OK**.</span></span>

7.  <span data-ttu-id="ba93c-118">Nella casella **immettere i nomi degli oggetti da selezionare** digitare **servizio di rete**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ba93c-118">In the **Enter object names to select** box, type **Network Service**, and then click **OK**.</span></span>

8.  <span data-ttu-id="ba93c-119">Nella finestra di dialogo **Proprietà amministratori locali di sola lettura RTC** fare clic su **OK**e quindi chiudere **Gestione server**.</span><span class="sxs-lookup"><span data-stu-id="ba93c-119">In the **RTC Local Read-only Administrators Properties** dialog box, click **OK**, and then close **Server Manager**.</span></span>

<span data-ttu-id="ba93c-120">Riavviare il computer del nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="ba93c-120">Restart the watcher node computer.</span></span>

</div>

<div>

## <a name="installing-the-watcher-node-configuration-files"></a><span data-ttu-id="ba93c-121">Installazione dei file di configurazione del nodo Watcher</span><span class="sxs-lookup"><span data-stu-id="ba93c-121">Installing the Watcher Node Configuration Files</span></span>

<span data-ttu-id="ba93c-122">Dopo il riavvio del computer del nodo Watcher, il passaggio successivo consiste nell'eseguire il file WatcherNode. msi.</span><span class="sxs-lookup"><span data-stu-id="ba93c-122">After the watcher node computer has restarted, your next step is to run the file Watchernode.msi.</span></span> <span data-ttu-id="ba93c-123">Per eseguire questo file, aprire Lync Server 2013 Management Shell facendo clic sul pulsante **Start**, scegliendo **tutti i programmi**, facendo clic su **Lync Server 2013**e quindi scegliendo **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="ba93c-123">To run this file, open the Lync Server 2013 Management Shell by clicking **Start**, clicking **All Programs**, clicking **Lync Server 2013**, and then clicking **Lync Server Management Shell**.</span></span> <span data-ttu-id="ba93c-124">In Lync Server Management Shell digitare il comando seguente e quindi premere INVIO (assicurarsi e specificare il percorso effettivo della copia di WatcherNode. msi):</span><span class="sxs-lookup"><span data-stu-id="ba93c-124">In the Lync Server Management Shell, type the following command and then press ENTER (be sure and specify the actual path to your copy of Watchernode.msi):</span></span>

    C:\Tools\Watchernode.msi Authentication=Negotiate

<div>


> [!NOTE]  
> <span data-ttu-id="ba93c-125">Come indicato in precedenza, Watchernode. msi può essere eseguito anche da una finestra di comando.</span><span class="sxs-lookup"><span data-stu-id="ba93c-125">As noted previously, Watchernode.msi can also be run from a command window.</span></span> <span data-ttu-id="ba93c-126">Per aprire una finestra di comando, fare clic su <STRONG>Start</STRONG>, fare clic con il pulsante destro del mouse su <STRONG>prompt dei comandi</STRONG>e quindi scegliere <STRONG>Esegui come amministratore</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="ba93c-126">To open a command window, click <STRONG>Start</STRONG>, right-click <STRONG>Command Prompt</STRONG>, and then click <STRONG>Run as administrator</STRONG>.</span></span> <span data-ttu-id="ba93c-127">Quando viene visualizzata la finestra di comando, digitare lo stesso comando illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="ba93c-127">When the command window opens, type the same command as shown earlier.</span></span>



</div>

<span data-ttu-id="ba93c-128">La modalità di negoziazione viene usata ogni volta che il nodo Watcher non può essere configurato come pool di applicazioni attendibili.</span><span class="sxs-lookup"><span data-stu-id="ba93c-128">The Negotiate mode is used any time the watcher node cannot be set up as a trusted application pool.</span></span> <span data-ttu-id="ba93c-129">In questa modalità, gli amministratori dovranno gestire le password degli utenti di test nel nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="ba93c-129">In this mode, administrators will need to manage test user passwords on the watcher node.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


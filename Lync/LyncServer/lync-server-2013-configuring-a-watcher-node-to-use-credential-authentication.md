---
title: "Lync Server 2013: configurazione di un nodo Watcher per l'utilizzo dell'autenticazione delle credenziali"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to use credential authentication
ms:assetid: 032e33f3-9483-42e6-a33c-347eb6779597
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204632(v=OCS.15)
ms:contentKeyID: 48183255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e05ac48896b50b4b83e4211a5036f6a6d513d43
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517692"
---
# <a name="configuring-a-watcher-node-to-use-credential-authentication-in-lync-server-2013"></a><span data-ttu-id="89d86-102">Configurazione di un nodo Watcher per l'utilizzo dell'autenticazione delle credenziali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89d86-102">Configuring a watcher node to use credential authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89d86-103">_**Ultimo argomento modificato:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="89d86-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="89d86-p101">Se il computer che funge da nodo Watcher si trova all'esterno della rete perimetrale, per configurarlo per l'esecuzione di transazioni sintetiche è necessario seguire una procedura leggermente diversa. Nello specifico, non andranno creati un pool di applicazioni attendibili e un'applicazione attendibile e sarà necessario installare un certificato che consenta al nodo Watcher di inviare avvisi a un computer che si trova all'interno della rete perimetrale. Questo vuol dire che bisognerà completare due attività separate:</span><span class="sxs-lookup"><span data-stu-id="89d86-p101">If your watcher node computer lies outside the perimeter network, then you must follow a slightly different procedure in order to configure that watcher node to run synthetic transactions. Specifically, you should not create a trusted application pool and a trusted application, and you must install a certificate that enables the watcher node to send alerts to a computer inside the perimeter network. This means that you will need to complete two separate tasks:</span></span>

  - <span data-ttu-id="89d86-107">Aggiornare l'appartenenza al gruppo RTC Local Read-Only Administrators del computer</span><span class="sxs-lookup"><span data-stu-id="89d86-107">Update the membership in the computer's RTC Local Read-only Administrators Group</span></span>

  - <span data-ttu-id="89d86-108">Installare i file di configurazione del nodo Watcher</span><span class="sxs-lookup"><span data-stu-id="89d86-108">Install the watcher node configuration files</span></span>

<div>

## <a name="updating-membership-in-the-rtc-local-read-only-administrators-group"></a><span data-ttu-id="89d86-109">Aggiornamento dell'appartenenza al gruppo RTC Local Read-Only Administrators</span><span class="sxs-lookup"><span data-stu-id="89d86-109">Updating Membership in the RTC Local Read-Only Administrators Group</span></span>

<span data-ttu-id="89d86-p102">Se il nodo Watcher si trova all'esterno della rete perimetrale, è necessario aggiungere l'account Servizio di rete al gruppo RTC Local Read-only Administrators nel computer che funge da nodo Watcher. A questo scopo, completare la procedura seguente nel nodo Watcher:</span><span class="sxs-lookup"><span data-stu-id="89d86-p102">If your watcher node lies outside the perimeter network, you must add the Network Service account to the RTC Local Read-only Administrators group on the watcher node computer. To do this, complete the following procedure on the watcher node:</span></span>

1.  <span data-ttu-id="89d86-112">Fare clic sul pulsante **Start**, fare clic su **Computer** con il pulsante destro del mouse e quindi scegliere **Gestione**.</span><span class="sxs-lookup"><span data-stu-id="89d86-112">Click **Start**, right-click **Computer**, and then click **Manage**.</span></span>

2.  <span data-ttu-id="89d86-113">In Server Manager espandere **Configurazione**, espandere **Utenti e gruppi locali** e quindi fare clic su **Gruppi**.</span><span class="sxs-lookup"><span data-stu-id="89d86-113">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="89d86-114">Nel riquadro Gruppi fare doppio clic su **RTC Local Read-only Administrators**.</span><span class="sxs-lookup"><span data-stu-id="89d86-114">In the Groups pane, double-click **RTC Local Read-only Administrators**.</span></span>

4.  <span data-ttu-id="89d86-115">Nella finestra delle proprietà del gruppo **RTC Local Read-only Administrators** fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="89d86-115">In the **RTC Local Read-only Administrators Properties** dialog box, click **Add**.</span></span>

5.  <span data-ttu-id="89d86-116">Nella finestra di dialogo **Selezione utenti, computer, account di servizio o gruppi** fare clic su **Percorsi**.</span><span class="sxs-lookup"><span data-stu-id="89d86-116">In the **Select Users, Computers, Service Accounts, or Groups** dialog box, click **Locations**.</span></span>

6.  <span data-ttu-id="89d86-117">Nella finestra di dialogo **Percorsi** selezionare il nome del computer che funge da nodo Watcher e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="89d86-117">In the **Locations** dialog box, select the name of the watcher node computer, and then click **OK**.</span></span>

7.  <span data-ttu-id="89d86-118">Nella casella **Immettere i nomi degli oggetti da selezionare** digitare **Servizio di rete** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="89d86-118">In the **Enter object names to select** box, type **Network Service**, and then click **OK**.</span></span>

8.  <span data-ttu-id="89d86-119">Nella finestra delle proprietà del gruppo **RTC Local Read-only Administrators Properties** fare clic su **OK** e quindi chiudere **Server Manager**.</span><span class="sxs-lookup"><span data-stu-id="89d86-119">In the **RTC Local Read-only Administrators Properties** dialog box, click **OK**, and then close **Server Manager**.</span></span>

<span data-ttu-id="89d86-120">Riavviare il computer che funge da nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="89d86-120">Restart the watcher node computer.</span></span>

</div>

<div>

## <a name="installing-the-watcher-node-configuration-files"></a><span data-ttu-id="89d86-121">Installazione dei file di configurazione del nodo Watcher</span><span class="sxs-lookup"><span data-stu-id="89d86-121">Installing the Watcher Node Configuration Files</span></span>

<span data-ttu-id="89d86-122">Dopo il riavvio del computer che funge da nodo Watcher, l'operazione successiva consiste nell'installare il file Watchernode.msi.</span><span class="sxs-lookup"><span data-stu-id="89d86-122">After the watcher node computer has restarted, your next step is to run the file Watchernode.msi.</span></span> <span data-ttu-id="89d86-123">Per eseguire questo file, aprire Lync Server 2013 Management Shell facendo clic sul pulsante **Start**, scegliendo **tutti i programmi**, **Lync Server 2013**e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="89d86-123">To run this file, open the Lync Server 2013 Management Shell by clicking **Start**, clicking **All Programs**, clicking **Lync Server 2013**, and then clicking **Lync Server Management Shell**.</span></span> <span data-ttu-id="89d86-124">In Lync Server Management Shell, digitare il comando seguente e quindi premere INVIO (accertarsi di specificare il percorso effettivo della copia di Watchernode.msi):</span><span class="sxs-lookup"><span data-stu-id="89d86-124">In the Lync Server Management Shell, type the following command and then press ENTER (be sure and specify the actual path to your copy of Watchernode.msi):</span></span>

    C:\Tools\Watchernode.msi Authentication=Negotiate

<div>


> [!NOTE]  
> <span data-ttu-id="89d86-p104">Come già osservato, Watchernode.msi può essere eseguito anche da una finestra di comando. Per aprire una finestra di comando fare clic su <STRONG>Start</STRONG>, fare clic con il pulsante destro del mouse su <STRONG>Prompt dei comandi</STRONG>, quindi scegliere <STRONG>Esegui come amministratore</STRONG>. All'apertura della finestra di comando, digitare lo stesso comando come descritto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="89d86-p104">As noted previously, Watchernode.msi can also be run from a command window. To open a command window, click <STRONG>Start</STRONG>, right-click <STRONG>Command Prompt</STRONG>, and then click <STRONG>Run as administrator</STRONG>. When the command window opens, type the same command as shown earlier.</span></span>



</div>

<span data-ttu-id="89d86-128">La modalità Negotiate viene usata ogni volta che non è possibile configurare il nodo Watcher come pool di applicazioni attendibili.</span><span class="sxs-lookup"><span data-stu-id="89d86-128">The Negotiate mode is used any time the watcher node cannot be set up as a trusted application pool.</span></span> <span data-ttu-id="89d86-129">In questa modalità, gli amministratori dovranno gestire le password utente di prova nel nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="89d86-129">In this mode, administrators will need to manage test user passwords on the watcher node.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


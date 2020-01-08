---
title: 'Lync Server 2013: importare i Management Pack di Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Importing the Lync Server 2013 management packs
ms:assetid: 846287e1-660f-453f-bdba-b2137b5f0ea1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205052(v=OCS.15)
ms:contentKeyID: 48184690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70c753334ea9a046c6081a73ce70e4de00de9188
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975244"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="importing-the-lync-server-2013-management-packs"></a><span data-ttu-id="a1640-102">Importazione dei Management Pack di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1640-102">Importing the Lync Server 2013 management packs</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1640-103">_**Argomento Ultima modifica:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="a1640-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="a1640-104">Per estendere le funzionalità di System Center Operations Manager, è possibile installare Management Pack, ovvero software che indica quali elementi possono essere monitorati da System Center Operations Manager e come devono essere controllati gli elementi e come devono essere attivati gli avvisi e segnalato.</span><span class="sxs-lookup"><span data-stu-id="a1640-104">You can extend the capabilities of System Center Operations Manager by installing management packs—software that dictates which items System Center Operations Manager can monitor, and how those items should be monitored and how alerts should be triggered and reported.</span></span> <span data-ttu-id="a1640-105">Lync Server 2013 include due Management Pack di System Center Operations Manager che fornisce le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="a1640-105">Lync Server 2013 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

  - <span data-ttu-id="a1640-106">Il componente e User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) tiene traccia dei problemi di Lync Server registrati nei registri eventi, registrati da contatori delle prestazioni oppure registrati nei record dettagli chiamata (CDR) o nella qualità dell'esperienza (QoE) database.</span><span class="sxs-lookup"><span data-stu-id="a1640-106">The Component and User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) tracks Lync Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDR) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="a1640-107">Per problemi critici, System Center Operations Manager può essere configurato per informare immediatamente gli amministratori tramite posta elettronica, messaggio istantaneo o messaggistica SMS (Short Message Service).</span><span class="sxs-lookup"><span data-stu-id="a1640-107">For critical problems, System Center Operations Manager can be configured to immediately notify administrators via email, instant message, or Short Message Service (SMS) messaging.</span></span> <span data-ttu-id="a1640-108">SMS è la tecnologia usata per inviare SMS da un dispositivo mobile a un altro.</span><span class="sxs-lookup"><span data-stu-id="a1640-108">SMS is the technology used to send text messages from one mobile device to another.)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a1640-109">Per informazioni dettagliate sulla configurazione della notifica di Operations Manager, vedere la notifica di configurazione nella <A href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?LinkId=268785</A>Raccolta TechNet.</span><span class="sxs-lookup"><span data-stu-id="a1640-109">For details about configuring Operations Manager notification, see the Configuring Notification in the TechNet Library at <A href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?LinkId=268785</A>.</span></span>

    
    </div>

  - <span data-ttu-id="a1640-110">Active Monitoring Management Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) verifica in modo proattivo i componenti principali di Lync Server, ad esempio l'accesso al sistema, lo scambio di messaggi istantanei o l'esecuzione di chiamate a un telefono che si trova sul pubblico commutato rete telefonica (PSTN).</span><span class="sxs-lookup"><span data-stu-id="a1640-110">The Active Monitoring Management Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) proactively tests key Lync Server components such as signing into to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="a1640-111">Questi test vengono eseguiti usando i cmdlet di transazione sintetica di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a1640-111">These tests are conducted using the Lync Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="a1640-112">Ad esempio, puoi usare il cmdlet **Test-CsIM** per simulare una conversazione di messaggistica istantanea tra una coppia di utenti di test.</span><span class="sxs-lookup"><span data-stu-id="a1640-112">For example, you can use the **Test-CsIM** cmdlet to simulate an instant messaging (IM) conversation between a pair of test users.</span></span> <span data-ttu-id="a1640-113">Se la conversazione di messaggistica simulata non riesce, viene generato un avviso.</span><span class="sxs-lookup"><span data-stu-id="a1640-113">If this simulated messaging conversation fails an alert is generated.</span></span>

<span data-ttu-id="a1640-114">È necessario importare i Management Pack.</span><span class="sxs-lookup"><span data-stu-id="a1640-114">You need to import the management packs.</span></span> <span data-ttu-id="a1640-115">Se non si importano i Management Pack, non è possibile usare Operations Manager per monitorare gli eventi di Lync Server o eseguire transazioni sintetiche di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a1640-115">If you do not import the management packs, you cannot use Operations Manager to monitor Lync Server events or run Lync Server synthetic transactions.</span></span>

<span data-ttu-id="a1640-116">Il Management Pack per il componente e l'utente viene usato solo per monitorare Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a1640-116">The Component and User Management Pack is only used to monitor Lync Server 2013.</span></span> <span data-ttu-id="a1640-117">In uno scenario di coesistenza, in cui sono installati sia Lync Server 2013 che Lync Server 2010, è necessario continuare a usare i Management Pack di Lync Server 2010 per i computer di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a1640-117">If you are in a coexistence scenario, where you have both Lync Server 2013 and Lync Server 2010 installed, you should continue to use the Lync Server 2010 management packs for your Lync Server 2010 computers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a1640-118">I Management Pack per Lync Server 2010 includono Lync Server 2010 Monitoring Management Pack e Lync Server 2010 Group Chat Monitoring Management Pack.</span><span class="sxs-lookup"><span data-stu-id="a1640-118">Management packs for Lync Server 2010 include the Lync Server 2010 Monitoring Management Pack and the Lync Server 2010 Group Chat Monitoring Management Pack.</span></span>



</div>

<span data-ttu-id="a1640-119">È possibile usare uno degli strumenti seguenti per importare i Management Pack:</span><span class="sxs-lookup"><span data-stu-id="a1640-119">You can use one of the following tools to import management packs:</span></span>

  - <span data-ttu-id="a1640-120">**System Center Operations Manager**   con questo metodo, è possibile usare Operations Manager per aggiungere il monitoraggio per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a1640-120">**System Center Operations Manager**   With this method, you use the Operations Manager to add monitoring for Lync Server.</span></span>

  - <span data-ttu-id="a1640-121">**Operations Manager Shell**   è possibile usare la shell di Operations Manager per importare direttamente o per risolvere i problemi che si verificano quando si importano i Management Pack tramite la console di System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="a1640-121">**Operations Manager Shell**   You can use the Operations Manager Shell to import directly or to troubleshoot any issues you encounter when you import management packs by using the System Center Operations Manager console.</span></span>

<div>

## <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a><span data-ttu-id="a1640-122">Importazione di Management Pack tramite System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="a1640-122">Importing the Management Packs by Using System Center Operations Manager</span></span>

1.  <span data-ttu-id="a1640-123">Scaricare i file Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp e Microsoft.LS.2013.Monitoring.ComponentAndUser.mp.</span><span class="sxs-lookup"><span data-stu-id="a1640-123">Download the files Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2013.Monitoring.ComponentAndUser.mp.</span></span>

2.  <span data-ttu-id="a1640-124">In System Center Operations Manager fare clic su **Amministrazione**.</span><span class="sxs-lookup"><span data-stu-id="a1640-124">In System Center Operations Manager, click **Administration**.</span></span>

3.  <span data-ttu-id="a1640-125">Nel riquadro **Amministrazione** fare clic con il pulsante destro del mouse su **Management Pack**e quindi scegliere **Importa Management Pack**.</span><span class="sxs-lookup"><span data-stu-id="a1640-125">In the **Administration** pane, right-click **Management Packs**, and then click **Import Management Packs**.</span></span>

4.  <span data-ttu-id="a1640-126">Nella finestra di dialogo **Seleziona Management Pack** fare clic su **Aggiungi**e quindi su **Aggiungi da disco**.</span><span class="sxs-lookup"><span data-stu-id="a1640-126">In the **Select Management Packs** dialog box, click **Add**, and then click **Add from disk**.</span></span>

5.  <span data-ttu-id="a1640-127">Nella finestra di dialogo **connessione Catalogo online** fare clic su **Annulla** per evitare che Operations Manager venga visualizzato online per verificare se esistono dipendenze per i Management Pack di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a1640-127">In the **Online Catalog Connection** dialog box, click **Cancel** to prevent Operations Manager from going online to see if any dependencies exist for the Lync Server management packs.</span></span> <span data-ttu-id="a1640-128">Se si usa System Center Operations Manager 2012, fare clic su **No**.</span><span class="sxs-lookup"><span data-stu-id="a1640-128">If you are using System Center Operations Manager 2012, click **No**.</span></span>

6.  <span data-ttu-id="a1640-129">Nella finestra **di dialogo Seleziona Management Pack da importare** individuare e selezionare i file **Microsoft.ls.2013.Monitoring.ActiveMonitoring.MP** e **Microsoft.ls.2013.Monitoring.ComponentAndUser.MP** e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="a1640-129">In the **Select Management Packs to import** dialog box, locate and select the files **Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp** and **Microsoft.LS.2013.Monitoring.ComponentAndUser.mp** and then click **Open**.</span></span> <span data-ttu-id="a1640-130">Per selezionare più file nella finestra di dialogo, fare clic sul primo file, tenere premuto CTRL e quindi fare clic sul secondo file.</span><span class="sxs-lookup"><span data-stu-id="a1640-130">To select multiple files in the dialog box, click the first file, hold down the Ctrl key and then click the second file.</span></span>

7.  <span data-ttu-id="a1640-131">Nella finestra di dialogo **Seleziona Management Pack** fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="a1640-131">In the **Select Management Packs** dialog box, click **Install**.</span></span> <span data-ttu-id="a1640-132">Se viene visualizzato un messaggio di errore e l'installazione non riesce, significa in genere che i file del Management Pack si trovano in una cartella protetta dal controllo dell'account utente di Windows.</span><span class="sxs-lookup"><span data-stu-id="a1640-132">If you get an error message and installation fails, that typically means that the management pack files are in a folder protected by the Windows User Account Control.</span></span> <span data-ttu-id="a1640-133">In questo caso, copiare i file in un'altra cartella e quindi riavviare il processo di importazione e installazione.</span><span class="sxs-lookup"><span data-stu-id="a1640-133">If this occurs, copy the files to a different folder and then restart the import and installation process.</span></span>

8.  <span data-ttu-id="a1640-134">Nella finestra di dialogo **Seleziona Management Pack** fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="a1640-134">In the **Select Management Packs** dialog box, click **Close**.</span></span> <span data-ttu-id="a1640-135">Tieni presente che il processo di importazione e installazione potrebbe richiedere diversi minuti per il completamento.</span><span class="sxs-lookup"><span data-stu-id="a1640-135">Note that the import and installation process might require several minutes to complete.</span></span>

</div>

<div>

## <a name="importing-management-packs-by-using-the-operations-manager-shell"></a><span data-ttu-id="a1640-136">Importazione di Management Pack tramite la shell di Operations Manager</span><span class="sxs-lookup"><span data-stu-id="a1640-136">Importing Management Packs by Using the Operations Manager Shell</span></span>

<span data-ttu-id="a1640-137">In generale, è più semplice importare i Management Pack tramite Operations Manager. Tuttavia, se si verifica un errore e l'importazione non riesce, la console non sempre fornisce rapporti di errore adeguati.</span><span class="sxs-lookup"><span data-stu-id="a1640-137">In general it is easier to import the management packs by using the Operations Manager.However, if an error occurs and the import fails, the console does not always provide adequate error reports.</span></span> <span data-ttu-id="a1640-138">Tramite il confronto, la shell di Operations Manager offre informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="a1640-138">By comparison, the Operations Manager Shell, provides detailed information.</span></span> <span data-ttu-id="a1640-139">Se si usa Operations Manager e si verificano problemi di importazione di un Management Pack, importare il pacchetto tramite Operations Manager Shell.</span><span class="sxs-lookup"><span data-stu-id="a1640-139">If you are using Operations Manager and you run into problems importing a management pack, import the pack by using the Operations Manager Shell .</span></span> <span data-ttu-id="a1640-140">La shell di Operations Manager offre ulteriori informazioni che potrebbero essere utili per determinare il motivo per cui l'importazione non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="a1640-140">The Operations Manager Shell provides more information that might help you determine why the import failed.</span></span>

<span data-ttu-id="a1640-141">Se si usa System Center Operations Manager 2007 R2, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="a1640-141">If you are using System Center Operations Manager 2007 R2, complete the following procedure:</span></span>

1.  <span data-ttu-id="a1640-142">Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, quindi **System Center Operations Manager 2007 R2**e quindi fare clic su **Operations Manager Shell**.</span><span class="sxs-lookup"><span data-stu-id="a1640-142">Click **Start**, click **All Programs**, click **System Center Operations Manager 2007 R2**, and then click **Operations Manager Shell**.</span></span>

2.  <span data-ttu-id="a1640-143">In Operations Manager Shell digitare il comando seguente al prompt dei comandi, usando il percorso effettivo della copia del file Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="a1640-143">In the Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp

3.  <span data-ttu-id="a1640-144">Dopo aver importato il primo Management Pack, ripetere il processo usando il percorso della copia del file Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span><span class="sxs-lookup"><span data-stu-id="a1640-144">After you import the first management pack, repeat the process using the path to your copy of the file Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span></span>
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ComponentAndUser.mp

4.  <span data-ttu-id="a1640-145">Chiudere la shell di Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="a1640-145">Close the Operations Manager Shell.</span></span>

<span data-ttu-id="a1640-146">Se si usa System Center Operations Manager 2012, eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="a1640-146">If you are using System Center Operations Manager 2012, complete this procedure instead:</span></span>

1.  <span data-ttu-id="a1640-147">Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Microsoft System Center 2012**, fare clic su **Operations Manager**e quindi su **Operations Manager Shell**.</span><span class="sxs-lookup"><span data-stu-id="a1640-147">Click **Start**, click **All Programs**, click **Microsoft System Center 2012**, click **Operations Manager**, and then click **Operations Manager Shell**.</span></span>

2.  <span data-ttu-id="a1640-148">In Operations Manager Shell digitare il comando seguente al prompt dei comandi, usando il percorso effettivo della copia del file Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="a1640-148">In the Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp"

3.  <span data-ttu-id="a1640-149">Dopo aver importato il primo Management Pack, ripetere il processo usando il percorso della copia del file Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span><span class="sxs-lookup"><span data-stu-id="a1640-149">After you have imported the first management pack, repeat the process using the path to your copy of the file Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span></span>
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ComponentAndUser.mp"

</div>

</div>

<span> </span>

</div>

</div>

</div>


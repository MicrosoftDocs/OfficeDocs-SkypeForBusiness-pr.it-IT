---
title: Configurare il server di gestione principale
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Riepilogo: configurare il server di gestione principale, installare System Center Operations Manager e importare Management Pack per Skype for Business Server 2019.'
ms.openlocfilehash: 316931aff5379de10b0301cc65e94443ed0f7675
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189755"
---
# <a name="configure-the-primary-management-server"></a><span data-ttu-id="b0e2f-103">Configurare il server di gestione principale</span><span class="sxs-lookup"><span data-stu-id="b0e2f-103">Configure the Primary Management Server</span></span>

<span data-ttu-id="b0e2f-104">**Riepilogo:** Configurare il server di gestione principale, installare System Center Operations Manager e importare Management Pack per Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b0e2f-104">**Summary:** Configure your primary management server, install System Center Operations Manager, and import management packs for Skype for Business Server 2019.</span></span>

<span data-ttu-id="b0e2f-105">Per sfruttare al meglio le nuove funzionalità di monitoraggio dell'integrità incluse in Skype for Business Server 2019, è prima di tutto necessario designare un computer per fungere da server di gestione principale.</span><span class="sxs-lookup"><span data-stu-id="b0e2f-105">To take full advantage of the new health monitoring capabilities included in Skype for Business Server 2019, you must first designate a computer to act as your primary management server.</span></span> <span data-ttu-id="b0e2f-106">È quindi necessario installare System Center Operations Manager 2012 SP1 o R2 o System Center Operations Manager 2007 R2 in tale computer.</span><span class="sxs-lookup"><span data-stu-id="b0e2f-106">You must then install System Center Operations Manager 2012 SP1 or R2 or System Center Operations Manager 2007 R2 on that computer.</span></span> <span data-ttu-id="b0e2f-107">Inoltre, devi prima installare una versione supportata di SQL Server in modo che funzioni come database back-end di Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="b0e2f-107">In addition, you must first install a supported version of SQL Server to function as your Operations Manager back-end database.</span></span>

<span data-ttu-id="b0e2f-108">Quando si installa System Center Operations Manager, sarà necessario installare tutti i componenti di tale prodotto, tra cui:</span><span class="sxs-lookup"><span data-stu-id="b0e2f-108">When you install System Center Operations Manager, you will need to install all the components of that product, including:</span></span>

- <span data-ttu-id="b0e2f-109">Database operativo</span><span class="sxs-lookup"><span data-stu-id="b0e2f-109">Operational database</span></span>

- <span data-ttu-id="b0e2f-110">Server</span><span class="sxs-lookup"><span data-stu-id="b0e2f-110">Server</span></span>

- <span data-ttu-id="b0e2f-111">Console</span><span class="sxs-lookup"><span data-stu-id="b0e2f-111">Console</span></span>

- <span data-ttu-id="b0e2f-112">Cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b0e2f-112">Windows PowerShell cmdlets</span></span>

- <span data-ttu-id="b0e2f-113">Console Web</span><span class="sxs-lookup"><span data-stu-id="b0e2f-113">Web console</span></span>

- <span data-ttu-id="b0e2f-114">Report</span><span class="sxs-lookup"><span data-stu-id="b0e2f-114">Reporting</span></span>

- <span data-ttu-id="b0e2f-115">Data warehouse</span><span class="sxs-lookup"><span data-stu-id="b0e2f-115">Data warehouse</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b0e2f-116">Per installare System Center Operations Manager 2012 è necessario installare "[Microsoft Report Viewer 2010 Redistributable Package](https://www.microsoft.com/en-us/download/details.aspx?id=6442)".</span><span class="sxs-lookup"><span data-stu-id="b0e2f-116">The "[Microsoft Report Viewer 2010 Redistributable Package](https://www.microsoft.com/en-us/download/details.aspx?id=6442)" needs to be installed before you install System Center Operations Manager 2012.</span></span>

<span data-ttu-id="b0e2f-117">Per informazioni dettagliate su questi prodotti e sulla relativa installazione, vedere i collegamenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="b0e2f-117">For details about these products and their installation, see the following links:</span></span>

- [<span data-ttu-id="b0e2f-118">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="b0e2f-118">System Center Operations Manager 2012</span></span>](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [<span data-ttu-id="b0e2f-119">System Center Operations Manager 2007</span><span class="sxs-lookup"><span data-stu-id="b0e2f-119">System Center Operations Manager 2007</span></span>](https://technet.microsoft.com/en-us/library/bb735860.aspx)

<span data-ttu-id="b0e2f-120">Tieni presente che puoi avere un solo server di gestione radice per la distribuzione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b0e2f-120">Keep in mind that you can have only one Root Management Server per Skype for Business Server deployment.</span></span>

## <a name="importing-the-skype-for-business-server-2019-management-packs"></a><span data-ttu-id="b0e2f-121">Importazione dei Management Pack di Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="b0e2f-121">Importing the Skype for Business Server 2019 Management Packs</span></span>

<span data-ttu-id="b0e2f-122">Per estendere le funzionalità di System Center Operations Manager, è possibile installare Management Pack, ovvero il software che stabilisce quali elementi possono essere monitorati da System Center Operations Manager, come devono essere monitorati gli elementi e come devono essere attivati gli avvisi e segnalato.</span><span class="sxs-lookup"><span data-stu-id="b0e2f-122">You can extend the capabilities of System Center Operations Manager by installing management packs—software that dictates which items System Center Operations Manager can monitor, how those items should be monitored, and how alerts should be triggered and reported.</span></span> <span data-ttu-id="b0e2f-123">Skype for Business Server 2019 include due Management Pack di System Center Operations Manager che fornisce le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="b0e2f-123">Skype for Business Server 2019 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

- <span data-ttu-id="b0e2f-124">**Il componente e il Management Pack degli utenti** (Microsoft.LS.2019.Monitoring.ComponentAndUser.mp) tiene traccia dei problemi di Skype for Business Server registrati nei registri eventi, registrati da contatori delle prestazioni oppure registrati nei record di dettagli chiamata (CDRs) o nei database QoE (Quality of Experience).</span><span class="sxs-lookup"><span data-stu-id="b0e2f-124">**The Component and User Management Pack** (Microsoft.LS.2019.Monitoring.ComponentAndUser.mp) tracks Skype for Business Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDRs) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="b0e2f-125">Per problemi critici, System Center Operations Manager può essere configurato per comunicare immediatamente agli amministratori tramite posta elettronica, messaggi istantanei o messaggi SMS.</span><span class="sxs-lookup"><span data-stu-id="b0e2f-125">For critical issues, System Center Operations Manager can be configured to immediately notify administrators through email, instant message, or SMS messaging.</span></span> <span data-ttu-id="b0e2f-126">(SMS o Short Message Service) è la tecnologia usata per inviare SMS da un dispositivo mobile a un altro.</span><span class="sxs-lookup"><span data-stu-id="b0e2f-126">(SMS, or Short Message Service, is the technology used to send text messages from one mobile device to another.)</span></span>

    > [!NOTE]
    >  <span data-ttu-id="b0e2f-127">Per informazioni dettagliate sulla configurazione della notifica di Operations Manager, vedere [configurazione della notifica](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="b0e2f-127">For details about configuring Operations Manager notification, see [Configuring Notification](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).</span></span>

- <span data-ttu-id="b0e2f-128">**Active Monitoring Management Pack** (Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp) verifica in modo proattivo i componenti principali di Skype for Business Server, ad esempio l'accesso al sistema, lo scambio di messaggi istantanei o l'esecuzione di chiamate a un telefono che si trova nella rete PSTN (Public Switched Telephone Network) ).</span><span class="sxs-lookup"><span data-stu-id="b0e2f-128">**The Active Monitoring Management Pack** (Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp) proactively tests key Skype for Business Server components, such as signing into to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="b0e2f-129">Questi test vengono condotti usando i cmdlet di transazione sintetica di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b0e2f-129">These tests are conducted by using the Skype for Business Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="b0e2f-130">Ad esempio, il cmdlet **Test-CsIM** viene usato per simulare una conversazione di messaggistica istantanea tra una coppia di utenti di test.</span><span class="sxs-lookup"><span data-stu-id="b0e2f-130">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="b0e2f-131">Se la conversazione simulata non riesce, viene generato un avviso.</span><span class="sxs-lookup"><span data-stu-id="b0e2f-131">If this simulated conversation fails, an alert is generated.</span></span>

<span data-ttu-id="b0e2f-132">L'importazione dei Management Pack è un passaggio cruciale.</span><span class="sxs-lookup"><span data-stu-id="b0e2f-132">Importing the management packs is a crucial step.</span></span> <span data-ttu-id="b0e2f-133">Se i Management Pack non vengono importati, non sarà possibile usare Operations Manager per monitorare gli eventi di Skype for Business Server o eseguire transazioni sintetiche di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b0e2f-133">If the management packs are not imported, you will not be able to use Operations Manager to monitor Skype for Business Server events or run Skype for Business Server synthetic transactions.</span></span>

<span data-ttu-id="b0e2f-134">Il Management Pack per i componenti e gli utenti viene usato per monitorare solo Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b0e2f-134">The Component and User Management Pack is used to monitor only Skype for Business Server 2019.</span></span> <span data-ttu-id="b0e2f-135">Se si è in uno scenario di coesistenza in cui sono installati sia Skype for Business Server 2019 che Skype for Business Server 2015, è necessario continuare a usare i Management Pack di Skype for Business Server 2015 per i computer Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b0e2f-135">If you are in a coexistence scenario where both Skype for Business Server 2019 and Skype for Business Server 2015 are installed, you should continue to use the Skype for Business Server 2015 management packs for your Skype for Business Server 2015 computers.</span></span>

> [!NOTE]
> <span data-ttu-id="b0e2f-136">I Management Pack per Skype for Business Server 2019 includono il componente Skype for Business Server 2019 e il Management Pack utenti di Skype for Business Server 2019 Active Monitoring Management Pack.</span><span class="sxs-lookup"><span data-stu-id="b0e2f-136">Management packs for Skype for Business Server 2019 include the Skype for Business Server 2019 Component and User Management Pack and the Skype for Business Server 2019 Active Monitoring Management Pack.</span></span>

<span data-ttu-id="b0e2f-137">È possibile usare uno degli strumenti seguenti per importare i Management Pack:</span><span class="sxs-lookup"><span data-stu-id="b0e2f-137">You can use one of the following tools to import management packs:</span></span>

- <span data-ttu-id="b0e2f-138">**System Center Operations Manager** Con questo metodo, puoi usare Operations Manager per aggiungere il monitoraggio per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b0e2f-138">**System Center Operations Manager** With this method, you use the Operations Manager to add monitoring for Skype for Business Server.</span></span>

- <span data-ttu-id="b0e2f-139">**Shell di Operations Manager** È possibile usare la shell di Operations Manager per importare direttamente o per risolvere eventuali problemi che si verificano quando si importano i Management Pack tramite la console di System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="b0e2f-139">**Operations Manager Shell** You can use the Operations Manager Shell to import directly, or to troubleshoot any issues that you encounter when you import management packs by using the System Center Operations Manager console.</span></span>

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a><span data-ttu-id="b0e2f-140">Importazione di Management Pack tramite System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="b0e2f-140">Importing the Management Packs by Using System Center Operations Manager</span></span>

1. <span data-ttu-id="b0e2f-141">Scaricare il file SkypeForBusiness2019ManagementPacks. msi dai download di Microsoft Web e installare MSI.</span><span class="sxs-lookup"><span data-stu-id="b0e2f-141">Download the SkypeForBusiness2019ManagementPacks.msi from the Microsoft Web downloads, and install the msi.</span></span>

2. <span data-ttu-id="b0e2f-142">In System Center Operations Manager fare clic su **Amministrazione**.</span><span class="sxs-lookup"><span data-stu-id="b0e2f-142">In System Center Operations Manager, click **Administration**.</span></span>

3. <span data-ttu-id="b0e2f-143">Nel riquadro Amministrazione fare clic con il pulsante destro del mouse su **Management Pack**e quindi scegliere **Importa Management Pack**.</span><span class="sxs-lookup"><span data-stu-id="b0e2f-143">In the Administration pane, right-click **Management Packs**, and then click **Import Management Packs**.</span></span>

4. <span data-ttu-id="b0e2f-144">Nella finestra di dialogo **Seleziona Management Pack** fare clic su **Aggiungi**e quindi su **Aggiungi da disco**.</span><span class="sxs-lookup"><span data-stu-id="b0e2f-144">In the **Select Management Packs** dialog box, click **Add**, and then click **Add from disk**.</span></span>

5. <span data-ttu-id="b0e2f-145">Nella finestra di dialogo **connessione Catalogo online** fare clic su **No**.</span><span class="sxs-lookup"><span data-stu-id="b0e2f-145">In the **Online Catalog Connection** dialog box, click **No**.</span></span>

6. <span data-ttu-id="b0e2f-146">Nella finestra **di dialogo Seleziona Management Pack da importare** individuare e selezionare i file Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp e Microsoft.ls.2019.Monitoring.ComponentAndUser.MP e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="b0e2f-146">In the **Select Management Packs to import** dialog box, locate and select the files Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2019.Monitoring.ComponentAndUser.mp, and then click **Open**.</span></span> <span data-ttu-id="b0e2f-147">Per selezionare più file nella finestra di dialogo, fare clic sul primo file e quindi tenere premuto il tasto CTRL e fare clic sui file successivi.</span><span class="sxs-lookup"><span data-stu-id="b0e2f-147">To select multiple files in the dialog box, click the first file, and then hold down the Ctrl key and click the subsequent files.</span></span>

7. <span data-ttu-id="b0e2f-148">Nella finestra di dialogo **Seleziona Management Pack** fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="b0e2f-148">In the **Select Management Packs** dialog box, click **Install**.</span></span> <span data-ttu-id="b0e2f-149">Se viene visualizzato un messaggio di errore e l'installazione non riesce, significa in genere che i file del Management Pack si trovano in una cartella protetta dal controllo dell'account utente di Windows.</span><span class="sxs-lookup"><span data-stu-id="b0e2f-149">If you get an error message and installation fails, that typically means that the management pack files are in a folder protected by the Windows User Account Control.</span></span> <span data-ttu-id="b0e2f-150">In questo caso, copiare i file in un'altra cartella e quindi riavviare il processo di importazione e installazione.</span><span class="sxs-lookup"><span data-stu-id="b0e2f-150">If this occurs, copy the files to a different folder, and then restart the import and installation process.</span></span>

8. <span data-ttu-id="b0e2f-151">Nella finestra di dialogo **Seleziona Management Pack** fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="b0e2f-151">In the **Select Management Packs** dialog box, click **Close**.</span></span> <span data-ttu-id="b0e2f-152">Il processo di importazione e installazione potrebbe richiedere diversi minuti per il completamento.</span><span class="sxs-lookup"><span data-stu-id="b0e2f-152">The import and installation process might require several minutes to complete.</span></span>

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a><span data-ttu-id="b0e2f-153">Importazione di Management Pack tramite la shell di Operations Manager</span><span class="sxs-lookup"><span data-stu-id="b0e2f-153">Importing the Management Packs by Using the Operations Manager Shell</span></span>

<span data-ttu-id="b0e2f-154">In generale, è più semplice importare i Management Pack tramite la console di Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="b0e2f-154">In general, it is easier to import the management packs by using the Operations Manager console.</span></span> <span data-ttu-id="b0e2f-155">Tuttavia, se si verifica un errore e l'importazione non riesce, la console non sempre fornisce rapporti di errore adeguati.</span><span class="sxs-lookup"><span data-stu-id="b0e2f-155">However, if an error occurs and the import fails, the console does not always provide adequate error reports.</span></span> <span data-ttu-id="b0e2f-156">In base al confronto, Operations Manager Shell offre informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="b0e2f-156">By comparison, the Operations Manager Shell provides detailed information.</span></span> <span data-ttu-id="b0e2f-157">Se si usa Operations Manager e si verificano problemi durante l'importazione di un Management Pack, importare il pacchetto tramite Operations Manager Shell.</span><span class="sxs-lookup"><span data-stu-id="b0e2f-157">If you are using Operations Manager and you encounter issues when importing a management pack, import the pack by using the Operations Manager Shell.</span></span> <span data-ttu-id="b0e2f-158">Le informazioni fornite da Operations Manager Shell consentono di determinare il motivo per cui l'importazione non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="b0e2f-158">The information provided by Operations Manager Shell can help you determine why the import failed.</span></span>

1. <span data-ttu-id="b0e2f-159">Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Microsoft System Center 2012**, fare clic su **Operations Manager**e quindi su **Operations Manager Shell**.</span><span class="sxs-lookup"><span data-stu-id="b0e2f-159">Click **Start**, click **All Programs**, click **Microsoft System Center 2012**, click **Operations Manager**, and then click **Operations Manager Shell**.</span></span>

2. <span data-ttu-id="b0e2f-160">In Operations Manager Shell digitare il comando seguente al prompt dei comandi, usando il percorso effettivo della copia del file Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="b0e2f-160">In Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>

   ```
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp"
   ```

3. <span data-ttu-id="b0e2f-161">Dopo aver importato il primo Management Pack, ripetere il processo usando il percorso per la copia del file Microsoft.LS.2019.Monitoring.ComponentAndUser.mp:</span><span class="sxs-lookup"><span data-stu-id="b0e2f-161">After you have imported the first management pack, repeat the process, using the path to your copy of the file Microsoft.LS.2019.Monitoring.ComponentAndUser.mp:</span></span>

   ```
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ComponentAndUser.mp"
   ```

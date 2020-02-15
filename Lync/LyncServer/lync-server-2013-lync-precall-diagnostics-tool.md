---
title: 'Lync Server 2013: strumento di diagnostica PreCall di Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync PreCall Diagnostics Tool
ms:assetid: 0ff291ec-cfb4-43eb-b5d6-a7a325681e3f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn451255(v=OCS.15)
ms:contentKeyID: 56708404
ms.date: 11/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a63743c634c9e87c743928d7641609ce12c464cb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-precall-diagnostics-tool-in-lync-server-2013"></a><span data-ttu-id="7e49d-102">Lync PreCall Diagnostics Tool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e49d-102">Lync PreCall Diagnostics Tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e49d-103">_**Ultimo argomento modificato:** 2016-11-04_</span><span class="sxs-lookup"><span data-stu-id="7e49d-103">_**Topic Last Modified:** 2016-11-04_</span></span>

<span data-ttu-id="7e49d-104">Lync PreCall Diagnostics Tool (PCD) è un'applicazione basata su client che consente di vedere in che modo lo stato corrente della rete potrebbe influire sulla qualità audio in una chiamata VoIP aziendale imminente.</span><span class="sxs-lookup"><span data-stu-id="7e49d-104">The Lync PreCall Diagnostics Tool (PCD) is a client-based application that allows you to see how the current state of your network might impact the audio quality in an upcoming Enterprise Voice call.</span></span>

<span data-ttu-id="7e49d-105">PCD è particolarmente utile in situazioni in cui l'ultimo hop di una rete rischia di essere il più debole (ad esempio, con laptop su una rete Wi-Fi pubblica o su utenti privati).</span><span class="sxs-lookup"><span data-stu-id="7e49d-105">PCD is most useful in situations where the last hop of a network is likely to be the weakest (for example, with laptops on a public WiFi network or home users).</span></span> <span data-ttu-id="7e49d-106">PCD crea un flusso di pacchetti di piccole dimensioni che attraversa la tappa finale della rete.</span><span class="sxs-lookup"><span data-stu-id="7e49d-106">PCD creates a small packet stream that traverses this final leg of the network.</span></span> <span data-ttu-id="7e49d-107">Lo strumento analizza quindi il flusso di pacchetti per valutare il modo in cui l'instabilità e la perdita lungo la gamba possono influire sulla qualità delle chiamate e quindi fornisce un report.</span><span class="sxs-lookup"><span data-stu-id="7e49d-107">The tool then analyzes the packet stream to estimate how the jitter and loss along this leg might impact call quality, and then provides a report.</span></span> <span data-ttu-id="7e49d-108">È possibile eseguire continuamente PCD sul client, anche quando vengono inserite le chiamate.</span><span class="sxs-lookup"><span data-stu-id="7e49d-108">You can run PCD continuously on the client, even while calls are being placed.</span></span> <span data-ttu-id="7e49d-109">Il flusso di pacchetti non ha un effetto significativo sulla larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="7e49d-109">The packet stream does not have a significant effect on bandwidth.</span></span>

<span data-ttu-id="7e49d-110">**L'ultima versione di PCD, versione 1,1, include i seguenti miglioramenti:**</span><span class="sxs-lookup"><span data-stu-id="7e49d-110">**The latest release of the PCD, version 1.1, includes the following enhancements:**</span></span>

  - <span data-ttu-id="7e49d-111">Supporto per password più lunghe, che possono essere fino a 127 caratteri</span><span class="sxs-lookup"><span data-stu-id="7e49d-111">Support for longer passwords, which can now be up to 127 characters</span></span>

  - <span data-ttu-id="7e49d-112">Diagnostica aggiuntiva per i problemi di accesso all'autenticazione</span><span class="sxs-lookup"><span data-stu-id="7e49d-112">Additional diagnostics for authentication sign-in issues</span></span>

  - <span data-ttu-id="7e49d-113">Supporto migliore per le distribuzioni ibride di Lync</span><span class="sxs-lookup"><span data-stu-id="7e49d-113">Better support for Lync hybrid deployments</span></span>

  - <span data-ttu-id="7e49d-114">Aggiornamenti per la selezione delle credenziali</span><span class="sxs-lookup"><span data-stu-id="7e49d-114">Updates to credential picker</span></span>

  - <span data-ttu-id="7e49d-115">Miglioramenti della stabilità</span><span class="sxs-lookup"><span data-stu-id="7e49d-115">Stability improvements</span></span>

<span data-ttu-id="7e49d-116">Apprezziamo eventuali commenti e suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="7e49d-116">We appreciate any feedback.</span></span> <span data-ttu-id="7e49d-117">Inviare tutte le domande o i problemi di supporto all'alias dei commenti <pcdfb@microsoft.com>e [suggerimenti PCD](mailto:pcdfb@microsoft.com) all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="7e49d-117">Please send all support questions or issues to the [PCD Feedback](mailto:pcdfb@microsoft.com) alias at <pcdfb@microsoft.com>.</span></span>

<span data-ttu-id="7e49d-118">In questo argomento sono incluse le sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7e49d-118">This topic includes the following sections:</span></span>

  - <span data-ttu-id="7e49d-119">Versioni di Lync PCD</span><span class="sxs-lookup"><span data-stu-id="7e49d-119">Lync PCD Versions</span></span>

  - <span data-ttu-id="7e49d-120">Requisiti di sistema di Lync PCD</span><span class="sxs-lookup"><span data-stu-id="7e49d-120">Lync PCD System Requirements</span></span>

  - <span data-ttu-id="7e49d-121">Funzionalità di Lync PCD</span><span class="sxs-lookup"><span data-stu-id="7e49d-121">Lync PCD Features</span></span>

  - <span data-ttu-id="7e49d-122">Esecuzione di Lync PCD</span><span class="sxs-lookup"><span data-stu-id="7e49d-122">Running Lync PCD</span></span>

  - <span data-ttu-id="7e49d-123">Disinstallazione di Lync PCD</span><span class="sxs-lookup"><span data-stu-id="7e49d-123">Uninstalling Lync PCD</span></span>

<span id="Version"></span>

<div>

## <a name="lync-pcd-versions"></a><span data-ttu-id="7e49d-124">Versioni di Lync PCD</span><span class="sxs-lookup"><span data-stu-id="7e49d-124">Lync PCD Versions</span></span>

<span data-ttu-id="7e49d-125">In questo argomento vengono descritte le versioni seguenti dello strumento, disponibili per il download gratuito:</span><span class="sxs-lookup"><span data-stu-id="7e49d-125">This topic describes the following versions of the tool, available for free download:</span></span>

  - <span data-ttu-id="7e49d-126">App desktop di Windows[http://go.microsoft.com/fwlink/?LinkId=327914](http://go.microsoft.com/fwlink/p/?linkid=327914)()</span><span class="sxs-lookup"><span data-stu-id="7e49d-126">Windows Desktop App ([http://go.microsoft.com/fwlink/?LinkId=327914](http://go.microsoft.com/fwlink/p/?linkid=327914))</span></span>

</div>

<span id="Requirements"></span>

<div>

## <a name="lync-pcd-system-requirements"></a><span data-ttu-id="7e49d-127">Requisiti di sistema di Lync PCD</span><span class="sxs-lookup"><span data-stu-id="7e49d-127">Lync PCD System Requirements</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7e49d-128">PCD richiede che Unified Communications Web API (UCWA) venga installata e configurata per supportare i client mobili nella distribuzione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7e49d-128">PCD requires that Unified Communications Web API (UCWA) be installed and configured to support mobile clients in the Lync Server deployment.</span></span> <span data-ttu-id="7e49d-129">UCWA viene installato con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7e49d-129">UCWA is installed with Lync Server.</span></span>



</div>

<div>

## <a name="windows-desktop-app-requirements"></a><span data-ttu-id="7e49d-130">Requisiti per le app desktop di Windows</span><span class="sxs-lookup"><span data-stu-id="7e49d-130">Windows Desktop App Requirements</span></span>

  - <span data-ttu-id="7e49d-131">Qualsiasi edizione del sistema operativo Windows 7 o Windows 8</span><span class="sxs-lookup"><span data-stu-id="7e49d-131">Any edition of the Windows 7 or Windows 8 operating system</span></span>

  - <span data-ttu-id="7e49d-132">Microsoft .NET Framework 4,5 disponibile all'indirizzo[http://go.microsoft.com/fwlink/?LinkId=327790](http://go.microsoft.com/fwlink/p/?linkid=327790)</span><span class="sxs-lookup"><span data-stu-id="7e49d-132">Microsoft .NET Framework 4.5 available at [http://go.microsoft.com/fwlink/?LinkId=327790](http://go.microsoft.com/fwlink/p/?linkid=327790)</span></span>

</div>

</div>

<span id="features"></span>

<div>

## <a name="lync-pcd-features"></a><span data-ttu-id="7e49d-133">Funzionalità di Lync PCD</span><span class="sxs-lookup"><span data-stu-id="7e49d-133">Lync PCD Features</span></span>

<span data-ttu-id="7e49d-134">Lync PCD include le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="7e49d-134">Lync PCD includes the following features:</span></span>

  - <span data-ttu-id="7e49d-135">Esecuzione in predefinita su richiesta (burst di 2 minuti)</span><span class="sxs-lookup"><span data-stu-id="7e49d-135">Run in default On Demand (2 minute bursts)</span></span>

  - <span data-ttu-id="7e49d-136">Eseguire la modalità sempre attiva (fino a 24 ore nella visualizzazione bloccata)</span><span class="sxs-lookup"><span data-stu-id="7e49d-136">Run in Always On (up to 24 hours in snapped view) mode</span></span>

  - <span data-ttu-id="7e49d-137">Visualizzazione cronologica delle esecuzioni dei test</span><span class="sxs-lookup"><span data-stu-id="7e49d-137">Historical view of your test runs</span></span>

  - <span data-ttu-id="7e49d-138">Diagnosticare gli errori di accesso (solo Lync PCD per Windows 8)</span><span class="sxs-lookup"><span data-stu-id="7e49d-138">Diagnose sign-in failures (Lync PCD for Windows 8 only)</span></span>

<span data-ttu-id="7e49d-139">![Schermate di accesso alle funzionalità di Lync PCD](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Schermate di accesso alle funzionalità di Lync PCD")</span><span class="sxs-lookup"><span data-stu-id="7e49d-139">![Lync PCD features Sign in progress screen shot](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Lync PCD features Sign in progress screen shot")</span></span>

  - <span data-ttu-id="7e49d-140">Visualizzazione grafica delle metriche di rete – MOS di rete, perdita di pacchetti e instabilità di interarrivo a schermo intero e visualizzazione a scatto.</span><span class="sxs-lookup"><span data-stu-id="7e49d-140">Graphical view of network metrics – Network MOS, Packet Loss and Interarrival Jitter in full screen and snapped view.</span></span>

<span data-ttu-id="7e49d-141">**Visualizzazione a schermo intero**</span><span class="sxs-lookup"><span data-stu-id="7e49d-141">**Full screen view**</span></span>

<span data-ttu-id="7e49d-142">![Grafico dei risultati del test dello strumento di diagnostica PreCall](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "Grafico dei risultati del test dello strumento di diagnostica PreCall")</span><span class="sxs-lookup"><span data-stu-id="7e49d-142">![PreCall Diagnostic Tool test result graphs](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "PreCall Diagnostic Tool test result graphs")</span></span>

<span data-ttu-id="7e49d-143">**Visualizzazione bloccata**</span><span class="sxs-lookup"><span data-stu-id="7e49d-143">**Snapped view**</span></span>

<span data-ttu-id="7e49d-144">![Risultati dei test per l'utilizzo dello strumento di diagnostica PreCall](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "Risultati dei test per l'utilizzo dello strumento di diagnostica PreCall")</span><span class="sxs-lookup"><span data-stu-id="7e49d-144">![PreCall Diagnostic Tool Utilization test results](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "PreCall Diagnostic Tool Utilization test results")</span></span>

</div>

<span id="running"></span>

<div>

## <a name="running-lync-pcd"></a><span data-ttu-id="7e49d-145">Esecuzione di Lync PCD</span><span class="sxs-lookup"><span data-stu-id="7e49d-145">Running Lync PCD</span></span>

<div>

## <a name="running-windows-desktop-app"></a><span data-ttu-id="7e49d-146">Esecuzione dell'app desktop di Windows</span><span class="sxs-lookup"><span data-stu-id="7e49d-146">Running Windows Desktop App</span></span>

1.  <span data-ttu-id="7e49d-147">Per avviare PCD su un sistema Windows 7, selezionare **PreCall Diagnostics** dal menu **Start** .</span><span class="sxs-lookup"><span data-stu-id="7e49d-147">To start the PCD on a Windows 7 system, select **PreCall Diagnostics** from the **Start** menu.</span></span>
    
    <span data-ttu-id="7e49d-148">Per avviare il PCD su un sistema Windows 8, selezionare l'icona nella schermata Start oppure cercare "PreCall Diagnostics".</span><span class="sxs-lookup"><span data-stu-id="7e49d-148">To start the PCD on a Windows 8 system, select the icon on your Start screen, or search for “PreCall Diagnostics.”</span></span>
    
    <span data-ttu-id="7e49d-149">![Icona dello strumento di diagnostica PreCall](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "Icona dello strumento di diagnostica PreCall")</span><span class="sxs-lookup"><span data-stu-id="7e49d-149">![PreCall Diagnostic tool icon](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "PreCall Diagnostic tool icon")</span></span>

2.  <span data-ttu-id="7e49d-150">Quando si avvia lo strumento, selezionare il metodo preferito per specificare le credenziali e selezionare la modalità di funzionamento della rete nella finestra di dialogo **Opzioni dello strumento di diagnostica PreCall** e quindi fare clic su **OK**:</span><span class="sxs-lookup"><span data-stu-id="7e49d-150">When the tool starts, select your preferred method of providing credentials and select the network operating mode in the **PreCall Diagnostics Tool Options** dialog box, then select **OK**:</span></span>

3.  <span data-ttu-id="7e49d-151">Selezionare il pulsante **Avvia test** per iniziare a eseguire la diagnostica.</span><span class="sxs-lookup"><span data-stu-id="7e49d-151">Select the **Start Test** button to start running diagnostics.</span></span>
    
    <span data-ttu-id="7e49d-152">Se è stata selezionata l'opzione **Usa credenziali di rete** , il test inizia immediatamente.</span><span class="sxs-lookup"><span data-stu-id="7e49d-152">If you selected the **Use network credentials** option, the test begins immediately.</span></span>
    
    <span data-ttu-id="7e49d-153">Se è stata selezionata l'opzione **let me Enter my credentials** , viene visualizzata la finestra di dialogo **sicurezza di Windows** .</span><span class="sxs-lookup"><span data-stu-id="7e49d-153">If you selected the **Let me enter my credentials** option, the **Windows Security** dialog box opens.</span></span> <span data-ttu-id="7e49d-154">Dopo aver immesso le credenziali, viene avviato il test.</span><span class="sxs-lookup"><span data-stu-id="7e49d-154">After you enter your credentials, the test starts.</span></span>

</div>

</div>

<span id="uninstall"></span>

<div>

## <a name="uninstalling-lync-pcd"></a><span data-ttu-id="7e49d-155">Disinstallazione di Lync PCD</span><span class="sxs-lookup"><span data-stu-id="7e49d-155">Uninstalling Lync PCD</span></span>

<span data-ttu-id="7e49d-156">Per rimuovere Lync PCD, seguire la procedura per il sistema operativo in uso:</span><span class="sxs-lookup"><span data-stu-id="7e49d-156">To remove Lync PCD, follow the procedure for your operating system:</span></span>

  - <span data-ttu-id="7e49d-157">In un sistema Windows 7, aprire il **Pannello di controllo**, selezionare **programmi e funzionalità**e fare doppio clic su **Lync 2013 PreCall Diagnostics**.</span><span class="sxs-lookup"><span data-stu-id="7e49d-157">On a Windows 7 system, open the **Control Panel**, select **Programs and Features**, and double-click **Lync 2013 PreCall Diagnostics**.</span></span>

  - <span data-ttu-id="7e49d-158">In un sistema Windows 8, fare clic con il pulsante destro del mouse sul riquadro PCD e scegliere **Disinstalla** dalla barra dell'app nella parte inferiore della schermata iniziale.</span><span class="sxs-lookup"><span data-stu-id="7e49d-158">On a Windows 8 system, right-click on the PCD tile and click **Uninstall** from the app bar at the bottom of the start screen.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


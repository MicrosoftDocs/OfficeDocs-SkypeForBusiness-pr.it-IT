---
title: 'Lync Server 2013: strumento di diagnostica prechiamata di Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync PreCall Diagnostics Tool
ms:assetid: 0ff291ec-cfb4-43eb-b5d6-a7a325681e3f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn451255(v=OCS.15)
ms:contentKeyID: 56708404
ms.date: 11/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e22b542a5840714455d4abdb0a7163e6a8ba748
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978971"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-precall-diagnostics-tool-in-lync-server-2013"></a><span data-ttu-id="6348d-102">Strumento di diagnostica prechiamata di Lync in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6348d-102">Lync PreCall Diagnostics Tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6348d-103">_**Argomento Ultima modifica:** 2016-11-04_</span><span class="sxs-lookup"><span data-stu-id="6348d-103">_**Topic Last Modified:** 2016-11-04_</span></span>

<span data-ttu-id="6348d-104">Lo strumento di diagnostica prechiamata di Lync (PCD) è un'applicazione basata sul client che consente di verificare in che modo lo stato corrente della rete potrebbe avere un impatto sulla qualità audio in una chiamata vocale aziendale imminente.</span><span class="sxs-lookup"><span data-stu-id="6348d-104">The Lync PreCall Diagnostics Tool (PCD) is a client-based application that allows you to see how the current state of your network might impact the audio quality in an upcoming Enterprise Voice call.</span></span>

<span data-ttu-id="6348d-105">PCD è molto utile in situazioni in cui l'ultimo hop di una rete rischia di essere il più debole, ad esempio con i computer portatili in una rete WiFi pubblica o con utenti privati.</span><span class="sxs-lookup"><span data-stu-id="6348d-105">PCD is most useful in situations where the last hop of a network is likely to be the weakest (for example, with laptops on a public WiFi network or home users).</span></span> <span data-ttu-id="6348d-106">PCD crea un piccolo flusso di pacchetti che attraversa questo segmento finale della rete.</span><span class="sxs-lookup"><span data-stu-id="6348d-106">PCD creates a small packet stream that traverses this final leg of the network.</span></span> <span data-ttu-id="6348d-107">Lo strumento analizza quindi il flusso di pacchetti per stimare in che modo il jitter e la perdita lungo questa gamba potrebbero avere un impatto sulla qualità delle chiamate e quindi fornire un report.</span><span class="sxs-lookup"><span data-stu-id="6348d-107">The tool then analyzes the packet stream to estimate how the jitter and loss along this leg might impact call quality, and then provides a report.</span></span> <span data-ttu-id="6348d-108">Puoi eseguire continuamente PCD nel client, anche quando vengono inserite le chiamate.</span><span class="sxs-lookup"><span data-stu-id="6348d-108">You can run PCD continuously on the client, even while calls are being placed.</span></span> <span data-ttu-id="6348d-109">Il flusso di pacchetti non ha un effetto significativo sulla larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="6348d-109">The packet stream does not have a significant effect on bandwidth.</span></span>

<span data-ttu-id="6348d-110">**L'ultima versione di PCD, versione 1,1, include i miglioramenti seguenti:**</span><span class="sxs-lookup"><span data-stu-id="6348d-110">**The latest release of the PCD, version 1.1, includes the following enhancements:**</span></span>

  - <span data-ttu-id="6348d-111">Supporto per le password più lunghe, che ora possono contenere fino a 127 caratteri</span><span class="sxs-lookup"><span data-stu-id="6348d-111">Support for longer passwords, which can now be up to 127 characters</span></span>

  - <span data-ttu-id="6348d-112">Diagnostica aggiuntiva per i problemi di accesso all'autenticazione</span><span class="sxs-lookup"><span data-stu-id="6348d-112">Additional diagnostics for authentication sign-in issues</span></span>

  - <span data-ttu-id="6348d-113">Supporto migliore per distribuzioni ibride di Lync</span><span class="sxs-lookup"><span data-stu-id="6348d-113">Better support for Lync hybrid deployments</span></span>

  - <span data-ttu-id="6348d-114">Aggiornamenti di selezione credenziali</span><span class="sxs-lookup"><span data-stu-id="6348d-114">Updates to credential picker</span></span>

  - <span data-ttu-id="6348d-115">Miglioramenti della stabilità</span><span class="sxs-lookup"><span data-stu-id="6348d-115">Stability improvements</span></span>

<span data-ttu-id="6348d-116">Apprezziamo qualsiasi feedback.</span><span class="sxs-lookup"><span data-stu-id="6348d-116">We appreciate any feedback.</span></span> <span data-ttu-id="6348d-117">Inviare tutte le domande o i problemi di supporto all'alias di [feedback PCD](mailto:pcdfb@microsoft.com) <pcdfb@microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="6348d-117">Please send all support questions or issues to the [PCD Feedback](mailto:pcdfb@microsoft.com) alias at <pcdfb@microsoft.com>.</span></span>

<span data-ttu-id="6348d-118">Questo argomento include le sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6348d-118">This topic includes the following sections:</span></span>

  - <span data-ttu-id="6348d-119">Versioni di Lync PCD</span><span class="sxs-lookup"><span data-stu-id="6348d-119">Lync PCD Versions</span></span>

  - <span data-ttu-id="6348d-120">Requisiti di sistema di Lync PCD</span><span class="sxs-lookup"><span data-stu-id="6348d-120">Lync PCD System Requirements</span></span>

  - <span data-ttu-id="6348d-121">Caratteristiche di Lync PCD</span><span class="sxs-lookup"><span data-stu-id="6348d-121">Lync PCD Features</span></span>

  - <span data-ttu-id="6348d-122">Eseguire Lync PCD</span><span class="sxs-lookup"><span data-stu-id="6348d-122">Running Lync PCD</span></span>

  - <span data-ttu-id="6348d-123">Disinstallazione di Lync PCD</span><span class="sxs-lookup"><span data-stu-id="6348d-123">Uninstalling Lync PCD</span></span>

<span id="Version"></span>

<div>

## <a name="lync-pcd-versions"></a><span data-ttu-id="6348d-124">Versioni di Lync PCD</span><span class="sxs-lookup"><span data-stu-id="6348d-124">Lync PCD Versions</span></span>

<span data-ttu-id="6348d-125">Questo argomento descrive le versioni seguenti dello strumento, disponibile per il download gratuito:</span><span class="sxs-lookup"><span data-stu-id="6348d-125">This topic describes the following versions of the tool, available for free download:</span></span>

  - <span data-ttu-id="6348d-126">App desktop di Windows[http://go.microsoft.com/fwlink/?LinkId=327914](http://go.microsoft.com/fwlink/p/?linkid=327914)()</span><span class="sxs-lookup"><span data-stu-id="6348d-126">Windows Desktop App ([http://go.microsoft.com/fwlink/?LinkId=327914](http://go.microsoft.com/fwlink/p/?linkid=327914))</span></span>

</div>

<span id="Requirements"></span>

<div>

## <a name="lync-pcd-system-requirements"></a><span data-ttu-id="6348d-127">Requisiti di sistema di Lync PCD</span><span class="sxs-lookup"><span data-stu-id="6348d-127">Lync PCD System Requirements</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6348d-128">PCD richiede l'installazione e la configurazione di Unified Communications Web API (UCWA) per supportare i client mobili nella distribuzione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6348d-128">PCD requires that Unified Communications Web API (UCWA) be installed and configured to support mobile clients in the Lync Server deployment.</span></span> <span data-ttu-id="6348d-129">UCWA viene installato con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6348d-129">UCWA is installed with Lync Server.</span></span>



</div>

<div>

## <a name="windows-desktop-app-requirements"></a><span data-ttu-id="6348d-130">Requisiti per le app desktop di Windows</span><span class="sxs-lookup"><span data-stu-id="6348d-130">Windows Desktop App Requirements</span></span>

  - <span data-ttu-id="6348d-131">Tutte le edizioni del sistema operativo Windows 7 o Windows 8</span><span class="sxs-lookup"><span data-stu-id="6348d-131">Any edition of the Windows 7 or Windows 8 operating system</span></span>

  - <span data-ttu-id="6348d-132">Microsoft .NET Framework 4,5 disponibile all'indirizzo[http://go.microsoft.com/fwlink/?LinkId=327790](http://go.microsoft.com/fwlink/p/?linkid=327790)</span><span class="sxs-lookup"><span data-stu-id="6348d-132">Microsoft .NET Framework 4.5 available at [http://go.microsoft.com/fwlink/?LinkId=327790](http://go.microsoft.com/fwlink/p/?linkid=327790)</span></span>

</div>

</div>

<span id="features"></span>

<div>

## <a name="lync-pcd-features"></a><span data-ttu-id="6348d-133">Caratteristiche di Lync PCD</span><span class="sxs-lookup"><span data-stu-id="6348d-133">Lync PCD Features</span></span>

<span data-ttu-id="6348d-134">Lync PCD include le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="6348d-134">Lync PCD includes the following features:</span></span>

  - <span data-ttu-id="6348d-135">Esegui in default su richiesta (2 minuti di burst)</span><span class="sxs-lookup"><span data-stu-id="6348d-135">Run in default On Demand (2 minute bursts)</span></span>

  - <span data-ttu-id="6348d-136">Esecuzione in modalità sempre attiva (fino a 24 ore in visualizzazione ancorata)</span><span class="sxs-lookup"><span data-stu-id="6348d-136">Run in Always On (up to 24 hours in snapped view) mode</span></span>

  - <span data-ttu-id="6348d-137">Visualizzazione cronologica delle esecuzioni dei test</span><span class="sxs-lookup"><span data-stu-id="6348d-137">Historical view of your test runs</span></span>

  - <span data-ttu-id="6348d-138">Diagnosticare gli errori di accesso (solo Lync PCD per Windows 8)</span><span class="sxs-lookup"><span data-stu-id="6348d-138">Diagnose sign-in failures (Lync PCD for Windows 8 only)</span></span>

<span data-ttu-id="6348d-139">![Funzionalità di accesso di Lync PCD schermata di stato](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "")</span><span class="sxs-lookup"><span data-stu-id="6348d-139">![Lync PCD features Sign in progress screen shot](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Lync PCD features Sign in progress screen shot")</span></span>

  - <span data-ttu-id="6348d-140">Visualizzazione grafica delle metriche di rete: MOS di rete, perdita di pacchetti e jitter di interarrivo a schermo intero e visualizzazione in blocco.</span><span class="sxs-lookup"><span data-stu-id="6348d-140">Graphical view of network metrics – Network MOS, Packet Loss and Interarrival Jitter in full screen and snapped view.</span></span>

<span data-ttu-id="6348d-141">**Visualizzazione a schermo intero**</span><span class="sxs-lookup"><span data-stu-id="6348d-141">**Full screen view**</span></span>

<span data-ttu-id="6348d-142">![PreCall strumento di diagnostica del risultato del test]degli strumenti di diagnostica di(images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "prechiamata") per i grafici del risultato</span><span class="sxs-lookup"><span data-stu-id="6348d-142">![PreCall Diagnostic Tool test result graphs](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "PreCall Diagnostic Tool test result graphs")</span></span>

<span data-ttu-id="6348d-143">**Visualizzazione bloccata**</span><span class="sxs-lookup"><span data-stu-id="6348d-143">**Snapped view**</span></span>

<span data-ttu-id="6348d-144">![PreCall test di utilizzo degli strumenti di diagnostica]PreCall risultati del(images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "test di utilizzo degli strumenti di diagnostica")</span><span class="sxs-lookup"><span data-stu-id="6348d-144">![PreCall Diagnostic Tool Utilization test results](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "PreCall Diagnostic Tool Utilization test results")</span></span>

</div>

<span id="running"></span>

<div>

## <a name="running-lync-pcd"></a><span data-ttu-id="6348d-145">Eseguire Lync PCD</span><span class="sxs-lookup"><span data-stu-id="6348d-145">Running Lync PCD</span></span>

<div>

## <a name="running-windows-desktop-app"></a><span data-ttu-id="6348d-146">Eseguire l'app desktop di Windows</span><span class="sxs-lookup"><span data-stu-id="6348d-146">Running Windows Desktop App</span></span>

1.  <span data-ttu-id="6348d-147">Per avviare il PCD in un sistema Windows 7, selezionare **diagnostica prechiamata** dal menu **Start** .</span><span class="sxs-lookup"><span data-stu-id="6348d-147">To start the PCD on a Windows 7 system, select **PreCall Diagnostics** from the **Start** menu.</span></span>
    
    <span data-ttu-id="6348d-148">Per avviare il PCD in un sistema Windows 8, selezionare l'icona nella schermata Start oppure cercare "diagnostica prechiamata".</span><span class="sxs-lookup"><span data-stu-id="6348d-148">To start the PCD on a Windows 8 system, select the icon on your Start screen, or search for “PreCall Diagnostics.”</span></span>
    
    <span data-ttu-id="6348d-149">(images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "Icona dello") strumento di diagnostica ![prechiamata]</span><span class="sxs-lookup"><span data-stu-id="6348d-149">![PreCall Diagnostic tool icon](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "PreCall Diagnostic tool icon")</span></span>

2.  <span data-ttu-id="6348d-150">Quando lo strumento viene avviato, selezionare il metodo preferito per fornire le credenziali e selezionare la modalità di funzionamento della rete nella finestra di dialogo **Opzioni strumento di diagnostica prechiamata** , quindi scegliere **OK**:</span><span class="sxs-lookup"><span data-stu-id="6348d-150">When the tool starts, select your preferred method of providing credentials and select the network operating mode in the **PreCall Diagnostics Tool Options** dialog box, then select **OK**:</span></span>

3.  <span data-ttu-id="6348d-151">Selezionare il pulsante **Avvia test** per iniziare a eseguire la diagnostica.</span><span class="sxs-lookup"><span data-stu-id="6348d-151">Select the **Start Test** button to start running diagnostics.</span></span>
    
    <span data-ttu-id="6348d-152">Se è stata selezionata l'opzione **Usa credenziali di rete** , il test inizia immediatamente.</span><span class="sxs-lookup"><span data-stu-id="6348d-152">If you selected the **Use network credentials** option, the test begins immediately.</span></span>
    
    <span data-ttu-id="6348d-153">Se è stata selezionata l'opzione **Consenti immissione credenziali personali** , viene visualizzata la finestra di dialogo **sicurezza di Windows** .</span><span class="sxs-lookup"><span data-stu-id="6348d-153">If you selected the **Let me enter my credentials** option, the **Windows Security** dialog box opens.</span></span> <span data-ttu-id="6348d-154">Dopo aver immesso le credenziali, viene avviato il test.</span><span class="sxs-lookup"><span data-stu-id="6348d-154">After you enter your credentials, the test starts.</span></span>

</div>

</div>

<span id="uninstall"></span>

<div>

## <a name="uninstalling-lync-pcd"></a><span data-ttu-id="6348d-155">Disinstallazione di Lync PCD</span><span class="sxs-lookup"><span data-stu-id="6348d-155">Uninstalling Lync PCD</span></span>

<span data-ttu-id="6348d-156">Per rimuovere Lync PCD, seguire la procedura per il sistema operativo in uso:</span><span class="sxs-lookup"><span data-stu-id="6348d-156">To remove Lync PCD, follow the procedure for your operating system:</span></span>

  - <span data-ttu-id="6348d-157">In un sistema Windows 7 aprire il **Pannello di controllo**, selezionare **programmi e funzionalità**e fare doppio clic su **Lync 2013 PreCall Diagnostics**.</span><span class="sxs-lookup"><span data-stu-id="6348d-157">On a Windows 7 system, open the **Control Panel**, select **Programs and Features**, and double-click **Lync 2013 PreCall Diagnostics**.</span></span>

  - <span data-ttu-id="6348d-158">In un sistema Windows 8 fare clic con il pulsante destro del mouse sul riquadro PCD e scegliere **Disinstalla** dalla barra dell'app nella parte inferiore della schermata Start.</span><span class="sxs-lookup"><span data-stu-id="6348d-158">On a Windows 8 system, right-click on the PCD tile and click **Uninstall** from the app bar at the bottom of the start screen.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


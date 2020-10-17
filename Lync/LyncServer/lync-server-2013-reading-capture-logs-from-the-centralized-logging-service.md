---
title: 'Lync Server 2013: lettura dei registri di acquisizione dal servizio di registrazione centralizzato'
description: 'Lync Server 2013: lettura dei registri di acquisizione dal servizio di registrazione centralizzato.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reading capture logs from the Centralized Logging Service
ms:assetid: c86ccf61-d86f-4ebd-b8d1-984a1b73005d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721879(v=OCS.15)
ms:contentKeyID: 49733813
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fcdd70c924b49098814e80a375ae34d2bf48dc41
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559162"
---
# <a name="reading-capture-logs-from-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="1444f-103">Lettura dei registri di acquisizione dal servizio di registrazione centralizzato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1444f-103">Reading capture logs from the Centralized Logging Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1444f-104">_**Ultimo argomento modificato:** 2016-12-28_</span><span class="sxs-lookup"><span data-stu-id="1444f-104">_**Topic Last Modified:** 2016-12-28_</span></span>

<span data-ttu-id="1444f-105">Si rende conto del vantaggio reale del servizio di registrazione centralizzato dopo aver eseguito la ricerca e si dispone di un file che è possibile utilizzare per individuare un problema segnalato.</span><span class="sxs-lookup"><span data-stu-id="1444f-105">You realize the real benefit of the Centralized Logging Service after you run the search and you have a file that you can use to track down a reported problem.</span></span> <span data-ttu-id="1444f-106">È possibile leggere il file in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="1444f-106">There are a number of ways that you can read the file.</span></span> <span data-ttu-id="1444f-107">Il file di output è in formato testo standard ed è possibile utilizzare Notepad.exe o qualsiasi altro programma che consenta l'apertura e la lettura di un file di testo.</span><span class="sxs-lookup"><span data-stu-id="1444f-107">The output file is in a standard text format and you can use Notepad.exe or any other programs that will allow you to open and read a text file.</span></span> <span data-ttu-id="1444f-108">Per i file più grandi e i problemi più complessi, è possibile utilizzare uno strumento come Snooper.exe che è stato creato per leggere e analizzare l'output di registrazione dal servizio di registrazione centralizzato.</span><span class="sxs-lookup"><span data-stu-id="1444f-108">For larger files and more complex issues, you could use a tool like Snooper.exe that is designed to read and parse the logging output from the Centralized Logging Service.</span></span> <span data-ttu-id="1444f-109">Snooper è incluso negli strumenti di debug di Lync Server 2013 disponibili come download separato.</span><span class="sxs-lookup"><span data-stu-id="1444f-109">Snooper is included with the Lync Server 2013 Debug Tools that are available as a separate download.</span></span> <span data-ttu-id="1444f-110">È possibile scaricare gli strumenti di debug di Lync Server 2013 qui: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257) .</span><span class="sxs-lookup"><span data-stu-id="1444f-110">You can download the Lync Server 2013 Debug Tools here: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257).</span></span> <span data-ttu-id="1444f-111">Quando si installano gli strumenti di debug di Lync Server 2013, non vengono creati scorciatoie e voci di menu.</span><span class="sxs-lookup"><span data-stu-id="1444f-111">When you install the Lync Server 2013 Debug Tools, short cuts and menu items are not created.</span></span> <span data-ttu-id="1444f-112">Dopo aver installato gli strumenti di debug di Lync Server 2013, aprire Esplora risorse, una finestra della riga di comando o Lync Server Management Shell e passare alla directory (percorso predefinito) C: \\ Program Files \\ Microsoft lync Server 2013 \\ Debugging Tools.</span><span class="sxs-lookup"><span data-stu-id="1444f-112">After you install the Lync Server 2013 Debug Tools, open Windows Explorer, a command-line window, or Lync Server Management Shell and go to the directory (default location) C:\\Program Files\\Microsoft Lync Server 2013\\Debugging Tools.</span></span> <span data-ttu-id="1444f-113">Fare doppio clic su Snooper.exe o digitare Snooper.exe, quindi premere INVIO se si utilizza la riga di comando o Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="1444f-113">Double-click Snooper.exe or type Snooper.exe, and then press ENTER if you are using the command line or Lync Server Management Shell.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1444f-114">Lo scopo di questo argomento non è quello di illustrare le tecniche di risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="1444f-114">The intent of this topic is not to detail and discuss troubleshooting techniques.</span></span> <span data-ttu-id="1444f-115">La risoluzione dei problemi e i processi attorno a esso sono un argomento complesso.</span><span class="sxs-lookup"><span data-stu-id="1444f-115">Troubleshooting and the processes around it is a complex subject.</span></span> <span data-ttu-id="1444f-116">Per informazioni dettagliate sulla risoluzione dei problemi di base e sulla risoluzione dei problemi relativi ai carichi di lavoro specifici, vedere Microsoft Lync Server 2010 Resource Kit book at <A href="https://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A> .</span><span class="sxs-lookup"><span data-stu-id="1444f-116">For details about troubleshooting basics and troubleshooting specific workloads, see the Microsoft Lync Server 2010 Resource Kit book at <A href="https://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A>.</span></span> <span data-ttu-id="1444f-117">I processi e le procedure si applicano ancora a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1444f-117">The processes and procedures still apply to Lync Server 2013.</span></span>



</div>

<span data-ttu-id="1444f-118">Lync Server 2013 introduce una versione aggiornata di Snooper che include alcune nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="1444f-118">Lync Server 2013 introduces an updated version of Snooper that includes some new features.</span></span> <span data-ttu-id="1444f-119">Nella schermata seguente viene visualizzata la versione di Snooper di Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="1444f-119">The following screen shot shows the version of Snooper from Office Communications Server 2007.</span></span>

<span data-ttu-id="1444f-120">![Versione di Snooper di Office Communications 2007.](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Versione di Snooper di Office Communications 2007.")</span><span class="sxs-lookup"><span data-stu-id="1444f-120">![Office Communications 2007 version of Snooper.](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Office Communications 2007 version of Snooper.")</span></span>

<span data-ttu-id="1444f-121">Nella schermata seguente viene illustrata la nuova versione di Snooper inclusa negli strumenti di debug di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1444f-121">The following screen shot shows the new version of Snooper included in the Lync Server 2013 Debug Tools.</span></span>

<span data-ttu-id="1444f-122">![Versione di Snooper di Lync Server 2013.](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Versione di Snooper di Lync Server 2013.")</span><span class="sxs-lookup"><span data-stu-id="1444f-122">![Lync Server 2013 version of Snooper.](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Lync Server 2013 version of Snooper.")</span></span>

<span data-ttu-id="1444f-123">Nella schermata seguente viene visualizzata la barra degli strumenti con funzioni di uso frequente.</span><span class="sxs-lookup"><span data-stu-id="1444f-123">The following screen shot shows the toolbar with frequently used functions.</span></span>

<span data-ttu-id="1444f-124">![Barra degli strumenti Snooper 2013.](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Barra degli strumenti Snooper 2013.")</span><span class="sxs-lookup"><span data-stu-id="1444f-124">![Snooper 2013 toolbar.](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Snooper 2013 toolbar.")</span></span>

<span data-ttu-id="1444f-125">E, la caratteristica più recente che aggiunge valore è la visualizzazione diagramma flusso (flusso di chiamata).</span><span class="sxs-lookup"><span data-stu-id="1444f-125">And, the newest feature that adds value is the Flow Chart (call flow) diagram view.</span></span> <span data-ttu-id="1444f-126">È possibile selezionare un flusso di messaggi nella scheda **messaggio** e fare clic sul pulsante **flusso di chiamata** .</span><span class="sxs-lookup"><span data-stu-id="1444f-126">You select a message flow in the **Message** tab and click the **Call Flow** button.</span></span> <span data-ttu-id="1444f-127">Quando si procede attraverso i messaggi, il diagramma del flusso di chiamata viene aggiornato con i nuovi dati.</span><span class="sxs-lookup"><span data-stu-id="1444f-127">As you proceed through the messages, the call flow diagram updates with new data.</span></span>

<span data-ttu-id="1444f-128">![Diagramma del flusso di chiamata di Snooper 2013.](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Diagramma del flusso di chiamata di Snooper 2013.")</span><span class="sxs-lookup"><span data-stu-id="1444f-128">![Snooper 2013 call flow diagram.](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Snooper 2013 call flow diagram.")</span></span>

<span data-ttu-id="1444f-129">È possibile posizionare il puntatore del mouse sulla visualizzazione diagramma e ottenere informazioni dettagliate sui messaggi e sul contenuto dei flussi e dei messaggi, nonché sugli elementi del server.</span><span class="sxs-lookup"><span data-stu-id="1444f-129">You can hover over the diagram view and get details about the messages and content of the flows and messages as well as the server elements.</span></span> <span data-ttu-id="1444f-130">Fare clic su qualsiasi freccia del flusso di chiamata per passare al messaggio nella visualizzazione messaggi.</span><span class="sxs-lookup"><span data-stu-id="1444f-130">Click on any call flow arrow to go to the message in the Messages view.</span></span>

<span data-ttu-id="1444f-131">![Dettagli del messaggio del diagramma di flusso delle chiamate.](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "Dettagli del messaggio del diagramma di flusso delle chiamate.")</span><span class="sxs-lookup"><span data-stu-id="1444f-131">![Call flow diagram message details.](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "Call flow diagram message details.")</span></span>

<div>

## <a name="to-open-a-log-file-in-snooper"></a><span data-ttu-id="1444f-132">Per aprire un file di registro in Snooper</span><span class="sxs-lookup"><span data-stu-id="1444f-132">To open a log file in Snooper</span></span>

1.  <span data-ttu-id="1444f-133">Per utilizzare Snooper e aprire i file di registro, è necessario l'accesso in lettura ai file di registro.</span><span class="sxs-lookup"><span data-stu-id="1444f-133">To use Snooper and open log files, you need read access to the log files.</span></span> <span data-ttu-id="1444f-134">Per utilizzare Snooper e accedere ai file di registro, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator (RBAC), oppure un ruolo RBAC personalizzato che contenga uno dei due gruppi.</span><span class="sxs-lookup"><span data-stu-id="1444f-134">To use Snooper and access the log files you must be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>

2.  <span data-ttu-id="1444f-135">Dopo l'installazione degli strumenti di debug di Lync Server (LyncDebugTools.msi), cambiare directory nel percorso di Snooper.exe tramite Esplora risorse o dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="1444f-135">After the installation of the Lync Server Debugging Tools (LyncDebugTools.msi), change directory to the location of Snooper.exe using Windows Explorer or from the command line.</span></span> <span data-ttu-id="1444f-136">Per impostazione predefinita, gli strumenti di debug sono disponibili in C: \\ Program Files \\ Microsoft Lync Server 2013 \\ Debugging Tools.</span><span class="sxs-lookup"><span data-stu-id="1444f-136">By default, the debugging tools are located in C:\\Program Files\\Microsoft Lync Server 2013\\Debugging Tools.</span></span> <span data-ttu-id="1444f-137">Fare doppio clic o eseguire Snooper.exe.</span><span class="sxs-lookup"><span data-stu-id="1444f-137">Double-click or run Snooper.exe.</span></span>

3.  <span data-ttu-id="1444f-138">Dopo aver aperto Snooper, fare clic con il pulsante destro del mouse su **file**, scegliere **OpenFile**, individuare i file di registro, selezionare un file nella finestra di dialogo **Apri** e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="1444f-138">After Snooper is open, right-click **File**, click **OpenFile**, find your log files, select a file in the **Open** dialog box, and then click **Open**.</span></span>

4.  <span data-ttu-id="1444f-139">I messaggi di **traccia** dei file di registro vengono visualizzati nella scheda **traccia** . Fare clic sulla scheda **messaggi** per visualizzare il contenuto del messaggio delle tracce raccolte.</span><span class="sxs-lookup"><span data-stu-id="1444f-139">The log file’s **Trace** messages are displayed on the **Trace** tab. Click the **Messages** tab to view the message contents of the collected traces.</span></span>

</div>

<div>

## <a name="to-display-a-call-flow-diagram"></a><span data-ttu-id="1444f-140">Per visualizzare un diagramma del flusso di chiamata</span><span class="sxs-lookup"><span data-stu-id="1444f-140">To display a call flow diagram</span></span>

1.  <span data-ttu-id="1444f-141">Per utilizzare Snooper e aprire i file di registro, è necessario l'accesso in lettura ai file di registro.</span><span class="sxs-lookup"><span data-stu-id="1444f-141">To use Snooper and open log files, you need read access to the log files.</span></span> <span data-ttu-id="1444f-142">Per utilizzare Snooper e accedere ai file di registro, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator (RBAC), oppure un ruolo RBAC personalizzato che contenga uno dei due gruppi.</span><span class="sxs-lookup"><span data-stu-id="1444f-142">To use Snooper and access the log files, you need to be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>

2.  <span data-ttu-id="1444f-143">Aprire un file di registro e fare clic sulla scheda **messaggi** , selezionare una conversazione nella visualizzazione messaggi oppure selezionare un componente di traccia nella scheda **traccia** .</span><span class="sxs-lookup"><span data-stu-id="1444f-143">Open a log file and click the **Messages** tab, select a conversation in the messages view or select a trace component on the **Trace** tab.</span></span>

3.  <span data-ttu-id="1444f-144">Fare clic su **flusso di chiamata**.</span><span class="sxs-lookup"><span data-stu-id="1444f-144">Click **Call Flow**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1444f-145">Se si fa clic su un messaggio o su una traccia che non fa parte di un flusso di chiamata, il diagramma non verrà visualizzato e viene visualizzato un messaggio di stato nella parte inferiore di Snooper che indica che "questo messaggio non è idoneo per callfow".</span><span class="sxs-lookup"><span data-stu-id="1444f-145">If you click on a message or trace that is not part of a call flow, the diagram will not appear and a status message appears at the bottom of Snooper stating “This message is not eligible for callfow”.</span></span> <span data-ttu-id="1444f-146">Scegliere un altro messaggio o traccia e il flusso di chiamata verrà visualizzato se il messaggio o la traccia è parte di un flusso di chiamata.</span><span class="sxs-lookup"><span data-stu-id="1444f-146">Choose another message or trace and the call flow will appear if the message or trace is part of a call flow.</span></span>

    
    </div>

4.  <span data-ttu-id="1444f-147">Spostarsi tra i messaggi o le righe di traccia e osservare se il diagramma di flusso delle chiamate viene aggiornato o modificato per visualizzare un nuovo diagramma.</span><span class="sxs-lookup"><span data-stu-id="1444f-147">Move through the Messages or the Trace lines and note whether the call flow diagram updates or changes to display a new diagram.</span></span>

5.  <span data-ttu-id="1444f-148">Posizionare il puntatore del mouse sugli elementi per ottenere informazioni sui messaggi di chiamata, gli endpoint e altri componenti.</span><span class="sxs-lookup"><span data-stu-id="1444f-148">Hover over elements to get information about call messages, endpoints, and other components.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


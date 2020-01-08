---
title: 'Lync Server 2013: leggere i registri di acquisizione dal servizio di registrazione centralizzato'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reading capture logs from the Centralized Logging Service
ms:assetid: c86ccf61-d86f-4ebd-b8d1-984a1b73005d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721879(v=OCS.15)
ms:contentKeyID: 49733813
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55bfeaa5bc9a2e89d8c52529c5d05ae7e3ee8feb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975144"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reading-capture-logs-from-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="1eec9-102">Lettura dei registri di acquisizione dal servizio di registrazione centralizzato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1eec9-102">Reading capture logs from the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1eec9-103">_**Argomento Ultima modifica:** 2016-12-28_</span><span class="sxs-lookup"><span data-stu-id="1eec9-103">_**Topic Last Modified:** 2016-12-28_</span></span>

<span data-ttu-id="1eec9-104">Dopo aver eseguito la ricerca, è possibile realizzare il vero vantaggio del servizio di registrazione centralizzato e si ha un file che può essere usato per rintracciare un problema segnalato.</span><span class="sxs-lookup"><span data-stu-id="1eec9-104">You realize the real benefit of the Centralized Logging Service after you run the search and you have a file that you can use to track down a reported problem.</span></span> <span data-ttu-id="1eec9-105">È possibile leggere il file in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="1eec9-105">There are a number of ways that you can read the file.</span></span> <span data-ttu-id="1eec9-106">Il file di output è in formato testo standard ed è possibile usare Notepad. exe o qualsiasi altra applicazione che consentirà di aprire e leggere un file di testo.</span><span class="sxs-lookup"><span data-stu-id="1eec9-106">The output file is in a standard text format and you can use Notepad.exe or any other programs that will allow you to open and read a text file.</span></span> <span data-ttu-id="1eec9-107">Per i file più grandi e i problemi più complessi, puoi usare uno strumento come Snooper. exe progettato per leggere e analizzare l'output di registrazione dal servizio di registrazione centralizzato.</span><span class="sxs-lookup"><span data-stu-id="1eec9-107">For larger files and more complex issues, you could use a tool like Snooper.exe that is designed to read and parse the logging output from the Centralized Logging Service.</span></span> <span data-ttu-id="1eec9-108">Snooper è incluso negli strumenti di debug di Lync Server 2013 disponibili come download separato.</span><span class="sxs-lookup"><span data-stu-id="1eec9-108">Snooper is included with the Lync Server 2013 Debug Tools that are available as a separate download.</span></span> <span data-ttu-id="1eec9-109">È possibile scaricare gli strumenti di debug di Lync Server 2013 [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257)qui:.</span><span class="sxs-lookup"><span data-stu-id="1eec9-109">You can download the Lync Server 2013 Debug Tools here: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257).</span></span> <span data-ttu-id="1eec9-110">Quando si installano gli strumenti di debug di Lync Server 2013, non vengono creati scorciatoie e voci di menu.</span><span class="sxs-lookup"><span data-stu-id="1eec9-110">When you install the Lync Server 2013 Debug Tools, short cuts and menu items are not created.</span></span> <span data-ttu-id="1eec9-111">Dopo aver installato gli strumenti di debug di Lync Server 2013, aprire Esplora risorse, una finestra della riga di comando o Lync Server Management Shell e accedere alla directory (posizione predefinita) C\\: programmi\\Microsoft Lync Server 2013\\strumenti di debug.</span><span class="sxs-lookup"><span data-stu-id="1eec9-111">After you install the Lync Server 2013 Debug Tools, open Windows Explorer, a command-line window, or Lync Server Management Shell and go to the directory (default location) C:\\Program Files\\Microsoft Lync Server 2013\\Debugging Tools.</span></span> <span data-ttu-id="1eec9-112">Fare doppio clic su Snooper. exe o digitare Snooper. exe, quindi premere INVIO se si usa la riga di comando o Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="1eec9-112">Double-click Snooper.exe or type Snooper.exe, and then press ENTER if you are using the command line or Lync Server Management Shell.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1eec9-113">Lo scopo di questo argomento non è dettagliare e discutere le tecniche di risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="1eec9-113">The intent of this topic is not to detail and discuss troubleshooting techniques.</span></span> <span data-ttu-id="1eec9-114">La risoluzione dei problemi e i processi che la circondano sono un argomento complesso.</span><span class="sxs-lookup"><span data-stu-id="1eec9-114">Troubleshooting and the processes around it is a complex subject.</span></span> <span data-ttu-id="1eec9-115">Per informazioni dettagliate sulla risoluzione dei problemi di base e sulla risoluzione dei problemi relativi ai carichi di lavoro specifici, vedere il <A href="http://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A>manuale del Resource Kit di Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1eec9-115">For details about troubleshooting basics and troubleshooting specific workloads, see the Microsoft Lync Server 2010 Resource Kit book at <A href="http://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A>.</span></span> <span data-ttu-id="1eec9-116">I processi e le procedure si applicano ancora a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1eec9-116">The processes and procedures still apply to Lync Server 2013.</span></span>



</div>

<span data-ttu-id="1eec9-117">Lync Server 2013 introduce una versione aggiornata di Snooper che include alcune nuove caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="1eec9-117">Lync Server 2013 introduces an updated version of Snooper that includes some new features.</span></span> <span data-ttu-id="1eec9-118">Lo screenshot seguente mostra la versione di Snooper da Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="1eec9-118">The following screen shot shows the version of Snooper from Office Communications Server 2007.</span></span>

<span data-ttu-id="1eec9-119">![Office Communications 2007 versione di Snooper.] (images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Office Communications 2007 versione di Snooper.")</span><span class="sxs-lookup"><span data-stu-id="1eec9-119">![Office Communications 2007 version of Snooper.](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Office Communications 2007 version of Snooper.")</span></span>

<span data-ttu-id="1eec9-120">Lo screenshot seguente mostra la nuova versione di Snooper inclusa negli strumenti di debug di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1eec9-120">The following screen shot shows the new version of Snooper included in the Lync Server 2013 Debug Tools.</span></span>

<span data-ttu-id="1eec9-121">![Versione di Snooper di Lync Server 2013.] (images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Versione di Snooper di Lync Server 2013.")</span><span class="sxs-lookup"><span data-stu-id="1eec9-121">![Lync Server 2013 version of Snooper.](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Lync Server 2013 version of Snooper.")</span></span>

<span data-ttu-id="1eec9-122">La schermata seguente mostra la barra degli strumenti con le funzioni usate di frequente.</span><span class="sxs-lookup"><span data-stu-id="1eec9-122">The following screen shot shows the toolbar with frequently used functions.</span></span>

<span data-ttu-id="1eec9-123">![Barra degli strumenti di snooper 2013.] (images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Barra degli strumenti di snooper 2013.")</span><span class="sxs-lookup"><span data-stu-id="1eec9-123">![Snooper 2013 toolbar.](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Snooper 2013 toolbar.")</span></span>

<span data-ttu-id="1eec9-124">La caratteristica più recente che aggiunge valore è la visualizzazione diagramma flusso (flusso delle chiamate).</span><span class="sxs-lookup"><span data-stu-id="1eec9-124">And, the newest feature that adds value is the Flow Chart (call flow) diagram view.</span></span> <span data-ttu-id="1eec9-125">Si seleziona un flusso di messaggi nella scheda **messaggio** e si fa clic sul pulsante **flusso di chiamata** .</span><span class="sxs-lookup"><span data-stu-id="1eec9-125">You select a message flow in the **Message** tab and click the **Call Flow** button.</span></span> <span data-ttu-id="1eec9-126">Quando si procede attraverso i messaggi, il diagramma di flusso delle chiamate viene aggiornato con i nuovi dati.</span><span class="sxs-lookup"><span data-stu-id="1eec9-126">As you proceed through the messages, the call flow diagram updates with new data.</span></span>

<span data-ttu-id="1eec9-127">![Diagramma di flusso delle chiamate di snooper 2013.] (images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Diagramma di flusso delle chiamate di snooper 2013.")</span><span class="sxs-lookup"><span data-stu-id="1eec9-127">![Snooper 2013 call flow diagram.](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Snooper 2013 call flow diagram.")</span></span>

<span data-ttu-id="1eec9-128">È possibile posizionare il puntatore del mouse sulla visualizzazione diagramma e ottenere informazioni dettagliate sui messaggi e il contenuto dei flussi e dei messaggi, nonché sugli elementi del server.</span><span class="sxs-lookup"><span data-stu-id="1eec9-128">You can hover over the diagram view and get details about the messages and content of the flows and messages as well as the server elements.</span></span> <span data-ttu-id="1eec9-129">Fare clic su una freccia del flusso di chiamata per passare al messaggio nella visualizzazione messaggi.</span><span class="sxs-lookup"><span data-stu-id="1eec9-129">Click on any call flow arrow to go to the message in the Messages view.</span></span>

<span data-ttu-id="1eec9-130">![Dettagli del messaggio del diagramma di flusso delle chiamate.] (images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "Dettagli del messaggio del diagramma di flusso delle chiamate.")</span><span class="sxs-lookup"><span data-stu-id="1eec9-130">![Call flow diagram message details.](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "Call flow diagram message details.")</span></span>

<div>

## <a name="to-open-a-log-file-in-snooper"></a><span data-ttu-id="1eec9-131">Per aprire un file di log in Snooper</span><span class="sxs-lookup"><span data-stu-id="1eec9-131">To open a log file in Snooper</span></span>

1.  <span data-ttu-id="1eec9-132">Per usare Snooper e aprire i file di log, è necessario l'accesso in lettura ai file di log.</span><span class="sxs-lookup"><span data-stu-id="1eec9-132">To use Snooper and open log files, you need read access to the log files.</span></span> <span data-ttu-id="1eec9-133">Per usare Snooper e accedere ai file di log, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator (RBAC) o di un ruolo RBAC personalizzato che contenga uno di questi due gruppi.</span><span class="sxs-lookup"><span data-stu-id="1eec9-133">To use Snooper and access the log files you must be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>

2.  <span data-ttu-id="1eec9-134">Dopo l'installazione degli strumenti di debug di Lync Server (LyncDebugTools. msi), cambiare directory nella posizione di Snooper. exe usando Esplora risorse o dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="1eec9-134">After the installation of the Lync Server Debugging Tools (LyncDebugTools.msi), change directory to the location of Snooper.exe using Windows Explorer or from the command line.</span></span> <span data-ttu-id="1eec9-135">Per impostazione predefinita, gli strumenti di debug si trovano in\\C:\\Program Files Microsoft Lync\\Server 2013 strumenti di debug.</span><span class="sxs-lookup"><span data-stu-id="1eec9-135">By default, the debugging tools are located in C:\\Program Files\\Microsoft Lync Server 2013\\Debugging Tools.</span></span> <span data-ttu-id="1eec9-136">Fare doppio clic su o eseguire Snooper. exe.</span><span class="sxs-lookup"><span data-stu-id="1eec9-136">Double-click or run Snooper.exe.</span></span>

3.  <span data-ttu-id="1eec9-137">Dopo aver aperto Snooper, fare clic con il pulsante destro del mouse su **file**, scegliere **OpenFile**, individuare i file di log, selezionare un file nella finestra di dialogo **Apri** e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="1eec9-137">After Snooper is open, right-click **File**, click **OpenFile**, find your log files, select a file in the **Open** dialog box, and then click **Open**.</span></span>

4.  <span data-ttu-id="1eec9-138">I messaggi di **traccia** del file di log vengono visualizzati nella scheda **traccia** . fare clic sulla scheda **messaggi** per visualizzare il contenuto del messaggio delle tracce raccolte.</span><span class="sxs-lookup"><span data-stu-id="1eec9-138">The log file’s **Trace** messages are displayed on the **Trace** tab. Click the **Messages** tab to view the message contents of the collected traces.</span></span>

</div>

<div>

## <a name="to-display-a-call-flow-diagram"></a><span data-ttu-id="1eec9-139">Per visualizzare un diagramma di flusso delle chiamate</span><span class="sxs-lookup"><span data-stu-id="1eec9-139">To display a call flow diagram</span></span>

1.  <span data-ttu-id="1eec9-140">Per usare Snooper e aprire i file di log, è necessario l'accesso in lettura ai file di log.</span><span class="sxs-lookup"><span data-stu-id="1eec9-140">To use Snooper and open log files, you need read access to the log files.</span></span> <span data-ttu-id="1eec9-141">Per usare Snooper e accedere ai file di log, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator (RBAC) o di un ruolo RBAC personalizzato che contenga uno di questi due gruppi.</span><span class="sxs-lookup"><span data-stu-id="1eec9-141">To use Snooper and access the log files, you need to be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>

2.  <span data-ttu-id="1eec9-142">Aprire un file di log e fare clic sulla scheda **messaggi** , selezionare una conversazione nella visualizzazione messaggi o selezionare un componente di traccia nella scheda **traccia** .</span><span class="sxs-lookup"><span data-stu-id="1eec9-142">Open a log file and click the **Messages** tab, select a conversation in the messages view or select a trace component on the **Trace** tab.</span></span>

3.  <span data-ttu-id="1eec9-143">Fare clic su **flusso di chiamata**.</span><span class="sxs-lookup"><span data-stu-id="1eec9-143">Click **Call Flow**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1eec9-144">Se si fa clic su un messaggio o una traccia che non fa parte di un flusso di chiamata, il diagramma non verrà visualizzato e viene visualizzato un messaggio di stato nella parte inferiore di Snooper che indica che "questo messaggio non è idoneo per callfow".</span><span class="sxs-lookup"><span data-stu-id="1eec9-144">If you click on a message or trace that is not part of a call flow, the diagram will not appear and a status message appears at the bottom of Snooper stating “This message is not eligible for callfow”.</span></span> <span data-ttu-id="1eec9-145">Scegliere un altro messaggio o traccia e il flusso di chiamata viene visualizzato se il messaggio o la traccia fa parte di un flusso di chiamata.</span><span class="sxs-lookup"><span data-stu-id="1eec9-145">Choose another message or trace and the call flow will appear if the message or trace is part of a call flow.</span></span>

    
    </div>

4.  <span data-ttu-id="1eec9-146">Spostarsi tra i messaggi o le linee di traccia e notare se il diagramma di flusso delle chiamate viene aggiornato o modificato per visualizzare un nuovo diagramma.</span><span class="sxs-lookup"><span data-stu-id="1eec9-146">Move through the Messages or the Trace lines and note whether the call flow diagram updates or changes to display a new diagram.</span></span>

5.  <span data-ttu-id="1eec9-147">Posizionare il puntatore del mouse sugli elementi per ottenere informazioni su messaggi di chiamata, endpoint e altri componenti.</span><span class="sxs-lookup"><span data-stu-id="1eec9-147">Hover over elements to get information about call messages, endpoints, and other components.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


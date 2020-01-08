---
title: 'Lync Server 2013: visualizzare i report di Best Practices Analyzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing reports from Best Practices Analyzer
ms:assetid: 7217a47b-36b1-4923-81ea-df754cff29bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg607690(v=OCS.15)
ms:contentKeyID: 48184465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb2c229d683ecd0dcf4fee94b456514527226152
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978012"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-reports-from-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="9601e-102">Visualizzazione dei report di Best Practices Analyzer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9601e-102">Viewing reports from Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9601e-103">_**Argomento Ultima modifica:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="9601e-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="9601e-104">Quando si usa Best Practices Analyzer per analizzare l'ambiente, è necessario specificare un nome per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="9601e-104">When you use Best Practices Analyzer to scan your environment, you specify a name for the scan.</span></span> <span data-ttu-id="9601e-105">Dopo che Best Practices Analyzer completa una scansione, archivia i risultati della scansione nei report e li salva sotto il nome della scansione.</span><span class="sxs-lookup"><span data-stu-id="9601e-105">After Best Practices Analyzer completes a scan, it stores the scan results in reports and saves them under the name of the scan.</span></span> <span data-ttu-id="9601e-106">Al termine della scansione, è possibile visualizzare i report generati per tale analisi facendo clic su **Visualizza un report di questa analisi delle procedure consigliate** direttamente dalla pagina di **analisi completata** .</span><span class="sxs-lookup"><span data-stu-id="9601e-106">Upon completion of the scan, you can view the reports generated for that scan by clicking **View a report of this Best Practices scan** directly from the **Scanning Completed** page.</span></span> <span data-ttu-id="9601e-107">È anche possibile visualizzare i report da tale analisi o scansioni precedenti in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="9601e-107">You can also view the reports from that scan or previous scans at a later time.</span></span> <span data-ttu-id="9601e-108">È possibile visualizzare i report nel computer locale in cui è stata eseguita l'analisi, importare i risultati dell'analisi da un altro computer oppure esportare i risultati della scansione per visualizzare i report in un altro computer in cui è installato Best Practices Analyzer.</span><span class="sxs-lookup"><span data-stu-id="9601e-108">You can view reports on the local computer on which the scan was run, import scan results from another computer, or export scan results to view the reports on another computer on which Best Practices Analyzer is installed.</span></span>

<span data-ttu-id="9601e-109">I risultati della scansione vengono presentati nei tipi di report seguenti:</span><span class="sxs-lookup"><span data-stu-id="9601e-109">Scan results are presented in the following types of reports:</span></span>

  - <span data-ttu-id="9601e-110">Report elenco</span><span class="sxs-lookup"><span data-stu-id="9601e-110">List reports</span></span>

  - <span data-ttu-id="9601e-111">Report albero</span><span class="sxs-lookup"><span data-stu-id="9601e-111">Tree reports</span></span>

  - <span data-ttu-id="9601e-112">Altri report</span><span class="sxs-lookup"><span data-stu-id="9601e-112">Other reports</span></span>

<span data-ttu-id="9601e-113">Questi report includono errori, avvisi e altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="9601e-113">These reports include errors, warnings, and other information.</span></span> <span data-ttu-id="9601e-114">Per informazioni dettagliate su ognuno di questi tipi di report e problemi, vedere [informazioni sui report creati da Best Practices Analyzer in Lync Server 2013](lync-server-2013-understanding-reports-created-by-best-practices-analyzer.md).</span><span class="sxs-lookup"><span data-stu-id="9601e-114">For details about each of these types of reports and issues, see [Understanding reports created by Best Practices Analyzer in Lync Server 2013](lync-server-2013-understanding-reports-created-by-best-practices-analyzer.md).</span></span>

<span data-ttu-id="9601e-115">Usare la procedura seguente per visualizzare i risultati di analisi generati in precedenza dall'analizzatore delle procedure consigliate.</span><span class="sxs-lookup"><span data-stu-id="9601e-115">Use the following procedure to view scan results previously generated by Best Practices Analyzer.</span></span>

<div>

## <a name="to-view-reports-from-a-previous-scan"></a><span data-ttu-id="9601e-116">Per visualizzare i report da una scansione precedente</span><span class="sxs-lookup"><span data-stu-id="9601e-116">To view reports from a previous scan</span></span>

1.  <span data-ttu-id="9601e-117">Accedere a un computer in cui è installato Best Practices Analyzer usando un account che fa parte dell'account utente locale.</span><span class="sxs-lookup"><span data-stu-id="9601e-117">Log on to a computer on which Best Practices Analyzer is installed using an account that is a member of the local User account.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="9601e-118">È possibile visualizzare i risultati di un'analisi usando un account che è un membro del gruppo Administrators locale, ma non è possibile eseguire un'analisi a meno che non si disponga di autorizzazioni e diritti utente appropriati.</span><span class="sxs-lookup"><span data-stu-id="9601e-118">You can view the results of a scan using an account that is a member of the local Administrators group, but you cannot run a scan unless you have appropriate user rights and permissions.</span></span> <span data-ttu-id="9601e-119">Per informazioni dettagliate, vedere <A href="lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md">appartenenze ai gruppi e requisiti per i diritti utente per Best Practices Analyzer in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9601e-119">For details, see <A href="lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md">Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013</A>.</span></span>

2.  <span data-ttu-id="9601e-120">Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Best Practices Analyzer**.</span><span class="sxs-lookup"><span data-stu-id="9601e-120">Click **Start**, point to **All Programs**, click **Microsoft Lync Server 2013**, and then click **Best Practices Analyzer**.</span></span>

3.  <span data-ttu-id="9601e-121">Nella schermata **iniziale** fare clic su **Seleziona i risultati della scansione da visualizzare**.</span><span class="sxs-lookup"><span data-stu-id="9601e-121">On the **Welcome** screen, click **Select the scan results to view**.</span></span>

4.  <span data-ttu-id="9601e-122">Nella pagina **selezionare una procedura consigliata per la visualizzazione** , eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9601e-122">On the **Select a Best Practices Scan to View** page, do one of the following:</span></span>
    
      - <span data-ttu-id="9601e-123">Per visualizzare i report dall'elenco dei risultati di analisi archiviati localmente, fare clic sul nome della scansione e quindi fare clic su **Visualizza un report di questa analisi**.</span><span class="sxs-lookup"><span data-stu-id="9601e-123">To view reports from the list of locally stored scan results, click the name of scan, and then click **View a report of this scan**.</span></span>
        
        > [!NOTE]  
        > <span data-ttu-id="9601e-124">L'Analizzatore procedure consigliate crea l'elenco dei file locali dalla &lt;cartella&gt;\\systemDrive Documents\\&lt;and&gt;Settings user \Dati Data\Microsoft\RtcBPA.</span><span class="sxs-lookup"><span data-stu-id="9601e-124">The Best Practices Analyzer creates the list of local files from the folder &lt;systemDrive&gt;\\Documents and Settings\\&lt;user&gt;\Application Data\Microsoft\RtcBPA.</span></span>
    
      - <span data-ttu-id="9601e-125">Per visualizzare i report per i risultati di un'analisi archiviata in un'altra posizione, fare clic su **Importa analisi**, individuare il file contenente i risultati della scansione e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="9601e-125">To view reports for results of a scan that are stored at another location, click **Import scan**, locate the file containing the scan results, and then click **Open**.</span></span>
        
        > [!NOTE]  
        > <span data-ttu-id="9601e-126">Se la versione di Best Practices Analyzer in questo computer non corrisponde alla versione usata per raccogliere i dati nel file importato, lo strumento nel computer potrebbe analizzare di nuovo il file dopo l'importazione.</span><span class="sxs-lookup"><span data-stu-id="9601e-126">If the version of Best Practices Analyzer on this computer does not match the version that was used to collect the data in the imported file, the tool on your computer might analyze the file again, after it is imported.</span></span>

5.  <span data-ttu-id="9601e-127">Nella pagina **Visualizza report procedure consigliate** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9601e-127">On the **View Best Practices Report** page, do one of the following:</span></span>
    
      - <span data-ttu-id="9601e-128">Per visualizzare i report in un elenco organizzato dal componente server, fare clic su **rapporti elenco**e quindi fare clic sulla scheda **tutti i problemi** o sulla scheda **elementi informativi** .</span><span class="sxs-lookup"><span data-stu-id="9601e-128">To view reports in a list organized by server component, click **List Reports**, and then click either the **All Issues** tab or the **Informational Items** tab.</span></span>
    
      - <span data-ttu-id="9601e-129">Per visualizzare i report come elenco gerarchico organizzato in base a tipi di risultati, fare clic su **report albero**e quindi fare clic sulla scheda **visualizzazione dettagliata** o sulla scheda **visualizzazione Riepilogo** .</span><span class="sxs-lookup"><span data-stu-id="9601e-129">To view reports as a hierarchical list organized by types of results, click **Tree Reports**, and then click either the **Detailed View** tab or the **Summary View** tab.</span></span>
    
      - <span data-ttu-id="9601e-130">Per visualizzare altri report, fare clic su **altri report**.</span><span class="sxs-lookup"><span data-stu-id="9601e-130">To view other reports, click **Other Reports**.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="9601e-131">Per informazioni dettagliate sui report di analizzatore delle procedure consigliate e sui problemi che identificano, vedere <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">visualizzazione e utilizzo dei report creati da Best Practices Analyzer in Lync server 2013</A> e <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">analisi e risoluzione dei problemi identificati dall'analizzatore delle procedure consigliate in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9601e-131">For details about the Best Practices Analyzer reports and the issues that they identify, see <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Viewing and working with reports created by Best Practices Analyzer in Lync Server 2013</A> and <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">Analyzing and resolving issues identified by Best Practices Analyzer in Lync Server 2013</A>.</span></span>

</div>

</div>

</div>

</div>

</div>


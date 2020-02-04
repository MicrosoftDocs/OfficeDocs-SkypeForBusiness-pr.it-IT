---
title: Uso di Best Practices Analyzer per analizzare la distribuzione per potenziali problemi
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Best Practices Analyzer to scan your deployment for potential issues
ms:assetid: 09c84509-dc91-4e7b-882b-3c467b6b026d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591343(v=OCS.15)
ms:contentKeyID: 48183359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f787268301570d4440240289c19fdd1e266a607
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744206"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-best-practices-analyzer-to-scan-your-lync-server-2013-deployment-for-potential-issues"></a><span data-ttu-id="7c192-102">Uso di Best Practices Analyzer per analizzare la distribuzione di Lync Server 2013 per potenziali problemi</span><span class="sxs-lookup"><span data-stu-id="7c192-102">Using Best Practices Analyzer to scan your Lync Server 2013 deployment for potential issues</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c192-103">_**Argomento Ultima modifica:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="7c192-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="7c192-104">Per eseguire un'analisi di Best Practices Analyzer, è necessario specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="7c192-104">To run a Best Practices Analyzer scan, you must specify the following:</span></span>

  - <span data-ttu-id="7c192-105">**Credenziali**   per eseguire un'analisi, è necessario accedere a un computer in cui è installato Best Practices Analyzer utilizzando un account membro del gruppo Administrators locale.</span><span class="sxs-lookup"><span data-stu-id="7c192-105">**Credentials**   To run a scan, you must log on to a computer on which Best Practices Analyzer is installed by using an account that is a member of the local Administrators group.</span></span> <span data-ttu-id="7c192-106">Inoltre, è necessario accedere con un account utente che disponga dei diritti utente e delle autorizzazioni necessarie per eseguire le analisi appropriate oppure specificare le credenziali con i diritti utente e le autorizzazioni appropriate quando si esegue Best Practices Analyzer.</span><span class="sxs-lookup"><span data-stu-id="7c192-106">Additionally, you need to log on by using a user account that has the user rights and permissions required to run the appropriate scans, or you must specify credentials that have the appropriate user rights and permissions when you run Best Practices Analyzer.</span></span> <span data-ttu-id="7c192-107">Per informazioni dettagliate, vedere [appartenenze ai gruppi e requisiti per i diritti utente per Best Practices Analyzer in Lync Server 2013](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md).</span><span class="sxs-lookup"><span data-stu-id="7c192-107">For details, see [Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md).</span></span>

  - <span data-ttu-id="7c192-108">**Ambito della scansione**   per specificare l'ambito della scansione, selezionare le categorie e i server che si desidera analizzare.</span><span class="sxs-lookup"><span data-stu-id="7c192-108">**Scope of scan**   To specify the scope of the scan, select the categories and servers that you want to scan.</span></span> <span data-ttu-id="7c192-109">È possibile selezionare tutte le categorie, una o più categorie o uno o più server all'interno di una specifica categoria nell'ambiente Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7c192-109">You can select all categories, one or more categories, or one or more servers within a specific category in your Lync Server environment.</span></span>

  - <span data-ttu-id="7c192-110">**Tipo di analisi**   attualmente, l'analisi dell'integrità è l'unico tipo di analisi disponibile (selezionato per impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="7c192-110">**Type of scan**   Currently, the Health Check scan is the only type of scan available (selected by default).</span></span> <span data-ttu-id="7c192-111">L'analisi dell'integrità consente di generare un report che include errori, avvisi e altre informazioni per tutti i server specificati nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="7c192-111">The Health Check scan generates a report that includes errors, warnings, and other information for all servers specified in the scope.</span></span>

  - <span data-ttu-id="7c192-112">\*\*\*\* Le opzioni di velocità della rete di velocità della rete includono la LAN veloce (100 Mbps o più), la LAN (10 Mbps), la WAN veloce (1,5 Mbps) o WAN (64 Kbps).   </span><span class="sxs-lookup"><span data-stu-id="7c192-112">**Network speed**   Network speed options include Fast LAN (100 Mbps or more), LAN (10 Mbps), Fast WAN (1.5 Mbps), or WAN (64 kbps).</span></span> <span data-ttu-id="7c192-113">Il tempo stimato per completare l'analisi si basa su questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="7c192-113">The estimated time to complete the scan is based on this setting.</span></span> <span data-ttu-id="7c192-114">Questa impostazione viene usata anche per impostare il periodo di timeout.</span><span class="sxs-lookup"><span data-stu-id="7c192-114">This setting is also used to set the time-out period.</span></span> <span data-ttu-id="7c192-115">Durante l'analisi, l'analizzatore delle procedure consigliate attende una risposta da un server per un determinato periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="7c192-115">During the scan, the Best Practices Analyzer waits for a response from a server for a specified time.</span></span> <span data-ttu-id="7c192-116">Se non riceve una risposta entro il periodo di timeout specificato, si sposta sul server successivo nell'analisi.</span><span class="sxs-lookup"><span data-stu-id="7c192-116">If it does not receive a response within the specified time-out period, it moves to the next server in the scan.</span></span> <span data-ttu-id="7c192-117">Nelle reti più lente, il periodo di timeout specificato è più lungo per tenere conto delle latenze di rete più lunghe.</span><span class="sxs-lookup"><span data-stu-id="7c192-117">On slower networks, this specified time-out period is longer to account for longer network latencies.</span></span> <span data-ttu-id="7c192-118">Ti consigliamo di selezionare il collegamento più lento nella topologia per questo parametro in modo che lo strumento non si esprima troppo rapidamente.</span><span class="sxs-lookup"><span data-stu-id="7c192-118">We recommend that you select the slowest link in your topology for this parameter so that the tool does not time out too quickly.</span></span>

<div>

## <a name="to-scan-your-lync-server-2013-deployment"></a><span data-ttu-id="7c192-119">Per analizzare la distribuzione di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c192-119">To scan your Lync Server 2013 deployment</span></span>

1.  <span data-ttu-id="7c192-120">Accedere a un computer in cui è installato Best Practices Analyzer utilizzando un account membro del gruppo Administrators locale e che disponga di altri diritti utente e autorizzazioni necessari.</span><span class="sxs-lookup"><span data-stu-id="7c192-120">Log on to a computer on which Best Practices Analyzer is installed by using an account that is a member of the local Administrators group, and has other required user rights and permissions.</span></span>

2.  <span data-ttu-id="7c192-121">Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Best Practices Analyzer**.</span><span class="sxs-lookup"><span data-stu-id="7c192-121">Click **Start**, point to **All Programs**, click **Microsoft Lync Server 2013**, and then click **Best Practices Analyzer**.</span></span>

3.  <span data-ttu-id="7c192-122">Nella schermata **iniziale** fare clic su **Seleziona opzioni per una nuova analisi**.</span><span class="sxs-lookup"><span data-stu-id="7c192-122">On the **Welcome** screen, click **Select options for a new scan**.</span></span>

4.  <span data-ttu-id="7c192-123">Nella pagina **Connetti a Active Directory** verificare il nome specificato in **Active Directory Server**e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7c192-123">On the **Connect to Active Directory** page, verify the name specified in **Active Directory Server**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="7c192-124">Per eseguire un'analisi usando le credenziali usate per accedere al computer, fare clic su **Connetti al server Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="7c192-124">To run a scan using the credentials that you used to log on to the computer, click **Connect to the Active Directory server**.</span></span>
    
      - <span data-ttu-id="7c192-125">Per specificare credenziali diverse che si desidera utilizzare per servizi di dominio Active Directory, Edge Server o Exchange Server, fare clic su **Mostra opzioni di accesso avanzate**, selezionare ogni casella di controllo per cui sono necessarie credenziali separate, specificare le credenziali per ogni casella di controllo selezionata e quindi fare clic su **Connetti al server di Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="7c192-125">To specify different credentials that you want to use for Active Directory Domain Services, Edge Server, or Exchange Server, click **Show advanced logon options**, select each check box for which separate credentials are required, specify the credentials for each selected check box, and then click **Connect to the Active Directory server**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="7c192-126">Prima di iniziare la scansione, Best Practices Analyzer esegue un controllo della rete e delle autorizzazioni per verificare che le credenziali dell'account specificato siano valide e che Best Practices Analyzer possa connettersi a servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7c192-126">Before beginning the scan, Best Practices Analyzer performs a network and permissions check to ensure that the specified account credentials are valid and that Best Practices Analyzer can connect to Active Directory Domain Services.</span></span> <span data-ttu-id="7c192-127">Se lo strumento è in uso in un server del gruppo di lavoro, lo strumento verifica anche che possa connettersi a Edge Server nella rete perimetrale (ovvero, se sono inclusi nella scansione).</span><span class="sxs-lookup"><span data-stu-id="7c192-127">If the tool is running on a workgroup server, the tool also verifies that it can connect to Edge Servers in the perimeter network (that is, if they are included in the scan).</span></span>

    
    </div>

5.  <span data-ttu-id="7c192-128">Nella pagina **Avvia una nuova analisi delle procedure consigliate** selezionare le opzioni che si desidera includere nella scansione, specificare la velocità di rete e quindi fare clic su **Avvia analisi**.</span><span class="sxs-lookup"><span data-stu-id="7c192-128">On the **Start a new Best Practices scan** page, select the options that you want to include in the scan, specify the network speed, and then click **Start scanning**.</span></span>

6.  <span data-ttu-id="7c192-129">Nella pagina **analisi completata** fare clic su **Visualizza un report di questa analisi delle procedure consigliate**.</span><span class="sxs-lookup"><span data-stu-id="7c192-129">On the **Scanning Completed** page, click **View a report of this Best Practices scan**.</span></span>

7.  <span data-ttu-id="7c192-130">Nella pagina **Visualizza report procedure consigliate** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7c192-130">On the **View Best Practices Report** page, do one of the following:</span></span>
    
      - <span data-ttu-id="7c192-131">Per visualizzare i report in un elenco organizzato dal componente server, fare clic su **rapporti elenco**e quindi fare clic sulla scheda **tutti i problemi** o sulla scheda **elementi informativi** .</span><span class="sxs-lookup"><span data-stu-id="7c192-131">To view reports in a list organized by server component, click **List Reports**, and then click either the **All Issues** tab or the **Informational Items** tab.</span></span>
    
      - <span data-ttu-id="7c192-132">Per visualizzare i report come elenco gerarchico organizzato in base a tipi di risultati, fare clic su **report albero**e quindi fare clic sulla scheda **visualizzazione dettagliata** o sulla scheda **visualizzazione Riepilogo** .</span><span class="sxs-lookup"><span data-stu-id="7c192-132">To view reports as a hierarchical list organized by types of results, click **Tree Reports**, and then click either the **Detailed View** tab or the **Summary View** tab.</span></span>
    
      - <span data-ttu-id="7c192-133">Per visualizzare altri report, fare clic su **altri report**.</span><span class="sxs-lookup"><span data-stu-id="7c192-133">To view other reports, click **Other Reports**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="7c192-134">Per informazioni dettagliate sui report di analizzatore delle procedure consigliate e sui problemi che identificano, vedere <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">visualizzazione e utilizzo dei report creati da Best Practices Analyzer in Lync server 2013</A> e <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">analisi e risoluzione dei problemi identificati dall'analizzatore delle procedure consigliate in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7c192-134">For details about the Best Practices Analyzer reports and the issues they identify, see <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Viewing and working with reports created by Best Practices Analyzer in Lync Server 2013</A> and <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">Analyzing and resolving issues identified by Best Practices Analyzer in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


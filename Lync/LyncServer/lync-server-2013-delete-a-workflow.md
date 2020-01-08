---
title: 'Lync Server 2013: eliminare un flusso di lavoro'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete a workflow
ms:assetid: 0469a6b8-ce1e-459b-bc3d-4c8adf2d97d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520944(v=OCS.15)
ms:contentKeyID: 48183274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1aabb1b46d3f67408d586bada6db3d1efaf0538e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-workflow-in-lync-server-2013"></a><span data-ttu-id="527d9-102">Eliminare un flusso di lavoro in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="527d9-102">Delete a workflow in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="527d9-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="527d9-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="527d9-104">Per eliminare un flusso di lavoro, usare una delle procedure seguenti.</span><span class="sxs-lookup"><span data-stu-id="527d9-104">Use one of the following procedures to delete a workflow.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-delete-a-workflow"></a><span data-ttu-id="527d9-105">Per usare il pannello di controllo di Lync Server eliminare un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="527d9-105">To use Lync Server Control Panel delete a workflow</span></span>

1.  <span data-ttu-id="527d9-106">Accedere come membro del gruppo RTCUniversalServerAdmins o come membro di uno dei ruoli amministrativi predefiniti che supportano il gruppo di risposte.</span><span class="sxs-lookup"><span data-stu-id="527d9-106">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="527d9-107">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="527d9-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="527d9-108">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="527d9-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="527d9-109">Nella barra di spostamento sinistra fare clic su **gruppi di risposte**e quindi su flusso di **lavoro**.</span><span class="sxs-lookup"><span data-stu-id="527d9-109">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="527d9-110">Nella pagina **flusso di lavoro** fare clic su **Crea o modifica flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="527d9-110">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="527d9-111">Nel campo **selezionare un servizio** di ricerca digitare parte o tutto il nome del servizio **ApplicationServer** che ospita il flusso di lavoro che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="527d9-111">In the **Select a Service** search field, type part or all of the name of the **ApplicationServer** service that hosts the workflow that you want to delete.</span></span>

6.  <span data-ttu-id="527d9-112">Nell'elenco dei servizi fare clic sul servizio desiderato e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="527d9-112">In the list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="527d9-113">Verrà visualizzata la pagina web strumento di configurazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="527d9-113">The Response Group Configuration Tool webpage opens.</span></span> <span data-ttu-id="527d9-114">È anche possibile aprire la pagina web strumento di configurazione di Response Group direttamente da un browser tramite la <STRONG>connessione&lt;a&gt;https://webPoolFqdn/rgsconfig</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="527d9-114">You can also open the Response Group Configuration Tool webpage directly from a web browser by connecting to <STRONG>https://&lt;webPoolFqdn&gt;/RgsConfig</STRONG>.</span></span>

    
    </div>

7.  <span data-ttu-id="527d9-115">In **Gestisci un flusso di lavoro esistente**individuare il flusso di lavoro che si vuole eliminare e quindi in **azione**fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="527d9-115">Under **Manage an Existing Workflow**, locate the workflow you want to delete, and then under **Action**, click **Delete**.</span></span>

8.  <span data-ttu-id="527d9-116">Fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="527d9-116">Click **Yes**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-workflow"></a><span data-ttu-id="527d9-117">Per usare Windows PowerShell per eliminare un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="527d9-117">To use Windows PowerShell to delete a workflow</span></span>

1.  <span data-ttu-id="527d9-118">Accedere come membro del gruppo RTCUniversalServerAdmins o come membro di uno dei ruoli amministrativi predefiniti che supportano il gruppo di risposte.</span><span class="sxs-lookup"><span data-stu-id="527d9-118">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="527d9-119">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="527d9-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="527d9-120">Nella riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="527d9-120">At the command line, run:</span></span>
    
        Get-CsRgsWorkflow -Identity <Application Server service> -Name "<name of workflow>" | Remove-CsRgsWorkflow
    
    <span data-ttu-id="527d9-121">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="527d9-121">For example:</span></span>
    
        Get-CsRgsWorkflow -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsWorkflow

</div>

</div>

<span> </span>

</div>

</div>

</div>


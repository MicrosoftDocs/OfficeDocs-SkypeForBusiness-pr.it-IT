---
title: 'Lync Server 2013: eliminare un flusso di lavoro'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a workflow
ms:assetid: 0469a6b8-ce1e-459b-bc3d-4c8adf2d97d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520944(v=OCS.15)
ms:contentKeyID: 48183274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1f3265591b1beb7180864b8e3a613989dfca397
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213992"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-a-workflow-in-lync-server-2013"></a><span data-ttu-id="e4657-102">Eliminare un flusso di lavoro in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4657-102">Delete a workflow in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4657-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e4657-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e4657-104">Utilizzare una delle procedure seguenti per eliminare un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e4657-104">Use one of the following procedures to delete a workflow.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-delete-a-workflow"></a><span data-ttu-id="e4657-105">Per utilizzare il pannello di controllo di Lync Server eliminare un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="e4657-105">To use Lync Server Control Panel delete a workflow</span></span>

1.  <span data-ttu-id="e4657-106">Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.</span><span class="sxs-lookup"><span data-stu-id="e4657-106">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="e4657-107">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e4657-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e4657-108">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e4657-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e4657-109">Sulla barra di spostamento sinistra fare clic su **Response Group** e quindi su **Flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="e4657-109">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="e4657-110">Nella pagina **Flusso di lavoro** fare clic su **Crea o modifica un flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="e4657-110">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="e4657-111">Nel campo di ricerca **Seleziona un servizio** digitare parte o tutto il nome del servizio **ApplicationServer** in cui è ospitato il flusso di lavoro che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="e4657-111">In the **Select a Service** search field, type part or all of the name of the **ApplicationServer** service that hosts the workflow that you want to delete.</span></span>

6.  <span data-ttu-id="e4657-112">Nell'elenco dei servizi fare clic sul servizio desiderato, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e4657-112">In the list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e4657-113">Verrà visualizzata la pagina Web dello strumento di configurazione di Response Group.</span><span class="sxs-lookup"><span data-stu-id="e4657-113">The Response Group Configuration Tool webpage opens.</span></span> <span data-ttu-id="e4657-114">È inoltre possibile aprire la pagina Web dello strumento di configurazione di Response Group direttamente da un browser tramite la connessione a <STRONG>&lt;https://FQDNpoolWeb&gt;/rgsconfig</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="e4657-114">You can also open the Response Group Configuration Tool webpage directly from a web browser by connecting to <STRONG>https://&lt;webPoolFqdn&gt;/RgsConfig</STRONG>.</span></span>

    
    </div>

7.  <span data-ttu-id="e4657-115">In **Gestisci un flusso di lavoro esistente** individuare il flusso di lavoro da eliminare e quindi in **Azione** fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="e4657-115">Under **Manage an Existing Workflow**, locate the workflow you want to delete, and then under **Action**, click **Delete**.</span></span>

8.  <span data-ttu-id="e4657-116">Fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="e4657-116">Click **Yes**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-workflow"></a><span data-ttu-id="e4657-117">Per utilizzare Windows PowerShell per eliminare un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="e4657-117">To use Windows PowerShell to delete a workflow</span></span>

1.  <span data-ttu-id="e4657-118">Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.</span><span class="sxs-lookup"><span data-stu-id="e4657-118">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="e4657-119">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e4657-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e4657-120">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e4657-120">At the command line, run:</span></span>
    
        Get-CsRgsWorkflow -Identity <Application Server service> -Name "<name of workflow>" | Remove-CsRgsWorkflow
    
    <span data-ttu-id="e4657-121">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e4657-121">For example:</span></span>
    
        Get-CsRgsWorkflow -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsWorkflow

</div>

</div>

<span> </span>

</div>

</div>

</div>


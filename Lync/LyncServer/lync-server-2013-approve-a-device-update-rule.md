---
title: 'Lync Server 2013: approvazione di una regola di aggiornamento del dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Approve a Device Update rule
ms:assetid: 9dbb1c9a-be0f-4e13-9234-05501ab43ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994053(v=OCS.15)
ms:contentKeyID: 51803964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25c6fad9547e9c738523ac0f460d3e6696d1920a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204427"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="approve-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="e7a7d-102">Approvazione di una regola di aggiornamento del dispositivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7a7d-102">Approve a Device Update rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7a7d-103">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="e7a7d-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="e7a7d-104">Dopo aver importato una regola di aggiornamento dei dispositivi, questa viene installata nei dispositivi di test.</span><span class="sxs-lookup"><span data-stu-id="e7a7d-104">After you import a device update rule, it’s installed on your test devices.</span></span> <span data-ttu-id="e7a7d-105">Se il testing ha esito positivo e si desidera eseguire l'aggiornamento all'organizzazione, approvarlo utilizzando il pannello di controllo di Lync Server o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e7a7d-105">If your testing is successful, and you want to roll out the update to your organization, approve it by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>

## <a name="to-approve-a-device-update-rule-by-using-lync-server-control-panel"></a><span data-ttu-id="e7a7d-106">Per approvare una regola di aggiornamento dei dispositivi tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="e7a7d-106">To approve a device update rule by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="e7a7d-107">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="e7a7d-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e7a7d-108">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e7a7d-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e7a7d-109">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e7a7d-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e7a7d-110">Nella pagina **aggiornamento dispositivi** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e7a7d-110">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="e7a7d-111">Per approvare una regola, selezionare la regola.</span><span class="sxs-lookup"><span data-stu-id="e7a7d-111">To approve one rule, select that rule.</span></span>
    
      - <span data-ttu-id="e7a7d-112">Per approvare tutte le regole, fare clic su **modifica**e quindi su **Seleziona tutto**.</span><span class="sxs-lookup"><span data-stu-id="e7a7d-112">To approve all rules, click **Edit**, and then click **Select All**.</span></span>

4.  <span data-ttu-id="e7a7d-113">Fare clic su **azione**e quindi su **approva**.</span><span class="sxs-lookup"><span data-stu-id="e7a7d-113">Click **Action**, and then click **Approve**.</span></span>

</div>

<div>

## <a name="approving-a-device-update-rule-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e7a7d-114">Approvazione di una regola di aggiornamento dei dispositivi tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e7a7d-114">Approving a Device Update Rule by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e7a7d-115">È inoltre possibile approvare le regole di aggiornamento dei dispositivi utilizzando Windows PowerShell e il cmdlet **approva-CsDeviceUpdateRule** .</span><span class="sxs-lookup"><span data-stu-id="e7a7d-115">Device update rules can also be approved by using Windows PowerShell and the **Approve-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="e7a7d-116">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e7a7d-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e7a7d-117">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="e7a7d-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-approve-a-single-device-update-rule"></a><span data-ttu-id="e7a7d-118">Per approvare una regola di aggiornamento di un singolo dispositivo</span><span class="sxs-lookup"><span data-stu-id="e7a7d-118">To approve a single device update rule</span></span>

  - <span data-ttu-id="e7a7d-119">Il comando seguente approva la regola di aggiornamento dei dispositivi d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 trovata nel server Web atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="e7a7d-119">The following command approves the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 found on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Approve-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9

</div>

<div>

## <a name="to-approve-multiple-device-update-rules"></a><span data-ttu-id="e7a7d-120">Per approvare le regole per l'aggiornamento di più dispositivi</span><span class="sxs-lookup"><span data-stu-id="e7a7d-120">To approve multiple device update rules</span></span>

  - <span data-ttu-id="e7a7d-121">Questo comando approva tutte le regole di aggiornamento del dispositivo per i dispositivi con marchio Microsoft:</span><span class="sxs-lookup"><span data-stu-id="e7a7d-121">This command approves all the device update rules for Microsoft-branded devices:</span></span>
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Approve-CsDeviceUpdateRule

</div>

<span data-ttu-id="e7a7d-122">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Approval-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Approve-CsDeviceUpdateRule) .</span><span class="sxs-lookup"><span data-stu-id="e7a7d-122">For details, see the Help topic for the [Approve-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Approve-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e7a7d-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7a7d-123">See Also</span></span>


[<span data-ttu-id="e7a7d-124">Importare le regole di aggiornamento del dispositivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7a7d-124">Import Device Update rules in Lync Server 2013</span></span>](lync-server-2013-import-device-update-rules.md)  
[<span data-ttu-id="e7a7d-125">Ripristinare una regola di aggiornamento del dispositivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7a7d-125">Restore a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-restore-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


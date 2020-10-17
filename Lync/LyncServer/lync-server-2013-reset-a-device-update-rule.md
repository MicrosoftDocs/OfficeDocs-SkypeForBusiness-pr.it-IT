---
title: 'Lync Server 2013: reimpostare una regola di aggiornamento del dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reset a Device Update rule
ms:assetid: d1f597e7-dffd-4756-af07-10613a5d8729
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994069(v=OCS.15)
ms:contentKeyID: 51803980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24f80dcd0404dfc237d1b63be378f0f333dd975b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511813"
---
# <a name="reset-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="9e88b-102">Reimpostare una regola di aggiornamento del dispositivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e88b-102">Reset a Device Update rule in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e88b-103">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="9e88b-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="9e88b-104">Se non si è interessati alla modalità di funzionamento di un aggiornamento sui dispositivi di test, è possibile reimpostare la regola di aggiornamento dei dispositivi, in modo da rimuovere lo stato in sospeso della regola e disinstallare l'aggiornamento dai dispositivi di test.</span><span class="sxs-lookup"><span data-stu-id="9e88b-104">If you don’t like the way that an update works on your test devices, you can reset the device update rule, which removes the rule’s pending status and uninstalls the update from the test devices.</span></span>

<span data-ttu-id="9e88b-105">È possibile rimuovere una regola di aggiornamento dei dispositivi utilizzando il pannello di controllo di Lync Server o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9e88b-105">You can remove a device update rule by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9e88b-106">Per disinstallare una regola già approvata (ovvero, srotolata), ripristinarla.</span><span class="sxs-lookup"><span data-stu-id="9e88b-106">To uninstall a rule that you’ve already approved (that is, rolled out), restore it.</span></span> <span data-ttu-id="9e88b-107">Per ulteriori informazioni, vedere <A href="lync-server-2013-restore-a-device-update-rule.md">ripristinare una regola di aggiornamento dei dispositivi in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9e88b-107">For details, see <A href="lync-server-2013-restore-a-device-update-rule.md">Restore a Device Update rule in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-reset-a-device-update-rule-by-using-lync-server-control-panel"></a><span data-ttu-id="9e88b-108">Per reimpostare una regola di aggiornamento dei dispositivi tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="9e88b-108">To reset a device update rule by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="9e88b-109">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="9e88b-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9e88b-110">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9e88b-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9e88b-111">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9e88b-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9e88b-112">Sulla barra di spostamento sinistra fare clic su **client**e quindi sul pulsante di spostamento **Aggiorna dispositivo** .</span><span class="sxs-lookup"><span data-stu-id="9e88b-112">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span>

4.  <span data-ttu-id="9e88b-113">Nella pagina **aggiornamento dispositivi** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9e88b-113">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="9e88b-114">Per reimpostare una regola, selezionare la regola che si desidera reimpostare.</span><span class="sxs-lookup"><span data-stu-id="9e88b-114">To reset one rule, select the rule you want to reset.</span></span>
    
      - <span data-ttu-id="9e88b-115">Per reimpostare tutte le regole, scegliere **Seleziona tutto**dal menu **modifica** .</span><span class="sxs-lookup"><span data-stu-id="9e88b-115">To reset all rules, on the **Edit** menu, click **Select All**.</span></span>
    
      - <span data-ttu-id="9e88b-116">Per reimpostare tutte le regole per una marca, utilizzare il menu colonna **marca** .</span><span class="sxs-lookup"><span data-stu-id="9e88b-116">To reset all rules for one brand, use the **Brand** column menu.</span></span>

5.  <span data-ttu-id="9e88b-117">Fare clic su **azione**e quindi su **Annulla aggiornamenti in sospeso**.</span><span class="sxs-lookup"><span data-stu-id="9e88b-117">Click **Action**, and then click **Cancel pending updates**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="9e88b-118">Se si è certi di non voler mai eseguire il rollback delle regole di aggiornamento dei dispositivi che sono state annullate, potrebbe essere necessario eliminarle.</span><span class="sxs-lookup"><span data-stu-id="9e88b-118">If you’re sure you’ll never want to roll out the device update rule(s) that you cancelled, you might want to delete them.</span></span> <span data-ttu-id="9e88b-119">Per ulteriori informazioni, vedere <A href="lync-server-2013-remove-a-device-update-rule.md">rimuovere una regola di aggiornamento dei dispositivi in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9e88b-119">For details, see <A href="lync-server-2013-remove-a-device-update-rule.md">Remove a Device Update rule in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="resetting-a-device-update-rule-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9e88b-120">Reimpostazione di una regola di aggiornamento dei dispositivi tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9e88b-120">Resetting a Device Update Rule by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9e88b-121">È possibile reimpostare le regole di aggiornamento dei dispositivi anche utilizzando Windows PowerShell e il cmdlet **Reset-CsDeviceUpdateRule** .</span><span class="sxs-lookup"><span data-stu-id="9e88b-121">Device update rules can also be reset by using Windows PowerShell and the **Reset-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="9e88b-122">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9e88b-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9e88b-123">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .</span><span class="sxs-lookup"><span data-stu-id="9e88b-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-reset-a-specific-device-update-rule-on-a-server"></a><span data-ttu-id="9e88b-124">Per reimpostare una regola di aggiornamento del dispositivo specifica in un server</span><span class="sxs-lookup"><span data-stu-id="9e88b-124">To reset a specific device update rule on a server</span></span>

  - <span data-ttu-id="9e88b-125">Il seguente comando Reimposta la regola di aggiornamento dei dispositivi d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 sul server Web atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="9e88b-125">The following command resets the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Reset-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-reset-all-the-device-update-rules-on-a-server"></a><span data-ttu-id="9e88b-126">Per reimpostare tutte le regole di aggiornamento dei dispositivi su un server</span><span class="sxs-lookup"><span data-stu-id="9e88b-126">To reset all the device update rules on a server</span></span>

  - <span data-ttu-id="9e88b-127">Questo comando consente di reimpostare tutte le regole di aggiornamento dei dispositivi sul server Web atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="9e88b-127">This command resets all the device update rules on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"  | Reset-CsDeviceUpdateRule

</div>

<div>

## <a name="to-reset-all-the-device-updates-rules-that-have-a-specific-brand"></a><span data-ttu-id="9e88b-128">Per reimpostare tutte le regole di aggiornamento dei dispositivi che dispongono di una marca specifica</span><span class="sxs-lookup"><span data-stu-id="9e88b-128">To reset all the device updates rules that have a specific brand</span></span>

  - <span data-ttu-id="9e88b-129">In questo esempio vengono reimpostati tutti gli aggiornamenti del dispositivo nell'organizzazione che dispongono di un marchio uguale a Microsoft:</span><span class="sxs-lookup"><span data-stu-id="9e88b-129">In this example, all the device updates throughout the organization that have a Brand equal to Microsoft are reset:</span></span>
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Reset-CsDeviceUpdateRule

</div>

<span data-ttu-id="9e88b-130">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Reset-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Reset-CsDeviceUpdateRule) .</span><span class="sxs-lookup"><span data-stu-id="9e88b-130">For details, see the Help topic for the [Reset-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Reset-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9e88b-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e88b-131">See Also</span></span>


[<span data-ttu-id="9e88b-132">Approvazione di una regola di aggiornamento del dispositivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e88b-132">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


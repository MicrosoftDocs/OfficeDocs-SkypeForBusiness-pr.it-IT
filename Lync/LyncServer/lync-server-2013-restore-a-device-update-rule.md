---
title: 'Lync Server 2013: ripristinare una regola di aggiornamento del dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restore a Device Update rule
ms:assetid: ac490baf-c7a0-48d9-8fd0-ba5729489341
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994061(v=OCS.15)
ms:contentKeyID: 51803972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90eeb82e710b6ea65bc32184685497494dbef8d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restore-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="e1ace-102">Ripristinare una regola di aggiornamento del dispositivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1ace-102">Restore a Device Update rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1ace-103">_**Argomento Ultima modifica:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="e1ace-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="e1ace-104">Per disinstallare una regola di aggiornamento del dispositivo dai dispositivi della distribuzione, ripristinarla.</span><span class="sxs-lookup"><span data-stu-id="e1ace-104">To uninstall a device update rule from the devices in your deployment, restore it.</span></span> <span data-ttu-id="e1ace-105">Ripristinando una regola di aggiornamento dei dispositivi viene disinstallata l'aggiornamento e viene reinstallata la versione precedente di tale regola.</span><span class="sxs-lookup"><span data-stu-id="e1ace-105">Restoring a device update rule both uninstalls the update and reinstalls the previous version of that rule.</span></span>

<span data-ttu-id="e1ace-106">È possibile ripristinare una regola di aggiornamento dei dispositivi tramite il pannello di controllo di Lync Server o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e1ace-106">You can restore a device update rule by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>

## <a name="to-restore-device-update-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="e1ace-107">Per ripristinare le regole di aggiornamento dei dispositivi tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="e1ace-107">To restore device update rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="e1ace-108">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="e1ace-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e1ace-109">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e1ace-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e1ace-110">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e1ace-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e1ace-111">Sulla barra di spostamento sinistra fare clic su **client**e quindi sul pulsante di spostamento **aggiornamento dispositivi** .</span><span class="sxs-lookup"><span data-stu-id="e1ace-111">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span>

4.  <span data-ttu-id="e1ace-112">Nella pagina **Update Device** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e1ace-112">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="e1ace-113">Per ripristinare una regola, selezionare la regola.</span><span class="sxs-lookup"><span data-stu-id="e1ace-113">To restore one rule, select that rule.</span></span>
    
      - <span data-ttu-id="e1ace-114">Per ripristinare tutte le regole, fare clic su **modifica**e quindi su **Seleziona tutto**.</span><span class="sxs-lookup"><span data-stu-id="e1ace-114">To restore all rules, click **Edit**, and then click **Select All**.</span></span>

5.  <span data-ttu-id="e1ace-115">Fare clic sul menu **azione** e quindi su **Ripristina**.</span><span class="sxs-lookup"><span data-stu-id="e1ace-115">Click the **Action** menu, and then click **Restore**.</span></span>

</div>

<div>

## <a name="restoring-device-update-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e1ace-116">Ripristino delle regole di aggiornamento dei dispositivi tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e1ace-116">Restoring Device Update Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e1ace-117">Le regole per gli aggiornamenti dei dispositivi possono essere ripristinate anche tramite Windows PowerShell e il cmdlet **Restore-CsDeviceUpdateRule** .</span><span class="sxs-lookup"><span data-stu-id="e1ace-117">Device updates rules can also be restored by using Windows PowerShell and the **Restore-CsDeviceUpdateRule** cmdlet..</span></span> <span data-ttu-id="e1ace-118">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e1ace-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e1ace-119">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="e1ace-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-restore-a-single-device-update-rule-on-a-server"></a><span data-ttu-id="e1ace-120">Per ripristinare una regola di aggiornamento di un singolo dispositivo in un server</span><span class="sxs-lookup"><span data-stu-id="e1ace-120">To restore a single device update rule on a server</span></span>

  - <span data-ttu-id="e1ace-121">Il comando seguente ripristina la regola di aggiornamento del dispositivo d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 sul server Web atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="e1ace-121">The following command restores the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Restore-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-restore-all-the-device-update-rules-on-a-server"></a><span data-ttu-id="e1ace-122">Per ripristinare tutte le regole di aggiornamento dei dispositivi in un server</span><span class="sxs-lookup"><span data-stu-id="e1ace-122">To restore all the device update rules on a server</span></span>

  - <span data-ttu-id="e1ace-123">Questo comando Ripristina tutte le regole di aggiornamento dei dispositivi sul server Web atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="e1ace-123">This command restores all the device update rules on the web server atl-cs-001.litwareinc.com:</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Restore-CsDeviceUpdateRule

</div>

<span data-ttu-id="e1ace-124">Per informazioni dettagliate, vedere l'argomento della Guida relativo al cmdlet [Restore-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Restore-CsDeviceUpdateRule) .</span><span class="sxs-lookup"><span data-stu-id="e1ace-124">For details, see the Help topic for the [Restore-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Restore-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


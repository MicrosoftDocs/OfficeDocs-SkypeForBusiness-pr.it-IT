---
title: 'Lync Server 2013: rimuovere una regola di aggiornamento del dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove a Device Update rule
ms:assetid: ad6e0c6a-cda4-4147-92d5-48bc393ac456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994066(v=OCS.15)
ms:contentKeyID: 51803977
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13b639e6541478874e80ab632b2ee231ea65151d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201482"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="bbfd4-102">Rimuovere una regola di aggiornamento del dispositivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bbfd4-102">Remove a Device Update rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bbfd4-103">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="bbfd4-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="bbfd4-104">La rimozione di una regola di aggiornamento dei dispositivi porta definitivamente fuori dalla coda di aggiornamento del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bbfd4-104">Removing a device update rule takes it permanently out of the device update queue.</span></span>

<span data-ttu-id="bbfd4-105">La rimozione di una regola è diversa dalla disinstallazione di un aggiornamento dai dispositivi della distribuzione o dai dispositivi di test.</span><span class="sxs-lookup"><span data-stu-id="bbfd4-105">Removing a rule is different from uninstalling an update from the devices in your deployment or from your test devices.</span></span> <span data-ttu-id="bbfd4-106">Per disinstallare un aggiornamento approvato dalla distribuzione, è necessario *ripristinare* la regola di aggiornamento dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="bbfd4-106">To uninstall an approved update from your deployment, you *restore* the device update rule.</span></span> <span data-ttu-id="bbfd4-107">Per ulteriori informazioni, vedere [ripristinare una regola di aggiornamento dei dispositivi in Lync Server 2013](lync-server-2013-restore-a-device-update-rule.md).</span><span class="sxs-lookup"><span data-stu-id="bbfd4-107">For details, see [Restore a Device Update rule in Lync Server 2013](lync-server-2013-restore-a-device-update-rule.md).</span></span> <span data-ttu-id="bbfd4-108">Per disinstallare un aggiornamento che non sono stati approvati dai dispositivi di test, è necessario *reimpostarlo* .</span><span class="sxs-lookup"><span data-stu-id="bbfd4-108">To uninstall an update you haven’t approved from your test devices, you *reset* it.</span></span> <span data-ttu-id="bbfd4-109">Per ulteriori informazioni, vedere [reimpostare una regola di aggiornamento dei dispositivi in Lync Server 2013](lync-server-2013-reset-a-device-update-rule.md).</span><span class="sxs-lookup"><span data-stu-id="bbfd4-109">For details, see [Reset a Device Update rule in Lync Server 2013](lync-server-2013-reset-a-device-update-rule.md).</span></span>

<span data-ttu-id="bbfd4-110">È possibile rimuovere una regola di aggiornamento dei dispositivi utilizzando il pannello di controllo di Lync Server o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bbfd4-110">You can remove a device update rule by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>

## <a name="to-remove-device-update-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="bbfd4-111">Per rimuovere le regole di aggiornamento dei dispositivi tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="bbfd4-111">To remove device update rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="bbfd4-112">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="bbfd4-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bbfd4-113">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bbfd4-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bbfd4-114">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="bbfd4-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bbfd4-115">Sulla barra di spostamento sinistra fare clic su **client**e quindi sul pulsante di spostamento **Aggiorna dispositivo** .</span><span class="sxs-lookup"><span data-stu-id="bbfd4-115">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span>

4.  <span data-ttu-id="bbfd4-116">Nella pagina **aggiornamento dispositivi** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bbfd4-116">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="bbfd4-117">Per rimuovere una regola, selezionare la regola che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="bbfd4-117">To remove one rule, select the rule you want to delete.</span></span>
    
      - <span data-ttu-id="bbfd4-118">Per rimuovere tutte le regole, fare clic sul menu **modifica** e quindi fare clic su **Seleziona tutto**.</span><span class="sxs-lookup"><span data-stu-id="bbfd4-118">To remove all rules, click the **Edit** menu, and then click **Select All**.</span></span>

5.  <span data-ttu-id="bbfd4-119">Fare clic su **Modifica** e quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="bbfd4-119">Click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="removing-device-update-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="bbfd4-120">Rimozione delle regole di aggiornamento dei dispositivi tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bbfd4-120">Removing Device Update Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="bbfd4-121">Le regole di aggiornamento dei dispositivi possono essere rimosse anche utilizzando Windows PowerShell e il cmdlet **Remove-CsDeviceUpdateRule** .</span><span class="sxs-lookup"><span data-stu-id="bbfd4-121">Device update rules can also be removed by using Windows PowerShell and the **Remove-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="bbfd4-122">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bbfd4-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="bbfd4-123">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="bbfd4-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-single-device-update-rule-from-a-server"></a><span data-ttu-id="bbfd4-124">Per rimuovere una regola di aggiornamento di un singolo dispositivo da un server</span><span class="sxs-lookup"><span data-stu-id="bbfd4-124">To remove a single device update rule from a server</span></span>

  - <span data-ttu-id="bbfd4-125">Il comando seguente rimuove la regola di aggiornamento dei dispositivi d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 dal server Web su atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="bbfd4-125">The following command removes the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 from the Web server on atl-cs-001.litwareinc.com.</span></span>
    
        Remove-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-remove-all-the-device-update-rules-from-a-server"></a><span data-ttu-id="bbfd4-126">Per rimuovere tutte le regole di aggiornamento dei dispositivi da un server</span><span class="sxs-lookup"><span data-stu-id="bbfd4-126">To remove all the device update rules from a server</span></span>

  - <span data-ttu-id="bbfd4-127">Questo comando rimuove tutte le regole di aggiornamento dei dispositivi dal server Web in atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="bbfd4-127">This command removes all the device update rules from the web server on atl-cs-001.litwareinc.com.</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Remove-CsDeviceUpdateRule

</div>

<span data-ttu-id="bbfd4-128">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule) .</span><span class="sxs-lookup"><span data-stu-id="bbfd4-128">For details, see the Help topic for the [Remove-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bbfd4-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bbfd4-129">See Also</span></span>


[<span data-ttu-id="bbfd4-130">Approvazione di una regola di aggiornamento del dispositivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bbfd4-130">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


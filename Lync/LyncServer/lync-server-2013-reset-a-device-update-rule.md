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
ms.openlocfilehash: 36a85ed29f6bf4838428af302904d80a2f792388
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723766"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="df852-102">Reimpostare una regola di aggiornamento del dispositivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df852-102">Reset a Device Update rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df852-103">_**Argomento Ultima modifica:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="df852-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="df852-104">Se non si è soddisfatti del funzionamento di un aggiornamento nei dispositivi di test, è possibile reimpostare la regola di aggiornamento del dispositivo, che rimuove lo stato in sospeso della regola e disinstalla l'aggiornamento dai dispositivi di test.</span><span class="sxs-lookup"><span data-stu-id="df852-104">If you don’t like the way that an update works on your test devices, you can reset the device update rule, which removes the rule’s pending status and uninstalls the update from the test devices.</span></span>

<span data-ttu-id="df852-105">È possibile rimuovere una regola di aggiornamento del dispositivo usando il pannello di controllo di Lync Server o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="df852-105">You can remove a device update rule by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="df852-106">Per disinstallare una regola già approvata, ovvero distribuita, ripristinarla.</span><span class="sxs-lookup"><span data-stu-id="df852-106">To uninstall a rule that you’ve already approved (that is, rolled out), restore it.</span></span> <span data-ttu-id="df852-107">Per informazioni dettagliate, vedere <A href="lync-server-2013-restore-a-device-update-rule.md">ripristinare una regola di aggiornamento dei dispositivi in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="df852-107">For details, see <A href="lync-server-2013-restore-a-device-update-rule.md">Restore a Device Update rule in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-reset-a-device-update-rule-by-using-lync-server-control-panel"></a><span data-ttu-id="df852-108">Per reimpostare una regola di aggiornamento dei dispositivi tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="df852-108">To reset a device update rule by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="df852-109">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="df852-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="df852-110">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="df852-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="df852-111">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="df852-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="df852-112">Sulla barra di spostamento sinistra fare clic su **client**e quindi sul pulsante di spostamento **aggiornamento dispositivi** .</span><span class="sxs-lookup"><span data-stu-id="df852-112">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span>

4.  <span data-ttu-id="df852-113">Nella pagina **Update Device** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="df852-113">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="df852-114">Per reimpostare una regola, selezionare la regola che si vuole reimpostare.</span><span class="sxs-lookup"><span data-stu-id="df852-114">To reset one rule, select the rule you want to reset.</span></span>
    
      - <span data-ttu-id="df852-115">Per reimpostare tutte le regole, scegliere **Seleziona tutto**dal menu **modifica** .</span><span class="sxs-lookup"><span data-stu-id="df852-115">To reset all rules, on the **Edit** menu, click **Select All**.</span></span>
    
      - <span data-ttu-id="df852-116">Per reimpostare tutte le regole per una sola marca, usare il menu colonna **marca** .</span><span class="sxs-lookup"><span data-stu-id="df852-116">To reset all rules for one brand, use the **Brand** column menu.</span></span>

5.  <span data-ttu-id="df852-117">Fare clic su **azione**e quindi su **Annulla aggiornamenti in sospeso**.</span><span class="sxs-lookup"><span data-stu-id="df852-117">Click **Action**, and then click **Cancel pending updates**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="df852-118">Se si è certi di non voler più implementare le regole di aggiornamento dei dispositivi annullate, è consigliabile eliminarle.</span><span class="sxs-lookup"><span data-stu-id="df852-118">If you’re sure you’ll never want to roll out the device update rule(s) that you cancelled, you might want to delete them.</span></span> <span data-ttu-id="df852-119">Per informazioni dettagliate, vedere <A href="lync-server-2013-remove-a-device-update-rule.md">rimuovere una regola di aggiornamento dei dispositivi in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="df852-119">For details, see <A href="lync-server-2013-remove-a-device-update-rule.md">Remove a Device Update rule in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="resetting-a-device-update-rule-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="df852-120">Reimpostazione di una regola di aggiornamento dei dispositivi con i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="df852-120">Resetting a Device Update Rule by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="df852-121">Le regole di aggiornamento dei dispositivi possono essere reimpostate anche tramite Windows PowerShell e il cmdlet **Reset-CsDeviceUpdateRule** .</span><span class="sxs-lookup"><span data-stu-id="df852-121">Device update rules can also be reset by using Windows PowerShell and the **Reset-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="df852-122">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="df852-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="df852-123">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="df852-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-reset-a-specific-device-update-rule-on-a-server"></a><span data-ttu-id="df852-124">Per reimpostare una regola di aggiornamento di un dispositivo specifico in un server</span><span class="sxs-lookup"><span data-stu-id="df852-124">To reset a specific device update rule on a server</span></span>

  - <span data-ttu-id="df852-125">Il comando seguente reimposta la regola di aggiornamento del dispositivo d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 sul server Web atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="df852-125">The following command resets the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Reset-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-reset-all-the-device-update-rules-on-a-server"></a><span data-ttu-id="df852-126">Per reimpostare tutte le regole di aggiornamento dei dispositivi in un server</span><span class="sxs-lookup"><span data-stu-id="df852-126">To reset all the device update rules on a server</span></span>

  - <span data-ttu-id="df852-127">Questo comando Reimposta tutte le regole di aggiornamento dei dispositivi sul server Web atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="df852-127">This command resets all the device update rules on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"  | Reset-CsDeviceUpdateRule

</div>

<div>

## <a name="to-reset-all-the-device-updates-rules-that-have-a-specific-brand"></a><span data-ttu-id="df852-128">Per reimpostare tutte le regole di aggiornamento dei dispositivi con un marchio specifico</span><span class="sxs-lookup"><span data-stu-id="df852-128">To reset all the device updates rules that have a specific brand</span></span>

  - <span data-ttu-id="df852-129">In questo esempio tutti gli aggiornamenti del dispositivo in tutta l'organizzazione che hanno un marchio uguale a Microsoft vengono reimpostati:</span><span class="sxs-lookup"><span data-stu-id="df852-129">In this example, all the device updates throughout the organization that have a Brand equal to Microsoft are reset:</span></span>
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Reset-CsDeviceUpdateRule

</div>

<span data-ttu-id="df852-130">Per informazioni dettagliate, vedere l'argomento della Guida relativo al cmdlet [Reset-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Reset-CsDeviceUpdateRule) .</span><span class="sxs-lookup"><span data-stu-id="df852-130">For details, see the Help topic for the [Reset-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Reset-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="df852-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df852-131">See Also</span></span>


[<span data-ttu-id="df852-132">Approvare una regola di aggiornamento del dispositivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df852-132">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


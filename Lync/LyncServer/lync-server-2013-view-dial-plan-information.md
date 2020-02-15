---
title: 'Lync Server 2013: visualizzare le informazioni del dial plan'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View dial plan information
ms:assetid: 25ed0112-a8a7-418a-8c2c-580081be692a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687997(v=OCS.15)
ms:contentKeyID: 49733587
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c63aead21441cb972cce2b6fb26391efc43969bb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42009559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-dial-plan-information-in-lync-server-2013"></a><span data-ttu-id="ffc48-102">Visualizzare le informazioni sul dial plan in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ffc48-102">View dial plan information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffc48-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ffc48-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ffc48-104">Per visualizzare informazioni per un dial plan esistente, eseguire i passaggi illustrati nella procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="ffc48-104">To view information for an existing dial plan, perform the steps in the following procedure.</span></span> <span data-ttu-id="ffc48-105">Se si desidera creare un nuovo dial plan, vedere [creare un dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="ffc48-105">If you want to create a new dial plan, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

<div>

## <a name="to-view-information-about-a-dial-plan-from-lync-server-control-panel"></a><span data-ttu-id="ffc48-106">Per visualizzare informazioni su un dial plan dal pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="ffc48-106">To view information about a dial plan from Lync Server Control Panel</span></span>

1.  <span data-ttu-id="ffc48-107">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="ffc48-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="ffc48-108">Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="ffc48-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="ffc48-109">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ffc48-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ffc48-110">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ffc48-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ffc48-111">Sulla barra di spostamento sinistra fare clic su **Routing vocale** e quindi su **Dial plan**.</span><span class="sxs-lookup"><span data-stu-id="ffc48-111">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>

4.  <span data-ttu-id="ffc48-112">Nella pagina **Dial plan** fare doppio clic sul nome di un dial plan.</span><span class="sxs-lookup"><span data-stu-id="ffc48-112">On the **Dial Plan** page, double-click a dial plan name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ffc48-113">È possibile visualizzare informazioni per un solo dial plan alla volta.</span><span class="sxs-lookup"><span data-stu-id="ffc48-113">You can view information for only one dial plan at a time.</span></span>

    
    </div>

</div>

<div>

## <a name="to-view-dial-plans-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ffc48-114">Per visualizzare i dial plan tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ffc48-114">To view dial plans by using Windows PowerShell cmdlets</span></span>

  - <span data-ttu-id="ffc48-115">I dial plan possono essere visualizzati utilizzando l'interfaccia della riga di comando di Windows PowerShell e il cmdlet **Get-CsDialPlan** .</span><span class="sxs-lookup"><span data-stu-id="ffc48-115">Dial plans can be viewed by using the Windows PowerShell command-line interface and the **Get-CsDialPlan** cmdlet.</span></span> <span data-ttu-id="ffc48-116">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ffc48-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="ffc48-117">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="ffc48-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="ffc48-118">Per visualizzare informazioni su tutti i dial plan, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="ffc48-118">To view information about all your dial plans, type the following command in the Lync Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsDialPlan
    
    <span data-ttu-id="ffc48-119">Tale comando restituirà informazioni simili a quelle che seguono:</span><span class="sxs-lookup"><span data-stu-id="ffc48-119">That command will return information similar to this:</span></span>
    
        Identity                 : Global
        Description              :
        DialinConferencingRegion :
        NormalizationRules       : {Description=;
                                   Pattern=^(\d+)$;Translation=$1;Name=
                                   KeepAll;IsInternalExtension=False}
        CountryCode              :
        State                    :
        City                     :
        ExternalAccessPrefix     :
        SimpleName               : DefaultProfile
        OptimizeDeviceDialing    : False

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ffc48-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ffc48-120">See Also</span></span>


[<span data-ttu-id="ffc48-121">Creare un dial plan in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ffc48-121">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="ffc48-122">Modificare un dial plan in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ffc48-122">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


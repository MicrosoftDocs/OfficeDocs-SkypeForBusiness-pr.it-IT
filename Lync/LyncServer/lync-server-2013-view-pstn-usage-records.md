---
title: 'Lync Server 2013: visualizzare i record di utilizzo PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View PSTN usage records
ms:assetid: 65025c78-c263-472c-9ff9-e170588f10b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398458(v=OCS.15)
ms:contentKeyID: 48184361
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84ba8e2091a88238caee188f3542b76f652129c4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038038"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="8456a-102">Visualizzare i record di utilizzo PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8456a-102">View PSTN usage records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8456a-103">_**Ultimo argomento modificato:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="8456a-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="8456a-104">Un record di utilizzo PSTN (Public Switched Telephone Network) specifica una classe di chiamata (ad esempio, interna, locale o interurbana) che può essere effettuata da diversi utenti o gruppi di utenti di un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8456a-104">A public switched telephone network (PSTN) usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users or groups of users in an organization.</span></span> <span data-ttu-id="8456a-105">Per informazioni dettagliate, vedere [PSTN Usage Records in Lync Server 2013](lync-server-2013-pstn-usage-records.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="8456a-105">For details, see [PSTN usage records in Lync Server 2013](lync-server-2013-pstn-usage-records.md) in the Planning documentation.</span></span>

<div>

## <a name="to-view-a-pstn-usage-record-by-using-lync-server-control-panel"></a><span data-ttu-id="8456a-106">Per visualizzare un record di utilizzo PSTN tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="8456a-106">To view a PSTN usage record by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="8456a-107">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="8456a-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="8456a-108">Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="8456a-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="8456a-109">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8456a-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8456a-110">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8456a-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8456a-111">Sulla barra di spostamento sinistra fare clic su **Routing vocale** e quindi su **Utilizzo PSTN**.</span><span class="sxs-lookup"><span data-stu-id="8456a-111">In the left navigation bar, click **Voice Routing** and then click **PSTN Usage**.</span></span>

4.  <span data-ttu-id="8456a-112">Nella pagina **Utilizzo PSTN** evidenziare i record di utilizzo PSTN che si desidera visualizzare, fare clic su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="8456a-112">On the **PSTN Usage** page, highlight the PSTN usage record you want to view, click **Edit** and then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8456a-113">In una pagina di sola lettura per il record di utilizzo PSTN selezionato vengono visualizzati le route e i criteri vocali associati.</span><span class="sxs-lookup"><span data-stu-id="8456a-113">A read-only page of the selected PSTN usage record shows the associated routes and associated voice policies.</span></span>

    
    </div>

</div>

<div>

## <a name="viewing-pstn-usage-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="8456a-114">Visualizzazione delle informazioni sull'utilizzo PSTN tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8456a-114">Viewing PSTN Usage Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="8456a-115">È inoltre possibile visualizzare gli utilizzi PSTN utilizzando Windows PowerShell e il cmdlet **Get-CsPstnUsage** .</span><span class="sxs-lookup"><span data-stu-id="8456a-115">You can also view PSTN usages by using Windows PowerShell and the **Get-CsPstnUsage** cmdlet.</span></span> <span data-ttu-id="8456a-116">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8456a-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="8456a-117">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="8456a-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-pstn-usage-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="8456a-118">Per visualizzare le informazioni sull'utilizzo PSTN tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8456a-118">To view PSTN usage information by using Windows PowerShell cmdlets</span></span>

  - <span data-ttu-id="8456a-119">Per visualizzare informazioni su tutti gli utilizzi PSTN, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="8456a-119">To view information about all of your PSTN usages, type the following command in the Lync Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsPstnUsage
    
    <span data-ttu-id="8456a-120">Il comando restituisce informazioni simili a quelle riportate di seguito:</span><span class="sxs-lookup"><span data-stu-id="8456a-120">This command returns information similar to the following:</span></span>
    
        Identity : Global
        Usage    : {Internal, Local, Long Distance}

</div>

<span data-ttu-id="8456a-121">Per informazioni dettagliate, vedere [Get-CsPstnUsage](https://docs.microsoft.com/powershell/module/skype/Get-CsPstnUsage).</span><span class="sxs-lookup"><span data-stu-id="8456a-121">For details, see [Get-CsPstnUsage](https://docs.microsoft.com/powershell/module/skype/Get-CsPstnUsage).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8456a-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8456a-122">See Also</span></span>


[<span data-ttu-id="8456a-123">Creare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8456a-123">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="8456a-124">Modificare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8456a-124">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


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
ms.openlocfilehash: b2551c8bbc40429d7e5bc4af45cae862991381a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756680"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="1ed51-102">Visualizzare i record di utilizzo PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ed51-102">View PSTN usage records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ed51-103">_**Argomento Ultima modifica:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="1ed51-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="1ed51-104">Un record di utilizzo PSTN (Public Switched Telephone Network) specifica una classe di chiamata, ad esempio Internal, local o Long Distance, che può essere eseguita da vari utenti o gruppi di utenti di un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1ed51-104">A public switched telephone network (PSTN) usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users or groups of users in an organization.</span></span> <span data-ttu-id="1ed51-105">Per informazioni dettagliate, vedere [record sull'utilizzo PSTN in Lync Server 2013](lync-server-2013-pstn-usage-records.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="1ed51-105">For details, see [PSTN usage records in Lync Server 2013](lync-server-2013-pstn-usage-records.md) in the Planning documentation.</span></span>

<div>

## <a name="to-view-a-pstn-usage-record-by-using-lync-server-control-panel"></a><span data-ttu-id="1ed51-106">Per visualizzare un record di utilizzo PSTN tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="1ed51-106">To view a PSTN usage record by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="1ed51-107">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="1ed51-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="1ed51-108">Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="1ed51-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="1ed51-109">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1ed51-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1ed51-110">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1ed51-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1ed51-111">Sulla barra di spostamento sinistra fare clic su **routing vocale** e quindi su **utilizzo PSTN**.</span><span class="sxs-lookup"><span data-stu-id="1ed51-111">In the left navigation bar, click **Voice Routing** and then click **PSTN Usage**.</span></span>

4.  <span data-ttu-id="1ed51-112">Nella pagina **uso PSTN** evidenziare il record di utilizzo PSTN che si vuole visualizzare, fare clic su **modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="1ed51-112">On the **PSTN Usage** page, highlight the PSTN usage record you want to view, click **Edit** and then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1ed51-113">Una pagina di sola lettura del record di utilizzo PSTN selezionato Mostra le route associate e i criteri vocali associati.</span><span class="sxs-lookup"><span data-stu-id="1ed51-113">A read-only page of the selected PSTN usage record shows the associated routes and associated voice policies.</span></span>

    
    </div>

</div>

<div>

## <a name="viewing-pstn-usage-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1ed51-114">Visualizzazione delle informazioni sull'utilizzo PSTN tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1ed51-114">Viewing PSTN Usage Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1ed51-115">È anche possibile visualizzare gli usi PSTN tramite Windows PowerShell e il cmdlet **Get-CsPstnUsage** .</span><span class="sxs-lookup"><span data-stu-id="1ed51-115">You can also view PSTN usages by using Windows PowerShell and the **Get-CsPstnUsage** cmdlet.</span></span> <span data-ttu-id="1ed51-116">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ed51-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1ed51-117">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="1ed51-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-pstn-usage-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1ed51-118">Per visualizzare le informazioni sull'utilizzo PSTN tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1ed51-118">To view PSTN usage information by using Windows PowerShell cmdlets</span></span>

  - <span data-ttu-id="1ed51-119">Per visualizzare informazioni su tutti gli usi PSTN, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="1ed51-119">To view information about all of your PSTN usages, type the following command in the Lync Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsPstnUsage
    
    <span data-ttu-id="1ed51-120">Questo comando restituisce informazioni simili a quelle seguenti:</span><span class="sxs-lookup"><span data-stu-id="1ed51-120">This command returns information similar to the following:</span></span>
    
        Identity : Global
        Usage    : {Internal, Local, Long Distance}

</div>

<span data-ttu-id="1ed51-121">Per informazioni dettagliate, vedere [Get-CsPstnUsage](https://docs.microsoft.com/powershell/module/skype/Get-CsPstnUsage).</span><span class="sxs-lookup"><span data-stu-id="1ed51-121">For details, see [Get-CsPstnUsage](https://docs.microsoft.com/powershell/module/skype/Get-CsPstnUsage).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1ed51-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1ed51-122">See Also</span></span>


[<span data-ttu-id="1ed51-123">Creare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ed51-123">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="1ed51-124">Modificare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ed51-124">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


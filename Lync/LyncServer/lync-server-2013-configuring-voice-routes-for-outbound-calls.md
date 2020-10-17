---
title: 'Lync Server 2013: configurazione delle route vocali per le chiamate in uscita'
description: 'Lync Server 2013: configurazione delle route vocali per le chiamate in uscita.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice routes for outbound calls
ms:assetid: 3c182cdd-7a4a-4a9d-bdac-4199f0abd947
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425890(v=OCS.15)
ms:contentKeyID: 48183875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2dd0d712295ecdd0e9a517330abcff36021e996d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542212"
---
# <a name="configuring-voice-routes-for-outbound-calls-in-lync-server-2013"></a><span data-ttu-id="6571c-103">Configurazione di route vocali per le chiamate in uscita in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6571c-103">Configuring voice routes for outbound calls in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6571c-104">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="6571c-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="6571c-105">Una route vocale di Lync Server 2013 associa i numeri di telefono di destinazione a uno o più gateway PSTN (Public Switched Telephone Network) o trunk SIP e uno o più record di utilizzo PSTN.</span><span class="sxs-lookup"><span data-stu-id="6571c-105">A Lync Server 2013 voice route associates destination phone numbers with one or more public switched telephone network (PSTN) gateways or SIP trunks and one or more PSTN usage records.</span></span>

<span data-ttu-id="6571c-106">**Per visualizzare le route vocali tramite il pannello di controllo di Lync Server**</span><span class="sxs-lookup"><span data-stu-id="6571c-106">**To view voice routes by using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="6571c-107">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6571c-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6571c-108">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6571c-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="6571c-109">Fare clic su **Routing vocale**.</span><span class="sxs-lookup"><span data-stu-id="6571c-109">Click **Voice Routing**.</span></span>

3.  <span data-ttu-id="6571c-110">Fare clic su **Route**.</span><span class="sxs-lookup"><span data-stu-id="6571c-110">Click **Route**.</span></span>

4.  <span data-ttu-id="6571c-p102">Fare doppio clic su una route vocale nell'elenco per visualizzare altre proprietà oppure selezionare la route e fare clic su **Modifica**. Quindi fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="6571c-p102">Double-click a voice route to view additional properties from the list of voice routes, or select the route and click **Edit**. Then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6571c-113">È possibile visualizzare informazioni dettagliate per una sola route per volta.</span><span class="sxs-lookup"><span data-stu-id="6571c-113">You can only view detailed information for a single route at a time.</span></span>

    
    </div>

<span data-ttu-id="6571c-114">**Per visualizzare le route vocali tramite Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="6571c-114">**To view voice routes by using Windows PowerShell**</span></span>

  - <span data-ttu-id="6571c-115">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="6571c-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span> <span data-ttu-id="6571c-116">Le route vocali possono essere visualizzate utilizzando Windows PowerShell e il cmdlet **Get-CsVoiceRoute** .</span><span class="sxs-lookup"><span data-stu-id="6571c-116">Voice routes can be viewed by using Windows PowerShell and the **Get-CsVoiceRoute** cmdlet.</span></span> <span data-ttu-id="6571c-117">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6571c-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="6571c-118">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="6571c-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="6571c-119">Per visualizzare informazioni su tutte le route vocali, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="6571c-119">To view information about all of your voice routes, type the following command in the Lync Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsVoiceRoute
    
    <span data-ttu-id="6571c-120">Verranno restituite informazioni simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="6571c-120">That will return information similar to this:</span></span>
    
        Identity          : global
        Priority          : -1
        Description       :
        NumberPattern     : ^(\+1[0-9]{10})$
        PstnUsages        : {}
        PstnGatewayList   : {}
        Name              : global
        SuppressCallerId  :
        AlternateCallerId :

<div>


> [!NOTE]  
> <span data-ttu-id="6571c-121">Per informazioni dettagliate, vedere <A href="lync-server-2013-voice-routes.md">Voice routes in Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="6571c-121">For details, see <A href="lync-server-2013-voice-routes.md">Voice routes in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6571c-122">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="6571c-122">In This Section</span></span>

  - [<span data-ttu-id="6571c-123">Creare una route vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6571c-123">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)

  - [<span data-ttu-id="6571c-124">Modificare una route vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6571c-124">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6571c-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6571c-125">See Also</span></span>


[<span data-ttu-id="6571c-126">Gestione del routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6571c-126">Managing voice routing in Lync Server 2013</span></span>](lync-server-2013-managing-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


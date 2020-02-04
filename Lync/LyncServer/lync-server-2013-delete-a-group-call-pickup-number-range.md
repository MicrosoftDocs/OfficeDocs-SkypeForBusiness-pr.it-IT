---
title: 'Lync Server 2013: eliminare un intervallo di numeri di raccolta di una chiamata di gruppo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a Group Call Pickup number range
ms:assetid: 521891f3-7a5d-45de-92dc-d57025453159
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945629(v=OCS.15)
ms:contentKeyID: 51541475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66b95df76c812b50ff9c220ea208406a5ab7cf2a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741026"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-group-call-pickup-number-range-in-lync-server-2013"></a><span data-ttu-id="ffef4-102">Eliminare un intervallo di numeri di prelievo delle chiamate di gruppo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ffef4-102">Delete a Group Call Pickup number range in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffef4-103">_**Argomento Ultima modifica:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="ffef4-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="ffef4-104">Usare la procedura seguente per eliminare un intervallo di numeri di prelievo delle chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="ffef4-104">Use the following procedure to delete a Group Call Pickup number range.</span></span>

<div>

## <a name="to-delete-a-call-pickup-group-number-range"></a><span data-ttu-id="ffef4-105">Per eliminare un intervallo di numeri del gruppo di raccolta chiamate</span><span class="sxs-lookup"><span data-stu-id="ffef4-105">To delete a call pickup group number range</span></span>

1.  <span data-ttu-id="ffef4-106">Accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in autorizzazioni di [configurazione delegate in Lync server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="ffef4-106">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="ffef4-107">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="ffef4-107">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ffef4-108">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="ffef4-108">At the command line, type:</span></span>
    
        Remove-CsCallParkOrbit -Identity "<group number range name>" 
    
    <span data-ttu-id="ffef4-109">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ffef4-109">For example:</span></span>
    
        Remove-CsCallParkOrbit -Identity "Redmond call pickup"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ffef4-110">Per informazioni dettagliate su altre opzioni, vedere <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.</span><span class="sxs-lookup"><span data-stu-id="ffef4-110">For details about more options, see <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ffef4-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ffef4-111">See Also</span></span>


[<span data-ttu-id="ffef4-112">Creare o modificare un intervallo orbit di Call Park in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ffef4-112">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)  


[<span data-ttu-id="ffef4-113">Remove-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="ffef4-113">Remove-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit)  
[<span data-ttu-id="ffef4-114">Get-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="ffef4-114">Get-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


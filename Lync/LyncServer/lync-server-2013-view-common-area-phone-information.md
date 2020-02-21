---
title: 'Lync Server 2013: visualizzare le informazioni sui telefoni delle aree comuni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View common area phone information
ms:assetid: e652240c-6a3f-4be7-a083-32f24c08e655
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994081(v=OCS.15)
ms:contentKeyID: 51803992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb9b9a928925bfc3ff933e2d94d39db8b652e6ff
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211532"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-common-area-phone-information-in-lync-server-2013"></a><span data-ttu-id="9dd15-102">Visualizzare le informazioni sui telefoni delle aree comuni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9dd15-102">View common area phone information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9dd15-103">_**Ultimo argomento modificato:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="9dd15-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="9dd15-104">È possibile visualizzare informazioni sui telefoni delle aree comuni configurati per l'utilizzo nell'organizzazione utilizzando il cmdlet **Get-CsCommonAreaPhone** .</span><span class="sxs-lookup"><span data-stu-id="9dd15-104">You can view information about the common area phones configured for use in your organization by using the **Get-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="9dd15-105">Utilizzato senza parametri, questo cmdlet restituisce informazioni su tutti i telefoni delle aree comuni.</span><span class="sxs-lookup"><span data-stu-id="9dd15-105">Used without any parameters, this cmdlet returns information about all your common area phones.</span></span> <span data-ttu-id="9dd15-106">I parametri facoltativi consentono di filtrare le informazioni in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="9dd15-106">Optional parameters provide different ways for you to filter information.</span></span> <span data-ttu-id="9dd15-107">Ad esempio, è possibile restituire tutti i telefoni delle aree comuni che dispongono di oggetti contatto in un'unità organizzativa specificata o in tutti gli oggetti contatti situati in un determinato edificio.</span><span class="sxs-lookup"><span data-stu-id="9dd15-107">For example, you can return all the common area phones that have contact objects in a specified organizational unit (OU) or all the contacts objects located in a specified building.</span></span> <span data-ttu-id="9dd15-108">Per informazioni dettagliate sui parametri **Get-CsCommonAreaPhone** , vedere [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone).</span><span class="sxs-lookup"><span data-stu-id="9dd15-108">For details about **Get-CsCommonAreaPhone** parameters, see [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone).</span></span>

<span data-ttu-id="9dd15-109">Eseguire **Get-CsCommonAreaPhone** sia da Lync Server 2013 Management Shell sia da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9dd15-109">Run **Get-CsCommonAreaPhone** either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


<div>

## <a name="viewing-information-about-all-your-common-area-phones"></a><span data-ttu-id="9dd15-110">Visualizzazione delle informazioni su tutti i telefoni delle aree comuni</span><span class="sxs-lookup"><span data-stu-id="9dd15-110">Viewing Information about All Your Common Area Phones</span></span>

  - <span data-ttu-id="9dd15-111">Per visualizzare informazioni su tutti i telefoni delle aree comuni, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="9dd15-111">To view information about all your common area phones, type the following command in the Lync Server Management Shell, and then press Enter:</span></span>
    
        Get-CsCommonAreaPhone
    
    <span data-ttu-id="9dd15-112">Otterrete informazioni simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="9dd15-112">You’ll get information similar to this:</span></span>
    
        Identity           : CN=Building 14 Lobby,OU=Redmond,
                             DC=litwareinc,DC=com
        RegistrarPool      : atl-cs-001.litwareinc.com
        Enabled            : True
        SipAddress         : sip:4714e34b-9781-421d-b07a-
                             52056b5b4a56@litwareinc.com
        ClientPolicy       :
        PinPolicy          :
        VoicePolicy        :
        MobilityPolicy     :
        GroupChatPolicy    :
        ConferencingPolicy :
        LineURI            : tel:+14255550712
        DisplayNumber      : 1-425-555-0712
        DisplayName        : Building 14 Lobby
        Description        :
        ExUmEnabled        : False

</div>

<span data-ttu-id="9dd15-113">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone) .</span><span class="sxs-lookup"><span data-stu-id="9dd15-113">For details, see the Help topic for the [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


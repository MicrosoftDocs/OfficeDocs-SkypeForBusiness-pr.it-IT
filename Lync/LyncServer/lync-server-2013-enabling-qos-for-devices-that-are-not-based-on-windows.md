---
title: 'Lync Server 2013: abilitazione di QoS per i dispositivi che non sono basati su Windows'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoS for devices that are not based on Windows
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 447c19b96e2189953db81db6ce4f022e4d0f6e6f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207683"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-qos-in-lync-server-2013-for-devices-that-are-not-based-on-windows"></a><span data-ttu-id="b3c02-102">Abilitazione del QoS in Lync Server 2013 per dispositivi che non sono basati su Windows</span><span class="sxs-lookup"><span data-stu-id="b3c02-102">Enabling QoS in Lync Server 2013 for devices that are not based on Windows</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3c02-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b3c02-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b3c02-104">Quando si installa Microsoft Lync Server 2013, la qualità del servizio (QoS) non verrà abilitata per i dispositivi utilizzati nell'organizzazione che utilizzano un sistema operativo diverso da Windows.</span><span class="sxs-lookup"><span data-stu-id="b3c02-104">When you install Microsoft Lync Server 2013, Quality of Service (QoS) will not be enabled for any devices used in your organization that use an operating system other than Windows.</span></span> <span data-ttu-id="b3c02-105">È possibile verificarlo eseguendo il comando riportato di seguito dall'interno di Lync Server 2013 Management Shell:</span><span class="sxs-lookup"><span data-stu-id="b3c02-105">You can verify this by running the following command from within the Lync Server 2013 Management Shell:</span></span>

    Get-CsMediaConfiguration

<span data-ttu-id="b3c02-106">Supponendo che non siano state apportate modifiche alle impostazioni di configurazione dei supporti, dovrebbero essere visualizzate informazioni simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="b3c02-106">Assuming you have not made any changes to your media configuration settings you should get back information similar to this:</span></span>

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

<span data-ttu-id="b3c02-107">Se la proprietà EnableQoS è impostata su false (come nell'output precedente), ciò significa che la qualità del servizio non è abilitata per i computer e i dispositivi che utilizzano un sistema operativo diverso da Windows.</span><span class="sxs-lookup"><span data-stu-id="b3c02-107">If the EnableQoS property is set to False (as in the preceding output) that means that Quality of Service is not enabled for computers and devices that use an operating system other than Windows.</span></span> <span data-ttu-id="b3c02-108">La funzionalità QoS è abilitata per impostazione predefinita per i dispositivi Lync Phone Edition. Tuttavia, è possibile disabilitare la qualità del servizio per Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="b3c02-108">QoS is enabled by default for Lync Phone Edition devices; however, it is possible to disable Quality of Service for Lync Phone Edition.</span></span>

<span data-ttu-id="b3c02-109">Per abilitare la qualità del servizio nell'ambito globale, eseguire il comando riportato di seguito dall'interno di Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="b3c02-109">To enable Quality of Service at the global scope, run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="b3c02-p103">Il comando precedente abilita QoS nell'ambito globale, tuttavia è importante osservare che le impostazioni di configurazione dei supporti possono essere applicate anche nell'ambito del sito. Se si desidera abilitare Qualità del servizio per un sito, è necessario includere l'Identità delle impostazioni di configurazione quando si chiama Set-CsMediaConfiguration. Questo comando, ad esempio, abilita QoS per il sito di Redmond:</span><span class="sxs-lookup"><span data-stu-id="b3c02-p103">The preceding command enables QoS at the global scope; however, it's important to note that media configuration settings can also be applied to the site scope. If you need to enable Quality of Service for a site you must include the Identity of the configuration settings when calling Set-CsMediaConfiguration. For example, this command enables QoS for the Redmond site:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True

<div>


> [!NOTE]  
> <span data-ttu-id="b3c02-p104">Non è sempre necessario abilitare QoS nell'ambito del sito. Le impostazioni assegnate all'ambito del sito hanno la precedenza su quelle assegnate all'ambito globale. Si supponga che QoS sia abilitato nell'ambito globale ma che sia disabilitato nell'ambito del sito (per il sito di Redmond.) In questo caso, Qualità del servizio verrà disabilitato per il sito di Redmond, in quanto le impostazioni del sito sono prioritarie. Per abilitare QoS per il sito di Redmond, sarà necessario usare le impostazioni di configurazione dei supporti applicate a tale sito.</span><span class="sxs-lookup"><span data-stu-id="b3c02-p104">Do you need to enable QoS at the site scope? That depends. Settings assigned to the site scope take precedence over settings assigned to the global scope. Suppose you have QoS enabled at the global scope but disabled at the site scope (for the Redmond site.) In that case, Quality of Service will be disabled for the Redmond site; that's because the site settings take precedence. To enable QoS for the Redmond site you will have to do so using the media configuration settings applied to that site.</span></span>



</div>

<span data-ttu-id="b3c02-118">Se si desidera abilitare contemporaneamente QoS per tutte le impostazioni di configurazione dei contenuti multimediali (indipendentemente dall'ambito), eseguire questo comando dall'interno di Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="b3c02-118">If you want to simultaneously enable QoS for all your media configuration settings (regardless of scope) then run this command from within the Lync Server Management Shell:</span></span>

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="b3c02-119">È possibile disabilitare QoS per i dispositivi che utilizzano un sistema operativo diverso da Windows impostando il valore della proprietà EnableQoS su false.</span><span class="sxs-lookup"><span data-stu-id="b3c02-119">You can disable QoS for devices that use an operating system other than Windows by setting the value of the EnableQoS property to False.</span></span> <span data-ttu-id="b3c02-120">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b3c02-120">For example:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

<span data-ttu-id="b3c02-121">Questo consente di implementare QoS su alcune parti della rete, ad esempio nel sito di Redmond, e lasciarlo disabilitato su altre parti.</span><span class="sxs-lookup"><span data-stu-id="b3c02-121">This gives you the ability to implement QoS on some portions of your network (for example, on the Redmond site) while leaving Quality of Service disabled on other portions of your network.</span></span>

<span data-ttu-id="b3c02-122">La funzionalità QoS può essere abilitata e disabilitata solo utilizzando Windows PowerShell queste opzioni non sono disponibili nel pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b3c02-122">QoS can only be enabled and disabled by using Windows PowerShell These options are not available in the Lync Server Control Panel.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


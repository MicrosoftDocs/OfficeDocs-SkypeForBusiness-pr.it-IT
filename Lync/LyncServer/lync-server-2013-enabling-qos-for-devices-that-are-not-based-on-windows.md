---
title: 'Lync Server 2013: abilitare QoS per i dispositivi che non sono basati su Windows'
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
ms.openlocfilehash: d7574169c5a8c9cb660a81b384711a4937056b37
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735631"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-qos-in-lync-server-2013-for-devices-that-are-not-based-on-windows"></a><span data-ttu-id="ec88f-102">Abilitazione del QoS in Lync Server 2013 per i dispositivi che non sono basati su Windows</span><span class="sxs-lookup"><span data-stu-id="ec88f-102">Enabling QoS in Lync Server 2013 for devices that are not based on Windows</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec88f-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ec88f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ec88f-104">Quando si installa Microsoft Lync Server 2013, la qualità del servizio (QoS) non verrà abilitata per i dispositivi usati nell'organizzazione che usano un sistema operativo diverso da Windows.</span><span class="sxs-lookup"><span data-stu-id="ec88f-104">When you install Microsoft Lync Server 2013, Quality of Service (QoS) will not be enabled for any devices used in your organization that use an operating system other than Windows.</span></span> <span data-ttu-id="ec88f-105">Puoi verificare questa operazione eseguendo il comando seguente dall'interno di Lync Server 2013 Management Shell:</span><span class="sxs-lookup"><span data-stu-id="ec88f-105">You can verify this by running the following command from within the Lync Server 2013 Management Shell:</span></span>

    Get-CsMediaConfiguration

<span data-ttu-id="ec88f-106">Supponendo che non siano state apportate modifiche alle impostazioni di configurazione multimediali, è consigliabile ripristinare le informazioni in modo simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="ec88f-106">Assuming you have not made any changes to your media configuration settings you should get back information similar to this:</span></span>

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

<span data-ttu-id="ec88f-107">Se la proprietà EnableQoS è impostata su false (come nell'output precedente), ciò significa che la qualità del servizio non è abilitata per i computer e i dispositivi che usano un sistema operativo diverso da Windows.</span><span class="sxs-lookup"><span data-stu-id="ec88f-107">If the EnableQoS property is set to False (as in the preceding output) that means that Quality of Service is not enabled for computers and devices that use an operating system other than Windows.</span></span> <span data-ttu-id="ec88f-108">La funzionalità QoS è abilitata per impostazione predefinita per i dispositivi Lync Phone Edition; Tuttavia, è possibile disabilitare la qualità del servizio per Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="ec88f-108">QoS is enabled by default for Lync Phone Edition devices; however, it is possible to disable Quality of Service for Lync Phone Edition.</span></span>

<span data-ttu-id="ec88f-109">Per abilitare la qualità del servizio nell'ambito globale, eseguire il comando seguente all'interno di Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="ec88f-109">To enable Quality of Service at the global scope, run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="ec88f-110">Il comando precedente consente di abilitare il QoS nell'ambito globale; Tuttavia, è importante notare che le impostazioni di configurazione multimediali possono essere applicate anche all'ambito del sito.</span><span class="sxs-lookup"><span data-stu-id="ec88f-110">The preceding command enables QoS at the global scope; however, it's important to note that media configuration settings can also be applied to the site scope.</span></span> <span data-ttu-id="ec88f-111">Se è necessario abilitare la qualità del servizio per un sito, è necessario includere l'identità delle impostazioni di configurazione quando si chiama Set-CsMediaConfiguration.</span><span class="sxs-lookup"><span data-stu-id="ec88f-111">If you need to enable Quality of Service for a site you must include the Identity of the configuration settings when calling Set-CsMediaConfiguration.</span></span> <span data-ttu-id="ec88f-112">Ad esempio, questo comando Abilita QoS per il sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="ec88f-112">For example, this command enables QoS for the Redmond site:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True

<div>


> [!NOTE]  
> <span data-ttu-id="ec88f-113">È necessario abilitare QoS nell'ambito del sito?</span><span class="sxs-lookup"><span data-stu-id="ec88f-113">Do you need to enable QoS at the site scope?</span></span> <span data-ttu-id="ec88f-114">Dipende.</span><span class="sxs-lookup"><span data-stu-id="ec88f-114">That depends.</span></span> <span data-ttu-id="ec88f-115">Le impostazioni assegnate all'ambito del sito hanno la precedenza sulle impostazioni assegnate all'ambito globale.</span><span class="sxs-lookup"><span data-stu-id="ec88f-115">Settings assigned to the site scope take precedence over settings assigned to the global scope.</span></span> <span data-ttu-id="ec88f-116">Supponiamo di avere abilitato QoS nell'ambito globale ma disabilitato nell'ambito del sito (per il sito Redmond). In questo caso, la qualità del servizio verrà disabilitata per il sito Redmond; il motivo è che le impostazioni del sito hanno la precedenza.</span><span class="sxs-lookup"><span data-stu-id="ec88f-116">Suppose you have QoS enabled at the global scope but disabled at the site scope (for the Redmond site.) In that case, Quality of Service will be disabled for the Redmond site; that's because the site settings take precedence.</span></span> <span data-ttu-id="ec88f-117">Per abilitare QoS per il sito Redmond, sarà necessario usare le impostazioni di configurazione multimediale applicate a tale sito.</span><span class="sxs-lookup"><span data-stu-id="ec88f-117">To enable QoS for the Redmond site you will have to do so using the media configuration settings applied to that site.</span></span>



</div>

<span data-ttu-id="ec88f-118">Se si vuole abilitare contemporaneamente QoS per tutte le impostazioni di configurazione multimediali (indipendentemente dall'ambito), eseguire questo comando dall'interno di Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="ec88f-118">If you want to simultaneously enable QoS for all your media configuration settings (regardless of scope) then run this command from within the Lync Server Management Shell:</span></span>

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="ec88f-119">Puoi disabilitare QoS per i dispositivi che usano un sistema operativo diverso da Windows impostando il valore della proprietà EnableQoS su false.</span><span class="sxs-lookup"><span data-stu-id="ec88f-119">You can disable QoS for devices that use an operating system other than Windows by setting the value of the EnableQoS property to False.</span></span> <span data-ttu-id="ec88f-120">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ec88f-120">For example:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

<span data-ttu-id="ec88f-121">In questo modo puoi implementare QoS in alcune parti della rete, ad esempio nel sito Redmond, lasciando la qualità del servizio disabilitata in altre parti della rete.</span><span class="sxs-lookup"><span data-stu-id="ec88f-121">This gives you the ability to implement QoS on some portions of your network (for example, on the Redmond site) while leaving Quality of Service disabled on other portions of your network.</span></span>

<span data-ttu-id="ec88f-122">Il QoS può essere abilitato e disabilitato solo con Windows PowerShell queste opzioni non sono disponibili nel pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ec88f-122">QoS can only be enabled and disabled by using Windows PowerShell These options are not available in the Lync Server Control Panel.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


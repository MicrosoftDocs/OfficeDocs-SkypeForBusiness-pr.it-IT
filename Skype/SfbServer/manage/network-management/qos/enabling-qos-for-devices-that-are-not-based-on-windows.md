---
title: Abilitazione di QoS per i dispositivi non basati su Windows
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Informazioni su come abilitare QoS per i dispositivi usati nell'organizzazione che usano un sistema operativo diverso da Windows.
ms.openlocfilehash: adb879d2319c5eeeb84578907ce57a3a408d9a13
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188531"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a><span data-ttu-id="f62b6-103">Abilitazione di QoS in Skype for Business Server per dispositivi non basati su Windows</span><span class="sxs-lookup"><span data-stu-id="f62b6-103">Enabling QoS in Skype for Business Server for devices that are not based on Windows</span></span>


<span data-ttu-id="f62b6-104">Quando si installa Skype for Business Server, la qualità del servizio (QoS) non verrà abilitata per i dispositivi usati nell'organizzazione che usano un sistema operativo diverso da Windows.</span><span class="sxs-lookup"><span data-stu-id="f62b6-104">When you install Skype for Business Server, Quality of Service (QoS) will not be enabled for any devices used in your organization that use an operating system other than Windows.</span></span> <span data-ttu-id="f62b6-105">Puoi verificare questa operazione eseguendo il comando seguente dall'interno di Skype for business ServerManagement Shell:</span><span class="sxs-lookup"><span data-stu-id="f62b6-105">You can verify this by running the following command from within the Skype for Business ServerManagement Shell:</span></span>

    Get-CsMediaConfiguration

<span data-ttu-id="f62b6-106">Supponendo che non siano state apportate modifiche alle impostazioni di configurazione multimediali, è consigliabile recuperare le informazioni in modo simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="f62b6-106">Assuming you have not made any changes to your media configuration settings, you should get back information similar to this:</span></span>

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

<span data-ttu-id="f62b6-107">Se la proprietà EnableQoS è impostata su false (come nell'output precedente), ciò significa che la qualità del servizio non è abilitata per i computer e i dispositivi che usano un sistema operativo diverso da Windows.</span><span class="sxs-lookup"><span data-stu-id="f62b6-107">If the EnableQoS property is set to False (as in the preceding output) that means that Quality of Service is not enabled for computers and devices that use an operating system other than Windows.</span></span>

<span data-ttu-id="f62b6-108">Per abilitare la qualità del servizio nell'ambito globale, eseguire il comando seguente dall'interno di Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="f62b6-108">To enable Quality of Service at the global scope, run the following command from within the Skype for Business Server Management Shell:</span></span>

    Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="f62b6-109">Il comando precedente consente di abilitare il QoS nell'ambito globale; Tuttavia, è importante notare che le impostazioni di configurazione multimediali possono essere applicate anche all'ambito del sito.</span><span class="sxs-lookup"><span data-stu-id="f62b6-109">The preceding command enables QoS at the global scope; however, it's important to note that media configuration settings can also be applied to the site scope.</span></span> <span data-ttu-id="f62b6-110">Se è necessario abilitare la qualità del servizio per un sito, è necessario includere l'identità delle impostazioni di configurazione quando si chiama Set-CsMediaConfiguration.</span><span class="sxs-lookup"><span data-stu-id="f62b6-110">If you need to enable Quality of Service for a site, you must include the Identity of the configuration settings when calling Set-CsMediaConfiguration.</span></span> <span data-ttu-id="f62b6-111">Ad esempio, questo comando Abilita QoS per il sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="f62b6-111">For example, this command enables QoS for the Redmond site:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> <span data-ttu-id="f62b6-112">È necessario abilitare QoS nell'ambito del sito?</span><span class="sxs-lookup"><span data-stu-id="f62b6-112">Do you need to enable QoS at the site scope?</span></span> <span data-ttu-id="f62b6-113">Dipende.</span><span class="sxs-lookup"><span data-stu-id="f62b6-113">That depends.</span></span> <span data-ttu-id="f62b6-114">Le impostazioni assegnate all'ambito del sito hanno la precedenza sulle impostazioni assegnate all'ambito globale.</span><span class="sxs-lookup"><span data-stu-id="f62b6-114">Settings assigned to the site scope take precedence over settings assigned to the global scope.</span></span> <span data-ttu-id="f62b6-115">Supponiamo di avere abilitato QoS nell'ambito globale ma disabilitato nell'ambito del sito (per il sito Redmond).</span><span class="sxs-lookup"><span data-stu-id="f62b6-115">Suppose you have QoS enabled at the global scope but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="f62b6-116">In questo caso, la qualità del servizio verrebbe disabilitata per il sito Redmond; il motivo è che le impostazioni del sito hanno la precedenza.</span><span class="sxs-lookup"><span data-stu-id="f62b6-116">In that case, Quality of Service would be disabled for the Redmond site; that's because the site settings take precedence.</span></span> <span data-ttu-id="f62b6-117">Per abilitare QoS per il sito Redmond, è necessario usare le impostazioni di configurazione multimediale applicate a tale sito.</span><span class="sxs-lookup"><span data-stu-id="f62b6-117">To enable QoS for the Redmond site, you would have to do so using the media configuration settings applied to that site.</span></span>


<span data-ttu-id="f62b6-118">Se si vuole abilitare il QoS simultaneamente per tutte le impostazioni di configurazione multimediali (indipendentemente dall'ambito), eseguire questo comando dall'interno di LSkype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="f62b6-118">If you want to simultaneously enable QoS for all your media configuration settings (regardless of scope), run this command from within the LSkype for Business Server Management Shell:</span></span>

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="f62b6-119">Puoi disabilitare QoS per i dispositivi che usano un sistema operativo diverso da Windows impostando il valore della proprietà EnableQoS su false.</span><span class="sxs-lookup"><span data-stu-id="f62b6-119">You can disable QoS for devices that use an operating system other than Windows by setting the value of the EnableQoS property to False.</span></span> <span data-ttu-id="f62b6-120">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f62b6-120">For example:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

<span data-ttu-id="f62b6-121">In questo modo puoi implementare QoS in alcune parti della rete, ad esempio nel sito Redmond, lasciando la qualità del servizio disabilitata in altre parti della rete.</span><span class="sxs-lookup"><span data-stu-id="f62b6-121">This gives you the ability to implement QoS on some portions of your network (for example, on the Redmond site) while leaving Quality of Service disabled on other portions of your network.</span></span>

<span data-ttu-id="f62b6-122">Il QoS può essere abilitato e disabilitato solo con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f62b6-122">QoS can only be enabled and disabled by using Windows PowerShell.</span></span> <span data-ttu-id="f62b6-123">Queste opzioni non sono disponibili nel pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f62b6-123">These options are not available in the Skype for Business Server Control Panel.</span></span>



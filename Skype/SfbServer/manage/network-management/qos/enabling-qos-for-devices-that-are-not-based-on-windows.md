---
title: Abilitazione di QoS per dispositivi non basati su Windows
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Informazioni su come abilitare QoS per i dispositivi utilizzati nell'organizzazione che utilizzano un sistema operativo diverso da Windows.
ms.openlocfilehash: c22f9c98c796ee11d06e3d58a02a36befef4539e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814176"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a><span data-ttu-id="7a40c-103">Abilitazione del QoS in Skype for Business Server per dispositivi che non sono basati su Windows</span><span class="sxs-lookup"><span data-stu-id="7a40c-103">Enabling QoS in Skype for Business Server for devices that are not based on Windows</span></span>


<span data-ttu-id="7a40c-104">Quando si installa Skype for Business Server, la qualità del servizio (QoS) non verrà abilitata per i dispositivi utilizzati nell'organizzazione che utilizzano un sistema operativo diverso da Windows.</span><span class="sxs-lookup"><span data-stu-id="7a40c-104">When you install Skype for Business Server, Quality of Service (QoS) will not be enabled for any devices used in your organization that use an operating system other than Windows.</span></span> <span data-ttu-id="7a40c-105">È possibile verificarlo eseguendo il comando riportato di seguito dall'interno della shell di ServerManagement di Skype for business:</span><span class="sxs-lookup"><span data-stu-id="7a40c-105">You can verify this by running the following command from within the Skype for Business ServerManagement Shell:</span></span>

    Get-CsMediaConfiguration

<span data-ttu-id="7a40c-106">Presupponendo che non siano state apportate modifiche alle impostazioni di configurazione del supporto, è consigliabile recuperare informazioni simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="7a40c-106">Assuming you have not made any changes to your media configuration settings, you should get back information similar to this:</span></span>

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

<span data-ttu-id="7a40c-107">Se la proprietà EnableQoS è impostata su false (come nell'output precedente), ciò significa che la qualità del servizio non è abilitata per i computer e i dispositivi che utilizzano un sistema operativo diverso da Windows.</span><span class="sxs-lookup"><span data-stu-id="7a40c-107">If the EnableQoS property is set to False (as in the preceding output) that means that Quality of Service is not enabled for computers and devices that use an operating system other than Windows.</span></span>

<span data-ttu-id="7a40c-108">Per abilitare la qualità del servizio nell'ambito globale, eseguire il comando riportato di seguito dall'interno di Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="7a40c-108">To enable Quality of Service at the global scope, run the following command from within the Skype for Business Server Management Shell:</span></span>

    Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="7a40c-109">Il comando precedente abilita QoS nell'ambito globale, tuttavia è importante osservare che le impostazioni di configurazione dei supporti possono essere applicate anche nell'ambito del sito.</span><span class="sxs-lookup"><span data-stu-id="7a40c-109">The preceding command enables QoS at the global scope; however, it's important to note that media configuration settings can also be applied to the site scope.</span></span> <span data-ttu-id="7a40c-110">Se è necessario abilitare la qualità del servizio per un sito, è necessario includere l'identità delle impostazioni di configurazione durante la chiamata a Set-CsMediaConfiguration.</span><span class="sxs-lookup"><span data-stu-id="7a40c-110">If you need to enable Quality of Service for a site, you must include the Identity of the configuration settings when calling Set-CsMediaConfiguration.</span></span> <span data-ttu-id="7a40c-111">Questo comando, ad esempio, abilita QoS per il sito di Redmond:</span><span class="sxs-lookup"><span data-stu-id="7a40c-111">For example, this command enables QoS for the Redmond site:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> <span data-ttu-id="7a40c-112">È necessario abilitare QoS nell'ambito del sito?</span><span class="sxs-lookup"><span data-stu-id="7a40c-112">Do you need to enable QoS at the site scope?</span></span> <span data-ttu-id="7a40c-113">Dipende.</span><span class="sxs-lookup"><span data-stu-id="7a40c-113">That depends.</span></span> <span data-ttu-id="7a40c-114">Le impostazioni assegnate all'ambito del sito hanno la precedenza sulle impostazioni assegnate all'ambito globale.</span><span class="sxs-lookup"><span data-stu-id="7a40c-114">Settings assigned to the site scope take precedence over settings assigned to the global scope.</span></span> <span data-ttu-id="7a40c-115">Si supponga di disporre di QoS abilitato nell'ambito globale ma disabilitato nell'ambito del sito (per il sito Redmond).</span><span class="sxs-lookup"><span data-stu-id="7a40c-115">Suppose you have QoS enabled at the global scope but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="7a40c-116">In tal caso, la qualità del servizio verrebbe disabilitata per il sito Redmond. Questo perché le impostazioni del sito hanno la precedenza.</span><span class="sxs-lookup"><span data-stu-id="7a40c-116">In that case, Quality of Service would be disabled for the Redmond site; that's because the site settings take precedence.</span></span> <span data-ttu-id="7a40c-117">Per abilitare QoS per il sito Redmond, è necessario utilizzare le impostazioni di configurazione multimediale applicate a tale sito.</span><span class="sxs-lookup"><span data-stu-id="7a40c-117">To enable QoS for the Redmond site, you would have to do so using the media configuration settings applied to that site.</span></span>


<span data-ttu-id="7a40c-118">Se si desidera abilitare contemporaneamente QoS per tutte le impostazioni di configurazione dei contenuti multimediali (indipendentemente dall'ambito), eseguire questo comando da LSkype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="7a40c-118">If you want to simultaneously enable QoS for all your media configuration settings (regardless of scope), run this command from within the LSkype for Business Server Management Shell:</span></span>

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="7a40c-119">È possibile disabilitare QoS per i dispositivi che utilizzano un sistema operativo diverso da Windows impostando il valore della proprietà EnableQoS su false.</span><span class="sxs-lookup"><span data-stu-id="7a40c-119">You can disable QoS for devices that use an operating system other than Windows by setting the value of the EnableQoS property to False.</span></span> <span data-ttu-id="7a40c-120">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="7a40c-120">For example:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

<span data-ttu-id="7a40c-121">Questo consente di implementare QoS su alcune parti della rete, ad esempio nel sito di Redmond, e lasciarlo disabilitato su altre parti.</span><span class="sxs-lookup"><span data-stu-id="7a40c-121">This gives you the ability to implement QoS on some portions of your network (for example, on the Redmond site) while leaving Quality of Service disabled on other portions of your network.</span></span>

<span data-ttu-id="7a40c-122">La funzionalità QoS può essere abilitata e disabilitata solo tramite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7a40c-122">QoS can only be enabled and disabled by using Windows PowerShell.</span></span> <span data-ttu-id="7a40c-123">Queste opzioni non sono disponibili nel pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7a40c-123">These options are not available in the Skype for Business Server Control Panel.</span></span>

> [!NOTE]
> <span data-ttu-id="7a40c-124">I client Skype for business per iOS versione 6,17 e versioni successive supportano QoS.</span><span class="sxs-lookup"><span data-stu-id="7a40c-124">Skype for Business clients for iOS Version 6.17 and later now support QoS.</span></span>  <span data-ttu-id="7a40c-125">Questa funzionalità QoS è applicabile solo ai client Skype for business e ai dispositivi di telefonia IP che sono registrati direttamente su un server interno Skype for business o Lync pool su reti gestite.</span><span class="sxs-lookup"><span data-stu-id="7a40c-125">This QoS capability is only applicable to Skype for Business clients and IP phone devices which are registered directly to an internal Skype for Business or Lync pool Server on managed networks.</span></span> <span data-ttu-id="7a40c-126">Il QoS non è applicabile per il traffico su Internet.</span><span class="sxs-lookup"><span data-stu-id="7a40c-126">QoS is not applicable for traffic routed over the Internet.</span></span>




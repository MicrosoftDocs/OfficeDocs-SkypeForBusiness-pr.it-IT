---
title: Configurare le impostazioni di Call Park in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: Modificare le impostazioni di Call Park in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 5ce9d15c4d233e620c5eb12c18688b5df958defb
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001366"
---
# <a name="configure-call-park-settings-in-skype-for-business"></a><span data-ttu-id="02e5b-103">Configurare le impostazioni di Call Park in Skype for business</span><span class="sxs-lookup"><span data-stu-id="02e5b-103">Configure Call Park settings in Skype for Business</span></span>

<span data-ttu-id="02e5b-104">Modificare le impostazioni di Call Park in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="02e5b-104">Modify Call Park settings in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="02e5b-105">Se non si vogliono usare le impostazioni predefinite di Call Park, è possibile personalizzarle.</span><span class="sxs-lookup"><span data-stu-id="02e5b-105">If you don't want to use default Call Park settings, you can customize them.</span></span> <span data-ttu-id="02e5b-106">Quando si installa l'applicazione Call Park, le impostazioni globali sono configurate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="02e5b-106">When you install the Call Park application, global settings are configured by default.</span></span> <span data-ttu-id="02e5b-107">È possibile modificare le impostazioni globali ed è anche possibile specificare impostazioni specifiche del sito.</span><span class="sxs-lookup"><span data-stu-id="02e5b-107">You can modify the global settings, and you can also specify site-specific settings.</span></span> <span data-ttu-id="02e5b-108">Usa il cmdlet **New-CsCpsConfiguration** per creare nuove impostazioni specifiche del sito.</span><span class="sxs-lookup"><span data-stu-id="02e5b-108">Use the **New-CsCpsConfiguration** cmdlet to create new site-specific settings.</span></span> <span data-ttu-id="02e5b-109">Usare il cmdlet **Set-CsCpsConfiguration** per modificare le impostazioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="02e5b-109">Use the **Set-CsCpsConfiguration** cmdlet to modify existing settings.</span></span>

> [!NOTE]
> <span data-ttu-id="02e5b-110">È consigliabile configurare almeno l'opzione **OnTimeoutURI** per la destinazione di fallback da usare quando si verifica un timeout per una chiamata parcheggiata e la risponderia non riesce.</span><span class="sxs-lookup"><span data-stu-id="02e5b-110">At a minimum, we recommend that you configure the **OnTimeoutURI** option for the fallback destination to use when a parked call times out and ringback fails.</span></span>

<span data-ttu-id="02e5b-111">USA cmdlet **New-CsCpsConfiguration** o il cmdlet **Set-CsCpsConfiguration** per configurare una delle impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="02e5b-111">Use **New-CsCpsConfiguration** cmdlet or the **Set-CsCpsConfiguration** cmdlet to configure any of the following settings:</span></span>


| <span data-ttu-id="02e5b-112">**Questa opzione:**</span><span class="sxs-lookup"><span data-stu-id="02e5b-112">**This option:**</span></span>                     | <span data-ttu-id="02e5b-113">**Specifica questo:**</span><span class="sxs-lookup"><span data-stu-id="02e5b-113">**Specifies this:**</span></span>                                                                                                                                                                                                                                                                                                                   |
|:-------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="02e5b-114">**CallPickupTimeoutThreshold**</span><span class="sxs-lookup"><span data-stu-id="02e5b-114">**CallPickupTimeoutThreshold**</span></span> <br/> | <span data-ttu-id="02e5b-115">La quantità di tempo che trascorre dopo il parcheggio di una chiamata prima che ritorni al telefono in cui è stata risolta la chiamata.</span><span class="sxs-lookup"><span data-stu-id="02e5b-115">The amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span>  <br/> <span data-ttu-id="02e5b-116">Il valore deve essere immesso nel formato HH: mm: SS per specificare le ore, i minuti e i secondi.</span><span class="sxs-lookup"><span data-stu-id="02e5b-116">The value must be entered in the format hh:mm:ss to specify the hours, minutes, and seconds.</span></span> <span data-ttu-id="02e5b-117">Il valore minimo è di 10 secondi e il valore massimo è di 10 minuti.</span><span class="sxs-lookup"><span data-stu-id="02e5b-117">The minimum value is 10 seconds, and the maximum value is 10 minutes.</span></span> <span data-ttu-id="02e5b-118">Il valore predefinito è 00:01:30.</span><span class="sxs-lookup"><span data-stu-id="02e5b-118">The default is 00:01:30.</span></span>  <br/> |
| <span data-ttu-id="02e5b-119">**EnableMusicOnHold**</span><span class="sxs-lookup"><span data-stu-id="02e5b-119">**EnableMusicOnHold**</span></span> <br/>          | <span data-ttu-id="02e5b-120">Se la musica viene riprodotta per un chiamante mentre viene parcheggiata una chiamata.</span><span class="sxs-lookup"><span data-stu-id="02e5b-120">Whether music plays for a caller while a call is parked.</span></span>  <br/> <span data-ttu-id="02e5b-121">I valori sono true o false.</span><span class="sxs-lookup"><span data-stu-id="02e5b-121">Values are True or False.</span></span> <span data-ttu-id="02e5b-122">Il valore predefinito è true.</span><span class="sxs-lookup"><span data-stu-id="02e5b-122">The default is True.</span></span>  <br/>                                                                                                                                                                                                                 |
| <span data-ttu-id="02e5b-123">**MaxCallPickupAttempts**</span><span class="sxs-lookup"><span data-stu-id="02e5b-123">**MaxCallPickupAttempts**</span></span> <br/>      | <span data-ttu-id="02e5b-124">Il numero di squilli di una chiamata parcheggiata torna al telefono che risponde prima che venga inoltrato all'URI (Uniform Resource Identifier) di fallback specificato per **OnTimeoutURI**.</span><span class="sxs-lookup"><span data-stu-id="02e5b-124">The number of times a parked call rings back to the answering phone before it is forwarded to the fallback Uniform Resource Identifier (URI) that is specified for **OnTimeoutURI**.</span></span> <span data-ttu-id="02e5b-125">Il valore predefinito è 1.</span><span class="sxs-lookup"><span data-stu-id="02e5b-125">The default is 1.</span></span>  <br/>                                                                                                                         |
| <span data-ttu-id="02e5b-126">**OnTimeoutURI**</span><span class="sxs-lookup"><span data-stu-id="02e5b-126">**OnTimeoutURI**</span></span> <br/>               | <span data-ttu-id="02e5b-127">Indirizzo SIP dell'utente o del gruppo di risposte a cui viene instradata una chiamata parcheggiata senza risposta quando viene superato **MaxCallPickupAttempts** .</span><span class="sxs-lookup"><span data-stu-id="02e5b-127">The SIP address of the user or response group to which an unanswered parked call is routed when **MaxCallPickupAttempts** is exceeded.</span></span> <br/> <span data-ttu-id="02e5b-128">Value deve essere un URI SIP che inizia con la stringa SIP:.</span><span class="sxs-lookup"><span data-stu-id="02e5b-128">Value must be a SIP URI beginning with the string sip:.</span></span> <span data-ttu-id="02e5b-129">Ad esempio, sip:bob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="02e5b-129">For example, sip:bob@contoso.com.</span></span> <span data-ttu-id="02e5b-130">L'impostazione predefinita non è l'indirizzo di inoltro.</span><span class="sxs-lookup"><span data-stu-id="02e5b-130">The default is no forwarding address.</span></span>  <br/>                                                   |

### <a name="to-configure-call-park-settings"></a><span data-ttu-id="02e5b-131">Per configurare le impostazioni di Call Park</span><span class="sxs-lookup"><span data-stu-id="02e5b-131">To configure Call Park settings</span></span>

1. <span data-ttu-id="02e5b-132">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="02e5b-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="02e5b-133">Eseguire</span><span class="sxs-lookup"><span data-stu-id="02e5b-133">Run:</span></span>

   ```powershell
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > <span data-ttu-id="02e5b-134">Usa il cmdlet **Get-CsSite** per identificare il sito.</span><span class="sxs-lookup"><span data-stu-id="02e5b-134">Use the **Get-CsSite** cmdlet to identify the site.</span></span> <span data-ttu-id="02e5b-135">Per informazioni dettagliate, vedi documentazione di Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="02e5b-135">For details, see Skype for Business Server Management Shell documentation.</span></span>

    <span data-ttu-id="02e5b-136">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="02e5b-136">For example:</span></span>

   ```powershell
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a><span data-ttu-id="02e5b-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02e5b-137">See also</span></span>

[<span data-ttu-id="02e5b-138">Personalizzare la musica di Call Park in attesa in Skype for business 2015</span><span class="sxs-lookup"><span data-stu-id="02e5b-138">Customize Call Park music on hold inSkype for Business 2015</span></span>](customize-call-park-music-on-hold.md)

[<span data-ttu-id="02e5b-139">New-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="02e5b-139">New-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)

[<span data-ttu-id="02e5b-140">Set-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="02e5b-140">Set-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)

[<span data-ttu-id="02e5b-141">Get-CsSite</span><span class="sxs-lookup"><span data-stu-id="02e5b-141">Get-CsSite</span></span>](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)

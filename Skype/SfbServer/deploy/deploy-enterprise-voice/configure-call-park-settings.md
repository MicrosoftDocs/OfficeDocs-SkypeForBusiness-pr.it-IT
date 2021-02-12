---
title: Configurare le impostazioni del parcheggio di chiamata in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: Modificare le impostazioni del parcheggio di chiamata in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 2380c9b505ceef6ac5f4bbe04996bfdf611de39c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804116"
---
# <a name="configure-call-park-settings-in-skype-for-business"></a><span data-ttu-id="eff9a-103">Configurare le impostazioni del parcheggio di chiamata in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="eff9a-103">Configure Call Park settings in Skype for Business</span></span>

<span data-ttu-id="eff9a-104">Modificare le impostazioni del parcheggio di chiamata in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="eff9a-104">Modify Call Park settings in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="eff9a-105">Se non si desidera utilizzare le impostazioni predefinite del parcheggio di chiamata, è possibile personalizzarle.</span><span class="sxs-lookup"><span data-stu-id="eff9a-105">If you don't want to use default Call Park settings, you can customize them.</span></span> <span data-ttu-id="eff9a-106">Quando si installa l'applicazione Parcheggio di chiamata, le impostazioni globali vengono configurate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="eff9a-106">When you install the Call Park application, global settings are configured by default.</span></span> <span data-ttu-id="eff9a-107">È possibile modificarle, nonché specificare impostazioni specifiche del sito.</span><span class="sxs-lookup"><span data-stu-id="eff9a-107">You can modify the global settings, and you can also specify site-specific settings.</span></span> <span data-ttu-id="eff9a-108">Usare il cmdlet **New-CsCpsConfiguration** per creare nuove impostazioni specifiche del sito.</span><span class="sxs-lookup"><span data-stu-id="eff9a-108">Use the **New-CsCpsConfiguration** cmdlet to create new site-specific settings.</span></span> <span data-ttu-id="eff9a-109">Usare il cmdlet **Set-CsCpsConfiguration** per modificare le impostazioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="eff9a-109">Use the **Set-CsCpsConfiguration** cmdlet to modify existing settings.</span></span>

> [!NOTE]
> <span data-ttu-id="eff9a-110">È consigliabile configurare come minimo l'opzione **OnTimeoutURI** per la destinazione di fallback da utilizzare quando si verifica il timeout di una chiamata parcheggiata e la richiamata ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="eff9a-110">At a minimum, we recommend that you configure the **OnTimeoutURI** option for the fallback destination to use when a parked call times out and ringback fails.</span></span>

<span data-ttu-id="eff9a-111">Usare il cmdlet **New-CsCpsConfiguration** o il cmdlet **Set-CsCpsConfiguration** per configurare una delle impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="eff9a-111">Use **New-CsCpsConfiguration** cmdlet or the **Set-CsCpsConfiguration** cmdlet to configure any of the following settings:</span></span>


| <span data-ttu-id="eff9a-112">**Opzione:**</span><span class="sxs-lookup"><span data-stu-id="eff9a-112">**This option:**</span></span>                     | <span data-ttu-id="eff9a-113">**Descrizione:**</span><span class="sxs-lookup"><span data-stu-id="eff9a-113">**Specifies this:**</span></span>                                                                                                                                                                                                                                                                                                                   |
|:-------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="eff9a-114">**CallPickupTimeoutThreshold**</span><span class="sxs-lookup"><span data-stu-id="eff9a-114">**CallPickupTimeoutThreshold**</span></span> <br/> | <span data-ttu-id="eff9a-115">Specifica quanto tempo deve trascorrere dopo che una chiamata è stata parcheggiata prima che squilli sul telefono da cui è stata effettuata la risposta.</span><span class="sxs-lookup"><span data-stu-id="eff9a-115">The amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span>  <br/> <span data-ttu-id="eff9a-p102">Il valore deve essere immesso nel formato hh:mm:ss per specificare le ore, i minuti e i secondi. Il valore minimo è 10 secondi e il valore massimo è 10 minuti. Il valore predefinito è 00:01:30.</span><span class="sxs-lookup"><span data-stu-id="eff9a-p102">The value must be entered in the format hh:mm:ss to specify the hours, minutes, and seconds. The minimum value is 10 seconds, and the maximum value is 10 minutes. The default is 00:01:30.</span></span>  <br/> |
| <span data-ttu-id="eff9a-119">**EnableMusicOnHold**</span><span class="sxs-lookup"><span data-stu-id="eff9a-119">**EnableMusicOnHold**</span></span> <br/>          | <span data-ttu-id="eff9a-120">Specifica se viene riprodotto un brano musicale per il chiamante mentre una chiamata è parcheggiata.</span><span class="sxs-lookup"><span data-stu-id="eff9a-120">Whether music plays for a caller while a call is parked.</span></span>  <br/> <span data-ttu-id="eff9a-p103">I valori consentiti sono True o False. Il valore predefinito è True.</span><span class="sxs-lookup"><span data-stu-id="eff9a-p103">Values are True or False. The default is True.</span></span>  <br/>                                                                                                                                                                                                                 |
| <span data-ttu-id="eff9a-123">**MaxCallPickupAttempts**</span><span class="sxs-lookup"><span data-stu-id="eff9a-123">**MaxCallPickupAttempts**</span></span> <br/>      | <span data-ttu-id="eff9a-p104">Specifica per una chiamata parcheggiata il numero di squilli sul telefono da cui è stata effettuata la risposta prima che la chiamata venga inoltrata all'URI (Uniform Resource Identifier) di fallback indicato per **OnTimeoutURI**. Il valore predefinito è 1.</span><span class="sxs-lookup"><span data-stu-id="eff9a-p104">The number of times a parked call rings back to the answering phone before it is forwarded to the fallback Uniform Resource Identifier (URI) that is specified for **OnTimeoutURI**. The default is 1.  </span></span><br/>                                                                                                                         |
| <span data-ttu-id="eff9a-126">**OnTimeoutURI**</span><span class="sxs-lookup"><span data-stu-id="eff9a-126">**OnTimeoutURI**</span></span> <br/>               | <span data-ttu-id="eff9a-127">Specifica l'indirizzo SIP dell'utente o del Response Group a cui viene instradata una chiamata parcheggiata senza risposta quando viene superato il valore specificato per **MaxCallPickupAttempts**.</span><span class="sxs-lookup"><span data-stu-id="eff9a-127">The SIP address of the user or response group to which an unanswered parked call is routed when **MaxCallPickupAttempts** is exceeded.</span></span> <br/> <span data-ttu-id="eff9a-p105">Il valore deve essere un URI SIP che inizia con la stringa sip:, ad esempio sip:bob@contoso.com. Per impostazione predefinita, non viene specificato un indirizzo di inoltro.</span><span class="sxs-lookup"><span data-stu-id="eff9a-p105">Value must be a SIP URI beginning with the string sip:. For example, sip:bob@contoso.com. The default is no forwarding address.  </span></span><br/>                                                   |

### <a name="to-configure-call-park-settings"></a><span data-ttu-id="eff9a-131">Per configurare le impostazioni del parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="eff9a-131">To configure Call Park settings</span></span>

1. <span data-ttu-id="eff9a-132">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="eff9a-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="eff9a-133">Correre:</span><span class="sxs-lookup"><span data-stu-id="eff9a-133">Run:</span></span>

   ```powershell
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > <span data-ttu-id="eff9a-134">Utilizzare il cmdlet **Get-CsSite** per identificare il sito.</span><span class="sxs-lookup"><span data-stu-id="eff9a-134">Use the **Get-CsSite** cmdlet to identify the site.</span></span> <span data-ttu-id="eff9a-135">Per informazioni dettagliate, vedere la documentazione di Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="eff9a-135">For details, see Skype for Business Server Management Shell documentation.</span></span>

    <span data-ttu-id="eff9a-136">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="eff9a-136">For example:</span></span>

   ```powershell
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a><span data-ttu-id="eff9a-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eff9a-137">See also</span></span>

[<span data-ttu-id="eff9a-138">Personalizzare la musica di attesa del parcheggio di chiamata inSkype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="eff9a-138">Customize Call Park music on hold inSkype for Business 2015</span></span>](customize-call-park-music-on-hold.md)

[<span data-ttu-id="eff9a-139">New-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="eff9a-139">New-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)

[<span data-ttu-id="eff9a-140">Set-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="eff9a-140">Set-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)

[<span data-ttu-id="eff9a-141">Get-CsSite</span><span class="sxs-lookup"><span data-stu-id="eff9a-141">Get-CsSite</span></span>](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)

---
title: Configurare l'escape della segreteria telefonica in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 'Riepilogo: informazioni su come configurare la modalità di escape della segreteria telefonica in Skype for Business Server tramite Skype for Business Server Management Shell.'
ms.openlocfilehash: e372b43a0a580cd1a7b95fc3db8130a65c8398ca
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768009"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a><span data-ttu-id="41ed4-103">Configurare l'escape della segreteria telefonica in Skype for business</span><span class="sxs-lookup"><span data-stu-id="41ed4-103">Configure voice mail escape in Skype for Business</span></span>

<span data-ttu-id="41ed4-104">**Riepilogo:** Informazioni su come configurare la modalità di escape della segreteria telefonica in Skype for Business Server tramite Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="41ed4-104">**Summary:** Learn how to configure voice mail escape in Skype for Business Server by using the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="41ed4-105">Quando un utente configura lo squillo simultaneo su un telefono cellulare, il chiamante viene in genere instradato alla segreteria telefonica personale dell'utente se il telefono cellulare è disattivato, non è più alimentato dalla batteria o fuori portata.</span><span class="sxs-lookup"><span data-stu-id="41ed4-105">When a user configures simultaneous ringing to a mobile phone, a caller will typically be routed to the user's personal voice mail if the mobile phone is turned off, out of battery power, or out of range.</span></span> <span data-ttu-id="41ed4-106">Con Skype for Business Server, gli utenti possono scegliere di avere chiamate correlate alle aziende instradate al sistema di segreteria telefonica aziendale.</span><span class="sxs-lookup"><span data-stu-id="41ed4-106">With Skype for Business Server , users can opt to have business-related calls routed to their corporate voice mail system.</span></span> <span data-ttu-id="41ed4-107">In particolare, è possibile configurare un timer e, se la chiamata viene risolta dalla segreteria telefonica del vettore entro l'intervallo di tempo definito, Skype for Business Server si disconnette dal sistema di segreteria telefonica del gestore (e dalla segreteria telefonica personale dell'utente), mentre l'utente gli endpoint rimanenti nel sistema aziendale continuano a squillare.</span><span class="sxs-lookup"><span data-stu-id="41ed4-107">Specifically, a timer can be configured, and if the call is answered by the carrier's voice mail within the range of time defined, Skype for Business Server will disconnect from the carrier's voice mail system (and the user's personal voice mail), while the user's remaining endpoints in the corporate system continue to ring.</span></span> <span data-ttu-id="41ed4-108">In questo modo, il chiamante viene indirizzato automaticamente alla segreteria telefonica aziendale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="41ed4-108">This way, the caller is automatically routed to the user's corporate voice mail.</span></span>

<span data-ttu-id="41ed4-109">Questa configurazione viene eseguita usando il cmdlet di Skype for Business Server Management Shell, **Set-CsVoicePolicy**, a livello di criteri vocali, con i parametri seguenti.</span><span class="sxs-lookup"><span data-stu-id="41ed4-109">This configuration is performed using the Skype for Business Server Management Shell cmdlet, **Set-CsVoicePolicy**, at the voice policy level, with the following parameters.</span></span>

### <a name="to-configure-voice-mail-escape"></a><span data-ttu-id="41ed4-110">Per configurare l'escape della segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="41ed4-110">To configure voice mail escape</span></span>

1. <span data-ttu-id="41ed4-111">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="41ed4-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="41ed4-112">Specificare i parametri seguenti per **Set-CsVoicePolicy**:</span><span class="sxs-lookup"><span data-stu-id="41ed4-112">Specify the following parameters to **Set-CsVoicePolicy**:</span></span>

   - <span data-ttu-id="41ed4-113">**EnableVoicemailEscapeTimer** -Abilita o Disabilita il timer di escape.</span><span class="sxs-lookup"><span data-stu-id="41ed4-113">**EnableVoicemailEscapeTimer** - Enables or disables the escape timer.</span></span>

   - <span data-ttu-id="41ed4-114">**PSTNVoicemailEscapeTimer** -specifica il valore di timeout in millisecondi.</span><span class="sxs-lookup"><span data-stu-id="41ed4-114">**PSTNVoicemailEscapeTimer** - Specifies the timeout value in milliseconds.</span></span> <span data-ttu-id="41ed4-115">Il valore predefinito è 1500 millisecondi e il valore può variare da 0 millisecondi a 8000 millisecondi.</span><span class="sxs-lookup"><span data-stu-id="41ed4-115">The default value is 1500 milliseconds, and the value can range from 0 milliseconds to 8000 milliseconds.</span></span>

## <a name="example"></a><span data-ttu-id="41ed4-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="41ed4-116">Example</span></span>

```powershell
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a><span data-ttu-id="41ed4-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41ed4-117">See also</span></span>

[<span data-ttu-id="41ed4-118">Configurazione dei criteri vocali e dei record di utilizzo PSTN per autorizzare le funzionalità e i privilegi di chiamata</span><span class="sxs-lookup"><span data-stu-id="41ed4-118">Configuring Voice Policies and PSTN Usage Records to Authorize Calling Features and Privileges</span></span>](https://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)


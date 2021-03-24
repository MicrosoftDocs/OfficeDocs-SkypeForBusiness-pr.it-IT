---
title: Configurare l'escape della segreteria telefonica in Skype for Business
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
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: "Riepilogo: informazioni su come configurare l'escape della segreteria telefonica in Skype for Business Server utilizzando Skype for Business Server Management Shell."
ms.openlocfilehash: c74142cf3b0f6c9d5a871e116d8e163a095ad3cd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106372"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a><span data-ttu-id="28207-103">Configurare l'escape della segreteria telefonica in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="28207-103">Configure voice mail escape in Skype for Business</span></span>

<span data-ttu-id="28207-104">**Riepilogo:** Informazioni su come configurare l'escape della segreteria telefonica in Skype for Business Server tramite Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="28207-104">**Summary:** Learn how to configure voice mail escape in Skype for Business Server by using the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="28207-105">Quando un utente configura lo squillo simultaneo a un telefono cellulare, un chiamante in genere viene instradato alla segreteria telefonica personale dell'utente se il telefono cellulare è spento, fuori batteria o fuori portata.</span><span class="sxs-lookup"><span data-stu-id="28207-105">When a user configures simultaneous ringing to a mobile phone, a caller will typically be routed to the user's personal voice mail if the mobile phone is turned off, out of battery power, or out of range.</span></span> <span data-ttu-id="28207-106">Con Skype for Business Server, gli utenti possono scegliere di instradare le chiamate aziendali al sistema di caselle vocali aziendali.</span><span class="sxs-lookup"><span data-stu-id="28207-106">With Skype for Business Server , users can opt to have business-related calls routed to their corporate voice mail system.</span></span> <span data-ttu-id="28207-107">In particolare, è possibile configurare un timer e, se la segreteria telefonica dell'operatore risponde entro l'intervallo di tempo definito, Skype for Business Server si disconnette dal sistema di caselle vocali dell'operatore (e dalla segreteria telefonica personale dell'utente), mentre gli endpoint rimanenti dell'utente nel sistema aziendale continuano a squillare.</span><span class="sxs-lookup"><span data-stu-id="28207-107">Specifically, a timer can be configured, and if the call is answered by the carrier's voice mail within the range of time defined, Skype for Business Server will disconnect from the carrier's voice mail system (and the user's personal voice mail), while the user's remaining endpoints in the corporate system continue to ring.</span></span> <span data-ttu-id="28207-108">In questo modo, il chiamante viene automaticamente instradato alla segreteria telefonica aziendale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="28207-108">This way, the caller is automatically routed to the user's corporate voice mail.</span></span>

<span data-ttu-id="28207-109">Questa configurazione viene eseguita utilizzando il cmdlet Di Skype for Business Server Management Shell, **Set-CsVoicePolicy**, a livello di criteri vocali, con i parametri seguenti.</span><span class="sxs-lookup"><span data-stu-id="28207-109">This configuration is performed using the Skype for Business Server Management Shell cmdlet, **Set-CsVoicePolicy**, at the voice policy level, with the following parameters.</span></span>

### <a name="to-configure-voice-mail-escape"></a><span data-ttu-id="28207-110">Per configurare l'escape del sistema di caselle vocali</span><span class="sxs-lookup"><span data-stu-id="28207-110">To configure voice mail escape</span></span>

1. <span data-ttu-id="28207-111">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="28207-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="28207-112">Specificare i parametri seguenti per **Set-CsVoicePolicy**:</span><span class="sxs-lookup"><span data-stu-id="28207-112">Specify the following parameters to **Set-CsVoicePolicy**:</span></span>

   - <span data-ttu-id="28207-113">**EnableVoicemailEscapeTimer** - Consente di abilitare o disabilitare il timer di escape.</span><span class="sxs-lookup"><span data-stu-id="28207-113">**EnableVoicemailEscapeTimer** - Enables or disables the escape timer.</span></span>

   - <span data-ttu-id="28207-p102">**PSTNVoicemailEscapeTimer** - Consente di specificare il valore di timeout in millisecondi. Il valore predefinito è 1500 millisecondi e i valori consentiti sono compresi tra 0 e 8000 millisecondi.</span><span class="sxs-lookup"><span data-stu-id="28207-p102">**PSTNVoicemailEscapeTimer** - Specifies the timeout value in milliseconds. The default value is 1500 milliseconds, and the value can range from 0 milliseconds to 8000 milliseconds.</span></span>

## <a name="example"></a><span data-ttu-id="28207-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="28207-116">Example</span></span>

```powershell
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a><span data-ttu-id="28207-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28207-117">See also</span></span>

[<span data-ttu-id="28207-118">Configurazione di criteri vocali e i record utilizzo PSTN per autorizzare privilegi e caratteristiche di chiamata</span><span class="sxs-lookup"><span data-stu-id="28207-118">Configuring Voice Policies and PSTN Usage Records to Authorize Calling Features and Privileges</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges)
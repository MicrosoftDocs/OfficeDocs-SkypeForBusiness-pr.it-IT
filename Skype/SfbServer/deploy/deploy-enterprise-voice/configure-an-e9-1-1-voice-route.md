---
title: Configurare una route vocale E9-1-1 in Skype for Business Server
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
ms.assetid: 6933b840-0e7b-4509-ae43-bc9065677547
description: Configurare le route vocali E9-1-1 in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: b5f3d12bb586a65fc1c553a021c1a27efb0c7f77
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804176"
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server"></a><span data-ttu-id="41961-103">Configurare una route vocale E9-1-1 in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="41961-103">Configure an E9-1-1 voice route in Skype for Business Server</span></span>
 
<span data-ttu-id="41961-104">Configurare le route vocali E9-1-1 in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="41961-104">Configure E9-1-1 voice routes in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="41961-105">Per distribuire il servizio E9-1-1, è innanzitutto necessario configurare una route vocale per le chiamate di emergenza.</span><span class="sxs-lookup"><span data-stu-id="41961-105">To deploy E9-1-1, you first need to configure an emergency call voice route.</span></span> <span data-ttu-id="41961-106">Per informazioni dettagliate sulla creazione di route vocali, vedere [Creare o modificare una route vocale in Skype for Business.](create-or-modify-a-voice-route.md)</span><span class="sxs-lookup"><span data-stu-id="41961-106">For details about creating voice routes, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span> <span data-ttu-id="41961-107">È possibile definire più di una route, ad esempio, se nella distribuzione sono inclusi un trunk SIP primario e un trunk SIP secondario.</span><span class="sxs-lookup"><span data-stu-id="41961-107">You may define more than one route if, for example, your deployment includes a primary SIP trunk and a secondary SIP trunk.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="41961-108">Per includere informazioni sulla posizione in un messaggio INVITE E9-1-1, è necessario configurare il trunk SIP per la connessione al provider di servizi E9-1-1 in modo che esegua il routing delle chiamate di emergenza attraverso il gateway.</span><span class="sxs-lookup"><span data-stu-id="41961-108">To include location information in an E9-1-1 INVITE, you need to configure the SIP trunk that connects to the E9-1-1 service provider to route emergency calls through the gateway.</span></span> <span data-ttu-id="41961-109">A tale scopo, impostare il flag EnablePIDFLOSupport nel cmdlet **Set-CsTrunkConfiguration** su True.</span><span class="sxs-lookup"><span data-stu-id="41961-109">To do this, set the EnablePIDFLOSupport flag on the **Set-CsTrunkConfiguration** cmdlet to True.</span></span> <span data-ttu-id="41961-110">Il valore predefinito per EnablePIDFLOSupport è False.</span><span class="sxs-lookup"><span data-stu-id="41961-110">The default value for EnablePIDFLOSupport is False.</span></span> <span data-ttu-id="41961-111">Ad esempio: non è necessario abilitare le posizioni di ricezione per `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` i gateway PSTN (Public Switched Telephone Network) di fallback e i gateway ELIN (Emergency Location Identification Number).</span><span class="sxs-lookup"><span data-stu-id="41961-111">For example: `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` It is not necessary to enable receiving locations for fallback public switched telephone network (PSTN) gateways and Emergency Location Identification Number (ELIN) gateways.</span></span>
  
### <a name="to-configure-an-e9-1-1-voice-route"></a><span data-ttu-id="41961-112">Per configurare una route vocale E9-1-1</span><span class="sxs-lookup"><span data-stu-id="41961-112">To configure an E9-1-1 voice route</span></span>

1. <span data-ttu-id="41961-113">Accedere al computer con un account membro del gruppo RTCUniversalServerAdmins o del ruolo amministrativo CsVoiceAdministrator.</span><span class="sxs-lookup"><span data-stu-id="41961-113">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins groups, or a member of the CsVoiceAdministrator administrative role.</span></span>
    
2.  <span data-ttu-id="41961-114">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="41961-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="41961-115">Eseguire il cmdlet seguente per creare un nuovo record di utilizzo PSTN.</span><span class="sxs-lookup"><span data-stu-id="41961-115">Run the following cmdlet to create a new PSTN usage record.</span></span> 
    
    <span data-ttu-id="41961-116">Deve essere lo stesso nome che verrà utilizzato per l'impostazione **PSTN** nei criteri di percorso.</span><span class="sxs-lookup"><span data-stu-id="41961-116">This must be the same name that you will use for the **PSTN** setting in the location policy.</span></span> <span data-ttu-id="41961-117">Anche se nella distribuzione reale saranno disponibili più record di utilizzo del telefono, nell'esempio seguente viene aggiunto "Emergency Usage" all'elenco corrente di utilizzi PSTN disponibili.</span><span class="sxs-lookup"><span data-stu-id="41961-117">Although your deployment will have multiple phone usage records, the following example adds "Emergency Usage" to the current list of available PSTN usages.</span></span> <span data-ttu-id="41961-118">Per informazioni dettagliate, vedere Configurare i criteri vocali, i record di utilizzo [PSTN e le route vocali in Skype for Business.](voice-and-pstn.md)</span><span class="sxs-lookup"><span data-stu-id="41961-118">For details, see [Configure voice policies, PSTN usage records, and voice routes in Skype for Business](voice-and-pstn.md).</span></span>
    
   ```powershell
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. <span data-ttu-id="41961-119">Eseguire il cmdlet seguente per creare una nuova route vocale con il record di utilizzo PSTN creato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="41961-119">Run the following cmdlet to create a new voice route by using the PSTN usage record that you created in the previous step.</span></span>
    
    <span data-ttu-id="41961-120">Il formato del numero deve essere lo stesso utilizzato nell'impostazione **Maschera di composizione di emergenza** nei criteri di percorso.</span><span class="sxs-lookup"><span data-stu-id="41961-120">The number pattern must be the same number pattern that is used in the **Emergency Dial String** setting in the location policy.</span></span> <span data-ttu-id="41961-121">È necessario un segno "+" perché Skype for Business aggiunge "+" alle chiamate di emergenza.</span><span class="sxs-lookup"><span data-stu-id="41961-121">A "+" sign is needed because Skype for Business adds "+" to emergency calls.</span></span> <span data-ttu-id="41961-122">"Co1-pstngateway-1" è l'ID di servizio del trunk SIP per il provider di servizi E9-1-1 o l'ID di servizio del gateway ELIN.</span><span class="sxs-lookup"><span data-stu-id="41961-122">"Co1-pstngateway-1" is the SIP trunk service ID for the E9-1-1 service provider or for the ELIN gateway service ID.</span></span> <span data-ttu-id="41961-123">Nell'esempio seguente viene utilizzato il nome "EmergencyRoute" per la route vocale.</span><span class="sxs-lookup"><span data-stu-id="41961-123">The following example uses "EmergencyRoute" as the name of the voice route.</span></span>
    
   ```powershell
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}
   ```

5. <span data-ttu-id="41961-124">Facoltativamente, per le connessioni trunk SIP, è consigliabile eseguire il cmdlet seguente per creare una route locale per le chiamate non gestite dal trunk SIP del provider di servizi E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="41961-124">Optionally, for SIP trunk connections, we recommend that you run the following cmdlet to create a local route for calls that are not handled by the E9-1-1 service provider's SIP trunk.</span></span> <span data-ttu-id="41961-125">Questa route verrà utilizzata se la connessione al provider di servizi E9-1-1 non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="41961-125">This route will be used if the connection to the E9-1-1 service provider is not available.</span></span> 
    
    <span data-ttu-id="41961-126">Nell'esempio seguente si presuppone che i criteri vocali dell'utente includano l'utilizzo 'Local'.</span><span class="sxs-lookup"><span data-stu-id="41961-126">The following example assumes that user has "Local" usage in their voice policy.</span></span>
    
   ```powershell
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```



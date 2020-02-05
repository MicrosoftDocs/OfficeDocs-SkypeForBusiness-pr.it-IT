---
title: Configurare una route vocale E9-1-1 in Skype for Business Server
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
ms.assetid: 6933b840-0e7b-4509-ae43-bc9065677547
description: Configurare le route vocali E9-1-1 in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: ca45ac924ce987113e5b88729dc074b112668caf
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768149"
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server"></a><span data-ttu-id="90cdf-103">Configurare una route vocale E9-1-1 in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="90cdf-103">Configure an E9-1-1 voice route in Skype for Business Server</span></span>
 
<span data-ttu-id="90cdf-104">Configurare le route vocali E9-1-1 in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="90cdf-104">Configure E9-1-1 voice routes in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="90cdf-105">Per distribuire E9-1-1, è prima di tutto necessario configurare una route vocale per le chiamate di emergenza.</span><span class="sxs-lookup"><span data-stu-id="90cdf-105">To deploy E9-1-1, you first need to configure an emergency call voice route.</span></span> <span data-ttu-id="90cdf-106">Per informazioni dettagliate sulla creazione di route vocali, vedere [creare o modificare una route vocale in Skype for business](create-or-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="90cdf-106">For details about creating voice routes, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span> <span data-ttu-id="90cdf-107">Puoi definire più di una route se, ad esempio, la distribuzione include un trunk SIP principale e un trunk SIP secondario.</span><span class="sxs-lookup"><span data-stu-id="90cdf-107">You may define more than one route if, for example, your deployment includes a primary SIP trunk and a secondary SIP trunk.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="90cdf-108">Per includere le informazioni sulla posizione in un invito di E9-1-1, è necessario configurare il trunk SIP che si connette al provider di servizi E9-1-1 per instradare le chiamate di emergenza tramite il gateway.</span><span class="sxs-lookup"><span data-stu-id="90cdf-108">To include location information in an E9-1-1 INVITE, you need to configure the SIP trunk that connects to the E9-1-1 service provider to route emergency calls through the gateway.</span></span> <span data-ttu-id="90cdf-109">A questo scopo, imposta il contrassegno EnablePIDFLOSupport sul cmdlet **Set-CsTrunkConfiguration** su true.</span><span class="sxs-lookup"><span data-stu-id="90cdf-109">To do this, set the EnablePIDFLOSupport flag on the **Set-CsTrunkConfiguration** cmdlet to True.</span></span> <span data-ttu-id="90cdf-110">Il valore predefinito per EnablePIDFLOSupport è false.</span><span class="sxs-lookup"><span data-stu-id="90cdf-110">The default value for EnablePIDFLOSupport is False.</span></span> <span data-ttu-id="90cdf-111">Ad esempio `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` , non è necessario abilitare le posizioni di ricezione per i gateway PSTN (Public Switched Telephone Network) di fallback e i gateway ELIN (Emergency Location Identification Number).</span><span class="sxs-lookup"><span data-stu-id="90cdf-111">For example: `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` It is not necessary to enable receiving locations for fallback public switched telephone network (PSTN) gateways and Emergency Location Identification Number (ELIN) gateways.</span></span>
  
### <a name="to-configure-an-e9-1-1-voice-route"></a><span data-ttu-id="90cdf-112">Per configurare una route vocale E9-1-1</span><span class="sxs-lookup"><span data-stu-id="90cdf-112">To configure an E9-1-1 voice route</span></span>

1. <span data-ttu-id="90cdf-113">Accedere al computer con un account membro dei gruppi RTCUniversalServerAdmins o un membro del ruolo di amministratore di CsVoiceAdministrator.</span><span class="sxs-lookup"><span data-stu-id="90cdf-113">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins groups, or a member of the CsVoiceAdministrator administrative role.</span></span>
    
2.  <span data-ttu-id="90cdf-114">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="90cdf-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="90cdf-115">Eseguire il cmdlet seguente per creare un nuovo record di utilizzo PSTN.</span><span class="sxs-lookup"><span data-stu-id="90cdf-115">Run the following cmdlet to create a new PSTN usage record.</span></span> 
    
    <span data-ttu-id="90cdf-116">Deve essere lo stesso nome che verrà usato per l'impostazione **PSTN** nei criteri di posizione.</span><span class="sxs-lookup"><span data-stu-id="90cdf-116">This must be the same name that you will use for the **PSTN** setting in the location policy.</span></span> <span data-ttu-id="90cdf-117">Anche se la distribuzione avrà più record utilizzo telefono, nell'esempio seguente viene aggiunto "utilizzo delle emergenze" all'elenco corrente degli usi PSTN disponibili.</span><span class="sxs-lookup"><span data-stu-id="90cdf-117">Although your deployment will have multiple phone usage records, the following example adds "Emergency Usage" to the current list of available PSTN usages.</span></span> <span data-ttu-id="90cdf-118">Per informazioni dettagliate, vedere [configurare i criteri vocali, i record di utilizzo PSTN e le route vocali in Skype for business](voice-and-pstn.md).</span><span class="sxs-lookup"><span data-stu-id="90cdf-118">For details, see [Configure voice policies, PSTN usage records, and voice routes in Skype for Business](voice-and-pstn.md).</span></span>
    
   ```powershell
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. <span data-ttu-id="90cdf-119">Eseguire il cmdlet seguente per creare una nuova route vocale usando il record di utilizzo PSTN creato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="90cdf-119">Run the following cmdlet to create a new voice route by using the PSTN usage record that you created in the previous step.</span></span>
    
    <span data-ttu-id="90cdf-120">Il pattern numerico deve essere lo stesso modello di numero usato nell'impostazione della **stringa di chiamata di emergenza** nei criteri di posizione.</span><span class="sxs-lookup"><span data-stu-id="90cdf-120">The number pattern must be the same number pattern that is used in the **Emergency Dial String** setting in the location policy.</span></span> <span data-ttu-id="90cdf-121">È necessario un segno "+" perché Skype for business aggiunge "+" alle chiamate di emergenza.</span><span class="sxs-lookup"><span data-stu-id="90cdf-121">A "+" sign is needed because Skype for Business adds "+" to emergency calls.</span></span> <span data-ttu-id="90cdf-122">"Co1-pstngateway-1" è l'ID del servizio trunk SIP per il provider di servizi E9-1-1 o per l'ID del servizio gateway ELIN.</span><span class="sxs-lookup"><span data-stu-id="90cdf-122">"Co1-pstngateway-1" is the SIP trunk service ID for the E9-1-1 service provider or for the ELIN gateway service ID.</span></span> <span data-ttu-id="90cdf-123">L'esempio seguente usa "EmergencyRoute" come nome della route vocale.</span><span class="sxs-lookup"><span data-stu-id="90cdf-123">The following example uses "EmergencyRoute" as the name of the voice route.</span></span>
    
   ```powershell
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}
   ```

5. <span data-ttu-id="90cdf-124">Facoltativamente, per le connessioni trunk SIP, è consigliabile eseguire il cmdlet seguente per creare una route locale per le chiamate non gestite dal trunk SIP del provider di servizi E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="90cdf-124">Optionally, for SIP trunk connections, we recommend that you run the following cmdlet to create a local route for calls that are not handled by the E9-1-1 service provider's SIP trunk.</span></span> <span data-ttu-id="90cdf-125">Questa route verrà usata se la connessione al provider di servizi E9-1-1 non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="90cdf-125">This route will be used if the connection to the E9-1-1 service provider is not available.</span></span> 
    
    <span data-ttu-id="90cdf-126">L'esempio seguente presuppone che l'utente abbia un uso "locale" nei criteri vocali.</span><span class="sxs-lookup"><span data-stu-id="90cdf-126">The following example assumes that user has "Local" usage in their voice policy.</span></span>
    
   ```powershell
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```



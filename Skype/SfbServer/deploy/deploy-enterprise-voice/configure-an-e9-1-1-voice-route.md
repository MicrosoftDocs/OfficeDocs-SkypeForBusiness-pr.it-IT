---
title: Configurare una route vocale E9-1-1 in Skype for Business Server
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
ms.assetid: 6933b840-0e7b-4509-ae43-bc9065677547
description: Configurare le route vocali E9-1-1 in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: a8121cc7a7345150e485dc2e2b81e062672f5703
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233942"
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server"></a>Configurare una route vocale E9-1-1 in Skype for Business Server
 
Configurare le route vocali E9-1-1 in Skype for Business Server VoIP aziendale. 
  
Per distribuire E9-1-1, è prima di tutto necessario configurare una route vocale per le chiamate di emergenza. Per informazioni dettagliate sulla creazione di route vocali, vedere [creare o modificare una route vocale in Skype for business](create-or-modify-a-voice-route.md). Puoi definire più di una route se, ad esempio, la distribuzione include un trunk SIP principale e un trunk SIP secondario. 
  
> [!NOTE]
> Per includere le informazioni sulla posizione in un invito di E9-1-1, è necessario configurare il trunk SIP che si connette al provider di servizi E9-1-1 per instradare le chiamate di emergenza tramite il gateway. A questo scopo, imposta il contrassegno EnablePIDFLOSupport sul cmdlet **Set-CsTrunkConfiguration** su true. Il valore predefinito per EnablePIDFLOSupport è false. Ad esempio `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` , non è necessario abilitare le posizioni di ricezione per i gateway PSTN (Public Switched Telephone Network) di fallback e i gateway ELIN (Emergency Location Identification Number).
  
### <a name="to-configure-an-e9-1-1-voice-route"></a>Per configurare una route vocale E9-1-1

1. Accedere al computer con un account membro dei gruppi RTCUniversalServerAdmins o un membro del ruolo di amministratore di CsVoiceAdministrator.
    
2.  Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
3. Eseguire il cmdlet seguente per creare un nuovo record di utilizzo PSTN. 
    
    Deve essere lo stesso nome che verrà usato per l'impostazione **PSTN** nei criteri di posizione. Anche se la distribuzione avrà più record utilizzo telefono, nell'esempio seguente viene aggiunto "utilizzo delle emergenze" all'elenco corrente degli usi PSTN disponibili. Per informazioni dettagliate, vedere [configurare i criteri vocali, i record di utilizzo PSTN e le route vocali in Skype for business](voice-and-pstn.md).
    
   ```
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. Eseguire il cmdlet seguente per creare una nuova route vocale usando il record di utilizzo PSTN creato nel passaggio precedente.
    
    Il pattern numerico deve essere lo stesso modello di numero usato nell'impostazione della **stringa di chiamata di emergenza** nei criteri di posizione. È necessario un segno "+" perché Skype for business aggiunge "+" alle chiamate di emergenza. "Co1-pstngateway-1" è l'ID del servizio trunk SIP per il provider di servizi E9-1-1 o per l'ID del servizio gateway ELIN. L'esempio seguente usa "EmergencyRoute" come nome della route vocale.
    
   ```
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}
   ```

5. Facoltativamente, per le connessioni trunk SIP, è consigliabile eseguire il cmdlet seguente per creare una route locale per le chiamate non gestite dal trunk SIP del provider di servizi E9-1-1. Questa route verrà usata se la connessione al provider di servizi E9-1-1 non è disponibile. 
    
    L'esempio seguente presuppone che l'utente abbia un uso "locale" nei criteri vocali.
    
   ```
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```



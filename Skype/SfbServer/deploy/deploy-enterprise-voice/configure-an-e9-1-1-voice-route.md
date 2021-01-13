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
description: Configurare le route vocali di E9-1-1 in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: b5f3d12bb586a65fc1c553a021c1a27efb0c7f77
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804176"
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server"></a>Configurare una route vocale E9-1-1 in Skype for Business Server
 
Configurare le route vocali di E9-1-1 in Skype for Business Server VoIP aziendale. 
  
Per distribuire il servizio E9-1-1, è innanzitutto necessario configurare una route vocale per le chiamate di emergenza. Per informazioni dettagliate sulla creazione di route vocali, vedere [creare o modificare una route vocale in Skype for business](create-or-modify-a-voice-route.md). È possibile definire più di una route, ad esempio, se nella distribuzione sono inclusi un trunk SIP primario e un trunk SIP secondario. 
  
> [!NOTE]
> Per includere informazioni sulla posizione in un messaggio INVITE E9-1-1, è necessario configurare il trunk SIP per la connessione al provider di servizi E9-1-1 in modo che esegua il routing delle chiamate di emergenza attraverso il gateway. A tale scopo, impostare il flag EnablePIDFLOSupport nel cmdlet **Set-CsTrunkConfiguration** su True. Il valore predefinito per EnablePIDFLOSupport è False. Ad esempio, `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` non è necessario abilitare le posizioni di ricezione per i gateway PSTN (Public Switched Telephone Network) e i gateway ELIN (Emergency Location Identification Number).
  
### <a name="to-configure-an-e9-1-1-voice-route"></a>Per configurare una route vocale E9-1-1

1. Accedere al computer con un account membro del gruppo RTCUniversalServerAdmins o del ruolo amministrativo CsVoiceAdministrator.
    
2.  Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.
    
3. Eseguire il cmdlet seguente per creare un nuovo record di utilizzo PSTN. 
    
    Deve essere lo stesso nome che verrà utilizzato per l'impostazione **PSTN** nei criteri di percorso. Anche se nella distribuzione reale saranno disponibili più record di utilizzo del telefono, nell'esempio seguente viene aggiunto "Emergency Usage" all'elenco corrente di utilizzi PSTN disponibili. Per informazioni dettagliate, vedere [configurare i criteri vocali, i record di utilizzo PSTN e le route vocali in Skype for business](voice-and-pstn.md).
    
   ```powershell
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. Eseguire il cmdlet seguente per creare una nuova route vocale con il record di utilizzo PSTN creato nel passaggio precedente.
    
    Il formato del numero deve essere lo stesso utilizzato nell'impostazione **Maschera di composizione di emergenza** nei criteri di percorso. È necessario un segno di "+" perché Skype for business aggiunge "+" alle chiamate di emergenza. "Co1-pstngateway-1" è l'ID di servizio del trunk SIP per il provider di servizi E9-1-1 o l'ID di servizio del gateway ELIN. Nell'esempio seguente viene utilizzato il nome "EmergencyRoute" per la route vocale.
    
   ```powershell
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}
   ```

5. Facoltativamente, per le connessioni trunk SIP, è consigliabile eseguire il cmdlet seguente per creare una route locale per le chiamate non gestite dal trunk SIP del provider di servizi E9-1-1. Questa route verrà utilizzata se la connessione al provider di servizi E9-1-1 non è disponibile. 
    
    Nell'esempio seguente si presuppone che i criteri vocali dell'utente includano l'utilizzo 'Local'.
    
   ```powershell
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```



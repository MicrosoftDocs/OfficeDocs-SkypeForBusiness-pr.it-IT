---
title: Creare criteri percorso in Skype for Business Server
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
ms.assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
description: Leggere questo argomento per informazioni su come configurare i criteri percorso del servizio di emergenza avanzato (E9-1-1) in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 46bd1167f573f1d43689d5d4ff145823dafa94a2ec64697e9c20a234b341619d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340282"
---
# <a name="create-location-policies-in-skype-for-business-server"></a>Creare criteri percorso in Skype for Business Server

Leggere questo argomento per informazioni su come configurare i criteri percorso del servizio di emergenza avanzato (E9-1-1) in Skype for Business Server VoIP aziendale. 

Skype for Business Server utilizza un criterio percorso per abilitare Skype for Business client per E9-1-1 durante la registrazione del client. I criteri percorso contengono le impostazioni che definiscono la modalità di implementazione di E9-1-1. Per ulteriori informazioni, vedere [Plan location policies for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).

È possibile definire i criteri percorso utilizzando Skype for Business pannello di controllo o il cmdlet [New-CsLocationPolicy.](/powershell/module/skype/new-cslocationpolicy?view=skype-ps)

> [!NOTE]
> Skype for Business Server ora supporta la configurazione di più numeri di emergenza per un client. Se si desidera configurare più numeri di emergenza, è necessario seguire le informazioni in Pianificare più numeri di emergenza [in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) e Configurare più numeri di emergenza [in Skype for Business](configure-multiple-emergency-numbers.md). 

È possibile modificare i criteri percorso globali e creare nuovi criteri percorso contrassegnati. Un client ottiene criteri globali quando non si trova in una subnet con criteri percorso associati oppure quando non è stato assegnato direttamente a criteri percorso. I criteri contrassegnati vengono assegnati a subnet o a utenti. 

Per creare criteri percorso, è necessario utilizzare un account membro del gruppo RTCUniversalServerAdmins o del ruolo amministrativo CsVoiceAdministrator oppure che disponga di equivalenti diritti e autorizzazioni di amministratore.

Per ulteriori informazioni, vedere [Plan location policies for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md). I cmdlet di questa procedura utilizzano un criterio percorso definito utilizzando i valori seguenti. Per una descrizione completa dei parametri e dei valori dei cmdlet, [vedere New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps).


| **Elemento**                               | **Valore**                                                                                                                                                                          |
|:------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| EnhancedEmergencyServicesEnabled  <br/>   | **Vero** <br/>                                                                                                                                                                     |
| LocationRequired  <br/>                   | **Dichiarazione di non responsabilità** <br/>                                                                                                                                                               |
| EnhancedEmergencyServiceDisclaimer  <br/> | È necessario impostare un percorso per il criterio aziendale. Se non si imposta un percorso, in caso di emergenza non sarà possibile essere individuati dai servizi di emergenza. Impostare un percorso.  <br/> |
| UseLocationForE911Only  <br/>             | **Falso** <br/>                                                                                                                                                                    |
| PstnUsage  <br/>                          | **EmergencyUsage** <br/>                                                                                                                                                           |
| EmergencyDialString  <br/>                | **911** <br/>                                                                                                                                                                      |
| EmergencyDialMask  <br/>                  | **112** <br/>                                                                                                                                                                      |
| NotificationUri  <br/>                    | <strong>sip:security@litwareinc.com</strong> <br/>                                                                                                                                 |
| ConferenceUri  <br/>                      | <strong>sip:+14255550123@litwareinc.com</strong> <br/>                                                                                                                             |
| ConferenceMode  <br/>                     | **twoway** <br/>                                                                                                                                                                   |
| LocationRefreshInterval  <br/>            | **2** <br/>                                                                                                                                                                        |

### <a name="to-create-location-policies"></a>Per creare criteri percorso

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi fare clic su **Skype for Business Server Management Shell.**

    > [!NOTE]
    > CsLocationPolicy non verrà eseguito correttamente se l'impostazione di **PstnUsage** non è già stata inserita nell'elenco Global di PstnUsages.

2. Facoltativamente, eseguire il cmdlet seguente per modificare i criteri percorso globali:

   ```powershell
   Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2
   ```

3. Eseguire il cmdlet seguente per creare criteri percorso contrassegnati.

   ```powershell
   New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2
   ```

4. Eseguire il cmdlet seguente per applicare i criteri percorso creati nel passaggio 3 ai criteri di un utente.

   ```powershell
   (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond
   ```
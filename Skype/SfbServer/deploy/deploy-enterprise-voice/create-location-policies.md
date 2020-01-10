---
title: Creare criteri di posizione in Skype for Business Server
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
ms.assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
description: Leggere questo argomento per informazioni su come configurare i criteri di posizione avanzati del servizio di emergenza (E9-1-1) in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: b7511de949e1c67fdf7a828d06826d22826f5694
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41000876"
---
# <a name="create-location-policies-in-skype-for-business-server"></a>Creare criteri di posizione in Skype for Business Server

Leggere questo argomento per informazioni su come configurare i criteri di posizione avanzati del servizio di emergenza (E9-1-1) in Skype for Business Server VoIP aziendale. 

Skype for Business Server usa un criterio di posizione per abilitare i client Skype for business per il E9-1-1 durante la registrazione client. Un criterio di posizione contiene le impostazioni che definiscono il modo in cui verrà implementato E9-1-1. Per altre informazioni, Vedi [pianificare i criteri di posizione per Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).

Puoi definire i criteri di posizione usando il pannello di controllo di Skype for business o usando il cmdlet [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) .

> [!NOTE]
> Skype for Business Server ora supporta la configurazione di più numeri di emergenza per un client. Se si vogliono configurare più numeri di emergenza, è necessario seguire le informazioni in [piano per i numeri di emergenza multipli in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) e [configurare più numeri di emergenza in Skype for business](configure-multiple-emergency-numbers.md). 

È possibile modificare i criteri di posizione globale e creare nuovi criteri di posizione contrassegnati. Un client ottiene un criterio globale quando non si trova all'interno di una subnet con un criterio di posizione associato o quando al client non è stato assegnato direttamente un criterio di posizione. I criteri contrassegnati vengono assegnati a subnet o utenti. 

Per creare un criterio di posizione, è necessario usare un account che sia membro del gruppo RTCUniversalServerAdmins oppure sia un membro del ruolo amministrativo di CsVoiceAdministrator o disponga di autorizzazioni e diritti di amministratore equivalenti.

Per altre informazioni, Vedi [pianificare i criteri di posizione per Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md). I cmdlet in questa procedura usano i criteri di posizione definiti con i valori seguenti. Per una descrizione completa di parametri e valori dei cmdlet, vedere [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps).


| **Elemento**                               | **Valore**                                                                                                                                                                          |
|:------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| EnhancedEmergencyServicesEnabled  <br/>   | **True** <br/>                                                                                                                                                                     |
| LocationRequired  <br/>                   | **Dichiarazione di non responsabilità** <br/>                                                                                                                                                               |
| EnhancedEmergencyServiceDisclaimer  <br/> | I criteri aziendali richiedono l'impostazione di una posizione. Se non si imposta una posizione, i servizi di emergenza non saranno in grado di individuare l'utente in caso di emergenza. Impostare una posizione.  <br/> |
| UseLocationForE911Only  <br/>             | **False** <br/>                                                                                                                                                                    |
| PstnUsage  <br/>                          | **EmergencyUsage** <br/>                                                                                                                                                           |
| EmergencyDialString  <br/>                | **911** <br/>                                                                                                                                                                      |
| EmergencyDialMask  <br/>                  | **112** <br/>                                                                                                                                                                      |
| NotificationUri  <br/>                    | <strong>sip:security@litwareinc.com</strong> <br/>                                                                                                                                 |
| ConferenceUri  <br/>                      | <strong>sip:+14255550123@litwareinc.com</strong> <br/>                                                                                                                             |
| ConferenceMode  <br/>                     | **TwoWay** <br/>                                                                                                                                                                   |
| LocationRefreshInterval  <br/>            | **2** <br/>                                                                                                                                                                        |

### <a name="to-create-location-policies"></a>Per creare criteri di posizione

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.

    > [!NOTE]
    > CsLocationPolicy non riesce se l'impostazione per **PstnUsage** non è già presente nell'elenco globale di PstnUsages.

2. Facoltativamente, eseguire il cmdlet seguente per modificare il criterio della posizione globale:

   ```powershell
   Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2
   ```

3. Eseguire la procedura seguente per creare criteri di posizione contrassegnati.

   ```powershell
   New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2
   ```

4. Eseguire il cmdlet seguente per applicare il criterio di posizione con tag creato nel passaggio 3 a un criterio utente.

   ```powershell
   (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond
   ```

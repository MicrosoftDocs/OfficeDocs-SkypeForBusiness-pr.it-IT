---
title: Gestire il mapping dei tasti per i comandi DTMF in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f91e80ee-a587-4a1b-ac8f-12fa102c098c
description: 'Riepilogo: informazioni su come gestire il mapping delle chiavi dei comandi DTMF (Dual-Tone Multi-Frequency) in Skype for Business Server.'
ms.openlocfilehash: fdb9846da81c4029fa67df606fa021397a46b3ad
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818537"
---
# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server"></a>Gestire il mapping dei tasti per i comandi DTMF in Skype for Business Server
 
**Riepilogo:** Informazioni su come gestire il mapping delle chiavi dei comandi DTMF (Dual-Tone Multi-Frequency) in Skype for Business Server.
  
Gli utenti dei servizi di conferenza telefonica con accesso esterno possono premere i tasti sul tastierino telefonico per eseguire i comandi DTMF (Dual-Tone Multi-Frequency). I comandi DTMF consentono agli utenti che effettuano la chiamata a una conferenza di controllare le impostazioni della conferenza, ad esempio disattivare e riattivare il segnale, o bloccare o sbloccare la conferenza, usando la tastiera del telefono. 
  
Per gestire le chiavi usate per i comandi DTMF, USA Skype for Business Server Management Shell con i cmdlet **Get-CsDialInConferencingDtmfConfiguration**, **Set-CsDialInConferencingDtmfConfiguration**e **New-CsDialInConferencingDtmfConfiguration** .
  
Quando si creano nuove impostazioni DTMF per i siti, le impostazioni del sito hanno la precedenza sulle impostazioni globali. 

### <a name="manage-the-key-mapping-of-dtmf-commands"></a>Gestire il mapping delle chiavi dei comandi DTMF

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo Cs-ServerAdministrator o CsAdministrator.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
3. Per visualizzare le impostazioni DTMF usate per i servizi di conferenza telefonica con accesso esterno, eseguire il comando seguente al prompt dei comandi:
    
   ```PowerShell
   Get-CsDialinConferencingDtmfConfiguration
   ```

4. Per modificare le impostazioni DTMF usate per i servizi di conferenza telefonica con accesso esterno, eseguire il cmdlet seguente e specificare il tasto da premere per ogni opzione che si vuole modificare:
    
   ```PowerShell
   Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
   [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
   [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
   [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
   [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
   ```

5. Opzionale Per creare altri set di comandi DTMF per siti specifici, usare il cmdlet **New-CsDialInConferencingDtmfConfiguration** con un'identità del sito.
    
L'esempio seguente scambia il tasto premuto per abilitare o disabilitare gli annunci e la chiave che viene premuta per disattivare e riattivare l'audio di tutti i partecipanti. Poiché non è specificata alcuna identità, le modifiche apportate alle impostazioni DTMF globali sono valide:
  
```PowerShell
Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
```

Per altre informazioni, vedere [Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps), [Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)e [New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps).
  


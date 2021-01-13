---
title: Gestire il mapping dei tasti per i comandi DTMF in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f91e80ee-a587-4a1b-ac8f-12fa102c098c
description: 'Riepilogo: informazioni su come gestire il mapping dei tasti per i comandi DTMF (Dual-Tone Multi-Frequency) in Skype for Business Server.'
ms.openlocfilehash: b804c9a0923630f6de3d1b5af2acdda123cc6331
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828096"
---
# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server"></a>Gestire il mapping dei tasti per i comandi DTMF in Skype for Business Server
 
**Riepilogo:** Informazioni su come gestire il mapping dei tasti per i comandi DTMF (Dual-Tone Multi-Frequency) in Skype for Business Server.
  
Gli utenti delle conferenze telefoniche con accesso esterno possono premere i tasti sul tastierino del telefono per eseguire i comandi DTMF (Dual-Tone Multi-Frequency). I comandi DTMF consentono agli utenti che accedono a una conferenza di controllare le impostazioni di conferenza, ad esempio il muting e la riattivazione o il blocco e lo sblocco della conferenza, tramite la tastiera del telefono. 
  
Per gestire le chiavi utilizzate per i comandi DTMF, utilizzare la shell di gestione di Skype for Business Server con i cmdlet **Get-CsDialInConferencingDtmfConfiguration**, **Set-CsDialInConferencingDtmfConfiguration** e **New-CsDialInConferencingDtmfConfiguration** .
  
Quando si creano nuove impostazioni DTMF per i siti, le impostazioni del sito hanno la precedenza sulle impostazioni globali. 

### <a name="manage-the-key-mapping-of-dtmf-commands"></a>Gestire il mapping dei tasti per i comandi DTMF

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo Cs-ServerAdministrator o CsAdministrator.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.
    
3. Per visualizzare le impostazioni DTMF utilizzate per le conferenze telefoniche con accesso esterno, eseguire il comando seguente al prompt dei comandi:
    
   ```PowerShell
   Get-CsDialinConferencingDtmfConfiguration
   ```

4. Per modificare le impostazioni DTMF utilizzate per le conferenze telefoniche con accesso esterno, eseguire il cmdlet seguente e specificare il tasto da premere per ogni opzione che si desidera modificare:
    
   ```PowerShell
   Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
   [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
   [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
   [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
   [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
   ```

5. Optional Per creare ulteriori insiemi di comandi DTMF per siti specifici, utilizzare il cmdlet **New-CsDialInConferencingDtmfConfiguration** con un'identità del sito.
    
Nell'esempio seguente viene scambiato il tasto premuto per abilitare o disabilitare gli annunci e il tasto premuto per disattivare e riattivare l'audio di tutti i partecipanti. Poiché non viene specificata alcuna identità, queste modifiche sono valide per le impostazioni DTMF globali:
  
```PowerShell
Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
```

Per ulteriori informazioni, vedere [Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps), [Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)e [New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps).
  


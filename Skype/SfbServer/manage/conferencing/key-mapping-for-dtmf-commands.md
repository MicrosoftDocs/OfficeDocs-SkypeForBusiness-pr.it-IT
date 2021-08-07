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
description: 'Riepilogo: informazioni su come gestire il mapping dei tasti dei comandi DTMF (Dual Tone Multi-Frequency) in Skype for Business Server.'
ms.openlocfilehash: 106cd301826792ec494df4d490a6b953baf3badd1740d9cfd2de12e6de966d09
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54276851"
---
# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server"></a>Gestire il mapping dei tasti per i comandi DTMF in Skype for Business Server
 
**Riepilogo:** Informazioni su come gestire il mapping dei tasti dei comandi DTMF (Dual Tone Multi-Frequency) in Skype for Business Server.
  
Gli utenti delle conferenze telefoniche con accesso esterno possono premere i tasti sulla tastiera del telefono per eseguire comandi DTMF (Dual-Tone Multi-Frequency). I comandi DTMF consentono agli utenti che affollano una conferenza di controllare le impostazioni della conferenza (ad esempio, la disattivazione e l'attivazione dell'audio o il blocco e lo sblocco della conferenza) utilizzando la tastiera del telefono. 
  
Per gestire le chiavi utilizzate per i comandi DTMF, utilizzare Skype for Business Server Management Shell con i cmdlet **Get-CsDialinConferencingDtmfConfiguration,** **Set-CsDialinConferencingDtmfConfiguration** e **New-CsDialinConferencingDtmfConfiguration.**
  
Quando si creano nuove impostazioni DTMF per i siti, le impostazioni del sito hanno la precedenza sulle impostazioni globali. 

### <a name="manage-the-key-mapping-of-dtmf-commands"></a>Gestire il mapping dei tasti dei comandi DTMF

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo Cs-ServerAdministrator o CsAdministrator.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi fare clic su **Skype for Business Server Management Shell.**
    
3. Per visualizzare le impostazioni DTMF utilizzate per le conferenze telefoniche con accesso esterno, al prompt dei comandi eseguire il comando seguente:
    
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

5. (Facoltativo) Per creare set aggiuntivi di comandi DTMF per siti specifici, utilizzare il cmdlet **New-CsDialinConferencingDtmfConfiguration** con un'identità di sito.
    
Nell'esempio seguente viene scambiato il tasto premuto per abilitare o disabilitare gli annunci e il tasto premuto per disattivare e riattivare l'audio di tutti i partecipanti. Poiché non viene specificata alcuna identità, queste modifiche si applicano alle impostazioni DTMF globali:
  
```PowerShell
Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
```

Per ulteriori informazioni, vedere [Get-CsDialInConferencingDtmfConfiguration,](/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) [Set-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)e [New-CsDialInConferencingDtmfConfiguration.](/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)

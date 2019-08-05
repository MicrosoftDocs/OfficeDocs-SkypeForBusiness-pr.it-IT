---
title: Gestione delle impostazioni dei gruppi di risposte a livello di applicazione in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
description: Gestire le impostazioni del gruppo di risposta a livello di applicazione, ad esempio musica in attesa e risponderie, in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 500ed8942fb859ce41340c94d0568e9e87b1c3d6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191129"
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business"></a>Gestione delle impostazioni dei gruppi di risposte a livello di applicazione in Skype for business
 
Gestire le impostazioni del gruppo di risposta a livello di applicazione, ad esempio musica in attesa e risponderie, in Skype for Business Server VoIP aziendale.
  
Le impostazioni a livello di applicazione per l'applicazione Response Group includono la configurazione predefinita per la musica in blocco, il file audio predefinito per la musica in blocco, il periodo di risponderia dell'agente e la configurazione del contesto delle chiamate. Puoi definire solo un set di impostazioni a livello di applicazione per ogni pool. Per visualizzare le impostazioni a livello di applicazione, usare il cmdlet **Get-CsRgsConfiguration** . Per modificare le impostazioni a livello di applicazione, usare il cmdlet **Set-CsRgsConfiguration** .
  
La musica predefinita in attesa viene riprodotta quando una chiamata viene inserita in attesa solo se non è stata definita alcuna musica personalizzata. Il contesto di chiamata è disponibile solo per le code assegnate ai flussi di lavoro interattivi. Se il contesto di chiamata è abilitato, un agente può visualizzare informazioni come il tempo di attesa del chiamante o le domande e le risposte del flusso di lavoro quando viene ricevuta la chiamata.
  
### <a name="to-modify-response-group-application-level-settings"></a>Per modificare le impostazioni a livello di Response Group Application

1. Accedere come membro del gruppo RTCUniversalServerAdmins o come membro di uno dei ruoli amministrativi predefiniti che supportano il gruppo di risposte.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
3. Nella riga di comando eseguire:
    
   ```
   Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
   ```

    Ad esempio:
    
   ```
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
   ```

    Per specificare un file audio da usare come musica predefinita in attesa, è necessario importare prima di tutto il file audio. Ad esempio:
    
   ```
   $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>
   ```

## <a name="see-also"></a>Vedere anche

[Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[Set-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)

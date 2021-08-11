---
title: Gestione delle impostazioni di Response Group a livello di applicazione in Skype for Business
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
ms.assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
description: Gestione delle impostazioni di Response Group a livello di applicazione, ad esempio le impostazioni di musica in attesa e di ringback, in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: a6883247f7be8816a8363c9b2790d6d0e45599484037d23af860b3e0f191dc10
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54337156"
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business"></a>Gestione delle impostazioni di Response Group a livello di applicazione in Skype for Business
 
Gestione delle impostazioni di Response Group a livello di applicazione, ad esempio le impostazioni di musica in attesa e di ringback, in Skype for Business Server VoIP aziendale.
  
Le impostazioni a livello di applicazione per l'applicazione Response Group includono la configurazione di musica di attesa predefinita, il file audio di musica di attesa predefinito, il periodo di tolleranza di ringback dell'agente e la configurazione del contesto di chiamata. È possibile definire solo un set di impostazioni a livello di applicazione per ogni pool. Per visualizzare le impostazioni a livello di applicazione, utilizzare il cmdlet **Get-CsRgsConfiguration**. Per modificare le impostazioni a livello di applicazione, utilizzare il cmdlet **Set-CsRgsConfiguration**.
  
La musica di attesa predefinita viene riprodotta quando una chiamata viene messa in attesa e non è stata definita alcuna musica di attesa personalizzata. Il contesto di chiamata è disponibile solo per le code assegnate ai flussi di lavoro interattivi. Se il contesto di chiamata è abilitato, un agente può visualizzare informazioni come il tempo di attesa del chiamante o le domande e le risposte del flusso di lavoro quando la chiamata viene ricevuta.
  
### <a name="to-modify-response-group-application-level-settings"></a>Per modificare le impostazioni a livello di applicazione di Response Group

1. Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi fare clic su **Skype for Business Server Management Shell.**
    
3. Nella riga di comando digitare il comando seguente:
    
   ```powershell
   Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
   ```

    Ad esempio:
    
   ```powershell
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
   ```

    Per specificare un file audio da utilizzare come musica di attesa predefinita, è necessario prima importare tale file. Ad esempio:
    
   ```powershell
   $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>
   ```

## <a name="see-also"></a>Vedere anche

[Get-CsRgsConfiguration](/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[Set-CsRgsConfiguration](/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[Import-CsRgsAudioFile](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
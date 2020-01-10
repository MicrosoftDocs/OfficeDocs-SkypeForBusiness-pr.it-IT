---
title: Personalizzare la musica di Call Park in attesa di Skype for business
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
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: Personalizzare la musica di Call Park in attesa in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: f071b83e155e2ddfb057619eb95773e4386b67c0
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001006"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a>Personalizzare la musica di Call Park in attesa di Skype for business
 
Personalizzare la musica di Call Park in attesa in Skype for Business Server VoIP aziendale.
  
È possibile specificare il proprio file musicale da usare per la musica in attesa, invece del file di musica predefinito fornito con Skype for Business Server. Per personalizzare la musica in attesa, usare il cmdlet **Set-CsCallParkServiceMusicOnHoldFile** .
  
> [!NOTE]
> Se si Personalizza la musica in attesa e si vuole la stessa musica per più siti, è necessario configurare il file musicale per ogni sito che esegue l'applicazione Parcheggio di chiamata. 
  
### <a name="to-customize-the-music-file"></a>Per personalizzare il file musicale

1. Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in autorizzazioni di **configurazione delegate**.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
3. Eseguire
    
   ```powershell
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > Usa il cmdlet **Get-CsService** per identificare il servizio. Per informazioni dettagliate, vedere [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps). 
  
    L'esempio seguente mostra come ottenere il contenuto di un file, soothingmusic. WMA, come matrice di byte e assegnarlo a una variabile. Il file audio viene quindi assegnato come file di musica in blocco per Call Park. Per informazioni dettagliate, vedere [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).
    
   ```powershell
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a>Vedere anche

[Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)

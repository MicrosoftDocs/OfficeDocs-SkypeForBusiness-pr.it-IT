---
title: Personalizzare la musica del parcheggio di chiamata in attesa inskype for business
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
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: Personalizzare la musica del parcheggio di chiamata in attesa in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 766b51895acda27c0558352968d21a39764b13a6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837076"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a>Personalizzare la musica del parcheggio di chiamata in attesa inskype for business
 
Personalizzare la musica del parcheggio di chiamata in attesa in Skype for Business Server VoIP aziendale.
  
È possibile specificare il proprio file musicale da utilizzare per la musica di attesa, invece del file musicale predefinito fornito con Skype for Business Server. Per personalizzare la musica di attesa, utilizzare il cmdlet **Set-CsCallParkServiceMusicOnHoldFile**.
  
> [!NOTE]
> Se si Personalizza la musica di attesa e si desidera la stessa musica per più siti, è necessario configurare il file musicale per ogni sito che esegue l'applicazione Parcheggio di chiamata. 
  
### <a name="to-customize-the-music-file"></a>Per personalizzare il file musicale

1. Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in **delegate Setup Permissions**.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.
    
3. Eseguire: 
    
   ```powershell
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > Utilizzare il cmdlet **Get-CsService** per identificare il servizio. Per informazioni dettagliate, vedere [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps). 
  
    L'esempio seguente mostra come ottenere il contenuto del file soothingmusic.wma sotto forma di matrice di byte e come assegnarlo a una variabile. Il file audio viene quindi assegnato come file di musica di attesa per Call Park. Per informazioni dettagliate, vedere [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).
    
   ```powershell
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a>Vedere anche

[Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)

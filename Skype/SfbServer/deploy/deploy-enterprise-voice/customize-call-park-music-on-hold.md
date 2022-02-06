---
title: Personalizzare la musica del parcheggio di chiamata in attesa inSkype for Business
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: Personalizzare la musica del parcheggio di chiamata in attesa Skype for Business Server VoIP aziendale.
---

# <a name="customize-call-park-music-on-hold-inskype-for-business"></a>Personalizzare la musica del parcheggio di chiamata in attesa inSkype for Business
 
Personalizzare la musica del parcheggio di chiamata in attesa Skype for Business Server VoIP aziendale.
  
Puoi specificare il tuo file musicale da usare per la musica in attesa, invece del file musicale predefinito fornito con Skype for Business Server. Per personalizzare la musica di attesa, utilizzare il cmdlet **Set-CsCallParkServiceMusicOnHoldFile**.
  
> [!NOTE]
> Se si personalizza la musica di attesa e si desidera la stessa musica per più siti, è necessario configurare il file musicale per ogni sito che esegue l'applicazione Parcheggio di chiamata. 
  
### <a name="to-customize-the-music-file"></a>Per personalizzare il file musicale

1. Accedere al computer in cui Skype for Business Server Management Shell è installato come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in **Delegate Setup Permissions**.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start****, scegliere** Tutti i programmi, **Skype for Business 2015** e quindi fare clic su **Skype for Business Server Management Shell**.
    
3. Correre:
    
   ```powershell
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > Utilizzare il cmdlet **Get-CsService** per identificare il servizio. Per informazioni dettagliate, [vedere Get-CsService](/powershell/module/skype/get-csservice?view=skype-ps). 
  
    L'esempio seguente mostra come ottenere il contenuto del file soothingmusic.wma sotto forma di matrice di byte e come assegnarlo a una variabile. Il file audio viene quindi assegnato come file di musica di attesa per Call Park. Per informazioni dettagliate, [vedere Set-CsCallParkServiceMusicOnHoldFile](/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).
    
   ```powershell
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a>Vedere anche

[Set-CsCallParkServiceMusicOnHoldFile](/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[Get-CsService](/powershell/module/skype/get-csservice?view=skype-ps)
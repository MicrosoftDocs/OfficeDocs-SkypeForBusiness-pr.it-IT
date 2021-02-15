---
title: Personalizzare la musica di attesa del parcheggio di chiamata inSkype for Business
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
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a><span data-ttu-id="d063b-103">Personalizzare la musica di attesa del parcheggio di chiamata inSkype for Business</span><span class="sxs-lookup"><span data-stu-id="d063b-103">Customize Call Park music on hold inSkype for Business</span></span>
 
<span data-ttu-id="d063b-104">Personalizzare la musica del parcheggio di chiamata in attesa in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="d063b-104">Customize the Call Park music on hold in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="d063b-105">Puoi specificare il tuo file musicale da usare per la musica di attesa, invece del file musicale predefinito fornito con Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d063b-105">You can specify your own music file to use for music on hold, instead of the default music file that ships with Skype for Business Server.</span></span> <span data-ttu-id="d063b-106">Per personalizzare la musica di attesa, utilizzare il cmdlet **Set-CsCallParkServiceMusicOnHoldFile**.</span><span class="sxs-lookup"><span data-stu-id="d063b-106">To customize music on hold, use the **Set-CsCallParkServiceMusicOnHoldFile** cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d063b-107">Se si personalizza la musica di attesa e si desidera utilizzare la stessa musica per più siti, è necessario configurare il file musicale per ogni sito che esegue l'applicazione Parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="d063b-107">If you customize music on hold and want the same music for multiple sites, you must configure the music file for each site that runs the Call Park application.</span></span> 
  
### <a name="to-customize-the-music-file"></a><span data-ttu-id="d063b-108">Per personalizzare il file musicale</span><span class="sxs-lookup"><span data-stu-id="d063b-108">To customize the music file</span></span>

1. <span data-ttu-id="d063b-109">Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in Delegare le autorizzazioni di **installazione.**</span><span class="sxs-lookup"><span data-stu-id="d063b-109">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="d063b-110">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="d063b-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="d063b-111">Correre:</span><span class="sxs-lookup"><span data-stu-id="d063b-111">Run:</span></span>
    
   ```powershell
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > <span data-ttu-id="d063b-112">Utilizzare il cmdlet **Get-CsService** per identificare il servizio.</span><span class="sxs-lookup"><span data-stu-id="d063b-112">Use the **Get-CsService** cmdlet to identify the service.</span></span> <span data-ttu-id="d063b-113">Per informazioni dettagliate, [vedere Get-CsService.](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="d063b-113">For details, see [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps).</span></span> 
  
    <span data-ttu-id="d063b-114">L'esempio seguente mostra come ottenere il contenuto del file soothingmusic.wma sotto forma di matrice di byte e come assegnarlo a una variabile.</span><span class="sxs-lookup"><span data-stu-id="d063b-114">The following example shows how to obtain the contents of a file, soothingmusic.wma, as a byte array and assign it to a variable.</span></span> <span data-ttu-id="d063b-115">Il file audio viene quindi assegnato come file di musica di attesa per Call Park.</span><span class="sxs-lookup"><span data-stu-id="d063b-115">Then the audio file is assigned as the music-on-hold file for Call Park.</span></span> <span data-ttu-id="d063b-116">Per informazioni dettagliate, [vedere Set-CsCallParkServiceMusicOnHoldFile.](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="d063b-116">For details, see [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).</span></span>
    
   ```powershell
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a><span data-ttu-id="d063b-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d063b-117">See also</span></span>

[<span data-ttu-id="d063b-118">Set-CsCallParkServiceMusicOnHoldFile</span><span class="sxs-lookup"><span data-stu-id="d063b-118">Set-CsCallParkServiceMusicOnHoldFile</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[<span data-ttu-id="d063b-119">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="d063b-119">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)

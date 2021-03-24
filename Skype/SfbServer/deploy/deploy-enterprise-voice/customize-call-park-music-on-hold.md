---
title: Personalizzare la musica del parcheggio di chiamata in attesa inSkype for Business
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
ms.openlocfilehash: 87dea58d9e339293b047373ac6c44a16bed3bdb3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093044"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a><span data-ttu-id="e2ee7-103">Personalizzare la musica del parcheggio di chiamata in attesa inSkype for Business</span><span class="sxs-lookup"><span data-stu-id="e2ee7-103">Customize Call Park music on hold inSkype for Business</span></span>
 
<span data-ttu-id="e2ee7-104">Personalizzare la musica del parcheggio di chiamata in attesa in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="e2ee7-104">Customize the Call Park music on hold in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="e2ee7-105">Puoi specificare il tuo file musicale da usare per la musica in attesa, invece del file musicale predefinito fornito con Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e2ee7-105">You can specify your own music file to use for music on hold, instead of the default music file that ships with Skype for Business Server.</span></span> <span data-ttu-id="e2ee7-106">Per personalizzare la musica di attesa, utilizzare il cmdlet **Set-CsCallParkServiceMusicOnHoldFile**.</span><span class="sxs-lookup"><span data-stu-id="e2ee7-106">To customize music on hold, use the **Set-CsCallParkServiceMusicOnHoldFile** cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e2ee7-107">Se si personalizza la musica di attesa e si desidera la stessa musica per più siti, è necessario configurare il file musicale per ogni sito che esegue l'applicazione Parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="e2ee7-107">If you customize music on hold and want the same music for multiple sites, you must configure the music file for each site that runs the Call Park application.</span></span> 
  
### <a name="to-customize-the-music-file"></a><span data-ttu-id="e2ee7-108">Per personalizzare il file musicale</span><span class="sxs-lookup"><span data-stu-id="e2ee7-108">To customize the music file</span></span>

1. <span data-ttu-id="e2ee7-109">Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in **Delegate Setup Permissions.**</span><span class="sxs-lookup"><span data-stu-id="e2ee7-109">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="e2ee7-110">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="e2ee7-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="e2ee7-111">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="e2ee7-111">Run:</span></span>
    
   ```powershell
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > <span data-ttu-id="e2ee7-112">Utilizzare il cmdlet **Get-CsService** per identificare il servizio.</span><span class="sxs-lookup"><span data-stu-id="e2ee7-112">Use the **Get-CsService** cmdlet to identify the service.</span></span> <span data-ttu-id="e2ee7-113">Per informazioni dettagliate, [vedere Get-CsService](/powershell/module/skype/get-csservice?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="e2ee7-113">For details, see [Get-CsService](/powershell/module/skype/get-csservice?view=skype-ps).</span></span> 
  
    <span data-ttu-id="e2ee7-114">L'esempio seguente mostra come ottenere il contenuto del file soothingmusic.wma sotto forma di matrice di byte e come assegnarlo a una variabile.</span><span class="sxs-lookup"><span data-stu-id="e2ee7-114">The following example shows how to obtain the contents of a file, soothingmusic.wma, as a byte array and assign it to a variable.</span></span> <span data-ttu-id="e2ee7-115">Il file audio viene quindi assegnato come file di musica di attesa per Call Park.</span><span class="sxs-lookup"><span data-stu-id="e2ee7-115">Then the audio file is assigned as the music-on-hold file for Call Park.</span></span> <span data-ttu-id="e2ee7-116">Per informazioni dettagliate, [vedere Set-CsCallParkServiceMusicOnHoldFile](/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="e2ee7-116">For details, see [Set-CsCallParkServiceMusicOnHoldFile](/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).</span></span>
    
   ```powershell
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a><span data-ttu-id="e2ee7-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2ee7-117">See also</span></span>

[<span data-ttu-id="e2ee7-118">Set-CsCallParkServiceMusicOnHoldFile</span><span class="sxs-lookup"><span data-stu-id="e2ee7-118">Set-CsCallParkServiceMusicOnHoldFile</span></span>](/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[<span data-ttu-id="e2ee7-119">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="e2ee7-119">Get-CsService</span></span>](/powershell/module/skype/get-csservice?view=skype-ps)
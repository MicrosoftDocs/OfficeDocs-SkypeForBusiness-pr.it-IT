---
title: Gestione delle impostazioni dei gruppi di risposte a livello di applicazione in Skype for business
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
ms.assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
description: Gestire le impostazioni del gruppo di risposta a livello di applicazione, ad esempio musica in attesa e risponderie, in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 4c5964d84e5fb84bf1c20c3e43bb0cc4aa25ae17
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001276"
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business"></a><span data-ttu-id="01aa6-103">Gestione delle impostazioni dei gruppi di risposte a livello di applicazione in Skype for business</span><span class="sxs-lookup"><span data-stu-id="01aa6-103">Managing application-level Response Group settings in Skype for Business</span></span>
 
<span data-ttu-id="01aa6-104">Gestire le impostazioni del gruppo di risposta a livello di applicazione, ad esempio musica in attesa e risponderie, in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="01aa6-104">Managing application-level Response Group settings, such as music-on-hold and ringback settings, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="01aa6-105">Le impostazioni a livello di applicazione per l'applicazione Response Group includono la configurazione predefinita per la musica in blocco, il file audio predefinito per la musica in blocco, il periodo di risponderia dell'agente e la configurazione del contesto delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="01aa6-105">Application-level settings for Response Group application include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="01aa6-106">Puoi definire solo un set di impostazioni a livello di applicazione per ogni pool.</span><span class="sxs-lookup"><span data-stu-id="01aa6-106">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="01aa6-107">Per visualizzare le impostazioni a livello di applicazione, usare il cmdlet **Get-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="01aa6-107">To view application-level settings, use the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="01aa6-108">Per modificare le impostazioni a livello di applicazione, usare il cmdlet **Set-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="01aa6-108">To modify the application-level settings, use the **Set-CsRgsConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="01aa6-109">La musica predefinita in attesa viene riprodotta quando una chiamata viene inserita in attesa solo se non è stata definita alcuna musica personalizzata.</span><span class="sxs-lookup"><span data-stu-id="01aa6-109">The default music on hold is played when a call is placed on hold only if no custom music on hold is defined.</span></span> <span data-ttu-id="01aa6-110">Il contesto di chiamata è disponibile solo per le code assegnate ai flussi di lavoro interattivi.</span><span class="sxs-lookup"><span data-stu-id="01aa6-110">Call context is available only for queues assigned to interactive workflows.</span></span> <span data-ttu-id="01aa6-111">Se il contesto di chiamata è abilitato, un agente può visualizzare informazioni come il tempo di attesa del chiamante o le domande e le risposte del flusso di lavoro quando viene ricevuta la chiamata.</span><span class="sxs-lookup"><span data-stu-id="01aa6-111">If call context is enabled, an agent can see information such as caller wait time or workflow questions and answers when the call is received.</span></span>
  
### <a name="to-modify-response-group-application-level-settings"></a><span data-ttu-id="01aa6-112">Per modificare le impostazioni a livello di Response Group Application</span><span class="sxs-lookup"><span data-stu-id="01aa6-112">To modify Response Group application-level settings</span></span>

1. <span data-ttu-id="01aa6-113">Accedere come membro del gruppo RTCUniversalServerAdmins o come membro di uno dei ruoli amministrativi predefiniti che supportano il gruppo di risposte.</span><span class="sxs-lookup"><span data-stu-id="01aa6-113">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="01aa6-114">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="01aa6-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="01aa6-115">Nella riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="01aa6-115">At the command line, run:</span></span>
    
   ```powershell
   Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
   ```

    <span data-ttu-id="01aa6-116">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="01aa6-116">For example:</span></span>
    
   ```powershell
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
   ```

    <span data-ttu-id="01aa6-117">Per specificare un file audio da usare come musica predefinita in attesa, è necessario importare prima di tutto il file audio.</span><span class="sxs-lookup"><span data-stu-id="01aa6-117">To specify an audio file to use as the default music on hold, you need to import the audio file first.</span></span> <span data-ttu-id="01aa6-118">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="01aa6-118">For example:</span></span>
    
   ```powershell
   $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>
   ```

## <a name="see-also"></a><span data-ttu-id="01aa6-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01aa6-119">See also</span></span>

[<span data-ttu-id="01aa6-120">Get-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="01aa6-120">Get-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[<span data-ttu-id="01aa6-121">Set-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="01aa6-121">Set-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[<span data-ttu-id="01aa6-122">Import-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="01aa6-122">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)

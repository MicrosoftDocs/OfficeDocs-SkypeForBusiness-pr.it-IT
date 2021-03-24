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
ms.openlocfilehash: 941164fb3a99f62303b45f587b64e7aff9cb1393
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103472"
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business"></a><span data-ttu-id="4dc57-103">Gestione delle impostazioni di Response Group a livello di applicazione in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="4dc57-103">Managing application-level Response Group settings in Skype for Business</span></span>
 
<span data-ttu-id="4dc57-104">Gestione delle impostazioni di Response Group a livello di applicazione, ad esempio le impostazioni di musica in attesa e di ringback, in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="4dc57-104">Managing application-level Response Group settings, such as music-on-hold and ringback settings, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="4dc57-105">Le impostazioni a livello di applicazione per l'applicazione Response Group includono la configurazione di musica di attesa predefinita, il file audio di musica di attesa predefinito, il periodo di tolleranza di ringback dell'agente e la configurazione del contesto di chiamata.</span><span class="sxs-lookup"><span data-stu-id="4dc57-105">Application-level settings for Response Group application include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="4dc57-106">È possibile definire solo un set di impostazioni a livello di applicazione per ogni pool.</span><span class="sxs-lookup"><span data-stu-id="4dc57-106">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="4dc57-107">Per visualizzare le impostazioni a livello di applicazione, utilizzare il cmdlet **Get-CsRgsConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="4dc57-107">To view application-level settings, use the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="4dc57-108">Per modificare le impostazioni a livello di applicazione, utilizzare il cmdlet **Set-CsRgsConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="4dc57-108">To modify the application-level settings, use the **Set-CsRgsConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="4dc57-p102">La musica di attesa predefinita viene riprodotta quando una chiamata viene messa in attesa e non è stata definita alcuna musica di attesa personalizzata. Il contesto di chiamata è disponibile solo per le code assegnate ai flussi di lavoro interattivi. Se il contesto di chiamata è abilitato, un agente può visualizzare informazioni come il tempo di attesa del chiamante o le domande e le risposte del flusso di lavoro quando la chiamata viene ricevuta.</span><span class="sxs-lookup"><span data-stu-id="4dc57-p102">The default music on hold is played when a call is placed on hold only if no custom music on hold is defined. Call context is available only for queues assigned to interactive workflows. If call context is enabled, an agent can see information such as caller wait time or workflow questions and answers when the call is received.</span></span>
  
### <a name="to-modify-response-group-application-level-settings"></a><span data-ttu-id="4dc57-112">Per modificare le impostazioni a livello di applicazione di Response Group</span><span class="sxs-lookup"><span data-stu-id="4dc57-112">To modify Response Group application-level settings</span></span>

1. <span data-ttu-id="4dc57-113">Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.</span><span class="sxs-lookup"><span data-stu-id="4dc57-113">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="4dc57-114">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="4dc57-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="4dc57-115">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="4dc57-115">At the command line, run:</span></span>
    
   ```powershell
   Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
   ```

    <span data-ttu-id="4dc57-116">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4dc57-116">For example:</span></span>
    
   ```powershell
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
   ```

    <span data-ttu-id="4dc57-p103">Per specificare un file audio da utilizzare come musica di attesa predefinita, è necessario prima importare tale file. Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4dc57-p103">To specify an audio file to use as the default music on hold, you need to import the audio file first. For example:</span></span>
    
   ```powershell
   $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>
   ```

## <a name="see-also"></a><span data-ttu-id="4dc57-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4dc57-119">See also</span></span>

[<span data-ttu-id="4dc57-120">Get-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="4dc57-120">Get-CsRgsConfiguration</span></span>](/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[<span data-ttu-id="4dc57-121">Set-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="4dc57-121">Set-CsRgsConfiguration</span></span>](/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[<span data-ttu-id="4dc57-122">Import-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="4dc57-122">Import-CsRgsAudioFile</span></span>](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
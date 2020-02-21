---
title: 'Lync Server 2013: gestione delle impostazioni del gruppo di risposta a livello di applicazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing application-level Response Group settings
ms:assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721843(v=OCS.15)
ms:contentKeyID: 49733776
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53d8b89177a69da0df49ebf42f026493742f3352
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-application-level-response-group-settings-in-lync-server-2013"></a><span data-ttu-id="81b1d-102">Gestione delle impostazioni dei Response Group a livello di applicazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81b1d-102">Managing application-level Response Group settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81b1d-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="81b1d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="81b1d-104">Le impostazioni a livello di applicazione per l'applicazione Response Group includono la configurazione predefinita per la musica in attesa, il file audio predefinito per la musica in attesa, il periodo di richiamata dell'agente e la configurazione del contesto delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="81b1d-104">Application-level settings for Response Group application include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="81b1d-105">È possibile definire solo un set di impostazioni a livello di applicazione per ogni pool.</span><span class="sxs-lookup"><span data-stu-id="81b1d-105">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="81b1d-106">Per visualizzare le impostazioni a livello di applicazione, utilizzare il cmdlet **Get-CsRgsConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="81b1d-106">To view application-level settings, use the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="81b1d-107">Per modificare le impostazioni a livello di applicazione, utilizzare il cmdlet **Set-CsRgsConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="81b1d-107">To modify the application-level settings, use the **Set-CsRgsConfiguration** cmdlet.</span></span>

<span data-ttu-id="81b1d-p102">La musica di attesa predefinita viene riprodotta quando una chiamata viene messa in attesa e non è stata definita alcuna musica di attesa personalizzata. Il contesto di chiamata è disponibile solo per le code assegnate ai flussi di lavoro interattivi. Se il contesto di chiamata è abilitato, un agente può visualizzare informazioni come il tempo di attesa del chiamante o le domande e le risposte del flusso di lavoro quando la chiamata viene ricevuta.</span><span class="sxs-lookup"><span data-stu-id="81b1d-p102">The default music on hold is played when a call is placed on hold only if no custom music on hold is defined. Call context is available only for queues assigned to interactive workflows. If call context is enabled, an agent can see information such as caller wait time or workflow questions and answers when the call is received.</span></span>

<div>

## <a name="to-modify-response-group-application-level-settings"></a><span data-ttu-id="81b1d-111">Per modificare le impostazioni a livello di applicazione Response Group</span><span class="sxs-lookup"><span data-stu-id="81b1d-111">To modify Response Group application-level settings</span></span>

1.  <span data-ttu-id="81b1d-112">Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.</span><span class="sxs-lookup"><span data-stu-id="81b1d-112">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="81b1d-113">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="81b1d-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="81b1d-114">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="81b1d-114">At the command line, run:</span></span>
    
        Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
    
    <span data-ttu-id="81b1d-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="81b1d-115">For example:</span></span>
    
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
    
    <span data-ttu-id="81b1d-p103">Per specificare un file audio da utilizzare come musica di attesa predefinita, è necessario prima importare tale file. Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="81b1d-p103">To specify an audio file to use as the default music on hold, you need to import the audio file first. For example:</span></span>
    
        $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="81b1d-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81b1d-118">See Also</span></span>


[<span data-ttu-id="81b1d-119">Get-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="81b1d-119">Get-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration)  
[<span data-ttu-id="81b1d-120">Set-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="81b1d-120">Set-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsConfiguration)  
[<span data-ttu-id="81b1d-121">Import-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="81b1d-121">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: gestire le impostazioni del gruppo di risposte a livello di applicazione'
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
ms.openlocfilehash: ffce659c2c4dc6c91ba4e4935b72c15e4cef4da5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-application-level-response-group-settings-in-lync-server-2013"></a><span data-ttu-id="a1fd3-102">Gestione delle impostazioni dei gruppi di risposte a livello di applicazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1fd3-102">Managing application-level Response Group settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1fd3-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a1fd3-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a1fd3-104">Le impostazioni a livello di applicazione per l'applicazione Response Group includono la configurazione predefinita per la musica in blocco, il file audio predefinito per la musica in blocco, il periodo di risponderia dell'agente e la configurazione del contesto delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="a1fd3-104">Application-level settings for Response Group application include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="a1fd3-105">Puoi definire solo un set di impostazioni a livello di applicazione per ogni pool.</span><span class="sxs-lookup"><span data-stu-id="a1fd3-105">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="a1fd3-106">Per visualizzare le impostazioni a livello di applicazione, usare il cmdlet **Get-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="a1fd3-106">To view application-level settings, use the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="a1fd3-107">Per modificare le impostazioni a livello di applicazione, usare il cmdlet **Set-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="a1fd3-107">To modify the application-level settings, use the **Set-CsRgsConfiguration** cmdlet.</span></span>

<span data-ttu-id="a1fd3-108">La musica predefinita in attesa viene riprodotta quando una chiamata viene inserita in attesa solo se non è stata definita alcuna musica personalizzata.</span><span class="sxs-lookup"><span data-stu-id="a1fd3-108">The default music on hold is played when a call is placed on hold only if no custom music on hold is defined.</span></span> <span data-ttu-id="a1fd3-109">Il contesto di chiamata è disponibile solo per le code assegnate ai flussi di lavoro interattivi.</span><span class="sxs-lookup"><span data-stu-id="a1fd3-109">Call context is available only for queues assigned to interactive workflows.</span></span> <span data-ttu-id="a1fd3-110">Se il contesto di chiamata è abilitato, un agente può visualizzare informazioni come il tempo di attesa del chiamante o le domande e le risposte del flusso di lavoro quando viene ricevuta la chiamata.</span><span class="sxs-lookup"><span data-stu-id="a1fd3-110">If call context is enabled, an agent can see information such as caller wait time or workflow questions and answers when the call is received.</span></span>

<div>

## <a name="to-modify-response-group-application-level-settings"></a><span data-ttu-id="a1fd3-111">Per modificare le impostazioni a livello di Response Group Application</span><span class="sxs-lookup"><span data-stu-id="a1fd3-111">To modify Response Group application-level settings</span></span>

1.  <span data-ttu-id="a1fd3-112">Accedere come membro del gruppo RTCUniversalServerAdmins o come membro di uno dei ruoli amministrativi predefiniti che supportano il gruppo di risposte.</span><span class="sxs-lookup"><span data-stu-id="a1fd3-112">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="a1fd3-113">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="a1fd3-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="a1fd3-114">Nella riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="a1fd3-114">At the command line, run:</span></span>
    
        Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
    
    <span data-ttu-id="a1fd3-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a1fd3-115">For example:</span></span>
    
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
    
    <span data-ttu-id="a1fd3-116">Per specificare un file audio da usare come musica predefinita in attesa, è necessario importare prima di tutto il file audio.</span><span class="sxs-lookup"><span data-stu-id="a1fd3-116">To specify an audio file to use as the default music on hold, you need to import the audio file first.</span></span> <span data-ttu-id="a1fd3-117">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a1fd3-117">For example:</span></span>
    
        $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a1fd3-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1fd3-118">See Also</span></span>


[<span data-ttu-id="a1fd3-119">Get-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="a1fd3-119">Get-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration)  
[<span data-ttu-id="a1fd3-120">Set-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="a1fd3-120">Set-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsConfiguration)  
[<span data-ttu-id="a1fd3-121">Import-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="a1fd3-121">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


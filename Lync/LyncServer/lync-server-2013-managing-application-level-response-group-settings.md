---
title: 'Lync Server 2013: gestire le impostazioni del gruppo di risposte a livello di applicazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing application-level Response Group settings
ms:assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721843(v=OCS.15)
ms:contentKeyID: 49733776
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bac03eaafc40ccd86aca8514319e3bf632ea6a83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981849"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-application-level-response-group-settings-in-lync-server-2013"></a>Gestione delle impostazioni dei gruppi di risposte a livello di applicazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Le impostazioni a livello di applicazione per l'applicazione Response Group includono la configurazione predefinita per la musica in blocco, il file audio predefinito per la musica in blocco, il periodo di risponderia dell'agente e la configurazione del contesto delle chiamate. Puoi definire solo un set di impostazioni a livello di applicazione per ogni pool. Per visualizzare le impostazioni a livello di applicazione, usare il cmdlet **Get-CsRgsConfiguration** . Per modificare le impostazioni a livello di applicazione, usare il cmdlet **Set-CsRgsConfiguration** .

La musica predefinita in attesa viene riprodotta quando una chiamata viene inserita in attesa solo se non è stata definita alcuna musica personalizzata. Il contesto di chiamata è disponibile solo per le code assegnate ai flussi di lavoro interattivi. Se il contesto di chiamata è abilitato, un agente può visualizzare informazioni come il tempo di attesa del chiamante o le domande e le risposte del flusso di lavoro quando viene ricevuta la chiamata.

<div>

## <a name="to-modify-response-group-application-level-settings"></a>Per modificare le impostazioni a livello di Response Group Application

1.  Accedere come membro del gruppo RTCUniversalServerAdmins o come membro di uno dei ruoli amministrativi predefiniti che supportano il gruppo di risposte.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Nella riga di comando eseguire:
    
        Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
    
    Ad esempio:
    
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
    
    Per specificare un file audio da usare come musica predefinita in attesa, è necessario importare prima di tutto il file audio. Ad esempio:
    
        $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration)  
[Set-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsConfiguration)  
[Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: cmdlet per la configurazione del trunking'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Trunking configuration cmdlets
ms:assetid: 2c36b03a-b80f-4321-a448-6ba26b9357f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416489(v=OCS.15)
ms:contentKeyID: 48183703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a734e8fdc169740cfe54282994e63190d63065a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518923"
---
# <a name="trunking-configuration-cmdlets-in-lync-server-2013"></a>Cmdlet per la configurazione del trunking in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-08_

I cmdlet per la configurazione dei trunk consentono di definire le impostazioni di un'entità peer di trunking, ad esempio un gateway PSTN (Public Switched Telephone Network), un sistema IP-PBX (Public Branch Exchange) o un servizio SBC (Session Border Controller) presso il provider di servizi. Tali impostazioni consentono di configurare diversi aspetti, ad esempio se abilitare o meno il bypass multimediale in questo trunk, se i pacchetti RTCP (Real-time Transport Control Protocol) devono essere inviati o meno in determinate condizioni e se richiedere o meno la crittografia SRTP (Secure Real-Time Protocol).

<div>

## <a name="trunking-configuration-cmdlets"></a>Cmdlet per la configurazione del trunking

Utilizzare i cmdlet seguenti per la configurazione dei trunk.

**Configurazione del trunking**

  - [Test-CsInterTrunkRouting](https://technet.microsoft.com/library/JJ204741(v=OCS.15))

<!-- end list -->

  - [Get-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ204962(v=OCS.15))

  - [New-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ205097(v=OCS.15))

  - [Remove-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ204836(v=OCS.15))

  - [Set-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ205400(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg398104(v=OCS.15))

  - <span></span>  
    [New-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg412803(v=OCS.15))

  - <span></span>  
    [Remove-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg398556(v=OCS.15))

  - <span></span>  
    [Set-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg413073(v=OCS.15))

<!-- end list -->

  - [Get-CsTrunk](https://technet.microsoft.com/library/JJ205244(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg398224(v=OCS.15))

  - <span></span>  
    [New-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg413021(v=OCS.15))

  - <span></span>  
    [Remove-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15))

  - <span></span>  
    [Set-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg398238(v=OCS.15))

  - <span></span>  
    [Test-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg398137(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsVoiceRegex](https://technet.microsoft.com/library/Gg412751(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Blog di PowerShell per Lync Server](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


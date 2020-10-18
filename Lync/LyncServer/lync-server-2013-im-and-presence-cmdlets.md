---
title: 'Lync Server 2013: cmdlet per la messaggistica istantanea e la presenza'
description: 'Lync Server 2013: cmdlet per la messaggistica istantanea e la presenza.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IM and presence cmdlets
ms:assetid: 7b882480-f3d5-44a2-bb75-fffb7e5caede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398611(v=OCS.15)
ms:contentKeyID: 48184589
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b6447219006737ba77cddd76aad0ac96368dab3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573302"
---
# <a name="im-and-presence-cmdlets-in-lync-server-2013"></a>Cmdlet per la messaggistica istantanea e la presenza in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-06-26_

I cmdlet per la messaggistica istantanea e la presenza consentono di gestire le funzionalità client tramite Windows PowerShell. È possibile impostare criteri di presenza applicabili agli utenti nell'ambito globale, a livello di sito o per utente. È inoltre possibile configurare diverse funzionalità per la privacy e la messaggistica istantanea.

<div>

## <a name="im-and-presence-cmdlets"></a>Cmdlet per la messaggistica istantanea e la presenza

Per configurare la messaggistica istantanea e la presenza utilizzare i cmdlet seguenti:

  - <span></span>  
    [Get-CsPresencePolicy](https://technet.microsoft.com/library/Gg398463(v=OCS.15))

  - <span></span>  
    [Grant-CsPresencePolicy](https://technet.microsoft.com/library/Gg398571(v=OCS.15))

  - <span></span>  
    [New-CsPresencePolicy](https://technet.microsoft.com/library/Gg412747(v=OCS.15))

  - <span></span>  
    [Remove-CsPresencePolicy](https://technet.microsoft.com/library/Gg399070(v=OCS.15))

  - <span></span>  
    [Set-CsPresencePolicy](https://technet.microsoft.com/library/Gg425782(v=OCS.15))

<!-- end list -->

  - [Get-CsPresenceProvider](https://technet.microsoft.com/library/JJ204705(v=OCS.15))

  - [New-CsPresenceProvider](https://technet.microsoft.com/library/JJ204895(v=OCS.15))

  - [Remove-CsPresenceProvider](https://technet.microsoft.com/library/JJ205036(v=OCS.15))

  - [Set-CsPresenceProvider](https://technet.microsoft.com/library/JJ204833(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg413002(v=OCS.15))

  - <span></span>  
    [New-CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg398807(v=OCS.15))

  - <span></span>  
    [Remove-CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg425821(v=OCS.15))

  - <span></span>  
    [Set-CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg398484(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-CsUserServer](https://technet.microsoft.com/library/Gg413026(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398133(v=OCS.15))

  - <span></span>  
    [New-CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg412926(v=OCS.15))

  - <span></span>  
    [Remove-CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398722(v=OCS.15))

  - <span></span>  
    [Set-CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398340(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg398527(v=OCS.15))

  - <span></span>  
    [New-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg425897(v=OCS.15))

  - <span></span>  
    [Remove-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg413064(v=OCS.15))

  - <span></span>  
    [Set-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg425736(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398980(v=OCS.15))

  - <span></span>  
    [New-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398244(v=OCS.15))

  - <span></span>  
    [Remove-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398171(v=OCS.15))

  - <span></span>  
    [Set-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg412960(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsGroupExpansion](https://technet.microsoft.com/library/Gg399009(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsGroupIM](https://technet.microsoft.com/library/Gg398273(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsIM](https://technet.microsoft.com/library/Gg425802(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsP2PAV](https://technet.microsoft.com/library/Gg412821(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsPresence](https://technet.microsoft.com/library/Gg398148(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Cmdlet per la gestione dei client in Lync Server 2013](lync-server-2013-client-management-cmdlets.md)  


[Blog di PowerShell per Lync Server](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


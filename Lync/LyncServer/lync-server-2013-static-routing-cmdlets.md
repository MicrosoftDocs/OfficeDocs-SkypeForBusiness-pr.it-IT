---
title: 'Lync Server 2013: cmdlet per il routing statico'
description: 'Lync Server 2013: cmdlet per il routing statico.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Static routing cmdlets
ms:assetid: 71d5e0cd-8412-4383-818a-95b851a4da4b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416492(v=OCS.15)
ms:contentKeyID: 48184496
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33fd251f63111cebb9297287252e666a7e10f0e1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546342"
---
# <a name="static-routing-cmdlets-in-lync-server-2013"></a>Cmdlet per il routing statico in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-06-20_

Con le route statiche gli amministratori possono predeterminare le route di rete utilizzate dai messaggi SIP. Quando riceve un messaggio, il server ne verifica l'indirizzo e quindi lo inoltra al server dell'hop successivo preconfigurato da un amministratore. Se configurate correttamente, le route statiche contribuiscono a garantire un recapito tempestivo e accurato dei messaggi, con un sovraccarico minimo sui server.

<div>

## <a name="static-routing-cmdlets"></a>Cmdlet per il routing statico

Se non diversamente indicato dal personale del supporto tecnico Microsoft, le route statiche configurate per Microsoft Lync Server 2013 devono essere create utilizzando il cmdlet [New-CsStaticRoute](https://technet.microsoft.com/library/Gg398265(v=OCS.15)) . Dopo la creazione di una route, è possibile utilizzare i cmdlet CsStaticRoutingConfiguration per aggiungerla a un insieme di configurazioni di routing statico.

**Routing statico**

  - <span></span>  
    [Get-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg398130(v=OCS.15))

  - <span></span>  
    [New-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg413041(v=OCS.15))

  - <span></span>  
    [Remove-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg412932(v=OCS.15))

  - <span></span>  
    [Set-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg425895(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsStaticRoute](https://technet.microsoft.com/library/Gg398265(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398754(v=OCS.15))

  - <span></span>  
    [New-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg425811(v=OCS.15))

  - <span></span>  
    [Remove-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398668(v=OCS.15))

  - <span></span>  
    [Set-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398724(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsSipProxyCustom](https://technet.microsoft.com/library/Gg425904(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsSipProxyRealm](https://technet.microsoft.com/library/Gg413084(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsSipProxyTCP](https://technet.microsoft.com/library/Gg425745(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsSipProxyTLS](https://technet.microsoft.com/library/Gg398629(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsSipProxyTransport](https://technet.microsoft.com/library/Gg398489(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsSipProxyUseDefault](https://technet.microsoft.com/library/Gg398274(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsSipProxyUseDefaultCert](https://technet.microsoft.com/library/Gg425858(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsIssuedCertIdconsente](https://technet.microsoft.com/library/Gg425814(v=OCS.15))

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


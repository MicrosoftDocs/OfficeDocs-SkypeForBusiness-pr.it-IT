---
title: 'Lync Server 2013: cmdlet per telefoni e dispositivi'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Phones and devices cmdlets
ms:assetid: 6ebeba4b-43ce-4a31-9060-50d249b7564c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415657(v=OCS.15)
ms:contentKeyID: 48184467
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e5e698c23c87f679302c6612bec138bcbae39f71
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755196"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phones-and-devices-cmdlets-in-lync-server-2013"></a>Cmdlet per telefoni e dispositivi in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-06-28_

Microsoft Lync Server 2013 offre numerosi cmdlet che consentono di gestire telefoni e altri dispositivi hardware. Ciò include elementi come telefoni VoIP (Voice over IP); telefoni per area comune (ad esempio, un telefono in una sala di attesa, una caffetteria o un altro luogo pubblico); e anche telefoni analogici, telefoni che non sono in grado di eseguire Lync Phone Edition.

<div>

## <a name="phones-and-devices-cmdlets"></a>Cmdlet per telefoni e dispositivi

I cmdlet **CsDeviceUpdate** vengono usati per gestire il servizio Web Update per dispositivi, un componente Lync Server che consente agli amministratori di distribuire gli aggiornamenti del firmware ai telefoni e ad altri dispositivi che usano Lync Phone Edition.

  - <span></span>  
    [Get-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg398748(v=OCS.15))

  - <span></span>  
    [Move-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg398816(v=OCS.15))

  - <span></span>  
    [New-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg412937(v=OCS.15))

  - <span></span>  
    [Remove-CsAnalogDevice](rehttps://technet.microsoft.com/en-us/library/Gg398816(v=OCS.15))

  - <span></span>  
    [Set-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg412843(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg412934(v=OCS.15))

  - <span></span>  
    [Move-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg412837(v=OCS.15))

  - <span></span>  
    [New-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg398430(v=OCS.15))

  - <span></span>  
    [Remove-CsCommonAreaPhone](rehttps://technet.microsoft.com/en-us/library/Gg412837(v=OCS.15))

  - <span></span>  
    [Set-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg398579(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398070(v=OCS.15))

  - <span></span>  
    [New-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398445(v=OCS.15))

  - <span></span>  
    [Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398249(v=OCS.15))

  - <span></span>  
    [Set-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg413042(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Import-CsDeviceUpdate](https://technet.microsoft.com/en-us/library/Gg398861(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg399030(v=OCS.15))

  - <span></span>  
    [New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg425761(v=OCS.15))

  - <span></span>  
    [Remove-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg425933(v=OCS.15))

  - <span></span>  
    [Set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg398320(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Clear-CsDeviceUpdateFile](https://technet.microsoft.com/en-us/library/Gg425835(v=OCS.15))

  - <span></span>  
    [Clear-CsDeviceUpdateLog](https://technet.microsoft.com/en-us/library/Gg412738(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Approva-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398949(v=OCS.15))

  - <span></span>  
    [Get-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398215(v=OCS.15))

  - <span></span>  
    [Remove-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg425930(v=OCS.15))

  - <span></span>  
    [Reset-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398181(v=OCS.15))

  - <span></span>  
    [Ripristinare-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398305(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsPhoneBootstrap](https://technet.microsoft.com/en-us/library/Gg412852(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsTestDevice](https://technet.microsoft.com/en-us/library/Gg398304(v=OCS.15))

  - <span></span>  
    [New-CsTestDevice](https://technet.microsoft.com/en-us/library/Gg425899(v=OCS.15))

  - <span></span>  
    [Remove-CsTestDevice](https://technet.microsoft.com/en-us/library/Gg398790(v=OCS.15))

  - <span></span>  
    [Set-CsTestDevice](https://technet.microsoft.com/en-us/library/Gg398156(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Blog di PowerShell per Lync Server](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


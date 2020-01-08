---
title: Eseguire la migrazione dei dispositivi analogici
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate analog devices
ms:assetid: ad072916-87ed-4d44-8289-aab87da86250
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721846(v=OCS.15)
ms:contentKeyID: 49733779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66866ee7cb6dafecb2c30b53d04a50f849f09c94
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979704"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-analog-devices"></a>Eseguire la migrazione dei dispositivi analogici

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-16_

Lync Server offre il supporto per i dispositivi analogici. In particolare, i dispositivi analogici supportati sono telefoni audio analogici e fax analogici. Puoi configurare i gateway qualificati per supportare l'uso di dispositivi analogici nell'ambiente Lync Server. Dopo la migrazione da Lync Server 2010 a Lync Server 2013, è anche necessario eseguire la migrazione degli oggetti contatto associati ai dispositivi analogici. USA Lync Server Management Shell per recuperare prima tutti gli oggetti contatto associati ai dispositivi analogici di Lync Server 2010 e quindi spostarli nel pool di Lync Server 2013.

<div>

## <a name="to-migrate-analog-devices"></a>Per eseguire la migrazione dei dispositivi analogici

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Nella riga di comando digitare:
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net

3.  Verificare che tutti gli oggetti contatto siano stati spostati nel pool di Lync Server 2013. Nella riga di comando digitare:
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}

4.  Verificare che tutti gli oggetti contatto siano ora associati al pool Lync Server 2013.

</div>

</div>

<span> </span>

</div>

</div>

</div>

